# CSubCommand::GetToolTip(IShellItemArray *,ushort * *)

- ea: `0x18000ab90`
- end: `0x18000aba3`
- name: `?GetToolTip@CSubCommand@@UEAAJPEAUIShellItemArray@@PEAPEAG@Z`
- size: `19`
- prototype: `__int64 __fastcall(CSubCommand *__hidden this, struct IShellItemArray *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000c010`

## pseudocode

```c
__int64 __fastcall CSubCommand::GetToolTip(CSubCommand *this, struct IShellItemArray *a2, unsigned __int16 **a3)
{
  return (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 **))(**((_QWORD **)this + 2) + 32LL))(
           *((_QWORD *)this + 2),
           a3);
}

```

## disassembly

```asm
0x18000ab90  mov     rcx, [rcx+10h]
0x18000ab94  mov     rdx, r8
0x18000ab97  mov     rax, [rcx]
0x18000ab9a  mov     rax, [rax+20h]
0x18000ab9e  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
