# _MsiSIPVerifyIndirectData_::_1_::dtor$6

- ea: `0x18000d4b0`
- end: `0x18000d4bc`
- name: `_MsiSIPVerifyIndirectData_::_1_::dtor$6`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180003340`

## pseudocode

```c
__int64 __fastcall MsiSIPVerifyIndirectData_::_1_::dtor_6(__int64 a1, __int64 a2)
{
  return CComPointer<IStream>::~CComPointer<IStream>((__int64 *)(a2 + 96));
}

```

## disassembly

```asm
0x18000d4b0  lea     rcx, [rdx+60h]
0x18000d4b7  jmp     ??1?$CComPointer@UIStream@@@@QEAA@XZ; CComPointer<IStream>::~CComPointer<IStream>(void)
```
