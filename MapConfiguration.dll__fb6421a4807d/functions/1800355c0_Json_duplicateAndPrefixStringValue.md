# Json::duplicateAndPrefixStringValue

- ea: `0x1800355c0`
- end: `0x1800356a7`
- name: `Json::duplicateAndPrefixStringValue`
- size: `231`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18003417c`
- `0x1800342dc`

## callees

- `0x1800094a0`
- `0x18000b215`
- `0x18000cd80`
- `0x18001a7a8`
- `0x18002ccd0`
- `0x18002f858`
- `0x1800355c0`
- `0x1800360f0`
- `0x180036128`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180035633`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180035633`

## string_xrefs

- `0x180035641`: `in Json::Value::duplicateAndPrefixStringValue(): Failed to allocate string value buffer`
- `0x1800355f9`: `in Json::Value::duplicateAndPrefixStringValue(): length too big for prefixing`

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
    std::ostringstream::ostringstream((__int64)v8);
    std::operator<<<std::char_traits<char>>(
      (__int64)v8,
      (__int64)"in Json::Value::duplicateAndPrefixStringValue(): length too big for prefixing");
    std::stringbuf::str(v9, v10);
    Json::throwLogicError(v10);
  }
  v4 = a2 + 5;
  v5 = malloc(2LL * (a2 + 5));
  v6 = v5;
  if ( !v5 )
  {
    std::string::string(
      (__int64)v10,
      (__int64)"in Json::Value::duplicateAndPrefixStringValue(): Failed to allocate string value buffer");
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
0x1800355c0  mov     [rsp+arg_10], rbx
0x1800355c5  push    rbp
0x1800355c6  push    rsi
0x1800355c7  push    rdi
0x1800355c8  sub     rsp, 150h
0x1800355cf  mov     rax, cs:__security_cookie
0x1800355d6  xor     rax, rsp
0x1800355d9  mov     [rsp+168h+var_28], rax
0x1800355e1  mov     ebx, edx
0x1800355e3  mov     rbp, rcx
0x1800355e6  cmp     edx, 7FFFFFFAh
0x1800355ec  jbe     short loc_18003562B
0x1800355ee  lea     rcx, [rsp+168h+var_138]
0x1800355f3  call    ??0?$basic_ostringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::ostringstream::ostringstream(void)
0x1800355f8  nop
0x1800355f9  lea     rdx, aInJsonValueDup; "in Json::Value::duplicateAndPrefixStrin"...
0x180035600  lea     rcx, [rsp+168h+var_138]
0x180035605  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18003560a  lea     rdx, [rsp+168h+var_48]
0x180035612  lea     rcx, [rsp+168h+var_130]
0x180035617  call    ?str@?$basic_stringbuf@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@XZ; std::stringbuf::str(void)
0x18003561c  nop
0x18003561d  lea     rcx, [rsp+168h+var_48]
0x180035625  call    ?throwLogicError@Json@@YAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Json::throwLogicError(std::string const &)
0x18003562b  lea     esi, [rbx+5]
0x18003562e  mov     ecx, esi
0x180035630  add     rcx, rcx; Size
0x180035633  call    cs:__imp_malloc
0x180035639  mov     rdi, rax
0x18003563c  test    rax, rax
0x18003563f  jnz     short loc_180035664
0x180035641  lea     rdx, aInJsonValueDup_0; "in Json::Value::duplicateAndPrefixStrin"...
0x180035648  lea     rcx, [rsp+168h+var_48]
0x180035650  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180035655  nop
0x180035656  lea     rcx, [rsp+168h+var_48]
0x18003565e  call    ?throwRuntimeError@Json@@YAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Json::throwRuntimeError(std::string const &)
0x180035664  mov     [rax], ebx
0x180035666  mov     r8, rbx
0x180035669  add     r8, r8; Size
0x18003566c  lea     rcx, [rax+8]; void *
0x180035670  mov     rdx, rbp; Src
0x180035673  call    memcpy_0
0x180035678  lea     ecx, [rsi-1]
0x18003567b  xor     eax, eax
0x18003567d  mov     [rdi+rcx*2], ax
0x180035681  mov     rax, rdi
0x180035684  mov     rcx, [rsp+168h+var_28]
0x18003568c  xor     rcx, rsp; StackCookie
0x18003568f  call    __security_check_cookie
0x180035694  mov     rbx, [rsp+168h+arg_10]
0x18003569c  add     rsp, 150h
0x1800356a3  pop     rdi
0x1800356a4  pop     rsi
0x1800356a5  pop     rbp
0x1800356a6  retn
```
