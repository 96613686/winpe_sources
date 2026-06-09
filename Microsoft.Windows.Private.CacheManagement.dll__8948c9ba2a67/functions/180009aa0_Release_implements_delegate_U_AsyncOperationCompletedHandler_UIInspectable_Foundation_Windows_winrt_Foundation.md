# ?Release@?$implements_delegate@U?$AsyncOperationCompletedHandler@UIInspectable@Foundation@Windows@winrt@@@Foundation@Windows@winrt@@Ushared_type@?1???$wait_for_completed@U?$IAsyncOperation@UIInspectable@Foundation@Windows@winrt@@@Foundation@Windows@winrt@@@impl@4@YA?A_PAEBU?$IAsyncOperation@UIInspectable@Foundation@Windows@winrt@@@234@I@Z@@impl@winrt@@UEAAIXZ

- ea: `0x180009aa0`
- end: `0x180009b0e`
- name: `?Release@?$implements_delegate@U?$AsyncOperationCompletedHandler@UIInspectable@Foundation@Windows@winrt@@@Foundation@Windows@winrt@@Ushared_type@?1???$wait_for_completed@U?$IAsyncOperation@UIInspectable@Foundation@Windows@winrt@@@Foundation@Windows@winrt@@@impl@4@YA?A_PAEBU?$IAsyncOperation@UIInspectable@Foundation@Windows@winrt@@@234@I@Z@@impl@winrt@@UEAAIXZ`
- size: `110`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180009aa0`
- `0x18000e800`
- `0x1800162bc`
- `0x180018238`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180009b07`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180009b07`

## pseudocode

```c
__int64 __fastcall _Release___implements_delegate_U__AsyncOperationCompletedHandler_UIInspectable_Foundation_Windows_winrt___Foundation_Windows_winrt__Ushared_type__1____wait_for_completed_U__IAsyncOperation_UIInspectable_Foundation_Windows_winrt___Foundation_Windows_winrt___impl_4_YA_A_PAEBU__IAsyncOperation_UIInspectable_Foundation_Windows_winrt___234_I_Z__impl_winrt__UEAAIXZ(
        _QWORD *a1)
{
  unsigned int v2; // edi
  void *v3; // rcx

  v2 = winrt::impl::implements_delegate_base::decrement_reference((winrt::impl::implements_delegate_base *)(a1 + 1));
  if ( !v2 && a1 )
  {
    if ( _InterlockedDecrement(&`winrt::get_module_lock'::`2'::s_lock) < 0 )
      abort();
    v3 = (void *)a1[2];
    if ( v3 )
    {
      WINRT_IMPL_CloseHandle(v3);
      a1[2] = 0;
    }
    operator delete(a1);
  }
  return v2;
}

```

## disassembly

```asm
0x180009aa0  mov     [rsp+arg_8], rbx
0x180009aa5  push    rdi
0x180009aa6  sub     rsp, 20h
0x180009aaa  mov     rbx, rcx
0x180009aad  add     rcx, 8; this
0x180009ab1  call    ?decrement_reference@implements_delegate_base@impl@winrt@@QEAAIXZ; winrt::impl::implements_delegate_base::decrement_reference(void)
0x180009ab6  mov     edi, eax
0x180009ab8  test    eax, eax
0x180009aba  jnz     short loc_180009AF6
0x180009abc  test    rbx, rbx
0x180009abf  jz      short loc_180009AF6
0x180009ac1  mov     ecx, 0FFFFFFFFh
0x180009ac6  lock xadd cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A, ecx; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180009ace  sub     ecx, 1
0x180009ad1  jnz     short loc_180009B03
0x180009ad3  mov     rcx, [rbx+10h]; hObject
0x180009ad7  test    rcx, rcx
0x180009ada  jz      short loc_180009AE9
0x180009adc  call    WINRT_IMPL_CloseHandle
0x180009ae1  mov     qword ptr [rbx+10h], 0
0x180009ae9  mov     edx, 20h ; ' '; unsigned __int64
0x180009aee  mov     rcx, rbx; void *
0x180009af1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180009af6  mov     rbx, [rsp+28h+arg_8]
0x180009afb  mov     eax, edi
0x180009afd  add     rsp, 20h
0x180009b01  pop     rdi
0x180009b02  retn
0x180009b03  test    ecx, ecx
0x180009b05  jns     short loc_180009AD3
0x180009b07  call    cs:__imp_abort
```
