# CShutdownPopupCommandHandler::Invoke(IPopupWindow *,IPopupCommand *)

- ea: `0x140008d80`
- end: `0x140008d99`
- name: `?Invoke@CShutdownPopupCommandHandler@@UEAAJPEAUIPopupWindow@@PEAUIPopupCommand@@@Z`
- size: `25`
- prototype: `__int64 __fastcall(CShutdownPopupCommandHandler *__hidden this, struct IPopupWindow *, struct IPopupCommand *)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14000a010`

## pseudocode

```c
__int64 __fastcall CShutdownPopupCommandHandler::Invoke(
        CShutdownPopupCommandHandler *this,
        struct IPopupWindow *a2,
        struct IPopupCommand *a3)
{
  return (*((__int64 (__fastcall **)(struct IPopupWindow *, struct IPopupCommand *, _QWORD))this + 2))(
           a2,
           a3,
           *((_QWORD *)this + 3));
}

```

## disassembly

```asm
0x140008d80  mov     rax, [rcx+10h]
0x140008d84  mov     r9, r8
0x140008d87  mov     r8, [rcx+18h]
0x140008d8b  mov     r10, rdx
0x140008d8e  mov     rdx, r9
0x140008d91  mov     rcx, r10
0x140008d94  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
