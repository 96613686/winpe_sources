# winrt::impl::make_agile_delegate<winrt::Windows::Foundation::AsyncOperationCompletedHandler<uint>>(winrt::Windows::Foundation::AsyncOperationCompletedHandler<uint> const &)

- ea: `0x180005be0`
- end: `0x180005d2e`
- name: `??$make_agile_delegate@U?$AsyncOperationCompletedHandler@I@Foundation@Windows@winrt@@@impl@winrt@@YA?AU?$AsyncOperationCompletedHandler@I@Foundation@Windows@1@AEBU2341@@Z`
- size: `334`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800097e0`

## callees

- `0x180001570`
- `0x18000197c`
- `0x180002109`
- `0x180005be0`
- `0x18000a014`
- `0x18000d010`

## pseudocode

```c
_QWORD *__fastcall winrt::impl::make_agile_delegate<winrt::Windows::Foundation::AsyncOperationCompletedHandler<unsigned int>>(
        _QWORD *a1,
        _QWORD *a2)
{
  void (__fastcall ***v4)(_QWORD, __int64 *, __int64 *); // rcx
  __int64 v5; // rax
  char v6; // si
  void (__fastcall ***v7)(_QWORD, __int64 *, __int64 *); // rcx
  __int64 v8; // rsi
  __int128 v9; // xmm6
  char *v10; // rax
  __int64 v11; // rcx
  __int64 v13; // [rsp+20h] [rbp-40h] BYREF
  __int64 v14; // [rsp+28h] [rbp-38h] BYREF
  __int128 v15; // [rsp+30h] [rbp-30h] BYREF

  v4 = (void (__fastcall ***)(_QWORD, __int64 *, __int64 *))*a2;
  v14 = 0;
  if ( !v4 )
  {
    v5 = 0;
LABEL_3:
    v6 = 0;
    goto LABEL_4;
  }
  (**v4)(v4, &winrt::impl::guid_v<winrt::impl::IAgileObject>, &v14);
  v5 = v14;
  if ( !v14 )
    goto LABEL_3;
  v6 = 1;
LABEL_4:
  if ( v5 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v14);
  if ( v6 )
  {
    v7 = (void (__fastcall ***)(_QWORD, __int64 *, __int64 *))*a2;
    *a1 = *a2;
    if ( v7 )
      ((void (__fastcall *)(void (__fastcall ***)(_QWORD, __int64 *, __int64 *)))(*v7)[1])(v7);
  }
  else
  {
    v15 = winrt::impl::guid_v<winrt::Windows::Foundation::AsyncOperationCompletedHandler<unsigned int>>;
    v13 = 0;
    WINRT_IMPL_RoGetAgileReference(0, &v15, *a2, &v13);
    v8 = v13;
    if ( v13 )
    {
      v13 = 0;
      v9 = v15;
      v10 = (char *)operator new(0x28u);
      *((_DWORD *)v10 + 2) = 1;
      *((_QWORD *)v10 + 2) = v8;
      *(_OWORD *)(v10 + 24) = v9;
      _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
      *(_QWORD *)v10 = &winrt::impl::delegate<winrt::Windows::Foundation::AsyncOperationCompletedHandler<unsigned int>,_lambda_574d5987c64a6b3f18218f4a51f47ca3_>::`vftable';
      *a1 = v10;
    }
    else
    {
      v11 = *a2;
      *a1 = *a2;
      if ( !v11 )
        return a1;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 8LL))(v11);
    }
    if ( v13 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v13);
  }
  return a1;
}

```

## disassembly

```asm
0x180005be0  mov     [rsp-18h+arg_10], rbx
0x180005be5  push    rbp
0x180005be6  push    rsi
0x180005be7  push    rdi
0x180005be8  mov     rbp, rsp
0x180005beb  sub     rsp, 60h
0x180005bef  movaps  [rsp+60h+var_10], xmm6
0x180005bf4  mov     rax, cs:__security_cookie
0x180005bfb  xor     rax, rsp
0x180005bfe  mov     [rbp+var_20], rax
0x180005c02  mov     rdi, rdx
0x180005c05  mov     rbx, rcx
0x180005c08  mov     rcx, [rdx]
0x180005c0b  mov     [rbp+var_38], 0
0x180005c13  test    rcx, rcx
0x180005c16  jnz     short loc_180005C50
0x180005c18  xor     eax, eax
0x180005c1a  xor     sil, sil
0x180005c1d  test    rax, rax
0x180005c20  jz      short loc_180005C2B
0x180005c22  lea     rcx, [rbp+var_38]
0x180005c26  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180005c2b  test    sil, sil
0x180005c2e  jz      short loc_180005C78
0x180005c30  mov     rcx, [rdi]
0x180005c33  mov     [rbx], rcx
0x180005c36  test    rcx, rcx
0x180005c39  jz      loc_180005D0A
0x180005c3f  mov     rax, [rcx]
0x180005c42  mov     rax, [rax+8]
0x180005c46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c4b  jmp     loc_180005D0A
0x180005c50  mov     rax, [rcx]
0x180005c53  lea     r8, [rbp+var_38]
0x180005c57  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x180005c5e  mov     rax, [rax]
0x180005c61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c66  mov     rax, [rbp+var_38]
0x180005c6a  mov     [rbp+var_38], rax
0x180005c6e  test    rax, rax
0x180005c71  jz      short loc_180005C1A
0x180005c73  mov     sil, 1
0x180005c76  jmp     short loc_180005C1D
0x180005c78  movups  xmm0, cs:??$guid_v@U?$AsyncOperationCompletedHandler@I@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::AsyncOperationCompletedHandler<uint>>
0x180005c7f  movdqu  [rbp+var_30], xmm0
0x180005c84  mov     [rbp+var_40], 0
0x180005c8c  lea     r9, [rbp+var_40]
0x180005c90  mov     r8, [rdi]
0x180005c93  lea     rdx, [rbp+var_30]
0x180005c97  xor     ecx, ecx
0x180005c99  call    WINRT_IMPL_RoGetAgileReference
0x180005c9e  mov     rsi, [rbp+var_40]
0x180005ca2  test    rsi, rsi
0x180005ca5  jz      short loc_180005CE3
0x180005ca7  mov     [rbp+var_40], 0
0x180005caf  movups  xmm6, [rbp+var_30]
0x180005cb3  mov     ecx, 28h ; '('; Size
0x180005cb8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005cbd  mov     dword ptr [rax+8], 1
0x180005cc4  mov     [rax+10h], rsi
0x180005cc8  movdqu  xmmword ptr [rax+18h], xmm6
0x180005ccd  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180005cd4  lea     rcx, ??_7?$delegate@U?$AsyncOperationCompletedHandler@I@Foundation@Windows@winrt@@V_lambda_574d5987c64a6b3f18218f4a51f47ca3_@@@impl@winrt@@6B@; const winrt::impl::delegate<winrt::Windows::Foundation::AsyncOperationCompletedHandler<uint>,_lambda_574d5987c64a6b3f18218f4a51f47ca3_>::`vftable'
0x180005cdb  mov     [rax], rcx
0x180005cde  mov     [rbx], rax
0x180005ce1  jmp     short loc_180005CFA
0x180005ce3  mov     rcx, [rdi]
0x180005ce6  mov     [rbx], rcx
0x180005ce9  test    rcx, rcx
0x180005cec  jz      short loc_180005D0A
0x180005cee  mov     rdx, [rcx]
0x180005cf1  mov     rax, [rdx+8]
0x180005cf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005cfa  cmp     [rbp+var_40], 0
0x180005cff  jz      short loc_180005D0A
0x180005d01  lea     rcx, [rbp+var_40]
0x180005d05  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180005d0a  mov     rax, rbx
0x180005d0d  mov     rcx, [rbp+var_20]
0x180005d11  xor     rcx, rsp; StackCookie
0x180005d14  call    __security_check_cookie
0x180005d19  mov     rbx, [rsp+60h+arg_10]
0x180005d21  movaps  xmm6, [rsp+60h+var_10]
0x180005d26  add     rsp, 60h
0x180005d2a  pop     rdi
0x180005d2b  pop     rsi
0x180005d2c  pop     rbp
0x180005d2d  retn
```
