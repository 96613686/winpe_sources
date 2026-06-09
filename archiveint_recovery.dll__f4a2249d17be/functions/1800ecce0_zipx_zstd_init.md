# zipx_zstd_init

- ea: `0x1800ecce0`
- end: `0x1800ecdbe`
- name: `zipx_zstd_init`
- size: `222`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800eb780`

## callees

- `0x180006c00`
- `0x180039460`
- `0x180039580`
- `0x18003baa0`
- `0x18003c050`
- `0x18003c3b0`
- `0x18003c3d0`
- `0x1800ecce0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800ecd65`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800ecd65`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800ecd7a`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800ecd7a`

## string_xrefs

- `0x1800ecd3e`: `Error initializing zstd decompressor: %s`
- `0x1800ecd8c`: `No memory for Zstd decompression`

## pseudocode

```c
__int64 __fastcall zipx_zstd_init(__int64 a1, __int64 a2)
{
  void **v2; // rdi
  __int64 DStream; // rax
  __int64 inited; // rdi
  const char *ErrorName; // rax
  void *v9; // rcx
  size_t v10; // rax
  void *v11; // rax

  v2 = (void **)(a2 + 512);
  if ( *(_BYTE *)(a2 + 520) )
  {
    ZSTD_freeDStream(*v2);
    *(_BYTE *)(a2 + 520) = 0;
  }
  DStream = ZSTD_createDStream();
  *v2 = (void *)DStream;
  inited = ZSTD_initDStream(DStream);
  if ( (unsigned int)ZSTD_isError(inited) )
  {
    ErrorName = (const char *)ZSTD_getErrorName(inited);
    archive_set_error(a1, 0xFFFFFFFFLL, "Error initializing zstd decompressor: %s", ErrorName);
    return 4294967271LL;
  }
  else
  {
    v9 = *(void **)(a2 + 168);
    *(_BYTE *)(a2 + 520) = 1;
    free(v9);
    v10 = ZSTD_DStreamOutSize();
    *(_QWORD *)(a2 + 176) = v10;
    v11 = malloc(v10);
    *(_QWORD *)(a2 + 168) = v11;
    if ( v11 )
    {
      *(_BYTE *)(a2 + 161) = 1;
      return 0;
    }
    else
    {
      archive_set_error(a1, 12, "No memory for Zstd decompression");
      return 4294967266LL;
    }
  }
}

```

## disassembly

```asm
0x1800ecce0  mov     [rsp+arg_0], rbx
0x1800ecce5  mov     [rsp+arg_8], rsi
0x1800eccea  push    rdi
0x1800ecceb  sub     rsp, 20h
0x1800eccef  cmp     byte ptr [rdx+208h], 0
0x1800eccf6  lea     rdi, [rdx+200h]
0x1800eccfd  mov     rbx, rdx
0x1800ecd00  mov     rsi, rcx
0x1800ecd03  jz      short loc_1800ECD14
0x1800ecd05  mov     rcx, [rdi]; Block
0x1800ecd08  call    ZSTD_freeDStream
0x1800ecd0d  mov     byte ptr [rbx+208h], 0
0x1800ecd14  call    ZSTD_createDStream
0x1800ecd19  mov     rcx, rax
0x1800ecd1c  mov     [rdi], rax
0x1800ecd1f  call    ZSTD_initDStream
0x1800ecd24  mov     rcx, rax
0x1800ecd27  mov     rdi, rax
0x1800ecd2a  call    ZSTD_isError
0x1800ecd2f  test    eax, eax
0x1800ecd31  jz      short loc_1800ECD57
0x1800ecd33  mov     rcx, rdi
0x1800ecd36  call    ZSTD_getErrorName
0x1800ecd3b  mov     r9, rax
0x1800ecd3e  lea     r8, aErrorInitializ; "Error initializing zstd decompressor: %"...
0x1800ecd45  or      edx, 0FFFFFFFFh
0x1800ecd48  mov     rcx, rsi
0x1800ecd4b  call    archive_set_error
0x1800ecd50  mov     eax, 0FFFFFFE7h
0x1800ecd55  jmp     short loc_1800ECDAE
0x1800ecd57  mov     rcx, [rbx+0A8h]; Block
0x1800ecd5e  mov     byte ptr [rbx+208h], 1
0x1800ecd65  call    cs:__imp_free
0x1800ecd6b  call    ZSTD_DStreamOutSize
0x1800ecd70  mov     rcx, rax; Size
0x1800ecd73  mov     [rbx+0B0h], rax
0x1800ecd7a  call    cs:__imp_malloc
0x1800ecd80  mov     [rbx+0A8h], rax
0x1800ecd87  test    rax, rax
0x1800ecd8a  jnz     short loc_1800ECDA5
0x1800ecd8c  lea     r8, aNoMemoryForZst; "No memory for Zstd decompression"
0x1800ecd93  mov     rcx, rsi
0x1800ecd96  lea     edx, [rax+0Ch]
0x1800ecd99  call    archive_set_error
0x1800ecd9e  mov     eax, 0FFFFFFE2h
0x1800ecda3  jmp     short loc_1800ECDAE
0x1800ecda5  mov     byte ptr [rbx+0A1h], 1
0x1800ecdac  xor     eax, eax
0x1800ecdae  mov     rbx, [rsp+28h+arg_0]
0x1800ecdb3  mov     rsi, [rsp+28h+arg_8]
0x1800ecdb8  add     rsp, 20h
0x1800ecdbc  pop     rdi
0x1800ecdbd  retn
```
