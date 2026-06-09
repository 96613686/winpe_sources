# wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState

- ea: `0x140004a78`
- end: `0x140004b8a`
- name: `wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState`
- size: `274`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140003560`
- `0x140004be4`

## callees

- `0x140004a78`
- `0x140004be4`
- `0x140013770`

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
0x140004a78  mov     [rsp+arg_10], rbx
0x140004a7d  mov     [rsp+arg_18], rbp
0x140004a82  push    rsi
0x140004a83  push    rdi
0x140004a84  push    r12
0x140004a86  push    r14
0x140004a88  push    r15
0x140004a8a  sub     rsp, 20h
0x140004a8e  mov     rax, cs:g_wil_details_ensureSubscribedToFeatureConfigurationChanges
0x140004a95  xor     r14d, r14d
0x140004a98  mov     [rsp+48h+arg_0], r14d
0x140004a9d  mov     r15, r8
0x140004aa0  mov     [rsp+48h+arg_8], rdx
0x140004aa5  mov     rbx, rdx
0x140004aa8  mov     r12, rcx
0x140004aab  test    rax, rax
0x140004aae  jz      short loc_140004AB8
0x140004ab0  call    _guard_dispatch_icall
0x140004ab5  mov     r14d, eax
0x140004ab8  lea     rdx, [rsp+48h+arg_0]
0x140004abd  mov     rcx, r15
0x140004ac0  call    wil_details_GetCurrentFeatureEnabledState
0x140004ac5  cmp     byte ptr [r15+1Ch], 0
0x140004aca  mov     rdi, rax
0x140004acd  jnz     short loc_140004ADC
0x140004acf  mov     ecx, r14d
0x140004ad2  neg     ecx
0x140004ad4  sbb     ebp, ebp
0x140004ad6  and     ebp, [rsp+48h+arg_0]
0x140004ada  jmp     short loc_140004AE0
0x140004adc  mov     ebp, [rsp+48h+arg_0]
0x140004ae0  mov     dword ptr [rsp+48h+arg_8], ebx
0x140004ae4  mov     esi, ebx
0x140004ae6  test    ebp, ebp
0x140004ae8  jz      short loc_140004B09
0x140004aea  mov     dword ptr [rsp+48h+arg_8], ebx
0x140004aee  test    bl, 2
0x140004af1  jnz     short loc_140004B09
0x140004af3  and     esi, 0FFFFF63Eh
0x140004af9  mov     eax, edi
0x140004afb  and     eax, 9C1h
0x140004b00  or      esi, eax
0x140004b02  or      esi, 2
0x140004b05  mov     dword ptr [rsp+48h+arg_8], esi
0x140004b09  mov     edx, ebx
0x140004b0b  and     edx, 4
0x140004b0e  jnz     short loc_140004B29
0x140004b10  mov     eax, esi
0x140004b12  mov     ecx, edi
0x140004b14  and     ecx, 400h
0x140004b1a  btr     eax, 0Ah
0x140004b1e  mov     esi, ecx
0x140004b20  or      esi, eax
0x140004b22  or      esi, 4
0x140004b25  mov     dword ptr [rsp+48h+arg_8], esi
0x140004b29  mov     eax, ebx
0x140004b2b  lock cmpxchg [r12], esi
0x140004b31  jz      short loc_140004B37
0x140004b33  mov     ebx, eax
0x140004b35  jmp     short loc_140004AE0
0x140004b37  test    edx, edx
0x140004b39  jnz     short loc_140004B57
0x140004b3b  mov     rax, cs:g_wil_details_subscribeFeatureStateCacheToConfigurationChanges
0x140004b42  test    rax, rax
0x140004b45  jz      short loc_140004B57
0x140004b47  movzx   edx, byte ptr [r15+1Ch]
0x140004b4c  mov     r8d, r14d
0x140004b4f  mov     rcx, r12
0x140004b52  call    _guard_dispatch_icall
0x140004b57  test    ebp, ebp
0x140004b59  jnz     short loc_140004B6D
0x140004b5b  and     esi, 0FFFFF63Eh
0x140004b61  and     edi, 9C1h
0x140004b67  or      esi, edi
0x140004b69  mov     dword ptr [rsp+48h+arg_8], esi
0x140004b6d  mov     rax, [rsp+48h+arg_8]
0x140004b72  mov     rbx, [rsp+48h+arg_10]
0x140004b77  mov     rbp, [rsp+48h+arg_18]
0x140004b7c  add     rsp, 20h
0x140004b80  pop     r15
0x140004b82  pop     r14
0x140004b84  pop     r12
0x140004b86  pop     rdi
0x140004b87  pop     rsi
0x140004b88  retn
```
