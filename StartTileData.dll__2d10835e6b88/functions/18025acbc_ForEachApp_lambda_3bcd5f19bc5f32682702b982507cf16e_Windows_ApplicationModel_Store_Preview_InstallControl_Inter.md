# ForEachApp<_lambda_3bcd5f19bc5f32682702b982507cf16e_>(Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppData *,_lambda_3bcd5f19bc5f32682702b982507cf16e_)

- ea: `0x18025acbc`
- end: `0x18025aecd`
- name: `??$ForEachApp@V_lambda_3bcd5f19bc5f32682702b982507cf16e_@@@@YAXPEAUIAppData@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@V_lambda_3bcd5f19bc5f32682702b982507cf16e_@@@Z`
- size: `529`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1801749d0`

## callees

- `0x18001dac0`
- `0x18002dde0`
- `0x18007ae80`
- `0x18016dad4`
- `0x180186f7c`
- `0x180201e50`
- `0x18025acbc`
- `0x18025bbdc`
- `0x18025c4cc`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18025ad6d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18025adc9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18025ae5d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18025ae74`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18025ad6d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18025adc9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18025ae5d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18025ae74`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18025adfb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18025ae0a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18025adfb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18025ae0a`

## string_xrefs

- `0x18025ad16`: `shellcommon\shell\tiles\curatedtilecollections\storeeventlistener\lib\storeeventlistenerimpl.cpp`
- `0x18025ad47`: `shellcommon\shell\tiles\curatedtilecollections\storeeventlistener\lib\storeeventlistenerimpl.cpp`
- `0x18025ad95`: `shellcommon\shell\tiles\curatedtilecollections\storeeventlistener\lib\storeeventlistenerimpl.cpp`
- `0x18025aebb`: `shellcommon\shell\tiles\curatedtilecollections\storeeventlistener\lib\storeeventlistenerimpl.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall ForEachApp<_lambda_3bcd5f19bc5f32682702b982507cf16e_>(
        __int64 *a1,
        _lambda_3bcd5f19bc5f32682702b982507cf16e_ *a2)
{
  __int64 v4; // rax
  int v5; // eax
  int v6; // eax
  __int64 (__fastcall *v7)(__int64 *, HSTRING *); // rbx
  int v8; // eax
  unsigned int i; // r14d
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, _QWORD, HSTRING *); // rbx
  int v12; // eax
  PCWSTR StringRawBuffer; // rbx
  PCWSTR v14; // rax
  _QWORD *v15; // rdx
  __int64 v16; // rdx
  unsigned int v17; // [rsp+20h] [rbp-60h] BYREF
  HSTRING v18; // [rsp+28h] [rbp-58h] BYREF
  HSTRING string; // [rsp+30h] [rbp-50h] BYREF
  __int64 v20; // [rsp+38h] [rbp-48h] BYREF
  _QWORD v21[2]; // [rsp+40h] [rbp-40h] BYREF
  _QWORD v22[4]; // [rsp+50h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]

  v21[1] = a2;
  v17 = 0;
  v4 = *a1;
  v20 = 0;
  v5 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v4 + 96))(a1, &v20);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x4A,
      (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\storeeventlistener\\lib\\storeeventlistenerimpl.cpp",
      (const char *)(unsigned int)v5,
      v17);
  v6 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v20 + 56LL))(v20, &v17);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x4B,
      (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\storeeventlistener\\lib\\storeeventlistenerimpl.cpp",
      (const char *)(unsigned int)v6,
      v17);
  v18 = 0;
  v7 = *(__int64 (__fastcall **)(__int64 *, HSTRING *))(*a1 + 208);
  WindowsDeleteString(0);
  v18 = 0;
  v8 = v7(a1, &v18);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x53,
      (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\storeeventlistener\\lib\\storeeventlistenerimpl.cpp",
      (const char *)(unsigned int)v8,
      v17);
  for ( i = 0; i < v17; ++i )
  {
    string = 0;
    v10 = v20;
    v11 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)v20 + 48LL);
    WindowsDeleteString(0);
    string = 0;
    v12 = v11(v10, i, &string);
    if ( v12 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x58,
        (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\storeeventlistener\\lib\\storeeventlistenerimpl.cpp",
        (const char *)(unsigned int)v12,
        v17);
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v14 = WindowsGetStringRawBuffer(v18, 0);
    CreateAumid(v22, v14, StringRawBuffer);
    v15 = v22;
    if ( v22[3] > 7u )
      v15 = (_QWORD *)v22[0];
    WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::AumidToUti(v21, v15);
    _lambda_3bcd5f19bc5f32682702b982507cf16e_::operator()(a2, v16, v21[0]);
    wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(v21);
    std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(v22);
    WindowsDeleteString(string);
  }
  WindowsDeleteString(v18);
  v18 = 0;
  wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v20);
  _lambda_3bcd5f19bc5f32682702b982507cf16e_::~_lambda_3bcd5f19bc5f32682702b982507cf16e_(a2);
}

```

