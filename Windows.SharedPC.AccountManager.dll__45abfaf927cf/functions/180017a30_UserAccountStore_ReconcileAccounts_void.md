# UserAccountStore::ReconcileAccounts(void)

- ea: `0x180017a30`
- end: `0x180017fec`
- name: `?ReconcileAccounts@UserAccountStore@@AEAAXXZ`
- size: `1468`
- prototype: `void __fastcall(UserAccountStore *__hidden this)`
- caller_count: `3`
- callee_count: `25`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800166c0`
- `0x180016860`
- `0x18001809c`

## callees

- `0x180003530`
- `0x180005120`
- `0x18000a584`
- `0x18000ccd4`
- `0x18000ccf4`
- `0x18000cd50`
- `0x18000cfc0`
- `0x18000f41c`
- `0x18000f454`
- `0x1800113d8`
- `0x1800123d4`
- `0x180013dcc`
- `0x1800144a8`
- `0x1800147a0`
- `0x1800147cc`
- `0x180014b40`
- `0x180014d50`
- `0x180014da0`
- `0x180014f20`
- `0x180014f34`
- `0x18001573c`
- `0x180015920`
- `0x180016eb8`
- `0x180017a30`
- `0x180026010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180017b48`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180017b48`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180017acf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180017acf`

## string_xrefs

- `0x180017ae3`: `shellcommon\shell\sharedpc\accountmanager\lib\accounts\useraccountstore.cpp`
- `0x180017af8`: `shellcommon\shell\sharedpc\accountmanager\lib\accounts\useraccountstore.cpp`
- `0x180017e50`: `shellcommon\shell\sharedpc\accountmanager\lib\accounts\useraccountstore.cpp`
- `0x180017e65`: `shellcommon\shell\sharedpc\accountmanager\lib\accounts\useraccountstore.cpp`
- `0x180017e7a`: `shellcommon\shell\sharedpc\accountmanager\lib\accounts\useraccountstore.cpp`
- `0x180017e8f`: `shellcommon\shell\sharedpc\accountmanager\lib\accounts\useraccountstore.cpp`
- `0x180017ea4`: `shellcommon\shell\sharedpc\accountmanager\lib\accounts\useraccountstore.cpp`
- `0x180017eb9`: `shellcommon\shell\sharedpc\accountmanager\lib\accounts\useraccountstore.cpp`
- `0x180017ece`: `shellcommon\shell\sharedpc\accountmanager\lib\accounts\useraccountstore.cpp`
- `0x180017ee3`: `shellcommon\shell\sharedpc\accountmanager\lib\accounts\useraccountstore.cpp`
- `0x180017fda`: `shellcommon\shell\sharedpc\accountmanager\lib\accounts\useraccountstore.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall UserAccountStore::ReconcileAccounts(UserAccountStore *this)
{
  char *v2; // r14
  _QWORD *v3; // rbx
  _QWORD *v4; // rdi
  int v5; // eax
  unsigned int v6; // eax
  DWORD i; // esi
  unsigned int v8; // eax
  __int64 v9; // rcx
  __int64 v10; // rcx
  _QWORD *v11; // rbx
  _QWORD *v12; // rdi
  __int64 v13; // rax
  int v14; // eax
  __int64 v15; // rax
  int v16; // eax
  int v17; // eax
  int v18; // eax
  int v19; // eax
  int v20; // eax
  int v21; // eax
  int v22; // eax
  __int64 v23; // rcx
  _QWORD *v24; // rdi
  __int64 v25; // rcx
  __int64 v26; // rdi
  __int64 v27; // rbx
  __int64 v28; // rsi
  __int64 v29; // rbx
  int phkResult; // [rsp+20h] [rbp-E0h]
  unsigned int phkResulta; // [rsp+20h] [rbp-E0h]
  unsigned int phkResultb; // [rsp+20h] [rbp-E0h]
  int v33; // [rsp+40h] [rbp-C0h] BYREF
  void *v34; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v35; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v36; // [rsp+54h] [rbp-ACh] BYREF
  __int64 v37; // [rsp+58h] [rbp-A8h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cchName; // [rsp+68h] [rbp-98h] BYREF
  __int64 v40; // [rsp+70h] [rbp-90h] BYREF
  __int64 v41; // [rsp+78h] [rbp-88h] BYREF
  __int64 v42; // [rsp+80h] [rbp-80h]
  __int64 v43; // [rsp+88h] [rbp-78h]
  __int64 v44; // [rsp+90h] [rbp-70h]
  char *v45; // [rsp+98h] [rbp-68h]
  _BYTE v46[8]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v47[40]; // [rsp+A8h] [rbp-58h] BYREF
  WCHAR Name[264]; // [rsp+D0h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+328h] [rbp+228h]

  v2 = (char *)this + 56;
  v3 = (_QWORD *)*((_QWORD *)this + 7);
  v4 = (_QWORD *)*((_QWORD *)this + 8);
  while ( v3 != v4 )
  {
    v5 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v3 + 72LL))(*v3, 0);
    if ( v5 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x174,
        (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\accounts\\useraccountstore.cpp",
        (const char *)(unsigned int)v5,
        phkResult);
    ++v3;
  }
  std::vector<SessionUserInfo>::vector<SessionUserInfo>(&v41);
  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Windows NT\\CurrentVersion\\ProfileList", 0, 9u, &hKey);
  if ( v6 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x17C,
      (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\accounts\\useraccountstore.cpp",
      (const char *)v6,
      phkResulta);
  for ( i = 0; ; ++i )
  {
    cchName = 260;
    v8 = RegEnumKeyExW(hKey, i, Name, &cchName, 0, 0, 0, 0);
    if ( v8 )
      break;
    v33 = 0;
    std::wstring::wstring(v47);
    UserAccountStore::GetUserAccountInfo(v10, Name, &v33, v47);
    v11 = *(_QWORD **)v2;
    v12 = (_QWORD *)*((_QWORD *)this + 8);
    while ( v11 != v12 )
    {
      if ( (*(unsigned __int8 (__fastcall **)(_QWORD, WCHAR *))(*(_QWORD *)*v11 + 96LL))(*v11, Name) )
      {
        (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v11 + 72LL))(*v11, 1);
        break;
      }
      ++v11;
    }
    if ( v11 == *((_QWORD **)this + 8) )
    {
      if ( v33 == 4 )
        goto LABEL_42;
      v34 = 0;
      if ( v33 == 1 )
        v13 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v47);
      else
        v13 = 0;
      v37 = v13;
      v14 = Microsoft::WRL::Details::MakeAndInitialize<UserAccount,IUserAccount,unsigned short (&)[260],enum AccountType &,unsigned short const *>(&v34);
      if ( v14 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x1A7,
          (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\accounts\\useraccountstore.cpp",
          (const char *)(unsigned int)v14,
          phkResultb);
      if ( v42 == v43 )
        std::vector<Microsoft::WRL::ComPtr<IUserAccount>>::_Emplace_reallocate<Microsoft::WRL::ComPtr<IUserAccount> const &>(
          &v41,
          v42,
          &v34);
      else
        std::vector<Microsoft::WRL::ComPtr<IUserAccount>>::_Emplace_back_with_unused_capacity<Microsoft::WRL::ComPtr<IUserAccount> const &>(
          &v41,
          &v34);
    }
    else
    {
      LODWORD(v37) = 4;
      (*(void (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*v11 + 40LL))(*v11, &v37);
      if ( v33 == (_DWORD)v37 )
        goto LABEL_42;
      v34 = 0;
      if ( v33 == 1 )
        v15 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v47);
      else
        v15 = 0;
      v44 = v15;
      v16 = Microsoft::WRL::Details::MakeAndInitialize<UserAccount,IUserAccount,unsigned short (&)[260],enum AccountType &,unsigned short const *>(&v34);
      if ( v16 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x1B4,
          (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\accounts\\useraccountstore.cpp",
          (const char *)(unsigned int)v16,
          phkResultb);
      v40 = 0;
      v35 = 0;
      v36 = 0;
      v17 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*v11 + 48LL))(*v11, &v40);
      if ( v17 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x1B9,
          (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\accounts\\useraccountstore.cpp",
          (const char *)(unsigned int)v17,
          phkResultb);
      v18 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(*(_QWORD *)*v11 + 64LL))(*v11, &v35);
      if ( v18 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x1BA,
          (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\accounts\\useraccountstore.cpp",
          (const char *)(unsigned int)v18,
          phkResultb);
      v19 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(*(_QWORD *)*v11 + 80LL))(*v11, &v36);
      if ( v19 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x1BB,
          (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\accounts\\useraccountstore.cpp",
          (const char *)(unsigned int)v19,
          phkResultb);
      v20 = (*(__int64 (__fastcall **)(void *, __int64))(*(_QWORD *)v34 + 56LL))(v34, v40);
      if ( v20 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x1BD,
          (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\accounts\\useraccountstore.cpp",
          (const char *)(unsigned int)v20,
          phkResultb);
      v21 = (*(__int64 (__fastcall **)(void *, _QWORD))(*(_QWORD *)v34 + 72LL))(v34, v35);
      if ( v21 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x1BE,
          (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\accounts\\useraccountstore.cpp",
          (const char *)(unsigned int)v21,
          phkResultb);
      v22 = (*(__int64 (__fastcall **)(void *, _QWORD))(*(_QWORD *)v34 + 88LL))(v34, v36);
      if ( v22 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x1BF,
          (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\accounts\\useraccountstore.cpp",
          (const char *)(unsigned int)v22,
          phkResultb);
      std::_Move_unchecked<Microsoft::WRL::ComPtr<IUserAccount> *,Microsoft::WRL::ComPtr<IUserAccount> *>(
        v11 + 1,
        *((_QWORD *)this + 8),
        v11);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(*((_QWORD *)this + 8) - 8LL);
      *((_QWORD *)this + 8) -= 8LL;
      v24 = (_QWORD *)*((_QWORD *)this + 8);
      if ( v24 == *((_QWORD **)v2 + 2) )
      {
        std::vector<Microsoft::WRL::ComPtr<IUserAccount>>::_Emplace_reallocate<Microsoft::WRL::ComPtr<IUserAccount> const &>(
          v2,
          v11,
          &v34);
      }
      else if ( v11 == v24 )
      {
        std::vector<Microsoft::WRL::ComPtr<IUserAccount>>::_Emplace_back_with_unused_capacity<Microsoft::WRL::ComPtr<IUserAccount> const &>(
          v2,
          &v34);
      }
      else
      {
        v45 = v2;
        std::_Default_allocator_traits<std::allocator<Microsoft::WRL::ComPtr<IUserAccount>>>::construct<Microsoft::WRL::ComPtr<IUserAccount>,Microsoft::WRL::ComPtr<IUserAccount> &>(
          v23,
          v46,
          &v34);
        std::_Default_allocator_traits<std::allocator<Microsoft::WRL::ComPtr<IUserAccount>>>::construct<Microsoft::WRL::ComPtr<IUserAccount>,Microsoft::WRL::ComPtr<IUserAccount>>(
          v25,
          v24,
          v24 - 1);
        *((_QWORD *)v2 + 1) += 8LL;
        std::_Move_backward_unchecked<Microsoft::WRL::ComPtr<IUserAccount> *,Microsoft::WRL::ComPtr<IUserAccount> *>(
          v11,
          v24 - 1,
          v24);
        Microsoft::WRL::ComPtr<IUserAccount>::operator=(v11, v46);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v46);
      }
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v34);
LABEL_42:
    std::wstring::_Tidy_deallocate(v47);
  }
  if ( v8 != 259 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x18A,
      (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\accounts\\useraccountstore.cpp",
      (const char *)v8,
      phkResultb);
  v26 = *((_QWORD *)v2 + 1);
  v27 = *(_QWORD *)v2;
  if ( *(_QWORD *)v2 != v26 )
  {
    do
    {
      if ( (unsigned __int8)lambda_90d4a07a344ba25b30dad4eaecd3f18e_::operator()(v9, v27) )
        break;
      v27 += 8;
    }
    while ( v27 != v26 );
    if ( v27 != v26 )
    {
      v28 = v27 + 8;
      if ( v27 + 8 == v26 )
        goto LABEL_61;
      do
      {
        if ( !(unsigned __int8)lambda_90d4a07a344ba25b30dad4eaecd3f18e_::operator()(v9, v28) )
        {
          Microsoft::WRL::ComPtr<IUserAccount>::operator=(v27, v28);
          v27 += 8;
        }
        v28 += 8;
      }
      while ( v28 != v26 );
      if ( v27 != v26 )
      {
LABEL_61:
        v29 = std::_Move_unchecked<Microsoft::WRL::ComPtr<IUserAccount> *,Microsoft::WRL::ComPtr<IUserAccount> *>(
                v26,
                *((_QWORD *)this + 8),
                v27);
        std::_Destroy_range<std::allocator<Microsoft::WRL::ComPtr<IUserAccount>>>(v29, *((_QWORD *)this + 8));
        *((_QWORD *)this + 8) = v29;
      }
    }
  }
  if ( v41 != v42 )
    std::vector<Microsoft::WRL::ComPtr<IUserAccount>>::_Insert_counted_range<Microsoft::WRL::ComPtr<IUserAccount> *>(
      v2,
      *((_QWORD *)this + 8),
      v41,
      (v42 - v41) >> 3);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  std::vector<Microsoft::WRL::ComPtr<IUserAccount>>::_Tidy(&v41);
}

```

## disassembly

```asm
0x180017a30  push    rbp
0x180017a32  push    rbx
0x180017a33  push    rsi
0x180017a34  push    rdi
0x180017a35  push    r14
0x180017a37  push    r15
0x180017a39  lea     rbp, [rsp-1F8h]
0x180017a41  sub     rsp, 2F8h
0x180017a48  mov     rax, cs:__security_cookie
0x180017a4f  xor     rax, rsp
0x180017a52  mov     [rbp+220h+var_40], rax
0x180017a59  mov     r15, rcx
0x180017a5c  lea     r14, [rcx+38h]
0x180017a60  mov     rbx, [r14]
0x180017a63  mov     rdi, [r14+8]
0x180017a67  jmp     short loc_180017A89
0x180017a69  mov     rcx, [rbx]
0x180017a6c  mov     rax, [rcx]
0x180017a6f  xor     edx, edx
0x180017a71  mov     rax, [rax+48h]
0x180017a75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017a7a  mov     rcx, [rbp+228h]; this
0x180017a81  test    eax, eax
0x180017a83  js      short loc_180017AF5
0x180017a85  add     rbx, 8
0x180017a89  cmp     rbx, rdi
0x180017a8c  jnz     short loc_180017A69
0x180017a8e  lea     rcx, [rsp+320h+var_2A8]
0x180017a93  call    ??0?$vector@USessionUserInfo@@V?$allocator@USessionUserInfo@@@std@@@std@@QEAA@XZ; std::vector<SessionUserInfo>::vector<SessionUserInfo>(void)
0x180017a98  nop
0x180017a99  mov     [rsp+320h+hKey], 0
0x180017aa2  xor     edx, edx
0x180017aa4  lea     rcx, [rsp+320h+hKey]
0x180017aa9  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180017aae  lea     rax, [rsp+320h+hKey]
0x180017ab3  mov     [rsp+320h+phkResult], rax; unsigned int
0x180017ab8  mov     r9d, 9; samDesired
0x180017abe  xor     r8d, r8d; ulOptions
0x180017ac1  lea     rdx, SubKey; "Software\\Microsoft\\Windows NT\\Curren"...
0x180017ac8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180017acf  call    cs:__imp_RegOpenKeyExW
0x180017ad5  mov     rcx, [rbp+228h]; this
0x180017adc  test    eax, eax
0x180017ade  jz      short loc_180017B0A
0x180017ae0  mov     r9d, eax; char *
0x180017ae3  lea     r8, aShellcommonShe_7; "shellcommon\\shell\\sharedpc\\accountma"...
0x180017aea  mov     edx, 17Ch; void *
0x180017aef  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180017af5  mov     r9d, eax; char *
0x180017af8  lea     r8, aShellcommonShe_7; "shellcommon\\shell\\sharedpc\\accountma"...
0x180017aff  mov     edx, 174h; void *
0x180017b04  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180017b0a  xor     esi, esi
0x180017b0c  mov     [rsp+320h+cchName], 104h
0x180017b14  mov     [rsp+320h+lpftLastWriteTime], 0; lpftLastWriteTime
0x180017b1d  mov     [rsp+320h+lpcchClass], 0; lpcchClass
0x180017b26  mov     [rsp+320h+lpClass], 0; lpClass
0x180017b2f  mov     [rsp+320h+phkResult], 0; unsigned int
0x180017b38  lea     r9, [rsp+320h+cchName]; lpcchName
0x180017b3d  lea     r8, [rbp+220h+Name]; lpName
0x180017b41  mov     edx, esi; dwIndex
0x180017b43  mov     rcx, [rsp+320h+hKey]; hKey
0x180017b48  call    cs:__imp_RegEnumKeyExW
0x180017b4e  test    eax, eax
0x180017b50  jnz     loc_180017EF5
0x180017b56  mov     [rsp+320h+var_2E0], eax
0x180017b5a  lea     rcx, [rbp+220h+var_278]
0x180017b5e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180017b63  nop
0x180017b64  lea     r9, [rbp+220h+var_278]
0x180017b68  lea     r8, [rsp+320h+var_2E0]
0x180017b6d  lea     rdx, [rbp+220h+Name]
0x180017b71  call    ?GetUserAccountInfo@UserAccountStore@@AEAAXPEBGAEAW4AccountType@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; UserAccountStore::GetUserAccountInfo(ushort const *,AccountType &,std::wstring &)
0x180017b76  mov     rbx, [r14]
0x180017b79  mov     rdi, [r15+40h]
0x180017b7d  jmp     short loc_180017B9A
0x180017b7f  mov     rcx, [rbx]
0x180017b82  mov     rax, [rcx]
0x180017b85  lea     rdx, [rbp+220h+Name]
0x180017b89  mov     rax, [rax+60h]
0x180017b8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017b92  test    al, al
0x180017b94  jnz     short loc_180017BA1
0x180017b96  add     rbx, 8
0x180017b9a  cmp     rbx, rdi
0x180017b9d  jnz     short loc_180017B7F
0x180017b9f  jmp     short loc_180017BB5
0x180017ba1  mov     rcx, [rbx]
0x180017ba4  mov     rax, [rcx]
0x180017ba7  mov     edx, 1
0x180017bac  mov     rax, [rax+48h]
0x180017bb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017bb5  cmp     rbx, [r15+40h]
0x180017bb9  jnz     short loc_180017C3A
0x180017bbb  cmp     [rsp+320h+var_2E0], 4
0x180017bc0  jz      loc_180017E3D
0x180017bc6  mov     [rsp+320h+var_2D8], 0
0x180017bcf  cmp     [rsp+320h+var_2E0], 1
0x180017bd4  jnz     short loc_180017BE1
0x180017bd6  lea     rcx, [rbp+220h+var_278]
0x180017bda  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180017bdf  jmp     short loc_180017BE3
0x180017be1  xor     eax, eax
0x180017be3  mov     [rsp+320h+var_2C8], rax
0x180017be8  lea     r9, [rsp+320h+var_2C8]
0x180017bed  lea     r8, [rsp+320h+var_2E0]
0x180017bf2  lea     rdx, [rbp+220h+Name]
0x180017bf6  lea     rcx, [rsp+320h+var_2D8]; void **
0x180017bfb  call    ??$MakeAndInitialize@VUserAccount@@UIUserAccount@@AEAY0BAE@GAEAW4AccountType@@PEBG@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@UIUserAccount@@@WRL@Microsoft@@@012@AEAY0BAE@GAEAW4AccountType@@$$QEAPEBG@Z; Microsoft::WRL::Details::MakeAndInitialize<UserAccount,IUserAccount,ushort (&)[260],AccountType &,ushort const *>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IUserAccount>>,ushort (&)[260],AccountType &,ushort const * &&)
0x180017c00  mov     rcx, [rbp+228h]; this
0x180017c07  test    eax, eax
0x180017c09  js      loc_180017E4D
0x180017c0f  mov     rdx, [rbp+220h+var_2A0]
0x180017c13  lea     rcx, [rsp+320h+var_2A8]
0x180017c18  cmp     rdx, [rbp+220h+var_298]
0x180017c1c  jz      short loc_180017C2A
0x180017c1e  lea     rdx, [rsp+320h+var_2D8]
0x180017c23  call    ??$_Emplace_back_with_unused_capacity@AEBV?$ComPtr@UIUserAccount@@@WRL@Microsoft@@@?$vector@V?$ComPtr@UIUserAccount@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIUserAccount@@@WRL@Microsoft@@@std@@@std@@AEAAAEAV?$ComPtr@UIUserAccount@@@WRL@Microsoft@@AEBV234@@Z; std::vector<Microsoft::WRL::ComPtr<IUserAccount>>::_Emplace_back_with_unused_capacity<Microsoft::WRL::ComPtr<IUserAccount> const &>(Microsoft::WRL::ComPtr<IUserAccount> const &)
0x180017c28  jmp     short loc_180017C35
0x180017c2a  lea     r8, [rsp+320h+var_2D8]
0x180017c2f  call    ??$_Emplace_reallocate@AEBV?$ComPtr@UIUserAccount@@@WRL@Microsoft@@@?$vector@V?$ComPtr@UIUserAccount@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIUserAccount@@@WRL@Microsoft@@@std@@@std@@AEAAPEAV?$ComPtr@UIUserAccount@@@WRL@Microsoft@@QEAV234@AEBV234@@Z; std::vector<Microsoft::WRL::ComPtr<IUserAccount>>::_Emplace_reallocate<Microsoft::WRL::ComPtr<IUserAccount> const &>(Microsoft::WRL::ComPtr<IUserAccount> * const,Microsoft::WRL::ComPtr<IUserAccount> const &)
0x180017c34  nop
0x180017c35  jmp     loc_180017E32
0x180017c3a  mov     dword ptr [rsp+320h+var_2C8], 4
0x180017c42  mov     rcx, [rbx]
0x180017c45  mov     rax, [rcx]
0x180017c48  lea     rdx, [rsp+320h+var_2C8]
0x180017c4d  mov     rax, [rax+28h]
0x180017c51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017c56  mov     eax, [rsp+320h+var_2E0]
0x180017c5a  cmp     eax, dword ptr [rsp+320h+var_2C8]
0x180017c5e  jz      loc_180017E3D
0x180017c64  mov     [rsp+320h+var_2D8], 0
0x180017c6d  cmp     eax, 1
0x180017c70  jnz     short loc_180017C7D
0x180017c72  lea     rcx, [rbp+220h+var_278]
0x180017c76  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180017c7b  jmp     short loc_180017C7F
0x180017c7d  xor     eax, eax
0x180017c7f  mov     [rbp+220h+var_290], rax
0x180017c83  lea     r9, [rbp+220h+var_290]
0x180017c87  lea     r8, [rsp+320h+var_2E0]
0x180017c8c  lea     rdx, [rbp+220h+Name]
0x180017c90  lea     rcx, [rsp+320h+var_2D8]; void **
0x180017c95  call    ??$MakeAndInitialize@VUserAccount@@UIUserAccount@@AEAY0BAE@GAEAW4AccountType@@PEBG@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@UIUserAccount@@@WRL@Microsoft@@@012@AEAY0BAE@GAEAW4AccountType@@$$QEAPEBG@Z; Microsoft::WRL::Details::MakeAndInitialize<UserAccount,IUserAccount,ushort (&)[260],AccountType &,ushort const *>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IUserAccount>>,ushort (&)[260],AccountType &,ushort const * &&)
0x180017c9a  mov     rcx, [rbp+228h]; this
0x180017ca1  test    eax, eax
0x180017ca3  js      loc_180017EE0
0x180017ca9  mov     [rsp+320h+var_2B0], 0
0x180017cb2  mov     [rsp+320h+var_2D0], 0
0x180017cba  mov     [rsp+320h+var_2CC], 0
0x180017cc2  mov     rcx, [rbx]
0x180017cc5  mov     rax, [rcx]
0x180017cc8  lea     rdx, [rsp+320h+var_2B0]
0x180017ccd  mov     rax, [rax+30h]
0x180017cd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017cd6  mov     rcx, [rbp+228h]; this
0x180017cdd  test    eax, eax
0x180017cdf  js      loc_180017ECB
0x180017ce5  mov     rcx, [rbx]
0x180017ce8  mov     rax, [rcx]
0x180017ceb  lea     rdx, [rsp+320h+var_2D0]
0x180017cf0  mov     rax, [rax+40h]
0x180017cf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017cf9  mov     rcx, [rbp+228h]; this
0x180017d00  test    eax, eax
0x180017d02  js      loc_180017EB6
0x180017d08  mov     rcx, [rbx]
0x180017d0b  mov     rax, [rcx]
0x180017d0e  lea     rdx, [rsp+320h+var_2CC]
0x180017d13  mov     rax, [rax+50h]
0x180017d17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017d1c  mov     rcx, [rbp+228h]; this
0x180017d23  test    eax, eax
0x180017d25  js      loc_180017EA1
0x180017d2b  mov     rcx, [rsp+320h+var_2D8]
0x180017d30  mov     rax, [rcx]
0x180017d33  mov     rdx, [rsp+320h+var_2B0]
0x180017d38  mov     rax, [rax+38h]
0x180017d3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017d41  mov     rcx, [rbp+228h]; this
0x180017d48  test    eax, eax
0x180017d4a  js      loc_180017E8C
0x180017d50  mov     rcx, [rsp+320h+var_2D8]
0x180017d55  mov     rax, [rcx]
0x180017d58  mov     edx, [rsp+320h+var_2D0]
0x180017d5c  mov     rax, [rax+48h]
0x180017d60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017d65  mov     rcx, [rbp+228h]; this
0x180017d6c  test    eax, eax
0x180017d6e  js      loc_180017E77
0x180017d74  mov     rcx, [rsp+320h+var_2D8]
0x180017d79  mov     rax, [rcx]
0x180017d7c  mov     edx, [rsp+320h+var_2CC]
0x180017d80  mov     rax, [rax+58h]
0x180017d84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017d89  mov     rcx, [rbp+228h]; this
0x180017d90  test    eax, eax
0x180017d92  js      loc_180017E62
0x180017d98  lea     rcx, [rbx+8]
0x180017d9c  mov     r8, rbx
0x180017d9f  mov     rdx, [r15+40h]
0x180017da3  call    ??$_Move_unchecked@PEAV?$ComPtr@UIUserAccount@@@WRL@Microsoft@@PEAV123@@std@@YAPEAV?$ComPtr@UIUserAccount@@@WRL@Microsoft@@PEAV123@00@Z; std::_Move_unchecked<Microsoft::WRL::ComPtr<IUserAccount> *,Microsoft::WRL::ComPtr<IUserAccount> *>(Microsoft::WRL::ComPtr<IUserAccount> *,Microsoft::WRL::ComPtr<IUserAccount> *,Microsoft::WRL::ComPtr<IUserAccount> *)
0x180017da8  mov     rcx, [r15+40h]
0x180017dac  sub     rcx, 8
0x180017db0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180017db5  add     qword ptr [r15+40h], 0FFFFFFFFFFFFFFF8h
0x180017dba  mov     rdi, [r15+40h]
0x180017dbe  cmp     rdi, [r14+10h]
0x180017dc2  jz      short loc_180017E21
0x180017dc4  cmp     rbx, rdi
0x180017dc7  jnz     short loc_180017DD8
0x180017dc9  lea     rdx, [rsp+320h+var_2D8]
0x180017dce  mov     rcx, r14
0x180017dd1  call    ??$_Emplace_back_with_unused_capacity@AEBV?$ComPtr@UIUserAccount@@@WRL@Microsoft@@@?$vector@V?$ComPtr@UIUserAccount@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIUserAccount@@@WRL@Microsoft@@@std@@@std@@AEAAAEAV?$ComPtr@UIUserAccount@@@WRL@Microsoft@@AEBV234@@Z; std::vector<Microsoft::WRL::ComPtr<IUserAccount>>::_Emplace_back_with_unused_capacity<Microsoft::WRL::ComPtr<IUserAccount> const &>(Microsoft::WRL::ComPtr<IUserAccount> const &)
0x180017dd6  jmp     short loc_180017E32
0x180017dd8  mov     [rbp+220h+var_288], r14
0x180017ddc  lea     r8, [rsp+320h+var_2D8]
0x180017de1  lea     rdx, [rbp+220h+var_280]
0x180017de5  call    ??$construct@V?$ComPtr@UIUserAccount@@@WRL@Microsoft@@AEAV123@@?$_Default_allocator_traits@V?$allocator@V?$ComPtr@UIUserAccount@@@WRL@Microsoft@@@std@@@std@@SAXAEAV?$allocator@V?$ComPtr@UIUserAccount@@@WRL@Microsoft@@@1@QEAV?$ComPtr@UIUserAccount@@@WRL@Microsoft@@AEAV345@@Z; std::_Default_allocator_traits<std::allocator<Microsoft::WRL::ComPtr<IUserAccount>>>::construct<Microsoft::WRL::ComPtr<IUserAccount>,Microsoft::WRL::ComPtr<IUserAccount> &>(std::allocator<Microsoft::WRL::ComPtr<IUserAccount>> &,Microsoft::WRL::ComPtr<IUserAccount> * const,Microsoft::WRL::ComPtr<IUserAccount> &)
0x180017dea  lea     r8, [rdi-8]
0x180017dee  mov     rdx, rdi
0x180017df1  call    ??$construct@V?$ComPtr@UIUserAccount@@@WRL@Microsoft@@V123@@?$_Default_allocator_traits@V?$allocator@V?$ComPtr@UIUserAccount@@@WRL@Microsoft@@@std@@@std@@SAXAEAV?$allocator@V?$ComPtr@UIUserAccount@@@WRL@Microsoft@@@1@QEAV?$ComPtr@UIUserAccount@@@WRL@Microsoft@@$$QEAV345@@Z; std::_Default_allocator_traits<std::allocator<Microsoft::WRL::ComPtr<IUserAccount>>>::construct<Microsoft::WRL::ComPtr<IUserAccount>,Microsoft::WRL::ComPtr<IUserAccount>>(std::allocator<Microsoft::WRL::ComPtr<IUserAccount>> &,Microsoft::WRL::ComPtr<IUserAccount> * const,Microsoft::WRL::ComPtr<IUserAccount> &&)
0x180017df6  add     qword ptr [r14+8], 8
0x180017dfb  mov     r8, rdi
0x180017dfe  lea     rdx, [rdi-8]
0x180017e02  mov     rcx, rbx
0x180017e05  call    ??$_Move_backward_unchecked@PEAV?$ComPtr@UIUserAccount@@@WRL@Microsoft@@PEAV123@@std@@YAPEAV?$ComPtr@UIUserAccount@@@WRL@Microsoft@@PEAV123@00@Z; std::_Move_backward_unchecked<Microsoft::WRL::ComPtr<IUserAccount> *,Microsoft::WRL::ComPtr<IUserAccount> *>(Microsoft::WRL::ComPtr<IUserAccount> *,Microsoft::WRL::ComPtr<IUserAccount> *,Microsoft::WRL::ComPtr<IUserAccount> *)
0x180017e0a  lea     rdx, [rbp+220h+var_280]
0x180017e0e  mov     rcx, rbx
0x180017e11  call    ??4?$ComPtr@UIUserAccount@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<IUserAccount>::operator=(Microsoft::WRL::ComPtr<IUserAccount> &&)
0x180017e16  lea     rcx, [rbp+220h+var_280]
0x180017e1a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180017e1f  jmp     short loc_180017E32
0x180017e21  lea     r8, [rsp+320h+var_2D8]
0x180017e26  mov     rdx, rbx
0x180017e29  mov     rcx, r14
0x180017e2c  call    ??$_Emplace_reallocate@AEBV?$ComPtr@UIUserAccount@@@WRL@Microsoft@@@?$vector@V?$ComPtr@UIUserAccount@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIUserAccount@@@WRL@Microsoft@@@std@@@std@@AEAAPEAV?$ComPtr@UIUserAccount@@@WRL@Microsoft@@QEAV234@AEBV234@@Z; std::vector<Microsoft::WRL::ComPtr<IUserAccount>>::_Emplace_reallocate<Microsoft::WRL::ComPtr<IUserAccount> const &>(Microsoft::WRL::ComPtr<IUserAccount> * const,Microsoft::WRL::ComPtr<IUserAccount> const &)
0x180017e31  nop
0x180017e32  lea     rcx, [rsp+320h+var_2D8]
0x180017e37  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180017e3c  nop
0x180017e3d  lea     rcx, [rbp+220h+var_278]
0x180017e41  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180017e46  inc     esi
0x180017e48  jmp     loc_180017B0C
0x180017e4d  mov     r9d, eax; char *
0x180017e50  lea     r8, aShellcommonShe_7; "shellcommon\\shell\\sharedpc\\accountma"...
0x180017e57  mov     edx, 1A7h; void *
0x180017e5c  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180017e62  mov     r9d, eax; char *
0x180017e65  lea     r8, aShellcommonShe_7; "shellcommon\\shell\\sharedpc\\accountma"...
0x180017e6c  mov     edx, 1BFh; void *
0x180017e71  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180017e77  mov     r9d, eax; char *
0x180017e7a  lea     r8, aShellcommonShe_7; "shellcommon\\shell\\sharedpc\\accountma"...
0x180017e81  mov     edx, 1BEh; void *
0x180017e86  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180017e8c  mov     r9d, eax; char *
0x180017e8f  lea     r8, aShellcommonShe_7; "shellcommon\\shell\\sharedpc\\accountma"...
0x180017e96  mov     edx, 1BDh; void *
0x180017e9b  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180017ea1  mov     r9d, eax; char *
0x180017ea4  lea     r8, aShellcommonShe_7; "shellcommon\\shell\\sharedpc\\accountma"...
0x180017eab  mov     edx, 1BBh; void *
0x180017eb0  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180017eb6  mov     r9d, eax; char *
0x180017eb9  lea     r8, aShellcommonShe_7; "shellcommon\\shell\\sharedpc\\accountma"...
0x180017ec0  mov     edx, 1BAh; void *
0x180017ec5  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180017ecb  mov     r9d, eax; char *
0x180017ece  lea     r8, aShellcommonShe_7; "shellcommon\\shell\\sharedpc\\accountma"...
0x180017ed5  mov     edx, 1B9h; void *
0x180017eda  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180017ee0  mov     r9d, eax; char *
0x180017ee3  lea     r8, aShellcommonShe_7; "shellcommon\\shell\\sharedpc\\accountma"...
0x180017eea  mov     edx, 1B4h; void *
0x180017eef  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180017ef5  cmp     eax, 103h
0x180017efa  jnz     loc_180017FD0
0x180017f00  mov     rdi, [r14+8]
0x180017f04  mov     rbx, [r14]
0x180017f07  cmp     rbx, rdi
0x180017f0a  jz      short loc_180017F7A
0x180017f0c  mov     rdx, rbx
0x180017f0f  call    _lambda_90d4a07a344ba25b30dad4eaecd3f18e___operator__
0x180017f14  test    al, al
0x180017f16  jnz     short loc_180017F21
0x180017f18  add     rbx, 8
0x180017f1c  cmp     rbx, rdi
0x180017f1f  jnz     short loc_180017F0C
0x180017f21  cmp     rbx, rdi
0x180017f24  jz      short loc_180017F7A
0x180017f26  lea     rsi, [rbx+8]
0x180017f2a  cmp     rsi, rdi
0x180017f2d  jz      short loc_180017F58
0x180017f2f  mov     rdx, rsi
0x180017f32  call    _lambda_90d4a07a344ba25b30dad4eaecd3f18e___operator__
0x180017f37  test    al, al
0x180017f39  jnz     short loc_180017F4A
  ... truncated ...
```
