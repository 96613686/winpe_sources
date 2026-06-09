# MpQuerySessionIdFromProcess

- ea: `0x1400384b4`
- end: `0x140038703`
- name: `MpQuerySessionIdFromProcess`
- size: `591`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1400387f0`
- `0x140068d64`
- `0x140084094`

## callees

- `0x1400051bc`
- `0x1400118d0`
- `0x1400384b4`

## import_xrefs

- `ntoskrnl!PsDereferencePrimaryToken` at `0x140038550`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x140038550`
- `ntoskrnl!SeQueryInformationToken` at `0x140038527`
- `ntoskrnl!SeQueryInformationToken` at `0x140038527`
- `ntoskrnl!PsReferencePrimaryToken` at `0x1400384f3`
- `ntoskrnl!PsReferencePrimaryToken` at `0x1400384f3`
- `ntoskrnl!PsLookupProcessByProcessId` at `0x140038598`
- `ntoskrnl!PsLookupProcessByProcessId` at `0x140038598`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x1400386db`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x1400386db`
- `ntoskrnl!KeBugCheck` at `0x1400386f6`
- `ntoskrnl!KeBugCheck` at `0x1400386f6`
- `ntoskrnl!ObfDereferenceObject` at `0x1400386a3`
- `ntoskrnl!ObfDereferenceObject` at `0x1400386a3`

## pseudocode

