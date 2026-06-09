# archive_read_support_format_iso9660

- ea: `0x180011c30`
- end: `0x180011d57`
- name: `archive_read_support_format_iso9660`
- size: `295`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180010f00`
- `0x1800ca690`

## callees

- `0x180004d78`
- `0x18000523c`
- `0x180006c00`
- `0x180011c30`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x180011c6d`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x180011c6d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180011d40`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180011d40`

## string_xrefs

- `0x180011c3a`: `archive_read_support_format_iso9660`

## pseudocode

```c
__int64 __fastcall archive_read_support_format_iso9660(__int64 a1)
{
  _DWORD *v3; // rax
  __int64 v4; // rbx
  _QWORD *v5; // rax
  unsigned int register_format; // edi

  if ( (unsigned int)_archive_check_magic(a1, 14594245, 1, "archive_read_support_format_iso9660") == -30 )
    return 4294967266LL;
  v3 = calloc(1u, 0x9F8u);
  v4 = (__int64)v3;
  if ( !v3 )
  {
    archive_set_error(a1, 12, "Can't allocate iso9660 data");
    return 4294967266LL;
  }
  *v3 = -1772054944;
  v5 = v3 + 32;
  *(_QWORD *)(v4 + 136) = v5;
  *(_DWORD *)(v4 + 4) = 1;
  *v5 = 0;
  *(_QWORD *)(v4 + 144) = 0;
  *(_QWORD *)(v4 + 152) = v4 + 144;
  *(_DWORD *)(v4 + 8) = 1;
  register_format = _archive_read_register_format(
                      a1,
                      v4,
                      (__int64)"iso9660",
                      (__int64)archive_read_format_iso9660_bid,
                      (__int64)&archive_read_format_iso9660_options,
                      (__int64)archive_read_format_iso9660_read_header,
                      (__int64)archive_read_format_iso9660_read_data,
                      (__int64)archive_commoncrypto_version,
                      0,
                      (__int64)archive_read_format_iso9660_cleanup,
                      0,
                      0);
  if ( !register_format )
    return 0;
  free((void *)v4);
  return register_format;
}

```

## disassembly

```asm
0x180011c30  mov     [rsp+arg_0], rbx
0x180011c35  push    rdi
0x180011c36  sub     rsp, 60h
0x180011c3a  lea     r9, aArchiveReadSup_59; "archive_read_support_format_iso9660"
0x180011c41  mov     edx, 0DEB0C5h
0x180011c46  mov     r8d, 1
0x180011c4c  mov     rdi, rcx
0x180011c4f  call    __archive_check_magic
0x180011c54  cmp     eax, 0FFFFFFE2h
0x180011c57  jnz     short loc_180011C63
0x180011c59  mov     eax, 0FFFFFFE2h
0x180011c5e  jmp     loc_180011D4C
0x180011c63  mov     edx, 9F8h; Size
0x180011c68  mov     ecx, 1; Count
0x180011c6d  call    cs:__imp_calloc
0x180011c73  mov     rbx, rax
0x180011c76  mov     rcx, rdi
0x180011c79  test    rax, rax
0x180011c7c  jnz     short loc_180011C8F
0x180011c7e  lea     r8, aCanTAllocateIs; "Can't allocate iso9660 data"
0x180011c85  lea     edx, [rax+0Ch]
0x180011c88  call    archive_set_error
0x180011c8d  jmp     short loc_180011C59
0x180011c8f  mov     dword ptr [rax], 96609660h
0x180011c95  lea     r9, archive_read_format_iso9660_bid
0x180011c9c  sub     rax, 0FFFFFFFFFFFFFF80h
0x180011ca0  mov     [rsp+68h+var_10], 0
0x180011ca9  mov     [rbx+88h], rax
0x180011cb0  lea     r8, aIso9660_0; "iso9660"
0x180011cb7  mov     [rsp+68h+var_18], 0
0x180011cc0  mov     rdx, rbx
0x180011cc3  mov     dword ptr [rbx+4], 1
0x180011cca  mov     qword ptr [rax], 0
0x180011cd1  lea     rax, [rbx+90h]
0x180011cd8  mov     qword ptr [rax], 0
0x180011cdf  mov     [rbx+98h], rax
0x180011ce6  lea     rax, archive_read_format_iso9660_cleanup
0x180011ced  mov     [rsp+68h+var_20], rax
0x180011cf2  lea     rax, archive_commoncrypto_version
0x180011cf9  mov     [rsp+68h+var_28], 0
0x180011d02  mov     [rsp+68h+var_30], rax
0x180011d07  lea     rax, archive_read_format_iso9660_read_data
0x180011d0e  mov     [rsp+68h+var_38], rax
0x180011d13  lea     rax, archive_read_format_iso9660_read_header
0x180011d1a  mov     [rsp+68h+var_40], rax
0x180011d1f  lea     rax, archive_read_format_iso9660_options
0x180011d26  mov     [rsp+68h+var_48], rax
0x180011d2b  mov     dword ptr [rbx+8], 1
0x180011d32  call    __archive_read_register_format
0x180011d37  mov     edi, eax
0x180011d39  test    eax, eax
0x180011d3b  jz      short loc_180011D4A
0x180011d3d  mov     rcx, rbx; Block
0x180011d40  call    cs:__imp_free
0x180011d46  mov     eax, edi
0x180011d48  jmp     short loc_180011D4C
0x180011d4a  xor     eax, eax
0x180011d4c  mov     rbx, [rsp+68h+arg_0]
0x180011d51  add     rsp, 60h
0x180011d55  pop     rdi
0x180011d56  retn
```
