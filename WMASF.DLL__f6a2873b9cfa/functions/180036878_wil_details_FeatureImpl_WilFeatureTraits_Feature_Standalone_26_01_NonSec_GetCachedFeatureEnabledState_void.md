# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x180036878`
- end: `0x1800369e5`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `365`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180039ec4`

## callees

- `0x1800015d0`
- `0x180036170`
- `0x180036878`
- `0x18003b548`
- `0x18003bc40`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  int v4; // ebp
  unsigned int v5; // edx
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
  enum FEATURE_CHANGE_TIME v17; // [rsp+20h] [rbp-28h] BYREF

  *a2 = 0;
  v3 = *(_DWORD *)Feature_Standalone_26_01_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_26_01_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v17 = FEATURE_CHANGE_TIME_READ;
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState(
                            (wil::details *)0x37E286C,
                            v5,
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
      v13 = v17 == FEATURE_CHANGE_TIME_READ;
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
              (volatile signed __int32 *)Feature_Standalone_26_01_NonSec__descriptor,
              v15,
              v14);
    }
    while ( v14 != v12 );
    if ( (v14 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_Standalone_26_01_NonSec__descriptor,
        3,
        v4);
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
0x180036878  mov     [rsp+arg_0], rbx
0x18003687d  mov     [rsp+arg_10], rbp
0x180036882  push    rsi
0x180036883  push    rdi
0x180036884  push    r15
0x180036886  sub     rsp, 30h
0x18003688a  mov     rax, cs:__security_cookie
0x180036891  xor     rax, rsp
0x180036894  mov     [rsp+48h+var_20], rax
0x180036899  mov     rsi, cs:Feature_Standalone_26_01_NonSec__descriptor
0x1800368a0  mov     rbx, rdx
0x1800368a3  mov     qword ptr [rdx], 0
0x1800368aa  mov     eax, [rsi]
0x1800368ac  mov     [rdx], eax
0x1800368ae  and     eax, 6
0x1800368b1  cmp     al, 6
0x1800368b3  jz      loc_1800369C2
0x1800368b9  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800368be  lea     r8, [rsp+48h+var_28]; enum FEATURE_CHANGE_TIME
0x1800368c3  mov     [rsp+48h+var_28], 0
0x1800368cb  mov     ecx, 37E286Ch; this
0x1800368d0  mov     ebp, eax
0x1800368d2  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x1800368d7  mov     r8d, eax
0x1800368da  mov     edx, eax
0x1800368dc  and     r8d, 0FFFFFF3Fh
0x1800368e3  and     edx, 80h
0x1800368e9  mov     ecx, r8d
0x1800368ec  mov     r15d, 40h ; '@'
0x1800368f2  and     ecx, 3
0x1800368f5  and     eax, r15d
0x1800368f8  shl     ecx, 2
0x1800368fb  or      ecx, eax
0x1800368fd  shl     ecx, 2
0x180036900  or      ecx, edx
0x180036902  lea     edi, ds:0[rcx*8]
0x180036909  test    r8d, r8d
0x18003690c  jnz     short loc_180036913
0x18003690e  mov     eax, r15d
0x180036911  jmp     short loc_18003691D
0x180036913  xor     eax, eax
0x180036915  cmp     r8d, 2
0x180036919  cmovz   eax, r15d
0x18003691d  or      edi, eax
0x18003691f  mov     eax, [rbx]
0x180036921  cmp     [rsp+48h+var_28], 0
0x180036926  mov     edx, eax
0x180036928  mov     [rbx], eax
0x18003692a  jz      short loc_18003695A
0x18003692c  test    dl, 2
0x18003692f  jnz     short loc_18003695A
0x180036931  mov     eax, edi
0x180036933  xor     eax, edx
0x180036935  and     eax, 180h
0x18003693a  xor     eax, edx
0x18003693c  mov     ecx, eax
0x18003693e  xor     ecx, edi
0x180036940  and     ecx, r15d
0x180036943  xor     ecx, eax
0x180036945  or      ecx, 1
0x180036948  mov     eax, ecx
0x18003694a  xor     eax, edi
0x18003694c  and     eax, 800h
0x180036951  xor     eax, ecx
0x180036953  or      eax, 2
0x180036956  mov     [rbx], eax
0x180036958  jmp     short loc_18003695C
0x18003695a  mov     eax, edx
0x18003695c  mov     r8d, edx
0x18003695f  and     r8d, 4
0x180036963  jnz     short loc_180036978
0x180036965  mov     ecx, edi
0x180036967  xor     ecx, eax
0x180036969  and     ecx, 400h
0x18003696f  xor     ecx, eax
0x180036971  or      ecx, 4
0x180036974  mov     [rbx], ecx
0x180036976  jmp     short loc_18003697A
0x180036978  mov     ecx, eax
0x18003697a  mov     eax, edx
0x18003697c  lock cmpxchg [rsi], ecx
0x180036980  jnz     short loc_180036921
0x180036982  test    r8d, r8d
0x180036985  jnz     short loc_180036997
0x180036987  mov     r8d, ebp
0x18003698a  mov     edx, 3
0x18003698f  mov     rcx, rsi
0x180036992  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180036997  test    byte ptr [rbx], 2
0x18003699a  jnz     short loc_1800369C2
0x18003699c  mov     ecx, [rbx]
0x18003699e  xor     ecx, edi
0x1800369a0  and     ecx, 180h
0x1800369a6  xor     ecx, [rbx]
0x1800369a8  mov     edx, ecx
0x1800369aa  xor     edx, edi
0x1800369ac  and     edx, r15d
0x1800369af  xor     edx, ecx
0x1800369b1  or      edx, 1
0x1800369b4  mov     ecx, edx
0x1800369b6  xor     ecx, edi
0x1800369b8  and     ecx, 800h
0x1800369be  xor     ecx, edx
0x1800369c0  mov     [rbx], ecx
0x1800369c2  mov     rax, rbx
0x1800369c5  mov     rcx, [rsp+48h+var_20]
0x1800369ca  xor     rcx, rsp; StackCookie
0x1800369cd  call    __security_check_cookie
0x1800369d2  mov     rbx, [rsp+48h+arg_0]
0x1800369d7  mov     rbp, [rsp+48h+arg_10]
0x1800369dc  add     rsp, 30h
0x1800369e0  pop     r15
0x1800369e2  pop     rdi
0x1800369e3  pop     rsi
0x1800369e4  retn
```
