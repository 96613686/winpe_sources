# ForEachApp<_lambda_abe844aed825a6f2782fc1a4b0f3b3f6_>(Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppData *,_lambda_abe844aed825a6f2782fc1a4b0f3b3f6_)

- ea: `0x18015a314`
- end: `0x18015a525`
- name: `??$ForEachApp@V_lambda_abe844aed825a6f2782fc1a4b0f3b3f6_@@@@YAXPEAUIAppData@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@V_lambda_abe844aed825a6f2782fc1a4b0f3b3f6_@@@Z`
- size: `529`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180159d04`

## callees

- `0x18001dac0`
- `0x18002dde0`
- `0x18007ae80`
- `0x18015a314`
- `0x18016dad4`
- `0x180187100`
- `0x180201e50`
- `0x18025bc04`
- `0x18025c4cc`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18015a3c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18015a41f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18015a4b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18015a4cd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18015a3c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18015a41f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18015a4b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18015a4cd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18015a451`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18015a460`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18015a451`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18015a460`

## string_xrefs

- `0x18015a36c`: `shellcommon\shell\tiles\curatedtilecollections\storeeventlistener\lib\storeeventlistenerimpl.cpp`
- `0x18015a39d`: `shellcommon\shell\tiles\curatedtilecollections\storeeventlistener\lib\storeeventlistenerimpl.cpp`
- `0x18015a3eb`: `shellcommon\shell\tiles\curatedtilecollections\storeeventlistener\lib\storeeventlistenerimpl.cpp`
- `0x18015a513`: `shellcommon\shell\tiles\curatedtilecollections\storeeventlistener\lib\storeeventlistenerimpl.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall ForEachApp<_lambda_abe844aed825a6f2782fc1a4b0f3b3f6_>(
        __int64 *a1,
        _lambda_abe844aed825a6f2782fc1a4b0f3b3f6_ *a2)
{
  __int64 v4; // rax
  int v5; // eax
  int v6; // eax
  __int64 (__fastcall *v7)(__int64 *, HSTRING *); // rbx
  int v8; // eax
  unsigned int i; // r15d
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, _QWORD, HSTRING *); // rbx
  int v12; // eax
  PCWSTR StringRawBuffer; // rbx
  PCWSTR v14; // rax
  _QWORD *v15; // rdx
  unsigned int v16; // [rsp+20h] [rbp-60h] BYREF
  HSTRING v17; // [rsp+28h] [rbp-58h] BYREF
  HSTRING string; // [rsp+30h] [rbp-50h] BYREF
  __int64 v19; // [rsp+38h] [rbp-48h] BYREF
  _QWORD v20[2]; // [rsp+40h] [rbp-40h] BYREF
  _QWORD v21[4]; // [rsp+50h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]

  v20[1] = a2;
  v16 = 0;
  v4 = *a1;
  v19 = 0;
  v5 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v4 + 96))(a1, &v19);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x4A,
      (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\storeeventlistener\\lib\\storeeventlistenerimpl.cpp",
      (const char *)(unsigned int)v5,
      v16);
  v6 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v19 + 56LL))(v19, &v16);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x4B,
      (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\storeeventlistener\\lib\\storeeventlistenerimpl.cpp",
      (const char *)(unsigned int)v6,
      v16);
  v17 = 0;
  v7 = *(__int64 (__fastcall **)(__int64 *, HSTRING *))(*a1 + 208);
  WindowsDeleteString(0);
  v17 = 0;
  v8 = v7(a1, &v17);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x53,
      (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\storeeventlistener\\lib\\storeeventlistenerimpl.cpp",
      (const char *)(unsigned int)v8,
      v16);
  for ( i = 0; i < v16; ++i )
  {
    string = 0;
    v10 = v19;
    v11 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)v19 + 48LL);
    WindowsDeleteString(0);
    string = 0;
    v12 = v11(v10, i, &string);
    if ( v12 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x58,
        (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\storeeventlistener\\lib\\storeeventlistenerimpl.cpp",
        (const char *)(unsigned int)v12,
        v16);
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v14 = WindowsGetStringRawBuffer(v17, 0);
    CreateAumid(v21, v14, StringRawBuffer);
    v15 = v21;
    if ( v21[3] > 7u )
      v15 = (_QWORD *)v21[0];
    WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::AumidToUti(v20, v15);
    _lambda_abe844aed825a6f2782fc1a4b0f3b3f6_::operator()(a2, a1, v20[0]);
    wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(v20);
    std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(v21);
    WindowsDeleteString(string);
  }
  WindowsDeleteString(v17);
  v17 = 0;
  wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v19);
  _lambda_abe844aed825a6f2782fc1a4b0f3b3f6_::~_lambda_abe844aed825a6f2782fc1a4b0f3b3f6_(a2);
}

