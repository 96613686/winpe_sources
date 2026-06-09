# Microsoft::WRL::Module<1,Windows::Internal::ServiceModule>::UnregisterCOMObject(ushort const *,ulong *,uint)

- ea: `0x180002690`
- end: `0x1800026ab`
- name: `?UnregisterCOMObject@?$Module@$00VServiceModule@Internal@Windows@@@WRL@Microsoft@@UEAAJPEBGPEAKI@Z`
- size: `27`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000d180`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000269b`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000269b`

## pseudocode

```c
__int64 Microsoft::WRL::Module<1,Windows::Internal::ServiceModule>::UnregisterCOMObject()
{
  RoOriginateError(2147500033LL, 0);
  return 2147500033LL;
}

```

## disassembly

```asm
0x180002690  sub     rsp, 28h
0x180002694  xor     edx, edx
0x180002696  mov     ecx, 80004001h
0x18000269b  call    cs:__imp_RoOriginateError
0x1800026a1  mov     eax, 80004001h
0x1800026a6  add     rsp, 28h
0x1800026aa  retn
```
