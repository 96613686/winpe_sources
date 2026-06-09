# __acrt_uninitialize_locks

- ea: `0x140016870`
- end: `0x1400168a7`
- name: `__acrt_uninitialize_locks`
- size: `55`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140016800`

## callees

- `0x140016870`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x14001688f`
- `KERNEL32!DeleteCriticalSection` at `0x14001688f`

## pseudocode

```c
char _acrt_uninitialize_locks()
{
  int v0; // ebx

  v0 = dword_14003D2D8;
  while ( v0 )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)&qword_14003D080[5 * (unsigned int)--v0]);
    --dword_14003D2D8;
  }
  return 1;
}

```

## disassembly

```asm
0x140016870  push    rbx
0x140016872  sub     rsp, 20h
0x140016876  mov     ebx, cs:dword_14003D2D8
0x14001687c  jmp     short loc_14001689B
0x14001687e  lea     rax, qword_14003D080
0x140016885  dec     ebx
0x140016887  lea     rcx, [rbx+rbx*4]
0x14001688b  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x14001688f  call    cs:__imp_DeleteCriticalSection
0x140016895  dec     cs:dword_14003D2D8
0x14001689b  test    ebx, ebx
0x14001689d  jnz     short loc_14001687E
0x14001689f  mov     al, 1
0x1400168a1  add     rsp, 20h
0x1400168a5  pop     rbx
0x1400168a6  retn
```
