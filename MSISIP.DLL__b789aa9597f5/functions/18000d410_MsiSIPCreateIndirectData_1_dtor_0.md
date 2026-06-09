# _MsiSIPCreateIndirectData_::_1_::dtor$0

- ea: `0x18000d410`
- end: `0x18000d41c`
- name: `_MsiSIPCreateIndirectData_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180003340`

## pseudocode

```c
__int64 __fastcall MsiSIPCreateIndirectData_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return CComPointer<IStream>::~CComPointer<IStream>((__int64 *)(a2 + 104));
}

```

## disassembly

```asm
0x18000d410  lea     rcx, [rdx+68h]
0x18000d417  jmp     ??1?$CComPointer@UIStream@@@@QEAA@XZ; CComPointer<IStream>::~CComPointer<IStream>(void)
```
