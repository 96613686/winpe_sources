# _archive_write_disk_free

- ea: `0x1800f4ef0`
- end: `0x1800f501e`
- name: `_archive_write_disk_free`
- size: `302`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x18000523c`
- `0x18000e7ec`
- `0x1800b1b60`
- `0x1800f49d0`
- `0x1800f4ef0`
- `0x1800f5640`
- `0x1800f5740`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800f4f76`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800f4f98`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800f4fb1`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800f4fd0`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800f5000`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800f500d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800f4f76`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800f4f98`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800f4fb1`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800f4fd0`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800f5000`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800f500d`

## string_xrefs

- `0x1800f4f0a`: `archive_write_disk_free`

## pseudocode

```c
__int64 __fastcall archive_write_disk_free(_QWORD *Block)
{
  __int64 result; // rax
  unsigned int v3; // esi
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx
  _QWORD *v8; // rcx
  _QWORD *v9; // rbx
  void *v10; // rcx

  if ( !Block )
    return 0;
  result = _archive_check_magic(Block, 3221336261LL, 0xFFFF, "archive_write_disk_free");
  if ( (_DWORD)result != -30 )
  {
    v3 = archive_write_disk_close((__int64)Block);
    archive_write_disk_set_group_lookup(Block, 0, 0, 0);
    archive_write_disk_set_user_lookup(Block, 0, 0, 0);
    archive_entry_free(Block[43]);
    v4 = (void *)Block[45];
    Block[46] = 0;
    Block[47] = 0;
    free(v4);
    Block[45] = 0;
    v5 = (void *)Block[49];
    Block[50] = 0;
    Block[51] = 0;
    free(v5);
    Block[49] = 0;
    v6 = (void *)Block[6];
    Block[7] = 0;
    Block[8] = 0;
    free(v6);
    Block[6] = 0;
    v7 = (void *)Block[32];
    Block[33] = 0;
    Block[34] = 0;
    free(v7);
    Block[32] = 0;
    *(_DWORD *)Block = 0;
    v8 = (_QWORD *)Block[11];
    if ( v8 )
    {
      do
      {
        v9 = (_QWORD *)*v8;
        free_sconv_object();
        v8 = v9;
      }
      while ( v9 );
    }
    v10 = (void *)Block[9];
    Block[11] = 0;
    free(v10);
    Block[9] = 0;
    free(Block);
    return v3;
  }
  return result;
}

```

## disassembly

```asm
0x1800f4ef0  push    rbx
0x1800f4ef2  push    rbp
0x1800f4ef3  push    rsi
0x1800f4ef4  push    rdi
0x1800f4ef5  sub     rsp, 28h
0x1800f4ef9  xor     ebp, ebp
0x1800f4efb  mov     rdi, rcx
0x1800f4efe  test    rcx, rcx
0x1800f4f01  jnz     short loc_1800F4F0A
0x1800f4f03  xor     eax, eax
0x1800f4f05  jmp     loc_1800F5015
0x1800f4f0a  lea     r9, aArchiveWriteDi_10; "archive_write_disk_free"
0x1800f4f11  mov     edx, 0C001B0C5h
0x1800f4f16  mov     r8d, 0FFFFh
0x1800f4f1c  call    __archive_check_magic
0x1800f4f21  cmp     eax, 0FFFFFFE2h
0x1800f4f24  jnz     short loc_1800F4F2B
0x1800f4f26  jmp     loc_1800F5015
0x1800f4f2b  mov     rcx, rdi
0x1800f4f2e  call    _archive_write_disk_close
0x1800f4f33  xor     r9d, r9d
0x1800f4f36  xor     r8d, r8d
0x1800f4f39  xor     edx, edx
0x1800f4f3b  mov     rcx, rdi
0x1800f4f3e  mov     esi, eax
0x1800f4f40  call    archive_write_disk_set_group_lookup
0x1800f4f45  xor     r9d, r9d
0x1800f4f48  xor     r8d, r8d
0x1800f4f4b  xor     edx, edx
0x1800f4f4d  mov     rcx, rdi
0x1800f4f50  call    archive_write_disk_set_user_lookup
0x1800f4f55  mov     rcx, [rdi+158h]
0x1800f4f5c  call    archive_entry_free
0x1800f4f61  mov     rcx, [rdi+168h]; Block
0x1800f4f68  mov     [rdi+170h], rbp
0x1800f4f6f  mov     [rdi+178h], rbp
0x1800f4f76  call    cs:__imp_free
0x1800f4f7c  mov     [rdi+168h], rbp
0x1800f4f83  mov     rcx, [rdi+188h]; Block
0x1800f4f8a  mov     [rdi+190h], rbp
0x1800f4f91  mov     [rdi+198h], rbp
0x1800f4f98  call    cs:__imp_free
0x1800f4f9e  mov     [rdi+188h], rbp
0x1800f4fa5  mov     rcx, [rdi+30h]; Block
0x1800f4fa9  mov     [rdi+38h], rbp
0x1800f4fad  mov     [rdi+40h], rbp
0x1800f4fb1  call    cs:__imp_free
0x1800f4fb7  mov     [rdi+30h], rbp
0x1800f4fbb  mov     rcx, [rdi+100h]; Block
0x1800f4fc2  mov     [rdi+108h], rbp
0x1800f4fc9  mov     [rdi+110h], rbp
0x1800f4fd0  call    cs:__imp_free
0x1800f4fd6  mov     [rdi+100h], rbp
0x1800f4fdd  mov     [rdi], ebp
0x1800f4fdf  mov     rcx, [rdi+58h]
0x1800f4fe3  test    rcx, rcx
0x1800f4fe6  jz      short loc_1800F4FF8
0x1800f4fe8  mov     rbx, [rcx]
0x1800f4feb  call    free_sconv_object
0x1800f4ff0  mov     rcx, rbx
0x1800f4ff3  test    rbx, rbx
0x1800f4ff6  jnz     short loc_1800F4FE8
0x1800f4ff8  mov     rcx, [rdi+48h]; Block
0x1800f4ffc  mov     [rdi+58h], rbp
0x1800f5000  call    cs:__imp_free
0x1800f5006  mov     rcx, rdi; Block
0x1800f5009  mov     [rdi+48h], rbp
0x1800f500d  call    cs:__imp_free
0x1800f5013  mov     eax, esi
0x1800f5015  add     rsp, 28h
0x1800f5019  pop     rdi
0x1800f501a  pop     rsi
0x1800f501b  pop     rbp
0x1800f501c  pop     rbx
0x1800f501d  retn
```
