# __vcrt_uninitialize_locks

- ea: `0x18001c088`
- end: `0x18001c0bf`
- name: `__vcrt_uninitialize_locks`
- size: `55`
- prototype: `char()`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180019cc0`
- `0x180019d0c`
- `0x18001c040`

## callees

- `0x18001c088`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18001c0a7`
- `KERNEL32!DeleteCriticalSection` at `0x18001c0a7`

## pseudocode

```c
char _vcrt_uninitialize_locks()
{
  int v0; // ebx

  v0 = dword_18002E530;
  while ( v0 )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)&qword_18002E508[5 * (unsigned int)--v0]);
    --dword_18002E530;
  }
  return 1;
}

```

## disassembly

```asm
0x18001c088  push    rbx
0x18001c08a  sub     rsp, 20h
0x18001c08e  mov     ebx, cs:dword_18002E530
0x18001c094  jmp     short loc_18001C0B3
0x18001c096  lea     rax, qword_18002E508
0x18001c09d  dec     ebx
0x18001c09f  lea     rcx, [rbx+rbx*4]
0x18001c0a3  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x18001c0a7  call    cs:__imp_DeleteCriticalSection
0x18001c0ad  dec     cs:dword_18002E530
0x18001c0b3  test    ebx, ebx
0x18001c0b5  jnz     short loc_18001C096
0x18001c0b7  mov     al, 1
0x18001c0b9  add     rsp, 20h
0x18001c0bd  pop     rbx
0x18001c0be  retn
```
