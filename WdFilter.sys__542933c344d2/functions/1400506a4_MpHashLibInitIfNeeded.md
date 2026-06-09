# MpHashLibInitIfNeeded

- ea: `0x1400506a4`
- end: `0x140050848`
- name: `MpHashLibInitIfNeeded`
- size: `420`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140050460`

## callees

- `0x1400026c0`
- `0x1400118d0`
- `0x1400506a4`
- `0x140080834`

## import_xrefs

- `ntoskrnl!ExInitializeLookasideListEx` at `0x1400507a6`
- `ntoskrnl!ExInitializeLookasideListEx` at `0x1400507a6`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x140050728`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x140050728`
- `ksecdd!BCryptGetProperty` at `0x140050766`
- `ksecdd!BCryptGetProperty` at `0x1400507e5`
- `ksecdd!BCryptGetProperty` at `0x140050766`
- `ksecdd!BCryptGetProperty` at `0x1400507e5`

## pseudocode

```c
__int64 MpHashLibInitIfNeeded()
{
  __int64 PoolWithTag; // rax
  signed __int64 v2; // rbx
  BCRYPT_HANDLE *v3; // r14
  NTSTATUS Property; // edi
  _DWORD *v5; // rsi
  BCRYPT_HANDLE v6; // rcx
  ULONG pcbResult; // [rsp+40h] [rbp-18h] BYREF

  if ( _InterlockedCompareExchange64((volatile signed __int64 *)&MpHashLibData, 0, 0) )
    return 0;
  pcbResult = 0;
  PoolWithTag = MpAllocatePoolWithTag((unsigned int)ExDefaultNonPagedPoolType, 144, 1751404621);
  v2 = PoolWithTag;
  if ( !PoolWithTag )
    return 3221225626LL;
  v3 = (BCRYPT_HANDLE *)(PoolWithTag + 8);
  *(_DWORD *)PoolWithTag = 9493028;
  Property = BCryptOpenAlgorithmProvider((BCRYPT_ALG_HANDLE *)(PoolWithTag + 8), L"SHA256", 0, 0);
  if ( Property < 0 )
    goto LABEL_12;
  _mm_lfence();
  v5 = (_DWORD *)(v2 + 16);
  Property = BCryptGetProperty(*v3, L"ObjectLength", (PUCHAR)(v2 + 16), 4u, &pcbResult, 0);
  if ( Property < 0 )
    goto LABEL_12;
  _mm_lfence();
  Property = ExInitializeLookasideListEx(
               (PLOOKASIDE_LIST_EX)(v2 + 32),
               0,
               0,
               PagedPool,
               0,
               (unsigned int)*v5,
               0x6868504Du,
               0);
  if ( Property < 0 )
    goto LABEL_12;
  _mm_lfence();
  v6 = *v3;
  *(_DWORD *)(v2 + 128) = *v5;
  Property = BCryptGetProperty(v6, L"HashDigestLength", (PUCHAR)(v2 + 20), 4u, &pcbResult, 0);
  if ( Property < 0 )
    goto LABEL_12;
  if ( *(_DWORD *)(v2 + 20) > 0x20u )
  {
    Property = -1073741789;
LABEL_12:
    MpHashLibReleaseImpl((PVOID)v2);
    return (unsigned int)Property;
  }
  *(_BYTE *)(v2 + 24) = 1;
  if ( _InterlockedCompareExchange64((volatile signed __int64 *)&MpHashLibData, v2, 0) )
    goto LABEL_12;
  return (unsigned int)Property;
}

