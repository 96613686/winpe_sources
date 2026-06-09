# DiagHubCommon::LogStream::~LogStream(void)

- ea: `0x14000a40c`
- end: `0x14000a42b`
- name: `??1LogStream@DiagHubCommon@@QEAA@XZ`
- size: `31`
- prototype: `void __fastcall(DiagHubCommon::LogStream *__hidden this)`
- caller_count: `17`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400152f6`
- `0x140015302`
- `0x14001530e`
- `0x14001531a`
- `0x140015326`
- `0x14001533e`
- `0x140015356`
- `0x140015372`
- `0x14001538e`
- `0x14001555f`
- `0x14001559b`
- `0x1400155d7`
- `0x140015613`
- `0x140015821`
- `0x140015839`
- `0x140015855`
- `0x140015871`

## callees

- `0x140003010`
- `0x14000d484`

## pseudocode

```c
void __fastcall DiagHubCommon::LogStream::~LogStream(DiagHubCommon::LogStream *this)
{
  std::wstring::~wstring((char *)this + 24);
  std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::_Tidy(this);
}

```

## disassembly

```asm
0x14000a40c  push    rbx
0x14000a40e  sub     rsp, 20h
0x14000a412  mov     rbx, rcx
0x14000a415  add     rcx, 18h
0x14000a419  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000a41e  mov     rcx, rbx
0x14000a421  add     rsp, 20h
0x14000a425  pop     rbx
0x14000a426  jmp     ?_Tidy@?$vector@V?$shared_ptr@VILogWriter@DiagHubCommon@@@std@@V?$allocator@V?$shared_ptr@VILogWriter@DiagHubCommon@@@std@@@2@@std@@AEAAXXZ; std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::_Tidy(void)
```
