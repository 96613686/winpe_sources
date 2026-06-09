# archive_write_add_filter_program

- ea: `0x1800f2dd0`
- end: `0x1800f2f0d`
- name: `archive_write_add_filter_program`
- size: `317`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800f2f20`

## callees

- `0x18000523c`
- `0x180006c00`
- `0x18000a2d0`
- `0x18000b4d0`
- `0x1800efa88`
- `0x1800f2a50`
- `0x1800f2d40`
- `0x1800f2dd0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__strdup` at `0x1800f2e2c`
- `api-ms-win-crt-private-l1-1-0!_o__strdup` at `0x1800f2e2c`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x1800f2e13`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x1800f2e13`

## string_xrefs

- `0x1800f2deb`: `archive_write_add_filter_program`

## pseudocode

```c
__int64 __fastcall archive_write_add_filter_program(__int64 a1, __int64 a2)
{
  __int64 v4; // rdi
  __int64 *v5; // rax
  __int64 *v6; // rbx
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rdx
  __int64 result; // rax

  v4 = _archive_write_allocate_filter(a1);
  if ( (unsigned int)_archive_check_magic(a1, 2965749982LL, 1, "archive_write_add_filter_program") != -30 )
  {
    v5 = (__int64 *)calloc(1u, 0x28u);
    *(_QWORD *)(v4 + 72) = v5;
    v6 = v5;
    if ( v5 )
    {
      v7 = _o__strdup(a2);
      v6[4] = v7;
      if ( v7 )
      {
        v8 = _archive_write_program_allocate(a2);
        *v6 = v8;
        if ( v8 )
        {
          v9 = -1;
          do
            ++v9;
          while ( *(_BYTE *)(a2 + v9) );
          if ( archive_string_ensure(v6 + 1, v9 + 10) )
          {
            v6[2] = 0;
            archive_strncat(v6 + 1, "Program: ", 9);
            archive_strncat(v6 + 1, a2, 0x1000000);
            *(_QWORD *)(v4 + 80) = v6[1];
            *(_QWORD *)(v4 + 32) = archive_compressor_program_open;
            *(_QWORD *)(v4 + 40) = archive_compressor_program_write;
            *(_QWORD *)(v4 + 56) = archive_compressor_program_close;
            *(_QWORD *)(v4 + 64) = archive_compressor_program_free;
            result = 0;
            *(_DWORD *)(v4 + 88) = 4;
            return result;
          }
        }
      }
    }
    archive_compressor_program_free(v4);
    archive_set_error(a1, 12, "Can't allocate memory for filter program");
  }
  return 4294967266LL;
}

```

## disassembly

```asm
0x1800f2dd0  push    rbx
0x1800f2dd2  push    rbp
0x1800f2dd3  push    rsi
0x1800f2dd4  push    rdi
0x1800f2dd5  push    r14
0x1800f2dd7  sub     rsp, 20h
0x1800f2ddb  mov     rsi, rdx
0x1800f2dde  mov     rbp, rcx
0x1800f2de1  call    __archive_write_allocate_filter
0x1800f2de6  mov     ebx, 1
0x1800f2deb  lea     r9, aArchiveWriteAd_25; "archive_write_add_filter_program"
0x1800f2df2  mov     r8d, ebx
0x1800f2df5  mov     edx, 0B0C5C0DEh
0x1800f2dfa  mov     rcx, rbp
0x1800f2dfd  mov     rdi, rax
0x1800f2e00  call    __archive_check_magic
0x1800f2e05  cmp     eax, 0FFFFFFE2h
0x1800f2e08  jz      loc_1800F2EFD
0x1800f2e0e  lea     edx, [rbx+27h]; Size
0x1800f2e11  mov     ecx, ebx; Count
0x1800f2e13  call    cs:__imp_calloc
0x1800f2e19  mov     [rdi+48h], rax
0x1800f2e1d  mov     rbx, rax
0x1800f2e20  test    rax, rax
0x1800f2e23  jz      loc_1800F2EE1
0x1800f2e29  mov     rcx, rsi
0x1800f2e2c  call    cs:__imp__o__strdup
0x1800f2e32  mov     [rbx+20h], rax
0x1800f2e36  test    rax, rax
0x1800f2e39  jz      loc_1800F2EE1
0x1800f2e3f  mov     rcx, rsi
0x1800f2e42  call    __archive_write_program_allocate
0x1800f2e47  mov     [rbx], rax
0x1800f2e4a  test    rax, rax
0x1800f2e4d  jz      loc_1800F2EE1
0x1800f2e53  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800f2e57  inc     rdx
0x1800f2e5a  cmp     byte ptr [rsi+rdx], 0
0x1800f2e5e  jnz     short loc_1800F2E57
0x1800f2e60  lea     r14, [rbx+8]
0x1800f2e64  add     rdx, 0Ah
0x1800f2e68  mov     rcx, r14
0x1800f2e6b  call    archive_string_ensure
0x1800f2e70  test    rax, rax
0x1800f2e73  jz      short loc_1800F2EE1
0x1800f2e75  mov     r8d, 9
0x1800f2e7b  mov     qword ptr [rbx+10h], 0
0x1800f2e83  lea     rdx, aProgram_0; "Program: "
0x1800f2e8a  mov     rcx, r14
0x1800f2e8d  call    archive_strncat
0x1800f2e92  mov     r8d, 1000000h
0x1800f2e98  mov     rdx, rsi
0x1800f2e9b  mov     rcx, r14
0x1800f2e9e  call    archive_strncat
0x1800f2ea3  mov     rax, [r14]
0x1800f2ea6  mov     [rdi+50h], rax
0x1800f2eaa  lea     rax, archive_compressor_program_open
0x1800f2eb1  mov     [rdi+20h], rax
0x1800f2eb5  lea     rax, archive_compressor_program_write
0x1800f2ebc  mov     [rdi+28h], rax
0x1800f2ec0  lea     rax, archive_compressor_program_close
0x1800f2ec7  mov     [rdi+38h], rax
0x1800f2ecb  lea     rax, archive_compressor_program_free
0x1800f2ed2  mov     [rdi+40h], rax
0x1800f2ed6  xor     eax, eax
0x1800f2ed8  mov     dword ptr [rdi+58h], 4
0x1800f2edf  jmp     short loc_1800F2F02
0x1800f2ee1  mov     rcx, rdi
0x1800f2ee4  call    archive_compressor_program_free
0x1800f2ee9  lea     r8, aCanTAllocateMe_25; "Can't allocate memory for filter progra"...
0x1800f2ef0  mov     edx, 0Ch
0x1800f2ef5  mov     rcx, rbp
0x1800f2ef8  call    archive_set_error
0x1800f2efd  mov     eax, 0FFFFFFE2h
0x1800f2f02  add     rsp, 20h
0x1800f2f06  pop     r14
0x1800f2f08  pop     rdi
0x1800f2f09  pop     rsi
0x1800f2f0a  pop     rbp
0x1800f2f0b  pop     rbx
0x1800f2f0c  retn
```
