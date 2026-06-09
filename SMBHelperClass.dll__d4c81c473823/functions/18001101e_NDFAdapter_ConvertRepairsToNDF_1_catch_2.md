# _NDFAdapter::ConvertRepairsToNDF_::_1_::catch$2

- ea: `0x18001101e`
- end: `0x180011097`
- name: `_NDFAdapter::ConvertRepairsToNDF_::_1_::catch$2`
- size: `121`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update`

## callees

- `0x18000257c`
- `0x18000c334`
- `0x18000c3a0`
- `0x18000cb74`
- `0x18000ee10`

## pseudocode

```c
void __fastcall __noreturn NDFAdapter::ConvertRepairsToNDF_::_1_::catch_2(__int64 a1, __int64 a2)
{
  FreeNDFRepairVisitor *v3; // rax

  NDFRepairConversionClosure::numConverted((NDFRepairConversionClosure *)(a2 + 48));
  *(_QWORD *)(a2 + 40) = 0;
  v3 = FreeNDFRepairVisitor::FreeNDFRepairVisitor((FreeNDFRepairVisitor *)(a2 + 40));
  VisitArray<tagRepairInfo>(*(_QWORD *)(a2 + 128), v3);
  FreeTestMemory(*(LPVOID *)(a2 + 128));
  **(_DWORD **)(a2 + 152) = 0;
  **(_QWORD **)(a2 + 144) = 0;
  *(_DWORD *)(a2 + 32) = *(_DWORD *)(a2 + 36);
  throw (TestException *)(a2 + 32);
}

```

## disassembly

```asm
0x18001101e  mov     [rsp+arg_8], rdx
0x180011023  push    rbp
0x180011024  sub     rsp, 20h
0x180011028  mov     rbp, rdx
0x18001102b  lea     rcx, [rbp+30h]; this
0x18001102f  call    ?numConverted@NDFRepairConversionClosure@@QEAAKXZ; NDFRepairConversionClosure::numConverted(void)
0x180011034  mov     r8d, eax
0x180011037  mov     qword ptr [rbp+28h], 0
0x18001103f  lea     rcx, [rbp+28h]; this
0x180011043  call    ??0FreeNDFRepairVisitor@@QEAA@XZ; FreeNDFRepairVisitor::FreeNDFRepairVisitor(void)
0x180011048  nop
0x180011049  mov     rdx, rax
0x18001104c  mov     rcx, [rbp+80h]
0x180011053  call    ??$VisitArray@UtagRepairInfo@@@@YAXPEAUtagRepairInfo@@AEAV?$Visitor@PEAUtagRepairInfo@@@@_K@Z; VisitArray<tagRepairInfo>(tagRepairInfo *,Visitor<tagRepairInfo *> &,unsigned __int64)
0x180011058  nop
0x180011059  mov     rcx, [rbp+80h]; pv
0x180011060  call    ?FreeTestMemory@@YAXPEAX@Z; FreeTestMemory(void *)
0x180011065  mov     rax, [rbp+98h]
0x18001106c  mov     dword ptr [rax], 0
0x180011072  mov     rax, [rbp+90h]
0x180011079  mov     qword ptr [rax], 0
0x180011080  mov     eax, [rbp+24h]
0x180011083  mov     [rbp+20h], eax
0x180011086  lea     rdx, _TI1?AW4TestException@@; pThrowInfo
0x18001108d  lea     rcx, [rbp+20h]; pExceptionObject
0x180011091  call    _CxxThrowException_0
```
