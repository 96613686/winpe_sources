# archive_write_set_format_zip

- ea: `0x180113ca0`
- end: `0x180113dff`
- name: `archive_write_set_format_zip`
- size: `351`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000523c`
- `0x180006c00`
- `0x180113ca0`
- `0x18011a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x180113cf6`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x180113cf6`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180113d63`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180113d63`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180113d4e`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180113d4e`

## string_xrefs

- `0x180113d69`: `Can't allocate compression buffer`
- `0x180113cb4`: `archive_write_set_format_zip`

## pseudocode

```c
__int64 __fastcall archive_write_set_format_zip(__int64 a1)
{
  __int64 result; // rax
  void (__fastcall *v3)(__int64); // rax
  _QWORD *v4; // rax
  _QWORD *v5; // rdi
  void *v6; // rax

  if ( (unsigned int)_archive_check_magic(a1, 2965749982LL, 1, "archive_write_set_format_zip") == -30 )
    return 4294967266LL;
  v3 = *(void (__fastcall **)(__int64))(a1 + 312);
  if ( v3 )
    v3(a1);
  v4 = calloc(1u, 0x248u);
  v5 = v4;
  if ( !v4 )
  {
    archive_set_error(a1, 12, "Can't allocate zip data");
    return 4294967266LL;
  }
  *((_DWORD *)v4 + 72) = -1;
  *((_WORD *)v4 + 146) = 6;
  *((_WORD *)v4 + 152) = 1;
  v4[28] = real_crc32;
  v4[71] = 0x10000;
  v6 = malloc(0x10000u);
  v5[72] = v6;
  if ( !v6 )
  {
    free(v5);
    archive_set_error(a1, 12, "Can't allocate compression buffer");
    return 4294967266LL;
  }
  *(_QWORD *)(a1 + 248) = v5;
  *(_QWORD *)(a1 + 256) = "zip";
  *(_QWORD *)(a1 + 272) = archive_write_zip_options;
  *(_QWORD *)(a1 + 288) = archive_write_zip_header;
  *(_QWORD *)(a1 + 296) = archive_write_zip_data;
  *(_QWORD *)(a1 + 280) = archive_write_zip_finish_entry;
  *(_QWORD *)(a1 + 304) = archive_write_zip_close;
  *(_QWORD *)(a1 + 312) = archive_write_zip_free;
  *(_QWORD *)(a1 + 24) = "ZIP";
  result = 0;
  *(_DWORD *)(a1 + 16) = 327680;
  return result;
}

```

## disassembly

```asm
0x180113ca0  mov     [rsp+arg_0], rbx
0x180113ca5  mov     [rsp+arg_8], rbp
0x180113caa  push    rdi
0x180113cab  sub     rsp, 20h
0x180113caf  mov     ebp, 1
0x180113cb4  lea     r9, aArchiveWriteSe_46; "archive_write_set_format_zip"
0x180113cbb  mov     r8d, ebp
0x180113cbe  mov     edx, 0B0C5C0DEh
0x180113cc3  mov     rbx, rcx
0x180113cc6  call    __archive_check_magic
0x180113ccb  cmp     eax, 0FFFFFFE2h
0x180113cce  jnz     short loc_180113CDA
0x180113cd0  mov     eax, 0FFFFFFE2h
0x180113cd5  jmp     loc_180113DEF
0x180113cda  mov     rax, [rbx+138h]
0x180113ce1  test    rax, rax
0x180113ce4  jz      short loc_180113CEE
0x180113ce6  mov     rcx, rbx
0x180113ce9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180113cee  mov     edx, 248h; Size
0x180113cf3  mov     rcx, rbp; Count
0x180113cf6  call    cs:__imp_calloc
0x180113cfc  mov     rdi, rax
0x180113cff  test    rax, rax
0x180113d02  jnz     short loc_180113D1A
0x180113d04  lea     r8, aCanTAllocateZi_1; "Can't allocate zip data"
0x180113d0b  mov     edx, 0Ch
0x180113d10  mov     rcx, rbx
0x180113d13  call    archive_set_error
0x180113d18  jmp     short loc_180113CD0
0x180113d1a  mov     dword ptr [rax+120h], 0FFFFFFFFh
0x180113d24  mov     ecx, 10000h; Size
0x180113d29  mov     word ptr [rax+124h], 6
0x180113d32  mov     [rax+130h], bp
0x180113d39  lea     rax, real_crc32
0x180113d40  mov     [rdi+0E0h], rax
0x180113d47  mov     [rdi+238h], rcx
0x180113d4e  call    cs:__imp_malloc
0x180113d54  mov     [rdi+240h], rax
0x180113d5b  test    rax, rax
0x180113d5e  jnz     short loc_180113D72
0x180113d60  mov     rcx, rdi; Block
0x180113d63  call    cs:__imp_free
0x180113d69  lea     r8, aCanTAllocateCo; "Can't allocate compression buffer"
0x180113d70  jmp     short loc_180113D0B
0x180113d72  lea     rax, aZip; "zip"
0x180113d79  mov     [rbx+0F8h], rdi
0x180113d80  mov     [rbx+100h], rax
0x180113d87  lea     rax, archive_write_zip_options
0x180113d8e  mov     [rbx+110h], rax
0x180113d95  lea     rax, archive_write_zip_header
0x180113d9c  mov     [rbx+120h], rax
0x180113da3  lea     rax, archive_write_zip_data
0x180113daa  mov     [rbx+128h], rax
0x180113db1  lea     rax, archive_write_zip_finish_entry
0x180113db8  mov     [rbx+118h], rax
0x180113dbf  lea     rax, archive_write_zip_close
0x180113dc6  mov     [rbx+130h], rax
0x180113dcd  lea     rax, archive_write_zip_free
0x180113dd4  mov     [rbx+138h], rax
0x180113ddb  lea     rax, aZip_0; "ZIP"
0x180113de2  mov     [rbx+18h], rax
0x180113de6  xor     eax, eax
0x180113de8  mov     dword ptr [rbx+10h], 50000h
0x180113def  mov     rbx, [rsp+28h+arg_0]
0x180113df4  mov     rbp, [rsp+28h+arg_8]
0x180113df9  add     rsp, 20h
0x180113dfd  pop     rdi
0x180113dfe  retn
```
