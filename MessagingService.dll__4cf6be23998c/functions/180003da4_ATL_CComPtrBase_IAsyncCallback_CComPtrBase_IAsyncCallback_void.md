# ATL::CComPtrBase<IAsyncCallback>::~CComPtrBase<IAsyncCallback>(void)

- ea: `0x180003da4`
- end: `0x180003dc2`
- name: `??1?$CComPtrBase@UIAsyncCallback@@@ATL@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180005720`
- `0x1800058c8`
- `0x180005a7c`
- `0x180005bd4`

## callees

- `0x180003da4`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall ATL::CComPtrBase<IAsyncCallback>::~CComPtrBase<IAsyncCallback>(__int64 *a1)
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
0x180003da4  sub     rsp, 28h
0x180003da8  mov     rcx, [rcx]
0x180003dab  test    rcx, rcx
0x180003dae  jz      short loc_180003DBD
0x180003db0  mov     rax, [rcx]
0x180003db3  mov     rax, [rax+10h]
0x180003db7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003dbc  nop
0x180003dbd  add     rsp, 28h
0x180003dc1  retn
```
