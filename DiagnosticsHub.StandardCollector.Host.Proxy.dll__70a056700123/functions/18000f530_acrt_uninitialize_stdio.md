# __acrt_uninitialize_stdio

- ea: `0x18000f530`
- end: `0x18000f58b`
- name: `__acrt_uninitialize_stdio`
- size: `91`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1800078e0`
- `0x18000f300`
- `0x18000f530`
- `0x1800159bc`
- `0x180015a80`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18000f561`
- `KERNEL32!DeleteCriticalSection` at `0x18000f561`

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
0x18000f530  push    rbx
0x18000f532  sub     rsp, 20h
0x18000f536  call    _flushall
0x18000f53b  call    _fcloseall
0x18000f540  xor     ebx, ebx
0x18000f542  mov     rcx, cs:__piob
0x18000f549  mov     rcx, [rbx+rcx]
0x18000f54d  call    __acrt_stdio_free_buffer_nolock
0x18000f552  mov     rax, cs:__piob
0x18000f559  mov     rcx, [rbx+rax]
0x18000f55d  add     rcx, 30h ; '0'; lpCriticalSection
0x18000f561  call    cs:__imp_DeleteCriticalSection
0x18000f567  add     rbx, 8
0x18000f56b  cmp     rbx, 18h
0x18000f56f  jnz     short loc_18000F542
0x18000f571  mov     rcx, cs:__piob; Block
0x18000f578  call    _free_base
0x18000f57d  and     cs:__piob, 0
0x18000f585  add     rsp, 20h
0x18000f589  pop     rbx
0x18000f58a  retn
```
