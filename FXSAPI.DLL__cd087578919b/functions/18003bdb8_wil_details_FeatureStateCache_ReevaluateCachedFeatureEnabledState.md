# wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState

- ea: `0x18003bdb8`
- end: `0x18003c00a`
- name: `wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState`
- size: `594`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003bdb8`
- `0x18003c054`

## callees

- `0x18000acb0`
- `0x18003bdb8`
- `0x18003e010`

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
0x18003bdb8  mov     rax, rsp
0x18003bdbb  push    rbx
0x18003bdbc  push    rbp
0x18003bdbd  push    rsi
0x18003bdbe  push    rdi
0x18003bdbf  push    r12
0x18003bdc1  push    r14
0x18003bdc3  push    r15
0x18003bdc5  sub     rsp, 50h
0x18003bdc9  xor     r15d, r15d
0x18003bdcc  mov     [rsp+88h+arg_8], rdx
0x18003bdd4  mov     [rax+8], r15d
0x18003bdd8  mov     r14, r8
0x18003bddb  mov     rax, cs:g_wil_details_ensureSubscribedToFeatureConfigurationChanges
0x18003bde2  mov     rbx, rdx
0x18003bde5  mov     r12, rcx
0x18003bde8  test    rax, rax
0x18003bdeb  jz      short loc_18003BDF5
0x18003bded  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bdf2  mov     r15d, eax
0x18003bdf5  mov     cl, [r14+1Ch]
0x18003bdf9  xor     r8d, r8d
0x18003bdfc  mov     edx, [r14+18h]
0x18003be00  sub     cl, 2
0x18003be03  xorps   xmm0, xmm0
0x18003be06  movups  [rsp+88h+var_58], xmm0
0x18003be0b  lea     ebp, [r8+1]
0x18003be0f  cmp     cl, bpl
0x18003be12  lea     rcx, [rsp+88h+var_58]
0x18003be17  setbe   r8b
0x18003be1b  xor     eax, eax
0x18003be1d  mov     [rsp+88h+var_48], rax
0x18003be22  lea     rax, [rsp+88h+arg_0]
0x18003be2a  mov     [rsp+88h+var_60], rax
0x18003be2f  mov     [rsp+88h+var_68], 0
0x18003be38  call    wil_QueryFeatureState
0x18003be3d  mov     ecx, dword ptr [rsp+88h+var_48]
0x18003be41  neg     ecx
0x18003be43  mov     ecx, dword ptr [rsp+88h+var_48+4]
0x18003be47  sbb     edx, edx
0x18003be49  and     edx, 400h
0x18003be4f  neg     ecx
0x18003be51  sbb     r8d, r8d
0x18003be54  and     r8d, 800h
0x18003be5b  or      r8d, edx
0x18003be5e  neg     eax
0x18003be60  sbb     eax, eax
0x18003be62  and     eax, dword ptr [rsp+88h+var_58]
0x18003be66  and     eax, 3
0x18003be69  mov     edx, eax
0x18003be6b  shl     edx, 7
0x18003be6e  or      edx, r8d
0x18003be71  test    eax, eax
0x18003be73  jnz     short loc_18003BE82
0x18003be75  mov     al, [r14+1Fh]
0x18003be79  neg     al
0x18003be7b  sbb     ecx, ecx
0x18003be7d  and     ecx, 40h
0x18003be80  jmp     short loc_18003BE8F
0x18003be82  xor     ecx, ecx
0x18003be84  cmp     dword ptr [rsp+88h+var_58], 2
0x18003be89  lea     eax, [rcx+40h]
0x18003be8c  cmovz   ecx, eax
0x18003be8f  or      edx, ecx
0x18003be91  mov     eax, edx
0x18003be93  shr     eax, 6
0x18003be96  and     eax, ebp
0x18003be98  mov     esi, eax
0x18003be9a  or      esi, edx
0x18003be9c  test    eax, eax
0x18003be9e  jz      loc_18003BF43
0x18003bea4  mov     rdi, [r14+20h]
0x18003bea8  test    rdi, rdi
0x18003beab  jz      loc_18003BF43
0x18003beb1  jmp     loc_18003BF3A
0x18003beb6  mov     rcx, [rdi]
0x18003beb9  test    rcx, rcx
0x18003bebc  jz      loc_18003BF43
0x18003bec2  cmp     byte ptr [rcx+1Eh], 0
0x18003bec6  jnz     short loc_18003BF20
0x18003bec8  cmp     byte ptr [rcx+1Dh], 0
0x18003becc  jnz     short loc_18003BF20
0x18003bece  mov     r9, [rcx]
0x18003bed1  mov     [rsp+88h+arg_10], 0
0x18003bedd  mov     eax, [r9]
0x18003bee0  mov     dword ptr [rsp+88h+arg_10], eax
0x18003bee7  test    al, 2
0x18003bee9  jz      short loc_18003BEF5
0x18003beeb  mov     rax, [rsp+88h+arg_10]
0x18003bef3  jmp     short loc_18003BF08
0x18003bef5  mov     rdx, [rsp+88h+arg_10]
0x18003befd  mov     r8, rcx
0x18003bf00  mov     rcx, r9
0x18003bf03  call    wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState
0x18003bf08  mov     ecx, esi
0x18003bf0a  and     ecx, eax
0x18003bf0c  mov     eax, esi
0x18003bf0e  test    bpl, cl
0x18003bf11  mov     ecx, 0
0x18003bf16  setnz   cl
0x18003bf19  and     eax, 0FFFFFFFEh
0x18003bf1c  mov     esi, ecx
0x18003bf1e  jmp     short loc_18003BF34
0x18003bf20  test    bpl, sil
0x18003bf23  jz      short loc_18003BF2F
0x18003bf25  cmp     byte ptr [rcx+1Fh], 0
0x18003bf29  jz      short loc_18003BF2F
0x18003bf2b  mov     eax, ebp
0x18003bf2d  jmp     short loc_18003BF31
0x18003bf2f  xor     eax, eax
0x18003bf31  and     esi, 0FFFFFFFEh
0x18003bf34  or      esi, eax
0x18003bf36  add     rdi, 8
0x18003bf3a  test    bpl, sil
0x18003bf3d  jnz     loc_18003BEB6
0x18003bf43  cmp     byte ptr [r14+1Ch], 0
0x18003bf48  jnz     short loc_18003BF5A
0x18003bf4a  mov     eax, r15d
0x18003bf4d  neg     eax
0x18003bf4f  sbb     ebp, ebp
0x18003bf51  and     ebp, [rsp+88h+arg_0]
0x18003bf58  jmp     short loc_18003BF61
0x18003bf5a  mov     ebp, [rsp+88h+arg_0]
0x18003bf61  mov     dword ptr [rsp+88h+arg_8], ebx
0x18003bf68  mov     edi, ebx
0x18003bf6a  test    ebp, ebp
0x18003bf6c  jz      short loc_18003BF90
0x18003bf6e  mov     dword ptr [rsp+88h+arg_8], ebx
0x18003bf75  test    bl, 2
0x18003bf78  jnz     short loc_18003BF90
0x18003bf7a  mov     edi, esi
0x18003bf7c  xor     edi, ebx
0x18003bf7e  and     edi, 9C1h
0x18003bf84  xor     edi, ebx
0x18003bf86  or      edi, 2
0x18003bf89  mov     dword ptr [rsp+88h+arg_8], edi
0x18003bf90  mov     ecx, ebx
0x18003bf92  and     ecx, 4
0x18003bf95  jnz     short loc_18003BFAF
0x18003bf97  mov     eax, edi
0x18003bf99  mov     edi, esi
0x18003bf9b  xor     edi, eax
0x18003bf9d  and     edi, 400h
0x18003bfa3  xor     edi, eax
0x18003bfa5  or      edi, 4
0x18003bfa8  mov     dword ptr [rsp+88h+arg_8], edi
0x18003bfaf  mov     eax, ebx
0x18003bfb1  lock cmpxchg [r12], edi
0x18003bfb7  jz      short loc_18003BFBD
0x18003bfb9  mov     ebx, eax
0x18003bfbb  jmp     short loc_18003BF61
0x18003bfbd  test    ecx, ecx
0x18003bfbf  jnz     short loc_18003BFDD
0x18003bfc1  mov     rax, cs:g_wil_details_subscribeFeatureStateCacheToConfigurationChanges
0x18003bfc8  test    rax, rax
0x18003bfcb  jz      short loc_18003BFDD
0x18003bfcd  movzx   edx, byte ptr [r14+1Ch]
0x18003bfd2  mov     r8d, r15d
0x18003bfd5  mov     rcx, r12
0x18003bfd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bfdd  test    ebp, ebp
0x18003bfdf  jnz     short loc_18003BFF2
0x18003bfe1  xor     esi, edi
0x18003bfe3  and     esi, 9C1h
0x18003bfe9  xor     esi, edi
0x18003bfeb  mov     dword ptr [rsp+88h+arg_8], esi
0x18003bff2  mov     rax, [rsp+88h+arg_8]
0x18003bffa  add     rsp, 50h
0x18003bffe  pop     r15
0x18003c000  pop     r14
0x18003c002  pop     r12
0x18003c004  pop     rdi
0x18003c005  pop     rsi
0x18003c006  pop     rbp
0x18003c007  pop     rbx
0x18003c008  retn
```
