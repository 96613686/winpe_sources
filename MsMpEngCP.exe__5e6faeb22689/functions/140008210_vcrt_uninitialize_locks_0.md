# __vcrt_uninitialize_locks_0

- ea: `0x140008210`
- end: `0x140008247`
- name: `__vcrt_uninitialize_locks_0`
- size: `55`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400081a0`

## callees

- `0x140008210`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x14000822f`
- `KERNEL32!DeleteCriticalSection` at `0x14000822f`

## pseudocode

```c
char _vcrt_uninitialize_locks_0()
{
  int v0; // ebx

  v0 = dword_14001A748;
  while ( v0 )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)&qword_14001A4F0[5 * (unsigned int)--v0]);
    --dword_14001A748;
  }
  return 1;
}

```

## disassembly

```asm
0x140008210  push    rbx
0x140008212  sub     rsp, 20h
0x140008216  mov     ebx, cs:dword_14001A748
0x14000821c  jmp     short loc_14000823B
0x14000821e  lea     rax, qword_14001A4F0
0x140008225  dec     ebx
0x140008227  lea     rcx, [rbx+rbx*4]
0x14000822b  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x14000822f  call    cs:DeleteCriticalSection
0x140008235  dec     cs:dword_14001A748
0x14000823b  test    ebx, ebx
0x14000823d  jnz     short loc_14000821E
0x14000823f  mov     al, 1
0x140008241  add     rsp, 20h
0x140008245  pop     rbx
0x140008246  retn
```
