# MpCreateProcessNotifyRoutine

- ea: `0x140082150`
- end: `0x14008237a`
- name: `MpCreateProcessNotifyRoutine`
- size: `554`
- prototype: `void __stdcall(HANDLE ParentId, HANDLE ProcessId, BOOLEAN Create)`
- caller_count: `0`
- callee_count: `7`
- tags: `reparse_path, authz_impersonation, loader_planting`

## callees

- `0x1400051bc`
- `0x1400118d0`
- `0x140036780`
- `0x140036d80`
- `0x140066180`
- `0x140070414`
- `0x140082150`

## import_xrefs

- `ntoskrnl!PsLookupProcessByProcessId` at `0x14008222e`
- `ntoskrnl!PsLookupProcessByProcessId` at `0x14008222e`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x140082312`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x140082312`
- `ntoskrnl!KeBugCheck` at `0x14008236d`
- `ntoskrnl!KeBugCheck` at `0x14008236d`
- `ntoskrnl!ObfDereferenceObject` at `0x1400822e2`
- `ntoskrnl!ObfDereferenceObject` at `0x1400822e2`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14008233a`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14008233a`

## pseudocode

```c
void __fastcall MpCreateProcessNotifyRoutine(HANDLE ParentId, HANDLE ProcessId, char Create)
{
  int ProcessName; // ecx
  int ImageNormalizedName; // eax
  __int64 v8; // rdx
  NTSTATUS v9; // ecx
  UNICODE_STRING *p_Name; // rax
  int v11; // [rsp+20h] [rbp-50h]
  UNICODE_STRING *v12; // [rsp+50h] [rbp-20h] BYREF
  PEPROCESS Process; // [rsp+58h] [rbp-18h] BYREF
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+60h] [rbp-10h]

  v12 = 0;
  FileNameInformation = 0;
  Process = 0;
  if ( Create )
  {
    ProcessName = MpGetProcessName(ProcessId, &v12);
    if ( ProcessName < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      {
        v8 = 17;
        v11 = ProcessName;
        goto LABEL_10;
      }
    }
    else
    {
      ImageNormalizedName = MpGetImageNormalizedName(0);
      if ( ImageNormalizedName < 0
        && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      {
        v8 = 16;
        v11 = ImageNormalizedName;
LABEL_10:
        _mm_lfence();
        WPP_SF_qD(
          WPP_GLOBAL_Control->AttachedDevice,
          v8,
          WPP_8ebd71c5d5f53801838f519f7d1f4ffb_Traceguids,
          KeGetCurrentThread(),
          v11);
      }
    }
  }
  v9 = PsLookupProcessByProcessId(ProcessId, &Process);
  if ( v9 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      _mm_lfence();
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        18,
        WPP_8ebd71c5d5f53801838f519f7d1f4ffb_Traceguids,
        KeGetCurrentThread(),
        v9);
    }
  }
  else
  {
    _InterlockedIncrement64(&ObTotalReferences);
    _mm_lfence();
    if ( FileNameInformation )
      p_Name = &FileNameInformation->Name;
    else
      p_Name = v12;
    MpHandleProcessNotification(Process, ParentId, ProcessId, Create, 0, 0, p_Name, 0, 0);
  }
  if ( Process )
  {
    ObfDereferenceObject(Process);
    if ( _InterlockedDecrement64(&ObTotalReferences) < 0 && *(int *)(MpData + 868) < 0 )
    {
      if ( KdRefreshDebuggerNotPresent() )
        KeBugCheck(1u);
      __debugbreak();
    }
  }
  if ( v12 )
    MpFreeString(v12);
  if ( FileNameInformation )
    FltReleaseFileNameInformation(FileNameInformation);
}

```

## disassembly

