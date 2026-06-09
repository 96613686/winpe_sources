# ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)

- ea: `0x1800021a4`
- end: `0x1800021c2`
- name: `??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `79`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002198`
- `0x180002680`
- `0x180002920`
- `0x180002ae0`
- `0x180002fec`
- `0x180003a48`
- `0x180004a50`
- `0x180004af0`
- `0x180004b90`
- `0x180005920`
- `0x180005fdc`
- `0x180006630`
- `0x1800066bc`
- `0x18000676c`
- `0x18000681c`
- `0x1800068cc`
- `0x180007160`
- `0x180007450`
- `0x180007510`
- `0x1800076c0`
- `0x1800076fc`
- `0x180007718`
- `0x180007778`
- `0x1800077a0`
- `0x1800077d4`
- `0x180007b40`
- `0x180007ba0`
- `0x180007c00`
- `0x180007e20`
- `0x180007ea0`
- `0x180007f20`
- `0x180008190`
- `0x180008838`
- `0x180008b20`
- `0x180008c40`
- `0x180008d50`
- `0x180008e60`
- `0x180009650`
- `0x180009710`
- `0x180009b1c`
- `0x180009b44`
- `0x180009b74`
- `0x18000a60c`
- `0x18000a72c`
- `0x18000a8fc`
- `0x18000a924`
- `0x18000a960`
- `0x18000a988`
- `0x18000b080`
- `0x18000b3b0`

## callees

- `0x1800021a4`
- `0x180014010`

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
0x1800021a4  sub     rsp, 28h
0x1800021a8  mov     rcx, [rcx]
0x1800021ab  test    rcx, rcx
0x1800021ae  jz      short loc_1800021BD
0x1800021b0  mov     rax, [rcx]
0x1800021b3  mov     rax, [rax+10h]
0x1800021b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800021bc  nop
0x1800021bd  add     rsp, 28h
0x1800021c1  retn
```
