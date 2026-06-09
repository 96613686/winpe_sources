# _CMDMPushConfiguration::CreatePushLaunchSchedule_::_1_::dtor$13

- ea: `0x140019a8f`
- end: `0x140019a9b`
- name: `_CMDMPushConfiguration::CreatePushLaunchSchedule_::_1_::dtor$13`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x14000928c`

## pseudocode

```c
void __fastcall CMDMPushConfiguration::CreatePushLaunchSchedule_::_1_::dtor_13(__int64 a1, __int64 a2)
{
  ATL::CComSafeArray<unsigned char,17>::~CComSafeArray<unsigned char,17>((SAFEARRAY **)(a2 + 96));
}

```

## disassembly

```asm
0x140019a8f  lea     rcx, [rdx+60h]
0x140019a96  jmp     ??1?$CComSafeArray@E$0BB@@ATL@@QEAA@XZ; ATL::CComSafeArray<uchar,17>::~CComSafeArray<uchar,17>(void)
```
