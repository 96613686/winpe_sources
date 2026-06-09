# DiagHubCommon::Logger::Logger(DiagHubCommon::LogStream,DiagHubCommon::LogStream,DiagHubCommon::LogStream,DiagHubCommon::LogStream,DiagHubCommon::LogStream)

- ea: `0x14000a298`
- end: `0x14000a40c`
- name: `??0Logger@DiagHubCommon@@AEAA@VLogStream@1@0000@Z`
- size: `372`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000a42c`

## callees

- `0x140003010`
- `0x14000b824`
- `0x14000b990`
- `0x14000d484`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 *__fastcall DiagHubCommon::Logger::Logger(
        __int64 *a1,
        _QWORD *a2,
        _QWORD *a3,
        _QWORD *a4,
        _QWORD *a5,
        _QWORD *a6)
{
  __int64 v10; // r8
  __int64 v11; // r8
  __int64 v12; // r8
  __int64 v13; // r8

  std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>(
    a1,
    a2,
    (__int64)a3);
  std::wstring::wstring(a1 + 3, a2 + 3);
  std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>(
    a1 + 7,
    a3,
    v10);
  std::wstring::wstring(a1 + 10, a3 + 3);
  std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>(
    a1 + 14,
    a4,
    v11);
  std::wstring::wstring(a1 + 17, a4 + 3);
  std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>(
    a1 + 21,
    a5,
    v12);
  std::wstring::wstring(a1 + 24, a5 + 3);
  std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>(
    a1 + 28,
    a6,
    v13);
  std::wstring::wstring(a1 + 31, a6 + 3);
  std::wstring::~wstring(a2 + 3);
  std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::_Tidy(a2);
  std::wstring::~wstring(a3 + 3);
  std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::_Tidy(a3);
  std::wstring::~wstring(a4 + 3);
  std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::_Tidy(a4);
  std::wstring::~wstring(a5 + 3);
  std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::_Tidy(a5);
  std::wstring::~wstring(a6 + 3);
  std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::_Tidy(a6);
  return a1;
}

```

## disassembly

