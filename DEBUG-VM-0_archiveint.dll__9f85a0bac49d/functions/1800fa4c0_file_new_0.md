# file_new_0

- ea: `0x1800fa4c0`
- end: `0x1800fa6fa`
- name: `file_new_0`
- size: `570`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, loader_planting`

## callers

- `0x1800f9240`

## callees

- `0x180006c00`
- `0x1800aba54`
- `0x1800b27e0`
- `0x1800ed038`
- `0x1800fa4c0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800fa562`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800fa562`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x1800fa506`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x1800fa506`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800fa570`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800fa5b1`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800fa660`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800fa570`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800fa5b1`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800fa660`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800fa59f`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800fa59f`

## string_xrefs

- `0x1800fa57f`: `A filename cannot be converted to UTF-16LE;You should disable making Joliet extension`
- `0x1800fa666`: `symlink path could not be converted to UTF-8`

## pseudocode

```c
__int64 __fastcall file_new_0(__int64 a1, __int64 a2, _QWORD *a3)
{
  __int64 v3; // rbp
  void *v7; // rbx
  unsigned int v9; // r15d
  int mbs_l; // eax
  __int64 v11; // rcx
  __int64 v12; // rbp
  size_t v13; // r14
  void *v14; // rax
  int i; // ecx
  __int64 v16; // rax
  __int16 v17; // cx
  __int64 v18; // rax
  size_t Size; // [rsp+60h] [rbp+8h] BYREF
  void *Src; // [rsp+70h] [rbp+18h] BYREF

  v3 = *(_QWORD *)(a1 + 248);
  Src = 0;
  Size = 0;
  *a3 = 0;
  v7 = calloc(1u, 0x80u);
  if ( !v7 )
  {
    archive_set_error(a1, 12, "Can't allocate memory");
    return 4294967266LL;
  }
  v9 = 0;
  mbs_l = archive_mstring_get_mbs_l(
            *(_QWORD *)a2,
            (int)a2 + 488,
            (unsigned int)&Src,
            (unsigned int)&Size,
            *(_QWORD *)(v3 + 264));
  v12 = -1;
  if ( mbs_l < 0 )
  {
    if ( *(_DWORD *)_o__errno(v11) == 12 )
    {
      free(v7);
      archive_set_error(a1, 12, "Can't allocate memory for UTF-16LE");
      return 4294967266LL;
    }
    archive_set_error(
      a1,
      0xFFFFFFFFLL,
      "A filename cannot be converted to UTF-16LE;You should disable making Joliet extension");
    v9 = -20;
  }
  v13 = Size;
  v14 = malloc(Size + 2);
  *((_QWORD *)v7 + 5) = v14;
  if ( !v14 )
  {
    free(v7);
    archive_set_error(a1, 12, "Can't allocate memory for Name");
    return 4294967266LL;
  }
  memcpy_0(v14, Src, v13);
  for ( i = 0; i < 2; ++i )
  {
    v16 = (unsigned int)i;
    *(_BYTE *)(*((_QWORD *)v7 + 5) + v16 + v13) = 0;
  }
  *((_DWORD *)v7 + 8) = v13;
  *((_WORD *)v7 + 56) = *(_WORD *)(a2 + 1032);
  if ( (*(_WORD *)(a2 + 1032) & 0xF000) == 0x8000 )
  {
    *((_QWORD *)v7 + 6) = *(_QWORD *)(a2 + 112);
  }
  else
  {
    *(_DWORD *)(a2 + 160) |= 0x40u;
    *(_DWORD *)(a2 + 16) = 0;
    *(_QWORD *)(a2 + 112) = 0;
  }
  v17 = *(_WORD *)(a2 + 1032) & 0xF000;
  if ( v17 == 0x4000 )
  {
    *((_DWORD *)v7 + 30) |= 1u;
  }
  else if ( v17 == -24576 )
  {
    v18 = archive_entry_symlink_utf8(a2);
    if ( !v18 )
    {
      free(v7);
      archive_set_error(a1, 0xFFFFFFFFLL, "symlink path could not be converted to UTF-8");
      return 4294967271LL;
    }
    do
      ++v12;
    while ( *(_BYTE *)(v18 + v12) );
    *((_QWORD *)v7 + 6) = v12;
  }
  if ( (*(_BYTE *)(a2 + 160) & 0x10) != 0 )
  {
    *((_DWORD *)v7 + 14) |= 1u;
    *((_QWORD *)v7 + 8) = *(_QWORD *)(a2 + 56);
    *((_DWORD *)v7 + 18) = *(_DWORD *)(a2 + 64);
  }
  if ( (*(_BYTE *)(a2 + 160) & 4) != 0 )
  {
    *((_DWORD *)v7 + 14) |= 2u;
    *((_QWORD *)v7 + 10) = *(_QWORD *)(a2 + 24);
    *((_DWORD *)v7 + 22) = *(_DWORD *)(a2 + 32);
  }
  if ( (*(_BYTE *)(a2 + 160) & 8) != 0 )
  {
    *((_DWORD *)v7 + 14) |= 4u;
    *((_QWORD *)v7 + 12) = *(_QWORD *)(a2 + 40);
    *((_DWORD *)v7 + 26) = *(_DWORD *)(a2 + 48);
  }
  *a3 = v7;
  return v9;
}

```

