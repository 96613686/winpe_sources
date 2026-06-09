# __vcrt_uninitialize_locks_0

- ea: `0x14001b520`
- end: `0x14001b557`
- name: `__vcrt_uninitialize_locks_0`
- size: `55`
- prototype: `char()`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14001b4b0`

## callees

- `0x14001b520`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x14001b53f`
- `KERNEL32!DeleteCriticalSection` at `0x14001b53f`

## pseudocode

```c
char _vcrt_uninitialize_locks_0()
{
  int v0; // ebx

  v0 = dword_14003EC68;
  while ( v0 )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)&qword_14003EA10[5 * (unsigned int)--v0]);
    --dword_14003EC68;
  }
  return 1;
}

```

## disassembly

```asm
0x14001b520  push    rbx
0x14001b522  sub     rsp, 20h
0x14001b526  mov     ebx, cs:dword_14003EC68
0x14001b52c  jmp     short loc_14001B54B
0x14001b52e  lea     rax, qword_14003EA10
0x14001b535  dec     ebx
0x14001b537  lea     rcx, [rbx+rbx*4]
0x14001b53b  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x14001b53f  call    cs:__imp_DeleteCriticalSection
0x14001b545  dec     cs:dword_14003EC68
0x14001b54b  test    ebx, ebx
0x14001b54d  jnz     short loc_14001B52E
0x14001b54f  mov     al, 1
0x14001b551  add     rsp, 20h
0x14001b555  pop     rbx
0x14001b556  retn
```
