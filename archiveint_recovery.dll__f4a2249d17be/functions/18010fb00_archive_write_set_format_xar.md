# archive_write_set_format_xar

- ea: `0x18010fb00`
- end: `0x18010fcd8`
- name: `archive_write_set_format_xar`
- size: `472`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x18000523c`
- `0x180006c00`
- `0x18000b4d0`
- `0x18010fb00`
- `0x180110880`
- `0x18011a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x18010fb55`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x18010fb55`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18010fbd4`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18010fbd4`

## string_xrefs

- `0x18010fb11`: `archive_write_set_format_xar`

## pseudocode

```c
__int64 __fastcall archive_write_set_format_xar(__int64 a1)
{
  __int64 result; // rax
  void (__fastcall *v3)(__int64); // rax
  _DWORD *v4; // rax
  __int64 v5; // rdx
  _DWORD *v6; // rdi
  __int64 v7; // rcx
  _QWORD *v8; // rax
  __int64 virtual_dir; // rax
  __int64 v10; // rdx
  __int64 v11; // rax

  if ( (unsigned int)_archive_check_magic(a1, 2965749982LL, 1, "archive_write_set_format_xar") == -30 )
    return 4294967266LL;
  v3 = *(void (__fastcall **)(__int64))(a1 + 312);
  if ( v3 )
    v3(a1);
  v4 = calloc(1u, 0x10208u);
  v6 = v4;
  v7 = a1;
  if ( !v4 )
  {
LABEL_6:
    archive_set_error(v7, 12, "Can't allocate xar data");
    return 4294967266LL;
  }
  *v4 = -1;
  v8 = v4 + 16506;
  *((_QWORD *)v6 + 8254) = v8;
  *v8 = 0;
  *((_QWORD *)v6 + 8256) = off_18011E4C8;
  *((_QWORD *)v6 + 8255) = 0;
  *((_QWORD *)v6 + 10) = 0;
  *((_QWORD *)v6 + 11) = 0;
  *((_QWORD *)v6 + 12) = 0;
  *((_QWORD *)v6 + 13) = 0;
  *((_QWORD *)v6 + 14) = 0;
  *((_QWORD *)v6 + 15) = 0;
  virtual_dir = file_create_virtual_dir(a1, v5, &unk_18012277F);
  *((_QWORD *)v6 + 3) = virtual_dir;
  if ( !virtual_dir )
  {
    free(v6);
    v7 = a1;
    goto LABEL_6;
  }
  *(_QWORD *)(virtual_dir + 88) = virtual_dir;
  v10 = *((_QWORD *)v6 + 3);
  *(_DWORD *)(v10 + 24) = v6[4]++;
  *(_QWORD *)(v10 + 56) = 0;
  **((_QWORD **)v6 + 8254) = v10;
  v11 = *((_QWORD *)v6 + 3);
  *((_QWORD *)v6 + 8254) = v10 + 56;
  *((_QWORD *)v6 + 4) = v11;
  *((_QWORD *)v6 + 5) = 0;
  *((_QWORD *)v6 + 6) = 0;
  *((_QWORD *)v6 + 7) = 0;
  archive_string_ensure(v6 + 10, 1);
  **((_BYTE **)v6 + 5) = 0;
  v6[32] = 1;
  v6[33] = 1;
  v6[34] = 1;
  v6[35] = 6;
  v6[36] = 1;
  *(_QWORD *)(a1 + 272) = xar_options;
  *(_QWORD *)(a1 + 288) = xar_write_header;
  *(_QWORD *)(a1 + 296) = xar_write_data;
  *(_QWORD *)(a1 + 280) = xar_finish_entry;
  *(_QWORD *)(a1 + 304) = xar_close;
  *(_QWORD *)(a1 + 312) = xar_free;
  result = 0;
  *(_QWORD *)(a1 + 248) = v6;
  *(_QWORD *)(a1 + 256) = "xar";
  *(_DWORD *)(a1 + 16) = 655360;
  *(_QWORD *)(a1 + 24) = "xar";
  return result;
}

```

## disassembly

