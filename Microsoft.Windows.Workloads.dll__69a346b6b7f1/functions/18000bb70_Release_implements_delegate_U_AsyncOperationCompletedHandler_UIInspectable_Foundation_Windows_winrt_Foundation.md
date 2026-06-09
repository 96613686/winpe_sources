# ?Release@?$implements_delegate@U?$AsyncOperationCompletedHandler@UIInspectable@Foundation@Windows@winrt@@@Foundation@Windows@winrt@@Ushared_type@?1???$wait_for_completed@U?$IAsyncOperation@UIInspectable@Foundation@Windows@winrt@@@Foundation@Windows@winrt@@@impl@4@YA?A_PAEBU?$IAsyncOperation@UIInspectable@Foundation@Windows@winrt@@@234@I@Z@@impl@winrt@@UEAAIXZ

- ea: `0x18000bb70`
- end: `0x18000bbde`
- name: `?Release@?$implements_delegate@U?$AsyncOperationCompletedHandler@UIInspectable@Foundation@Windows@winrt@@@Foundation@Windows@winrt@@Ushared_type@?1???$wait_for_completed@U?$IAsyncOperation@UIInspectable@Foundation@Windows@winrt@@@Foundation@Windows@winrt@@@impl@4@YA?A_PAEBU?$IAsyncOperation@UIInspectable@Foundation@Windows@winrt@@@234@I@Z@@impl@winrt@@UEAAIXZ`
- size: `110`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x18000bb70`
- `0x1800109c0`
- `0x180030b1b`
- `0x18003509c`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18000bbd7`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18000bbd7`

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
0x18000bb70  mov     [rsp+arg_8], rbx
0x18000bb75  push    rdi
0x18000bb76  sub     rsp, 20h
0x18000bb7a  mov     rbx, rcx
0x18000bb7d  add     rcx, 8; this
0x18000bb81  call    ?decrement_reference@implements_delegate_base@impl@winrt@@QEAAIXZ; winrt::impl::implements_delegate_base::decrement_reference(void)
0x18000bb86  mov     edi, eax
0x18000bb88  test    eax, eax
0x18000bb8a  jnz     short loc_18000BBC6
0x18000bb8c  test    rbx, rbx
0x18000bb8f  jz      short loc_18000BBC6
0x18000bb91  mov     ecx, 0FFFFFFFFh
0x18000bb96  lock xadd cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A, ecx; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18000bb9e  sub     ecx, 1
0x18000bba1  jnz     short loc_18000BBD3
0x18000bba3  mov     rcx, [rbx+10h]; hObject
0x18000bba7  test    rcx, rcx
0x18000bbaa  jz      short loc_18000BBB9
0x18000bbac  call    WINRT_IMPL_CloseHandle
0x18000bbb1  mov     qword ptr [rbx+10h], 0
0x18000bbb9  mov     edx, 20h ; ' '; unsigned __int64
0x18000bbbe  mov     rcx, rbx; void *
0x18000bbc1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000bbc6  mov     rbx, [rsp+28h+arg_8]
0x18000bbcb  mov     eax, edi
0x18000bbcd  add     rsp, 20h
0x18000bbd1  pop     rdi
0x18000bbd2  retn
0x18000bbd3  test    ecx, ecx
0x18000bbd5  jns     short loc_18000BBA3
0x18000bbd7  call    cs:__imp_abort
```
