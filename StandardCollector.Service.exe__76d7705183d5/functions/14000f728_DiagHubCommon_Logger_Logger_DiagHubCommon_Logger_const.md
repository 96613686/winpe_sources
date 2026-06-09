# DiagHubCommon::Logger::Logger(DiagHubCommon::Logger const &)

- ea: `0x14000f728`
- end: `0x14000f80d`
- name: `??0Logger@DiagHubCommon@@QEAA@AEBV01@@Z`
- size: `229`
- prototype: `__int64 __fastcall(DiagHubCommon::Logger *__hidden this, const struct DiagHubCommon::Logger *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001388`
- `0x140005760`

## callees

- `0x14000b824`
- `0x14000b990`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
DiagHubCommon::Logger *__fastcall DiagHubCommon::Logger::Logger(
        DiagHubCommon::Logger *this,
        const struct DiagHubCommon::Logger *a2,
        __int64 a3)
{
  __int64 v5; // r8
  __int64 v6; // r8
  __int64 v7; // r8
  __int64 v8; // r8

  std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>(
    (__int64 *)this,
    a2,
    a3);
  std::wstring::wstring((char *)this + 24, (char *)a2 + 24);
  std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>(
    (__int64 *)this + 7,
    (_QWORD *)a2 + 7,
    v5);
  std::wstring::wstring((char *)this + 80, (char *)a2 + 80);
  std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>(
    (__int64 *)this + 14,
    (_QWORD *)a2 + 14,
    v6);
  std::wstring::wstring((char *)this + 136, (char *)a2 + 136);
  std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>(
    (__int64 *)this + 21,
    (_QWORD *)a2 + 21,
    v7);
  std::wstring::wstring((char *)this + 192, (char *)a2 + 192);
  std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>(
    (__int64 *)this + 28,
    (_QWORD *)a2 + 28,
    v8);
  std::wstring::wstring((char *)this + 248, (char *)a2 + 248);
  return this;
}

```

## disassembly

```asm
0x14000f728  mov     [rsp+arg_10], rbx
0x14000f72d  mov     [rsp+arg_0], rcx
0x14000f732  push    rbp
0x14000f733  push    rsi
0x14000f734  push    rdi
0x14000f735  sub     rsp, 20h
0x14000f739  mov     rsi, rdx
0x14000f73c  mov     rbp, rcx
0x14000f73f  mov     [rsp+38h+arg_8], rcx
0x14000f744  call    ??0?$vector@V?$shared_ptr@VILogWriter@DiagHubCommon@@@std@@V?$allocator@V?$shared_ptr@VILogWriter@DiagHubCommon@@@std@@@2@@std@@QEAA@AEBV01@@Z; std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>(std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>> const &)
0x14000f749  nop
0x14000f74a  lea     rdx, [rsi+18h]
0x14000f74e  lea     rcx, [rbp+18h]
0x14000f752  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14000f757  nop
0x14000f758  lea     rdi, [rbp+38h]
0x14000f75c  mov     [rsp+38h+arg_8], rdi
0x14000f761  lea     rdx, [rsi+38h]
0x14000f765  mov     rcx, rdi
0x14000f768  call    ??0?$vector@V?$shared_ptr@VILogWriter@DiagHubCommon@@@std@@V?$allocator@V?$shared_ptr@VILogWriter@DiagHubCommon@@@std@@@2@@std@@QEAA@AEBV01@@Z; std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>(std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>> const &)
0x14000f76d  nop
0x14000f76e  lea     rdx, [rsi+50h]
0x14000f772  lea     rcx, [rdi+18h]
0x14000f776  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14000f77b  nop
0x14000f77c  lea     rdi, [rbp+70h]
0x14000f780  mov     [rsp+38h+arg_8], rdi
0x14000f785  lea     rdx, [rsi+70h]
0x14000f789  mov     rcx, rdi
0x14000f78c  call    ??0?$vector@V?$shared_ptr@VILogWriter@DiagHubCommon@@@std@@V?$allocator@V?$shared_ptr@VILogWriter@DiagHubCommon@@@std@@@2@@std@@QEAA@AEBV01@@Z; std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>(std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>> const &)
0x14000f791  nop
0x14000f792  lea     rdx, [rsi+88h]
0x14000f799  lea     rcx, [rdi+18h]
0x14000f79d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14000f7a2  nop
0x14000f7a3  lea     rdi, [rbp+0A8h]
0x14000f7aa  mov     [rsp+38h+arg_8], rdi
0x14000f7af  lea     rbx, [rsi+0A8h]
0x14000f7b6  mov     rdx, rbx
0x14000f7b9  mov     rcx, rdi
0x14000f7bc  call    ??0?$vector@V?$shared_ptr@VILogWriter@DiagHubCommon@@@std@@V?$allocator@V?$shared_ptr@VILogWriter@DiagHubCommon@@@std@@@2@@std@@QEAA@AEBV01@@Z; std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>(std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>> const &)
0x14000f7c1  nop
0x14000f7c2  lea     rdx, [rbx+18h]
0x14000f7c6  lea     rcx, [rdi+18h]
0x14000f7ca  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14000f7cf  nop
0x14000f7d0  lea     rdi, [rbp+0E0h]
0x14000f7d7  mov     [rsp+38h+arg_8], rdi
0x14000f7dc  lea     rbx, [rsi+0E0h]
0x14000f7e3  mov     rdx, rbx
0x14000f7e6  mov     rcx, rdi
0x14000f7e9  call    ??0?$vector@V?$shared_ptr@VILogWriter@DiagHubCommon@@@std@@V?$allocator@V?$shared_ptr@VILogWriter@DiagHubCommon@@@std@@@2@@std@@QEAA@AEBV01@@Z; std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>(std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>> const &)
0x14000f7ee  nop
0x14000f7ef  lea     rdx, [rbx+18h]
0x14000f7f3  lea     rcx, [rdi+18h]
0x14000f7f7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14000f7fc  nop
0x14000f7fd  mov     rax, rbp
0x14000f800  mov     rbx, [rsp+38h+arg_10]
0x14000f805  add     rsp, 20h
0x14000f809  pop     rdi
0x14000f80a  pop     rsi
0x14000f80b  pop     rbp
0x14000f80c  retn
```
