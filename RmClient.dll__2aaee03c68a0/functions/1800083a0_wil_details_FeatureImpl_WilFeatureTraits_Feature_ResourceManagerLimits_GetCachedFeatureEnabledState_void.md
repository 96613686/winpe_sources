# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ResourceManagerLimits>::GetCachedFeatureEnabledState(void)

- ea: `0x1800083a0`
- end: `0x1800085ce`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ResourceManagerLimits@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `558`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800081e8`

## callees

- `0x1800083a0`
- `0x180008ce8`
- `0x180008da0`
- `0x18001c010`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ResourceManagerLimits>::GetCachedFeatureEnabledState(
        __int64 a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // ebp
  __int64 (__fastcall *v5)(__int64, _QWORD, __int64 *); // rax
  int v6; // eax
  __int16 v7; // si
  __int16 v8; // cx
  __int16 v9; // si
  int v10; // eax
  char v11; // cl
  __int16 v12; // ax
  unsigned __int16 v13; // si
  signed __int32 v14; // eax
  signed __int32 v15; // edx
  int v16; // r9d
  int v17; // r8d
  signed __int32 v18; // ecx
  int v20; // ecx
  __int64 v21; // [rsp+40h] [rbp+8h] BYREF

  v21 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_ResourceManagerLimits__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_ResourceManagerLimits__descriptor;
  if ( (v3 & 6) == 6 )
    return a2;
  v4 = dword_18002EDCC;
  if ( !dword_18002EDCC )
    v4 = wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl((RTL_SRWLOCK *)wil::details::g_enabledStateManager);
  v5 = (__int64 (__fastcall *)(__int64, _QWORD, __int64 *))g_wil_details_internalGetFeatureEnabledState;
  LODWORD(v21) = 0;
  if ( !g_wil_details_internalGetFeatureEnabledState )
  {
    v5 = (__int64 (__fastcall *)(__int64, _QWORD, __int64 *))g_wil_details_apiGetFeatureEnabledState;
    if ( !g_wil_details_apiGetFeatureEnabledState )
    {
      v7 = 0;
      goto LABEL_6;
    }
  }
  v6 = v5(31261443, 0, &v21);
  v7 = 8 * (v6 & 0x80 | (4 * (v6 & 0x40 | (4 * (v6 & 3)))));
  if ( (v6 & 0xFFFFFF3F) == 0 )
  {
LABEL_6:
    v8 = 64;
    goto LABEL_7;
  }
  v8 = 0;
  if ( (v6 & 0xFFFFFF3F) == 2 )
    v8 = 64;
LABEL_7:
  v9 = v8 | v7;
  if ( (v9 & 0xC00) == 0xC00 )
  {
    v11 = 1;
    v10 = v9 & 0x40;
  }
  else
  {
    v10 = v9 & 0x40;
    if ( (v9 & 0x40) != 0 )
    {
LABEL_36:
      v12 = 1;
      goto LABEL_12;
    }
    v11 = 0;
  }
  if ( v10 && v11 )
    goto LABEL_36;
  v12 = 0;
LABEL_12:
  v13 = v12 | v9;
  if ( !v4 )
    LODWORD(v21) = 0;
  v14 = *(_DWORD *)a2;
  do
  {
    v15 = v14;
    *(_DWORD *)a2 = v14;
    if ( !(_DWORD)v21 || (v14 & 2) != 0 )
    {
      v16 = v14;
    }
    else
    {
      v16 = v14
          ^ ((unsigned __int16)v14
           ^ v13)
          & 0x180
          ^ ((unsigned __int8)v13
           ^ (unsigned __int8)(v14 ^ (v14 ^ v13) & 0x80))
          & 0x40
          ^ ((unsigned __int8)v13
           ^ (unsigned __int8)(v14 ^ (v14 ^ v13) & 0x80 ^ (v13 ^ v14 ^ (v14 ^ v13) & 0x80) & 0x40))
          & 1
          ^ (v13
           ^ (unsigned __int16)(v14
                              ^ (v14
                               ^ v13)
                              & 0x180
                              ^ ((unsigned __int8)v13
                               ^ (unsigned __int8)(v14 ^ (v14 ^ v13) & 0x80))
                              & 0x40
                              ^ ((unsigned __int8)v13
                               ^ (unsigned __int8)(v14 ^ (v14 ^ v13) & 0x80 ^ (v13 ^ v14 ^ (v14 ^ v13) & 0x80) & 0x40))
                              & 1))
          & 0x800
          | 2;
      *(_DWORD *)a2 = v16;
    }
    v17 = v14 & 4;
    if ( (v14 & 4) != 0 )
    {
      v18 = v16;
    }
    else
    {
      v18 = v16 ^ ((unsigned __int16)v16 ^ v13) & 0x400 | 4;
      *(_DWORD *)a2 = v18;
    }
    v14 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_ResourceManagerLimits__descriptor, v18, v14);
  }
  while ( v15 != v14 );
  if ( !v17 )
    wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(
      wil::details::g_enabledStateManager,
      Feature_ResourceManagerLimits__descriptor,
      0,
      v4);
  if ( (*(_DWORD *)a2 & 2) == 0 )
  {
    v20 = *(_DWORD *)a2
        ^ (v13
         ^ (unsigned __int16)*(_DWORD *)a2)
        & 0x180
        ^ ((unsigned __int8)v13
         ^ (unsigned __int8)(*(_DWORD *)a2 ^ (v13 ^ *(_DWORD *)a2) & 0x80))
        & 0x40;
    *(_DWORD *)a2 = v20
                  ^ ((unsigned __int8)v13
                   ^ (unsigned __int8)v20)
                  & 1
                  ^ (v13
                   ^ (unsigned __int16)(v20 ^ ((unsigned __int8)v13 ^ (unsigned __int8)v20) & 1))
                  & 0x800;
  }
  return a2;
}

```

