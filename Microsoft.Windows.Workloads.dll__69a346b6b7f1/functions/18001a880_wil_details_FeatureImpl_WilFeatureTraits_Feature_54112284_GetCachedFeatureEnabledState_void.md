# wil::details::FeatureImpl<__WilFeatureTraits_Feature_54112284>::GetCachedFeatureEnabledState(void)

- ea: `0x18001a880`
- end: `0x18001aa60`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_54112284@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `480`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001a0e0`

## callees

- `0x18000fdc0`
- `0x1800100b0`
- `0x18001a880`
- `0x180034ef0`
- `0x18003bed0`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001aa00`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001aa00`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18001a9bf`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18001a9bf`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_54112284>::GetCachedFeatureEnabledState(
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
    v7 = v6(54112284, 0, &v22);
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
0x18001a880  push    rbx
0x18001a882  push    rsi
0x18001a883  push    r14
0x18001a885  sub     rsp, 40h
0x18001a889  mov     rax, cs:__security_cookie
0x18001a890  xor     rax, rsp
0x18001a893  mov     [rsp+58h+var_20], rax
0x18001a898  xor     r14d, r14d
0x18001a89b  mov     rbx, rdx
0x18001a89e  mov     [rdx], r14
0x18001a8a1  mov     rsi, rcx
0x18001a8a4  mov     eax, [rcx]
0x18001a8a6  mov     [rdx], eax
0x18001a8a8  and     eax, 6
0x18001a8ab  cmp     al, 6
0x18001a8ad  jz      loc_18001AA5B
0x18001a8b3  mov     [rsp+58h+arg_10], rbp
0x18001a8b8  mov     [rsp+58h+arg_18], rdi
0x18001a8bd  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001a8c2  mov     ebp, eax
0x18001a8c4  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18001a8cb  test    rax, rax
0x18001a8ce  jnz     short loc_18001A8DC
0x18001a8d0  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18001a8d7  test    rax, rax
0x18001a8da  jz      short loc_18001A92E
0x18001a8dc  lea     r8, [rsp+58h+var_28]
0x18001a8e1  xor     edx, edx
0x18001a8e3  mov     ecx, 339B01Ch
0x18001a8e8  call    cs:__guard_dispatch_icall_fptr
0x18001a8ee  mov     r8d, eax
0x18001a8f1  mov     edx, eax
0x18001a8f3  and     r8d, 0FFFFFF3Fh
0x18001a8fa  and     eax, 40h
0x18001a8fd  and     edx, 80h
0x18001a903  mov     ecx, r8d
0x18001a906  and     ecx, 3
0x18001a909  shl     ecx, 2
0x18001a90c  or      ecx, eax
0x18001a90e  shl     ecx, 2
0x18001a911  or      ecx, edx
0x18001a913  shl     ecx, 3
0x18001a916  test    r8d, r8d
0x18001a919  jz      short loc_18001A931
0x18001a91b  cmp     r8d, 2
0x18001a91f  mov     eax, r14d
0x18001a922  mov     edx, 40h ; '@'
0x18001a927  cmovz   eax, edx
0x18001a92a  or      eax, ecx
0x18001a92c  jmp     short loc_18001A936
0x18001a92e  mov     ecx, r14d
0x18001a931  mov     eax, ecx
0x18001a933  or      eax, 40h
0x18001a936  mov     edi, eax
0x18001a938  shr     edi, 6
0x18001a93b  and     edi, 1
0x18001a93e  or      edi, eax
0x18001a940  test    ebp, ebp
0x18001a942  jnz     short loc_18001A949
0x18001a944  mov     [rsp+58h+var_28], r14d
0x18001a949  mov     eax, [rbx]
0x18001a94b  mov     edx, eax
0x18001a94d  mov     [rbx], eax
0x18001a94f  mov     ecx, eax
0x18001a951  cmp     [rsp+58h+var_28], r14d
0x18001a956  jz      short loc_18001A989
0x18001a958  test    dl, 2
0x18001a95b  jnz     short loc_18001A989
0x18001a95d  xor     eax, edi
0x18001a95f  and     eax, 180h
0x18001a964  xor     eax, ecx
0x18001a966  mov     ecx, eax
0x18001a968  xor     ecx, edi
0x18001a96a  and     ecx, 40h
0x18001a96d  xor     ecx, eax
0x18001a96f  mov     eax, ecx
0x18001a971  xor     eax, edi
0x18001a973  and     eax, 1
0x18001a976  xor     eax, ecx
0x18001a978  mov     ecx, eax
0x18001a97a  xor     ecx, edi
0x18001a97c  and     ecx, 800h
0x18001a982  xor     ecx, eax
0x18001a984  or      ecx, 2
0x18001a987  mov     [rbx], ecx
0x18001a989  mov     r8d, edx
0x18001a98c  and     r8d, 4
0x18001a990  jnz     short loc_18001A9A2
0x18001a992  mov     eax, edi
0x18001a994  xor     eax, ecx
0x18001a996  and     eax, 400h
0x18001a99b  xor     ecx, eax
0x18001a99d  or      ecx, 4
0x18001a9a0  mov     [rbx], ecx
0x18001a9a2  mov     eax, edx
0x18001a9a4  lock cmpxchg [rsi], ecx
0x18001a9a8  jnz     short loc_18001A94B
0x18001a9aa  test    r8d, r8d
0x18001a9ad  jnz     short loc_18001AA06
0x18001a9af  cmp     cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A, r14b; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18001a9b6  jz      short loc_18001AA06
0x18001a9b8  lea     rcx, SRWLock; SRWLock
0x18001a9bf  call    cs:__imp_AcquireSRWLockExclusive
0x18001a9c5  mov     eax, cs:dword_1800583FC
0x18001a9cb  test    ebp, ebp
0x18001a9cd  jz      short loc_18001A9F2
0x18001a9cf  cmp     ebp, eax
0x18001a9d1  jnz     short loc_18001A9F2
0x18001a9d3  lea     rdx, [rsp+58h+var_38]; void *
0x18001a9d8  mov     [rsp+58h+var_38], r14
0x18001a9dd  lea     rcx, qword_180058430; this
0x18001a9e4  mov     [rsp+58h+var_30], rsi
0x18001a9e9  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18001a9ee  test    al, al
0x18001a9f0  jnz     short loc_18001A9F9
0x18001a9f2  lock and dword ptr [rsi], 0FFFFF7C1h
0x18001a9f9  lea     rcx, SRWLock; SRWLock
0x18001aa00  call    cs:__imp_ReleaseSRWLockExclusive
0x18001aa06  mov     ecx, [rbx]
0x18001aa08  mov     rbp, [rsp+58h+arg_10]
0x18001aa0d  test    cl, 2
0x18001aa10  jnz     short loc_18001AA3D
0x18001aa12  mov     eax, ecx
0x18001aa14  xor     eax, edi
0x18001aa16  and     eax, 180h
0x18001aa1b  xor     eax, ecx
0x18001aa1d  mov     ecx, eax
0x18001aa1f  xor     ecx, edi
0x18001aa21  and     ecx, 40h
0x18001aa24  xor     ecx, eax
0x18001aa26  mov     edx, ecx
0x18001aa28  xor     edx, edi
0x18001aa2a  and     edx, 1
0x18001aa2d  xor     edx, ecx
0x18001aa2f  mov     ecx, edx
0x18001aa31  xor     ecx, edi
0x18001aa33  and     ecx, 800h
0x18001aa39  xor     ecx, edx
0x18001aa3b  mov     [rbx], ecx
0x18001aa3d  mov     rdi, [rsp+58h+arg_18]
0x18001aa42  mov     rax, rbx
0x18001aa45  mov     rcx, [rsp+58h+var_20]
0x18001aa4a  xor     rcx, rsp; StackCookie
0x18001aa4d  call    __security_check_cookie
0x18001aa52  add     rsp, 40h
0x18001aa56  pop     r14
0x18001aa58  pop     rsi
0x18001aa59  pop     rbx
0x18001aa5a  retn
0x18001aa5b  mov     rax, rbx
0x18001aa5e  jmp     short loc_18001AA45
```