```

## disassembly

```asm
0x18015a314  mov     [rsp-28h+arg_10], rbx
0x18015a319  push    rbp
0x18015a31a  push    rsi
0x18015a31b  push    rdi
0x18015a31c  push    r14
0x18015a31e  push    r15
0x18015a320  mov     rbp, rsp
0x18015a323  sub     rsp, 80h
0x18015a32a  mov     rax, cs:__security_cookie
0x18015a331  xor     rax, rsp
0x18015a334  mov     [rbp+var_10], rax
0x18015a338  mov     r14, rdx
0x18015a33b  mov     rsi, rcx
0x18015a33e  mov     [rbp+var_38], rdx
0x18015a342  mov     [rbp+var_60], 0
0x18015a349  mov     rax, [rcx]
0x18015a34c  mov     [rbp+var_48], 0
0x18015a354  lea     rdx, [rbp+var_48]
0x18015a358  mov     rax, [rax+60h]
0x18015a35c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015a361  mov     rcx, [rbp+28h]; this
0x18015a365  test    eax, eax
0x18015a367  jns     short loc_18015A37E
0x18015a369  mov     r9d, eax; char *
0x18015a36c  lea     r8, aShellcommonShe_106; "shellcommon\\shell\\tiles\\curatedtilec"...
0x18015a373  mov     edx, 4Ah ; 'J'; void *
0x18015a378  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18015a37e  mov     rcx, [rbp+var_48]
0x18015a382  mov     rax, [rcx]
0x18015a385  lea     rdx, [rbp+var_60]
0x18015a389  mov     rax, [rax+38h]
0x18015a38d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015a392  mov     rcx, [rbp+28h]; this
0x18015a396  test    eax, eax
0x18015a398  jns     short loc_18015A3AF
0x18015a39a  mov     r9d, eax; char *
0x18015a39d  lea     r8, aShellcommonShe_106; "shellcommon\\shell\\tiles\\curatedtilec"...
0x18015a3a4  mov     edx, 4Bh ; 'K'; void *
0x18015a3a9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18015a3af  mov     [rbp+var_58], 0
0x18015a3b7  mov     rax, [rsi]
0x18015a3ba  mov     rbx, [rax+0D0h]
0x18015a3c1  xor     ecx, ecx; string
0x18015a3c3  call    cs:__imp_WindowsDeleteString
0x18015a3c9  mov     [rbp+var_58], 0
0x18015a3d1  lea     rdx, [rbp+var_58]
0x18015a3d5  mov     rcx, rsi
0x18015a3d8  mov     rax, rbx
0x18015a3db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015a3e0  mov     rcx, [rbp+28h]; this
0x18015a3e4  test    eax, eax
0x18015a3e6  jns     short loc_18015A3FD
0x18015a3e8  mov     r9d, eax; char *
0x18015a3eb  lea     r8, aShellcommonShe_106; "shellcommon\\shell\\tiles\\curatedtilec"...
0x18015a3f2  mov     edx, 53h ; 'S'; void *
0x18015a3f7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18015a3fd  xor     r15d, r15d
0x18015a400  cmp     [rbp+var_60], r15d
0x18015a404  jbe     loc_18015A4C9
0x18015a40a  mov     [rbp+string], 0
0x18015a412  mov     rdi, [rbp+var_48]
0x18015a416  mov     rax, [rdi]
0x18015a419  mov     rbx, [rax+30h]
0x18015a41d  xor     ecx, ecx; string
0x18015a41f  call    cs:__imp_WindowsDeleteString
0x18015a425  mov     [rbp+string], 0
0x18015a42d  lea     r8, [rbp+string]
0x18015a431  mov     edx, r15d
0x18015a434  mov     rcx, rdi
0x18015a437  mov     rax, rbx
0x18015a43a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015a43f  mov     rcx, [rbp+28h]; this
0x18015a443  test    eax, eax
0x18015a445  js      loc_18015A510
0x18015a44b  xor     edx, edx; length
0x18015a44d  mov     rcx, [rbp+string]; string
0x18015a451  call    cs:__imp_WindowsGetStringRawBuffer
0x18015a457  mov     rbx, rax
0x18015a45a  xor     edx, edx; length
0x18015a45c  mov     rcx, [rbp+var_58]; string
0x18015a460  call    cs:__imp_WindowsGetStringRawBuffer
0x18015a466  mov     r8, rbx
0x18015a469  mov     rdx, rax
0x18015a46c  lea     rcx, [rbp+var_30]
0x18015a470  call    ?CreateAumid@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG0@Z; CreateAumid(ushort const *,ushort const *)
0x18015a475  nop
0x18015a476  lea     rdx, [rbp+var_30]
0x18015a47a  cmp     [rbp+var_18], 7
0x18015a47f  cmova   rdx, [rbp+var_30]
0x18015a484  lea     rcx, [rbp+var_40]
0x18015a488  call    WindowsInternal__Shell__UnifiedTile__CuratedTileCollections__AumidToUti
0x18015a48d  nop
0x18015a48e  mov     r8, [rbp+var_40]
0x18015a492  mov     rdx, rsi
0x18015a495  mov     rcx, r14
0x18015a498  call    ??R_lambda_abe844aed825a6f2782fc1a4b0f3b3f6_@@QEBAXPEAUIAppData@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@PEAUIUnifiedTileIdentifier@UnifiedTile@Shell@WindowsInternal@@@Z; _lambda_abe844aed825a6f2782fc1a4b0f3b3f6_::operator()(Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppData *,WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier *)
0x18015a49d  nop
0x18015a49e  lea     rcx, [rbp+var_40]; void *
0x18015a4a2  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x18015a4a7  nop
0x18015a4a8  lea     rcx, [rbp+var_30]; void *
0x18015a4ac  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCollectionAssociatedTypes@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@@std@@QEAA@XZ; std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(void)
0x18015a4b1  nop
0x18015a4b2  mov     rcx, [rbp+string]; string
0x18015a4b6  call    cs:__imp_WindowsDeleteString
0x18015a4bc  inc     r15d
0x18015a4bf  cmp     r15d, [rbp+var_60]
0x18015a4c3  jb      loc_18015A40A
0x18015a4c9  mov     rcx, [rbp+var_58]; string
0x18015a4cd  call    cs:__imp_WindowsDeleteString
0x18015a4d3  mov     [rbp+var_58], 0
0x18015a4db  lea     rcx, [rbp+var_48]; void *
0x18015a4df  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x18015a4e4  nop
0x18015a4e5  mov     rcx, r14; this
0x18015a4e8  call    ??1_lambda_abe844aed825a6f2782fc1a4b0f3b3f6_@@QEAA@XZ; _lambda_abe844aed825a6f2782fc1a4b0f3b3f6_::~_lambda_abe844aed825a6f2782fc1a4b0f3b3f6_(void)
0x18015a4ed  mov     rcx, [rbp+var_10]
0x18015a4f1  xor     rcx, rsp; StackCookie
0x18015a4f4  call    __security_check_cookie
0x18015a4f9  mov     rbx, [rsp+80h+arg_10]
0x18015a501  add     rsp, 80h
0x18015a508  pop     r15
0x18015a50a  pop     r14
0x18015a50c  pop     rdi
0x18015a50d  pop     rsi
0x18015a50e  pop     rbp
0x18015a50f  retn
0x18015a510  mov     r9d, eax; char *
0x18015a513  lea     r8, aShellcommonShe_106; "shellcommon\\shell\\tiles\\curatedtilec"...
0x18015a51a  mov     edx, 58h ; 'X'; void *
0x18015a51f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
