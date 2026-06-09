# __doserrno

- ea: `0x18000bf9c`
- end: `0x18000bfbc`
- name: `__doserrno`
- size: `32`
- prototype: `unsigned int *__cdecl()`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x180016f98`
- `0x180017054`
- `0x180017ed8`
- `0x180018874`
- `0x180018960`
- `0x18001a3fc`

## callees

- `0x18000bf9c`
- `0x180010420`

## pseudocode

```c
unsigned int *__cdecl _doserrno()
{
  __int64 v0; // rax

  v0 = _acrt_getptd_noexit();
  if ( v0 )
    return (unsigned int *)(v0 + 36);
  else
    return (unsigned int *)&dword_18003D0C4;
}

```

## disassembly

```asm
0x18000bf9c  sub     rsp, 28h
0x18000bfa0  call    __acrt_getptd_noexit
0x18000bfa5  test    rax, rax
0x18000bfa8  jnz     short loc_18000BFB3
0x18000bfaa  lea     rax, dword_18003D0C4
0x18000bfb1  jmp     short loc_18000BFB7
0x18000bfb3  add     rax, 24h ; '$'
0x18000bfb7  add     rsp, 28h
0x18000bfbb  retn
```
