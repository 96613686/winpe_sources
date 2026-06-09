# MpHardenBindFltBind

- ea: `0x14007ab88`
- end: `0x14007af3c`
- name: `MpHardenBindFltBind`
- size: `948`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140069c80`

## callees

- `0x140002450`
- `0x1400051bc`
- `0x1400068fc`
- `0x1400118d0`
- `0x140030060`
- `0x14003a1b0`
- `0x14003ee80`
- `0x140040388`
- `0x140046e30`
- `0x1400471ac`
- `0x14007ab88`
- `0x14008ab44`

## import_xrefs

- `ntoskrnl!PsInitialSystemProcess` at `0x14007ac48`
- `ntoskrnl!IoThreadToProcess` at `0x14007abf6`
- `ntoskrnl!IoThreadToProcess` at `0x14007ac22`
- `ntoskrnl!IoThreadToProcess` at `0x14007abf6`
- `ntoskrnl!IoThreadToProcess` at `0x14007ac22`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14007ae50`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14007aeac`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14007ae50`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14007aeac`
- `FLTMGR!FltGetFileNameInformation` at `0x14007acf7`
- `FLTMGR!FltGetFileNameInformation` at `0x14007acf7`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14007af00`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14007af00`

## string_xrefs

- `0x14007aebc`: `[Mini-filter] Denied access to file [%wZ] from process [%wZ][Pid:%u]. DynamicFsHardeningEnabled[%d].`

## pseudocode

```c
__int64 __fastcall MpHardenBindFltBind(PFLT_CALLBACK_DATA CallbackData, __int64 a2)
{
  int v2; // ebp
  struct _KPROCESS *v4; // rbx
  struct _KPROCESS *v5; // rbx
  struct _KPROCESS *RequestorProcess; // rax
  NTSTATUS ProcessContextByObject; // ebx
  int v9; // r15d
  char IsAMPath; // al
  char CurrentProcessId; // al
  unsigned int v12; // eax
  __int64 v13; // [rsp+20h] [rbp-68h]
  __int64 v14; // [rsp+40h] [rbp-48h]
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+48h] [rbp-40h] BYREF

  v14 = 0;
  v2 = a2;
  FileNameInformation = 0;
  if ( !CallbackData || !a2 || CallbackData->Iopb->MajorFunction != 0xF9 )
    return 3221225485LL;
  v4 = *(struct _KPROCESS **)(MpData + 232);
  if ( IoThreadToProcess(KeGetCurrentThread()) == v4 )
    return 0;
  v5 = *(struct _KPROCESS **)(MpData + 256);
  if ( IoThreadToProcess(KeGetCurrentThread()) == v5 )
    return 0;
  RequestorProcess = (struct _KPROCESS *)MpGetRequestorProcess(CallbackData);
  if ( !RequestorProcess || PsInitialSystemProcess == RequestorProcess )
    return 0;
  ProcessContextByObject = MpGetProcessContextByObject(RequestorProcess);
  if ( ProcessContextByObject >= 0 )
  {
    _mm_lfence();
    v9 = *(_DWORD *)(MpData + 868) & 0x4000;
    if ( (unsigned __int8)MpCheckForAmHardening((_DWORD)CallbackData, v2, 0, v14, 0) )
    {
      ProcessContextByObject = FltGetFileNameInformation(CallbackData, 0x101u, &FileNameInformation);
      if ( ProcessContextByObject >= 0 )
      {
        if ( v9 )
          IsAMPath = 1;
        else
          IsAMPath = MpIsAMPath(v14, FileNameInformation);
        if ( IsAMPath )
        {
          ProcessContextByObject = 1835009;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
          {
            CurrentProcessId = (unsigned __int8)PsGetCurrentProcessId();
            WPP_SF_ZZDd(
              WPP_GLOBAL_Control->AttachedDevice,
              96,
              (unsigned int)WPP_ced1f0f3184e37ff4d326dc12ac9f83e_Traceguids,
              &CallbackData->Iopb->TargetFileObject->FileName,
              0,
              CurrentProcessId,
              v9 != 0);
          }
          v12 = (unsigned int)PsGetCurrentProcessId();
          LODWORD(v13) = v9 != 0;
          MpLogPrintfW(
            L"[Mini-filter] Denied access to file [%wZ] from process [%wZ][Pid:%u]. DynamicFsHardeningEnabled[%d].",
            &CallbackData->Iopb->TargetFileObject->FileName,
            0,
            v12,
            v13);
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        {
          _mm_lfence();
          WPP_SF_qD(
            WPP_GLOBAL_Control->AttachedDevice,
            95,
            WPP_ced1f0f3184e37ff4d326dc12ac9f83e_Traceguids,
            KeGetCurrentThread(),
            ProcessContextByObject);
        }
        if ( ProcessContextByObject == -1073741536 || ProcessContextByObject == -1073741749 )
          ProcessContextByObject = 1835009;
      }
    }
    if ( FileNameInformation )
      FltReleaseFileNameInformation(FileNameInformation);
  }
  else
  {
    _mm_lfence();
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        94,
        WPP_ced1f0f3184e37ff4d326dc12ac9f83e_Traceguids,
        CallbackData->Thread,
        ProcessContextByObject);
  }
  return (unsigned int)ProcessContextByObject;
}

