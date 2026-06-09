# UsoPerformExpeditedWork(wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>,uint)

- ea: `0x180012c48`
- end: `0x180013068`
- name: `?UsoPerformExpeditedWork@@YAXV?$basic_zstring_view@_W@wil@@00I@Z`
- size: `1056`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `14`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800150a0`

## callees

- `0x18000bbd0`
- `0x18000f0a4`
- `0x18000fb9c`
- `0x180012c48`
- `0x180013070`
- `0x180018848`
- `0x18002d1a4`
- `0x18002eab4`
- `0x180033f14`
- `0x180035a50`
- `0x180036b10`
- `0x18003a274`
- `0x180056500`
- `0x18005c5e0`

## string_xrefs

- `0x180013043`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall UsoPerformExpeditedWork(const wchar_t **a1, __int128 *a2, __int128 *a3, int a4)
{
  int v7; // r14d
  int v8; // r15d
  bool v9; // r12
  __int64 traits_2_unsigned_short; // rax
  const char *v11; // r9
  __int64 v12; // r11
  __int64 v13; // rax
  __int64 v14; // rdx
  __int64 *v15; // rax
  __int64 v16; // rdx
  __int64 v17; // rbx
  __int64 v18; // rdx
  void (__fastcall ***v19)(_QWORD, __int64); // rcx
  __int64 v20; // rcx
  void (__fastcall ***v21)(_QWORD, __int64); // r8
  __int64 v22; // rbx
  __int64 v23; // rax
  __int64 v24; // rcx
  void (__fastcall ***v25)(_QWORD, __int64); // rcx
  __int64 v26; // rcx
  void (__fastcall ***v27)(_QWORD, __int64); // r8
  bool v28; // si
  bool v29; // di
  __int64 v30; // rbx
  int v31; // eax
  __int128 v32; // [rsp+50h] [rbp-59h] BYREF
  __int64 v33; // [rsp+60h] [rbp-49h]
  int v34[4]; // [rsp+70h] [rbp-39h] BYREF
  __int128 v35; // [rsp+80h] [rbp-29h] BYREF
  int v36; // [rsp+90h] [rbp-19h] BYREF
  __int64 v37; // [rsp+98h] [rbp-11h] BYREF
  int v38; // [rsp+A0h] [rbp-9h]
  char v39; // [rsp+A4h] [rbp-5h]
  bool v40; // [rsp+A5h] [rbp-4h]
  __int128 v41; // [rsp+B0h] [rbp+7h] BYREF
  __int64 v42; // [rsp+C0h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  v7 = -1;
  v8 = 0;
  v9 = 0;
  v37 = 0;
  v42 = 60LL * a4;
  traits_2_unsigned_short = anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                              L"https",
                              &dword_180068904,
                              0);
  if ( traits_2_unsigned_short == v12 || (v13 = (traits_2_unsigned_short - (__int64)L"https") >> 1, v13 == -1) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xC9,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
      v11);
  *(_QWORD *)&v41 = L"https";
  *((_QWORD *)&v41 + 1) = v13;
  v35 = *a3;
  if ( (unsigned __int8)Strings::istarts_with(&v35, &v41) )
  {
    v41 = 0;
    v35 = *a2;
    v32 = *a3;
    InstallAppForAllUsers(&v41, &v32, &v35);
    *(_QWORD *)&v35 = &v41;
    *((_QWORD *)&v35 + 1) = &v42;
    v15 = (__int64 *)std::async__UsoPerformExpeditedWork_::_7_::_lambda_1___(&v32, v14, &v35);
    v35 = 0;
    v17 = *v15;
    *v15 = 0;
    *(_QWORD *)&v35 = v17;
    BYTE8(v35) = 1;
    if ( !v17 || *(_BYTE *)(v17 + 184) )
      std::_Throw_future_error2(4);
    LOBYTE(v16) = 1;
    v7 = *(_DWORD *)(*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v17 + 16LL))(v17, v16);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v17 + 8), 0xFFFFFFFF) == 1 )
    {
      v19 = *(void (__fastcall ****)(_QWORD, __int64))(v17 + 200);
      if ( v19 )
        (**v19)(v19, v17);
      else
        (**(void (__fastcall ***)(__int64, __int64))v17)(v17, 1);
    }
    v20 = v32;
    if ( (_QWORD)v32 && !_InterlockedDecrement((volatile signed __int32 *)(v32 + 8)) )
    {
      v21 = *(void (__fastcall ****)(_QWORD, __int64))(v20 + 200);
      if ( v21 )
        (**v21)(*(_QWORD *)(v20 + 200), v20);
      else
        (**(void (__fastcall ***)(__int64, __int64))v20)(v20, 1);
    }
    if ( v7 )
    {
      v32 = 0u;
      v33 = 0x100000006LL;
    }
    else
    {
      *((_QWORD *)&v35 + 1) = 1;
      v22 = v41;
      *(_QWORD *)&v41 = 0;
      *(_QWORD *)&v35 = v22;
      if ( !v22 || *(_BYTE *)(v22 + 208) )
        std::_Throw_future_error2(4);
      LOBYTE(v18) = 1;
      v23 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v22 + 16LL))(v22, v18);
      LODWORD(v32) = *(_DWORD *)v23;
      v24 = *(_QWORD *)(v23 + 8);
      *(_QWORD *)(v23 + 8) = 0;
      *((_QWORD *)&v32 + 1) = v24;
      LODWORD(v33) = *(_DWORD *)(v23 + 16);
      WORD2(v33) = *(_WORD *)(v23 + 20);
      if ( !_InterlockedDecrement((volatile signed __int32 *)(v22 + 8)) )
      {
        v25 = *(void (__fastcall ****)(_QWORD, __int64))(v22 + 224);
        if ( v25 )
          (**v25)(v25, v22);
        else
          (**(void (__fastcall ***)(__int64, __int64))v22)(v22, 1);
      }
    }
    AppInstallResult::operator=(&v36, &v32);
    if ( *((_QWORD *)&v32 + 1) )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref((char *)&v32 + 8);
    v26 = v41;
    if ( (_QWORD)v41 && _InterlockedExchangeAdd((volatile signed __int32 *)(v41 + 8), 0xFFFFFFFF) == 1 )
    {
      v27 = *(void (__fastcall ****)(_QWORD, __int64))(v26 + 224);
      if ( v27 )
        (**v27)(*(_QWORD *)(v26 + 224), v26);
      else
        (**(void (__fastcall ***)(__int64, __int64))v26)(v26, 1);
    }
  }
  else
  {
    v32 = 0x80070057;
    v33 = 8;
    AppInstallResult::operator=(&v36, &v32);
    if ( *((_QWORD *)&v32 + 1) )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref((char *)&v32 + 8);
  }
  v28 = v40;
  v29 = v40 || !v39;
  v30 = v37;
  *(_QWORD *)&v41 = v37;
  if ( v37 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 8LL))(v37);
  if ( v30 )
  {
    v9 = 1;
    v34[0] = 0;
    v31 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v30 + 64LL))(v30, v34);
    if ( v31 < 0 )
      winrt::throw_hresult((unsigned int)v31);
    v8 = v34[0];
  }
  ClientCoreTelemetry::AppUpdateResult(*a1, v29, 1, v7, v28, v38, v36, v8, v9);
  ReportUOWorkCompleted(*a1, v29);
  if ( v30 )
  {
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v41);
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v37);
  }
}

```