## disassembly

```asm
0x1800fa4c0  mov     rax, rsp
0x1800fa4c3  mov     [rax+10h], rbx
0x1800fa4c7  mov     [rax+20h], rbp
0x1800fa4cb  push    rsi
0x1800fa4cc  push    rdi
0x1800fa4cd  push    r12
0x1800fa4cf  push    r14
0x1800fa4d1  push    r15
0x1800fa4d3  sub     rsp, 30h
0x1800fa4d7  mov     rbp, [rcx+0F8h]
0x1800fa4de  mov     rdi, rdx
0x1800fa4e1  mov     edx, 80h; Size
0x1800fa4e6  mov     qword ptr [rax+18h], 0
0x1800fa4ee  mov     rsi, rcx
0x1800fa4f1  mov     qword ptr [rax+8], 0
0x1800fa4f9  mov     r12, r8
0x1800fa4fc  mov     qword ptr [r8], 0
0x1800fa503  lea     ecx, [rdx-7Fh]; Count
0x1800fa506  call    cs:__imp_calloc
0x1800fa50c  mov     rbx, rax
0x1800fa50f  test    rax, rax
0x1800fa512  jnz     short loc_1800FA532
0x1800fa514  lea     r8, aCanTAllocateMe_30; "Can't allocate memory"
0x1800fa51b  mov     edx, 0Ch
0x1800fa520  mov     rcx, rsi
0x1800fa523  call    archive_set_error
0x1800fa528  mov     eax, 0FFFFFFE2h
0x1800fa52d  jmp     loc_1800FA6E3
0x1800fa532  mov     rax, [rbp+108h]
0x1800fa539  lea     rdx, [rdi+1E8h]
0x1800fa540  mov     rcx, [rdi]
0x1800fa543  lea     r9, [rsp+58h+Size]
0x1800fa548  lea     r8, [rsp+58h+Src]
0x1800fa54d  mov     [rsp+58h+var_38], rax
0x1800fa552  xor     r15d, r15d
0x1800fa555  call    archive_mstring_get_mbs_l
0x1800fa55a  or      rbp, 0FFFFFFFFFFFFFFFFh
0x1800fa55e  test    eax, eax
0x1800fa560  jns     short loc_1800FA596
0x1800fa562  call    cs:__imp__o__errno
0x1800fa568  cmp     dword ptr [rax], 0Ch
0x1800fa56b  jnz     short loc_1800FA57F
0x1800fa56d  mov     rcx, rbx; Block
0x1800fa570  call    cs:__imp_free
0x1800fa576  lea     r8, aCanTAllocateMe_4; "Can't allocate memory for UTF-16LE"
0x1800fa57d  jmp     short loc_1800FA51B
0x1800fa57f  lea     r8, aAFilenameCanno; "A filename cannot be converted to UTF-1"...
0x1800fa586  mov     edx, ebp
0x1800fa588  mov     rcx, rsi
0x1800fa58b  call    archive_set_error
0x1800fa590  mov     r15d, 0FFFFFFECh
0x1800fa596  mov     r14, [rsp+58h+Size]
0x1800fa59b  lea     rcx, [r14+2]; Size
0x1800fa59f  call    cs:__imp_malloc
0x1800fa5a5  mov     [rbx+28h], rax
0x1800fa5a9  test    rax, rax
0x1800fa5ac  jnz     short loc_1800FA5C3
0x1800fa5ae  mov     rcx, rbx; Block
0x1800fa5b1  call    cs:__imp_free
0x1800fa5b7  lea     r8, aCanTAllocateMe_18; "Can't allocate memory for Name"
0x1800fa5be  jmp     loc_1800FA51B
0x1800fa5c3  mov     rdx, [rsp+58h+Src]; Src
0x1800fa5c8  mov     r8, r14; Size
0x1800fa5cb  mov     rcx, rax; void *
0x1800fa5ce  call    memcpy_0
0x1800fa5d3  xor     ecx, ecx
0x1800fa5d5  mov     eax, ecx
0x1800fa5d7  inc     ecx
0x1800fa5d9  add     rax, [rbx+28h]
0x1800fa5dd  mov     byte ptr [rax+r14], 0
0x1800fa5e2  cmp     ecx, 2
0x1800fa5e5  jl      short loc_1800FA5D5
0x1800fa5e7  mov     [rbx+20h], r14d
0x1800fa5eb  mov     ecx, 0F000h
0x1800fa5f0  movzx   eax, word ptr [rdi+408h]
0x1800fa5f7  mov     edx, 8000h
0x1800fa5fc  mov     [rbx+70h], ax
0x1800fa600  movzx   eax, word ptr [rdi+408h]
0x1800fa607  and     ax, cx
0x1800fa60a  cmp     ax, dx
0x1800fa60d  jnz     short loc_1800FA619
0x1800fa60f  mov     rax, [rdi+70h]
0x1800fa613  mov     [rbx+30h], rax
0x1800fa617  jmp     short loc_1800FA62F
0x1800fa619  or      dword ptr [rdi+0A0h], 40h
0x1800fa620  mov     dword ptr [rdi+10h], 0
0x1800fa627  mov     qword ptr [rdi+70h], 0
0x1800fa62f  and     cx, [rdi+408h]
0x1800fa636  mov     eax, 4000h
0x1800fa63b  cmp     cx, ax
0x1800fa63e  jnz     short loc_1800FA646
0x1800fa640  or      dword ptr [rbx+78h], 1
0x1800fa644  jmp     short loc_1800FA68B
0x1800fa646  mov     eax, 0A000h
0x1800fa64b  cmp     cx, ax
0x1800fa64e  jnz     short loc_1800FA68B
0x1800fa650  mov     rcx, rdi
0x1800fa653  call    archive_entry_symlink_utf8
0x1800fa658  test    rax, rax
0x1800fa65b  jnz     short loc_1800FA67E
0x1800fa65d  mov     rcx, rbx; Block
0x1800fa660  call    cs:__imp_free
0x1800fa666  lea     r8, aSymlinkPathCou; "symlink path could not be converted to "...
0x1800fa66d  mov     edx, ebp
0x1800fa66f  mov     rcx, rsi
0x1800fa672  call    archive_set_error
0x1800fa677  mov     eax, 0FFFFFFE7h
0x1800fa67c  jmp     short loc_1800FA6E3
0x1800fa67e  inc     rbp
0x1800fa681  cmp     byte ptr [rax+rbp], 0
0x1800fa685  jnz     short loc_1800FA67E
0x1800fa687  mov     [rbx+30h], rbp
0x1800fa68b  test    byte ptr [rdi+0A0h], 10h
0x1800fa692  jz      short loc_1800FA6A6
0x1800fa694  or      dword ptr [rbx+38h], 1
0x1800fa698  mov     rax, [rdi+38h]
0x1800fa69c  mov     [rbx+40h], rax
0x1800fa6a0  mov     eax, [rdi+40h]
0x1800fa6a3  mov     [rbx+48h], eax
0x1800fa6a6  test    byte ptr [rdi+0A0h], 4
0x1800fa6ad  jz      short loc_1800FA6C1
0x1800fa6af  or      dword ptr [rbx+38h], 2
0x1800fa6b3  mov     rax, [rdi+18h]
0x1800fa6b7  mov     [rbx+50h], rax
0x1800fa6bb  mov     eax, [rdi+20h]
0x1800fa6be  mov     [rbx+58h], eax
0x1800fa6c1  test    byte ptr [rdi+0A0h], 8
0x1800fa6c8  jz      short loc_1800FA6DC
0x1800fa6ca  or      dword ptr [rbx+38h], 4
0x1800fa6ce  mov     rcx, [rdi+28h]
0x1800fa6d2  mov     [rbx+60h], rcx
0x1800fa6d6  mov     ecx, [rdi+30h]
0x1800fa6d9  mov     [rbx+68h], ecx
0x1800fa6dc  mov     [r12], rbx
0x1800fa6e0  mov     eax, r15d
0x1800fa6e3  mov     rbx, [rsp+58h+arg_8]
0x1800fa6e8  mov     rbp, [rsp+58h+arg_18]
0x1800fa6ed  add     rsp, 30h
0x1800fa6f1  pop     r15
0x1800fa6f3  pop     r14
0x1800fa6f5  pop     r12
0x1800fa6f7  pop     rdi
0x1800fa6f8  pop     rsi
0x1800fa6f9  retn
```
