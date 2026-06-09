# ATL::CHeapPtr<tWAVEFORMATEX,ATL::CComAllocator>::~CHeapPtr<tWAVEFORMATEX,ATL::CComAllocator>(void)

- ea: `0x180041cac`
- end: `0x180041cd3`
- name: `??1?$CHeapPtr@UtWAVEFORMATEX@@VCComAllocator@ATL@@@ATL@@QEAA@XZ`
- size: `39`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x180041ca0`
- `0x180056dd0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041cb8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180041cb8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ATL::CHeapPtr<tWAVEFORMATEX,ATL::CComAllocator>::~CHeapPtr<tWAVEFORMATEX,ATL::CComAllocator>(
        LPVOID *a1)
{
  CoTaskMemFree(*a1);
  *a1 = 0;
}

```

## disassembly

```asm
0x180041cac  push    rbx
0x180041cae  sub     rsp, 20h
0x180041cb2  mov     rbx, rcx
0x180041cb5  mov     rcx, [rcx]; pv
0x180041cb8  call    cs:__imp_CoTaskMemFree
0x180041cbf  nop     dword ptr [rax+rax+00h]
0x180041cc4  nop
0x180041cc5  mov     qword ptr [rbx], 0
0x180041ccc  add     rsp, 20h
0x180041cd0  pop     rbx
0x180041cd1  retn
```
