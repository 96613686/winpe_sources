# CCommandHandler::GetIcon(IShellItemArray *,ushort * *)

- ea: `0x18000aa20`
- end: `0x18000aa3d`
- name: `?GetIcon@CCommandHandler@@UEAAJPEAUIShellItemArray@@PEAPEAG@Z`
- size: `29`
- prototype: `HRESULT __fastcall(CCommandHandler *this, struct IShellItemArray *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## import_xrefs

- `SHLWAPI!SHStrDupW` at `0x18000aa36`

## pseudocode

```c
HRESULT __fastcall CCommandHandler::GetIcon(CCommandHandler *this, struct IShellItemArray *a2, unsigned __int16 **a3)
{
  return SHStrDupW((LPCWSTR)(&off_18000D370)[4 * *((int *)this + 16)], a3);
}

```

## disassembly

```asm
0x18000aa20  movsxd  rcx, dword ptr [rcx+40h]
0x18000aa24  lea     rax, off_18000D370
0x18000aa2b  shl     rcx, 5
0x18000aa2f  mov     rdx, r8
0x18000aa32  mov     rcx, [rcx+rax]
0x18000aa36  jmp     cs:__imp_SHStrDupW
```
