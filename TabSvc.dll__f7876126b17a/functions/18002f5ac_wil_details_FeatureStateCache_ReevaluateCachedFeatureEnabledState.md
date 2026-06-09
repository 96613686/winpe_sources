# wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState

- ea: `0x18002f5ac`
- end: `0x18002f6be`
- name: `wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState`
- size: `274`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002f420`
- `0x18002f820`

## callees

- `0x18002f5ac`
- `0x18002f704`
- `0x180031010`

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
0x18002f5ac  mov     [rsp+arg_10], rbx
0x18002f5b1  mov     [rsp+arg_18], rbp
0x18002f5b6  push    rsi
0x18002f5b7  push    rdi
0x18002f5b8  push    r12
0x18002f5ba  push    r14
0x18002f5bc  push    r15
0x18002f5be  sub     rsp, 20h
0x18002f5c2  mov     rax, cs:g_wil_details_ensureSubscribedToFeatureConfigurationChanges
0x18002f5c9  xor     r14d, r14d
0x18002f5cc  mov     [rsp+48h+arg_0], r14d
0x18002f5d1  mov     r15, r8
0x18002f5d4  mov     [rsp+48h+arg_8], rdx
0x18002f5d9  mov     rdi, rdx
0x18002f5dc  mov     r12, rcx
0x18002f5df  test    rax, rax
0x18002f5e2  jz      short loc_18002F5EC
0x18002f5e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f5e9  mov     r14d, eax
0x18002f5ec  lea     rdx, [rsp+48h+arg_0]
0x18002f5f1  mov     rcx, r15
0x18002f5f4  call    wil_details_GetCurrentFeatureEnabledState
0x18002f5f9  cmp     byte ptr [r15+1Ch], 0
0x18002f5fe  mov     rbx, rax
0x18002f601  jnz     short loc_18002F610
0x18002f603  mov     ecx, r14d
0x18002f606  neg     ecx
0x18002f608  sbb     ebp, ebp
0x18002f60a  and     ebp, [rsp+48h+arg_0]
0x18002f60e  jmp     short loc_18002F614
0x18002f610  mov     ebp, [rsp+48h+arg_0]
0x18002f614  mov     dword ptr [rsp+48h+arg_8], edi
0x18002f618  mov     esi, edi
0x18002f61a  test    ebp, ebp
0x18002f61c  jz      short loc_18002F63E
0x18002f61e  mov     dword ptr [rsp+48h+arg_8], edi
0x18002f622  test    dil, 2
0x18002f626  jnz     short loc_18002F63E
0x18002f628  and     esi, 0FFFFF63Eh
0x18002f62e  mov     eax, ebx
0x18002f630  and     eax, 9C1h
0x18002f635  or      esi, eax
0x18002f637  or      esi, 2
0x18002f63a  mov     dword ptr [rsp+48h+arg_8], esi
0x18002f63e  mov     edx, edi
0x18002f640  and     edx, 4
0x18002f643  jnz     short loc_18002F65E
0x18002f645  mov     eax, esi
0x18002f647  mov     ecx, ebx
0x18002f649  and     ecx, 400h
0x18002f64f  btr     eax, 0Ah
0x18002f653  mov     esi, ecx
0x18002f655  or      esi, eax
0x18002f657  or      esi, 4
0x18002f65a  mov     dword ptr [rsp+48h+arg_8], esi
0x18002f65e  mov     eax, edi
0x18002f660  lock cmpxchg [r12], esi
0x18002f666  jz      short loc_18002F66C
0x18002f668  mov     edi, eax
0x18002f66a  jmp     short loc_18002F614
0x18002f66c  test    edx, edx
0x18002f66e  jnz     short loc_18002F68C
0x18002f670  mov     rax, cs:g_wil_details_subscribeFeatureStateCacheToConfigurationChanges
0x18002f677  test    rax, rax
0x18002f67a  jz      short loc_18002F68C
0x18002f67c  movzx   edx, byte ptr [r15+1Ch]
0x18002f681  mov     r8d, r14d
0x18002f684  mov     rcx, r12
0x18002f687  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f68c  test    ebp, ebp
0x18002f68e  jnz     short loc_18002F6A2
0x18002f690  and     ebx, 9C1h
0x18002f696  and     esi, 0FFFFF63Eh
0x18002f69c  or      ebx, esi
0x18002f69e  mov     dword ptr [rsp+48h+arg_8], ebx
0x18002f6a2  mov     rax, [rsp+48h+arg_8]
0x18002f6a7  mov     rbx, [rsp+48h+arg_10]
0x18002f6ac  mov     rbp, [rsp+48h+arg_18]
0x18002f6b1  add     rsp, 20h
0x18002f6b5  pop     r15
0x18002f6b7  pop     r14
0x18002f6b9  pop     r12
0x18002f6bb  pop     rdi
0x18002f6bc  pop     rsi
0x18002f6bd  retn
```