```asm
0x140082150  mov     [rsp-18h+arg_10], rbx
0x140082155  mov     [rsp-18h+arg_18], rsi
0x14008215a  push    rbp
0x14008215b  push    rdi
0x14008215c  push    r15
0x14008215e  mov     rbp, rsp
0x140082161  sub     rsp, 70h
0x140082165  mov     rax, cs:__security_cookie
0x14008216c  xor     rax, rsp
0x14008216f  mov     [rbp+var_8], rax
0x140082173  mov     [rbp+var_20], 0
0x14008217b  mov     dil, r8b
0x14008217e  mov     [rbp+FileNameInformation], 0
0x140082186  mov     rbx, rdx
0x140082189  mov     [rbp+Process], 0
0x140082191  mov     rsi, rcx
0x140082194  lea     r15, WPP_GLOBAL_Control
0x14008219b  test    r8b, r8b
0x14008219e  jz      loc_140082227
0x1400821a4  lea     rdx, [rbp+var_20]
0x1400821a8  mov     rcx, rbx
0x1400821ab  call    MpGetProcessName
0x1400821b0  mov     ecx, eax
0x1400821b2  test    eax, eax
0x1400821b4  js      short loc_1400821E8
0x1400821b6  mov     rdx, [rbp+var_20]
0x1400821ba  lea     r8, [rbp+FileNameInformation]
0x1400821be  xor     ecx, ecx; Object
0x1400821c0  call    MpGetImageNormalizedName
0x1400821c5  test    eax, eax
0x1400821c7  jns     short loc_140082227
0x1400821c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400821d0  cmp     rcx, r15
0x1400821d3  jz      short loc_140082227
0x1400821d5  mov     ecx, [rcx+2Ch]
0x1400821d8  test    cl, 1
0x1400821db  jz      short loc_140082227
0x1400821dd  mov     edx, 10h
0x1400821e2  mov     [rsp+70h+var_50], eax
0x1400821e6  jmp     short loc_140082204
0x1400821e8  mov     rax, cs:WPP_GLOBAL_Control
0x1400821ef  cmp     rax, r15
0x1400821f2  jz      short loc_140082227
0x1400821f4  mov     eax, [rax+2Ch]
0x1400821f7  test    al, 1
0x1400821f9  jz      short loc_140082227
0x1400821fb  mov     edx, 11h
0x140082200  mov     [rsp+70h+var_50], ecx
0x140082204  lfence
0x140082207  mov     r9, gs:188h
0x140082210  lea     r8, WPP_8ebd71c5d5f53801838f519f7d1f4ffb_Traceguids
0x140082217  mov     rcx, cs:WPP_GLOBAL_Control
0x14008221e  mov     rcx, [rcx+18h]
0x140082222  call    WPP_SF_qD
0x140082227  lea     rdx, [rbp+Process]; Process
0x14008222b  mov     rcx, rbx; ProcessId
0x14008222e  call    cs:__imp_PsLookupProcessByProcessId
0x140082235  nop     dword ptr [rax+rax+00h]
0x14008223a  mov     ecx, eax
0x14008223c  test    eax, eax
0x14008223e  js      short loc_14008229A
0x140082240  lock inc cs:ObTotalReferences
0x140082248  lfence
0x14008224b  mov     rax, [rbp+FileNameInformation]
0x14008224f  test    rax, rax
0x140082252  jz      short loc_14008225A
0x140082254  add     rax, 8
0x140082258  jmp     short loc_14008225E
0x14008225a  mov     rax, [rbp+var_20]
0x14008225e  mov     rcx, [rbp+Process]
0x140082262  mov     r9b, dil
0x140082265  mov     [rsp+70h+var_30], 0
0x14008226e  mov     r8, rbx
0x140082271  mov     [rsp+70h+var_38], 0
0x14008227a  mov     rdx, rsi
0x14008227d  mov     [rsp+70h+var_40], rax
0x140082282  mov     [rsp+70h+var_48], 0
0x14008228b  mov     [rsp+70h+var_50], 0
0x140082293  call    MpHandleProcessNotification
0x140082298  jmp     short loc_1400822D9
0x14008229a  mov     rax, cs:WPP_GLOBAL_Control
0x1400822a1  cmp     rax, r15
0x1400822a4  jz      short loc_1400822D9
0x1400822a6  mov     eax, [rax+2Ch]
0x1400822a9  test    al, 1
0x1400822ab  jz      short loc_1400822D9
0x1400822ad  lfence
0x1400822b0  mov     r9, gs:188h
0x1400822b9  lea     r8, WPP_8ebd71c5d5f53801838f519f7d1f4ffb_Traceguids
0x1400822c0  mov     [rsp+70h+var_50], ecx
0x1400822c4  mov     edx, 12h
0x1400822c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400822d0  mov     rcx, [rcx+18h]
0x1400822d4  call    WPP_SF_qD
0x1400822d9  mov     rcx, [rbp+Process]; Object
0x1400822dd  test    rcx, rcx
0x1400822e0  jz      short loc_140082323
0x1400822e2  call    cs:__imp_ObfDereferenceObject
0x1400822e9  nop     dword ptr [rax+rax+00h]
0x1400822ee  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400822f2  lock xadd cs:ObTotalReferences, rax
0x1400822fb  cmp     rax, 1
0x1400822ff  jns     short loc_140082323
0x140082301  mov     rax, cs:MpData
0x140082308  mov     ecx, [rax+364h]
0x14008230e  test    ecx, ecx
0x140082310  jns     short loc_140082323
0x140082312  call    cs:__imp_KdRefreshDebuggerNotPresent
0x140082319  nop     dword ptr [rax+rax+00h]
0x14008231e  test    al, al
0x140082320  jnz     short loc_140082368
0x140082322  int     3; Trap to Debugger
0x140082323  mov     rcx, [rbp+var_20]
0x140082327  test    rcx, rcx
0x14008232a  jz      short loc_140082331
0x14008232c  call    MpFreeString
0x140082331  mov     rcx, [rbp+FileNameInformation]; FileNameInformation
0x140082335  test    rcx, rcx
0x140082338  jz      short loc_140082346
0x14008233a  call    cs:__imp_FltReleaseFileNameInformation
0x140082341  nop     dword ptr [rax+rax+00h]
0x140082346  mov     rcx, [rbp+var_8]
0x14008234a  xor     rcx, rsp; StackCookie
0x14008234d  call    __security_check_cookie
0x140082352  lea     r11, [rsp+70h+var_s0]
0x140082357  mov     rbx, [r11+30h]
0x14008235b  mov     rsi, [r11+38h]
0x14008235f  mov     rsp, r11
0x140082362  pop     r15
0x140082364  pop     rdi
0x140082365  pop     rbp
0x140082366  retn
0x140082368  mov     ecx, 1; BugCheckCode
0x14008236d  call    cs:__imp_KeBugCheck
```
