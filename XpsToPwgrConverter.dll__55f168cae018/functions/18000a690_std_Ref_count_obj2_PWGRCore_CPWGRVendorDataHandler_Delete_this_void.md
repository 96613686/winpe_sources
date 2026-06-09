# std::_Ref_count_obj2<PWGRCore::CPWGRVendorDataHandler>::_Delete_this(void)

- ea: `0x18000a690`
- end: `0x18000a6af`
- name: `?_Delete_this@?$_Ref_count_obj2@VCPWGRVendorDataHandler@PWGRCore@@@std@@EEAAXXZ`
- size: `31`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18000a690`
- `0x180011010`

## pseudocode

```c
__int64 __fastcall std::_Ref_count_obj2<PWGRCore::CPWGRVendorDataHandler>::_Delete_this(__int64 a1)
{
  __int64 result; // rax

  if ( a1 )
    return (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 16LL))(a1, 1);
  return result;
}

```

## disassembly

```asm
0x18000a690  sub     rsp, 28h
0x18000a694  test    rcx, rcx
0x18000a697  jz      short loc_18000A6AA
0x18000a699  mov     rax, [rcx]
0x18000a69c  mov     edx, 1
0x18000a6a1  mov     rax, [rax+10h]
0x18000a6a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a6aa  add     rsp, 28h
0x18000a6ae  retn
```
