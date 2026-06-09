# Windows::Internal::XamlPopupWindowImpl::SetPopupCommands(uint,IPopupCommand * *)

- ea: `0x1800a2ad0`
- end: `0x1800a2d7f`
- name: `?SetPopupCommands@XamlPopupWindowImpl@Internal@Windows@@UEAAJIPEAPEAUIPopupCommand@@@Z`
- size: `687`
- prototype: `__int64 __fastcall(Windows::Internal::XamlPopupWindowImpl *__hidden this, unsigned int, struct IPopupCommand **)`
- caller_count: `0`
- callee_count: `13`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180021d80`
- `0x18002a974`
- `0x18003217c`
- `0x180034db4`
- `0x18003d858`
- `0x180046b40`
- `0x1800485b8`
- `0x180050ba0`
- `0x18009d848`
- `0x18009f688`
- `0x1800a2ad0`
- `0x1800a5570`
- `0x1800e5010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a2caf`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800a2caf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a2ba0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a2c74`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a2c9b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a2ba0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a2c74`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a2c9b`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Windows::Internal::XamlPopupWindowImpl::SetPopupCommands(
        Windows::Internal::XamlPopupWindowImpl *this,
        unsigned int a2,
        struct IPopupCommand **a3)
{
  unsigned int v4; // edi
  unsigned __int64 i; // rbx
  unsigned __int64 v7; // rax
  struct IPopupCommand *v8; // rdx
  __int64 v9; // rcx
  int v10; // eax
  unsigned int v11; // ebx
  __int64 v12; // rdx
  unsigned __int64 j; // r15
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, LPVOID *); // rbx
  int v16; // eax
  __int64 *v17; // rdi
  __int64 (__fastcall *v18)(__int64 *, __int64); // rbx
  int v19; // eax
  __int64 v20; // rdx
  __int64 *v21; // rdi
  __int64 v22; // r13
  const WCHAR *v23; // rbx
  unsigned __int64 v24; // rcx
  signed int v25; // eax
  unsigned int v26; // eax
  void (__fastcall *v28)(Windows::Internal::XamlPopupWindowImpl *, _QWORD); // rbx
  unsigned int *v29; // rax
  void (__fastcall *v30)(Windows::Internal::XamlPopupWindowImpl *, _QWORD); // rbx
  unsigned int *v31; // rax
  unsigned int v32; // [rsp+20h] [rbp-60h] BYREF
  __int64 *v33; // [rsp+28h] [rbp-58h] BYREF
  LPVOID pv; // [rsp+30h] [rbp-50h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+38h] [rbp-48h] BYREF
  __int64 v36; // [rsp+50h] [rbp-30h]
  HSTRING_HEADER v37; // [rsp+58h] [rbp-28h] BYREF
  __int64 v38; // [rsp+70h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]

  v4 = a2;
  if ( a2 >= *((_DWORD *)this + 30) )
    v4 = *((_DWORD *)this + 30);
  for ( i = 0; i < 5; ++i )
  {
    v7 = i;
    if ( i >= v4 )
      v8 = 0;
    else
      v8 = a3[v7];
    Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::operator=(
      (char *)this + v7 * 8 + 328,
      v8);
  }
  *((_DWORD *)this + 29) = v4;
  v33 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
  v10 = Windows::Foundation::Collections::Internal::detail::CreateExternalVector<HSTRING__ *,Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<HSTRING__ *>>>(
          v9,
          &v33);
  v11 = v10;
  if ( v10 < 0 )
  {
    v12 = 945;
LABEL_27:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"shell\\windowsuiimmersive\\popup\\xamlpopupwindowimpl.cpp",
      (const char *)(unsigned int)v10,
      v32);
LABEL_28:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
    return v11;
  }
  for ( j = 0; ; ++j )
  {
    if ( j >= 5 )
      goto LABEL_25;
    v14 = *((_QWORD *)this + j + 41);
    if ( v14 )
      break;
LABEL_21:
    ;
  }
  pv = 0;
  v15 = *(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v14 + 24LL);
  CoTaskMemFree(0);
  v16 = v15(v14, &pv);
  if ( v16 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x3B7,
      (unsigned int)"shell\\windowsuiimmersive\\popup\\xamlpopupwindowimpl.cpp",
      (const char *)(unsigned int)v16,
      v32);
    v17 = v33;
    v18 = *(__int64 (__fastcall **)(__int64 *, __int64))(*v33 + 104);
    v36 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, &Class, 1u, 0);
    v19 = v18(v17, v36);
    v11 = v19;
    if ( v19 < 0 )
    {
      v20 = 957;
LABEL_23:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v20,
        (unsigned int)"shell\\windowsuiimmersive\\popup\\xamlpopupwindowimpl.cpp",
        (const char *)(unsigned int)v19,
        v32);
      CoTaskMemFree(pv);
      goto LABEL_28;
    }
