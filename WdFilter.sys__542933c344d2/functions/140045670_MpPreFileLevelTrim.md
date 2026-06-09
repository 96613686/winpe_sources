# MpPreFileLevelTrim

- ea: `0x140045670`
- end: `0x1400459b7`
- name: `MpPreFileLevelTrim`
- size: `839`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140044520`

## callees

- `0x140002450`
- `0x1400051bc`
- `0x1400068fc`
- `0x1400118d0`
- `0x140030060`
- `0x14003a1b0`
- `0x14003ee80`
- `0x140040388`
- `0x140045670`
- `0x140046e30`
- `0x1400471ac`
- `0x14008ab44`

## import_xrefs

- `ntoskrnl!PsGetCurrentProcessId` at `0x14004591f`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14004597c`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14004591f`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14004597c`
- `FLTMGR!FltGetFileNameInformation` at `0x14004573e`
- `FLTMGR!FltGetFileNameInformation` at `0x14004573e`
- `FLTMGR!FltGetFileSystemType` at `0x1400456e4`
- `FLTMGR!FltGetFileSystemType` at `0x1400456e4`
- `FLTMGR!FltIsDirectory` at `0x14004581b`
- `FLTMGR!FltIsDirectory` at `0x14004581b`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400457cf`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400457cf`

## string_xrefs

- `0x14004599e`: `[Mini-filter] Denied access to file [%wZ] from process [%wZ][Pid:%u]. DynamicFsHardeningEnabled[%d].`

## pseudocode

```c
__int64 __fastcall MpPreFileLevelTrim(PFLT_CALLBACK_DATA CallbackData, __int64 a2)
{
  unsigned int v4; // ebx
  struct _KPROCESS *RequestorProcess; // rax
  int v6; // esi
  int v7; // r12d
  struct _FLT_INSTANCE *v9; // rdx
  struct _FILE_OBJECT *v10; // rcx
  char IsAMPath; // al
  char CurrentProcessId; // al
  HANDLE v13; // rax
  __int64 v14; // [rsp+20h] [rbp-50h]
  __int64 v15; // [rsp+40h] [rbp-30h]
  int v16; // [rsp+48h] [rbp-28h]
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+50h] [rbp-20h] BYREF
  unsigned __int8 IsDirectory[4]; // [rsp+58h] [rbp-18h] BYREF
  enum _FLT_FILESYSTEM_TYPE FileSystemType; // [rsp+5Ch] [rbp-14h] BYREF

  v15 = 0;
  FileSystemType = FLT_FSTYPE_UNKNOWN;
  v4 = 1;
  FileNameInformation = 0;
  RequestorProcess = (struct _KPROCESS *)MpGetRequestorProcess(CallbackData);
  if ( !RequestorProcess || (int)MpGetProcessContextByObject(RequestorProcess) < 0 )
    return v4;
  _mm_lfence();
  v6 = FltGetFileSystemType(*(PVOID *)(a2 + 24), &FileSystemType);
  v7 = *(_DWORD *)(MpData + 868) & 0x4000;
  v16 = v7;
  if ( (unsigned __int8)MpCheckForAmHardening((_DWORD)CallbackData, a2, 0, v15, FileSystemType == FLT_FSTYPE_MUP) )
  {
    _mm_lfence();
    v6 = FltGetFileNameInformation(CallbackData, 0x101u, &FileNameInformation);
    if ( v6 >= 0 )
    {
      if ( v7 )
      {
        v9 = *(struct _FLT_INSTANCE **)(a2 + 24);
        v10 = *(struct _FILE_OBJECT **)(a2 + 32);
        IsDirectory[0] = 0;
        v6 = FltIsDirectory(v10, v9, IsDirectory);
        if ( v6 < 0 )
          IsDirectory[0] = 0;
        v7 = v16;
        IsAMPath = 1;
      }
      else
      {
        IsAMPath = MpIsAMPath(v15, FileNameInformation);
      }
      if ( IsAMPath )
      {
        _mm_lfence();
        CallbackData->IoStatus.Status = -1073741790;
        v4 = 4;
        CallbackData->IoStatus.Information = 0;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
        {
          _mm_lfence();
          CurrentProcessId = (unsigned __int8)PsGetCurrentProcessId();
          WPP_SF_ZZDd(
            WPP_GLOBAL_Control->AttachedDevice,
            29,
            (unsigned int)WPP_1bce4dab9b883aab79efa6fb296bde6e_Traceguids,
            &CallbackData->Iopb->TargetFileObject->FileName,
            0,
            CurrentProcessId,
            v7 != 0);
        }
        v13 = PsGetCurrentProcessId();
        LODWORD(v14) = v7 != 0;
        MpLogPrintfW(
          L"[Mini-filter] Denied access to file [%wZ] from process [%wZ][Pid:%u]. DynamicFsHardeningEnabled[%d].",
          &CallbackData->Iopb->TargetFileObject->FileName,
          0,
          v13,
          v14);
        goto LABEL_11;
      }
    }
    else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      _mm_lfence();
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        28,
        WPP_1bce4dab9b883aab79efa6fb296bde6e_Traceguids,
        KeGetCurrentThread(),
        v6);
    }
  }
  if ( v6 == -1073741536 || v6 == -1073741749 )
  {
    CallbackData->IoStatus.Status = v6;
    v4 = 4;
    CallbackData->IoStatus.Information = 0;
  }
LABEL_11:
  if ( FileNameInformation )
    FltReleaseFileNameInformation(FileNameInformation);
  return v4;
}

```

