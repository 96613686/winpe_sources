# __acrt_uninitialize_stdio

- ea: `0x1802131f0`
- end: `0x18021324b`
- name: `__acrt_uninitialize_stdio`
- size: `91`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1802131f0`
- `0x180219680`
- `0x18021de74`
- `0x18021e268`
- `0x18021e270`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180213221`
- `KERNEL32!DeleteCriticalSection` at `0x180213221`

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
0x1802131f0  push    rbx
0x1802131f2  sub     rsp, 20h
0x1802131f6  call    _flushall
0x1802131fb  call    _fcloseall
0x180213200  xor     ebx, ebx
0x180213202  mov     rcx, cs:__piob
0x180213209  mov     rcx, [rbx+rcx]
0x18021320d  call    __acrt_stdio_free_buffer_nolock
0x180213212  mov     rax, cs:__piob
0x180213219  mov     rcx, [rbx+rax]
0x18021321d  add     rcx, 30h ; '0'; lpCriticalSection
0x180213221  call    cs:__imp_DeleteCriticalSection
0x180213227  add     rbx, 8
0x18021322b  cmp     rbx, 18h
0x18021322f  jnz     short loc_180213202
0x180213231  mov     rcx, cs:__piob; Block
0x180213238  call    _free_base
0x18021323d  and     cs:__piob, 0
0x180213245  add     rsp, 20h
0x180213249  pop     rbx
0x18021324a  retn
```
