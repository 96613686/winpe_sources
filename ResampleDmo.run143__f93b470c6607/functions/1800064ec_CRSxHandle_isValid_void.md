# CRSxHandle::isValid(void)

- ea: `0x1800064ec`
- end: `0x180006502`
- name: `?isValid@CRSxHandle@@QEAAHXZ`
- size: `22`
- prototype: `__int64 __fastcall(CRSxHandle *__hidden this)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x18006eac0`
- `0x18006eb00`
- `0x18006eb70`
- `0x18006eba0`
- `0x18006ebd0`
- `0x18006ecf0`
- `0x18006ed20`
- `0x18006ed60`

## callees

- `0x1800064ec`

## pseudocode

```c
_BOOL8 __fastcall CRSxHandle::isValid(CRSxHandle *this)
{
  _BOOL8 result; // rax

  result = 0;
  if ( *(_DWORD *)this == -863945167 )
    return *((_QWORD *)this + 1) != 0;
  return result;
}

```

## disassembly

```asm
0x1800064ec  xor     eax, eax
0x1800064ee  cmp     dword ptr [rcx], 0CC813E31h
0x1800064f4  jnz     short locret_180006501
0x1800064f6  cmp     [rcx+8], rax
0x1800064fa  jz      short locret_180006501
0x1800064fc  mov     eax, 1
0x180006501  retn
```
