# winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportJobHandler::CancelPrintJobDesktop(void)

- ea: `0x18004f290`
- end: `0x18004f31f`
- name: `?CancelPrintJobDesktop@PrintSupportJobHandler@implementation@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@AEAAXXZ`
- size: `143`
- prototype: `void __fastcall(winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportJobHandler *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004f088`

## callees

- `0x1800129dc`
- `0x1800213ac`
- `0x180023664`
- `0x18004f290`

## import_xrefs

- `WINSPOOL!OpenPrinterW` at `0x18004f2b6`
- `WINSPOOL!OpenPrinterW` at `0x18004f2b6`
- `WINSPOOL!SetJobW` at `0x18004f2dc`
- `WINSPOOL!SetJobW` at `0x18004f2dc`

## string_xrefs

- `0x18004f2fb`: `onecoreuap\printscan\print\workflow\broker\psa_lib\printsupportjobhandler.cpp`
- `0x18004f30d`: `onecoreuap\printscan\print\workflow\broker\psa_lib\printsupportjobhandler.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportJobHandler::CancelPrintJobDesktop(
        winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportJobHandler *this)
{
  WCHAR *v2; // rax
  const char *v3; // r9
  const char *v4; // r9
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  HANDLE phPrinter; // [rsp+40h] [rbp+8h] BYREF

  phPrinter = 0;
  v2 = (WCHAR *)winrt::hstring::c_str((winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportJobHandler *)((char *)this + 24));
  if ( !OpenPrinterW(v2, &phPrinter, 0) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x99,
      (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\psa_lib\\printsupportjobhandler.cpp",
      v3);
  if ( !SetJobW(phPrinter, *((_DWORD *)this + 8), 0, 0, 5u) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x9A,
      (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\psa_lib\\printsupportjobhandler.cpp",
      v4);
  wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int ClosePrinter(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int ClosePrinter(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&phPrinter);
}

```

## disassembly

```asm
0x18004f290  push    rbx
0x18004f292  sub     rsp, 30h
0x18004f296  mov     rbx, rcx
0x18004f299  mov     [rsp+38h+phPrinter], 0
0x18004f2a2  add     rcx, 18h; this
0x18004f2a6  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x18004f2ab  xor     r8d, r8d; pDefault
0x18004f2ae  lea     rdx, [rsp+38h+phPrinter]; phPrinter
0x18004f2b3  mov     rcx, rax; pPrinterName
0x18004f2b6  call    cs:__imp_OpenPrinterW
0x18004f2bc  mov     rcx, [rsp+38h]; this
0x18004f2c1  test    eax, eax
0x18004f2c3  jz      short loc_18004F30D
0x18004f2c5  mov     edx, [rbx+20h]; JobId
0x18004f2c8  nop
0x18004f2c9  mov     [rsp+38h+Command], 5; Command
0x18004f2d1  xor     r9d, r9d; pJob
0x18004f2d4  xor     r8d, r8d; Level
0x18004f2d7  mov     rcx, [rsp+38h+phPrinter]; hPrinter
0x18004f2dc  call    cs:__imp_SetJobW
0x18004f2e2  mov     rcx, [rsp+38h]; this
0x18004f2e7  test    eax, eax
0x18004f2e9  jz      short loc_18004F2FB
0x18004f2eb  lea     rcx, [rsp+38h+phPrinter]
0x18004f2f0  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?ClosePrinter@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&ClosePrinter(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&ClosePrinter(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18004f2f5  add     rsp, 30h
0x18004f2f9  pop     rbx
0x18004f2fa  retn
0x18004f2fb  lea     r8, aOnecoreuapPrin_5; "onecoreuap\\printscan\\print\\workflow"...
0x18004f302  mov     edx, 9Ah; void *
0x18004f307  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18004f30d  lea     r8, aOnecoreuapPrin_5; "onecoreuap\\printscan\\print\\workflow"...
0x18004f314  mov     edx, 99h; void *
0x18004f319  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
