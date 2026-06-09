# wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState

- ea: `0x14000e100`
- end: `0x14000e211`
- name: `wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState`
- size: `273`
- prototype: `__int64 __fastcall(volatile signed __int32 *, __int64, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000e26c`
- `0x14000e4b8`

## callees

- `0x14000e100`
- `0x14000e26c`
- `0x140027010`

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
0x14000e100  mov     [rsp+arg_10], rbx
0x14000e105  mov     [rsp+arg_18], rbp
0x14000e10a  push    rsi
0x14000e10b  push    rdi
0x14000e10c  push    r12
0x14000e10e  push    r14
0x14000e110  push    r15
0x14000e112  sub     rsp, 20h
0x14000e116  mov     rax, cs:g_wil_details_ensureSubscribedToFeatureConfigurationChanges
0x14000e11d  xor     r14d, r14d
0x14000e120  mov     [rsp+48h+arg_0], r14d
0x14000e125  mov     r15, r8
0x14000e128  mov     [rsp+48h+arg_8], rdx
0x14000e12d  mov     rbx, rdx
0x14000e130  mov     r12, rcx
0x14000e133  test    rax, rax
0x14000e136  jz      short loc_14000E140
0x14000e138  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e13d  mov     r14d, eax
0x14000e140  lea     rdx, [rsp+48h+arg_0]
0x14000e145  mov     rcx, r15
0x14000e148  call    wil_details_GetCurrentFeatureEnabledState
0x14000e14d  cmp     byte ptr [r15+1Ch], 0
0x14000e152  mov     rdi, rax
0x14000e155  jnz     short loc_14000E164
0x14000e157  mov     ecx, r14d
0x14000e15a  neg     ecx
0x14000e15c  sbb     ebp, ebp
0x14000e15e  and     ebp, [rsp+48h+arg_0]
0x14000e162  jmp     short loc_14000E168
0x14000e164  mov     ebp, [rsp+48h+arg_0]
0x14000e168  mov     dword ptr [rsp+48h+arg_8], ebx
0x14000e16c  mov     esi, ebx
0x14000e16e  test    ebp, ebp
0x14000e170  jz      short loc_14000E191
0x14000e172  mov     dword ptr [rsp+48h+arg_8], ebx
0x14000e176  test    bl, 2
0x14000e179  jnz     short loc_14000E191
0x14000e17b  and     esi, 0FFFFF63Eh
0x14000e181  mov     eax, edi
0x14000e183  and     eax, 9C1h
0x14000e188  or      esi, eax
0x14000e18a  or      esi, 2
0x14000e18d  mov     dword ptr [rsp+48h+arg_8], esi
0x14000e191  mov     edx, ebx
0x14000e193  and     edx, 4
0x14000e196  jnz     short loc_14000E1B1
0x14000e198  mov     eax, esi
0x14000e19a  mov     ecx, edi
0x14000e19c  and     ecx, 400h
0x14000e1a2  btr     eax, 0Ah
0x14000e1a6  mov     esi, ecx
0x14000e1a8  or      esi, eax
0x14000e1aa  or      esi, 4
0x14000e1ad  mov     dword ptr [rsp+48h+arg_8], esi
0x14000e1b1  mov     eax, ebx
0x14000e1b3  lock cmpxchg [r12], esi
0x14000e1b9  jz      short loc_14000E1BF
0x14000e1bb  mov     ebx, eax
0x14000e1bd  jmp     short loc_14000E168
0x14000e1bf  test    edx, edx
0x14000e1c1  jnz     short loc_14000E1DF
0x14000e1c3  mov     rax, cs:g_wil_details_subscribeFeatureStateCacheToConfigurationChanges
0x14000e1ca  test    rax, rax
0x14000e1cd  jz      short loc_14000E1DF
0x14000e1cf  movzx   edx, byte ptr [r15+1Ch]
0x14000e1d4  mov     r8d, r14d
0x14000e1d7  mov     rcx, r12
0x14000e1da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e1df  test    ebp, ebp
0x14000e1e1  jnz     short loc_14000E1F5
0x14000e1e3  and     esi, 0FFFFF63Eh
0x14000e1e9  and     edi, 9C1h
0x14000e1ef  or      esi, edi
0x14000e1f1  mov     dword ptr [rsp+48h+arg_8], esi
0x14000e1f5  mov     rax, [rsp+48h+arg_8]
0x14000e1fa  mov     rbx, [rsp+48h+arg_10]
0x14000e1ff  mov     rbp, [rsp+48h+arg_18]
0x14000e204  add     rsp, 20h
0x14000e208  pop     r15
0x14000e20a  pop     r14
0x14000e20c  pop     r12
0x14000e20e  pop     rdi
0x14000e20f  pop     rsi
0x14000e210  retn
```
