# ConnectedStorage::UserManager::GetLocalUsers(void)

- ea: `0x18002b5b0`
- end: `0x18002b97e`
- name: `?GetLocalUsers@UserManager@ConnectedStorage@@UEBA?AV?$vector@VSimpleHStringWrapper@ConnectedStorage@@V?$allocator@VSimpleHStringWrapper@ConnectedStorage@@@std@@@std@@XZ`
- size: `974`
- prototype: `__int64 __fastcall(ConnectedStorage::UserManager *this)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000a040`
- `0x18000aae4`
- `0x18000cb9c`
- `0x180011b94`
- `0x180011c0c`
- `0x180028cf4`
- `0x180029824`
- `0x180029e38`
- `0x18002a740`
- `0x18002b5b0`
- `0x18002b9e4`
- `0x18002cf5c`
- `0x18002e394`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002b8fa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002b8fa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b7ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b81e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b891`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b89f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b7ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b81e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b891`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002b89f`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
__int64 __fastcall ConnectedStorage::UserManager::GetLocalUsers(
        ConnectedStorage::UserManager *this,
        __int64 a2,
        char *a3)
{
  char *v5; // r15
  __int64 v6; // r14
  __int64 v7; // rbx
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)); // rbx
  int v10; // eax
  const unsigned __int16 *v11; // r8
  __int64 (__fastcall ***v12)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v13)(_QWORD, GUID *, __int64 *); // rdi
  int v14; // eax
  const unsigned __int16 *v15; // r8
  __int64 v16; // rdi
  __int64 (__fastcall *v17)(__int64, __int64 *); // rbx
  int v18; // eax
  const unsigned __int16 *v19; // r8
  int v20; // eax
  const unsigned __int16 *v21; // r8
  __int64 v22; // rdi
  __int64 (__fastcall *v23)(__int64, __int64 *); // rbx
  int v24; // eax
  const unsigned __int16 *v25; // r8
  __int64 v26; // rdi
  __int64 (__fastcall *v27)(__int64, __int64 *); // rbx
  int v28; // eax
  const unsigned __int16 *v29; // r8
  int v30; // eax
  const unsigned __int16 *v31; // r8
  HSTRING *v32; // rax
  __int64 v33; // rcx
  HSTRING *v34; // rax
  __int64 v35; // rcx
  HSTRING v37; // [rsp+20h] [rbp-59h] BYREF
  __int64 v38; // [rsp+28h] [rbp-51h] BYREF
  __int64 v39; // [rsp+30h] [rbp-49h] BYREF
  HSTRING v40; // [rsp+38h] [rbp-41h] BYREF
  __int64 v41; // [rsp+40h] [rbp-39h] BYREF
  __int64 v42; // [rsp+48h] [rbp-31h] BYREF
  __int64 (__fastcall ***v43)(_QWORD, GUID *, __int64 *); // [rsp+50h] [rbp-29h] BYREF
  HSTRING string; // [rsp+58h] [rbp-21h] BYREF
  HSTRING v45; // [rsp+60h] [rbp-19h] BYREF
  HSTRING v46; // [rsp+68h] [rbp-11h] BYREF
  HSTRING newString; // [rsp+70h] [rbp-9h] BYREF
  HSTRING v48; // [rsp+78h] [rbp-1h] BYREF
  HSTRING v49; // [rsp+80h] [rbp+7h] BYREF
  LPCRITICAL_SECTION lpCriticalSection[9]; // [rsp+88h] [rbp+Fh] BYREF
  char v51; // [rsp+E0h] [rbp+67h] BYREF
  __int64 v52; // [rsp+E8h] [rbp+6Fh]
  unsigned int v53; // [rsp+F0h] [rbp+77h] BYREF
  int v54; // [rsp+F8h] [rbp+7Fh]

  v52 = a2;
  v54 = 1;
  ConnectedStorage::Mutex::Lock::Lock(
    (ConnectedStorage::Mutex::Lock *)lpCriticalSection,
    (struct _RTL_CRITICAL_SECTION *)((char *)this + 168),
    a3);
  ConnectedStorage::UserManager::EnsureUserStatics(this);
  *(_QWORD *)a2 = 0;
  *(_QWORD *)(a2 + 8) = 0;
  *(_QWORD *)(a2 + 16) = 0;
  v54 = 1;
  v5 = (char *)this + 264;
  v6 = *((_QWORD *)this + 34);
  v7 = *((_QWORD *)this + 33);
  if ( v7 == v6 )
  {
    v43 = 0;
    v8 = *((_QWORD *)this + 36);
    v9 = *(__int64 (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)v8 + 88LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
    v10 = v9(v8, &v43);
    if ( v10 < 0 )
      ConnectedStorage::ReportErrorAndThrow(
        (ConnectedStorage *)(unsigned int)v10,
        (int)L"_userMgrStatics->get_Profiles(&userProfiles)",
        v11);
    v42 = 0;
    v12 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v43;
    v13 = **v43;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
    v14 = v13(v12, &GUID_65dcc3f8_46ff_52db_977c_af5d75a301c6, &v42);
    if ( v14 < 0 )
      ConnectedStorage::ReportErrorAndThrow(
        (ConnectedStorage *)(unsigned int)v14,
        (int)L"userProfiles.As(&iterable)",
        v15);
    v39 = 0;
    v16 = v42;
    v17 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v42 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39);
    v18 = v17(v16, &v39);
    if ( v18 < 0 )
      ConnectedStorage::ReportErrorAndThrow(
        (ConnectedStorage *)(unsigned int)v18,
        (int)L"iterable->First(&iterator)",
        v19);
    v51 = 0;
    v20 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v39 + 56LL))(v39, &v51);
    if ( v20 < 0 )
      ConnectedStorage::ReportErrorAndThrow(
        (ConnectedStorage *)(unsigned int)v20,
        (int)L"iterator->get_HasCurrent(&hasCurrent)",
        v21);
    do
    {
      if ( !v51 )
        break;
      v41 = 0;
      v22 = v39;
      v23 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v39 + 48LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v41);
      v24 = v23(v22, &v41);
      if ( v24 < 0 )
        ConnectedStorage::ReportErrorAndThrow(
          (ConnectedStorage *)(unsigned int)v24,
          (int)L"iterator->get_Current(&profile)",
          v25);
      v38 = 0;
      v26 = v41;
      v27 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v41 + 88LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v38);
      v28 = v27(v26, &v38);
      if ( v28 < 0 )
        ConnectedStorage::ReportErrorAndThrow(
          (ConnectedStorage *)(unsigned int)v28,
          (int)L"profile->get_Properties(&propSet)",
          v29);
      v53 = 0;
      v30 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v41 + 48LL))(v41, &v53);
      if ( v30 < 0 )
        ConnectedStorage::ReportErrorAndThrow(
          (ConnectedStorage *)(unsigned int)v30,
          (int)L"profile->get_Id(&userId)",
          v31);
      v32 = ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(&string, L"XboxUserId");
      ConnectedStorage::UserManager::GetPropertyValue(v33, &v37, v38, v32);
      WindowsDeleteString(string);
      string = 0;
      v34 = ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(&v45, L"Sid");
      ConnectedStorage::UserManager::GetPropertyValue(v35, &v40, v38, v34);
      WindowsDeleteString(v45);
      v45 = 0;
      if ( !ConnectedStorage::SimpleHStringWrapper::IsEmpty((ConnectedStorage::SimpleHStringWrapper *)&v37) )
      {
        if ( *(_QWORD *)(a2 + 8) == *(_QWORD *)(a2 + 16) )
        {
          std::vector<ConnectedStorage::SimpleHStringWrapper>::_Emplace_reallocate<ConnectedStorage::SimpleHStringWrapper const &>(
            a2,
            *(_QWORD *)(a2 + 8),
            &v37);
        }
        else
        {
          ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(*(HSTRING **)(a2 + 8), &v37);
          *(_QWORD *)(a2 + 8) += 8LL;
        }
        ConnectedStorage::UserManager::LocalUserInfo::LocalUserInfo(
          &v46,
          v53,
          (const struct ConnectedStorage::SimpleHStringWrapper *)&v40,
          (const struct ConnectedStorage::SimpleHStringWrapper *)&v37);
        std::vector<ConnectedStorage::UserManager::LocalUserInfo>::push_back(v5, &v46);
        ConnectedStorage::UserManager::LocalUserInfo::~LocalUserInfo((ConnectedStorage::UserManager::LocalUserInfo *)&v46);
      }
      WindowsDeleteString(v40);
      v40 = 0;
      WindowsDeleteString(v37);
      v37 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v38);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v41);
    }
    while ( (*(int (__fastcall **)(__int64, char *))(*(_QWORD *)v39 + 64LL))(v39, &v51) >= 0 );
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
  }
  else
  {
    do
    {
      LODWORD(v46) = *(_DWORD *)v7;
      ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(&newString, (HSTRING *)(v7 + 8));
      ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(&v48, (HSTRING *)(v7 + 16));
      ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(&v49, (HSTRING *)(v7 + 24));
      if ( *(_QWORD *)(a2 + 8) == *(_QWORD *)(a2 + 16) )
      {
        std::vector<ConnectedStorage::SimpleHStringWrapper>::_Emplace_reallocate<ConnectedStorage::SimpleHStringWrapper const &>(
          a2,
          *(_QWORD *)(a2 + 8),
          &newString);
      }
      else
      {
        ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(*(HSTRING **)(a2 + 8), &newString);
        *(_QWORD *)(a2 + 8) += 8LL;
      }
      ConnectedStorage::UserManager::LocalUserInfo::~LocalUserInfo((ConnectedStorage::UserManager::LocalUserInfo *)&v46);
      v7 += 32;
    }
    while ( v7 != v6 );
  }
  LeaveCriticalSection(lpCriticalSection[0]);
  return a2;
}

```

