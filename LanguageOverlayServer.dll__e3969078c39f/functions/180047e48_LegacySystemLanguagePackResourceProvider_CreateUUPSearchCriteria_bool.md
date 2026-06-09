# LegacySystemLanguagePackResourceProvider::_CreateUUPSearchCriteria(bool *)

- ea: `0x180047e48`
- end: `0x18004826b`
- name: `?_CreateUUPSearchCriteria@LegacySystemLanguagePackResourceProvider@@CA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEA_N@Z`
- size: `1059`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180049d70`

## callees

- `0x180003a00`
- `0x180006b8c`
- `0x180012a98`
- `0x1800137bc`
- `0x180014ed0`
- `0x180033c30`
- `0x18003ff74`
- `0x180047e48`
- `0x180049794`
- `0x18006a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180047fc2`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180047fc2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004801d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800480ca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800480da`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004801d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800480ca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800480da`
- `OLEAUT32!__imp_SysAllocString` at `0x180048096`
- `OLEAUT32!__imp_SysAllocString` at `0x180048096`
- `ext-ms-win-deployment-productenumerator-l1-1-0!PE_CreateProductEnumerator` at `0x180047e89`
- `ext-ms-win-deployment-productenumerator-l1-1-0!PE_CreateProductEnumerator` at `0x180047e89`

## string_xrefs

- `0x180048170`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180048193`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\systemlanguageresourcesprovider.cpp`
- `0x1800481a8`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\systemlanguageresourcesprovider.cpp`
- `0x1800481bd`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\systemlanguageresourcesprovider.cpp`
- `0x1800481d2`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\systemlanguageresourcesprovider.cpp`
- `0x1800481e7`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\systemlanguageresourcesprovider.cpp`
- `0x1800481ff`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\systemlanguageresourcesprovider.cpp`
- `0x180048214`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\systemlanguageresourcesprovider.cpp`
- `0x18004822c`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\systemlanguageresourcesprovider.cpp`
- `0x180048244`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\systemlanguageresourcesprovider.cpp`
- `0x180048259`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\systemlanguageresourcesprovider.cpp`
- `0x18004806a`: `' and IsInstalled=0 and RebootRequired=1 and DeploymentAction=*)`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
BSTR *__fastcall LegacySystemLanguagePackResourceProvider::_CreateUUPSearchCriteria(BSTR *a1, _BYTE *a2)
{
  int v4; // eax
  int v5; // eax
  int v6; // eax
  unsigned int v7; // ebx
  int v8; // eax
  _QWORD *v9; // rcx
  __int64 *v10; // rcx
  __int64 v11; // rax
  int v12; // eax
  __int64 v13; // rax
  int v14; // eax
  void *v15; // rcx
  int updated; // eax
  wchar_t *v17; // rdx
  const OLECHAR *v18; // rcx
  BSTR v19; // rax
  const char *v20; // r9
  void *v21; // rcx
  _QWORD *v22; // rcx
  __int64 *v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // rcx
  unsigned int v27; // eax
  void *v28; // [rsp+30h] [rbp-39h] BYREF
  char v29; // [rsp+38h] [rbp-31h]
  BSTR *v30; // [rsp+40h] [rbp-29h]
  unsigned int v31; // [rsp+48h] [rbp-21h] BYREF
  __int64 *v32; // [rsp+50h] [rbp-19h] BYREF
  _QWORD *v33; // [rsp+58h] [rbp-11h] BYREF
  __int64 v34; // [rsp+60h] [rbp-9h] BYREF
  LPVOID pv; // [rsp+68h] [rbp-1h]
  LPVOID v36; // [rsp+70h] [rbp+7h] BYREF
  __int64 v37; // [rsp+78h] [rbp+Fh] BYREF
  OLECHAR *psz[2]; // [rsp+80h] [rbp+17h] BYREF
  __int128 v39; // [rsp+90h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v30 = a1;
  v37 = 0;
  v4 = PE_CreateProductEnumerator(&v37);
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1D5,
      (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\systemlanguageresourcesprovider.cpp",
      (const char *)(unsigned int)v4,
      0);
  v34 = 0;
  v5 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v37 + 24LL))(v37, &v34);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1D8,
      (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\systemlanguageresourcesprovider.cpp",
      (const char *)(unsigned int)v5,
      0);
  v31 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v34 + 24LL))(v34, &v31);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1DB,
      (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\systemlanguageresourcesprovider.cpp",
      (const char *)(unsigned int)v6,
      0);
  if ( !v31 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1DC,
      (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\systemlanguageresourcesprovider.cpp",
      (const char *)0x8000FFFFLL,
      0);
  *a2 = 1;
  v7 = 0;
  while ( 1 )
  {
    v32 = 0;
    v8 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 **))(*(_QWORD *)v34 + 32LL))(v34, v7, &v32);
    if ( v8 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1E4,
        (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\systemlanguageresourcesprovider.cpp",
        (const char *)(unsigned int)v8,
        0);
    v33 = 0;
    if ( (*(int (__fastcall **)(__int64 *, const wchar_t *, _QWORD **))(*v32 + 40))(v32, L"PrimaryOSProduct", &v33) >= 0 )
      break;
    v9 = v33;
    if ( v33 )
    {
      v33 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v9 + 16LL))(v9);
    }
    v10 = v32;
    if ( v32 )
    {
      v32 = 0;
      (*(void (__fastcall **)(__int64 *))(*v10 + 16))(v10);
    }
    if ( ++v7 >= v31 )
    {
      v27 = wil::verify_hresult<long>(2148469073LL);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x202,
        (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\systemlanguageresourcesprovider.cpp",
        (const char *)v27,
        0);
    }
  }
  v36 = 0;
  v11 = *v33;
  v36 = 0;
  v12 = (*(__int64 (__fastcall **)(_QWORD *, LPVOID *))(v11 + 32))(v33, &v36);
  if ( v12 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1EA,
      (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\systemlanguageresourcesprovider.cpp",
      (const char *)(unsigned int)v12,
      0);
  if ( !(unsigned int)_o__wtoi(v36) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1EB,
      (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\systemlanguageresourcesprovider.cpp",
      (const char *)0x8000FFFFLL,
      0);
  pv = 0;
  v13 = *v32;
  v28 = 0;
  v29 = 1;
  v14 = (*(__int64 (__fastcall **)(__int64 *, void **))(v13 + 24))(v32, &v28);
  if ( v14 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1EE,
      (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\systemlanguageresourcesprovider.cpp",
      (const char *)(unsigned int)v14,
      0);
  if ( v29 )
  {
    v15 = pv;
    pv = v28;
    if ( v15 )
      CoTaskMemFree(v15);
  }
  *(_OWORD *)psz = 0;
  v39 = 0;
  std::wstring::_Construct<1,unsigned short const *>((char **)psz, L"(Product='", 0xAu);
  std::wstring::operator+=(psz, pv);
  updated = IsUpdateCurrentVersionOnly(a2);
  if ( updated < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1F3,
      (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\systemlanguageresourcesprovider.cpp",
      (const char *)(unsigned int)updated,
      0);
  v17 = L"' and CurrentVersionOnly=1 and DeploymentAction=*)";
  if ( !*a2 )
    v17 = L"' and IsInstalled=0 and RebootRequired=1 and DeploymentAction=*)";
  std::wstring::operator+=(psz, v17);
  v18 = (const OLECHAR *)psz;
  if ( *((_QWORD *)&v39 + 1) > 7u )
    v18 = psz[0];
  v19 = SysAllocString(v18);
  *a1 = v19;
  if ( !v19 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x15F3,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v20);
  std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>::~basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>((char **)psz);
  v21 = pv;
  pv = 0;
  if ( v21 )
    CoTaskMemFree(v21);
  if ( v36 )
    CoTaskMemFree(v36);
  v22 = v33;
  if ( v33 )
  {
    v33 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v22 + 16LL))(v22);
  }
  v23 = v32;
  if ( v32 )
  {
    v32 = 0;
    (*(void (__fastcall **)(__int64 *))(*v23 + 16))(v23);
  }
  v24 = v34;
  if ( v34 )
  {
    v34 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  }
  v25 = v37;
  if ( v37 )
  {
    v37 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  }
  return a1;
}

```

## disassembly

```asm
0x180047e48  mov     [rsp-8+arg_10], rbx
0x180047e4d  mov     [rsp-8+arg_18], rsi
0x180047e52  push    rbp
0x180047e53  push    rdi
0x180047e54  push    r14
0x180047e56  lea     rbp, [rsp-47h]
0x180047e5b  sub     rsp, 0B0h
0x180047e62  mov     rax, cs:__security_cookie
0x180047e69  xor     rax, rsp
0x180047e6c  mov     [rbp+57h+var_20], rax
0x180047e70  mov     rsi, rdx
0x180047e73  mov     rdi, rcx
0x180047e76  mov     [rbp+57h+var_80], rcx
0x180047e7a  xor     r14d, r14d
0x180047e7d  mov     [rbp+57h+var_A0], r14d
0x180047e81  mov     [rbp+57h+var_48], r14
0x180047e85  lea     rcx, [rbp+57h+var_48]
0x180047e89  call    cs:__imp_PE_CreateProductEnumerator
0x180047e8f  mov     rcx, [rbp+5Fh]; this
0x180047e93  test    eax, eax
0x180047e95  js      loc_1800481BA
0x180047e9b  mov     [rbp+57h+var_60], r14
0x180047e9f  mov     rcx, [rbp+57h+var_48]
0x180047ea3  mov     rax, [rcx]
0x180047ea6  lea     rdx, [rbp+57h+var_60]
0x180047eaa  mov     rax, [rax+18h]
0x180047eae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047eb3  mov     rcx, [rbp+5Fh]; this
0x180047eb7  test    eax, eax
0x180047eb9  js      loc_1800481CF
0x180047ebf  mov     [rbp+57h+var_78], r14d
0x180047ec3  mov     rcx, [rbp+57h+var_60]
0x180047ec7  mov     rax, [rcx]
0x180047eca  lea     rdx, [rbp+57h+var_78]
0x180047ece  mov     rax, [rax+18h]
0x180047ed2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047ed7  mov     rcx, [rbp+5Fh]; this
0x180047edb  test    eax, eax
0x180047edd  js      loc_1800481E4
0x180047ee3  mov     edx, [rbp+57h+var_78]
0x180047ee6  test    edx, edx
0x180047ee8  setz    al
0x180047eeb  mov     rcx, [rbp+5Fh]; this
0x180047eef  test    al, al
0x180047ef1  jnz     loc_1800481F9
0x180047ef7  mov     byte ptr [rsi], 1
0x180047efa  mov     ebx, r14d
0x180047efd  test    edx, edx
0x180047eff  jz      loc_180048182
0x180047f05  mov     [rbp+57h+var_70], r14
0x180047f09  mov     rcx, [rbp+57h+var_60]
0x180047f0d  mov     rax, [rcx]
0x180047f10  lea     r8, [rbp+57h+var_70]
0x180047f14  mov     edx, ebx
0x180047f16  mov     rax, [rax+20h]
0x180047f1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047f1f  mov     rcx, [rbp+5Fh]; this
0x180047f23  test    eax, eax
0x180047f25  js      loc_1800481A5
0x180047f2b  mov     [rbp+57h+var_68], r14
0x180047f2f  mov     rcx, [rbp+57h+var_70]
0x180047f33  mov     rax, [rcx]
0x180047f36  lea     r8, [rbp+57h+var_68]
0x180047f3a  lea     rdx, aPrimaryosprodu; "PrimaryOSProduct"
0x180047f41  mov     rax, [rax+28h]
0x180047f45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047f4a  test    eax, eax
0x180047f4c  jns     short loc_180047F92
0x180047f4e  mov     rcx, [rbp+57h+var_68]
0x180047f52  test    rcx, rcx
0x180047f55  jz      short loc_180047F68
0x180047f57  mov     [rbp+57h+var_68], r14
0x180047f5b  mov     rax, [rcx]
0x180047f5e  mov     rax, [rax+10h]
0x180047f62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047f67  nop
0x180047f68  mov     rcx, [rbp+57h+var_70]
0x180047f6c  test    rcx, rcx
0x180047f6f  jz      short loc_180047F82
0x180047f71  mov     [rbp+57h+var_70], r14
0x180047f75  mov     rax, [rcx]
0x180047f78  mov     rax, [rax+10h]
0x180047f7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047f81  nop
0x180047f82  inc     ebx
0x180047f84  cmp     ebx, [rbp+57h+var_78]
0x180047f87  jnb     loc_180048182
0x180047f8d  jmp     loc_180047F05
0x180047f92  mov     [rbp+57h+var_50], r14
0x180047f96  mov     rcx, [rbp+57h+var_68]
0x180047f9a  mov     rax, [rcx]
0x180047f9d  mov     [rbp+57h+var_50], r14
0x180047fa1  lea     rdx, [rbp+57h+var_50]
0x180047fa5  mov     rax, [rax+20h]
0x180047fa9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047fae  mov     rcx, [rbp+5Fh]; this
0x180047fb2  test    eax, eax
0x180047fb4  js      loc_180048211
0x180047fba  mov     rbx, [rbp+5Fh]
0x180047fbe  mov     rcx, [rbp+57h+var_50]
0x180047fc2  call    cs:__imp__o__wtoi
0x180047fc8  test    eax, eax
0x180047fca  jz      loc_180048226
0x180047fd0  mov     [rbp+57h+pv], r14
0x180047fd4  mov     rcx, [rbp+57h+var_70]
0x180047fd8  mov     rax, [rcx]
0x180047fdb  lea     rdx, [rbp+57h+pv]
0x180047fdf  mov     [rbp+57h+var_98], rdx
0x180047fe3  mov     [rbp+57h+var_90], r14
0x180047fe7  mov     [rbp+57h+var_88], 1
0x180047feb  lea     rdx, [rbp+57h+var_90]
0x180047fef  mov     rax, [rax+18h]
0x180047ff3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047ff8  mov     rcx, [rbp+5Fh]; this
0x180047ffc  test    eax, eax
0x180047ffe  js      loc_180048241
0x180048004  cmp     [rbp+57h+var_88], r14b
0x180048008  jz      short loc_180048023
0x18004800a  mov     rdx, [rbp+57h+var_98]
0x18004800e  mov     rcx, [rdx]; pv
0x180048011  mov     rax, [rbp+57h+var_90]
0x180048015  mov     [rdx], rax
0x180048018  test    rcx, rcx
0x18004801b  jz      short loc_180048023
0x18004801d  call    cs:__imp_CoTaskMemFree
0x180048023  xorps   xmm0, xmm0
0x180048026  movups  xmmword ptr [rbp+57h+psz], xmm0
0x18004802a  xorps   xmm1, xmm1
0x18004802d  movdqu  [rbp+57h+var_30], xmm1
0x180048032  mov     r8d, 0Ah
0x180048038  lea     rdx, aProduct; "(Product='"
0x18004803f  lea     rcx, [rbp+57h+psz]
0x180048043  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180048048  nop
0x180048049  mov     rdx, [rbp+57h+pv]; void *
0x18004804d  lea     rcx, [rbp+57h+psz]; Src
0x180048051  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator+=(ushort const * const)
0x180048056  mov     rcx, rsi
0x180048059  call    _IsUpdateCurrentVersionOnly
0x18004805e  mov     rcx, [rbp+5Fh]; this
0x180048062  test    eax, eax
0x180048064  js      loc_180048256
0x18004806a  lea     rax, aAndIsinstalled; "' and IsInstalled=0 and RebootRequired="...
0x180048071  lea     rdx, aAndCurrentvers; "' and CurrentVersionOnly=1 and Deployme"...
0x180048078  cmp     [rsi], r14b
0x18004807b  cmovz   rdx, rax; void *
0x18004807f  lea     rcx, [rbp+57h+psz]; Src
0x180048083  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator+=(ushort const * const)
0x180048088  lea     rcx, [rbp+57h+psz]
0x18004808c  cmp     qword ptr [rbp+57h+var_30+8], 7
0x180048091  cmova   rcx, [rbp+57h+psz]; psz
0x180048096  call    cs:__imp_SysAllocString
0x18004809c  mov     [rdi], rax
0x18004809f  mov     [rbp+57h+var_A0], 2
0x1800480a6  mov     rcx, [rbp+5Fh]; this
0x1800480aa  test    rax, rax
0x1800480ad  jz      loc_180048170
0x1800480b3  lea     rcx, [rbp+57h+psz]; void *
0x1800480b7  call    ??1?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@QEAA@XZ; std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>::~basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>(void)
0x1800480bc  nop
0x1800480bd  mov     rcx, [rbp+57h+pv]; pv
0x1800480c1  mov     [rbp+57h+pv], r14
0x1800480c5  test    rcx, rcx
0x1800480c8  jz      short loc_1800480D1
0x1800480ca  call    cs:__imp_CoTaskMemFree
0x1800480d0  nop
0x1800480d1  mov     rcx, [rbp+57h+var_50]; pv
0x1800480d5  test    rcx, rcx
0x1800480d8  jz      short loc_1800480E1
0x1800480da  call    cs:__imp_CoTaskMemFree
0x1800480e0  nop
0x1800480e1  mov     rcx, [rbp+57h+var_68]
0x1800480e5  test    rcx, rcx
0x1800480e8  jz      short loc_1800480FB
0x1800480ea  mov     [rbp+57h+var_68], r14
0x1800480ee  mov     rax, [rcx]
0x1800480f1  mov     rax, [rax+10h]
0x1800480f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800480fa  nop
0x1800480fb  mov     rcx, [rbp+57h+var_70]
0x1800480ff  test    rcx, rcx
0x180048102  jz      short loc_180048115
0x180048104  mov     [rbp+57h+var_70], r14
0x180048108  mov     rax, [rcx]
0x18004810b  mov     rax, [rax+10h]
0x18004810f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048114  nop
0x180048115  mov     rcx, [rbp+57h+var_60]
0x180048119  test    rcx, rcx
0x18004811c  jz      short loc_18004812F
0x18004811e  mov     [rbp+57h+var_60], r14
0x180048122  mov     rax, [rcx]
0x180048125  mov     rax, [rax+10h]
0x180048129  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004812e  nop
0x18004812f  mov     rcx, [rbp+57h+var_48]
0x180048133  test    rcx, rcx
0x180048136  jz      short loc_180048149
0x180048138  mov     [rbp+57h+var_48], r14
0x18004813c  mov     rdx, [rcx]
0x18004813f  mov     rax, [rdx+10h]
0x180048143  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048148  nop
0x180048149  mov     rax, rdi
0x18004814c  mov     rcx, [rbp+57h+var_20]
0x180048150  xor     rcx, rsp; StackCookie
0x180048153  call    __security_check_cookie
0x180048158  lea     r11, [rsp+0C0h+var_10]
0x180048160  mov     rbx, [r11+30h]
0x180048164  mov     rsi, [r11+38h]
0x180048168  mov     rsp, r11
0x18004816b  pop     r14
0x18004816d  pop     rdi
0x18004816e  pop     rbp
0x18004816f  retn
0x180048170  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180048177  mov     edx, 15F3h; void *
0x18004817c  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x180048182  mov     ecx, 800F0951h
0x180048187  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18004818c  mov     r9d, eax; char *
0x18004818f  mov     rcx, [rbp+5Fh]; this
0x180048193  lea     r8, aOnecoreBaseLan_26; "onecore\\base\\languageoverlay\\service"...
0x18004819a  mov     edx, 202h; void *
0x18004819f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800481a5  mov     r9d, eax; char *
0x1800481a8  lea     r8, aOnecoreBaseLan_26; "onecore\\base\\languageoverlay\\service"...
0x1800481af  mov     edx, 1E4h; void *
0x1800481b4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800481ba  mov     r9d, eax; char *
0x1800481bd  lea     r8, aOnecoreBaseLan_26; "onecore\\base\\languageoverlay\\service"...
0x1800481c4  mov     edx, 1D5h; void *
0x1800481c9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800481cf  mov     r9d, eax; char *
0x1800481d2  lea     r8, aOnecoreBaseLan_26; "onecore\\base\\languageoverlay\\service"...
0x1800481d9  mov     edx, 1D8h; void *
0x1800481de  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800481e4  mov     r9d, eax; char *
0x1800481e7  lea     r8, aOnecoreBaseLan_26; "onecore\\base\\languageoverlay\\service"...
0x1800481ee  mov     edx, 1DBh; void *
0x1800481f3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800481f9  mov     r9d, 8000FFFFh; char *
0x1800481ff  lea     r8, aOnecoreBaseLan_26; "onecore\\base\\languageoverlay\\service"...
0x180048206  mov     edx, 1DCh; void *
0x18004820b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180048211  mov     r9d, eax; char *
0x180048214  lea     r8, aOnecoreBaseLan_26; "onecore\\base\\languageoverlay\\service"...
0x18004821b  mov     edx, 1EAh; void *
0x180048220  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180048226  mov     r9d, 8000FFFFh; char *
0x18004822c  lea     r8, aOnecoreBaseLan_26; "onecore\\base\\languageoverlay\\service"...
0x180048233  mov     edx, 1EBh; void *
0x180048238  mov     rcx, rbx; this
0x18004823b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180048241  mov     r9d, eax; char *
0x180048244  lea     r8, aOnecoreBaseLan_26; "onecore\\base\\languageoverlay\\service"...
0x18004824b  mov     edx, 1EEh; void *
0x180048250  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180048256  mov     r9d, eax; char *
0x180048259  lea     r8, aOnecoreBaseLan_26; "onecore\\base\\languageoverlay\\service"...
0x180048260  mov     edx, 1F3h; void *
0x180048265  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
