# wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState

- ea: `0x180032614`
- end: `0x180032888`
- name: `wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState`
- size: `628`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180032614`
- `0x1800328d4`

## callees

- `0x180009a78`
- `0x180032614`
- `0x180037010`

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
0x180032614  mov     rax, rsp
0x180032617  mov     [rax+8], rcx
0x18003261b  push    rbx
0x18003261c  push    rbp
0x18003261d  push    rsi
0x18003261e  push    rdi
0x18003261f  push    r12
0x180032621  push    r13
0x180032623  push    r14
0x180032625  push    r15
0x180032627  sub     rsp, 58h
0x18003262b  xor     edi, edi
0x18003262d  mov     [rsp+98h+arg_18], rdx
0x180032635  mov     [rax+10h], edi
0x180032638  mov     r13, r8
0x18003263b  mov     rax, cs:g_wil_details_ensureSubscribedToFeatureConfigurationChanges
0x180032642  mov     rbx, rdx
0x180032645  mov     [rsp+98h+arg_10], edi
0x18003264c  mov     r14, rcx
0x18003264f  test    rax, rax
0x180032652  jz      short loc_180032660
0x180032654  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032659  mov     [rsp+98h+arg_10], eax
0x180032660  mov     cl, [r13+1Ch]
0x180032664  mov     r8d, edi
0x180032667  mov     edx, [r13+18h]
0x18003266b  sub     cl, 2
0x18003266e  xorps   xmm0, xmm0
0x180032671  mov     ebp, 1
0x180032676  cmp     cl, bpl
0x180032679  lea     rcx, [rsp+98h+var_60]
0x18003267e  movups  [rsp+98h+var_60], xmm0
0x180032683  setbe   r8b
0x180032687  xor     eax, eax
0x180032689  mov     [rsp+98h+var_50], rax
0x18003268e  lea     rax, [rsp+98h+arg_8]
0x180032696  mov     [rsp+98h+var_70], rax
0x18003269b  mov     [rsp+98h+var_78], rdi
0x1800326a0  call    wil_QueryFeatureState
0x1800326a5  mov     ecx, dword ptr [rsp+98h+var_50]
0x1800326a9  lea     r15d, [rbp+3Fh]
0x1800326ad  neg     ecx
0x1800326af  mov     ecx, dword ptr [rsp+98h+var_50+4]
0x1800326b3  sbb     edx, edx
0x1800326b5  and     edx, 400h
0x1800326bb  neg     ecx
0x1800326bd  sbb     r8d, r8d
0x1800326c0  and     r8d, 800h
0x1800326c7  or      r8d, edx
0x1800326ca  neg     eax
0x1800326cc  sbb     eax, eax
0x1800326ce  and     eax, dword ptr [rsp+98h+var_60]
0x1800326d2  and     eax, 3
0x1800326d5  mov     edi, eax
0x1800326d7  shl     edi, 7
0x1800326da  or      edi, r8d
0x1800326dd  test    eax, eax
0x1800326df  jnz     short loc_1800326EE
0x1800326e1  mov     al, [r13+1Fh]
0x1800326e5  neg     al
0x1800326e7  sbb     ecx, ecx
0x1800326e9  and     ecx, r15d
0x1800326ec  jmp     short loc_1800326F9
0x1800326ee  xor     ecx, ecx
0x1800326f0  cmp     dword ptr [rsp+98h+var_60], 2
0x1800326f5  cmovz   ecx, r15d
0x1800326f9  or      edi, ecx
0x1800326fb  mov     ecx, 0C00h
0x180032700  mov     eax, edi
0x180032702  and     eax, ecx
0x180032704  cmp     eax, ecx
0x180032706  jnz     short loc_18003270D
0x180032708  mov     r12d, ebp
0x18003270b  jmp     short loc_180032719
0x18003270d  xor     r12d, r12d
0x180032710  test    r15b, dil
0x180032713  jz      loc_1800327AA
0x180032719  mov     r14, [r13+20h]
0x18003271d  mov     esi, ebp
0x18003271f  test    r14, r14
0x180032722  jz      short loc_180032793
0x180032724  mov     rcx, [r14]
0x180032727  test    rcx, rcx
0x18003272a  jz      short loc_180032793
0x18003272c  cmp     byte ptr [rcx+1Eh], 0
0x180032730  jnz     short loc_18003277F
0x180032732  cmp     byte ptr [rcx+1Dh], 0
0x180032736  jnz     short loc_18003277F
0x180032738  mov     r9, [rcx]
0x18003273b  mov     [rsp+98h+var_68], 0
0x180032744  mov     eax, [r9]
0x180032747  mov     dword ptr [rsp+98h+var_68], eax
0x18003274b  test    al, 2
0x18003274d  jz      short loc_180032756
0x18003274f  mov     rax, [rsp+98h+var_68]
0x180032754  jmp     short loc_180032766
0x180032756  mov     rdx, [rsp+98h+var_68]
0x18003275b  mov     r8, rcx
0x18003275e  mov     rcx, r9
0x180032761  call    wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState
0x180032766  test    esi, esi
0x180032768  jz      short loc_180032773
0x18003276a  test    bpl, al
0x18003276d  jz      short loc_180032773
0x18003276f  mov     esi, ebp
0x180032771  jmp     short loc_180032775
0x180032773  xor     esi, esi
0x180032775  add     r14, 8
0x180032779  test    esi, esi
0x18003277b  jnz     short loc_180032724
0x18003277d  jmp     short loc_180032793
0x18003277f  test    esi, esi
0x180032781  jz      short loc_180032791
0x180032783  cmp     byte ptr [rcx+1Fh], 0
0x180032787  jz      short loc_180032791
0x180032789  mov     esi, ebp
0x18003278b  add     r14, 8
0x18003278f  jmp     short loc_180032724
0x180032791  xor     esi, esi
0x180032793  mov     r14, [rsp+98h+arg_0]
0x18003279b  test    r12d, r12d
0x18003279e  jz      short loc_1800327AC
0x1800327a0  test    esi, esi
0x1800327a2  jnz     short loc_1800327AC
0x1800327a4  btr     edi, 0Ah
0x1800327a8  jmp     short loc_1800327AC
0x1800327aa  xor     esi, esi
0x1800327ac  test    r15b, dil
0x1800327af  jz      short loc_1800327B5
0x1800327b1  test    esi, esi
0x1800327b3  jnz     short loc_1800327B7
0x1800327b5  xor     ebp, ebp
0x1800327b7  mov     r8d, [rsp+98h+arg_10]
0x1800327bf  and     edi, 0FFFFFFFEh
0x1800327c2  or      edi, ebp
0x1800327c4  cmp     byte ptr [r13+1Ch], 0
0x1800327c9  jnz     short loc_1800327DB
0x1800327cb  mov     eax, r8d
0x1800327ce  neg     eax
0x1800327d0  sbb     ebp, ebp
0x1800327d2  and     ebp, [rsp+98h+arg_8]
0x1800327d9  jmp     short loc_1800327E2
0x1800327db  mov     ebp, [rsp+98h+arg_8]
0x1800327e2  mov     r15d, 9C1h
0x1800327e8  mov     dword ptr [rsp+98h+arg_18], ebx
0x1800327ef  mov     esi, ebx
0x1800327f1  test    ebp, ebp
0x1800327f3  jz      short loc_180032814
0x1800327f5  mov     dword ptr [rsp+98h+arg_18], ebx
0x1800327fc  test    bl, 2
0x1800327ff  jnz     short loc_180032814
0x180032801  mov     esi, edi
0x180032803  xor     esi, ebx
0x180032805  and     esi, r15d
0x180032808  xor     esi, ebx
0x18003280a  or      esi, 2
0x18003280d  mov     dword ptr [rsp+98h+arg_18], esi
0x180032814  mov     ecx, ebx
0x180032816  and     ecx, 4
0x180032819  jnz     short loc_180032833
0x18003281b  mov     eax, esi
0x18003281d  mov     esi, edi
0x18003281f  xor     esi, eax
0x180032821  and     esi, 400h
0x180032827  xor     esi, eax
0x180032829  or      esi, 4
0x18003282c  mov     dword ptr [rsp+98h+arg_18], esi
0x180032833  mov     eax, ebx
0x180032835  lock cmpxchg [r14], esi
0x18003283a  jz      short loc_180032840
0x18003283c  mov     ebx, eax
0x18003283e  jmp     short loc_1800327E8
0x180032840  test    ecx, ecx
0x180032842  jnz     short loc_18003285D
0x180032844  mov     rax, cs:g_wil_details_subscribeFeatureStateCacheToConfigurationChanges
0x18003284b  test    rax, rax
0x18003284e  jz      short loc_18003285D
0x180032850  movzx   edx, byte ptr [r13+1Ch]
0x180032855  mov     rcx, r14
0x180032858  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003285d  test    ebp, ebp
0x18003285f  jnz     short loc_18003286F
0x180032861  xor     edi, esi
0x180032863  and     edi, r15d
0x180032866  xor     edi, esi
0x180032868  mov     dword ptr [rsp+98h+arg_18], edi
0x18003286f  mov     rax, [rsp+98h+arg_18]
0x180032877  add     rsp, 58h
0x18003287b  pop     r15
0x18003287d  pop     r14
0x18003287f  pop     r13
0x180032881  pop     r12
0x180032883  pop     rdi
0x180032884  pop     rsi
0x180032885  pop     rbp
0x180032886  pop     rbx
0x180032887  retn
```
