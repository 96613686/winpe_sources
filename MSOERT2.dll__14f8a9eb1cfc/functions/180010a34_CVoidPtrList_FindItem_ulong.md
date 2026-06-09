# CVoidPtrList::FindItem(ulong)

- ea: `0x180010a34`
- end: `0x180010a48`
- name: `?FindItem@CVoidPtrList@@AEAAPEAUCNode@@K@Z`
- size: `20`
- prototype: `struct CNode *__fastcall(CVoidPtrList *__hidden this, unsigned int)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180010a60`
- `0x180010be0`
- `0x180010d00`

## callees

- `0x180010a34`

## pseudocode

```c
struct CNode *__fastcall CVoidPtrList::FindItem(CVoidPtrList *this, int a2)
{
  struct CNode *result; // rax

  for ( result = (struct CNode *)*((_QWORD *)this + 1);
        result && a2 != *((_DWORD *)result + 6);
        result = *(struct CNode **)result )
  {
    ;
  }
  return result;
}

```

## disassembly

```asm
0x180010a34  mov     rax, [rcx+8]
0x180010a38  jmp     short loc_180010A42
0x180010a3a  cmp     edx, [rax+18h]
0x180010a3d  jz      short locret_180010A47
0x180010a3f  mov     rax, [rax]
0x180010a42  test    rax, rax
0x180010a45  jnz     short loc_180010A3A
0x180010a47  retn
```
