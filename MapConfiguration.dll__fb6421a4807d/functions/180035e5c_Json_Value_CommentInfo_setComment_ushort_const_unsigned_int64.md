# Json::Value::CommentInfo::setComment(ushort const *,unsigned __int64)

- ea: `0x180035e5c`
- end: `0x180035f3a`
- name: `?setComment@CommentInfo@Value@Json@@QEAAXPEBG_K@Z`
- size: `222`
- prototype: `void(Json::Value::CommentInfo *__hidden this, const unsigned __int16 *, unsigned __int64)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003417c`
- `0x180035f6c`

## callees

- `0x1800094a0`
- `0x18000cd80`
- `0x18001a7a8`
- `0x18002ccd0`
- `0x18002f858`
- `0x1800356b0`
- `0x180035e5c`
- `0x1800360f0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180035e90`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180035e90`

## string_xrefs

- `0x180035e9e`: `assert json failed`
- `0x180035ed7`: `in Json::Value::setComment(): Comments must start with /`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall Json::Value::CommentInfo::setComment(void **this, unsigned __int16 *a2)
{
  void *v4; // rcx
  _BYTE v5[8]; // [rsp+30h] [rbp-138h] BYREF
  _BYTE v6[232]; // [rsp+38h] [rbp-130h] BYREF
  _BYTE v7[32]; // [rsp+120h] [rbp-48h] BYREF

  v4 = *this;
  if ( v4 )
  {
    free(v4);
    *this = 0;
  }
  if ( !a2 )
  {
    std::string::string((__int64)v7, (__int64)"assert json failed");
    Json::throwLogicError(v7);
  }
  if ( *a2 && *a2 != 47 )
  {
    std::ostringstream::ostringstream((__int64)v5);
    std::operator<<<std::char_traits<char>>(
      (__int64)v5,
      (__int64)"in Json::Value::setComment(): Comments must start with /");
    std::stringbuf::str(v6, v7);
    Json::throwLogicError(v7);
  }
  *this = (void *)Json::duplicateStringValue(a2);
}

```

## disassembly

```asm
0x180035e5c  mov     [rsp+arg_18], rbx
0x180035e61  push    rbp
0x180035e62  push    rsi
0x180035e63  push    rdi
0x180035e64  sub     rsp, 150h
0x180035e6b  mov     rax, cs:__security_cookie
0x180035e72  xor     rax, rsp
0x180035e75  mov     [rsp+168h+var_28], rax
0x180035e7d  mov     rsi, r8
0x180035e80  mov     rbx, rdx
0x180035e83  mov     rdi, rcx
0x180035e86  xor     ebp, ebp
0x180035e88  mov     rcx, [rcx]; Block
0x180035e8b  test    rcx, rcx
0x180035e8e  jz      short loc_180035E99
0x180035e90  call    cs:__imp_free
0x180035e96  mov     [rdi], rbp
0x180035e99  test    rbx, rbx
0x180035e9c  jnz     short loc_180035EC1
0x180035e9e  lea     rdx, aAssertJsonFail; "assert json failed"
0x180035ea5  lea     rcx, [rsp+168h+var_48]
0x180035ead  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180035eb2  nop
0x180035eb3  lea     rcx, [rsp+168h+var_48]
0x180035ebb  call    ?throwLogicError@Json@@YAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Json::throwLogicError(std::string const &)
0x180035ec1  cmp     [rbx], bp
0x180035ec4  jz      short loc_180035F09
0x180035ec6  cmp     word ptr [rbx], 2Fh ; '/'
0x180035eca  jz      short loc_180035F09
0x180035ecc  lea     rcx, [rsp+168h+var_138]
0x180035ed1  call    ??0?$basic_ostringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::ostringstream::ostringstream(void)
0x180035ed6  nop
0x180035ed7  lea     rdx, aInJsonValueSet; "in Json::Value::setComment(): Comments "...
0x180035ede  lea     rcx, [rsp+168h+var_138]
0x180035ee3  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180035ee8  lea     rdx, [rsp+168h+var_48]
0x180035ef0  lea     rcx, [rsp+168h+var_130]
0x180035ef5  call    ?str@?$basic_stringbuf@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@XZ; std::stringbuf::str(void)
0x180035efa  nop
0x180035efb  lea     rcx, [rsp+168h+var_48]
0x180035f03  call    ?throwLogicError@Json@@YAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Json::throwLogicError(std::string const &)
0x180035f09  mov     rdx, rsi
0x180035f0c  mov     rcx, rbx; Src
0x180035f0f  call    Json__duplicateStringValue
0x180035f14  mov     [rdi], rax
0x180035f17  mov     rcx, [rsp+168h+var_28]
0x180035f1f  xor     rcx, rsp; StackCookie
0x180035f22  call    __security_check_cookie
0x180035f27  mov     rbx, [rsp+168h+arg_18]
0x180035f2f  add     rsp, 150h
0x180035f36  pop     rdi
0x180035f37  pop     rsi
0x180035f38  pop     rbp
0x180035f39  retn
```
