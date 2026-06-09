# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x18000e7fc`
- end: `0x18000e969`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_02_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `365`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000f144`

## callees

- `0x1800058e8`
- `0x180009270`
- `0x18000e7fc`
- `0x180018010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // ebp
  __int64 (__fastcall *v5)(__int64, __int64, wil::details **); // rax
  int v6; // edx
  int v7; // eax
  int v8; // edi
  int v9; // eax
  bool v10; // zf
  signed __int32 v11; // edx
  signed __int32 v12; // ecx
  wil::details *v14; // [rsp+40h] [rbp+8h] BYREF

  v14 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_Standalone_26_02_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_26_02_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v14) = 0;
    v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
    if ( g_wil_details_internalGetFeatureEnabledState
      || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
    {
      v6 = v5(58599550, 3, &v14);
    }
    else
    {
      v6 = 0;
    }
    if ( (v6 & 0xFFFFFF3F) != 0 )
    {
      v7 = 0;
      if ( (v6 & 0xFFFFFF3F) == 2 )
        v7 = 64;
    }
    else
    {
      v7 = 64;
    }
    v8 = v7 | (8 * (v6 & 0x80 | (4 * (v6 & 0x40 | (4 * (v6 & 3))))));
    v9 = *(_DWORD *)a2;
    do
    {
      v10 = (_DWORD)v14 == 0;
      v11 = v9;
      *(_DWORD *)a2 = v9;
      if ( !v10 && (v9 & 2) == 0 )
      {
        v9 = (v9
            ^ ((unsigned __int16)v8
             ^ (unsigned __int16)v9)
            & 0x180
            ^ (v8
             ^ v9
             ^ ((unsigned __int16)v8
              ^ (unsigned __int16)v9)
             & 0x180)
            & 0x40
            | 1)
           ^ ((unsigned __int16)v8
            ^ ((unsigned __int16)(v9 ^ (v8 ^ v9) & 0x180 ^ (v8 ^ v9 ^ (v8 ^ v9) & 0x180) & 0x40) | 1))
           & 0x800
           | 2;
        *(_DWORD *)a2 = v9;
      }
      v12 = v9;
      if ( (v11 & 4) == 0 )
      {
        v12 = v9 ^ ((unsigned __int16)v8 ^ (unsigned __int16)v9) & 0x400 | 4;
        *(_DWORD *)a2 = v12;
      }
      v9 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_26_02_NonSec__descriptor, v12, v11);
    }
    while ( v11 != v9 );
    if ( (v11 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_Standalone_26_02_NonSec__descriptor, 3, v4);
    if ( (*(_BYTE *)a2 & 2) == 0 )
      *(_DWORD *)a2 = (*(_DWORD *)a2
                     ^ ((unsigned __int16)v8
                      ^ (unsigned __int16)*(_DWORD *)a2)
                     & 0x180
                     ^ (v8
                      ^ *(_DWORD *)a2
                      ^ ((unsigned __int16)v8
                       ^ (unsigned __int16)*(_DWORD *)a2)
                      & 0x180)
                     & 0x40
                     | 1)
                    ^ ((unsigned __int16)v8
                     ^ (*(_WORD *)a2
                      ^ ((unsigned __int16)v8
                       ^ (unsigned __int16)*(_DWORD *)a2)
                      & 0x180
                      ^ ((unsigned __int16)v8
                       ^ *(_WORD *)a2
                       ^ ((unsigned __int16)v8
                        ^ (unsigned __int16)*(_DWORD *)a2)
                       & 0x180)
                      & 0x40
                      | 1))
                    & 0x800;
  }
  return a2;
}

