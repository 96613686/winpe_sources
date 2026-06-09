# ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)

- ea: `0x180007364`
- end: `0x180007382`
- name: `??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ`
- size: `30`
- prototype: ``
- caller_count: `15`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180007358`
- `0x180007e2c`
- `0x180007f4c`
- `0x180008bd4`
- `0x18000c980`
- `0x18000cfc4`
- `0x18000d590`
- `0x18000db20`
- `0x18000de68`
- `0x18000e034`
- `0x18000e40c`
- `0x18000e888`
- `0x18000ef24`
- `0x180015e1c`
- `0x1800163f4`

## callees

- `0x180007364`
- `0x18001e010`

## pseudocode

```c
__int64 __fastcall ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(__int64 *a1)
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
0x180007364  sub     rsp, 28h
0x180007368  mov     rcx, [rcx]
0x18000736b  test    rcx, rcx
0x18000736e  jz      short loc_18000737C
0x180007370  mov     rax, [rcx]
0x180007373  mov     rax, [rax+10h]
0x180007377  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000737c  add     rsp, 28h
0x180007380  retn
```