LABEL_20:
    CoTaskMemFree(pv);
    goto LABEL_21;
  }
  v21 = v33;
  v22 = *v33;
  v38 = 0;
  v23 = (const WCHAR *)pv;
  v32 = 0;
  v24 = -1;
  do
    ++v24;
  while ( *((_WORD *)pv + v24) );
  v25 = ULongLongToUInt(v24, &v32);
  if ( v25 >= 0 )
  {
    v26 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v32);
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v37, v23, v26, v32);
    v19 = (*(__int64 (__fastcall **)(__int64 *, __int64))(v22 + 104))(v21, v38);
    v11 = v19;
    if ( v19 < 0 )
    {
      v20 = 953;
      goto LABEL_23;
    }
    goto LABEL_20;
  }
  RaiseException(v25, 1u, 0, 0);
LABEL_25:
  hstringHeader.Reserved.Reserved1 = this;
  *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = &v33;
  v10 = CreationThreadDispatcher::RunSync__lambda_fc43420f6685c1574e6dc5d53b5e8db0___(
          *((_QWORD *)this + 36),
          &hstringHeader);
  v11 = v10;
  if ( v10 < 0 )
  {
    v12 = 969;
    goto LABEL_27;
  }
  if ( *((_BYTE *)this + 136) )
  {
    v28 = *(void (__fastcall **)(Windows::Internal::XamlPopupWindowImpl *, _QWORD))(*(_QWORD *)this + 72LL);
    v29 = (unsigned int *)std::optional<unsigned int>::value((char *)this + 132);
    v28(this, *v29);
  }
  if ( *((_BYTE *)this + 148) )
  {
    v30 = *(void (__fastcall **)(Windows::Internal::XamlPopupWindowImpl *, _QWORD))(*(_QWORD *)this + 112LL);
    v31 = (unsigned int *)std::optional<unsigned int>::value((char *)this + 144);
    v30(this, *v31);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
  return 0;
}

