# __vcrt_uninitialize_locks_0

- ea: `0x140022294`
- end: `0x1400222cb`
- name: `__vcrt_uninitialize_locks_0`
- size: `55`
- prototype: `char()`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x14001ee00`
- `0x14001ee28`
- `0x14002224c`

## callees

- `0x140022294`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1400222b3`
- `KERNEL32!DeleteCriticalSection` at `0x1400222b3`

## pseudocode

```c
char _vcrt_uninitialize_locks_0()
{
  int v0; // ebx

  v0 = dword_1400D7920;
  while ( v0 )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)&qword_1400D78F8[5 * (unsigned int)--v0]);
    --dword_1400D7920;
  }
  return 1;
}

```

## disassembly

```asm
0x140022294  push    rbx
0x140022296  sub     rsp, 20h
0x14002229a  mov     ebx, cs:dword_1400D7920
0x1400222a0  jmp     short loc_1400222BF
0x1400222a2  lea     rax, qword_1400D78F8
0x1400222a9  dec     ebx
0x1400222ab  lea     rcx, [rbx+rbx*4]
0x1400222af  lea     rcx, [rax+rcx*8]; lpCriticalSection
0x1400222b3  call    cs:DeleteCriticalSection
0x1400222b9  dec     cs:dword_1400D7920
0x1400222bf  test    ebx, ebx
0x1400222c1  jnz     short loc_1400222A2
0x1400222c3  mov     al, 1
0x1400222c5  add     rsp, 20h
0x1400222c9  pop     rbx
0x1400222ca  retn
```
