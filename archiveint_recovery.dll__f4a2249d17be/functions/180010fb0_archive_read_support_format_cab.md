# archive_read_support_format_cab

- ea: `0x180010fb0`
- end: `0x1800110e6`
- name: `archive_read_support_format_cab`
- size: `310`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180010f00`
- `0x1800ca690`

## callees

- `0x180004d78`
- `0x18000523c`
- `0x180006c00`
- `0x18000b4d0`
- `0x180010fb0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x180010fed`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x180010fed`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180011054`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800110d3`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180011054`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800110d3`

## string_xrefs

- `0x180010fbf`: `archive_read_support_format_cab`

## pseudocode

```c
__int64 __fastcall archive_read_support_format_cab(__int64 a1)
{
  _QWORD *v3; // rax
  void *v4; // rbx

  if ( (unsigned int)_archive_check_magic(a1, 14594245, 1, "archive_read_support_format_cab") == -30 )
    return 4294967266LL;
  v3 = calloc(1u, 0x1A8u);
  v4 = v3;
  if ( !v3 )
  {
    archive_set_error(a1, 12, "Can't allocate CAB data");
    return 4294967266LL;
  }
  v3[16] = 0;
  v3[15] = 0;
  v3[17] = 0;
  if ( !archive_string_ensure(v3 + 15, 512) )
  {
    archive_set_error(a1, 12, "Can't allocate memory");
    free(v4);
    return 4294967266LL;
  }
  if ( (unsigned int)_archive_read_register_format(
                       a1,
                       (__int64)v4,
                       (__int64)"cab",
                       (__int64)archive_read_format_cab_bid,
                       (__int64)&archive_read_format_cab_options,
                       (__int64)archive_read_format_cab_read_header,
                       (__int64)archive_read_format_cab_read_data,
                       (__int64)archive_read_format_cab_read_data_skip,
                       0,
                       (__int64)archive_read_format_cab_cleanup,
                       0,
                       0) )
    free(v4);
  return 0;
}

```

## disassembly

```asm
0x180010fb0  mov     [rsp+arg_0], rbx
0x180010fb5  push    rdi
0x180010fb6  sub     rsp, 60h
0x180010fba  mov     ebx, 1
0x180010fbf  lea     r9, aArchiveReadSup_66; "archive_read_support_format_cab"
0x180010fc6  mov     r8d, ebx
0x180010fc9  mov     edx, 0DEB0C5h
0x180010fce  mov     rdi, rcx
0x180010fd1  call    __archive_check_magic
0x180010fd6  cmp     eax, 0FFFFFFE2h
0x180010fd9  jnz     short loc_180010FE5
0x180010fdb  mov     eax, 0FFFFFFE2h
0x180010fe0  jmp     loc_1800110DB
0x180010fe5  mov     edx, 1A8h; Size
0x180010fea  mov     rcx, rbx; Count
0x180010fed  call    cs:__imp_calloc
0x180010ff3  mov     rbx, rax
0x180010ff6  test    rax, rax
0x180010ff9  jnz     short loc_18001100F
0x180010ffb  lea     r8, aCanTAllocateCa; "Can't allocate CAB data"
0x180011002  mov     rcx, rdi
0x180011005  lea     edx, [rax+0Ch]
0x180011008  call    archive_set_error
0x18001100d  jmp     short loc_180010FDB
0x18001100f  lea     rcx, [rax+78h]
0x180011013  mov     qword ptr [rax+80h], 0
0x18001101e  mov     edx, 200h
0x180011023  mov     qword ptr [rcx], 0
0x18001102a  mov     qword ptr [rax+88h], 0
0x180011035  call    archive_string_ensure
0x18001103a  mov     rcx, rdi
0x18001103d  test    rax, rax
0x180011040  jnz     short loc_18001105F
0x180011042  lea     r8, aCanTAllocateMe_30; "Can't allocate memory"
0x180011049  lea     edx, [rax+0Ch]
0x18001104c  call    archive_set_error
0x180011051  mov     rcx, rbx; Block
0x180011054  call    cs:__imp_free
0x18001105a  jmp     loc_180010FDB
0x18001105f  mov     [rsp+68h+var_10], 0
0x180011068  lea     rax, archive_read_format_cab_cleanup
0x18001106f  mov     [rsp+68h+var_18], 0
0x180011078  lea     r9, archive_read_format_cab_bid
0x18001107f  mov     [rsp+68h+var_20], rax
0x180011084  lea     r8, aCab_0; "cab"
0x18001108b  mov     [rsp+68h+var_28], 0
0x180011094  lea     rax, archive_read_format_cab_read_data_skip
0x18001109b  mov     [rsp+68h+var_30], rax
0x1800110a0  mov     rdx, rbx
0x1800110a3  lea     rax, archive_read_format_cab_read_data
0x1800110aa  mov     [rsp+68h+var_38], rax
0x1800110af  lea     rax, archive_read_format_cab_read_header
0x1800110b6  mov     [rsp+68h+var_40], rax
0x1800110bb  lea     rax, archive_read_format_cab_options
0x1800110c2  mov     [rsp+68h+var_48], rax
0x1800110c7  call    __archive_read_register_format
0x1800110cc  test    eax, eax
0x1800110ce  jz      short loc_1800110D9
0x1800110d0  mov     rcx, rbx; Block
0x1800110d3  call    cs:__imp_free
0x1800110d9  xor     eax, eax
0x1800110db  mov     rbx, [rsp+68h+arg_0]
0x1800110e0  add     rsp, 60h
0x1800110e4  pop     rdi
0x1800110e5  retn
```
