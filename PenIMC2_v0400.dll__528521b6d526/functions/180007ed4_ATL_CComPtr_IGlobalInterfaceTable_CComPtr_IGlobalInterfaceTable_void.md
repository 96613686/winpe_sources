# ATL::CComPtr<IGlobalInterfaceTable>::~CComPtr<IGlobalInterfaceTable>(void)

- ea: `0x180007ed4`
- end: `0x180007ef8`
- name: `??1?$CComPtr@UIGlobalInterfaceTable@@@ATL@@QEAA@XZ`
- size: `36`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000ea28`
- `0x18000ea40`
- `0x18000eaa2`
- `0x18000ead2`

## callees

- `0x180007ed4`
- `0x18000e4a0`

## pseudocode

```c
__int64 __fastcall ATL::CComPtr<IGlobalInterfaceTable>::~CComPtr<IGlobalInterfaceTable>(__int64 *a1)
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
0x180007ed4  mov     [rsp+arg_0], rcx
0x180007ed9  sub     rsp, 28h
0x180007edd  mov     rcx, [rcx]
0x180007ee0  test    rcx, rcx
0x180007ee3  jz      short loc_180007EF3
0x180007ee5  mov     rax, [rcx]
0x180007ee8  mov     rax, [rax+10h]
0x180007eec  call    cs:__guard_dispatch_icall_fptr
0x180007ef2  nop
0x180007ef3  add     rsp, 28h
0x180007ef7  retn
```
