# ATL::CComPtr<ITypeInfo>::~CComPtr<ITypeInfo>(void)

- ea: `0x180002d00`
- end: `0x180002d1e`
- name: `??1?$CComPtr@UITypeInfo@@@ATL@@QEAA@XZ`
- size: `30`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000991f`
- `0x180009931`
- `0x180009943`

## callees

- `0x180002d00`
- `0x18000a010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x180002d00  sub     rsp, 28h
0x180002d04  mov     rcx, [rcx]
0x180002d07  test    rcx, rcx
0x180002d0a  jz      short loc_180002D19
0x180002d0c  mov     rax, [rcx]
0x180002d0f  mov     rax, [rax+10h]
0x180002d13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d18  nop
0x180002d19  add     rsp, 28h
0x180002d1d  retn
```
