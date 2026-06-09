# archive_write_add_filter_lzop

- ea: `0x1800f2830`
- end: `0x1800f2934`
- name: `archive_write_add_filter_lzop`
- size: `260`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x18000523c`
- `0x180006c00`
- `0x1800efa88`
- `0x1800f2830`
- `0x1800f2a50`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x1800f287d`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x1800f287d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800f28ff`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800f28ff`

## string_xrefs

- `0x1800f284c`: `archive_write_add_filter_lzop`
- `0x1800f2907`: `Using external lzop program for lzop compression`

## pseudocode

```c
__int64 __fastcall archive_write_add_filter_lzop(__int64 a1)
{
  __int64 v2; // rsi
  _QWORD *v4; // rbx
  __int64 v5; // rax

  v2 = _archive_write_allocate_filter();
  if ( (unsigned int)_archive_check_magic(a1, 2965749982LL, 1, "archive_write_add_filter_lzop") == -30 )
    return 4294967266LL;
  v4 = calloc(1u, 0x10u);
  if ( !v4 )
  {
LABEL_4:
    archive_set_error(a1, 12, "Can't allocate memory");
    return 4294967266LL;
  }
  *(_DWORD *)(v2 + 88) = 11;
  *(_QWORD *)(v2 + 32) = archive_write_lzop_open;
  *(_QWORD *)(v2 + 80) = "lzop";
  *(_QWORD *)(v2 + 24) = &archive_write_lzop_options;
  *(_QWORD *)(v2 + 40) = archive_write_lzop_write;
  *(_QWORD *)(v2 + 56) = archive_write_lzop_close;
  *(_QWORD *)(v2 + 64) = archive_write_lzop_free;
  *(_QWORD *)(v2 + 72) = v4;
  v5 = _archive_write_program_allocate();
  v4[1] = v5;
  if ( !v5 )
  {
    free(v4);
    goto LABEL_4;
  }
  *(_DWORD *)v4 = 0;
  archive_set_error(a1, 0xFFFFFFFFLL, "Using external lzop program for lzop compression");
  return 4294967276LL;
}

```

## disassembly

```asm
0x1800f2830  mov     [rsp+arg_0], rbx
0x1800f2835  mov     [rsp+arg_8], rsi
0x1800f283a  push    rdi
0x1800f283b  sub     rsp, 20h
0x1800f283f  mov     rdi, rcx
0x1800f2842  call    __archive_write_allocate_filter
0x1800f2847  mov     ebx, 1
0x1800f284c  lea     r9, aArchiveWriteAd_17; "archive_write_add_filter_lzop"
0x1800f2853  mov     r8d, ebx
0x1800f2856  mov     edx, 0B0C5C0DEh
0x1800f285b  mov     rcx, rdi
0x1800f285e  mov     rsi, rax
0x1800f2861  call    __archive_check_magic
0x1800f2866  cmp     eax, 0FFFFFFE2h
0x1800f2869  jnz     short loc_1800F2875
0x1800f286b  mov     eax, 0FFFFFFE2h
0x1800f2870  jmp     loc_1800F2924
0x1800f2875  mov     edx, 10h; Size
0x1800f287a  mov     rcx, rbx; Count
0x1800f287d  call    cs:__imp_calloc
0x1800f2883  mov     rbx, rax
0x1800f2886  test    rax, rax
0x1800f2889  jnz     short loc_1800F28A1
0x1800f288b  lea     r8, aCanTAllocateMe_30; "Can't allocate memory"
0x1800f2892  mov     edx, 0Ch
0x1800f2897  mov     rcx, rdi
0x1800f289a  call    archive_set_error
0x1800f289f  jmp     short loc_1800F286B
0x1800f28a1  lea     rax, archive_write_lzop_open
0x1800f28a8  mov     dword ptr [rsi+58h], 0Bh
0x1800f28af  mov     [rsi+20h], rax
0x1800f28b3  lea     rcx, aLzop; "lzop"
0x1800f28ba  lea     rax, archive_write_lzop_options
0x1800f28c1  mov     [rsi+50h], rcx
0x1800f28c5  mov     [rsi+18h], rax
0x1800f28c9  lea     rax, archive_write_lzop_write
0x1800f28d0  mov     [rsi+28h], rax
0x1800f28d4  lea     rax, archive_write_lzop_close
0x1800f28db  mov     [rsi+38h], rax
0x1800f28df  lea     rax, archive_write_lzop_free
0x1800f28e6  mov     [rsi+40h], rax
0x1800f28ea  mov     [rsi+48h], rbx
0x1800f28ee  call    __archive_write_program_allocate
0x1800f28f3  mov     [rbx+8], rax
0x1800f28f7  test    rax, rax
0x1800f28fa  jnz     short loc_1800F2907
0x1800f28fc  mov     rcx, rbx; Block
0x1800f28ff  call    cs:__imp_free
0x1800f2905  jmp     short loc_1800F288B
0x1800f2907  lea     r8, aUsingExternalL_2; "Using external lzop program for lzop co"...
0x1800f290e  mov     dword ptr [rbx], 0
0x1800f2914  or      edx, 0FFFFFFFFh
0x1800f2917  mov     rcx, rdi
0x1800f291a  call    archive_set_error
0x1800f291f  mov     eax, 0FFFFFFECh
0x1800f2924  mov     rbx, [rsp+28h+arg_0]
0x1800f2929  mov     rsi, [rsp+28h+arg_8]
0x1800f292e  add     rsp, 20h
0x1800f2932  pop     rdi
0x1800f2933  retn
```
