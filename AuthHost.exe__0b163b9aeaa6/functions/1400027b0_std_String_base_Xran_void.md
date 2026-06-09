# std::_String_base::_Xran(void)

- ea: `0x1400027b0`
- end: `0x140002808`
- name: `?_Xran@_String_base@std@@SAXXZ`
- size: `88`
- prototype: `void __noreturn(void)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x14000fa74`
- `0x14000fbc8`
- `0x14001017c`
- `0x14001020c`

## callees

- `0x1400029d3`
- `0x14000cf6c`
- `0x14000d1ec`

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
0x1400027b0  sub     rsp, 0A8h
0x1400027b7  mov     [rsp+0A8h+var_88], 0FFFFFFFFFFFFFFFEh
0x1400027c0  mov     rax, cs:__security_cookie
0x1400027c7  xor     rax, rsp
0x1400027ca  mov     [rsp+0A8h+var_18], rax
0x1400027d2  lea     rdx, aInvalidStringP; "invalid string position"
0x1400027d9  lea     rcx, [rsp+0A8h+var_80]
0x1400027de  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@QEAA@PEBD@Z; std::string::string(char const *)
0x1400027e3  nop
0x1400027e4  xor     r8d, r8d
0x1400027e7  lea     rdx, [rsp+0A8h+var_80]
0x1400027ec  lea     rcx, [rsp+0A8h+pExceptionObject]
0x1400027f1  call    ??0out_of_range@std@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@1@PEAV_STL70@@@Z; std::out_of_range::out_of_range(std::string const &,_STL70 *)
0x1400027f6  lea     rdx, _TI3?AVout_of_range@std@@; pThrowInfo
0x1400027fd  lea     rcx, [rsp+0A8h+pExceptionObject]; pExceptionObject
0x140002802  call    _CxxThrowException_0
```
