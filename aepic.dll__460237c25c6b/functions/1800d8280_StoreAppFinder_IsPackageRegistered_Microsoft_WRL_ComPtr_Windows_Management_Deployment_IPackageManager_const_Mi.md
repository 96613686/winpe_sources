# StoreAppFinder::IsPackageRegistered(Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager> const &,Microsoft::WRL::ComPtr<Windows::ApplicationModel::IPackage> const &)

- ea: `0x1800d8280`
- end: `0x1800d853a`
- name: `?IsPackageRegistered@StoreAppFinder@@SA_NAEBV?$ComPtr@UIPackageManager@Deployment@Management@Windows@@@WRL@Microsoft@@AEBV?$ComPtr@UIPackage@ApplicationModel@Windows@@@34@@Z`
- size: `698`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x1800d5ab4`

## callees

- `0x180005890`
- `0x18000a2d4`
- `0x18001082c`
- `0x18001c5f0`
- `0x1800c97f0`
- `0x1800d8280`
- `0x1800dac8c`
- `0x1800eb010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800d8497`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800d8497`

## string_xrefs

- `0x1800d82e1`: `onecore\base\appcompat\inventory\software\inv\lib\storeappfinder.cpp`
- `0x1800d831a`: `onecore\base\appcompat\inventory\software\inv\lib\storeappfinder.cpp`
- `0x1800d8356`: `onecore\base\appcompat\inventory\software\inv\lib\storeappfinder.cpp`
- `0x1800d838f`: `onecore\base\appcompat\inventory\software\inv\lib\storeappfinder.cpp`
- `0x1800d83c4`: `onecore\base\appcompat\inventory\software\inv\lib\storeappfinder.cpp`
- `0x1800d8464`: `onecore\base\appcompat\inventory\software\inv\lib\storeappfinder.cpp`
- `0x1800d8513`: `onecore\base\appcompat\inventory\software\inv\lib\storeappfinder.cpp`
- `0x1800d8528`: `onecore\base\appcompat\inventory\software\inv\lib\storeappfinder.cpp`

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
  __int64 v24; // [rsp+48h] [rbp-38h] BYREF
  LPCWSTR lpFileName[4]; // [rsp+50h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]

  v22 = 0;
  v4 = *a2;
  v5 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)*a2 + 48LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v22);
  v6 = v5(v4, &v22);
  if ( v6 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x33F,
      (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeappfinder.cpp",
      (const char *)(unsigned int)v6,
      v18);
  v24 = 0;
  v7 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v22 + 96LL))(v22, &v24);
  if ( v7 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x343,
      (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeappfinder.cpp",
      (const char *)(unsigned int)v7,
      v18);
  v23 = 0;
  v8 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64 *))(*(_QWORD *)*a1 + 120LL))(*a1, v24, &v23);
  if ( v8 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x347,
      (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeappfinder.cpp",
      (const char *)(unsigned int)v8,
      v18);
  v20 = 0;
  v9 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v23 + 48LL))(v23, &v20);
  if ( v9 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x34B,
      (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeappfinder.cpp",
      (const char *)(unsigned int)v9,
      v18);
  LOBYTE(v18) = 0;
  v10 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v20 + 56LL))(v20, &v18);
  if ( v10 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x350,
      (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeappfinder.cpp",
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
        (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeappfinder.cpp",
        (const char *)(unsigned int)v12,
        v18);
    v19 = 0;
    v13 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v21 + 56LL))(v21, &v19);
    if ( v13 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x35A,
        (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeappfinder.cpp",
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
      std::wstring::_Tidy_deallocate(lpFileName);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v21);
      break;
    }
    v14 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v20 + 64LL))(v20, &v18);
    if ( v14 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x365,
        (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\storeappfinder.cpp",
        (const char *)(unsigned int)v14,
        v18);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v21);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23);
  Windows::Internal::String::~String((Windows::Internal::String *)&v24);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v22);
  return v11;
}

