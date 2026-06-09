# PvCreateListItem

- ea: `0x18005d030`
- end: `0x18005d0da`
- name: `PvCreateListItem`
- size: `170`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, unsigned int)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x18005b600`
- `0x18005c990`
- `0x18005cd68`
- `0x18005d118`

## callees

- `0x1800582c4`
- `0x18005cfd0`
- `0x18005d030`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x18005d066`
- `KERNEL32!HeapAlloc` at `0x18005d066`
- `KERNEL32!HeapFree` at `0x18005d09b`
- `KERNEL32!HeapFree` at `0x18005d09b`

## pseudocode

```c
_QWORD *__fastcall PvCreateListItem(__int64 a1, _QWORD *a2, unsigned int a3)
{
  _QWORD **v3; // rsi
  _QWORD *ListItem; // rbx
  void *v8; // rax
  _QWORD *i; // rcx

  v3 = (_QWORD **)a2;
  ListItem = PvFindListItem((_QWORD *)*a2, *(_QWORD *)(a1 + 584), 0);
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
0x18005d030  push    rbx
0x18005d032  push    rbp
0x18005d033  push    rsi
0x18005d034  push    rdi
0x18005d035  sub     rsp, 28h
0x18005d039  mov     rsi, rdx
0x18005d03c  mov     ebp, r8d
0x18005d03f  mov     rdx, [rcx+248h]
0x18005d046  mov     rdi, rcx
0x18005d049  xor     r8d, r8d
0x18005d04c  mov     rcx, [rsi]
0x18005d04f  call    PvFindListItem
0x18005d054  mov     rbx, rax
0x18005d057  test    rax, rax
0x18005d05a  jnz     short loc_18005D0CD
0x18005d05c  mov     rcx, [rdi+8]; hHeap
0x18005d060  lea     edx, [rax+8]; dwFlags
0x18005d063  mov     r8d, ebp; dwBytes
0x18005d066  call    cs:__imp_HeapAlloc
0x18005d06d  nop     dword ptr [rax+rax+00h]
0x18005d072  mov     rbx, rax
0x18005d075  test    rax, rax
0x18005d078  jnz     short loc_18005D07E
0x18005d07a  xor     eax, eax
0x18005d07c  jmp     short loc_18005D0D0
0x18005d07e  lea     rdx, [rdi+240h]
0x18005d085  mov     rcx, rdi
0x18005d088  call    PstrParseString
0x18005d08d  test    rax, rax
0x18005d090  jnz     short loc_18005D0A9
0x18005d092  mov     rcx, [rdi+8]; hHeap
0x18005d096  mov     r8, rbx; lpMem
0x18005d099  xor     edx, edx; dwFlags
0x18005d09b  call    cs:__imp_HeapFree
0x18005d0a2  nop     dword ptr [rax+rax+00h]
0x18005d0a7  jmp     short loc_18005D07A
0x18005d0a9  mov     [rbx+8], rax
0x18005d0ad  mov     qword ptr [rbx], 0
0x18005d0b4  mov     rcx, [rsi]
0x18005d0b7  test    rcx, rcx
0x18005d0ba  jz      short loc_18005D0CA
0x18005d0bc  mov     rax, [rcx]
0x18005d0bf  mov     rsi, rcx
0x18005d0c2  mov     rcx, rax
0x18005d0c5  test    rax, rax
0x18005d0c8  jnz     short loc_18005D0BC
0x18005d0ca  mov     [rsi], rbx
0x18005d0cd  mov     rax, rbx
0x18005d0d0  add     rsp, 28h
0x18005d0d4  pop     rdi
0x18005d0d5  pop     rsi
0x18005d0d6  pop     rbp
0x18005d0d7  pop     rbx
0x18005d0d8  retn
```
