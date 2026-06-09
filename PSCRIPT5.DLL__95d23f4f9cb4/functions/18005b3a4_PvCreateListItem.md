# PvCreateListItem

- ea: `0x18005b3a4`
- end: `0x18005b441`
- name: `PvCreateListItem`
- size: `157`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x1800599a0`
- `0x18005ad20`
- `0x18005b0e4`
- `0x18005b47c`

## callees

- `0x180056744`
- `0x18005b34c`
- `0x18005b3a4`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x18005b3da`
- `KERNEL32!HeapAlloc` at `0x18005b3da`
- `KERNEL32!HeapFree` at `0x18005b409`
- `KERNEL32!HeapFree` at `0x18005b409`

## pseudocode

```c
_QWORD *__fastcall PvCreateListItem(__int64 a1, _QWORD *a2, unsigned int a3)
{
  _QWORD **v3; // rsi
  _QWORD *ListItem; // rbx
  __int64 v8; // rax
  _QWORD *i; // rcx

  v3 = (_QWORD **)a2;
  ListItem = (_QWORD *)PvFindListItem(*a2, *(_QWORD *)(a1 + 584), 0);
  if ( !ListItem )
  {
    ListItem = HeapAlloc(*(HANDLE *)(a1 + 8), 8u, a3);
    if ( !ListItem )
      return 0;
    v8 = PstrParseString(a1, a1 + 576);
    if ( !v8 )
    {
      HeapFree(*(HANDLE *)(a1 + 8), 0, ListItem);
      return 0;
    }
    ListItem[1] = v8;
    *ListItem = 0;
    for ( i = *v3; i; i = (_QWORD *)*i )
      v3 = (_QWORD **)i;
    *v3 = ListItem;
  }
  return ListItem;
}

```

## disassembly

```asm
0x18005b3a4  push    rbx
0x18005b3a6  push    rbp
0x18005b3a7  push    rsi
0x18005b3a8  push    rdi
0x18005b3a9  sub     rsp, 28h
0x18005b3ad  mov     rsi, rdx
0x18005b3b0  mov     ebp, r8d
0x18005b3b3  mov     rdx, [rcx+248h]
0x18005b3ba  mov     rdi, rcx
0x18005b3bd  xor     r8d, r8d
0x18005b3c0  mov     rcx, [rsi]
0x18005b3c3  call    PvFindListItem
0x18005b3c8  mov     rbx, rax
0x18005b3cb  test    rax, rax
0x18005b3ce  jnz     short loc_18005B435
0x18005b3d0  mov     rcx, [rdi+8]; hHeap
0x18005b3d4  lea     edx, [rax+8]; dwFlags
0x18005b3d7  mov     r8d, ebp; dwBytes
0x18005b3da  call    cs:__imp_HeapAlloc
0x18005b3e0  mov     rbx, rax
0x18005b3e3  test    rax, rax
0x18005b3e6  jnz     short loc_18005B3EC
0x18005b3e8  xor     eax, eax
0x18005b3ea  jmp     short loc_18005B438
0x18005b3ec  lea     rdx, [rdi+240h]
0x18005b3f3  mov     rcx, rdi
0x18005b3f6  call    PstrParseString
0x18005b3fb  test    rax, rax
0x18005b3fe  jnz     short loc_18005B411
0x18005b400  mov     rcx, [rdi+8]; hHeap
0x18005b404  mov     r8, rbx; lpMem
0x18005b407  xor     edx, edx; dwFlags
0x18005b409  call    cs:__imp_HeapFree
0x18005b40f  jmp     short loc_18005B3E8
0x18005b411  mov     [rbx+8], rax
0x18005b415  mov     qword ptr [rbx], 0
0x18005b41c  mov     rcx, [rsi]
0x18005b41f  test    rcx, rcx
0x18005b422  jz      short loc_18005B432
0x18005b424  mov     rax, [rcx]
0x18005b427  mov     rsi, rcx
0x18005b42a  mov     rcx, rax
0x18005b42d  test    rax, rax
0x18005b430  jnz     short loc_18005B424
0x18005b432  mov     [rsi], rbx
0x18005b435  mov     rax, rbx
0x18005b438  add     rsp, 28h
0x18005b43c  pop     rdi
0x18005b43d  pop     rsi
0x18005b43e  pop     rbp
0x18005b43f  pop     rbx
0x18005b440  retn
```
