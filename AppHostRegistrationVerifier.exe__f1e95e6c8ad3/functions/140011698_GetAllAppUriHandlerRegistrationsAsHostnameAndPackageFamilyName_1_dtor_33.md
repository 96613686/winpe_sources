# _GetAllAppUriHandlerRegistrationsAsHostnameAndPackageFamilyName_::_1_::dtor$33

- ea: `0x140011698`
- end: `0x1400116a4`
- name: `_GetAllAppUriHandlerRegistrationsAsHostnameAndPackageFamilyName_::_1_::dtor$33`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14000a254`

## pseudocode

```c
void __fastcall GetAllAppUriHandlerRegistrationsAsHostnameAndPackageFamilyName_::_1_::dtor_33(__int64 a1, __int64 a2)
{
  AppUriHandlerRegistrationInfo::~AppUriHandlerRegistrationInfo((HSTRING *)(a2 + 176));
}

```

## disassembly

```asm
0x140011698  lea     rcx, [rdx+0B0h]; this
0x14001169f  jmp     ??1AppUriHandlerRegistrationInfo@@QEAA@XZ; AppUriHandlerRegistrationInfo::~AppUriHandlerRegistrationInfo(void)
```
