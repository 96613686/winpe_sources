# _CWfHelperClass::GetRepairInfo_::_1_::dtor$0

- ea: `0x18000cb10`
- end: `0x18000cb1c`
- name: `_CWfHelperClass::GetRepairInfo_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x180002860`

## pseudocode

```c
void __fastcall CWfHelperClass::GetRepairInfo_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  TNDFDeallocator<tagRepairInfo *,&void FreeRepairInfos(tagRepairInfo *,unsigned long,int)>::~TNDFDeallocator<tagRepairInfo *,&void FreeRepairInfos(tagRepairInfo *,unsigned long,int)>(a2 + 40);
}

```

## disassembly

```asm
0x18000cb10  lea     rcx, [rdx+28h]
0x18000cb17  jmp     ??1?$TNDFDeallocator@PEAUtagRepairInfo@@$1?FreeRepairInfos@@YAXPEAU1@KH@Z@@QEAA@XZ; TNDFDeallocator<tagRepairInfo *,&FreeRepairInfos(tagRepairInfo *,ulong,int)>::~TNDFDeallocator<tagRepairInfo *,&FreeRepairInfos(tagRepairInfo *,ulong,int)>(void)
```
