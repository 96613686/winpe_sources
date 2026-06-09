# _Concurrency::task_void_::task_void___lambda_5a3b4c8fbc070cd6d2fcfe17e4a62358____::_1_::dtor$2

- ea: `0x180017e22`
- end: `0x180017e2e`
- name: `_Concurrency::task_void_::task_void___lambda_5a3b4c8fbc070cd6d2fcfe17e4a62358____::_1_::dtor$2`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x1800100e8`

## pseudocode

```c
void __fastcall Concurrency::task_void_::task_void___lambda_5a3b4c8fbc070cd6d2fcfe17e4a62358____::_1_::dtor_2(
        __int64 a1,
        __int64 a2)
{
  Concurrency::cancellation_token::~cancellation_token((volatile signed __int32 **)(a2 + 216));
}

```

## disassembly

```asm
0x180017e22  lea     rcx, [rdx+0D8h]; this
0x180017e29  jmp     ??1cancellation_token@Concurrency@@QEAA@XZ; Concurrency::cancellation_token::~cancellation_token(void)
```
