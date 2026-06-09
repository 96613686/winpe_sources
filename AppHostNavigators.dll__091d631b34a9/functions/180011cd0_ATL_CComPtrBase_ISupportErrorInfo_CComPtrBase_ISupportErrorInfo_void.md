# ATL::CComPtrBase<ISupportErrorInfo>::~CComPtrBase<ISupportErrorInfo>(void)

- ea: `0x180011cd0`
- end: `0x180011ced`
- name: `??1?$CComPtrBase@UISupportErrorInfo@@@ATL@@QEAA@XZ`
- size: `29`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180011d80`
- `0x180011e98`

## callees

- `0x180011cd0`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall ATL::CComPtrBase<ISupportErrorInfo>::~CComPtrBase<ISupportErrorInfo>(__int64 *a1)
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
0x180011cd0  sub     rsp, 28h
0x180011cd4  mov     rcx, [rcx]
0x180011cd7  test    rcx, rcx
0x180011cda  jz      short loc_180011CE8
0x180011cdc  mov     rax, [rcx]
0x180011cdf  mov     rax, [rax+10h]
0x180011ce3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011ce8  add     rsp, 28h
0x180011cec  retn
```
