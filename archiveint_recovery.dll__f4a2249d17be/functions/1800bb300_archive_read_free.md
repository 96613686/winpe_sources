# _archive_read_free

- ea: `0x1800bb300`
- end: `0x1800bb4aa`
- name: `_archive_read_free`
- size: `426`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x18000523c`
- `0x18000e7ec`
- `0x180015810`
- `0x1800b1b60`
- `0x1800bb0e8`
- `0x1800bb300`
- `0x1800eec10`
- `0x18011a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800bb40b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800bb414`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800bb436`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800bb47b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800bb490`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800bb499`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800bb40b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800bb414`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800bb436`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800bb47b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800bb490`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800bb499`

## string_xrefs

- `0x1800bb318`: `archive_read_free`

## pseudocode

```c
__int64 __fastcall archive_read_free(char *Block)
{
  __int64 result; // rax
  unsigned int close; // esi
  __int64 (__fastcall *v4)(char *); // rax
  __int64 i; // rbx
  void (__fastcall *v6)(char *); // rax
  __int64 j; // rbx
  __int64 v8; // rcx
  void (__fastcall *v9)(char *); // rax
  __int64 v10; // rbx
  __int64 v11; // rbp
  size_t v12; // r8
  _BYTE *v13; // rcx
  void *v14; // rcx
  _QWORD *v15; // rcx
  _QWORD *v16; // rbx
  void *v17; // rcx

  if ( !Block )
    return 0;
  result = _archive_check_magic(Block, 14594245, 0xFFFF, "archive_read_free");
  if ( (_DWORD)result != -30 )
  {
    close = 0;
    if ( *((_DWORD *)Block + 1) != 32 && *((_DWORD *)Block + 1) != 0x8000 )
      close = archive_read_close(Block);
    v4 = (__int64 (__fastcall *)(char *))*((_QWORD *)Block + 261);
    if ( v4 )
      close = v4(Block);
    for ( i = 0; i != 16; ++i )
    {
      *((_QWORD *)Block + 259) = &Block[88 * i + 664];
      v6 = *(void (__fastcall **)(char *))&Block[88 * i + 728];
      if ( v6 )
        v6(Block);
    }
    _archive_read_free_filters(Block);
    for ( j = 0; j != 16; ++j )
    {
      v8 = *(_QWORD *)&Block[24 * j + 264];
      if ( v8 )
      {
        v9 = *(void (__fastcall **)(char *))(v8 + 16);
        if ( v9 )
          v9(&Block[16 * j + 248 + 8 * j]);
      }
    }
    v10 = *((_QWORD *)Block + 262);
    if ( v10 )
    {
      do
      {
        v11 = *(_QWORD *)(v10 + 8);
        v12 = -1;
        v13 = *(_BYTE **)v10;
        do
          ++v12;
        while ( v13[v12] );
        memset_0(v13, 0, v12);
        free(*(void **)v10);
        free((void *)v10);
        v10 = v11;
      }
      while ( v11 );
    }
    v14 = (void *)*((_QWORD *)Block + 6);
    *((_QWORD *)Block + 7) = 0;
    *((_QWORD *)Block + 8) = 0;
    free(v14);
    *((_QWORD *)Block + 6) = 0;
    archive_entry_free(*((_QWORD *)Block + 18));
    *(_DWORD *)Block = 0;
    v15 = (_QWORD *)*((_QWORD *)Block + 11);
    if ( v15 )
    {
      do
      {
        v16 = (_QWORD *)*v15;
        free_sconv_object();
        v15 = v16;
      }
      while ( v16 );
    }
    v17 = (void *)*((_QWORD *)Block + 9);
    *((_QWORD *)Block + 11) = 0;
    free(v17);
    *((_QWORD *)Block + 9) = 0;
    free(*((void **)Block + 30));
    free(Block);
    return close;
  }
  return result;
}

```

## disassembly

