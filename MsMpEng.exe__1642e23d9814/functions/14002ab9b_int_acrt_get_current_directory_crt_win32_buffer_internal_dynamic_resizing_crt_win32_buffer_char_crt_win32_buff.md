# int `__acrt_get_current_directory<__crt_win32_buffer_internal_dynamic_resizing>(__crt_win32_buffer<char,__crt_win32_buffer_internal_dynamic_resizing> &)'::`1'::dtor$0

- ea: `0x14002ab9b`
- end: `0x14002aba7`
- name: `?dtor$0@?0???$__acrt_get_current_directory@U__crt_win32_buffer_internal_dynamic_resizing@@@@YAHAEAV?$__crt_win32_buffer@DU__crt_win32_buffer_internal_dynamic_resizing@@@@@Z@4HA_0`
- size: `12`
- prototype: `__int64 (__fastcall *__fastcall(__int64, __int64))(int, int, int, int, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14002ab9b`

## pseudocode

```c
__int64 (__fastcall *__fastcall `__acrt_get_current_directory<__crt_win32_buffer_internal_dynamic_resizing>'::`1'::dtor$0(
        __int64 a1,
        __int64 a2))(int, int, int, int, __int64)
{
  __int64 (__fastcall *result)(int, int, int, int, __int64); // rax

  if ( !*(_BYTE *)(a2 + 32) )
  {
    off_14003C138[0] = sub_140008760;
    off_14003C140[0] = sub_140008760;
    off_14003C148[0] = sub_140008760;
    off_14003C150 = sub_140008780;
    result = sub_1400087A0;
    off_14003C158 = sub_1400087A0;
  }
  return result;
}

```

## disassembly

```asm
0x14002ab9b  lea     rcx, [rdx+20h]
0x14002aba2  jmp     loc_14000895C
0x14000895c  cmp     byte ptr [rcx], 0
0x14000895f  jnz     short locret_1400089A7
0x140008961  lea     rax, sub_140008760
0x140008968  mov     cs:off_14003C138, rax
0x14000896f  lea     rax, sub_140008760
0x140008976  mov     cs:off_14003C140, rax
0x14000897d  lea     rax, sub_140008760
0x140008984  mov     cs:off_14003C148, rax
0x14000898b  lea     rax, sub_140008780
0x140008992  mov     cs:off_14003C150, rax
0x140008999  lea     rax, sub_1400087A0
0x1400089a0  mov     cs:off_14003C158, rax
0x1400089a7  retn
```
