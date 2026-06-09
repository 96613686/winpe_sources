# ATL::CComPtr<ITypeInfo>::~CComPtr<ITypeInfo>(void)

- ea: `0x180009ec8`
- end: `0x180009ee6`
- name: `??1?$CComPtr@UITypeInfo@@@ATL@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000e707`
- `0x18000e719`
- `0x18000e72b`

## callees

- `0x180009ec8`
- `0x18000f010`

## pseudocode

```c
__int64 __fastcall ATL::CComPtr<ITypeInfo>::~CComPtr<ITypeInfo>(__int64 *a1)
{
  __int64 v1; // rcx
  __int64 result; // rax

  v1 = *a1;
  if ( v1 )
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
  return result;
}

```

## disassembly

```asm
0x180009ec8  sub     rsp, 28h
0x180009ecc  mov     rcx, [rcx]
0x180009ecf  test    rcx, rcx
0x180009ed2  jz      short loc_180009EE1
0x180009ed4  mov     rax, [rcx]
0x180009ed7  mov     rax, [rax+10h]
0x180009edb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ee0  nop
0x180009ee1  add     rsp, 28h
0x180009ee5  retn
```