```

## disassembly

```asm
0x18000e7fc  mov     [rsp+arg_8], rbx
0x18000e801  mov     [rsp+arg_10], rbp
0x18000e806  mov     [rsp+arg_0], rcx
0x18000e80b  push    rsi
0x18000e80c  push    rdi
0x18000e80d  push    r15
0x18000e80f  sub     rsp, 20h
0x18000e813  mov     rsi, cs:Feature_Standalone_26_02_NonSec__descriptor
0x18000e81a  mov     rbx, rdx
0x18000e81d  mov     qword ptr [rdx], 0
0x18000e824  mov     eax, [rsi]
0x18000e826  mov     [rdx], eax
0x18000e828  and     eax, 6
0x18000e82b  cmp     al, 6
0x18000e82d  jz      loc_18000E953
0x18000e833  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000e838  mov     ebp, eax
0x18000e83a  mov     dword ptr [rsp+38h+arg_0], 0
0x18000e842  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000e849  test    rax, rax
0x18000e84c  jz      short loc_18000E866
0x18000e84e  lea     r8, [rsp+38h+arg_0]
0x18000e853  mov     edx, 3
0x18000e858  mov     ecx, 37E287Eh
0x18000e85d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e862  mov     edx, eax
0x18000e864  jmp     short loc_18000E874
0x18000e866  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000e86d  test    rax, rax
0x18000e870  jnz     short loc_18000E84E
0x18000e872  xor     edx, edx
0x18000e874  mov     r8d, edx
0x18000e877  mov     eax, edx
0x18000e879  and     r8d, 0FFFFFF3Fh
0x18000e880  and     edx, 80h
0x18000e886  mov     ecx, r8d
0x18000e889  mov     r15d, 40h ; '@'
0x18000e88f  and     ecx, 3
0x18000e892  and     eax, r15d
0x18000e895  shl     ecx, 2
0x18000e898  or      ecx, eax
0x18000e89a  shl     ecx, 2
0x18000e89d  or      ecx, edx
0x18000e89f  lea     edi, ds:0[rcx*8]
0x18000e8a6  test    r8d, r8d
0x18000e8a9  jnz     short loc_18000E8B0
0x18000e8ab  mov     eax, r15d
0x18000e8ae  jmp     short loc_18000E8BA
0x18000e8b0  xor     eax, eax
0x18000e8b2  cmp     r8d, 2
0x18000e8b6  cmovz   eax, r15d
0x18000e8ba  or      edi, eax
0x18000e8bc  mov     eax, [rbx]
0x18000e8be  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000e8c3  mov     edx, eax
0x18000e8c5  mov     [rbx], eax
0x18000e8c7  jz      short loc_18000E8F3
0x18000e8c9  test    dl, 2
0x18000e8cc  jnz     short loc_18000E8F3
0x18000e8ce  xor     eax, edi
0x18000e8d0  and     eax, 180h
0x18000e8d5  xor     eax, edx
0x18000e8d7  mov     ecx, eax
0x18000e8d9  xor     ecx, edi
0x18000e8db  and     ecx, r15d
0x18000e8de  xor     ecx, eax
0x18000e8e0  or      ecx, 1
0x18000e8e3  mov     eax, ecx
0x18000e8e5  xor     eax, edi
0x18000e8e7  and     eax, 800h
0x18000e8ec  xor     eax, ecx
0x18000e8ee  or      eax, 2
0x18000e8f1  mov     [rbx], eax
0x18000e8f3  mov     r8d, edx
0x18000e8f6  mov     ecx, eax
0x18000e8f8  and     r8d, 4
0x18000e8fc  jnz     short loc_18000E90D
0x18000e8fe  xor     ecx, edi
0x18000e900  and     ecx, 400h
0x18000e906  xor     ecx, eax
0x18000e908  or      ecx, 4
0x18000e90b  mov     [rbx], ecx
0x18000e90d  mov     eax, edx
0x18000e90f  lock cmpxchg [rsi], ecx
0x18000e913  jnz     short loc_18000E8BE
0x18000e915  test    r8d, r8d
0x18000e918  jnz     short loc_18000E92A
0x18000e91a  mov     r8d, ebp
0x18000e91d  mov     edx, 3
0x18000e922  mov     rcx, rsi
0x18000e925  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000e92a  test    byte ptr [rbx], 2
0x18000e92d  jnz     short loc_18000E953
0x18000e92f  mov     eax, [rbx]
0x18000e931  xor     eax, edi
0x18000e933  and     eax, 180h
0x18000e938  xor     eax, [rbx]
0x18000e93a  mov     ecx, eax
0x18000e93c  xor     ecx, edi
0x18000e93e  and     ecx, r15d
0x18000e941  xor     ecx, eax
0x18000e943  or      ecx, 1
0x18000e946  mov     eax, ecx
0x18000e948  xor     eax, edi
0x18000e94a  and     eax, 800h
0x18000e94f  xor     eax, ecx
0x18000e951  mov     [rbx], eax
0x18000e953  mov     rbp, [rsp+38h+arg_10]
0x18000e958  mov     rax, rbx
0x18000e95b  mov     rbx, [rsp+38h+arg_8]
0x18000e960  add     rsp, 20h
0x18000e964  pop     r15
0x18000e966  pop     rdi
0x18000e967  pop     rsi
0x18000e968  retn
```
