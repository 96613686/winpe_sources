# std::tr1::_Ref_count<SerializedRegistryKey>::_Destroy(void)

- ea: `0x180020f60`
- end: `0x180020f83`
- name: `?_Destroy@?$_Ref_count@VSerializedRegistryKey@@@tr1@std@@EEAAXXZ`
- size: `35`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x180020f60`
- `0x180025010`

## pseudocode

```c
__int64 __fastcall std::tr1::_Ref_count<SerializedRegistryKey>::_Destroy(__int64 a1)
{
  __int64 v1; // rcx
  __int64 result; // rax

  v1 = *(_QWORD *)(a1 + 16);
  if ( v1 )
    return (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v1 + 96LL))(v1, 1);
  return result;
}

```

## disassembly

```asm
0x180020f60  sub     rsp, 28h
0x180020f64  mov     rcx, [rcx+10h]
0x180020f68  test    rcx, rcx
0x180020f6b  jz      short loc_180020F7E
0x180020f6d  mov     rax, [rcx]
0x180020f70  mov     edx, 1
0x180020f75  mov     rax, [rax+60h]
0x180020f79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020f7e  add     rsp, 28h
0x180020f82  retn
```
