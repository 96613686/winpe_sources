# wil::details::FeatureImpl<__WilFeatureTraits_Feature_55648890>::GetCachedFeatureEnabledState(void)

- ea: `0x18001a6a0`
- end: `0x18001a880`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_55648890@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `480`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180019f30`

## callees

- `0x18000fdc0`
- `0x1800100b0`
- `0x18001a6a0`
- `0x180034ef0`
- `0x18003bed0`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001a820`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001a820`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18001a7df`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18001a7df`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_55648890>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v4; // eax
  int v5; // ebp
  __int64 (__fastcall *v6)(__int64, _QWORD, int *); // rax
  int v7; // eax
  unsigned int v8; // r8d
  int v9; // ecx
  int v10; // eax
  unsigned int v11; // eax
  int v12; // edi
  signed __int32 v13; // eax
  signed __int32 v14; // edx
  signed __int32 v15; // ecx
  int v16; // ecx
  int v17; // r8d
  unsigned __int64 v18; // r8
  int v19; // ecx
  _QWORD v21[2]; // [rsp+20h] [rbp-38h] BYREF
  int v22; // [rsp+30h] [rbp-28h] BYREF

  *a2 = 0;
  v4 = *(_DWORD *)a1;
  *(_DWORD *)a2 = *(_DWORD *)a1;
  if ( (v4 & 6) == 6 )
    return a2;
  v5 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
  v6 = (__int64 (__fastcall *)(__int64, _QWORD, int *))g_wil_details_internalGetFeatureEnabledState;
  if ( g_wil_details_internalGetFeatureEnabledState
    || (v6 = (__int64 (__fastcall *)(__int64, _QWORD, int *))g_wil_details_apiGetFeatureEnabledState) != 0 )
  {
    v7 = v6(55648890, 0, &v22);
    v8 = v7 & 0xFFFFFF3F;
    v9 = 8 * (v7 & 0x80 | (4 * (v7 & 0x40 | (4 * (v7 & 3)))));
    if ( (v7 & 0xFFFFFF3F) != 0 )
    {
      v10 = 0;
      if ( v8 == 2 )
        v10 = 64;
      v11 = v9 | v10;
      goto LABEL_10;
    }
  }
  else
  {
    v9 = 0;
  }
  v11 = v9 | 0x40;
LABEL_10:
  v12 = v11 | (v11 >> 6) & 1;
  if ( !v5 )
    v22 = 0;
  v13 = *(_DWORD *)a2;
  do
  {
    v14 = v13;
    *(_DWORD *)a2 = v13;
    v15 = v13;
    if ( v22 && (v13 & 2) == 0 )
    {
      v16 = v13
          ^ ((unsigned __int16)v12
           ^ (unsigned __int16)v13)
          & 0x180
          ^ ((unsigned __int8)v12
           ^ (unsigned __int8)(v13 ^ (v12 ^ v13) & 0x80))
          & 0x40;
      v15 = v16
          ^ ((unsigned __int8)v12
           ^ (unsigned __int8)v16)
          & 1
          ^ ((unsigned __int16)v12
           ^ (unsigned __int16)(v16 ^ ((unsigned __int8)v12 ^ (unsigned __int8)v16) & 1))
          & 0x800
          | 2;
      *(_DWORD *)a2 = v15;
    }
    v17 = v13 & 4;
    if ( (v13 & 4) == 0 )
    {
      v15 = ((unsigned __int16)v15 ^ (unsigned __int16)v12) & 0x400 ^ v15 | 4;
      *(_DWORD *)a2 = v15;
    }
    v13 = _InterlockedCompareExchange((volatile signed __int32 *)a1, v15, v13);
  }
  while ( v14 != v13 );
  if ( !v17 && wil::details::g_enabledStateManager )
  {
    AcquireSRWLockExclusive(&SRWLock);
    if ( !v5
      || v5 != dword_1800583FC
      || (v21[0] = 0,
          v21[1] = a1,
          !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180058430, v21, v18)) )
    {
      _InterlockedAnd((volatile signed __int32 *)a1, 0xFFFFF7C1);
    }
    ReleaseSRWLockExclusive(&SRWLock);
  }
  if ( (*(_DWORD *)a2 & 2) == 0 )
  {
    v19 = *(_DWORD *)a2
        ^ ((unsigned __int16)v12
         ^ (unsigned __int16)*(_DWORD *)a2)
        & 0x180
        ^ ((unsigned __int8)v12
         ^ (unsigned __int8)(*(_DWORD *)a2 ^ (v12 ^ *(_DWORD *)a2) & 0x80))
        & 0x40;
    *(_DWORD *)a2 = v19
                  ^ ((unsigned __int8)v12
                   ^ (unsigned __int8)v19)
                  & 1
                  ^ ((unsigned __int16)v12
                   ^ (unsigned __int16)(v19 ^ ((unsigned __int8)v12 ^ (unsigned __int8)v19) & 1))
                  & 0x800;
  }
  return a2;
}

```

