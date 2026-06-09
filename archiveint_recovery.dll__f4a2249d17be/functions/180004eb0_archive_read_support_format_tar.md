# archive_read_support_format_tar

- ea: `0x180004eb0`
- end: `0x180005020`
- name: `archive_read_support_format_tar`
- size: `368`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180010f00`
- `0x1800ca690`
- `0x1800df490`

## callees

- `0x180004eb0`
- `0x18000523c`
- `0x180006c00`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x180004eed`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x180004eed`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000500d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000500d`

## string_xrefs

- `0x180004f0f`: `__archive_read_register_format`
- `0x180004eba`: `archive_read_support_format_tar`

## pseudocode

```c
__int64 __fastcall archive_read_support_format_tar(__int64 a1)
{
  void *v3; // rdi
  int i; // eax
  __int64 v5; // rdx
  __int64 (__fastcall *v6)(_QWORD, _QWORD); // rcx

  if ( (unsigned int)_archive_check_magic(a1, 14594245, 1, "archive_read_support_format_tar") == -30 )
    return 4294967266LL;
  v3 = calloc(1u, 0x158u);
  if ( !v3 )
  {
    archive_set_error(a1, 12, "Can't allocate tar data");
    return 4294967266LL;
  }
  if ( (unsigned int)_archive_check_magic(a1, 14594245, 1, "__archive_read_register_format") != -30 )
  {
    for ( i = 0; i < 16; ++i )
    {
      v5 = 88LL * i;
      v6 = *(__int64 (__fastcall **)(_QWORD, _QWORD))(v5 + a1 + 680);
      if ( v6 == archive_read_format_tar_bid )
        goto LABEL_13;
      if ( !v6 )
      {
        *(_QWORD *)(v5 + a1 + 680) = archive_read_format_tar_bid;
        *(_QWORD *)(v5 + a1 + 688) = &archive_read_format_tar_options;
        *(_QWORD *)(v5 + a1 + 696) = archive_read_format_tar_read_header;
        *(_QWORD *)(v5 + a1 + 720) = 0;
        *(_QWORD *)(v5 + a1 + 664) = v3;
        *(_QWORD *)(v5 + a1 + 736) = 0;
        *(_QWORD *)(v5 + a1 + 744) = 0;
        *(_QWORD *)(88 * (i + 8LL) + a1) = archive_read_format_tar_read_data;
        *(_QWORD *)(v5 + a1 + 712) = archive_read_format_tar_skip;
        *(_QWORD *)(v5 + a1 + 728) = archive_read_format_tar_cleanup;
        *(_QWORD *)(v5 + a1 + 672) = "tar";
        return 0;
      }
    }
    archive_set_error(a1, 12, "Not enough slots for format registration", archive_read_format_tar_bid);
  }
LABEL_13:
  free(v3);
  return 0;
}

```

## disassembly

```asm
0x180004eb0  mov     [rsp+arg_0], rbx
0x180004eb5  push    rdi
0x180004eb6  sub     rsp, 20h
0x180004eba  lea     r9, aArchiveReadSup_53; "archive_read_support_format_tar"
0x180004ec1  mov     edx, 0DEB0C5h
0x180004ec6  mov     r8d, 1
0x180004ecc  mov     rbx, rcx
0x180004ecf  call    __archive_check_magic
0x180004ed4  cmp     eax, 0FFFFFFE2h
0x180004ed7  jnz     short loc_180004EE3
0x180004ed9  mov     eax, 0FFFFFFE2h
0x180004ede  jmp     loc_180005015
0x180004ee3  mov     edx, 158h; Size
0x180004ee8  mov     ecx, 1; Count
0x180004eed  call    cs:__imp_calloc
0x180004ef3  mov     rdi, rax
0x180004ef6  mov     rcx, rbx
0x180004ef9  test    rax, rax
0x180004efc  jnz     short loc_180004F0F
0x180004efe  lea     r8, aCanTAllocateTa; "Can't allocate tar data"
0x180004f05  lea     edx, [rax+0Ch]
0x180004f08  call    archive_set_error
0x180004f0d  jmp     short loc_180004ED9
0x180004f0f  lea     r9, aArchiveReadReg; "__archive_read_register_format"
0x180004f16  mov     edx, 0DEB0C5h
0x180004f1b  mov     r8d, 1
0x180004f21  call    __archive_check_magic
0x180004f26  cmp     eax, 0FFFFFFE2h
0x180004f29  jz      loc_18000500A
0x180004f2f  xor     eax, eax
0x180004f31  lea     r9, archive_read_format_tar_bid
0x180004f38  cmp     eax, 10h
0x180004f3b  jge     loc_180004FF6
0x180004f41  movsxd  r8, eax
0x180004f44  imul    rdx, r8, 58h ; 'X'
0x180004f48  mov     rcx, [rdx+rbx+2A8h]
0x180004f50  cmp     rcx, r9
0x180004f53  jz      loc_18000500A
0x180004f59  test    rcx, rcx
0x180004f5c  jz      short loc_180004F62
0x180004f5e  inc     eax
0x180004f60  jmp     short loc_180004F38
0x180004f62  lea     rax, archive_read_format_tar_options
0x180004f69  mov     [rdx+rbx+2A8h], r9
0x180004f71  mov     [rdx+rbx+2B0h], rax
0x180004f79  lea     rax, archive_read_format_tar_read_header
0x180004f80  mov     [rdx+rbx+2B8h], rax
0x180004f88  lea     rax, [r8+8]
0x180004f8c  imul    rcx, rax, 58h ; 'X'
0x180004f90  lea     rax, archive_read_format_tar_read_data
0x180004f97  mov     qword ptr [rdx+rbx+2D0h], 0
0x180004fa3  mov     [rdx+rbx+298h], rdi
0x180004fab  mov     qword ptr [rdx+rbx+2E0h], 0
0x180004fb7  mov     qword ptr [rdx+rbx+2E8h], 0
0x180004fc3  mov     [rcx+rbx], rax
0x180004fc7  lea     rax, archive_read_format_tar_skip
0x180004fce  mov     [rdx+rbx+2C8h], rax
0x180004fd6  lea     rax, archive_read_format_tar_cleanup
0x180004fdd  mov     [rdx+rbx+2D8h], rax
0x180004fe5  lea     rax, aTar_0; "tar"
0x180004fec  mov     [rdx+rbx+2A0h], rax
0x180004ff4  jmp     short loc_180005013
0x180004ff6  lea     r8, aNotEnoughSlots_0; "Not enough slots for format registratio"...
0x180004ffd  mov     edx, 0Ch
0x180005002  mov     rcx, rbx
0x180005005  call    archive_set_error
0x18000500a  mov     rcx, rdi; Block
0x18000500d  call    cs:__imp_free
0x180005013  xor     eax, eax
0x180005015  mov     rbx, [rsp+28h+arg_0]
0x18000501a  add     rsp, 20h
0x18000501e  pop     rdi
0x18000501f  retn
```
