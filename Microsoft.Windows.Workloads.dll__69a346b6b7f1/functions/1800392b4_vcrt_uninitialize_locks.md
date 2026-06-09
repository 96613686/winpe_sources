# __vcrt_uninitialize_locks

- ea: `0x1800392b4`
- end: `0x1800392eb`
- name: `__vcrt_uninitialize_locks`
- size: `55`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180037020`
- `0x18003706c`
- `0x18003926c`

## callees

- `0x1800392b4`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1800392d3`
- `KERNEL32!DeleteCriticalSection` at `0x1800392d3`

## pseudocode

```c
char _vcrt_uninitialize_locks()
{
  int v0; // ebx

  v0 = dword_180059C10;
  while ( v0 )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)&qword_180059BE8[5 * (unsigned int)--v0]);
    --dword_180059C10;
  }
  return 1;
}

```

## disassembly

```asm
0x1800392b4  push    rbx
0x1800392b6  sub     rsp, 20h
0x1800392ba  mov     ebx, cs:dword_180059C10
0x1800392c0  jmp     short loc_1800392DF
0x1800392c2  lea     rax, qword_180059BE8
0x1800392c9  dec     ebx
0x1800392cb  lea     rcx, [rbx+rbx*4]
0x1800392cf  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x1800392d3  call    cs:__imp_DeleteCriticalSection
0x1800392d9  dec     cs:dword_180059C10
0x1800392df  test    ebx, ebx
0x1800392e1  jnz     short loc_1800392C2
0x1800392e3  mov     al, 1
0x1800392e5  add     rsp, 20h
0x1800392e9  pop     rbx
0x1800392ea  retn
```
