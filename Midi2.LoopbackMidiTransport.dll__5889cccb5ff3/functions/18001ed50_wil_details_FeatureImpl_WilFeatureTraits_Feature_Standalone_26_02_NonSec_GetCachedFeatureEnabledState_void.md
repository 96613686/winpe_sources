# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x18001ed50`
- end: `0x18001eebd`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_02_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `365`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001f86c`

## callees

- `0x18001e65c`
- `0x18001ed50`
- `0x180020fe4`
- `0x180032010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  int v4; // ebp
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
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_Standalone_26_02_NonSec__descriptor,
        3,
        v4);
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
0x18001ed50  mov     [rsp+arg_8], rbx
0x18001ed55  mov     [rsp+arg_10], rbp
0x18001ed5a  mov     [rsp+arg_0], rcx
0x18001ed5f  push    rsi
0x18001ed60  push    rdi
0x18001ed61  push    r15
0x18001ed63  sub     rsp, 20h
0x18001ed67  mov     rsi, cs:Feature_Standalone_26_02_NonSec__descriptor
0x18001ed6e  mov     rbx, rdx
0x18001ed71  mov     qword ptr [rdx], 0
0x18001ed78  mov     eax, [rsi]
0x18001ed7a  mov     [rdx], eax
0x18001ed7c  and     eax, 6
0x18001ed7f  cmp     al, 6
0x18001ed81  jz      loc_18001EEA7
0x18001ed87  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001ed8c  mov     ebp, eax
0x18001ed8e  mov     dword ptr [rsp+38h+arg_0], 0
0x18001ed96  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18001ed9d  test    rax, rax
0x18001eda0  jz      short loc_18001EDBA
0x18001eda2  lea     r8, [rsp+38h+arg_0]
0x18001eda7  mov     edx, 3
0x18001edac  mov     ecx, 37E287Eh
0x18001edb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001edb6  mov     edx, eax
0x18001edb8  jmp     short loc_18001EDC8
0x18001edba  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18001edc1  test    rax, rax
0x18001edc4  jnz     short loc_18001EDA2
0x18001edc6  xor     edx, edx
0x18001edc8  mov     r8d, edx
0x18001edcb  mov     eax, edx
0x18001edcd  and     r8d, 0FFFFFF3Fh
0x18001edd4  and     edx, 80h
0x18001edda  mov     ecx, r8d
0x18001eddd  mov     r15d, 40h ; '@'
0x18001ede3  and     ecx, 3
0x18001ede6  and     eax, r15d
0x18001ede9  shl     ecx, 2
0x18001edec  or      ecx, eax
0x18001edee  shl     ecx, 2
0x18001edf1  or      ecx, edx
0x18001edf3  lea     edi, ds:0[rcx*8]
0x18001edfa  test    r8d, r8d
0x18001edfd  jnz     short loc_18001EE04
0x18001edff  mov     eax, r15d
0x18001ee02  jmp     short loc_18001EE0E
0x18001ee04  xor     eax, eax
0x18001ee06  cmp     r8d, 2
0x18001ee0a  cmovz   eax, r15d
0x18001ee0e  or      edi, eax
0x18001ee10  mov     eax, [rbx]
0x18001ee12  cmp     dword ptr [rsp+38h+arg_0], 0
0x18001ee17  mov     edx, eax
0x18001ee19  mov     [rbx], eax
0x18001ee1b  jz      short loc_18001EE47
0x18001ee1d  test    dl, 2
0x18001ee20  jnz     short loc_18001EE47
0x18001ee22  xor     eax, edi
0x18001ee24  and     eax, 180h
0x18001ee29  xor     eax, edx
0x18001ee2b  mov     ecx, eax
0x18001ee2d  xor     ecx, edi
0x18001ee2f  and     ecx, r15d
0x18001ee32  xor     ecx, eax
0x18001ee34  or      ecx, 1
0x18001ee37  mov     eax, ecx
0x18001ee39  xor     eax, edi
0x18001ee3b  and     eax, 800h
0x18001ee40  xor     eax, ecx
0x18001ee42  or      eax, 2
0x18001ee45  mov     [rbx], eax
0x18001ee47  mov     r8d, edx
0x18001ee4a  mov     ecx, eax
0x18001ee4c  and     r8d, 4
0x18001ee50  jnz     short loc_18001EE61
0x18001ee52  xor     ecx, edi
0x18001ee54  and     ecx, 400h
0x18001ee5a  xor     ecx, eax
0x18001ee5c  or      ecx, 4
0x18001ee5f  mov     [rbx], ecx
0x18001ee61  mov     eax, edx
0x18001ee63  lock cmpxchg [rsi], ecx
0x18001ee67  jnz     short loc_18001EE12
0x18001ee69  test    r8d, r8d
0x18001ee6c  jnz     short loc_18001EE7E
0x18001ee6e  mov     r8d, ebp
0x18001ee71  mov     edx, 3
0x18001ee76  mov     rcx, rsi
0x18001ee79  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001ee7e  test    byte ptr [rbx], 2
0x18001ee81  jnz     short loc_18001EEA7
0x18001ee83  mov     eax, [rbx]
0x18001ee85  xor     eax, edi
0x18001ee87  and     eax, 180h
0x18001ee8c  xor     eax, [rbx]
0x18001ee8e  mov     ecx, eax
0x18001ee90  xor     ecx, edi
0x18001ee92  and     ecx, r15d
0x18001ee95  xor     ecx, eax
0x18001ee97  or      ecx, 1
0x18001ee9a  mov     eax, ecx
0x18001ee9c  xor     eax, edi
0x18001ee9e  and     eax, 800h
0x18001eea3  xor     eax, ecx
0x18001eea5  mov     [rbx], eax
0x18001eea7  mov     rbp, [rsp+38h+arg_10]
0x18001eeac  mov     rax, rbx
0x18001eeaf  mov     rbx, [rsp+38h+arg_8]
0x18001eeb4  add     rsp, 20h
0x18001eeb8  pop     r15
0x18001eeba  pop     rdi
0x18001eebb  pop     rsi
0x18001eebc  retn
```
