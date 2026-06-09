# StoreAppFinder::IsPackageRegistered(Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager> const &,Microsoft::WRL::ComPtr<Windows::ApplicationModel::IPackage> const &)

- ea: `0x1800fe5ac`
- end: `0x1800fe86f`
- name: `?IsPackageRegistered@StoreAppFinder@@SA_NAEBV?$ComPtr@UIPackageManager@Deployment@Management@Windows@@@WRL@Microsoft@@AEBV?$ComPtr@UIPackage@ApplicationModel@Windows@@@34@@Z`
- size: `707`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x180008e58`

## callees

- `0x18000a39c`
- `0x180018a60`
- `0x180029388`
- `0x180042d0c`
- `0x180059920`
- `0x1800679f8`
- `0x1800fe5ac`
- `0x180130010`

## import_xrefs

- `KERNEL32!GetFileAttributesW` at `0x1800fe7cc`
- `KERNEL32!GetFileAttributesW` at `0x1800fe7cc`

## string_xrefs

- `0x1800fe616`: `onecore\internal\base\inc\appcompat\inventory\storeappfinder.cpp`
- `0x1800fe64f`: `onecore\internal\base\inc\appcompat\inventory\storeappfinder.cpp`
- `0x1800fe68b`: `onecore\internal\base\inc\appcompat\inventory\storeappfinder.cpp`
- `0x1800fe6c4`: `onecore\internal\base\inc\appcompat\inventory\storeappfinder.cpp`
- `0x1800fe6f9`: `onecore\internal\base\inc\appcompat\inventory\storeappfinder.cpp`
- `0x1800fe799`: `onecore\internal\base\inc\appcompat\inventory\storeappfinder.cpp`
- `0x1800fe848`: `onecore\internal\base\inc\appcompat\inventory\storeappfinder.cpp`
- `0x1800fe85d`: `onecore\internal\base\inc\appcompat\inventory\storeappfinder.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
bool __fastcall StoreAppFinder::IsPackageRegistered(_QWORD *a1, __int64 *a2)
{
  __int64 v4; // rdi
  __int64 (__fastcall *v5)(__int64, __int64 *); // rbx
  int v6; // eax
  int v7; // eax
  int v8; // eax
  int v9; // eax
  int v10; // eax
  bool v11; // bl
  int v12; // eax
  int v13; // eax
  int v14; // eax
  const WCHAR *v15; // rcx
  DWORD FileAttributesW; // eax
  int v18; // [rsp+20h] [rbp-60h] BYREF
  int v19; // [rsp+24h] [rbp-5Ch] BYREF
  __int64 v20; // [rsp+28h] [rbp-58h] BYREF
  __int64 v21; // [rsp+30h] [rbp-50h] BYREF
  __int64 v22; // [rsp+38h] [rbp-48h] BYREF
  __int64 v23; // [rsp+40h] [rbp-40h] BYREF
  _QWORD v24[2]; // [rsp+48h] [rbp-38h] BYREF
  LPCWSTR lpFileName[4]; // [rsp+58h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]

  v24[1] = -2;
  v22 = 0;
  v4 = *a2;
  v5 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)*a2 + 48LL);
  Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(&v22);
  v6 = v5(v4, &v22);
  if ( v6 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x33F,
      (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeappfinder.cpp",
      (const char *)(unsigned int)v6,
      v18);
  v24[0] = 0;
  v7 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v22 + 96LL))(v22, v24);
  if ( v7 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x343,
      (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeappfinder.cpp",
      (const char *)(unsigned int)v7,
      v18);
  v23 = 0;
  v8 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64 *))(*(_QWORD *)*a1 + 120LL))(*a1, v24[0], &v23);
  if ( v8 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x347,
      (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeappfinder.cpp",
      (const char *)(unsigned int)v8,
      v18);
  v20 = 0;
  v9 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v23 + 48LL))(v23, &v20);
  if ( v9 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x34B,
      (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeappfinder.cpp",
      (const char *)(unsigned int)v9,
      v18);
  LOBYTE(v18) = 0;
  v10 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v20 + 56LL))(v20, &v18);
  if ( v10 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x350,
      (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeappfinder.cpp",
      (const char *)(unsigned int)v10,
      v18);
  v11 = 0;
  while ( (_BYTE)v18 )
  {
    v21 = 0;
    v12 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v20 + 48LL))(v20, &v21);
    if ( v12 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x356,
        (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeappfinder.cpp",
        (const char *)(unsigned int)v12,
        v18);
    v19 = 0;
    v13 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v21 + 56LL))(v21, &v19);
    if ( v13 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x35A,
        (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeappfinder.cpp",
        (const char *)(unsigned int)v13,
        v18);
    if ( v19 == 2 )
    {
      StoreApplication::GetStoreAppInstallLocationFromPackage(lpFileName, a2);
      if ( lpFileName[2] )
      {
        v15 = (const WCHAR *)lpFileName;
        if ( lpFileName[3] > (LPCWSTR)7 )
          v15 = lpFileName[0];
        FileAttributesW = GetFileAttributesW(v15);
        if ( FileAttributesW != -1 )
          v11 = (FileAttributesW & 0x10) != 0;
      }
      std::wstring::~wstring(lpFileName);
      Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(&v21);
      break;
    }
    v14 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v20 + 64LL))(v20, &v18);
    if ( v14 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x365,
        (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\storeappfinder.cpp",
        (const char *)(unsigned int)v14,
        v18);
    Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(&v21);
  }
  Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(&v20);
  Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(&v23);
  Windows::Internal::String::~String((Windows::Internal::String *)v24);
  Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(&v22);
  return v11;
}

