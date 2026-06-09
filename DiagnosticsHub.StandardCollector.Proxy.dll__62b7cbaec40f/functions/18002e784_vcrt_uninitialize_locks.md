# __vcrt_uninitialize_locks

- ea: `0x18002e784`
- end: `0x18002e7bb`
- name: `__vcrt_uninitialize_locks`
- size: `55`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180022c70`
- `0x180022cbc`
- `0x18002e720`

## callees

- `0x18002e784`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18002e7a3`
- `KERNEL32!DeleteCriticalSection` at `0x18002e7a3`

## pseudocode

```c
char _vcrt_uninitialize_locks()
{
  int v0; // ebx

  v0 = dword_18007CB98;
  while ( v0 )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)&qword_18007CB70[5 * (unsigned int)--v0]);
    --dword_18007CB98;
  }
  return 1;
}

```

## disassembly

```asm
0x18002e784  push    rbx
0x18002e786  sub     rsp, 20h
0x18002e78a  mov     ebx, cs:dword_18007CB98
0x18002e790  jmp     short loc_18002E7AF
0x18002e792  lea     rax, qword_18007CB70
0x18002e799  dec     ebx
0x18002e79b  lea     rcx, [rbx+rbx*4]
0x18002e79f  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x18002e7a3  call    cs:__imp_DeleteCriticalSection
0x18002e7a9  dec     cs:dword_18007CB98
0x18002e7af  test    ebx, ebx
0x18002e7b1  jnz     short loc_18002E792
0x18002e7b3  mov     al, 1
0x18002e7b5  add     rsp, 20h
0x18002e7b9  pop     rbx
0x18002e7ba  retn
```
