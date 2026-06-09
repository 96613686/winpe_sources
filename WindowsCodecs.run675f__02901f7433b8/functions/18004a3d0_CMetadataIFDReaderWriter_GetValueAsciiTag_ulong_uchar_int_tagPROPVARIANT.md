# CMetadataIFDReaderWriter::GetValueAsciiTag(ulong,uchar * *,int,tagPROPVARIANT *)

- ea: `0x18004a3d0`
- end: `0x18004a7f7`
- name: `?GetValueAsciiTag@CMetadataIFDReaderWriter@@IEAAJKPEAPEAEHPEAUtagPROPVARIANT@@@Z`
- size: `1063`
- prototype: `__int64 __fastcall(CMetadataIFDReaderWriter *this, unsigned int, unsigned __int8 **, int, PROPVARIANT *pvar)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180048f40`
- `0x180049f00`

## callees

- `0x180025d9c`
- `0x18004a3d0`
- `0x1800bd9d4`
- `0x1800e6af4`
- `0x18017e438`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18004a54f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18004a54f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004a5ce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004a669`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004a6c2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004a741`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004a5ce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004a669`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004a6c2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004a741`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004a654`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18004a654`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a529`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a7e6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a529`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a7e6`

## pseudocode

```c
__int64 __fastcall CMetadataIFDReaderWriter::GetValueAsciiTag(
        CMetadataIFDReaderWriter *this,
        unsigned int a2,
        unsigned __int8 **a3,
        int a4,
        PROPVARIANT *pvar)
{
  unsigned __int8 *v5; // r12
  void *v7; // r15
  _BYTE *v8; // rdx
  unsigned int v9; // r14d
  __int64 v10; // rax
  unsigned int v11; // ecx
  unsigned __int8 *v12; // r9
  unsigned int v13; // edx
  int v14; // ebx
  int v15; // r13d
  unsigned int v16; // r8d
  unsigned int v17; // edx
  int v18; // r8d
  __int64 v19; // rcx
  int v20; // r14d
  LPVOID *v21; // rdi
  PROPVARIANT *v22; // rcx
  int v24; // eax
  __int64 v25; // rdx
  int v26; // ecx
  unsigned __int8 *v27; // rax
  unsigned __int8 *v28; // rbx
  unsigned __int64 v29; // rax
  bool v30; // zf
  unsigned int v31; // esi
  BYTE *v32; // rax
  int v33; // r13d
  BYTE *v34; // rdi
  PROPVARIANT *v35; // rax
  unsigned int v36; // edi
  unsigned int v37; // esi
  void *v38; // rax
  bool v39; // zf
  unsigned int v40; // eax
  size_t v41; // r8
  __int64 v42; // rbx
  unsigned int v43; // [rsp+30h] [rbp-40h]
  unsigned int v44; // [rsp+34h] [rbp-3Ch]
  int v45; // [rsp+38h] [rbp-38h] BYREF
  int *v46; // [rsp+40h] [rbp-30h] BYREF
  unsigned __int8 *v47; // [rsp+48h] [rbp-28h]
  void *Block[2]; // [rsp+50h] [rbp-20h] BYREF
  __int64 v49; // [rsp+60h] [rbp-10h]
  unsigned int v50; // [rsp+68h] [rbp-8h]
  char v51; // [rsp+B8h] [rbp+48h] BYREF
  unsigned __int8 **v52; // [rsp+C0h] [rbp+50h]
  int v53; // [rsp+C8h] [rbp+58h]

  v53 = a4;
  v52 = a3;
  v5 = *a3;
  v51 = 0;
  v49 = 0;
  v50 = 0;
  v7 = 0;
  v8 = (char *)this + 132;
  v9 = 0;
  *(_OWORD *)Block = 0;
  if ( !a2 )
  {
    if ( (*v8 & 2) != 0 )
      goto LABEL_55;
    a2 = 1;
    v53 = 0;
    v5 = (unsigned __int8 *)&v51;
  }
  if ( !v5[a2 - 1] )
    goto LABEL_3;
  if ( (*v8 & 2) != 0 )
  {
LABEL_55:
    v14 = -2003292317;
LABEL_56:
    v39 = (_DWORD)g_doStackCaptures == 0;
LABEL_57:
    if ( !v39 )
      DoStackCapture(v14);
    goto LABEL_46;
  }
  if ( a2 + 1 < a2 )
  {
    v30 = (_DWORD)g_doStackCaptures == 0;
    goto LABEL_43;
  }
  v7 = CoTaskMemAlloc(a2 + 1);
  if ( !v7 )
  {
LABEL_69:
    v14 = -2147024882;
    goto LABEL_56;
  }
  v40 = a2;
  v41 = a2++;
  v42 = v40;
  memcpy_0(v7, v5, v41);
  *((_BYTE *)v7 + v42) = 0;
  v5 = (unsigned __int8 *)v7;
LABEL_3:
  v10 = 0;
  v11 = 0;
  v44 = 0;
  v12 = v5;
  v47 = v5;
  v13 = 0;
  v14 = 0;
  while ( 1 )
  {
    v43 = v13;
    v15 = v14;
    if ( v13 >= a2 )
      break;
    if ( *v12 )
    {
      ++v13;
      goto LABEL_7;
    }
    v16 = v13;
    v17 = v9 + 1;
    v18 = v16 - v11 + 1;
    v45 = v18;
    if ( v9 + 1 < v9 )
    {
      if ( (_DWORD)g_doStackCaptures )
        DoStackCapture(-2147024362);
      v14 = -2147024362;
LABEL_39:
      if ( (_DWORD)g_doStackCaptures )
        DoStackCapture(v14);
LABEL_15:
      if ( v14 < 0 )
        goto LABEL_46;
      v12 = v47;
      goto LABEL_17;
    }
    if ( v17 > HIDWORD(v49) )
    {
      v46 = &v45;
      v24 = DynArrayImpl<0>::Grow((unsigned int)Block, 4, 1, 0, (__int64)&v46);
      v14 = v24;
      if ( v24 < 0 )
      {
        if ( (_DWORD)g_doStackCaptures )
          DoStackCapture(v24);
        v9 = v50;
      }
      else
      {
        v25 = 4 * v50;
        v9 = v50 + 1;
        v26 = *v46;
        ++v50;
        *(_DWORD *)((char *)Block[0] + v25) = v26;
      }
      if ( v14 < 0 )
        goto LABEL_39;
      goto LABEL_15;
    }
    v14 = 0;
    v19 = v9++;
    v50 = v17;
    *((_DWORD *)Block[0] + v19) = v18;
LABEL_17:
    v10 = v44 + 1;
    v11 = v43 + 1;
    ++v44;
    v13 = v43 + 1;
LABEL_7:
    v47 = ++v12;
  }
  if ( (_DWORD)v10 != 1 )
  {
    v29 = 8 * v10;
    if ( v29 > 0xFFFFFFFF )
    {
      v30 = (_DWORD)g_doStackCaptures == 0;
LABEL_43:
      if ( !v30 )
        DoStackCapture(-2147024362);
      v14 = -2147024362;
LABEL_46:
      v20 = v53;
LABEL_47:
      v21 = (LPVOID *)v52;
      PropVariantClear(pvar);
      goto LABEL_23;
    }
    v31 = v29;
    v32 = (BYTE *)CoTaskMemAlloc((unsigned int)v29);
    v33 = 0;
    v34 = v32;
    if ( v32 )
    {
      v14 = 0;
      memset_0(v32, 0, v31);
      v35 = pvar;
      pvar[2] = v34;
      v36 = 0;
      *(_WORD *)v35 = 4126;
      *((_DWORD *)v35 + 2) = v44;
      while ( 1 )
      {
        if ( v36 >= v44 )
        {
          v21 = (LPVOID *)v52;
          v20 = v53;
          goto LABEL_23;
        }
        v37 = *((_DWORD *)Block[0] + v36);
        v38 = CoTaskMemAlloc(v37);
        if ( !v38 )
          break;
        *((_QWORD *)pvar[2] + v36) = v38;
        memcpy_0(v38, &v5[v33], v37);
        v33 += v37;
        ++v36;
      }
      v39 = (_DWORD)g_doStackCaptures == 0;
      v14 = -2147024882;
      goto LABEL_57;
    }
    goto LABEL_69;
  }
  v20 = v53;
  if ( v7 )
  {
    v5 = (unsigned __int8 *)v7;
    v7 = 0;
    goto LABEL_35;
  }
  if ( v53 )
  {
    v21 = (LPVOID *)v52;
    *v52 = 0;
    goto LABEL_22;
  }
  v27 = (unsigned __int8 *)CoTaskMemAlloc(a2);
  v28 = v27;
  if ( !v27 )
  {
    v14 = -2147024882;
    if ( (_DWORD)g_doStackCaptures )
      DoStackCapture(-2147024882);
    goto LABEL_47;
  }
  memcpy_0(v27, v5, a2);
  v5 = v28;
LABEL_35:
  v21 = (LPVOID *)v52;
LABEL_22:
  v22 = pvar;
  *(_WORD *)pvar = 30;
  v22[1] = v5;
  v14 = v15;
LABEL_23:
  if ( v20 && *v21 )
  {
    CoTaskMemFree(*v21);
    *v21 = 0;
  }
  if ( v7 )
    CoTaskMemFree(v7);
  if ( Block[0] != Block[1] )
    free(Block[0]);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x18004a3d0  mov     [rsp-38h+arg_0], rbx
0x18004a3d5  mov     [rsp-38h+arg_18], r9d
0x18004a3da  mov     [rsp-38h+arg_10], r8
0x18004a3df  push    rbp
0x18004a3e0  push    rsi
0x18004a3e1  push    rdi
0x18004a3e2  push    r12
0x18004a3e4  push    r13
0x18004a3e6  push    r14
0x18004a3e8  push    r15
0x18004a3ea  mov     rbp, rsp
0x18004a3ed  sub     rsp, 70h
0x18004a3f1  mov     r12, [r8]
0x18004a3f4  xor     r13d, r13d
0x18004a3f7  mov     esi, edx
0x18004a3f9  mov     [rbp+arg_8], r13b
0x18004a3fd  mov     [rbp+var_10], r13
0x18004a401  xorps   xmm0, xmm0
0x18004a404  mov     [rbp+var_8], r13d
0x18004a408  mov     r15d, r13d
0x18004a40b  lea     rdx, [rcx+84h]
0x18004a412  mov     r14d, r13d
0x18004a415  movdqu  xmmword ptr [rbp+Block], xmm0
0x18004a41a  test    esi, esi
0x18004a41c  jz      loc_18004A7B2
0x18004a422  lea     eax, [rsi-1]
0x18004a425  cmp     [rax+r12], r13b
0x18004a429  jnz     loc_18004A70A
0x18004a42f  mov     eax, r13d
0x18004a432  mov     ecx, r13d
0x18004a435  mov     [rbp+var_3C], eax
0x18004a438  mov     r9, r12
0x18004a43b  mov     [rbp+var_28], r12
0x18004a43f  mov     edx, r13d
0x18004a442  mov     ebx, r13d
0x18004a445  mov     edi, 80070216h
0x18004a44a  mov     [rbp+var_40], edx
0x18004a44d  mov     r13d, ebx
0x18004a450  cmp     edx, esi
0x18004a452  jnb     loc_18004A4DD
0x18004a458  xor     r13d, r13d
0x18004a45b  cmp     [r9], r13b
0x18004a45e  jz      short loc_18004A46B
0x18004a460  inc     edx
0x18004a462  inc     r9
0x18004a465  mov     [rbp+var_28], r9
0x18004a469  jmp     short loc_18004A44A
0x18004a46b  mov     r8d, edx
0x18004a46e  lea     edx, [r14+1]
0x18004a472  sub     r8d, ecx
0x18004a475  inc     r8d
0x18004a478  mov     [rbp+var_38], r8d
0x18004a47c  cmp     edx, r14d
0x18004a47f  jb      loc_18004A600
0x18004a485  cmp     edx, dword ptr [rbp+var_10+4]
0x18004a488  ja      loc_18004A576
0x18004a48e  mov     rax, [rbp+Block]
0x18004a492  mov     ebx, r13d
0x18004a495  mov     ecx, r14d
0x18004a498  mov     r14d, edx
0x18004a49b  mov     [rbp+var_8], edx
0x18004a49e  mov     [rax+rcx*4], r8d
0x18004a4a2  jmp     short loc_18004A4CC
0x18004a4a4  cmp     cs:?g_doStackCaptures@@3HA, r13d; int g_doStackCaptures
0x18004a4ab  jz      short loc_18004A4B4
0x18004a4ad  mov     ecx, ebx; int
0x18004a4af  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18004a4b4  mov     r14d, [rbp+var_8]
0x18004a4b8  test    ebx, ebx
0x18004a4ba  js      loc_18004A612
0x18004a4c0  test    ebx, ebx
0x18004a4c2  js      loc_18004A648
0x18004a4c8  mov     r9, [rbp+var_28]
0x18004a4cc  mov     eax, [rbp+var_3C]
0x18004a4cf  mov     ecx, [rbp+var_40]
0x18004a4d2  inc     eax
0x18004a4d4  inc     ecx
0x18004a4d6  mov     [rbp+var_3C], eax
0x18004a4d9  mov     edx, ecx
0x18004a4db  jmp     short loc_18004A462
0x18004a4dd  cmp     eax, 1
0x18004a4e0  jnz     loc_18004A62B
0x18004a4e6  mov     r14d, [rbp+arg_18]
0x18004a4ea  test    r15, r15
0x18004a4ed  jnz     loc_18004A72D
0x18004a4f3  test    r14d, r14d
0x18004a4f6  jz      loc_18004A5CA
0x18004a4fc  mov     rdi, [rbp+arg_10]
0x18004a500  mov     [rdi], r15
0x18004a503  mov     rcx, [rbp+pvar]
0x18004a507  mov     word ptr [rcx], 1Eh
0x18004a50c  mov     [rcx+8], r12
0x18004a510  mov     ebx, r13d
0x18004a513  test    r13d, r13d
0x18004a516  js      loc_18004A654
0x18004a51c  test    r14d, r14d
0x18004a51f  jz      short loc_18004A53C
0x18004a521  mov     rcx, [rdi]; pv
0x18004a524  test    rcx, rcx
0x18004a527  jz      short loc_18004A53C
0x18004a529  call    cs:__imp_CoTaskMemFree
0x18004a530  nop     dword ptr [rax+rax+00h]
0x18004a535  mov     qword ptr [rdi], 0
0x18004a53c  test    r15, r15
0x18004a53f  jnz     loc_18004A7E3
0x18004a545  mov     rcx, [rbp+Block]; Block
0x18004a549  cmp     rcx, [rbp+Block+8]
0x18004a54d  jz      short loc_18004A55B
0x18004a54f  call    cs:__imp_free
0x18004a556  nop     dword ptr [rax+rax+00h]
0x18004a55b  mov     eax, ebx
0x18004a55d  mov     rbx, [rsp+70h+arg_0]
0x18004a565  add     rsp, 70h
0x18004a569  pop     r15
0x18004a56b  pop     r14
0x18004a56d  pop     r13
0x18004a56f  pop     r12
0x18004a571  pop     rdi
0x18004a572  pop     rsi
0x18004a573  pop     rbp
0x18004a574  retn
0x18004a576  xor     r9d, r9d
0x18004a579  lea     rax, [rbp+var_38]
0x18004a57d  mov     [rbp+var_30], rax
0x18004a581  lea     rcx, [rbp+Block]
0x18004a585  lea     rax, [rbp+var_30]
0x18004a589  mov     [rsp+70h+var_50], rax
0x18004a58e  lea     edx, [r9+4]
0x18004a592  lea     r8d, [r9+1]
0x18004a596  call    ?Grow@?$DynArrayImpl@$0A@@@IEAAJIIHPEAPEBX@Z; DynArrayImpl<0>::Grow(uint,uint,int,void const * *)
0x18004a59b  mov     ebx, eax
0x18004a59d  test    eax, eax
0x18004a59f  js      loc_18004A4A4
0x18004a5a5  mov     r14d, [rbp+var_8]
0x18004a5a9  mov     rax, [rbp+var_30]
0x18004a5ad  lea     edx, ds:0[r14*4]
0x18004a5b5  inc     r14d
0x18004a5b8  mov     ecx, [rax]
0x18004a5ba  mov     rax, [rbp+Block]
0x18004a5be  mov     [rbp+var_8], r14d
0x18004a5c2  mov     [rdx+rax], ecx
0x18004a5c5  jmp     loc_18004A4B8
0x18004a5ca  mov     ecx, esi; cb
0x18004a5cc  mov     edi, esi
0x18004a5ce  call    cs:__imp_CoTaskMemAlloc
0x18004a5d5  nop     dword ptr [rax+rax+00h]
0x18004a5da  mov     rbx, rax
0x18004a5dd  test    rax, rax
0x18004a5e0  jz      loc_18004A794
0x18004a5e6  mov     r8d, edi; Size
0x18004a5e9  mov     rdx, r12; Src
0x18004a5ec  mov     rcx, rax; void *
0x18004a5ef  call    memcpy_0
0x18004a5f4  mov     r12, rbx
0x18004a5f7  mov     rdi, [rbp+arg_10]
0x18004a5fb  jmp     loc_18004A503
0x18004a600  cmp     cs:?g_doStackCaptures@@3HA, r13d; int g_doStackCaptures
0x18004a607  jz      short loc_18004A610
0x18004a609  mov     ecx, edi; int
0x18004a60b  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18004a610  mov     ebx, edi
0x18004a612  cmp     cs:?g_doStackCaptures@@3HA, r13d; int g_doStackCaptures
0x18004a619  jz      loc_18004A4C0
0x18004a61f  mov     ecx, ebx; int
0x18004a621  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18004a626  jmp     loc_18004A4C0
0x18004a62b  shl     rax, 3
0x18004a62f  mov     ecx, 0FFFFFFFFh
0x18004a634  cmp     rax, rcx
0x18004a637  jbe     short loc_18004A665
0x18004a639  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18004a640  jnz     loc_18004A7D7
0x18004a646  mov     ebx, edi
0x18004a648  mov     r14d, [rbp+arg_18]
0x18004a64c  mov     rcx, [rbp+pvar]; pvar
0x18004a650  mov     rdi, [rbp+arg_10]
0x18004a654  call    cs:__imp_PropVariantClear
0x18004a65b  nop     dword ptr [rax+rax+00h]
0x18004a660  jmp     loc_18004A51C
0x18004a665  mov     ecx, eax; cb
0x18004a667  mov     esi, eax
0x18004a669  call    cs:__imp_CoTaskMemAlloc
0x18004a670  nop     dword ptr [rax+rax+00h]
0x18004a675  xor     r13d, r13d
0x18004a678  mov     rdi, rax
0x18004a67b  test    rax, rax
0x18004a67e  jz      loc_18004A7CD
0x18004a684  mov     r8d, esi; Size
0x18004a687  xor     edx, edx; Val
0x18004a689  mov     rcx, rax; void *
0x18004a68c  mov     ebx, r13d
0x18004a68f  call    memset_0
0x18004a694  mov     rax, [rbp+pvar]
0x18004a698  mov     r14d, [rbp+var_3C]
0x18004a69c  mov     [rax+10h], rdi
0x18004a6a0  mov     edi, r13d
0x18004a6a3  mov     word ptr [rax], 101Eh
0x18004a6a8  mov     [rax+8], r14d
0x18004a6ac  mov     [rbp+var_3C], r13d
0x18004a6b0  cmp     edi, r14d
0x18004a6b3  jnb     short loc_18004A6FD
0x18004a6b5  mov     rax, [rbp+Block]
0x18004a6b9  mov     r13d, edi
0x18004a6bc  mov     esi, [rax+r13*4]
0x18004a6c0  mov     ecx, esi; cb
0x18004a6c2  call    cs:__imp_CoTaskMemAlloc
0x18004a6c9  nop     dword ptr [rax+rax+00h]
0x18004a6ce  test    rax, rax
0x18004a6d1  jz      loc_18004A786
0x18004a6d7  mov     rcx, [rbp+pvar]
0x18004a6db  mov     r8d, esi; Size
0x18004a6de  mov     rcx, [rcx+10h]
0x18004a6e2  mov     [rcx+r13*8], rax
0x18004a6e6  mov     rcx, rax; void *
0x18004a6e9  mov     r13d, [rbp+var_3C]
0x18004a6ed  lea     rdx, [r12+r13]; Src
0x18004a6f1  call    memcpy_0
0x18004a6f6  add     r13d, esi
0x18004a6f9  inc     edi
0x18004a6fb  jmp     short loc_18004A6AC
0x18004a6fd  mov     rdi, [rbp+arg_10]
0x18004a701  mov     r14d, [rbp+arg_18]
0x18004a705  jmp     loc_18004A51C
0x18004a70a  test    byte ptr [rdx], 2
0x18004a70d  jz      short loc_18004A738
0x18004a70f  mov     ebx, 88982F63h
0x18004a714  cmp     cs:?g_doStackCaptures@@3HA, r13d; int g_doStackCaptures
0x18004a71b  jz      loc_18004A648
0x18004a721  mov     ecx, ebx; int
0x18004a723  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18004a728  jmp     loc_18004A648
0x18004a72d  mov     r12, r15
0x18004a730  xor     r15d, r15d
0x18004a733  jmp     loc_18004A5F7
0x18004a738  lea     ebx, [rsi+1]
0x18004a73b  cmp     ebx, esi
0x18004a73d  jb      short loc_18004A775
0x18004a73f  mov     ecx, ebx; cb
0x18004a741  call    cs:__imp_CoTaskMemAlloc
0x18004a748  nop     dword ptr [rax+rax+00h]
0x18004a74d  mov     r15, rax
0x18004a750  test    rax, rax
0x18004a753  jz      short loc_18004A7CD
0x18004a755  mov     eax, esi
0x18004a757  mov     rdx, r12; Src
0x18004a75a  mov     r8d, eax; Size
0x18004a75d  mov     esi, ebx
0x18004a75f  mov     rcx, r15; void *
0x18004a762  mov     ebx, eax
0x18004a764  call    memcpy_0
0x18004a769  mov     [rbx+r15], r13b
0x18004a76d  mov     r12, r15
0x18004a770  jmp     loc_18004A42F
0x18004a775  cmp     cs:?g_doStackCaptures@@3HA, r13d; int g_doStackCaptures
0x18004a77c  mov     edi, 80070216h
0x18004a781  jmp     loc_18004A640
0x18004a786  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18004a78d  mov     ebx, 8007000Eh
0x18004a792  jmp     short loc_18004A71B
0x18004a794  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18004a79b  mov     ebx, 8007000Eh
0x18004a7a0  jz      loc_18004A64C
0x18004a7a6  mov     ecx, ebx; int
0x18004a7a8  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18004a7ad  jmp     loc_18004A64C
0x18004a7b2  test    byte ptr [rdx], 2
0x18004a7b5  jnz     loc_18004A70F
0x18004a7bb  mov     esi, 1
0x18004a7c0  mov     [rbp+arg_18], r13d
0x18004a7c4  lea     r12, [rbp+arg_8]
0x18004a7c8  jmp     loc_18004A422
0x18004a7cd  mov     ebx, 8007000Eh
0x18004a7d2  jmp     loc_18004A714
0x18004a7d7  mov     ecx, edi; int
0x18004a7d9  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18004a7de  jmp     loc_18004A646
0x18004a7e3  mov     rcx, r15; pv
0x18004a7e6  call    cs:__imp_CoTaskMemFree
0x18004a7ed  nop     dword ptr [rax+rax+00h]
0x18004a7f2  jmp     loc_18004A545
```