## disassembly

```asm
0x18002b5b0  mov     [rsp-8+arg_8], rdx
0x18002b5b5  push    rbp
0x18002b5b6  push    rbx
0x18002b5b7  push    rsi
0x18002b5b8  push    rdi
0x18002b5b9  push    r12
0x18002b5bb  push    r14
0x18002b5bd  push    r15
0x18002b5bf  lea     rbp, [rsp-27h]
0x18002b5c4  sub     rsp, 0A0h
0x18002b5cb  mov     rsi, rdx
0x18002b5ce  mov     rdi, rcx
0x18002b5d1  mov     ebx, 1
0x18002b5d6  mov     [rbp+57h+arg_18], ebx
0x18002b5d9  lea     rdx, [rcx+0A8h]; struct ConnectedStorage::Mutex *
0x18002b5e0  lea     rcx, [rbp+57h+lpCriticalSection]; this
0x18002b5e4  call    ??0Lock@Mutex@ConnectedStorage@@QEAA@AEAV12@PEAD@Z; ConnectedStorage::Mutex::Lock::Lock(ConnectedStorage::Mutex &,char *)
0x18002b5e9  nop
0x18002b5ea  mov     rcx, rdi; this
0x18002b5ed  call    ?EnsureUserStatics@UserManager@ConnectedStorage@@AEBAXXZ; ConnectedStorage::UserManager::EnsureUserStatics(void)
0x18002b5f2  xor     r12d, r12d
0x18002b5f5  mov     [rsi], r12
0x18002b5f8  mov     [rsi+8], r12
0x18002b5fc  mov     [rsi+10h], r12
0x18002b600  mov     [rbp+57h+arg_18], ebx
0x18002b603  lea     r15, [rdi+108h]
0x18002b60a  mov     r14, [r15+8]
0x18002b60e  mov     rbx, [r15]
0x18002b611  cmp     rbx, r14
0x18002b614  jz      short loc_18002B689
0x18002b616  mov     eax, [rbx]
0x18002b618  mov     dword ptr [rbp+57h+var_68], eax
0x18002b61b  lea     rdx, [rbx+8]; struct ConnectedStorage::SimpleHStringWrapper *
0x18002b61f  lea     rcx, [rbp+57h+newString]; newString
0x18002b623  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@AEBV01@@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(ConnectedStorage::SimpleHStringWrapper const &)
0x18002b628  nop
0x18002b629  lea     rdx, [rbx+10h]; struct ConnectedStorage::SimpleHStringWrapper *
0x18002b62d  lea     rcx, [rbp+57h+var_58]; newString
0x18002b631  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@AEBV01@@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(ConnectedStorage::SimpleHStringWrapper const &)
0x18002b636  nop
0x18002b637  lea     rdx, [rbx+18h]; struct ConnectedStorage::SimpleHStringWrapper *
0x18002b63b  lea     rcx, [rbp+57h+var_50]; newString
0x18002b63f  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@AEBV01@@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(ConnectedStorage::SimpleHStringWrapper const &)
0x18002b644  nop
0x18002b645  mov     rax, [rsi+8]
0x18002b649  cmp     rax, [rsi+10h]
0x18002b64d  jz      short loc_18002B662
0x18002b64f  lea     rdx, [rbp+57h+newString]; struct ConnectedStorage::SimpleHStringWrapper *
0x18002b653  mov     rcx, rax; newString
0x18002b656  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@AEBV01@@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(ConnectedStorage::SimpleHStringWrapper const &)
0x18002b65b  add     qword ptr [rsi+8], 8
0x18002b660  jmp     short loc_18002B672
0x18002b662  lea     r8, [rbp+57h+newString]
0x18002b666  mov     rdx, rax
0x18002b669  mov     rcx, rsi
0x18002b66c  call    ??$_Emplace_reallocate@AEBVSimpleHStringWrapper@ConnectedStorage@@@?$vector@VSimpleHStringWrapper@ConnectedStorage@@V?$allocator@VSimpleHStringWrapper@ConnectedStorage@@@std@@@std@@AEAAPEAVSimpleHStringWrapper@ConnectedStorage@@QEAV23@AEBV23@@Z; std::vector<ConnectedStorage::SimpleHStringWrapper>::_Emplace_reallocate<ConnectedStorage::SimpleHStringWrapper const &>(ConnectedStorage::SimpleHStringWrapper * const,ConnectedStorage::SimpleHStringWrapper const &)
0x18002b671  nop
0x18002b672  lea     rcx, [rbp+57h+var_68]; this
0x18002b676  call    ??1LocalUserInfo@UserManager@ConnectedStorage@@QEAA@XZ; ConnectedStorage::UserManager::LocalUserInfo::~LocalUserInfo(void)
0x18002b67b  add     rbx, 20h ; ' '
0x18002b67f  cmp     rbx, r14
0x18002b682  jnz     short loc_18002B616
0x18002b684  jmp     loc_18002B8F6
0x18002b689  mov     [rbp+57h+var_80], r12
0x18002b68d  mov     rdi, [rdi+120h]
0x18002b694  mov     rax, [rdi]
0x18002b697  mov     rbx, [rax+58h]
0x18002b69b  lea     rcx, [rbp+57h+var_80]
0x18002b69f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002b6a4  lea     rdx, [rbp+57h+var_80]
0x18002b6a8  mov     rcx, rdi
0x18002b6ab  mov     rax, rbx
0x18002b6ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b6b3  test    eax, eax
0x18002b6b5  js      loc_18002B933
0x18002b6bb  mov     [rbp+57h+var_88], r12
0x18002b6bf  mov     rbx, [rbp+57h+var_80]
0x18002b6c3  mov     rax, [rbx]
0x18002b6c6  mov     rdi, [rax]
0x18002b6c9  lea     rcx, [rbp+57h+var_88]
0x18002b6cd  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002b6d2  lea     r8, [rbp+57h+var_88]
0x18002b6d6  lea     rdx, _GUID_65dcc3f8_46ff_52db_977c_af5d75a301c6
0x18002b6dd  mov     rcx, rbx
0x18002b6e0  mov     rax, rdi
0x18002b6e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b6e8  nop
0x18002b6e9  test    eax, eax
0x18002b6eb  js      loc_18002B942
0x18002b6f1  mov     [rbp+57h+var_A0], r12
0x18002b6f5  mov     rdi, [rbp+57h+var_88]
0x18002b6f9  mov     rax, [rdi]
0x18002b6fc  mov     rbx, [rax+30h]
0x18002b700  lea     rcx, [rbp+57h+var_A0]
0x18002b704  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002b709  lea     rdx, [rbp+57h+var_A0]
0x18002b70d  mov     rcx, rdi
0x18002b710  mov     rax, rbx
0x18002b713  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b718  test    eax, eax
0x18002b71a  js      loc_18002B951
0x18002b720  mov     [rbp+57h+arg_0], r12b
0x18002b724  mov     rcx, [rbp+57h+var_A0]
0x18002b728  mov     rax, [rcx]
0x18002b72b  lea     rdx, [rbp+57h+arg_0]
0x18002b72f  mov     rax, [rax+38h]
0x18002b733  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b738  test    eax, eax
0x18002b73a  js      loc_18002B960
0x18002b740  cmp     [rbp+57h+arg_0], r12b
0x18002b744  jz      loc_18002B8D8
0x18002b74a  mov     [rbp+57h+var_90], r12
0x18002b74e  mov     rdi, [rbp+57h+var_A0]
0x18002b752  mov     rax, [rdi]
0x18002b755  mov     rbx, [rax+30h]
0x18002b759  lea     rcx, [rbp+57h+var_90]
0x18002b75d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002b762  lea     rdx, [rbp+57h+var_90]
0x18002b766  mov     rcx, rdi
0x18002b769  mov     rax, rbx
0x18002b76c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b771  test    eax, eax
0x18002b773  js      loc_18002B924
0x18002b779  mov     [rbp+57h+var_A8], r12
0x18002b77d  mov     rdi, [rbp+57h+var_90]
0x18002b781  mov     rax, [rdi]
0x18002b784  mov     rbx, [rax+58h]
0x18002b788  lea     rcx, [rbp+57h+var_A8]
0x18002b78c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002b791  lea     rdx, [rbp+57h+var_A8]
0x18002b795  mov     rcx, rdi
0x18002b798  mov     rax, rbx
0x18002b79b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b7a0  test    eax, eax
0x18002b7a2  js      loc_18002B915
0x18002b7a8  mov     [rbp+57h+arg_10], r12d
0x18002b7ac  mov     rcx, [rbp+57h+var_90]
0x18002b7b0  mov     rax, [rcx]
0x18002b7b3  lea     rdx, [rbp+57h+arg_10]
0x18002b7b7  mov     rax, [rax+30h]
0x18002b7bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b7c0  test    eax, eax
0x18002b7c2  js      loc_18002B96F
0x18002b7c8  lea     rdx, aXboxuserid; "XboxUserId"
0x18002b7cf  lea     rcx, [rbp+57h+string]; string
0x18002b7d3  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@PEBG@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(ushort const *)
0x18002b7d8  nop
0x18002b7d9  mov     r9, rax
0x18002b7dc  mov     r8, [rbp+57h+var_A8]
0x18002b7e0  lea     rdx, [rbp+57h+var_B0]
0x18002b7e4  call    ?GetPropertyValue@UserManager@ConnectedStorage@@AEBA?AVSimpleHStringWrapper@2@PEAUIPropertySet@Collections@Foundation@Windows@@AEBV32@@Z; ConnectedStorage::UserManager::GetPropertyValue(Windows::Foundation::Collections::IPropertySet *,ConnectedStorage::SimpleHStringWrapper const &)
0x18002b7e9  nop
0x18002b7ea  mov     rcx, [rbp+57h+string]; string
0x18002b7ee  call    cs:__imp_WindowsDeleteString
0x18002b7f4  mov     [rbp+57h+string], r12
0x18002b7f8  lea     rdx, aSid; "Sid"
0x18002b7ff  lea     rcx, [rbp+57h+var_70]; string
0x18002b803  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@PEBG@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(ushort const *)
0x18002b808  nop
0x18002b809  mov     r9, rax
0x18002b80c  mov     r8, [rbp+57h+var_A8]
0x18002b810  lea     rdx, [rbp+57h+var_98]
0x18002b814  call    ?GetPropertyValue@UserManager@ConnectedStorage@@AEBA?AVSimpleHStringWrapper@2@PEAUIPropertySet@Collections@Foundation@Windows@@AEBV32@@Z; ConnectedStorage::UserManager::GetPropertyValue(Windows::Foundation::Collections::IPropertySet *,ConnectedStorage::SimpleHStringWrapper const &)
0x18002b819  nop
0x18002b81a  mov     rcx, [rbp+57h+var_70]; string
0x18002b81e  call    cs:__imp_WindowsDeleteString
0x18002b824  mov     [rbp+57h+var_70], r12
0x18002b828  lea     rcx, [rbp+57h+var_B0]; this
0x18002b82c  call    ?IsEmpty@SimpleHStringWrapper@ConnectedStorage@@QEBA_NXZ; ConnectedStorage::SimpleHStringWrapper::IsEmpty(void)
0x18002b831  test    al, al
0x18002b833  jnz     short loc_18002B88D
0x18002b835  mov     rax, [rsi+8]
0x18002b839  cmp     rax, [rsi+10h]
0x18002b83d  jz      short loc_18002B852
0x18002b83f  lea     rdx, [rbp+57h+var_B0]; struct ConnectedStorage::SimpleHStringWrapper *
0x18002b843  mov     rcx, rax; newString
0x18002b846  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@AEBV01@@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(ConnectedStorage::SimpleHStringWrapper const &)
0x18002b84b  add     qword ptr [rsi+8], 8
0x18002b850  jmp     short loc_18002B861
0x18002b852  lea     r8, [rbp+57h+var_B0]
0x18002b856  mov     rdx, rax
0x18002b859  mov     rcx, rsi
0x18002b85c  call    ??$_Emplace_reallocate@AEBVSimpleHStringWrapper@ConnectedStorage@@@?$vector@VSimpleHStringWrapper@ConnectedStorage@@V?$allocator@VSimpleHStringWrapper@ConnectedStorage@@@std@@@std@@AEAAPEAVSimpleHStringWrapper@ConnectedStorage@@QEAV23@AEBV23@@Z; std::vector<ConnectedStorage::SimpleHStringWrapper>::_Emplace_reallocate<ConnectedStorage::SimpleHStringWrapper const &>(ConnectedStorage::SimpleHStringWrapper * const,ConnectedStorage::SimpleHStringWrapper const &)
0x18002b861  lea     r9, [rbp+57h+var_B0]; struct ConnectedStorage::SimpleHStringWrapper *
0x18002b865  lea     r8, [rbp+57h+var_98]; struct ConnectedStorage::SimpleHStringWrapper *
0x18002b869  mov     edx, [rbp+57h+arg_10]; unsigned int
0x18002b86c  lea     rcx, [rbp+57h+var_68]; this
0x18002b870  call    ??0LocalUserInfo@UserManager@ConnectedStorage@@QEAA@IAEBVSimpleHStringWrapper@2@0@Z; ConnectedStorage::UserManager::LocalUserInfo::LocalUserInfo(uint,ConnectedStorage::SimpleHStringWrapper const &,ConnectedStorage::SimpleHStringWrapper const &)
0x18002b875  nop
0x18002b876  lea     rdx, [rbp+57h+var_68]
0x18002b87a  mov     rcx, r15
0x18002b87d  call    ?push_back@?$vector@ULocalUserInfo@UserManager@ConnectedStorage@@V?$allocator@ULocalUserInfo@UserManager@ConnectedStorage@@@std@@@std@@QEAAX$$QEAULocalUserInfo@UserManager@ConnectedStorage@@@Z; std::vector<ConnectedStorage::UserManager::LocalUserInfo>::push_back(ConnectedStorage::UserManager::LocalUserInfo &&)
0x18002b882  nop
0x18002b883  lea     rcx, [rbp+57h+var_68]; this
0x18002b887  call    ??1LocalUserInfo@UserManager@ConnectedStorage@@QEAA@XZ; ConnectedStorage::UserManager::LocalUserInfo::~LocalUserInfo(void)
0x18002b88c  nop
0x18002b88d  mov     rcx, [rbp+57h+var_98]; string
0x18002b891  call    cs:__imp_WindowsDeleteString
0x18002b897  mov     [rbp+57h+var_98], r12
0x18002b89b  mov     rcx, [rbp+57h+var_B0]; string
0x18002b89f  call    cs:__imp_WindowsDeleteString
0x18002b8a5  mov     [rbp+57h+var_B0], r12
0x18002b8a9  lea     rcx, [rbp+57h+var_A8]
0x18002b8ad  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002b8b2  nop
0x18002b8b3  lea     rcx, [rbp+57h+var_90]
0x18002b8b7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002b8bc  mov     rcx, [rbp+57h+var_A0]
0x18002b8c0  mov     rax, [rcx]
0x18002b8c3  lea     rdx, [rbp+57h+arg_0]
0x18002b8c7  mov     rax, [rax+40h]
0x18002b8cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b8d0  test    eax, eax
0x18002b8d2  jns     loc_18002B740
0x18002b8d8  lea     rcx, [rbp+57h+var_A0]
0x18002b8dc  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002b8e1  nop
0x18002b8e2  lea     rcx, [rbp+57h+var_88]
0x18002b8e6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002b8eb  nop
0x18002b8ec  lea     rcx, [rbp+57h+var_80]
0x18002b8f0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002b8f5  nop
0x18002b8f6  mov     rcx, [rbp+57h+lpCriticalSection]; lpCriticalSection
0x18002b8fa  call    cs:__imp_LeaveCriticalSection
0x18002b900  mov     rax, rsi
0x18002b903  add     rsp, 0A0h
0x18002b90a  pop     r15
0x18002b90c  pop     r14
0x18002b90e  pop     r12
0x18002b910  pop     rdi
0x18002b911  pop     rsi
0x18002b912  pop     rbx
0x18002b913  pop     rbp
0x18002b914  retn
0x18002b915  lea     rdx, aProfileGetProp; "profile->get_Properties(&propSet)"
0x18002b91c  mov     ecx, eax; this
0x18002b91e  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x18002b924  lea     rdx, aIteratorGetCur; "iterator->get_Current(&profile)"
0x18002b92b  mov     ecx, eax; this
0x18002b92d  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x18002b933  lea     rdx, aUsermgrstatics_1; "_userMgrStatics->get_Profiles(&userProf"...
0x18002b93a  mov     ecx, eax; this
0x18002b93c  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x18002b942  lea     rdx, aUserprofilesAs; "userProfiles.As(&iterable)"
0x18002b949  mov     ecx, eax; this
0x18002b94b  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x18002b951  lea     rdx, aIterableFirstI; "iterable->First(&iterator)"
0x18002b958  mov     ecx, eax; this
0x18002b95a  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x18002b960  lea     rdx, aIteratorGetHas; "iterator->get_HasCurrent(&hasCurrent)"
0x18002b967  mov     ecx, eax; this
0x18002b969  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x18002b96f  lea     rdx, aProfileGetIdUs; "profile->get_Id(&userId)"
0x18002b976  mov     ecx, eax; this
0x18002b978  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
```
