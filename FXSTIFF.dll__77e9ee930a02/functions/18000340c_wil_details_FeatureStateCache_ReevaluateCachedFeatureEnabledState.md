# wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState

- ea: `0x18000340c`
- end: `0x18000365e`
- name: `wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState`
- size: `594`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000340c`
- `0x1800036a8`

## callees

- `0x180002dac`
- `0x18000340c`
- `0x180019010`

## pseudocode

```c
__int64 __fastcall wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState(
        volatile signed __int32 *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  unsigned int v4; // r15d
  signed __int32 v6; // ebx
  unsigned int v8; // edx
  unsigned __int8 v9; // cl
  int v10; // eax
  int v11; // eax
  int v12; // ecx
  unsigned int v13; // edx
  int v14; // esi
  __int64 *v15; // rdi
  __int64 v16; // rcx
  _DWORD *v17; // r9
  unsigned __int8 v18; // al
  BOOL v19; // ecx
  unsigned int v20; // eax
  unsigned int v21; // esi
  int v22; // ebp
  signed __int32 v23; // edi
  signed __int32 v24; // eax
  __int128 v26; // [rsp+30h] [rbp-58h] BYREF
  __int64 v27; // [rsp+40h] [rbp-48h]
  int v28; // [rsp+90h] [rbp+8h] BYREF
  __int64 v29; // [rsp+98h] [rbp+10h]
  __int64 v30; // [rsp+A0h] [rbp+18h]

  v4 = 0;
  v29 = a2;
  v28 = 0;
  v6 = a2;
  if ( g_wil_details_ensureSubscribedToFeatureConfigurationChanges )
    v4 = g_wil_details_ensureSubscribedToFeatureConfigurationChanges();
  v8 = *(_DWORD *)(a3 + 24);
  v9 = *(_BYTE *)(a3 + 28) - 2;
  v26 = 0;
  v27 = 0;
  v10 = wil_QueryFeatureState((__int64)&v26, v8, v9 <= 1u, a4, 0, &v28);
  v11 = (unsigned __int8)v26 & (unsigned __int8)-(v10 != 0) & 3;
  if ( v11 )
  {
    v12 = 0;
    if ( (_DWORD)v26 == 2 )
      v12 = 64;
  }
  else
  {
    v12 = *(_BYTE *)(a3 + 31) != 0 ? 0x40 : 0;
  }
  v13 = v12 | ((_DWORD)v27 != 0 ? 0x400 : 0) | (HIDWORD(v27) != 0 ? 0x800 : 0) | (v11 << 7);
  v14 = v13 | (v13 >> 6) & 1;
  if ( ((v13 >> 6) & 1) != 0 )
  {
    v15 = *(__int64 **)(a3 + 32);
    if ( v15 )
    {
      while ( (v14 & 1) != 0 )
      {
        v16 = *v15;
        if ( !*v15 )
          break;
        if ( *(_BYTE *)(v16 + 30) || *(_BYTE *)(v16 + 29) )
        {
          v20 = (v14 & 1) != 0 && *(_BYTE *)(v16 + 31);
          v21 = v14 & 0xFFFFFFFE;
        }
        else
        {
          v17 = *(_DWORD **)v16;
          v30 = 0;
          LODWORD(v30) = *v17;
          if ( (v30 & 2) != 0 )
            v18 = v30;
          else
            v18 = wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState(v17, v30, v16);
          v19 = (v18 & (unsigned __int8)v14 & 1) != 0;
          v20 = v14 & 0xFFFFFFFE;
          v21 = v19;
        }
        v14 = v20 | v21;
        ++v15;
      }
    }
  }
  if ( *(_BYTE *)(a3 + 28) )
    v22 = v28;
  else
    v22 = v4 != 0 ? v28 : 0;
  while ( 1 )
  {
    LODWORD(v29) = v6;
    v23 = v6;
    if ( v22 )
    {
      LODWORD(v29) = v6;
      if ( (v6 & 2) == 0 )
      {
        v23 = v6 ^ ((unsigned __int16)v6 ^ (unsigned __int16)v14) & 0x9C1 | 2;
        LODWORD(v29) = v23;
      }
    }
    if ( (v6 & 4) == 0 )
    {
      v23 = v23 ^ ((unsigned __int16)v23 ^ (unsigned __int16)v14) & 0x400 | 4;
      LODWORD(v29) = v23;
    }
    v24 = _InterlockedCompareExchange(a1, v23, v6);
    if ( v6 == v24 )
      break;
    v6 = v24;
  }
  if ( (v6 & 4) == 0 && g_wil_details_subscribeFeatureStateCacheToConfigurationChanges )
    g_wil_details_subscribeFeatureStateCacheToConfigurationChanges(a1, *(unsigned __int8 *)(a3 + 28), v4);
  if ( !v22 )
    LODWORD(v29) = v23 ^ ((unsigned __int16)v23 ^ (unsigned __int16)v14) & 0x9C1;
  return v29;
}

