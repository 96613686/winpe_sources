# wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState

- ea: `0x18000fd5c`
- end: `0x18000fe6d`
- name: `wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState`
- size: `273`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000feb8`
- `0x180010104`

## callees

- `0x18000fd5c`
- `0x18000feb8`
- `0x18001c010`

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
0x18000fd5c  mov     [rsp+arg_10], rbx
0x18000fd61  mov     [rsp+arg_18], rbp
0x18000fd66  push    rsi
0x18000fd67  push    rdi
0x18000fd68  push    r12
0x18000fd6a  push    r14
0x18000fd6c  push    r15
0x18000fd6e  sub     rsp, 20h
0x18000fd72  mov     rax, cs:g_wil_details_ensureSubscribedToFeatureConfigurationChanges
0x18000fd79  xor     r14d, r14d
0x18000fd7c  mov     [rsp+48h+arg_0], r14d
0x18000fd81  mov     r15, r8
0x18000fd84  mov     [rsp+48h+arg_8], rdx
0x18000fd89  mov     rbx, rdx
0x18000fd8c  mov     r12, rcx
0x18000fd8f  test    rax, rax
0x18000fd92  jz      short loc_18000FD9C
0x18000fd94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fd99  mov     r14d, eax
0x18000fd9c  lea     rdx, [rsp+48h+arg_0]
0x18000fda1  mov     rcx, r15
0x18000fda4  call    wil_details_GetCurrentFeatureEnabledState
0x18000fda9  cmp     byte ptr [r15+1Ch], 0
0x18000fdae  mov     rdi, rax
0x18000fdb1  jnz     short loc_18000FDC0
0x18000fdb3  mov     ecx, r14d
0x18000fdb6  neg     ecx
0x18000fdb8  sbb     ebp, ebp
0x18000fdba  and     ebp, [rsp+48h+arg_0]
0x18000fdbe  jmp     short loc_18000FDC4
0x18000fdc0  mov     ebp, [rsp+48h+arg_0]
0x18000fdc4  mov     dword ptr [rsp+48h+arg_8], ebx
0x18000fdc8  mov     esi, ebx
0x18000fdca  test    ebp, ebp
0x18000fdcc  jz      short loc_18000FDED
0x18000fdce  mov     dword ptr [rsp+48h+arg_8], ebx
0x18000fdd2  test    bl, 2
0x18000fdd5  jnz     short loc_18000FDED
0x18000fdd7  and     esi, 0FFFFF63Eh
0x18000fddd  mov     eax, edi
0x18000fddf  and     eax, 9C1h
0x18000fde4  or      esi, eax
0x18000fde6  or      esi, 2
0x18000fde9  mov     dword ptr [rsp+48h+arg_8], esi
0x18000fded  mov     edx, ebx
0x18000fdef  and     edx, 4
0x18000fdf2  jnz     short loc_18000FE0D
0x18000fdf4  mov     eax, esi
0x18000fdf6  mov     ecx, edi
0x18000fdf8  and     ecx, 400h
0x18000fdfe  btr     eax, 0Ah
0x18000fe02  mov     esi, ecx
0x18000fe04  or      esi, eax
0x18000fe06  or      esi, 4
0x18000fe09  mov     dword ptr [rsp+48h+arg_8], esi
0x18000fe0d  mov     eax, ebx
0x18000fe0f  lock cmpxchg [r12], esi
0x18000fe15  jz      short loc_18000FE1B
0x18000fe17  mov     ebx, eax
0x18000fe19  jmp     short loc_18000FDC4
0x18000fe1b  test    edx, edx
0x18000fe1d  jnz     short loc_18000FE3B
0x18000fe1f  mov     rax, cs:g_wil_details_subscribeFeatureStateCacheToConfigurationChanges
0x18000fe26  test    rax, rax
0x18000fe29  jz      short loc_18000FE3B
0x18000fe2b  movzx   edx, byte ptr [r15+1Ch]
0x18000fe30  mov     r8d, r14d
0x18000fe33  mov     rcx, r12
0x18000fe36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fe3b  test    ebp, ebp
0x18000fe3d  jnz     short loc_18000FE51
0x18000fe3f  and     esi, 0FFFFF63Eh
0x18000fe45  and     edi, 9C1h
0x18000fe4b  or      esi, edi
0x18000fe4d  mov     dword ptr [rsp+48h+arg_8], esi
0x18000fe51  mov     rax, [rsp+48h+arg_8]
0x18000fe56  mov     rbx, [rsp+48h+arg_10]
0x18000fe5b  mov     rbp, [rsp+48h+arg_18]
0x18000fe60  add     rsp, 20h
0x18000fe64  pop     r15
0x18000fe66  pop     r14
0x18000fe68  pop     r12
0x18000fe6a  pop     rdi
0x18000fe6b  pop     rsi
0x18000fe6c  retn
```
