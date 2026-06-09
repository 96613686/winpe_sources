# ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)

- ea: `0x18000453c`
- end: `0x18000455a`
- name: `??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `12`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001090`
- `0x180002610`
- `0x180004530`
- `0x1800048e0`
- `0x180005dc0`
- `0x1800065b4`
- `0x18000a708`
- `0x18000a738`
- `0x18000a890`
- `0x18000ac54`
- `0x18000b1e0`
- `0x18000b250`

## callees

- `0x18000453c`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(__int64 *a1)
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
0x18000453c  sub     rsp, 28h
0x180004540  mov     rcx, [rcx]
0x180004543  test    rcx, rcx
0x180004546  jz      short loc_180004555
0x180004548  mov     rax, [rcx]
0x18000454b  mov     rax, [rax+10h]
0x18000454f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004554  nop
0x180004555  add     rsp, 28h
0x180004559  retn
```
