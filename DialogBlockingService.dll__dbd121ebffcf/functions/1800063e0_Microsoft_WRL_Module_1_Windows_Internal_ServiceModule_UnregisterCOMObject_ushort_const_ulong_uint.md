# Microsoft::WRL::Module<1,Windows::Internal::ServiceModule>::UnregisterCOMObject(ushort const *,ulong *,uint)

- ea: `0x1800063e0`
- end: `0x1800063fb`
- name: `?UnregisterCOMObject@?$Module@$00VServiceModule@Internal@Windows@@@WRL@Microsoft@@UEAAJPEBGPEAKI@Z`
- size: `27`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800063eb`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800063eb`

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
0x1800063e0  sub     rsp, 28h
0x1800063e4  xor     edx, edx
0x1800063e6  mov     ecx, 80004001h
0x1800063eb  call    cs:__imp_RoOriginateError
0x1800063f1  mov     eax, 80004001h
0x1800063f6  add     rsp, 28h
0x1800063fa  retn
```
