# _MsiSIPPutSignedDataMsg_::_1_::dtor$0

- ea: `0x18000d430`
- end: `0x18000d43c`
- name: `_MsiSIPPutSignedDataMsg_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180003340`

## pseudocode

```c
__int64 __fastcall MsiSIPPutSignedDataMsg_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return CComPointer<IStream>::~CComPointer<IStream>((__int64 *)(a2 + 72));
}

```

## disassembly

```asm
0x18000d430  lea     rcx, [rdx+48h]
0x18000d437  jmp     ??1?$CComPointer@UIStream@@@@QEAA@XZ; CComPointer<IStream>::~CComPointer<IStream>(void)
```
