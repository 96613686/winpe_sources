# __acrt_uninitialize_stdio

- ea: `0x18000fc90`
- end: `0x18000fceb`
- name: `__acrt_uninitialize_stdio`
- size: `91`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180008040`
- `0x18000fa60`
- `0x18000fc90`
- `0x18001611c`
- `0x1800161e0`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18000fcc1`
- `KERNEL32!DeleteCriticalSection` at `0x18000fcc1`

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
0x18000fc90  push    rbx
0x18000fc92  sub     rsp, 20h
0x18000fc96  call    _flushall
0x18000fc9b  call    _fcloseall
0x18000fca0  xor     ebx, ebx
0x18000fca2  mov     rcx, cs:__piob
0x18000fca9  mov     rcx, [rbx+rcx]
0x18000fcad  call    __acrt_stdio_free_buffer_nolock
0x18000fcb2  mov     rax, cs:__piob
0x18000fcb9  mov     rcx, [rbx+rax]
0x18000fcbd  add     rcx, 30h ; '0'; lpCriticalSection
0x18000fcc1  call    cs:__imp_DeleteCriticalSection
0x18000fcc7  add     rbx, 8
0x18000fccb  cmp     rbx, 18h
0x18000fccf  jnz     short loc_18000FCA2
0x18000fcd1  mov     rcx, cs:__piob; Block
0x18000fcd8  call    _free_base
0x18000fcdd  and     cs:__piob, 0
0x18000fce5  add     rsp, 20h
0x18000fce9  pop     rbx
0x18000fcea  retn
```