```asm
0x14000a298  mov     rax, rsp
0x14000a29b  mov     [rax+20h], r9
0x14000a29f  mov     [rax+18h], r8
0x14000a2a3  mov     [rax+10h], rdx
0x14000a2a7  mov     [rax+8], rcx
0x14000a2ab  push    rbx
0x14000a2ac  push    rbp
0x14000a2ad  push    rsi
0x14000a2ae  push    rdi
0x14000a2af  push    r12
0x14000a2b1  push    r13
0x14000a2b3  push    r14
0x14000a2b5  push    r15
0x14000a2b7  sub     rsp, 38h
0x14000a2bb  mov     rsi, r9
0x14000a2be  mov     rdi, r8
0x14000a2c1  mov     r13, rdx
0x14000a2c4  mov     rbp, rcx
0x14000a2c7  mov     [rax-58h], rcx
0x14000a2cb  call    ??0?$vector@V?$shared_ptr@VILogWriter@DiagHubCommon@@@std@@V?$allocator@V?$shared_ptr@VILogWriter@DiagHubCommon@@@std@@@2@@std@@QEAA@AEBV01@@Z; std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>(std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>> const &)
0x14000a2d0  nop
0x14000a2d1  lea     rcx, [rbp+18h]
0x14000a2d5  lea     rdx, [r13+18h]
0x14000a2d9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14000a2de  nop
0x14000a2df  lea     rbx, [rbp+38h]
0x14000a2e3  mov     [rsp+78h+var_58], rbx
0x14000a2e8  mov     rdx, rdi
0x14000a2eb  mov     rcx, rbx
0x14000a2ee  call    ??0?$vector@V?$shared_ptr@VILogWriter@DiagHubCommon@@@std@@V?$allocator@V?$shared_ptr@VILogWriter@DiagHubCommon@@@std@@@2@@std@@QEAA@AEBV01@@Z; std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>(std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>> const &)
0x14000a2f3  nop
0x14000a2f4  lea     rcx, [rbx+18h]
0x14000a2f8  lea     rdx, [rdi+18h]
0x14000a2fc  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14000a301  nop
0x14000a302  lea     rbx, [rbp+70h]
0x14000a306  mov     [rsp+78h+var_58], rbx
0x14000a30b  mov     rdx, rsi
0x14000a30e  mov     rcx, rbx
0x14000a311  call    ??0?$vector@V?$shared_ptr@VILogWriter@DiagHubCommon@@@std@@V?$allocator@V?$shared_ptr@VILogWriter@DiagHubCommon@@@std@@@2@@std@@QEAA@AEBV01@@Z; std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>(std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>> const &)
0x14000a316  nop
0x14000a317  lea     r15, [rsi+18h]
0x14000a31b  lea     rcx, [rbx+18h]
0x14000a31f  mov     rdx, r15
0x14000a322  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14000a327  nop
0x14000a328  lea     rbx, [rbp+0A8h]
0x14000a32f  mov     [rsp+78h+var_58], rbx
0x14000a334  mov     r14, [rsp+78h+arg_20]
0x14000a33c  mov     rdx, r14
0x14000a33f  mov     rcx, rbx
0x14000a342  call    ??0?$vector@V?$shared_ptr@VILogWriter@DiagHubCommon@@@std@@V?$allocator@V?$shared_ptr@VILogWriter@DiagHubCommon@@@std@@@2@@std@@QEAA@AEBV01@@Z; std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>(std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>> const &)
0x14000a347  nop
0x14000a348  lea     rcx, [rbx+18h]
0x14000a34c  lea     rdx, [r14+18h]
0x14000a350  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14000a355  nop
0x14000a356  mov     rbx, [rsp+78h+arg_0]
0x14000a35e  add     rbx, 0E0h
0x14000a365  mov     [rsp+78h+var_58], rbx
0x14000a36a  mov     rsi, [rsp+78h+arg_28]
0x14000a372  mov     rdx, rsi
0x14000a375  mov     rcx, rbx
0x14000a378  call    ??0?$vector@V?$shared_ptr@VILogWriter@DiagHubCommon@@@std@@V?$allocator@V?$shared_ptr@VILogWriter@DiagHubCommon@@@std@@@2@@std@@QEAA@AEBV01@@Z; std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>(std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>> const &)
0x14000a37d  nop
0x14000a37e  lea     rcx, [rbx+18h]
0x14000a382  lea     rdx, [rsi+18h]
0x14000a386  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14000a38b  nop
0x14000a38c  lea     rcx, [r13+18h]
0x14000a390  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000a395  mov     rcx, [rsp+78h+arg_8]
0x14000a39d  call    ?_Tidy@?$vector@V?$shared_ptr@VILogWriter@DiagHubCommon@@@std@@V?$allocator@V?$shared_ptr@VILogWriter@DiagHubCommon@@@std@@@2@@std@@AEAAXXZ; std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::_Tidy(void)
0x14000a3a2  nop
0x14000a3a3  lea     rcx, [rdi+18h]
0x14000a3a7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000a3ac  mov     rcx, [rsp+78h+arg_10]
0x14000a3b4  call    ?_Tidy@?$vector@V?$shared_ptr@VILogWriter@DiagHubCommon@@@std@@V?$allocator@V?$shared_ptr@VILogWriter@DiagHubCommon@@@std@@@2@@std@@AEAAXXZ; std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::_Tidy(void)
0x14000a3b9  nop
0x14000a3ba  mov     rcx, r15
0x14000a3bd  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000a3c2  mov     rcx, [rsp+78h+arg_18]
0x14000a3ca  call    ?_Tidy@?$vector@V?$shared_ptr@VILogWriter@DiagHubCommon@@@std@@V?$allocator@V?$shared_ptr@VILogWriter@DiagHubCommon@@@std@@@2@@std@@AEAAXXZ; std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::_Tidy(void)
0x14000a3cf  nop
0x14000a3d0  lea     rcx, [r14+18h]
0x14000a3d4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000a3d9  mov     rcx, r14
0x14000a3dc  call    ?_Tidy@?$vector@V?$shared_ptr@VILogWriter@DiagHubCommon@@@std@@V?$allocator@V?$shared_ptr@VILogWriter@DiagHubCommon@@@std@@@2@@std@@AEAAXXZ; std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::_Tidy(void)
0x14000a3e1  nop
0x14000a3e2  lea     rcx, [rsi+18h]
0x14000a3e6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000a3eb  mov     rcx, rsi
0x14000a3ee  call    ?_Tidy@?$vector@V?$shared_ptr@VILogWriter@DiagHubCommon@@@std@@V?$allocator@V?$shared_ptr@VILogWriter@DiagHubCommon@@@std@@@2@@std@@AEAAXXZ; std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::_Tidy(void)
0x14000a3f3  mov     rax, [rsp+78h+arg_0]
0x14000a3fb  add     rsp, 38h
0x14000a3ff  pop     r15
0x14000a401  pop     r14
0x14000a403  pop     r13
0x14000a405  pop     r12
0x14000a407  pop     rdi
0x14000a408  pop     rsi
0x14000a409  pop     rbp
0x14000a40a  pop     rbx
0x14000a40b  retn
```
