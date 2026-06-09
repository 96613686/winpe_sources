# __acrt_uninitialize_stdio

- ea: `0x14006ce60`
- end: `0x14006cebb`
- name: `__acrt_uninitialize_stdio`
- size: `91`
- prototype: `void()`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x14006cd30`
- `0x14006ce60`
- `0x140072280`
- `0x140076244`
- `0x1400770dc`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x14006ce91`
- `KERNEL32!DeleteCriticalSection` at `0x14006ce91`

## pseudocode

```c
void _acrt_uninitialize_stdio()
{
  __int64 i; // rbx

  flushall();
  fcloseall();
  for ( i = 0; i != 24; i += 8 )
  {
    _acrt_stdio_free_buffer_nolock(*(_QWORD *)((char *)qword_1400C43C0 + i));
    DeleteCriticalSection((LPCRITICAL_SECTION)(*(_QWORD *)((char *)qword_1400C43C0 + i) + 48LL));
  }
  free_base(qword_1400C43C0);
  qword_1400C43C0 = 0;
}

```

## disassembly

```asm
0x14006ce60  push    rbx
0x14006ce62  sub     rsp, 20h
0x14006ce66  call    _flushall
0x14006ce6b  call    _fcloseall
0x14006ce70  xor     ebx, ebx
0x14006ce72  mov     rcx, cs:qword_1400C43C0
0x14006ce79  mov     rcx, [rbx+rcx]
0x14006ce7d  call    __acrt_stdio_free_buffer_nolock
0x14006ce82  mov     rax, cs:qword_1400C43C0
0x14006ce89  mov     rcx, [rbx+rax]
0x14006ce8d  add     rcx, 30h ; '0'; lpCriticalSection
0x14006ce91  call    cs:__imp_DeleteCriticalSection
0x14006ce97  add     rbx, 8
0x14006ce9b  cmp     rbx, 18h
0x14006ce9f  jnz     short loc_14006CE72
0x14006cea1  mov     rcx, cs:qword_1400C43C0; Block
0x14006cea8  call    _free_base
0x14006cead  and     cs:qword_1400C43C0, 0
0x14006ceb5  add     rsp, 20h
0x14006ceb9  pop     rbx
0x14006ceba  retn
```
