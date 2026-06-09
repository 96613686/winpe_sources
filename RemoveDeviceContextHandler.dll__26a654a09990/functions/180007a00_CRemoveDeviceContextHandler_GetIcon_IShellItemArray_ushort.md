# CRemoveDeviceContextHandler::GetIcon(IShellItemArray *,ushort * *)

- ea: `0x180007a00`
- end: `0x180007a06`
- name: `?GetIcon@CRemoveDeviceContextHandler@@UEAAJPEAUIShellItemArray@@PEAPEAG@Z`
- size: `6`
- prototype: `__int64 __fastcall(CRemoveDeviceContextHandler *__hidden this, struct IShellItemArray *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## pseudocode

```c
__int64 __fastcall CRemoveDeviceContextHandler::GetIcon(
        CRemoveDeviceContextHandler *this,
        struct IShellItemArray *a2,
        unsigned __int16 **a3)
{
  return 2147500033LL;
}

```

## disassembly

```asm
0x180007a00  mov     eax, 80004001h
0x180007a05  retn
```
