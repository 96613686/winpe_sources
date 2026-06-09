# ATL::CComQIPtr<ITaskHandlerStatus,&__s_GUID const _GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a>::~CComQIPtr<ITaskHandlerStatus,&__s_GUID const _GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a>(void)

- ea: `0x1400374e8`
- end: `0x140037506`
- name: `??1?$CComQIPtr@UITaskHandlerStatus@@$1?_GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a@@3U__s_GUID@@B@ATL@@QEAA@XZ`
- size: `30`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x140040631`
- `0x140040643`

## callees

- `0x1400374e8`
- `0x140041010`

## pseudocode

```c
__int64 __fastcall ATL::CComQIPtr<ITaskHandlerStatus,&__s_GUID const _GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a>::~CComQIPtr<ITaskHandlerStatus,&__s_GUID const _GUID_eaec7a8f_27a0_4ddc_8675_14726a01a38a>(
        __int64 *a1)
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
0x1400374e8  sub     rsp, 28h
0x1400374ec  mov     rcx, [rcx]
0x1400374ef  test    rcx, rcx
0x1400374f2  jz      short loc_140037501
0x1400374f4  mov     rax, [rcx]
0x1400374f7  mov     rax, [rax+10h]
0x1400374fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140037500  nop
0x140037501  add     rsp, 28h
0x140037505  retn
```
