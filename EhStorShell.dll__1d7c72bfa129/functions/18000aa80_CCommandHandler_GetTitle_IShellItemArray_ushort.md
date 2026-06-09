# CCommandHandler::GetTitle(IShellItemArray *,ushort * *)

- ea: `0x18000aa80`
- end: `0x18000aa9a`
- name: `?GetTitle@CCommandHandler@@UEAAJPEAUIShellItemArray@@PEAPEAG@Z`
- size: `26`
- prototype: `__int64 __fastcall(CCommandHandler *this, struct IShellItemArray *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000af88`

## pseudocode

```c
__int64 __fastcall CCommandHandler::GetTitle(CCommandHandler *this, struct IShellItemArray *a2, unsigned __int16 **a3)
{
  return LoadStringFromResource(*(_DWORD *)&byte_18000D368[32 * *((int *)this + 16)], a3);
}

```

## disassembly

```asm
0x18000aa80  movsxd  rcx, dword ptr [rcx+40h]
0x18000aa84  lea     rax, byte_18000D368
0x18000aa8b  shl     rcx, 5
0x18000aa8f  mov     rdx, r8; ppwsz
0x18000aa92  mov     ecx, [rcx+rax]; uID
0x18000aa95  jmp     ?LoadStringFromResource@@YAJIPEAPEAG@Z; LoadStringFromResource(uint,ushort * *)
```
