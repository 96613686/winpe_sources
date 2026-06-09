# AutoScz::~AutoScz(void)

- ea: `0x140007040`
- end: `0x140007045`
- name: `??1AutoScz@@QEAA@XZ`
- size: `5`
- prototype: `void __fastcall(AutoScz *__hidden this)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x140029cd0`
- `0x140029ce2`
- `0x140029cf4`
- `0x140029d3c`
- `0x140029d4e`
- `0x140029d60`
- `0x140029dff`

## callees

- `0x14000726c`

## pseudocode

```c
// attributes: thunk
void __fastcall AutoScz::~AutoScz(_QWORD *this)
{
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(this);
}

```

## disassembly

```asm
0x140007040  jmp     ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
```
