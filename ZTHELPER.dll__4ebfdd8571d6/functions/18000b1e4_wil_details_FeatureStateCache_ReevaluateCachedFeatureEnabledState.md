# wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState

- ea: `0x18000b1e4`
- end: `0x18000b2f6`
- name: `wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState`
- size: `274`
- prototype: `__int64 __fastcall(volatile signed __int32 *, __int64, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000ac08`
- `0x18000b4a8`

## callees

- `0x18000b1e4`
- `0x18000b350`
- `0x180018010`

## pseudocode

```c
__int64 __fastcall wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState(
        volatile signed __int32 *a1,
        __int64 a2,
        __int64 a3)
{
  unsigned int v3; // r14d
  signed __int32 v5; // edi
  __int16 CurrentFeatureEnabledState; // bx
  int v8; // ebp
  unsigned int v9; // esi
  signed __int32 v10; // eax
  int v12; // [rsp+50h] [rbp+8h] BYREF
  __int64 v13; // [rsp+58h] [rbp+10h]

  v3 = 0;
  v12 = 0;
  v13 = a2;
  v5 = a2;
  if ( g_wil_details_ensureSubscribedToFeatureConfigurationChanges )
    v3 = g_wil_details_ensureSubscribedToFeatureConfigurationChanges();
  CurrentFeatureEnabledState = wil_details_GetCurrentFeatureEnabledState(a3, &v12);
  if ( *(_BYTE *)(a3 + 28) )
    v8 = v12;
  else
    v8 = v3 != 0 ? v12 : 0;
  while ( 1 )
  {
    LODWORD(v13) = v5;
    v9 = v5;
    if ( v8 )
    {
      LODWORD(v13) = v5;
      if ( (v5 & 2) == 0 )
      {
        v9 = CurrentFeatureEnabledState & 0x9C1 | v5 & 0xFFFFF63E | 2;
        LODWORD(v13) = v9;
      }
    }
    if ( (v5 & 4) == 0 )
    {
      v9 = v9 & 0xFFFFFBFF | CurrentFeatureEnabledState & 0x400 | 4;
      LODWORD(v13) = v9;
    }
    v10 = _InterlockedCompareExchange(a1, v9, v5);
    if ( v5 == v10 )
      break;
    v5 = v10;
  }
  if ( (v5 & 4) == 0 && g_wil_details_subscribeFeatureStateCacheToConfigurationChanges )
    g_wil_details_subscribeFeatureStateCacheToConfigurationChanges(a1, *(unsigned __int8 *)(a3 + 28), v3);
  if ( !v8 )
    LODWORD(v13) = v9 & 0xFFFFF63E | CurrentFeatureEnabledState & 0x9C1;
  return v13;
}

```

## disassembly

```asm
0x18000b1e4  mov     [rsp+arg_10], rbx
0x18000b1e9  mov     [rsp+arg_18], rbp
0x18000b1ee  push    rsi
0x18000b1ef  push    rdi
0x18000b1f0  push    r12
0x18000b1f2  push    r14
0x18000b1f4  push    r15
0x18000b1f6  sub     rsp, 20h
0x18000b1fa  mov     rax, cs:g_wil_details_ensureSubscribedToFeatureConfigurationChanges
0x18000b201  xor     r14d, r14d
0x18000b204  mov     [rsp+48h+arg_0], r14d
0x18000b209  mov     r15, r8
0x18000b20c  mov     [rsp+48h+arg_8], rdx
0x18000b211  mov     rdi, rdx
0x18000b214  mov     r12, rcx
0x18000b217  test    rax, rax
0x18000b21a  jz      short loc_18000B224
0x18000b21c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b221  mov     r14d, eax
0x18000b224  lea     rdx, [rsp+48h+arg_0]
0x18000b229  mov     rcx, r15
0x18000b22c  call    wil_details_GetCurrentFeatureEnabledState
0x18000b231  cmp     byte ptr [r15+1Ch], 0
0x18000b236  mov     rbx, rax
0x18000b239  jnz     short loc_18000B248
0x18000b23b  mov     ecx, r14d
0x18000b23e  neg     ecx
0x18000b240  sbb     ebp, ebp
0x18000b242  and     ebp, [rsp+48h+arg_0]
0x18000b246  jmp     short loc_18000B24C
0x18000b248  mov     ebp, [rsp+48h+arg_0]
0x18000b24c  mov     dword ptr [rsp+48h+arg_8], edi
0x18000b250  mov     esi, edi
0x18000b252  test    ebp, ebp
0x18000b254  jz      short loc_18000B276
0x18000b256  mov     dword ptr [rsp+48h+arg_8], edi
0x18000b25a  test    dil, 2
0x18000b25e  jnz     short loc_18000B276
0x18000b260  and     esi, 0FFFFF63Eh
0x18000b266  mov     eax, ebx
0x18000b268  and     eax, 9C1h
0x18000b26d  or      esi, eax
0x18000b26f  or      esi, 2
0x18000b272  mov     dword ptr [rsp+48h+arg_8], esi
0x18000b276  mov     edx, edi
0x18000b278  and     edx, 4
0x18000b27b  jnz     short loc_18000B296
0x18000b27d  mov     eax, esi
0x18000b27f  mov     ecx, ebx
0x18000b281  and     ecx, 400h
0x18000b287  btr     eax, 0Ah
0x18000b28b  mov     esi, ecx
0x18000b28d  or      esi, eax
0x18000b28f  or      esi, 4
0x18000b292  mov     dword ptr [rsp+48h+arg_8], esi
0x18000b296  mov     eax, edi
0x18000b298  lock cmpxchg [r12], esi
0x18000b29e  jz      short loc_18000B2A4
0x18000b2a0  mov     edi, eax
0x18000b2a2  jmp     short loc_18000B24C
0x18000b2a4  test    edx, edx
0x18000b2a6  jnz     short loc_18000B2C4
0x18000b2a8  mov     rax, cs:g_wil_details_subscribeFeatureStateCacheToConfigurationChanges
0x18000b2af  test    rax, rax
0x18000b2b2  jz      short loc_18000B2C4
0x18000b2b4  movzx   edx, byte ptr [r15+1Ch]
0x18000b2b9  mov     r8d, r14d
0x18000b2bc  mov     rcx, r12
0x18000b2bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b2c4  test    ebp, ebp
0x18000b2c6  jnz     short loc_18000B2DA
0x18000b2c8  and     ebx, 9C1h
0x18000b2ce  and     esi, 0FFFFF63Eh
0x18000b2d4  or      ebx, esi
0x18000b2d6  mov     dword ptr [rsp+48h+arg_8], ebx
0x18000b2da  mov     rax, [rsp+48h+arg_8]
0x18000b2df  mov     rbx, [rsp+48h+arg_10]
0x18000b2e4  mov     rbp, [rsp+48h+arg_18]
0x18000b2e9  add     rsp, 20h
0x18000b2ed  pop     r15
0x18000b2ef  pop     r14
0x18000b2f1  pop     r12
0x18000b2f3  pop     rdi
0x18000b2f4  pop     rsi
0x18000b2f5  retn
```
