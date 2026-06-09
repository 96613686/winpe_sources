# _RpcClientMonitorThread_::_1_::dtor$0

- ea: `0x1400121b4`
- end: `0x1400121c0`
- name: `_RpcClientMonitorThread_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140004670`

## pseudocode

```c
void __fastcall RpcClientMonitorThread_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  std::wstring::~wstring((char **)(a2 + 64));
}

```

## disassembly

```asm
0x1400121b4  lea     rcx, [rdx+40h]; void *
0x1400121bb  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
