# wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState

- ea: `0x180028cc4`
- end: `0x180028f38`
- name: `wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState`
- size: `628`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180028cc4`
- `0x180028f84`

## callees

- `0x18000aab8`
- `0x180028cc4`
- `0x18002b010`

## pseudocode

```c
__int64 __fastcall wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState(
        volatile signed __int32 *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  signed __int32 v5; // ebx
  volatile signed __int32 *v6; // r14
  unsigned int v7; // edx
  int v8; // ebp
  bool v9; // cf
  bool v10; // zf
  int v11; // eax
  int v12; // eax
  int v13; // ecx
  int v14; // edi
  int v15; // r12d
  unsigned int ***v16; // r14
  BOOL v17; // esi
  unsigned int **v18; // rcx
  char v19; // al
  unsigned int v20; // edi
  int v21; // ebp
  signed __int32 v22; // esi
  signed __int32 v23; // eax
  __int64 v25; // [rsp+30h] [rbp-68h]
  __int128 v26; // [rsp+38h] [rbp-60h] BYREF
  __int64 v27; // [rsp+48h] [rbp-50h]
  int v29; // [rsp+A8h] [rbp+10h] BYREF
  int v30; // [rsp+B0h] [rbp+18h]
  __int64 v31; // [rsp+B8h] [rbp+20h]

  v31 = a2;
  v29 = 0;
  v5 = a2;
  v30 = 0;
  v6 = a1;
  if ( g_wil_details_ensureSubscribedToFeatureConfigurationChanges )
    v30 = g_wil_details_ensureSubscribedToFeatureConfigurationChanges();
  v7 = *(_DWORD *)(a3 + 24);
  v8 = 1;
  v9 = *(_BYTE *)(a3 + 28) == 2;
  v10 = *(_BYTE *)(a3 + 28) == 3;
  v26 = 0;
  v27 = 0;
  v11 = wil_QueryFeatureState((__int64)&v26, v7, v9 | (unsigned __int8)v10, a4, 0, &v29);
  v12 = (unsigned __int8)v26 & (unsigned __int8)-(v11 != 0) & 3;
  if ( v12 )
  {
    v13 = 0;
    if ( (_DWORD)v26 == 2 )
      v13 = 64;
  }
  else
  {
    v13 = *(_BYTE *)(a3 + 31) != 0 ? 0x40 : 0;
  }
  v14 = v13 | ((_DWORD)v27 != 0 ? 0x400 : 0) | (HIDWORD(v27) != 0 ? 0x800 : 0) | (v12 << 7);
  if ( (v13 & 0xC00 | ((_DWORD)v27 != 0 ? 0x400 : 0) | (HIDWORD(v27) != 0 ? 0x800 : 0) | (v12 << 7) & 0xC00) == 0xC00 )
  {
    v15 = 1;
  }
  else
  {
    v15 = 0;
    if ( (v13 & 0x40) == 0 )
    {
      v17 = 0;
      goto LABEL_26;
    }
  }
  v16 = *(unsigned int ****)(a3 + 32);
  v17 = 1;
  if ( v16 )
  {
    while ( 1 )
    {
      v18 = *v16;
      if ( !*v16 )
        break;
      if ( *((_BYTE *)v18 + 30) || *((_BYTE *)v18 + 29) )
      {
        if ( !*((_BYTE *)v18 + 31) )
        {
          v17 = 0;
          break;
        }
        v17 = 1;
        ++v16;
      }
      else
      {
        v25 = **v18;
        if ( (v25 & 2) != 0 )
          v19 = **v18;
        else
          v19 = wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState(*v18, v25, v18);
        v17 = (v19 & 1) != 0;
        ++v16;
        if ( (v19 & 1) == 0 )
          break;
      }
    }
  }
  v6 = a1;
  if ( v15 && !v17 )
    v14 &= ~0x400u;
LABEL_26:
  if ( (v14 & 0x40) == 0 || !v17 )
    v8 = 0;
  v20 = v8 | v14 & 0xFFFFFFFE;
  if ( *(_BYTE *)(a3 + 28) )
    v21 = v29;
  else
    v21 = v30 != 0 ? v29 : 0;
  while ( 1 )
  {
    LODWORD(v31) = v5;
    v22 = v5;
    if ( v21 )
    {
      LODWORD(v31) = v5;
      if ( (v5 & 2) == 0 )
      {
        v22 = v5 ^ (v5 ^ v20) & 0x9C1 | 2;
        LODWORD(v31) = v22;
      }
    }
    if ( (v5 & 4) == 0 )
    {
      v22 = v22 ^ ((unsigned __int16)v22 ^ (unsigned __int16)v20) & 0x400 | 4;
      LODWORD(v31) = v22;
    }
    v23 = _InterlockedCompareExchange(v6, v22, v5);
    if ( v5 == v23 )
      break;
    v5 = v23;
  }
  if ( (v5 & 4) == 0 && g_wil_details_subscribeFeatureStateCacheToConfigurationChanges )
    g_wil_details_subscribeFeatureStateCacheToConfigurationChanges(v6, *(unsigned __int8 *)(a3 + 28));
  if ( !v21 )
    LODWORD(v31) = v22 ^ (v22 ^ v20) & 0x9C1;
  return v31;
}

