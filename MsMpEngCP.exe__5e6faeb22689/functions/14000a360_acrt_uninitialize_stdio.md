# __acrt_uninitialize_stdio

- ea: `0x14000a360`
- end: `0x14000a3bb`
- name: `__acrt_uninitialize_stdio`
- size: `91`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x140006940`
- `0x14000a230`
- `0x14000a360`
- `0x14000c2f8`
- `0x14000c3ac`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x14000a391`
- `KERNEL32!DeleteCriticalSection` at `0x14000a391`

## pseudocode

```c
void _acrt_uninitialize_stdio()
{
  __int64 i; // rbx

  flushall();
  fcloseall();
  for ( i = 0; i != 24; i += 8 )
  {
    _acrt_stdio_free_buffer_nolock(*(_QWORD *)((char *)qword_14001AC58 + i));
    DeleteCriticalSection((LPCRITICAL_SECTION)(*(_QWORD *)((char *)qword_14001AC58 + i) + 48LL));
  }
  free_base(qword_14001AC58);
  qword_14001AC58 = 0;
}

```

## disassembly

```asm
0x14000a360  push    rbx
0x14000a362  sub     rsp, 20h
0x14000a366  call    _flushall
0x14000a36b  call    _fcloseall
0x14000a370  xor     ebx, ebx
0x14000a372  mov     rcx, cs:qword_14001AC58
0x14000a379  mov     rcx, [rbx+rcx]
0x14000a37d  call    __acrt_stdio_free_buffer_nolock
0x14000a382  mov     rax, cs:qword_14001AC58
0x14000a389  mov     rcx, [rbx+rax]
0x14000a38d  add     rcx, 30h ; '0'; lpCriticalSection
0x14000a391  call    cs:DeleteCriticalSection
0x14000a397  add     rbx, 8
0x14000a39b  cmp     rbx, 18h
0x14000a39f  jnz     short loc_14000A372
0x14000a3a1  mov     rcx, cs:qword_14001AC58; Block
0x14000a3a8  call    _free_base
0x14000a3ad  and     cs:qword_14001AC58, 0
0x14000a3b5  add     rsp, 20h
0x14000a3b9  pop     rbx
0x14000a3ba  retn
```
