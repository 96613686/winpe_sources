# wil::details::FeatureImpl<__WilFeatureTraits_Feature_55709058>::GetCachedFeatureEnabledState(void)

- ea: `0x18000b3a0`
- end: `0x18000b580`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_55709058@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `480`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000ab70`
- `0x18000b580`

## callees

- `0x1800043f0`
- `0x180004880`
- `0x18000b3a0`
- `0x1800181b0`
- `0x18001cdf0`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x18000b4df`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000b4df`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000b520`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000b520`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_55709058>::GetCachedFeatureEnabledState(
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
    v7 = v6(55709058, 0, &v22);
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
      || v5 != dword_18002D33C
      || (v21[0] = 0,
          v21[1] = a1,
          !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_18002D370, v21, v18)) )
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
0x18000b3a0  push    rbx
0x18000b3a2  push    rsi
0x18000b3a3  push    r14
0x18000b3a5  sub     rsp, 40h
0x18000b3a9  mov     rax, cs:__security_cookie
0x18000b3b0  xor     rax, rsp
0x18000b3b3  mov     [rsp+58h+var_20], rax
0x18000b3b8  xor     r14d, r14d
0x18000b3bb  mov     rbx, rdx
0x18000b3be  mov     [rdx], r14
0x18000b3c1  mov     rsi, rcx
0x18000b3c4  mov     eax, [rcx]
0x18000b3c6  mov     [rdx], eax
0x18000b3c8  and     eax, 6
0x18000b3cb  cmp     al, 6
0x18000b3cd  jz      loc_18000B57B
0x18000b3d3  mov     [rsp+58h+arg_10], rbp
0x18000b3d8  mov     [rsp+58h+arg_18], rdi
0x18000b3dd  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000b3e2  mov     ebp, eax
0x18000b3e4  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000b3eb  test    rax, rax
0x18000b3ee  jnz     short loc_18000B3FC
0x18000b3f0  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000b3f7  test    rax, rax
0x18000b3fa  jz      short loc_18000B44E
0x18000b3fc  lea     r8, [rsp+58h+var_28]
0x18000b401  xor     edx, edx
0x18000b403  mov     ecx, 3520D82h
0x18000b408  call    cs:__guard_dispatch_icall_fptr
0x18000b40e  mov     r8d, eax
0x18000b411  mov     edx, eax
0x18000b413  and     r8d, 0FFFFFF3Fh
0x18000b41a  and     eax, 40h
0x18000b41d  and     edx, 80h
0x18000b423  mov     ecx, r8d
0x18000b426  and     ecx, 3
0x18000b429  shl     ecx, 2
0x18000b42c  or      ecx, eax
0x18000b42e  shl     ecx, 2
0x18000b431  or      ecx, edx
0x18000b433  shl     ecx, 3
0x18000b436  test    r8d, r8d
0x18000b439  jz      short loc_18000B451
0x18000b43b  cmp     r8d, 2
0x18000b43f  mov     eax, r14d
0x18000b442  mov     edx, 40h ; '@'
0x18000b447  cmovz   eax, edx
0x18000b44a  or      eax, ecx
0x18000b44c  jmp     short loc_18000B456
0x18000b44e  mov     ecx, r14d
0x18000b451  mov     eax, ecx
0x18000b453  or      eax, 40h
0x18000b456  mov     edi, eax
0x18000b458  shr     edi, 6
0x18000b45b  and     edi, 1
0x18000b45e  or      edi, eax
0x18000b460  test    ebp, ebp
0x18000b462  jnz     short loc_18000B469
0x18000b464  mov     [rsp+58h+var_28], r14d
0x18000b469  mov     eax, [rbx]
0x18000b46b  mov     edx, eax
0x18000b46d  mov     [rbx], eax
0x18000b46f  mov     ecx, eax
0x18000b471  cmp     [rsp+58h+var_28], r14d
0x18000b476  jz      short loc_18000B4A9
0x18000b478  test    dl, 2
0x18000b47b  jnz     short loc_18000B4A9
0x18000b47d  xor     eax, edi
0x18000b47f  and     eax, 180h
0x18000b484  xor     eax, ecx
0x18000b486  mov     ecx, eax
0x18000b488  xor     ecx, edi
0x18000b48a  and     ecx, 40h
0x18000b48d  xor     ecx, eax
0x18000b48f  mov     eax, ecx
0x18000b491  xor     eax, edi
0x18000b493  and     eax, 1
0x18000b496  xor     eax, ecx
0x18000b498  mov     ecx, eax
0x18000b49a  xor     ecx, edi
0x18000b49c  and     ecx, 800h
0x18000b4a2  xor     ecx, eax
0x18000b4a4  or      ecx, 2
0x18000b4a7  mov     [rbx], ecx
0x18000b4a9  mov     r8d, edx
0x18000b4ac  and     r8d, 4
0x18000b4b0  jnz     short loc_18000B4C2
0x18000b4b2  mov     eax, edi
0x18000b4b4  xor     eax, ecx
0x18000b4b6  and     eax, 400h
0x18000b4bb  xor     ecx, eax
0x18000b4bd  or      ecx, 4
0x18000b4c0  mov     [rbx], ecx
0x18000b4c2  mov     eax, edx
0x18000b4c4  lock cmpxchg [rsi], ecx
0x18000b4c8  jnz     short loc_18000B46B
0x18000b4ca  test    r8d, r8d
0x18000b4cd  jnz     short loc_18000B526
0x18000b4cf  cmp     cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A, r14b; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000b4d6  jz      short loc_18000B526
0x18000b4d8  lea     rcx, SRWLock; SRWLock
0x18000b4df  call    cs:__imp_AcquireSRWLockExclusive
0x18000b4e5  mov     eax, cs:dword_18002D33C
0x18000b4eb  test    ebp, ebp
0x18000b4ed  jz      short loc_18000B512
0x18000b4ef  cmp     ebp, eax
0x18000b4f1  jnz     short loc_18000B512
0x18000b4f3  lea     rdx, [rsp+58h+var_38]; void *
0x18000b4f8  mov     [rsp+58h+var_38], r14
0x18000b4fd  lea     rcx, qword_18002D370; this
0x18000b504  mov     [rsp+58h+var_30], rsi
0x18000b509  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18000b50e  test    al, al
0x18000b510  jnz     short loc_18000B519
0x18000b512  lock and dword ptr [rsi], 0FFFFF7C1h
0x18000b519  lea     rcx, SRWLock; SRWLock
0x18000b520  call    cs:__imp_ReleaseSRWLockExclusive
0x18000b526  mov     ecx, [rbx]
0x18000b528  mov     rbp, [rsp+58h+arg_10]
0x18000b52d  test    cl, 2
0x18000b530  jnz     short loc_18000B55D
0x18000b532  mov     eax, ecx
0x18000b534  xor     eax, edi
0x18000b536  and     eax, 180h
0x18000b53b  xor     eax, ecx
0x18000b53d  mov     ecx, eax
0x18000b53f  xor     ecx, edi
0x18000b541  and     ecx, 40h
0x18000b544  xor     ecx, eax
0x18000b546  mov     edx, ecx
0x18000b548  xor     edx, edi
0x18000b54a  and     edx, 1
0x18000b54d  xor     edx, ecx
0x18000b54f  mov     ecx, edx
0x18000b551  xor     ecx, edi
0x18000b553  and     ecx, 800h
0x18000b559  xor     ecx, edx
0x18000b55b  mov     [rbx], ecx
0x18000b55d  mov     rdi, [rsp+58h+arg_18]
0x18000b562  mov     rax, rbx
0x18000b565  mov     rcx, [rsp+58h+var_20]
0x18000b56a  xor     rcx, rsp; StackCookie
0x18000b56d  call    __security_check_cookie
0x18000b572  add     rsp, 40h
0x18000b576  pop     r14
0x18000b578  pop     rsi
0x18000b579  pop     rbx
0x18000b57a  retn
0x18000b57b  mov     rax, rbx
0x18000b57e  jmp     short loc_18000B565
```
