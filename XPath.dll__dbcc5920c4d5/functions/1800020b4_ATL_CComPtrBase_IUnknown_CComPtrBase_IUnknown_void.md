# ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)

- ea: `0x1800020b4`
- end: `0x1800020d1`
- name: `??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ`
- size: `29`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `49`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001b20`
- `0x1800020d8`
- `0x1800021e0`
- `0x180002438`
- `0x180002e9c`
- `0x180002fcc`
- `0x180003340`
- `0x18000338c`
- `0x1800033b8`
- `0x1800033e8`
- `0x180003420`
- `0x180004aac`
- `0x180004d24`
- `0x180005124`
- `0x180005550`
- `0x1800056a0`
- `0x180005830`
- `0x18000588c`
- `0x180005a3c`
- `0x180005b60`
- `0x180005c7c`
- `0x1800064f4`
- `0x1800065e0`
- `0x180006618`
- `0x180006730`
- `0x1800067c8`
- `0x1800067f8`
- `0x180006838`
- `0x180008060`
- `0x1800080b8`
- `0x180008d28`
- `0x180008dc4`
- `0x180008f04`
- `0x1800094f4`
- `0x1800097cc`
- `0x180009890`
- `0x180009d84`
- `0x180009f24`
- `0x18000a280`
- `0x18000b170`
- `0x18000c830`
- `0x18000c8d0`
- `0x18000cc54`
- `0x18000d8a0`
- `0x18000e498`
- `0x180010500`
- `0x180010618`
- `0x1800110b8`
- `0x1800112d8`

## callees

- `0x1800020b4`
- `0x180012010`

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
0x1800020b4  sub     rsp, 28h
0x1800020b8  mov     rcx, [rcx]
0x1800020bb  test    rcx, rcx
0x1800020be  jz      short loc_1800020CC
0x1800020c0  mov     rax, [rcx]
0x1800020c3  mov     rax, [rax+10h]
0x1800020c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800020cc  add     rsp, 28h
0x1800020d0  retn
```
