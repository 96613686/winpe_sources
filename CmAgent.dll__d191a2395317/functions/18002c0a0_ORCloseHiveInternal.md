# ORCloseHiveInternal

- ea: `0x18002c0a0`
- end: `0x18002c15e`
- name: `ORCloseHiveInternal`
- size: `190`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18002c068`
- `0x18002c164`

## callees

- `0x180002b28`
- `0x18002c0a0`
- `0x18002d0d0`
- `0x18002eef8`
- `0x180030b90`
- `0x180030de0`
- `0x1800318a8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002c105`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002c105`

## pseudocode

```c
__int64 __fastcall ORCloseHiveInternal(char *Block)
{
  char *v2; // rdi
  char *v3; // rax
  char **v4; // rcx
  char *v5; // rdx
  __int64 v6; // rcx
  void *v7; // rcx

  if ( Block )
  {
    ORFreeSecurityCellList(Block);
    ORFreeTree(*((_QWORD *)Block + 7));
    v2 = (char *)*((_QWORD *)Block + 12);
    while ( v2 != Block + 96 )
    {
      v3 = *(char **)v2;
      if ( *(char **)(*(_QWORD *)v2 + 8LL) != v2 || (v4 = (char **)*((_QWORD *)v2 + 1), *v4 != v2) )
        __fastfail(3u);
      *v4 = v3;
      v5 = v2;
      *((_QWORD *)v3 + 1) = v4;
      v2 = v3;
      ORFreeNode(Block, v5);
    }
    DeleteCriticalSection((LPCRITICAL_SECTION)(Block + 136));
    v6 = *((_QWORD *)Block + 16);
    if ( v6 )
      ORCloseFile(v6);
    ORFreeOrNop(Block, Block + 40);
    v7 = (void *)*((_QWORD *)Block + 2);
    if ( v7 )
      aligned_free(v7);
    aligned_free(Block);
  }
  return 0;
}

```

## disassembly

```asm
0x18002c0a0  mov     [rsp+arg_0], rbx
0x18002c0a5  mov     [rsp+arg_8], rsi
0x18002c0aa  push    rdi
0x18002c0ab  sub     rsp, 20h
0x18002c0af  mov     rbx, rcx
0x18002c0b2  test    rcx, rcx
0x18002c0b5  jz      loc_18002C144
0x18002c0bb  call    ORFreeSecurityCellList
0x18002c0c0  mov     rcx, [rbx+38h]
0x18002c0c4  call    ORFreeTree
0x18002c0c9  lea     rsi, [rbx+60h]
0x18002c0cd  mov     rdi, [rsi]
0x18002c0d0  jmp     short loc_18002C0F9
0x18002c0d2  mov     rax, [rdi]
0x18002c0d5  cmp     [rax+8], rdi
0x18002c0d9  jnz     short loc_18002C157
0x18002c0db  mov     rcx, [rdi+8]
0x18002c0df  cmp     [rcx], rdi
0x18002c0e2  jnz     short loc_18002C157
0x18002c0e4  mov     [rcx], rax
0x18002c0e7  mov     rdx, rdi
0x18002c0ea  mov     [rax+8], rcx
0x18002c0ee  mov     rdi, rax
0x18002c0f1  mov     rcx, rbx
0x18002c0f4  call    ORFreeNode
0x18002c0f9  cmp     rdi, rsi
0x18002c0fc  jnz     short loc_18002C0D2
0x18002c0fe  lea     rcx, [rbx+88h]; lpCriticalSection
0x18002c105  call    cs:__imp_DeleteCriticalSection
0x18002c10c  nop     dword ptr [rax+rax+00h]
0x18002c111  mov     rcx, [rbx+80h]
0x18002c118  test    rcx, rcx
0x18002c11b  jz      short loc_18002C122
0x18002c11d  call    ORCloseFile
0x18002c122  lea     rdx, [rbx+28h]
0x18002c126  mov     rcx, rbx
0x18002c129  call    ORFreeOrNop
0x18002c12e  mov     rcx, [rbx+10h]; Block
0x18002c132  test    rcx, rcx
0x18002c135  jz      short loc_18002C13C
0x18002c137  call    _aligned_free
0x18002c13c  mov     rcx, rbx; Block
0x18002c13f  call    _aligned_free
0x18002c144  mov     rbx, [rsp+28h+arg_0]
0x18002c149  xor     eax, eax
0x18002c14b  mov     rsi, [rsp+28h+arg_8]
0x18002c150  add     rsp, 20h
0x18002c154  pop     rdi
0x18002c155  retn
0x18002c157  mov     ecx, 3
0x18002c15c  int     29h; Win8: RtlFailFast(ecx)
```
