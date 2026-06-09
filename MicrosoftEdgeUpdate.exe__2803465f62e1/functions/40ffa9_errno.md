# __errno

- ea: `0x40ffa9`
- end: `0x40ffbc`
- name: `__errno`
- size: `19`
- prototype: `int *__cdecl()`
- caller_count: `39`
- callee_count: `2`
- tags: ``

## callers

- `0x40e4a7`
- `0x40eda9`
- `0x40ee87`
- `0x40eef0`
- `0x40f400`
- `0x40f4c0`
- `0x40fda8`
- `0x40fdf6`
- `0x40fe5a`
- `0x40ff73`
- `0x40ffbd`
- `0x41001a`
- `0x410078`
- `0x4108e0`
- `0x410cee`
- `0x411024`
- `0x411108`
- `0x411199`
- `0x411fa6`
- `0x4121f6`
- `0x412e3d`
- `0x412f99`
- `0x412fe0`
- `0x4135ea`
- `0x41361d`
- `0x413686`
- `0x413728`
- `0x413f20`
- `0x414012`
- `0x4142d7`
- `0x4144d9`
- `0x4145d4`
- `0x4145f3`
- `0x4146bc`
- `0x414733`
- `0x414c9c`
- `0x414d28`
- `0x415783`
- `0x4162e3`

## callees

- `0x40fb00`
- `0x40ffa9`

## pseudocode

```c
int *__cdecl _errno()
{
  char *v0; // eax

  v0 = (char *)__acrt_getptd_noexit();
  if ( v0 )
    return (int *)(v0 + 16);
  else
    return &dword_417120;
}

```

## disassembly

```asm
0x40ffa9  call    ___acrt_getptd_noexit
0x40ffae  test    eax, eax
0x40ffb0  jnz     short loc_40FFB8
0x40ffb2  mov     eax, offset dword_417120
0x40ffb7  retn
0x40ffb8  add     eax, 10h
0x40ffbb  retn
```
