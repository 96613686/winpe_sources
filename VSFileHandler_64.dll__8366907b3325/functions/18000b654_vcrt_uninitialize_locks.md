# __vcrt_uninitialize_locks

- ea: `0x18000b654`
- end: `0x18000b68b`
- name: `__vcrt_uninitialize_locks`
- size: `55`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180009284`
- `0x1800092d0`
- `0x18000b60c`

## callees

- `0x18000b654`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18000b673`
- `KERNEL32!DeleteCriticalSection` at `0x18000b673`

## pseudocode

```c
char _vcrt_uninitialize_locks()
{
  int v0; // ebx

  v0 = dword_18003E250;
  while ( v0 )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)&unk_18003E228 + (unsigned int)--v0);
    --dword_18003E250;
  }
  return 1;
}

```

## disassembly

```asm
0x18000b654  push    rbx
0x18000b656  sub     rsp, 20h
0x18000b65a  mov     ebx, cs:dword_18003E250
0x18000b660  jmp     short loc_18000B67F
0x18000b662  lea     rax, unk_18003E228
0x18000b669  dec     ebx
0x18000b66b  lea     rcx, [rbx+rbx*4]
0x18000b66f  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x18000b673  call    cs:__imp_DeleteCriticalSection
0x18000b679  dec     cs:dword_18003E250
0x18000b67f  test    ebx, ebx
0x18000b681  jnz     short loc_18000B662
0x18000b683  mov     al, 1
0x18000b685  add     rsp, 20h
0x18000b689  pop     rbx
0x18000b68a  retn
```
