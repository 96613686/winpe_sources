# wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState

- ea: `0x140004c48`
- end: `0x140004d5a`
- name: `wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState`
- size: `274`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140003690`
- `0x1400046e4`

## callees

- `0x140004c48`
- `0x140004db4`
- `0x1400138a0`

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
0x140004c48  mov     [rsp+arg_10], rbx
0x140004c4d  mov     [rsp+arg_18], rbp
0x140004c52  push    rsi
0x140004c53  push    rdi
0x140004c54  push    r12
0x140004c56  push    r14
0x140004c58  push    r15
0x140004c5a  sub     rsp, 20h
0x140004c5e  mov     rax, cs:g_wil_details_ensureSubscribedToFeatureConfigurationChanges
0x140004c65  xor     r14d, r14d
0x140004c68  mov     [rsp+48h+arg_0], r14d
0x140004c6d  mov     r15, r8
0x140004c70  mov     [rsp+48h+arg_8], rdx
0x140004c75  mov     rbx, rdx
0x140004c78  mov     r12, rcx
0x140004c7b  test    rax, rax
0x140004c7e  jz      short loc_140004C88
0x140004c80  call    _guard_dispatch_icall
0x140004c85  mov     r14d, eax
0x140004c88  lea     rdx, [rsp+48h+arg_0]
0x140004c8d  mov     rcx, r15
0x140004c90  call    wil_details_GetCurrentFeatureEnabledState
0x140004c95  cmp     byte ptr [r15+1Ch], 0
0x140004c9a  mov     rdi, rax
0x140004c9d  jnz     short loc_140004CAC
0x140004c9f  mov     ecx, r14d
0x140004ca2  neg     ecx
0x140004ca4  sbb     ebp, ebp
0x140004ca6  and     ebp, [rsp+48h+arg_0]
0x140004caa  jmp     short loc_140004CB0
0x140004cac  mov     ebp, [rsp+48h+arg_0]
0x140004cb0  mov     dword ptr [rsp+48h+arg_8], ebx
0x140004cb4  mov     esi, ebx
0x140004cb6  test    ebp, ebp
0x140004cb8  jz      short loc_140004CD9
0x140004cba  mov     dword ptr [rsp+48h+arg_8], ebx
0x140004cbe  test    bl, 2
0x140004cc1  jnz     short loc_140004CD9
0x140004cc3  and     esi, 0FFFFF63Eh
0x140004cc9  mov     eax, edi
0x140004ccb  and     eax, 9C1h
0x140004cd0  or      esi, eax
0x140004cd2  or      esi, 2
0x140004cd5  mov     dword ptr [rsp+48h+arg_8], esi
0x140004cd9  mov     edx, ebx
0x140004cdb  and     edx, 4
0x140004cde  jnz     short loc_140004CF9
0x140004ce0  mov     eax, esi
0x140004ce2  mov     ecx, edi
0x140004ce4  and     ecx, 400h
0x140004cea  btr     eax, 0Ah
0x140004cee  mov     esi, ecx
0x140004cf0  or      esi, eax
0x140004cf2  or      esi, 4
0x140004cf5  mov     dword ptr [rsp+48h+arg_8], esi
0x140004cf9  mov     eax, ebx
0x140004cfb  lock cmpxchg [r12], esi
0x140004d01  jz      short loc_140004D07
0x140004d03  mov     ebx, eax
0x140004d05  jmp     short loc_140004CB0
0x140004d07  test    edx, edx
0x140004d09  jnz     short loc_140004D27
0x140004d0b  mov     rax, cs:g_wil_details_subscribeFeatureStateCacheToConfigurationChanges
0x140004d12  test    rax, rax
0x140004d15  jz      short loc_140004D27
0x140004d17  movzx   edx, byte ptr [r15+1Ch]
0x140004d1c  mov     r8d, r14d
0x140004d1f  mov     rcx, r12
0x140004d22  call    _guard_dispatch_icall
0x140004d27  test    ebp, ebp
0x140004d29  jnz     short loc_140004D3D
0x140004d2b  and     esi, 0FFFFF63Eh
0x140004d31  and     edi, 9C1h
0x140004d37  or      esi, edi
0x140004d39  mov     dword ptr [rsp+48h+arg_8], esi
0x140004d3d  mov     rax, [rsp+48h+arg_8]
0x140004d42  mov     rbx, [rsp+48h+arg_10]
0x140004d47  mov     rbp, [rsp+48h+arg_18]
0x140004d4c  add     rsp, 20h
0x140004d50  pop     r15
0x140004d52  pop     r14
0x140004d54  pop     r12
0x140004d56  pop     rdi
0x140004d57  pop     rsi
0x140004d58  retn
```
