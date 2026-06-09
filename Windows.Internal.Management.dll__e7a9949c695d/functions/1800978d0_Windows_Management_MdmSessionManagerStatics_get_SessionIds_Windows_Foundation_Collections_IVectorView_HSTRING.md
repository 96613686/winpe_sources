# Windows::Management::MdmSessionManagerStatics::get_SessionIds(Windows::Foundation::Collections::IVectorView<HSTRING__ *> * *)

- ea: `0x1800978d0`
- end: `0x180097c63`
- name: `?get_SessionIds@MdmSessionManagerStatics@Management@Windows@@UEAAJPEAPEAU?$IVectorView@PEAUHSTRING__@@@Collections@Foundation@3@@Z`
- size: `915`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000992c`
- `0x18000a2a4`
- `0x180017204`
- `0x180034fcc`
- `0x18006db38`
- `0x18009519c`
- `0x180095ec8`
- `0x180096098`
- `0x1800964d0`
- `0x180096c48`
- `0x1800978d0`
- `0x1800b7010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180097a2b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180097a54`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180097ab8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180097b1a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180097a2b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180097a54`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180097ab8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180097b1a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180097a8a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180097aea`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180097b4c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180097b5d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180097bdb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180097c2a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180097c3b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180097a8a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180097aea`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180097b4c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180097b5d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180097bdb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180097c2a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180097c3b`
- `omadmapi!__imp_OmaDmEnumerateInitiationInfo` at `0x18009797b`
- `omadmapi!__imp_OmaDmEnumerateInitiationInfo` at `0x18009797b`

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
0x1800978d0  mov     [rsp-28h+arg_0], rbx
0x1800978d5  push    rbp
0x1800978d6  push    rsi
0x1800978d7  push    rdi
0x1800978d8  push    r14
0x1800978da  push    r15
0x1800978dc  mov     rbp, rsp
0x1800978df  sub     rsp, 50h
0x1800978e3  mov     r14, rdx
0x1800978e6  xor     r15d, r15d
0x1800978e9  test    rdx, rdx
0x1800978ec  jnz     short loc_180097910
0x1800978ee  mov     rcx, [rbp+28h]; this
0x1800978f2  mov     ebx, 80004003h
0x1800978f7  mov     r9d, ebx; char *
0x1800978fa  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\enterprisemgmt\\winr"...
0x180097901  mov     edx, 0C4h; void *
0x180097906  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009790b  jmp     loc_180097C4D
0x180097910  mov     [rdx], r15
0x180097913  mov     [rbp+var_20], r15
0x180097917  lea     rax, [rbp+var_20]
0x18009791b  mov     [rbp+var_18], rax
0x18009791f  mov     [rbp+var_10], r15
0x180097923  mov     [rbp+var_8], 1
0x180097927  lea     rcx, [rbp+var_10]; unsigned __int16 **
0x18009792b  call    ?GetEnterpriseAccountId@MdmSessionManagerStatics@Management@Windows@@SAJPEAPEAG@Z; Windows::Management::MdmSessionManagerStatics::GetEnterpriseAccountId(ushort * *)
0x180097930  mov     ebx, eax
0x180097932  mov     dword ptr [rbp+SubStr], eax
0x180097935  lea     rcx, [rbp+var_18]
0x180097939  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x18009793e  test    ebx, ebx
0x180097940  jns     short loc_180097962
0x180097942  lea     rdx, aGetSessionids; "get_SessionIds"
0x180097949  lea     rcx, [rbp+SubStr]
0x18009794d  call    ??$GetAccountFailed@AEAJAEAY0P@$$CBD@MdmSyncTraceProvider@@SAXAEAJAEAY0P@$$CBD@Z; MdmSyncTraceProvider::GetAccountFailed<long &,char const (&)[15]>(long &,char const (&)[15])
0x180097952  lea     rcx, [rbp+var_20]
0x180097956  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18009795b  xor     eax, eax
0x18009795d  jmp     loc_180097C4F
0x180097962  mov     [rbp+arg_8], r15d
0x180097966  mov     [rbp+hMem], r15
0x18009796a  lea     r9, [rbp+arg_8]
0x18009796e  lea     r8, [rbp+hMem]
0x180097972  mov     edx, 1
0x180097977  mov     rcx, [rbp+var_20]
0x18009797b  call    cs:__imp_OmaDmEnumerateInitiationInfo
0x180097981  mov     dword ptr [rbp+SubStr], eax
0x180097984  test    eax, eax
0x180097986  jns     short loc_18009799D
0x180097988  lea     rdx, aGetSessionids; "get_SessionIds"
0x18009798f  lea     rcx, [rbp+SubStr]
0x180097993  call    ??$SessionEnumFailed@AEAJAEAY0P@$$CBD@MdmSyncTraceProvider@@SAXAEAJAEAY0P@$$CBD@Z; MdmSyncTraceProvider::SessionEnumFailed<long &,char const (&)[15]>(long &,char const (&)[15])
0x180097998  jmp     loc_180097C41
0x18009799d  mov     [rbp+SubStr], r15
0x1800979a1  lea     rdx, [rbp+SubStr]
0x1800979a5  call    ??$CreateExternalVector@PEAUHSTRING__@@V?$AgileVector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@$0A@@Internal@Collections@Foundation@Windows@@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEAPEAU?$IVector@PEAUHSTRING__@@@234@@ZPEAPEAV?$AgileVector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@$0A@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalVector<HSTRING__ *,Windows::Foundation::Collections::Internal::AgileVector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::IVector<HSTRING__ *> * *),Windows::Foundation::Collections::Internal::AgileVector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0> * *)
0x1800979aa  mov     esi, r15d
0x1800979ad  mov     rdi, [rbp+SubStr]
0x1800979b1  cmp     esi, [rbp+arg_8]
0x1800979b4  jnb     loc_180097B68
0x1800979ba  mov     dword ptr [rbp+SubStr], 7Bh ; '{'
0x1800979c1  mov     eax, esi
0x1800979c3  lea     rdx, [rbp+SubStr]; SubStr
0x1800979c7  mov     rcx, [rbp+hMem]
0x1800979cb  mov     rcx, [rcx+rax*8]; Str
0x1800979cf  call    ?wcsstr@@YAPEAGPEAGPEBG@Z; wcsstr(ushort *,ushort const *)
0x1800979d4  test    rax, rax
0x1800979d7  jz      short loc_180097A31
0x1800979d9  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800979dd  inc     r8; unsigned int
0x1800979e0  cmp     [rax+r8*2], r15w
0x1800979e5  jnz     short loc_1800979DD
0x1800979e7  mov     [rbp+string], r15
0x1800979eb  cmp     r8, 7FFFFFFFh
0x1800979f2  ja      loc_180097AF9
0x1800979f8  mov     rdx, rax; unsigned __int16 *
0x1800979fb  lea     rcx, [rbp+string]; this
0x1800979ff  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x180097a04  mov     ebx, eax
0x180097a06  test    eax, eax
0x180097a08  js      loc_180097A9C
0x180097a0e  mov     rax, [rdi]
0x180097a11  mov     rdx, [rbp+string]
0x180097a15  mov     rcx, rdi
0x180097a18  mov     rax, [rax+68h]
0x180097a1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097a21  mov     ebx, eax
0x180097a23  test    eax, eax
0x180097a25  js      short loc_180097A38
0x180097a27  mov     rcx, [rbp+string]; string
0x180097a2b  call    cs:__imp_WindowsDeleteString
0x180097a31  inc     esi
0x180097a33  jmp     loc_1800979B1
0x180097a38  mov     rcx, [rbp+28h]; this
0x180097a3c  mov     r9d, eax; char *
0x180097a3f  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\enterprisemgmt\\winr"...
0x180097a46  mov     edx, 0FEh; void *
0x180097a4b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180097a50  mov     rcx, [rbp+string]; string
0x180097a54  call    cs:__imp_WindowsDeleteString
0x180097a5a  mov     [rbp+string], r15
0x180097a5e  test    rdi, rdi
0x180097a61  jz      short loc_180097A73
0x180097a63  mov     rax, [rdi]
0x180097a66  mov     rcx, rdi
0x180097a69  mov     rax, [rax+10h]
0x180097a6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097a72  nop
0x180097a73  mov     edi, r15d
0x180097a76  cmp     [rbp+arg_8], r15d
0x180097a7a  jbe     loc_180097B59
0x180097a80  mov     eax, edi
0x180097a82  mov     rcx, [rbp+hMem]
0x180097a86  mov     rcx, [rcx+rax*8]; hMem
0x180097a8a  call    cs:__imp_LocalFree
0x180097a90  inc     edi
0x180097a92  cmp     edi, [rbp+arg_8]
0x180097a95  jb      short loc_180097A80
0x180097a97  jmp     loc_180097B59
0x180097a9c  mov     rcx, [rbp+28h]; this
0x180097aa0  mov     r9d, eax; char *
0x180097aa3  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\enterprisemgmt\\winr"...
0x180097aaa  mov     edx, 0FDh; void *
0x180097aaf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180097ab4  mov     rcx, [rbp+string]; string
0x180097ab8  call    cs:__imp_WindowsDeleteString
0x180097abe  mov     [rbp+string], r15
0x180097ac2  test    rdi, rdi
0x180097ac5  jz      short loc_180097AD7
0x180097ac7  mov     rax, [rdi]
0x180097aca  mov     rcx, rdi
0x180097acd  mov     rax, [rax+10h]
0x180097ad1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097ad6  nop
0x180097ad7  mov     edi, r15d
0x180097ada  cmp     [rbp+arg_8], r15d
0x180097ade  jbe     short loc_180097B59
0x180097ae0  mov     eax, edi
0x180097ae2  mov     rcx, [rbp+hMem]
0x180097ae6  mov     rcx, [rcx+rax*8]; hMem
0x180097aea  call    cs:__imp_LocalFree
0x180097af0  inc     edi
0x180097af2  cmp     edi, [rbp+arg_8]
0x180097af5  jb      short loc_180097AE0
0x180097af7  jmp     short loc_180097B59
0x180097af9  mov     rcx, [rbp+28h]; this
0x180097afd  mov     ebx, 80070216h
0x180097b02  mov     r9d, ebx; char *
0x180097b05  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\enterprisemgmt\\winr"...
0x180097b0c  mov     edx, 0FBh; void *
0x180097b11  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180097b16  mov     rcx, [rbp+string]; string
0x180097b1a  call    cs:__imp_WindowsDeleteString
0x180097b20  mov     [rbp+string], r15
0x180097b24  test    rdi, rdi
0x180097b27  jz      short loc_180097B39
0x180097b29  mov     rax, [rdi]
0x180097b2c  mov     rcx, rdi
0x180097b2f  mov     rax, [rax+10h]
0x180097b33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097b38  nop
0x180097b39  mov     edi, r15d
0x180097b3c  cmp     [rbp+arg_8], r15d
0x180097b40  jbe     short loc_180097B59
0x180097b42  mov     eax, edi
0x180097b44  mov     rcx, [rbp+hMem]
0x180097b48  mov     rcx, [rcx+rax*8]; hMem
0x180097b4c  call    cs:__imp_LocalFree
0x180097b52  inc     edi
0x180097b54  cmp     edi, [rbp+arg_8]
0x180097b57  jb      short loc_180097B42
0x180097b59  mov     rcx, [rbp+hMem]; hMem
0x180097b5d  call    cs:__imp_LocalFree
0x180097b63  jmp     loc_180097C44
0x180097b68  mov     [rbp+var_28], r15
0x180097b6c  mov     rax, [rdi]
0x180097b6f  mov     rbx, [rax+40h]
0x180097b73  lea     rcx, [rbp+var_28]
0x180097b77  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180097b7c  lea     rdx, [rbp+var_28]
0x180097b80  mov     rcx, rdi
0x180097b83  mov     rax, rbx
0x180097b86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097b8b  mov     ebx, eax
0x180097b8d  test    eax, eax
0x180097b8f  jns     short loc_180097BED
0x180097b91  mov     rcx, [rbp+28h]; this
0x180097b95  mov     r9d, eax; char *
0x180097b98  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\enterprisemgmt\\winr"...
0x180097b9f  mov     edx, 103h; void *
0x180097ba4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180097ba9  lea     rcx, [rbp+var_28]
0x180097bad  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180097bb2  nop
0x180097bb3  test    rdi, rdi
0x180097bb6  jz      short loc_180097BC8
0x180097bb8  mov     rax, [rdi]
0x180097bbb  mov     rcx, rdi
0x180097bbe  mov     rax, [rax+10h]
0x180097bc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097bc7  nop
0x180097bc8  mov     edi, r15d
0x180097bcb  cmp     [rbp+arg_8], r15d
0x180097bcf  jbe     short loc_180097B59
0x180097bd1  mov     eax, edi
0x180097bd3  mov     rcx, [rbp+hMem]
0x180097bd7  mov     rcx, [rcx+rax*8]; hMem
0x180097bdb  call    cs:__imp_LocalFree
0x180097be1  inc     edi
0x180097be3  cmp     edi, [rbp+arg_8]
0x180097be6  jb      short loc_180097BD1
0x180097be8  jmp     loc_180097B59
0x180097bed  mov     rax, [rbp+var_28]
0x180097bf1  mov     [rbp+var_28], r15
0x180097bf5  mov     [r14], rax
0x180097bf8  lea     rcx, [rbp+var_28]
0x180097bfc  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180097c01  nop
0x180097c02  test    rdi, rdi
0x180097c05  jz      short loc_180097C17
0x180097c07  mov     rax, [rdi]
0x180097c0a  mov     rcx, rdi
0x180097c0d  mov     rax, [rax+10h]
0x180097c11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097c16  nop
0x180097c17  mov     ebx, r15d
0x180097c1a  cmp     [rbp+arg_8], r15d
0x180097c1e  jbe     short loc_180097C37
0x180097c20  mov     eax, ebx
0x180097c22  mov     rcx, [rbp+hMem]
0x180097c26  mov     rcx, [rcx+rax*8]; hMem
0x180097c2a  call    cs:__imp_LocalFree
0x180097c30  inc     ebx
0x180097c32  cmp     ebx, [rbp+arg_8]
0x180097c35  jb      short loc_180097C20
0x180097c37  mov     rcx, [rbp+hMem]; hMem
0x180097c3b  call    cs:__imp_LocalFree
0x180097c41  mov     ebx, r15d
0x180097c44  lea     rcx, [rbp+var_20]
0x180097c48  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180097c4d  mov     eax, ebx
0x180097c4f  mov     rbx, [rsp+50h+arg_0]
0x180097c57  add     rsp, 50h
0x180097c5b  pop     r15
0x180097c5d  pop     r14
0x180097c5f  pop     rdi
0x180097c60  pop     rsi
0x180097c61  pop     rbp
0x180097c62  retn
```
