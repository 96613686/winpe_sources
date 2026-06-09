# DownloadToTempFile(ushort const *,ushort const *,ushort const *,ushort const *,HSTRING__ * *)

- ea: `0x180128fe4`
- end: `0x180129278`
- name: `?DownloadToTempFile@@YAJPEBG000PEAPEAUHSTRING__@@@Z`
- size: `660`
- prototype: `__int64 __usercall@<rax>(const unsigned __int16 *@<rcx>, const unsigned __int16 *@<rdx>, const unsigned __int16 *@<r8>, const unsigned __int16 *@<r9>, HSTRING *)`
- caller_count: `2`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180126f08`
- `0x1801d7f5c`

## callees

- `0x180009ea0`
- `0x180014f18`
- `0x18001cce0`
- `0x180022e14`
- `0x1800724a4`
- `0x18007e528`
- `0x1800992a8`
- `0x1800ceb88`
- `0x1800d2100`
- `0x180128fe4`
- `0x180129e74`
- `0x180129f90`
- `0x1801db1b0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180129133`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18012922f`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180129133`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18012922f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801290d3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18012913d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801291d1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180129239`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801290d3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18012913d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801291d1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180129239`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180129101`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18012912a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801291fd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180129226`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180129101`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18012912a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801291fd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180129226`

## pseudocode

```c
// Hidden C++ exception states: #wind=8 #try_helpers=1
__int64 __fastcall DownloadToTempFile(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4,
        HSTRING *a5)
{
  char IsEnabled; // al
  __int64 v9; // rdx
  __int64 TokenForSid; // rax
  __int64 v11; // rax
  __int64 v12; // rcx
  int TempFilePath; // esi
  HSTRING v14; // rbx
  const unsigned __int16 *StringRawBuffer; // r8
  HSTRING v16; // rax
  const WCHAR *v17; // rax
  __int64 v19; // rdx
  __int64 v20; // rdx
  __int64 v21; // rax
  const unsigned __int16 *v22; // rcx
  int TempFilePath_Deprecated; // edi
  HSTRING v24; // rbx
  const unsigned __int16 *v25; // rax
  HSTRING v26; // rax
  const WCHAR *v27; // rax
  HSTRING string; // [rsp+20h] [rbp-88h] BYREF
  __int64 v29; // [rsp+28h] [rbp-80h] BYREF
  void **v30; // [rsp+30h] [rbp-78h] BYREF
  __int64 v31; // [rsp+38h] [rbp-70h]
  _QWORD v32[2]; // [rsp+40h] [rbp-68h] BYREF
  _BYTE v33[32]; // [rsp+50h] [rbp-58h] BYREF

  string = (HSTRING)a4;
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixAccessDeniedForStaticProgressHandlers>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_FixAccessDeniedForStaticProgressHandlers>::GetImpl'::`2'::impl);
  *a5 = 0;
  if ( IsEnabled )
  {
    v30 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
    v31 = 0;
    v29 = -1;
    if ( a4 )
    {
      v9 = *(_QWORD *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(v33, &string) + 24);
      TokenForSid = TokenHelpers::GetTokenForSid(v32, v9);
      Microsoft::WRL::Wrappers::HandleT<HINTERNETTraits>::operator=(&v30, TokenForSid);
      v32[0] = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
      Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(v32);
      v11 = wil::impersonate_token(&string, v31);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>>::operator=(
        &v29,
        v11);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&string);
    }
    else
    {
      Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(&v30);
      v31 = -6;
    }
    WindowsDeleteString(0);
    string = 0;
    TempFilePath = GetTempFilePath(v12, &v30, &string);
    v14 = string;
    if ( TempFilePath >= 0 )
    {
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      TempFilePath = FetchImageFromNetworkAndSaveToFile(a1, a2, StringRawBuffer);
      if ( TempFilePath < 0 )
      {
        v17 = WindowsGetStringRawBuffer(v14, 0);
        DeleteFileW(v17);
      }
      else
      {
        v16 = v14;
        v14 = 0;
        *a5 = v16;
      }
    }
    WindowsDeleteString(v14);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&v29);
    v30 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
    Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(&v30);
    return (unsigned int)TempFilePath;
  }
  else
  {
    v29 = -1;
    if ( a4 )
    {
      v19 = *(_QWORD *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(v33, &string) + 24);
      v20 = *(_QWORD *)(TokenHelpers::GetTokenForSid(v32, v19) + 8);
      v21 = wil::impersonate_token(&v30, v20);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>>::operator=(
        &v29,
        v21);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&v30);
      v32[0] = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
      Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(v32);
    }
    WindowsDeleteString(0);
    string = 0;
    TempFilePath_Deprecated = GetTempFilePath_Deprecated(v22, a4, &string);
    v24 = string;
    if ( TempFilePath_Deprecated >= 0 )
    {
      v25 = WindowsGetStringRawBuffer(string, 0);
      TempFilePath_Deprecated = FetchImageFromNetworkAndSaveToFile(a1, a2, v25);
      if ( TempFilePath_Deprecated < 0 )
      {
        v27 = WindowsGetStringRawBuffer(v24, 0);
        DeleteFileW(v27);
      }
      else
      {
        v26 = v24;
        v24 = 0;
        *a5 = v26;
      }
    }
    WindowsDeleteString(v24);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&v29);
    return (unsigned int)TempFilePath_Deprecated;
  }
}

