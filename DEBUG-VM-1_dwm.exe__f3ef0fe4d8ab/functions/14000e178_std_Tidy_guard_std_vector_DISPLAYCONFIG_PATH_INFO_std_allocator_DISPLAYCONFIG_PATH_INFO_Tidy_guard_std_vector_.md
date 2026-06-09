# std::_Tidy_guard<std::vector<DISPLAYCONFIG_PATH_INFO,std::allocator<DISPLAYCONFIG_PATH_INFO>>>::~_Tidy_guard<std::vector<DISPLAYCONFIG_PATH_INFO,std::allocator<DISPLAYCONFIG_PATH_INFO>>>(void)

- ea: `0x14000e178`
- end: `0x14000e18e`
- name: `??1?$_Tidy_guard@V?$vector@UDISPLAYCONFIG_PATH_INFO@@V?$allocator@UDISPLAYCONFIG_PATH_INFO@@@std@@@std@@@std@@QEAA@XZ`
- size: `22`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14000df8c`

## callees

- `0x14000e178`
- `0x14000f1b0`

## pseudocode

```c
__int64 __fastcall std::_Tidy_guard<std::vector<DISPLAYCONFIG_PATH_INFO>>::~_Tidy_guard<std::vector<DISPLAYCONFIG_PATH_INFO>>(
        __int64 **a1)
{
  __int64 *v1; // rcx
  __int64 result; // rax

  v1 = *a1;
  if ( v1 )
    return std::vector<DISPLAYCONFIG_PATH_INFO>::_Tidy(v1);
  return result;
}

```

## disassembly

```asm
0x14000e178  sub     rsp, 28h
0x14000e17c  mov     rcx, [rcx]
0x14000e17f  test    rcx, rcx
0x14000e182  jz      short loc_14000E189
0x14000e184  call    ?_Tidy@?$vector@UDISPLAYCONFIG_PATH_INFO@@V?$allocator@UDISPLAYCONFIG_PATH_INFO@@@std@@@std@@AEAAXXZ; std::vector<DISPLAYCONFIG_PATH_INFO>::_Tidy(void)
0x14000e189  add     rsp, 28h
0x14000e18d  retn
```
