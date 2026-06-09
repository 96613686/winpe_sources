# ATL::CComPtr<TransportManager>::~CComPtr<TransportManager>(void)

- ea: `0x180002be4`
- end: `0x180002c01`
- name: `??1?$CComPtr@VTransportManager@@@ATL@@QEAA@XZ`
- size: `29`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000aec0`
- `0x18000aed2`
- `0x18000af3e`
- `0x18000af62`

## callees

- `0x180002be4`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall ATL::CComPtr<TransportManager>::~CComPtr<TransportManager>(__int64 *a1)
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
0x180002be4  sub     rsp, 28h
0x180002be8  mov     rcx, [rcx]
0x180002beb  test    rcx, rcx
0x180002bee  jz      short loc_180002BFC
0x180002bf0  mov     rax, [rcx]
0x180002bf3  mov     rax, [rax+10h]
0x180002bf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002bfc  add     rsp, 28h
0x180002c00  retn
```
