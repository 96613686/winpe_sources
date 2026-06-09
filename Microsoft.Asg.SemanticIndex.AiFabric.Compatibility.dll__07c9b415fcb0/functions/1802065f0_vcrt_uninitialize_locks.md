# __vcrt_uninitialize_locks

- ea: `0x1802065f0`
- end: `0x180206627`
- name: `__vcrt_uninitialize_locks`
- size: `55`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1801fa320`
- `0x1801fa36c`
- `0x18020658c`

## callees

- `0x1802065f0`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18020660f`
- `KERNEL32!DeleteCriticalSection` at `0x18020660f`

## pseudocode

```c
char _vcrt_uninitialize_locks()
{
  int v0; // ebx

  v0 = dword_1803E1B30;
  while ( v0 )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)&qword_1803E1B08[5 * (unsigned int)--v0]);
    --dword_1803E1B30;
  }
  return 1;
}

```

## disassembly

```asm
0x1802065f0  push    rbx
0x1802065f2  sub     rsp, 20h
0x1802065f6  mov     ebx, cs:dword_1803E1B30
0x1802065fc  jmp     short loc_18020661B
0x1802065fe  lea     rax, qword_1803E1B08
0x180206605  dec     ebx
0x180206607  lea     rcx, [rbx+rbx*4]
0x18020660b  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x18020660f  call    cs:__imp_DeleteCriticalSection
0x180206615  dec     cs:dword_1803E1B30
0x18020661b  test    ebx, ebx
0x18020661d  jnz     short loc_1802065FE
0x18020661f  mov     al, 1
0x180206621  add     rsp, 20h
0x180206625  pop     rbx
0x180206626  retn
```
