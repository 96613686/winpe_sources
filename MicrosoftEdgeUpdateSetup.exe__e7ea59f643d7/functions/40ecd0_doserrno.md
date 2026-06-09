# ___doserrno

- ea: `0x40ecd0`
- end: `0x40ece3`
- name: `___doserrno`
- size: `19`
- prototype: `unsigned int *__cdecl()`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x40ecad`
- `0x41043d`
- `0x4104ce`
- `0x413ce6`
- `0x414580`
- `0x414672`
- `0x417638`

## callees

- `0x40e970`
- `0x40ecd0`

## pseudocode

```c
unsigned int *__cdecl __doserrno()
{
  char *v0; // eax

  v0 = (char *)__acrt_getptd_noexit();
  if ( v0 )
    return (unsigned int *)(v0 + 20);
  else
    return (unsigned int *)dword_426058;
}

```

## disassembly

```asm
0x40ecd0  call    ___acrt_getptd_noexit
0x40ecd5  test    eax, eax
0x40ecd7  jnz     short loc_40ECDF
0x40ecd9  mov     eax, offset dword_426058
0x40ecde  retn
0x40ecdf  add     eax, 14h
0x40ece2  retn
```