```c
__int64 __fastcall MpQuerySessionIdFromProcess(struct _KPROCESS *a1, void *a2, _DWORD *a3)
{
  char v3; // r14
  PACCESS_TOKEN v5; // rax
  void *v6; // rsi
  NTSTATUS v7; // ebp
  NTSTATUS v8; // ebx
  PEPROCESS Process; // [rsp+30h] [rbp-48h] BYREF
  PVOID TokenInformation; // [rsp+38h] [rbp-40h] BYREF

  v3 = 0;
  Process = a1;
  if ( !a3 )
    return (unsigned int)-1073741811;
  if ( a1 )
  {
LABEL_3:
    v5 = PsReferencePrimaryToken(a1);
    LODWORD(TokenInformation) = 0;
    v6 = v5;
    if ( v5 )
    {
      v7 = SeQueryInformationToken(v5, TokenSessionId, &TokenInformation);
      v8 = v7;
      if ( v7 >= 0 )
      {
        *a3 = (_DWORD)TokenInformation;
LABEL_7:
        PsDereferencePrimaryToken(v6);
LABEL_8:
        if ( v3 )
        {
          ObfDereferenceObject(Process);
          if ( _InterlockedDecrement64(&ObTotalReferences) < 0 && *(int *)(MpData + 868) < 0 )
          {
            if ( KdRefreshDebuggerNotPresent() )
              KeBugCheck(1u);
            __debugbreak();
          }
        }
        return (unsigned int)v8;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      {
        _mm_lfence();
        WPP_SF_qD(
          WPP_GLOBAL_Control->AttachedDevice,
          16,
          WPP_81cd47ed6b7c3e33e522c0360ded0121_Traceguids,
          KeGetCurrentThread(),
          v7);
      }
    }
    else
    {
      v8 = -1073741811;
      v7 = -1073741811;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      _mm_lfence();
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        18,
        WPP_81cd47ed6b7c3e33e522c0360ded0121_Traceguids,
        KeGetCurrentThread(),
        v7);
    }
    if ( !v6 )
      goto LABEL_8;
    goto LABEL_7;
  }
  v8 = PsLookupProcessByProcessId(a2, &Process);
  if ( v8 >= 0 )
  {
    _InterlockedIncrement64(&ObTotalReferences);
    a1 = Process;
    v3 = 1;
    goto LABEL_3;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
  {
    _mm_lfence();
    WPP_SF_qD(
      WPP_GLOBAL_Control->AttachedDevice,
      17,
      WPP_81cd47ed6b7c3e33e522c0360ded0121_Traceguids,
      KeGetCurrentThread(),
      v8);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1400384b4  mov     [rsp+arg_18], rbx
0x1400384b9  push    rbp
0x1400384ba  push    rsi
0x1400384bb  push    rdi
0x1400384bc  push    r14
0x1400384be  push    r15
0x1400384c0  sub     rsp, 50h
0x1400384c4  mov     rax, cs:__security_cookie
0x1400384cb  xor     rax, rsp
0x1400384ce  mov     [rsp+78h+var_38], rax
0x1400384d3  xor     r14b, r14b
0x1400384d6  mov     [rsp+78h+Process], rcx
0x1400384db  mov     r15, r8
0x1400384de  mov     rax, rdx
0x1400384e1  test    r8, r8
0x1400384e4  jz      loc_140038589
0x1400384ea  test    rcx, rcx
0x1400384ed  jz      loc_140038590
0x1400384f3  call    cs:__imp_PsReferencePrimaryToken
0x1400384fa  nop     dword ptr [rax+rax+00h]
0x1400384ff  mov     dword ptr [rsp+78h+TokenInformation], 0
0x140038507  lea     rdi, WPP_GLOBAL_Control
0x14003850e  mov     rsi, rax
0x140038511  test    rax, rax
0x140038514  jz      loc_14003864B
0x14003851a  lea     r8, [rsp+78h+TokenInformation]; TokenInformation
0x14003851f  mov     edx, 0Ch; TokenInformationClass
0x140038524  mov     rcx, rax; Token
0x140038527  call    cs:__imp_SeQueryInformationToken
0x14003852e  nop     dword ptr [rax+rax+00h]
0x140038533  mov     ebp, eax
0x140038535  mov     ebx, eax
0x140038537  test    eax, eax
0x140038539  js      loc_14003860A
0x14003853f  mov     eax, dword ptr [rsp+78h+TokenInformation]
0x140038543  mov     [r15], eax
0x140038546  jmp     short loc_14003854D
0x140038548  test    rsi, rsi
0x14003854b  jz      short loc_14003855C
0x14003854d  mov     rcx, rsi; PrimaryToken
0x140038550  call    cs:__imp_PsDereferencePrimaryToken
0x140038557  nop     dword ptr [rax+rax+00h]
0x14003855c  test    r14b, r14b
0x14003855f  jnz     loc_14003869E
0x140038565  mov     eax, ebx
0x140038567  mov     rcx, [rsp+78h+var_38]
0x14003856c  xor     rcx, rsp; StackCookie
0x14003856f  call    __security_check_cookie
0x140038574  mov     rbx, [rsp+78h+arg_18]
0x14003857c  add     rsp, 50h
0x140038580  pop     r15
0x140038582  pop     r14
0x140038584  pop     rdi
0x140038585  pop     rsi
0x140038586  pop     rbp
0x140038587  retn
0x140038589  mov     ebx, 0C000000Dh
0x14003858e  jmp     short loc_140038565
0x140038590  lea     rdx, [rsp+78h+Process]; Process
0x140038595  mov     rcx, rax; ProcessId
0x140038598  call    cs:__imp_PsLookupProcessByProcessId
0x14003859f  nop     dword ptr [rax+rax+00h]
0x1400385a4  mov     ebx, eax
0x1400385a6  test    eax, eax
0x1400385a8  js      short loc_1400385BF
0x1400385aa  lock inc cs:ObTotalReferences
0x1400385b2  mov     rcx, [rsp+78h+Process]
0x1400385b7  mov     r14b, 1
0x1400385ba  jmp     loc_1400384F3
0x1400385bf  mov     rax, cs:WPP_GLOBAL_Control
0x1400385c6  lea     rdi, WPP_GLOBAL_Control
0x1400385cd  cmp     rax, rdi
0x1400385d0  jz      short loc_140038565
0x1400385d2  mov     eax, [rax+2Ch]
0x1400385d5  test    al, 1
0x1400385d7  jz      short loc_140038565
0x1400385d9  lfence
0x1400385dc  mov     r9, gs:188h
0x1400385e5  lea     r8, WPP_81cd47ed6b7c3e33e522c0360ded0121_Traceguids
0x1400385ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1400385f3  mov     edx, 11h
0x1400385f8  mov     [rsp+78h+var_58], ebx
0x1400385fc  mov     rcx, [rcx+18h]
0x140038600  call    WPP_SF_qD
0x140038605  jmp     loc_140038565
0x14003860a  mov     rax, cs:WPP_GLOBAL_Control
0x140038611  cmp     rax, rdi
0x140038614  jz      short loc_140038652
0x140038616  mov     eax, [rax+2Ch]
0x140038619  test    al, 1
0x14003861b  jz      short loc_140038652
0x14003861d  lfence
0x140038620  mov     r9, gs:188h
0x140038629  lea     r8, WPP_81cd47ed6b7c3e33e522c0360ded0121_Traceguids
0x140038630  mov     rcx, cs:WPP_GLOBAL_Control
0x140038637  mov     edx, 10h
0x14003863c  mov     [rsp+78h+var_58], ebp
0x140038640  mov     rcx, [rcx+18h]
0x140038644  call    WPP_SF_qD
0x140038649  jmp     short loc_140038652
0x14003864b  mov     ebx, 0C000000Dh
0x140038650  mov     ebp, ebx
0x140038652  mov     rax, cs:WPP_GLOBAL_Control
0x140038659  cmp     rax, rdi
0x14003865c  jz      loc_140038548
0x140038662  mov     eax, [rax+2Ch]
0x140038665  test    al, 1
0x140038667  jz      loc_140038548
0x14003866d  lfence
0x140038670  mov     r9, gs:188h
0x140038679  lea     r8, WPP_81cd47ed6b7c3e33e522c0360ded0121_Traceguids
0x140038680  mov     rcx, cs:WPP_GLOBAL_Control
0x140038687  mov     edx, 12h
0x14003868c  mov     [rsp+78h+var_58], ebp
0x140038690  mov     rcx, [rcx+18h]
0x140038694  call    WPP_SF_qD
0x140038699  jmp     loc_140038548
0x14003869e  mov     rcx, [rsp+78h+Process]; Object
0x1400386a3  call    cs:__imp_ObfDereferenceObject
0x1400386aa  nop     dword ptr [rax+rax+00h]
0x1400386af  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400386b3  lock xadd cs:ObTotalReferences, rax
0x1400386bc  cmp     rax, 1
0x1400386c0  jns     loc_140038565
0x1400386c6  mov     rax, cs:MpData
0x1400386cd  mov     ecx, [rax+364h]
0x1400386d3  test    ecx, ecx
0x1400386d5  jns     loc_140038565
0x1400386db  call    cs:__imp_KdRefreshDebuggerNotPresent
0x1400386e2  nop     dword ptr [rax+rax+00h]
0x1400386e7  test    al, al
0x1400386e9  jnz     short loc_1400386F1
0x1400386eb  int     3; Trap to Debugger
0x1400386ec  jmp     loc_140038565
0x1400386f1  mov     ecx, 1; BugCheckCode
0x1400386f6  call    cs:__imp_KeBugCheck
```
