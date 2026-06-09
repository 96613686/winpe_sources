# CCommandHandler::GetToolTip(IShellItemArray *,ushort * *)

- ea: `0x18000ab70`
- end: `0x18000ab8a`
- name: `?GetToolTip@CCommandHandler@@UEAAJPEAUIShellItemArray@@PEAPEAG@Z`
- size: `26`
- prototype: `__int64 __fastcall(CCommandHandler *this, struct IShellItemArray *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000af88`

## pseudocode

```c
__int64 __fastcall CCommandHandler::GetToolTip(
        CCommandHandler *this,
        struct IShellItemArray *a2,
        unsigned __int16 **a3)
{
  return LoadStringFromResource(dword_18000D36C[8 * *((int *)this + 16)], a3);
}

```

## disassembly

```asm
0x18000ab70  movsxd  rcx, dword ptr [rcx+40h]
0x18000ab74  lea     rax, dword_18000D36C
0x18000ab7b  shl     rcx, 5
0x18000ab7f  mov     rdx, r8; ppwsz
0x18000ab82  mov     ecx, [rcx+rax]; uID
0x18000ab85  jmp     ?LoadStringFromResource@@YAJIPEAPEAG@Z; LoadStringFromResource(uint,ushort * *)
```
