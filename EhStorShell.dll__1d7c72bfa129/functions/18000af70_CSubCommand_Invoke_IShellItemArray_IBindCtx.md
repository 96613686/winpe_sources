# CSubCommand::Invoke(IShellItemArray *,IBindCtx *)

- ea: `0x18000af70`
- end: `0x18000af80`
- name: `?Invoke@CSubCommand@@UEAAJPEAUIShellItemArray@@PEAUIBindCtx@@@Z`
- size: `16`
- prototype: `__int64 __fastcall(CSubCommand *__hidden this, struct IShellItemArray *, struct IBindCtx *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000c010`

## pseudocode

```c
__int64 __fastcall CSubCommand::Invoke(CSubCommand *this, struct IShellItemArray *a2, struct IBindCtx *a3)
{
  return (*(__int64 (__fastcall **)(_QWORD, struct IShellItemArray *, struct IBindCtx *))(**((_QWORD **)this + 2) + 40LL))(
           *((_QWORD *)this + 2),
           a2,
           a3);
}

```

## disassembly

```asm
0x18000af70  mov     rcx, [rcx+10h]
0x18000af74  mov     rax, [rcx]
0x18000af77  mov     rax, [rax+28h]
0x18000af7b  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
