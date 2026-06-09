# Windows::Management::MdmSessionManagerStatics::get_SessionIds(Windows::Foundation::Collections::IVectorView<HSTRING__ *> * *)

- ea: `0x18009a360`
- end: `0x18009a740`
- name: `?get_SessionIds@MdmSessionManagerStatics@Management@Windows@@UEAAJPEAPEAU?$IVectorView@PEAUHSTRING__@@@Collections@Foundation@3@@Z`
- size: `992`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180009be4`
- `0x18000a5c4`
- `0x1800179f8`
- `0x1800340e4`
- `0x18006ef5c`
- `0x180097acc`
- `0x1800988a8`
- `0x180098a80`
- `0x180098ec0`
- `0x180099684`
- `0x18009a360`
- `0x1800bb010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009a4c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009a4f0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009a560`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009a5d2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009a4c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009a4f0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009a560`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009a5d2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009a52c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009a59c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009a60a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009a621`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009a6a5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009a6fa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009a711`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009a52c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009a59c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009a60a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009a621`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009a6a5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009a6fa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009a711`
- `omadmapi!__imp_OmaDmEnumerateInitiationInfo` at `0x18009a40b`
- `omadmapi!__imp_OmaDmEnumerateInitiationInfo` at `0x18009a40b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Management::MdmSessionManagerStatics::get_SessionIds(__int64 a1, _QWORD *a2)
{
  unsigned int v3; // ebx
  int EnterpriseAccountId; // ebx
  __int64 v6; // rcx
  unsigned int v7; // esi
  __int64 v8; // rdi
  wchar_t *v9; // rax
  unsigned __int64 v10; // r8
  int v11; // eax
  int v12; // eax
  unsigned int k; // edi
  unsigned int j; // edi
  unsigned int i; // edi
  __int64 (__fastcall *v16)(__int64, __int64 *); // rbx
  int v17; // eax
  unsigned int m; // edi
  __int64 v19; // rax
  unsigned int n; // ebx
  HSTRING string; // [rsp+20h] [rbp-30h] BYREF
  __int64 v22; // [rsp+28h] [rbp-28h] BYREF
  __int64 v23; // [rsp+30h] [rbp-20h] BYREF
  __int64 *v24; // [rsp+38h] [rbp-18h] BYREF
  unsigned __int16 *v25; // [rsp+40h] [rbp-10h] BYREF
  char v26; // [rsp+48h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  unsigned int v28; // [rsp+88h] [rbp+38h] BYREF
  __int64 SubStr; // [rsp+90h] [rbp+40h] BYREF
  HLOCAL hMem; // [rsp+98h] [rbp+48h] BYREF

  if ( a2 )
  {
    *a2 = 0;
    v23 = 0;
    v24 = &v23;
    v25 = 0;
    v26 = 1;
    EnterpriseAccountId = Windows::Management::MdmSessionManagerStatics::GetEnterpriseAccountId(&v25);
    LODWORD(SubStr) = EnterpriseAccountId;
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v24);
    if ( EnterpriseAccountId < 0 )
    {
      MdmSyncTraceProvider::GetAccountFailed<long &,char const (&)[15]>(&SubStr, "get_SessionIds");
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v23);
      return 0;
    }
    v28 = 0;
    hMem = 0;
    LODWORD(SubStr) = OmaDmEnumerateInitiationInfo(v23, 1, &hMem, &v28);
    if ( (int)SubStr >= 0 )
    {
      SubStr = 0;
      Windows::Foundation::Collections::Internal::detail::CreateExternalVector<HSTRING__ *,Windows::Foundation::Collections::Internal::AgileVector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>>(
        v6,
        &SubStr);
      v7 = 0;
      v8 = SubStr;
      while ( v7 < v28 )
      {
        wcscpy((wchar_t *)&SubStr, L"{");
        v9 = wcsstr(*((const wchar_t **)hMem + v7), (const wchar_t *)&SubStr);
        if ( v9 )
        {
          v10 = -1;
          do
            ++v10;
          while ( v9[v10] );
          string = 0;
          if ( v10 > 0x7FFFFFFF )
          {
            v3 = -2147024362;
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xFB,
              (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\winrt\\lib\\mdmsync\\mdmsessionmanager.cpp",
              (const char *)0x80070216LL,
              (int)string);
            WindowsDeleteString(string);
            string = 0;
            if ( v8 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
            for ( i = 0; i < v28; ++i )
              LocalFree(*((HLOCAL *)hMem + i));
            goto LABEL_31;
          }
          v11 = Microsoft::WRL::Wrappers::HString::Set((Microsoft::WRL::Wrappers::HString *)&string, v9, v10);
          v3 = v11;
          if ( v11 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xFD,
              (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\winrt\\lib\\mdmsync\\mdmsessionmanager.cpp",
              (const char *)(unsigned int)v11,
              (int)string);
            WindowsDeleteString(string);
            string = 0;
            if ( v8 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
            for ( j = 0; j < v28; ++j )
              LocalFree(*((HLOCAL *)hMem + j));
            goto LABEL_31;
          }
          v12 = (*(__int64 (__fastcall **)(__int64, HSTRING))(*(_QWORD *)v8 + 104LL))(v8, string);
          v3 = v12;
          if ( v12 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xFE,
              (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\winrt\\lib\\mdmsync\\mdmsessionmanager.cpp",
              (const char *)(unsigned int)v12,
              (int)string);
            WindowsDeleteString(string);
            string = 0;
            if ( v8 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
            for ( k = 0; k < v28; ++k )
              LocalFree(*((HLOCAL *)hMem + k));
LABEL_31:
            LocalFree(hMem);
            goto LABEL_44;
          }
          WindowsDeleteString(string);
        }
        ++v7;
      }
      v22 = 0;
      v16 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v8 + 64LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v22);
      v17 = v16(v8, &v22);
      v3 = v17;
      if ( v17 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x103,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\winrt\\lib\\mdmsync\\mdmsessionmanager.cpp",
          (const char *)(unsigned int)v17,
          (int)string);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v22);
        if ( v8 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
        for ( m = 0; m < v28; ++m )
          LocalFree(*((HLOCAL *)hMem + m));
        goto LABEL_31;
      }
      v19 = v22;
      v22 = 0;
      *a2 = v19;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v22);
      if ( v8 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
      for ( n = 0; n < v28; ++n )
        LocalFree(*((HLOCAL *)hMem + n));
      LocalFree(hMem);
    }
    else
    {
      MdmSyncTraceProvider::SessionEnumFailed<long &,char const (&)[15]>(&SubStr, "get_SessionIds");
    }
    v3 = 0;
LABEL_44:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v23);
  }
  else
  {
    v3 = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC4,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\winrt\\lib\\mdmsync\\mdmsessionmanager.cpp",
      (const char *)0x80004003LL,
      (int)string);
  }
  return v3;
}

```

