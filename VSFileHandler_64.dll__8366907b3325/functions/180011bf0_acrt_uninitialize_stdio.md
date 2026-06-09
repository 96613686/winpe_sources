# __acrt_uninitialize_stdio

- ea: `0x180011bf0`
- end: `0x180011c4b`
- name: `__acrt_uninitialize_stdio`
- size: `91`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x18000fe3c`
- `0x180011bf0`
- `0x1800146f8`
- `0x1800167ec`
- `0x1800168a0`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180011c21`
- `KERNEL32!DeleteCriticalSection` at `0x180011c21`

## pseudocode

```c
void _acrt_uninitialize_stdio()
{
  __int64 i; // rbx

  flushall();
  fcloseall();
  for ( i = 0; i != 24; i += 8 )
  {
    _acrt_stdio_free_buffer_nolock(*(_QWORD *)((char *)_piob + i));
    DeleteCriticalSection((LPCRITICAL_SECTION)(*(_QWORD *)((char *)_piob + i) + 48LL));
  }
  free_base(_piob);
  _piob = 0;
}

```

## disassembly

```asm
0x180011bf0  push    rbx
0x180011bf2  sub     rsp, 20h
0x180011bf6  call    _flushall
0x180011bfb  call    _fcloseall
0x180011c00  xor     ebx, ebx
0x180011c02  mov     rcx, cs:__piob
0x180011c09  mov     rcx, [rbx+rcx]
0x180011c0d  call    __acrt_stdio_free_buffer_nolock
0x180011c12  mov     rax, cs:__piob
0x180011c19  mov     rcx, [rbx+rax]
0x180011c1d  add     rcx, 30h ; '0'; lpCriticalSection
0x180011c21  call    cs:__imp_DeleteCriticalSection
0x180011c27  add     rbx, 8
0x180011c2b  cmp     rbx, 18h
0x180011c2f  jnz     short loc_180011C02
0x180011c31  mov     rcx, cs:__piob; Block
0x180011c38  call    _free_base
0x180011c3d  and     cs:__piob, 0
0x180011c45  add     rsp, 20h
0x180011c49  pop     rbx
0x180011c4a  retn
```
