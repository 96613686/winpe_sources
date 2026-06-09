# DiagHubCommon::Logger::~Logger(void)

- ea: `0x14000d7fc`
- end: `0x14000d87b`
- name: `??1Logger@DiagHubCommon@@QEAA@XZ`
- size: `127`
- prototype: `void __fastcall(DiagHubCommon::Logger *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000a42c`
- `0x14000f810`
- `0x140010a04`
- `0x140015c10`

## callees

- `0x140003010`
- `0x14000d484`

## pseudocode

```c
void __fastcall DiagHubCommon::Logger::~Logger(DiagHubCommon::Logger *this)
{
  _QWORD *v1; // rbx

  v1 = (_QWORD *)((char *)this + 224);
  std::wstring::~wstring((char *)this + 248);
  std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::_Tidy(v1);
  std::wstring::~wstring((char *)this + 192);
  std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::_Tidy((_QWORD *)this + 21);
  std::wstring::~wstring((char *)this + 136);
  std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::_Tidy((_QWORD *)this + 14);
  std::wstring::~wstring((char *)this + 80);
  std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::_Tidy((_QWORD *)this + 7);
  std::wstring::~wstring((char *)this + 24);
  std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::_Tidy(this);
}

```

## disassembly

```asm
0x14000d7fc  mov     [rsp+arg_0], rbx
0x14000d801  push    rdi
0x14000d802  sub     rsp, 20h
0x14000d806  lea     rbx, [rcx+0E0h]
0x14000d80d  mov     rdi, rcx
0x14000d810  lea     rcx, [rbx+18h]
0x14000d814  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000d819  mov     rcx, rbx
0x14000d81c  call    ?_Tidy@?$vector@V?$shared_ptr@VILogWriter@DiagHubCommon@@@std@@V?$allocator@V?$shared_ptr@VILogWriter@DiagHubCommon@@@std@@@2@@std@@AEAAXXZ; std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::_Tidy(void)
0x14000d821  lea     rbx, [rdi+0A8h]
0x14000d828  lea     rcx, [rbx+18h]
0x14000d82c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000d831  mov     rcx, rbx
0x14000d834  call    ?_Tidy@?$vector@V?$shared_ptr@VILogWriter@DiagHubCommon@@@std@@V?$allocator@V?$shared_ptr@VILogWriter@DiagHubCommon@@@std@@@2@@std@@AEAAXXZ; std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::_Tidy(void)
0x14000d839  lea     rcx, [rdi+88h]
0x14000d840  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000d845  lea     rcx, [rdi+70h]
0x14000d849  call    ?_Tidy@?$vector@V?$shared_ptr@VILogWriter@DiagHubCommon@@@std@@V?$allocator@V?$shared_ptr@VILogWriter@DiagHubCommon@@@std@@@2@@std@@AEAAXXZ; std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::_Tidy(void)
0x14000d84e  lea     rcx, [rdi+50h]
0x14000d852  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000d857  lea     rcx, [rdi+38h]
0x14000d85b  call    ?_Tidy@?$vector@V?$shared_ptr@VILogWriter@DiagHubCommon@@@std@@V?$allocator@V?$shared_ptr@VILogWriter@DiagHubCommon@@@std@@@2@@std@@AEAAXXZ; std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::_Tidy(void)
0x14000d860  lea     rcx, [rdi+18h]
0x14000d864  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000d869  mov     rcx, rdi
0x14000d86c  mov     rbx, [rsp+28h+arg_0]
0x14000d871  add     rsp, 20h
0x14000d875  pop     rdi
0x14000d876  jmp     ?_Tidy@?$vector@V?$shared_ptr@VILogWriter@DiagHubCommon@@@std@@V?$allocator@V?$shared_ptr@VILogWriter@DiagHubCommon@@@std@@@2@@std@@AEAAXXZ; std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::_Tidy(void)
```
