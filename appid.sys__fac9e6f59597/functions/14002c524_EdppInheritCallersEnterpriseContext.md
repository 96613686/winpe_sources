# EdppInheritCallersEnterpriseContext

- ea: `0x14002c524`
- end: `0x14002c832`
- name: `EdppInheritCallersEnterpriseContext`
- size: `782`
- prototype: `__int64 __fastcall(_QWORD *, unsigned int)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x14002bff0`

## callees

- `0x140005544`
- `0x1400056d0`
- `0x140005710`
- `0x140005848`
- `0x1400058c8`
- `0x140006674`
- `0x14000675c`
- `0x140006798`
- `0x1400067c0`
- `0x14002c524`
- `0x14002c89c`

## import_xrefs

- `ntoskrnl!ObOpenObjectByPointer` at `0x14002c6af`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14002c6af`
- `ntoskrnl!ZwQueryInformationToken` at `0x14002c602`
- `ntoskrnl!ZwQueryInformationToken` at `0x14002c602`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14002c7da`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14002c7da`
- `ntoskrnl!SeCaptureSubjectContext` at `0x14002c637`
- `ntoskrnl!SeCaptureSubjectContext` at `0x14002c637`
- `ntoskrnl!RtlIsSandboxedToken` at `0x14002c664`
- `ntoskrnl!RtlIsSandboxedToken` at `0x14002c664`
- `ntoskrnl!ZwCompareTokens` at `0x14002c6d1`
- `ntoskrnl!ZwCompareTokens` at `0x14002c6d1`
- `ntoskrnl!ZwClose` at `0x14002c5ce`
- `ntoskrnl!ZwClose` at `0x14002c7c5`
- `ntoskrnl!ZwClose` at `0x14002c7ef`
- `ntoskrnl!ZwClose` at `0x14002c804`
- `ntoskrnl!ZwClose` at `0x14002c5ce`
- `ntoskrnl!ZwClose` at `0x14002c7c5`
- `ntoskrnl!ZwClose` at `0x14002c7ef`
- `ntoskrnl!ZwClose` at `0x14002c804`

## pseudocode

```c
__int64 __fastcall EdppInheritCallersEnterpriseContext(_QWORD *a1, unsigned int a2)
{
  __int64 v3; // rsi
  char v4; // r15
  __int64 v5; // rdi
  NTSTATUS IsEnterpriseExempt; // ebx
  __int64 v7; // r14
  __int64 v8; // rdx
  char IsSandboxedToken; // al
  PACCESS_TOKEN PrimaryToken; // rcx
  int v11; // edx
  int v12; // r9d
  __int64 v13; // rax
  HANDLE Handle; // [rsp+40h] [rbp-39h] BYREF
  HANDLE TokenHandle; // [rsp+48h] [rbp-31h] BYREF
  ULONG ReturnLength; // [rsp+50h] [rbp-29h] BYREF
  __int64 v18; // [rsp+58h] [rbp-21h] BYREF
  __int64 v19; // [rsp+60h] [rbp-19h] BYREF
  HANDLE SecondTokenHandle; // [rsp+68h] [rbp-11h] BYREF
  __int64 v21; // [rsp+70h] [rbp-9h] BYREF
  __int64 v22; // [rsp+78h] [rbp-1h] BYREF
  struct _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+80h] [rbp+7h] BYREF
  char v24; // [rsp+E8h] [rbp+6Fh] BYREF
  unsigned __int8 Equal; // [rsp+F0h] [rbp+77h] BYREF
  int TokenInformation; // [rsp+F8h] [rbp+7Fh] BYREF

  v24 = 0;
  Equal = 0;
  v3 = 0;
  v19 = 0;
  v4 = 0;
  TokenInformation = 0;
  v5 = 0;
  Handle = 0;
  TokenHandle = 0;
  ReturnLength = 0;
  SecondTokenHandle = 0;
  v18 = 0;
  v22 = 0;
  v21 = 0;
  memset(&SubjectContext, 0, sizeof(SubjectContext));
  if ( a2 < 0x18 || a1[2] >= 2u )
  {
    IsEnterpriseExempt = -1073741811;
    goto LABEL_32;
  }
  IsEnterpriseExempt = EdppOpenKernelTokenHandle(*a1, 8, &Handle);
  if ( IsEnterpriseExempt >= 0 )
  {
    IsEnterpriseExempt = EdppOpenKernelTokenHandle(a1[1], 140, &TokenHandle);
    if ( IsEnterpriseExempt < 0 )
    {
      ZwClose(Handle);
      Handle = 0;
      goto LABEL_32;
    }
    v7 = a1[2];
    IsEnterpriseExempt = ZwQueryInformationToken(
                           TokenHandle,
                           TokenImpersonationLevel,
                           &TokenInformation,
                           4u,
                           &ReturnLength);
    if ( IsEnterpriseExempt >= 0 )
    {
      if ( TokenInformation != 2 )
      {
LABEL_9:
        IsEnterpriseExempt = -1073741790;
        goto LABEL_32;
      }
      memset(&SubjectContext, 0, sizeof(SubjectContext));
      SeCaptureSubjectContext(&SubjectContext);
      v4 = 1;
      IsEnterpriseExempt = SrpIsEnterpriseExempt(&SubjectContext, &v24);
      if ( IsEnterpriseExempt >= 0 )
      {
        LOBYTE(v8) = 1;
        IsSandboxedToken = RtlIsSandboxedToken(&SubjectContext, v8);
        if ( !v24 && IsSandboxedToken )
          goto LABEL_9;
        PrimaryToken = SubjectContext.PrimaryToken;
        if ( SubjectContext.ClientToken )
          PrimaryToken = SubjectContext.ClientToken;
        if ( !PrimaryToken )
          goto LABEL_9;
        IsEnterpriseExempt = ObOpenObjectByPointer(PrimaryToken, 0x200u, 0, 8u, 0, 0, &SecondTokenHandle);
        if ( IsEnterpriseExempt >= 0 )
        {
          IsEnterpriseExempt = ZwCompareTokens(TokenHandle, SecondTokenHandle, &Equal);
          if ( IsEnterpriseExempt >= 0 )
          {
            if ( !Equal )
              goto LABEL_9;
            IsEnterpriseExempt = SrpGetEnterpriseContextToken(Handle, &v19);
            if ( IsEnterpriseExempt < 0
              || (IsEnterpriseExempt = SrpGetEvaluationFlagsToken(Handle, &v21), IsEnterpriseExempt < 0) )
            {
              v3 = v19;
            }
            else
            {
              v3 = v19;
              if ( (v7 & 1) != 0 )
              {
                v13 = *(_QWORD *)(v19 + 8);
                if ( (v13 & 2) != 0 )
                  *(_QWORD *)(v19 + 8) = v13 | 8;
              }
              IsEnterpriseExempt = SrpSetEnterpriseContextToken((_DWORD)TokenHandle, v11, 0, v12, v3, v21);
              if ( IsEnterpriseExempt >= 0 )
              {
                IsEnterpriseExempt = SrpGetAppUniqueIdFromToken(Handle, &v18);
                if ( IsEnterpriseExempt < 0
                  || (IsEnterpriseExempt = SrpGetProcessUniqueIdFromToken(Handle, &v22), IsEnterpriseExempt < 0) )
                {
                  v5 = v18;
                }
                else
                {
                  v5 = v18;
                  if ( !v18
                    || (IsEnterpriseExempt = SrpSetInheritedAppUniqueIdOnToken(TokenHandle, v18), IsEnterpriseExempt >= 0) )
                  {
                    IsEnterpriseExempt = SrpSetInheritedProcessUniqueIdOnToken(TokenHandle, v22);
                  }
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_32:
  SrpDeleteEnterpriseContext(v3);
  if ( SecondTokenHandle )
    ZwClose(SecondTokenHandle);
  if ( v4 )
    SeReleaseSubjectContext(&SubjectContext);
  if ( Handle )
    ZwClose(Handle);
  if ( TokenHandle )
    ZwClose(TokenHandle);
  if ( v5 )
    SrpDeleteEnterpriseContext(v5);
  return (unsigned int)IsEnterpriseExempt;
}

```

## disassembly

```asm
0x14002c524  push    rbp
0x14002c526  push    rbx
0x14002c527  push    rsi
0x14002c528  push    rdi
0x14002c529  push    r12
0x14002c52b  push    r14
0x14002c52d  push    r15
0x14002c52f  lea     rbp, [rsp-27h]
0x14002c534  sub     rsp, 0A0h
0x14002c53b  xor     r12d, r12d
0x14002c53e  xorps   xmm0, xmm0
0x14002c541  mov     [rbp+57h+arg_8], r12b
0x14002c545  mov     r14, rcx
0x14002c548  mov     [rbp+57h+Equal], r12b
0x14002c54c  mov     esi, r12d
0x14002c54f  mov     [rbp+57h+var_70], r12
0x14002c553  mov     r15b, r12b
0x14002c556  mov     [rbp+57h+TokenInformation], r12d
0x14002c55a  mov     edi, r12d
0x14002c55d  mov     [rbp+57h+Handle], r12
0x14002c561  mov     [rbp+57h+TokenHandle], r12
0x14002c565  mov     [rbp+57h+var_80], r12d
0x14002c569  mov     [rbp+57h+SecondTokenHandle], r12
0x14002c56d  mov     [rbp+57h+var_78], r12
0x14002c571  mov     [rbp+57h+var_58], r12
0x14002c575  mov     [rbp+57h+var_60], r12
0x14002c579  movups  xmmword ptr [rbp+57h+SubjectContext.ClientToken], xmm0
0x14002c57d  movups  xmmword ptr [rbp+57h+SubjectContext.PrimaryToken], xmm0
0x14002c581  cmp     edx, 18h
0x14002c584  jnb     short loc_14002C590
0x14002c586  mov     ebx, 0C000000Dh
0x14002c58b  jmp     loc_14002C7B4
0x14002c590  cmp     qword ptr [rcx+10h], 2
0x14002c595  jnb     short loc_14002C586
0x14002c597  mov     rcx, [rcx]
0x14002c59a  lea     r8, [rbp+57h+Handle]
0x14002c59e  mov     edx, 8
0x14002c5a3  call    EdppOpenKernelTokenHandle
0x14002c5a8  mov     ebx, eax
0x14002c5aa  test    eax, eax
0x14002c5ac  js      loc_14002C7B4
0x14002c5b2  mov     rcx, [r14+8]
0x14002c5b6  lea     r8, [rbp+57h+TokenHandle]
0x14002c5ba  mov     edx, 8Ch
0x14002c5bf  call    EdppOpenKernelTokenHandle
0x14002c5c4  mov     ebx, eax
0x14002c5c6  test    eax, eax
0x14002c5c8  jns     short loc_14002C5E3
0x14002c5ca  mov     rcx, [rbp+57h+Handle]; Handle
0x14002c5ce  call    cs:__imp_ZwClose
0x14002c5d5  nop     dword ptr [rax+rax+00h]
0x14002c5da  mov     [rbp+57h+Handle], r12
0x14002c5de  jmp     loc_14002C7B4
0x14002c5e3  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x14002c5e7  lea     rax, [rbp+57h+var_80]
0x14002c5eb  mov     r14, [r14+10h]
0x14002c5ef  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x14002c5f3  mov     r9d, 4; TokenInformationLength
0x14002c5f9  mov     [rsp+0D0h+ReturnLength], rax; ReturnLength
0x14002c5fe  lea     edx, [r9+5]; TokenInformationClass
0x14002c602  call    cs:__imp_ZwQueryInformationToken
0x14002c609  nop     dword ptr [rax+rax+00h]
0x14002c60e  mov     ebx, eax
0x14002c610  test    eax, eax
0x14002c612  js      loc_14002C7B4
0x14002c618  cmp     [rbp+57h+TokenInformation], 2
0x14002c61c  jz      short loc_14002C628
0x14002c61e  mov     ebx, 0C0000022h
0x14002c623  jmp     loc_14002C7B4
0x14002c628  xorps   xmm0, xmm0
0x14002c62b  lea     rcx, [rbp+57h+SubjectContext]; SubjectContext
0x14002c62f  movups  xmmword ptr [rbp+57h+SubjectContext.ClientToken], xmm0
0x14002c633  movups  xmmword ptr [rbp+57h+SubjectContext.PrimaryToken], xmm0
0x14002c637  call    cs:__imp_SeCaptureSubjectContext
0x14002c63e  nop     dword ptr [rax+rax+00h]
0x14002c643  lea     rdx, [rbp+57h+arg_8]
0x14002c647  mov     r15b, 1
0x14002c64a  lea     rcx, [rbp+57h+SubjectContext]
0x14002c64e  call    SrpIsEnterpriseExempt
0x14002c653  mov     ebx, eax
0x14002c655  test    eax, eax
0x14002c657  js      loc_14002C7B4
0x14002c65d  mov     dl, r15b
0x14002c660  lea     rcx, [rbp+57h+SubjectContext]
0x14002c664  call    cs:__imp_RtlIsSandboxedToken
0x14002c66b  nop     dword ptr [rax+rax+00h]
0x14002c670  cmp     [rbp+57h+arg_8], r12b
0x14002c674  jnz     short loc_14002C67A
0x14002c676  test    al, al
0x14002c678  jnz     short loc_14002C61E
0x14002c67a  mov     rax, [rbp+57h+SubjectContext.ClientToken]
0x14002c67e  mov     rcx, [rbp+57h+SubjectContext.PrimaryToken]
0x14002c682  test    rax, rax
0x14002c685  cmovnz  rcx, rax; Object
0x14002c689  test    rcx, rcx
0x14002c68c  jz      short loc_14002C61E
0x14002c68e  lea     rax, [rbp+57h+SecondTokenHandle]
0x14002c692  mov     r9d, 8; DesiredAccess
0x14002c698  mov     [rsp+0D0h+var_A0], rax; Handle
0x14002c69d  xor     r8d, r8d; PassedAccessState
0x14002c6a0  mov     [rsp+0D0h+AccessMode], r12b; AccessMode
0x14002c6a5  mov     edx, 200h; HandleAttributes
0x14002c6aa  mov     [rsp+0D0h+ReturnLength], r12; ObjectType
0x14002c6af  call    cs:__imp_ObOpenObjectByPointer
0x14002c6b6  nop     dword ptr [rax+rax+00h]
0x14002c6bb  mov     ebx, eax
0x14002c6bd  test    eax, eax
0x14002c6bf  js      loc_14002C7B4
0x14002c6c5  mov     rdx, [rbp+57h+SecondTokenHandle]; SecondTokenHandle
0x14002c6c9  lea     r8, [rbp+57h+Equal]; Equal
0x14002c6cd  mov     rcx, [rbp+57h+TokenHandle]; FirstTokenHandle
0x14002c6d1  call    cs:__imp_ZwCompareTokens
0x14002c6d8  nop     dword ptr [rax+rax+00h]
0x14002c6dd  mov     ebx, eax
0x14002c6df  test    eax, eax
0x14002c6e1  js      loc_14002C7B4
0x14002c6e7  cmp     [rbp+57h+Equal], r12b
0x14002c6eb  jz      loc_14002C61E
0x14002c6f1  mov     rcx, [rbp+57h+Handle]
0x14002c6f5  lea     rdx, [rbp+57h+var_70]
0x14002c6f9  call    SrpGetEnterpriseContextToken
0x14002c6fe  mov     ebx, eax
0x14002c700  test    eax, eax
0x14002c702  js      loc_14002C7B0
0x14002c708  mov     rcx, [rbp+57h+Handle]
0x14002c70c  lea     rdx, [rbp+57h+var_60]
0x14002c710  call    SrpGetEvaluationFlagsToken
0x14002c715  mov     ebx, eax
0x14002c717  test    eax, eax
0x14002c719  js      loc_14002C7B0
0x14002c71f  mov     rsi, [rbp+57h+var_70]
0x14002c723  test    r15b, r14b
0x14002c726  jz      short loc_14002C738
0x14002c728  mov     rax, [rsi+8]
0x14002c72c  test    al, 2
0x14002c72e  jz      short loc_14002C738
0x14002c730  or      rax, 8
0x14002c734  mov     [rsi+8], rax
0x14002c738  mov     rax, [rbp+57h+var_60]
0x14002c73c  xor     r8d, r8d
0x14002c73f  mov     rcx, [rbp+57h+TokenHandle]
0x14002c743  mov     qword ptr [rsp+0D0h+AccessMode], rax
0x14002c748  mov     [rsp+0D0h+ReturnLength], rsi
0x14002c74d  call    SrpSetEnterpriseContextToken
0x14002c752  mov     ebx, eax
0x14002c754  test    eax, eax
0x14002c756  js      short loc_14002C7B4
0x14002c758  mov     rcx, [rbp+57h+Handle]
0x14002c75c  lea     rdx, [rbp+57h+var_78]
0x14002c760  call    SrpGetAppUniqueIdFromToken
0x14002c765  mov     ebx, eax
0x14002c767  test    eax, eax
0x14002c769  js      short loc_14002C7AA
0x14002c76b  mov     rcx, [rbp+57h+Handle]
0x14002c76f  lea     rdx, [rbp+57h+var_58]
0x14002c773  call    SrpGetProcessUniqueIdFromToken
0x14002c778  mov     ebx, eax
0x14002c77a  test    eax, eax
0x14002c77c  js      short loc_14002C7AA
0x14002c77e  mov     rdi, [rbp+57h+var_78]
0x14002c782  test    rdi, rdi
0x14002c785  jz      short loc_14002C799
0x14002c787  mov     rcx, [rbp+57h+TokenHandle]
0x14002c78b  mov     rdx, rdi
0x14002c78e  call    SrpSetInheritedAppUniqueIdOnToken
0x14002c793  mov     ebx, eax
0x14002c795  test    eax, eax
0x14002c797  js      short loc_14002C7B4
0x14002c799  mov     rdx, [rbp+57h+var_58]
0x14002c79d  mov     rcx, [rbp+57h+TokenHandle]
0x14002c7a1  call    SrpSetInheritedProcessUniqueIdOnToken
0x14002c7a6  mov     ebx, eax
0x14002c7a8  jmp     short loc_14002C7B4
0x14002c7aa  mov     rdi, [rbp+57h+var_78]
0x14002c7ae  jmp     short loc_14002C7B4
0x14002c7b0  mov     rsi, [rbp+57h+var_70]
0x14002c7b4  mov     rcx, rsi
0x14002c7b7  call    SrpDeleteEnterpriseContext
0x14002c7bc  mov     rcx, [rbp+57h+SecondTokenHandle]; Handle
0x14002c7c0  test    rcx, rcx
0x14002c7c3  jz      short loc_14002C7D1
0x14002c7c5  call    cs:__imp_ZwClose
0x14002c7cc  nop     dword ptr [rax+rax+00h]
0x14002c7d1  test    r15b, r15b
0x14002c7d4  jz      short loc_14002C7E6
0x14002c7d6  lea     rcx, [rbp+57h+SubjectContext]; SubjectContext
0x14002c7da  call    cs:__imp_SeReleaseSubjectContext
0x14002c7e1  nop     dword ptr [rax+rax+00h]
0x14002c7e6  mov     rcx, [rbp+57h+Handle]; Handle
0x14002c7ea  test    rcx, rcx
0x14002c7ed  jz      short loc_14002C7FB
0x14002c7ef  call    cs:__imp_ZwClose
0x14002c7f6  nop     dword ptr [rax+rax+00h]
0x14002c7fb  mov     rcx, [rbp+57h+TokenHandle]; Handle
0x14002c7ff  test    rcx, rcx
0x14002c802  jz      short loc_14002C810
0x14002c804  call    cs:__imp_ZwClose
0x14002c80b  nop     dword ptr [rax+rax+00h]
0x14002c810  test    rdi, rdi
0x14002c813  jz      short loc_14002C81D
0x14002c815  mov     rcx, rdi
0x14002c818  call    SrpDeleteEnterpriseContext
0x14002c81d  mov     eax, ebx
0x14002c81f  add     rsp, 0A0h
0x14002c826  pop     r15
0x14002c828  pop     r14
0x14002c82a  pop     r12
0x14002c82c  pop     rdi
0x14002c82d  pop     rsi
0x14002c82e  pop     rbx
0x14002c82f  pop     rbp
0x14002c830  retn
```
