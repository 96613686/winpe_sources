# Microsoft::WRL::ActivationFactory<Windows::Internal::ISecurityMitigationsBrokerStatics,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::ActivateInstance(IInspectable * *)

- ea: `0x180003790`
- end: `0x1800037b2`
- name: `?ActivateInstance@?$ActivationFactory@UISecurityMitigationsBrokerStatics@Internal@Windows@@VNil@Details@WRL@Microsoft@@V4567@$0A@@WRL@Microsoft@@UEAAJPEAPEAUIInspectable@@@Z`
- size: `34`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800037a2`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800037a2`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ActivationFactory<Windows::Internal::ISecurityMitigationsBrokerStatics,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::ActivateInstance(
        __int64 a1,
        _QWORD *a2)
{
  *a2 = 0;
  RoOriginateError(2147500033LL, 0);
  return 2147500033LL;
}

```

## disassembly

```asm
0x180003790  sub     rsp, 28h
0x180003794  mov     qword ptr [rdx], 0
0x18000379b  mov     ecx, 80004001h
0x1800037a0  xor     edx, edx
0x1800037a2  call    cs:__imp_RoOriginateError
0x1800037a8  mov     eax, 80004001h
0x1800037ad  add     rsp, 28h
0x1800037b1  retn
```