```

## disassembly

```asm
0x1800a2ad0  mov     [rsp-38h+arg_8], rbx
0x1800a2ad5  push    rbp
0x1800a2ad6  push    rsi
0x1800a2ad7  push    rdi
0x1800a2ad8  push    r12
0x1800a2ada  push    r13
0x1800a2adc  push    r14
0x1800a2ade  push    r15
0x1800a2ae0  mov     rbp, rsp
0x1800a2ae3  sub     rsp, 80h
0x1800a2aea  mov     rax, cs:__security_cookie
0x1800a2af1  xor     rax, rsp
0x1800a2af4  mov     [rbp+var_8], rax
0x1800a2af8  mov     r15, r8
0x1800a2afb  mov     edi, edx
0x1800a2afd  mov     rsi, rcx
0x1800a2b00  cmp     edx, [rcx+78h]
0x1800a2b03  cmovnb  edi, [rcx+78h]
0x1800a2b07  xor     r12d, r12d
0x1800a2b0a  mov     ebx, r12d
0x1800a2b0d  mov     r14d, edi
0x1800a2b10  lea     rax, ds:0[rbx*8]
0x1800a2b18  cmp     rbx, r14
0x1800a2b1b  jnb     short loc_1800A2B23
0x1800a2b1d  mov     rdx, [rax+r15]
0x1800a2b21  jmp     short loc_1800A2B26
0x1800a2b23  mov     rdx, r12
0x1800a2b26  lea     rcx, [rsi+148h]
0x1800a2b2d  add     rcx, rax
0x1800a2b30  call    ??4?$ComPtr@UIAsyncActionCompletedHandler@Foundation@Windows@@@WRL@Microsoft@@QEAAAEAV012@PEAUIAsyncActionCompletedHandler@Foundation@Windows@@@Z; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::operator=(Windows::Foundation::IAsyncActionCompletedHandler *)
0x1800a2b35  inc     rbx
0x1800a2b38  cmp     rbx, 5
0x1800a2b3c  jb      short loc_1800A2B10
0x1800a2b3e  mov     [rsi+74h], edi
0x1800a2b41  mov     [rbp+var_58], r12
0x1800a2b45  lea     rcx, [rbp+var_58]
0x1800a2b49  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800a2b4e  lea     rdx, [rbp+var_58]
0x1800a2b52  call    ??$CreateExternalVector@PEAUHSTRING__@@V?$Vector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$DefaultVectorOptions@PEAUHSTRING__@@@3456@@Internal@Collections@Foundation@Windows@@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEAPEAU?$IVector@PEAUHSTRING__@@@234@@ZPEAPEAV?$Vector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$DefaultVectorOptions@PEAUHSTRING__@@@3456@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalVector<HSTRING__ *,Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<HSTRING__ *>>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::IVector<HSTRING__ *> * *),Windows::Foundation::Collections::Internal::Vector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<HSTRING__ *>> * *)
0x1800a2b57  mov     ebx, eax
0x1800a2b59  test    eax, eax
0x1800a2b5b  jns     short loc_1800A2B6E
0x1800a2b5d  lea     r8, aShellWindowsui_15; "shell\\windowsuiimmersive\\popup\\xamlp"...
0x1800a2b64  mov     edx, 3B1h
0x1800a2b69  jmp     loc_1800A2CE0
0x1800a2b6e  mov     r15, r12
0x1800a2b71  lea     r14, aShellWindowsui_15; "shell\\windowsuiimmersive\\popup\\xamlp"...
0x1800a2b78  cmp     r15, 5
0x1800a2b7c  jnb     loc_1800A2CB6
0x1800a2b82  mov     rdi, [rsi+r15*8+148h]
0x1800a2b8a  test    rdi, rdi
0x1800a2b8d  jz      loc_1800A2C7A
0x1800a2b93  mov     [rbp+pv], r12
0x1800a2b97  mov     rax, [rdi]
0x1800a2b9a  mov     rbx, [rax+18h]
0x1800a2b9e  xor     ecx, ecx; pv
0x1800a2ba0  call    cs:__imp_CoTaskMemFree
0x1800a2ba6  lea     rdx, [rbp+pv]
0x1800a2baa  mov     rcx, rdi
0x1800a2bad  mov     rax, rbx
0x1800a2bb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2bb5  mov     rcx, [rbp+38h]; this
0x1800a2bb9  test    eax, eax
0x1800a2bbb  jns     short loc_1800A2C10
0x1800a2bbd  mov     r9d, eax; char *
0x1800a2bc0  mov     r8, r14; unsigned int
0x1800a2bc3  mov     edx, 3B7h; void *
0x1800a2bc8  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800a2bcd  mov     rdi, [rbp+var_58]
0x1800a2bd1  mov     rax, [rdi]
0x1800a2bd4  mov     rbx, [rax+68h]
0x1800a2bd8  mov     [rbp+var_30], r12
0x1800a2bdc  xor     r9d, r9d; unsigned int
0x1800a2bdf  lea     r8d, [r9+1]; unsigned int
0x1800a2be3  lea     rdx, Class; sourceString
0x1800a2bea  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x1800a2bee  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800a2bf3  nop
0x1800a2bf4  mov     rdx, [rbp+var_30]
0x1800a2bf8  mov     rcx, rdi
0x1800a2bfb  mov     rax, rbx
0x1800a2bfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2c03  mov     ebx, eax
0x1800a2c05  test    eax, eax
0x1800a2c07  jns     short loc_1800A2C70
0x1800a2c09  mov     edx, 3BDh
0x1800a2c0e  jmp     short loc_1800A2C87
0x1800a2c10  mov     rdi, [rbp+var_58]
0x1800a2c14  mov     r13, [rdi]
0x1800a2c17  mov     [rbp+var_10], r12
0x1800a2c1b  mov     rbx, [rbp+pv]
0x1800a2c1f  mov     [rbp+var_60], r12d
0x1800a2c23  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800a2c27  inc     rcx; unsigned __int64
0x1800a2c2a  cmp     [rbx+rcx*2], r12w
0x1800a2c2f  jnz     short loc_1800A2C27
0x1800a2c31  lea     rdx, [rbp+var_60]; unsigned int *
0x1800a2c35  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x1800a2c3a  test    eax, eax
0x1800a2c3c  js      short loc_1800A2CA3
0x1800a2c3e  mov     ecx, [rbp+var_60]; unsigned int
0x1800a2c41  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x1800a2c46  mov     r9d, [rbp+var_60]; unsigned int
0x1800a2c4a  mov     r8d, eax; unsigned int
0x1800a2c4d  mov     rdx, rbx; sourceString
0x1800a2c50  lea     rcx, [rbp+var_28]; hstringHeader
0x1800a2c54  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800a2c59  nop
0x1800a2c5a  mov     rdx, [rbp+var_10]
0x1800a2c5e  mov     rcx, rdi
0x1800a2c61  mov     rax, [r13+68h]
0x1800a2c65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2c6a  mov     ebx, eax
0x1800a2c6c  test    eax, eax
0x1800a2c6e  js      short loc_1800A2C82
0x1800a2c70  mov     rcx, [rbp+pv]; pv
0x1800a2c74  call    cs:__imp_CoTaskMemFree
0x1800a2c7a  inc     r15
0x1800a2c7d  jmp     loc_1800A2B78
0x1800a2c82  mov     edx, 3B9h; void *
0x1800a2c87  mov     r8, r14; unsigned int
0x1800a2c8a  mov     r9d, eax; char *
0x1800a2c8d  mov     rcx, [rbp+38h]; this
0x1800a2c91  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a2c96  nop
0x1800a2c97  mov     rcx, [rbp+pv]; pv
0x1800a2c9b  call    cs:__imp_CoTaskMemFree
0x1800a2ca1  jmp     short loc_1800A2CED
0x1800a2ca3  xor     r9d, r9d; lpArguments
0x1800a2ca6  xor     r8d, r8d; nNumberOfArguments
0x1800a2ca9  lea     edx, [r9+1]; dwExceptionFlags
0x1800a2cad  mov     ecx, eax; dwExceptionCode
0x1800a2caf  call    cs:__imp_RaiseException
0x1800a2cb5  nop
0x1800a2cb6  mov     qword ptr [rbp+hstringHeader.Reserved], rsi
0x1800a2cba  lea     rax, [rbp+var_58]
0x1800a2cbe  mov     qword ptr [rbp+hstringHeader.Reserved+8], rax
0x1800a2cc2  lea     rdx, [rbp+hstringHeader]
0x1800a2cc6  mov     rcx, [rsi+120h]
0x1800a2ccd  call    CreationThreadDispatcher__RunSync__lambda_fc43420f6685c1574e6dc5d53b5e8db0___
0x1800a2cd2  mov     ebx, eax
0x1800a2cd4  test    eax, eax
0x1800a2cd6  jns     short loc_1800A2CFA
0x1800a2cd8  mov     r8, r14; unsigned int
0x1800a2cdb  mov     edx, 3C9h; void *
0x1800a2ce0  mov     r9d, eax; char *
0x1800a2ce3  mov     rcx, [rbp+38h]; this
0x1800a2ce7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a2cec  nop
0x1800a2ced  lea     rcx, [rbp+var_58]
0x1800a2cf1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800a2cf6  mov     eax, ebx
0x1800a2cf8  jmp     short loc_1800A2D58
0x1800a2cfa  cmp     [rsi+88h], r12b
0x1800a2d01  jz      short loc_1800A2D23
0x1800a2d03  mov     rax, [rsi]
0x1800a2d06  mov     rbx, [rax+48h]
0x1800a2d0a  lea     rcx, [rsi+84h]
0x1800a2d11  call    ?value@?$optional@I@std@@QEGAAAEAIXZ; std::optional<uint>::value(void)
0x1800a2d16  mov     edx, [rax]
0x1800a2d18  mov     rcx, rsi
0x1800a2d1b  mov     rax, rbx
0x1800a2d1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2d23  cmp     [rsi+94h], r12b
0x1800a2d2a  jz      short loc_1800A2D4D
0x1800a2d2c  mov     rax, [rsi]
0x1800a2d2f  mov     rbx, [rax+70h]
0x1800a2d33  lea     rcx, [rsi+90h]
0x1800a2d3a  call    ?value@?$optional@I@std@@QEGAAAEAIXZ; std::optional<uint>::value(void)
0x1800a2d3f  mov     edx, [rax]
0x1800a2d41  mov     rcx, rsi
0x1800a2d44  mov     rax, rbx
0x1800a2d47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2d4c  nop
0x1800a2d4d  lea     rcx, [rbp+var_58]
0x1800a2d51  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800a2d56  xor     eax, eax
0x1800a2d58  mov     rcx, [rbp+var_8]
0x1800a2d5c  xor     rcx, rsp; StackCookie
0x1800a2d5f  call    __security_check_cookie
0x1800a2d64  mov     rbx, [rsp+80h+arg_8]
0x1800a2d6c  add     rsp, 80h
0x1800a2d73  pop     r15
0x1800a2d75  pop     r14
0x1800a2d77  pop     r13
0x1800a2d79  pop     r12
0x1800a2d7b  pop     rdi
0x1800a2d7c  pop     rsi
0x1800a2d7d  pop     rbp
0x1800a2d7e  retn
```