## disassembly

```asm
0x18009a360  mov     [rsp-28h+arg_0], rbx
0x18009a365  push    rbp
0x18009a366  push    rsi
0x18009a367  push    rdi
0x18009a368  push    r14
0x18009a36a  push    r15
0x18009a36c  mov     rbp, rsp
0x18009a36f  sub     rsp, 50h
0x18009a373  mov     r14, rdx
0x18009a376  xor     r15d, r15d
0x18009a379  test    rdx, rdx
0x18009a37c  jnz     short loc_18009A3A0
0x18009a37e  mov     rcx, [rbp+28h]; this
0x18009a382  mov     ebx, 80004003h
0x18009a387  mov     r9d, ebx; char *
0x18009a38a  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\enterprisemgmt\\winr"...
0x18009a391  mov     edx, 0C4h; void *
0x18009a396  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009a39b  jmp     loc_18009A729
0x18009a3a0  mov     [rdx], r15
0x18009a3a3  mov     [rbp+var_20], r15
0x18009a3a7  lea     rax, [rbp+var_20]
0x18009a3ab  mov     [rbp+var_18], rax
0x18009a3af  mov     [rbp+var_10], r15
0x18009a3b3  mov     [rbp+var_8], 1
0x18009a3b7  lea     rcx, [rbp+var_10]; unsigned __int16 **
0x18009a3bb  call    ?GetEnterpriseAccountId@MdmSessionManagerStatics@Management@Windows@@SAJPEAPEAG@Z; Windows::Management::MdmSessionManagerStatics::GetEnterpriseAccountId(ushort * *)
0x18009a3c0  mov     ebx, eax
0x18009a3c2  mov     dword ptr [rbp+SubStr], eax
0x18009a3c5  lea     rcx, [rbp+var_18]
0x18009a3c9  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x18009a3ce  test    ebx, ebx
0x18009a3d0  jns     short loc_18009A3F2
0x18009a3d2  lea     rdx, aGetSessionids; "get_SessionIds"
0x18009a3d9  lea     rcx, [rbp+SubStr]
0x18009a3dd  call    ??$GetAccountFailed@AEAJAEAY0P@$$CBD@MdmSyncTraceProvider@@SAXAEAJAEAY0P@$$CBD@Z; MdmSyncTraceProvider::GetAccountFailed<long &,char const (&)[15]>(long &,char const (&)[15])
0x18009a3e2  lea     rcx, [rbp+var_20]
0x18009a3e6  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18009a3eb  xor     eax, eax
0x18009a3ed  jmp     loc_18009A72B
0x18009a3f2  mov     [rbp+arg_8], r15d
0x18009a3f6  mov     [rbp+hMem], r15
0x18009a3fa  lea     r9, [rbp+arg_8]
0x18009a3fe  lea     r8, [rbp+hMem]
0x18009a402  mov     edx, 1
0x18009a407  mov     rcx, [rbp+var_20]
0x18009a40b  call    cs:__imp_OmaDmEnumerateInitiationInfo
0x18009a412  nop     dword ptr [rax+rax+00h]
0x18009a417  mov     dword ptr [rbp+SubStr], eax
0x18009a41a  test    eax, eax
0x18009a41c  jns     short loc_18009A433
0x18009a41e  lea     rdx, aGetSessionids; "get_SessionIds"
0x18009a425  lea     rcx, [rbp+SubStr]
0x18009a429  call    ??$SessionEnumFailed@AEAJAEAY0P@$$CBD@MdmSyncTraceProvider@@SAXAEAJAEAY0P@$$CBD@Z; MdmSyncTraceProvider::SessionEnumFailed<long &,char const (&)[15]>(long &,char const (&)[15])
0x18009a42e  jmp     loc_18009A71D
0x18009a433  mov     [rbp+SubStr], r15
0x18009a437  lea     rdx, [rbp+SubStr]
0x18009a43b  call    ??$CreateExternalVector@PEAUHSTRING__@@V?$AgileVector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@$0A@@Internal@Collections@Foundation@Windows@@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEAPEAU?$IVector@PEAUHSTRING__@@@234@@ZPEAPEAV?$AgileVector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@$0A@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalVector<HSTRING__ *,Windows::Foundation::Collections::Internal::AgileVector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::IVector<HSTRING__ *> * *),Windows::Foundation::Collections::Internal::AgileVector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0> * *)
0x18009a440  mov     esi, r15d
0x18009a443  mov     rdi, [rbp+SubStr]
0x18009a447  cmp     esi, [rbp+arg_8]
0x18009a44a  jnb     loc_18009A632
0x18009a450  mov     dword ptr [rbp+SubStr], 7Bh ; '{'
0x18009a457  mov     eax, esi
0x18009a459  lea     rdx, [rbp+SubStr]; SubStr
0x18009a45d  mov     rcx, [rbp+hMem]
0x18009a461  mov     rcx, [rcx+rax*8]; Str
0x18009a465  call    ?wcsstr@@YAPEAGPEAGPEBG@Z; wcsstr(ushort *,ushort const *)
0x18009a46a  test    rax, rax
0x18009a46d  jz      short loc_18009A4CD
0x18009a46f  or      r8, 0FFFFFFFFFFFFFFFFh
0x18009a473  inc     r8; unsigned int
0x18009a476  cmp     [rax+r8*2], r15w
0x18009a47b  jnz     short loc_18009A473
0x18009a47d  mov     [rbp+string], r15
0x18009a481  cmp     r8, 7FFFFFFFh
0x18009a488  ja      loc_18009A5B1
0x18009a48e  mov     rdx, rax; unsigned __int16 *
0x18009a491  lea     rcx, [rbp+string]; this
0x18009a495  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x18009a49a  mov     ebx, eax
0x18009a49c  test    eax, eax
0x18009a49e  js      loc_18009A544
0x18009a4a4  mov     rax, [rdi]
0x18009a4a7  mov     rdx, [rbp+string]
0x18009a4ab  mov     rcx, rdi
0x18009a4ae  mov     rax, [rax+68h]
0x18009a4b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a4b7  mov     ebx, eax
0x18009a4b9  test    eax, eax
0x18009a4bb  js      short loc_18009A4D4
0x18009a4bd  mov     rcx, [rbp+string]; string
0x18009a4c1  call    cs:__imp_WindowsDeleteString
0x18009a4c8  nop     dword ptr [rax+rax+00h]
0x18009a4cd  inc     esi
0x18009a4cf  jmp     loc_18009A447
0x18009a4d4  mov     rcx, [rbp+28h]; this
0x18009a4d8  mov     r9d, eax; char *
0x18009a4db  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\enterprisemgmt\\winr"...
0x18009a4e2  mov     edx, 0FEh; void *
0x18009a4e7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009a4ec  mov     rcx, [rbp+string]; string
0x18009a4f0  call    cs:__imp_WindowsDeleteString
0x18009a4f7  nop     dword ptr [rax+rax+00h]
0x18009a4fc  mov     [rbp+string], r15
0x18009a500  test    rdi, rdi
0x18009a503  jz      short loc_18009A515
0x18009a505  mov     rax, [rdi]
0x18009a508  mov     rcx, rdi
0x18009a50b  mov     rax, [rax+10h]
0x18009a50f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a514  nop
0x18009a515  mov     edi, r15d
0x18009a518  cmp     [rbp+arg_8], r15d
0x18009a51c  jbe     loc_18009A61D
0x18009a522  mov     eax, edi
0x18009a524  mov     rcx, [rbp+hMem]
0x18009a528  mov     rcx, [rcx+rax*8]; hMem
0x18009a52c  call    cs:__imp_LocalFree
0x18009a533  nop     dword ptr [rax+rax+00h]
0x18009a538  inc     edi
0x18009a53a  cmp     edi, [rbp+arg_8]
0x18009a53d  jb      short loc_18009A522
0x18009a53f  jmp     loc_18009A61D
0x18009a544  mov     rcx, [rbp+28h]; this
0x18009a548  mov     r9d, eax; char *
0x18009a54b  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\enterprisemgmt\\winr"...
0x18009a552  mov     edx, 0FDh; void *
0x18009a557  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009a55c  mov     rcx, [rbp+string]; string
0x18009a560  call    cs:__imp_WindowsDeleteString
0x18009a567  nop     dword ptr [rax+rax+00h]
0x18009a56c  mov     [rbp+string], r15
0x18009a570  test    rdi, rdi
0x18009a573  jz      short loc_18009A585
0x18009a575  mov     rax, [rdi]
0x18009a578  mov     rcx, rdi
0x18009a57b  mov     rax, [rax+10h]
0x18009a57f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a584  nop
0x18009a585  mov     edi, r15d
0x18009a588  cmp     [rbp+arg_8], r15d
0x18009a58c  jbe     loc_18009A61D
0x18009a592  mov     eax, edi
0x18009a594  mov     rcx, [rbp+hMem]
0x18009a598  mov     rcx, [rcx+rax*8]; hMem
0x18009a59c  call    cs:__imp_LocalFree
0x18009a5a3  nop     dword ptr [rax+rax+00h]
0x18009a5a8  inc     edi
0x18009a5aa  cmp     edi, [rbp+arg_8]
0x18009a5ad  jb      short loc_18009A592
0x18009a5af  jmp     short loc_18009A61D
0x18009a5b1  mov     rcx, [rbp+28h]; this
0x18009a5b5  mov     ebx, 80070216h
0x18009a5ba  mov     r9d, ebx; char *
0x18009a5bd  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\enterprisemgmt\\winr"...
0x18009a5c4  mov     edx, 0FBh; void *
0x18009a5c9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009a5ce  mov     rcx, [rbp+string]; string
0x18009a5d2  call    cs:__imp_WindowsDeleteString
0x18009a5d9  nop     dword ptr [rax+rax+00h]
0x18009a5de  mov     [rbp+string], r15
0x18009a5e2  test    rdi, rdi
0x18009a5e5  jz      short loc_18009A5F7
0x18009a5e7  mov     rax, [rdi]
0x18009a5ea  mov     rcx, rdi
0x18009a5ed  mov     rax, [rax+10h]
0x18009a5f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a5f6  nop
0x18009a5f7  mov     edi, r15d
0x18009a5fa  cmp     [rbp+arg_8], r15d
0x18009a5fe  jbe     short loc_18009A61D
0x18009a600  mov     eax, edi
0x18009a602  mov     rcx, [rbp+hMem]
0x18009a606  mov     rcx, [rcx+rax*8]; hMem
0x18009a60a  call    cs:__imp_LocalFree
0x18009a611  nop     dword ptr [rax+rax+00h]
0x18009a616  inc     edi
0x18009a618  cmp     edi, [rbp+arg_8]
0x18009a61b  jb      short loc_18009A600
0x18009a61d  mov     rcx, [rbp+hMem]; hMem
0x18009a621  call    cs:__imp_LocalFree
0x18009a628  nop     dword ptr [rax+rax+00h]
0x18009a62d  jmp     loc_18009A720
0x18009a632  mov     [rbp+var_28], r15
0x18009a636  mov     rax, [rdi]
0x18009a639  mov     rbx, [rax+40h]
0x18009a63d  lea     rcx, [rbp+var_28]
0x18009a641  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18009a646  lea     rdx, [rbp+var_28]
0x18009a64a  mov     rcx, rdi
0x18009a64d  mov     rax, rbx
0x18009a650  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a655  mov     ebx, eax
0x18009a657  test    eax, eax
0x18009a659  jns     short loc_18009A6BD
0x18009a65b  mov     rcx, [rbp+28h]; this
0x18009a65f  mov     r9d, eax; char *
0x18009a662  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\enterprisemgmt\\winr"...
0x18009a669  mov     edx, 103h; void *
0x18009a66e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009a673  lea     rcx, [rbp+var_28]
0x18009a677  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18009a67c  nop
0x18009a67d  test    rdi, rdi
0x18009a680  jz      short loc_18009A692
0x18009a682  mov     rax, [rdi]
0x18009a685  mov     rcx, rdi
0x18009a688  mov     rax, [rax+10h]
0x18009a68c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a691  nop
0x18009a692  mov     edi, r15d
0x18009a695  cmp     [rbp+arg_8], r15d
0x18009a699  jbe     short loc_18009A61D
0x18009a69b  mov     eax, edi
0x18009a69d  mov     rcx, [rbp+hMem]
0x18009a6a1  mov     rcx, [rcx+rax*8]; hMem
0x18009a6a5  call    cs:__imp_LocalFree
0x18009a6ac  nop     dword ptr [rax+rax+00h]
0x18009a6b1  inc     edi
0x18009a6b3  cmp     edi, [rbp+arg_8]
0x18009a6b6  jb      short loc_18009A69B
0x18009a6b8  jmp     loc_18009A61D
0x18009a6bd  mov     rax, [rbp+var_28]
0x18009a6c1  mov     [rbp+var_28], r15
0x18009a6c5  mov     [r14], rax
0x18009a6c8  lea     rcx, [rbp+var_28]
0x18009a6cc  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18009a6d1  nop
0x18009a6d2  test    rdi, rdi
0x18009a6d5  jz      short loc_18009A6E7
0x18009a6d7  mov     rax, [rdi]
0x18009a6da  mov     rcx, rdi
0x18009a6dd  mov     rax, [rax+10h]
0x18009a6e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a6e6  nop
0x18009a6e7  mov     ebx, r15d
0x18009a6ea  cmp     [rbp+arg_8], r15d
0x18009a6ee  jbe     short loc_18009A70D
0x18009a6f0  mov     eax, ebx
0x18009a6f2  mov     rcx, [rbp+hMem]
0x18009a6f6  mov     rcx, [rcx+rax*8]; hMem
0x18009a6fa  call    cs:__imp_LocalFree
0x18009a701  nop     dword ptr [rax+rax+00h]
0x18009a706  inc     ebx
0x18009a708  cmp     ebx, [rbp+arg_8]
0x18009a70b  jb      short loc_18009A6F0
0x18009a70d  mov     rcx, [rbp+hMem]; hMem
0x18009a711  call    cs:__imp_LocalFree
0x18009a718  nop     dword ptr [rax+rax+00h]
0x18009a71d  mov     ebx, r15d
0x18009a720  lea     rcx, [rbp+var_20]
0x18009a724  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18009a729  mov     eax, ebx
0x18009a72b  mov     rbx, [rsp+50h+arg_0]
0x18009a733  add     rsp, 50h
0x18009a737  pop     r15
0x18009a739  pop     r14
0x18009a73b  pop     rdi
0x18009a73c  pop     rsi
0x18009a73d  pop     rbp
0x18009a73e  retn
```
