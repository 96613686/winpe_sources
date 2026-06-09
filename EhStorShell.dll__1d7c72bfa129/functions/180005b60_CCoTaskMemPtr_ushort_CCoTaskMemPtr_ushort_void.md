# CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)

- ea: `0x180005b60`
- end: `0x180005b74`
- name: `??1?$CCoTaskMemPtr@G@@QEAA@XZ`
- size: `20`
- prototype: `void __fastcall(void **)`
- caller_count: `8`
- callee_count: `0`
- tags: `service_task`

## callers

- `0x180005dc0`
- `0x18000a760`
- `0x18000a890`
- `0x18000adb4`
- `0x18000b8ec`
- `0x18000b9c4`
- `0x18000bd68`
- `0x18000bd9e`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180005b6d`

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
0x180005b60  mov     rax, rcx
0x180005b63  mov     rcx, [rcx]
0x180005b66  mov     qword ptr [rax], 0
0x180005b6d  jmp     cs:__imp_CoTaskMemFree
```