```asm
0x1800bb300  push    rbx
0x1800bb302  push    rbp
0x1800bb303  push    rsi
0x1800bb304  push    rdi
0x1800bb305  sub     rsp, 28h
0x1800bb309  mov     rdi, rcx
0x1800bb30c  test    rcx, rcx
0x1800bb30f  jnz     short loc_1800BB318
0x1800bb311  xor     eax, eax
0x1800bb313  jmp     loc_1800BB4A1
0x1800bb318  lea     r9, aArchiveReadFre_0; "archive_read_free"
0x1800bb31f  mov     edx, 0DEB0C5h
0x1800bb324  mov     r8d, 0FFFFh
0x1800bb32a  call    __archive_check_magic
0x1800bb32f  cmp     eax, 0FFFFFFE2h
0x1800bb332  jnz     short loc_1800BB339
0x1800bb334  jmp     loc_1800BB4A1
0x1800bb339  xor     esi, esi
0x1800bb33b  cmp     dword ptr [rdi+4], 20h ; ' '
0x1800bb33f  jz      short loc_1800BB354
0x1800bb341  cmp     dword ptr [rdi+4], 8000h
0x1800bb348  jz      short loc_1800BB354
0x1800bb34a  mov     rcx, rdi
0x1800bb34d  call    archive_read_close
0x1800bb352  mov     esi, eax
0x1800bb354  mov     rax, [rdi+828h]
0x1800bb35b  test    rax, rax
0x1800bb35e  jz      short loc_1800BB36A
0x1800bb360  mov     rcx, rdi
0x1800bb363  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bb368  mov     esi, eax
0x1800bb36a  xor     ebx, ebx
0x1800bb36c  imul    rcx, rbx, 58h ; 'X'
0x1800bb370  lea     rax, [rdi+298h]
0x1800bb377  add     rax, rcx
0x1800bb37a  mov     [rdi+818h], rax
0x1800bb381  mov     rax, [rcx+rdi+2D8h]
0x1800bb389  test    rax, rax
0x1800bb38c  jz      short loc_1800BB396
0x1800bb38e  mov     rcx, rdi
0x1800bb391  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bb396  inc     rbx
0x1800bb399  cmp     rbx, 10h
0x1800bb39d  jnz     short loc_1800BB36C
0x1800bb39f  mov     rcx, rdi
0x1800bb3a2  call    __archive_read_free_filters
0x1800bb3a7  xor     ebx, ebx
0x1800bb3a9  lea     rax, [rbx+rbx*2]
0x1800bb3ad  mov     rcx, [rdi+rax*8+108h]
0x1800bb3b5  test    rcx, rcx
0x1800bb3b8  jz      short loc_1800BB3D7
0x1800bb3ba  mov     rax, [rcx+10h]
0x1800bb3be  test    rax, rax
0x1800bb3c1  jz      short loc_1800BB3D7
0x1800bb3c3  lea     rcx, ds:1Fh[rbx*2]
0x1800bb3cb  add     rcx, rbx
0x1800bb3ce  lea     rcx, [rdi+rcx*8]
0x1800bb3d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bb3d7  inc     rbx
0x1800bb3da  cmp     rbx, 10h
0x1800bb3de  jnz     short loc_1800BB3A9
0x1800bb3e0  mov     rbx, [rdi+830h]
0x1800bb3e7  test    rbx, rbx
0x1800bb3ea  jz      short loc_1800BB422
0x1800bb3ec  mov     rbp, [rbx+8]
0x1800bb3f0  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800bb3f4  mov     rcx, [rbx]; void *
0x1800bb3f7  inc     r8; Size
0x1800bb3fa  cmp     byte ptr [rcx+r8], 0
0x1800bb3ff  jnz     short loc_1800BB3F7
0x1800bb401  xor     edx, edx; Val
0x1800bb403  call    memset_0
0x1800bb408  mov     rcx, [rbx]; Block
0x1800bb40b  call    cs:__imp_free
0x1800bb411  mov     rcx, rbx; Block
0x1800bb414  call    cs:__imp_free
0x1800bb41a  mov     rbx, rbp
0x1800bb41d  test    rbp, rbp
0x1800bb420  jnz     short loc_1800BB3EC
0x1800bb422  mov     rcx, [rdi+30h]; Block
0x1800bb426  mov     qword ptr [rdi+38h], 0
0x1800bb42e  mov     qword ptr [rdi+40h], 0
0x1800bb436  call    cs:__imp_free
0x1800bb43c  mov     qword ptr [rdi+30h], 0
0x1800bb444  mov     rcx, [rdi+90h]
0x1800bb44b  call    archive_entry_free
0x1800bb450  mov     dword ptr [rdi], 0
0x1800bb456  mov     rcx, [rdi+58h]
0x1800bb45a  test    rcx, rcx
0x1800bb45d  jz      short loc_1800BB46F
0x1800bb45f  mov     rbx, [rcx]
0x1800bb462  call    free_sconv_object
0x1800bb467  mov     rcx, rbx
0x1800bb46a  test    rbx, rbx
0x1800bb46d  jnz     short loc_1800BB45F
0x1800bb46f  mov     rcx, [rdi+48h]; Block
0x1800bb473  mov     qword ptr [rdi+58h], 0
0x1800bb47b  call    cs:__imp_free
0x1800bb481  mov     qword ptr [rdi+48h], 0
0x1800bb489  mov     rcx, [rdi+0F0h]; Block
0x1800bb490  call    cs:__imp_free
0x1800bb496  mov     rcx, rdi; Block
0x1800bb499  call    cs:__imp_free
0x1800bb49f  mov     eax, esi
0x1800bb4a1  add     rsp, 28h
0x1800bb4a5  pop     rdi
0x1800bb4a6  pop     rsi
0x1800bb4a7  pop     rbp
0x1800bb4a8  pop     rbx
0x1800bb4a9  retn
```
