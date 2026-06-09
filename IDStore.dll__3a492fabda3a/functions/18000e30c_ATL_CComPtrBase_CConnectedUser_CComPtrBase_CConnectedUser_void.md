# ATL::CComPtrBase<CConnectedUser>::~CComPtrBase<CConnectedUser>(void)

- ea: `0x18000e30c`
- end: `0x18000e329`
- name: `??1?$CComPtrBase@VCConnectedUser@@@ATL@@QEAA@XZ`
- size: `29`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180016060`

## callees

- `0x18000e30c`
- `0x18001b010`

## pseudocode

```c
__int64 __fastcall ATL::CComPtrBase<CConnectedUser>::~CComPtrBase<CConnectedUser>(__int64 *a1)
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
0x18000e30c  sub     rsp, 28h
0x18000e310  mov     rcx, [rcx]
0x18000e313  test    rcx, rcx
0x18000e316  jz      short loc_18000E324
0x18000e318  mov     rax, [rcx]
0x18000e31b  mov     rax, [rax+10h]
0x18000e31f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e324  add     rsp, 28h
0x18000e328  retn
```