## disassembly

```asm
0x1800083a0  mov     [rsp+arg_0], rcx
0x1800083a5  push    rbx
0x1800083a6  push    rdi
0x1800083a7  push    r14
0x1800083a9  sub     rsp, 20h
0x1800083ad  mov     rdi, cs:Feature_ResourceManagerLimits__descriptor
0x1800083b4  xor     r14d, r14d
0x1800083b7  mov     [rdx], r14
0x1800083ba  mov     rbx, rdx
0x1800083bd  mov     eax, [rdi]
0x1800083bf  mov     [rdx], eax
0x1800083c1  and     eax, 6
0x1800083c4  cmp     al, 6
0x1800083c6  jz      loc_1800084DA
0x1800083cc  mov     [rsp+38h+arg_8], rbp
0x1800083d1  mov     ebp, cs:dword_18002EDCC
0x1800083d7  nop
0x1800083d8  mov     [rsp+38h+arg_10], rsi
0x1800083dd  test    ebp, ebp
0x1800083df  jz      loc_1800084FD
0x1800083e5  mov     rax, cs:g_wil_details_internalGetFeatureEnabledState
0x1800083ec  mov     dword ptr [rsp+38h+arg_0], r14d
0x1800083f1  test    rax, rax
0x1800083f4  jz      loc_180008557
0x1800083fa  lea     r8, [rsp+38h+arg_0]
0x1800083ff  xor     edx, edx
0x180008401  mov     ecx, 1DD0303h
0x180008406  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000840b  mov     r8d, eax
0x18000840e  mov     edx, eax
0x180008410  and     r8d, 0FFFFFF3Fh
0x180008417  and     eax, 40h
0x18000841a  and     edx, 80h
0x180008420  mov     ecx, r8d
0x180008423  and     ecx, 3
0x180008426  shl     ecx, 2
0x180008429  or      ecx, eax
0x18000842b  shl     ecx, 2
0x18000842e  or      ecx, edx
0x180008430  lea     esi, ds:0[rcx*8]
0x180008437  test    r8d, r8d
0x18000843a  jnz     loc_18000856F
0x180008440  mov     ecx, 40h ; '@'
0x180008445  or      esi, ecx
0x180008447  mov     eax, esi
0x180008449  and     eax, 0C00h
0x18000844e  cmp     eax, 0C00h
0x180008453  mov     eax, esi
0x180008455  jz      loc_180008583
0x18000845b  and     eax, 40h
0x18000845e  jnz     loc_180008595
0x180008464  xor     cl, cl
0x180008466  test    eax, eax
0x180008468  jnz     loc_18000858D
0x18000846e  mov     eax, r14d
0x180008471  or      esi, eax
0x180008473  test    ebp, ebp
0x180008475  jnz     short loc_18000847C
0x180008477  mov     dword ptr [rsp+38h+arg_0], r14d
0x18000847c  mov     eax, [rbx]
0x18000847e  mov     edx, eax
0x180008480  mov     [rbx], eax
0x180008482  cmp     dword ptr [rsp+38h+arg_0], r14d
0x180008487  jnz     loc_180008515
0x18000848d  mov     r9d, edx
0x180008490  mov     r8d, edx
0x180008493  and     r8d, 4
0x180008497  jnz     short loc_180008510
0x180008499  mov     ecx, esi
0x18000849b  xor     ecx, r9d
0x18000849e  and     ecx, 400h
0x1800084a4  xor     ecx, r9d
0x1800084a7  or      ecx, 4
0x1800084aa  mov     [rbx], ecx
0x1800084ac  mov     eax, edx
0x1800084ae  lock cmpxchg [rdi], ecx
0x1800084b2  jnz     short loc_18000847E
0x1800084b4  test    r8d, r8d
0x1800084b7  jz      short loc_1800084E6
0x1800084b9  mov     ecx, [rbx]
0x1800084bb  mov     rbp, [rsp+38h+arg_8]
0x1800084c0  test    cl, 2
0x1800084c3  jz      loc_18000859F
0x1800084c9  mov     rsi, [rsp+38h+arg_10]
0x1800084ce  mov     rax, rbx
0x1800084d1  add     rsp, 20h
0x1800084d5  pop     r14
0x1800084d7  pop     rdi
0x1800084d8  pop     rbx
0x1800084d9  retn
0x1800084da  mov     rax, rbx
0x1800084dd  add     rsp, 20h
0x1800084e1  pop     r14
0x1800084e3  pop     rdi
0x1800084e4  pop     rbx
0x1800084e5  retn
0x1800084e6  mov     r9d, ebp
0x1800084e9  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800084f0  xor     r8d, r8d
0x1800084f3  mov     rdx, rdi
0x1800084f6  call    ?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1800084fb  jmp     short loc_1800084B9
0x1800084fd  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x180008504  call    ?EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ; wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)
0x180008509  mov     ebp, eax
0x18000850b  jmp     loc_1800083E5
0x180008510  mov     ecx, r9d
0x180008513  jmp     short loc_1800084AC
0x180008515  test    dl, 2
0x180008518  jnz     loc_18000848D
0x18000851e  mov     eax, esi
0x180008520  xor     eax, edx
0x180008522  and     eax, 180h
0x180008527  xor     eax, edx
0x180008529  mov     ecx, eax
0x18000852b  xor     ecx, esi
0x18000852d  and     ecx, 40h
0x180008530  xor     ecx, eax
0x180008532  mov     eax, ecx
0x180008534  xor     eax, esi
0x180008536  and     eax, 1
0x180008539  xor     eax, ecx
0x18000853b  mov     r9d, eax
0x18000853e  xor     r9d, esi
0x180008541  and     r9d, 800h
0x180008548  xor     r9d, eax
0x18000854b  or      r9d, 2
0x18000854f  mov     [rbx], r9d
0x180008552  jmp     loc_180008490
0x180008557  mov     rax, cs:g_wil_details_apiGetFeatureEnabledState
0x18000855e  test    rax, rax
0x180008561  jnz     loc_1800083FA
0x180008567  mov     esi, r14d
0x18000856a  jmp     loc_180008440
0x18000856f  cmp     r8d, 2
0x180008573  mov     ecx, r14d
0x180008576  mov     eax, 40h ; '@'
0x18000857b  cmovz   ecx, eax
0x18000857e  jmp     loc_180008445
0x180008583  mov     cl, 1
0x180008585  and     eax, 40h
0x180008588  jmp     loc_180008466
0x18000858d  test    cl, cl
0x18000858f  jz      loc_18000846E
0x180008595  mov     eax, 1
0x18000859a  jmp     loc_180008471
0x18000859f  mov     eax, ecx
0x1800085a1  xor     eax, esi
0x1800085a3  and     eax, 180h
0x1800085a8  xor     eax, ecx
0x1800085aa  mov     ecx, eax
0x1800085ac  xor     ecx, esi
0x1800085ae  and     ecx, 40h
0x1800085b1  xor     ecx, eax
0x1800085b3  mov     edx, ecx
0x1800085b5  xor     edx, esi
0x1800085b7  and     edx, 1
0x1800085ba  xor     edx, ecx
0x1800085bc  mov     eax, edx
0x1800085be  xor     eax, esi
0x1800085c0  and     eax, 800h
0x1800085c5  xor     eax, edx
0x1800085c7  mov     [rbx], eax
0x1800085c9  jmp     loc_1800084C9
```
