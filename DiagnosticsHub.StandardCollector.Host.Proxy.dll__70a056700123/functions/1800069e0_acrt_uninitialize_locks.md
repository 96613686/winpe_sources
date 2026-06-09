# __acrt_uninitialize_locks

- ea: `0x1800069e0`
- end: `0x180006a17`
- name: `__acrt_uninitialize_locks`
- size: `55`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180006970`

## callees

- `0x1800069e0`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1800069ff`
- `KERNEL32!DeleteCriticalSection` at `0x1800069ff`

## pseudocode

```c
char _acrt_uninitialize_locks()
{
  int v0; // ebx

  v0 = dword_180078408;
  while ( v0 )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)&qword_1800781B0[5 * (unsigned int)--v0]);
    --dword_180078408;
  }
  return 1;
}

```

## disassembly

```asm
0x1800069e0  push    rbx
0x1800069e2  sub     rsp, 20h
0x1800069e6  mov     ebx, cs:dword_180078408
0x1800069ec  jmp     short loc_180006A0B
0x1800069ee  lea     rax, qword_1800781B0
0x1800069f5  dec     ebx
0x1800069f7  lea     rcx, [rbx+rbx*4]
0x1800069fb  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x1800069ff  call    cs:__imp_DeleteCriticalSection
0x180006a05  dec     cs:dword_180078408
0x180006a0b  test    ebx, ebx
0x180006a0d  jnz     short loc_1800069EE
0x180006a0f  mov     al, 1
0x180006a11  add     rsp, 20h
0x180006a15  pop     rbx
0x180006a16  retn
```
