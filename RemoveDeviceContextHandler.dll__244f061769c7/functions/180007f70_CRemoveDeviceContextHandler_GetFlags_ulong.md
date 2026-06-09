# CRemoveDeviceContextHandler::GetFlags(ulong *)

- ea: `0x180007f70`
- end: `0x180007f79`
- name: `?GetFlags@CRemoveDeviceContextHandler@@UEAAJPEAK@Z`
- size: `9`
- prototype: `__int64 __fastcall(CRemoveDeviceContextHandler *__hidden this, unsigned int *)`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## pseudocode

```c
__int64 __fastcall CRemoveDeviceContextHandler::GetFlags(CRemoveDeviceContextHandler *this, unsigned int *a2)
{
  *a2 = 16;
  return 0;
}

```

## disassembly

```asm
0x180007f70  mov     dword ptr [rdx], 10h
0x180007f76  xor     eax, eax
0x180007f78  retn
```
