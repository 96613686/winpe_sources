# compression_init_encoder_xz

- ea: `0x1801104e4`
- end: `0x1801106ed`
- name: `compression_init_encoder_xz`
- size: `521`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1801128e8`

## callees

- `0x180006c00`
- `0x180015810`
- `0x180023c20`
- `0x180023d50`
- `0x180024c60`
- `0x18011004c`
- `0x1801104e4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x180110549`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x180110549`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180110581`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180110678`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180110691`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180110581`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180110678`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180110691`

## string_xrefs

- `0x180110697`: `Internal error initializing compression library: Cannot allocate memory`
- `0x180110587`: `Internal error initializing compression library`
- `0x18011067e`: `Internal error initializing compression library: It's a bug in liblzma`

## pseudocode

```c
__int64 __fastcall compression_init_encoder_xz(__int64 a1, __int64 a2, int a3, int a4)
{
  char *v8; // rdi
  const char *v9; // r8
  __int64 v10; // rdx
  int v11; // eax
  __int64 result; // rax
  _BYTE v13[4]; // [rsp+20h] [rbp-128h] BYREF
  int v14; // [rsp+24h] [rbp-124h]
  int v15; // [rsp+30h] [rbp-118h]
  char *v16; // [rsp+38h] [rbp-110h]
  int v17; // [rsp+40h] [rbp-108h]
  _BYTE v18[4]; // [rsp+A0h] [rbp-A8h] BYREF
  int v19; // [rsp+A4h] [rbp-A4h]

  v19 = 0;
  memset_0(v18, 0, 0x6Cu);
  memset_0(v13, 0, 0x80u);
  if ( *(_DWORD *)(a2 + 48) )
    compression_end_0(a1, a2);
  v8 = (char *)calloc(1u, 0xA8u);
  if ( !v8 )
  {
    v9 = "Can't allocate memory for xz stream";
LABEL_17:
    archive_set_error(a1, 12, v9);
    return 4294967266LL;
  }
  v10 = 9;
  if ( a3 <= 9 )
    v10 = (unsigned int)a3;
  if ( (unsigned __int8)lzma_lzma_preset(v18, v10) )
  {
    free(v8);
    v9 = "Internal error initializing compression library";
LABEL_16:
    *(_QWORD *)(a2 + 56) = 0;
    goto LABEL_17;
  }
  *((_QWORD *)v8 + 18) = v18;
  *((_QWORD *)v8 + 17) = 33;
  *((_QWORD *)v8 + 19) = -1;
  *(_OWORD *)v8 = xmmword_18013F460;
  *((_OWORD *)v8 + 1) = xmmword_18013F470;
  *((_OWORD *)v8 + 2) = xmmword_18013F480;
  *((_OWORD *)v8 + 3) = xmmword_18013F490;
  *((_OWORD *)v8 + 4) = xmmword_18013F4A0;
  *((_OWORD *)v8 + 5) = xmmword_18013F4B0;
  *((_OWORD *)v8 + 6) = xmmword_18013F4C0;
  *((_OWORD *)v8 + 7) = xmmword_18013F4D0;
  *((_QWORD *)v8 + 16) = 0;
  if ( a4 <= 1 )
  {
    v11 = lzma_stream_encoder(v8, v8 + 136, 4);
  }
  else
  {
    memset_0(v13, 0, 0x80u);
    v14 = a4;
    v15 = 300;
    v16 = v8 + 136;
    v17 = 4;
    v11 = lzma_stream_encoder_mt(v8, v13);
  }
  if ( v11 )
  {
    if ( v11 != 5 )
    {
      free(v8);
      *(_QWORD *)(a2 + 56) = 0;
      archive_set_error(a1, 0xFFFFFFFFLL, "Internal error initializing compression library: It's a bug in liblzma");
      return 4294967266LL;
    }
    free(v8);
    v9 = "Internal error initializing compression library: Cannot allocate memory";
    goto LABEL_16;
  }
  *(_QWORD *)(a2 + 56) = v8;
  *(_QWORD *)(a2 + 64) = compression_code_lzma_0;
  *(_QWORD *)(a2 + 72) = compression_end_lzma_0;
  result = 0;
  *(_DWORD *)(a2 + 48) = 1;
  return result;
}

```

## disassembly

