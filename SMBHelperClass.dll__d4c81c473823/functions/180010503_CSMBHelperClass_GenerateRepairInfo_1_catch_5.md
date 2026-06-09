# _CSMBHelperClass::GenerateRepairInfo_::_1_::catch$5

- ea: `0x180010503`
- end: `0x18001052b`
- name: `_CSMBHelperClass::GenerateRepairInfo_::_1_::catch$5`
- size: `40`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update`

## pseudocode

```c
__int64 __fastcall CSMBHelperClass::GenerateRepairInfo_::_1_::catch_5(__int64 a1, __int64 a2)
{
  *(_DWORD *)(a2 + 152) = -2147467259;
  return 0;
}

```

## disassembly

```asm
0x180010503  mov     [rsp+arg_8], rdx
0x180010508  push    rbp
0x180010509  sub     rsp, 20h
0x18001050d  mov     rbp, rdx
0x180010510  mov     dword ptr [rbp+98h], 80004005h
0x18001051a  mov     rax, 0
0x180010524  add     rsp, 20h
0x180010528  pop     rbp
0x180010529  retn
```
