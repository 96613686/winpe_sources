# StoreAppFinder::GetEvidenceFromPackageAndDependenciesSr(ConfigSettings const &,Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage>,std::vector<Application,std::allocator<Application>> &)

- ea: `0x1800d768c`
- end: `0x1800d78ae`
- name: `?GetEvidenceFromPackageAndDependenciesSr@StoreAppFinder@@SAXAEBVConfigSettings@@V?$ComPtr@UIPackage@StateRepository@Internal@Windows@@@WRL@Microsoft@@AEAV?$vector@VApplication@@V?$allocator@VApplication@@@std@@@std@@@Z`
- size: `546`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800d5ab4`

## callees

- `0x180005890`
- `0x18000a2d4`
- `0x1800252b0`
- `0x1800c97f0`
- `0x1800d768c`
- `0x1800d78b4`
- `0x1800eb010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800d771f`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800d771f`

## string_xrefs

- `0x1800d7730`: `onecore\base\appcompat\inventory\software\inv\lib\storeappfinder.cpp`
- `0x1800d7773`: `onecore\base\appcompat\inventory\software\inv\lib\storeappfinder.cpp`
- `0x1800d77ab`: `onecore\base\appcompat\inventory\software\inv\lib\storeappfinder.cpp`
- `0x1800d7887`: `onecore\base\appcompat\inventory\software\inv\lib\storeappfinder.cpp`
- `0x1800d789c`: `onecore\base\appcompat\inventory\software\inv\lib\storeappfinder.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall StoreAppFinder::GetEvidenceFromPackageAndDependenciesSr(struct ConfigSettings *a1, _QWORD *a2)
{
  __int64 v4; // rbx
  int ActivationFactory; // eax
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, _QWORD, __int64 *); // rbx
  int v8; // eax
  int v9; // eax
  unsigned int i; // esi
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, _QWORD, __int64 *); // rbx
  int v13; // eax
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, _QWORD *); // rbx
  int v16; // eax
  unsigned int v18; // [rsp+20h] [rbp-60h] BYREF
  __int64 v19; // [rsp+28h] [rbp-58h] BYREF
  __int64 v20; // [rsp+30h] [rbp-50h] BYREF
  __int64 v21; // [rsp+38h] [rbp-48h] BYREF
  _QWORD v22[2]; // [rsp+40h] [rbp-40h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+50h] [rbp-30h] BYREF
  __int64 v24; // [rsp+68h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]

  v22[1] = a2;
  v22[0] = 0;
  StoreAppFinder::GetEvidenceFromPackageSr(a1);
  v19 = 0;
  v21 = 0;
  v20 = 0;
  v24 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Internal.StateRepository.NamedDependency",
    0x31u,
    0x30u);
  v4 = v24;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
  ActivationFactory = RoGetActivationFactory(v4, &GUID_a11a8611_7d1e_419b_b359_c4438518bb5e, &v20);
  if ( ActivationFactory < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x46B,
      (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeappfinder.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v18);
  v6 = v20;
  v7 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v20 + 104LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
  v8 = v7(v6, *a2, &v19);
  if ( v8 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x46E,
      (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeappfinder.cpp",
      (const char *)(unsigned int)v8,
      v18);
  v18 = 0;
  v9 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v19 + 56LL))(v19, &v18);
  if ( v9 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x472,
      (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeappfinder.cpp",
      (const char *)(unsigned int)v9,
      v18);
  for ( i = 0; i < v18; ++i )
  {
    v11 = v19;
    v12 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v19 + 48LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v21);
    v13 = v12(v11, i, &v21);
    if ( v13 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x478,
        (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeappfinder.cpp",
        (const char *)(unsigned int)v13,
        v18);
    v14 = v21;
    v15 = *(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v21 + 80LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v22);
    v16 = v15(v14, v22);
    if ( v16 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x47B,
        (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeappfinder.cpp",
        (const char *)(unsigned int)v16,
        v18);
    StoreAppFinder::GetEvidenceFromPackageSr(a1);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v21);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v22);
  return Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a2);
}

```

