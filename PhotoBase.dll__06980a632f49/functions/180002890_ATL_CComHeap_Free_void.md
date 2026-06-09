# ATL::CComHeap::Free(void *)

- ea: `0x180002890`
- end: `0x18000289a`
- name: `?Free@CComHeap@ATL@@UEAAXPEAX@Z`
- size: `10`
- prototype: `void __fastcall(ATL::CComHeap *__hidden this, void *)`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180002893`

## pseudocode

```c
void __fastcall ATL::CComHeap::Free(ATL::CComHeap *this, void *a2)
{
  CoTaskMemFree(a2);
}

```

## disassembly

```asm
0x180002890  mov     rcx, rdx
0x180002893  jmp     cs:__imp_CoTaskMemFree
```
