# Json::Value::operator[](int)

- ea: `0x180034714`
- end: `0x18003478b`
- name: `??AValue@Json@@QEAAAEAV01@H@Z`
- size: `119`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180021e14`
- `0x180038504`

## callees

- `0x1800094a0`
- `0x18000cd80`
- `0x18001a7a8`
- `0x18002f858`
- `0x180034714`
- `0x180034794`
- `0x1800360f0`

## string_xrefs

- `0x18003473c`: `in Json::Value::operator[](int index): index cannot be negative`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Json::Value::operator[](__int64 **a1, int a2)
{
  _BYTE v3[8]; // [rsp+30h] [rbp-128h] BYREF
  _BYTE v4[232]; // [rsp+38h] [rbp-120h] BYREF
  _BYTE v5[32]; // [rsp+120h] [rbp-38h] BYREF

  if ( a2 < 0 )
  {
    std::ostringstream::ostringstream((__int64)v3);
    std::operator<<<std::char_traits<char>>(
      (__int64)v3,
      (__int64)"in Json::Value::operator[](int index): index cannot be negative");
    std::stringbuf::str(v4, v5);
    Json::throwLogicError(v5);
  }
  return Json::Value::operator[](a1, a2);
}

```

## disassembly

```asm
0x180034714  sub     rsp, 158h
0x18003471b  mov     rax, cs:__security_cookie
0x180034722  xor     rax, rsp
0x180034725  mov     [rsp+158h+var_18], rax
0x18003472d  test    edx, edx
0x18003472f  jns     short loc_18003476E
0x180034731  lea     rcx, [rsp+158h+var_128]
0x180034736  call    ??0?$basic_ostringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::ostringstream::ostringstream(void)
0x18003473b  nop
0x18003473c  lea     rdx, aInJsonValueOpe; "in Json::Value::operator[](int index): "...
0x180034743  lea     rcx, [rsp+158h+var_128]
0x180034748  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18003474d  lea     rdx, [rsp+158h+var_38]
0x180034755  lea     rcx, [rsp+158h+var_120]
0x18003475a  call    ?str@?$basic_stringbuf@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@XZ; std::stringbuf::str(void)
0x18003475f  nop
0x180034760  lea     rcx, [rsp+158h+var_38]
0x180034768  call    ?throwLogicError@Json@@YAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Json::throwLogicError(std::string const &)
0x18003476e  call    ??AValue@Json@@QEAAAEAV01@I@Z; Json::Value::operator[](uint)
0x180034773  mov     rcx, [rsp+158h+var_18]
0x18003477b  xor     rcx, rsp; StackCookie
0x18003477e  call    __security_check_cookie
0x180034783  add     rsp, 158h
0x18003478a  retn
```
