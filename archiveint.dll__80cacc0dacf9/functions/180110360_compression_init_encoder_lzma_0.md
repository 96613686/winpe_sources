# compression_init_encoder_lzma_0

- ea: `0x180110360`
- end: `0x1801104db`
- name: `compression_init_encoder_lzma_0`
- size: `379`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1801128e8`

## callees

- `0x180006c00`
- `0x180015810`
- `0x180023a50`
- `0x180023c20`
- `0x18011004c`
- `0x180110360`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x1801103c8`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x1801103c8`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180110460`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18011047a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180110460`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18011047a`

## string_xrefs

- `0x180110480`: `Internal error initializing compression library: Cannot allocate memory`
- `0x1801103b2`: `Internal error initializing compression library`
- `0x180110466`: `Internal error initializing compression library: It's a bug in liblzma`

## pseudocode

```c
__int64 __fastcall compression_init_encoder_lzma_0(__int64 a1, __int64 a2, unsigned int a3)
{
  const char *v6; // r8
  _OWORD *v7; // rax
  void *v8; // rdi
  int v9; // eax
  __int64 result; // rax
  _BYTE v11[4]; // [rsp+20h] [rbp-78h] BYREF
  int v12; // [rsp+24h] [rbp-74h]

  v12 = 0;
  memset_0(v11, 0, 0x6Cu);
  if ( *(_DWORD *)(a2 + 48) )
    compression_end_0(a1, a2);
  if ( (unsigned __int8)lzma_lzma_preset(v11, a3) )
  {
    v6 = "Internal error initializing compression library";
LABEL_11:
    *(_QWORD *)(a2 + 56) = 0;
    goto LABEL_12;
  }
  v7 = calloc(1u, 0x88u);
  v8 = v7;
  if ( !v7 )
  {
    v6 = "Can't allocate memory for lzma stream";
LABEL_12:
    archive_set_error(a1, 12, v6);
    return 4294967266LL;
  }
  *v7 = xmmword_18013F460;
  v7[1] = xmmword_18013F470;
  v7[2] = xmmword_18013F480;
  v7[3] = xmmword_18013F490;
  v7[4] = xmmword_18013F4A0;
  v7[5] = xmmword_18013F4B0;
  v7[6] = xmmword_18013F4C0;
  v7[7] = xmmword_18013F4D0;
  *((_QWORD *)v7 + 16) = 0;
  v9 = lzma_alone_encoder(v7, v11);
  if ( v9 )
  {
    if ( v9 != 5 )
    {
      free(v8);
      *(_QWORD *)(a2 + 56) = 0;
      archive_set_error(a1, 0xFFFFFFFFLL, "Internal error initializing compression library: It's a bug in liblzma");
      return 4294967266LL;
    }
    free(v8);
    v6 = "Internal error initializing compression library: Cannot allocate memory";
    goto LABEL_11;
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
0x180110360  mov     [rsp+arg_0], rbx
0x180110365  mov     [rsp+arg_8], rsi
0x18011036a  push    rdi
0x18011036b  sub     rsp, 90h
0x180110372  xor     eax, eax
0x180110374  mov     edi, r8d
0x180110377  mov     rbx, rdx
0x18011037a  mov     [rsp+98h+var_74], eax
0x18011037e  mov     rsi, rcx
0x180110381  xor     edx, edx; Val
0x180110383  lea     rcx, [rsp+98h+var_78]; void *
0x180110388  lea     r8d, [rax+6Ch]; Size
0x18011038c  call    memset_0
0x180110391  cmp     dword ptr [rbx+30h], 0
0x180110395  jz      short loc_1801103A2
0x180110397  mov     rdx, rbx
0x18011039a  mov     rcx, rsi
0x18011039d  call    compression_end_0
0x1801103a2  mov     edx, edi
0x1801103a4  lea     rcx, [rsp+98h+var_78]
0x1801103a9  call    lzma_lzma_preset
0x1801103ae  test    al, al
0x1801103b0  jz      short loc_1801103BE
0x1801103b2  lea     r8, aInternalErrorI_8; "Internal error initializing compression"...
0x1801103b9  jmp     loc_180110487
0x1801103be  mov     edx, 88h; Size
0x1801103c3  mov     ecx, 1; Count
0x1801103c8  call    cs:__imp_calloc
0x1801103ce  mov     rdi, rax
0x1801103d1  test    rax, rax
0x1801103d4  jnz     short loc_1801103E2
0x1801103d6  lea     r8, aCanTAllocateMe_2; "Can't allocate memory for lzma stream"
0x1801103dd  jmp     loc_18011048F
0x1801103e2  movaps  xmm0, cs:xmmword_18013F460
0x1801103e9  lea     rdx, [rsp+98h+var_78]
0x1801103ee  movaps  xmm1, cs:xmmword_18013F470
0x1801103f5  mov     rcx, rdi
0x1801103f8  movups  xmmword ptr [rax], xmm0
0x1801103fb  movaps  xmm0, cs:xmmword_18013F480
0x180110402  movups  xmmword ptr [rax+10h], xmm1
0x180110406  movaps  xmm1, cs:xmmword_18013F490
0x18011040d  movups  xmmword ptr [rax+20h], xmm0
0x180110411  movaps  xmm0, cs:xmmword_18013F4A0
0x180110418  movups  xmmword ptr [rax+30h], xmm1
0x18011041c  movaps  xmm1, cs:xmmword_18013F4B0
0x180110423  movups  xmmword ptr [rax+40h], xmm0
0x180110427  movaps  xmm0, cs:xmmword_18013F4C0
0x18011042e  movups  xmmword ptr [rax+50h], xmm1
0x180110432  movaps  xmm1, cs:xmmword_18013F4D0
0x180110439  movups  xmmword ptr [rax+60h], xmm0
0x18011043d  movups  xmmword ptr [rax+70h], xmm1
0x180110441  mov     rax, cs:qword_18013F4E0
0x180110448  mov     [rdi+80h], rax
0x18011044f  call    lzma_alone_encoder
0x180110454  test    eax, eax
0x180110456  jz      short loc_1801104A3
0x180110458  mov     rcx, rdi; Block
0x18011045b  cmp     eax, 5
0x18011045e  jz      short loc_18011047A
0x180110460  call    cs:__imp_free
0x180110466  lea     r8, aInternalErrorI_11; "Internal error initializing compression"...
0x18011046d  mov     qword ptr [rbx+38h], 0
0x180110475  or      edx, 0FFFFFFFFh
0x180110478  jmp     short loc_180110494
0x18011047a  call    cs:__imp_free
0x180110480  lea     r8, aInternalErrorI_0; "Internal error initializing compression"...
0x180110487  mov     qword ptr [rbx+38h], 0
0x18011048f  mov     edx, 0Ch
0x180110494  mov     rcx, rsi
0x180110497  call    archive_set_error
0x18011049c  mov     eax, 0FFFFFFE2h
0x1801104a1  jmp     short loc_1801104C6
0x1801104a3  lea     rax, compression_code_lzma_0
0x1801104aa  mov     [rbx+38h], rdi
0x1801104ae  mov     [rbx+40h], rax
0x1801104b2  lea     rax, compression_end_lzma_0
0x1801104b9  mov     [rbx+48h], rax
0x1801104bd  xor     eax, eax
0x1801104bf  mov     dword ptr [rbx+30h], 1
0x1801104c6  lea     r11, [rsp+98h+var_8]
0x1801104ce  mov     rbx, [r11+10h]
0x1801104d2  mov     rsi, [r11+18h]
0x1801104d6  mov     rsp, r11
0x1801104d9  pop     rdi
0x1801104da  retn
```
