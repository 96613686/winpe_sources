# archive_read_support_format_mtree

- ea: `0x180011b10`
- end: `0x180011c1d`
- name: `archive_read_support_format_mtree`
- size: `269`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180010f00`
- `0x1800ca690`

## callees

- `0x180004d78`
- `0x18000523c`
- `0x180006c00`
- `0x180011b10`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x180011b4d`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x180011b4d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180011c0a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180011c0a`

## string_xrefs

- `0x180011b1f`: `archive_read_support_format_mtree`

## pseudocode

```c
__int64 __fastcall archive_read_support_format_mtree(__int64 a1)
{
  void *v3; // rax
  void *v4; // rbx

  if ( (unsigned int)_archive_check_magic(a1, 14594245, 1, "archive_read_support_format_mtree") == -30 )
    return 4294967266LL;
  v3 = calloc(1u, 0xB8u);
  v4 = v3;
  if ( !v3 )
  {
    archive_set_error(a1, 12, "Can't allocate mtree data");
    return 4294967266LL;
  }
  *((_BYTE *)v3 + 176) = 0;
  *((_DWORD *)v3 + 12) = -1;
  *((_QWORD *)v3 + 20) = off_18011DCE8;
  *((_QWORD *)v3 + 19) = 0;
  if ( (unsigned int)_archive_read_register_format(
                       a1,
                       (__int64)v3,
                       (__int64)"mtree",
                       (__int64)mtree_bid,
                       (__int64)&archive_read_format_mtree_options,
                       (__int64)read_header,
                       (__int64)read_data,
                       (__int64)skip,
                       0,
                       (__int64)cleanup,
                       0,
                       0) )
    free(v4);
  return 0;
}

```

## disassembly

```asm
0x180011b10  mov     [rsp+arg_0], rbx
0x180011b15  push    rdi
0x180011b16  sub     rsp, 60h
0x180011b1a  mov     ebx, 1
0x180011b1f  lea     r9, aArchiveReadSup_58; "archive_read_support_format_mtree"
0x180011b26  mov     r8d, ebx
0x180011b29  mov     edx, 0DEB0C5h
0x180011b2e  mov     rdi, rcx
0x180011b31  call    __archive_check_magic
0x180011b36  cmp     eax, 0FFFFFFE2h
0x180011b39  jnz     short loc_180011B45
0x180011b3b  mov     eax, 0FFFFFFE2h
0x180011b40  jmp     loc_180011C12
0x180011b45  mov     edx, 0B8h; Size
0x180011b4a  mov     rcx, rbx; Count
0x180011b4d  call    cs:__imp_calloc
0x180011b53  mov     rbx, rax
0x180011b56  mov     rcx, rdi
0x180011b59  test    rax, rax
0x180011b5c  jnz     short loc_180011B6F
0x180011b5e  lea     r8, aCanTAllocateMt; "Can't allocate mtree data"
0x180011b65  lea     edx, [rax+0Ch]
0x180011b68  call    archive_set_error
0x180011b6d  jmp     short loc_180011B3B
0x180011b6f  mov     byte ptr [rax+0B0h], 0
0x180011b76  lea     r9, mtree_bid
0x180011b7d  mov     dword ptr [rax+30h], 0FFFFFFFFh
0x180011b84  lea     r8, aMtree_0; "mtree"
0x180011b8b  mov     [rsp+68h+var_10], 0
0x180011b94  lea     rax, off_18011DCE8
0x180011b9b  mov     [rbx+0A0h], rax
0x180011ba2  mov     rdx, rbx
0x180011ba5  mov     [rsp+68h+var_18], 0
0x180011bae  lea     rax, cleanup
0x180011bb5  mov     [rsp+68h+var_20], rax
0x180011bba  lea     rax, skip
0x180011bc1  mov     [rsp+68h+var_28], 0
0x180011bca  mov     [rsp+68h+var_30], rax
0x180011bcf  lea     rax, read_data
0x180011bd6  mov     [rsp+68h+var_38], rax
0x180011bdb  lea     rax, read_header
0x180011be2  mov     [rsp+68h+var_40], rax
0x180011be7  lea     rax, archive_read_format_mtree_options
0x180011bee  mov     [rsp+68h+var_48], rax
0x180011bf3  mov     qword ptr [rbx+98h], 0
0x180011bfe  call    __archive_read_register_format
0x180011c03  test    eax, eax
0x180011c05  jz      short loc_180011C10
0x180011c07  mov     rcx, rbx; Block
0x180011c0a  call    cs:__imp_free
0x180011c10  xor     eax, eax
0x180011c12  mov     rbx, [rsp+68h+arg_0]
0x180011c17  add     rsp, 60h
0x180011c1b  pop     rdi
0x180011c1c  retn
```
