# _dynamic_atexit_destructor_for__CRuntimeBroker::s_brokerAumid__

- ea: `0x14000f470`
- end: `0x14000f491`
- name: `_dynamic_atexit_destructor_for__CRuntimeBroker::s_brokerAumid__`
- size: `33`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000f47b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000f47b`

## pseudocode

```c
HRESULT dynamic_atexit_destructor_for__CRuntimeBroker::s_brokerAumid__()
{
  HRESULT result; // eax

  result = WindowsDeleteString(CRuntimeBroker::s_brokerAumid);
  CRuntimeBroker::s_brokerAumid = 0;
  return result;
}

```

## disassembly

```asm
0x14000f470  sub     rsp, 28h
0x14000f474  mov     rcx, cs:?s_brokerAumid@CRuntimeBroker@@2VHString@Wrappers@WRL@Microsoft@@A; string
0x14000f47b  call    cs:__imp_WindowsDeleteString
0x14000f481  mov     cs:?s_brokerAumid@CRuntimeBroker@@2VHString@Wrappers@WRL@Microsoft@@A, 0; Microsoft::WRL::Wrappers::HString CRuntimeBroker::s_brokerAumid
0x14000f48c  add     rsp, 28h
0x14000f490  retn
```
