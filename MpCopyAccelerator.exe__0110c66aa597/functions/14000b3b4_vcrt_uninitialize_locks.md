# __vcrt_uninitialize_locks

- ea: `0x14000b3b4`
- end: `0x14000b3eb`
- name: `__vcrt_uninitialize_locks`
- size: `55`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140007f3c`
- `0x140007f64`
- `0x14000b36c`

## callees

- `0x14000b3b4`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x14000b3d3`
- `KERNEL32!DeleteCriticalSection` at `0x14000b3d3`

## pseudocode

```c
char _vcrt_uninitialize_locks()
{
  int v0; // ebx

  v0 = dword_14003C820;
  while ( v0 )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)&qword_14003C7F8[5 * (unsigned int)--v0]);
    --dword_14003C820;
  }
  return 1;
}

```

## disassembly

```asm
0x14000b3b4  push    rbx
0x14000b3b6  sub     rsp, 20h
0x14000b3ba  mov     ebx, cs:dword_14003C820
0x14000b3c0  jmp     short loc_14000B3DF
0x14000b3c2  lea     rax, qword_14003C7F8
0x14000b3c9  dec     ebx
0x14000b3cb  lea     rcx, [rbx+rbx*4]
0x14000b3cf  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x14000b3d3  call    cs:__imp_DeleteCriticalSection
0x14000b3d9  dec     cs:dword_14003C820
0x14000b3df  test    ebx, ebx
0x14000b3e1  jnz     short loc_14000B3C2
0x14000b3e3  mov     al, 1
0x14000b3e5  add     rsp, 20h
0x14000b3e9  pop     rbx
0x14000b3ea  retn
```