```

## disassembly

```asm
0x1400506a4  mov     rax, rsp
0x1400506a7  mov     [rax+8], rbx
0x1400506ab  mov     [rax+10h], rbp
0x1400506af  mov     [rax+18h], rsi
0x1400506b3  mov     [rax+20h], rdi
0x1400506b7  push    r14
0x1400506b9  sub     rsp, 50h
0x1400506bd  mov     rax, cs:__security_cookie
0x1400506c4  xor     rax, rsp
0x1400506c7  mov     [rsp+58h+var_10], rax
0x1400506cc  xor     ebp, ebp
0x1400506ce  xor     eax, eax
0x1400506d0  lock cmpxchg cs:MpHashLibData, rbp
0x1400506d9  jz      short loc_1400506E2
0x1400506db  xor     eax, eax
0x1400506dd  jmp     loc_14005081F
0x1400506e2  mov     ecx, cs:ExDefaultNonPagedPoolType
0x1400506e8  mov     edx, 90h
0x1400506ed  mov     r8d, 6864504Dh
0x1400506f3  mov     [rsp+58h+var_18], ebp
0x1400506f7  call    MpAllocatePoolWithTag
0x1400506fc  mov     rbx, rax
0x1400506ff  test    rax, rax
0x140050702  jnz     short loc_14005070E
0x140050704  mov     eax, 0C000009Ah
0x140050709  jmp     loc_14005081F
0x14005070e  lea     r14, [rax+8]
0x140050712  mov     dword ptr [rax], 90DA24h
0x140050718  mov     rcx, r14; phAlgorithm
0x14005071b  lea     rdx, pszAlgId; "SHA256"
0x140050722  xor     r9d, r9d; dwFlags
0x140050725  xor     r8d, r8d; pszImplementation
0x140050728  call    cs:__imp_BCryptOpenAlgorithmProvider
0x14005072f  nop     dword ptr [rax+rax+00h]
0x140050734  mov     edi, eax
0x140050736  test    eax, eax
0x140050738  js      loc_140050815
0x14005073e  lfence
0x140050741  mov     rcx, [r14]; hObject
0x140050744  lea     rax, [rsp+58h+var_18]
0x140050749  lea     rsi, [rbx+10h]
0x14005074d  mov     [rsp+58h+dwFlags], ebp; dwFlags
0x140050751  mov     r8, rsi; pbOutput
0x140050754  mov     [rsp+58h+pcbResult], rax; pcbResult
0x140050759  mov     r9d, 4; cbOutput
0x14005075f  lea     rdx, pszProperty; "ObjectLength"
0x140050766  call    cs:__imp_BCryptGetProperty
0x14005076d  nop     dword ptr [rax+rax+00h]
0x140050772  mov     edi, eax
0x140050774  test    eax, eax
0x140050776  js      loc_140050815
0x14005077c  lfence
0x14005077f  mov     eax, [rsi]
0x140050781  lea     rcx, [rbx+20h]; Lookaside
0x140050785  mov     [rsp+58h+Depth], bp; Depth
0x14005078a  mov     r9d, 1; PoolType
0x140050790  mov     [rsp+58h+Tag], 6868504Dh; Tag
0x140050798  xor     r8d, r8d; Free
0x14005079b  mov     qword ptr [rsp+58h+dwFlags], rax; Size
0x1400507a0  xor     edx, edx; Allocate
0x1400507a2  mov     dword ptr [rsp+58h+pcbResult], ebp; Flags
0x1400507a6  call    cs:__imp_ExInitializeLookasideListEx
0x1400507ad  nop     dword ptr [rax+rax+00h]
0x1400507b2  mov     edi, eax
0x1400507b4  test    eax, eax
0x1400507b6  js      short loc_140050815
0x1400507b8  lfence
0x1400507bb  mov     eax, [rsi]
0x1400507bd  lea     r8, [rbx+14h]; pbOutput
0x1400507c1  mov     rcx, [r14]; hObject
0x1400507c4  lea     rdx, aHashdigestleng; "HashDigestLength"
0x1400507cb  mov     [rbx+80h], eax
0x1400507d1  mov     r9d, 4; cbOutput
0x1400507d7  lea     rax, [rsp+58h+var_18]
0x1400507dc  mov     [rsp+58h+dwFlags], ebp; dwFlags
0x1400507e0  mov     [rsp+58h+pcbResult], rax; pcbResult
0x1400507e5  call    cs:__imp_BCryptGetProperty
0x1400507ec  nop     dword ptr [rax+rax+00h]
0x1400507f1  mov     edi, eax
0x1400507f3  test    eax, eax
0x1400507f5  js      short loc_140050815
0x1400507f7  cmp     dword ptr [rbx+14h], 20h ; ' '
0x1400507fb  jbe     short loc_140050804
0x1400507fd  mov     edi, 0C0000023h
0x140050802  jmp     short loc_140050815
0x140050804  mov     byte ptr [rbx+18h], 1
0x140050808  xor     eax, eax
0x14005080a  lock cmpxchg cs:MpHashLibData, rbx
0x140050813  jz      short loc_14005081D
0x140050815  mov     rcx, rbx; P
0x140050818  call    MpHashLibReleaseImpl
0x14005081d  mov     eax, edi
0x14005081f  mov     rcx, [rsp+58h+var_10]
0x140050824  xor     rcx, rsp; StackCookie
0x140050827  call    __security_check_cookie
0x14005082c  mov     rbx, [rsp+58h+arg_0]
0x140050831  mov     rbp, [rsp+58h+arg_8]
0x140050836  mov     rsi, [rsp+58h+arg_10]
0x14005083b  mov     rdi, [rsp+58h+arg_18]
0x140050840  add     rsp, 50h
0x140050844  pop     r14
0x140050846  retn
```
