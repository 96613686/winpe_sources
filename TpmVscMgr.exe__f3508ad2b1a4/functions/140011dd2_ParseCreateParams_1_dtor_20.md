# _ParseCreateParams_::_1_::dtor$20

- ea: `0x140011dd2`
- end: `0x140011dde`
- name: `_ParseCreateParams_::_1_::dtor$20`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140008454`

## pseudocode

```c
void __fastcall ParseCreateParams_::_1_::dtor_20(__int64 a1, __int64 a2)
{
  errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(a2 + 96, a2);
}

```

## disassembly

```asm
0x140011dd2  lea     rcx, [rdx+60h]
0x140011dd9  jmp     ??1?$scoped_error@Utag@winerror_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(void)
```
