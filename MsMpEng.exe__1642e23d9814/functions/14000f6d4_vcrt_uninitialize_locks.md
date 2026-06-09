# __vcrt_uninitialize_locks

- ea: `0x14000f6d4`
- end: `0x14000f70b`
- name: `__vcrt_uninitialize_locks`
- size: `55`
- prototype: `char()`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x14000c260`
- `0x14000c288`
- `0x14000f68c`

## callees

- `0x14000f6d4`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x14000f6f3`
- `KERNEL32!DeleteCriticalSection` at `0x14000f6f3`

## pseudocode

```c
char _vcrt_uninitialize_locks()
{
  int v0; // ebx

  v0 = dword_14003E230;
  while ( v0 )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)&qword_14003E208[5 * (unsigned int)--v0]);
    --dword_14003E230;
  }
  return 1;
}

```

## disassembly

```asm
0x14000f6d4  push    rbx
0x14000f6d6  sub     rsp, 20h
0x14000f6da  mov     ebx, cs:dword_14003E230
0x14000f6e0  jmp     short loc_14000F6FF
0x14000f6e2  lea     rax, qword_14003E208
0x14000f6e9  dec     ebx
0x14000f6eb  lea     rcx, [rbx+rbx*4]
0x14000f6ef  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x14000f6f3  call    cs:__imp_DeleteCriticalSection
0x14000f6f9  dec     cs:dword_14003E230
0x14000f6ff  test    ebx, ebx
0x14000f701  jnz     short loc_14000F6E2
0x14000f703  mov     al, 1
0x14000f705  add     rsp, 20h
0x14000f709  pop     rbx
0x14000f70a  retn
```
