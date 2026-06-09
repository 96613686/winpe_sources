# __vcrt_uninitialize_locks

- ea: `0x14000e09c`
- end: `0x14000e0d3`
- name: `__vcrt_uninitialize_locks`
- size: `55`
- prototype: `char()`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x14000bbe8`
- `0x14000bc18`
- `0x14000e04c`

## callees

- `0x14000e09c`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x14000e0bb`
- `KERNEL32!DeleteCriticalSection` at `0x14000e0bb`

## pseudocode

```c
char _vcrt_uninitialize_locks()
{
  int v0; // ebx

  v0 = dword_1400158A8;
  while ( v0 )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)&qword_140015880[5 * (unsigned int)--v0]);
    --dword_1400158A8;
  }
  return 1;
}

```

## disassembly

```asm
0x14000e09c  push    rbx
0x14000e09e  sub     rsp, 20h
0x14000e0a2  mov     ebx, cs:dword_1400158A8
0x14000e0a8  jmp     short loc_14000E0C7
0x14000e0aa  lea     rax, qword_140015880
0x14000e0b1  dec     ebx
0x14000e0b3  lea     rcx, [rbx+rbx*4]
0x14000e0b7  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x14000e0bb  call    cs:__imp_DeleteCriticalSection
0x14000e0c1  dec     cs:dword_1400158A8
0x14000e0c7  test    ebx, ebx
0x14000e0c9  jnz     short loc_14000E0AA
0x14000e0cb  mov     al, 1
0x14000e0cd  add     rsp, 20h
0x14000e0d1  pop     rbx
0x14000e0d2  retn
```