## disassembly

```asm
0x18001a6a0  push    rbx
0x18001a6a2  push    rsi
0x18001a6a3  push    r14
0x18001a6a5  sub     rsp, 40h
0x18001a6a9  mov     rax, cs:__security_cookie
0x18001a6b0  xor     rax, rsp
0x18001a6b3  mov     [rsp+58h+var_20], rax
0x18001a6b8  xor     r14d, r14d
0x18001a6bb  mov     rbx, rdx
0x18001a6be  mov     [rdx], r14
0x18001a6c1  mov     rsi, rcx
0x18001a6c4  mov     eax, [rcx]
0x18001a6c6  mov     [rdx], eax
0x18001a6c8  and     eax, 6
0x18001a6cb  cmp     al, 6
0x18001a6cd  jz      loc_18001A87B
0x18001a6d3  mov     [rsp+58h+arg_10], rbp
0x18001a6d8  mov     [rsp+58h+arg_18], rdi
0x18001a6dd  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001a6e2  mov     ebp, eax
0x18001a6e4  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18001a6eb  test    rax, rax
0x18001a6ee  jnz     short loc_18001A6FC
0x18001a6f0  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18001a6f7  test    rax, rax
0x18001a6fa  jz      short loc_18001A74E
0x18001a6fc  lea     r8, [rsp+58h+var_28]
0x18001a701  xor     edx, edx
0x18001a703  mov     ecx, 351227Ah
0x18001a708  call    cs:__guard_dispatch_icall_fptr
0x18001a70e  mov     r8d, eax
0x18001a711  mov     edx, eax
0x18001a713  and     r8d, 0FFFFFF3Fh
0x18001a71a  and     eax, 40h
0x18001a71d  and     edx, 80h
0x18001a723  mov     ecx, r8d
0x18001a726  and     ecx, 3
0x18001a729  shl     ecx, 2
0x18001a72c  or      ecx, eax
0x18001a72e  shl     ecx, 2
0x18001a731  or      ecx, edx
0x18001a733  shl     ecx, 3
0x18001a736  test    r8d, r8d
0x18001a739  jz      short loc_18001A751
0x18001a73b  cmp     r8d, 2
0x18001a73f  mov     eax, r14d
0x18001a742  mov     edx, 40h ; '@'
0x18001a747  cmovz   eax, edx
0x18001a74a  or      eax, ecx
0x18001a74c  jmp     short loc_18001A756
0x18001a74e  mov     ecx, r14d
0x18001a751  mov     eax, ecx
0x18001a753  or      eax, 40h
0x18001a756  mov     edi, eax
0x18001a758  shr     edi, 6
0x18001a75b  and     edi, 1
0x18001a75e  or      edi, eax
0x18001a760  test    ebp, ebp
0x18001a762  jnz     short loc_18001A769
0x18001a764  mov     [rsp+58h+var_28], r14d
0x18001a769  mov     eax, [rbx]
0x18001a76b  mov     edx, eax
0x18001a76d  mov     [rbx], eax
0x18001a76f  mov     ecx, eax
0x18001a771  cmp     [rsp+58h+var_28], r14d
0x18001a776  jz      short loc_18001A7A9
0x18001a778  test    dl, 2
0x18001a77b  jnz     short loc_18001A7A9
0x18001a77d  xor     eax, edi
0x18001a77f  and     eax, 180h
0x18001a784  xor     eax, ecx
0x18001a786  mov     ecx, eax
0x18001a788  xor     ecx, edi
0x18001a78a  and     ecx, 40h
0x18001a78d  xor     ecx, eax
0x18001a78f  mov     eax, ecx
0x18001a791  xor     eax, edi
0x18001a793  and     eax, 1
0x18001a796  xor     eax, ecx
0x18001a798  mov     ecx, eax
0x18001a79a  xor     ecx, edi
0x18001a79c  and     ecx, 800h
0x18001a7a2  xor     ecx, eax
0x18001a7a4  or      ecx, 2
0x18001a7a7  mov     [rbx], ecx
0x18001a7a9  mov     r8d, edx
0x18001a7ac  and     r8d, 4
0x18001a7b0  jnz     short loc_18001A7C2
0x18001a7b2  mov     eax, edi
0x18001a7b4  xor     eax, ecx
0x18001a7b6  and     eax, 400h
0x18001a7bb  xor     ecx, eax
0x18001a7bd  or      ecx, 4
0x18001a7c0  mov     [rbx], ecx
0x18001a7c2  mov     eax, edx
0x18001a7c4  lock cmpxchg [rsi], ecx
0x18001a7c8  jnz     short loc_18001A76B
0x18001a7ca  test    r8d, r8d
0x18001a7cd  jnz     short loc_18001A826
0x18001a7cf  cmp     cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A, r14b; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18001a7d6  jz      short loc_18001A826
0x18001a7d8  lea     rcx, SRWLock; SRWLock
0x18001a7df  call    cs:__imp_AcquireSRWLockExclusive
0x18001a7e5  mov     eax, cs:dword_1800583FC
0x18001a7eb  test    ebp, ebp
0x18001a7ed  jz      short loc_18001A812
0x18001a7ef  cmp     ebp, eax
0x18001a7f1  jnz     short loc_18001A812
0x18001a7f3  lea     rdx, [rsp+58h+var_38]; void *
0x18001a7f8  mov     [rsp+58h+var_38], r14
0x18001a7fd  lea     rcx, qword_180058430; this
0x18001a804  mov     [rsp+58h+var_30], rsi
0x18001a809  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18001a80e  test    al, al
0x18001a810  jnz     short loc_18001A819
0x18001a812  lock and dword ptr [rsi], 0FFFFF7C1h
0x18001a819  lea     rcx, SRWLock; SRWLock
0x18001a820  call    cs:__imp_ReleaseSRWLockExclusive
0x18001a826  mov     ecx, [rbx]
0x18001a828  mov     rbp, [rsp+58h+arg_10]
0x18001a82d  test    cl, 2
0x18001a830  jnz     short loc_18001A85D
0x18001a832  mov     eax, ecx
0x18001a834  xor     eax, edi
0x18001a836  and     eax, 180h
0x18001a83b  xor     eax, ecx
0x18001a83d  mov     ecx, eax
0x18001a83f  xor     ecx, edi
0x18001a841  and     ecx, 40h
0x18001a844  xor     ecx, eax
0x18001a846  mov     edx, ecx
0x18001a848  xor     edx, edi
0x18001a84a  and     edx, 1
0x18001a84d  xor     edx, ecx
0x18001a84f  mov     ecx, edx
0x18001a851  xor     ecx, edi
0x18001a853  and     ecx, 800h
0x18001a859  xor     ecx, edx
0x18001a85b  mov     [rbx], ecx
0x18001a85d  mov     rdi, [rsp+58h+arg_18]
0x18001a862  mov     rax, rbx
0x18001a865  mov     rcx, [rsp+58h+var_20]
0x18001a86a  xor     rcx, rsp; StackCookie
0x18001a86d  call    __security_check_cookie
0x18001a872  add     rsp, 40h
0x18001a876  pop     r14
0x18001a878  pop     rsi
0x18001a879  pop     rbx
0x18001a87a  retn
0x18001a87b  mov     rax, rbx
0x18001a87e  jmp     short loc_18001A865
```
