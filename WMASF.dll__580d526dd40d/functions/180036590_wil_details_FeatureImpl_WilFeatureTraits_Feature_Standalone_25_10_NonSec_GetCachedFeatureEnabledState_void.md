# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x180036590`
- end: `0x1800366fd`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `365`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180039d8c`

## callees

- `0x1800015d0`
- `0x180036170`
- `0x180036590`
- `0x18003b548`
- `0x18003bc40`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(
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
  FEATURE_CHANGE_TIME v17; // [rsp+20h] [rbp-28h] BYREF

  *a2 = 0;
  v3 = *(_DWORD *)Feature_Standalone_25_10_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_25_10_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v17 = FEATURE_CHANGE_TIME_READ;
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    FeatureEnabledState = wil::details::WilApi_GetFeatureEnabledState(
                            (wil::details *)0x2AF34F8,
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
              (volatile signed __int32 *)Feature_Standalone_25_10_NonSec__descriptor,
              v15,
              v14);
    }
    while ( v14 != v12 );
    if ( (v14 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_Standalone_25_10_NonSec__descriptor,
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
0x180036590  mov     [rsp+arg_0], rbx
0x180036595  mov     [rsp+arg_10], rbp
0x18003659a  push    rsi
0x18003659b  push    rdi
0x18003659c  push    r15
0x18003659e  sub     rsp, 30h
0x1800365a2  mov     rax, cs:__security_cookie
0x1800365a9  xor     rax, rsp
0x1800365ac  mov     [rsp+48h+var_20], rax
0x1800365b1  mov     rsi, cs:Feature_Standalone_25_10_NonSec__descriptor
0x1800365b8  mov     rbx, rdx
0x1800365bb  mov     qword ptr [rdx], 0
0x1800365c2  mov     eax, [rsi]
0x1800365c4  mov     [rdx], eax
0x1800365c6  and     eax, 6
0x1800365c9  cmp     al, 6
0x1800365cb  jz      loc_1800366DA
0x1800365d1  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800365d6  lea     r8, [rsp+48h+var_28]; enum FEATURE_CHANGE_TIME
0x1800365db  mov     [rsp+48h+var_28], 0
0x1800365e3  mov     ecx, 2AF34F8h; this
0x1800365e8  mov     ebp, eax
0x1800365ea  call    ?WilApi_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z; wil::details::WilApi_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)
0x1800365ef  mov     r8d, eax
0x1800365f2  mov     edx, eax
0x1800365f4  and     r8d, 0FFFFFF3Fh
0x1800365fb  and     edx, 80h
0x180036601  mov     ecx, r8d
0x180036604  mov     r15d, 40h ; '@'
0x18003660a  and     ecx, 3
0x18003660d  and     eax, r15d
0x180036610  shl     ecx, 2
0x180036613  or      ecx, eax
0x180036615  shl     ecx, 2
0x180036618  or      ecx, edx
0x18003661a  lea     edi, ds:0[rcx*8]
0x180036621  test    r8d, r8d
0x180036624  jnz     short loc_18003662B
0x180036626  mov     eax, r15d
0x180036629  jmp     short loc_180036635
0x18003662b  xor     eax, eax
0x18003662d  cmp     r8d, 2
0x180036631  cmovz   eax, r15d
0x180036635  or      edi, eax
0x180036637  mov     eax, [rbx]
0x180036639  cmp     [rsp+48h+var_28], 0
0x18003663e  mov     edx, eax
0x180036640  mov     [rbx], eax
0x180036642  jz      short loc_180036672
0x180036644  test    dl, 2
0x180036647  jnz     short loc_180036672
0x180036649  mov     eax, edi
0x18003664b  xor     eax, edx
0x18003664d  and     eax, 180h
0x180036652  xor     eax, edx
0x180036654  mov     ecx, eax
0x180036656  xor     ecx, edi
0x180036658  and     ecx, r15d
0x18003665b  xor     ecx, eax
0x18003665d  or      ecx, 1
0x180036660  mov     eax, ecx
0x180036662  xor     eax, edi
0x180036664  and     eax, 800h
0x180036669  xor     eax, ecx
0x18003666b  or      eax, 2
0x18003666e  mov     [rbx], eax
0x180036670  jmp     short loc_180036674
0x180036672  mov     eax, edx
0x180036674  mov     r8d, edx
0x180036677  and     r8d, 4
0x18003667b  jnz     short loc_180036690
0x18003667d  mov     ecx, edi
0x18003667f  xor     ecx, eax
0x180036681  and     ecx, 400h
0x180036687  xor     ecx, eax
0x180036689  or      ecx, 4
0x18003668c  mov     [rbx], ecx
0x18003668e  jmp     short loc_180036692
0x180036690  mov     ecx, eax
0x180036692  mov     eax, edx
0x180036694  lock cmpxchg [rsi], ecx
0x180036698  jnz     short loc_180036639
0x18003669a  test    r8d, r8d
0x18003669d  jnz     short loc_1800366AF
0x18003669f  mov     r8d, ebp
0x1800366a2  mov     edx, 3
0x1800366a7  mov     rcx, rsi
0x1800366aa  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1800366af  test    byte ptr [rbx], 2
0x1800366b2  jnz     short loc_1800366DA
0x1800366b4  mov     ecx, [rbx]
0x1800366b6  xor     ecx, edi
0x1800366b8  and     ecx, 180h
0x1800366be  xor     ecx, [rbx]
0x1800366c0  mov     edx, ecx
0x1800366c2  xor     edx, edi
0x1800366c4  and     edx, r15d
0x1800366c7  xor     edx, ecx
0x1800366c9  or      edx, 1
0x1800366cc  mov     ecx, edx
0x1800366ce  xor     ecx, edi
0x1800366d0  and     ecx, 800h
0x1800366d6  xor     ecx, edx
0x1800366d8  mov     [rbx], ecx
0x1800366da  mov     rax, rbx
0x1800366dd  mov     rcx, [rsp+48h+var_20]
0x1800366e2  xor     rcx, rsp; StackCookie
0x1800366e5  call    __security_check_cookie
0x1800366ea  mov     rbx, [rsp+48h+arg_0]
0x1800366ef  mov     rbp, [rsp+48h+arg_10]
0x1800366f4  add     rsp, 30h
0x1800366f8  pop     r15
0x1800366fa  pop     rdi
0x1800366fb  pop     rsi
0x1800366fc  retn
```
