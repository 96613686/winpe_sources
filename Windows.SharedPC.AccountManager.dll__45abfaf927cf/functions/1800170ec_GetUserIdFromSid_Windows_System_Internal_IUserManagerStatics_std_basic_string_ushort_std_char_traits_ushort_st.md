# GetUserIdFromSid(Windows::System::Internal::IUserManagerStatics *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x1800170ec`
- end: `0x18001720c`
- name: `?GetUserIdFromSid@@YAIPEAUIUserManagerStatics@Internal@System@Windows@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `288`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180015ee0`

## callees

- `0x180005120`
- `0x18000ccd4`
- `0x18001238c`
- `0x180014f80`
- `0x180015490`
- `0x1800157c4`
- `0x1800170ec`
- `0x18001998c`
- `0x180026010`

## string_xrefs

- `0x180017122`: `shellcommon\shell\sharedpc\accountmanager\lib\accounts\useraccountstore.cpp`
- `0x1800171d7`: `shellcommon\shell\sharedpc\accountmanager\lib\accounts\useraccountstore.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall GetUserIdFromSid(__int64 *a1, __int64 a2)
{
  __int64 v3; // rax
  int v4; // eax
  __int64 v5; // rbx
  __int64 v6; // rax
  __int64 v7; // rax
  unsigned int *v8; // rax
  int v9; // eax
  unsigned int v10; // ebx
  int v12; // [rsp+20h] [rbp-49h]
  __int64 v13; // [rsp+28h] [rbp-41h] BYREF
  int v14; // [rsp+30h] [rbp-39h]
  __int64 v15; // [rsp+38h] [rbp-31h]
  unsigned int v16[4]; // [rsp+40h] [rbp-29h] BYREF
  _BYTE v17[8]; // [rsp+50h] [rbp-19h] BYREF
  _BYTE *v18; // [rsp+58h] [rbp-11h]
  _BYTE v19[32]; // [rsp+60h] [rbp-9h] BYREF
  _BYTE v20[24]; // [rsp+80h] [rbp+17h] BYREF
  _BYTE v21[16]; // [rsp+98h] [rbp+2Fh] BYREF
  _BYTE v22[24]; // [rsp+A8h] [rbp+3Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]
  unsigned int v24; // [rsp+D0h] [rbp+67h] BYREF
  __int64 v25; // [rsp+E0h] [rbp+77h] BYREF
  __int64 v26; // [rsp+E8h] [rbp+7Fh] BYREF

  v3 = *a1;
  v25 = 0;
  v4 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v3 + 88))(a1, &v25);
  if ( v4 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x44,
      (int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\accounts\\useraccountstore.cpp",
      (const char *)(unsigned int)v4,
      v12);
  v5 = v25;
  v26 = v25;
  v18 = v19;
  std::wstring::wstring(v19, a2);
  v6 = wil::vector_range<Windows::Foundation::Collections::IVectorView<Windows::System::Internal::IUserProfile *>,wil::err_exception_policy>::end(
         &v26,
         (__int64)v20);
  v13 = v5;
  v14 = 0;
  v15 = 0;
  std::find_if_wil::vector_range_Windows::Foundation::Collections::IVectorView_Windows::System::Internal::IUserProfile____wil::err_exception_policy_::vector_iterator__lambda_51819d7fac86715c0f09c653aa5bf692___(
    v16,
    &v13,
    v6,
    v19);
  v24 = 0;
  v7 = wil::vector_range<Windows::Foundation::Collections::IVectorView<Windows::System::Internal::IUserProfile *>,wil::err_exception_policy>::end(
         &v26,
         (__int64)v21);
  LOBYTE(v5) = v16[2] != *(_DWORD *)(v7 + 8);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v22);
  if ( (_BYTE)v5 )
  {
    v8 = wil::vector_range<Windows::Foundation::Collections::IVectorView<Windows::System::Internal::IUserProfile *>,wil::err_exception_policy>::vector_iterator::operator*(v16);
    v9 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(**(_QWORD **)v8 + 48LL))(*(_QWORD *)v8, &v24);
    if ( v9 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x52,
        (int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\accounts\\useraccountstore.cpp",
        (const char *)(unsigned int)v9,
        v12);
  }
  v10 = v24;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v17);
  wil::com_ptr_t<Windows::System::Internal::IUserProfile2,wil::err_exception_policy>::~com_ptr_t<Windows::System::Internal::IUserProfile2,wil::err_exception_policy>(&v25);
  return v10;
}

```

## disassembly

