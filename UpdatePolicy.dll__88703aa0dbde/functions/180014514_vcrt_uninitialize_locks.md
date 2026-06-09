# __vcrt_uninitialize_locks

- ea: `0x180014514`
- end: `0x18001454b`
- name: `__vcrt_uninitialize_locks`
- size: `55`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180010c68`
- `0x180010ccc`
- `0x1800144c4`

## callees

- `0x180014514`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180014533`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180014533`

## pseudocode

```c
char _vcrt_uninitialize_locks()
{
  int v0; // ebx

  v0 = dword_18001FE68;
  while ( v0 )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)&qword_18001FE40[5 * (unsigned int)--v0]);
    --dword_18001FE68;
  }
  return 1;
}

```

## disassembly

```asm
0x180014514  push    rbx
0x180014516  sub     rsp, 20h
0x18001451a  mov     ebx, cs:dword_18001FE68
0x180014520  jmp     short loc_18001453F
0x180014522  lea     rax, qword_18001FE40
0x180014529  dec     ebx
0x18001452b  lea     rcx, [rbx+rbx*4]
0x18001452f  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x180014533  call    cs:__imp_DeleteCriticalSection
0x180014539  dec     cs:dword_18001FE68
0x18001453f  test    ebx, ebx
0x180014541  jnz     short loc_180014522
0x180014543  mov     al, 1
0x180014545  add     rsp, 20h
0x180014549  pop     rbx
0x18001454a  retn
```
