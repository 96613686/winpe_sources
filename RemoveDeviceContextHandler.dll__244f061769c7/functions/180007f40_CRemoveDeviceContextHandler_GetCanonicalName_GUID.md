# CRemoveDeviceContextHandler::GetCanonicalName(_GUID *)

- ea: `0x180007f40`
- end: `0x180007f4e`
- name: `?GetCanonicalName@CRemoveDeviceContextHandler@@UEAAJPEAU_GUID@@@Z`
- size: `14`
- prototype: `__int64 __fastcall(CRemoveDeviceContextHandler *__hidden this, struct _GUID *)`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## pseudocode

```c
__int64 __fastcall CRemoveDeviceContextHandler::GetCanonicalName(CRemoveDeviceContextHandler *this, struct _GUID *a2)
{
  __int64 result; // rax

  result = 0;
  *a2 = GUID_RemoveDeviceCommand;
  return result;
}

```

## disassembly

```asm
0x180007f40  movups  xmm0, xmmword ptr cs:GUID_RemoveDeviceCommand.Data1
0x180007f47  xor     eax, eax
0x180007f49  movdqu  xmmword ptr [rdx], xmm0
0x180007f4d  retn
```
