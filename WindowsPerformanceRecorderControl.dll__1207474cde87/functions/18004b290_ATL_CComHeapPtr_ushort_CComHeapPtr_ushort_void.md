# ATL::CComHeapPtr<ushort>::~CComHeapPtr<ushort>(void)

- ea: `0x18004b290`
- end: `0x18004b2af`
- name: `??1?$CComHeapPtr@G@ATL@@QEAA@XZ`
- size: `31`
- prototype: `void __fastcall(LPVOID *)`
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x180087202`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b29c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b29c`

## pseudocode

```c
void __fastcall ATL::CComHeapPtr<unsigned short>::~CComHeapPtr<unsigned short>(LPVOID *a1)
{
  CoTaskMemFree(*a1);
  *a1 = 0;
}

```

## disassembly

```asm
0x18004b290  push    rbx
0x18004b292  sub     rsp, 20h
0x18004b296  mov     rbx, rcx
0x18004b299  mov     rcx, [rcx]; pv
0x18004b29c  call    cs:__imp_CoTaskMemFree
0x18004b2a2  mov     qword ptr [rbx], 0
0x18004b2a9  add     rsp, 20h
0x18004b2ad  pop     rbx
0x18004b2ae  retn
```
