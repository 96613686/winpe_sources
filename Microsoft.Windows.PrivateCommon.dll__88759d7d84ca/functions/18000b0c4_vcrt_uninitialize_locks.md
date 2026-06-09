# __vcrt_uninitialize_locks

- ea: `0x18000b0c4`
- end: `0x18000b0fb`
- name: `__vcrt_uninitialize_locks`
- size: `55`
- prototype: `char()`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180008bc4`
- `0x180008c10`
- `0x18000b07c`

## callees

- `0x18000b0c4`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18000b0e3`
- `KERNEL32!DeleteCriticalSection` at `0x18000b0e3`

## pseudocode

```c
char _vcrt_uninitialize_locks()
{
  int v0; // ebx

  v0 = dword_180016210;
  while ( v0 )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)&qword_1800161E8[5 * (unsigned int)--v0]);
    --dword_180016210;
  }
  return 1;
}

```

## disassembly

```asm
0x18000b0c4  push    rbx
0x18000b0c6  sub     rsp, 20h
0x18000b0ca  mov     ebx, cs:dword_180016210
0x18000b0d0  jmp     short loc_18000B0EF
0x18000b0d2  lea     rax, qword_1800161E8
0x18000b0d9  dec     ebx
0x18000b0db  lea     rcx, [rbx+rbx*4]
0x18000b0df  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x18000b0e3  call    cs:__imp_DeleteCriticalSection
0x18000b0e9  dec     cs:dword_180016210
0x18000b0ef  test    ebx, ebx
0x18000b0f1  jnz     short loc_18000B0D2
0x18000b0f3  mov     al, 1
0x18000b0f5  add     rsp, 20h
0x18000b0f9  pop     rbx
0x18000b0fa  retn
```
