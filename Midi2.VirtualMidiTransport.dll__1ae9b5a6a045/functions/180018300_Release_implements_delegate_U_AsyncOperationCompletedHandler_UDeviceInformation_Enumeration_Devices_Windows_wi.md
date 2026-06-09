# ?Release@?$implements_delegate@U?$AsyncOperationCompletedHandler@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@Ushared_type@?1???$wait_for_completed@U?$IAsyncOperation@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@@impl@4@YA?A_PAEBU?$IAsyncOperation@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@234@I@Z@@impl@winrt@@UEAAIXZ

- ea: `0x180018300`
- end: `0x18001836d`
- name: `?Release@?$implements_delegate@U?$AsyncOperationCompletedHandler@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@Ushared_type@?1???$wait_for_completed@U?$IAsyncOperation@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@@impl@4@YA?A_PAEBU?$IAsyncOperation@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@234@I@Z@@impl@winrt@@UEAAIXZ`
- size: `109`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180003914`
- `0x180004754`
- `0x180018300`
- `0x1800194a0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180018366`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180018366`

## pseudocode

```c
__int64 __fastcall _Release___implements_delegate_U__AsyncOperationCompletedHandler_UDeviceInformation_Enumeration_Devices_Windows_winrt___Foundation_Windows_winrt__Ushared_type__1____wait_for_completed_U__IAsyncOperation_UDeviceInformation_Enumeration_Devices_Windows_winrt___Foundation_Windows_winrt___impl_4_YA_A_PAEBU__IAsyncOperation_UDeviceInformation_Enumeration_Devices_Windows_winrt___234_I_Z__impl_winrt__UEAAIXZ(
        _QWORD *Block)
{
  unsigned int v2; // edi
  void *v3; // rcx

  v2 = winrt::impl::implements_delegate_base::decrement_reference((winrt::impl::implements_delegate_base *)(Block + 1));
  if ( !v2 && Block )
  {
    if ( _InterlockedDecrement(&`winrt::get_module_lock'::`2'::s_lock) < 0 )
      abort();
    v3 = (void *)Block[2];
    if ( v3 )
    {
      WINRT_IMPL_CloseHandle(v3);
      Block[2] = 0;
    }
    operator delete(Block);
  }
  return v2;
}

```

## disassembly

```asm
0x180018300  mov     [rsp+arg_0], rbx
0x180018305  push    rdi
0x180018306  sub     rsp, 20h
0x18001830a  mov     rbx, rcx
0x18001830d  add     rcx, 8; this
0x180018311  call    ?decrement_reference@implements_delegate_base@impl@winrt@@QEAAIXZ; winrt::impl::implements_delegate_base::decrement_reference(void)
0x180018316  mov     edi, eax
0x180018318  test    eax, eax
0x18001831a  jnz     short loc_180018355
0x18001831c  test    rbx, rbx
0x18001831f  jz      short loc_180018355
0x180018321  or      edx, 0FFFFFFFFh
0x180018324  lock xadd cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A, edx; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18001832c  sub     edx, 1
0x18001832f  jnz     short loc_180018362
0x180018331  nop
0x180018332  mov     rcx, [rbx+10h]; hObject
0x180018336  test    rcx, rcx
0x180018339  jz      short loc_180018348
0x18001833b  call    WINRT_IMPL_CloseHandle
0x180018340  mov     qword ptr [rbx+10h], 0
0x180018348  mov     edx, 20h ; ' '
0x18001834d  mov     rcx, rbx; Block
0x180018350  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180018355  mov     rbx, [rsp+28h+arg_0]
0x18001835a  mov     eax, edi
0x18001835c  add     rsp, 20h
0x180018360  pop     rdi
0x180018361  retn
0x180018362  test    edx, edx
0x180018364  jns     short loc_180018332
0x180018366  call    cs:__imp_abort
```
