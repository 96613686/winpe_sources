# std::_Ref_count_obj2<RfbDiskFolderWmiQuery>::_Delete_this(void)

- ea: `0x180007250`
- end: `0x18000726f`
- name: `?_Delete_this@?$_Ref_count_obj2@VRfbDiskFolderWmiQuery@@@std@@EEAAXXZ`
- size: `31`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180007250`
- `0x180019010`

## pseudocode

```c
__int64 __fastcall std::_Ref_count_obj2<RfbDiskFolderWmiQuery>::_Delete_this(__int64 a1)
{
  __int64 result; // rax

  if ( a1 )
    return (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 16LL))(a1, 1);
  return result;
}

```

## disassembly

```asm
0x180007250  sub     rsp, 28h
0x180007254  test    rcx, rcx
0x180007257  jz      short loc_18000726A
0x180007259  mov     rax, [rcx]
0x18000725c  mov     edx, 1
0x180007261  mov     rax, [rax+10h]
0x180007265  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000726a  add     rsp, 28h
0x18000726e  retn
```
