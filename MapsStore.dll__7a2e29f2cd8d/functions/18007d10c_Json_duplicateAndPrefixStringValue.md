# Json::duplicateAndPrefixStringValue

- ea: `0x18007d10c`
- end: `0x18007d1f3`
- name: `Json::duplicateAndPrefixStringValue`
- size: `231`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `3`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18007bea4`
- `0x18007c004`
- `0x18007c04c`

## callees

- `0x18000d090`
- `0x18000dc98`
- `0x180016468`
- `0x180021da8`
- `0x18002d9d8`
- `0x180033bd8`
- `0x18007d10c`
- `0x18007dbf8`
- `0x18007dc30`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18007d17f`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18007d17f`

## string_xrefs

- `0x18007d145`: `in Json::Value::duplicateAndPrefixStringValue(): length too big for prefixing`
- `0x18007d18d`: `in Json::Value::duplicateAndPrefixStringValue(): Failed to allocate string value buffer`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_DWORD *__fastcall Json::duplicateAndPrefixStringValue(void *Src, unsigned int a2)
{
  __int64 v2; // rbx
  unsigned int v4; // esi
  _DWORD *v5; // rax
  _DWORD *v6; // rdi
  char v8[8]; // [rsp+30h] [rbp-138h] BYREF
  char v9[232]; // [rsp+38h] [rbp-130h] BYREF
  _BYTE v10[32]; // [rsp+120h] [rbp-48h] BYREF

  v2 = a2;
  if ( a2 > 0x7FFFFFFA )
  {
    std::ostringstream::ostringstream(v8);
    std::operator<<<std::char_traits<char>>(
      v8,
      "in Json::Value::duplicateAndPrefixStringValue(): length too big for prefixing");
    std::stringbuf::str(v9, v10);
    Json::throwLogicError(v10);
  }
  v4 = a2 + 5;
  v5 = malloc(2LL * (a2 + 5));
  v6 = v5;
  if ( !v5 )
  {
    std::string::string(v10, "in Json::Value::duplicateAndPrefixStringValue(): Failed to allocate string value buffer");
    Json::throwRuntimeError(v10);
  }
  *v5 = v2;
  memcpy_0(v5 + 2, Src, 2 * v2);
  *((_WORD *)v6 + v4 - 1) = 0;
  return v6;
}

```

## disassembly

```asm
0x18007d10c  mov     [rsp+arg_10], rbx
0x18007d111  push    rbp
0x18007d112  push    rsi
0x18007d113  push    rdi
0x18007d114  sub     rsp, 150h
0x18007d11b  mov     rax, cs:__security_cookie
0x18007d122  xor     rax, rsp
0x18007d125  mov     [rsp+168h+var_28], rax
0x18007d12d  mov     ebx, edx
0x18007d12f  mov     rbp, rcx
0x18007d132  cmp     edx, 7FFFFFFAh
0x18007d138  jbe     short loc_18007D177
0x18007d13a  lea     rcx, [rsp+168h+var_138]
0x18007d13f  call    ??0?$basic_ostringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::ostringstream::ostringstream(void)
0x18007d144  nop
0x18007d145  lea     rdx, aInJsonValueDup; "in Json::Value::duplicateAndPrefixStrin"...
0x18007d14c  lea     rcx, [rsp+168h+var_138]
0x18007d151  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18007d156  lea     rdx, [rsp+168h+var_48]
0x18007d15e  lea     rcx, [rsp+168h+var_130]
0x18007d163  call    ?str@?$basic_stringbuf@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@XZ; std::stringbuf::str(void)
0x18007d168  nop
0x18007d169  lea     rcx, [rsp+168h+var_48]
0x18007d171  call    ?throwLogicError@Json@@YAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Json::throwLogicError(std::string const &)
0x18007d177  lea     esi, [rbx+5]
0x18007d17a  mov     ecx, esi
0x18007d17c  add     rcx, rcx; Size
0x18007d17f  call    cs:__imp_malloc
0x18007d185  mov     rdi, rax
0x18007d188  test    rax, rax
0x18007d18b  jnz     short loc_18007D1B0
0x18007d18d  lea     rdx, aInJsonValueDup_0; "in Json::Value::duplicateAndPrefixStrin"...
0x18007d194  lea     rcx, [rsp+168h+var_48]
0x18007d19c  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18007d1a1  nop
0x18007d1a2  lea     rcx, [rsp+168h+var_48]
0x18007d1aa  call    ?throwRuntimeError@Json@@YAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Json::throwRuntimeError(std::string const &)
0x18007d1b0  mov     [rax], ebx
0x18007d1b2  mov     r8, rbx
0x18007d1b5  add     r8, r8; Size
0x18007d1b8  lea     rcx, [rax+8]; void *
0x18007d1bc  mov     rdx, rbp; Src
0x18007d1bf  call    memcpy_0
0x18007d1c4  lea     ecx, [rsi-1]
0x18007d1c7  xor     eax, eax
0x18007d1c9  mov     [rdi+rcx*2], ax
0x18007d1cd  mov     rax, rdi
0x18007d1d0  mov     rcx, [rsp+168h+var_28]
0x18007d1d8  xor     rcx, rsp; StackCookie
0x18007d1db  call    __security_check_cookie
0x18007d1e0  mov     rbx, [rsp+168h+arg_10]
0x18007d1e8  add     rsp, 150h
0x18007d1ef  pop     rdi
0x18007d1f0  pop     rsi
0x18007d1f1  pop     rbp
0x18007d1f2  retn
```