```

## disassembly

```asm
0x14007ab88  mov     [rsp+arg_10], rbx
0x14007ab8d  push    rbp
0x14007ab8e  push    rsi
0x14007ab8f  push    rdi
0x14007ab90  push    r14
0x14007ab92  push    r15
0x14007ab94  sub     rsp, 60h
0x14007ab98  mov     rax, cs:__security_cookie
0x14007ab9f  xor     rax, rsp
0x14007aba2  mov     [rsp+88h+var_38], rax
0x14007aba7  mov     [rsp+88h+var_48], 0
0x14007abb0  mov     rbp, rdx
0x14007abb3  mov     [rsp+88h+FileNameInformation], 0
0x14007abbc  mov     rsi, rcx
0x14007abbf  test    rcx, rcx
0x14007abc2  jz      loc_14007AF15
0x14007abc8  test    rdx, rdx
0x14007abcb  jz      loc_14007AF15
0x14007abd1  mov     rax, [rcx+10h]
0x14007abd5  cmp     byte ptr [rax+4], 0F9h
0x14007abd9  jnz     loc_14007AF15
0x14007abdf  mov     rcx, gs:188h; Thread
0x14007abe8  mov     rax, cs:MpData
0x14007abef  mov     rbx, [rax+0E8h]
0x14007abf6  call    cs:__imp_IoThreadToProcess
0x14007abfd  nop     dword ptr [rax+rax+00h]
0x14007ac02  cmp     rax, rbx
0x14007ac05  jz      loc_14007AF11
0x14007ac0b  mov     rcx, gs:188h; Thread
0x14007ac14  mov     rax, cs:MpData
0x14007ac1b  mov     rbx, [rax+100h]
0x14007ac22  call    cs:__imp_IoThreadToProcess
0x14007ac29  nop     dword ptr [rax+rax+00h]
0x14007ac2e  cmp     rax, rbx
0x14007ac31  jz      loc_14007AF11
0x14007ac37  mov     rcx, rsi
0x14007ac3a  call    MpGetRequestorProcess
0x14007ac3f  test    rax, rax
0x14007ac42  jz      loc_14007AF11
0x14007ac48  mov     rcx, cs:__imp_PsInitialSystemProcess
0x14007ac4f  cmp     [rcx], rax
0x14007ac52  jz      loc_14007AF11
0x14007ac58  lea     rdx, [rsp+88h+var_48]
0x14007ac5d  mov     rcx, rax; Process
0x14007ac60  call    MpGetProcessContextByObject
0x14007ac65  mov     ebx, eax
0x14007ac67  test    eax, eax
0x14007ac69  jns     short loc_14007ACAF
0x14007ac6b  lfence
0x14007ac6e  mov     r10, cs:WPP_GLOBAL_Control
0x14007ac75  lea     rax, WPP_GLOBAL_Control
0x14007ac7c  cmp     r10, rax
0x14007ac7f  jz      short loc_14007ACA8
0x14007ac81  mov     edx, [r10+2Ch]
0x14007ac85  mov     cl, 1
0x14007ac87  test    cl, dl
0x14007ac89  jz      short loc_14007ACA8
0x14007ac8b  mov     r9, [rsi+8]
0x14007ac8f  lea     r8, WPP_ced1f0f3184e37ff4d326dc12ac9f83e_Traceguids
0x14007ac96  mov     rcx, [r10+18h]
0x14007ac9a  mov     edx, 5Eh ; '^'
0x14007ac9f  mov     dword ptr [rsp+88h+var_68], ebx
0x14007aca3  call    WPP_SF_qD
0x14007aca8  mov     eax, ebx
0x14007acaa  jmp     loc_14007AF1A
0x14007acaf  lfence
0x14007acb2  mov     rax, cs:MpData
0x14007acb9  xor     r8d, r8d
0x14007acbc  mov     rdi, [rsp+88h+var_48]
0x14007acc1  mov     rdx, rbp
0x14007acc4  mov     r9, rdi
0x14007acc7  mov     byte ptr [rsp+88h+var_68], 0
0x14007accc  mov     rcx, rsi
0x14007accf  mov     r15d, [rax+364h]
0x14007acd6  and     r15d, 4000h
0x14007acdd  call    MpCheckForAmHardening
0x14007ace2  test    al, al
0x14007ace4  jz      loc_14007AEE5
0x14007acea  lea     r8, [rsp+88h+FileNameInformation]; FileNameInformation
0x14007acef  mov     edx, 101h; NameOptions
0x14007acf4  mov     rcx, rsi; CallbackData
0x14007acf7  call    cs:__imp_FltGetFileNameInformation
0x14007acfe  nop     dword ptr [rax+rax+00h]
0x14007ad03  mov     ebx, eax
0x14007ad05  test    eax, eax
0x14007ad07  jns     short loc_14007AD70
0x14007ad09  mov     rcx, cs:WPP_GLOBAL_Control
0x14007ad10  lea     rax, WPP_GLOBAL_Control
0x14007ad17  cmp     rcx, rax
0x14007ad1a  jz      short loc_14007AD51
0x14007ad1c  mov     eax, [rcx+2Ch]
0x14007ad1f  mov     cl, 1
0x14007ad21  test    cl, al
0x14007ad23  jz      short loc_14007AD51
0x14007ad25  lfence
0x14007ad28  mov     r9, gs:188h
0x14007ad31  lea     r8, WPP_ced1f0f3184e37ff4d326dc12ac9f83e_Traceguids
0x14007ad38  mov     rcx, cs:WPP_GLOBAL_Control
0x14007ad3f  mov     edx, 5Fh ; '_'
0x14007ad44  mov     dword ptr [rsp+88h+var_68], ebx
0x14007ad48  mov     rcx, [rcx+18h]
0x14007ad4c  call    WPP_SF_qD
0x14007ad51  mov     eax, ebx
0x14007ad53  cmp     ebx, 0C0000120h
0x14007ad59  jz      short loc_14007AD66
0x14007ad5b  cmp     eax, 0C000004Bh
0x14007ad60  jnz     loc_14007AEE5
0x14007ad66  mov     ebx, 1C0001h
0x14007ad6b  jmp     loc_14007AEE5
0x14007ad70  test    r15d, r15d
0x14007ad73  jz      loc_14007AE09
0x14007ad79  cmp     cs:MpFsHardeningData, 0
0x14007ad81  mov     r9, [rbp+18h]
0x14007ad85  mov     r14, [rsp+88h+FileNameInformation]
0x14007ad8a  jz      short loc_14007AE00
0x14007ad8c  test    rdi, rdi
0x14007ad8f  jz      short loc_14007AE00
0x14007ad91  test    r14, r14
0x14007ad94  jz      short loc_14007AE00
0x14007ad96  lea     rax, [rsp+88h+var_48]
0x14007ad9b  mov     dword ptr [rsp+88h+var_48], 0
0x14007ada3  mov     [rsp+88h+var_58], rax; __int64
0x14007ada8  xor     r8d, r8d
0x14007adab  xor     edx, edx; String2
0x14007adad  mov     [rsp+88h+var_68], 0; __int64
0x14007adb6  mov     rcx, r14; FileNameInformation
0x14007adb9  call    FsHardeningMatch
0x14007adbe  mov     dl, al
0x14007adc0  mov     cl, 1
0x14007adc2  test    al, al
0x14007adc4  jz      short loc_14007AE02
0x14007adc6  mov     eax, dword ptr [rsp+88h+var_48]
0x14007adca  and     al, cl
0x14007adcc  neg     al
0x14007adce  sbb     bpl, bpl
0x14007add1  and     bpl, dl
0x14007add4  test    byte ptr [rsp+88h+var_48], 2
0x14007add9  jz      short loc_14007ADFB
0x14007addb  mov     r8, [rdi+80h]
0x14007ade2  mov     r9, r14
0x14007ade5  mov     byte ptr [rsp+88h+var_60], 0
0x14007adea  mov     dl, bpl
0x14007aded  mov     [rsp+88h+var_68], 0
0x14007adf6  call    MpTraceFsHardeningNotification
0x14007adfb  mov     cl, bpl
0x14007adfe  jmp     short loc_14007AE02
0x14007ae00  xor     cl, cl
0x14007ae02  test    cl, cl
0x14007ae04  setz    al
0x14007ae07  jmp     short loc_14007AE19
0x14007ae09  mov     rdx, [rsp+88h+FileNameInformation]
0x14007ae0e  xor     r8d, r8d
0x14007ae11  mov     rcx, rdi
0x14007ae14  call    MpIsAMPath
0x14007ae19  test    al, al
0x14007ae1b  jz      loc_14007AEE5
0x14007ae21  mov     ebx, 1C0001h
0x14007ae26  mov     rcx, cs:WPP_GLOBAL_Control
0x14007ae2d  lea     rax, WPP_GLOBAL_Control
0x14007ae34  cmp     rcx, rax
0x14007ae37  jz      short loc_14007AE9C
0x14007ae39  mov     eax, [rcx+2Ch]
0x14007ae3c  test    al, 2
0x14007ae3e  jz      short loc_14007AE9C
0x14007ae40  test    rdi, rdi
0x14007ae43  jz      short loc_14007AE4E
0x14007ae45  mov     rbp, [rdi+80h]
0x14007ae4c  jmp     short loc_14007AE50
0x14007ae4e  xor     ebp, ebp
0x14007ae50  call    cs:__imp_PsGetCurrentProcessId
0x14007ae57  nop     dword ptr [rax+rax+00h]
0x14007ae5c  mov     rcx, [rsi+10h]
0x14007ae60  xor     r8d, r8d
0x14007ae63  test    r15d, r15d
0x14007ae66  mov     edx, 60h ; '`'
0x14007ae6b  setnz   r8b
0x14007ae6f  mov     r9, [rcx+8]
0x14007ae73  mov     rcx, cs:WPP_GLOBAL_Control
0x14007ae7a  add     r9, 58h ; 'X'
0x14007ae7e  mov     dword ptr [rsp+88h+var_58], r8d
0x14007ae83  lea     r8, WPP_ced1f0f3184e37ff4d326dc12ac9f83e_Traceguids
0x14007ae8a  mov     [rsp+88h+var_60], eax
0x14007ae8e  mov     [rsp+88h+var_68], rbp
0x14007ae93  mov     rcx, [rcx+18h]
0x14007ae97  call    WPP_SF_ZZDd
0x14007ae9c  test    rdi, rdi
0x14007ae9f  jz      short loc_14007AEAA
0x14007aea1  mov     rbp, [rdi+80h]
0x14007aea8  jmp     short loc_14007AEAC
0x14007aeaa  xor     ebp, ebp
0x14007aeac  call    cs:__imp_PsGetCurrentProcessId
0x14007aeb3  nop     dword ptr [rax+rax+00h]
0x14007aeb8  mov     rdx, [rsi+10h]
0x14007aebc  lea     rcx, aMiniFilterDeni_1; "[Mini-filter] Denied access to file [%w"...
0x14007aec3  xor     r9d, r9d
0x14007aec6  mov     r8, rbp
0x14007aec9  test    r15d, r15d
0x14007aecc  mov     rdx, [rdx+8]
0x14007aed0  setnz   r9b
0x14007aed4  mov     dword ptr [rsp+88h+var_68], r9d
0x14007aed9  add     rdx, 58h ; 'X'
0x14007aedd  mov     r9d, eax
0x14007aee0  call    MpLogPrintfW
0x14007aee5  test    rdi, rdi
0x14007aee8  jz      short loc_14007AEF2
0x14007aeea  mov     rcx, rdi
0x14007aeed  call    MpReleaseProcessContext
0x14007aef2  mov     rcx, [rsp+88h+FileNameInformation]; FileNameInformation
0x14007aef7  test    rcx, rcx
0x14007aefa  jz      loc_14007ACA8
0x14007af00  call    cs:__imp_FltReleaseFileNameInformation
0x14007af07  nop     dword ptr [rax+rax+00h]
0x14007af0c  jmp     loc_14007ACA8
0x14007af11  xor     eax, eax
0x14007af13  jmp     short loc_14007AF1A
0x14007af15  mov     eax, 0C000000Dh
0x14007af1a  mov     rcx, [rsp+88h+var_38]
0x14007af1f  xor     rcx, rsp; StackCookie
0x14007af22  call    __security_check_cookie
0x14007af27  mov     rbx, [rsp+88h+arg_10]
0x14007af2f  add     rsp, 60h
0x14007af33  pop     r15
0x14007af35  pop     r14
0x14007af37  pop     rdi
0x14007af38  pop     rsi
0x14007af39  pop     rbp
0x14007af3a  retn
```
