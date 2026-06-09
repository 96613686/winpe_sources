# ?Release@?$implements_delegate@U?$AsyncOperationCompletedHandler@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@Ushared_type@?1???$wait_for_completed@U?$IAsyncOperation@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@@impl@4@YA?A_PAEBU?$IAsyncOperation@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@234@I@Z@@impl@winrt@@UEAAIXZ

- ea: `0x180010390`
- end: `0x1800103fd`
- name: `?Release@?$implements_delegate@U?$AsyncOperationCompletedHandler@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@Ushared_type@?1???$wait_for_completed@U?$IAsyncOperation@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@Foundation@Windows@winrt@@@impl@4@YA?A_PAEBU?$IAsyncOperation@UDeviceInformation@Enumeration@Devices@Windows@winrt@@@234@I@Z@@impl@winrt@@UEAAIXZ`
- size: `109`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180002e94`
- `0x180003aec`
- `0x180010390`
- `0x180010f80`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800103f6`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800103f6`

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
0x180010390  mov     [rsp+arg_0], rbx
0x180010395  push    rdi
0x180010396  sub     rsp, 20h
0x18001039a  mov     rbx, rcx
0x18001039d  add     rcx, 8; this
0x1800103a1  call    ?decrement_reference@implements_delegate_base@impl@winrt@@QEAAIXZ; winrt::impl::implements_delegate_base::decrement_reference(void)
0x1800103a6  mov     edi, eax
0x1800103a8  test    eax, eax
0x1800103aa  jnz     short loc_1800103E5
0x1800103ac  test    rbx, rbx
0x1800103af  jz      short loc_1800103E5
0x1800103b1  or      edx, 0FFFFFFFFh
0x1800103b4  lock xadd cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A, edx; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x1800103bc  sub     edx, 1
0x1800103bf  jnz     short loc_1800103F2
0x1800103c1  nop
0x1800103c2  mov     rcx, [rbx+10h]; hObject
0x1800103c6  test    rcx, rcx
0x1800103c9  jz      short loc_1800103D8
0x1800103cb  call    WINRT_IMPL_CloseHandle
0x1800103d0  mov     qword ptr [rbx+10h], 0
0x1800103d8  mov     edx, 20h ; ' '
0x1800103dd  mov     rcx, rbx; Block
0x1800103e0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800103e5  mov     rbx, [rsp+28h+arg_0]
0x1800103ea  mov     eax, edi
0x1800103ec  add     rsp, 20h
0x1800103f0  pop     rdi
0x1800103f1  retn
0x1800103f2  test    edx, edx
0x1800103f4  jns     short loc_1800103C2
0x1800103f6  call    cs:__imp_abort
```
