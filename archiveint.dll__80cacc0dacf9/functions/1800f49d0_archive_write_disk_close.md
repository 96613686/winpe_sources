# _archive_write_disk_close

- ea: `0x1800f49d0`
- end: `0x1800f4ae8`
- name: `_archive_write_disk_close`
- size: `280`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x1800f4ef0`

## callees

- `0x18000523c`
- `0x18000e568`
- `0x1800f49d0`
- `0x1800f4c10`
- `0x1800f6ba4`
- `0x1800f7890`
- `0x1800f7aa0`
- `0x1800f7cbc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800f4ab5`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800f4abe`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800f4ab5`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800f4abe`

## string_xrefs

- `0x1800f49db`: `archive_write_disk_close`

## pseudocode

```c
__int64 __fastcall archive_write_disk_close(__int64 a1)
{
  __int64 result; // rax
  unsigned int v3; // ebp
  char *v4; // rdi
  const WCHAR **v5; // r14
  char *v6; // rbx
  FILETIME v7; // [rsp+50h] [rbp-38h]

  result = _archive_check_magic(a1, 3221336261LL, 6, "archive_write_disk_close");
  if ( (_DWORD)result != -30 )
  {
    v3 = archive_write_disk_finish_entry(a1);
    v4 = (char *)sort_dir_list(*(_QWORD *)(a1 + 152));
    if ( v4 )
    {
      do
      {
        *(_QWORD *)(a1 + 336) = 0;
        v5 = (const WCHAR **)(v4 + 128);
        if ( (v4[124] & 4) != 0 )
          set_times(
            a1,
            -1,
            *((_WORD *)v4 + 32),
            *v5,
            *((_QWORD *)v4 + 9),
            *((_DWORD *)v4 + 26),
            *((_QWORD *)v4 + 10),
            *((_DWORD *)v4 + 27),
            *((_QWORD *)v4 + 11),
            *((_DWORD *)v4 + 28),
            v7);
        if ( (*((_DWORD *)v4 + 31) & 0x20000000) != 0 )
          la_chmod(*v5, *((_WORD *)v4 + 32));
        if ( (v4[124] & 0x40) != 0 )
          set_fflags_platform(*v5, *((_DWORD *)v4 + 30), 0);
        v6 = *(char **)v4;
        archive_acl_clear(v4 + 8);
        free((void *)*v5);
        free(v4);
        v4 = v6;
      }
      while ( v6 );
    }
    *(_QWORD *)(a1 + 152) = 0;
    return v3;
  }
  return result;
}

```

## disassembly

```asm
0x1800f49d0  push    rbx
0x1800f49d2  push    rbp
0x1800f49d3  push    rsi
0x1800f49d4  push    rdi
0x1800f49d5  push    r14
0x1800f49d7  sub     rsp, 60h
0x1800f49db  lea     r9, aArchiveWriteDi_12; "archive_write_disk_close"
0x1800f49e2  mov     edx, 0C001B0C5h
0x1800f49e7  mov     r8d, 6
0x1800f49ed  mov     rsi, rcx
0x1800f49f0  call    __archive_check_magic
0x1800f49f5  cmp     eax, 0FFFFFFE2h
0x1800f49f8  jnz     short loc_1800F49FF
0x1800f49fa  jmp     loc_1800F4ADD
0x1800f49ff  mov     rcx, rsi
0x1800f4a02  call    _archive_write_disk_finish_entry
0x1800f4a07  mov     rcx, [rsi+98h]
0x1800f4a0e  mov     ebp, eax
0x1800f4a10  call    sort_dir_list
0x1800f4a15  mov     rdi, rax
0x1800f4a18  test    rax, rax
0x1800f4a1b  jz      loc_1800F4AD0
0x1800f4a21  mov     qword ptr [rsi+150h], 0
0x1800f4a2c  lea     r14, [rdi+80h]
0x1800f4a33  test    byte ptr [rdi+7Ch], 4
0x1800f4a37  jz      short loc_1800F4A7D
0x1800f4a39  mov     eax, [rdi+70h]
0x1800f4a3c  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800f4a40  movzx   r8d, word ptr [rdi+40h]
0x1800f4a45  mov     rcx, rsi
0x1800f4a48  mov     r9, [r14]
0x1800f4a4b  mov     [rsp+88h+var_40], eax
0x1800f4a4f  mov     rax, [rdi+58h]
0x1800f4a53  mov     [rsp+88h+var_48], rax
0x1800f4a58  mov     eax, [rdi+6Ch]
0x1800f4a5b  mov     [rsp+88h+var_50], eax
0x1800f4a5f  mov     rax, [rdi+50h]
0x1800f4a63  mov     [rsp+88h+var_58], rax
0x1800f4a68  mov     eax, [rdi+68h]
0x1800f4a6b  mov     [rsp+88h+var_60], eax
0x1800f4a6f  mov     rax, [rdi+48h]
0x1800f4a73  mov     [rsp+88h+var_68], rax
0x1800f4a78  call    set_times
0x1800f4a7d  test    dword ptr [rdi+7Ch], 20000000h
0x1800f4a84  jz      short loc_1800F4A92
0x1800f4a86  movzx   edx, word ptr [rdi+40h]
0x1800f4a8a  mov     rcx, [r14]; lpFileName
0x1800f4a8d  call    la_chmod
0x1800f4a92  test    byte ptr [rdi+7Ch], 40h
0x1800f4a96  jz      short loc_1800F4AA6
0x1800f4a98  mov     edx, [rdi+78h]
0x1800f4a9b  xor     r8d, r8d
0x1800f4a9e  mov     rcx, [r14]; lpFileName
0x1800f4aa1  call    set_fflags_platform
0x1800f4aa6  mov     rbx, [rdi]
0x1800f4aa9  lea     rcx, [rdi+8]
0x1800f4aad  call    archive_acl_clear
0x1800f4ab2  mov     rcx, [r14]; Block
0x1800f4ab5  call    cs:__imp_free
0x1800f4abb  mov     rcx, rdi; Block
0x1800f4abe  call    cs:__imp_free
0x1800f4ac4  mov     rdi, rbx
0x1800f4ac7  test    rbx, rbx
0x1800f4aca  jnz     loc_1800F4A21
0x1800f4ad0  mov     qword ptr [rsi+98h], 0
0x1800f4adb  mov     eax, ebp
0x1800f4add  add     rsp, 60h
0x1800f4ae1  pop     r14
0x1800f4ae3  pop     rdi
0x1800f4ae4  pop     rsi
0x1800f4ae5  pop     rbp
0x1800f4ae6  pop     rbx
0x1800f4ae7  retn
```
