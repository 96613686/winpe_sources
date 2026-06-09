# _CSMBHelperClass::Initialize_::_1_::catch$2

- ea: `0x1800107f4`
- end: `0x180010831`
- name: `_CSMBHelperClass::Initialize_::_1_::catch$2`
- size: `61`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800107f4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010808`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010808`

## pseudocode

```c
_BOOL8 __fastcall CSMBHelperClass::Initialize_::_1_::catch_2(__int64 a1, __int64 a2)
{
  CoTaskMemFree(*(LPVOID *)(a2 + 224));
  return *(_DWORD *)(a2 + 40) != 0;
}

```

## disassembly

```asm
0x1800107f4  mov     [rsp+arg_8], rdx
0x1800107f9  push    rbp
0x1800107fa  sub     rsp, 20h
0x1800107fe  mov     rbp, rdx
0x180010801  mov     rcx, [rbp+0E0h]; pv
0x180010808  call    cs:__imp_CoTaskMemFree
0x18001080e  cmp     dword ptr [rbp+28h], 0
0x180010812  jnz     short loc_180010820
0x180010814  mov     rax, 0
0x18001081e  jmp     short loc_18001082A
0x180010820  mov     rax, 1
0x18001082a  add     rsp, 20h
0x18001082e  pop     rbp
0x18001082f  retn
```
