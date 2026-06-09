# wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState

- ea: `0x1800033b4`
- end: `0x180003628`
- name: `wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState`
- size: `628`
- prototype: `__int64 __fastcall(volatile signed __int32 *, __int64, __int64, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800033b4`
- `0x180003674`

## callees

- `0x180002d84`
- `0x1800033b4`
- `0x180019010`

## pseudocode

```c
__int64 __fastcall wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState(
        volatile signed __int32 *a1,
        __int64 a2,
        __int64 a3,
        int a4)
{
  signed __int32 v5; // ebx
  volatile signed __int32 *v6; // r14
  int v7; // edx
  int v8; // ebp
  bool v9; // cf
  bool v10; // zf
  int FeatureState; // eax
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
  FeatureState = wil_QueryFeatureState((unsigned int)&v26, v7, v9 | (unsigned __int8)v10, a4, 0, (__int64)&v29);
  v12 = (unsigned __int8)v26 & (unsigned __int8)-(FeatureState != 0) & 3;
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
0x1800033b4  mov     rax, rsp
0x1800033b7  mov     [rax+8], rcx
0x1800033bb  push    rbx
0x1800033bc  push    rbp
0x1800033bd  push    rsi
0x1800033be  push    rdi
0x1800033bf  push    r12
0x1800033c1  push    r13
0x1800033c3  push    r14
0x1800033c5  push    r15
0x1800033c7  sub     rsp, 58h
0x1800033cb  xor     edi, edi
0x1800033cd  mov     [rsp+98h+arg_18], rdx
0x1800033d5  mov     [rax+10h], edi
0x1800033d8  mov     r13, r8
0x1800033db  mov     rax, cs:g_wil_details_ensureSubscribedToFeatureConfigurationChanges
0x1800033e2  mov     rbx, rdx
0x1800033e5  mov     [rsp+98h+arg_10], edi
0x1800033ec  mov     r14, rcx
0x1800033ef  test    rax, rax
0x1800033f2  jz      short loc_180003400
0x1800033f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033f9  mov     [rsp+98h+arg_10], eax
0x180003400  mov     cl, [r13+1Ch]
0x180003404  mov     r8d, edi
0x180003407  mov     edx, [r13+18h]
0x18000340b  sub     cl, 2
0x18000340e  xorps   xmm0, xmm0
0x180003411  mov     ebp, 1
0x180003416  cmp     cl, bpl
0x180003419  lea     rcx, [rsp+98h+var_60]
0x18000341e  movups  [rsp+98h+var_60], xmm0
0x180003423  setbe   r8b
0x180003427  xor     eax, eax
0x180003429  mov     [rsp+98h+var_50], rax
0x18000342e  lea     rax, [rsp+98h+arg_8]
0x180003436  mov     [rsp+98h+var_70], rax
0x18000343b  mov     [rsp+98h+var_78], rdi
0x180003440  call    wil_QueryFeatureState
0x180003445  mov     ecx, dword ptr [rsp+98h+var_50]
0x180003449  lea     r15d, [rbp+3Fh]
0x18000344d  neg     ecx
0x18000344f  mov     ecx, dword ptr [rsp+98h+var_50+4]
0x180003453  sbb     edx, edx
0x180003455  and     edx, 400h
0x18000345b  neg     ecx
0x18000345d  sbb     r8d, r8d
0x180003460  and     r8d, 800h
0x180003467  or      r8d, edx
0x18000346a  neg     eax
0x18000346c  sbb     eax, eax
0x18000346e  and     eax, dword ptr [rsp+98h+var_60]
0x180003472  and     eax, 3
0x180003475  mov     edi, eax
0x180003477  shl     edi, 7
0x18000347a  or      edi, r8d
0x18000347d  test    eax, eax
0x18000347f  jnz     short loc_18000348E
0x180003481  mov     al, [r13+1Fh]
0x180003485  neg     al
0x180003487  sbb     ecx, ecx
0x180003489  and     ecx, r15d
0x18000348c  jmp     short loc_180003499
0x18000348e  xor     ecx, ecx
0x180003490  cmp     dword ptr [rsp+98h+var_60], 2
0x180003495  cmovz   ecx, r15d
0x180003499  or      edi, ecx
0x18000349b  mov     ecx, 0C00h
0x1800034a0  mov     eax, edi
0x1800034a2  and     eax, ecx
0x1800034a4  cmp     eax, ecx
0x1800034a6  jnz     short loc_1800034AD
0x1800034a8  mov     r12d, ebp
0x1800034ab  jmp     short loc_1800034B9
0x1800034ad  xor     r12d, r12d
0x1800034b0  test    r15b, dil
0x1800034b3  jz      loc_18000354A
0x1800034b9  mov     r14, [r13+20h]
0x1800034bd  mov     esi, ebp
0x1800034bf  test    r14, r14
0x1800034c2  jz      short loc_180003533
0x1800034c4  mov     rcx, [r14]
0x1800034c7  test    rcx, rcx
0x1800034ca  jz      short loc_180003533
0x1800034cc  cmp     byte ptr [rcx+1Eh], 0
0x1800034d0  jnz     short loc_18000351F
0x1800034d2  cmp     byte ptr [rcx+1Dh], 0
0x1800034d6  jnz     short loc_18000351F
0x1800034d8  mov     r9, [rcx]
0x1800034db  mov     [rsp+98h+var_68], 0
0x1800034e4  mov     eax, [r9]
0x1800034e7  mov     dword ptr [rsp+98h+var_68], eax
0x1800034eb  test    al, 2
0x1800034ed  jz      short loc_1800034F6
0x1800034ef  mov     rax, [rsp+98h+var_68]
0x1800034f4  jmp     short loc_180003506
0x1800034f6  mov     rdx, [rsp+98h+var_68]
0x1800034fb  mov     r8, rcx
0x1800034fe  mov     rcx, r9
0x180003501  call    wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState
0x180003506  test    esi, esi
0x180003508  jz      short loc_180003513
0x18000350a  test    bpl, al
0x18000350d  jz      short loc_180003513
0x18000350f  mov     esi, ebp
0x180003511  jmp     short loc_180003515
0x180003513  xor     esi, esi
0x180003515  add     r14, 8
0x180003519  test    esi, esi
0x18000351b  jnz     short loc_1800034C4
0x18000351d  jmp     short loc_180003533
0x18000351f  test    esi, esi
0x180003521  jz      short loc_180003531
0x180003523  cmp     byte ptr [rcx+1Fh], 0
0x180003527  jz      short loc_180003531
0x180003529  mov     esi, ebp
0x18000352b  add     r14, 8
0x18000352f  jmp     short loc_1800034C4
0x180003531  xor     esi, esi
0x180003533  mov     r14, [rsp+98h+arg_0]
0x18000353b  test    r12d, r12d
0x18000353e  jz      short loc_18000354C
0x180003540  test    esi, esi
0x180003542  jnz     short loc_18000354C
0x180003544  btr     edi, 0Ah
0x180003548  jmp     short loc_18000354C
0x18000354a  xor     esi, esi
0x18000354c  test    r15b, dil
0x18000354f  jz      short loc_180003555
0x180003551  test    esi, esi
0x180003553  jnz     short loc_180003557
0x180003555  xor     ebp, ebp
0x180003557  mov     r8d, [rsp+98h+arg_10]
0x18000355f  and     edi, 0FFFFFFFEh
0x180003562  or      edi, ebp
0x180003564  cmp     byte ptr [r13+1Ch], 0
0x180003569  jnz     short loc_18000357B
0x18000356b  mov     eax, r8d
0x18000356e  neg     eax
0x180003570  sbb     ebp, ebp
0x180003572  and     ebp, [rsp+98h+arg_8]
0x180003579  jmp     short loc_180003582
0x18000357b  mov     ebp, [rsp+98h+arg_8]
0x180003582  mov     r15d, 9C1h
0x180003588  mov     dword ptr [rsp+98h+arg_18], ebx
0x18000358f  mov     esi, ebx
0x180003591  test    ebp, ebp
0x180003593  jz      short loc_1800035B4
0x180003595  mov     dword ptr [rsp+98h+arg_18], ebx
0x18000359c  test    bl, 2
0x18000359f  jnz     short loc_1800035B4
0x1800035a1  mov     esi, edi
0x1800035a3  xor     esi, ebx
0x1800035a5  and     esi, r15d
0x1800035a8  xor     esi, ebx
0x1800035aa  or      esi, 2
0x1800035ad  mov     dword ptr [rsp+98h+arg_18], esi
0x1800035b4  mov     ecx, ebx
0x1800035b6  and     ecx, 4
0x1800035b9  jnz     short loc_1800035D3
0x1800035bb  mov     eax, esi
0x1800035bd  mov     esi, edi
0x1800035bf  xor     esi, eax
0x1800035c1  and     esi, 400h
0x1800035c7  xor     esi, eax
0x1800035c9  or      esi, 4
0x1800035cc  mov     dword ptr [rsp+98h+arg_18], esi
0x1800035d3  mov     eax, ebx
0x1800035d5  lock cmpxchg [r14], esi
0x1800035da  jz      short loc_1800035E0
0x1800035dc  mov     ebx, eax
0x1800035de  jmp     short loc_180003588
0x1800035e0  test    ecx, ecx
0x1800035e2  jnz     short loc_1800035FD
0x1800035e4  mov     rax, cs:g_wil_details_subscribeFeatureStateCacheToConfigurationChanges
0x1800035eb  test    rax, rax
0x1800035ee  jz      short loc_1800035FD
0x1800035f0  movzx   edx, byte ptr [r13+1Ch]
0x1800035f5  mov     rcx, r14
0x1800035f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035fd  test    ebp, ebp
0x1800035ff  jnz     short loc_18000360F
0x180003601  xor     edi, esi
0x180003603  and     edi, r15d
0x180003606  xor     edi, esi
0x180003608  mov     dword ptr [rsp+98h+arg_18], edi
0x18000360f  mov     rax, [rsp+98h+arg_18]
0x180003617  add     rsp, 58h
0x18000361b  pop     r15
0x18000361d  pop     r14
0x18000361f  pop     r13
0x180003621  pop     r12
0x180003623  pop     rdi
0x180003624  pop     rsi
0x180003625  pop     rbp
0x180003626  pop     rbx
0x180003627  retn
```
