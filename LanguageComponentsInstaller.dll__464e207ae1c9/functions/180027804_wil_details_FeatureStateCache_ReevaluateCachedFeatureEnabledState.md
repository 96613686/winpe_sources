# wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState

- ea: `0x180027804`
- end: `0x180027a78`
- name: `wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState`
- size: `628`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180027804`
- `0x180027ad4`

## callees

- `0x1800236a8`
- `0x180027804`
- `0x18002a010`

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
0x180027804  mov     rax, rsp
0x180027807  mov     [rax+8], rcx
0x18002780b  push    rbx
0x18002780c  push    rbp
0x18002780d  push    rsi
0x18002780e  push    rdi
0x18002780f  push    r12
0x180027811  push    r13
0x180027813  push    r14
0x180027815  push    r15
0x180027817  sub     rsp, 58h
0x18002781b  xor     edi, edi
0x18002781d  mov     [rsp+98h+arg_18], rdx
0x180027825  mov     [rax+10h], edi
0x180027828  mov     r13, r8
0x18002782b  mov     rax, cs:g_wil_details_ensureSubscribedToFeatureConfigurationChanges
0x180027832  mov     rbx, rdx
0x180027835  mov     [rsp+98h+arg_10], edi
0x18002783c  mov     r14, rcx
0x18002783f  test    rax, rax
0x180027842  jz      short loc_180027850
0x180027844  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027849  mov     [rsp+98h+arg_10], eax
0x180027850  mov     cl, [r13+1Ch]
0x180027854  mov     r8d, edi
0x180027857  mov     edx, [r13+18h]
0x18002785b  sub     cl, 2
0x18002785e  xorps   xmm0, xmm0
0x180027861  mov     ebp, 1
0x180027866  cmp     cl, bpl
0x180027869  lea     rcx, [rsp+98h+var_60]
0x18002786e  movups  [rsp+98h+var_60], xmm0
0x180027873  setbe   r8b
0x180027877  xor     eax, eax
0x180027879  mov     [rsp+98h+var_50], rax
0x18002787e  lea     rax, [rsp+98h+arg_8]
0x180027886  mov     [rsp+98h+var_70], rax
0x18002788b  mov     [rsp+98h+var_78], rdi
0x180027890  call    wil_QueryFeatureState
0x180027895  mov     ecx, dword ptr [rsp+98h+var_50]
0x180027899  lea     r15d, [rbp+3Fh]
0x18002789d  neg     ecx
0x18002789f  mov     ecx, dword ptr [rsp+98h+var_50+4]
0x1800278a3  sbb     edx, edx
0x1800278a5  and     edx, 400h
0x1800278ab  neg     ecx
0x1800278ad  sbb     r8d, r8d
0x1800278b0  and     r8d, 800h
0x1800278b7  or      r8d, edx
0x1800278ba  neg     eax
0x1800278bc  sbb     eax, eax
0x1800278be  and     eax, dword ptr [rsp+98h+var_60]
0x1800278c2  and     eax, 3
0x1800278c5  mov     edi, eax
0x1800278c7  shl     edi, 7
0x1800278ca  or      edi, r8d
0x1800278cd  test    eax, eax
0x1800278cf  jnz     short loc_1800278DE
0x1800278d1  mov     al, [r13+1Fh]
0x1800278d5  neg     al
0x1800278d7  sbb     ecx, ecx
0x1800278d9  and     ecx, r15d
0x1800278dc  jmp     short loc_1800278E9
0x1800278de  xor     ecx, ecx
0x1800278e0  cmp     dword ptr [rsp+98h+var_60], 2
0x1800278e5  cmovz   ecx, r15d
0x1800278e9  or      edi, ecx
0x1800278eb  mov     ecx, 0C00h
0x1800278f0  mov     eax, edi
0x1800278f2  and     eax, ecx
0x1800278f4  cmp     eax, ecx
0x1800278f6  jnz     short loc_1800278FD
0x1800278f8  mov     r12d, ebp
0x1800278fb  jmp     short loc_180027909
0x1800278fd  xor     r12d, r12d
0x180027900  test    r15b, dil
0x180027903  jz      loc_18002799A
0x180027909  mov     r14, [r13+20h]
0x18002790d  mov     esi, ebp
0x18002790f  test    r14, r14
0x180027912  jz      short loc_180027983
0x180027914  mov     rcx, [r14]
0x180027917  test    rcx, rcx
0x18002791a  jz      short loc_180027983
0x18002791c  cmp     byte ptr [rcx+1Eh], 0
0x180027920  jnz     short loc_18002796F
0x180027922  cmp     byte ptr [rcx+1Dh], 0
0x180027926  jnz     short loc_18002796F
0x180027928  mov     r9, [rcx]
0x18002792b  mov     [rsp+98h+var_68], 0
0x180027934  mov     eax, [r9]
0x180027937  mov     dword ptr [rsp+98h+var_68], eax
0x18002793b  test    al, 2
0x18002793d  jz      short loc_180027946
0x18002793f  mov     rax, [rsp+98h+var_68]
0x180027944  jmp     short loc_180027956
0x180027946  mov     rdx, [rsp+98h+var_68]
0x18002794b  mov     r8, rcx
0x18002794e  mov     rcx, r9
0x180027951  call    wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState
0x180027956  test    esi, esi
0x180027958  jz      short loc_180027963
0x18002795a  test    bpl, al
0x18002795d  jz      short loc_180027963
0x18002795f  mov     esi, ebp
0x180027961  jmp     short loc_180027965
0x180027963  xor     esi, esi
0x180027965  add     r14, 8
0x180027969  test    esi, esi
0x18002796b  jnz     short loc_180027914
0x18002796d  jmp     short loc_180027983
0x18002796f  test    esi, esi
0x180027971  jz      short loc_180027981
0x180027973  cmp     byte ptr [rcx+1Fh], 0
0x180027977  jz      short loc_180027981
0x180027979  mov     esi, ebp
0x18002797b  add     r14, 8
0x18002797f  jmp     short loc_180027914
0x180027981  xor     esi, esi
0x180027983  mov     r14, [rsp+98h+arg_0]
0x18002798b  test    r12d, r12d
0x18002798e  jz      short loc_18002799C
0x180027990  test    esi, esi
0x180027992  jnz     short loc_18002799C
0x180027994  btr     edi, 0Ah
0x180027998  jmp     short loc_18002799C
0x18002799a  xor     esi, esi
0x18002799c  test    r15b, dil
0x18002799f  jz      short loc_1800279A5
0x1800279a1  test    esi, esi
0x1800279a3  jnz     short loc_1800279A7
0x1800279a5  xor     ebp, ebp
0x1800279a7  mov     r8d, [rsp+98h+arg_10]
0x1800279af  and     edi, 0FFFFFFFEh
0x1800279b2  or      edi, ebp
0x1800279b4  cmp     byte ptr [r13+1Ch], 0
0x1800279b9  jnz     short loc_1800279CB
0x1800279bb  mov     eax, r8d
0x1800279be  neg     eax
0x1800279c0  sbb     ebp, ebp
0x1800279c2  and     ebp, [rsp+98h+arg_8]
0x1800279c9  jmp     short loc_1800279D2
0x1800279cb  mov     ebp, [rsp+98h+arg_8]
0x1800279d2  mov     r15d, 9C1h
0x1800279d8  mov     dword ptr [rsp+98h+arg_18], ebx
0x1800279df  mov     esi, ebx
0x1800279e1  test    ebp, ebp
0x1800279e3  jz      short loc_180027A04
0x1800279e5  mov     dword ptr [rsp+98h+arg_18], ebx
0x1800279ec  test    bl, 2
0x1800279ef  jnz     short loc_180027A04
0x1800279f1  mov     esi, edi
0x1800279f3  xor     esi, ebx
0x1800279f5  and     esi, r15d
0x1800279f8  xor     esi, ebx
0x1800279fa  or      esi, 2
0x1800279fd  mov     dword ptr [rsp+98h+arg_18], esi
0x180027a04  mov     ecx, ebx
0x180027a06  and     ecx, 4
0x180027a09  jnz     short loc_180027A23
0x180027a0b  mov     eax, esi
0x180027a0d  mov     esi, edi
0x180027a0f  xor     esi, eax
0x180027a11  and     esi, 400h
0x180027a17  xor     esi, eax
0x180027a19  or      esi, 4
0x180027a1c  mov     dword ptr [rsp+98h+arg_18], esi
0x180027a23  mov     eax, ebx
0x180027a25  lock cmpxchg [r14], esi
0x180027a2a  jz      short loc_180027A30
0x180027a2c  mov     ebx, eax
0x180027a2e  jmp     short loc_1800279D8
0x180027a30  test    ecx, ecx
0x180027a32  jnz     short loc_180027A4D
0x180027a34  mov     rax, cs:g_wil_details_subscribeFeatureStateCacheToConfigurationChanges
0x180027a3b  test    rax, rax
0x180027a3e  jz      short loc_180027A4D
0x180027a40  movzx   edx, byte ptr [r13+1Ch]
0x180027a45  mov     rcx, r14
0x180027a48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027a4d  test    ebp, ebp
0x180027a4f  jnz     short loc_180027A5F
0x180027a51  xor     edi, esi
0x180027a53  and     edi, r15d
0x180027a56  xor     edi, esi
0x180027a58  mov     dword ptr [rsp+98h+arg_18], edi
0x180027a5f  mov     rax, [rsp+98h+arg_18]
0x180027a67  add     rsp, 58h
0x180027a6b  pop     r15
0x180027a6d  pop     r14
0x180027a6f  pop     r13
0x180027a71  pop     r12
0x180027a73  pop     rdi
0x180027a74  pop     rsi
0x180027a75  pop     rbp
0x180027a76  pop     rbx
0x180027a77  retn
```
