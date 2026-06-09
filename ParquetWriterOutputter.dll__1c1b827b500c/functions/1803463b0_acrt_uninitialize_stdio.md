# __acrt_uninitialize_stdio

- ea: `0x1803463b0`
- end: `0x18034640b`
- name: `__acrt_uninitialize_stdio`
- size: `91`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1803463b0`
- `0x180346620`
- `0x18034962c`
- `0x1803505d0`
- `0x180350684`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1803463e1`
- `KERNEL32!DeleteCriticalSection` at `0x1803463e1`

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
0x1803463b0  push    rbx
0x1803463b2  sub     rsp, 20h
0x1803463b6  call    _flushall
0x1803463bb  call    _fcloseall
0x1803463c0  xor     ebx, ebx
0x1803463c2  mov     rcx, cs:__piob
0x1803463c9  mov     rcx, [rbx+rcx]
0x1803463cd  call    __acrt_stdio_free_buffer_nolock
0x1803463d2  mov     rax, cs:__piob
0x1803463d9  mov     rcx, [rbx+rax]
0x1803463dd  add     rcx, 30h ; '0'; lpCriticalSection
0x1803463e1  call    cs:__imp_DeleteCriticalSection
0x1803463e7  add     rbx, 8
0x1803463eb  cmp     rbx, 18h
0x1803463ef  jnz     short loc_1803463C2
0x1803463f1  mov     rcx, cs:__piob; Block
0x1803463f8  call    _free_base
0x1803463fd  and     cs:__piob, 0
0x180346405  add     rsp, 20h
0x180346409  pop     rbx
0x18034640a  retn
```
