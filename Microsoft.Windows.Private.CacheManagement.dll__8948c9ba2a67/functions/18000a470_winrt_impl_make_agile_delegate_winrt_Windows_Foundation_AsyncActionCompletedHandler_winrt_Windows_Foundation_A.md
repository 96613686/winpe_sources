# winrt::impl::make_agile_delegate<winrt::Windows::Foundation::AsyncActionCompletedHandler>(winrt::Windows::Foundation::AsyncActionCompletedHandler const &)

- ea: `0x18000a470`
- end: `0x18000a5c7`
- name: `??$make_agile_delegate@UAsyncActionCompletedHandler@Foundation@Windows@winrt@@@impl@winrt@@YA?AUAsyncActionCompletedHandler@Foundation@Windows@1@AEBU2341@@Z`
- size: `343`
- prototype: `_QWORD *__fastcall(_QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180008c70`

## callees

- `0x180003840`
- `0x18000a470`
- `0x1800181b0`
- `0x1800181fc`
- `0x18001c795`
- `0x18001cdf0`

## pseudocode

```c
_QWORD *__fastcall winrt::impl::make_agile_delegate<winrt::Windows::Foundation::AsyncActionCompletedHandler>(
        _QWORD *a1,
        _QWORD *a2)
{
  void (__fastcall ***v4)(_QWORD, __int64 *, __int128 *); // rcx
  bool v5; // si
  void (__fastcall ***v6)(_QWORD, __int64 *, __int128 *); // rcx
  __int64 v7; // rsi
  char *v8; // rax
  __int64 v9; // rcx
  __int128 v11; // [rsp+20h] [rbp-38h] BYREF
  __int64 v12; // [rsp+30h] [rbp-28h] BYREF
  __int128 v13; // [rsp+38h] [rbp-20h] BYREF

  v4 = (void (__fastcall ***)(_QWORD, __int64 *, __int128 *))*a2;
  if ( !*a2 )
    goto LABEL_7;
  *(_QWORD *)&v11 = 0;
  (**v4)(v4, &winrt::impl::guid_v<winrt::impl::IAgileObject>, &v11);
  v5 = (_QWORD)v11 != 0;
  if ( (_QWORD)v11 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v11);
  if ( v5 )
  {
    v6 = (void (__fastcall ***)(_QWORD, __int64 *, __int128 *))*a2;
    *a1 = *a2;
    if ( v6 )
      ((void (__fastcall *)(void (__fastcall ***)(_QWORD, __int64 *, __int128 *)))(*v6)[1])(v6);
  }
  else
  {
LABEL_7:
    v13 = winrt::impl::guid_v<winrt::Windows::Foundation::AsyncActionCompletedHandler>;
    v12 = 0;
    WINRT_IMPL_RoGetAgileReference(0, &v13, *a2, &v12);
    v7 = v12;
    if ( v12 )
    {
      v12 = 0;
      v11 = v13;
      v8 = (char *)operator new(0x28u);
      *((_DWORD *)v8 + 2) = 1;
      *((_QWORD *)v8 + 2) = v7;
      *(_OWORD *)(v8 + 24) = v11;
      _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
      *(_QWORD *)v8 = &winrt::impl::delegate<winrt::Windows::Foundation::AsyncActionCompletedHandler,_lambda_dc4921c5914f1dac0ac69065375e73ef_>::`vftable';
      *a1 = v8;
    }
    else
    {
      v9 = *a2;
      *a1 = *a2;
      if ( !v9 )
        return a1;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 8LL))(v9);
    }
    if ( v12 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v12);
  }
  return a1;
}

