# Json::duplicateStringValue

- ea: `0x18007d1fc`
- end: `0x18007d294`
- name: `Json::duplicateStringValue`
- size: `152`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18007bdb8`
- `0x18007d964`

## callees

- `0x18000d090`
- `0x18000dc98`
- `0x180016468`
- `0x18007d1fc`
- `0x18007dc30`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18007d235`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18007d235`

## string_xrefs

- `0x18007d243`: `in Json::Value::duplicateStringValue(): Failed to allocate string value buffer`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char *__fastcall Json::duplicateStringValue(void *Src, unsigned __int64 a2)
{
  __int64 v3; // rax
  size_t v4; // rdi
  char *v5; // rax
  char *v6; // rbx
  _BYTE v8[32]; // [rsp+20h] [rbp-38h] BYREF

  v3 = 2147483646;
  if ( a2 < 0x7FFFFFFF )
    v3 = a2;
  v4 = 2 * v3;
  v5 = (char *)malloc(2 * v3 + 2);
  v6 = v5;
  if ( !v5 )
  {
    std::string::string(v8, "in Json::Value::duplicateStringValue(): Failed to allocate string value buffer");
    Json::throwRuntimeError(v8);
  }
  memcpy_0(v5, Src, v4);
  *(_WORD *)&v6[v4] = 0;
  return v6;
}

```

## disassembly

```asm
0x18007d1fc  mov     [rsp+arg_10], rbx
0x18007d201  mov     [rsp+arg_18], rsi
0x18007d206  push    rdi
0x18007d207  sub     rsp, 50h
0x18007d20b  mov     rax, cs:__security_cookie
0x18007d212  xor     rax, rsp
0x18007d215  mov     [rsp+58h+var_18], rax
0x18007d21a  mov     rsi, rcx
0x18007d21d  mov     eax, 7FFFFFFEh
0x18007d222  cmp     rdx, 7FFFFFFFh
0x18007d229  cmovb   rax, rdx
0x18007d22d  lea     rdi, [rax+rax]
0x18007d231  lea     rcx, [rdi+2]; Size
0x18007d235  call    cs:__imp_malloc
0x18007d23b  mov     rbx, rax
0x18007d23e  test    rax, rax
0x18007d241  jnz     short loc_18007D260
0x18007d243  lea     rdx, aInJsonValueDup_1; "in Json::Value::duplicateStringValue():"...
0x18007d24a  lea     rcx, [rsp+58h+var_38]
0x18007d24f  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18007d254  nop
0x18007d255  lea     rcx, [rsp+58h+var_38]
0x18007d25a  call    ?throwRuntimeError@Json@@YAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Json::throwRuntimeError(std::string const &)
0x18007d260  mov     r8, rdi; Size
0x18007d263  mov     rdx, rsi; Src
0x18007d266  mov     rcx, rbx; void *
0x18007d269  call    memcpy_0
0x18007d26e  xor     eax, eax
0x18007d270  mov     [rdi+rbx], ax
0x18007d274  mov     rax, rbx
0x18007d277  mov     rcx, [rsp+58h+var_18]
0x18007d27c  xor     rcx, rsp; StackCookie
0x18007d27f  call    __security_check_cookie
0x18007d284  mov     rbx, [rsp+58h+arg_10]
0x18007d289  mov     rsi, [rsp+58h+arg_18]
0x18007d28e  add     rsp, 50h
0x18007d292  pop     rdi
0x18007d293  retn
```
