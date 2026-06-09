# wil::details::FeatureImpl<__WilFeatureTraits_Feature_iCxz8Qnks>::GetCachedFeatureEnabledState(void)

- ea: `0x18000eaa0`
- end: `0x18000ec80`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_iCxz8Qnks@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `480`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000e370`
- `0x180029c70`

## callees

- `0x18000eaa0`
- `0x18000fdc0`
- `0x1800100b0`
- `0x180034ef0`
- `0x18003bed0`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000ec20`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000ec20`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000ebdf`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000ebdf`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_iCxz8Qnks>::GetCachedFeatureEnabledState(
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
    v7 = v6(53668051, 0, &v22);
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
0x18000eaa0  push    rbx
0x18000eaa2  push    rsi
0x18000eaa3  push    r14
0x18000eaa5  sub     rsp, 40h
0x18000eaa9  mov     rax, cs:__security_cookie
0x18000eab0  xor     rax, rsp
0x18000eab3  mov     [rsp+58h+var_20], rax
0x18000eab8  xor     r14d, r14d
0x18000eabb  mov     rbx, rdx
0x18000eabe  mov     [rdx], r14
0x18000eac1  mov     rsi, rcx
0x18000eac4  mov     eax, [rcx]
0x18000eac6  mov     [rdx], eax
0x18000eac8  and     eax, 6
0x18000eacb  cmp     al, 6
0x18000eacd  jz      loc_18000EC7B
0x18000ead3  mov     [rsp+58h+arg_10], rbp
0x18000ead8  mov     [rsp+58h+arg_18], rdi
0x18000eadd  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000eae2  mov     ebp, eax
0x18000eae4  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000eaeb  test    rax, rax
0x18000eaee  jnz     short loc_18000EAFC
0x18000eaf0  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000eaf7  test    rax, rax
0x18000eafa  jz      short loc_18000EB4E
0x18000eafc  lea     r8, [rsp+58h+var_28]
0x18000eb01  xor     edx, edx
0x18000eb03  mov     ecx, 332E8D3h
0x18000eb08  call    cs:__guard_dispatch_icall_fptr
0x18000eb0e  mov     r8d, eax
0x18000eb11  mov     edx, eax
0x18000eb13  and     r8d, 0FFFFFF3Fh
0x18000eb1a  and     eax, 40h
0x18000eb1d  and     edx, 80h
0x18000eb23  mov     ecx, r8d
0x18000eb26  and     ecx, 3
0x18000eb29  shl     ecx, 2
0x18000eb2c  or      ecx, eax
0x18000eb2e  shl     ecx, 2
0x18000eb31  or      ecx, edx
0x18000eb33  shl     ecx, 3
0x18000eb36  test    r8d, r8d
0x18000eb39  jz      short loc_18000EB51
0x18000eb3b  cmp     r8d, 2
0x18000eb3f  mov     eax, r14d
0x18000eb42  mov     edx, 40h ; '@'
0x18000eb47  cmovz   eax, edx
0x18000eb4a  or      eax, ecx
0x18000eb4c  jmp     short loc_18000EB56
0x18000eb4e  mov     ecx, r14d
0x18000eb51  mov     eax, ecx
0x18000eb53  or      eax, 40h
0x18000eb56  mov     edi, eax
0x18000eb58  shr     edi, 6
0x18000eb5b  and     edi, 1
0x18000eb5e  or      edi, eax
0x18000eb60  test    ebp, ebp
0x18000eb62  jnz     short loc_18000EB69
0x18000eb64  mov     [rsp+58h+var_28], r14d
0x18000eb69  mov     eax, [rbx]
0x18000eb6b  mov     edx, eax
0x18000eb6d  mov     [rbx], eax
0x18000eb6f  mov     ecx, eax
0x18000eb71  cmp     [rsp+58h+var_28], r14d
0x18000eb76  jz      short loc_18000EBA9
0x18000eb78  test    dl, 2
0x18000eb7b  jnz     short loc_18000EBA9
0x18000eb7d  xor     eax, edi
0x18000eb7f  and     eax, 180h
0x18000eb84  xor     eax, ecx
0x18000eb86  mov     ecx, eax
0x18000eb88  xor     ecx, edi
0x18000eb8a  and     ecx, 40h
0x18000eb8d  xor     ecx, eax
0x18000eb8f  mov     eax, ecx
0x18000eb91  xor     eax, edi
0x18000eb93  and     eax, 1
0x18000eb96  xor     eax, ecx
0x18000eb98  mov     ecx, eax
0x18000eb9a  xor     ecx, edi
0x18000eb9c  and     ecx, 800h
0x18000eba2  xor     ecx, eax
0x18000eba4  or      ecx, 2
0x18000eba7  mov     [rbx], ecx
0x18000eba9  mov     r8d, edx
0x18000ebac  and     r8d, 4
0x18000ebb0  jnz     short loc_18000EBC2
0x18000ebb2  mov     eax, edi
0x18000ebb4  xor     eax, ecx
0x18000ebb6  and     eax, 400h
0x18000ebbb  xor     ecx, eax
0x18000ebbd  or      ecx, 4
0x18000ebc0  mov     [rbx], ecx
0x18000ebc2  mov     eax, edx
0x18000ebc4  lock cmpxchg [rsi], ecx
0x18000ebc8  jnz     short loc_18000EB6B
0x18000ebca  test    r8d, r8d
0x18000ebcd  jnz     short loc_18000EC26
0x18000ebcf  cmp     cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A, r14b; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000ebd6  jz      short loc_18000EC26
0x18000ebd8  lea     rcx, SRWLock; SRWLock
0x18000ebdf  call    cs:__imp_AcquireSRWLockExclusive
0x18000ebe5  mov     eax, cs:dword_1800583FC
0x18000ebeb  test    ebp, ebp
0x18000ebed  jz      short loc_18000EC12
0x18000ebef  cmp     ebp, eax
0x18000ebf1  jnz     short loc_18000EC12
0x18000ebf3  lea     rdx, [rsp+58h+var_38]; void *
0x18000ebf8  mov     [rsp+58h+var_38], r14
0x18000ebfd  lea     rcx, qword_180058430; this
0x18000ec04  mov     [rsp+58h+var_30], rsi
0x18000ec09  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18000ec0e  test    al, al
0x18000ec10  jnz     short loc_18000EC19
0x18000ec12  lock and dword ptr [rsi], 0FFFFF7C1h
0x18000ec19  lea     rcx, SRWLock; SRWLock
0x18000ec20  call    cs:__imp_ReleaseSRWLockExclusive
0x18000ec26  mov     ecx, [rbx]
0x18000ec28  mov     rbp, [rsp+58h+arg_10]
0x18000ec2d  test    cl, 2
0x18000ec30  jnz     short loc_18000EC5D
0x18000ec32  mov     eax, ecx
0x18000ec34  xor     eax, edi
0x18000ec36  and     eax, 180h
0x18000ec3b  xor     eax, ecx
0x18000ec3d  mov     ecx, eax
0x18000ec3f  xor     ecx, edi
0x18000ec41  and     ecx, 40h
0x18000ec44  xor     ecx, eax
0x18000ec46  mov     edx, ecx
0x18000ec48  xor     edx, edi
0x18000ec4a  and     edx, 1
0x18000ec4d  xor     edx, ecx
0x18000ec4f  mov     ecx, edx
0x18000ec51  xor     ecx, edi
0x18000ec53  and     ecx, 800h
0x18000ec59  xor     ecx, edx
0x18000ec5b  mov     [rbx], ecx
0x18000ec5d  mov     rdi, [rsp+58h+arg_18]
0x18000ec62  mov     rax, rbx
0x18000ec65  mov     rcx, [rsp+58h+var_20]
0x18000ec6a  xor     rcx, rsp; StackCookie
0x18000ec6d  call    __security_check_cookie
0x18000ec72  add     rsp, 40h
0x18000ec76  pop     r14
0x18000ec78  pop     rsi
0x18000ec79  pop     rbx
0x18000ec7a  retn
0x18000ec7b  mov     rax, rbx
0x18000ec7e  jmp     short loc_18000EC65
```
