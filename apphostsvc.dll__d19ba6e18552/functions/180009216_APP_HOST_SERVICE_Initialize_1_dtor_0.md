# _APP_HOST_SERVICE::Initialize_::_1_::dtor$0

- ea: `0x180009216`
- end: `0x180009222`
- name: `_APP_HOST_SERVICE::Initialize_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, service_task`

## callees

- `0x180001048`

## pseudocode

```c
void __fastcall APP_HOST_SERVICE::Initialize_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 32));
}

```

## disassembly

```asm
0x180009216  mov     rcx, [rdx+20h]; Block
0x18000921d  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
