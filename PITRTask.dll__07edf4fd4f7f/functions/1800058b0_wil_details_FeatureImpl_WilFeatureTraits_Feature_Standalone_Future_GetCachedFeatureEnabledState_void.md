# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::GetCachedFeatureEnabledState(void)

- ea: `0x1800058b0`
- end: `0x180005a40`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_Future@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `400`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180005ba0`
- `0x180005d04`
- `0x180005e88`

## callees

- `0x180004f64`
- `0x1800058b0`
- `0x180009800`
- `0x1800107c0`
- `0x180012010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Standalone_Future__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_Future__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    v14 = 0;
    v5 = (__int64 (__fastcall *)(__int64, __int64, int *))g_wil_details_internalGetFeatureEnabledState;
    if ( g_wil_details_internalGetFeatureEnabledState
      || (v5 = (__int64 (__fastcall *)(__int64, __int64, int *))g_wil_details_apiGetFeatureEnabledState) != 0 )
    {
      v6 = v5(49453572, 3, &v14);
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
            ^ ((unsigned __int16)v9
             ^ (unsigned __int16)v8)
            & 0x180
            ^ (v8
             ^ v9
             ^ ((unsigned __int16)v9
              ^ (unsigned __int16)v8)
             & 0x180)
            & 0x40
            | 1)
           ^ ((unsigned __int16)v8
            ^ ((unsigned __int16)(v9 ^ (v9 ^ v8) & 0x180 ^ (v8 ^ v9 ^ (v9 ^ v8) & 0x180) & 0x40) | 1))
           & 0x800
           | 2;
        *(_DWORD *)a2 = v9;
      }
      if ( (v11 & 4) != 0 )
      {
        v12 = v9;
      }
      else
      {
        v12 = v9 ^ ((unsigned __int16)v9 ^ (unsigned __int16)v8) & 0x400 | 4;
        *(_DWORD *)a2 = v12;
      }
      v9 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_Future__descriptor, v12, v11);
    }
    while ( v11 != v9 );
    if ( (v11 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_Standalone_Future__descriptor, 3, v4);
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
0x1800058b0  mov     [rsp+arg_0], rbx
0x1800058b5  mov     [rsp+arg_10], rbp
0x1800058ba  push    rsi
0x1800058bb  push    rdi
0x1800058bc  push    r15
0x1800058be  sub     rsp, 30h
0x1800058c2  mov     rax, cs:__security_cookie
0x1800058c9  xor     rax, rsp
0x1800058cc  mov     [rsp+48h+var_20], rax
0x1800058d1  mov     rsi, cs:Feature_Standalone_Future__descriptor
0x1800058d8  mov     rbx, rdx
0x1800058db  mov     qword ptr [rdx], 0
0x1800058e2  mov     eax, [rsi]
0x1800058e4  mov     [rdx], eax
0x1800058e6  and     eax, 6
0x1800058e9  cmp     al, 6
0x1800058eb  jz      loc_180005A1D
0x1800058f1  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800058f6  mov     ebp, eax
0x1800058f8  mov     [rsp+48h+var_28], 0
0x180005900  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x180005907  test    rax, rax
0x18000590a  jz      short loc_180005924
0x18000590c  lea     r8, [rsp+48h+var_28]
0x180005911  mov     edx, 3
0x180005916  mov     ecx, 2F29A04h
0x18000591b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005920  mov     edx, eax
0x180005922  jmp     short loc_180005932
0x180005924  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000592b  test    rax, rax
0x18000592e  jnz     short loc_18000590C
0x180005930  xor     edx, edx
0x180005932  mov     r8d, edx
0x180005935  mov     eax, edx
0x180005937  and     r8d, 0FFFFFF3Fh
0x18000593e  and     edx, 80h
0x180005944  mov     ecx, r8d
0x180005947  mov     r15d, 40h ; '@'
0x18000594d  and     ecx, 3
0x180005950  and     eax, r15d
0x180005953  shl     ecx, 2
0x180005956  or      ecx, eax
0x180005958  shl     ecx, 2
0x18000595b  or      ecx, edx
0x18000595d  lea     edi, ds:0[rcx*8]
0x180005964  test    r8d, r8d
0x180005967  jnz     short loc_18000596E
0x180005969  mov     eax, r15d
0x18000596c  jmp     short loc_180005978
0x18000596e  xor     eax, eax
0x180005970  cmp     r8d, 2
0x180005974  cmovz   eax, r15d
0x180005978  or      edi, eax
0x18000597a  mov     eax, [rbx]
0x18000597c  cmp     [rsp+48h+var_28], 0
0x180005981  mov     edx, eax
0x180005983  mov     [rbx], eax
0x180005985  jz      short loc_1800059B5
0x180005987  test    dl, 2
0x18000598a  jnz     short loc_1800059B5
0x18000598c  mov     eax, edi
0x18000598e  xor     eax, edx
0x180005990  and     eax, 180h
0x180005995  xor     eax, edx
0x180005997  mov     ecx, eax
0x180005999  xor     ecx, edi
0x18000599b  and     ecx, r15d
0x18000599e  xor     ecx, eax
0x1800059a0  or      ecx, 1
0x1800059a3  mov     eax, ecx
0x1800059a5  xor     eax, edi
0x1800059a7  and     eax, 800h
0x1800059ac  xor     eax, ecx
0x1800059ae  or      eax, 2
0x1800059b1  mov     [rbx], eax
0x1800059b3  jmp     short loc_1800059B7
0x1800059b5  mov     eax, edx
0x1800059b7  mov     r8d, edx
0x1800059ba  and     r8d, 4
0x1800059be  jnz     short loc_1800059D3
0x1800059c0  mov     ecx, edi
0x1800059c2  xor     ecx, eax
0x1800059c4  and     ecx, 400h
0x1800059ca  xor     ecx, eax
0x1800059cc  or      ecx, 4
0x1800059cf  mov     [rbx], ecx
0x1800059d1  jmp     short loc_1800059D5
0x1800059d3  mov     ecx, eax
0x1800059d5  mov     eax, edx
0x1800059d7  lock cmpxchg [rsi], ecx
0x1800059db  jnz     short loc_18000597C
0x1800059dd  test    r8d, r8d
0x1800059e0  jnz     short loc_1800059F2
0x1800059e2  mov     r8d, ebp
0x1800059e5  mov     edx, 3
0x1800059ea  mov     rcx, rsi
0x1800059ed  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1800059f2  test    byte ptr [rbx], 2
0x1800059f5  jnz     short loc_180005A1D
0x1800059f7  mov     ecx, [rbx]
0x1800059f9  xor     ecx, edi
0x1800059fb  and     ecx, 180h
0x180005a01  xor     ecx, [rbx]
0x180005a03  mov     edx, ecx
0x180005a05  xor     edx, edi
0x180005a07  and     edx, r15d
0x180005a0a  xor     edx, ecx
0x180005a0c  or      edx, 1
0x180005a0f  mov     ecx, edx
0x180005a11  xor     ecx, edi
0x180005a13  and     ecx, 800h
0x180005a19  xor     ecx, edx
0x180005a1b  mov     [rbx], ecx
0x180005a1d  mov     rax, rbx
0x180005a20  mov     rcx, [rsp+48h+var_20]
0x180005a25  xor     rcx, rsp; StackCookie
0x180005a28  call    __security_check_cookie
0x180005a2d  mov     rbx, [rsp+48h+arg_0]
0x180005a32  mov     rbp, [rsp+48h+arg_10]
0x180005a37  add     rsp, 30h
0x180005a3b  pop     r15
0x180005a3d  pop     rdi
0x180005a3e  pop     rsi
0x180005a3f  retn
```
