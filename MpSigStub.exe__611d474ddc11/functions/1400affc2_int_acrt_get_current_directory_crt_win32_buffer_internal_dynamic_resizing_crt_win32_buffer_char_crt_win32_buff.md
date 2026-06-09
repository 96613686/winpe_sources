# int `__acrt_get_current_directory<__crt_win32_buffer_internal_dynamic_resizing>(__crt_win32_buffer<char,__crt_win32_buffer_internal_dynamic_resizing> &)'::`1'::dtor$0

- ea: `0x1400affc2`
- end: `0x1400affce`
- name: `?dtor$0@?0???$__acrt_get_current_directory@U__crt_win32_buffer_internal_dynamic_resizing@@@@YAHAEAV?$__crt_win32_buffer@DU__crt_win32_buffer_internal_dynamic_resizing@@@@@Z@4HA_6`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1400327b4`

## pseudocode

```c
__int64 __fastcall `__acrt_get_current_directory<__crt_win32_buffer_internal_dynamic_resizing>'::`1'::dtor$0(
        __int64 a1,
        __int64 a2)
{
  return sub_1400327B4(a2 + 32);
}

```

## disassembly

```asm
0x1400affc2  lea     rcx, [rdx+20h]
0x1400affc9  jmp     sub_1400327B4
```
