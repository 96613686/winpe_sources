# ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)

- ea: `0x18000eb68`
- end: `0x18000eb86`
- name: `??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ`
- size: `30`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000c810`
- `0x18000d000`
- `0x18000d630`
- `0x18000eb5c`
- `0x18000eb8c`
- `0x18001c058`

## callees

- `0x18000eb68`
- `0x180021010`

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
0x18000eb68  sub     rsp, 28h
0x18000eb6c  mov     rcx, [rcx]
0x18000eb6f  test    rcx, rcx
0x18000eb72  jz      short loc_18000EB81
0x18000eb74  mov     rax, [rcx]
0x18000eb77  mov     rax, [rax+10h]
0x18000eb7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eb80  nop
0x18000eb81  add     rsp, 28h
0x18000eb85  retn
```
