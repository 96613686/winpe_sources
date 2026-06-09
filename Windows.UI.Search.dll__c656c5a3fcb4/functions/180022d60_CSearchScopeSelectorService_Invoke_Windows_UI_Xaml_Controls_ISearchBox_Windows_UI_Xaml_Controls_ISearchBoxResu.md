# CSearchScopeSelectorService::Invoke(Windows::UI::Xaml::Controls::ISearchBox *,Windows::UI::Xaml::Controls::ISearchBoxResultSuggestionChosenEventArgs *)

- ea: `0x180022d60`
- end: `0x180022e77`
- name: `?Invoke@CSearchScopeSelectorService@@UEAAJPEAUISearchBox@Controls@Xaml@UI@Windows@@PEAUISearchBoxResultSuggestionChosenEventArgs@3456@@Z`
- size: `279`
- prototype: `__int64 __fastcall(CSearchScopeSelectorService *__hidden this, struct Windows::UI::Xaml::Controls::ISearchBox *, struct Windows::UI::Xaml::Controls::ISearchBoxResultSuggestionChosenEventArgs *)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x180016ca0`
- `0x18001f680`
- `0x1800221c4`
- `0x180022d60`
- `0x180026454`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180022da1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180022e1f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180022da1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180022e1f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180022d7d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180022d7d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSearchScopeSelectorService::Invoke(
        HSTRING *this,
        struct Windows::UI::Xaml::Controls::ISearchBox *a2,
        struct Windows::UI::Xaml::Controls::ISearchBoxResultSuggestionChosenEventArgs *a3)
{
  int v5; // ebx
  const WCHAR *StringRawBuffer; // rax
  __int64 (__fastcall *v7)(struct Windows::UI::Xaml::Controls::ISearchBoxResultSuggestionChosenEventArgs *, HSTRING *); // rbx
  struct IUnknown *v8; // rdx
  unsigned int v9; // r8d
  _QWORD v11[3]; // [rsp+20h] [rbp-18h] BYREF
  int v12; // [rsp+40h] [rbp+8h] BYREF
  HSTRING string; // [rsp+58h] [rbp+20h] BYREF

  v5 = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(this[3], 0);
  if ( (unsigned int)IsAppScope(StringRawBuffer) )
  {
    string = 0;
    v7 = *(__int64 (__fastcall **)(struct Windows::UI::Xaml::Controls::ISearchBoxResultSuggestionChosenEventArgs *, HSTRING *))(*(_QWORD *)a3 + 48LL);
    WindowsDeleteString(0);
    string = 0;
    v5 = v7(a3, &string);
    if ( v5 >= 0 )
    {
      v12 = 0;
      v5 = (*(__int64 (__fastcall **)(struct Windows::UI::Xaml::Controls::ISearchBoxResultSuggestionChosenEventArgs *, int *))(*(_QWORD *)a3 + 56LL))(
             a3,
             &v12);
      if ( v5 >= 0 )
      {
        v11[0] = &string;
        v11[1] = &v12;
        v5 = CSearchScopeSelectorService::_InvokeOnBroker<_lambda_4308d9ea5880b5e4ebf2343abf1ad045_>(
               this - 9,
               (__int64)v11);
        if ( v5 >= 0 )
          Windows::Internal::IUnknown_TryToReturnActivation((Windows::Internal *)*(this - 7), v8, v9);
      }
    }
    WindowsDeleteString(string);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 188) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 185) >= 4u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 22),
      12,
      &WPP_9ff13e183948381501d20d2536b3ba22_Traceguids,
      (unsigned int)v5);
  }
  return 0;
}

