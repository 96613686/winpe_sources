# __vcrt_uninitialize_locks

- ea: `0x180050f24`
- end: `0x180050f5b`
- name: `__vcrt_uninitialize_locks`
- size: `55`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18004ec2c`
- `0x18004ec78`
- `0x180050edc`

## callees

- `0x180050f24`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180050f43`
- `KERNEL32!DeleteCriticalSection` at `0x180050f43`

## pseudocode

```c
char _vcrt_uninitialize_locks()
{
  int v0; // ebx

  v0 = dword_180086460;
  while ( v0 )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)&qword_180086438[5 * (unsigned int)--v0]);
    --dword_180086460;
  }
  return 1;
}

```

## disassembly

```asm
0x180050f24  push    rbx
0x180050f26  sub     rsp, 20h
0x180050f2a  mov     ebx, cs:dword_180086460
0x180050f30  jmp     short loc_180050F4F
0x180050f32  lea     rax, qword_180086438
0x180050f39  dec     ebx
0x180050f3b  lea     rcx, [rbx+rbx*4]
0x180050f3f  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x180050f43  call    cs:__imp_DeleteCriticalSection
0x180050f49  dec     cs:dword_180086460
0x180050f4f  test    ebx, ebx
0x180050f51  jnz     short loc_180050F32
0x180050f53  mov     al, 1
0x180050f55  add     rsp, 20h
0x180050f59  pop     rbx
0x180050f5a  retn
```
