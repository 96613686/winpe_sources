# winrt::impl::implements_delegate<winrt::Windows::Foundation::AsyncOperationWithProgressCompletedHandler<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::impl::disconnect_aware_handler<1,winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,1>>>::Release(void)

- ea: `0x18001aa60`
- end: `0x18001aae3`
- name: `?Release@?$implements_delegate@U?$AsyncOperationWithProgressCompletedHandler@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@U?$disconnect_aware_handler@$00U?$await_adapter@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@$00@impl@winrt@@@impl@4@@impl@winrt@@UEAAIXZ`
- size: `131`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x1800040a0`
- `0x1800109c0`
- `0x18001a290`
- `0x18001aa60`
- `0x18003509c`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18001aadc`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18001aadc`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall winrt::impl::implements_delegate<winrt::Windows::Foundation::AsyncOperationWithProgressCompletedHandler<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::impl::disconnect_aware_handler<1,winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,1>>>::Release(
        __int64 *a1)
{
  unsigned int v2; // esi

  v2 = winrt::impl::implements_delegate_base::decrement_reference((winrt::impl::implements_delegate_base *)(a1 + 1));
  if ( !v2 && a1 )
  {
    if ( _InterlockedDecrement(&`winrt::get_module_lock'::`2'::s_lock) < 0 )
      abort();
    if ( a1[5] )
      winrt::impl::disconnect_aware_handler<1,winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,1>>::Complete(a1 + 2);
    if ( a1[2] )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 2);
    operator delete(a1);
  }
  return v2;
}

```

## disassembly

```asm
0x18001aa60  mov     [rsp+arg_8], rbx
0x18001aa65  mov     [rsp+arg_10], rsi
0x18001aa6a  push    rdi
0x18001aa6b  sub     rsp, 20h
0x18001aa6f  mov     rdi, rcx
0x18001aa72  add     rcx, 8; this
0x18001aa76  call    ?decrement_reference@implements_delegate_base@impl@winrt@@QEAAIXZ; winrt::impl::implements_delegate_base::decrement_reference(void)
0x18001aa7b  mov     esi, eax
0x18001aa7d  test    eax, eax
0x18001aa7f  jnz     short loc_18001AAC6
0x18001aa81  test    rdi, rdi
0x18001aa84  jz      short loc_18001AAC6
0x18001aa86  mov     ecx, 0FFFFFFFFh
0x18001aa8b  lock xadd cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A, ecx; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18001aa93  sub     ecx, 1
0x18001aa96  jnz     short loc_18001AAD8
0x18001aa98  cmp     qword ptr [rdi+28h], 0
0x18001aa9d  jz      short loc_18001AAA8
0x18001aa9f  lea     rcx, [rdi+10h]
0x18001aaa3  call    ?Complete@?$disconnect_aware_handler@$00U?$await_adapter@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@$00@impl@winrt@@@impl@winrt@@AEAAXXZ; winrt::impl::disconnect_aware_handler<1,winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,1>>::Complete(void)
0x18001aaa8  cmp     qword ptr [rdi+10h], 0
0x18001aaad  jz      short loc_18001AAB9
0x18001aaaf  lea     rcx, [rdi+10h]
0x18001aab3  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001aab8  nop
0x18001aab9  mov     edx, 30h ; '0'; unsigned __int64
0x18001aabe  mov     rcx, rdi; void *
0x18001aac1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001aac6  mov     eax, esi
0x18001aac8  mov     rbx, [rsp+28h+arg_8]
0x18001aacd  mov     rsi, [rsp+28h+arg_10]
0x18001aad2  add     rsp, 20h
0x18001aad6  pop     rdi
0x18001aad7  retn
0x18001aad8  test    ecx, ecx
0x18001aada  jns     short loc_18001AA98
0x18001aadc  call    cs:__imp_abort
```
