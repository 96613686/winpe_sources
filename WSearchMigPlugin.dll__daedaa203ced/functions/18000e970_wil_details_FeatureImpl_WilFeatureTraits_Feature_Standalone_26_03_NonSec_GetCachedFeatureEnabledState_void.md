# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_03_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x18000e970`
- end: `0x18000eadd`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_03_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `365`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000f594`

## callees

- `0x1800058e8`
- `0x180009270`
- `0x18000e970`
- `0x180018010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_03_NonSec>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Standalone_26_03_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_26_03_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v14) = 0;
    v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
    if ( g_wil_details_internalGetFeatureEnabledState
      || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
    {
      v6 = v5(58599553, 3, &v14);
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
      v9 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_26_03_NonSec__descriptor, v12, v11);
    }
    while ( v11 != v9 );
    if ( (v11 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_Standalone_26_03_NonSec__descriptor, 3, v4);
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
0x18000e970  mov     [rsp+arg_8], rbx
0x18000e975  mov     [rsp+arg_10], rbp
0x18000e97a  mov     [rsp+arg_0], rcx
0x18000e97f  push    rsi
0x18000e980  push    rdi
0x18000e981  push    r15
0x18000e983  sub     rsp, 20h
0x18000e987  mov     rsi, cs:Feature_Standalone_26_03_NonSec__descriptor
0x18000e98e  mov     rbx, rdx
0x18000e991  mov     qword ptr [rdx], 0
0x18000e998  mov     eax, [rsi]
0x18000e99a  mov     [rdx], eax
0x18000e99c  and     eax, 6
0x18000e99f  cmp     al, 6
0x18000e9a1  jz      loc_18000EAC7
0x18000e9a7  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000e9ac  mov     ebp, eax
0x18000e9ae  mov     dword ptr [rsp+38h+arg_0], 0
0x18000e9b6  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000e9bd  test    rax, rax
0x18000e9c0  jz      short loc_18000E9DA
0x18000e9c2  lea     r8, [rsp+38h+arg_0]
0x18000e9c7  mov     edx, 3
0x18000e9cc  mov     ecx, 37E2881h
0x18000e9d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e9d6  mov     edx, eax
0x18000e9d8  jmp     short loc_18000E9E8
0x18000e9da  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000e9e1  test    rax, rax
0x18000e9e4  jnz     short loc_18000E9C2
0x18000e9e6  xor     edx, edx
0x18000e9e8  mov     r8d, edx
0x18000e9eb  mov     eax, edx
0x18000e9ed  and     r8d, 0FFFFFF3Fh
0x18000e9f4  and     edx, 80h
0x18000e9fa  mov     ecx, r8d
0x18000e9fd  mov     r15d, 40h ; '@'
0x18000ea03  and     ecx, 3
0x18000ea06  and     eax, r15d
0x18000ea09  shl     ecx, 2
0x18000ea0c  or      ecx, eax
0x18000ea0e  shl     ecx, 2
0x18000ea11  or      ecx, edx
0x18000ea13  lea     edi, ds:0[rcx*8]
0x18000ea1a  test    r8d, r8d
0x18000ea1d  jnz     short loc_18000EA24
0x18000ea1f  mov     eax, r15d
0x18000ea22  jmp     short loc_18000EA2E
0x18000ea24  xor     eax, eax
0x18000ea26  cmp     r8d, 2
0x18000ea2a  cmovz   eax, r15d
0x18000ea2e  or      edi, eax
0x18000ea30  mov     eax, [rbx]
0x18000ea32  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000ea37  mov     edx, eax
0x18000ea39  mov     [rbx], eax
0x18000ea3b  jz      short loc_18000EA67
0x18000ea3d  test    dl, 2
0x18000ea40  jnz     short loc_18000EA67
0x18000ea42  xor     eax, edi
0x18000ea44  and     eax, 180h
0x18000ea49  xor     eax, edx
0x18000ea4b  mov     ecx, eax
0x18000ea4d  xor     ecx, edi
0x18000ea4f  and     ecx, r15d
0x18000ea52  xor     ecx, eax
0x18000ea54  or      ecx, 1
0x18000ea57  mov     eax, ecx
0x18000ea59  xor     eax, edi
0x18000ea5b  and     eax, 800h
0x18000ea60  xor     eax, ecx
0x18000ea62  or      eax, 2
0x18000ea65  mov     [rbx], eax
0x18000ea67  mov     r8d, edx
0x18000ea6a  mov     ecx, eax
0x18000ea6c  and     r8d, 4
0x18000ea70  jnz     short loc_18000EA81
0x18000ea72  xor     ecx, edi
0x18000ea74  and     ecx, 400h
0x18000ea7a  xor     ecx, eax
0x18000ea7c  or      ecx, 4
0x18000ea7f  mov     [rbx], ecx
0x18000ea81  mov     eax, edx
0x18000ea83  lock cmpxchg [rsi], ecx
0x18000ea87  jnz     short loc_18000EA32
0x18000ea89  test    r8d, r8d
0x18000ea8c  jnz     short loc_18000EA9E
0x18000ea8e  mov     r8d, ebp
0x18000ea91  mov     edx, 3
0x18000ea96  mov     rcx, rsi
0x18000ea99  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000ea9e  test    byte ptr [rbx], 2
0x18000eaa1  jnz     short loc_18000EAC7
0x18000eaa3  mov     eax, [rbx]
0x18000eaa5  xor     eax, edi
0x18000eaa7  and     eax, 180h
0x18000eaac  xor     eax, [rbx]
0x18000eaae  mov     ecx, eax
0x18000eab0  xor     ecx, edi
0x18000eab2  and     ecx, r15d
0x18000eab5  xor     ecx, eax
0x18000eab7  or      ecx, 1
0x18000eaba  mov     eax, ecx
0x18000eabc  xor     eax, edi
0x18000eabe  and     eax, 800h
0x18000eac3  xor     eax, ecx
0x18000eac5  mov     [rbx], eax
0x18000eac7  mov     rbp, [rsp+38h+arg_10]
0x18000eacc  mov     rax, rbx
0x18000eacf  mov     rbx, [rsp+38h+arg_8]
0x18000ead4  add     rsp, 20h
0x18000ead8  pop     r15
0x18000eada  pop     rdi
0x18000eadb  pop     rsi
0x18000eadc  retn
```
