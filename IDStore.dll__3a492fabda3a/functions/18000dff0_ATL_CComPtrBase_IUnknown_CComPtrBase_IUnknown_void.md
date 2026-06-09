# ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)

- ea: `0x18000dff0`
- end: `0x18000e00e`
- name: `??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `11`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001808`
- `0x180005000`
- `0x1800074dc`
- `0x180008910`
- `0x180012b10`
- `0x180013170`
- `0x1800132b0`
- `0x180013430`
- `0x1800139bc`
- `0x180013b40`
- `0x180014140`

## callees

- `0x18000dff0`
- `0x18001b010`

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
0x18000dff0  sub     rsp, 28h
0x18000dff4  mov     rcx, [rcx]
0x18000dff7  test    rcx, rcx
0x18000dffa  jz      short loc_18000E009
0x18000dffc  mov     rax, [rcx]
0x18000dfff  mov     rax, [rax+10h]
0x18000e003  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e008  nop
0x18000e009  add     rsp, 28h
0x18000e00d  retn
```
