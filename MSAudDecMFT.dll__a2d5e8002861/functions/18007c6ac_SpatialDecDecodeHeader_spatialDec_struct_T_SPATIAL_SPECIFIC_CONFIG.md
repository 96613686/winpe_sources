# SpatialDecDecodeHeader(spatialDec_struct *,T_SPATIAL_SPECIFIC_CONFIG *)

- ea: `0x18007c6ac`
- end: `0x18007ca67`
- name: `?SpatialDecDecodeHeader@@YA?AW4SACDEC_ERROR@@PEAUspatialDec_struct@@PEAUT_SPATIAL_SPECIFIC_CONFIG@@@Z`
- size: `955`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18007f544`

## callees

- `0x18004dd14`
- `0x18007c6ac`
- `0x18007ca70`

## pseudocode

```c
__int64 __fastcall SpatialDecDecodeHeader(__int64 a1, __int64 a2)
{
  int v3; // r9d
  int v5; // r8d
  int v6; // eax
  _BYTE *v7; // r8
  int v8; // ecx
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  int v14; // ecx
  const signed __int8 near *const *v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // rax
  int v18; // ecx
  int v19; // ecx
  int v20; // ecx
  int v21; // ecx
  int v22; // ecx
  int v23; // ecx
  int i; // r9d
  __int64 v26; // rcx
  int j; // edx
  __int64 v28; // rcx
  __int64 k; // r8
  int v30; // r8d
  int v31; // ecx
  int v32; // edx
  int v33; // eax
  bool v34; // zf
  int v35; // r9d
  __int64 v36; // rdx
  int v37; // r9d
  __int64 v38; // rdx
  char v39; // al
  unsigned int v40; // eax
  int v41; // ecx
  char v42; // al
  int v43; // ecx
  int m; // ecx
  __int64 v45; // rax

  v3 = *(_DWORD *)(a1 + 192);
  *(_DWORD *)(a1 + 4) = *(_DWORD *)(a2 + 4);
  v5 = *(_DWORD *)(a2 + 8);
  v6 = v5 * v3;
  *(_DWORD *)(a1 + 156) = v5;
  v7 = *(_BYTE **)(a1 + 360);
  *(_DWORD *)(a1 + 172) = v6;
  v8 = *(_DWORD *)(a2 + 12);
  *(_DWORD *)(a1 + 380) = v8;
  if ( (*v7 & 0x20) == 0 )
    v3 += 7;
  *(_DWORD *)(a1 + 196) = v3;
  *(_DWORD *)(a1 + 188) = 12;
  *(_DWORD *)(a1 + 376) = v8;
  if ( (*v7 & 0x20) == 0 )
  {
    v18 = v8 - 4;
    if ( v18 )
    {
      v19 = v18 - 1;
      if ( v19 )
      {
        v20 = v19 - 2;
        if ( v20 )
        {
          v21 = v20 - 3;
          if ( v21 )
          {
            v22 = v21 - 4;
            if ( v22 )
            {
              v23 = v22 - 6;
              if ( v23 )
              {
                if ( v23 != 8 )
                  return 4294966305LL;
                v15 = &kernels_28_to_71;
              }
              else
              {
                v15 = &kernels_20_to_71;
              }
            }
            else
            {
              v15 = &kernels_14_to_71;
            }
          }
          else
          {
            v15 = &kernels_10_to_71;
          }
        }
        else
        {
          v15 = &kernels_7_to_71;
        }
      }
      else
      {
        v15 = &kernels_5_to_71;
      }
    }
    else
    {
      v15 = &kernels_4_to_71;
    }
    v16 = a1;
    v17 = 200;
    goto LABEL_35;
  }
  v9 = v8 - 4;
  if ( !v9 )
  {
    v15 = &kernels_4_to_64;
    goto LABEL_18;
  }
  v10 = v9 - 1;
  if ( !v10 )
  {
    v15 = &kernels_5_to_64;
    goto LABEL_18;
  }
  v11 = v10 - 2;
  if ( !v11 )
  {
    v15 = &kernels_7_to_64;
    goto LABEL_18;
  }
  v12 = v11 - 2;
  if ( !v12 )
  {
    v15 = &kernels_9_to_64;
    goto LABEL_18;
  }
  v13 = v12 - 3;
  if ( !v13 )
  {
    v15 = &kernels_12_to_64;
    goto LABEL_18;
  }
  v14 = v13 - 3;
  if ( !v14 )
  {
    v15 = &kernels_15_to_64;
    goto LABEL_18;
  }
  if ( v14 != 8 )
    return 4294966305LL;
  v15 = &kernels_23_to_64;
LABEL_18:
  v16 = 200;
  v17 = a1;
LABEL_35:
  *(_QWORD *)(v17 + v16) = v15;
  memset_0(*(void **)(a1 + 216), 0, 0x74u);
  for ( i = 0;
        i < *(_DWORD *)(a1 + 196);
        *(_DWORD *)(*(_QWORD *)(a1 + 216) + 4LL * *(char *)(v26 + *(_QWORD *)(a1 + 200)) + 4) = i )
  {
    v26 = i++;
  }
  for ( j = *(char *)(i + *(_QWORD *)(a1 + 200) - 1LL) + 2; j < 29; ++j )
  {
    v28 = j;
    *(_DWORD *)(*(_QWORD *)(a1 + 216) + 4 * v28) = i;
  }
  for ( k = 0; k != 28; ++k )
    *(_DWORD *)(a1 + 4 * k + 224) = *(_DWORD *)(*(_QWORD *)(a1 + 216) + 4 * (k + 1))
                                  - *(_DWORD *)(*(_QWORD *)(a1 + 216) + 4 * k);
  *(_DWORD *)(a1 + 80) = *(_DWORD *)(a2 + 16);
  v30 = *(_DWORD *)(a2 + 52);
  *(_DWORD *)(a1 + 92) = v30;
  v31 = *(_DWORD *)(a2 + 44);
  *(_DWORD *)(a1 + 84) = v31;
  v32 = *(_DWORD *)(a2 + 48);
  *(_DWORD *)(a1 + 88) = v32;
  *(_DWORD *)(a1 + 104) = *(_DWORD *)(a2 + 20);
  v33 = *(_DWORD *)(a2 + 24);
  *(_DWORD *)(a1 + 108) = v33;
  *(_DWORD *)(a1 + 96) = v32;
  *(_DWORD *)(a1 + 112) = 0;
  if ( v33 == 2 )
    *(_DWORD *)(a1 + 108) = 1;
  if ( (**(_BYTE **)(a1 + 360) & 2) != 0 )
    *(_DWORD *)(a1 + 112) = *(_DWORD *)(a2 + 28);
  v34 = *(_DWORD *)(a1 + 176) == -1;
  *(_DWORD *)(a1 + 132) = *((_DWORD *)&clipGainTable__CDK + *(int *)(a2 + 32));
  *(_DWORD *)(a1 + 116) = *(_DWORD *)(a2 + 36);
  *(_DWORD *)(a1 + 124) = *(_DWORD *)(a2 + 40);
  if ( v34 )
    *(_DWORD *)(a1 + 88) = v31;
  else
    v31 = v32;
  *(_DWORD *)(a1 + 100) = v31;
  v35 = 0;
  *(_DWORD *)(a1 + 1008) = *(unsigned __int8 *)(a2 + 181);
  for ( *(_DWORD *)(a1 + 544) = *(unsigned __int8 *)(a2 + 169); v35 < v30; v30 = *(_DWORD *)(a1 + 92) )
  {
    v36 = v35++;
    *(_BYTE *)(v36 + *(_QWORD *)(a1 + 360) + 182) = *(_BYTE *)(a1 + 380);
    *(_DWORD *)(*(_QWORD *)(a1 + 384) + 4 * v36) = *(unsigned __int8 *)(v36 + *(_QWORD *)(a1 + 360) + 182);
  }
  if ( *(_DWORD *)(a1 + 112) )
  {
    v37 = 0;
    if ( v30 > 0 )
    {
      v38 = 0;
      do
      {
        v39 = *(_BYTE *)(a2 + 8 * v38 + 80);
        *(_BYTE *)(v38 + a1 + 340) = v39;
        if ( v39 )
        {
          v40 = *(unsigned __int8 *)(a2 + 8 * v38 + 84);
          *(_BYTE *)(v38 + a1 + 345) = v40;
          v41 = *(_DWORD *)(*(_QWORD *)(a1 + 216) + 4LL * v40);
          v42 = 3;
          v43 = v41 - 7;
          if ( v43 > 3 )
            v42 = v43;
        }
        else
        {
          *(_BYTE *)(v38 + a1 + 345) = 0;
          v42 = 0;
        }
        *(_BYTE *)(v38 + a1 + 350) = v42;
        ++v37;
        ++v38;
      }
      while ( v37 < v30 );
    }
  }
  else
  {
    for ( m = 0; m < v30; *(_BYTE *)(v45 + a1 + 345) = 0 )
    {
      v45 = (unsigned int)m++;
      *(_BYTE *)(v45 + a1 + 340) = 0;
    }
  }
  if ( *(_DWORD *)(a1 + 80) != 7 )
    return 4294966306LL;
  v34 = *(_DWORD *)(a1 + 108) == 2;
  *(_DWORD *)(a1 + 136) = 1;
  *(_DWORD *)(a1 + 144) = 1;
  *(_DWORD *)(a1 + 152) = 1;
  if ( v34 )
    *(_DWORD *)(a1 + 152) = 2;
  *(_DWORD *)(a1 + 148) = 2;
  *(_DWORD *)(a1 + 540) = *(unsigned __int8 *)(a2 + 166);
  *(_DWORD *)(a1 + 120) = *(unsigned __int8 *)(a2 + 167);
  SpatialDecDecodeHelperInfo(a2);
  return 0;
}

