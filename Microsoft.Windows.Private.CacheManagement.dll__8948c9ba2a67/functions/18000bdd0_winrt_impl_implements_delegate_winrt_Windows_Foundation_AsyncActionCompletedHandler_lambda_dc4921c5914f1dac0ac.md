# winrt::impl::implements_delegate<winrt::Windows::Foundation::AsyncActionCompletedHandler,_lambda_dc4921c5914f1dac0ac69065375e73ef_>::Release(void)

- ea: `0x18000bdd0`
- end: `0x18000be38`
- name: `?Release@?$implements_delegate@UAsyncActionCompletedHandler@Foundation@Windows@winrt@@V_lambda_dc4921c5914f1dac0ac69065375e73ef_@@@impl@winrt@@UEAAIXZ`
- size: `104`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180003840`
- `0x18000bdd0`
- `0x18000e800`
- `0x180018238`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18000be31`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18000be31`

## pseudocode

```c
__int64 __fastcall winrt::impl::implements_delegate<winrt::Windows::Foundation::AsyncActionCompletedHandler,_lambda_dc4921c5914f1dac0ac69065375e73ef_>::Release(
        _QWORD *a1)
{
  unsigned int v2; // edi

  v2 = winrt::impl::implements_delegate_base::decrement_reference((winrt::impl::implements_delegate_base *)(a1 + 1));
  if ( !v2 && a1 )
  {
    if ( _InterlockedDecrement(&`winrt::get_module_lock'::`2'::s_lock) < 0 )
      abort();
    if ( a1[2] )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 2);
    operator delete(a1);
  }
  return v2;
}

```

## disassembly

```asm
0x18000bdd0  mov     [rsp+arg_8], rbx
0x18000bdd5  push    rdi
0x18000bdd6  sub     rsp, 20h
0x18000bdda  mov     rbx, rcx
0x18000bddd  add     rcx, 8; this
0x18000bde1  call    ?decrement_reference@implements_delegate_base@impl@winrt@@QEAAIXZ; winrt::impl::implements_delegate_base::decrement_reference(void)
0x18000bde6  mov     edi, eax
0x18000bde8  test    eax, eax
0x18000bdea  jnz     short loc_18000BE20
0x18000bdec  test    rbx, rbx
0x18000bdef  jz      short loc_18000BE20
0x18000bdf1  mov     ecx, 0FFFFFFFFh
0x18000bdf6  lock xadd cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A, ecx; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18000bdfe  sub     ecx, 1
0x18000be01  jnz     short loc_18000BE2D
0x18000be03  cmp     qword ptr [rbx+10h], 0
0x18000be08  lea     rcx, [rbx+10h]
0x18000be0c  jz      short loc_18000BE13
0x18000be0e  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000be13  mov     edx, 28h ; '('; unsigned __int64
0x18000be18  mov     rcx, rbx; void *
0x18000be1b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000be20  mov     rbx, [rsp+28h+arg_8]
0x18000be25  mov     eax, edi
0x18000be27  add     rsp, 20h
0x18000be2b  pop     rdi
0x18000be2c  retn
0x18000be2d  test    ecx, ecx
0x18000be2f  jns     short loc_18000BE03
0x18000be31  call    cs:__imp_abort
```
