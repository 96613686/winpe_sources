# _ParseCreateParams_::_1_::dtor$37

- ea: `0x14001207c`
- end: `0x140012088`
- name: `_ParseCreateParams_::_1_::dtor$37`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140008454`

## pseudocode

```c
void __fastcall ParseCreateParams_::_1_::dtor_37(__int64 a1, __int64 a2)
{
  errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(a2 + 72, a2);
}

```

## disassembly

```asm
0x14001207c  lea     rcx, [rdx+48h]
0x140012083  jmp     ??1?$scoped_error@Utag@winerror_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(void)
```
