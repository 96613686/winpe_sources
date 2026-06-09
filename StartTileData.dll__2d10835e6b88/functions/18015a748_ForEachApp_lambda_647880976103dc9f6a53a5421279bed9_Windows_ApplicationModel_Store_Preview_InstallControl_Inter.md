# ForEachApp<_lambda_647880976103dc9f6a53a5421279bed9_>(Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppData *,_lambda_647880976103dc9f6a53a5421279bed9_)

- ea: `0x18015a748`
- end: `0x18015a95a`
- name: `??$ForEachApp@V_lambda_647880976103dc9f6a53a5421279bed9_@@@@YAXPEAUIAppData@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@V_lambda_647880976103dc9f6a53a5421279bed9_@@@Z`
- size: `530`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18015a52c`

## callees

- `0x18001dac0`
- `0x18002dde0`
- `0x18007ae80`
- `0x18015a748`
- `0x18016dad4`
- `0x180201e50`
- `0x18025bf98`
- `0x18025c4cc`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18015a7f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18015a855`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18015a8e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18015a900`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18015a7f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18015a855`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18015a8e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18015a900`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18015a887`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18015a896`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18015a887`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18015a896`

## string_xrefs

- `0x18015a7a2`: `shellcommon\shell\tiles\curatedtilecollections\storeeventlistener\lib\storeeventlistenerimpl.cpp`
- `0x18015a7d3`: `shellcommon\shell\tiles\curatedtilecollections\storeeventlistener\lib\storeeventlistenerimpl.cpp`
- `0x18015a821`: `shellcommon\shell\tiles\curatedtilecollections\storeeventlistener\lib\storeeventlistenerimpl.cpp`
- `0x18015a948`: `shellcommon\shell\tiles\curatedtilecollections\storeeventlistener\lib\storeeventlistenerimpl.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall ForEachApp<_lambda_647880976103dc9f6a53a5421279bed9_>(__int64 *a1, __int64 a2)
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
    _lambda_647880976103dc9f6a53a5421279bed9_::operator()(a2, v16, v21[0]);
    wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(v21);
    std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(v22);
    WindowsDeleteString(string);
  }
  WindowsDeleteString(v18);
  v18 = 0;
  wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v20);
  wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>((void *)(a2 + 8));
}