```

## disassembly

```asm
0x180022d60  mov     [rsp+arg_8], rbx
0x180022d65  mov     [rsp+arg_10], rsi
0x180022d6a  push    rdi
0x180022d6b  sub     rsp, 30h
0x180022d6f  mov     rsi, r8
0x180022d72  mov     rdi, rcx
0x180022d75  xor     ebx, ebx
0x180022d77  xor     edx, edx; length
0x180022d79  mov     rcx, [rcx+18h]; string
0x180022d7d  call    cs:__imp_WindowsGetStringRawBuffer
0x180022d83  mov     rcx, rax; lpString1
0x180022d86  call    IsAppScope
0x180022d8b  test    eax, eax
0x180022d8d  jz      loc_180022E25
0x180022d93  mov     [rsp+38h+string], rbx
0x180022d98  mov     rax, [rsi]
0x180022d9b  mov     rbx, [rax+30h]
0x180022d9f  xor     ecx, ecx; string
0x180022da1  call    cs:__imp_WindowsDeleteString
0x180022da7  mov     [rsp+38h+string], 0
0x180022db0  lea     rdx, [rsp+38h+string]
0x180022db5  mov     rcx, rsi
0x180022db8  mov     rax, rbx
0x180022dbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022dc0  mov     ebx, eax
0x180022dc2  test    eax, eax
0x180022dc4  js      short loc_180022E1A
0x180022dc6  mov     [rsp+38h+arg_0], 0
0x180022dce  mov     rax, [rsi]
0x180022dd1  lea     rdx, [rsp+38h+arg_0]
0x180022dd6  mov     rcx, rsi
0x180022dd9  mov     rax, [rax+38h]
0x180022ddd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022de2  mov     ebx, eax
0x180022de4  test    eax, eax
0x180022de6  js      short loc_180022E1A
0x180022de8  lea     rax, [rsp+38h+string]
0x180022ded  mov     [rsp+38h+var_18], rax
0x180022df2  lea     rax, [rsp+38h+arg_0]
0x180022df7  mov     [rsp+38h+var_10], rax
0x180022dfc  lea     rcx, [rdi-48h]; this
0x180022e00  lea     rdx, [rsp+38h+var_18]
0x180022e05  call    ??$_InvokeOnBroker@V_lambda_4308d9ea5880b5e4ebf2343abf1ad045_@@@CSearchScopeSelectorService@@AEAAJAEBV_lambda_4308d9ea5880b5e4ebf2343abf1ad045_@@@Z; CSearchScopeSelectorService::_InvokeOnBroker<_lambda_4308d9ea5880b5e4ebf2343abf1ad045_>(_lambda_4308d9ea5880b5e4ebf2343abf1ad045_ const &)
0x180022e0a  mov     ebx, eax
0x180022e0c  test    eax, eax
0x180022e0e  js      short loc_180022E1A
0x180022e10  mov     rcx, [rdi-38h]; this
0x180022e14  call    ?IUnknown_TryToReturnActivation@Internal@Windows@@YAXPEAUIUnknown@@K@Z; Windows::Internal::IUnknown_TryToReturnActivation(IUnknown *,ulong)
0x180022e19  nop
0x180022e1a  mov     rcx, [rsp+38h+string]; string
0x180022e1f  call    cs:__imp_WindowsDeleteString
0x180022e25  lea     rax, WPP_GLOBAL_Control
0x180022e2c  mov     rcx, cs:WPP_GLOBAL_Control
0x180022e33  cmp     rcx, rax
0x180022e36  jz      short loc_180022E65
0x180022e38  test    byte ptr [rcx+0BCh], 1
0x180022e3f  jz      short loc_180022E65
0x180022e41  cmp     byte ptr [rcx+0B9h], 4
0x180022e48  jb      short loc_180022E65
0x180022e4a  mov     edx, 0Ch
0x180022e4f  mov     r9d, ebx
0x180022e52  lea     r8, WPP_9ff13e183948381501d20d2536b3ba22_Traceguids
0x180022e59  mov     rcx, [rcx+0B0h]
0x180022e60  call    WPP_SF_d
0x180022e65  xor     eax, eax
0x180022e67  mov     rbx, [rsp+38h+arg_8]
0x180022e6c  mov     rsi, [rsp+38h+arg_10]
0x180022e71  add     rsp, 30h
0x180022e75  pop     rdi
0x180022e76  retn
```