```

## disassembly

```asm
0x18007c6ac  mov     [rsp+arg_0], rbx
0x18007c6b1  push    rdi
0x18007c6b2  sub     rsp, 20h
0x18007c6b6  mov     eax, [rdx+4]
0x18007c6b9  mov     rbx, rcx
0x18007c6bc  mov     r9d, [rcx+0C0h]
0x18007c6c3  mov     rdi, rdx
0x18007c6c6  mov     [rcx+4], eax
0x18007c6c9  mov     eax, r9d
0x18007c6cc  mov     r8d, [rdx+8]
0x18007c6d0  imul    eax, r8d
0x18007c6d4  mov     [rcx+9Ch], r8d
0x18007c6db  mov     r8, [rbx+168h]
0x18007c6e2  mov     [rcx+0ACh], eax
0x18007c6e8  lea     eax, [r9+7]
0x18007c6ec  mov     ecx, [rdx+0Ch]
0x18007c6ef  mov     [rbx+17Ch], ecx
0x18007c6f5  test    byte ptr [r8], 20h
0x18007c6f9  cmovz   r9d, eax
0x18007c6fd  mov     [rbx+0C4h], r9d
0x18007c704  mov     dword ptr [rbx+0BCh], 0Ch
0x18007c70e  mov     [rbx+178h], ecx
0x18007c714  test    byte ptr [r8], 20h
0x18007c718  jz      short loc_18007C784
0x18007c71a  sub     ecx, 4
0x18007c71d  jz      short loc_18007C773
0x18007c71f  sub     ecx, 1
0x18007c722  jz      short loc_18007C76A
0x18007c724  sub     ecx, 2
0x18007c727  jz      short loc_18007C761
0x18007c729  sub     ecx, 2
0x18007c72c  jz      short loc_18007C758
0x18007c72e  sub     ecx, 3
0x18007c731  jz      short loc_18007C74F
0x18007c733  sub     ecx, 3
0x18007c736  jz      short loc_18007C746
0x18007c738  cmp     ecx, 8
0x18007c73b  jnz     short loc_18007C7A7
0x18007c73d  lea     rcx, ?kernels_23_to_64@@3QBCB; signed char const near * const kernels_23_to_64
0x18007c744  jmp     short loc_18007C77A
0x18007c746  lea     rcx, ?kernels_15_to_64@@3QBCB; signed char const near * const kernels_15_to_64
0x18007c74d  jmp     short loc_18007C77A
0x18007c74f  lea     rcx, ?kernels_12_to_64@@3QBCB; signed char const near * const kernels_12_to_64
0x18007c756  jmp     short loc_18007C77A
0x18007c758  lea     rcx, ?kernels_9_to_64@@3QBCB; signed char const near * const kernels_9_to_64
0x18007c75f  jmp     short loc_18007C77A
0x18007c761  lea     rcx, ?kernels_7_to_64@@3QBCB; signed char const near * const kernels_7_to_64
0x18007c768  jmp     short loc_18007C77A
0x18007c76a  lea     rcx, ?kernels_5_to_64@@3QBCB; signed char const near * const kernels_5_to_64
0x18007c771  jmp     short loc_18007C77A
0x18007c773  lea     rcx, ?kernels_4_to_64@@3QBCB; signed char const near * const kernels_4_to_64
0x18007c77a  mov     edx, 0C8h
0x18007c77f  mov     rax, rbx
0x18007c782  jmp     short loc_18007C7F6
0x18007c784  sub     ecx, 4
0x18007c787  jz      short loc_18007C7E7
0x18007c789  sub     ecx, 1
0x18007c78c  jz      short loc_18007C7DE
0x18007c78e  sub     ecx, 2
0x18007c791  jz      short loc_18007C7D5
0x18007c793  sub     ecx, 3
0x18007c796  jz      short loc_18007C7CC
0x18007c798  sub     ecx, 4
0x18007c79b  jz      short loc_18007C7C3
0x18007c79d  sub     ecx, 6
0x18007c7a0  jz      short loc_18007C7BA
0x18007c7a2  cmp     ecx, 8
0x18007c7a5  jz      short loc_18007C7B1
0x18007c7a7  mov     eax, 0FFFFFC21h
0x18007c7ac  jmp     loc_18007CA5B
0x18007c7b1  lea     rcx, ?kernels_28_to_71@@3QBCB; signed char const near * const kernels_28_to_71
0x18007c7b8  jmp     short loc_18007C7EE
0x18007c7ba  lea     rcx, ?kernels_20_to_71@@3QBCB; signed char const near * const kernels_20_to_71
0x18007c7c1  jmp     short loc_18007C7EE
0x18007c7c3  lea     rcx, ?kernels_14_to_71@@3QBCB; signed char const near * const kernels_14_to_71
0x18007c7ca  jmp     short loc_18007C7EE
0x18007c7cc  lea     rcx, ?kernels_10_to_71@@3QBCB; signed char const near * const kernels_10_to_71
0x18007c7d3  jmp     short loc_18007C7EE
0x18007c7d5  lea     rcx, ?kernels_7_to_71@@3QBCB; signed char const near * const kernels_7_to_71
0x18007c7dc  jmp     short loc_18007C7EE
0x18007c7de  lea     rcx, ?kernels_5_to_71@@3QBCB; signed char const near * const kernels_5_to_71
0x18007c7e5  jmp     short loc_18007C7EE
0x18007c7e7  lea     rcx, ?kernels_4_to_71@@3QBCB; signed char const near * const kernels_4_to_71
0x18007c7ee  mov     rdx, rbx
0x18007c7f1  mov     eax, 0C8h
0x18007c7f6  mov     [rax+rdx], rcx
0x18007c7fa  xor     edx, edx; Val
0x18007c7fc  mov     rcx, [rbx+0D8h]; void *
0x18007c803  lea     r8d, [rdx+74h]; Size
0x18007c807  call    memset_0
0x18007c80c  xor     r10d, r10d
0x18007c80f  mov     r9d, r10d
0x18007c812  cmp     [rbx+0C4h], r10d
0x18007c819  jle     short loc_18007C846
0x18007c81b  mov     rax, [rbx+0C8h]
0x18007c822  lea     r8d, [r9+1]
0x18007c826  movsxd  rcx, r9d
0x18007c829  mov     r9d, r8d
0x18007c82c  movsx   rdx, byte ptr [rcx+rax]
0x18007c831  mov     rax, [rbx+0D8h]
0x18007c838  mov     [rax+rdx*4+4], r8d
0x18007c83d  cmp     r8d, [rbx+0C4h]
0x18007c844  jl      short loc_18007C81B
0x18007c846  mov     rax, [rbx+0C8h]
0x18007c84d  mov     r11d, 1
0x18007c853  movsxd  rcx, r9d
0x18007c856  movsx   edx, byte ptr [rcx+rax-1]
0x18007c85b  add     edx, 2
0x18007c85e  jmp     short loc_18007C871
0x18007c860  mov     rax, [rbx+0D8h]
0x18007c867  movsxd  rcx, edx
0x18007c86a  add     edx, r11d
0x18007c86d  mov     [rax+rcx*4], r9d
0x18007c871  cmp     edx, 1Dh
0x18007c874  jl      short loc_18007C860
0x18007c876  mov     r8, r10
0x18007c879  mov     rax, [rbx+0D8h]
0x18007c880  lea     rdx, [r8+1]
0x18007c884  mov     ecx, [rax+rdx*4]
0x18007c887  sub     ecx, [rax+r8*4]
0x18007c88b  mov     [rbx+r8*4+0E0h], ecx
0x18007c893  mov     r8, rdx
0x18007c896  cmp     rdx, 1Ch
0x18007c89a  jnz     short loc_18007C879
0x18007c89c  mov     eax, [rdi+10h]
0x18007c89f  mov     [rbx+50h], eax
0x18007c8a2  mov     r8d, [rdi+34h]
0x18007c8a6  mov     [rbx+5Ch], r8d
0x18007c8aa  mov     ecx, [rdi+2Ch]
0x18007c8ad  mov     [rbx+54h], ecx
0x18007c8b0  mov     edx, [rdi+30h]
0x18007c8b3  mov     [rbx+58h], edx
0x18007c8b6  mov     eax, [rdi+14h]
0x18007c8b9  mov     [rbx+68h], eax
0x18007c8bc  mov     eax, [rdi+18h]
0x18007c8bf  mov     [rbx+6Ch], eax
0x18007c8c2  mov     [rbx+60h], edx
0x18007c8c5  mov     [rbx+70h], r10d
0x18007c8c9  cmp     eax, 2
0x18007c8cc  jnz     short loc_18007C8D2
0x18007c8ce  mov     [rbx+6Ch], r11d
0x18007c8d2  mov     rax, [rbx+168h]
0x18007c8d9  test    byte ptr [rax], 2
0x18007c8dc  jz      short loc_18007C8E4
0x18007c8de  mov     eax, [rdi+1Ch]
0x18007c8e1  mov     [rbx+70h], eax
0x18007c8e4  cmp     dword ptr [rbx+0B0h], 0FFFFFFFFh
0x18007c8eb  lea     r9, ?clipGainTable__CDK@@3QBMB; float const near * const clipGainTable__CDK
0x18007c8f2  movsxd  rax, dword ptr [rdi+20h]
0x18007c8f6  mov     eax, [r9+rax*4]
0x18007c8fa  mov     [rbx+84h], eax
0x18007c900  mov     eax, [rdi+24h]
0x18007c903  mov     [rbx+74h], eax
0x18007c906  mov     eax, [rdi+28h]
0x18007c909  mov     [rbx+7Ch], eax
0x18007c90c  jnz     short loc_18007C913
0x18007c90e  mov     [rbx+58h], ecx
0x18007c911  jmp     short loc_18007C915
0x18007c913  mov     ecx, edx
0x18007c915  mov     [rbx+64h], ecx
0x18007c918  mov     r9d, r10d
0x18007c91b  movzx   eax, byte ptr [rdi+0B5h]
0x18007c922  mov     [rbx+3F0h], eax
0x18007c928  movzx   eax, byte ptr [rdi+0A9h]
0x18007c92f  mov     [rbx+220h], eax
0x18007c935  test    r8d, r8d
0x18007c938  jle     short loc_18007C976
0x18007c93a  mov     rcx, [rbx+168h]
0x18007c941  mov     al, [rbx+17Ch]
0x18007c947  movsxd  rdx, r9d
0x18007c94a  add     r9d, r11d
0x18007c94d  mov     [rdx+rcx+0B6h], al
0x18007c954  mov     rax, [rbx+168h]
0x18007c95b  movzx   ecx, byte ptr [rdx+rax+0B6h]
0x18007c963  mov     rax, [rbx+180h]
0x18007c96a  mov     [rax+rdx*4], ecx
0x18007c96d  mov     r8d, [rbx+5Ch]
0x18007c971  cmp     r9d, r8d
0x18007c974  jl      short loc_18007C93A
0x18007c976  cmp     [rbx+70h], r10d
0x18007c97a  jz      short loc_18007C9DC
0x18007c97c  mov     r9d, r10d
0x18007c97f  test    r8d, r8d
0x18007c982  jle     short loc_18007C9FE
0x18007c984  mov     rdx, r10
0x18007c987  mov     al, [rdi+rdx*8+50h]
0x18007c98b  mov     [rdx+rbx+154h], al
0x18007c992  test    al, al
0x18007c994  jz      short loc_18007C9BD
0x18007c996  movzx   eax, byte ptr [rdi+rdx*8+54h]
0x18007c99b  mov     [rdx+rbx+159h], al
0x18007c9a2  mov     ecx, eax
0x18007c9a4  mov     rax, [rbx+0D8h]
0x18007c9ab  mov     ecx, [rax+rcx*4]
0x18007c9ae  mov     eax, 3
0x18007c9b3  add     ecx, 0FFFFFFF9h
0x18007c9b6  cmp     ecx, eax
0x18007c9b8  cmovg   eax, ecx
0x18007c9bb  jmp     short loc_18007C9C8
0x18007c9bd  mov     [rdx+rbx+159h], r10b
0x18007c9c5  mov     al, r10b
0x18007c9c8  mov     [rdx+rbx+15Eh], al
0x18007c9cf  add     r9d, r11d
0x18007c9d2  add     rdx, r11
0x18007c9d5  cmp     r9d, r8d
0x18007c9d8  jl      short loc_18007C987
0x18007c9da  jmp     short loc_18007C9FE
0x18007c9dc  mov     ecx, r10d
0x18007c9df  test    r8d, r8d
0x18007c9e2  jle     short loc_18007C9FE
0x18007c9e4  mov     eax, ecx
0x18007c9e6  add     ecx, r11d
0x18007c9e9  mov     [rax+rbx+154h], r10b
0x18007c9f1  mov     [rax+rbx+159h], r10b
0x18007c9f9  cmp     ecx, r8d
0x18007c9fc  jl      short loc_18007C9E4
0x18007c9fe  cmp     dword ptr [rbx+50h], 7
0x18007ca02  jz      short loc_18007CA0B
0x18007ca04  mov     eax, 0FFFFFC22h
0x18007ca09  jmp     short loc_18007CA5B
0x18007ca0b  cmp     dword ptr [rbx+6Ch], 2
0x18007ca0f  mov     [rbx+88h], r11d
0x18007ca16  mov     [rbx+90h], r11d
0x18007ca1d  mov     [rbx+98h], r11d
0x18007ca24  jnz     short loc_18007CA30
0x18007ca26  mov     dword ptr [rbx+98h], 2
0x18007ca30  mov     dword ptr [rbx+94h], 2
0x18007ca3a  mov     rcx, rdi
0x18007ca3d  movzx   eax, byte ptr [rdi+0A6h]
0x18007ca44  mov     [rbx+21Ch], eax
0x18007ca4a  movzx   eax, byte ptr [rdi+0A7h]
0x18007ca51  mov     [rbx+78h], eax
0x18007ca54  call    SpatialDecDecodeHelperInfo
0x18007ca59  xor     eax, eax
0x18007ca5b  mov     rbx, [rsp+28h+arg_0]
0x18007ca60  add     rsp, 20h
0x18007ca64  pop     rdi
0x18007ca65  retn
```
