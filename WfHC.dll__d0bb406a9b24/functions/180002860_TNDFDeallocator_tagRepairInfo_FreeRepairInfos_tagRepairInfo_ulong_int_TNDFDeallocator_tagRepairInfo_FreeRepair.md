# TNDFDeallocator<tagRepairInfo *,&FreeRepairInfos(tagRepairInfo *,ulong,int)>::~TNDFDeallocator<tagRepairInfo *,&FreeRepairInfos(tagRepairInfo *,ulong,int)>(void)

- ea: `0x180002860`
- end: `0x180002878`
- name: `??1?$TNDFDeallocator@PEAUtagRepairInfo@@$1?FreeRepairInfos@@YAXPEAU1@KH@Z@@QEAA@XZ`
- size: `24`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x18000cb10`

## callees

- `0x180002860`
- `0x180003c10`

## pseudocode

```c
void __fastcall TNDFDeallocator<tagRepairInfo *,&void FreeRepairInfos(tagRepairInfo *,unsigned long,int)>::~TNDFDeallocator<tagRepairInfo *,&void FreeRepairInfos(tagRepairInfo *,unsigned long,int)>(
        __int64 a1)
{
  if ( *(_QWORD *)a1 )
    FreeRepairInfos(*(struct tagRepairInfo **)a1, *(_DWORD *)(a1 + 8), *(_DWORD *)(a1 + 12));
}

```

## disassembly

```asm
0x180002860  mov     rax, [rcx]
0x180002863  test    rax, rax
0x180002866  jz      short locret_180002877
0x180002868  mov     r8d, [rcx+0Ch]; int
0x18000286c  mov     edx, [rcx+8]; unsigned int
0x18000286f  mov     rcx, rax; pv
0x180002872  jmp     ?FreeRepairInfos@@YAXPEAUtagRepairInfo@@KH@Z; FreeRepairInfos(tagRepairInfo *,ulong,int)
0x180002877  retn
```