```

## disassembly

```asm
0x1800fe5ac  mov     rax, rsp
0x1800fe5af  push    rbp
0x1800fe5b0  push    rdi
0x1800fe5b1  push    r14
0x1800fe5b3  mov     rbp, rsp
0x1800fe5b6  sub     rsp, 80h
0x1800fe5bd  mov     [rbp+var_30], 0FFFFFFFFFFFFFFFEh
0x1800fe5c5  mov     [rax+18h], rbx
0x1800fe5c9  mov     [rax+20h], rsi
0x1800fe5cd  mov     rax, cs:__security_cookie
0x1800fe5d4  xor     rax, rsp
0x1800fe5d7  mov     [rbp+var_8], rax
0x1800fe5db  mov     rsi, rdx
0x1800fe5de  mov     r14, rcx
0x1800fe5e1  mov     [rbp+var_48], 0
0x1800fe5e9  mov     rdi, [rdx]
0x1800fe5ec  mov     rax, [rdi]
0x1800fe5ef  mov     rbx, [rax+30h]
0x1800fe5f3  lea     rcx, [rbp+var_48]
0x1800fe5f7  call    ?InternalRelease@?$ComPtr@UIXmlDocument@Dom@Xml@Data@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(void)
0x1800fe5fc  lea     rdx, [rbp+var_48]
0x1800fe600  mov     rcx, rdi
0x1800fe603  mov     rax, rbx
0x1800fe606  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fe60b  mov     rcx, [rbp+18h]; this
0x1800fe60f  test    eax, eax
0x1800fe611  jns     short loc_1800FE628
0x1800fe613  mov     r9d, eax; char *
0x1800fe616  lea     r8, aOnecoreInterna_3; "onecore\\internal\\base\\inc\\appcompat"...
0x1800fe61d  mov     edx, 33Fh; void *
0x1800fe622  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800fe628  mov     [rbp+var_38], 0
0x1800fe630  mov     rcx, [rbp+var_48]
0x1800fe634  mov     rax, [rcx]
0x1800fe637  lea     rdx, [rbp+var_38]
0x1800fe63b  mov     rax, [rax+60h]
0x1800fe63f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fe644  mov     rcx, [rbp+18h]; this
0x1800fe648  test    eax, eax
0x1800fe64a  jns     short loc_1800FE661
0x1800fe64c  mov     r9d, eax; char *
0x1800fe64f  lea     r8, aOnecoreInterna_3; "onecore\\internal\\base\\inc\\appcompat"...
0x1800fe656  mov     edx, 343h; void *
0x1800fe65b  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800fe661  mov     [rbp+var_40], 0
0x1800fe669  mov     rcx, [r14]
0x1800fe66c  mov     rax, [rcx]
0x1800fe66f  lea     r8, [rbp+var_40]
0x1800fe673  mov     rdx, [rbp+var_38]
0x1800fe677  mov     rax, [rax+78h]
0x1800fe67b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fe680  mov     rcx, [rbp+18h]; this
0x1800fe684  test    eax, eax
0x1800fe686  jns     short loc_1800FE69D
0x1800fe688  mov     r9d, eax; char *
0x1800fe68b  lea     r8, aOnecoreInterna_3; "onecore\\internal\\base\\inc\\appcompat"...
0x1800fe692  mov     edx, 347h; void *
0x1800fe697  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800fe69d  mov     [rbp+var_58], 0
0x1800fe6a5  mov     rcx, [rbp+var_40]
0x1800fe6a9  mov     rax, [rcx]
0x1800fe6ac  lea     rdx, [rbp+var_58]
0x1800fe6b0  mov     rax, [rax+30h]
0x1800fe6b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fe6b9  mov     rcx, [rbp+18h]; this
0x1800fe6bd  test    eax, eax
0x1800fe6bf  jns     short loc_1800FE6D6
0x1800fe6c1  mov     r9d, eax; char *
0x1800fe6c4  lea     r8, aOnecoreInterna_3; "onecore\\internal\\base\\inc\\appcompat"...
0x1800fe6cb  mov     edx, 34Bh; void *
0x1800fe6d0  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800fe6d6  mov     byte ptr [rbp+var_60], 0
0x1800fe6da  mov     rcx, [rbp+var_58]
0x1800fe6de  mov     rax, [rcx]
0x1800fe6e1  lea     rdx, [rbp+var_60]
0x1800fe6e5  mov     rax, [rax+38h]
0x1800fe6e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fe6ee  mov     rcx, [rbp+18h]; this
0x1800fe6f2  test    eax, eax
0x1800fe6f4  jns     short loc_1800FE70B
0x1800fe6f6  mov     r9d, eax; char *
0x1800fe6f9  lea     r8, aOnecoreInterna_3; "onecore\\internal\\base\\inc\\appcompat"...
0x1800fe700  mov     edx, 350h; void *
0x1800fe705  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800fe70b  xor     bl, bl
0x1800fe70d  cmp     byte ptr [rbp+var_60], 0
0x1800fe711  jz      loc_1800FE7F8
0x1800fe717  mov     [rbp+var_50], 0
0x1800fe71f  mov     rcx, [rbp+var_58]
0x1800fe723  mov     rax, [rcx]
0x1800fe726  lea     rdx, [rbp+var_50]
0x1800fe72a  mov     rax, [rax+30h]
0x1800fe72e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fe733  mov     rcx, [rbp+18h]; this
0x1800fe737  test    eax, eax
0x1800fe739  js      loc_1800FE85A
0x1800fe73f  mov     [rbp+var_5C], 0
0x1800fe746  mov     rcx, [rbp+var_50]
0x1800fe74a  mov     rax, [rcx]
0x1800fe74d  lea     rdx, [rbp+var_5C]
0x1800fe751  mov     rax, [rax+38h]
0x1800fe755  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fe75a  mov     rcx, [rbp+18h]; this
0x1800fe75e  test    eax, eax
0x1800fe760  js      loc_1800FE845
0x1800fe766  cmp     [rbp+var_5C], 2
0x1800fe76a  jz      short loc_1800FE7AB
0x1800fe76c  mov     rcx, [rbp+var_58]
0x1800fe770  mov     rax, [rcx]
0x1800fe773  lea     rdx, [rbp+var_60]
0x1800fe777  mov     rax, [rax+40h]
0x1800fe77b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fe780  mov     rcx, [rbp+18h]; this
0x1800fe784  test    eax, eax
0x1800fe786  js      short loc_1800FE796
0x1800fe788  lea     rcx, [rbp+var_50]
0x1800fe78c  call    ?InternalRelease@?$ComPtr@UIXmlDocument@Dom@Xml@Data@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(void)
0x1800fe791  jmp     loc_1800FE70D
0x1800fe796  mov     r9d, eax; char *
0x1800fe799  lea     r8, aOnecoreInterna_3; "onecore\\internal\\base\\inc\\appcompat"...
0x1800fe7a0  mov     edx, 365h; void *
0x1800fe7a5  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800fe7ab  mov     rdx, rsi
0x1800fe7ae  lea     rcx, [rbp+lpFileName]
0x1800fe7b2  call    ?GetStoreAppInstallLocationFromPackage@StoreApplication@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$ComPtr@UIPackage@ApplicationModel@Windows@@@WRL@Microsoft@@@Z; StoreApplication::GetStoreAppInstallLocationFromPackage(Microsoft::WRL::ComPtr<Windows::ApplicationModel::IPackage> const &)
0x1800fe7b7  cmp     [rbp+var_18], 0
0x1800fe7bc  jbe     short loc_1800FE7E4
0x1800fe7be  lea     rcx, [rbp+lpFileName]
0x1800fe7c2  cmp     [rbp+var_10], 7
0x1800fe7c7  cmova   rcx, [rbp+lpFileName]; lpFileName
0x1800fe7cc  call    cs:__imp_GetFileAttributesW
0x1800fe7d2  cmp     eax, 0FFFFFFFFh
0x1800fe7d5  jz      short loc_1800FE7E4
0x1800fe7d7  test    al, 10h
0x1800fe7d9  movzx   ebx, bl
0x1800fe7dc  mov     eax, 1
0x1800fe7e1  cmovnz  ebx, eax
0x1800fe7e4  lea     rcx, [rbp+lpFileName]
0x1800fe7e8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800fe7ed  nop
0x1800fe7ee  lea     rcx, [rbp+var_50]
0x1800fe7f2  call    ?InternalRelease@?$ComPtr@UIXmlDocument@Dom@Xml@Data@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(void)
0x1800fe7f7  nop
0x1800fe7f8  lea     rcx, [rbp+var_58]
0x1800fe7fc  call    ?InternalRelease@?$ComPtr@UIXmlDocument@Dom@Xml@Data@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(void)
0x1800fe801  nop
0x1800fe802  lea     rcx, [rbp+var_40]
0x1800fe806  call    ?InternalRelease@?$ComPtr@UIXmlDocument@Dom@Xml@Data@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(void)
0x1800fe80b  nop
0x1800fe80c  lea     rcx, [rbp+var_38]; this
0x1800fe810  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800fe815  nop
0x1800fe816  lea     rcx, [rbp+var_48]
0x1800fe81a  call    ?InternalRelease@?$ComPtr@UIXmlDocument@Dom@Xml@Data@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>::InternalRelease(void)
0x1800fe81f  mov     al, bl
0x1800fe821  mov     rcx, [rbp+var_8]
0x1800fe825  xor     rcx, rsp; StackCookie
0x1800fe828  call    __security_check_cookie
0x1800fe82d  lea     r11, [rsp+80h+var_s0]
0x1800fe835  mov     rbx, [r11+30h]
0x1800fe839  mov     rsi, [r11+38h]
0x1800fe83d  mov     rsp, r11
0x1800fe840  pop     r14
0x1800fe842  pop     rdi
0x1800fe843  pop     rbp
0x1800fe844  retn
0x1800fe845  mov     r9d, eax; char *
0x1800fe848  lea     r8, aOnecoreInterna_3; "onecore\\internal\\base\\inc\\appcompat"...
0x1800fe84f  mov     edx, 35Ah; void *
0x1800fe854  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800fe85a  mov     r9d, eax; char *
0x1800fe85d  lea     r8, aOnecoreInterna_3; "onecore\\internal\\base\\inc\\appcompat"...
0x1800fe864  mov     edx, 356h; void *
0x1800fe869  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
