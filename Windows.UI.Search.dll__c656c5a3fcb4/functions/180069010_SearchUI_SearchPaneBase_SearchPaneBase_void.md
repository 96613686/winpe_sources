# SearchUI::SearchPaneBase::SearchPaneBase(void)

- ea: `0x180069010`
- end: `0x180069100`
- name: `??0SearchPaneBase@SearchUI@@IE$AAA@XZ`
- size: `240`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callers

- `0x1800630a4`

## callees

- `0x180005124`
- `0x180068f30`
- `0x180069010`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800690cb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800690cb`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800690af`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800690af`

## string_xrefs

- `0x1800690c1`: `SetTextServicesDpiCalculationOverride`
- `0x1800690a8`: `MsftEdit.dll`

## pseudocode

```c
_QWORD *__fastcall SearchUI::SearchPaneBase::SearchPaneBase(_QWORD *a1)
{
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  FARPROC v4; // rbx

  *a1 = &SearchUI::SearchPaneBase::`vftable'{for `SearchUI::__ISearchPaneBasePublicNonVirtuals'};
  a1[1] = &SearchUI::SearchPaneBase::`vftable'{for `Platform::IDisposable'};
  a1[8] = &SearchUI::SearchPaneBase::`vftable'{for `Platform::Object's `Windows::UI::Xaml::Controls::Page'};
  a1[3] = &SearchUI::SearchPaneBase::`vftable'{for `Windows::UI::Xaml::Controls::UserControl'};
  a1[2] = &SearchUI::SearchPaneBase::`vftable'{for `Windows::UI::Xaml::Controls::IPage'};
  a1[44] = &SearchUI::SearchPaneBase::`vftable'{for `Windows::UI::Search::Internal::SearchPane::ISearchPane'};
  a1[45] = &SearchUI::SearchPaneBase::`vftable'{for `__abi_IUnknown'};
  a1[46] = &SearchUI::SearchPaneBase::`vftable'{for `Platform::Object's `Platform::Details::IWeakReferenceSource'};
  __abi_FTMWeakRefData::__abi_FTMWeakRefData(a1 + 49);
  a1[48] = 0;
  Windows::UI::Xaml::Controls::Page::Page(a1 + 2);
  Library = LoadLibraryExW(L"MsftEdit.dll", 0, 0);
  a1[47] = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "SetTextServicesDpiCalculationOverride");
    v4 = ProcAddress;
    if ( ProcAddress )
    {
      if ( ((int (__fastcall *)(void (__fastcall *)(void *, int *, int *), _QWORD))ProcAddress)(InitializeDPI, 0) >= 0 )
        a1[48] = v4;
    }
  }
  return a1;
}

```

## disassembly

```asm
0x180069010  mov     [rsp+arg_8], rbx
0x180069015  mov     [rsp+arg_0], rcx
0x18006901a  push    rdi
0x18006901b  sub     rsp, 20h
0x18006901f  mov     rdi, rcx
0x180069022  lea     rax, ??_7SearchPaneBase@SearchUI@@6B__ISearchPaneBasePublicNonVirtuals@1@@; const SearchUI::SearchPaneBase::`vftable'{for `SearchUI::__ISearchPaneBasePublicNonVirtuals'}
0x180069029  mov     [rcx], rax
0x18006902c  lea     rax, ??_7SearchPaneBase@SearchUI@@6BIDisposable@Platform@@@; const SearchUI::SearchPaneBase::`vftable'{for `Platform::IDisposable'}
0x180069033  mov     [rcx+8], rax
0x180069037  lea     rax, ??_7SearchPaneBase@SearchUI@@6BObject@Platform@@Page@Controls@Xaml@UI@Windows@@@; const SearchUI::SearchPaneBase::`vftable'{for `Platform::Object's `Windows::UI::Xaml::Controls::Page'}
0x18006903e  mov     [rcx+40h], rax
0x180069042  lea     rax, ??_7SearchPaneBase@SearchUI@@6BUserControl@Controls@Xaml@UI@Windows@@@; const SearchUI::SearchPaneBase::`vftable'{for `Windows::UI::Xaml::Controls::UserControl'}
0x180069049  mov     [rcx+18h], rax
0x18006904d  lea     rax, ??_7SearchPaneBase@SearchUI@@6BIPage@Controls@Xaml@UI@Windows@@@; const SearchUI::SearchPaneBase::`vftable'{for `Windows::UI::Xaml::Controls::IPage'}
0x180069054  mov     [rcx+10h], rax
0x180069058  lea     rax, ??_7SearchPaneBase@SearchUI@@6BISearchPane@SearchPane@Internal@Search@UI@Windows@@@; const SearchUI::SearchPaneBase::`vftable'{for `Windows::UI::Search::Internal::SearchPane::ISearchPane'}
0x18006905f  mov     [rcx+160h], rax
0x180069066  lea     rax, ??_7SearchPaneBase@SearchUI@@6B__abi_IUnknown@@@; const SearchUI::SearchPaneBase::`vftable'{for `__abi_IUnknown'}
0x18006906d  mov     [rcx+168h], rax
0x180069074  lea     rax, ??_7SearchPaneBase@SearchUI@@6BObject@Platform@@IWeakReferenceSource@Details@3@@; const SearchUI::SearchPaneBase::`vftable'{for `Platform::Object's `Platform::Details::IWeakReferenceSource'}
0x18006907b  mov     [rcx+170h], rax
0x180069082  add     rcx, 188h
0x180069089  call    ??0__abi_FTMWeakRefData@@QEAA@PE$AAVObject@Platform@@W4CallbackContext@2@@Z; __abi_FTMWeakRefData::__abi_FTMWeakRefData(Platform::Object *,Platform::CallbackContext)
0x18006908e  nop
0x18006908f  mov     qword ptr [rdi+180h], 0
0x18006909a  lea     rcx, [rdi+10h]
0x18006909e  call    ??0Page@Controls@Xaml@UI@Windows@@QE$AAA@XZ; Windows::UI::Xaml::Controls::Page::Page(void)
0x1800690a3  xor     r8d, r8d; dwFlags
0x1800690a6  xor     edx, edx; hFile
0x1800690a8  lea     rcx, LibFileName; "MsftEdit.dll"
0x1800690af  call    cs:__imp_LoadLibraryExW
0x1800690b5  mov     [rdi+178h], rax
0x1800690bc  test    rax, rax
0x1800690bf  jz      short loc_1800690F2
0x1800690c1  lea     rdx, aSettextservice; "SetTextServicesDpiCalculationOverride"
0x1800690c8  mov     rcx, rax; hModule
0x1800690cb  call    cs:__imp_GetProcAddress
0x1800690d1  mov     rbx, rax
0x1800690d4  test    rax, rax
0x1800690d7  jz      short loc_1800690F2
0x1800690d9  xor     edx, edx
0x1800690db  lea     rcx, ?InitializeDPI@@YAXPEAXPEAJ1@Z; InitializeDPI(void *,long *,long *)
0x1800690e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800690e7  test    eax, eax
0x1800690e9  js      short loc_1800690F2
0x1800690eb  mov     [rdi+180h], rbx
0x1800690f2  mov     rax, rdi
0x1800690f5  mov     rbx, [rsp+28h+arg_8]
0x1800690fa  add     rsp, 20h
0x1800690fe  pop     rdi
0x1800690ff  retn
```
