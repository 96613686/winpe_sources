# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_03_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x180013950`
- end: `0x180013abd`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_03_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `365`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180014f0c`

## callees

- `0x180004a48`
- `0x180008344`
- `0x180013950`
- `0x18002a010`

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
0x180013950  mov     [rsp+arg_8], rbx
0x180013955  mov     [rsp+arg_10], rbp
0x18001395a  mov     [rsp+arg_0], rcx
0x18001395f  push    rsi
0x180013960  push    rdi
0x180013961  push    r15
0x180013963  sub     rsp, 20h
0x180013967  mov     rsi, cs:Feature_Standalone_26_03_NonSec__descriptor
0x18001396e  mov     rbx, rdx
0x180013971  mov     qword ptr [rdx], 0
0x180013978  mov     eax, [rsi]
0x18001397a  mov     [rdx], eax
0x18001397c  and     eax, 6
0x18001397f  cmp     al, 6
0x180013981  jz      loc_180013AA7
0x180013987  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001398c  mov     ebp, eax
0x18001398e  mov     dword ptr [rsp+38h+arg_0], 0
0x180013996  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18001399d  test    rax, rax
0x1800139a0  jz      short loc_1800139BA
0x1800139a2  lea     r8, [rsp+38h+arg_0]
0x1800139a7  mov     edx, 3
0x1800139ac  mov     ecx, 37E2881h
0x1800139b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800139b6  mov     edx, eax
0x1800139b8  jmp     short loc_1800139C8
0x1800139ba  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x1800139c1  test    rax, rax
0x1800139c4  jnz     short loc_1800139A2
0x1800139c6  xor     edx, edx
0x1800139c8  mov     r8d, edx
0x1800139cb  mov     eax, edx
0x1800139cd  and     r8d, 0FFFFFF3Fh
0x1800139d4  and     edx, 80h
0x1800139da  mov     ecx, r8d
0x1800139dd  mov     r15d, 40h ; '@'
0x1800139e3  and     ecx, 3
0x1800139e6  and     eax, r15d
0x1800139e9  shl     ecx, 2
0x1800139ec  or      ecx, eax
0x1800139ee  shl     ecx, 2
0x1800139f1  or      ecx, edx
0x1800139f3  lea     edi, ds:0[rcx*8]
0x1800139fa  test    r8d, r8d
0x1800139fd  jnz     short loc_180013A04
0x1800139ff  mov     eax, r15d
0x180013a02  jmp     short loc_180013A0E
0x180013a04  xor     eax, eax
0x180013a06  cmp     r8d, 2
0x180013a0a  cmovz   eax, r15d
0x180013a0e  or      edi, eax
0x180013a10  mov     eax, [rbx]
0x180013a12  cmp     dword ptr [rsp+38h+arg_0], 0
0x180013a17  mov     edx, eax
0x180013a19  mov     [rbx], eax
0x180013a1b  jz      short loc_180013A47
0x180013a1d  test    dl, 2
0x180013a20  jnz     short loc_180013A47
0x180013a22  xor     eax, edi
0x180013a24  and     eax, 180h
0x180013a29  xor     eax, edx
0x180013a2b  mov     ecx, eax
0x180013a2d  xor     ecx, edi
0x180013a2f  and     ecx, r15d
0x180013a32  xor     ecx, eax
0x180013a34  or      ecx, 1
0x180013a37  mov     eax, ecx
0x180013a39  xor     eax, edi
0x180013a3b  and     eax, 800h
0x180013a40  xor     eax, ecx
0x180013a42  or      eax, 2
0x180013a45  mov     [rbx], eax
0x180013a47  mov     r8d, edx
0x180013a4a  mov     ecx, eax
0x180013a4c  and     r8d, 4
0x180013a50  jnz     short loc_180013A61
0x180013a52  xor     ecx, edi
0x180013a54  and     ecx, 400h
0x180013a5a  xor     ecx, eax
0x180013a5c  or      ecx, 4
0x180013a5f  mov     [rbx], ecx
0x180013a61  mov     eax, edx
0x180013a63  lock cmpxchg [rsi], ecx
0x180013a67  jnz     short loc_180013A12
0x180013a69  test    r8d, r8d
0x180013a6c  jnz     short loc_180013A7E
0x180013a6e  mov     r8d, ebp
0x180013a71  mov     edx, 3
0x180013a76  mov     rcx, rsi
0x180013a79  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180013a7e  test    byte ptr [rbx], 2
0x180013a81  jnz     short loc_180013AA7
0x180013a83  mov     eax, [rbx]
0x180013a85  xor     eax, edi
0x180013a87  and     eax, 180h
0x180013a8c  xor     eax, [rbx]
0x180013a8e  mov     ecx, eax
0x180013a90  xor     ecx, edi
0x180013a92  and     ecx, r15d
0x180013a95  xor     ecx, eax
0x180013a97  or      ecx, 1
0x180013a9a  mov     eax, ecx
0x180013a9c  xor     eax, edi
0x180013a9e  and     eax, 800h
0x180013aa3  xor     eax, ecx
0x180013aa5  mov     [rbx], eax
0x180013aa7  mov     rbp, [rsp+38h+arg_10]
0x180013aac  mov     rax, rbx
0x180013aaf  mov     rbx, [rsp+38h+arg_8]
0x180013ab4  add     rsp, 20h
0x180013ab8  pop     r15
0x180013aba  pop     rdi
0x180013abb  pop     rsi
0x180013abc  retn
```
