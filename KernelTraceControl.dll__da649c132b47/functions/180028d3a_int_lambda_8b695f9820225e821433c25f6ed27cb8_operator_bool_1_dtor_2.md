# int `_lambda_8b695f9820225e821433c25f6ed27cb8_::operator()(bool)'::`1'::dtor$2

- ea: `0x180028d3a`
- end: `0x180028d46`
- name: `?dtor$2@?0???R_lambda_8b695f9820225e821433c25f6ed27cb8_@@QEBA?AV?$task@_N@Concurrency@@_N@Z@4HA`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x1800268f4`

## pseudocode

```c
void __fastcall `_lambda_8b695f9820225e821433c25f6ed27cb8_::operator()'::`1'::dtor$2(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 120));
}

```

## disassembly

```asm
0x180028d3a  mov     rcx, [rdx+78h]; Block
0x180028d41  jmp     ??3@YAXPEAX@Z
```
