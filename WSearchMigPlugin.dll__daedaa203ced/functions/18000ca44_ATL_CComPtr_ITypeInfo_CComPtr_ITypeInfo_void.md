# ATL::CComPtr<ITypeInfo>::~CComPtr<ITypeInfo>(void)

- ea: `0x18000ca44`
- end: `0x18000ca6b`
- name: `??1?$CComPtr@UITypeInfo@@@ATL@@QEAA@XZ`
- size: `39`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800178b1`
- `0x1800178c3`
- `0x1800178d5`

## callees

- `0x18000ca44`
- `0x180018010`

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
0x18000ca44  sub     rsp, 38h
0x18000ca48  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x18000ca51  mov     rcx, [rcx]
0x18000ca54  test    rcx, rcx
0x18000ca57  jz      short loc_18000CA66
0x18000ca59  mov     rax, [rcx]
0x18000ca5c  mov     rax, [rax+10h]
0x18000ca60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ca65  nop
0x18000ca66  add     rsp, 38h
0x18000ca6a  retn
```
