# __chkstk

- ea: `0x40eb40`
- end: `0x40eb6b`
- name: `__chkstk`
- size: `43`
- prototype: `void *__usercall@<eax>(unsigned int@<eax>, int@<ecx>)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x40bc9a`
- `0x40c09d`
- `0x40c146`

## callees

- `0x40eb40`

## pseudocode

```c
void *__usercall _chkstk@<eax>(unsigned int a1@<eax>, int a2@<ecx>)
{
  unsigned int v2; // ecx
  unsigned int i; // eax
  int v5; // [esp-4h] [ebp-4h] BYREF
  _UNKNOWN *retaddr; // [esp+0h] [ebp+0h] BYREF

  v5 = a2;
  v2 = ~((unsigned int)((unsigned int)&retaddr - (unsigned __int64)a1) >> 32) & ((unsigned int)&retaddr - a1);
  for ( i = (unsigned int)&v5 & 0xFFFFF000; v2 < i; i -= 4096 )
    ;
  return retaddr;
}

```

## disassembly

```asm
0x40eb40  push    ecx
0x40eb41  lea     ecx, [esp+4]
0x40eb45  sub     ecx, eax
0x40eb47  sbb     eax, eax
0x40eb49  not     eax
0x40eb4b  and     ecx, eax
0x40eb4d  mov     eax, esp
0x40eb4f  and     eax, 0FFFFF000h
0x40eb54  cmp     ecx, eax
0x40eb56  jb      short loc_40EB62
0x40eb58  mov     eax, ecx
0x40eb5a  pop     ecx
0x40eb5b  xchg    eax, esp
0x40eb5c  mov     eax, [eax]
0x40eb5e  mov     [esp+0], eax
0x40eb61  retn
0x40eb62  sub     eax, 1000h
0x40eb67  test    [eax], eax
0x40eb69  jmp     short loc_40EB54
```
