# _CMDMPushConfiguration::CreatePushLaunchSchedule_::_1_::dtor$12

- ea: `0x140018d1c`
- end: `0x140018d28`
- name: `_CMDMPushConfiguration::CreatePushLaunchSchedule_::_1_::dtor$12`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140008e6c`

## pseudocode

```c
void __fastcall CMDMPushConfiguration::CreatePushLaunchSchedule_::_1_::dtor_12(__int64 a1, __int64 a2)
{
  ATL::CComSafeArray<unsigned char,17>::~CComSafeArray<unsigned char,17>((SAFEARRAY **)(a2 + 88));
}

```

## disassembly

```asm
0x140018d1c  lea     rcx, [rdx+58h]
0x140018d23  jmp     ??1?$CComSafeArray@E$0BB@@ATL@@QEAA@XZ; ATL::CComSafeArray<uchar,17>::~CComSafeArray<uchar,17>(void)
```
