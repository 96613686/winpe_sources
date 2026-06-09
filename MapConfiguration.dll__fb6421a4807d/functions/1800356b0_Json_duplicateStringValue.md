# Json::duplicateStringValue

- ea: `0x1800356b0`
- end: `0x180035748`
- name: `Json::duplicateStringValue`
- size: `152`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180034014`
- `0x180035e5c`

## callees

- `0x1800094a0`
- `0x18000b215`
- `0x18002ccd0`
- `0x1800356b0`
- `0x180036128`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800356e9`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800356e9`

## string_xrefs

- `0x1800356f7`: `in Json::Value::duplicateStringValue(): Failed to allocate string value buffer`

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
    std::string::string(
      (__int64)v8,
      (__int64)"in Json::Value::duplicateStringValue(): Failed to allocate string value buffer");
    Json::throwRuntimeError(v8);
  }
  memcpy_0(v5, Src, v4);
  *(_WORD *)&v6[v4] = 0;
  return v6;
}

```

## disassembly

```asm
0x1800356b0  mov     [rsp+arg_10], rbx
0x1800356b5  mov     [rsp+arg_18], rsi
0x1800356ba  push    rdi
0x1800356bb  sub     rsp, 50h
0x1800356bf  mov     rax, cs:__security_cookie
0x1800356c6  xor     rax, rsp
0x1800356c9  mov     [rsp+58h+var_18], rax
0x1800356ce  mov     rsi, rcx
0x1800356d1  mov     eax, 7FFFFFFEh
0x1800356d6  cmp     rdx, 7FFFFFFFh
0x1800356dd  cmovb   rax, rdx
0x1800356e1  lea     rdi, [rax+rax]
0x1800356e5  lea     rcx, [rdi+2]; Size
0x1800356e9  call    cs:__imp_malloc
0x1800356ef  mov     rbx, rax
0x1800356f2  test    rax, rax
0x1800356f5  jnz     short loc_180035714
0x1800356f7  lea     rdx, aInJsonValueDup_1; "in Json::Value::duplicateStringValue():"...
0x1800356fe  lea     rcx, [rsp+58h+var_38]
0x180035703  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180035708  nop
0x180035709  lea     rcx, [rsp+58h+var_38]
0x18003570e  call    ?throwRuntimeError@Json@@YAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Json::throwRuntimeError(std::string const &)
0x180035714  mov     r8, rdi; Size
0x180035717  mov     rdx, rsi; Src
0x18003571a  mov     rcx, rbx; void *
0x18003571d  call    memcpy_0
0x180035722  xor     eax, eax
0x180035724  mov     [rdi+rbx], ax
0x180035728  mov     rax, rbx
0x18003572b  mov     rcx, [rsp+58h+var_18]
0x180035730  xor     rcx, rsp; StackCookie
0x180035733  call    __security_check_cookie
0x180035738  mov     rbx, [rsp+58h+arg_10]
0x18003573d  mov     rsi, [rsp+58h+arg_18]
0x180035742  add     rsp, 50h
0x180035746  pop     rdi
0x180035747  retn
```
