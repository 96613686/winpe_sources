# archive_write_add_filter_zstd

- ea: `0x1800f43c0`
- end: `0x1800f44f4`
- name: `archive_write_add_filter_zstd`
- size: `308`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18000523c`
- `0x180006c00`
- `0x1800415a0`
- `0x1800efa88`
- `0x1800f43c0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x1800f440d`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x1800f440d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800f44d0`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800f44d0`

## string_xrefs

- `0x1800f43dc`: `archive_write_add_filter_zstd`
- `0x1800f44d6`: `Failed to allocate zstd compressor object`

## pseudocode

```c
__int64 __fastcall archive_write_add_filter_zstd(__int64 a1)
{
  __int64 v2; // rdi
  _QWORD *v4; // rax
  __int64 v5; // rdx
  __int64 v6; // rcx
  _QWORD *v7; // rbx
  __int64 CStream; // rax

  v2 = _archive_write_allocate_filter();
  if ( (unsigned int)_archive_check_magic(a1, 2965749982LL, 1, "archive_write_add_filter_zstd") == -30 )
    return 4294967266LL;
  v4 = calloc(1u, 0x78u);
  v7 = v4;
  if ( !v4 )
  {
    archive_set_error(a1, 12, "Out of memory");
    return 4294967266LL;
  }
  *(_QWORD *)(v2 + 72) = v4;
  *(_QWORD *)(v2 + 32) = archive_compressor_zstd_open;
  *(_QWORD *)(v2 + 24) = archive_compressor_zstd_options;
  *(_QWORD *)(v2 + 48) = archive_compressor_zstd_flush;
  *(_QWORD *)(v2 + 56) = archive_compressor_zstd_close;
  *(_QWORD *)(v2 + 64) = archive_compressor_zstd_free;
  *(_QWORD *)(v2 + 80) = "zstd";
  *(_DWORD *)(v2 + 88) = 14;
  v4[4] = -1;
  v4[6] = -1;
  *v4 = 3;
  *((_DWORD *)v4 + 2) = 0;
  *((_DWORD *)v4 + 4) = 0;
  v4[3] = 0;
  v4[5] = 0;
  v4[8] = 0;
  v4[9] = 0;
  CStream = ZSTD_createCStream(v6, v5);
  v7[11] = CStream;
  if ( !CStream )
  {
    free(v7);
    archive_set_error(a1, 12, "Failed to allocate zstd compressor object");
    return 4294967266LL;
  }
  return 0;
}

```

## disassembly

```asm
0x1800f43c0  mov     [rsp+arg_0], rbx
0x1800f43c5  mov     [rsp+arg_8], rsi
0x1800f43ca  push    rdi
0x1800f43cb  sub     rsp, 20h
0x1800f43cf  mov     rsi, rcx
0x1800f43d2  call    __archive_write_allocate_filter
0x1800f43d7  mov     ebx, 1
0x1800f43dc  lea     r9, aArchiveWriteAd_19; "archive_write_add_filter_zstd"
0x1800f43e3  mov     r8d, ebx
0x1800f43e6  mov     edx, 0B0C5C0DEh
0x1800f43eb  mov     rcx, rsi
0x1800f43ee  mov     rdi, rax
0x1800f43f1  call    __archive_check_magic
0x1800f43f6  cmp     eax, 0FFFFFFE2h
0x1800f43f9  jnz     short loc_1800F4405
0x1800f43fb  mov     eax, 0FFFFFFE2h
0x1800f4400  jmp     loc_1800F44E4
0x1800f4405  mov     edx, 78h ; 'x'; Size
0x1800f440a  mov     rcx, rbx; Count
0x1800f440d  call    cs:__imp_calloc
0x1800f4413  mov     rbx, rax
0x1800f4416  test    rax, rax
0x1800f4419  jnz     short loc_1800F4431
0x1800f441b  lea     r8, aOutOfMemory_0; "Out of memory"
0x1800f4422  mov     edx, 0Ch
0x1800f4427  mov     rcx, rsi
0x1800f442a  call    archive_set_error
0x1800f442f  jmp     short loc_1800F43FB
0x1800f4431  mov     [rdi+48h], rbx
0x1800f4435  lea     rax, archive_compressor_zstd_open
0x1800f443c  mov     [rdi+20h], rax
0x1800f4440  lea     rax, archive_compressor_zstd_options
0x1800f4447  mov     [rdi+18h], rax
0x1800f444b  lea     rax, archive_compressor_zstd_flush
0x1800f4452  mov     [rdi+30h], rax
0x1800f4456  lea     rax, archive_compressor_zstd_close
0x1800f445d  mov     [rdi+38h], rax
0x1800f4461  lea     rax, archive_compressor_zstd_free
0x1800f4468  mov     [rdi+40h], rax
0x1800f446c  lea     rax, aZstd; "zstd"
0x1800f4473  mov     [rdi+50h], rax
0x1800f4477  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800f447b  mov     dword ptr [rdi+58h], 0Eh
0x1800f4482  mov     [rbx+20h], rax
0x1800f4486  mov     [rbx+30h], rax
0x1800f448a  mov     qword ptr [rbx], 3
0x1800f4491  mov     dword ptr [rbx+8], 0
0x1800f4498  mov     dword ptr [rbx+10h], 0
0x1800f449f  mov     qword ptr [rbx+18h], 0
0x1800f44a7  mov     qword ptr [rbx+28h], 0
0x1800f44af  mov     qword ptr [rbx+40h], 0
0x1800f44b7  mov     qword ptr [rbx+48h], 0
0x1800f44bf  call    ZSTD_createCStream
0x1800f44c4  mov     [rbx+58h], rax
0x1800f44c8  test    rax, rax
0x1800f44cb  jnz     short loc_1800F44E2
0x1800f44cd  mov     rcx, rbx; Block
0x1800f44d0  call    cs:__imp_free
0x1800f44d6  lea     r8, aFailedToAlloca; "Failed to allocate zstd compressor obje"...
0x1800f44dd  jmp     loc_1800F4422
0x1800f44e2  xor     eax, eax
0x1800f44e4  mov     rbx, [rsp+28h+arg_0]
0x1800f44e9  mov     rsi, [rsp+28h+arg_8]
0x1800f44ee  add     rsp, 20h
0x1800f44f2  pop     rdi
0x1800f44f3  retn
```
