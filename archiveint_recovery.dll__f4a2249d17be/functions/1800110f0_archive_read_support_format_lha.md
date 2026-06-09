# archive_read_support_format_lha

- ea: `0x1800110f0`
- end: `0x1800111f7`
- name: `archive_read_support_format_lha`
- size: `263`
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
- `0x1800110f0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x18001112d`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x18001112d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800111e4`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800111e4`

## string_xrefs

- `0x1800110ff`: `archive_read_support_format_lha`

## pseudocode

```c
__int64 __fastcall archive_read_support_format_lha(__int64 a1)
{
  _QWORD *v3; // rax
  void *v4; // rbx

  if ( (unsigned int)_archive_check_magic(a1, 14594245, 1, "archive_read_support_format_lha") == -30 )
    return 4294967266LL;
  v3 = calloc(1u, 0x1A0u);
  v4 = v3;
  if ( !v3 )
  {
    archive_set_error(a1, 12, "Can't allocate lha data");
    return 4294967266LL;
  }
  v3[33] = 0;
  v3[34] = 0;
  v3[35] = 0;
  if ( (unsigned int)_archive_read_register_format(
                       a1,
                       (__int64)v3,
                       (__int64)"lha",
                       (__int64)archive_read_format_lha_bid,
                       (__int64)&archive_read_format_lha_options,
                       (__int64)archive_read_format_lha_read_header,
                       (__int64)archive_read_format_lha_read_data,
                       (__int64)archive_read_format_lha_read_data_skip,
                       0,
                       (__int64)archive_read_format_lha_cleanup,
                       0,
                       0) )
    free(v4);
  return 0;
}

```

## disassembly

```asm
0x1800110f0  mov     [rsp+arg_0], rbx
0x1800110f5  push    rdi
0x1800110f6  sub     rsp, 60h
0x1800110fa  mov     ebx, 1
0x1800110ff  lea     r9, aArchiveReadSup_64; "archive_read_support_format_lha"
0x180011106  mov     r8d, ebx
0x180011109  mov     edx, 0DEB0C5h
0x18001110e  mov     rdi, rcx
0x180011111  call    __archive_check_magic
0x180011116  cmp     eax, 0FFFFFFE2h
0x180011119  jnz     short loc_180011125
0x18001111b  mov     eax, 0FFFFFFE2h
0x180011120  jmp     loc_1800111EC
0x180011125  mov     edx, 1A0h; Size
0x18001112a  mov     rcx, rbx; Count
0x18001112d  call    cs:__imp_calloc
0x180011133  mov     rbx, rax
0x180011136  mov     rcx, rdi
0x180011139  test    rax, rax
0x18001113c  jnz     short loc_18001114F
0x18001113e  lea     r8, aCanTAllocateLh; "Can't allocate lha data"
0x180011145  lea     edx, [rax+0Ch]
0x180011148  call    archive_set_error
0x18001114d  jmp     short loc_18001111B
0x18001114f  mov     [rsp+68h+var_10], 0
0x180011158  lea     r9, archive_read_format_lha_bid
0x18001115f  mov     qword ptr [rax+108h], 0
0x18001116a  lea     r8, aLha; "lha"
0x180011171  mov     qword ptr [rax+110h], 0
0x18001117c  mov     rdx, rbx
0x18001117f  mov     qword ptr [rax+118h], 0
0x18001118a  lea     rax, archive_read_format_lha_cleanup
0x180011191  mov     [rsp+68h+var_18], 0
0x18001119a  mov     [rsp+68h+var_20], rax
0x18001119f  lea     rax, archive_read_format_lha_read_data_skip
0x1800111a6  mov     [rsp+68h+var_28], 0
0x1800111af  mov     [rsp+68h+var_30], rax
0x1800111b4  lea     rax, archive_read_format_lha_read_data
0x1800111bb  mov     [rsp+68h+var_38], rax
0x1800111c0  lea     rax, archive_read_format_lha_read_header
0x1800111c7  mov     [rsp+68h+var_40], rax
0x1800111cc  lea     rax, archive_read_format_lha_options
0x1800111d3  mov     [rsp+68h+var_48], rax
0x1800111d8  call    __archive_read_register_format
0x1800111dd  test    eax, eax
0x1800111df  jz      short loc_1800111EA
0x1800111e1  mov     rcx, rbx; Block
0x1800111e4  call    cs:__imp_free
0x1800111ea  xor     eax, eax
0x1800111ec  mov     rbx, [rsp+68h+arg_0]
0x1800111f1  add     rsp, 60h
0x1800111f5  pop     rdi
0x1800111f6  retn
```
