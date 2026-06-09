# _DiagnosisTextBuilderImpl::GetXML_::_1_::catch$12

- ea: `0x18000ccfc`
- end: `0x18000cd26`
- name: `_DiagnosisTextBuilderImpl::GetXML_::_1_::catch$12`
- size: `42`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## pseudocode

```c
__int64 __fastcall DiagnosisTextBuilderImpl::GetXML_::_1_::catch_12(__int64 a1, __int64 a2)
{
  *(_DWORD *)(a2 + 128) = **(_DWORD **)(a2 + 40);
  return 0;
}

```

## disassembly

```asm
0x18000ccfc  mov     [rsp+arg_8], rdx
0x18000cd01  push    rbp
0x18000cd02  sub     rsp, 20h
0x18000cd06  mov     rbp, rdx
0x18000cd09  mov     rax, [rbp+28h]
0x18000cd0d  mov     ecx, [rax]
0x18000cd0f  mov     [rbp+80h], ecx
0x18000cd15  mov     rax, 0
0x18000cd1f  add     rsp, 20h
0x18000cd23  pop     rbp
0x18000cd24  retn
```