## disassembly

```asm
0x1800d768c  push    rbp
0x1800d768e  push    rbx
0x1800d768f  push    rsi
0x1800d7690  push    rdi
0x1800d7691  push    r12
0x1800d7693  push    r14
0x1800d7695  push    r15
0x1800d7697  mov     rbp, rsp
0x1800d769a  sub     rsp, 80h
0x1800d76a1  mov     rax, cs:__security_cookie
0x1800d76a8  xor     rax, rsp
0x1800d76ab  mov     [rbp+var_10], rax
0x1800d76af  mov     r12, r8
0x1800d76b2  mov     r14, rdx
0x1800d76b5  mov     r15, rcx
0x1800d76b8  mov     [rbp+var_38], rdx
0x1800d76bc  mov     [rbp+var_40], 0
0x1800d76c4  call    ?GetEvidenceFromPackageSr@StoreAppFinder@@SAXAEBVConfigSettings@@AEBV?$ComPtr@UIPackage@StateRepository@Internal@Windows@@@WRL@Microsoft@@AEAV?$vector@VApplication@@V?$allocator@VApplication@@@std@@@std@@@Z; StoreAppFinder::GetEvidenceFromPackageSr(ConfigSettings const &,Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage> const &,std::vector<Application> &)
0x1800d76c9  mov     [rbp+var_58], 0
0x1800d76d1  mov     [rbp+var_48], 0
0x1800d76d9  mov     [rbp+var_50], 0
0x1800d76e1  mov     [rbp+var_18], 0
0x1800d76e9  mov     r9d, 30h ; '0'; unsigned int
0x1800d76ef  lea     r8d, [r9+1]; unsigned int
0x1800d76f3  lea     rdx, ?RuntimeClass_Windows_Internal_StateRepository_NamedDependency@@3QBGB; "Windows.Internal.StateRepository.NamedD"...
0x1800d76fa  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x1800d76fe  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800d7703  nop
0x1800d7704  mov     rbx, [rbp+var_18]
0x1800d7708  lea     rcx, [rbp+var_50]
0x1800d770c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800d7711  lea     r8, [rbp+var_50]
0x1800d7715  lea     rdx, _GUID_a11a8611_7d1e_419b_b359_c4438518bb5e
0x1800d771c  mov     rcx, rbx
0x1800d771f  call    cs:__imp_RoGetActivationFactory
0x1800d7725  mov     rcx, [rbp+38h]; this
0x1800d7729  test    eax, eax
0x1800d772b  jns     short loc_1800D7742
0x1800d772d  mov     r9d, eax; char *
0x1800d7730  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appcompat\\inventory\\so"...
0x1800d7737  mov     edx, 46Bh; void *
0x1800d773c  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800d7742  mov     rdi, [rbp+var_50]
0x1800d7746  mov     rax, [rdi]
0x1800d7749  mov     rbx, [rax+68h]
0x1800d774d  lea     rcx, [rbp+var_58]
0x1800d7751  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800d7756  lea     r8, [rbp+var_58]
0x1800d775a  mov     rdx, [r14]
0x1800d775d  mov     rcx, rdi
0x1800d7760  mov     rax, rbx
0x1800d7763  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d7768  mov     rcx, [rbp+38h]; this
0x1800d776c  test    eax, eax
0x1800d776e  jns     short loc_1800D7785
0x1800d7770  mov     r9d, eax; char *
0x1800d7773  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appcompat\\inventory\\so"...
0x1800d777a  mov     edx, 46Eh; void *
0x1800d777f  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800d7785  mov     [rbp+var_60], 0
0x1800d778c  mov     rcx, [rbp+var_58]
0x1800d7790  mov     rax, [rcx]
0x1800d7793  lea     rdx, [rbp+var_60]
0x1800d7797  mov     rax, [rax+38h]
0x1800d779b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d77a0  mov     rcx, [rbp+38h]; this
0x1800d77a4  test    eax, eax
0x1800d77a6  jns     short loc_1800D77BD
0x1800d77a8  mov     r9d, eax; char *
0x1800d77ab  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appcompat\\inventory\\so"...
0x1800d77b2  mov     edx, 472h; void *
0x1800d77b7  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800d77bd  xor     esi, esi
0x1800d77bf  cmp     [rbp+var_60], esi
0x1800d77c2  jbe     short loc_1800D7836
0x1800d77c4  mov     rdi, [rbp+var_58]
0x1800d77c8  mov     rax, [rdi]
0x1800d77cb  mov     rbx, [rax+30h]
0x1800d77cf  lea     rcx, [rbp+var_48]
0x1800d77d3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800d77d8  lea     r8, [rbp+var_48]
0x1800d77dc  mov     edx, esi
0x1800d77de  mov     rcx, rdi
0x1800d77e1  mov     rax, rbx
0x1800d77e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d77e9  mov     rcx, [rbp+38h]; this
0x1800d77ed  test    eax, eax
0x1800d77ef  js      loc_1800D7899
0x1800d77f5  mov     rdi, [rbp+var_48]
0x1800d77f9  mov     rax, [rdi]
0x1800d77fc  mov     rbx, [rax+50h]
0x1800d7800  lea     rcx, [rbp+var_40]
0x1800d7804  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800d7809  lea     rdx, [rbp+var_40]
0x1800d780d  mov     rcx, rdi
0x1800d7810  mov     rax, rbx
0x1800d7813  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d7818  mov     rcx, [rbp+38h]; this
0x1800d781c  test    eax, eax
0x1800d781e  js      short loc_1800D7884
0x1800d7820  mov     r8, r12
0x1800d7823  lea     rdx, [rbp+var_40]
0x1800d7827  mov     rcx, r15
0x1800d782a  call    ?GetEvidenceFromPackageSr@StoreAppFinder@@SAXAEBVConfigSettings@@AEBV?$ComPtr@UIPackage@StateRepository@Internal@Windows@@@WRL@Microsoft@@AEAV?$vector@VApplication@@V?$allocator@VApplication@@@std@@@std@@@Z; StoreAppFinder::GetEvidenceFromPackageSr(ConfigSettings const &,Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage> const &,std::vector<Application> &)
0x1800d782f  inc     esi
0x1800d7831  cmp     esi, [rbp+var_60]
0x1800d7834  jb      short loc_1800D77C4
0x1800d7836  lea     rcx, [rbp+var_50]
0x1800d783a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800d783f  nop
0x1800d7840  lea     rcx, [rbp+var_48]
0x1800d7844  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800d7849  nop
0x1800d784a  lea     rcx, [rbp+var_58]
0x1800d784e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800d7853  nop
0x1800d7854  lea     rcx, [rbp+var_40]
0x1800d7858  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800d785d  nop
0x1800d785e  mov     rcx, r14
0x1800d7861  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800d7866  mov     rcx, [rbp+var_10]
0x1800d786a  xor     rcx, rsp; StackCookie
0x1800d786d  call    __security_check_cookie
0x1800d7872  add     rsp, 80h
0x1800d7879  pop     r15
0x1800d787b  pop     r14
0x1800d787d  pop     r12
0x1800d787f  pop     rdi
0x1800d7880  pop     rsi
0x1800d7881  pop     rbx
0x1800d7882  pop     rbp
0x1800d7883  retn
0x1800d7884  mov     r9d, eax; char *
0x1800d7887  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appcompat\\inventory\\so"...
0x1800d788e  mov     edx, 47Bh; void *
0x1800d7893  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800d7899  mov     r9d, eax; char *
0x1800d789c  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appcompat\\inventory\\so"...
0x1800d78a3  mov     edx, 478h; void *
0x1800d78a8  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
