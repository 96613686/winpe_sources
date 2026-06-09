# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ResourceManagerLimits>::GetCachedVariantState(void)

- ea: `0x180008e80`
- end: `0x18000900d`
- name: `?GetCachedVariantState@?$FeatureImpl@U__WilFeatureTraits_Feature_ResourceManagerLimits@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `397`
- prototype: `__int64 *__fastcall(wil::details *, signed __int64 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180007ce8`

## callees

- `0x180008ce8`
- `0x180008d78`
- `0x180008e80`
- `0x18001c010`

## pseudocode

```c
__int64 *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ResourceManagerLimits>::GetCachedVariantState(
        wil::details *a1,
        signed __int64 *a2)
{
  __int64 v3; // rax
  unsigned int v4; // esi
  __int64 (__fastcall *v5)(__int64, _QWORD, int *, int *, wil::details **); // rax
  int v6; // edx
  __int64 v8; // r9
  signed __int64 v9; // rax
  signed __int64 v10; // r10
  int v11; // eax
  bool v12; // zf
  int v13; // r8d
  int v14; // r11d
  int v15; // eax
  wil::details *v16; // [rsp+50h] [rbp+20h] BYREF
  int v17; // [rsp+58h] [rbp+28h] BYREF
  int v18; // [rsp+60h] [rbp+30h] BYREF

  v16 = a1;
  v3 = *Feature_ResourceManagerLimits__descriptor;
  *a2 = *Feature_ResourceManagerLimits__descriptor;
  if ( (v3 & 0xC) != 0xC )
  {
    LODWORD(v16) = 0;
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    v17 = 0;
    v5 = (__int64 (__fastcall *)(__int64, _QWORD, int *, int *, wil::details **))g_wil_details_internalGetFeatureVariant;
    v6 = 0;
    v18 = 0;
    if ( g_wil_details_internalGetFeatureVariant
      || (v5 = (__int64 (__fastcall *)(__int64, _QWORD, int *, int *, wil::details **))g_wil_details_apiGetFeatureVariant) != 0 )
    {
      v6 = v5(31261443, 0, &v18, &v17, &v16);
    }
    v13 = (v17 != 0 ? 0x400 : 0) | (16 * (v6 & 0x80));
    if ( (v6 & 0xFFFFFE7F) != 0 && (v13 ^= (v6 & 0x3F) << 12, (v6 & 0x100) != 0) )
      v14 = v18;
    else
      v14 = 0;
    if ( !v4 )
      LODWORD(v16) = 0;
    v8 = *a2;
    v9 = *a2;
    v10 = *a2;
    while ( 1 )
    {
      *(_DWORD *)a2 = v8;
      *((_DWORD *)a2 + 1) = HIDWORD(v9);
      if ( (v8 & 8) != 0 )
      {
        v11 = v8;
      }
      else
      {
        v15 = (int)v16;
        *((_DWORD *)a2 + 1) = v14;
        v11 = ((v15 != 0 ? 8 : 0) | (v8 ^ (v13 ^ v8) & 0x3F000) & 0xFFFFFFF7)
            ^ ((unsigned __int16)v13
             ^ ((v15 != 0 ? 8 : 0)
              | ((unsigned __int16)v8 ^ ((unsigned __int16)v13 ^ (unsigned __int16)v8) & 0xF000) & 0xFFF7))
            & 0x800;
        *(_DWORD *)a2 = v11;
      }
      if ( (v8 & 4) == 0 )
        *(_DWORD *)a2 = v11 ^ ((unsigned __int16)v11 ^ (unsigned __int16)v13) & 0x400 | 4;
      v9 = _InterlockedCompareExchange64(Feature_ResourceManagerLimits__descriptor, *a2, v10);
      v12 = v10 == v9;
      v10 = v9;
      if ( v12 )
        break;
      LODWORD(v8) = v9;
    }
    if ( (v8 & 4) == 0 )
      wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(
        wil::details::g_enabledStateManager,
        Feature_ResourceManagerLimits__descriptor,
        0,
        v4);
  }
  return a2;
}

```

## disassembly

```asm
0x180008e80  mov     [rsp-18h+arg_18], rbx
0x180008e85  mov     [rsp-18h+arg_0], rcx
0x180008e8a  push    rbp
0x180008e8b  push    rsi
0x180008e8c  push    rdi
0x180008e8d  mov     rbp, rsp
0x180008e90  sub     rsp, 30h
0x180008e94  mov     rdi, cs:Feature_ResourceManagerLimits__descriptor
0x180008e9b  mov     rbx, rdx
0x180008e9e  mov     rax, [rdi]
0x180008ea1  mov     [rdx], rax
0x180008ea4  and     eax, 0Ch
0x180008ea7  cmp     al, 0Ch
0x180008ea9  jz      short loc_180008EFE
0x180008eab  mov     dword ptr [rbp+arg_0], 0
0x180008eb2  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180008eb7  mov     esi, eax
0x180008eb9  mov     [rbp+arg_8], 0
0x180008ec0  mov     rax, cs:g_wil_details_internalGetFeatureVariant
0x180008ec7  xor     edx, edx
0x180008ec9  mov     [rbp+arg_10], 0
0x180008ed0  test    rax, rax
0x180008ed3  jz      short loc_180008F50
0x180008ed5  lea     rcx, [rbp+arg_0]
0x180008ed9  mov     [rsp+30h+var_10], rcx
0x180008ede  lea     r9, [rbp+arg_8]
0x180008ee2  mov     ecx, 1DD0303h
0x180008ee7  lea     r8, [rbp+arg_10]
0x180008eeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ef0  mov     edx, eax
0x180008ef2  jmp     short loc_180008F60
0x180008ef4  test    r9b, 4
0x180008ef8  jz      loc_180008FF3
0x180008efe  mov     rax, rbx
0x180008f01  mov     rbx, [rsp+30h+arg_18]
0x180008f06  add     rsp, 30h
0x180008f0a  pop     rdi
0x180008f0b  pop     rsi
0x180008f0c  pop     rbp
0x180008f0d  retn
0x180008f0e  test    esi, esi
0x180008f10  jnz     short loc_180008F15
0x180008f12  mov     dword ptr [rbp+arg_0], esi
0x180008f15  mov     r9, [rbx]
0x180008f18  mov     rax, r9
0x180008f1b  mov     r10, r9
0x180008f1e  shr     rax, 20h
0x180008f22  mov     [rbx], r9d
0x180008f25  mov     [rbx+4], eax
0x180008f28  test    r9b, 8
0x180008f2c  jz      short loc_180008FA7
0x180008f2e  mov     eax, r9d
0x180008f31  test    r9b, 4
0x180008f35  jz      loc_180008FDC
0x180008f3b  mov     rcx, [rbx]
0x180008f3e  mov     rax, r10
0x180008f41  lock cmpxchg [rdi], rcx
0x180008f46  mov     r10, rax
0x180008f49  jz      short loc_180008EF4
0x180008f4b  mov     r9d, eax
0x180008f4e  jmp     short loc_180008F1E
0x180008f50  mov     rax, cs:g_wil_details_apiGetFeatureVariant
0x180008f57  test    rax, rax
0x180008f5a  jnz     loc_180008ED5
0x180008f60  mov     eax, [rbp+arg_8]
0x180008f63  mov     r8d, edx
0x180008f66  neg     eax
0x180008f68  mov     eax, edx
0x180008f6a  sbb     ecx, ecx
0x180008f6c  and     r8d, 80h
0x180008f73  shl     r8d, 4
0x180008f77  and     ecx, 400h
0x180008f7d  or      r8d, ecx
0x180008f80  and     eax, 0FFFFFE7Fh
0x180008f85  jz      short loc_180008F9F
0x180008f87  and     eax, 3Fh
0x180008f8a  shl     eax, 0Ch
0x180008f8d  xor     r8d, eax
0x180008f90  bt      edx, 8
0x180008f94  jnb     short loc_180008F9F
0x180008f96  mov     r11d, [rbp+arg_10]
0x180008f9a  jmp     loc_180008F0E
0x180008f9f  xor     r11d, r11d
0x180008fa2  jmp     loc_180008F0E
0x180008fa7  mov     eax, dword ptr [rbp+arg_0]
0x180008faa  mov     edx, r9d
0x180008fad  xor     edx, r8d
0x180008fb0  mov     [rbx+4], r11d
0x180008fb4  and     edx, 3F000h
0x180008fba  xor     edx, r9d
0x180008fbd  neg     eax
0x180008fbf  sbb     ecx, ecx
0x180008fc1  and     edx, 0FFFFFFF7h
0x180008fc4  and     ecx, 8
0x180008fc7  or      edx, ecx
0x180008fc9  mov     eax, edx
0x180008fcb  xor     eax, r8d
0x180008fce  and     eax, 800h
0x180008fd3  xor     eax, edx
0x180008fd5  mov     [rbx], eax
0x180008fd7  jmp     loc_180008F31
0x180008fdc  mov     ecx, r8d
0x180008fdf  xor     ecx, eax
0x180008fe1  and     ecx, 400h
0x180008fe7  xor     ecx, eax
0x180008fe9  or      ecx, 4
0x180008fec  mov     [rbx], ecx
0x180008fee  jmp     loc_180008F3B
0x180008ff3  mov     r9d, esi
0x180008ff6  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180008ffd  xor     r8d, r8d
0x180009000  mov     rdx, rdi
0x180009003  call    ?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180009008  jmp     loc_180008EFE
```
