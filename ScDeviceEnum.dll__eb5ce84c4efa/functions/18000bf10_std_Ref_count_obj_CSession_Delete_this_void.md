# std::_Ref_count_obj<CSession>::_Delete_this(void)

- ea: `0x18000bf10`
- end: `0x18000bf2f`
- name: `?_Delete_this@?$_Ref_count_obj@VCSession@@@std@@EEAAXXZ`
- size: `31`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000bf10`
- `0x180020010`

## pseudocode

```c
__int64 __fastcall std::_Ref_count_obj<CSession>::_Delete_this(__int64 a1)
{
  __int64 result; // rax

  if ( a1 )
    return (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 16LL))(a1, 1);
  return result;
}

```

## disassembly

```asm
0x18000bf10  sub     rsp, 28h
0x18000bf14  test    rcx, rcx
0x18000bf17  jz      short loc_18000BF2A
0x18000bf19  mov     rax, [rcx]
0x18000bf1c  mov     edx, 1
0x18000bf21  mov     rax, [rax+10h]
0x18000bf25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf2a  add     rsp, 28h
0x18000bf2e  retn
```
