# std::_Tidy_guard<std::vector<DISPLAYCONFIG_MODE_INFO,std::allocator<DISPLAYCONFIG_MODE_INFO>>>::~_Tidy_guard<std::vector<DISPLAYCONFIG_MODE_INFO,std::allocator<DISPLAYCONFIG_MODE_INFO>>>(void)

- ea: `0x14000e15c`
- end: `0x14000e172`
- name: `??1?$_Tidy_guard@V?$vector@UDISPLAYCONFIG_MODE_INFO@@V?$allocator@UDISPLAYCONFIG_MODE_INFO@@@std@@@std@@@std@@QEAA@XZ`
- size: `22`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14000df24`

## callees

- `0x14000e15c`
- `0x14000f16c`

## pseudocode

```c
__int64 __fastcall std::_Tidy_guard<std::vector<DISPLAYCONFIG_MODE_INFO>>::~_Tidy_guard<std::vector<DISPLAYCONFIG_MODE_INFO>>(
        __int64 **a1)
{
  __int64 *v1; // rcx
  __int64 result; // rax

  v1 = *a1;
  if ( v1 )
    return std::vector<DISPLAYCONFIG_MODE_INFO>::_Tidy(v1);
  return result;
}

```

## disassembly

```asm
0x14000e15c  sub     rsp, 28h
0x14000e160  mov     rcx, [rcx]
0x14000e163  test    rcx, rcx
0x14000e166  jz      short loc_14000E16D
0x14000e168  call    ?_Tidy@?$vector@UDISPLAYCONFIG_MODE_INFO@@V?$allocator@UDISPLAYCONFIG_MODE_INFO@@@std@@@std@@AEAAXXZ; std::vector<DISPLAYCONFIG_MODE_INFO>::_Tidy(void)
0x14000e16d  add     rsp, 28h
0x14000e171  retn
```