```asm
0x1801104e4  push    rbx
0x1801104e6  push    rbp
0x1801104e7  push    rsi
0x1801104e8  push    rdi
0x1801104e9  push    r14
0x1801104eb  push    r15
0x1801104ed  sub     rsp, 118h
0x1801104f4  xor     eax, eax
0x1801104f6  mov     ebp, r8d
0x1801104f9  mov     rbx, rdx
0x1801104fc  mov     [rsp+148h+var_A4], eax
0x180110503  mov     rsi, rcx
0x180110506  xor     edx, edx; Val
0x180110508  lea     rcx, [rsp+148h+var_A8]; void *
0x180110510  mov     r15d, r9d
0x180110513  lea     r8d, [rax+6Ch]; Size
0x180110517  call    memset_0
0x18011051c  xor     edx, edx; Val
0x18011051e  lea     rcx, [rsp+148h+var_128]; void *
0x180110523  mov     r8d, 80h; Size
0x180110529  call    memset_0
0x18011052e  cmp     dword ptr [rbx+30h], 0
0x180110532  jz      short loc_18011053F
0x180110534  mov     rdx, rbx
0x180110537  mov     rcx, rsi
0x18011053a  call    compression_end_0
0x18011053f  mov     edx, 0A8h; Size
0x180110544  mov     ecx, 1; Count
0x180110549  call    cs:__imp_calloc
0x18011054f  mov     rdi, rax
0x180110552  test    rax, rax
0x180110555  jnz     short loc_180110563
0x180110557  lea     r8, aCanTAllocateMe; "Can't allocate memory for xz stream"
0x18011055e  jmp     loc_1801106A6
0x180110563  mov     edx, 9
0x180110568  lea     rcx, [rsp+148h+var_A8]
0x180110570  cmp     ebp, edx
0x180110572  cmovle  edx, ebp
0x180110575  call    lzma_lzma_preset
0x18011057a  test    al, al
0x18011057c  jz      short loc_180110593
0x18011057e  mov     rcx, rdi; Block
0x180110581  call    cs:__imp_free
0x180110587  lea     r8, aInternalErrorI_8; "Internal error initializing compression"...
0x18011058e  jmp     loc_18011069E
0x180110593  movaps  xmm0, cs:xmmword_18013F460
0x18011059a  lea     r14, [rdi+88h]
0x1801105a1  movaps  xmm1, cs:xmmword_18013F470
0x1801105a8  lea     rax, [rsp+148h+var_A8]
0x1801105b0  mov     [r14+8], rax
0x1801105b4  or      rbp, 0FFFFFFFFFFFFFFFFh
0x1801105b8  mov     rax, cs:qword_18013F4E0
0x1801105bf  mov     qword ptr [r14], 21h ; '!'
0x1801105c6  mov     [r14+10h], rbp
0x1801105ca  movups  xmmword ptr [rdi], xmm0
0x1801105cd  movaps  xmm0, cs:xmmword_18013F480
0x1801105d4  movups  xmmword ptr [rdi+10h], xmm1
0x1801105d8  movaps  xmm1, cs:xmmword_18013F490
0x1801105df  movups  xmmword ptr [rdi+20h], xmm0
0x1801105e3  movaps  xmm0, cs:xmmword_18013F4A0
0x1801105ea  movups  xmmword ptr [rdi+30h], xmm1
0x1801105ee  movaps  xmm1, cs:xmmword_18013F4B0
0x1801105f5  movups  xmmword ptr [rdi+40h], xmm0
0x1801105f9  movaps  xmm0, cs:xmmword_18013F4C0
0x180110600  movups  xmmword ptr [rdi+50h], xmm1
0x180110604  movaps  xmm1, cs:xmmword_18013F4D0
0x18011060b  movups  xmmword ptr [rdi+60h], xmm0
0x18011060f  movups  xmmword ptr [rdi+70h], xmm1
0x180110613  mov     [rdi+80h], rax
0x18011061a  cmp     r15d, 1
0x18011061e  jle     short loc_18011065B
0x180110620  xor     edx, edx; Val
0x180110622  lea     rcx, [rsp+148h+var_128]; void *
0x180110627  mov     r8d, 80h; Size
0x18011062d  call    memset_0
0x180110632  lea     rdx, [rsp+148h+var_128]
0x180110637  mov     [rsp+148h+var_124], r15d
0x18011063c  mov     rcx, rdi
0x18011063f  mov     [rsp+148h+var_118], 12Ch
0x180110647  mov     [rsp+148h+var_110], r14
0x18011064c  mov     [rsp+148h+var_108], 4
0x180110654  call    lzma_stream_encoder_mt
0x180110659  jmp     short loc_18011066C
0x18011065b  mov     r8d, 4
0x180110661  mov     rdx, r14
0x180110664  mov     rcx, rdi
0x180110667  call    lzma_stream_encoder
0x18011066c  test    eax, eax
0x18011066e  jz      short loc_1801106BA
0x180110670  mov     rcx, rdi; Block
0x180110673  cmp     eax, 5
0x180110676  jz      short loc_180110691
0x180110678  call    cs:__imp_free
0x18011067e  lea     r8, aInternalErrorI_11; "Internal error initializing compression"...
0x180110685  mov     qword ptr [rbx+38h], 0
0x18011068d  mov     edx, ebp
0x18011068f  jmp     short loc_1801106AB
0x180110691  call    cs:__imp_free
0x180110697  lea     r8, aInternalErrorI_0; "Internal error initializing compression"...
0x18011069e  mov     qword ptr [rbx+38h], 0
0x1801106a6  mov     edx, 0Ch
0x1801106ab  mov     rcx, rsi
0x1801106ae  call    archive_set_error
0x1801106b3  mov     eax, 0FFFFFFE2h
0x1801106b8  jmp     short loc_1801106DD
0x1801106ba  lea     rax, compression_code_lzma_0
0x1801106c1  mov     [rbx+38h], rdi
0x1801106c5  mov     [rbx+40h], rax
0x1801106c9  lea     rax, compression_end_lzma_0
0x1801106d0  mov     [rbx+48h], rax
0x1801106d4  xor     eax, eax
0x1801106d6  mov     dword ptr [rbx+30h], 1
0x1801106dd  add     rsp, 118h
0x1801106e4  pop     r15
0x1801106e6  pop     r14
0x1801106e8  pop     rdi
0x1801106e9  pop     rsi
0x1801106ea  pop     rbp
0x1801106eb  pop     rbx
0x1801106ec  retn
```