```

## disassembly

```asm
0x18000340c  mov     rax, rsp
0x18000340f  push    rbx
0x180003410  push    rbp
0x180003411  push    rsi
0x180003412  push    rdi
0x180003413  push    r12
0x180003415  push    r14
0x180003417  push    r15
0x180003419  sub     rsp, 50h
0x18000341d  xor     r15d, r15d
0x180003420  mov     [rsp+88h+arg_8], rdx
0x180003428  mov     [rax+8], r15d
0x18000342c  mov     r14, r8
0x18000342f  mov     rax, cs:g_wil_details_ensureSubscribedToFeatureConfigurationChanges
0x180003436  mov     rbx, rdx
0x180003439  mov     r12, rcx
0x18000343c  test    rax, rax
0x18000343f  jz      short loc_180003449
0x180003441  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003446  mov     r15d, eax
0x180003449  mov     cl, [r14+1Ch]
0x18000344d  xor     r8d, r8d
0x180003450  mov     edx, [r14+18h]
0x180003454  sub     cl, 2
0x180003457  xorps   xmm0, xmm0
0x18000345a  movups  [rsp+88h+var_58], xmm0
0x18000345f  lea     ebp, [r8+1]
0x180003463  cmp     cl, bpl
0x180003466  lea     rcx, [rsp+88h+var_58]
0x18000346b  setbe   r8b
0x18000346f  xor     eax, eax
0x180003471  mov     [rsp+88h+var_48], rax
0x180003476  lea     rax, [rsp+88h+arg_0]
0x18000347e  mov     [rsp+88h+var_60], rax
0x180003483  mov     [rsp+88h+var_68], 0
0x18000348c  call    wil_QueryFeatureState
0x180003491  mov     ecx, dword ptr [rsp+88h+var_48]
0x180003495  neg     ecx
0x180003497  mov     ecx, dword ptr [rsp+88h+var_48+4]
0x18000349b  sbb     edx, edx
0x18000349d  and     edx, 400h
0x1800034a3  neg     ecx
0x1800034a5  sbb     r8d, r8d
0x1800034a8  and     r8d, 800h
0x1800034af  or      r8d, edx
0x1800034b2  neg     eax
0x1800034b4  sbb     eax, eax
0x1800034b6  and     eax, dword ptr [rsp+88h+var_58]
0x1800034ba  and     eax, 3
0x1800034bd  mov     edx, eax
0x1800034bf  shl     edx, 7
0x1800034c2  or      edx, r8d
0x1800034c5  test    eax, eax
0x1800034c7  jnz     short loc_1800034D6
0x1800034c9  mov     al, [r14+1Fh]
0x1800034cd  neg     al
0x1800034cf  sbb     ecx, ecx
0x1800034d1  and     ecx, 40h
0x1800034d4  jmp     short loc_1800034E3
0x1800034d6  xor     ecx, ecx
0x1800034d8  cmp     dword ptr [rsp+88h+var_58], 2
0x1800034dd  lea     eax, [rcx+40h]
0x1800034e0  cmovz   ecx, eax
0x1800034e3  or      edx, ecx
0x1800034e5  mov     eax, edx
0x1800034e7  shr     eax, 6
0x1800034ea  and     eax, ebp
0x1800034ec  mov     esi, eax
0x1800034ee  or      esi, edx
0x1800034f0  test    eax, eax
0x1800034f2  jz      loc_180003597
0x1800034f8  mov     rdi, [r14+20h]
0x1800034fc  test    rdi, rdi
0x1800034ff  jz      loc_180003597
0x180003505  jmp     loc_18000358E
0x18000350a  mov     rcx, [rdi]
0x18000350d  test    rcx, rcx
0x180003510  jz      loc_180003597
0x180003516  cmp     byte ptr [rcx+1Eh], 0
0x18000351a  jnz     short loc_180003574
0x18000351c  cmp     byte ptr [rcx+1Dh], 0
0x180003520  jnz     short loc_180003574
0x180003522  mov     r9, [rcx]
0x180003525  mov     [rsp+88h+arg_10], 0
0x180003531  mov     eax, [r9]
0x180003534  mov     dword ptr [rsp+88h+arg_10], eax
0x18000353b  test    al, 2
0x18000353d  jz      short loc_180003549
0x18000353f  mov     rax, [rsp+88h+arg_10]
0x180003547  jmp     short loc_18000355C
0x180003549  mov     rdx, [rsp+88h+arg_10]
0x180003551  mov     r8, rcx
0x180003554  mov     rcx, r9
0x180003557  call    wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState
0x18000355c  mov     ecx, esi
0x18000355e  and     ecx, eax
0x180003560  mov     eax, esi
0x180003562  test    bpl, cl
0x180003565  mov     ecx, 0
0x18000356a  setnz   cl
0x18000356d  and     eax, 0FFFFFFFEh
0x180003570  mov     esi, ecx
0x180003572  jmp     short loc_180003588
0x180003574  test    bpl, sil
0x180003577  jz      short loc_180003583
0x180003579  cmp     byte ptr [rcx+1Fh], 0
0x18000357d  jz      short loc_180003583
0x18000357f  mov     eax, ebp
0x180003581  jmp     short loc_180003585
0x180003583  xor     eax, eax
0x180003585  and     esi, 0FFFFFFFEh
0x180003588  or      esi, eax
0x18000358a  add     rdi, 8
0x18000358e  test    bpl, sil
0x180003591  jnz     loc_18000350A
0x180003597  cmp     byte ptr [r14+1Ch], 0
0x18000359c  jnz     short loc_1800035AE
0x18000359e  mov     eax, r15d
0x1800035a1  neg     eax
0x1800035a3  sbb     ebp, ebp
0x1800035a5  and     ebp, [rsp+88h+arg_0]
0x1800035ac  jmp     short loc_1800035B5
0x1800035ae  mov     ebp, [rsp+88h+arg_0]
0x1800035b5  mov     dword ptr [rsp+88h+arg_8], ebx
0x1800035bc  mov     edi, ebx
0x1800035be  test    ebp, ebp
0x1800035c0  jz      short loc_1800035E4
0x1800035c2  mov     dword ptr [rsp+88h+arg_8], ebx
0x1800035c9  test    bl, 2
0x1800035cc  jnz     short loc_1800035E4
0x1800035ce  mov     edi, esi
0x1800035d0  xor     edi, ebx
0x1800035d2  and     edi, 9C1h
0x1800035d8  xor     edi, ebx
0x1800035da  or      edi, 2
0x1800035dd  mov     dword ptr [rsp+88h+arg_8], edi
0x1800035e4  mov     ecx, ebx
0x1800035e6  and     ecx, 4
0x1800035e9  jnz     short loc_180003603
0x1800035eb  mov     eax, edi
0x1800035ed  mov     edi, esi
0x1800035ef  xor     edi, eax
0x1800035f1  and     edi, 400h
0x1800035f7  xor     edi, eax
0x1800035f9  or      edi, 4
0x1800035fc  mov     dword ptr [rsp+88h+arg_8], edi
0x180003603  mov     eax, ebx
0x180003605  lock cmpxchg [r12], edi
0x18000360b  jz      short loc_180003611
0x18000360d  mov     ebx, eax
0x18000360f  jmp     short loc_1800035B5
0x180003611  test    ecx, ecx
0x180003613  jnz     short loc_180003631
0x180003615  mov     rax, cs:g_wil_details_subscribeFeatureStateCacheToConfigurationChanges
0x18000361c  test    rax, rax
0x18000361f  jz      short loc_180003631
0x180003621  movzx   edx, byte ptr [r14+1Ch]
0x180003626  mov     r8d, r15d
0x180003629  mov     rcx, r12
0x18000362c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003631  test    ebp, ebp
0x180003633  jnz     short loc_180003646
0x180003635  xor     esi, edi
0x180003637  and     esi, 9C1h
0x18000363d  xor     esi, edi
0x18000363f  mov     dword ptr [rsp+88h+arg_8], esi
0x180003646  mov     rax, [rsp+88h+arg_8]
0x18000364e  add     rsp, 50h
0x180003652  pop     r15
0x180003654  pop     r14
0x180003656  pop     r12
0x180003658  pop     rdi
0x180003659  pop     rsi
0x18000365a  pop     rbp
0x18000365b  pop     rbx
0x18000365c  retn
```
