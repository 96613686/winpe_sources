# wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState

- ea: `0x140002824`
- end: `0x140002936`
- name: `wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState`
- size: `274`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400027ec`
- `0x140002aa8`

## callees

- `0x140002824`
- `0x140002990`
- `0x140006a60`

## pseudocode

```c
__int64 __fastcall wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState(
        volatile signed __int32 *a1,
        __int64 a2,
        __int64 a3)
{
  unsigned int v3; // r14d
  signed __int32 v5; // ebx
  __int16 CurrentFeatureEnabledState; // di
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
    LODWORD(v13) = CurrentFeatureEnabledState & 0x9C1 | v9 & 0xFFFFF63E;
  return v13;
}

```

## disassembly

```asm
0x140002824  mov     [rsp+arg_10], rbx
0x140002829  mov     [rsp+arg_18], rbp
0x14000282e  push    rsi
0x14000282f  push    rdi
0x140002830  push    r12
0x140002832  push    r14
0x140002834  push    r15
0x140002836  sub     rsp, 20h
0x14000283a  mov     rax, cs:g_wil_details_ensureSubscribedToFeatureConfigurationChanges
0x140002841  xor     r14d, r14d
0x140002844  mov     [rsp+48h+arg_0], r14d
0x140002849  mov     r15, r8
0x14000284c  mov     [rsp+48h+arg_8], rdx
0x140002851  mov     rbx, rdx
0x140002854  mov     r12, rcx
0x140002857  test    rax, rax
0x14000285a  jz      short loc_140002864
0x14000285c  call    _guard_dispatch_icall
0x140002861  mov     r14d, eax
0x140002864  lea     rdx, [rsp+48h+arg_0]
0x140002869  mov     rcx, r15
0x14000286c  call    wil_details_GetCurrentFeatureEnabledState
0x140002871  cmp     byte ptr [r15+1Ch], 0
0x140002876  mov     rdi, rax
0x140002879  jnz     short loc_140002888
0x14000287b  mov     ecx, r14d
0x14000287e  neg     ecx
0x140002880  sbb     ebp, ebp
0x140002882  and     ebp, [rsp+48h+arg_0]
0x140002886  jmp     short loc_14000288C
0x140002888  mov     ebp, [rsp+48h+arg_0]
0x14000288c  mov     dword ptr [rsp+48h+arg_8], ebx
0x140002890  mov     esi, ebx
0x140002892  test    ebp, ebp
0x140002894  jz      short loc_1400028B5
0x140002896  mov     dword ptr [rsp+48h+arg_8], ebx
0x14000289a  test    bl, 2
0x14000289d  jnz     short loc_1400028B5
0x14000289f  and     esi, 0FFFFF63Eh
0x1400028a5  mov     eax, edi
0x1400028a7  and     eax, 9C1h
0x1400028ac  or      esi, eax
0x1400028ae  or      esi, 2
0x1400028b1  mov     dword ptr [rsp+48h+arg_8], esi
0x1400028b5  mov     edx, ebx
0x1400028b7  and     edx, 4
0x1400028ba  jnz     short loc_1400028D5
0x1400028bc  mov     eax, esi
0x1400028be  mov     ecx, edi
0x1400028c0  and     ecx, 400h
0x1400028c6  btr     eax, 0Ah
0x1400028ca  mov     esi, ecx
0x1400028cc  or      esi, eax
0x1400028ce  or      esi, 4
0x1400028d1  mov     dword ptr [rsp+48h+arg_8], esi
0x1400028d5  mov     eax, ebx
0x1400028d7  lock cmpxchg [r12], esi
0x1400028dd  jz      short loc_1400028E3
0x1400028df  mov     ebx, eax
0x1400028e1  jmp     short loc_14000288C
0x1400028e3  test    edx, edx
0x1400028e5  jnz     short loc_140002903
0x1400028e7  mov     rax, cs:g_wil_details_subscribeFeatureStateCacheToConfigurationChanges
0x1400028ee  test    rax, rax
0x1400028f1  jz      short loc_140002903
0x1400028f3  movzx   edx, byte ptr [r15+1Ch]
0x1400028f8  mov     r8d, r14d
0x1400028fb  mov     rcx, r12
0x1400028fe  call    _guard_dispatch_icall
0x140002903  test    ebp, ebp
0x140002905  jnz     short loc_140002919
0x140002907  and     esi, 0FFFFF63Eh
0x14000290d  and     edi, 9C1h
0x140002913  or      esi, edi
0x140002915  mov     dword ptr [rsp+48h+arg_8], esi
0x140002919  mov     rax, [rsp+48h+arg_8]
0x14000291e  mov     rbx, [rsp+48h+arg_10]
0x140002923  mov     rbp, [rsp+48h+arg_18]
0x140002928  add     rsp, 20h
0x14000292c  pop     r15
0x14000292e  pop     r14
0x140002930  pop     r12
0x140002932  pop     rdi
0x140002933  pop     rsi
0x140002934  retn
```