```asm
0x1800170ec  push    rbp
0x1800170ee  push    rbx
0x1800170ef  push    rdi
0x1800170f0  lea     rbp, [rsp-47h]
0x1800170f5  sub     rsp, 0B0h
0x1800170fc  mov     rdi, rdx
0x1800170ff  mov     rax, [rcx]
0x180017102  mov     [rbp+57h+arg_10], 0
0x18001710a  lea     rdx, [rbp+57h+arg_10]
0x18001710e  mov     rax, [rax+58h]
0x180017112  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017117  mov     rcx, [rbp+5Fh]; this
0x18001711b  test    eax, eax
0x18001711d  jns     short loc_180017134
0x18001711f  mov     r9d, eax; char *
0x180017122  lea     r8, aShellcommonShe_7; "shellcommon\\shell\\sharedpc\\accountma"...
0x180017129  mov     edx, 44h ; 'D'; void *
0x18001712e  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180017134  mov     rbx, [rbp+57h+arg_10]
0x180017138  mov     [rbp+57h+arg_18], rbx
0x18001713c  lea     rax, [rbp+57h+var_60]
0x180017140  mov     [rbp+57h+var_68], rax
0x180017144  mov     rdx, rdi
0x180017147  lea     rcx, [rbp+57h+var_60]
0x18001714b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180017150  nop
0x180017151  lea     rdx, [rbp+57h+var_40]
0x180017155  lea     rcx, [rbp+57h+arg_18]
0x180017159  call    ?end@?$vector_range@U?$IVectorView@PEAUIUserProfile@Internal@System@Windows@@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA?AVvector_iterator@12@XZ; wil::vector_range<Windows::Foundation::Collections::IVectorView<Windows::System::Internal::IUserProfile *>,wil::err_exception_policy>::end(void)
0x18001715e  mov     [rbp+57h+var_98], rbx
0x180017162  mov     [rbp+57h+var_90], 0
0x180017169  mov     [rbp+57h+var_88], 0
0x180017171  lea     r9, [rbp+57h+var_60]
0x180017175  mov     r8, rax
0x180017178  lea     rdx, [rbp+57h+var_98]
0x18001717c  lea     rcx, [rbp+57h+var_80]
0x180017180  call    std__find_if_wil__vector_range_Windows__Foundation__Collections__IVectorView_Windows__System__Internal__IUserProfile____wil__err_exception_policy___vector_iterator__lambda_51819d7fac86715c0f09c653aa5bf692___
0x180017185  nop
0x180017186  mov     [rbp+57h+arg_0], 0
0x18001718d  lea     rdx, [rbp+57h+var_28]
0x180017191  lea     rcx, [rbp+57h+arg_18]
0x180017195  call    ?end@?$vector_range@U?$IVectorView@PEAUIUserProfile@Internal@System@Windows@@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA?AVvector_iterator@12@XZ; wil::vector_range<Windows::Foundation::Collections::IVectorView<Windows::System::Internal::IUserProfile *>,wil::err_exception_policy>::end(void)
0x18001719a  mov     ecx, [rax+8]
0x18001719d  cmp     [rbp+57h+var_78], ecx
0x1800171a0  setnz   bl
0x1800171a3  lea     rcx, [rbp+57h+var_18]
0x1800171a7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800171ac  test    bl, bl
0x1800171ae  jz      short loc_1800171E9
0x1800171b0  lea     rcx, [rbp+57h+var_80]
0x1800171b4  call    ??Dvector_iterator@?$vector_range@U?$IVectorView@PEAUIUserProfile@Internal@System@Windows@@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAAAEBV?$ComPtr@UIUserProfile@Internal@System@Windows@@@WRL@Microsoft@@XZ; wil::vector_range<Windows::Foundation::Collections::IVectorView<Windows::System::Internal::IUserProfile *>,wil::err_exception_policy>::vector_iterator::operator*(void)
0x1800171b9  mov     rcx, [rax]
0x1800171bc  mov     rax, [rcx]
0x1800171bf  lea     rdx, [rbp+57h+arg_0]
0x1800171c3  mov     rax, [rax+30h]
0x1800171c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800171cc  mov     rcx, [rbp+5Fh]; this
0x1800171d0  test    eax, eax
0x1800171d2  jns     short loc_1800171E9
0x1800171d4  mov     r9d, eax; char *
0x1800171d7  lea     r8, aShellcommonShe_7; "shellcommon\\shell\\sharedpc\\accountma"...
0x1800171de  mov     edx, 52h ; 'R'; void *
0x1800171e3  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800171e9  mov     ebx, [rbp+57h+arg_0]
0x1800171ec  lea     rcx, [rbp+57h+var_70]
0x1800171f0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800171f5  nop
0x1800171f6  lea     rcx, [rbp+57h+arg_10]
0x1800171fa  call    ??1?$com_ptr_t@UIUserProfile2@Internal@System@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::System::Internal::IUserProfile2,wil::err_exception_policy>::~com_ptr_t<Windows::System::Internal::IUserProfile2,wil::err_exception_policy>(void)
0x1800171ff  mov     eax, ebx
0x180017201  add     rsp, 0B0h
0x180017208  pop     rdi
0x180017209  pop     rbx
0x18001720a  pop     rbp
0x18001720b  retn
```
