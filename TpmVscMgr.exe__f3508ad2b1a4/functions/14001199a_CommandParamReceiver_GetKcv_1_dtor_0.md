# _CommandParamReceiver::GetKcv_::_1_::dtor$0

- ea: `0x14001199a`
- end: `0x1400119a6`
- name: `_CommandParamReceiver::GetKcv_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140008454`

## pseudocode

```c
void __fastcall CommandParamReceiver::GetKcv_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(a2 + 80, a2);
}

```

## disassembly

```asm
0x14001199a  lea     rcx, [rdx+50h]
0x1400119a1  jmp     ??1?$scoped_error@Utag@winerror_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(void)
```
