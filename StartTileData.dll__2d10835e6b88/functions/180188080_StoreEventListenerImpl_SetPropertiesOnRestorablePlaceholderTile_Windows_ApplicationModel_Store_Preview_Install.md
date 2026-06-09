# StoreEventListenerImpl::SetPropertiesOnRestorablePlaceholderTile(Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IAppData *,WindowsUpdate::Internal::IInstallItem *,std::shared_ptr<DataStoreCache::PlaceholderTileTransformer::PlaceholderTile> const &)

- ea: `0x180188080`
- end: `0x1801882c6`
- name: `?SetPropertiesOnRestorablePlaceholderTile@StoreEventListenerImpl@@AEAAXPEAUIAppData@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@@PEAUIInstallItem@3WindowsUpdate@@AEBV?$shared_ptr@VPlaceholderTile@PlaceholderTileTransformer@DataStoreCache@@@std@@@Z`
- size: `582`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180187298`

## callees

- `0x18001dac0`
- `0x1800756e4`
- `0x18008d550`
- `0x180161204`
- `0x180183098`
- `0x1801831c4`
- `0x1801854f0`
- `0x180187ee4`
- `0x18018801c`
- `0x180188080`
- `0x1801c59a0`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180188123`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180188123`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801880b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180188164`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801881d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180188288`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18018829a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801882ac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801880b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180188164`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801881d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180188288`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18018829a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801882ac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801880f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801881a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180188218`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801880f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801881a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180188218`

## string_xrefs

- `0x1801880da`: `shellcommon\shell\tiles\curatedtilecollections\storeeventlistener\lib\storeeventlistenerimpl.cpp`
- `0x18018818c`: `shellcommon\shell\tiles\curatedtilecollections\storeeventlistener\lib\storeeventlistenerimpl.cpp`
- `0x1801881fd`: `shellcommon\shell\tiles\curatedtilecollections\storeeventlistener\lib\storeeventlistenerimpl.cpp`
- `0x18018825f`: `shellcommon\shell\tiles\curatedtilecollections\storeeventlistener\lib\storeeventlistenerimpl.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
HRESULT __fastcall StoreEventListenerImpl::SetPropertiesOnRestorablePlaceholderTile(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        DataStoreCache::PlaceholderTileTransformer::PlaceholderTile **a4)
{
  __int64 (__fastcall *v7)(__int64, HSTRING *); // rbx
  int v8; // eax
  DataStoreCache::PlaceholderTileTransformer::PlaceholderTile *v9; // rbx
  PCWSTR StringRawBuffer; // rax
  __int64 v11; // rax
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, HSTRING *); // rbx
  int v14; // eax
  DataStoreCache::PlaceholderTileTransformer::PlaceholderTile *v15; // rbx
  PCWSTR v16; // rax
  __int64 v17; // rax
  __int64 (__fastcall *v18)(__int64, HSTRING *); // rbx
  int v19; // eax
  DataStoreCache::PlaceholderTileTransformer::PlaceholderTile *v20; // rbx
  PCWSTR v21; // rax
  __int64 v22; // rax
  bool v23; // dl
  int v24; // eax
  HSTRING v26; // [rsp+20h] [rbp-40h] BYREF
  HSTRING string; // [rsp+28h] [rbp-38h] BYREF
  __int64 v28; // [rsp+30h] [rbp-30h] BYREF
  _BYTE v29[40]; // [rsp+38h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]
  __int64 v31; // [rsp+90h] [rbp+30h] BYREF
  HSTRING v32; // [rsp+98h] [rbp+38h] BYREF

  v31 = a1;
  string = 0;
  v7 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)a2 + 48LL);
  WindowsDeleteString(0);
  string = 0;
  v8 = v7(a2, &string);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x174,
      (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\storeeventlistener\\lib\\storeeventlistenerimpl.cpp",
      (const char *)(unsigned int)v8,
      (int)v26);
  v9 = *a4;
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  v11 = std::wstring::wstring(v29, StringRawBuffer);
  DataStoreCache::PlaceholderTileTransformer::PlaceholderTile::SetProductId(v9, v11);
  v12 = *((_QWORD *)*a4 + 2);
  AcquireSRWLockExclusive((PSRWLOCK)(v12 + 128));
  v28 = v12 + 128;
  *(_DWORD *)(*(_QWORD *)(v12 + 136) + 32LL) = 1;
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v28);
  DataStoreCache::PlaceholderTileTransformer::PlaceholderTileLocalImpl::OnItemUpdated(
    (DataStoreCache::PlaceholderTileTransformer::PlaceholderTileLocalImpl *)v12,
    *(const struct Windows::Data::PlaceholderTileLocal **)(v12 + 136));
  v26 = 0;
  v13 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)a2 + 64LL);
  WindowsDeleteString(0);
  v26 = 0;
  v14 = v13(a2, &v26);
  if ( v14 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x17B,
      (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\storeeventlistener\\lib\\storeeventlistenerimpl.cpp",
      (const char *)(unsigned int)v14,
      (int)v26);
  v15 = *a4;
  v16 = WindowsGetStringRawBuffer(v26, 0);
  v17 = std::wstring::wstring(v29, v16);
  DataStoreCache::PlaceholderTileTransformer::PlaceholderTile::SetPackageFamilyName(v15, v17);
  v32 = 0;
  v18 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)a2 + 72LL);
  WindowsDeleteString(0);
  v32 = 0;
  v19 = v18(a2, &v32);
  if ( v19 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x17F,
      (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\storeeventlistener\\lib\\storeeventlistenerimpl.cpp",
      (const char *)(unsigned int)v19,
      (int)v26);
  v20 = *a4;
  v21 = WindowsGetStringRawBuffer(v32, 0);
  v22 = std::wstring::wstring(v29, v21);
  DataStoreCache::PlaceholderTileTransformer::PlaceholderTile::SetPackageFullName(v20, v22);
  DataStoreCache::PlaceholderTileTransformer::PlaceholderTile::SetIsPrimary(*a4, v23);
  LOBYTE(v31) = 0;
  v24 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a3 + 120LL))(a3, &v31);
  if ( v24 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x186,
      (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\storeeventlistener\\lib\\storeeventlistenerimpl.cpp",
      (const char *)(unsigned int)v24,
      (int)v26);
  if ( (_BYTE)v31 )
    DataStoreCache::PlaceholderTileTransformer::PlaceholderTile::SetInstallReason(*a4, 1);
  WindowsDeleteString(v32);
  v32 = 0;
  WindowsDeleteString(v26);
  v26 = 0;
  return WindowsDeleteString(string);
}

