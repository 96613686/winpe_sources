# ___doserrno

- ea: `0x40ff96`
- end: `0x40ffa9`
- name: `___doserrno`
- size: `19`
- prototype: `unsigned int *__cdecl()`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x40ff73`
- `0x411108`
- `0x411199`
- `0x413686`
- `0x413f20`
- `0x414012`
- `0x414d28`

## callees

- `0x40fb00`
- `0x40ff96`

## pseudocode

```c
unsigned int *__cdecl __doserrno()
{
  char *v0; // eax

  v0 = (char *)__acrt_getptd_noexit();
  if ( v0 )
    return (unsigned int *)(v0 + 20);
  else
    return (unsigned int *)&dword_417124;
}

```

## disassembly

```asm
0x40ff96  call    ___acrt_getptd_noexit
0x40ff9b  test    eax, eax
0x40ff9d  jnz     short loc_40FFA5
0x40ff9f  mov     eax, offset dword_417124
0x40ffa4  retn
0x40ffa5  add     eax, 14h
0x40ffa8  retn
```
