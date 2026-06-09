# Microsoft::WRL::Wrappers::HandleT<CoTaskMemBufferTraits>::InternalClose(void)

- ea: `0x18000cc40`
- end: `0x18000cc55`
- name: `?InternalClose@?$HandleT@UCoTaskMemBufferTraits@@@Wrappers@WRL@Microsoft@@MEAA_NXZ`
- size: `21`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cc48`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cc48`

## pseudocode

```c
char __fastcall Microsoft::WRL::Wrappers::HandleT<CoTaskMemBufferTraits>::InternalClose(__int64 a1)
{
  CoTaskMemFree(*(LPVOID *)(a1 + 8));
  return 1;
}

```

## disassembly

```asm
0x18000cc40  sub     rsp, 28h
0x18000cc44  mov     rcx, [rcx+8]; pv
0x18000cc48  call    cs:__imp_CoTaskMemFree
0x18000cc4e  mov     al, 1
0x18000cc50  add     rsp, 28h
0x18000cc54  retn
```
