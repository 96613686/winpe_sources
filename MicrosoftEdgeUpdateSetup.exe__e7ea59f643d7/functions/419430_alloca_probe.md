# __alloca_probe

- ea: `0x419430`
- end: `0x41945b`
- name: `__alloca_probe`
- size: `43`
- prototype: `void *__usercall@<eax>(unsigned int@<eax>, int@<ecx>)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x41428a`
- `0x414365`
- `0x41444e`
- `0x4192e0`
- `0x4192f6`

## callees

- `0x419430`

## pseudocode

```c
void *__usercall _alloca_probe@<eax>(unsigned int a1@<eax>, int a2@<ecx>)
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
0x419430  push    ecx
0x419431  lea     ecx, [esp+4]
0x419435  sub     ecx, eax
0x419437  sbb     eax, eax
0x419439  not     eax
0x41943b  and     ecx, eax
0x41943d  mov     eax, esp
0x41943f  and     eax, 0FFFFF000h
0x419444  cmp     ecx, eax
0x419446  jb      short loc_419452
0x419448  mov     eax, ecx
0x41944a  pop     ecx
0x41944b  xchg    eax, esp
0x41944c  mov     eax, [eax]
0x41944e  mov     [esp+0], eax
0x419451  retn
0x419452  sub     eax, 1000h
0x419457  test    [eax], eax
0x419459  jmp     short loc_419444
```
