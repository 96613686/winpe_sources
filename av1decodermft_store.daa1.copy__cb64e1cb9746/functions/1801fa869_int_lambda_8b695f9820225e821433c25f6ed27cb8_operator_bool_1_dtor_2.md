# int `_lambda_8b695f9820225e821433c25f6ed27cb8_::operator()(bool)'::`1'::dtor$2

- ea: `0x1801fa869`
- end: `0x1801fa875`
- name: `?dtor$2@?0???R_lambda_8b695f9820225e821433c25f6ed27cb8_@@QEBA?AV?$task@_N@Concurrency@@_N@Z@4HA`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18012d6b0`

## pseudocode

```c
__int64 __fastcall `_lambda_8b695f9820225e821433c25f6ed27cb8_::operator()'::`1'::dtor$2(__int64 a1, __int64 a2)
{
  return sub_18012D6B0(*(_QWORD *)(a2 + 120));
}

```

## disassembly

```asm
0x1801fa869  mov     rcx, [rdx+78h]
0x1801fa870  jmp     sub_18012D6B0
```
