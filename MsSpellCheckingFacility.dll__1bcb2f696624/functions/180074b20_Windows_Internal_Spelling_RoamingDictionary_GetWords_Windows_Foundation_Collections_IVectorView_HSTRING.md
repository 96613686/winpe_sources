# Windows::Internal::Spelling::RoamingDictionary::GetWords(Windows::Foundation::Collections::IVectorView<HSTRING__ *> * *)

- ea: `0x180074b20`
- end: `0x180074f21`
- name: `?GetWords@RoamingDictionary@Spelling@Internal@Windows@@UEAAJPEAPEAU?$IVectorView@PEAUHSTRING__@@@Collections@Foundation@4@@Z`
- size: `1025`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18003834c`
- `0x180040cc4`
- `0x1800425a8`
- `0x1800431c0`
- `0x18004aa2c`
- `0x180061320`
- `0x180062314`
- `0x180070530`
- `0x18007257c`
- `0x180072664`
- `0x180074b20`
- `0x1800c0010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180074d04`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180074db6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180074e0f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180074d04`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180074db6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180074e0f`

## string_xrefs

- `0x180074b63`: `onecoreuap\base\win32\winnls\els\advancedservices\spelling\spellcheck\current\roamingdictionary.cpp`
- `0x180074b8e`: `onecoreuap\base\win32\winnls\els\advancedservices\spelling\spellcheck\current\roamingdictionary.cpp`
- `0x180074be2`: `onecoreuap\base\win32\winnls\els\advancedservices\spelling\spellcheck\current\roamingdictionary.cpp`
- `0x180074c29`: `onecoreuap\base\win32\winnls\els\advancedservices\spelling\spellcheck\current\roamingdictionary.cpp`
- `0x180074cdb`: `onecoreuap\base\win32\winnls\els\advancedservices\spelling\spellcheck\current\roamingdictionary.cpp`
- `0x180074d7f`: `onecoreuap\base\win32\winnls\els\advancedservices\spelling\spellcheck\current\roamingdictionary.cpp`
- `0x180074e49`: `onecoreuap\base\win32\winnls\els\advancedservices\spelling\spellcheck\current\roamingdictionary.cpp`
- `0x180074ea4`: `onecoreuap\base\win32\winnls\els\advancedservices\spelling\spellcheck\current\roamingdictionary.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
__int64 __fastcall Windows::Internal::Spelling::RoamingDictionary::GetWords(
        Windows::Internal::Spelling::RoamingDictionary *a1,
        __int64 a2)
{
  int v5; // eax
  __int64 *v6; // rcx
  __int64 v7; // rax
  int v8; // eax
  __int64 v9; // rcx
  unsigned int v10; // ebx
  int v11; // eax
  unsigned int v12; // ebx
  int v13; // eax
  __int64 *v14; // rbx
  int v15; // eax
  unsigned int v16; // edi
  __int64 v17; // rbx
  unsigned int j; // edx
  void *v19; // rcx
  __int64 i; // rdi
  __int64 v21; // rax
  HSTRING v22; // rdx
  int v23; // eax
  unsigned int v24; // esi
  __int64 v25; // rbx
  void *v26; // rcx
  __int64 v27; // rdi
  void *v28; // rcx
  int v29; // eax
  unsigned int v30; // edi
  int v31; // eax
  unsigned int v32; // ebx
  int v33; // [rsp+20h] [rbp-3A8h]
  int v34; // [rsp+30h] [rbp-398h] BYREF
  __int64 v35; // [rsp+38h] [rbp-390h] BYREF
  unsigned int v36; // [rsp+40h] [rbp-388h] BYREF
  __int64 *v37; // [rsp+48h] [rbp-380h] BYREF
  unsigned int v38; // [rsp+50h] [rbp-378h] BYREF
  HSTRING string[3]; // [rsp+58h] [rbp-370h] BYREF
  char v40; // [rsp+70h] [rbp-358h]
  LPVOID pv[100]; // [rsp+80h] [rbp-348h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3C8h] [rbp+0h]

  if ( a2 )
  {
    v5 = Windows::Internal::Spelling::RoamingDictionary::EnsureInitialized(a1);
    if ( v5 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x71,
        (unsigned int)"onecoreuap\\base\\win32\\winnls\\els\\advancedservices\\spelling\\spellcheck\\current\\roamingdictionary.cpp",
        (const char *)(unsigned int)v5,
        v33);
    v38 = 100;
    v35 = 0;
    v6 = (__int64 *)*((_QWORD *)a1 + 18);
    v7 = *v6;
    v35 = 0;
    v8 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v7 + 32))(v6, &v35);
    v10 = v8;
    if ( v8 >= 0 )
    {
      v37 = 0;
      v11 = Windows::Foundation::Collections::Internal::detail::CreateExternalVector<HSTRING__ *,Windows::Foundation::Collections::Internal::AgileVector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>>(
              v9,
              &v37);
      v12 = v11;
      if ( v11 >= 0 )
      {
        v13 = 100;
        v36 = 100;
        v14 = v37;
        while ( 1 )
        {
          if ( v13 != 100 )
          {
            v29 = (*(__int64 (__fastcall **)(__int64 *, __int64))(*v14 + 64))(v14, a2);
            v30 = v29;
            if ( v29 >= 0 )
            {
              v34 = 0;
              v31 = (*(__int64 (__fastcall **)(__int64 *, int *))(*v14 + 56))(v14, &v34);
              v32 = v31;
              if ( v31 >= 0 )
              {
                SpellingTelemetry::GetWords<unsigned int &>(&v34);
                ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v37);
                ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v35);
                return 0;
              }
              else
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x98,
                  (unsigned int)"onecoreuap\\base\\win32\\winnls\\els\\advancedservices\\spelling\\spellcheck\\current\\r"
                                "oamingdictionary.cpp",
                  (const char *)(unsigned int)v31,
                  v33);
                ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v37);
                ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v35);
                return v32;
              }
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x95,
                (unsigned int)"onecoreuap\\base\\win32\\winnls\\els\\advancedservices\\spelling\\spellcheck\\current\\roa"
                              "mingdictionary.cpp",
                (const char *)(unsigned int)v29,
                v33);
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v37);
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v35);
              return v30;
            }
          }
          memset_0(pv, 0, sizeof(pv));
          string[1] = (HSTRING)&v38;
          string[2] = (HSTRING)pv;
          v40 = 1;
          v36 = 0;
          v15 = (*(__int64 (__fastcall **)(__int64, __int64, LPVOID *, unsigned int *))(*(_QWORD *)v35 + 24LL))(
                  v35,
                  100,
                  pv,
                  &v36);
          v16 = v15;
          if ( v15 < 0 )
            break;
          for ( i = 0; ; i = (unsigned int)(i + 1) )
          {
            v13 = v36;
            if ( (unsigned int)i >= v36 )
              break;
            wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(
              string,
              (PCNZWCH)pv[i]);
            v21 = *v14;
            v22 = string[0];
            string[0] = 0;
            v23 = (*(__int64 (__fastcall **)(__int64 *, HSTRING))(v21 + 104))(v14, v22);
            v24 = v23;
            if ( v23 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x91,
                (unsigned int)"onecoreuap\\base\\win32\\winnls\\els\\advancedservices\\spelling\\spellcheck\\current\\roa"
                              "mingdictionary.cpp",
                (const char *)(unsigned int)v23,
                v33);
              Windows::Internal::String::~String((Windows::Internal::String *)string);
              if ( v38 )
              {
                v25 = 0;
                do
                {
                  v26 = pv[v25];
                  if ( v26 )
                    CoTaskMemFree(v26);
                  v25 = (unsigned int)(v25 + 1);
                }
                while ( (unsigned int)v25 < v38 );
              }
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v37);
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v35);
              return v24;
            }
            Windows::Internal::String::~String((Windows::Internal::String *)string);
          }
          if ( v38 )
          {
            v27 = 0;
            do
            {
              v28 = pv[v27];
              if ( v28 )
                CoTaskMemFree(v28);
              v27 = (unsigned int)(v27 + 1);
            }
            while ( (unsigned int)v27 < v38 );
            v13 = v36;
          }
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x8C,
          (unsigned int)"onecoreuap\\base\\win32\\winnls\\els\\advancedservices\\spelling\\spellcheck\\current\\roamingdictionary.cpp",
          (const char *)(unsigned int)v15,
          v33);
        v17 = 0;
        for ( j = v38; (unsigned int)v17 < j; v17 = (unsigned int)(v17 + 1) )
        {
          v19 = pv[v17];
          if ( v19 )
          {
            CoTaskMemFree(v19);
            j = v38;
          }
        }
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v37);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v35);
        return v16;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x7A,
          (unsigned int)"onecoreuap\\base\\win32\\winnls\\els\\advancedservices\\spelling\\spellcheck\\current\\roamingdictionary.cpp",
          (const char *)(unsigned int)v11,
          v33);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v37);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v35);
        return v12;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x77,
        (unsigned int)"onecoreuap\\base\\win32\\winnls\\els\\advancedservices\\spelling\\spellcheck\\current\\roamingdictionary.cpp",
        (const char *)(unsigned int)v8,
        v33);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v35);
      return v10;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x70,
      (unsigned int)"onecoreuap\\base\\win32\\winnls\\els\\advancedservices\\spelling\\spellcheck\\current\\roamingdictionary.cpp",
      (const char *)0x80070057LL,
      v33);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x180074b20  mov     [rsp+arg_10], rbx
