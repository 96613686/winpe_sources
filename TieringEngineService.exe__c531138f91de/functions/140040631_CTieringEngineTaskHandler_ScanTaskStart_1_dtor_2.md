# _CTieringEngineTaskHandler::ScanTaskStart_::_1_::dtor$2

- ea: `0x140040631`
- end: `0x14004063d`
- name: `_CTieringEngineTaskHandler::ScanTaskStart_::_1_::dtor$2`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1400374e8`

## pseudocode

```c
__int64 __fastcall CTieringEngineTaskHandler::ScanTaskStart_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  return ATL::CComQIPtr<ITaskHandlerStatus,&__s_GUID const _GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a>::~CComQIPtr<ITaskHandlerStatus,&__s_GUID const _GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a>((__int64 *)(a2 + 48));
}

```

## disassembly

```asm
0x140040631  lea     rcx, [rdx+30h]
0x140040638  jmp     ??1?$CComQIPtr@UITaskHandlerStatus@@$1?_GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a@@3U__s_GUID@@B@ATL@@QEAA@XZ; ATL::CComQIPtr<ITaskHandlerStatus,&__s_GUID const _GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a>::~CComQIPtr<ITaskHandlerStatus,&__s_GUID const _GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a>(void)
```
