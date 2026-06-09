# zisofs_read_data

- ea: `0x1800d2d48`
- end: `0x1800d322c`
- name: `zisofs_read_data`
- size: `1252`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800cfd80`

## callees

- `0x180005914`
- `0x180006c00`
- `0x180012634`
- `0x180015810`
- `0x1800aba54`
- `0x1800d2d48`
- `0x18011736c`
- `0x180117448`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800d2e19`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800d2e7a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800d2e19`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800d2e7a`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800d2e33`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800d2e83`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800d2e33`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800d2e83`

## string_xrefs

- `0x1800d2e95`: `No memory for zisofs decompression`
- `0x1800d30e4`: `Can't initialize zisofs decompression.`
- `0x1800d318c`: `zisofs decompression failed (%d)`

## pseudocode

```c
__int64 __fastcall zisofs_read_data(__int64 a1, _QWORD *a2, _QWORD *a3, _QWORD *a4)
{
  __int64 *v4; // rax
  __int64 v7; // rbx
  char *filter_ahead; // rax
  unsigned __int64 v9; // rdi
  char *v10; // r12
  unsigned __int64 v12; // rsi
  unsigned __int64 v13; // r14
  void *v14; // rcx
  void *v15; // rax
  int v16; // ecx
  size_t v17; // r14
  void *v18; // rcx
  void *v19; // rax
  unsigned __int64 v20; // rax
  size_t v21; // r14
  BOOL v22; // edx
  unsigned __int64 v23; // r15
  __int64 v24; // r14
  unsigned __int64 v25; // rcx
  size_t v26; // r15
  __int64 v27; // rdx
  __int64 v28; // r8
  __int64 v29; // r10
  unsigned int v30; // ecx
  bool v31; // zf
  __int64 v32; // rcx
  int v33; // eax
  unsigned __int64 v34; // rcx
  _QWORD *v35; // r15
  unsigned int v36; // eax
  unsigned __int64 v37; // rdi
  __int64 v38; // [rsp+60h] [rbp+8h] BYREF
  _QWORD *v39; // [rsp+68h] [rbp+10h]
  _QWORD *v40; // [rsp+70h] [rbp+18h]

  v40 = a3;
  v39 = a2;
  v4 = *(__int64 **)(a1 + 2072);
  v38 = 0;
  v7 = *v4;
  filter_ahead = (char *)_archive_read_filter_ahead(*(_QWORD *)(a1 + 632), 1u, (size_t *)&v38);
  v9 = v38;
  v10 = filter_ahead;
  if ( v38 <= 0 )
  {
    archive_set_error(a1, 42, "Truncated zisofs file body");
    return 4294967266LL;
  }
  if ( v38 > *(_QWORD *)(v7 + 216) )
    v9 = *(_QWORD *)(v7 + 216);
  v12 = v9;
  if ( !*(_DWORD *)(v7 + 248) )
  {
    v13 = 4
        * ((unsigned __int64)((1LL << *(_DWORD *)(v7 + 236)) + *(_QWORD *)(v7 + 240) - 1LL) >> *(_DWORD *)(v7 + 236))
        + 4;
    if ( *(_QWORD *)(v7 + 320) < v13 )
    {
      v14 = *(void **)(v7 + 312);
      if ( v14 )
        free(v14);
      v15 = malloc((v13 & 0xFFFFFFFFFFFFFC00uLL) + 1024);
      *(_QWORD *)(v7 + 312) = v15;
      if ( !v15 )
        goto LABEL_16;
      *(_QWORD *)(v7 + 320) = (v13 & 0xFFFFFFFFFFFFFC00uLL) + 1024;
    }
    v16 = *(_DWORD *)(v7 + 236);
    *(_QWORD *)(v7 + 328) = v13;
    v17 = 1LL << v16;
    if ( *(_QWORD *)(v7 + 264) < (unsigned __int64)(1LL << v16) )
    {
      v18 = *(void **)(v7 + 256);
      if ( v18 )
        free(v18);
      v19 = malloc(v17);
      *(_QWORD *)(v7 + 256) = v19;
      if ( !v19 )
      {
LABEL_16:
        archive_set_error(a1, 12, "No memory for zisofs decompression");
        return 4294967266LL;
      }
    }
    v20 = *(_QWORD *)(v7 + 296);
    *(_QWORD *)(v7 + 264) = v17;
    if ( v20 < 0x10 )
    {
      v21 = 16 - v20;
      if ( v9 < 16 - v20 )
        v21 = v9;
      memcpy_0((void *)(v7 + v20 + 276), v10, v21);
      *(_QWORD *)(v7 + 296) += v21;
      v12 = v9 - v21;
      v20 = *(_QWORD *)(v7 + 296);
      v10 += v21;
    }
    if ( !*(_DWORD *)(v7 + 304) )
    {
      if ( v20 != 16 )
      {
        v24 = 0;
        goto LABEL_37;
      }
      v22 = *(_QWORD *)(v7 + 276) != 0x7D6DBC99653E437LL;
      if ( (*(unsigned __int8 *)(v7 + 284)
          | ((*(unsigned __int8 *)(v7 + 285)
            | ((*(unsigned __int8 *)(v7 + 286) | ((unsigned __int64)*(unsigned __int8 *)(v7 + 287) << 8)) << 8)) << 8)) != *(_QWORD *)(v7 + 240) )
        v22 = 1;
      if ( *(_BYTE *)(v7 + 288) != 4 )
        v22 = 1;
      if ( *(unsigned __int8 *)(v7 + 289) != *(_DWORD *)(v7 + 236) || v22 )
      {
        archive_set_error(a1, 42, "Illegal zisofs file body");
        return 4294967266LL;
      }
      *(_DWORD *)(v7 + 304) = 1;
    }
    v23 = *(_QWORD *)(v7 + 328);
    v24 = 0;
    v25 = *(_QWORD *)(v7 + 336);
    if ( v25 < v23 )
    {
      v26 = v23 - v25;
      if ( v12 < v26 )
        v26 = v12;
      memcpy_0((void *)(*(_QWORD *)(v7 + 312) + v25), v10, v26);
      *(_QWORD *)(v7 + 336) += v26;
      v12 -= v26;
      v10 += v26;
      if ( *(_QWORD *)(v7 + 336) == *(_QWORD *)(v7 + 328) )
      {
        *(_QWORD *)(v7 + 344) = 0;
        *(_DWORD *)(v7 + 352) = 0;
        *(_DWORD *)(v7 + 248) = 1;
      }
    }
LABEL_37:
    if ( !*(_DWORD *)(v7 + 248) )
      goto LABEL_57;
  }
  if ( !*(_DWORD *)(v7 + 352) )
  {
    v27 = *(_QWORD *)(v7 + 344);
    if ( (unsigned __int64)(v27 + 4) >= *(_QWORD *)(v7 + 328) )
      goto LABEL_51;
    v28 = *(_QWORD *)(v7 + 312);
    v29 = *(unsigned __int8 *)(v28 + v27)
        | ((*(unsigned __int8 *)(v28 + v27 + 1) | (*(unsigned __int16 *)(v28 + v27 + 2) << 8)) << 8);
    if ( v29 != v9 + *(unsigned int *)(v7 + 272) - v12 )
    {
      archive_set_error(a1, 42, "Illegal zisofs block pointers(cannot seek)");
      return 4294967266LL;
    }
    v30 = *(unsigned __int8 *)(v28 + v27 + 4)
        | ((*(unsigned __int8 *)(v28 + v27 + 5) | (*(unsigned __int16 *)(v28 + v27 + 6) << 8)) << 8);
    if ( v30 < (unsigned int)v29 )
    {
LABEL_51:
      archive_set_error(a1, 42, "Illegal zisofs block pointers");
      return 4294967266LL;
    }
    *(_QWORD *)(v7 + 344) = v27 + 4;
    v31 = *(_DWORD *)(v7 + 448) == 0;
    *(_DWORD *)(v7 + 352) = v30 - v29;
    v32 = v7 + 360;
    if ( v31 )
      v33 = inflateInit2_(v32, 15, v28);
    else
      v33 = inflateReset(v32, v27, v28);
    if ( v33 )
    {
      archive_set_error(a1, 0xFFFFFFFFLL, "Can't initialize zisofs decompression.");
      return 4294967266LL;
    }
    *(_DWORD *)(v7 + 448) = 1;
    *(_DWORD *)(v7 + 372) = 0;
    *(_DWORD *)(v7 + 388) = 0;
  }
  v34 = *(unsigned int *)(v7 + 352);
  if ( (_DWORD)v34 )
  {
    v35 = (_QWORD *)(v7 + 360);
    *(_QWORD *)(v7 + 360) = v10;
    if ( v12 <= v34 )
      LODWORD(v34) = v12;
    *(_DWORD *)(v7 + 368) = v34;
    *(_QWORD *)(v7 + 376) = *(_QWORD *)(v7 + 256);
    *(_DWORD *)(v7 + 384) = *(_DWORD *)(v7 + 264);
    v36 = inflate(v7 + 360, 0);
    if ( v36 >= 2 )
    {
      archive_set_error(a1, 0xFFFFFFFFLL, "zisofs decompression failed (%d)", v36);
      return 4294967266LL;
    }
    v24 = *(_QWORD *)(v7 + 264) - *(unsigned int *)(v7 + 384);
    v12 += (unsigned __int64)&v10[-*v35];
    *(_DWORD *)(v7 + 352) = (_DWORD)v10 + *(_DWORD *)(v7 + 352) - *(_DWORD *)v35;
  }
  else
  {
    memset_0(*(void **)(v7 + 256), 0, *(_QWORD *)(v7 + 264));
    v24 = *(_QWORD *)(v7 + 264);
  }
LABEL_57:
  v37 = v9 - v12;
  *v39 = *(_QWORD *)(v7 + 256);
  *v40 = v24;
  *a4 = *(_QWORD *)(v7 + 208);
  *(_QWORD *)(v7 + 208) += v24;
  *(_QWORD *)(v7 + 216) -= v37;
  *(_QWORD *)(v7 + 160) += v37;
  *(_DWORD *)(v7 + 272) += v37;
  *(_QWORD *)(v7 + 224) += v37;
  return 0;
}

```