## disassembly

```asm
0x180012c48  mov     [rsp-8+arg_18], rbx
0x180012c4d  push    rbp
0x180012c4e  push    rsi
0x180012c4f  push    rdi
0x180012c50  push    r12
0x180012c52  push    r13
0x180012c54  push    r14
0x180012c56  push    r15
0x180012c58  lea     rbp, [rsp-27h]
0x180012c5d  sub     rsp, 0D0h
0x180012c64  mov     rax, cs:__security_cookie
0x180012c6b  xor     rax, rsp
0x180012c6e  mov     [rbp+57h+var_38], rax
0x180012c72  mov     rbx, r8
0x180012c75  mov     rdi, rdx
0x180012c78  mov     r13, rcx
0x180012c7b  xor     esi, esi
0x180012c7d  or      r14d, 0FFFFFFFFh
0x180012c81  mov     r15d, esi
0x180012c84  mov     r12b, sil
0x180012c87  mov     [rbp+57h+var_68], rsi
0x180012c8b  movsxd  rax, r9d
0x180012c8e  imul    rcx, rax, 3Ch ; '<'
0x180012c92  mov     [rbp+57h+var_40], rcx
0x180012c96  xor     r8d, r8d
0x180012c99  lea     r11, dword_180068904
0x180012ca0  mov     rdx, r11
0x180012ca3  lea     rcx, aHttps; "https"
0x180012caa  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x180012caf  cmp     rax, r11
0x180012cb2  jz      loc_18001303F
0x180012cb8  lea     rcx, aHttps; "https"
0x180012cbf  sub     rax, rcx
0x180012cc2  sar     rax, 1
0x180012cc5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180012cc9  jz      loc_18001303F
0x180012ccf  mov     qword ptr [rbp+57h+var_50], rcx
0x180012cd3  mov     qword ptr [rbp+57h+var_50+8], rax
0x180012cd7  movaps  xmm0, xmmword ptr [rbx]
0x180012cda  movdqa  [rbp+57h+var_80], xmm0
0x180012cdf  lea     rdx, [rbp+57h+var_50]
0x180012ce3  lea     rcx, [rbp+57h+var_80]
0x180012ce7  call    ?istarts_with@Strings@@YA_NV?$basic_zstring_view@_W@wil@@0@Z; Strings::istarts_with(wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>)
0x180012cec  test    al, al
0x180012cee  jnz     short loc_180012D2D
0x180012cf0  mov     dword ptr [rbp+57h+var_B0], 80070057h
0x180012cf7  xor     eax, eax
0x180012cf9  mov     dword ptr [rbp+57h+var_B0+4], eax
0x180012cfc  mov     qword ptr [rbp+57h+var_B0+8], rsi
0x180012d00  mov     [rbp+57h+var_A0], 8
0x180012d08  lea     rdx, [rbp+57h+var_B0]
0x180012d0c  lea     rcx, [rbp+57h+var_70]
0x180012d10  call    ??4AppInstallResult@@QEAAAEAU0@$$QEAU0@@Z; AppInstallResult::operator=(AppInstallResult &&)
0x180012d15  cmp     qword ptr [rbp+57h+var_B0+8], rsi
0x180012d19  jz      loc_180012F51
0x180012d1f  lea     rcx, [rbp+57h+var_B0+8]
0x180012d23  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180012d28  jmp     loc_180012F51
0x180012d2d  xorps   xmm0, xmm0
0x180012d30  movups  [rbp+57h+var_50], xmm0
0x180012d34  movaps  xmm1, xmmword ptr [rdi]
0x180012d37  movdqa  [rbp+57h+var_80], xmm1
0x180012d3c  movaps  xmm0, xmmword ptr [rbx]
0x180012d3f  movdqa  [rbp+57h+var_B0], xmm0
0x180012d44  lea     r8, [rbp+57h+var_80]
0x180012d48  lea     rdx, [rbp+57h+var_B0]
0x180012d4c  lea     rcx, [rbp+57h+var_50]
0x180012d50  call    ?InstallAppForAllUsers@@YA?AV?$future@UAppInstallResult@@@std@@V?$basic_zstring_view@_W@wil@@0@Z; InstallAppForAllUsers(wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>)
0x180012d55  nop
0x180012d56  lea     rax, [rbp+57h+var_50]
0x180012d5a  mov     qword ptr [rbp+57h+var_80], rax
0x180012d5e  lea     rax, [rbp+57h+var_40]
0x180012d62  mov     qword ptr [rbp+57h+var_80+8], rax
0x180012d66  lea     r8, [rbp+57h+var_80]
0x180012d6a  lea     rcx, [rbp+57h+var_B0]
0x180012d6e  call    std__async__UsoPerformExpeditedWork____7____lambda_1___
0x180012d73  nop
0x180012d74  xorps   xmm0, xmm0
0x180012d77  movups  [rbp+57h+var_80], xmm0
0x180012d7b  mov     rbx, [rax]
0x180012d7e  mov     [rax], rsi
0x180012d81  mov     qword ptr [rbp+57h+var_80], rbx
0x180012d85  mov     byte ptr [rbp+57h+var_80+8], 1
0x180012d89  test    rbx, rbx
0x180012d8c  jz      loc_180013034
0x180012d92  cmp     [rbx+0B8h], sil
0x180012d99  jnz     loc_180013034
0x180012d9f  mov     rax, [rbx]
0x180012da2  mov     dl, 1
0x180012da4  mov     rcx, rbx
0x180012da7  mov     rax, [rax+10h]
0x180012dab  call    _guard_dispatch_icall
0x180012db0  mov     r14d, [rax]
0x180012db3  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180012db7  mov     eax, edi
0x180012db9  lock xadd [rbx+8], eax
0x180012dbe  add     eax, edi
0x180012dc0  jnz     short loc_180012DF2
0x180012dc2  mov     rcx, [rbx+0C8h]
0x180012dc9  test    rcx, rcx
0x180012dcc  jz      short loc_180012DDE
0x180012dce  mov     rax, [rcx]
0x180012dd1  mov     rdx, rbx
0x180012dd4  mov     rax, [rax]
0x180012dd7  call    _guard_dispatch_icall
0x180012ddc  jmp     short loc_180012DF2
0x180012dde  mov     rax, [rbx]
0x180012de1  mov     edx, 1
0x180012de6  mov     rcx, rbx
0x180012de9  mov     rax, [rax]
0x180012dec  call    _guard_dispatch_icall
0x180012df1  nop
0x180012df2  mov     rcx, qword ptr [rbp+57h+var_B0]
0x180012df6  test    rcx, rcx
0x180012df9  jz      short loc_180012E35
0x180012dfb  mov     eax, edi
0x180012dfd  lock xadd [rcx+8], eax
0x180012e02  add     eax, edi
0x180012e04  jnz     short loc_180012E35
0x180012e06  mov     r8, [rcx+0C8h]
0x180012e0d  test    r8, r8
0x180012e10  jz      short loc_180012E25
0x180012e12  mov     rax, [r8]
0x180012e15  mov     rdx, rcx
0x180012e18  mov     rcx, r8
0x180012e1b  mov     rax, [rax]
0x180012e1e  call    _guard_dispatch_icall
0x180012e23  jmp     short loc_180012E35
0x180012e25  mov     rax, [rcx]
0x180012e28  mov     edx, 1
0x180012e2d  mov     rax, [rax]
0x180012e30  call    _guard_dispatch_icall
0x180012e35  test    r14d, r14d
0x180012e38  jnz     loc_180012EDB
0x180012e3e  xorps   xmm0, xmm0
0x180012e41  movups  [rbp+57h+var_80], xmm0
0x180012e45  mov     rbx, qword ptr [rbp+57h+var_50]
0x180012e49  mov     qword ptr [rbp+57h+var_50], rsi
0x180012e4d  mov     qword ptr [rbp+57h+var_80], rbx
0x180012e51  mov     byte ptr [rbp+57h+var_80+8], 1
0x180012e55  test    rbx, rbx
0x180012e58  jz      loc_180013055
0x180012e5e  cmp     [rbx+0D0h], sil
0x180012e65  jnz     loc_180013055
0x180012e6b  mov     rax, [rbx]
0x180012e6e  mov     dl, 1
0x180012e70  mov     rcx, rbx
0x180012e73  mov     rax, [rax+10h]
0x180012e77  call    _guard_dispatch_icall
0x180012e7c  mov     ecx, [rax]
0x180012e7e  mov     dword ptr [rbp+57h+var_B0], ecx
0x180012e81  mov     rcx, [rax+8]
0x180012e85  mov     [rax+8], rsi
0x180012e89  mov     qword ptr [rbp+57h+var_B0+8], rcx
0x180012e8d  mov     ecx, [rax+10h]
0x180012e90  mov     dword ptr [rbp+57h+var_A0], ecx
0x180012e93  mov     cl, [rax+14h]
0x180012e96  mov     byte ptr [rbp+57h+var_A0+4], cl
0x180012e99  mov     al, [rax+15h]
0x180012e9c  mov     byte ptr [rbp+57h+var_A0+5], al
0x180012e9f  mov     eax, edi
0x180012ea1  lock xadd [rbx+8], eax
0x180012ea6  add     eax, edi
0x180012ea8  jnz     short loc_180012EF1
0x180012eaa  mov     rcx, [rbx+0E0h]
0x180012eb1  test    rcx, rcx
0x180012eb4  jz      short loc_180012EC6
0x180012eb6  mov     rax, [rcx]
0x180012eb9  mov     rdx, rbx
0x180012ebc  mov     rax, [rax]
0x180012ebf  call    _guard_dispatch_icall
0x180012ec4  jmp     short loc_180012EF1
0x180012ec6  mov     rax, [rbx]
0x180012ec9  mov     edx, 1
0x180012ece  mov     rcx, rbx
0x180012ed1  mov     rax, [rax]
0x180012ed4  call    _guard_dispatch_icall
0x180012ed9  jmp     short loc_180012EF1
0x180012edb  mov     qword ptr [rbp+57h+var_B0], rsi
0x180012edf  mov     qword ptr [rbp+57h+var_B0+8], rsi
0x180012ee3  mov     dword ptr [rbp+57h+var_A0], 6
0x180012eea  mov     dword ptr [rbp+57h+var_A0+4], 1
0x180012ef1  lea     rdx, [rbp+57h+var_B0]
0x180012ef5  lea     rcx, [rbp+57h+var_70]
0x180012ef9  call    ??4AppInstallResult@@QEAAAEAU0@$$QEAU0@@Z; AppInstallResult::operator=(AppInstallResult &&)
0x180012efe  cmp     qword ptr [rbp+57h+var_B0+8], rsi
0x180012f02  jz      short loc_180012F0E
0x180012f04  lea     rcx, [rbp+57h+var_B0+8]
0x180012f08  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180012f0d  nop
0x180012f0e  mov     rcx, qword ptr [rbp+57h+var_50]
0x180012f12  test    rcx, rcx
0x180012f15  jz      short loc_180012F51
0x180012f17  mov     eax, edi
0x180012f19  lock xadd [rcx+8], eax
0x180012f1e  add     eax, edi
0x180012f20  jnz     short loc_180012F51
0x180012f22  mov     r8, [rcx+0E0h]
0x180012f29  test    r8, r8
0x180012f2c  jz      short loc_180012F41
0x180012f2e  mov     rax, [r8]
0x180012f31  mov     rdx, rcx
0x180012f34  mov     rcx, r8
0x180012f37  mov     rax, [rax]
0x180012f3a  call    _guard_dispatch_icall
0x180012f3f  jmp     short loc_180012F51
0x180012f41  mov     rax, [rcx]
0x180012f44  mov     edx, 1
0x180012f49  mov     rax, [rax]
0x180012f4c  call    _guard_dispatch_icall
0x180012f51  mov     sil, [rbp+57h+var_5B]
0x180012f55  test    sil, sil
0x180012f58  jnz     short loc_180012F65
0x180012f5a  cmp     [rbp+57h+var_5C], sil
0x180012f5e  jz      short loc_180012F65
0x180012f60  xor     dil, dil
0x180012f63  jmp     short loc_180012F68
0x180012f65  mov     dil, 1
0x180012f68  mov     rbx, [rbp+57h+var_68]
0x180012f6c  mov     qword ptr [rbp+57h+var_50], rbx
0x180012f70  test    rbx, rbx
0x180012f73  jz      short loc_180012F85
0x180012f75  mov     rax, [rbx]
0x180012f78  mov     rcx, rbx
0x180012f7b  mov     rax, [rax+8]
0x180012f7f  call    _guard_dispatch_icall
0x180012f84  nop
0x180012f85  test    rbx, rbx
0x180012f88  jz      short loc_180012FB3
0x180012f8a  mov     r12b, 1
0x180012f8d  mov     [rbp+57h+var_90], 0
0x180012f94  mov     rax, [rbx]
0x180012f97  lea     rdx, [rbp+57h+var_90]
0x180012f9b  mov     rcx, rbx
0x180012f9e  mov     rax, [rax+40h]
0x180012fa2  call    _guard_dispatch_icall
0x180012fa7  test    eax, eax
0x180012fa9  js      loc_180013060
0x180012faf  mov     r15d, [rbp+57h+var_90]
0x180012fb3  mov     [rsp+100h+var_C0], r12b; bool
0x180012fb8  mov     [rsp+100h+var_C8], r15d; int
0x180012fbd  mov     eax, [rbp+57h+var_70]
0x180012fc0  mov     [rsp+100h+var_D0], eax; int
0x180012fc4  mov     eax, [rbp+57h+var_60]
0x180012fc7  mov     [rsp+100h+var_D8], eax; int
0x180012fcb  mov     [rsp+100h+var_E0], sil; bool
0x180012fd0  mov     r9d, r14d; int
0x180012fd3  mov     r8b, 1; bool
0x180012fd6  mov     dl, dil; bool
0x180012fd9  mov     rcx, [r13+0]; wchar_t *
0x180012fdd  call    ?AppUpdateResult@ClientCoreTelemetry@@SAXPEB_W_N1H1HJJ1@Z; ClientCoreTelemetry::AppUpdateResult(wchar_t const *,bool,bool,int,bool,int,long,long,bool)
0x180012fe2  movzx   edx, dil; int
0x180012fe6  mov     rcx, [r13+0]; wchar_t *
0x180012fea  call    ?ReportUOWorkCompleted@@YAXPEB_WH@Z; ReportUOWorkCompleted(wchar_t const *,int)
0x180012fef  nop
0x180012ff0  test    rbx, rbx
0x180012ff3  jz      short loc_180012FFF
0x180012ff5  lea     rcx, [rbp+57h+var_50]
0x180012ff9  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180012ffe  nop
0x180012fff  test    rbx, rbx
0x180013002  jz      short loc_18001300D
0x180013004  lea     rcx, [rbp+57h+var_68]
0x180013008  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001300d  mov     rcx, [rbp+57h+var_38]
0x180013011  xor     rcx, rsp; StackCookie
0x180013014  call    __security_check_cookie
0x180013019  mov     rbx, [rsp+100h+arg_18]
0x180013021  add     rsp, 0D0h
0x180013028  pop     r15
0x18001302a  pop     r14
0x18001302c  pop     r13
0x18001302e  pop     r12
0x180013030  pop     rdi
0x180013031  pop     rsi
0x180013032  pop     rbp
0x180013033  retn
0x180013034  mov     ecx, 4
0x180013039  call    ?_Throw_future_error2@std@@YAXW4future_errc@1@@Z; std::_Throw_future_error2(std::future_errc)
0x18001303f  mov     rcx, [rbp+5Fh]; this
0x180013043  lea     r8, aCW1SPackagesMi_0; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x18001304a  mov     edx, 0C9h; void *
0x18001304f  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180013055  mov     ecx, 4
0x18001305a  call    ?_Throw_future_error2@std@@YAXW4future_errc@1@@Z; std::_Throw_future_error2(std::future_errc)
0x180013060  mov     ecx, eax
0x180013062  call    ?throw_hresult@winrt@@YAXUhresult@1@@Z; winrt::throw_hresult(winrt::hresult)
```
