# ??$wait_for_completed@UIAsyncAction@Foundation@Windows@winrt@@@impl@winrt@@YA?A_PAEBUIAsyncAction@Foundation@Windows@1@I@Z

- ea: `0x180004d78`
- end: `0x180004e5f`
- name: `??$wait_for_completed@UIAsyncAction@Foundation@Windows@winrt@@@impl@winrt@@YA?A_PAEBUIAsyncAction@Foundation@Windows@1@I@Z`
- size: `231`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000ec24`

## callees

- `0x180002324`
- `0x180002e70`
- `0x180002f2d`
- `0x180004d78`
- `0x18000f214`
- `0x18000f440`
- `0x18000f544`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall winrt::impl::wait_for_completed<winrt::Windows::Foundation::IAsyncAction>(__int64 *a1)
{
  const struct winrt::impl::slim_source_location *v2; // rdx
  HANDLE EventW; // rsi
  __int64 v4; // rcx
  int v5; // eax
  unsigned int v6; // ebx
  char *v8; // [rsp+20h] [rbp-30h] BYREF
  __int128 v9; // [rsp+28h] [rbp-28h]
  int v10; // [rsp+38h] [rbp-18h] BYREF
  __int128 v11; // [rsp+40h] [rbp-10h]
  char *v12; // [rsp+80h] [rbp+30h]

  LODWORD(v8) = 0;
  v9 = 0;
  EventW = WINRT_IMPL_CreateEventW(0, 1, 0, 0);
  if ( !EventW )
    winrt::throw_last_error((winrt *)&v8, v2);
  v12 = (char *)operator new(0x20u);
  *((_DWORD *)v12 + 2) = 1;
  *((_QWORD *)v12 + 2) = EventW;
  *((_DWORD *)v12 + 6) = 0;
  _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
  *(_QWORD *)v12 = ___7__delegate_UAsyncActionCompletedHandler_Foundation_Windows_winrt__Ushared_type__1____wait_for_completed_UIAsyncAction_Foundation_Windows_winrt___impl_4_YA_A_PAEBUIAsyncAction_234_I_Z__impl_winrt__6B_;
  v8 = v12;
  *(_QWORD *)&v9 = v12 + 16;
  v4 = *a1;
  v10 = 0;
  v11 = 0;
  v5 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 48LL))(v4);
  if ( v5 < 0 )
    winrt::throw_hresult((unsigned int)v5, &v10);
  WaitForSingleObject_0(*((HANDLE *)v12 + 2), 0xFFFFFFFF);
  v6 = *((_DWORD *)v12 + 6);
  winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v8);
  return v6;
}

```

## disassembly

```asm
0x180004d78  mov     [rsp-18h+arg_0], rbx
0x180004d7d  mov     [rsp-18h+arg_18], rsi
0x180004d82  push    rbp
0x180004d83  push    rdi
0x180004d84  push    r14
0x180004d86  mov     rbp, rsp
0x180004d89  sub     rsp, 50h
0x180004d8d  mov     r14, rcx
0x180004d90  mov     dword ptr [rbp+var_30], 0
0x180004d97  xorps   xmm0, xmm0
0x180004d9a  movdqu  [rbp+var_28], xmm0
0x180004d9f  xor     r9d, r9d; lpName
0x180004da2  xor     r8d, r8d; bInitialState
0x180004da5  lea     edi, [r9+1]
0x180004da9  mov     edx, edi; bManualReset
0x180004dab  xor     ecx, ecx; lpEventAttributes
0x180004dad  call    WINRT_IMPL_CreateEventW
0x180004db2  mov     rsi, rax
0x180004db5  test    rax, rax
0x180004db8  jz      loc_180004E55
0x180004dbe  mov     [rbp+var_30], rax
0x180004dc2  xor     ebx, ebx
0x180004dc4  mov     qword ptr [rbp+var_28], rbx
0x180004dc8  lea     ecx, [rdi+1Fh]; Size
0x180004dcb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004dd0  mov     rdx, rax
0x180004dd3  mov     [rbp+arg_10], rax
0x180004dd7  mov     [rax+8], edi
0x180004dda  lea     rdi, [rax+10h]
0x180004dde  mov     [rdi], rsi
0x180004de1  mov     [rdi+8], ebx
0x180004de4  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180004deb  lea     rax, ??_7?$delegate@UAsyncActionCompletedHandler@Foundation@Windows@winrt@@Ushared_type@?1???$wait_for_completed@UIAsyncAction@Foundation@Windows@winrt@@@impl@4@YA?A_PAEBUIAsyncAction@234@I@Z@@impl@winrt@@6B@
0x180004df2  mov     [rdx], rax
0x180004df5  mov     [rbp+var_30], rdx
0x180004df9  mov     qword ptr [rbp+var_28], rdi
0x180004dfd  mov     rcx, [r14]
0x180004e00  mov     [rbp+var_18], ebx
0x180004e03  xorps   xmm0, xmm0
0x180004e06  movdqu  [rbp+var_10], xmm0
0x180004e0b  mov     rax, [rcx]
0x180004e0e  mov     rax, [rax+30h]
0x180004e12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e17  test    eax, eax
0x180004e19  js      short loc_180004E49
0x180004e1b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180004e1e  mov     rcx, [rdi]; hHandle
0x180004e21  call    WaitForSingleObject_0
0x180004e26  mov     ebx, [rdi+8]
0x180004e29  lea     rcx, [rbp+var_30]
0x180004e2d  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180004e32  mov     eax, ebx
0x180004e34  lea     r11, [rsp+50h+var_s0]
0x180004e39  mov     rbx, [r11+20h]
0x180004e3d  mov     rsi, [r11+38h]
0x180004e41  mov     rsp, r11
0x180004e44  pop     r14
0x180004e46  pop     rdi
0x180004e47  pop     rbp
0x180004e48  retn
0x180004e49  lea     rdx, [rbp+var_18]
0x180004e4d  mov     ecx, eax
0x180004e4f  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180004e55  lea     rcx, [rbp+var_30]; this
0x180004e59  call    ?throw_last_error@winrt@@YAXAEBUslim_source_location@impl@1@@Z; winrt::throw_last_error(winrt::impl::slim_source_location const &)
```
