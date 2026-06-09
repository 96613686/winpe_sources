# _StringEnumerationMatcher::findMatches_::_1_::catch$0

- ea: `0x180010de0`
- end: `0x180010e09`
- name: `_StringEnumerationMatcher::findMatches_::_1_::catch$0`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010df1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010df1`

## pseudocode

```c
__int64 __fastcall StringEnumerationMatcher::findMatches_::_1_::catch_0(__int64 a1, __int64 a2)
{
  CoTaskMemFree(*(LPVOID *)(a2 + 40));
  return 0;
}

```

## disassembly

```asm
0x180010de0  mov     [rsp+arg_8], rdx
0x180010de5  push    rbp
0x180010de6  sub     rsp, 20h
0x180010dea  mov     rbp, rdx
0x180010ded  mov     rcx, [rbp+28h]; pv
0x180010df1  call    cs:__imp_CoTaskMemFree
0x180010df7  nop
0x180010df8  mov     rax, 0
0x180010e02  add     rsp, 20h
0x180010e06  pop     rbp
0x180010e07  retn
```
