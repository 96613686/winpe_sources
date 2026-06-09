# CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)

- ea: `0x140008904`
- end: `0x140008918`
- name: `??1?$CCoTaskMemPtr@E@@QEAA@XZ`
- size: `20`
- prototype: `void __fastcall(void **)`
- caller_count: `2`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400092d4`
- `0x14000dcf0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140008911`

## pseudocode

```c
void __fastcall CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(void **a1)
{
  void *v2; // rcx

  v2 = *a1;
  *a1 = 0;
  CoTaskMemFree(v2);
}

```

## disassembly

```asm
0x140008904  mov     rax, rcx
0x140008907  mov     rcx, [rcx]
0x14000890a  mov     qword ptr [rax], 0
0x140008911  jmp     cs:__imp_CoTaskMemFree
```
