# CSearchScopeSelectorService::Invoke(IInspectable *,Windows::UI::Search::Internal::Common::IScopeChangedEventArgs *)

- ea: `0x180022a60`
- end: `0x180022bfc`
- name: `?Invoke@CSearchScopeSelectorService@@UEAAJPEAUIInspectable@@PEAUIScopeChangedEventArgs@Common@Internal@Search@UI@Windows@@@Z`
- size: `412`
- prototype: `__int64 __fastcall(CSearchScopeSelectorService *__hidden this, struct IInspectable *, struct Windows::UI::Search::Internal::Common::IScopeChangedEventArgs *)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180007b3c`
- `0x18000f2a8`
- `0x180022a60`
- `0x18002590c`
- `0x180026454`
- `0x180030f9c`
- `0x180076c50`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180022a9a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180022ad2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180022bc8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180022bd3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180022a9a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180022ad2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180022bc8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180022bd3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180022aff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180022b0e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180022b36`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180022aff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180022b0e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180022b36`
- `PROPSYS!__imp_PropVariantToWinRTPropertyValue` at `0x180022b78`
- `PROPSYS!__imp_PropVariantToWinRTPropertyValue` at `0x180022b78`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CSearchScopeSelectorService::Invoke(
        CSearchScopeSelectorService *this,
        struct IInspectable *a2,
        struct Windows::UI::Search::Internal::Common::IScopeChangedEventArgs *a3)
{
  __int64 (__fastcall *v5)(struct Windows::UI::Search::Internal::Common::IScopeChangedEventArgs *, HSTRING *); // rbx
  int v6; // edi
  __int64 (__fastcall *v7)(struct Windows::UI::Search::Internal::Common::IScopeChangedEventArgs *, HSTRING *); // rbx
  const unsigned __int16 *StringRawBuffer; // rbx
  const WCHAR *v9; // rax
  const WCHAR *v10; // rax
  void *v11; // rbx
  __int64 v12; // rdx
  __int64 v13; // rcx
  HSTRING v15; // [rsp+30h] [rbp-40h] BYREF
  void *ppv; // [rsp+38h] [rbp-38h] BYREF
  HSTRING string; // [rsp+40h] [rbp-30h] BYREF
  HSTRING_HEADER propvar; // [rsp+48h] [rbp-28h] BYREF
  __int64 v19; // [rsp+60h] [rbp-10h]

  v15 = 0;
  v5 = *(__int64 (__fastcall **)(struct Windows::UI::Search::Internal::Common::IScopeChangedEventArgs *, HSTRING *))(*(_QWORD *)a3 + 48LL);
  WindowsDeleteString(0);
  v15 = 0;
  v6 = v5(a3, &v15);
  if ( v6 >= 0 )
  {
    string = 0;
    v7 = *(__int64 (__fastcall **)(struct Windows::UI::Search::Internal::Common::IScopeChangedEventArgs *, HSTRING *))(*(_QWORD *)a3 + 56LL);
    WindowsDeleteString(0);
    string = 0;
    v6 = v7(a3, &string);
    if ( v6 >= 0 )
    {
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      v9 = WindowsGetStringRawBuffer(v15, 0);
      v6 = CSearchScopeSelectorService::_SetCurrentScope(
             (CSearchScopeSelectorService *)((char *)this - 48),
             v9,
             StringRawBuffer,
             1);
      if ( v6 >= 0 )
      {
        v10 = WindowsGetStringRawBuffer(v15, 0);
        if ( (unsigned int)IsAppScope(v10) )
        {
          ppv = 0;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&ppv);
          LOWORD(propvar.Reserved.Reserved1) = 11;
          *(_WORD *)&propvar.Reserved.Reserved2[8] = -1;
          if ( PropVariantToWinRTPropertyValue(
                 &propvar.Reserved.Reserved1,
                 &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90,
                 &ppv) >= 0 )
          {
            v11 = ppv;
            v19 = 0;
            Microsoft::WRL::Wrappers::HStringReference::CreateReference(&propvar, L"RestoreScope", 0xDu, 0xCu);
            SetSearchViewProperty(v13, v12, *((_QWORD *)this - 4), v19, v11);
          }
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&ppv);
        }
      }
    }
    WindowsDeleteString(string);
  }
  WindowsDeleteString(v15);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180022a60  mov     [rsp-18h+arg_8], rbx
