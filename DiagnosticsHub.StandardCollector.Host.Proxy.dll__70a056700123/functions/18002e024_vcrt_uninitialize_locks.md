# __vcrt_uninitialize_locks

- ea: `0x18002e024`
- end: `0x18002e05b`
- name: `__vcrt_uninitialize_locks`
- size: `55`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180022510`
- `0x18002255c`
- `0x18002dfc0`

## callees

- `0x18002e024`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18002e043`
- `KERNEL32!DeleteCriticalSection` at `0x18002e043`

## pseudocode

```c
char _vcrt_uninitialize_locks()
{
  int v0; // ebx

  v0 = dword_1800790E8;
  while ( v0 )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)&qword_1800790C0[5 * (unsigned int)--v0]);
    --dword_1800790E8;
  }
  return 1;
}

```

## disassembly

```asm
0x18002e024  push    rbx
0x18002e026  sub     rsp, 20h
0x18002e02a  mov     ebx, cs:dword_1800790E8
0x18002e030  jmp     short loc_18002E04F
0x18002e032  lea     rax, qword_1800790C0
0x18002e039  dec     ebx
0x18002e03b  lea     rcx, [rbx+rbx*4]
0x18002e03f  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x18002e043  call    cs:__imp_DeleteCriticalSection
0x18002e049  dec     cs:dword_1800790E8
0x18002e04f  test    ebx, ebx
0x18002e051  jnz     short loc_18002E032
0x18002e053  mov     al, 1
0x18002e055  add     rsp, 20h
0x18002e059  pop     rbx
0x18002e05a  retn
```
