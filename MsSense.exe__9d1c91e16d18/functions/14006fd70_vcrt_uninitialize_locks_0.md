# __vcrt_uninitialize_locks_0

- ea: `0x14006fd70`
- end: `0x14006fda7`
- name: `__vcrt_uninitialize_locks_0`
- size: `55`
- prototype: `char()`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14006fd00`

## callees

- `0x14006fd70`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x14006fd8f`
- `KERNEL32!DeleteCriticalSection` at `0x14006fd8f`

## pseudocode

```c
char _vcrt_uninitialize_locks_0()
{
  int v0; // ebx

  v0 = dword_1400C4648;
  while ( v0 )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)&qword_1400C43F0[5 * (unsigned int)--v0]);
    --dword_1400C4648;
  }
  return 1;
}

```

## disassembly

```asm
0x14006fd70  push    rbx
0x14006fd72  sub     rsp, 20h
0x14006fd76  mov     ebx, cs:dword_1400C4648
0x14006fd7c  jmp     short loc_14006FD9B
0x14006fd7e  lea     rax, qword_1400C43F0
0x14006fd85  dec     ebx
0x14006fd87  lea     rcx, [rbx+rbx*4]
0x14006fd8b  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x14006fd8f  call    cs:__imp_DeleteCriticalSection
0x14006fd95  dec     cs:dword_1400C4648
0x14006fd9b  test    ebx, ebx
0x14006fd9d  jnz     short loc_14006FD7E
0x14006fd9f  mov     al, 1
0x14006fda1  add     rsp, 20h
0x14006fda5  pop     rbx
0x14006fda6  retn
```
