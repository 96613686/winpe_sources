# IsVisitorAccount(Windows::System::Internal::IUserManagerStatics *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180023490`
- end: `0x18002357d`
- name: `?IsVisitorAccount@@YA_NPEAUIUserManagerStatics@Internal@System@Windows@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `237`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180005120`
- `0x18000ccd4`
- `0x18001238c`
- `0x180015490`
- `0x18001998c`
- `0x1800230a8`
- `0x180023490`
- `0x180026010`

## string_xrefs

- `0x1800234cd`: `shellcommon\shell\sharedpc\accountmanager\lib\util\specialaccountsutils.cpp`

## pseudocode

```c
char __fastcall IsVisitorAccount(_QWORD *a1, __int64 a2)
{
  __int64 v4; // rax
  int v5; // eax
  __int64 v6; // rbx
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v10; // [rsp+20h] [rbp-49h] BYREF
  int v11; // [rsp+28h] [rbp-41h]
  __int64 v12; // [rsp+30h] [rbp-39h]
  _BYTE v13[8]; // [rsp+40h] [rbp-29h] BYREF
  int v14; // [rsp+48h] [rbp-21h]
  __int64 v15; // [rsp+50h] [rbp-19h] BYREF
  _QWORD *v16; // [rsp+58h] [rbp-11h] BYREF
  _BYTE v17[32]; // [rsp+60h] [rbp-9h] BYREF
  _BYTE v18[24]; // [rsp+80h] [rbp+17h] BYREF
  _BYTE v19[16]; // [rsp+98h] [rbp+2Fh] BYREF
  __int64 v20[3]; // [rsp+A8h] [rbp+3Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]
  __int64 v22; // [rsp+D0h] [rbp+67h] BYREF
  __int64 v23; // [rsp+E0h] [rbp+77h] BYREF
  _QWORD *v24; // [rsp+E8h] [rbp+7Fh]

  v4 = *a1;
  v22 = 0;
  v5 = (*(__int64 (__fastcall **)(_QWORD *, __int64 *))(v4 + 88))(a1, &v22);
  if ( v5 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x43,
      (int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\util\\specialaccountsutils.cpp",
      (const char *)(unsigned int)v5,
      v10);
  v6 = v22;
  v23 = v22;
  v24 = &v16;
  v16 = a1;
  std::wstring::wstring(v17, a2);
  v7 = wil::vector_range<Windows::Foundation::Collections::IVectorView<Windows::System::Internal::IUserProfile *>,wil::err_exception_policy>::end(
         &v23,
         (__int64)v18);
  v10 = v6;
  v11 = 0;
  v12 = 0;
  ((void (__fastcall *)(_BYTE *, __int64 *, __int64, _QWORD **))std::find_if_wil::vector_range_Windows::Foundation::Collections::IVectorView_Windows::System::Internal::IUserProfile____wil::err_exception_policy_::vector_iterator__lambda_cfbb64e7b6e71bf2a69857e755b6a7e1___)(
    v13,
    &v10,
    v7,
    &v16);
  v8 = wil::vector_range<Windows::Foundation::Collections::IVectorView<Windows::System::Internal::IUserProfile *>,wil::err_exception_policy>::end(
         &v23,
         (__int64)v19);
  LOBYTE(v6) = v14 != *(_DWORD *)(v8 + 8);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v20);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v15);
  wil::com_ptr_t<Windows::System::Internal::IUserProfile2,wil::err_exception_policy>::~com_ptr_t<Windows::System::Internal::IUserProfile2,wil::err_exception_policy>(&v22);
  return v6;
}

```

## disassembly

