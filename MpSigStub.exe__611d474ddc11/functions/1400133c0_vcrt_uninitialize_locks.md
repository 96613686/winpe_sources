# __vcrt_uninitialize_locks

- ea: `0x1400133c0`
- end: `0x1400133f7`
- name: `__vcrt_uninitialize_locks`
- size: `55`
- prototype: `char()`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140013350`

## callees

- `0x1400133c0`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1400133df`
- `KERNEL32!DeleteCriticalSection` at `0x1400133df`

## pseudocode

```c
char _vcrt_uninitialize_locks()
{
  int v0; // ebx

  v0 = dword_1400D7010;
  while ( v0 )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)&qword_1400D6DE0[5 * (unsigned int)--v0]);
    --dword_1400D7010;
  }
  return 1;
}

```

## disassembly

```asm
0x1400133c0  push    rbx
0x1400133c2  sub     rsp, 20h
0x1400133c6  mov     ebx, cs:dword_1400D7010
0x1400133cc  jmp     short loc_1400133EB
0x1400133ce  lea     rax, qword_1400D6DE0
0x1400133d5  dec     ebx
0x1400133d7  lea     rcx, [rbx+rbx*4]
0x1400133db  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x1400133df  call    cs:DeleteCriticalSection
0x1400133e5  dec     cs:dword_1400D7010
0x1400133eb  test    ebx, ebx
0x1400133ed  jnz     short loc_1400133CE
0x1400133ef  mov     al, 1
0x1400133f1  add     rsp, 20h
0x1400133f5  pop     rbx
0x1400133f6  retn
```
