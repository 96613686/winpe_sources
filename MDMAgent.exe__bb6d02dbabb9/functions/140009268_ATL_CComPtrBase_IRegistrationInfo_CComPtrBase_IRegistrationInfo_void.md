# ATL::CComPtrBase<IRegistrationInfo>::~CComPtrBase<IRegistrationInfo>(void)

- ea: `0x140009268`
- end: `0x140009286`
- name: `??1?$CComPtrBase@UIRegistrationInfo@@@ATL@@QEAA@XZ`
- size: `30`
- prototype: ``
- caller_count: `13`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400099c8`
- `0x140009ae8`
- `0x14000a51c`
- `0x14000c314`
- `0x14000d780`
- `0x14000ddd8`
- `0x14000e3a4`
- `0x14000e934`
- `0x14000ec7c`
- `0x14000ee48`
- `0x14000f220`
- `0x14000f69c`
- `0x14000fd3c`

## callees

- `0x140009268`
- `0x14001a010`

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
0x140009268  sub     rsp, 28h
0x14000926c  mov     rcx, [rcx]
0x14000926f  test    rcx, rcx
0x140009272  jz      short loc_140009280
0x140009274  mov     rax, [rcx]
0x140009277  mov     rax, [rax+10h]
0x14000927b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009280  add     rsp, 28h
0x140009284  retn
```
