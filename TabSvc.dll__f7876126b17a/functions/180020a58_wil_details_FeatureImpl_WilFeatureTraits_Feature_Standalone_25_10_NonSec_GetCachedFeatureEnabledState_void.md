# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x180020a58`
- end: `0x180020bb0`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `344`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800223b4`

## callees

- `0x180019930`
- `0x18001a080`
- `0x18001a6e4`
- `0x180020a58`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // eax
  unsigned int v5; // ebp
  int *v6; // r9
  enum FEATURE_ENABLED_STATE FeatureEnabledState; // eax
  unsigned int v8; // r8d
  int v9; // edi
  int v10; // eax
  int v11; // edi
  int v12; // eax
  bool v13; // zf
  signed __int32 v14; // edx
  signed __int32 v15; // ecx
  wil::details *v17; // [rsp+40h] [rbp+8h] BYREF

  v17 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_Standalone_25_10_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_25_10_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v17) = 0;
    v5 = v4;
    FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState(
                            (wil::details *)0x2AF34F8,
                            3u,
                            (enum FEATURE_CHANGE_TIME)&v17,
                            v6);
    v8 = FeatureEnabledState & 0xFFFFFF3F;
    v9 = 8 * (FeatureEnabledState & 0x80 | (4 * (FeatureEnabledState & 0x40 | (4 * (FeatureEnabledState & 3)))));
    if ( (FeatureEnabledState & 0xFFFFFF3F) != 0 )
    {
      v10 = 0;
      if ( v8 == 2 )
        v10 = 64;
    }
    else
    {
      v10 = 64;
    }
    v11 = v10 | v9;
    v12 = *(_DWORD *)a2;
    do
    {
      v13 = (_DWORD)v17 == 0;
      v14 = v12;
      *(_DWORD *)a2 = v12;
      if ( !v13 && (v12 & 2) == 0 )
      {
        v12 = (v12
             ^ ((unsigned __int16)v12
              ^ (unsigned __int16)v11)
             & 0x180
             ^ (v11
              ^ v12
              ^ ((unsigned __int16)v12
               ^ (unsigned __int16)v11)
              & 0x180)
             & 0x40
             | 1)
            ^ ((unsigned __int16)v11
             ^ ((unsigned __int16)(v12 ^ (v12 ^ v11) & 0x180 ^ (v11 ^ v12 ^ (v12 ^ v11) & 0x180) & 0x40) | 1))
            & 0x800
            | 2;
        *(_DWORD *)a2 = v12;
      }
      if ( (v14 & 4) != 0 )
      {
        v15 = v12;
      }
      else
      {
        v15 = v12 ^ ((unsigned __int16)v12 ^ (unsigned __int16)v11) & 0x400 | 4;
        *(_DWORD *)a2 = v15;
      }
      v12 = _InterlockedCompareExchange(
              (volatile signed __int32 *)Feature_Standalone_25_10_NonSec__descriptor,
              v15,
              v14);
    }
    while ( v14 != v12 );
    if ( (v14 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_Standalone_25_10_NonSec__descriptor, 3, v5);
    if ( (*(_BYTE *)a2 & 2) == 0 )
      *(_DWORD *)a2 = (*(_DWORD *)a2
                     ^ ((unsigned __int16)v11
                      ^ (unsigned __int16)*(_DWORD *)a2)
                     & 0x180
                     ^ (v11
                      ^ *(_DWORD *)a2
                      ^ ((unsigned __int16)v11
                       ^ (unsigned __int16)*(_DWORD *)a2)
                      & 0x180)
                     & 0x40
                     | 1)
                    ^ ((unsigned __int16)v11
                     ^ (*(_WORD *)a2
                      ^ ((unsigned __int16)v11
                       ^ (unsigned __int16)*(_DWORD *)a2)
                      & 0x180
                      ^ ((unsigned __int16)v11
                       ^ *(_WORD *)a2
                       ^ ((unsigned __int16)v11
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
0x180020a58  mov     [rsp+arg_8], rbx
0x180020a5d  mov     [rsp+arg_10], rbp
0x180020a62  mov     [rsp+arg_0], rcx
0x180020a67  push    rsi
0x180020a68  push    rdi
0x180020a69  push    r15
0x180020a6b  sub     rsp, 20h
0x180020a6f  mov     rsi, cs:Feature_Standalone_25_10_NonSec__descriptor
0x180020a76  mov     rbx, rdx
0x180020a79  mov     qword ptr [rdx], 0
0x180020a80  mov     eax, [rsi]
0x180020a82  mov     [rdx], eax
0x180020a84  and     eax, 6
0x180020a87  cmp     al, 6
0x180020a89  jz      loc_180020B9A
0x180020a8f  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180020a94  lea     r8, [rsp+38h+arg_0]; enum FEATURE_CHANGE_TIME
0x180020a99  mov     dword ptr [rsp+38h+arg_0], 0
0x180020aa1  mov     edx, 3; unsigned int
0x180020aa6  mov     ecx, 2AF34F8h; this
0x180020aab  mov     ebp, eax
0x180020aad  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x180020ab2  mov     r8d, eax
0x180020ab5  mov     ecx, eax
0x180020ab7  and     r8d, 0FFFFFF3Fh
0x180020abe  and     eax, 80h
0x180020ac3  mov     edx, r8d
0x180020ac6  mov     r15d, 40h ; '@'
0x180020acc  and     edx, 3
0x180020acf  and     ecx, r15d
0x180020ad2  shl     edx, 2
0x180020ad5  or      edx, ecx
0x180020ad7  shl     edx, 2
0x180020ada  or      edx, eax
0x180020adc  lea     edi, ds:0[rdx*8]
0x180020ae3  test    r8d, r8d
0x180020ae6  jnz     short loc_180020AED
0x180020ae8  mov     eax, r15d
0x180020aeb  jmp     short loc_180020AF7
0x180020aed  xor     eax, eax
0x180020aef  cmp     r8d, 2
0x180020af3  cmovz   eax, r15d
0x180020af7  or      edi, eax
0x180020af9  mov     eax, [rbx]
0x180020afb  cmp     dword ptr [rsp+38h+arg_0], 0
0x180020b00  mov     edx, eax
0x180020b02  mov     [rbx], eax
0x180020b04  jz      short loc_180020B34
0x180020b06  test    dl, 2
0x180020b09  jnz     short loc_180020B34
0x180020b0b  mov     eax, edi
0x180020b0d  xor     eax, edx
0x180020b0f  and     eax, 180h
0x180020b14  xor     eax, edx
0x180020b16  mov     ecx, eax
0x180020b18  xor     ecx, edi
0x180020b1a  and     ecx, r15d
0x180020b1d  xor     ecx, eax
0x180020b1f  or      ecx, 1
0x180020b22  mov     eax, ecx
0x180020b24  xor     eax, edi
0x180020b26  and     eax, 800h
0x180020b2b  xor     eax, ecx
0x180020b2d  or      eax, 2
0x180020b30  mov     [rbx], eax
0x180020b32  jmp     short loc_180020B36
0x180020b34  mov     eax, edx
0x180020b36  mov     r8d, edx
0x180020b39  and     r8d, 4
0x180020b3d  jnz     short loc_180020B52
0x180020b3f  mov     ecx, edi
0x180020b41  xor     ecx, eax
0x180020b43  and     ecx, 400h
0x180020b49  xor     ecx, eax
0x180020b4b  or      ecx, 4
0x180020b4e  mov     [rbx], ecx
0x180020b50  jmp     short loc_180020B54
0x180020b52  mov     ecx, eax
0x180020b54  mov     eax, edx
0x180020b56  lock cmpxchg [rsi], ecx
0x180020b5a  jnz     short loc_180020AFB
0x180020b5c  test    r8d, r8d
0x180020b5f  jnz     short loc_180020B71
0x180020b61  mov     r8d, ebp
0x180020b64  mov     edx, 3
0x180020b69  mov     rcx, rsi
0x180020b6c  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180020b71  test    byte ptr [rbx], 2
0x180020b74  jnz     short loc_180020B9A
0x180020b76  mov     eax, [rbx]
0x180020b78  xor     eax, edi
0x180020b7a  and     eax, 180h
0x180020b7f  xor     eax, [rbx]
0x180020b81  mov     ecx, eax
0x180020b83  xor     ecx, edi
0x180020b85  and     ecx, r15d
0x180020b88  xor     ecx, eax
0x180020b8a  or      ecx, 1
0x180020b8d  mov     eax, ecx
0x180020b8f  xor     eax, edi
0x180020b91  and     eax, 800h
0x180020b96  xor     eax, ecx
0x180020b98  mov     [rbx], eax
0x180020b9a  mov     rbp, [rsp+38h+arg_10]
0x180020b9f  mov     rax, rbx
0x180020ba2  mov     rbx, [rsp+38h+arg_8]
0x180020ba7  add     rsp, 20h
0x180020bab  pop     r15
0x180020bad  pop     rdi
0x180020bae  pop     rsi
0x180020baf  retn
```
