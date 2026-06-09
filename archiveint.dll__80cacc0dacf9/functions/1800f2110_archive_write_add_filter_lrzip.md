# archive_write_add_filter_lrzip

- ea: `0x1800f2110`
- end: `0x1800f2205`
- name: `archive_write_add_filter_lrzip`
- size: `245`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18000523c`
- `0x180006c00`
- `0x1800efa88`
- `0x1800f2110`
- `0x1800f2a50`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x1800f2158`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x1800f2158`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800f2196`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800f2196`

## string_xrefs

- `0x1800f2127`: `archive_write_add_filter_lrzip`
- `0x1800f21ad`: `Using external lrzip program for lrzip compression`

## pseudocode

```c
__int64 __fastcall archive_write_add_filter_lrzip(__int64 a1)
{
  __int64 v2; // rdi
  _QWORD *v4; // rbx
  __int64 v5; // rax

  v2 = _archive_write_allocate_filter();
  if ( (unsigned int)_archive_check_magic(a1, 2965749982LL, 1, "archive_write_add_filter_lrzip") == -30 )
    return 4294967266LL;
  v4 = calloc(1u, 0x10u);
  if ( !v4 )
  {
LABEL_4:
    archive_set_error(a1, 12, "Can't allocate memory");
    return 4294967266LL;
  }
  v5 = _archive_write_program_allocate("lrzip");
  *v4 = v5;
  if ( !v5 )
  {
    free(v4);
    goto LABEL_4;
  }
  *(_QWORD *)(v2 + 80) = "lrzip";
  *(_QWORD *)(v2 + 32) = archive_write_lrzip_open;
  *(_DWORD *)(v2 + 88) = 10;
  *(_QWORD *)(v2 + 24) = &archive_write_lrzip_options;
  *(_QWORD *)(v2 + 72) = v4;
  *(_QWORD *)(v2 + 40) = archive_compressor_program_write;
  *(_QWORD *)(v2 + 56) = archive_compressor_program_close;
  *(_QWORD *)(v2 + 64) = archive_write_lrzip_free;
  archive_set_error(a1, 0xFFFFFFFFLL, "Using external lrzip program for lrzip compression");
  return 4294967276LL;
}

```

## disassembly

```asm
0x1800f2110  push    rbx
0x1800f2112  push    rsi
0x1800f2113  push    rdi
0x1800f2114  push    r14
0x1800f2116  sub     rsp, 28h
0x1800f211a  mov     rsi, rcx
0x1800f211d  call    __archive_write_allocate_filter
0x1800f2122  mov     ebx, 1
0x1800f2127  lea     r9, aArchiveWriteAd_22; "archive_write_add_filter_lrzip"
0x1800f212e  mov     r8d, ebx
0x1800f2131  mov     edx, 0B0C5C0DEh
0x1800f2136  mov     rcx, rsi
0x1800f2139  mov     rdi, rax
0x1800f213c  call    __archive_check_magic
0x1800f2141  cmp     eax, 0FFFFFFE2h
0x1800f2144  jnz     short loc_1800F2150
0x1800f2146  mov     eax, 0FFFFFFE2h
0x1800f214b  jmp     loc_1800F21FB
0x1800f2150  mov     edx, 10h; Size
0x1800f2155  mov     rcx, rbx; Count
0x1800f2158  call    cs:__imp_calloc
0x1800f215e  mov     rbx, rax
0x1800f2161  test    rax, rax
0x1800f2164  jnz     short loc_1800F217C
0x1800f2166  lea     r8, aCanTAllocateMe_30; "Can't allocate memory"
0x1800f216d  mov     edx, 0Ch
0x1800f2172  mov     rcx, rsi
0x1800f2175  call    archive_set_error
0x1800f217a  jmp     short loc_1800F2146
0x1800f217c  lea     r14, aLrzip; "lrzip"
0x1800f2183  mov     rcx, r14
0x1800f2186  call    __archive_write_program_allocate
0x1800f218b  mov     [rbx], rax
0x1800f218e  test    rax, rax
0x1800f2191  jnz     short loc_1800F219E
0x1800f2193  mov     rcx, rbx; Block
0x1800f2196  call    cs:__imp_free
0x1800f219c  jmp     short loc_1800F2166
0x1800f219e  lea     rax, archive_write_lrzip_open
0x1800f21a5  mov     [rdi+50h], r14
0x1800f21a9  mov     [rdi+20h], rax
0x1800f21ad  lea     r8, aUsingExternalL; "Using external lrzip program for lrzip "...
0x1800f21b4  lea     rax, archive_write_lrzip_options
0x1800f21bb  mov     dword ptr [rdi+58h], 0Ah
0x1800f21c2  mov     [rdi+18h], rax
0x1800f21c6  or      edx, 0FFFFFFFFh
0x1800f21c9  lea     rax, archive_compressor_program_write
0x1800f21d0  mov     [rdi+48h], rbx
0x1800f21d4  mov     [rdi+28h], rax
0x1800f21d8  mov     rcx, rsi
0x1800f21db  lea     rax, archive_compressor_program_close
0x1800f21e2  mov     [rdi+38h], rax
0x1800f21e6  lea     rax, archive_write_lrzip_free
0x1800f21ed  mov     [rdi+40h], rax
0x1800f21f1  call    archive_set_error
0x1800f21f6  mov     eax, 0FFFFFFECh
0x1800f21fb  add     rsp, 28h
0x1800f21ff  pop     r14
0x1800f2201  pop     rdi
0x1800f2202  pop     rsi
0x1800f2203  pop     rbx
0x1800f2204  retn
```
