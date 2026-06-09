# CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)

- ea: `0x180010354`
- end: `0x180010368`
- name: `??1?$CCoTaskMemPtr@G@@QEAA@XZ`
- size: `20`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x180010aa4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010361`

## pseudocode

```c
void __fastcall CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(void **a1)
{
  void *v2; // rcx

  v2 = *a1;
  *a1 = 0;
  CoTaskMemFree(v2);
}

```

## disassembly

```asm
0x180010354  mov     rax, rcx
0x180010357  mov     rcx, [rcx]
0x18001035a  mov     qword ptr [rax], 0
0x180010361  jmp     cs:__imp_CoTaskMemFree
```
