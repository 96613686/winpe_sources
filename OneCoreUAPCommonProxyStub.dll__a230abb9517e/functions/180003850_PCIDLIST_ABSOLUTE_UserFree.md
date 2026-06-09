# PCIDLIST_ABSOLUTE_UserFree

- ea: `0x180003850`
- end: `0x18000385a`
- name: `PCIDLIST_ABSOLUTE_UserFree`
- size: `10`
- prototype: `void __stdcall(unsigned int *, LPCITEMIDLIST *)`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003853`

## pseudocode

```c
void __stdcall PCIDLIST_ABSOLUTE_UserFree(unsigned int *a1, LPCITEMIDLIST *a2)
{
  CoTaskMemFree((LPVOID)*a2);
}

```

## disassembly

```asm
0x180003850  mov     rcx, [rdx]
0x180003853  jmp     cs:__imp_CoTaskMemFree
```