```asm
0x18010fb00  push    rbx
0x18010fb02  push    rbp
0x18010fb03  push    rsi
0x18010fb04  push    rdi
0x18010fb05  push    r14
0x18010fb07  sub     rsp, 20h
0x18010fb0b  mov     r14d, 1
0x18010fb11  lea     r9, aArchiveWriteSe_63; "archive_write_set_format_xar"
0x18010fb18  mov     r8d, r14d
0x18010fb1b  mov     edx, 0B0C5C0DEh
0x18010fb20  mov     rsi, rcx
0x18010fb23  call    __archive_check_magic
0x18010fb28  lea     ebx, [r14-1Fh]
0x18010fb2c  cmp     eax, ebx
0x18010fb2e  jnz     short loc_18010FB37
0x18010fb30  mov     eax, ebx
0x18010fb32  jmp     loc_18010FCCD
0x18010fb37  mov     rax, [rsi+138h]
0x18010fb3e  xor     ebp, ebp
0x18010fb40  test    rax, rax
0x18010fb43  jz      short loc_18010FB4D
0x18010fb45  mov     rcx, rsi
0x18010fb48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010fb4d  mov     edx, 10208h; Size
0x18010fb52  mov     rcx, r14; Count
0x18010fb55  call    cs:__imp_calloc
0x18010fb5b  mov     rdi, rax
0x18010fb5e  mov     rcx, rsi
0x18010fb61  test    rax, rax
0x18010fb64  jnz     short loc_18010FB79
0x18010fb66  mov     edx, 0Ch
0x18010fb6b  lea     r8, aCanTAllocateXa; "Can't allocate xar data"
0x18010fb72  call    archive_set_error
0x18010fb77  jmp     short loc_18010FB30
0x18010fb79  mov     dword ptr [rax], 0FFFFFFFFh
0x18010fb7f  lea     r8, unk_18012277F
0x18010fb86  add     rax, 101E8h
0x18010fb8c  mov     [rdi+101F0h], rax
0x18010fb93  mov     [rax], rbp
0x18010fb96  lea     rax, off_18011E4C8
0x18010fb9d  mov     [rdi+10200h], rax
0x18010fba4  mov     [rdi+101F8h], rbp
0x18010fbab  mov     [rdi+50h], rbp
0x18010fbaf  mov     [rdi+58h], rbp
0x18010fbb3  mov     [rdi+60h], rbp
0x18010fbb7  mov     [rdi+68h], rbp
0x18010fbbb  mov     [rdi+70h], rbp
0x18010fbbf  mov     [rdi+78h], rbp
0x18010fbc3  call    file_create_virtual_dir
0x18010fbc8  mov     [rdi+18h], rax
0x18010fbcc  test    rax, rax
0x18010fbcf  jnz     short loc_18010FBDF
0x18010fbd1  mov     rcx, rdi; Block
0x18010fbd4  call    cs:__imp_free
0x18010fbda  mov     rcx, rsi
0x18010fbdd  jmp     short loc_18010FB66
0x18010fbdf  mov     [rax+58h], rax
0x18010fbe3  lea     rbx, [rdi+28h]
0x18010fbe7  mov     rdx, [rdi+18h]
0x18010fbeb  mov     eax, [rdi+10h]
0x18010fbee  mov     [rdx+18h], eax
0x18010fbf1  lea     rcx, [rdx+38h]
0x18010fbf5  add     [rdi+10h], r14d
0x18010fbf9  mov     [rcx], rbp
0x18010fbfc  mov     rax, [rdi+101F0h]
0x18010fc03  mov     [rax], rdx
0x18010fc06  mov     rdx, r14
0x18010fc09  mov     rax, [rdi+18h]
0x18010fc0d  mov     [rdi+101F0h], rcx
0x18010fc14  mov     rcx, rbx
0x18010fc17  mov     [rdi+20h], rax
0x18010fc1b  mov     [rbx], rbp
0x18010fc1e  mov     [rdi+30h], rbp
0x18010fc22  mov     [rdi+38h], rbp
0x18010fc26  call    archive_string_ensure
0x18010fc2b  mov     rax, [rbx]
0x18010fc2e  lea     rcx, aXar; "xar"
0x18010fc35  mov     [rax], bpl
0x18010fc38  lea     rax, xar_options
0x18010fc3f  mov     [rdi+80h], r14d
0x18010fc46  mov     [rdi+84h], r14d
0x18010fc4d  mov     [rdi+88h], r14d
0x18010fc54  mov     dword ptr [rdi+8Ch], 6
0x18010fc5e  mov     [rdi+90h], r14d
0x18010fc65  mov     [rsi+110h], rax
0x18010fc6c  lea     rax, xar_write_header
0x18010fc73  mov     [rsi+120h], rax
0x18010fc7a  lea     rax, xar_write_data
0x18010fc81  mov     [rsi+128h], rax
0x18010fc88  lea     rax, xar_finish_entry
0x18010fc8f  mov     [rsi+118h], rax
0x18010fc96  lea     rax, xar_close
0x18010fc9d  mov     [rsi+130h], rax
0x18010fca4  lea     rax, xar_free
0x18010fcab  mov     [rsi+138h], rax
0x18010fcb2  xor     eax, eax
0x18010fcb4  mov     [rsi+0F8h], rdi
0x18010fcbb  mov     [rsi+100h], rcx
0x18010fcc2  mov     dword ptr [rsi+10h], 0A0000h
0x18010fcc9  mov     [rsi+18h], rcx
0x18010fccd  add     rsp, 20h
0x18010fcd1  pop     r14
0x18010fcd3  pop     rdi
0x18010fcd4  pop     rsi
0x18010fcd5  pop     rbp
0x18010fcd6  pop     rbx
0x18010fcd7  retn
```
