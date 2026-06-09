# ATL::CComHeapPtr<tWAVEFORMATEX>::~CComHeapPtr<tWAVEFORMATEX>(void)

- ea: `0x140007bd8`
- end: `0x140007bf7`
- name: `??1?$CComHeapPtr@UtWAVEFORMATEX@@@ATL@@QEAA@XZ`
- size: `31`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x14002f689`
- `0x14002f69b`
- `0x14003070d`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140007be4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140007be4`

## pseudocode

```c
void __fastcall ATL::CComHeapPtr<tWAVEFORMATEX>::~CComHeapPtr<tWAVEFORMATEX>(LPVOID *a1)
{
  CoTaskMemFree(*a1);
  *a1 = 0;
}

```

## disassembly

```asm
0x140007bd8  push    rbx
0x140007bda  sub     rsp, 20h
0x140007bde  mov     rbx, rcx
0x140007be1  mov     rcx, [rcx]; pv
0x140007be4  call    cs:__imp_CoTaskMemFree
0x140007bea  mov     qword ptr [rbx], 0
0x140007bf1  add     rsp, 20h
0x140007bf5  pop     rbx
0x140007bf6  retn
```
