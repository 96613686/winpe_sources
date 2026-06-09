# wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState

- ea: `0x140001dc4`
- end: `0x140001ed6`
- name: `wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState`
- size: `274`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400015c0`
- `0x14000185c`

## callees

- `0x140001dc4`
- `0x140001f20`
- `0x140002710`

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
0x140001dc4  mov     [rsp+arg_10], rbx
0x140001dc9  mov     [rsp+arg_18], rbp
0x140001dce  push    rsi
0x140001dcf  push    rdi
0x140001dd0  push    r12
0x140001dd2  push    r14
0x140001dd4  push    r15
0x140001dd6  sub     rsp, 20h
0x140001dda  mov     rax, cs:g_wil_details_ensureSubscribedToFeatureConfigurationChanges
0x140001de1  xor     r14d, r14d
0x140001de4  mov     [rsp+48h+arg_0], r14d
0x140001de9  mov     r15, r8
0x140001dec  mov     [rsp+48h+arg_8], rdx
0x140001df1  mov     rbx, rdx
0x140001df4  mov     r12, rcx
0x140001df7  test    rax, rax
0x140001dfa  jz      short loc_140001E04
0x140001dfc  call    _guard_dispatch_icall
0x140001e01  mov     r14d, eax
0x140001e04  lea     rdx, [rsp+48h+arg_0]
0x140001e09  mov     rcx, r15
0x140001e0c  call    wil_details_GetCurrentFeatureEnabledState
0x140001e11  cmp     byte ptr [r15+1Ch], 0
0x140001e16  mov     rdi, rax
0x140001e19  jnz     short loc_140001E28
0x140001e1b  mov     ecx, r14d
0x140001e1e  neg     ecx
0x140001e20  sbb     ebp, ebp
0x140001e22  and     ebp, [rsp+48h+arg_0]
0x140001e26  jmp     short loc_140001E2C
0x140001e28  mov     ebp, [rsp+48h+arg_0]
0x140001e2c  mov     dword ptr [rsp+48h+arg_8], ebx
0x140001e30  mov     esi, ebx
0x140001e32  test    ebp, ebp
0x140001e34  jz      short loc_140001E55
0x140001e36  mov     dword ptr [rsp+48h+arg_8], ebx
0x140001e3a  test    bl, 2
0x140001e3d  jnz     short loc_140001E55
0x140001e3f  and     esi, 0FFFFF63Eh
0x140001e45  mov     eax, edi
0x140001e47  and     eax, 9C1h
0x140001e4c  or      esi, eax
0x140001e4e  or      esi, 2
0x140001e51  mov     dword ptr [rsp+48h+arg_8], esi
0x140001e55  mov     edx, ebx
0x140001e57  and     edx, 4
0x140001e5a  jnz     short loc_140001E75
0x140001e5c  mov     eax, esi
0x140001e5e  mov     ecx, edi
0x140001e60  and     ecx, 400h
0x140001e66  btr     eax, 0Ah
0x140001e6a  mov     esi, ecx
0x140001e6c  or      esi, eax
0x140001e6e  or      esi, 4
0x140001e71  mov     dword ptr [rsp+48h+arg_8], esi
0x140001e75  mov     eax, ebx
0x140001e77  lock cmpxchg [r12], esi
0x140001e7d  jz      short loc_140001E83
0x140001e7f  mov     ebx, eax
0x140001e81  jmp     short loc_140001E2C
0x140001e83  test    edx, edx
0x140001e85  jnz     short loc_140001EA3
0x140001e87  mov     rax, cs:g_wil_details_subscribeFeatureStateCacheToConfigurationChanges
0x140001e8e  test    rax, rax
0x140001e91  jz      short loc_140001EA3
0x140001e93  movzx   edx, byte ptr [r15+1Ch]
0x140001e98  mov     r8d, r14d
0x140001e9b  mov     rcx, r12
0x140001e9e  call    _guard_dispatch_icall
0x140001ea3  test    ebp, ebp
0x140001ea5  jnz     short loc_140001EB9
0x140001ea7  and     esi, 0FFFFF63Eh
0x140001ead  and     edi, 9C1h
0x140001eb3  or      esi, edi
0x140001eb5  mov     dword ptr [rsp+48h+arg_8], esi
0x140001eb9  mov     rax, [rsp+48h+arg_8]
0x140001ebe  mov     rbx, [rsp+48h+arg_10]
0x140001ec3  mov     rbp, [rsp+48h+arg_18]
0x140001ec8  add     rsp, 20h
0x140001ecc  pop     r15
0x140001ece  pop     r14
0x140001ed0  pop     r12
0x140001ed2  pop     rdi
0x140001ed3  pop     rsi
0x140001ed4  retn
```
