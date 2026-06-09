# __acrt_uninitialize_stdio

- ea: `0x140011b60`
- end: `0x140011bbb`
- name: `__acrt_uninitialize_stdio`
- size: `91`
- prototype: `void()`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1400107c4`
- `0x140011b60`
- `0x140015818`
- `0x140015c0c`
- `0x140015c14`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x140011b91`
- `KERNEL32!DeleteCriticalSection` at `0x140011b91`

## pseudocode

```c
void _acrt_uninitialize_stdio()
{
  __int64 i; // rbx

  flushall();
  fcloseall();
  for ( i = 0; i != 24; i += 8 )
  {
    _acrt_stdio_free_buffer_nolock(*(_QWORD *)((char *)Block + i));
    DeleteCriticalSection((LPCRITICAL_SECTION)(*(_QWORD *)((char *)Block + i) + 48LL));
  }
  free_base(Block);
  Block = 0;
}

```

## disassembly

```asm
0x140011b60  push    rbx
0x140011b62  sub     rsp, 20h
0x140011b66  call    _flushall
0x140011b6b  call    _fcloseall
0x140011b70  xor     ebx, ebx
0x140011b72  mov     rcx, cs:Block
0x140011b79  mov     rcx, [rbx+rcx]
0x140011b7d  call    __acrt_stdio_free_buffer_nolock
0x140011b82  mov     rax, cs:Block
0x140011b89  mov     rcx, [rbx+rax]
0x140011b8d  add     rcx, 30h ; '0'; lpCriticalSection
0x140011b91  call    cs:DeleteCriticalSection
0x140011b97  add     rbx, 8
0x140011b9b  cmp     rbx, 18h
0x140011b9f  jnz     short loc_140011B72
0x140011ba1  mov     rcx, cs:Block; Block
0x140011ba8  call    _free_base
0x140011bad  and     cs:Block, 0
0x140011bb5  add     rsp, 20h
0x140011bb9  pop     rbx
0x140011bba  retn
```
