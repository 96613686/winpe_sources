# wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState

- ea: `0x180007da0`
- end: `0x180007eb1`
- name: `wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState`
- size: `273`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180007838`
- `0x180008064`

## callees

- `0x180007da0`
- `0x180007f0c`
- `0x18000d010`

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
0x180007da0  mov     [rsp+arg_10], rbx
0x180007da5  mov     [rsp+arg_18], rbp
0x180007daa  push    rsi
0x180007dab  push    rdi
0x180007dac  push    r12
0x180007dae  push    r14
0x180007db0  push    r15
0x180007db2  sub     rsp, 20h
0x180007db6  mov     rax, cs:g_wil_details_ensureSubscribedToFeatureConfigurationChanges
0x180007dbd  xor     r14d, r14d
0x180007dc0  mov     [rsp+48h+arg_0], r14d
0x180007dc5  mov     r15, r8
0x180007dc8  mov     [rsp+48h+arg_8], rdx
0x180007dcd  mov     rbx, rdx
0x180007dd0  mov     r12, rcx
0x180007dd3  test    rax, rax
0x180007dd6  jz      short loc_180007DE0
0x180007dd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ddd  mov     r14d, eax
0x180007de0  lea     rdx, [rsp+48h+arg_0]
0x180007de5  mov     rcx, r15
0x180007de8  call    wil_details_GetCurrentFeatureEnabledState
0x180007ded  cmp     byte ptr [r15+1Ch], 0
0x180007df2  mov     rdi, rax
0x180007df5  jnz     short loc_180007E04
0x180007df7  mov     ecx, r14d
0x180007dfa  neg     ecx
0x180007dfc  sbb     ebp, ebp
0x180007dfe  and     ebp, [rsp+48h+arg_0]
0x180007e02  jmp     short loc_180007E08
0x180007e04  mov     ebp, [rsp+48h+arg_0]
0x180007e08  mov     dword ptr [rsp+48h+arg_8], ebx
0x180007e0c  mov     esi, ebx
0x180007e0e  test    ebp, ebp
0x180007e10  jz      short loc_180007E31
0x180007e12  mov     dword ptr [rsp+48h+arg_8], ebx
0x180007e16  test    bl, 2
0x180007e19  jnz     short loc_180007E31
0x180007e1b  and     esi, 0FFFFF63Eh
0x180007e21  mov     eax, edi
0x180007e23  and     eax, 9C1h
0x180007e28  or      esi, eax
0x180007e2a  or      esi, 2
0x180007e2d  mov     dword ptr [rsp+48h+arg_8], esi
0x180007e31  mov     edx, ebx
0x180007e33  and     edx, 4
0x180007e36  jnz     short loc_180007E51
0x180007e38  mov     eax, esi
0x180007e3a  mov     ecx, edi
0x180007e3c  and     ecx, 400h
0x180007e42  btr     eax, 0Ah
0x180007e46  mov     esi, ecx
0x180007e48  or      esi, eax
0x180007e4a  or      esi, 4
0x180007e4d  mov     dword ptr [rsp+48h+arg_8], esi
0x180007e51  mov     eax, ebx
0x180007e53  lock cmpxchg [r12], esi
0x180007e59  jz      short loc_180007E5F
0x180007e5b  mov     ebx, eax
0x180007e5d  jmp     short loc_180007E08
0x180007e5f  test    edx, edx
0x180007e61  jnz     short loc_180007E7F
0x180007e63  mov     rax, cs:g_wil_details_subscribeFeatureStateCacheToConfigurationChanges
0x180007e6a  test    rax, rax
0x180007e6d  jz      short loc_180007E7F
0x180007e6f  movzx   edx, byte ptr [r15+1Ch]
0x180007e74  mov     r8d, r14d
0x180007e77  mov     rcx, r12
0x180007e7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e7f  test    ebp, ebp
0x180007e81  jnz     short loc_180007E95
0x180007e83  and     esi, 0FFFFF63Eh
0x180007e89  and     edi, 9C1h
0x180007e8f  or      esi, edi
0x180007e91  mov     dword ptr [rsp+48h+arg_8], esi
0x180007e95  mov     rax, [rsp+48h+arg_8]
0x180007e9a  mov     rbx, [rsp+48h+arg_10]
0x180007e9f  mov     rbp, [rsp+48h+arg_18]
0x180007ea4  add     rsp, 20h
0x180007ea8  pop     r15
0x180007eaa  pop     r14
0x180007eac  pop     r12
0x180007eae  pop     rdi
0x180007eaf  pop     rsi
0x180007eb0  retn
```
