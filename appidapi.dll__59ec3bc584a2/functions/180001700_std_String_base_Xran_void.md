# std::_String_base::_Xran(void)

- ea: `0x180001700`
- end: `0x180001758`
- name: `?_Xran@_String_base@std@@SAXXZ`
- size: `88`
- prototype: `void __noreturn(void)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x180001760`
- `0x180001934`
- `0x18000379c`
- `0x1800039e8`
- `0x180003af0`

## callees

- `0x1800010a8`
- `0x1800012b8`
- `0x18000227c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __noreturn std::_String_base::_Xran(void)
{
  _BYTE v0[40]; // [rsp+28h] [rbp-80h] BYREF
  _BYTE pExceptionObject[64]; // [rsp+50h] [rbp-58h] BYREF

  std::string::string(v0, "invalid string position");
  std::out_of_range::out_of_range(pExceptionObject, v0, 0);
  throw (std::out_of_range *)pExceptionObject;
}

```

## disassembly

```asm
0x180001700  sub     rsp, 0A8h
0x180001707  mov     [rsp+0A8h+var_88], 0FFFFFFFFFFFFFFFEh
0x180001710  mov     rax, cs:__security_cookie
0x180001717  xor     rax, rsp
0x18000171a  mov     [rsp+0A8h+var_18], rax
0x180001722  lea     rdx, aInvalidStringP; "invalid string position"
0x180001729  lea     rcx, [rsp+0A8h+var_80]
0x18000172e  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@QEAA@PEBD@Z; std::string::string(char const *)
0x180001733  nop
0x180001734  xor     r8d, r8d
0x180001737  lea     rdx, [rsp+0A8h+var_80]
0x18000173c  lea     rcx, [rsp+0A8h+pExceptionObject]
0x180001741  call    ??0out_of_range@std@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@1@PEAV_STL70@@@Z; std::out_of_range::out_of_range(std::string const &,_STL70 *)
0x180001746  lea     rdx, _TI3?AVout_of_range@std@@; pThrowInfo
0x18000174d  lea     rcx, [rsp+0A8h+pExceptionObject]; pExceptionObject
0x180001752  call    _CxxThrowException_0
```
