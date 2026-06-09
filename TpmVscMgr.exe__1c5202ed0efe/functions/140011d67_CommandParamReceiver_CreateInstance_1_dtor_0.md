# _CommandParamReceiver::CreateInstance_::_1_::dtor$0

- ea: `0x140011d67`
- end: `0x140011d73`
- name: `_CommandParamReceiver::CreateInstance_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140008454`

## pseudocode

```c
void __fastcall CommandParamReceiver::CreateInstance_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(a2 + 104, a2);
}

```

## disassembly

```asm
0x140011d67  lea     rcx, [rdx+68h]
0x140011d6e  jmp     ??1?$scoped_error@Utag@winerror_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(void)
```
