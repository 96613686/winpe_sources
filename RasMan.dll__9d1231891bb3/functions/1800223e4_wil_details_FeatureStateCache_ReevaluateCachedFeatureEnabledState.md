# wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState

- ea: `0x1800223e4`
- end: `0x1800224f5`
- name: `wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState`
- size: `273`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180021e40`
- `0x1800226a8`

## callees

- `0x1800223e4`
- `0x180022550`
- `0x180027010`

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
0x1800223e4  mov     [rsp+arg_10], rbx
0x1800223e9  mov     [rsp+arg_18], rbp
0x1800223ee  push    rsi
0x1800223ef  push    rdi
0x1800223f0  push    r12
0x1800223f2  push    r14
0x1800223f4  push    r15
0x1800223f6  sub     rsp, 20h
0x1800223fa  mov     rax, cs:g_wil_details_ensureSubscribedToFeatureConfigurationChanges
0x180022401  xor     r14d, r14d
0x180022404  mov     [rsp+48h+arg_0], r14d
0x180022409  mov     r15, r8
0x18002240c  mov     [rsp+48h+arg_8], rdx
0x180022411  mov     rbx, rdx
0x180022414  mov     r12, rcx
0x180022417  test    rax, rax
0x18002241a  jz      short loc_180022424
0x18002241c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022421  mov     r14d, eax
0x180022424  lea     rdx, [rsp+48h+arg_0]
0x180022429  mov     rcx, r15
0x18002242c  call    wil_details_GetCurrentFeatureEnabledState
0x180022431  cmp     byte ptr [r15+1Ch], 0
0x180022436  mov     rdi, rax
0x180022439  jnz     short loc_180022448
0x18002243b  mov     ecx, r14d
0x18002243e  neg     ecx
0x180022440  sbb     ebp, ebp
0x180022442  and     ebp, [rsp+48h+arg_0]
0x180022446  jmp     short loc_18002244C
0x180022448  mov     ebp, [rsp+48h+arg_0]
0x18002244c  mov     dword ptr [rsp+48h+arg_8], ebx
0x180022450  mov     esi, ebx
0x180022452  test    ebp, ebp
0x180022454  jz      short loc_180022475
0x180022456  mov     dword ptr [rsp+48h+arg_8], ebx
0x18002245a  test    bl, 2
0x18002245d  jnz     short loc_180022475
0x18002245f  and     esi, 0FFFFF63Eh
0x180022465  mov     eax, edi
0x180022467  and     eax, 9C1h
0x18002246c  or      esi, eax
0x18002246e  or      esi, 2
0x180022471  mov     dword ptr [rsp+48h+arg_8], esi
0x180022475  mov     edx, ebx
0x180022477  and     edx, 4
0x18002247a  jnz     short loc_180022495
0x18002247c  mov     eax, esi
0x18002247e  mov     ecx, edi
0x180022480  and     ecx, 400h
0x180022486  btr     eax, 0Ah
0x18002248a  mov     esi, ecx
0x18002248c  or      esi, eax
0x18002248e  or      esi, 4
0x180022491  mov     dword ptr [rsp+48h+arg_8], esi
0x180022495  mov     eax, ebx
0x180022497  lock cmpxchg [r12], esi
0x18002249d  jz      short loc_1800224A3
0x18002249f  mov     ebx, eax
0x1800224a1  jmp     short loc_18002244C
0x1800224a3  test    edx, edx
0x1800224a5  jnz     short loc_1800224C3
0x1800224a7  mov     rax, cs:g_wil_details_subscribeFeatureStateCacheToConfigurationChanges
0x1800224ae  test    rax, rax
0x1800224b1  jz      short loc_1800224C3
0x1800224b3  movzx   edx, byte ptr [r15+1Ch]
0x1800224b8  mov     r8d, r14d
0x1800224bb  mov     rcx, r12
0x1800224be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800224c3  test    ebp, ebp
0x1800224c5  jnz     short loc_1800224D9
0x1800224c7  and     esi, 0FFFFF63Eh
0x1800224cd  and     edi, 9C1h
0x1800224d3  or      esi, edi
0x1800224d5  mov     dword ptr [rsp+48h+arg_8], esi
0x1800224d9  mov     rax, [rsp+48h+arg_8]
0x1800224de  mov     rbx, [rsp+48h+arg_10]
0x1800224e3  mov     rbp, [rsp+48h+arg_18]
0x1800224e8  add     rsp, 20h
0x1800224ec  pop     r15
0x1800224ee  pop     r14
0x1800224f0  pop     r12
0x1800224f2  pop     rdi
0x1800224f3  pop     rsi
0x1800224f4  retn
```
