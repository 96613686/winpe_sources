# NDFRepairConversionClosure::numConverted(void)

- ea: `0x18000cb74`
- end: `0x18000cb78`
- name: `?numConverted@NDFRepairConversionClosure@@QEAAKXZ`
- size: `4`
- prototype: `unsigned int __fastcall(NDFRepairConversionClosure *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x18001101e`

## pseudocode

```c
__int64 __fastcall NDFRepairConversionClosure::numConverted(NDFRepairConversionClosure *this)
{
  return *((unsigned int *)this + 6);
}

```

## disassembly

```asm
0x18000cb74  mov     eax, [rcx+18h]
0x18000cb77  retn
```
