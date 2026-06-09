# _CommandParamReceiver::operator()_::_1_::dtor$0_0

- ea: `0x140011d31`
- end: `0x140011d3d`
- name: `_CommandParamReceiver::operator()_::_1_::dtor$0_0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140008454`

## pseudocode

```c
void __fastcall CommandParamReceiver::operator()_::_1_::dtor_0_0(__int64 a1, __int64 a2)
{
  errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(a2 + 160, a2);
}

```

## disassembly

```asm
0x140011d31  lea     rcx, [rdx+0A0h]
0x140011d38  jmp     ??1?$scoped_error@Utag@winerror_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(void)
```
