# ATL::CComPtrBase<IEnumPortableDeviceConnectors>::~CComPtrBase<IEnumPortableDeviceConnectors>(void)

- ea: `0x1800080e0`
- end: `0x1800080fe`
- name: `??1?$CComPtrBase@UIEnumPortableDeviceConnectors@@@ATL@@QEAA@XZ`
- size: `30`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180004620`
- `0x180011f78`

## callees

- `0x1800080e0`
- `0x180016010`

## pseudocode

```c
__int64 __fastcall ATL::CComPtrBase<IEnumPortableDeviceConnectors>::~CComPtrBase<IEnumPortableDeviceConnectors>(
        __int64 *a1)
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
0x1800080e0  sub     rsp, 28h
0x1800080e4  mov     rcx, [rcx]
0x1800080e7  test    rcx, rcx
0x1800080ea  jz      short loc_1800080F9
0x1800080ec  mov     rax, [rcx]
0x1800080ef  mov     rax, [rax+10h]
0x1800080f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800080f8  nop
0x1800080f9  add     rsp, 28h
0x1800080fd  retn
```
