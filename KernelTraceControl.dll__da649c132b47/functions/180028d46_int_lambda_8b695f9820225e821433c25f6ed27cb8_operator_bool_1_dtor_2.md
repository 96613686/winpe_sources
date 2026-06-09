# int `_lambda_8b695f9820225e821433c25f6ed27cb8_::operator()(bool)'::`1'::dtor$2

- ea: `0x180028d46`
- end: `0x180028d52`
- name: `?dtor$2@?0???R_lambda_8b695f9820225e821433c25f6ed27cb8_@@QEBA?AV?$task@_N@Concurrency@@_N@Z@4HA_0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180005dc0`

## pseudocode

```c
void __fastcall `_lambda_8b695f9820225e821433c25f6ed27cb8_::operator()'::`1'::dtor$2(__int64 a1, __int64 a2)
{
  Microsoft::Windows::Performance::CEventTraceExtenderBase::~CEventTraceExtenderBase(*(Microsoft::Windows::Performance::CEventTraceExtenderBase **)(a2 + 120));
}

```

## disassembly

```asm
0x180028d46  mov     rcx, [rdx+78h]; this
0x180028d4d  jmp     ??1CEventTraceExtenderBase@Performance@Windows@Microsoft@@QEAA@XZ
```