```

## disassembly

```asm
0x180128fe4  mov     [rsp+arg_0], rbx
0x180128fe9  push    rsi
0x180128fea  push    rdi
0x180128feb  push    r12
0x180128fed  push    r14
0x180128fef  push    r15
0x180128ff1  sub     rsp, 80h
0x180128ff8  mov     rax, cs:__security_cookie
0x180128fff  xor     rax, rsp
0x180129002  mov     [rsp+0A8h+var_38], rax
0x180129007  mov     rbx, r9
0x18012900a  mov     r12, rdx
0x18012900d  mov     r15, rcx
0x180129010  mov     [rsp+0A8h+string], rbx
0x180129015  mov     r14, [rsp+0A8h+arg_20]
0x18012901d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_FixAccessDeniedForStaticProgressHandlers@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_FixAccessDeniedForStaticProgressHandlers@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixAccessDeniedForStaticProgressHandlers> `wil::Feature<__WilFeatureTraits_Feature_FixAccessDeniedForStaticProgressHandlers>::GetImpl(void)'::`2'::impl
0x180129024  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_FixAccessDeniedForStaticProgressHandlers@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FixAccessDeniedForStaticProgressHandlers>::__private_IsEnabled(void)
0x180129029  mov     qword ptr [r14], 0
0x180129030  test    al, al
0x180129032  jz      loc_180129165
0x180129038  lea     rdi, ??_7?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable'
0x18012903f  mov     [rsp+0A8h+var_78], rdi
0x180129044  mov     [rsp+0A8h+var_70], 0
0x18012904d  mov     [rsp+0A8h+var_80], 0FFFFFFFFFFFFFFFFh
0x180129056  test    rbx, rbx
0x180129059  jz      short loc_1801290BE
0x18012905b  lea     rdx, [rsp+0A8h+string]
0x180129060  lea     rcx, [rsp+0A8h+var_58]
0x180129065  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18012906a  nop
0x18012906b  mov     rdx, [rax+18h]
0x18012906f  lea     rcx, [rsp+0A8h+var_68]
0x180129074  call    ?GetTokenForSid@TokenHelpers@@YA?AV?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@PEAUHSTRING__@@@Z; TokenHelpers::GetTokenForSid(HSTRING__ *)
0x180129079  mov     rdx, rax
0x18012907c  lea     rcx, [rsp+0A8h+var_78]
0x180129081  call    ??4?$HandleT@UHINTERNETTraits@@@Wrappers@WRL@Microsoft@@QEAAAEAV0123@$$QEAV0123@@Z; Microsoft::WRL::Wrappers::HandleT<HINTERNETTraits>::operator=(Microsoft::WRL::Wrappers::HandleT<HINTERNETTraits> &&)
0x180129086  mov     [rsp+0A8h+var_68], rdi
0x18012908b  lea     rcx, [rsp+0A8h+var_68]
0x180129090  call    ?Close@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(void)
0x180129095  nop
0x180129096  mov     rdx, [rsp+0A8h+var_70]
0x18012909b  lea     rcx, [rsp+0A8h+string]
0x1801290a0  call    ?impersonate_token@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@PEAX@Z; wil::impersonate_token(void *)
0x1801290a5  mov     rdx, rax
0x1801290a8  lea     rcx, [rsp+0A8h+var_80]
0x1801290ad  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>> &&)
0x1801290b2  lea     rcx, [rsp+0A8h+string]
0x1801290b7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x1801290bc  jmp     short loc_1801290D1
0x1801290be  lea     rcx, [rsp+0A8h+var_78]
0x1801290c3  call    ?Close@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(void)
0x1801290c8  mov     [rsp+0A8h+var_70], 0FFFFFFFFFFFFFFFAh
0x1801290d1  xor     ecx, ecx; string
0x1801290d3  call    cs:__imp_WindowsDeleteString
0x1801290d9  mov     [rsp+0A8h+string], 0
0x1801290e2  lea     r8, [rsp+0A8h+string]
0x1801290e7  lea     rdx, [rsp+0A8h+var_78]
0x1801290ec  call    ?GetTempFilePath@@YAJPEBGAEAV?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@PEAPEAUHSTRING__@@@Z; GetTempFilePath(ushort const *,Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits> &,HSTRING__ * *)
0x1801290f1  mov     esi, eax
0x1801290f3  mov     rbx, [rsp+0A8h+string]
0x1801290f8  test    eax, eax
0x1801290fa  js      short loc_18012913A
0x1801290fc  xor     edx, edx; length
0x1801290fe  mov     rcx, rbx; string
0x180129101  call    cs:__imp_WindowsGetStringRawBuffer
0x180129107  mov     r8, rax; unsigned __int16 *
0x18012910a  mov     rdx, r12; unsigned __int16 *
0x18012910d  mov     rcx, r15; unsigned __int16 *
0x180129110  call    ?FetchImageFromNetworkAndSaveToFile@@YAJPEBG00@Z; FetchImageFromNetworkAndSaveToFile(ushort const *,ushort const *,ushort const *)
0x180129115  mov     esi, eax
0x180129117  test    eax, eax
0x180129119  js      short loc_180129125
0x18012911b  mov     rax, rbx
0x18012911e  xor     ebx, ebx
0x180129120  mov     [r14], rax
0x180129123  jmp     short loc_18012913A
0x180129125  xor     edx, edx; length
0x180129127  mov     rcx, rbx; string
0x18012912a  call    cs:__imp_WindowsGetStringRawBuffer
0x180129130  mov     rcx, rax; lpFileName
0x180129133  call    cs:__imp_DeleteFileW
0x180129139  nop
0x18012913a  mov     rcx, rbx; string
0x18012913d  call    cs:__imp_WindowsDeleteString
0x180129143  nop
0x180129144  lea     rcx, [rsp+0A8h+var_80]
0x180129149  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x18012914e  nop
0x18012914f  mov     [rsp+0A8h+var_78], rdi
0x180129154  lea     rcx, [rsp+0A8h+var_78]
0x180129159  call    ?Close@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(void)
0x18012915e  mov     eax, esi
0x180129160  jmp     loc_180129252
0x180129165  mov     [rsp+0A8h+var_80], 0FFFFFFFFFFFFFFFFh
0x18012916e  test    rbx, rbx
0x180129171  jz      short loc_1801291CF
0x180129173  lea     rdx, [rsp+0A8h+string]
0x180129178  lea     rcx, [rsp+0A8h+var_58]
0x18012917d  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180129182  nop
0x180129183  mov     rdx, [rax+18h]
0x180129187  lea     rcx, [rsp+0A8h+var_68]
0x18012918c  call    ?GetTokenForSid@TokenHelpers@@YA?AV?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@PEAUHSTRING__@@@Z; TokenHelpers::GetTokenForSid(HSTRING__ *)
0x180129191  nop
0x180129192  mov     rdx, [rax+8]
0x180129196  lea     rcx, [rsp+0A8h+var_78]
0x18012919b  call    ?impersonate_token@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@PEAX@Z; wil::impersonate_token(void *)
0x1801291a0  mov     rdx, rax
0x1801291a3  lea     rcx, [rsp+0A8h+var_80]
0x1801291a8  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>> &&)
0x1801291ad  lea     rcx, [rsp+0A8h+var_78]
0x1801291b2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x1801291b7  nop
0x1801291b8  lea     rdi, ??_7?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable'
0x1801291bf  mov     [rsp+0A8h+var_68], rdi
0x1801291c4  lea     rcx, [rsp+0A8h+var_68]
0x1801291c9  call    ?Close@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(void)
0x1801291ce  nop
0x1801291cf  xor     ecx, ecx; string
0x1801291d1  call    cs:__imp_WindowsDeleteString
0x1801291d7  mov     [rsp+0A8h+string], 0
0x1801291e0  lea     r8, [rsp+0A8h+string]; HSTRING *
0x1801291e5  mov     rdx, rbx; unsigned __int16 *
0x1801291e8  call    ?GetTempFilePath_Deprecated@@YAJPEBG0PEAPEAUHSTRING__@@@Z; GetTempFilePath_Deprecated(ushort const *,ushort const *,HSTRING__ * *)
0x1801291ed  mov     edi, eax
0x1801291ef  mov     rbx, [rsp+0A8h+string]
0x1801291f4  test    eax, eax
0x1801291f6  js      short loc_180129236
0x1801291f8  xor     edx, edx; length
0x1801291fa  mov     rcx, rbx; string
0x1801291fd  call    cs:__imp_WindowsGetStringRawBuffer
0x180129203  mov     r8, rax; unsigned __int16 *
0x180129206  mov     rdx, r12; unsigned __int16 *
0x180129209  mov     rcx, r15; unsigned __int16 *
0x18012920c  call    ?FetchImageFromNetworkAndSaveToFile@@YAJPEBG00@Z; FetchImageFromNetworkAndSaveToFile(ushort const *,ushort const *,ushort const *)
0x180129211  mov     edi, eax
0x180129213  test    eax, eax
0x180129215  js      short loc_180129221
0x180129217  mov     rax, rbx
0x18012921a  xor     ebx, ebx
0x18012921c  mov     [r14], rax
0x18012921f  jmp     short loc_180129236
0x180129221  xor     edx, edx; length
0x180129223  mov     rcx, rbx; string
0x180129226  call    cs:__imp_WindowsGetStringRawBuffer
0x18012922c  mov     rcx, rax; lpFileName
0x18012922f  call    cs:__imp_DeleteFileW
0x180129235  nop
0x180129236  mov     rcx, rbx; string
0x180129239  call    cs:__imp_WindowsDeleteString
0x18012923f  nop
0x180129240  lea     rcx, [rsp+0A8h+var_80]
0x180129245  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x18012924a  mov     eax, edi
0x18012924c  jmp     short loc_180129252
0x18012924e  mov     eax, dword ptr [rsp+0A8h+string]
0x180129252  mov     rcx, [rsp+0A8h+var_38]
0x180129257  xor     rcx, rsp; StackCookie
0x18012925a  call    __security_check_cookie
0x18012925f  mov     rbx, [rsp+0A8h+arg_0]
0x180129267  add     rsp, 80h
0x18012926e  pop     r15
0x180129270  pop     r14
0x180129272  pop     r12
0x180129274  pop     rdi
0x180129275  pop     rsi
0x180129276  retn
```