```

## disassembly

```asm
0x18000a470  mov     [rsp+arg_10], rbx
0x18000a475  mov     [rsp+arg_18], rsi
0x18000a47a  push    rdi
0x18000a47b  sub     rsp, 50h
0x18000a47f  mov     rax, cs:__security_cookie
0x18000a486  xor     rax, rsp
0x18000a489  mov     [rsp+58h+var_10], rax
0x18000a48e  mov     rdi, rdx
0x18000a491  mov     rbx, rcx
0x18000a494  mov     rcx, [rdx]
0x18000a497  test    rcx, rcx
0x18000a49a  jz      short loc_18000A503
0x18000a49c  mov     qword ptr [rsp+58h+var_38], 0
0x18000a4a5  mov     rax, [rcx]
0x18000a4a8  lea     r8, [rsp+58h+var_38]
0x18000a4ad  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18000a4b4  mov     rax, [rax]
0x18000a4b7  call    cs:__guard_dispatch_icall_fptr
0x18000a4bd  mov     rax, qword ptr [rsp+58h+var_38]
0x18000a4c2  mov     qword ptr [rsp+58h+var_38], rax
0x18000a4c7  test    rax, rax
0x18000a4ca  setnz   sil
0x18000a4ce  test    rax, rax
0x18000a4d1  jz      short loc_18000A4DD
0x18000a4d3  lea     rcx, [rsp+58h+var_38]
0x18000a4d8  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000a4dd  test    sil, sil
0x18000a4e0  jz      short loc_18000A503
0x18000a4e2  mov     rcx, [rdi]
0x18000a4e5  mov     [rbx], rcx
0x18000a4e8  test    rcx, rcx
0x18000a4eb  jz      loc_18000A5A7
0x18000a4f1  mov     rdx, [rcx]
0x18000a4f4  mov     rax, [rdx+8]
0x18000a4f8  call    cs:__guard_dispatch_icall_fptr
0x18000a4fe  jmp     loc_18000A5A7
0x18000a503  movups  xmm0, cs:??$guid_v@UAsyncActionCompletedHandler@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::AsyncActionCompletedHandler>
0x18000a50a  movups  [rsp+58h+var_20], xmm0
0x18000a50f  mov     [rsp+58h+var_28], 0
0x18000a518  lea     r9, [rsp+58h+var_28]
0x18000a51d  mov     r8, [rdi]
0x18000a520  lea     rdx, [rsp+58h+var_20]
0x18000a525  xor     ecx, ecx
0x18000a527  call    WINRT_IMPL_RoGetAgileReference
0x18000a52c  mov     rsi, [rsp+58h+var_28]
0x18000a531  test    rsi, rsi
0x18000a534  jz      short loc_18000A57D
0x18000a536  mov     [rsp+58h+var_28], 0
0x18000a53f  movups  xmm0, [rsp+58h+var_20]
0x18000a544  movups  [rsp+58h+var_38], xmm0
0x18000a549  mov     ecx, 28h ; '('; Size
0x18000a54e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a553  mov     dword ptr [rax+8], 1
0x18000a55a  mov     [rax+10h], rsi
0x18000a55e  movups  xmm0, [rsp+58h+var_38]
0x18000a563  movups  xmmword ptr [rax+18h], xmm0
0x18000a567  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18000a56e  lea     rcx, ??_7?$delegate@UAsyncActionCompletedHandler@Foundation@Windows@winrt@@V_lambda_dc4921c5914f1dac0ac69065375e73ef_@@@impl@winrt@@6B@; const winrt::impl::delegate<winrt::Windows::Foundation::AsyncActionCompletedHandler,_lambda_dc4921c5914f1dac0ac69065375e73ef_>::`vftable'
0x18000a575  mov     [rax], rcx
0x18000a578  mov     [rbx], rax
0x18000a57b  jmp     short loc_18000A595
0x18000a57d  mov     rcx, [rdi]
0x18000a580  mov     [rbx], rcx
0x18000a583  test    rcx, rcx
0x18000a586  jz      short loc_18000A5A7
0x18000a588  mov     rax, [rcx]
0x18000a58b  mov     rax, [rax+8]
0x18000a58f  call    cs:__guard_dispatch_icall_fptr
0x18000a595  cmp     [rsp+58h+var_28], 0
0x18000a59b  jz      short loc_18000A5A7
0x18000a59d  lea     rcx, [rsp+58h+var_28]
0x18000a5a2  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000a5a7  mov     rax, rbx
0x18000a5aa  mov     rcx, [rsp+58h+var_10]
0x18000a5af  xor     rcx, rsp; StackCookie
0x18000a5b2  call    __security_check_cookie
0x18000a5b7  mov     rbx, [rsp+58h+arg_10]
0x18000a5bc  mov     rsi, [rsp+58h+arg_18]
0x18000a5c1  add     rsp, 50h
0x18000a5c5  pop     rdi
0x18000a5c6  retn
```
