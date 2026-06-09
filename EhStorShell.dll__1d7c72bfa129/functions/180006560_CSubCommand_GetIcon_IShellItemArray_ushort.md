# CSubCommand::GetIcon(IShellItemArray *,ushort * *)

- ea: `0x180006560`
- end: `0x180006566`
- name: `?GetIcon@CSubCommand@@UEAAJPEAUIShellItemArray@@PEAPEAG@Z`
- size: `6`
- prototype: `__int64 __fastcall(CSubCommand *__hidden this, struct IShellItemArray *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 __fastcall CSubCommand::GetIcon(CSubCommand *this, struct IShellItemArray *a2, unsigned __int16 **a3)
{
  return 2147500033LL;
}

```

## disassembly

```asm
0x180006560  mov     eax, 80004001h
0x180006565  retn
```