```

## disassembly

```asm
0x1800d8280  mov     [rsp-18h+arg_10], rbx
0x1800d8285  mov     [rsp-18h+arg_18], rsi
0x1800d828a  push    rbp
0x1800d828b  push    rdi
0x1800d828c  push    r14
0x1800d828e  mov     rbp, rsp
0x1800d8291  sub     rsp, 80h
0x1800d8298  mov     rax, cs:__security_cookie
0x1800d829f  xor     rax, rsp
0x1800d82a2  mov     [rbp+var_10], rax
0x1800d82a6  mov     rsi, rdx
0x1800d82a9  mov     r14, rcx
0x1800d82ac  mov     [rbp+var_48], 0
0x1800d82b4  mov     rdi, [rdx]
0x1800d82b7  mov     rax, [rdi]
0x1800d82ba  mov     rbx, [rax+30h]
0x1800d82be  lea     rcx, [rbp+var_48]
0x1800d82c2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800d82c7  lea     rdx, [rbp+var_48]
0x1800d82cb  mov     rcx, rdi
0x1800d82ce  mov     rax, rbx
0x1800d82d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d82d6  mov     rcx, [rbp+18h]; this
0x1800d82da  test    eax, eax
0x1800d82dc  jns     short loc_1800D82F3
0x1800d82de  mov     r9d, eax; char *
0x1800d82e1  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appcompat\\inventory\\so"...
0x1800d82e8  mov     edx, 33Fh; void *
0x1800d82ed  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800d82f3  mov     [rbp+var_38], 0
0x1800d82fb  mov     rcx, [rbp+var_48]
0x1800d82ff  mov     rax, [rcx]
0x1800d8302  lea     rdx, [rbp+var_38]
0x1800d8306  mov     rax, [rax+60h]
0x1800d830a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d830f  mov     rcx, [rbp+18h]; this
0x1800d8313  test    eax, eax
0x1800d8315  jns     short loc_1800D832C
0x1800d8317  mov     r9d, eax; char *
0x1800d831a  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appcompat\\inventory\\so"...
0x1800d8321  mov     edx, 343h; void *
0x1800d8326  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800d832c  mov     [rbp+var_40], 0
0x1800d8334  mov     rcx, [r14]
0x1800d8337  mov     rax, [rcx]
0x1800d833a  lea     r8, [rbp+var_40]
0x1800d833e  mov     rdx, [rbp+var_38]
0x1800d8342  mov     rax, [rax+78h]
0x1800d8346  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d834b  mov     rcx, [rbp+18h]; this
0x1800d834f  test    eax, eax
0x1800d8351  jns     short loc_1800D8368
0x1800d8353  mov     r9d, eax; char *
0x1800d8356  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appcompat\\inventory\\so"...
0x1800d835d  mov     edx, 347h; void *
0x1800d8362  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800d8368  mov     [rbp+var_58], 0
0x1800d8370  mov     rcx, [rbp+var_40]
0x1800d8374  mov     rax, [rcx]
0x1800d8377  lea     rdx, [rbp+var_58]
0x1800d837b  mov     rax, [rax+30h]
0x1800d837f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d8384  mov     rcx, [rbp+18h]; this
0x1800d8388  test    eax, eax
0x1800d838a  jns     short loc_1800D83A1
0x1800d838c  mov     r9d, eax; char *
0x1800d838f  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appcompat\\inventory\\so"...
0x1800d8396  mov     edx, 34Bh; void *
0x1800d839b  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800d83a1  mov     byte ptr [rbp+var_60], 0
0x1800d83a5  mov     rcx, [rbp+var_58]
0x1800d83a9  mov     rax, [rcx]
0x1800d83ac  lea     rdx, [rbp+var_60]
0x1800d83b0  mov     rax, [rax+38h]
0x1800d83b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d83b9  mov     rcx, [rbp+18h]; this
0x1800d83bd  test    eax, eax
0x1800d83bf  jns     short loc_1800D83D6
0x1800d83c1  mov     r9d, eax; char *
0x1800d83c4  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appcompat\\inventory\\so"...
0x1800d83cb  mov     edx, 350h; void *
0x1800d83d0  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800d83d6  xor     bl, bl
0x1800d83d8  cmp     byte ptr [rbp+var_60], 0
0x1800d83dc  jz      loc_1800D84C3
0x1800d83e2  mov     [rbp+var_50], 0
0x1800d83ea  mov     rcx, [rbp+var_58]
0x1800d83ee  mov     rax, [rcx]
0x1800d83f1  lea     rdx, [rbp+var_50]
0x1800d83f5  mov     rax, [rax+30h]
0x1800d83f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d83fe  mov     rcx, [rbp+18h]; this
0x1800d8402  test    eax, eax
0x1800d8404  js      loc_1800D8525
0x1800d840a  mov     [rbp+var_5C], 0
0x1800d8411  mov     rcx, [rbp+var_50]
0x1800d8415  mov     rax, [rcx]
0x1800d8418  lea     rdx, [rbp+var_5C]
0x1800d841c  mov     rax, [rax+38h]
0x1800d8420  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d8425  mov     rcx, [rbp+18h]; this
0x1800d8429  test    eax, eax
0x1800d842b  js      loc_1800D8510
0x1800d8431  cmp     [rbp+var_5C], 2
0x1800d8435  jz      short loc_1800D8476
0x1800d8437  mov     rcx, [rbp+var_58]
0x1800d843b  mov     rax, [rcx]
0x1800d843e  lea     rdx, [rbp+var_60]
0x1800d8442  mov     rax, [rax+40h]
0x1800d8446  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d844b  mov     rcx, [rbp+18h]; this
0x1800d844f  test    eax, eax
0x1800d8451  js      short loc_1800D8461
0x1800d8453  lea     rcx, [rbp+var_50]
0x1800d8457  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800d845c  jmp     loc_1800D83D8
0x1800d8461  mov     r9d, eax; char *
0x1800d8464  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appcompat\\inventory\\so"...
0x1800d846b  mov     edx, 365h; void *
0x1800d8470  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800d8476  mov     rdx, rsi
0x1800d8479  lea     rcx, [rbp+lpFileName]
0x1800d847d  call    ?GetStoreAppInstallLocationFromPackage@StoreApplication@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$ComPtr@UIPackage@ApplicationModel@Windows@@@WRL@Microsoft@@@Z; StoreApplication::GetStoreAppInstallLocationFromPackage(Microsoft::WRL::ComPtr<Windows::ApplicationModel::IPackage> const &)
0x1800d8482  cmp     [rbp+var_20], 0
0x1800d8487  jbe     short loc_1800D84AF
0x1800d8489  lea     rcx, [rbp+lpFileName]
0x1800d848d  cmp     [rbp+var_18], 7
0x1800d8492  cmova   rcx, [rbp+lpFileName]; lpFileName
0x1800d8497  call    cs:__imp_GetFileAttributesW
0x1800d849d  cmp     eax, 0FFFFFFFFh
0x1800d84a0  jz      short loc_1800D84AF
0x1800d84a2  test    al, 10h
0x1800d84a4  movzx   ebx, bl
0x1800d84a7  mov     eax, 1
0x1800d84ac  cmovnz  ebx, eax
0x1800d84af  lea     rcx, [rbp+lpFileName]
0x1800d84b3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800d84b8  nop
0x1800d84b9  lea     rcx, [rbp+var_50]
0x1800d84bd  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800d84c2  nop
0x1800d84c3  lea     rcx, [rbp+var_58]
0x1800d84c7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800d84cc  nop
0x1800d84cd  lea     rcx, [rbp+var_40]
0x1800d84d1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800d84d6  nop
0x1800d84d7  lea     rcx, [rbp+var_38]; this
0x1800d84db  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800d84e0  nop
0x1800d84e1  lea     rcx, [rbp+var_48]
0x1800d84e5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800d84ea  mov     al, bl
0x1800d84ec  mov     rcx, [rbp+var_10]
0x1800d84f0  xor     rcx, rsp; StackCookie
0x1800d84f3  call    __security_check_cookie
0x1800d84f8  lea     r11, [rsp+80h+var_s0]
0x1800d8500  mov     rbx, [r11+30h]
0x1800d8504  mov     rsi, [r11+38h]
0x1800d8508  mov     rsp, r11
0x1800d850b  pop     r14
0x1800d850d  pop     rdi
0x1800d850e  pop     rbp
0x1800d850f  retn
0x1800d8510  mov     r9d, eax; char *
0x1800d8513  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appcompat\\inventory\\so"...
0x1800d851a  mov     edx, 35Ah; void *
0x1800d851f  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800d8525  mov     r9d, eax; char *
0x1800d8528  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appcompat\\inventory\\so"...
0x1800d852f  mov     edx, 356h; void *
0x1800d8534  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
