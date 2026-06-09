# __alloca_probe

- ea: `0x416740`
- end: `0x41676b`
- name: `__alloca_probe`
- size: `43`
- prototype: `void *__usercall@<eax>(unsigned int@<eax>, int@<ecx>)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x413c2a`
- `0x413d05`
- `0x413dee`
- `0x416710`
- `0x416726`

## callees

- `0x416740`

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
0x416740  push    ecx
0x416741  lea     ecx, [esp+4]
0x416745  sub     ecx, eax
0x416747  sbb     eax, eax
0x416749  not     eax
0x41674b  and     ecx, eax
0x41674d  mov     eax, esp
0x41674f  and     eax, 0FFFFF000h
0x416754  cmp     ecx, eax
0x416756  jb      short loc_416762
0x416758  mov     eax, ecx
0x41675a  pop     ecx
0x41675b  xchg    eax, esp
0x41675c  mov     eax, [eax]
0x41675e  mov     [esp+0], eax
0x416761  retn
0x416762  sub     eax, 1000h
0x416767  test    [eax], eax
0x416769  jmp     short loc_416754
```