0x180074b25  mov     [rsp+arg_18], rsi
0x180074b2a  push    rdi
0x180074b2b  push    r12
0x180074b2d  push    r14
0x180074b2f  sub     rsp, 3B0h
0x180074b36  mov     rax, cs:__security_cookie
0x180074b3d  xor     rax, rsp
0x180074b40  mov     [rsp+3C8h+var_28], rax
0x180074b48  mov     r14, rdx
0x180074b4b  mov     rbx, rcx
0x180074b4e  test    rdx, rdx
0x180074b51  jnz     short loc_180074B7A
0x180074b53  mov     rcx, [rsp+3C8h]; this
0x180074b5b  mov     ebx, 80070057h
0x180074b60  mov     r9d, ebx; char *
0x180074b63  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\win32\\winnls\\els\\a"...
0x180074b6a  lea     edx, [r14+70h]; void *
0x180074b6e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180074b73  mov     eax, ebx
0x180074b75  jmp     loc_180074EF7
0x180074b7a  call    ?EnsureInitialized@RoamingDictionary@Spelling@Internal@Windows@@AEAAJXZ; Windows::Internal::Spelling::RoamingDictionary::EnsureInitialized(void)
0x180074b7f  mov     rcx, [rsp+3C8h]; this
0x180074b87  test    eax, eax
0x180074b89  jns     short loc_180074B9F
0x180074b8b  mov     r9d, eax; char *
0x180074b8e  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\win32\\winnls\\els\\a"...
0x180074b95  mov     edx, 71h ; 'q'; void *
0x180074b9a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180074b9f  mov     [rsp+3C8h+var_378], 64h ; 'd'
0x180074ba7  mov     [rsp+3C8h+var_390], 0
0x180074bb0  mov     rcx, [rbx+90h]
0x180074bb7  mov     rax, [rcx]
0x180074bba  mov     [rsp+3C8h+var_390], 0
0x180074bc3  lea     rdx, [rsp+3C8h+var_390]
0x180074bc8  mov     rax, [rax+20h]
0x180074bcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074bd1  mov     ebx, eax
0x180074bd3  test    eax, eax
0x180074bd5  jns     short loc_180074C05
0x180074bd7  mov     rcx, [rsp+3C8h]; this
0x180074bdf  mov     r9d, eax; char *
0x180074be2  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\win32\\winnls\\els\\a"...
0x180074be9  mov     edx, 77h ; 'w'; void *
0x180074bee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180074bf3  nop
0x180074bf4  lea     rcx, [rsp+3C8h+var_390]
0x180074bf9  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180074bfe  mov     eax, ebx
0x180074c00  jmp     loc_180074EF7
0x180074c05  mov     [rsp+3C8h+var_380], 0
0x180074c0e  lea     rdx, [rsp+3C8h+var_380]
0x180074c13  call    ??$CreateExternalVector@PEAUHSTRING__@@V?$AgileVector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@$0A@@Internal@Collections@Foundation@Windows@@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEAPEAU?$IVector@PEAUHSTRING__@@@234@@ZPEAPEAV?$AgileVector@PEAUHSTRING__@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@$0A@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalVector<HSTRING__ *,Windows::Foundation::Collections::Internal::AgileVector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::IVector<HSTRING__ *> * *),Windows::Foundation::Collections::Internal::AgileVector<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0> * *)
0x180074c18  mov     ebx, eax
0x180074c1a  test    eax, eax
0x180074c1c  jns     short loc_180074C57
0x180074c1e  mov     rcx, [rsp+3C8h]; this
0x180074c26  mov     r9d, eax; char *
0x180074c29  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\win32\\winnls\\els\\a"...
0x180074c30  mov     edx, 7Ah ; 'z'; void *
0x180074c35  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180074c3a  nop
0x180074c3b  lea     rcx, [rsp+3C8h+var_380]
0x180074c40  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180074c45  nop
0x180074c46  lea     rcx, [rsp+3C8h+var_390]
0x180074c4b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180074c50  mov     eax, ebx
0x180074c52  jmp     loc_180074EF7
0x180074c57  mov     eax, 64h ; 'd'
0x180074c5c  mov     [rsp+3C8h+var_388], eax
0x180074c60  mov     rbx, [rsp+3C8h+var_380]
0x180074c65  cmp     eax, 64h ; 'd'
0x180074c68  jnz     loc_180074E26
0x180074c6e  xor     edx, edx; Val
0x180074c70  mov     r8d, 320h; Size
0x180074c76  lea     rcx, [rsp+3C8h+pv]; void *
0x180074c7e  call    memset_0
0x180074c83  lea     r12, [rsp+3C8h+var_378]
0x180074c88  mov     [rsp+3C8h+var_368], r12
0x180074c8d  lea     rsi, [rsp+3C8h+pv]
0x180074c95  mov     [rsp+3C8h+var_360], rsi
0x180074c9a  mov     [rsp+3C8h+var_358], 1
0x180074c9f  mov     [rsp+3C8h+var_388], 0
0x180074ca7  mov     rcx, [rsp+3C8h+var_390]
0x180074cac  mov     rax, [rcx]
0x180074caf  lea     r9, [rsp+3C8h+var_388]
0x180074cb4  lea     r8, [rsp+3C8h+pv]
0x180074cbc  mov     edx, 64h ; 'd'
0x180074cc1  mov     rax, [rax+18h]
0x180074cc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074cca  mov     edi, eax
0x180074ccc  test    eax, eax
0x180074cce  jns     short loc_180074D30
0x180074cd0  mov     rcx, [rsp+3C8h]; this
0x180074cd8  mov     r9d, eax; char *
0x180074cdb  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\win32\\winnls\\els\\a"...
0x180074ce2  mov     edx, 8Ch; void *
0x180074ce7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180074cec  nop
0x180074ced  xor     ebx, ebx
0x180074cef  mov     edx, [rsp+3C8h+var_378]
0x180074cf3  test    edx, edx
0x180074cf5  jz      short loc_180074D14
0x180074cf7  mov     rcx, [rsp+rbx*8+3C8h+pv]; pv
0x180074cff  test    rcx, rcx
0x180074d02  jz      short loc_180074D0E
0x180074d04  call    cs:__imp_CoTaskMemFree
0x180074d0a  mov     edx, [rsp+3C8h+var_378]
0x180074d0e  inc     ebx
0x180074d10  cmp     ebx, edx
0x180074d12  jb      short loc_180074CF7
0x180074d14  lea     rcx, [rsp+3C8h+var_380]
0x180074d19  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180074d1e  nop
0x180074d1f  lea     rcx, [rsp+3C8h+var_390]
0x180074d24  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180074d29  mov     eax, edi
0x180074d2b  jmp     loc_180074EF7
0x180074d30  xor     edi, edi
0x180074d32  mov     eax, [rsp+3C8h+var_388]
0x180074d36  cmp     edi, eax
0x180074d38  jnb     loc_180074DF1
0x180074d3e  mov     rdx, [rsp+rdi*8+3C8h+pv]; sourceString
0x180074d46  lea     rcx, [rsp+3C8h+string]; string
0x180074d4b  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180074d50  nop
0x180074d51  mov     rax, [rbx]
0x180074d54  mov     rdx, [rsp+3C8h+string]
0x180074d59  mov     [rsp+3C8h+string], 0
0x180074d62  mov     rcx, rbx
0x180074d65  mov     rax, [rax+68h]
0x180074d69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074d6e  mov     esi, eax
0x180074d70  test    eax, eax
0x180074d72  jns     short loc_180074DE0
0x180074d74  mov     rcx, [rsp+3C8h]; this
0x180074d7c  mov     r9d, eax; char *
0x180074d7f  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\win32\\winnls\\els\\a"...
0x180074d86  mov     edx, 91h; void *
0x180074d8b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180074d90  nop
0x180074d91  lea     rcx, [rsp+3C8h+string]; this
0x180074d96  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180074d9b  nop
0x180074d9c  cmp     dword ptr [r12], 0
0x180074da1  jbe     short loc_180074DC4
0x180074da3  xor     ebx, ebx
0x180074da5  lea     rdi, [rsp+3C8h+pv]
0x180074dad  mov     rcx, [rdi+rbx*8]; pv
0x180074db1  test    rcx, rcx
0x180074db4  jz      short loc_180074DBC
0x180074db6  call    cs:__imp_CoTaskMemFree
0x180074dbc  inc     ebx
0x180074dbe  cmp     ebx, [r12]
0x180074dc2  jb      short loc_180074DAD
0x180074dc4  lea     rcx, [rsp+3C8h+var_380]
0x180074dc9  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180074dce  nop
0x180074dcf  lea     rcx, [rsp+3C8h+var_390]
0x180074dd4  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180074dd9  mov     eax, esi
0x180074ddb  jmp     loc_180074EF7
0x180074de0  lea     rcx, [rsp+3C8h+string]; this
0x180074de5  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180074dea  inc     edi
0x180074dec  jmp     loc_180074D32
0x180074df1  cmp     dword ptr [r12], 0
0x180074df6  jbe     loc_180074C65
0x180074dfc  xor     edi, edi
0x180074dfe  lea     rsi, [rsp+3C8h+pv]
0x180074e06  mov     rcx, [rsi+rdi*8]; pv
0x180074e0a  test    rcx, rcx
0x180074e0d  jz      short loc_180074E15
0x180074e0f  call    cs:__imp_CoTaskMemFree
0x180074e15  inc     edi
0x180074e17  cmp     edi, [r12]
0x180074e1b  jb      short loc_180074E06
0x180074e1d  mov     eax, [rsp+3C8h+var_388]
0x180074e21  jmp     loc_180074C65
0x180074e26  mov     rax, [rbx]
0x180074e29  mov     rdx, r14
0x180074e2c  mov     rcx, rbx
0x180074e2f  mov     rax, [rax+40h]
0x180074e33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074e38  mov     edi, eax
0x180074e3a  test    eax, eax
0x180074e3c  jns     short loc_180074E77
0x180074e3e  mov     rcx, [rsp+3C8h]; this
0x180074e46  mov     r9d, eax; char *
0x180074e49  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\win32\\winnls\\els\\a"...
0x180074e50  mov     edx, 95h; void *
0x180074e55  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180074e5a  nop
0x180074e5b  lea     rcx, [rsp+3C8h+var_380]
0x180074e60  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180074e65  nop
0x180074e66  lea     rcx, [rsp+3C8h+var_390]
0x180074e6b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180074e70  mov     eax, edi
0x180074e72  jmp     loc_180074EF7
0x180074e77  mov     [rsp+3C8h+var_398], 0
0x180074e7f  mov     rax, [rbx]
0x180074e82  lea     rdx, [rsp+3C8h+var_398]
0x180074e87  mov     rcx, rbx
0x180074e8a  mov     rax, [rax+38h]
0x180074e8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074e93  mov     ebx, eax
0x180074e95  test    eax, eax
0x180074e97  jns     short loc_180074ECF
0x180074e99  mov     rcx, [rsp+3C8h]; this
0x180074ea1  mov     r9d, eax; char *
0x180074ea4  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\win32\\winnls\\els\\a"...
0x180074eab  mov     edx, 98h; void *
0x180074eb0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180074eb5  nop
0x180074eb6  lea     rcx, [rsp+3C8h+var_380]
0x180074ebb  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180074ec0  nop
0x180074ec1  lea     rcx, [rsp+3C8h+var_390]
0x180074ec6  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180074ecb  mov     eax, ebx
0x180074ecd  jmp     short loc_180074EF7
0x180074ecf  lea     rcx, [rsp+3C8h+var_398]
0x180074ed4  call    ??$GetWords@AEAI@SpellingTelemetry@@SAXAEAI@Z; SpellingTelemetry::GetWords<uint &>(uint &)
0x180074ed9  nop
0x180074eda  lea     rcx, [rsp+3C8h+var_380]
0x180074edf  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180074ee4  nop
0x180074ee5  lea     rcx, [rsp+3C8h+var_390]
0x180074eea  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180074eef  xor     eax, eax
0x180074ef1  jmp     short loc_180074EF7
0x180074ef3  mov     eax, [rsp+3C8h+var_398]
0x180074ef7  mov     rcx, [rsp+3C8h+var_28]
0x180074eff  xor     rcx, rsp; StackCookie
0x180074f02  call    __security_check_cookie
0x180074f07  lea     r11, [rsp+3C8h+var_18]
0x180074f0f  mov     rbx, [r11+30h]
0x180074f13  mov     rsi, [r11+38h]
0x180074f17  mov     rsp, r11
0x180074f1a  pop     r14
0x180074f1c  pop     r12
0x180074f1e  pop     rdi
0x180074f1f  retn
```
