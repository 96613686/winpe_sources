# __acrt_thread_detach

- ea: `0x18000e6e4`
- end: `0x18000e6f4`
- name: `__acrt_thread_detach`
- size: `16`
- prototype: `__crt_bool __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800077d0`

## callees

- `0x180010260`

## pseudocode

```c
__crt_bool __cdecl _acrt_thread_detach()
{
  _acrt_freeptd();
  return 1;
}

```

## disassembly

```asm
0x18000e6e4  sub     rsp, 28h
0x18000e6e8  call    __acrt_freeptd
0x18000e6ed  mov     al, 1
0x18000e6ef  add     rsp, 28h
0x18000e6f3  retn
```
