# __acrt_uninitialize_stdio

- ea: `0x140011250`
- end: `0x1400112ab`
- name: `__acrt_uninitialize_stdio`
- size: `91`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x140011250`
- `0x140013e10`
- `0x140016224`
- `0x140016618`
- `0x140016620`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x140011281`
- `KERNEL32!DeleteCriticalSection` at `0x140011281`

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
0x140011250  push    rbx
0x140011252  sub     rsp, 20h
0x140011256  call    _flushall
0x14001125b  call    _fcloseall
0x140011260  xor     ebx, ebx
0x140011262  mov     rcx, cs:__piob
0x140011269  mov     rcx, [rbx+rcx]
0x14001126d  call    __acrt_stdio_free_buffer_nolock
0x140011272  mov     rax, cs:__piob
0x140011279  mov     rcx, [rbx+rax]
0x14001127d  add     rcx, 30h ; '0'; lpCriticalSection
0x140011281  call    cs:__imp_DeleteCriticalSection
0x140011287  add     rbx, 8
0x14001128b  cmp     rbx, 18h
0x14001128f  jnz     short loc_140011262
0x140011291  mov     rcx, cs:__piob; Block
0x140011298  call    _free_base
0x14001129d  and     cs:__piob, 0
0x1400112a5  add     rsp, 20h
0x1400112a9  pop     rbx
0x1400112aa  retn
```