```asm
0x180023490  mov     [rsp-8+arg_8], rbx
0x180023495  push    rbp
0x180023496  push    rsi
0x180023497  push    rdi
0x180023498  lea     rbp, [rsp-47h]
0x18002349d  sub     rsp, 0B0h
0x1800234a4  mov     rsi, rdx
0x1800234a7  mov     rdi, rcx
0x1800234aa  mov     rax, [rcx]
0x1800234ad  mov     [rbp+57h+arg_0], 0
0x1800234b5  lea     rdx, [rbp+57h+arg_0]
0x1800234b9  mov     rax, [rax+58h]
0x1800234bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800234c2  mov     rcx, [rbp+5Fh]; this
0x1800234c6  test    eax, eax
0x1800234c8  jns     short loc_1800234DF
0x1800234ca  mov     r9d, eax; char *
0x1800234cd  lea     r8, aShellcommonShe_15; "shellcommon\\shell\\sharedpc\\accountma"...
0x1800234d4  mov     edx, 43h ; 'C'; void *
0x1800234d9  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800234df  mov     rbx, [rbp+57h+arg_0]
0x1800234e3  mov     [rbp+57h+arg_10], rbx
0x1800234e7  lea     rax, [rbp+57h+var_68]
0x1800234eb  mov     [rbp+57h+arg_18], rax
0x1800234ef  mov     [rbp+57h+var_68], rdi
0x1800234f3  mov     rdx, rsi
0x1800234f6  lea     rcx, [rbp+57h+var_60]
0x1800234fa  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800234ff  nop
0x180023500  lea     rdx, [rbp+57h+var_40]
0x180023504  lea     rcx, [rbp+57h+arg_10]
0x180023508  call    ?end@?$vector_range@U?$IVectorView@PEAUIUserProfile@Internal@System@Windows@@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA?AVvector_iterator@12@XZ; wil::vector_range<Windows::Foundation::Collections::IVectorView<Windows::System::Internal::IUserProfile *>,wil::err_exception_policy>::end(void)
0x18002350d  mov     [rbp+57h+var_A0], rbx
0x180023511  mov     [rbp+57h+var_98], 0
0x180023518  mov     [rbp+57h+var_90], 0
0x180023520  lea     r9, [rbp+57h+var_68]
0x180023524  mov     r8, rax
0x180023527  lea     rdx, [rbp+57h+var_A0]
0x18002352b  lea     rcx, [rbp+57h+var_80]
0x18002352f  call    std__find_if_wil__vector_range_Windows__Foundation__Collections__IVectorView_Windows__System__Internal__IUserProfile____wil__err_exception_policy___vector_iterator__lambda_cfbb64e7b6e71bf2a69857e755b6a7e1___
0x180023534  nop
0x180023535  lea     rdx, [rbp+57h+var_28]
0x180023539  lea     rcx, [rbp+57h+arg_10]
0x18002353d  call    ?end@?$vector_range@U?$IVectorView@PEAUIUserProfile@Internal@System@Windows@@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA?AVvector_iterator@12@XZ; wil::vector_range<Windows::Foundation::Collections::IVectorView<Windows::System::Internal::IUserProfile *>,wil::err_exception_policy>::end(void)
0x180023542  mov     ecx, [rax+8]
0x180023545  cmp     [rbp+57h+var_78], ecx
0x180023548  setnz   bl
0x18002354b  lea     rcx, [rbp+57h+var_18]
0x18002354f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180023554  nop
0x180023555  lea     rcx, [rbp+57h+var_70]
0x180023559  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002355e  nop
0x18002355f  lea     rcx, [rbp+57h+arg_0]
0x180023563  call    ??1?$com_ptr_t@UIUserProfile2@Internal@System@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::System::Internal::IUserProfile2,wil::err_exception_policy>::~com_ptr_t<Windows::System::Internal::IUserProfile2,wil::err_exception_policy>(void)
0x180023568  mov     al, bl
0x18002356a  mov     rbx, [rsp+0C0h+arg_8]
0x180023572  add     rsp, 0B0h
0x180023579  pop     rdi
0x18002357a  pop     rsi
0x18002357b  pop     rbp
0x18002357c  retn
```