```

## disassembly

```asm
0x180188080  mov     [rsp-28h+arg_10], rbx
0x180188085  mov     [rsp-28h+arg_0], rcx
0x18018808a  push    rbp
0x18018808b  push    rsi
0x18018808c  push    rdi
0x18018808d  push    r14
0x18018808f  push    r15
0x180188091  mov     rbp, rsp
0x180188094  sub     rsp, 60h
0x180188098  mov     rsi, r9
0x18018809b  mov     r15, r8
0x18018809e  mov     r14, rdx
0x1801880a1  mov     [rbp+string], 0
0x1801880a9  mov     rax, [rdx]
0x1801880ac  mov     rbx, [rax+30h]
0x1801880b0  xor     ecx, ecx; string
0x1801880b2  call    cs:__imp_WindowsDeleteString
0x1801880b8  mov     [rbp+string], 0
0x1801880c0  lea     rdx, [rbp+string]
0x1801880c4  mov     rcx, r14
0x1801880c7  mov     rax, rbx
0x1801880ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801880cf  mov     rcx, [rbp+28h]; this
0x1801880d3  test    eax, eax
0x1801880d5  jns     short loc_1801880EC
0x1801880d7  mov     r9d, eax; char *
0x1801880da  lea     r8, aShellcommonShe_106; "shellcommon\\shell\\tiles\\curatedtilec"...
0x1801880e1  mov     edx, 174h; void *
0x1801880e6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1801880ec  mov     rbx, [rsi]
0x1801880ef  xor     edx, edx; length
0x1801880f1  mov     rcx, [rbp+string]; string
0x1801880f5  call    cs:__imp_WindowsGetStringRawBuffer
0x1801880fb  mov     rdx, rax
0x1801880fe  lea     rcx, [rbp+var_28]
0x180188102  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180188107  mov     rdx, rax
0x18018810a  mov     rcx, rbx
0x18018810d  call    ?SetProductId@PlaceholderTile@PlaceholderTileTransformer@DataStoreCache@@QEAAXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; DataStoreCache::PlaceholderTileTransformer::PlaceholderTile::SetProductId(std::wstring)
0x180188112  mov     rax, [rsi]
0x180188115  mov     rdi, [rax+10h]
0x180188119  lea     rbx, [rdi+80h]
0x180188120  mov     rcx, rbx; SRWLock
0x180188123  call    cs:__imp_AcquireSRWLockExclusive
0x180188129  mov     [rbp+var_30], rbx
0x18018812d  mov     rax, [rdi+88h]
0x180188134  mov     dword ptr [rax+20h], 1
0x18018813b  lea     rcx, [rbp+var_30]
0x18018813f  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x180188144  mov     rdx, [rdi+88h]; struct Windows::Data::PlaceholderTileLocal *
0x18018814b  mov     rcx, rdi; this
0x18018814e  call    ?OnItemUpdated@PlaceholderTileLocalImpl@PlaceholderTileTransformer@DataStoreCache@@IEAAXAEBUPlaceholderTileLocal@Data@Windows@@@Z; DataStoreCache::PlaceholderTileTransformer::PlaceholderTileLocalImpl::OnItemUpdated(Windows::Data::PlaceholderTileLocal const &)
0x180188153  mov     [rbp+var_40], 0
0x18018815b  mov     rax, [r14]
0x18018815e  mov     rbx, [rax+40h]
0x180188162  xor     ecx, ecx; string
0x180188164  call    cs:__imp_WindowsDeleteString
0x18018816a  mov     [rbp+var_40], 0
0x180188172  lea     rdx, [rbp+var_40]
0x180188176  mov     rcx, r14
0x180188179  mov     rax, rbx
0x18018817c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180188181  mov     rcx, [rbp+28h]; this
0x180188185  test    eax, eax
0x180188187  jns     short loc_18018819E
0x180188189  mov     r9d, eax; char *
0x18018818c  lea     r8, aShellcommonShe_106; "shellcommon\\shell\\tiles\\curatedtilec"...
0x180188193  mov     edx, 17Bh; void *
0x180188198  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18018819e  mov     rbx, [rsi]
0x1801881a1  xor     edx, edx; length
0x1801881a3  mov     rcx, [rbp+var_40]; string
0x1801881a7  call    cs:__imp_WindowsGetStringRawBuffer
0x1801881ad  mov     rdx, rax
0x1801881b0  lea     rcx, [rbp+var_28]
0x1801881b4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1801881b9  mov     rdx, rax
0x1801881bc  mov     rcx, rbx
0x1801881bf  call    ?SetPackageFamilyName@PlaceholderTile@PlaceholderTileTransformer@DataStoreCache@@QEAAXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; DataStoreCache::PlaceholderTileTransformer::PlaceholderTile::SetPackageFamilyName(std::wstring)
0x1801881c4  mov     [rbp+arg_8], 0
0x1801881cc  mov     rax, [r14]
0x1801881cf  mov     rbx, [rax+48h]
0x1801881d3  xor     ecx, ecx; string
0x1801881d5  call    cs:__imp_WindowsDeleteString
0x1801881db  mov     [rbp+arg_8], 0
0x1801881e3  lea     rdx, [rbp+arg_8]
0x1801881e7  mov     rcx, r14
0x1801881ea  mov     rax, rbx
0x1801881ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801881f2  mov     rcx, [rbp+28h]; this
0x1801881f6  test    eax, eax
0x1801881f8  jns     short loc_18018820F
0x1801881fa  mov     r9d, eax; char *
0x1801881fd  lea     r8, aShellcommonShe_106; "shellcommon\\shell\\tiles\\curatedtilec"...
0x180188204  mov     edx, 17Fh; void *
0x180188209  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18018820f  mov     rbx, [rsi]
0x180188212  xor     edx, edx; length
0x180188214  mov     rcx, [rbp+arg_8]; string
0x180188218  call    cs:__imp_WindowsGetStringRawBuffer
0x18018821e  mov     rdx, rax
0x180188221  lea     rcx, [rbp+var_28]
0x180188225  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18018822a  mov     rdx, rax
0x18018822d  mov     rcx, rbx
0x180188230  call    ?SetPackageFullName@PlaceholderTile@PlaceholderTileTransformer@DataStoreCache@@QEAAXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; DataStoreCache::PlaceholderTileTransformer::PlaceholderTile::SetPackageFullName(std::wstring)
0x180188235  mov     rcx, [rsi]; this
0x180188238  call    ?SetIsPrimary@PlaceholderTile@PlaceholderTileTransformer@DataStoreCache@@QEAAX_N@Z; DataStoreCache::PlaceholderTileTransformer::PlaceholderTile::SetIsPrimary(bool)
0x18018823d  mov     byte ptr [rbp+arg_0], 0
0x180188241  mov     rax, [r15]
0x180188244  lea     rdx, [rbp+arg_0]
0x180188248  mov     rcx, r15
0x18018824b  mov     rax, [rax+78h]
0x18018824f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180188254  mov     rcx, [rbp+28h]; this
0x180188258  test    eax, eax
0x18018825a  jns     short loc_180188270
0x18018825c  mov     r9d, eax; char *
0x18018825f  lea     r8, aShellcommonShe_106; "shellcommon\\shell\\tiles\\curatedtilec"...
0x180188266  mov     edx, 186h; void *
0x18018826b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180188270  cmp     byte ptr [rbp+arg_0], 0
0x180188274  jz      short loc_180188284
0x180188276  mov     edx, 1
0x18018827b  mov     rcx, [rsi]
0x18018827e  call    ?SetInstallReason@PlaceholderTile@PlaceholderTileTransformer@DataStoreCache@@QEAAXW4InstallReasonType@23@@Z; DataStoreCache::PlaceholderTileTransformer::PlaceholderTile::SetInstallReason(DataStoreCache::PlaceholderTileTransformer::InstallReasonType)
0x180188283  nop
0x180188284  mov     rcx, [rbp+arg_8]; string
0x180188288  call    cs:__imp_WindowsDeleteString
0x18018828e  mov     [rbp+arg_8], 0
0x180188296  mov     rcx, [rbp+var_40]; string
0x18018829a  call    cs:__imp_WindowsDeleteString
0x1801882a0  mov     [rbp+var_40], 0
0x1801882a8  mov     rcx, [rbp+string]; string
0x1801882ac  call    cs:__imp_WindowsDeleteString
0x1801882b2  mov     rbx, [rsp+60h+arg_10]
0x1801882ba  add     rsp, 60h
0x1801882be  pop     r15
0x1801882c0  pop     r14
0x1801882c2  pop     rdi
0x1801882c3  pop     rsi
0x1801882c4  pop     rbp
0x1801882c5  retn
```
