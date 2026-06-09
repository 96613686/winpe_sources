# _FileUtility::GetFullTempFilePath_::_1_::dtor$2

- ea: `0x180011e05`
- end: `0x180011e11`
- name: `_FileUtility::GetFullTempFilePath_::_1_::dtor$2`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180010ad4`

## pseudocode

```c
void __fastcall FileUtility::GetFullTempFilePath_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>((void **)(a2 + 96));
}

```

## disassembly

```asm
0x180011e05  lea     rcx, [rdx+60h]
0x180011e0c  jmp     ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
```
