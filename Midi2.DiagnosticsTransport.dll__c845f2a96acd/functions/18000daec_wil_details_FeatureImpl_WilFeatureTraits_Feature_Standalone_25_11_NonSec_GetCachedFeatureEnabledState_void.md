# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x18000daec`
- end: `0x18000dc59`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `365`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000ea60`

## callees

- `0x18000d6e0`
- `0x18000daec`
- `0x18000ff38`
- `0x180013010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Standalone_25_11_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_25_11_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v14) = 0;
    v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_internalGetFeatureEnabledState;
    if ( g_wil_details_internalGetFeatureEnabledState
      || (v5 = (__int64 (__fastcall *)(__int64, __int64, wil::details **))g_wil_details_apiGetFeatureEnabledState) != 0 )
    {
      v6 = v5(45036797, 3, &v14);
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
      v9 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_25_11_NonSec__descriptor, v12, v11);
    }
    while ( v11 != v9 );
    if ( (v11 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_Standalone_25_11_NonSec__descriptor,
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
0x18000daec  mov     [rsp+arg_8], rbx
0x18000daf1  mov     [rsp+arg_10], rbp
0x18000daf6  mov     [rsp+arg_0], rcx
0x18000dafb  push    rsi
0x18000dafc  push    rdi
0x18000dafd  push    r15
0x18000daff  sub     rsp, 20h
0x18000db03  mov     rsi, cs:Feature_Standalone_25_11_NonSec__descriptor
0x18000db0a  mov     rbx, rdx
0x18000db0d  mov     qword ptr [rdx], 0
0x18000db14  mov     eax, [rsi]
0x18000db16  mov     [rdx], eax
0x18000db18  and     eax, 6
0x18000db1b  cmp     al, 6
0x18000db1d  jz      loc_18000DC43
0x18000db23  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000db28  mov     ebp, eax
0x18000db2a  mov     dword ptr [rsp+38h+arg_0], 0
0x18000db32  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000db39  test    rax, rax
0x18000db3c  jz      short loc_18000DB56
0x18000db3e  lea     r8, [rsp+38h+arg_0]
0x18000db43  mov     edx, 3
0x18000db48  mov     ecx, 2AF34FDh
0x18000db4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db52  mov     edx, eax
0x18000db54  jmp     short loc_18000DB64
0x18000db56  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000db5d  test    rax, rax
0x18000db60  jnz     short loc_18000DB3E
0x18000db62  xor     edx, edx
0x18000db64  mov     r8d, edx
0x18000db67  mov     eax, edx
0x18000db69  and     r8d, 0FFFFFF3Fh
0x18000db70  and     edx, 80h
0x18000db76  mov     ecx, r8d
0x18000db79  mov     r15d, 40h ; '@'
0x18000db7f  and     ecx, 3
0x18000db82  and     eax, r15d
0x18000db85  shl     ecx, 2
0x18000db88  or      ecx, eax
0x18000db8a  shl     ecx, 2
0x18000db8d  or      ecx, edx
0x18000db8f  lea     edi, ds:0[rcx*8]
0x18000db96  test    r8d, r8d
0x18000db99  jnz     short loc_18000DBA0
0x18000db9b  mov     eax, r15d
0x18000db9e  jmp     short loc_18000DBAA
0x18000dba0  xor     eax, eax
0x18000dba2  cmp     r8d, 2
0x18000dba6  cmovz   eax, r15d
0x18000dbaa  or      edi, eax
0x18000dbac  mov     eax, [rbx]
0x18000dbae  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000dbb3  mov     edx, eax
0x18000dbb5  mov     [rbx], eax
0x18000dbb7  jz      short loc_18000DBE3
0x18000dbb9  test    dl, 2
0x18000dbbc  jnz     short loc_18000DBE3
0x18000dbbe  xor     eax, edi
0x18000dbc0  and     eax, 180h
0x18000dbc5  xor     eax, edx
0x18000dbc7  mov     ecx, eax
0x18000dbc9  xor     ecx, edi
0x18000dbcb  and     ecx, r15d
0x18000dbce  xor     ecx, eax
0x18000dbd0  or      ecx, 1
0x18000dbd3  mov     eax, ecx
0x18000dbd5  xor     eax, edi
0x18000dbd7  and     eax, 800h
0x18000dbdc  xor     eax, ecx
0x18000dbde  or      eax, 2
0x18000dbe1  mov     [rbx], eax
0x18000dbe3  mov     r8d, edx
0x18000dbe6  mov     ecx, eax
0x18000dbe8  and     r8d, 4
0x18000dbec  jnz     short loc_18000DBFD
0x18000dbee  xor     ecx, edi
0x18000dbf0  and     ecx, 400h
0x18000dbf6  xor     ecx, eax
0x18000dbf8  or      ecx, 4
0x18000dbfb  mov     [rbx], ecx
0x18000dbfd  mov     eax, edx
0x18000dbff  lock cmpxchg [rsi], ecx
0x18000dc03  jnz     short loc_18000DBAE
0x18000dc05  test    r8d, r8d
0x18000dc08  jnz     short loc_18000DC1A
0x18000dc0a  mov     r8d, ebp
0x18000dc0d  mov     edx, 3
0x18000dc12  mov     rcx, rsi
0x18000dc15  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000dc1a  test    byte ptr [rbx], 2
0x18000dc1d  jnz     short loc_18000DC43
0x18000dc1f  mov     eax, [rbx]
0x18000dc21  xor     eax, edi
0x18000dc23  and     eax, 180h
0x18000dc28  xor     eax, [rbx]
0x18000dc2a  mov     ecx, eax
0x18000dc2c  xor     ecx, edi
0x18000dc2e  and     ecx, r15d
0x18000dc31  xor     ecx, eax
0x18000dc33  or      ecx, 1
0x18000dc36  mov     eax, ecx
0x18000dc38  xor     eax, edi
0x18000dc3a  and     eax, 800h
0x18000dc3f  xor     eax, ecx
0x18000dc41  mov     [rbx], eax
0x18000dc43  mov     rbp, [rsp+38h+arg_10]
0x18000dc48  mov     rax, rbx
0x18000dc4b  mov     rbx, [rsp+38h+arg_8]
0x18000dc50  add     rsp, 20h
0x18000dc54  pop     r15
0x18000dc56  pop     rdi
0x18000dc57  pop     rsi
0x18000dc58  retn
```
