# archive_read_support_format_rar5

- ea: `0x180011870`
- end: `0x180011986`
- name: `archive_read_support_format_rar5`
- size: `278`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x180010f00`
- `0x1800ca690`

## callees

- `0x180004d78`
- `0x18000523c`
- `0x180006c00`
- `0x180011870`
- `0x1800de180`
- `0x1800de26c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800118ed`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800118ed`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800118a8`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800118a8`

## string_xrefs

- `0x18001187a`: `archive_read_support_format_rar5`

## pseudocode

```c
__int64 __fastcall archive_read_support_format_rar5(__int64 a1)
{
  void *v3; // rax
  void *v4; // rdi
  unsigned int register_format; // edi

  if ( (unsigned int)_archive_check_magic(a1, 14594245, 1, "archive_read_support_format_rar5") == -30 )
    return 4294967266LL;
  v3 = malloc(0x5348u);
  v4 = v3;
  if ( !v3 )
  {
    archive_set_error(a1, 12, "Can't allocate rar5 data");
    return 4294967266LL;
  }
  if ( (unsigned int)rar5_init(v3) )
  {
    archive_set_error(a1, 12, "Can't allocate rar5 filter buffer");
    free(v4);
    return 4294967266LL;
  }
  register_format = _archive_read_register_format(
                      a1,
                      (__int64)v4,
                      (__int64)"rar5",
                      (__int64)rar5_bid,
                      (__int64)archive_write_grzip_options,
                      (__int64)rar5_read_header,
                      (__int64)rar5_read_data,
                      (__int64)rar5_read_data_skip,
                      (__int64)rar5_seek_data,
                      (__int64)rar5_cleanup,
                      (__int64)archive_read_support_format_zip_capabilities_streamable,
                      (__int64)rar5_has_encrypted_entries);
  if ( register_format )
    rar5_cleanup(a1);
  return register_format;
}

```

## disassembly

```asm
0x180011870  mov     [rsp+arg_0], rbx
0x180011875  push    rdi
0x180011876  sub     rsp, 60h
0x18001187a  lea     r9, aArchiveReadSup_60; "archive_read_support_format_rar5"
0x180011881  mov     edx, 0DEB0C5h
0x180011886  mov     r8d, 1
0x18001188c  mov     rbx, rcx
0x18001188f  call    __archive_check_magic
0x180011894  cmp     eax, 0FFFFFFE2h
0x180011897  jnz     short loc_1800118A3
0x180011899  mov     eax, 0FFFFFFE2h
0x18001189e  jmp     loc_18001197B
0x1800118a3  mov     ecx, 5348h; Size
0x1800118a8  call    cs:__imp_malloc
0x1800118ae  mov     rdi, rax
0x1800118b1  test    rax, rax
0x1800118b4  jnz     short loc_1800118CA
0x1800118b6  lea     r8, aCanTAllocateRa_0; "Can't allocate rar5 data"
0x1800118bd  mov     rcx, rbx
0x1800118c0  lea     edx, [rax+0Ch]
0x1800118c3  call    archive_set_error
0x1800118c8  jmp     short loc_180011899
0x1800118ca  mov     rcx, rdi
0x1800118cd  call    rar5_init
0x1800118d2  mov     rcx, rbx
0x1800118d5  test    eax, eax
0x1800118d7  jz      short loc_1800118F5
0x1800118d9  lea     r8, aCanTAllocateRa; "Can't allocate rar5 filter buffer"
0x1800118e0  mov     edx, 0Ch
0x1800118e5  call    archive_set_error
0x1800118ea  mov     rcx, rdi; Block
0x1800118ed  call    cs:__imp_free
0x1800118f3  jmp     short loc_180011899
0x1800118f5  lea     rax, rar5_has_encrypted_entries
0x1800118fc  mov     rdx, rdi
0x1800118ff  mov     [rsp+68h+var_10], rax
0x180011904  lea     r9, rar5_bid
0x18001190b  lea     rax, archive_read_support_format_zip_capabilities_streamable
0x180011912  mov     [rsp+68h+var_18], rax
0x180011917  lea     r8, aRar5_0; "rar5"
0x18001191e  lea     rax, rar5_cleanup
0x180011925  mov     [rsp+68h+var_20], rax
0x18001192a  lea     rax, rar5_seek_data
0x180011931  mov     [rsp+68h+var_28], rax
0x180011936  lea     rax, rar5_read_data_skip
0x18001193d  mov     [rsp+68h+var_30], rax
0x180011942  lea     rax, rar5_read_data
0x180011949  mov     [rsp+68h+var_38], rax
0x18001194e  lea     rax, rar5_read_header
0x180011955  mov     [rsp+68h+var_40], rax
0x18001195a  lea     rax, archive_write_grzip_options
0x180011961  mov     [rsp+68h+var_48], rax
0x180011966  call    __archive_read_register_format
0x18001196b  mov     edi, eax
0x18001196d  test    eax, eax
0x18001196f  jz      short loc_180011979
0x180011971  mov     rcx, rbx
0x180011974  call    rar5_cleanup
0x180011979  mov     eax, edi
0x18001197b  mov     rbx, [rsp+68h+arg_0]
0x180011980  add     rsp, 60h
0x180011984  pop     rdi
0x180011985  retn
```
