# __acrt_uninitialize_stdio

- ea: `0x14001b190`
- end: `0x14001b1eb`
- name: `__acrt_uninitialize_stdio`
- size: `91`
- prototype: `void()`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x140019930`
- `0x14001b190`
- `0x14001bf18`
- `0x14001c29c`
- `0x140020614`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x14001b1c1`
- `KERNEL32!DeleteCriticalSection` at `0x14001b1c1`

## pseudocode

```c
void _acrt_uninitialize_stdio()
{
  __int64 i; // rbx

  flushall();
  fcloseall();
  for ( i = 0; i != 24; i += 8 )
  {
    _acrt_stdio_free_buffer_nolock(*(_QWORD *)((char *)qword_14003E5D0 + i));
    DeleteCriticalSection((LPCRITICAL_SECTION)(*(_QWORD *)((char *)qword_14003E5D0 + i) + 48LL));
  }
  free_base(qword_14003E5D0);
  qword_14003E5D0 = 0;
}

```

## disassembly

```asm
0x14001b190  push    rbx
0x14001b192  sub     rsp, 20h
0x14001b196  call    _flushall
0x14001b19b  call    _fcloseall
0x14001b1a0  xor     ebx, ebx
0x14001b1a2  mov     rcx, cs:qword_14003E5D0
0x14001b1a9  mov     rcx, [rbx+rcx]
0x14001b1ad  call    __acrt_stdio_free_buffer_nolock
0x14001b1b2  mov     rax, cs:qword_14003E5D0
0x14001b1b9  mov     rcx, [rbx+rax]
0x14001b1bd  add     rcx, 30h ; '0'; lpCriticalSection
0x14001b1c1  call    cs:__imp_DeleteCriticalSection
0x14001b1c7  add     rbx, 8
0x14001b1cb  cmp     rbx, 18h
0x14001b1cf  jnz     short loc_14001B1A2
0x14001b1d1  mov     rcx, cs:qword_14003E5D0; Block
0x14001b1d8  call    _free_base
0x14001b1dd  and     cs:qword_14003E5D0, 0
0x14001b1e5  add     rsp, 20h
0x14001b1e9  pop     rbx
0x14001b1ea  retn
```
