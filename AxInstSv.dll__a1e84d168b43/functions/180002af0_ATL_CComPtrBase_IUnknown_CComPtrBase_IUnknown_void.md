# ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)

- ea: `0x180002af0`
- end: `0x180002b0e`
- name: `??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ`
- size: `30`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002ae4`
- `0x180002b78`
- `0x180002bb0`
- `0x180003260`
- `0x180006640`
- `0x18000f170`

## callees

- `0x180002af0`
- `0x180015010`

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
0x180002af0  sub     rsp, 28h
0x180002af4  mov     rcx, [rcx]
0x180002af7  test    rcx, rcx
0x180002afa  jz      short loc_180002B09
0x180002afc  mov     rax, [rcx]
0x180002aff  mov     rax, [rax+10h]
0x180002b03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b08  nop
0x180002b09  add     rsp, 28h
0x180002b0d  retn
```
