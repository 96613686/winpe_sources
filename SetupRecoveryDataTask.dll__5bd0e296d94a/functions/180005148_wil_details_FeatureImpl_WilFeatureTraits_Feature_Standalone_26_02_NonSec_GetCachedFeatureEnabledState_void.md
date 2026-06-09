# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x180005148`
- end: `0x1800052ce`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_02_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `390`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180005430`

## callees

- `0x1800049e4`
- `0x180005148`
- `0x180009528`
- `0x18000c610`
- `0x18000d010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // ebp
  __int64 (__fastcall *v5)(__int64, __int64, int *); // rax
  int v6; // edx
  int v7; // eax
  int v8; // edi
  int v9; // eax
  bool v10; // zf
  signed __int32 v11; // edx
  signed __int32 v12; // ecx
  int v14; // [rsp+20h] [rbp-28h] BYREF

  *a2 = 0;
  v3 = *(_DWORD *)Feature_Standalone_26_02_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_26_02_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    v14 = 0;
    v5 = (__int64 (__fastcall *)(__int64, __int64, int *))g_wil_details_internalGetFeatureEnabledState;
    if ( g_wil_details_internalGetFeatureEnabledState
      || (v5 = (__int64 (__fastcall *)(__int64, __int64, int *))g_wil_details_apiGetFeatureEnabledState) != 0 )
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
      v10 = v14 == 0;
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
0x180005148  mov     [rsp+arg_0], rbx
0x18000514d  mov     [rsp+arg_10], rbp
0x180005152  push    rsi
0x180005153  push    rdi
0x180005154  push    r15
0x180005156  sub     rsp, 30h
0x18000515a  mov     rax, cs:__security_cookie
0x180005161  xor     rax, rsp
0x180005164  mov     [rsp+48h+var_20], rax
0x180005169  mov     rsi, cs:Feature_Standalone_26_02_NonSec__descriptor
0x180005170  mov     rbx, rdx
0x180005173  mov     qword ptr [rdx], 0
0x18000517a  mov     eax, [rsi]
0x18000517c  mov     [rdx], eax
0x18000517e  and     eax, 6
0x180005181  cmp     al, 6
0x180005183  jz      loc_1800052AB
0x180005189  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000518e  mov     ebp, eax
0x180005190  mov     [rsp+48h+var_28], 0
0x180005198  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x18000519f  test    rax, rax
0x1800051a2  jz      short loc_1800051BC
0x1800051a4  lea     r8, [rsp+48h+var_28]
0x1800051a9  mov     edx, 3
0x1800051ae  mov     ecx, 37E287Eh
0x1800051b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800051b8  mov     edx, eax
0x1800051ba  jmp     short loc_1800051CA
0x1800051bc  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x1800051c3  test    rax, rax
0x1800051c6  jnz     short loc_1800051A4
0x1800051c8  xor     edx, edx
0x1800051ca  mov     r8d, edx
0x1800051cd  mov     eax, edx
0x1800051cf  and     r8d, 0FFFFFF3Fh
0x1800051d6  and     edx, 80h
0x1800051dc  mov     ecx, r8d
0x1800051df  mov     r15d, 40h ; '@'
0x1800051e5  and     ecx, 3
0x1800051e8  and     eax, r15d
0x1800051eb  shl     ecx, 2
0x1800051ee  or      ecx, eax
0x1800051f0  shl     ecx, 2
0x1800051f3  or      ecx, edx
0x1800051f5  lea     edi, ds:0[rcx*8]
0x1800051fc  test    r8d, r8d
0x1800051ff  jnz     short loc_180005206
0x180005201  mov     eax, r15d
0x180005204  jmp     short loc_180005210
0x180005206  xor     eax, eax
0x180005208  cmp     r8d, 2
0x18000520c  cmovz   eax, r15d
0x180005210  or      edi, eax
0x180005212  mov     eax, [rbx]
0x180005214  cmp     [rsp+48h+var_28], 0
0x180005219  mov     edx, eax
0x18000521b  mov     [rbx], eax
0x18000521d  jz      short loc_180005249
0x18000521f  test    dl, 2
0x180005222  jnz     short loc_180005249
0x180005224  xor     eax, edi
0x180005226  and     eax, 180h
0x18000522b  xor     eax, edx
0x18000522d  mov     ecx, eax
0x18000522f  xor     ecx, edi
0x180005231  and     ecx, r15d
0x180005234  xor     ecx, eax
0x180005236  or      ecx, 1
0x180005239  mov     eax, ecx
0x18000523b  xor     eax, edi
0x18000523d  and     eax, 800h
0x180005242  xor     eax, ecx
0x180005244  or      eax, 2
0x180005247  mov     [rbx], eax
0x180005249  mov     r8d, edx
0x18000524c  mov     ecx, eax
0x18000524e  and     r8d, 4
0x180005252  jnz     short loc_180005263
0x180005254  xor     ecx, edi
0x180005256  and     ecx, 400h
0x18000525c  xor     ecx, eax
0x18000525e  or      ecx, 4
0x180005261  mov     [rbx], ecx
0x180005263  mov     eax, edx
0x180005265  lock cmpxchg [rsi], ecx
0x180005269  jnz     short loc_180005214
0x18000526b  test    r8d, r8d
0x18000526e  jnz     short loc_180005280
0x180005270  mov     r8d, ebp
0x180005273  mov     edx, 3
0x180005278  mov     rcx, rsi
0x18000527b  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180005280  test    byte ptr [rbx], 2
0x180005283  jnz     short loc_1800052AB
0x180005285  mov     ecx, [rbx]
0x180005287  xor     ecx, edi
0x180005289  and     ecx, 180h
0x18000528f  xor     ecx, [rbx]
0x180005291  mov     edx, ecx
0x180005293  xor     edx, edi
0x180005295  and     edx, r15d
0x180005298  xor     edx, ecx
0x18000529a  or      edx, 1
0x18000529d  mov     ecx, edx
0x18000529f  xor     ecx, edi
0x1800052a1  and     ecx, 800h
0x1800052a7  xor     ecx, edx
0x1800052a9  mov     [rbx], ecx
0x1800052ab  mov     rax, rbx
0x1800052ae  mov     rcx, [rsp+48h+var_20]
0x1800052b3  xor     rcx, rsp; StackCookie
0x1800052b6  call    __security_check_cookie
0x1800052bb  mov     rbx, [rsp+48h+arg_0]
0x1800052c0  mov     rbp, [rsp+48h+arg_10]
0x1800052c5  add     rsp, 30h
0x1800052c9  pop     r15
0x1800052cb  pop     rdi
0x1800052cc  pop     rsi
0x1800052cd  retn
```
