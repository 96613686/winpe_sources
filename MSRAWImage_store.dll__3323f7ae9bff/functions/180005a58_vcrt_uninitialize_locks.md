# __vcrt_uninitialize_locks

- ea: `0x180005a58`
- end: `0x180005a8f`
- name: `__vcrt_uninitialize_locks`
- size: `55`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180003cb0`
- `0x180003d14`
- `0x180005a08`

## callees

- `0x180005a58`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005a77`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005a77`

## pseudocode

```c
char _vcrt_uninitialize_locks()
{
  int v0; // ebx

  v0 = dword_1801268D8;
  while ( v0 )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)&qword_1801268B0[5 * (unsigned int)--v0]);
    --dword_1801268D8;
  }
  return 1;
}

```

## disassembly

```asm
0x180005a58  push    rbx
0x180005a5a  sub     rsp, 20h
0x180005a5e  mov     ebx, cs:dword_1801268D8
0x180005a64  jmp     short loc_180005A83
0x180005a66  lea     rax, qword_1801268B0
0x180005a6d  dec     ebx
0x180005a6f  lea     rcx, [rbx+rbx*4]
0x180005a73  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x180005a77  call    cs:__imp_DeleteCriticalSection
0x180005a7d  dec     cs:dword_1801268D8
0x180005a83  test    ebx, ebx
0x180005a85  jnz     short loc_180005A66
0x180005a87  mov     al, 1
0x180005a89  add     rsp, 20h
0x180005a8d  pop     rbx
0x180005a8e  retn
```