```

## disassembly

```asm
0x18015a748  mov     [rsp-18h+arg_10], rbx
0x18015a74d  mov     [rsp-18h+arg_18], rsi
0x18015a752  push    rbp
0x18015a753  push    rdi
0x18015a754  push    r14
0x18015a756  mov     rbp, rsp
0x18015a759  sub     rsp, 80h
0x18015a760  mov     rax, cs:__security_cookie
0x18015a767  xor     rax, rsp
0x18015a76a  mov     [rbp+var_10], rax
0x18015a76e  mov     rsi, rdx
0x18015a771  mov     rdi, rcx
0x18015a774  mov     [rbp+var_38], rdx
0x18015a778  mov     [rbp+var_60], 0
0x18015a77f  mov     rax, [rcx]
0x18015a782  mov     [rbp+var_48], 0
0x18015a78a  lea     rdx, [rbp+var_48]
0x18015a78e  mov     rax, [rax+60h]
0x18015a792  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015a797  mov     rcx, [rbp+18h]; this
0x18015a79b  test    eax, eax
0x18015a79d  jns     short loc_18015A7B4
0x18015a79f  mov     r9d, eax; char *
0x18015a7a2  lea     r8, aShellcommonShe_106; "shellcommon\\shell\\tiles\\curatedtilec"...
0x18015a7a9  mov     edx, 4Ah ; 'J'; void *
0x18015a7ae  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18015a7b4  mov     rcx, [rbp+var_48]
0x18015a7b8  mov     rax, [rcx]
0x18015a7bb  lea     rdx, [rbp+var_60]
0x18015a7bf  mov     rax, [rax+38h]
0x18015a7c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015a7c8  mov     rcx, [rbp+18h]; this
0x18015a7cc  test    eax, eax
0x18015a7ce  jns     short loc_18015A7E5
0x18015a7d0  mov     r9d, eax; char *
0x18015a7d3  lea     r8, aShellcommonShe_106; "shellcommon\\shell\\tiles\\curatedtilec"...
0x18015a7da  mov     edx, 4Bh ; 'K'; void *
0x18015a7df  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18015a7e5  mov     [rbp+var_58], 0
0x18015a7ed  mov     rax, [rdi]
0x18015a7f0  mov     rbx, [rax+0D0h]
0x18015a7f7  xor     ecx, ecx; string
0x18015a7f9  call    cs:__imp_WindowsDeleteString
0x18015a7ff  mov     [rbp+var_58], 0
0x18015a807  lea     rdx, [rbp+var_58]
0x18015a80b  mov     rcx, rdi
0x18015a80e  mov     rax, rbx
0x18015a811  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015a816  mov     rcx, [rbp+18h]; this
0x18015a81a  test    eax, eax
0x18015a81c  jns     short loc_18015A833
0x18015a81e  mov     r9d, eax; char *
0x18015a821  lea     r8, aShellcommonShe_106; "shellcommon\\shell\\tiles\\curatedtilec"...
0x18015a828  mov     edx, 53h ; 'S'; void *
0x18015a82d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18015a833  xor     r14d, r14d
0x18015a836  cmp     [rbp+var_60], r14d
0x18015a83a  jbe     loc_18015A8FC
0x18015a840  mov     [rbp+string], 0
0x18015a848  mov     rdi, [rbp+var_48]
0x18015a84c  mov     rax, [rdi]
0x18015a84f  mov     rbx, [rax+30h]
0x18015a853  xor     ecx, ecx; string
0x18015a855  call    cs:__imp_WindowsDeleteString
0x18015a85b  mov     [rbp+string], 0
0x18015a863  lea     r8, [rbp+string]
0x18015a867  mov     edx, r14d
0x18015a86a  mov     rcx, rdi
0x18015a86d  mov     rax, rbx
0x18015a870  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015a875  mov     rcx, [rbp+18h]; this
0x18015a879  test    eax, eax
0x18015a87b  js      loc_18015A945
0x18015a881  xor     edx, edx; length
0x18015a883  mov     rcx, [rbp+string]; string
0x18015a887  call    cs:__imp_WindowsGetStringRawBuffer
0x18015a88d  mov     rbx, rax
0x18015a890  xor     edx, edx; length
0x18015a892  mov     rcx, [rbp+var_58]; string
0x18015a896  call    cs:__imp_WindowsGetStringRawBuffer
0x18015a89c  mov     r8, rbx
0x18015a89f  mov     rdx, rax
0x18015a8a2  lea     rcx, [rbp+var_30]
0x18015a8a6  call    ?CreateAumid@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG0@Z; CreateAumid(ushort const *,ushort const *)
0x18015a8ab  nop
0x18015a8ac  lea     rdx, [rbp+var_30]
0x18015a8b0  cmp     [rbp+var_18], 7
0x18015a8b5  cmova   rdx, [rbp+var_30]
0x18015a8ba  lea     rcx, [rbp+var_40]
0x18015a8be  call    WindowsInternal__Shell__UnifiedTile__CuratedTileCollections__AumidToUti
0x18015a8c3  nop
0x18015a8c4  mov     r8, [rbp+var_40]
0x18015a8c8  mov     rcx, rsi
0x18015a8cb  call    ??R_lambda_647880976103dc9f6a53a5421279bed9_@@QEBA@PEAUIAppData@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@PEAUIUnifiedTileIdentifier@UnifiedTile@Shell@WindowsInternal@@@Z; _lambda_647880976103dc9f6a53a5421279bed9_::operator()(Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppData *,WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier *)
0x18015a8d0  nop
0x18015a8d1  lea     rcx, [rbp+var_40]; void *
0x18015a8d5  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x18015a8da  nop
0x18015a8db  lea     rcx, [rbp+var_30]; void *
0x18015a8df  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UCollectionAssociatedTypes@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@@std@@QEAA@XZ; std::pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>::~pair<std::wstring const,WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CollectionAssociatedTypes>(void)
0x18015a8e4  nop
0x18015a8e5  mov     rcx, [rbp+string]; string
0x18015a8e9  call    cs:__imp_WindowsDeleteString
0x18015a8ef  inc     r14d
0x18015a8f2  cmp     r14d, [rbp+var_60]
0x18015a8f6  jb      loc_18015A840
0x18015a8fc  mov     rcx, [rbp+var_58]; string
0x18015a900  call    cs:__imp_WindowsDeleteString
0x18015a906  mov     [rbp+var_58], 0
0x18015a90e  lea     rcx, [rbp+var_48]; void *
0x18015a912  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x18015a917  nop
0x18015a918  lea     rcx, [rsi+8]; void *
0x18015a91c  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x18015a921  mov     rcx, [rbp+var_10]
0x18015a925  xor     rcx, rsp; StackCookie
0x18015a928  call    __security_check_cookie
0x18015a92d  lea     r11, [rsp+80h+var_s0]
0x18015a935  mov     rbx, [r11+30h]
0x18015a939  mov     rsi, [r11+38h]
0x18015a93d  mov     rsp, r11
0x18015a940  pop     r14
0x18015a942  pop     rdi
0x18015a943  pop     rbp
0x18015a944  retn
0x18015a945  mov     r9d, eax; char *
0x18015a948  lea     r8, aShellcommonShe_106; "shellcommon\\shell\\tiles\\curatedtilec"...
0x18015a94f  mov     edx, 58h ; 'X'; void *
0x18015a954  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
