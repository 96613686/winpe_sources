# compression_init_encoder_lzma

- ea: `0x1800f9e3c`
- end: `0x1800fa056`
- name: `compression_init_encoder_lzma`
- size: `538`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800f8c94`

## callees

- `0x180006c00`
- `0x180015810`
- `0x180023c20`
- `0x180024760`
- `0x1800247b0`
- `0x180024820`
- `0x1800f9a30`
- `0x1800f9e3c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x1800f9e89`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x1800f9e89`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800f9ebe`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800f9f01`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800f9f2e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800f9f52`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800f9fe0`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800f9ffa`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800f9ebe`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800f9f01`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800f9f2e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800f9f52`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800f9fe0`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800f9ffa`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800f9f1c`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800f9f1c`

## string_xrefs

- `0x1800fa000`: `Internal error initializing compression library: Cannot allocate memory`
- `0x1800f9ec4`: `Internal error initializing compression library`
- `0x1800f9fe6`: `Internal error initializing compression library: It's a bug in liblzma`

## pseudocode

```c
__int64 __fastcall compression_init_encoder_lzma(__int64 a1, __int64 a2, int a3, __int64 a4)
{
  char *v8; // rdi
  const char *v9; // r8
  __int64 v10; // rdx
  _DWORD *v11; // rbp
  void *v12; // rax
  int v13; // eax
  __int64 v14; // rdx
  __int64 result; // rax
  _BYTE v16[4]; // [rsp+20h] [rbp-A8h] BYREF
  int v17; // [rsp+24h] [rbp-A4h]

  v17 = 0;
  memset_0(v16, 0, 0x6Cu);
  if ( *(_DWORD *)(a2 + 64) )
    compression_end(a1, a2);
  v8 = (char *)calloc(1u, 0xA8u);
  if ( !v8 )
  {
    v9 = "Can't allocate memory for lzma stream";
LABEL_22:
    v14 = 12;
    goto LABEL_23;
  }
  v10 = 9;
  if ( a3 <= 9 )
    v10 = (unsigned int)a3;
  if ( (unsigned __int8)lzma_lzma_preset(v16, v10) )
  {
    free(v8);
    v9 = "Internal error initializing compression library";
LABEL_21:
    *(_QWORD *)(a2 + 72) = 0;
    goto LABEL_22;
  }
  *((_QWORD *)v8 + 17) = a4;
  v11 = (_DWORD *)(a2 + 48);
  *((_QWORD *)v8 + 18) = v16;
  *((_QWORD *)v8 + 19) = -1;
  if ( (unsigned int)lzma_properties_size(a2 + 48, v8 + 136) )
  {
    free(v8);
    v9 = "lzma_properties_size failed";
    goto LABEL_19;
  }
  if ( *v11 )
  {
    v12 = malloc((unsigned int)*v11);
    *(_QWORD *)(a2 + 56) = v12;
    if ( !v12 )
    {
      free(v8);
      v9 = "Cannot allocate memory";
      goto LABEL_21;
    }
    if ( (unsigned int)lzma_properties_encode(v8 + 136, v12) )
    {
      free(v8);
      v9 = "lzma_properties_encode failed";
      goto LABEL_19;
    }
  }
  *(_OWORD *)v8 = xmmword_18013F460;
  *((_OWORD *)v8 + 1) = xmmword_18013F470;
  *((_OWORD *)v8 + 2) = xmmword_18013F480;
  *((_OWORD *)v8 + 3) = xmmword_18013F490;
  *((_OWORD *)v8 + 4) = xmmword_18013F4A0;
  *((_OWORD *)v8 + 5) = xmmword_18013F4B0;
  *((_OWORD *)v8 + 6) = xmmword_18013F4C0;
  *((_OWORD *)v8 + 7) = xmmword_18013F4D0;
  *((_QWORD *)v8 + 16) = 0;
  v13 = lzma_raw_encoder(v8, v8 + 136);
  if ( v13 )
  {
    if ( v13 == 5 )
    {
      free(v8);
      v9 = "Internal error initializing compression library: Cannot allocate memory";
      goto LABEL_21;
    }
    free(v8);
    v9 = "Internal error initializing compression library: It's a bug in liblzma";
LABEL_19:
    *(_QWORD *)(a2 + 72) = 0;
    v14 = 0xFFFFFFFFLL;
LABEL_23:
    archive_set_error(a1, v14, v9);
    return 4294967266LL;
  }
  *(_QWORD *)(a2 + 72) = v8;
  *(_QWORD *)(a2 + 80) = compression_code_lzma;
  *(_QWORD *)(a2 + 88) = compression_end_lzma;
  result = 0;
  *(_DWORD *)(a2 + 64) = 1;
  return result;
}

```