0x180022a65  mov     [rsp-18h+arg_18], rsi
0x180022a6a  push    rbp
0x180022a6b  push    rdi
0x180022a6c  push    r14
0x180022a6e  mov     rbp, rsp
0x180022a71  sub     rsp, 70h
0x180022a75  mov     rax, cs:__security_cookie
0x180022a7c  xor     rax, rsp
0x180022a7f  mov     [rbp+var_8], rax
0x180022a83  mov     rsi, r8
0x180022a86  mov     r14, rcx
0x180022a89  mov     [rbp+var_40], 0
0x180022a91  mov     rax, [r8]
0x180022a94  mov     rbx, [rax+30h]
0x180022a98  xor     ecx, ecx; string
0x180022a9a  call    cs:__imp_WindowsDeleteString
0x180022aa0  mov     [rbp+var_40], 0
0x180022aa8  lea     rdx, [rbp+var_40]
0x180022aac  mov     rcx, rsi
0x180022aaf  mov     rax, rbx
0x180022ab2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022ab7  mov     edi, eax
0x180022ab9  test    eax, eax
0x180022abb  js      loc_180022BCF
0x180022ac1  mov     [rbp+string], 0
0x180022ac9  mov     rax, [rsi]
0x180022acc  mov     rbx, [rax+38h]
0x180022ad0  xor     ecx, ecx; string
0x180022ad2  call    cs:__imp_WindowsDeleteString
0x180022ad8  mov     [rbp+string], 0
0x180022ae0  lea     rdx, [rbp+string]
0x180022ae4  mov     rcx, rsi
0x180022ae7  mov     rax, rbx
0x180022aea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022aef  mov     edi, eax
0x180022af1  test    eax, eax
0x180022af3  js      loc_180022BC4
0x180022af9  xor     edx, edx; length
0x180022afb  mov     rcx, [rbp+string]; string
0x180022aff  call    cs:__imp_WindowsGetStringRawBuffer
0x180022b05  mov     rbx, rax
0x180022b08  xor     edx, edx; length
0x180022b0a  mov     rcx, [rbp+var_40]; string
0x180022b0e  call    cs:__imp_WindowsGetStringRawBuffer
0x180022b14  lea     rcx, [r14-30h]; this
0x180022b18  mov     r9b, 1; bool
0x180022b1b  mov     r8, rbx; unsigned __int16 *
0x180022b1e  mov     rdx, rax; lpString1
0x180022b21  call    ?_SetCurrentScope@CSearchScopeSelectorService@@AEAAJPEBG0_N@Z; CSearchScopeSelectorService::_SetCurrentScope(ushort const *,ushort const *,bool)
0x180022b26  mov     edi, eax
0x180022b28  test    eax, eax
0x180022b2a  js      loc_180022BC4
0x180022b30  xor     edx, edx; length
0x180022b32  mov     rcx, [rbp+var_40]; string
0x180022b36  call    cs:__imp_WindowsGetStringRawBuffer
0x180022b3c  mov     rcx, rax; lpString1
0x180022b3f  call    IsAppScope
0x180022b44  test    eax, eax
0x180022b46  jz      short loc_180022BC4
0x180022b48  mov     [rbp+ppv], 0
0x180022b50  lea     rcx, [rbp+ppv]
0x180022b54  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180022b59  mov     eax, 0Bh
0x180022b5e  mov     word ptr [rbp+propvar], ax
0x180022b62  or      eax, 0FFFFFFFFh
0x180022b65  mov     [rbp+var_20], ax
0x180022b69  lea     r8, [rbp+ppv]; ppv
0x180022b6d  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; riid
0x180022b74  lea     rcx, [rbp+propvar]; propvar
0x180022b78  call    cs:__imp_PropVariantToWinRTPropertyValue
0x180022b7e  test    eax, eax
0x180022b80  js      short loc_180022BBA
0x180022b82  mov     rbx, [rbp+ppv]
0x180022b86  mov     [rbp+var_10], 0
0x180022b8e  mov     r9d, 0Ch; unsigned int
0x180022b94  lea     r8d, [r9+1]; unsigned int
0x180022b98  lea     rdx, aRestorescope; "RestoreScope"
0x180022b9f  lea     rcx, [rbp+propvar]; hstringHeader
0x180022ba3  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180022ba8  mov     [rsp+70h+var_50], rbx
0x180022bad  mov     r9, [rbp+var_10]
0x180022bb1  mov     r8, [r14-20h]
0x180022bb5  call    SetSearchViewProperty
0x180022bba  lea     rcx, [rbp+ppv]
0x180022bbe  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x180022bc3  nop
0x180022bc4  mov     rcx, [rbp+string]; string
0x180022bc8  call    cs:__imp_WindowsDeleteString
0x180022bce  nop
0x180022bcf  mov     rcx, [rbp+var_40]; string
0x180022bd3  call    cs:__imp_WindowsDeleteString
0x180022bd9  mov     eax, edi
0x180022bdb  mov     rcx, [rbp+var_8]
0x180022bdf  xor     rcx, rsp; StackCookie
0x180022be2  call    __security_check_cookie
0x180022be7  lea     r11, [rsp+70h+var_s0]
0x180022bec  mov     rbx, [r11+28h]
0x180022bf0  mov     rsi, [r11+38h]
0x180022bf4  mov     rsp, r11
0x180022bf7  pop     r14
0x180022bf9  pop     rdi
0x180022bfa  pop     rbp
0x180022bfb  retn
```
