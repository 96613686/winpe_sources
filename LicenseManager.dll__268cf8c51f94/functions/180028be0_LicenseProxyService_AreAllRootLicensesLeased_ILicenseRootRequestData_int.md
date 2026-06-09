# LicenseProxyService::AreAllRootLicensesLeased(ILicenseRootRequestData *,int *)

- ea: `0x180028be0`
- end: `0x1800292b8`
- name: `?AreAllRootLicensesLeased@LicenseProxyService@@UEAAJPEAUILicenseRootRequestData@@PEAH@Z`
- size: `1752`
- prototype: `__int64 __fastcall(LicenseProxyService *__hidden this, struct ILicenseRootRequestData *, int *)`
- caller_count: `0`
- callee_count: `17`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180004738`
- `0x180012dc0`
- `0x180013b50`
- `0x18001f268`
- `0x18001faec`
- `0x180028b10`
- `0x180028be0`
- `0x18002aae8`
- `0x1800332f4`
- `0x180054a54`
- `0x1800593bc`
- `0x180075e60`
- `0x180097f40`
- `0x180098750`
- `0x1800992a4`
- `0x180099364`
- `0x1800b8010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180028c8b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180028ca2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180028c8b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180028ca2`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x180028c23`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x180028c23`

## string_xrefs

- `0x180028c62`: `LicenseProxyService::AreAllRootLicensesLeased`
- `0x180028db0`: `LicenseProxyService::AreAllRootLicensesLeased`
- `0x18002902e`: `LicenseProxyService::AreAllRootLicensesLeased`
- `0x180029160`: `LicenseProxyService::AreAllRootLicensesLeased`

## pseudocode

```c
// Hidden C++ exception states: #wind=13 #try_helpers=1
__int64 __fastcall LicenseProxyService::AreAllRootLicensesLeased(
        LicenseProxyService *this,
        struct ILicenseRootRequestData *a2,
        int *a3)
{
  int v7; // eax
  unsigned int v8; // edi
  PSRWLOCK v9; // r15
  int v10; // eax
  int v11; // ebx
  PSRWLOCK v12; // r14
  unsigned int i; // ebx
  int v14; // eax
  int v15; // eax
  int v16; // eax
  __int64 (__fastcall **Ptr)(PSRWLOCK, RTL_SRWLOCK **); // rax
  int v18; // eax
  int v19; // eax
  int v20; // eax
  unsigned int v21; // edx
  __int64 *v22; // rcx
  unsigned int j; // ebx
  __int64 v24; // rax
  int v25; // eax
  __int64 *v26; // rcx
  __int64 *v27; // rcx
  int Format; // [rsp+20h] [rbp-E8h]
  unsigned int v29; // [rsp+40h] [rbp-C8h] BYREF
  __int64 *v30; // [rsp+48h] [rbp-C0h] BYREF
  PSRWLOCK SRWLock; // [rsp+50h] [rbp-B8h] BYREF
  RTL_SRWLOCK *v32; // [rsp+58h] [rbp-B0h] BYREF
  ContentIdString *v33[2]; // [rsp+60h] [rbp-A8h] BYREF
  ContentIdString *v34; // [rsp+70h] [rbp-98h]
  int v35; // [rsp+78h] [rbp-90h] BYREF
  PSRWLOCK v36; // [rsp+80h] [rbp-88h] BYREF
  int v37; // [rsp+88h] [rbp-80h]
  PSRWLOCK v38; // [rsp+90h] [rbp-78h] BYREF
  unsigned int v39; // [rsp+98h] [rbp-70h]
  ContentIdString *v40; // [rsp+A0h] [rbp-68h] BYREF
  _BYTE v41[32]; // [rsp+A8h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+0h]

  *a3 = 0;
  v35 = 0;
  RtlGetDeviceFamilyInfoEnum(0, &v35, 0);
  if ( v35 != 5 && (unsigned int)(v35 - 11) > 1 )
    return 0;
  Microsoft::WRL::Wrappers::SRWLock::LockShared(&SRWLock, (char *)this + 40);
  if ( *((_BYTE *)this + 64) )
  {
    if ( SRWLock )
      ReleaseSRWLockShared(SRWLock);
    v38 = 0;
    v39 = 0;
    v29 = 0;
    SRWLock = 0;
    v7 = (*(__int64 (__fastcall **)(struct ILicenseRootRequestData *, unsigned int *, PSRWLOCK *))(*(_QWORD *)a2 + 40LL))(
           a2,
           &v29,
           &SRWLock);
    if ( v7 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x3A9,
        (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\proxy.cpp",
        (const char *)(unsigned int)v7,
        Format);
    v8 = v29;
    v9 = SRWLock;
    ComArray<ComInterfaceTraits<IStoredLicenseDocument>>::_free((LPVOID *)&v38);
    v38 = v9;
    v39 = v8;
    v36 = 0;
    v37 = 0;
    v29 = 0;
    SRWLock = 0;
    v10 = (*(__int64 (__fastcall **)(struct ILicenseRootRequestData *, unsigned int *, PSRWLOCK *))(*(_QWORD *)a2 + 48LL))(
            a2,
            &v29,
            &SRWLock);
    if ( v10 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x3B1,
        (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\proxy.cpp",
        (const char *)(unsigned int)v10,
        Format);
    v11 = v29;
    v12 = SRWLock;
    ComArray<ComInterfaceTraits<IStoredLicenseDocument>>::_free((LPVOID *)&v36);
    v36 = v12;
    v37 = v11;
    if ( v8 == v11 )
    {
      *(_OWORD *)v33 = 0;
      v34 = 0;
      for ( i = 0; ; ++i )
      {
        v30 = 0;
        if ( i >= v8 )
          break;
        v14 = (**(__int64 (__fastcall ***)(PVOID, GUID *, __int64 **))v9[i].Ptr)(
                v9[i].Ptr,
                &GUID_450650a1_f019_4d2e_a24a_7346b7cf9b21,
                &v30);
        if ( v14 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x3C1,
            (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\proxy.cpp",
            (const char *)(unsigned int)v14,
            Format);
        v29 = 0;
        v15 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(*v30 + 152))(v30, &v29);
        if ( v15 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x3C4,
            (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\proxy.cpp",
            (const char *)(unsigned int)v15,
            Format);
        if ( v29 == 3 )
        {
          SRWLock = 0;
          v16 = Microsoft::WRL::ComPtr<IStoredKeyDocument>::As<IStoredUserRootDocument>(&v30, &SRWLock);
          if ( v16 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x3C8,
              (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\proxy.cpp",
              (const char *)(unsigned int)v16,
              Format);
          v32 = 0;
          Ptr = (__int64 (__fastcall **)(PSRWLOCK, RTL_SRWLOCK **))SRWLock->Ptr;
          v32 = 0;
          v18 = Ptr[20](SRWLock, &v32);
          if ( v18 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x3CB,
              (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\proxy.cpp",
              (const char *)(unsigned int)v18,
              Format);
          std::basic_string<unsigned short,case_insensitive_char_traits,std::allocator<unsigned short>>::basic_string<unsigned short,case_insensitive_char_traits,std::allocator<unsigned short>>(
            v41,
            v32);
          if ( v33[1] == v34 )
          {
            std::vector<std::basic_string<unsigned short,case_insensitive_char_traits,std::allocator<unsigned short>>>::_Emplace_reallocate<std::basic_string<unsigned short,case_insensitive_char_traits,std::allocator<unsigned short>>>(
              v33,
              v33[1],
              v41);
          }
          else
          {
            std::basic_string<unsigned short,case_insensitive_char_traits,std::allocator<unsigned short>>::basic_string<unsigned short,case_insensitive_char_traits,std::allocator<unsigned short>>(
              v33[1],
              v41);
            v33[1] = (ContentIdString *)((char *)v33[1] + 32);
          }
          ContentIdString::~ContentIdString((ContentIdString *)v41);
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>((void **)&v32);
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&SRWLock);
        }
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v30);
      }
      v19 = (*(__int64 (__fastcall **)(struct ILicenseRootRequestData *, __int64 **))(*(_QWORD *)a2 + 56LL))(a2, &v30);
      if ( v19 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x3D4,
          (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\proxy.cpp",
          (const char *)(unsigned int)v19,
          Format);
      v29 = 0;
      v20 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(*v30 + 24))(v30, &v29);
      if ( v20 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x3D6,
          (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\proxy.cpp",
          (const char *)(unsigned int)v20,
          Format);
      v21 = v29;
      if ( v29 >= (unsigned __int64)((v33[1] - v33[0]) >> 5) )
      {
        for ( j = 0; j < v21; ++j )
        {
          v32 = 0;
          v24 = *v30;
          v32 = 0;
          v25 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, RTL_SRWLOCK **))(v24 + 32))(v30, j, &v32);
          if ( v25 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x3E2,
              (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\proxy.cpp",
              (const char *)(unsigned int)v25,
              Format);
          SRWLock = v32;
          std::find<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<std::basic_string<unsigned short,case_insensitive_char_traits,std::allocator<unsigned short>>>>>,unsigned short *>(
            &v40,
            v33[0],
            v33[1],
            &SRWLock);
          if ( v40 == v33[1] )
          {
            LogMessage(
              3u,
              "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\proxy.cpp",
              0x3E7u,
              "LicenseProxyService::AreAllRootLicensesLeased",
              (wchar_t *)L"AreAllRootLicensesLeased returning false becuse user %s is missing its root",
              v32);
            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>((void **)&v32);
            v26 = v30;
            if ( v30 )
            {
              v30 = 0;
              (*(void (__fastcall **)(__int64 *))(*v26 + 16))(v26);
            }
            if ( v33[0] )
            {
              std::_Destroy_range<std::allocator<std::wstring>>(v33[0]);
              std::_Deallocate<16>(v33[0], (v34 - v33[0]) & 0xFFFFFFFFFFFFFFE0uLL);
              *(_OWORD *)v33 = 0;
              v34 = 0;
            }
            goto LABEL_57;
          }
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>((void **)&v32);
          v21 = v29;
        }
        v27 = v30;
        if ( v30 )
        {
          v30 = 0;
          (*(void (__fastcall **)(__int64 *))(*v27 + 16))(v27);
        }
        *a3 = 1;
        if ( v33[0] )
        {
          std::_Destroy_range<std::allocator<std::wstring>>(v33[0]);
          std::_Deallocate<16>(v33[0], (v34 - v33[0]) & 0xFFFFFFFFFFFFFFE0uLL);
          *(_OWORD *)v33 = 0;
          v34 = 0;
        }
      }
      else
      {
        LogMessage(
          3u,
          "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\proxy.cpp",
          0x3DBu,
          "LicenseProxyService::AreAllRootLicensesLeased",
          (wchar_t *)L"AreAllRootLicensesLeased returning false because there are %d user roots but only %d users",
          (v33[1] - v33[0]) >> 5,
          v29);
        v22 = v30;
        if ( v30 )
        {
          v30 = 0;
          (*(void (__fastcall **)(__int64 *))(*v22 + 16))(v22);
        }
        if ( v33[0] )
        {
          std::_Destroy_range<std::allocator<std::wstring>>(v33[0]);
          std::_Deallocate<16>(v33[0], (v34 - v33[0]) & 0xFFFFFFFFFFFFFFE0uLL);
          *(_OWORD *)v33 = 0;
          v34 = 0;
        }
      }
LABEL_57:
      ComArray<ComInterfaceTraits<IStoredLicenseDocument>>::_free((LPVOID *)&v36);
      ComArray<ComInterfaceTraits<IStoredLicenseDocument>>::_free((LPVOID *)&v38);
      return 0;
    }
    else
    {
      LogMessage(
        3u,
        "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\proxy.cpp",
        0x3B8u,
        "LicenseProxyService::AreAllRootLicensesLeased",
        (wchar_t *)L"AreAllRootLicensesLeased returning false because key count of %d does not mach lease count of %d",
        v8,
        v11);
      ComArray<ComInterfaceTraits<IStoredLicenseDocument>>::_free((LPVOID *)&v36);
      ComArray<ComInterfaceTraits<IStoredLicenseDocument>>::_free((LPVOID *)&v38);
      return 0;
    }
  }
  else
  {
    LogMessage(
      3u,
      "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\proxy.cpp",
      0x39Eu,
      "LicenseProxyService::AreAllRootLicensesLeased",
      (wchar_t *)L"AreAllRootLicensesLeased returning false because subscription root keys may be missing");
    if ( SRWLock )
      ReleaseSRWLockShared(SRWLock);
    return 0;
  }
}

```

## disassembly

```asm
0x180028be0  push    rbx
0x180028be2  push    rsi
0x180028be3  push    rdi
0x180028be4  push    r12
0x180028be6  push    r13
0x180028be8  push    r14
0x180028bea  push    r15
0x180028bec  sub     rsp, 0D0h
0x180028bf3  mov     rax, cs:__security_cookie
0x180028bfa  xor     rax, rsp
0x180028bfd  mov     [rsp+108h+var_40], rax
0x180028c05  mov     r12, r8
0x180028c08  mov     rsi, rdx
0x180028c0b  mov     rbx, rcx
0x180028c0e  xor     r13d, r13d
0x180028c11  mov     [r8], r13d
0x180028c14  mov     [rsp+108h+var_90], r13d
0x180028c19  xor     r8d, r8d
0x180028c1c  lea     rdx, [rsp+108h+var_90]
0x180028c21  xor     ecx, ecx
0x180028c23  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x180028c29  mov     eax, [rsp+108h+var_90]
0x180028c2d  cmp     eax, 5
0x180028c30  jz      short loc_180028C41
0x180028c32  add     eax, 0FFFFFFF5h
0x180028c35  cmp     eax, 1
0x180028c38  jbe     short loc_180028C41
0x180028c3a  xor     eax, eax
0x180028c3c  jmp     loc_180029294
0x180028c41  lea     rdx, [rbx+28h]
0x180028c45  lea     rcx, [rsp+108h+SRWLock]
0x180028c4a  call    ?LockShared@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockShared@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockShared(_RTL_SRWLOCK *)
0x180028c4f  nop
0x180028c50  cmp     [rbx+40h], r13b
0x180028c54  jnz     short loc_180028C98
0x180028c56  lea     rax, aAreallrootlice_1; "AreAllRootLicensesLeased returning fals"...
0x180028c5d  mov     [rsp+108h+Format], rax; Format
0x180028c62  lea     r9, aLicenseproxyse_13; "LicenseProxyService::AreAllRootLicenses"...
0x180028c69  mov     r8d, 39Eh; unsigned int
0x180028c6f  lea     rdx, aOnecoreuapEndu_20; "onecoreuap\\enduser\\winstore\\licensem"...
0x180028c76  mov     ecx, 3; unsigned int
0x180028c7b  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x180028c80  nop
0x180028c81  mov     rcx, [rsp+108h+SRWLock]; SRWLock
0x180028c86  test    rcx, rcx
0x180028c89  jz      short loc_180028C91
0x180028c8b  call    cs:__imp_ReleaseSRWLockShared
0x180028c91  xor     eax, eax
0x180028c93  jmp     loc_180029294
0x180028c98  mov     rcx, [rsp+108h+SRWLock]; SRWLock
0x180028c9d  test    rcx, rcx
0x180028ca0  jz      short loc_180028CA8
0x180028ca2  call    cs:__imp_ReleaseSRWLockShared
0x180028ca8  mov     [rsp+108h+var_78], r13
0x180028cb0  mov     [rsp+108h+var_70], r13d
0x180028cb8  mov     [rsp+108h+var_C8], r13d
0x180028cbd  mov     [rsp+108h+SRWLock], r13
0x180028cc2  mov     rax, [rsi]
0x180028cc5  lea     r8, [rsp+108h+SRWLock]
0x180028cca  lea     rdx, [rsp+108h+var_C8]
0x180028ccf  mov     rcx, rsi
0x180028cd2  mov     rax, [rax+28h]
0x180028cd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028cdb  mov     rcx, [rsp+108h]; this
0x180028ce3  test    eax, eax
0x180028ce5  jns     short loc_180028CFB
0x180028ce7  mov     r9d, eax; char *
0x180028cea  lea     r8, aOnecoreuapEndu_20; "onecoreuap\\enduser\\winstore\\licensem"...
0x180028cf1  mov     edx, 3A9h; void *
0x180028cf6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180028cfb  mov     edi, [rsp+108h+var_C8]
0x180028cff  mov     r15, [rsp+108h+SRWLock]
0x180028d04  lea     rcx, [rsp+108h+var_78]
0x180028d0c  call    ?_free@?$ComArray@U?$ComInterfaceTraits@UIStoredLicenseDocument@@@@@@AEAAXXZ; ComArray<ComInterfaceTraits<IStoredLicenseDocument>>::_free(void)
0x180028d11  mov     [rsp+108h+var_78], r15
0x180028d19  mov     [rsp+108h+var_70], edi
0x180028d20  mov     [rsp+108h+var_88], r13
0x180028d28  mov     [rsp+108h+var_80], r13d
0x180028d30  mov     [rsp+108h+var_C8], r13d
0x180028d35  mov     [rsp+108h+SRWLock], r13
0x180028d3a  mov     rax, [rsi]
0x180028d3d  lea     r8, [rsp+108h+SRWLock]
0x180028d42  lea     rdx, [rsp+108h+var_C8]
0x180028d47  mov     rcx, rsi
0x180028d4a  mov     rax, [rax+30h]
0x180028d4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028d53  mov     rcx, [rsp+108h]; this
0x180028d5b  test    eax, eax
0x180028d5d  jns     short loc_180028D73
0x180028d5f  mov     r9d, eax; char *
0x180028d62  lea     r8, aOnecoreuapEndu_20; "onecoreuap\\enduser\\winstore\\licensem"...
0x180028d69  mov     edx, 3B1h; void *
0x180028d6e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180028d73  mov     ebx, [rsp+108h+var_C8]
0x180028d77  mov     r14, [rsp+108h+SRWLock]
0x180028d7c  lea     rcx, [rsp+108h+var_88]
0x180028d84  call    ?_free@?$ComArray@U?$ComInterfaceTraits@UIStoredLicenseDocument@@@@@@AEAAXXZ; ComArray<ComInterfaceTraits<IStoredLicenseDocument>>::_free(void)
0x180028d89  mov     [rsp+108h+var_88], r14
0x180028d91  mov     [rsp+108h+var_80], ebx
0x180028d98  cmp     edi, ebx
0x180028d9a  jz      short loc_180028DF2
0x180028d9c  mov     [rsp+108h+var_D8], ebx
0x180028da0  mov     dword ptr [rsp+108h+var_E0], edi
0x180028da4  lea     rax, aAreallrootlice_0; "AreAllRootLicensesLeased returning fals"...
0x180028dab  mov     [rsp+108h+Format], rax; Format
0x180028db0  lea     r9, aLicenseproxyse_13; "LicenseProxyService::AreAllRootLicenses"...
0x180028db7  mov     r8d, 3B8h; unsigned int
0x180028dbd  lea     rdx, aOnecoreuapEndu_20; "onecoreuap\\enduser\\winstore\\licensem"...
0x180028dc4  mov     ecx, 3; unsigned int
0x180028dc9  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x180028dce  nop
0x180028dcf  lea     rcx, [rsp+108h+var_88]
0x180028dd7  call    ?_free@?$ComArray@U?$ComInterfaceTraits@UIStoredLicenseDocument@@@@@@AEAAXXZ; ComArray<ComInterfaceTraits<IStoredLicenseDocument>>::_free(void)
0x180028ddc  nop
0x180028ddd  lea     rcx, [rsp+108h+var_78]
0x180028de5  call    ?_free@?$ComArray@U?$ComInterfaceTraits@UIStoredLicenseDocument@@@@@@AEAAXXZ; ComArray<ComInterfaceTraits<IStoredLicenseDocument>>::_free(void)
0x180028dea  nop
0x180028deb  xor     eax, eax
0x180028ded  jmp     loc_180029294
0x180028df2  xorps   xmm0, xmm0
0x180028df5  movdqu  xmmword ptr [rsp+108h+var_A8], xmm0
0x180028dfb  mov     [rsp+108h+var_98], r13
0x180028e00  mov     ebx, r13d
0x180028e03  mov     [rsp+108h+var_C0], r13
0x180028e08  cmp     ebx, edi
0x180028e0a  jnb     loc_180028F8F
0x180028e10  mov     eax, ebx
0x180028e12  mov     rcx, [r15+rax*8]
0x180028e16  mov     rax, [rcx]
0x180028e19  lea     r8, [rsp+108h+var_C0]
0x180028e1e  lea     rdx, _GUID_450650a1_f019_4d2e_a24a_7346b7cf9b21
0x180028e25  mov     rax, [rax]
0x180028e28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028e2d  mov     rcx, [rsp+108h]; this
0x180028e35  test    eax, eax
0x180028e37  jns     short loc_180028E4D
0x180028e39  mov     r9d, eax; char *
0x180028e3c  lea     r8, aOnecoreuapEndu_20; "onecoreuap\\enduser\\winstore\\licensem"...
0x180028e43  mov     edx, 3C1h; void *
0x180028e48  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180028e4d  mov     [rsp+108h+var_C8], r13d
0x180028e52  mov     rcx, [rsp+108h+var_C0]
0x180028e57  mov     rax, [rcx]
0x180028e5a  lea     rdx, [rsp+108h+var_C8]
0x180028e5f  mov     rax, [rax+98h]
0x180028e66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028e6b  mov     rcx, [rsp+108h]; this
0x180028e73  test    eax, eax
0x180028e75  jns     short loc_180028E8B
0x180028e77  mov     r9d, eax; char *
0x180028e7a  lea     r8, aOnecoreuapEndu_20; "onecoreuap\\enduser\\winstore\\licensem"...
0x180028e81  mov     edx, 3C4h; void *
0x180028e86  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180028e8b  cmp     [rsp+108h+var_C8], 3
0x180028e90  jnz     loc_180028F7E
0x180028e96  mov     [rsp+108h+SRWLock], r13
0x180028e9b  lea     rdx, [rsp+108h+SRWLock]
0x180028ea0  lea     rcx, [rsp+108h+var_C0]
0x180028ea5  call    ??$As@UIStoredUserRootDocument@@@?$ComPtr@UIStoredKeyDocument@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIStoredUserRootDocument@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IStoredKeyDocument>::As<IStoredUserRootDocument>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IStoredUserRootDocument>>)
0x180028eaa  mov     rcx, [rsp+108h]; this
0x180028eb2  test    eax, eax
0x180028eb4  jns     short loc_180028ECA
0x180028eb6  mov     r9d, eax; char *
0x180028eb9  lea     r8, aOnecoreuapEndu_20; "onecoreuap\\enduser\\winstore\\licensem"...
0x180028ec0  mov     edx, 3C8h; void *
0x180028ec5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180028eca  mov     [rsp+108h+var_B0], r13
0x180028ecf  mov     rcx, [rsp+108h+SRWLock]
0x180028ed4  mov     rax, [rcx]
0x180028ed7  mov     [rsp+108h+var_B0], r13
0x180028edc  lea     rdx, [rsp+108h+var_B0]
0x180028ee1  mov     rax, [rax+0A0h]
0x180028ee8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028eed  mov     rcx, [rsp+108h]; this
0x180028ef5  test    eax, eax
0x180028ef7  jns     short loc_180028F0D
0x180028ef9  mov     r9d, eax; char *
0x180028efc  lea     r8, aOnecoreuapEndu_20; "onecoreuap\\enduser\\winstore\\licensem"...
0x180028f03  mov     edx, 3CBh; void *
0x180028f08  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180028f0d  mov     rdx, [rsp+108h+var_B0]
0x180028f12  lea     rcx, [rsp+108h+var_60]
0x180028f1a  call    ??0?$basic_string@GUcase_insensitive_char_traits@@V?$allocator@G@std@@@std@@QEAA@QEBG@Z; std::basic_string<ushort,case_insensitive_char_traits,std::allocator<ushort>>::basic_string<ushort,case_insensitive_char_traits,std::allocator<ushort>>(ushort const * const)
0x180028f1f  nop
0x180028f20  mov     rax, [rsp+108h+var_A8+8]
0x180028f25  cmp     rax, [rsp+108h+var_98]
0x180028f2a  jz      short loc_180028F44
0x180028f2c  lea     rdx, [rsp+108h+var_60]
0x180028f34  mov     rcx, rax
0x180028f37  call    ??0?$basic_string@GUcase_insensitive_char_traits@@V?$allocator@G@std@@@std@@QEAA@$$QEAV01@@Z; std::basic_string<ushort,case_insensitive_char_traits,std::allocator<ushort>>::basic_string<ushort,case_insensitive_char_traits,std::allocator<ushort>>(std::basic_string<ushort,case_insensitive_char_traits,std::allocator<ushort>> &&)
0x180028f3c  add     [rsp+108h+var_A8+8], 20h ; ' '
0x180028f42  jmp     short loc_180028F5A
0x180028f44  lea     r8, [rsp+108h+var_60]
0x180028f4c  mov     rdx, rax
0x180028f4f  lea     rcx, [rsp+108h+var_A8]
0x180028f54  call    ??$_Emplace_reallocate@V?$basic_string@GUcase_insensitive_char_traits@@V?$allocator@G@std@@@std@@@?$vector@V?$basic_string@GUcase_insensitive_char_traits@@V?$allocator@G@std@@@std@@V?$allocator@V?$basic_string@GUcase_insensitive_char_traits@@V?$allocator@G@std@@@std@@@2@@std@@AEAAPEAV?$basic_string@GUcase_insensitive_char_traits@@V?$allocator@G@std@@@1@QEAV21@$$QEAV21@@Z; std::vector<std::basic_string<ushort,case_insensitive_char_traits,std::allocator<ushort>>>::_Emplace_reallocate<std::basic_string<ushort,case_insensitive_char_traits,std::allocator<ushort>>>(std::basic_string<ushort,case_insensitive_char_traits,std::allocator<ushort>> * const,std::basic_string<ushort,case_insensitive_char_traits,std::allocator<ushort>> &&)
0x180028f59  nop
0x180028f5a  lea     rcx, [rsp+108h+var_60]; this
0x180028f62  call    ??1ContentIdString@@QEAA@XZ; ContentIdString::~ContentIdString(void)
0x180028f67  nop
0x180028f68  lea     rcx, [rsp+108h+var_B0]
0x180028f6d  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180028f72  nop
0x180028f73  lea     rcx, [rsp+108h+SRWLock]
0x180028f78  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180028f7d  nop
0x180028f7e  lea     rcx, [rsp+108h+var_C0]
0x180028f83  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180028f88  inc     ebx
0x180028f8a  jmp     loc_180028E03
0x180028f8f  mov     rax, [rsi]
0x180028f92  lea     rdx, [rsp+108h+var_C0]
0x180028f97  mov     rcx, rsi
0x180028f9a  mov     rax, [rax+38h]
0x180028f9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028fa3  mov     rcx, [rsp+108h]; this
0x180028fab  test    eax, eax
0x180028fad  jns     short loc_180028FC3
0x180028faf  mov     r9d, eax; char *
0x180028fb2  lea     r8, aOnecoreuapEndu_20; "onecoreuap\\enduser\\winstore\\licensem"...
0x180028fb9  mov     edx, 3D4h; void *
0x180028fbe  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180028fc3  mov     [rsp+108h+var_C8], r13d
0x180028fc8  mov     rcx, [rsp+108h+var_C0]
0x180028fcd  mov     rax, [rcx]
0x180028fd0  lea     rdx, [rsp+108h+var_C8]
0x180028fd5  mov     rax, [rax+18h]
0x180028fd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028fde  mov     rcx, [rsp+108h]; this
0x180028fe6  test    eax, eax
0x180028fe8  jns     short loc_180028FFE
0x180028fea  mov     r9d, eax; char *
0x180028fed  lea     r8, aOnecoreuapEndu_20; "onecoreuap\\enduser\\winstore\\licensem"...
0x180028ff4  mov     edx, 3D6h; void *
0x180028ff9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180028ffe  mov     rcx, [rsp+108h+var_A8+8]
0x180029003  sub     rcx, [rsp+108h+var_A8]
0x180029008  sar     rcx, 5
0x18002900c  mov     edx, [rsp+108h+var_C8]
0x180029010  cmp     rdx, rcx
0x180029013  jnb     loc_1800290C4
0x180029019  mov     [rsp+108h+var_D8], edx
0x18002901d  mov     [rsp+108h+var_E0], rcx
0x180029022  lea     rax, aAreallrootlice_2; "AreAllRootLicensesLeased returning fals"...
0x180029029  mov     [rsp+108h+Format], rax; Format
0x18002902e  lea     r9, aLicenseproxyse_13; "LicenseProxyService::AreAllRootLicenses"...
0x180029035  mov     r8d, 3DBh; unsigned int
0x18002903b  lea     rdx, aOnecoreuapEndu_20; "onecoreuap\\enduser\\winstore\\licensem"...
0x180029042  mov     ecx, 3; unsigned int
0x180029047  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x18002904c  nop
0x18002904d  mov     rcx, [rsp+108h+var_C0]
0x180029052  test    rcx, rcx
0x180029055  jz      short loc_180029069
0x180029057  mov     [rsp+108h+var_C0], r13
0x18002905c  mov     rax, [rcx]
0x18002905f  mov     rax, [rax+10h]
0x180029063  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029068  nop
0x180029069  mov     rcx, [rsp+108h+var_A8]; this
0x18002906e  test    rcx, rcx
0x180029071  jz      short loc_1800290A1
0x180029073  mov     rdx, [rsp+108h+var_A8+8]
0x180029078  call    ??$_Destroy_range@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEAV10@AEAV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::wstring>>(std::wstring *,std::wstring * const,std::allocator<std::wstring> &)
0x18002907d  mov     rcx, [rsp+108h+var_A8]
0x180029082  mov     rdx, [rsp+108h+var_98]
0x180029087  sub     rdx, rcx
0x18002908a  and     rdx, 0FFFFFFFFFFFFFFE0h
0x18002908e  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180029093  xorps   xmm0, xmm0
0x180029096  movdqu  xmmword ptr [rsp+108h+var_A8], xmm0
0x18002909c  mov     [rsp+108h+var_98], r13
0x1800290a1  lea     rcx, [rsp+108h+var_88]
0x1800290a9  call    ?_free@?$ComArray@U?$ComInterfaceTraits@UIStoredLicenseDocument@@@@@@AEAAXXZ; ComArray<ComInterfaceTraits<IStoredLicenseDocument>>::_free(void)
0x1800290ae  nop
0x1800290af  lea     rcx, [rsp+108h+var_78]
0x1800290b7  call    ?_free@?$ComArray@U?$ComInterfaceTraits@UIStoredLicenseDocument@@@@@@AEAAXXZ; ComArray<ComInterfaceTraits<IStoredLicenseDocument>>::_free(void)
0x1800290bc  nop
0x1800290bd  xor     eax, eax
0x1800290bf  jmp     loc_180029294
0x1800290c4  mov     ebx, r13d
0x1800290c7  cmp     ebx, edx
0x1800290c9  jnb     loc_180029216
0x1800290cf  mov     [rsp+108h+var_B0], r13
0x1800290d4  mov     rcx, [rsp+108h+var_C0]
0x1800290d9  mov     rax, [rcx]
0x1800290dc  mov     [rsp+108h+var_B0], r13
0x1800290e1  lea     r8, [rsp+108h+var_B0]
0x1800290e6  mov     edx, ebx
0x1800290e8  mov     rax, [rax+20h]
0x1800290ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800290f1  mov     rcx, [rsp+108h]; this
0x1800290f9  test    eax, eax
0x1800290fb  jns     short loc_180029111
0x1800290fd  mov     r9d, eax; char *
0x180029100  lea     r8, aOnecoreuapEndu_20; "onecoreuap\\enduser\\winstore\\licensem"...
0x180029107  mov     edx, 3E2h; void *
0x18002910c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180029111  mov     rax, [rsp+108h+var_B0]
0x180029116  mov     [rsp+108h+SRWLock], rax
  ... truncated ...
```
