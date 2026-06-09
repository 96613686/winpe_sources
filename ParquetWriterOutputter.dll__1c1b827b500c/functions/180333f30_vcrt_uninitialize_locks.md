# __vcrt_uninitialize_locks

- ea: `0x180333f30`
- end: `0x180333f67`
- name: `__vcrt_uninitialize_locks`
- size: `55`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18032c06c`
- `0x18032c0c8`
- `0x180333ecc`

## callees

- `0x180333f30`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180333f4f`
- `KERNEL32!DeleteCriticalSection` at `0x180333f4f`

## pseudocode

```c
char _vcrt_uninitialize_locks()
{
  int v0; // ebx

  v0 = dword_1804C71E0;
  while ( v0 )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)&qword_1804C71B8[5 * (unsigned int)--v0]);
    --dword_1804C71E0;
  }
  return 1;
}

```

## disassembly

```asm
0x180333f30  push    rbx
0x180333f32  sub     rsp, 20h
0x180333f36  mov     ebx, cs:dword_1804C71E0
0x180333f3c  jmp     short loc_180333F5B
0x180333f3e  lea     rax, qword_1804C71B8
0x180333f45  dec     ebx
0x180333f47  lea     rcx, [rbx+rbx*4]
0x180333f4b  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x180333f4f  call    cs:__imp_DeleteCriticalSection
0x180333f55  dec     cs:dword_1804C71E0
0x180333f5b  test    ebx, ebx
0x180333f5d  jnz     short loc_180333F3E
0x180333f5f  mov     al, 1
0x180333f61  add     rsp, 20h
0x180333f65  pop     rbx
0x180333f66  retn
```
