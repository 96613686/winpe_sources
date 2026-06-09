# CSearchPaneTypeToSearchService::_OnSearchBoxQueryChanged(Windows::UI::Xaml::Controls::ISearchBox *,Windows::UI::Xaml::Controls::ISearchBoxQueryChangedEventArgs *)

- ea: `0x180028780`
- end: `0x180028841`
- name: `?_OnSearchBoxQueryChanged@CSearchPaneTypeToSearchService@@AEAAJPEAUISearchBox@Controls@Xaml@UI@Windows@@PEAUISearchBoxQueryChangedEventArgs@3456@@Z`
- size: `193`
- prototype: `__int64 __fastcall(CSearchPaneTypeToSearchService *__hidden this, struct Windows::UI::Xaml::Controls::ISearchBox *, struct Windows::UI::Xaml::Controls::ISearchBoxQueryChangedEventArgs *)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180020e1c`
- `0x1800273e0`
- `0x180028320`
- `0x180028780`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800287b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028816`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002882b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800287b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028816`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002882b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSearchPaneTypeToSearchService::_OnSearchBoxQueryChanged(
        CSearchPaneTypeToSearchService *this,
        struct Windows::UI::Xaml::Controls::ISearchBox *a2,
        struct Windows::UI::Xaml::Controls::ISearchBoxQueryChangedEventArgs *a3)
{
  int v5; // esi
  __int64 (__fastcall *v6)(struct Windows::UI::Xaml::Controls::ISearchBoxQueryChangedEventArgs *, Microsoft::WRL::Wrappers::Details **); // rbx
  HSTRING v7; // r8
  Microsoft::WRL::Wrappers::Details *v8; // rcx
  HSTRING v9; // r8
  Microsoft::WRL::Wrappers::Details **v10; // rbx
  int v12; // [rsp+40h] [rbp+8h] BYREF
  Microsoft::WRL::Wrappers::Details *v13; // [rsp+58h] [rbp+20h] BYREF

  v5 = 0;
  if ( Microsoft::WRL::EventSource<IStartMenuXAMLViewActivationEventHandler,Microsoft::WRL::InvokeModeOptions<-2>>::GetSize(
         (char *)this + 168,
         a2) )
  {
    v13 = 0;
    v6 = *(__int64 (__fastcall **)(struct Windows::UI::Xaml::Controls::ISearchBoxQueryChangedEventArgs *, Microsoft::WRL::Wrappers::Details **))(*(_QWORD *)a3 + 48LL);
    WindowsDeleteString(0);
    v13 = 0;
    v5 = v6(a3, &v13);
    v8 = v13;
    if ( v5 >= 0 )
    {
      v10 = (Microsoft::WRL::Wrappers::Details **)((char *)this + 200);
      if ( !(unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(v13, 0, v7)
        && (unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(*v10, 0, v9) )
      {
        v12 = 1;
        CSearchPaneTypeToSearchService::_FireActivationChangedOnBackgroundThread(
          this,
          (const struct StartMenuXAMLViewActivationEventArgs *)&v12);
      }
      WindowsDeleteString((HSTRING)*v10);
      *v10 = v13;
      v8 = 0;
      v13 = 0;
    }
    WindowsDeleteString((HSTRING)v8);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180028780  mov     [rsp+arg_8], rbx
0x180028785  push    rsi
0x180028786  push    rdi
0x180028787  push    r14
0x180028789  sub     rsp, 20h
0x18002878d  mov     r14, r8
0x180028790  mov     rdi, rcx
0x180028793  xor     esi, esi
0x180028795  add     rcx, 0A8h
0x18002879c  call    ?GetSize@?$EventSource@UIStartMenuXAMLViewActivationEventHandler@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@QEBA_KXZ; Microsoft::WRL::EventSource<IStartMenuXAMLViewActivationEventHandler,Microsoft::WRL::InvokeModeOptions<-2>>::GetSize(void)
0x1800287a1  test    rax, rax
0x1800287a4  jz      loc_180028831
0x1800287aa  mov     [rsp+38h+arg_18], rsi
0x1800287af  mov     rax, [r14]
0x1800287b2  mov     rbx, [rax+30h]
0x1800287b6  xor     ecx, ecx; string
0x1800287b8  call    cs:__imp_WindowsDeleteString
0x1800287be  mov     [rsp+38h+arg_18], rsi
0x1800287c3  lea     rdx, [rsp+38h+arg_18]
0x1800287c8  mov     rcx, r14
0x1800287cb  mov     rax, rbx
0x1800287ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800287d3  mov     esi, eax
0x1800287d5  mov     rcx, [rsp+38h+arg_18]; this
0x1800287da  test    eax, eax
0x1800287dc  js      short loc_18002882B
0x1800287de  xor     edx, edx; HSTRING
0x1800287e0  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x1800287e5  lea     rbx, [rdi+0C8h]
0x1800287ec  test    eax, eax
0x1800287ee  jnz     short loc_180028813
0x1800287f0  xor     edx, edx; HSTRING
0x1800287f2  mov     rcx, [rbx]; this
0x1800287f5  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x1800287fa  test    eax, eax
0x1800287fc  jz      short loc_180028813
0x1800287fe  mov     [rsp+38h+arg_0], 1
0x180028806  lea     rdx, [rsp+38h+arg_0]; struct StartMenuXAMLViewActivationEventArgs *
0x18002880b  mov     rcx, rdi; this
0x18002880e  call    ?_FireActivationChangedOnBackgroundThread@CSearchPaneTypeToSearchService@@AEAAXAEBUStartMenuXAMLViewActivationEventArgs@@@Z; CSearchPaneTypeToSearchService::_FireActivationChangedOnBackgroundThread(StartMenuXAMLViewActivationEventArgs const &)
0x180028813  mov     rcx, [rbx]; string
0x180028816  call    cs:__imp_WindowsDeleteString
0x18002881c  mov     rax, [rsp+38h+arg_18]
0x180028821  mov     [rbx], rax
0x180028824  xor     ecx, ecx; string
0x180028826  mov     [rsp+38h+arg_18], rcx
0x18002882b  call    cs:__imp_WindowsDeleteString
0x180028831  mov     eax, esi
0x180028833  mov     rbx, [rsp+38h+arg_8]
0x180028838  add     rsp, 20h
0x18002883c  pop     r14
0x18002883e  pop     rdi
0x18002883f  pop     rsi
0x180028840  retn
```
