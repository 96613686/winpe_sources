# ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)

- ea: `0x180002244`
- end: `0x180002262`
- name: `??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ`
- size: `30`
- prototype: ``
- caller_count: `74`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000e59f`
- `0x18000e5f6`
- `0x18000e636`
- `0x18000e692`
- `0x18000e69e`
- `0x18000e6da`
- `0x18000e6e6`
- `0x18000e8b4`
- `0x18000e8c0`
- `0x18000e8cc`
- `0x18000e920`
- `0x18000e92c`
- `0x18000e938`
- `0x18000e944`
- `0x18000e950`
- `0x18000e95c`
- `0x18000e980`
- `0x18000e98c`
- `0x18000e9bc`
- `0x18000e9e0`
- `0x18000e9f8`
- `0x18000ea04`
- `0x18000ea34`
- `0x18000ea4c`
- `0x18000ea58`
- `0x18000ea96`
- `0x18000eaae`
- `0x18000eac6`
- `0x18000eade`
- `0x18000eaea`
- `0x18000eaf6`
- `0x18000eb32`
- `0x18000eb4a`
- `0x18000eb56`
- `0x18000eb62`
- `0x18000ebaa`
- `0x18000ebb6`
- `0x18000ebc2`
- `0x18000ebce`
- `0x18000ebda`
- `0x18000ebfe`
- `0x18000ec16`
- `0x18000ec3a`
- `0x18000ecd8`
- `0x18000ece4`
- `0x18000ecfc`
- `0x18000ed14`
- `0x18000ed20`
- `0x18000ed2c`
- `0x18000ed5c`

## callees

- `0x180002244`
- `0x18000e4a0`

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
0x180002244  sub     rsp, 28h
0x180002248  mov     rcx, [rcx]
0x18000224b  test    rcx, rcx
0x18000224e  jz      short loc_18000225D
0x180002250  mov     rax, [rcx]
0x180002253  mov     rax, [rax+10h]
0x180002257  call    cs:__guard_dispatch_icall_fptr
0x18000225d  add     rsp, 28h
0x180002261  retn
```
