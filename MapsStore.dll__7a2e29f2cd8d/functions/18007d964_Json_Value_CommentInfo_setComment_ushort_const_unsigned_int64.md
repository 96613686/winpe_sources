# Json::Value::CommentInfo::setComment(ushort const *,unsigned __int64)

- ea: `0x18007d964`
- end: `0x18007da42`
- name: `?setComment@CommentInfo@Value@Json@@QEAAXPEBG_K@Z`
- size: `222`
- prototype: `void(Json::Value::CommentInfo *__hidden this, const unsigned __int16 *, unsigned __int64)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18007bea4`
- `0x18007da74`

## callees

- `0x18000d090`
- `0x180016468`
- `0x180021da8`
- `0x18002d9d8`
- `0x180033bd8`
- `0x18007d1fc`
- `0x18007d964`
- `0x18007dbf8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18007d998`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18007d998`

## string_xrefs

- `0x18007d9df`: `in Json::Value::setComment(): Comments must start with /`
- `0x18007d9a6`: `assert json failed`

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
    std::string::string(v7, "assert json failed");
    Json::throwLogicError(v7);
  }
  if ( *a2 && *a2 != 47 )
  {
    std::ostringstream::ostringstream(v5);
    std::operator<<<std::char_traits<char>>(v5, "in Json::Value::setComment(): Comments must start with /");
    std::stringbuf::str(v6, v7);
    Json::throwLogicError(v7);
  }
  *this = (void *)Json::duplicateStringValue(a2);
}

```

## disassembly

```asm
0x18007d964  mov     [rsp+arg_18], rbx
0x18007d969  push    rbp
0x18007d96a  push    rsi
0x18007d96b  push    rdi
0x18007d96c  sub     rsp, 150h
0x18007d973  mov     rax, cs:__security_cookie
0x18007d97a  xor     rax, rsp
0x18007d97d  mov     [rsp+168h+var_28], rax
0x18007d985  mov     rsi, r8
0x18007d988  mov     rbx, rdx
0x18007d98b  mov     rdi, rcx
0x18007d98e  xor     ebp, ebp
0x18007d990  mov     rcx, [rcx]; Block
0x18007d993  test    rcx, rcx
0x18007d996  jz      short loc_18007D9A1
0x18007d998  call    cs:__imp_free
0x18007d99e  mov     [rdi], rbp
0x18007d9a1  test    rbx, rbx
0x18007d9a4  jnz     short loc_18007D9C9
0x18007d9a6  lea     rdx, aAssertJsonFail; "assert json failed"
0x18007d9ad  lea     rcx, [rsp+168h+var_48]
0x18007d9b5  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18007d9ba  nop
0x18007d9bb  lea     rcx, [rsp+168h+var_48]
0x18007d9c3  call    ?throwLogicError@Json@@YAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Json::throwLogicError(std::string const &)
0x18007d9c9  cmp     [rbx], bp
0x18007d9cc  jz      short loc_18007DA11
0x18007d9ce  cmp     word ptr [rbx], 2Fh ; '/'
0x18007d9d2  jz      short loc_18007DA11
0x18007d9d4  lea     rcx, [rsp+168h+var_138]
0x18007d9d9  call    ??0?$basic_ostringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::ostringstream::ostringstream(void)
0x18007d9de  nop
0x18007d9df  lea     rdx, aInJsonValueSet; "in Json::Value::setComment(): Comments "...
0x18007d9e6  lea     rcx, [rsp+168h+var_138]
0x18007d9eb  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18007d9f0  lea     rdx, [rsp+168h+var_48]
0x18007d9f8  lea     rcx, [rsp+168h+var_130]
0x18007d9fd  call    ?str@?$basic_stringbuf@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@XZ; std::stringbuf::str(void)
0x18007da02  nop
0x18007da03  lea     rcx, [rsp+168h+var_48]
0x18007da0b  call    ?throwLogicError@Json@@YAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Json::throwLogicError(std::string const &)
0x18007da11  mov     rdx, rsi
0x18007da14  mov     rcx, rbx; Src
0x18007da17  call    Json__duplicateStringValue
0x18007da1c  mov     [rdi], rax
0x18007da1f  mov     rcx, [rsp+168h+var_28]
0x18007da27  xor     rcx, rsp; StackCookie
0x18007da2a  call    __security_check_cookie
0x18007da2f  mov     rbx, [rsp+168h+arg_18]
0x18007da37  add     rsp, 150h
0x18007da3e  pop     rdi
0x18007da3f  pop     rsi
0x18007da40  pop     rbp
0x18007da41  retn
```
