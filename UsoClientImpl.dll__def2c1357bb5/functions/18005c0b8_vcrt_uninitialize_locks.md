# __vcrt_uninitialize_locks

- ea: `0x18005c0b8`
- end: `0x18005c0ef`
- name: `__vcrt_uninitialize_locks`
- size: `55`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180058a20`
- `0x180058a84`
- `0x18005c068`

## callees

- `0x18005c0b8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18005c0d7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18005c0d7`

## pseudocode

```c
char _vcrt_uninitialize_locks()
{
  int v0; // ebx

  v0 = dword_18009F538;
  while ( v0 )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)&qword_18009F510[5 * (unsigned int)--v0]);
    --dword_18009F538;
  }
  return 1;
}

```

## disassembly

```asm
0x18005c0b8  push    rbx
0x18005c0ba  sub     rsp, 20h
0x18005c0be  mov     ebx, cs:dword_18009F538
0x18005c0c4  jmp     short loc_18005C0E3
0x18005c0c6  lea     rax, qword_18009F510
0x18005c0cd  dec     ebx
0x18005c0cf  lea     rcx, [rbx+rbx*4]
0x18005c0d3  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x18005c0d7  call    cs:__imp_DeleteCriticalSection
0x18005c0dd  dec     cs:dword_18009F538
0x18005c0e3  test    ebx, ebx
0x18005c0e5  jnz     short loc_18005C0C6
0x18005c0e7  mov     al, 1
0x18005c0e9  add     rsp, 20h
0x18005c0ed  pop     rbx
0x18005c0ee  retn
```
