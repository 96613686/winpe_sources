# __vcrt_uninitialize_locks

- ea: `0x140060ce0`
- end: `0x140060d17`
- name: `__vcrt_uninitialize_locks`
- size: `55`
- prototype: `char()`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1400549c0`
- `0x1400549e8`
- `0x140060c7c`

## callees

- `0x140060ce0`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x140060cff`
- `KERNEL32!DeleteCriticalSection` at `0x140060cff`

## pseudocode

```c
char _vcrt_uninitialize_locks()
{
  int v0; // ebx

  v0 = dword_1400C4360;
  while ( v0 )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)&qword_1400C4338[5 * (unsigned int)--v0]);
    --dword_1400C4360;
  }
  return 1;
}

```

## disassembly

```asm
0x140060ce0  push    rbx
0x140060ce2  sub     rsp, 20h
0x140060ce6  mov     ebx, cs:dword_1400C4360
0x140060cec  jmp     short loc_140060D0B
0x140060cee  lea     rax, qword_1400C4338
0x140060cf5  dec     ebx
0x140060cf7  lea     rcx, [rbx+rbx*4]
0x140060cfb  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x140060cff  call    cs:__imp_DeleteCriticalSection
0x140060d05  dec     cs:dword_1400C4360
0x140060d0b  test    ebx, ebx
0x140060d0d  jnz     short loc_140060CEE
0x140060d0f  mov     al, 1
0x140060d11  add     rsp, 20h
0x140060d15  pop     rbx
0x140060d16  retn
```
