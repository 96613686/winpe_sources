# ATL::CComPtrBase<IPMApplicationInfo>::~CComPtrBase<IPMApplicationInfo>(void)

- ea: `0x18000506c`
- end: `0x180005089`
- name: `??1?$CComPtrBase@UIPMApplicationInfo@@@ATL@@QEAA@XZ`
- size: `29`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800058f0`

## callees

- `0x18000506c`
- `0x180007010`

## pseudocode

```c
__int64 __fastcall ATL::CComPtrBase<IPMApplicationInfo>::~CComPtrBase<IPMApplicationInfo>(__int64 *a1)
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
0x18000506c  sub     rsp, 28h
0x180005070  mov     rcx, [rcx]
0x180005073  test    rcx, rcx
0x180005076  jz      short loc_180005084
0x180005078  mov     rax, [rcx]
0x18000507b  mov     rax, [rax+10h]
0x18000507f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005084  add     rsp, 28h
0x180005088  retn
```
