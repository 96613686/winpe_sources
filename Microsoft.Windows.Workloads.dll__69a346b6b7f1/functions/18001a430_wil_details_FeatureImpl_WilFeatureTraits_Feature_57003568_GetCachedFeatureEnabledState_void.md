# wil::details::FeatureImpl<__WilFeatureTraits_Feature_57003568>::GetCachedFeatureEnabledState(void)

- ea: `0x18001a430`
- end: `0x18001a610`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_57003568@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `480`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180019d50`
- `0x18002a390`

## callees

- `0x18000fdc0`
- `0x1800100b0`
- `0x18001a430`
- `0x180034ef0`
- `0x18003bed0`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001a5b0`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001a5b0`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18001a56f`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18001a56f`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_57003568>::GetCachedFeatureEnabledState(
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
    v7 = v6(57003568, 0, &v22);
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
0x18001a430  push    rbx
0x18001a432  push    rsi
0x18001a433  push    r14
0x18001a435  sub     rsp, 40h
0x18001a439  mov     rax, cs:__security_cookie
0x18001a440  xor     rax, rsp
0x18001a443  mov     [rsp+58h+var_20], rax
0x18001a448  xor     r14d, r14d
0x18001a44b  mov     rbx, rdx
0x18001a44e  mov     [rdx], r14
0x18001a451  mov     rsi, rcx
0x18001a454  mov     eax, [rcx]
0x18001a456  mov     [rdx], eax
0x18001a458  and     eax, 6
0x18001a45b  cmp     al, 6
0x18001a45d  jz      loc_18001A60B
0x18001a463  mov     [rsp+58h+arg_10], rbp
0x18001a468  mov     [rsp+58h+arg_18], rdi
0x18001a46d  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001a472  mov     ebp, eax
0x18001a474  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18001a47b  test    rax, rax
0x18001a47e  jnz     short loc_18001A48C
0x18001a480  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18001a487  test    rax, rax
0x18001a48a  jz      short loc_18001A4DE
0x18001a48c  lea     r8, [rsp+58h+var_28]
0x18001a491  xor     edx, edx
0x18001a493  mov     ecx, 365CE30h
0x18001a498  call    cs:__guard_dispatch_icall_fptr
0x18001a49e  mov     r8d, eax
0x18001a4a1  mov     edx, eax
0x18001a4a3  and     r8d, 0FFFFFF3Fh
0x18001a4aa  and     eax, 40h
0x18001a4ad  and     edx, 80h
0x18001a4b3  mov     ecx, r8d
0x18001a4b6  and     ecx, 3
0x18001a4b9  shl     ecx, 2
0x18001a4bc  or      ecx, eax
0x18001a4be  shl     ecx, 2
0x18001a4c1  or      ecx, edx
0x18001a4c3  shl     ecx, 3
0x18001a4c6  test    r8d, r8d
0x18001a4c9  jz      short loc_18001A4E1
0x18001a4cb  cmp     r8d, 2
0x18001a4cf  mov     eax, r14d
0x18001a4d2  mov     edx, 40h ; '@'
0x18001a4d7  cmovz   eax, edx
0x18001a4da  or      eax, ecx
0x18001a4dc  jmp     short loc_18001A4E6
0x18001a4de  mov     ecx, r14d
0x18001a4e1  mov     eax, ecx
0x18001a4e3  or      eax, 40h
0x18001a4e6  mov     edi, eax
0x18001a4e8  shr     edi, 6
0x18001a4eb  and     edi, 1
0x18001a4ee  or      edi, eax
0x18001a4f0  test    ebp, ebp
0x18001a4f2  jnz     short loc_18001A4F9
0x18001a4f4  mov     [rsp+58h+var_28], r14d
0x18001a4f9  mov     eax, [rbx]
0x18001a4fb  mov     edx, eax
0x18001a4fd  mov     [rbx], eax
0x18001a4ff  mov     ecx, eax
0x18001a501  cmp     [rsp+58h+var_28], r14d
0x18001a506  jz      short loc_18001A539
0x18001a508  test    dl, 2
0x18001a50b  jnz     short loc_18001A539
0x18001a50d  xor     eax, edi
0x18001a50f  and     eax, 180h
0x18001a514  xor     eax, ecx
0x18001a516  mov     ecx, eax
0x18001a518  xor     ecx, edi
0x18001a51a  and     ecx, 40h
0x18001a51d  xor     ecx, eax
0x18001a51f  mov     eax, ecx
0x18001a521  xor     eax, edi
0x18001a523  and     eax, 1
0x18001a526  xor     eax, ecx
0x18001a528  mov     ecx, eax
0x18001a52a  xor     ecx, edi
0x18001a52c  and     ecx, 800h
0x18001a532  xor     ecx, eax
0x18001a534  or      ecx, 2
0x18001a537  mov     [rbx], ecx
0x18001a539  mov     r8d, edx
0x18001a53c  and     r8d, 4
0x18001a540  jnz     short loc_18001A552
0x18001a542  mov     eax, edi
0x18001a544  xor     eax, ecx
0x18001a546  and     eax, 400h
0x18001a54b  xor     ecx, eax
0x18001a54d  or      ecx, 4
0x18001a550  mov     [rbx], ecx
0x18001a552  mov     eax, edx
0x18001a554  lock cmpxchg [rsi], ecx
0x18001a558  jnz     short loc_18001A4FB
0x18001a55a  test    r8d, r8d
0x18001a55d  jnz     short loc_18001A5B6
0x18001a55f  cmp     cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A, r14b; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18001a566  jz      short loc_18001A5B6
0x18001a568  lea     rcx, SRWLock; SRWLock
0x18001a56f  call    cs:__imp_AcquireSRWLockExclusive
0x18001a575  mov     eax, cs:dword_1800583FC
0x18001a57b  test    ebp, ebp
0x18001a57d  jz      short loc_18001A5A2
0x18001a57f  cmp     ebp, eax
0x18001a581  jnz     short loc_18001A5A2
0x18001a583  lea     rdx, [rsp+58h+var_38]; void *
0x18001a588  mov     [rsp+58h+var_38], r14
0x18001a58d  lea     rcx, qword_180058430; this
0x18001a594  mov     [rsp+58h+var_30], rsi
0x18001a599  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18001a59e  test    al, al
0x18001a5a0  jnz     short loc_18001A5A9
0x18001a5a2  lock and dword ptr [rsi], 0FFFFF7C1h
0x18001a5a9  lea     rcx, SRWLock; SRWLock
0x18001a5b0  call    cs:__imp_ReleaseSRWLockExclusive
0x18001a5b6  mov     ecx, [rbx]
0x18001a5b8  mov     rbp, [rsp+58h+arg_10]
0x18001a5bd  test    cl, 2
0x18001a5c0  jnz     short loc_18001A5ED
0x18001a5c2  mov     eax, ecx
0x18001a5c4  xor     eax, edi
0x18001a5c6  and     eax, 180h
0x18001a5cb  xor     eax, ecx
0x18001a5cd  mov     ecx, eax
0x18001a5cf  xor     ecx, edi
0x18001a5d1  and     ecx, 40h
0x18001a5d4  xor     ecx, eax
0x18001a5d6  mov     edx, ecx
0x18001a5d8  xor     edx, edi
0x18001a5da  and     edx, 1
0x18001a5dd  xor     edx, ecx
0x18001a5df  mov     ecx, edx
0x18001a5e1  xor     ecx, edi
0x18001a5e3  and     ecx, 800h
0x18001a5e9  xor     ecx, edx
0x18001a5eb  mov     [rbx], ecx
0x18001a5ed  mov     rdi, [rsp+58h+arg_18]
0x18001a5f2  mov     rax, rbx
0x18001a5f5  mov     rcx, [rsp+58h+var_20]
0x18001a5fa  xor     rcx, rsp; StackCookie
0x18001a5fd  call    __security_check_cookie
0x18001a602  add     rsp, 40h
0x18001a606  pop     r14
0x18001a608  pop     rsi
0x18001a609  pop     rbx
0x18001a60a  retn
0x18001a60b  mov     rax, rbx
0x18001a60e  jmp     short loc_18001A5F5
```