## disassembly

```asm
0x1800d2d48  mov     r11, rsp
0x1800d2d4b  mov     [r11+20h], rbx
0x1800d2d4f  mov     [r11+18h], r8
0x1800d2d53  mov     [r11+10h], rdx
0x1800d2d57  push    rbp
0x1800d2d58  push    rsi
0x1800d2d59  push    rdi
0x1800d2d5a  push    r12
0x1800d2d5c  push    r13
0x1800d2d5e  push    r14
0x1800d2d60  push    r15
0x1800d2d62  sub     rsp, 20h
0x1800d2d66  mov     rax, [rcx+818h]
0x1800d2d6d  lea     r8, [r11+8]
0x1800d2d71  mov     rbp, rcx
0x1800d2d74  mov     qword ptr [r11+8], 0
0x1800d2d7c  mov     rcx, [rcx+278h]
0x1800d2d83  mov     r15d, 1
0x1800d2d89  mov     edx, r15d
0x1800d2d8c  mov     r13, r9
0x1800d2d8f  mov     rbx, [rax]
0x1800d2d92  call    __archive_read_filter_ahead
0x1800d2d97  mov     rdi, [rsp+58h+arg_0]
0x1800d2d9c  mov     r12, rax
0x1800d2d9f  test    rdi, rdi
0x1800d2da2  jg      short loc_1800D2DC2
0x1800d2da4  lea     r8, aTruncatedZisof; "Truncated zisofs file body"
0x1800d2dab  mov     edx, 2Ah ; '*'
0x1800d2db0  mov     rcx, rbp
0x1800d2db3  call    archive_set_error
0x1800d2db8  mov     eax, 0FFFFFFE2h
0x1800d2dbd  jmp     loc_1800D3217
0x1800d2dc2  mov     rax, [rbx+0D8h]
0x1800d2dc9  cmp     rdi, rax
0x1800d2dcc  cmovg   rdi, rax
0x1800d2dd0  cmp     dword ptr [rbx+0F8h], 0
0x1800d2dd7  mov     rsi, rdi
0x1800d2dda  jnz     loc_1800D300A
0x1800d2de0  mov     ecx, [rbx+0ECh]
0x1800d2de6  mov     rdx, r15
0x1800d2de9  mov     r8, [rbx+0F0h]
0x1800d2df0  dec     r8
0x1800d2df3  shl     rdx, cl
0x1800d2df6  add     r8, rdx
0x1800d2df9  shr     r8, cl
0x1800d2dfc  lea     r14, ds:4[r8*4]
0x1800d2e04  cmp     [rbx+140h], r14
0x1800d2e0b  jnb     short loc_1800D2E52
0x1800d2e0d  mov     rcx, [rbx+138h]; Block
0x1800d2e14  test    rcx, rcx
0x1800d2e17  jz      short loc_1800D2E1F
0x1800d2e19  call    cs:__imp_free
0x1800d2e1f  mov     r15, r14
0x1800d2e22  and     r15, 0FFFFFFFFFFFFFC00h
0x1800d2e29  add     r15, 400h
0x1800d2e30  mov     rcx, r15; Size
0x1800d2e33  call    cs:__imp_malloc
0x1800d2e39  mov     [rbx+138h], rax
0x1800d2e40  test    rax, rax
0x1800d2e43  jz      short loc_1800D2E95
0x1800d2e45  mov     [rbx+140h], r15
0x1800d2e4c  mov     r15d, 1
0x1800d2e52  mov     ecx, [rbx+0ECh]
0x1800d2e58  mov     [rbx+148h], r14
0x1800d2e5f  mov     r14, r15
0x1800d2e62  shl     r14, cl
0x1800d2e65  cmp     [rbx+108h], r14
0x1800d2e6c  jnb     short loc_1800D2EA6
0x1800d2e6e  mov     rcx, [rbx+100h]; Block
0x1800d2e75  test    rcx, rcx
0x1800d2e78  jz      short loc_1800D2E80
0x1800d2e7a  call    cs:__imp_free
0x1800d2e80  mov     rcx, r14; Size
0x1800d2e83  call    cs:__imp_malloc
0x1800d2e89  mov     [rbx+100h], rax
0x1800d2e90  test    rax, rax
0x1800d2e93  jnz     short loc_1800D2EA6
0x1800d2e95  lea     r8, aNoMemoryForZis; "No memory for zisofs decompression"
0x1800d2e9c  mov     edx, 0Ch
0x1800d2ea1  jmp     loc_1800D2DB0
0x1800d2ea6  mov     rax, [rbx+128h]
0x1800d2ead  mov     [rbx+108h], r14
0x1800d2eb4  cmp     rax, 10h
0x1800d2eb8  jnb     short loc_1800D2EF4
0x1800d2eba  mov     r14d, 10h
0x1800d2ec0  sub     r14, rax
0x1800d2ec3  cmp     rdi, r14
0x1800d2ec6  jnb     short loc_1800D2ECB
0x1800d2ec8  mov     r14, rdi
0x1800d2ecb  lea     rcx, [rax+114h]
0x1800d2ed2  mov     r8, r14; Size
0x1800d2ed5  add     rcx, rbx; void *
0x1800d2ed8  mov     rdx, r12; Src
0x1800d2edb  call    memcpy_0
0x1800d2ee0  add     [rbx+128h], r14
0x1800d2ee7  sub     rsi, r14
0x1800d2eea  mov     rax, [rbx+128h]
0x1800d2ef1  add     r12, r14
0x1800d2ef4  cmp     dword ptr [rbx+130h], 0
0x1800d2efb  jnz     short loc_1800D2F7C
0x1800d2efd  cmp     rax, 10h
0x1800d2f01  jnz     loc_1800D2FF2
0x1800d2f07  mov     rax, [rbx+114h]
0x1800d2f0e  xor     edx, edx
0x1800d2f10  cmp     rax, cs:qword_180133450
0x1800d2f17  movzx   eax, byte ptr [rbx+11Eh]
0x1800d2f1e  movzx   ecx, byte ptr [rbx+11Fh]
0x1800d2f25  cmovnz  edx, r15d
0x1800d2f29  shl     rcx, 8
0x1800d2f2d  or      rcx, rax
0x1800d2f30  movzx   eax, byte ptr [rbx+11Dh]
0x1800d2f37  shl     rcx, 8
0x1800d2f3b  or      rcx, rax
0x1800d2f3e  movzx   eax, byte ptr [rbx+11Ch]
0x1800d2f45  shl     rcx, 8
0x1800d2f49  or      rcx, rax
0x1800d2f4c  movzx   eax, byte ptr [rbx+121h]
0x1800d2f53  cmp     rcx, [rbx+0F0h]
0x1800d2f5a  cmovnz  edx, r15d
0x1800d2f5e  cmp     byte ptr [rbx+120h], 4
0x1800d2f65  cmovnz  edx, r15d
0x1800d2f69  cmp     eax, [rbx+0ECh]
0x1800d2f6f  jnz     short loc_1800D2FE6
0x1800d2f71  test    edx, edx
0x1800d2f73  jnz     short loc_1800D2FE6
0x1800d2f75  mov     [rbx+130h], r15d
0x1800d2f7c  mov     r15, [rbx+148h]
0x1800d2f83  xor     r14d, r14d
0x1800d2f86  mov     rcx, [rbx+150h]
0x1800d2f8d  cmp     rcx, r15
0x1800d2f90  jnb     short loc_1800D2FF7
0x1800d2f92  sub     r15, rcx
0x1800d2f95  mov     rdx, r12; Src
0x1800d2f98  cmp     rsi, r15
0x1800d2f9b  cmovb   r15, rsi
0x1800d2f9f  add     rcx, [rbx+138h]; void *
0x1800d2fa6  mov     r8, r15; Size
0x1800d2fa9  call    memcpy_0
0x1800d2fae  add     [rbx+150h], r15
0x1800d2fb5  sub     rsi, r15
0x1800d2fb8  mov     rax, [rbx+150h]
0x1800d2fbf  add     r12, r15
0x1800d2fc2  lea     r15d, [r14+1]
0x1800d2fc6  cmp     rax, [rbx+148h]
0x1800d2fcd  jnz     short loc_1800D2FFD
0x1800d2fcf  mov     [rbx+158h], r14
0x1800d2fd6  mov     [rbx+160h], r14d
0x1800d2fdd  mov     [rbx+0F8h], r15d
0x1800d2fe4  jmp     short loc_1800D2FFD
0x1800d2fe6  lea     r8, aIllegalZisofsF; "Illegal zisofs file body"
0x1800d2fed  jmp     loc_1800D2DAB
0x1800d2ff2  xor     r14d, r14d
0x1800d2ff5  jmp     short loc_1800D2FFD
0x1800d2ff7  mov     r15d, 1
0x1800d2ffd  cmp     dword ptr [rbx+0F8h], 0
0x1800d3004  jz      loc_1800D31CE
0x1800d300a  cmp     dword ptr [rbx+160h], 0
0x1800d3011  jnz     loc_1800D310E
0x1800d3017  mov     rdx, [rbx+158h]
0x1800d301e  lea     r9, [rdx+4]
0x1800d3022  cmp     r9, [rbx+148h]
0x1800d3029  jnb     loc_1800D3139
0x1800d302f  mov     r8, [rbx+138h]
0x1800d3036  movzx   eax, byte ptr [r8+rdx+2]
0x1800d303c  movzx   r10d, byte ptr [r8+rdx+3]
0x1800d3042  shl     r10d, 8
0x1800d3046  or      r10d, eax
0x1800d3049  movzx   eax, byte ptr [r8+rdx+1]
0x1800d304f  shl     r10d, 8
0x1800d3053  or      r10d, eax
0x1800d3056  movzx   eax, byte ptr [r8+rdx]
0x1800d305b  shl     r10d, 8
0x1800d305f  or      r10d, eax
0x1800d3062  mov     eax, [rbx+110h]
0x1800d3068  sub     rax, rsi
0x1800d306b  add     rax, rdi
0x1800d306e  cmp     r10, rax
0x1800d3071  jz      short loc_1800D307F
0x1800d3073  lea     r8, aIllegalZisofsB; "Illegal zisofs block pointers(cannot se"...
0x1800d307a  jmp     loc_1800D2DAB
0x1800d307f  movzx   eax, byte ptr [r8+rdx+6]
0x1800d3085  movzx   ecx, byte ptr [r8+rdx+7]
0x1800d308b  shl     ecx, 8
0x1800d308e  or      ecx, eax
0x1800d3090  movzx   eax, byte ptr [r8+rdx+5]
0x1800d3096  shl     ecx, 8
0x1800d3099  or      ecx, eax
0x1800d309b  movzx   eax, byte ptr [r8+rdx+4]
0x1800d30a1  shl     ecx, 8
0x1800d30a4  or      ecx, eax
0x1800d30a6  cmp     ecx, r10d
0x1800d30a9  jb      loc_1800D3139
0x1800d30af  sub     ecx, r10d
0x1800d30b2  mov     [rbx+158h], r9
0x1800d30b9  cmp     dword ptr [rbx+1C0h], 0
0x1800d30c0  mov     [rbx+160h], ecx
0x1800d30c6  lea     rcx, [rbx+168h]
0x1800d30cd  jz      short loc_1800D30D6
0x1800d30cf  call    inflateReset
0x1800d30d4  jmp     short loc_1800D30E0
0x1800d30d6  mov     edx, 0Fh
0x1800d30db  call    inflateInit2_
0x1800d30e0  test    eax, eax
0x1800d30e2  jz      short loc_1800D30F3
0x1800d30e4  lea     r8, aCanTInitialize_2; "Can't initialize zisofs decompression."
0x1800d30eb  or      edx, 0FFFFFFFFh
0x1800d30ee  jmp     loc_1800D2DB0
0x1800d30f3  mov     [rbx+1C0h], r15d
0x1800d30fa  mov     dword ptr [rbx+174h], 0
0x1800d3104  mov     dword ptr [rbx+184h], 0
0x1800d310e  mov     ecx, [rbx+160h]
0x1800d3114  test    ecx, ecx
0x1800d3116  jnz     short loc_1800D3145
0x1800d3118  mov     r8, [rbx+108h]; Size
0x1800d311f  xor     edx, edx; Val
0x1800d3121  mov     rcx, [rbx+100h]; void *
0x1800d3128  call    memset_0
0x1800d312d  mov     r14, [rbx+108h]
0x1800d3134  jmp     loc_1800D31CE
0x1800d3139  lea     r8, aIllegalZisofsB_0; "Illegal zisofs block pointers"
0x1800d3140  jmp     loc_1800D2DAB
0x1800d3145  lea     r15, [rbx+168h]
0x1800d314c  mov     [r15], r12
0x1800d314f  cmp     rsi, rcx
0x1800d3152  ja      short loc_1800D3156
0x1800d3154  mov     ecx, esi
0x1800d3156  mov     [rbx+170h], ecx
0x1800d315c  xor     edx, edx
0x1800d315e  mov     rax, [rbx+100h]
0x1800d3165  mov     rcx, r15
0x1800d3168  mov     [rbx+178h], rax
0x1800d316f  mov     eax, [rbx+108h]
0x1800d3175  mov     [rbx+180h], eax
0x1800d317b  call    inflate
0x1800d3180  test    eax, eax
0x1800d3182  jz      short loc_1800D31A3
0x1800d3184  cmp     eax, 1
0x1800d3187  jz      short loc_1800D31A3
0x1800d3189  mov     r9d, eax
0x1800d318c  lea     r8, aZisofsDecompre; "zisofs decompression failed (%d)"
0x1800d3193  or      edx, 0FFFFFFFFh
0x1800d3196  mov     rcx, rbp
0x1800d3199  call    archive_set_error
0x1800d319e  jmp     loc_1800D2DB8
0x1800d31a3  mov     eax, [rbx+180h]
0x1800d31a9  mov     r14, [rbx+108h]
0x1800d31b0  sub     r14, rax
0x1800d31b3  mov     rax, r12
0x1800d31b6  sub     rax, [r15]
0x1800d31b9  add     rsi, rax
0x1800d31bc  mov     eax, [rbx+160h]
0x1800d31c2  sub     eax, [r15]
0x1800d31c5  add     eax, r12d
0x1800d31c8  mov     [rbx+160h], eax
0x1800d31ce  mov     rax, [rbx+100h]
0x1800d31d5  sub     rdi, rsi
0x1800d31d8  mov     rcx, [rsp+58h+arg_8]
0x1800d31dd  mov     [rcx], rax
0x1800d31e0  mov     rax, [rsp+58h+arg_10]
0x1800d31e5  mov     [rax], r14
0x1800d31e8  mov     rax, [rbx+0D0h]
0x1800d31ef  mov     [r13+0], rax
0x1800d31f3  add     [rbx+0D0h], r14
0x1800d31fa  sub     [rbx+0D8h], rdi
0x1800d3201  add     [rbx+0A0h], rdi
0x1800d3208  add     [rbx+110h], edi
0x1800d320e  add     [rbx+0E0h], rdi
0x1800d3215  xor     eax, eax
0x1800d3217  mov     rbx, [rsp+58h+arg_18]
0x1800d321c  add     rsp, 20h
0x1800d3220  pop     r15
0x1800d3222  pop     r14
0x1800d3224  pop     r13
0x1800d3226  pop     r12
0x1800d3228  pop     rdi
0x1800d3229  pop     rsi
0x1800d322a  pop     rbp
0x1800d322b  retn
```