## disassembly

```asm
0x140045670  mov     [rsp-38h+arg_10], rbx
0x140045675  push    rbp
0x140045676  push    rsi
0x140045677  push    rdi
0x140045678  push    r12
0x14004567a  push    r13
0x14004567c  push    r14
0x14004567e  push    r15
0x140045680  mov     rbp, rsp
0x140045683  sub     rsp, 70h
0x140045687  mov     rax, cs:__security_cookie
0x14004568e  xor     rax, rsp
0x140045691  mov     [rbp+var_10], rax
0x140045695  mov     r15, rdx
0x140045698  mov     [rbp+var_30], 0
0x1400456a0  mov     r14, rcx
0x1400456a3  mov     [rbp+FileSystemType], 0
0x1400456aa  mov     ebx, 1
0x1400456af  mov     [rbp+FileNameInformation], 0
0x1400456b7  call    MpGetRequestorProcess
0x1400456bc  test    rax, rax
0x1400456bf  jz      loc_1400457DB
0x1400456c5  lea     rdx, [rbp+var_30]
0x1400456c9  mov     rcx, rax; Process
0x1400456cc  call    MpGetProcessContextByObject
0x1400456d1  test    eax, eax
0x1400456d3  js      loc_1400457DB
0x1400456d9  lfence
0x1400456dc  mov     rcx, [r15+18h]; FltObject
0x1400456e0  lea     rdx, [rbp+FileSystemType]; FileSystemType
0x1400456e4  call    cs:__imp_FltGetFileSystemType
0x1400456eb  nop     dword ptr [rax+rax+00h]
0x1400456f0  mov     rdi, [rbp+var_30]
0x1400456f4  mov     rdx, r15
0x1400456f7  mov     esi, eax
0x1400456f9  mov     r9, rdi
0x1400456fc  mov     rax, cs:MpData
0x140045703  mov     rcx, r14
0x140045706  mov     r12d, [rax+364h]
0x14004570d  and     r12d, 4000h
0x140045714  cmp     [rbp+FileSystemType], 0Dh
0x140045718  mov     [rbp+var_28], r12d
0x14004571c  setz    al
0x14004571f  xor     r8d, r8d
0x140045722  mov     byte ptr [rsp+70h+var_50], al
0x140045726  call    MpCheckForAmHardening
0x14004572b  test    al, al
0x14004572d  jz      short loc_140045798
0x14004572f  lfence
0x140045732  lea     r8, [rbp+FileNameInformation]; FileNameInformation
0x140045736  mov     edx, 101h; NameOptions
0x14004573b  mov     rcx, r14; CallbackData
0x14004573e  call    cs:__imp_FltGetFileNameInformation
0x140045745  nop     dword ptr [rax+rax+00h]
0x14004574a  mov     esi, eax
0x14004574c  test    eax, eax
0x14004574e  jns     loc_140045802
0x140045754  mov     rcx, cs:WPP_GLOBAL_Control
0x14004575b  lea     rax, WPP_GLOBAL_Control
0x140045762  cmp     rcx, rax
0x140045765  jz      short loc_140045798
0x140045767  mov     eax, [rcx+2Ch]
0x14004576a  test    bl, al
0x14004576c  jz      short loc_140045798
0x14004576e  lfence
0x140045771  mov     r9, gs:188h
0x14004577a  lea     edx, [rbx+1Bh]
0x14004577d  mov     rcx, cs:WPP_GLOBAL_Control
0x140045784  lea     r8, WPP_1bce4dab9b883aab79efa6fb296bde6e_Traceguids
0x14004578b  mov     dword ptr [rsp+70h+var_50], esi
0x14004578f  mov     rcx, [rcx+18h]
0x140045793  call    WPP_SF_qD
0x140045798  cmp     esi, 0C0000120h
0x14004579e  jz      short loc_1400457A8
0x1400457a0  cmp     esi, 0C000004Bh
0x1400457a6  jnz     short loc_1400457B9
0x1400457a8  mov     [r14+18h], esi
0x1400457ac  mov     ebx, 4
0x1400457b1  mov     qword ptr [r14+20h], 0
0x1400457b9  test    rdi, rdi
0x1400457bc  jz      short loc_1400457C6
0x1400457be  mov     rcx, rdi
0x1400457c1  call    MpReleaseProcessContext
0x1400457c6  mov     rcx, [rbp+FileNameInformation]; FileNameInformation
0x1400457ca  test    rcx, rcx
0x1400457cd  jz      short loc_1400457DB
0x1400457cf  call    cs:__imp_FltReleaseFileNameInformation
0x1400457d6  nop     dword ptr [rax+rax+00h]
0x1400457db  mov     eax, ebx
0x1400457dd  mov     rcx, [rbp+var_10]
0x1400457e1  xor     rcx, rsp; StackCookie
0x1400457e4  call    __security_check_cookie
0x1400457e9  mov     rbx, [rsp+70h+arg_10]
0x1400457f1  add     rsp, 70h
0x1400457f5  pop     r15
0x1400457f7  pop     r14
0x1400457f9  pop     r13
0x1400457fb  pop     r12
0x1400457fd  pop     rdi
0x1400457fe  pop     rsi
0x1400457ff  pop     rbp
0x140045800  retn
0x140045802  test    r12d, r12d
0x140045805  jz      loc_1400458C3
0x14004580b  mov     rdx, [r15+18h]; Instance
0x14004580f  lea     r8, [rbp+IsDirectory]; IsDirectory
0x140045813  mov     rcx, [r15+20h]; FileObject
0x140045817  mov     [rbp+IsDirectory], 0
0x14004581b  call    cs:__imp_FltIsDirectory
0x140045822  nop     dword ptr [rax+rax+00h]
0x140045827  mov     esi, eax
0x140045829  test    eax, eax
0x14004582b  jns     short loc_140045836
0x14004582d  xor     r12b, r12b
0x140045830  mov     [rbp+IsDirectory], r12b
0x140045834  jmp     short loc_14004583A
0x140045836  mov     r12b, [rbp+IsDirectory]
0x14004583a  mov     r9, [r15+18h]
0x14004583e  xor     r15d, r15d
0x140045841  cmp     cs:MpFsHardeningData, r15
0x140045848  mov     r13, [rbp+FileNameInformation]
0x14004584c  jz      short loc_1400458B7
0x14004584e  test    rdi, rdi
0x140045851  jz      short loc_1400458B7
0x140045853  test    r13, r13
0x140045856  jz      short loc_1400458B7
0x140045858  lea     rax, [rbp+var_30]
0x14004585c  mov     dword ptr [rbp+var_30], r15d
0x140045860  mov     [rsp+70h+var_40], rax; __int64
0x140045865  xor     r8d, r8d
0x140045868  xor     edx, edx; String2
0x14004586a  mov     [rsp+70h+var_50], r15; __int64
0x14004586f  mov     rcx, r13; FileNameInformation
0x140045872  call    FsHardeningMatch
0x140045877  mov     cl, al
0x140045879  test    al, al
0x14004587b  jnz     short loc_140045882
0x14004587d  mov     r15b, bl
0x140045880  jmp     short loc_1400458B7
0x140045882  mov     eax, dword ptr [rbp+var_30]
0x140045885  and     al, bl
0x140045887  neg     al
0x140045889  sbb     r15b, r15b
0x14004588c  and     r15b, cl
0x14004588f  test    byte ptr [rbp+var_30], 2
0x140045893  jz      short loc_1400458B7
0x140045895  mov     r8, [rdi+80h]
0x14004589c  mov     r9, r13
0x14004589f  mov     byte ptr [rsp+70h+var_48], r12b
0x1400458a4  mov     dl, r15b
0x1400458a7  mov     cl, bl
0x1400458a9  mov     [rsp+70h+var_50], 0
0x1400458b2  call    MpTraceFsHardeningNotification
0x1400458b7  mov     r12d, [rbp+var_28]
0x1400458bb  test    r15b, r15b
0x1400458be  setz    al
0x1400458c1  jmp     short loc_1400458D2
0x1400458c3  mov     rdx, [rbp+FileNameInformation]
0x1400458c7  xor     r8d, r8d
0x1400458ca  mov     rcx, rdi
0x1400458cd  call    MpIsAMPath
0x1400458d2  test    al, al
0x1400458d4  jz      loc_140045798
0x1400458da  lfence
0x1400458dd  mov     dword ptr [r14+18h], 0C0000022h
0x1400458e5  mov     ebx, 4
0x1400458ea  mov     qword ptr [r14+20h], 0
0x1400458f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400458f9  lea     rax, WPP_GLOBAL_Control
0x140045900  cmp     rcx, rax
0x140045903  jz      short loc_14004596C
0x140045905  mov     eax, [rcx+2Ch]
0x140045908  test    al, 2
0x14004590a  jz      short loc_14004596C
0x14004590c  lfence
0x14004590f  test    rdi, rdi
0x140045912  jz      short loc_14004591D
0x140045914  mov     rsi, [rdi+80h]
0x14004591b  jmp     short loc_14004591F
0x14004591d  xor     esi, esi
0x14004591f  call    cs:__imp_PsGetCurrentProcessId
0x140045926  nop     dword ptr [rax+rax+00h]
0x14004592b  xor     ecx, ecx
0x14004592d  mov     edx, 1Dh
0x140045932  mov     r8, rax
0x140045935  test    r12d, r12d
0x140045938  mov     rax, [r14+10h]
0x14004593c  setnz   cl
0x14004593f  mov     dword ptr [rsp+70h+var_40], ecx
0x140045943  mov     rcx, cs:WPP_GLOBAL_Control
0x14004594a  mov     r9, [rax+8]
0x14004594e  mov     [rsp+70h+var_48], r8d
0x140045953  add     r9, 58h ; 'X'
0x140045957  lea     r8, WPP_1bce4dab9b883aab79efa6fb296bde6e_Traceguids
0x14004595e  mov     [rsp+70h+var_50], rsi
0x140045963  mov     rcx, [rcx+18h]
0x140045967  call    WPP_SF_ZZDd
0x14004596c  test    rdi, rdi
0x14004596f  jz      short loc_14004597A
0x140045971  mov     rsi, [rdi+80h]
0x140045978  jmp     short loc_14004597C
0x14004597a  xor     esi, esi
0x14004597c  call    cs:__imp_PsGetCurrentProcessId
0x140045983  nop     dword ptr [rax+rax+00h]
0x140045988  xor     ecx, ecx
0x14004598a  mov     r8, rsi
0x14004598d  mov     r9, rax
0x140045990  test    r12d, r12d
0x140045993  mov     rax, [r14+10h]
0x140045997  setnz   cl
0x14004599a  mov     dword ptr [rsp+70h+var_50], ecx
0x14004599e  lea     rcx, aMiniFilterDeni_1; "[Mini-filter] Denied access to file [%w"...
0x1400459a5  mov     rdx, [rax+8]
0x1400459a9  add     rdx, 58h ; 'X'
0x1400459ad  call    MpLogPrintfW
0x1400459b2  jmp     loc_1400457B9
```
