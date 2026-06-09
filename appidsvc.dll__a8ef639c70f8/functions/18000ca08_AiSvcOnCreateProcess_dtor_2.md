# AiSvcOnCreateProcess$dtor$2

- ea: `0x18000ca08`
- end: `0x18000ca14`
- name: `AiSvcOnCreateProcess$dtor$2`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180006164`

## pseudocode

```c
void __fastcall AiSvcOnCreateProcess_dtor_2(__int64 a1, __int64 a2)
{
  std::unique_ptr<ON_CREATE_PROC_DATA>::~unique_ptr<ON_CREATE_PROC_DATA>((void ***)(a2 + 152));
}

```

## disassembly

```asm
0x18000ca08  lea     rcx, [rdx+98h]
0x18000ca0f  jmp     ??1?$unique_ptr@VON_CREATE_PROC_DATA@@U?$default_delete@VON_CREATE_PROC_DATA@@@std@@@std@@QEAA@XZ; std::unique_ptr<ON_CREATE_PROC_DATA>::~unique_ptr<ON_CREATE_PROC_DATA>(void)
```
