# int `__acrt_get_current_directory<__crt_win32_buffer_internal_dynamic_resizing>(__crt_win32_buffer<char,__crt_win32_buffer_internal_dynamic_resizing> &)'::`1'::dtor$0

- ea: `0x1400aed29`
- end: `0x1400aed35`
- name: `?dtor$0@?0???$__acrt_get_current_directory@U__crt_win32_buffer_internal_dynamic_resizing@@@@YAHAEAV?$__crt_win32_buffer@DU__crt_win32_buffer_internal_dynamic_resizing@@@@@Z@4HA`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1400257e0`

## pseudocode

```c
void __fastcall `__acrt_get_current_directory<__crt_win32_buffer_internal_dynamic_resizing>'::`1'::dtor$0(
        __int64 a1,
        __int64 a2)
{
  sub_1400257E0((void *)(a2 + 32));
}

```

## disassembly

```asm
0x1400aed29  lea     rcx, [rdx+20h]; void *
0x1400aed30  jmp     sub_1400257E0
```
