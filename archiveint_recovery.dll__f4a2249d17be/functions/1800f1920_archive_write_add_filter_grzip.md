# archive_write_add_filter_grzip

- ea: `0x1800f1920`
- end: `0x1800f1a15`
- name: `archive_write_add_filter_grzip`
- size: `245`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18000523c`
- `0x180006c00`
- `0x1800efa88`
- `0x1800f1920`
- `0x1800f2a50`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x1800f1968`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x1800f1968`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800f19a6`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800f19a6`

## string_xrefs

- `0x1800f1937`: `archive_write_add_filter_grzip`
- `0x1800f19bd`: `Using external grzip program for grzip compression`

## pseudocode

```c
__int64 __fastcall archive_write_add_filter_grzip(__int64 a1)
{
  __int64 v2; // rsi
  _QWORD *v4; // rbx
  __int64 v5; // rax

  v2 = _archive_write_allocate_filter();
  if ( (unsigned int)_archive_check_magic(a1, 2965749982LL, 1, "archive_write_add_filter_grzip") == -30 )
    return 4294967266LL;
  v4 = calloc(1u, 8u);
  if ( !v4 )
  {
LABEL_4:
    archive_set_error(a1, 12, "Can't allocate memory");
    return 4294967266LL;
  }
  v5 = _archive_write_program_allocate("grzip");
  *v4 = v5;
  if ( !v5 )
  {
    free(v4);
    goto LABEL_4;
  }
  *(_QWORD *)(v2 + 80) = "grzip";
  *(_QWORD *)(v2 + 32) = archive_write_grzip_open;
  *(_DWORD *)(v2 + 88) = 12;
  *(_QWORD *)(v2 + 24) = archive_write_grzip_options;
  *(_QWORD *)(v2 + 72) = v4;
  *(_QWORD *)(v2 + 40) = archive_compressor_program_write;
  *(_QWORD *)(v2 + 56) = archive_compressor_program_close;
  *(_QWORD *)(v2 + 64) = archive_write_lrzip_free;
  archive_set_error(a1, 0xFFFFFFFFLL, "Using external grzip program for grzip compression");
  return 4294967276LL;
}

```

## disassembly

```asm
0x1800f1920  push    rbx
0x1800f1922  push    rsi
0x1800f1923  push    rdi
0x1800f1924  push    r14
0x1800f1926  sub     rsp, 28h
0x1800f192a  mov     rdi, rcx
0x1800f192d  call    __archive_write_allocate_filter
0x1800f1932  mov     ebx, 1
0x1800f1937  lea     r9, aArchiveWriteAd_16; "archive_write_add_filter_grzip"
0x1800f193e  mov     r8d, ebx
0x1800f1941  mov     edx, 0B0C5C0DEh
0x1800f1946  mov     rcx, rdi
0x1800f1949  mov     rsi, rax
0x1800f194c  call    __archive_check_magic
0x1800f1951  cmp     eax, 0FFFFFFE2h
0x1800f1954  jnz     short loc_1800F1960
0x1800f1956  mov     eax, 0FFFFFFE2h
0x1800f195b  jmp     loc_1800F1A0B
0x1800f1960  mov     edx, 8; Size
0x1800f1965  mov     rcx, rbx; Count
0x1800f1968  call    cs:__imp_calloc
0x1800f196e  mov     rbx, rax
0x1800f1971  test    rax, rax
0x1800f1974  jnz     short loc_1800F198C
0x1800f1976  lea     r8, aCanTAllocateMe_30; "Can't allocate memory"
0x1800f197d  mov     edx, 0Ch
0x1800f1982  mov     rcx, rdi
0x1800f1985  call    archive_set_error
0x1800f198a  jmp     short loc_1800F1956
0x1800f198c  lea     r14, aGrzip; "grzip"
0x1800f1993  mov     rcx, r14
0x1800f1996  call    __archive_write_program_allocate
0x1800f199b  mov     [rbx], rax
0x1800f199e  test    rax, rax
0x1800f19a1  jnz     short loc_1800F19AE
0x1800f19a3  mov     rcx, rbx; Block
0x1800f19a6  call    cs:__imp_free
0x1800f19ac  jmp     short loc_1800F1976
0x1800f19ae  lea     rax, archive_write_grzip_open
0x1800f19b5  mov     [rsi+50h], r14
0x1800f19b9  mov     [rsi+20h], rax
0x1800f19bd  lea     r8, aUsingExternalG_0; "Using external grzip program for grzip "...
0x1800f19c4  lea     rax, archive_write_grzip_options
0x1800f19cb  mov     dword ptr [rsi+58h], 0Ch
0x1800f19d2  mov     [rsi+18h], rax
0x1800f19d6  or      edx, 0FFFFFFFFh
0x1800f19d9  lea     rax, archive_compressor_program_write
0x1800f19e0  mov     [rsi+48h], rbx
0x1800f19e4  mov     [rsi+28h], rax
0x1800f19e8  mov     rcx, rdi
0x1800f19eb  lea     rax, archive_compressor_program_close
0x1800f19f2  mov     [rsi+38h], rax
0x1800f19f6  lea     rax, archive_write_lrzip_free
0x1800f19fd  mov     [rsi+40h], rax
0x1800f1a01  call    archive_set_error
0x1800f1a06  mov     eax, 0FFFFFFECh
0x1800f1a0b  add     rsp, 28h
0x1800f1a0f  pop     r14
0x1800f1a11  pop     rdi
0x1800f1a12  pop     rsi
0x1800f1a13  pop     rbx
0x1800f1a14  retn
```
