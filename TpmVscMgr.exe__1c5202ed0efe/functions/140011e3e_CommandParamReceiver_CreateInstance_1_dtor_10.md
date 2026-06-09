# _CommandParamReceiver::CreateInstance_::_1_::dtor$10

- ea: `0x140011e3e`
- end: `0x140011e4a`
- name: `_CommandParamReceiver::CreateInstance_::_1_::dtor$10`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140008454`

## pseudocode

```c
void __fastcall CommandParamReceiver::CreateInstance_::_1_::dtor_10(__int64 a1, __int64 a2)
{
  errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(a2 + 120, a2);
}

```

## disassembly

```asm
0x140011e3e  lea     rcx, [rdx+78h]
0x140011e45  jmp     ??1?$scoped_error@Utag@winerror_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(void)
```