## disassembly

```asm
0x18025acbc  mov     [rsp-18h+arg_10], rbx
0x18025acc1  mov     [rsp-18h+arg_18], rsi
0x18025acc6  push    rbp
0x18025acc7  push    rdi
0x18025acc8  push    r14
0x18025acca  mov     rbp, rsp
0x18025accd  sub     rsp, 80h
0x18025acd4  mov     rax, cs:__security_cookie
0x18025acdb  xor     rax, rsp
0x18025acde  mov     [rbp+var_10], rax
0x18025ace2  mov     rsi, rdx
0x18025ace5  mov     rdi, rcx
0x18025ace8  mov     [rbp+var_38], rdx
0x18025acec  mov     [rbp+var_60], 0
0x18025acf3  mov     rax, [rcx]
0x18025acf6  mov     [rbp+var_48], 0
0x18025acfe  lea     rdx, [rbp+var_48]
0x18025ad02  mov     rax, [rax+60h]
0x18025ad06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18025ad0b  mov     rcx, [rbp+18h]; this
0x18025ad0f  test    eax, eax
0x18025ad11  jns     short loc_18025AD28
0x18025ad13  mov     r9d, eax; char *
0x18025ad16  lea     r8, aShellcommonShe_106; "shellcommon\\shell\\tiles\\curatedtilec"...
0x18025ad1d  mov     edx, 4Ah ; 'J'; void *
0x18025ad22  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18025ad28  mov     rcx, [rbp+var_48]
0x18025ad2c  mov     rax, [rcx]
0x18025ad2f  lea     rdx, [rbp+var_60]
0x18025ad33  mov     rax, [rax+38h]
0x18025ad37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18025ad3c  mov     rcx, [rbp+18h]; this
0x18025ad40  test    eax, eax
0x18025ad42  jns     short loc_18025AD59
0x18025ad44  mov     r9d, eax; char *
0x18025ad47  lea     r8, aShellcommonShe_106; "shellcommon\\shell\\tiles\\curatedtilec"...
0x18025ad4e  mov     edx, 4Bh ; 'K'; void *
0x18025ad53  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18025ad59  mov     [rbp+var_58], 0
0x18025ad61  mov     rax, [rdi]
0x18025ad64  mov     rbx, [rax+0D0h]
0x18025ad6b  xor     ecx, ecx; string
0x18025ad6d  call    cs:__imp_WindowsDeleteString
0x18025ad73  mov     [rbp+var_58], 0
0x18025ad7b  lea     rdx, [rbp+var_58]
0x18025ad7f  mov     rcx, rdi
0x18025ad82  mov     rax, rbx
0x18025ad85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18025ad8a  mov     rcx, [rbp+18h]; this
0x18025ad8e  test    eax, eax
0x18025ad90  jns     short loc_18025ADA7
0x18025ad92  mov     r9d, eax; char *
0x18025ad95  lea     r8, aShellcommonShe_106; "shellcommon\\shell\\tiles\\curatedtilec"...
0x18025ad9c  mov     edx, 53h ; 'S'; void *
0x18025ada1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18025ada7  xor     r14d, r14d
0x18025adaa  cmp     [rbp+var_60], r14d
0x18025adae  jbe     loc_18025AE70
0x18025adb4  mov     [rbp+string], 0
0x18025adbc  mov     rdi, [rbp+var_48]
0x18025adc0  mov     rax, [rdi]
0x18025adc3  mov     rbx, [rax+30h]
0x18025adc7  xor     ecx, ecx; string
0x18025adc9  call    cs:__imp_WindowsDeleteString
0x18025adcf  mov     [rbp+string], 0
0x18025add7  lea     r8, [rbp+string]
0x18025addb  mov     edx, r14d
0x18025adde  mov     rcx, rdi
0x18025ade1  mov     rax, rbx
0x18025ade4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18025ade9  mov     rcx, [rbp+18h]; this
0x18025aded  test    eax, eax
0x18025adef  js      loc_18025AEB8
0x18025adf5  xor     edx, edx; length
0x18025adf7  mov     rcx, [rbp+string]; string
0x18025adfb  call    cs:__imp_WindowsGetStringRawBuffer
0x18025ae01  mov     rbx, rax
0x18025ae04  xor     edx, edx; length
0x18025ae06  mov     rcx, [rbp+var_58]; string
0x18025ae0a  call    cs:__imp_WindowsGetStringRawBuffer
0x18025ae10  mov     r8, rbx
0x18025ae13  mov     rdx, rax
0x18025ae16  lea     rcx, [rbp+var_30]
0x18025ae1a  call    ?CreateAumid@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG0@Z; CreateAumid(ushort const *,ushort const *)
0x18025ae1f  nop
0x18025ae20  lea     rdx, [rbp+var_30]
0x18025ae24  cmp     [rbp+var_18], 7
0x18025ae29  cmova   rdx, [rbp+var_30]
0x18025ae2e  lea     rcx, [rbp+var_40]
0x18025ae32  call    WindowsInternal__Shell__UnifiedTile__CuratedTileCollections__AumidToUti
0x18025ae37  nop
0x18025ae38  mov     r8, [rbp+var_40]
0x18025ae3c  mov     rcx, rsi
0x18025ae3f  call    ??R_lambda_3bcd5f19bc5f32682702b982507cf16e_@@QEBAXPEAUIAppData@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@PEAUIUnifiedTileIdentifier@UnifiedTile@Shell@WindowsInternal@@@Z; _lambda_3bcd5f19bc5f32682702b982507cf16e_::operator()(Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppData *,WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier *)
0x18025ae44  nop
0x18025ae45  lea     rcx, [rbp+var_40]; void *
0x18025ae49  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x18025ae4e  nop
0x18025ae4f  lea     rcx, [rbp+var_30]; void *
0x18025ae53  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCollectionAssociatedTypes@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@@std@@QEAA@XZ; std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(void)
0x18025ae58  nop
0x18025ae59  mov     rcx, [rbp+string]; string
0x18025ae5d  call    cs:__imp_WindowsDeleteString
0x18025ae63  inc     r14d
0x18025ae66  cmp     r14d, [rbp+var_60]
0x18025ae6a  jb      loc_18025ADB4
0x18025ae70  mov     rcx, [rbp+var_58]; string
0x18025ae74  call    cs:__imp_WindowsDeleteString
0x18025ae7a  mov     [rbp+var_58], 0
0x18025ae82  lea     rcx, [rbp+var_48]; void *
0x18025ae86  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x18025ae8b  nop
0x18025ae8c  mov     rcx, rsi; this
0x18025ae8f  call    ??1_lambda_3bcd5f19bc5f32682702b982507cf16e_@@QEAA@XZ; _lambda_3bcd5f19bc5f32682702b982507cf16e_::~_lambda_3bcd5f19bc5f32682702b982507cf16e_(void)
0x18025ae94  mov     rcx, [rbp+var_10]
0x18025ae98  xor     rcx, rsp; StackCookie
0x18025ae9b  call    __security_check_cookie
0x18025aea0  lea     r11, [rsp+80h+var_s0]
0x18025aea8  mov     rbx, [r11+30h]
0x18025aeac  mov     rsi, [r11+38h]
0x18025aeb0  mov     rsp, r11
0x18025aeb3  pop     r14
0x18025aeb5  pop     rdi
0x18025aeb6  pop     rbp
0x18025aeb7  retn
0x18025aeb8  mov     r9d, eax; char *
0x18025aebb  lea     r8, aShellcommonShe_106; "shellcommon\\shell\\tiles\\curatedtilec"...
0x18025aec2  mov     edx, 58h ; 'X'; void *
0x18025aec7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
