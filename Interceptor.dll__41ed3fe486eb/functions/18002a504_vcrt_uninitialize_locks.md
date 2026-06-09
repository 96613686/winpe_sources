# __vcrt_uninitialize_locks

- ea: `0x18002a504`
- end: `0x18002a53b`
- name: `__vcrt_uninitialize_locks`
- size: `55`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180028350`
- `0x18002839c`
- `0x18002a4bc`

## callees

- `0x18002a504`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18002a523`
- `KERNEL32!DeleteCriticalSection` at `0x18002a523`

## pseudocode

```c
char _vcrt_uninitialize_locks()
{
  int v0; // ebx

  v0 = dword_180065500;
  while ( v0 )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)&qword_1800654D8[5 * (unsigned int)--v0]);
    --dword_180065500;
  }
  return 1;
}

```

## disassembly

```asm
0x18002a504  push    rbx
0x18002a506  sub     rsp, 20h
0x18002a50a  mov     ebx, cs:dword_180065500
0x18002a510  jmp     short loc_18002A52F
0x18002a512  lea     rax, qword_1800654D8
0x18002a519  dec     ebx
0x18002a51b  lea     rcx, [rbx+rbx*4]
0x18002a51f  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x18002a523  call    cs:__imp_DeleteCriticalSection
0x18002a529  dec     cs:dword_180065500
0x18002a52f  test    ebx, ebx
0x18002a531  jnz     short loc_18002A512
0x18002a533  mov     al, 1
0x18002a535  add     rsp, 20h
0x18002a539  pop     rbx
0x18002a53a  retn
```