```

## disassembly

```asm
0x180028cc4  mov     rax, rsp
0x180028cc7  mov     [rax+8], rcx
0x180028ccb  push    rbx
0x180028ccc  push    rbp
0x180028ccd  push    rsi
0x180028cce  push    rdi
0x180028ccf  push    r12
0x180028cd1  push    r13
0x180028cd3  push    r14
0x180028cd5  push    r15
0x180028cd7  sub     rsp, 58h
0x180028cdb  xor     edi, edi
0x180028cdd  mov     [rsp+98h+arg_18], rdx
0x180028ce5  mov     [rax+10h], edi
0x180028ce8  mov     r13, r8
0x180028ceb  mov     rax, cs:g_wil_details_ensureSubscribedToFeatureConfigurationChanges
0x180028cf2  mov     rbx, rdx
0x180028cf5  mov     [rsp+98h+arg_10], edi
0x180028cfc  mov     r14, rcx
0x180028cff  test    rax, rax
0x180028d02  jz      short loc_180028D10
0x180028d04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028d09  mov     [rsp+98h+arg_10], eax
0x180028d10  mov     cl, [r13+1Ch]
0x180028d14  mov     r8d, edi
0x180028d17  mov     edx, [r13+18h]
0x180028d1b  sub     cl, 2
0x180028d1e  xorps   xmm0, xmm0
0x180028d21  mov     ebp, 1
0x180028d26  cmp     cl, bpl
0x180028d29  lea     rcx, [rsp+98h+var_60]
0x180028d2e  movups  [rsp+98h+var_60], xmm0
0x180028d33  setbe   r8b
0x180028d37  xor     eax, eax
0x180028d39  mov     [rsp+98h+var_50], rax
0x180028d3e  lea     rax, [rsp+98h+arg_8]
0x180028d46  mov     [rsp+98h+var_70], rax
0x180028d4b  mov     [rsp+98h+var_78], rdi
0x180028d50  call    wil_QueryFeatureState
0x180028d55  mov     ecx, dword ptr [rsp+98h+var_50]
0x180028d59  lea     r15d, [rbp+3Fh]
0x180028d5d  neg     ecx
0x180028d5f  mov     ecx, dword ptr [rsp+98h+var_50+4]
0x180028d63  sbb     edx, edx
0x180028d65  and     edx, 400h
0x180028d6b  neg     ecx
0x180028d6d  sbb     r8d, r8d
0x180028d70  and     r8d, 800h
0x180028d77  or      r8d, edx
0x180028d7a  neg     eax
0x180028d7c  sbb     eax, eax
0x180028d7e  and     eax, dword ptr [rsp+98h+var_60]
0x180028d82  and     eax, 3
0x180028d85  mov     edi, eax
0x180028d87  shl     edi, 7
0x180028d8a  or      edi, r8d
0x180028d8d  test    eax, eax
0x180028d8f  jnz     short loc_180028D9E
0x180028d91  mov     al, [r13+1Fh]
0x180028d95  neg     al
0x180028d97  sbb     ecx, ecx
0x180028d99  and     ecx, r15d
0x180028d9c  jmp     short loc_180028DA9
0x180028d9e  xor     ecx, ecx
0x180028da0  cmp     dword ptr [rsp+98h+var_60], 2
0x180028da5  cmovz   ecx, r15d
0x180028da9  or      edi, ecx
0x180028dab  mov     ecx, 0C00h
0x180028db0  mov     eax, edi
0x180028db2  and     eax, ecx
0x180028db4  cmp     eax, ecx
0x180028db6  jnz     short loc_180028DBD
0x180028db8  mov     r12d, ebp
0x180028dbb  jmp     short loc_180028DC9
0x180028dbd  xor     r12d, r12d
0x180028dc0  test    r15b, dil
0x180028dc3  jz      loc_180028E5A
0x180028dc9  mov     r14, [r13+20h]
0x180028dcd  mov     esi, ebp
0x180028dcf  test    r14, r14
0x180028dd2  jz      short loc_180028E43
0x180028dd4  mov     rcx, [r14]
0x180028dd7  test    rcx, rcx
0x180028dda  jz      short loc_180028E43
0x180028ddc  cmp     byte ptr [rcx+1Eh], 0
0x180028de0  jnz     short loc_180028E2F
0x180028de2  cmp     byte ptr [rcx+1Dh], 0
0x180028de6  jnz     short loc_180028E2F
0x180028de8  mov     r9, [rcx]
0x180028deb  mov     [rsp+98h+var_68], 0
0x180028df4  mov     eax, [r9]
0x180028df7  mov     dword ptr [rsp+98h+var_68], eax
0x180028dfb  test    al, 2
0x180028dfd  jz      short loc_180028E06
0x180028dff  mov     rax, [rsp+98h+var_68]
0x180028e04  jmp     short loc_180028E16
0x180028e06  mov     rdx, [rsp+98h+var_68]
0x180028e0b  mov     r8, rcx
0x180028e0e  mov     rcx, r9
0x180028e11  call    wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState
0x180028e16  test    esi, esi
0x180028e18  jz      short loc_180028E23
0x180028e1a  test    bpl, al
0x180028e1d  jz      short loc_180028E23
0x180028e1f  mov     esi, ebp
0x180028e21  jmp     short loc_180028E25
0x180028e23  xor     esi, esi
0x180028e25  add     r14, 8
0x180028e29  test    esi, esi
0x180028e2b  jnz     short loc_180028DD4
0x180028e2d  jmp     short loc_180028E43
0x180028e2f  test    esi, esi
0x180028e31  jz      short loc_180028E41
0x180028e33  cmp     byte ptr [rcx+1Fh], 0
0x180028e37  jz      short loc_180028E41
0x180028e39  mov     esi, ebp
0x180028e3b  add     r14, 8
0x180028e3f  jmp     short loc_180028DD4
0x180028e41  xor     esi, esi
0x180028e43  mov     r14, [rsp+98h+arg_0]
0x180028e4b  test    r12d, r12d
0x180028e4e  jz      short loc_180028E5C
0x180028e50  test    esi, esi
0x180028e52  jnz     short loc_180028E5C
0x180028e54  btr     edi, 0Ah
0x180028e58  jmp     short loc_180028E5C
0x180028e5a  xor     esi, esi
0x180028e5c  test    r15b, dil
0x180028e5f  jz      short loc_180028E65
0x180028e61  test    esi, esi
0x180028e63  jnz     short loc_180028E67
0x180028e65  xor     ebp, ebp
0x180028e67  mov     r8d, [rsp+98h+arg_10]
0x180028e6f  and     edi, 0FFFFFFFEh
0x180028e72  or      edi, ebp
0x180028e74  cmp     byte ptr [r13+1Ch], 0
0x180028e79  jnz     short loc_180028E8B
0x180028e7b  mov     eax, r8d
0x180028e7e  neg     eax
0x180028e80  sbb     ebp, ebp
0x180028e82  and     ebp, [rsp+98h+arg_8]
0x180028e89  jmp     short loc_180028E92
0x180028e8b  mov     ebp, [rsp+98h+arg_8]
0x180028e92  mov     r15d, 9C1h
0x180028e98  mov     dword ptr [rsp+98h+arg_18], ebx
0x180028e9f  mov     esi, ebx
0x180028ea1  test    ebp, ebp
0x180028ea3  jz      short loc_180028EC4
0x180028ea5  mov     dword ptr [rsp+98h+arg_18], ebx
0x180028eac  test    bl, 2
0x180028eaf  jnz     short loc_180028EC4
0x180028eb1  mov     esi, edi
0x180028eb3  xor     esi, ebx
0x180028eb5  and     esi, r15d
0x180028eb8  xor     esi, ebx
0x180028eba  or      esi, 2
0x180028ebd  mov     dword ptr [rsp+98h+arg_18], esi
0x180028ec4  mov     ecx, ebx
0x180028ec6  and     ecx, 4
0x180028ec9  jnz     short loc_180028EE3
0x180028ecb  mov     eax, esi
0x180028ecd  mov     esi, edi
0x180028ecf  xor     esi, eax
0x180028ed1  and     esi, 400h
0x180028ed7  xor     esi, eax
0x180028ed9  or      esi, 4
0x180028edc  mov     dword ptr [rsp+98h+arg_18], esi
0x180028ee3  mov     eax, ebx
0x180028ee5  lock cmpxchg [r14], esi
0x180028eea  jz      short loc_180028EF0
0x180028eec  mov     ebx, eax
0x180028eee  jmp     short loc_180028E98
0x180028ef0  test    ecx, ecx
0x180028ef2  jnz     short loc_180028F0D
0x180028ef4  mov     rax, cs:g_wil_details_subscribeFeatureStateCacheToConfigurationChanges
0x180028efb  test    rax, rax
0x180028efe  jz      short loc_180028F0D
0x180028f00  movzx   edx, byte ptr [r13+1Ch]
0x180028f05  mov     rcx, r14
0x180028f08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028f0d  test    ebp, ebp
0x180028f0f  jnz     short loc_180028F1F
0x180028f11  xor     edi, esi
0x180028f13  and     edi, r15d
0x180028f16  xor     edi, esi
0x180028f18  mov     dword ptr [rsp+98h+arg_18], edi
0x180028f1f  mov     rax, [rsp+98h+arg_18]
0x180028f27  add     rsp, 58h
0x180028f2b  pop     r15
0x180028f2d  pop     r14
0x180028f2f  pop     r13
0x180028f31  pop     r12
0x180028f33  pop     rdi
0x180028f34  pop     rsi
0x180028f35  pop     rbp
0x180028f36  pop     rbx
0x180028f37  retn
```