## disassembly

```asm
0x1800f9e3c  push    rbx
0x1800f9e3e  push    rbp
0x1800f9e3f  push    rsi
0x1800f9e40  push    rdi
0x1800f9e41  push    r14
0x1800f9e43  push    r15
0x1800f9e45  sub     rsp, 98h
0x1800f9e4c  xor     eax, eax
0x1800f9e4e  mov     ebp, r8d
0x1800f9e51  mov     rbx, rdx
0x1800f9e54  mov     [rsp+0C8h+var_A4], eax
0x1800f9e58  mov     rsi, rcx
0x1800f9e5b  xor     edx, edx; Val
0x1800f9e5d  lea     rcx, [rsp+0C8h+var_A8]; void *
0x1800f9e62  mov     r15, r9
0x1800f9e65  lea     r8d, [rax+6Ch]; Size
0x1800f9e69  call    memset_0
0x1800f9e6e  cmp     dword ptr [rbx+40h], 0
0x1800f9e72  jz      short loc_1800F9E7F
0x1800f9e74  mov     rdx, rbx
0x1800f9e77  mov     rcx, rsi
0x1800f9e7a  call    compression_end
0x1800f9e7f  mov     edx, 0A8h; Size
0x1800f9e84  mov     ecx, 1; Count
0x1800f9e89  call    cs:__imp_calloc
0x1800f9e8f  mov     rdi, rax
0x1800f9e92  test    rax, rax
0x1800f9e95  jnz     short loc_1800F9EA3
0x1800f9e97  lea     r8, aCanTAllocateMe_2; "Can't allocate memory for lzma stream"
0x1800f9e9e  jmp     loc_1800FA00F
0x1800f9ea3  mov     edx, 9
0x1800f9ea8  lea     rcx, [rsp+0C8h+var_A8]
0x1800f9ead  cmp     ebp, edx
0x1800f9eaf  cmovle  edx, ebp
0x1800f9eb2  call    lzma_lzma_preset
0x1800f9eb7  test    al, al
0x1800f9eb9  jz      short loc_1800F9ED0
0x1800f9ebb  mov     rcx, rdi; Block
0x1800f9ebe  call    cs:__imp_free
0x1800f9ec4  lea     r8, aInternalErrorI_8; "Internal error initializing compression"...
0x1800f9ecb  jmp     loc_1800FA007
0x1800f9ed0  lea     r14, [rdi+88h]
0x1800f9ed7  mov     [r14], r15
0x1800f9eda  lea     rax, [rsp+0C8h+var_A8]
0x1800f9edf  lea     rbp, [rbx+30h]
0x1800f9ee3  mov     [r14+8], rax
0x1800f9ee7  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800f9eeb  mov     rdx, r14
0x1800f9eee  mov     rcx, rbp
0x1800f9ef1  mov     [r14+10h], r15
0x1800f9ef5  call    lzma_properties_size
0x1800f9efa  test    eax, eax
0x1800f9efc  jz      short loc_1800F9F13
0x1800f9efe  mov     rcx, rdi; Block
0x1800f9f01  call    cs:__imp_free
0x1800f9f07  lea     r8, aLzmaProperties; "lzma_properties_size failed"
0x1800f9f0e  jmp     loc_1800F9FED
0x1800f9f13  cmp     dword ptr [rbp+0], 0
0x1800f9f17  jz      short loc_1800F9F64
0x1800f9f19  mov     ecx, [rbp+0]; Size
0x1800f9f1c  call    cs:__imp_malloc
0x1800f9f22  mov     [rbx+38h], rax
0x1800f9f26  test    rax, rax
0x1800f9f29  jnz     short loc_1800F9F40
0x1800f9f2b  mov     rcx, rdi; Block
0x1800f9f2e  call    cs:__imp_free
0x1800f9f34  lea     r8, aCannotAllocate; "Cannot allocate memory"
0x1800f9f3b  jmp     loc_1800FA007
0x1800f9f40  mov     rdx, rax
0x1800f9f43  mov     rcx, r14
0x1800f9f46  call    lzma_properties_encode
0x1800f9f4b  test    eax, eax
0x1800f9f4d  jz      short loc_1800F9F64
0x1800f9f4f  mov     rcx, rdi; Block
0x1800f9f52  call    cs:__imp_free
0x1800f9f58  lea     r8, aLzmaProperties_0; "lzma_properties_encode failed"
0x1800f9f5f  jmp     loc_1800F9FED
0x1800f9f64  movaps  xmm0, cs:xmmword_18013F460
0x1800f9f6b  mov     rdx, r14
0x1800f9f6e  movaps  xmm1, cs:xmmword_18013F470
0x1800f9f75  mov     rcx, rdi
0x1800f9f78  mov     rax, cs:qword_18013F4E0
0x1800f9f7f  movups  xmmword ptr [rdi], xmm0
0x1800f9f82  movaps  xmm0, cs:xmmword_18013F480
0x1800f9f89  movups  xmmword ptr [rdi+10h], xmm1
0x1800f9f8d  movaps  xmm1, cs:xmmword_18013F490
0x1800f9f94  movups  xmmword ptr [rdi+20h], xmm0
0x1800f9f98  movaps  xmm0, cs:xmmword_18013F4A0
0x1800f9f9f  movups  xmmword ptr [rdi+30h], xmm1
0x1800f9fa3  movaps  xmm1, cs:xmmword_18013F4B0
0x1800f9faa  movups  xmmword ptr [rdi+40h], xmm0
0x1800f9fae  movaps  xmm0, cs:xmmword_18013F4C0
0x1800f9fb5  movups  xmmword ptr [rdi+50h], xmm1
0x1800f9fb9  movaps  xmm1, cs:xmmword_18013F4D0
0x1800f9fc0  movups  xmmword ptr [rdi+60h], xmm0
0x1800f9fc4  movups  xmmword ptr [rdi+70h], xmm1
0x1800f9fc8  mov     [rdi+80h], rax
0x1800f9fcf  call    lzma_raw_encoder
0x1800f9fd4  test    eax, eax
0x1800f9fd6  jz      short loc_1800FA023
0x1800f9fd8  mov     rcx, rdi; Block
0x1800f9fdb  cmp     eax, 5
0x1800f9fde  jz      short loc_1800F9FFA
0x1800f9fe0  call    cs:__imp_free
0x1800f9fe6  lea     r8, aInternalErrorI_11; "Internal error initializing compression"...
0x1800f9fed  mov     qword ptr [rbx+48h], 0
0x1800f9ff5  mov     edx, r15d
0x1800f9ff8  jmp     short loc_1800FA014
0x1800f9ffa  call    cs:__imp_free
0x1800fa000  lea     r8, aInternalErrorI_0; "Internal error initializing compression"...
0x1800fa007  mov     qword ptr [rbx+48h], 0
0x1800fa00f  mov     edx, 0Ch
0x1800fa014  mov     rcx, rsi
0x1800fa017  call    archive_set_error
0x1800fa01c  mov     eax, 0FFFFFFE2h
0x1800fa021  jmp     short loc_1800FA046
0x1800fa023  lea     rax, compression_code_lzma
0x1800fa02a  mov     [rbx+48h], rdi
0x1800fa02e  mov     [rbx+50h], rax
0x1800fa032  lea     rax, compression_end_lzma
0x1800fa039  mov     [rbx+58h], rax
0x1800fa03d  xor     eax, eax
0x1800fa03f  mov     dword ptr [rbx+40h], 1
0x1800fa046  add     rsp, 98h
0x1800fa04d  pop     r15
0x1800fa04f  pop     r14
0x1800fa051  pop     rdi
0x1800fa052  pop     rsi
0x1800fa053  pop     rbp
0x1800fa054  pop     rbx
0x1800fa055  retn
```
