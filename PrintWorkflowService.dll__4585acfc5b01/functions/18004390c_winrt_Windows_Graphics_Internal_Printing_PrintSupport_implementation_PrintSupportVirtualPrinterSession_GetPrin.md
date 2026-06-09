# winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportVirtualPrinterSession::GetPrintDeviceCapabilities(void)

- ea: `0x18004390c`
- end: `0x180043a4b`
- name: `?GetPrintDeviceCapabilities@PrintSupportVirtualPrinterSession@implementation@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@QEAA?AUhstring@8@XZ`
- size: `319`
- prototype: `IStream *__fastcall(__int64, IStream *)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18004b380`

## callees

- `0x180003ca0`
- `0x180012784`
- `0x1800127a4`
- `0x180012820`
- `0x1800129dc`
- `0x1800147fc`
- `0x1800228c0`
- `0x18003b194`
- `0x18004390c`
- `0x1800441c4`

## import_xrefs

- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileEx` at `0x1800439b4`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileEx` at `0x1800439b4`

## string_xrefs

- `0x180043a09`: `onecoreuap\printscan\print\workflow\broker\psa_lib\printsupportvirtualprintersession.cpp`
- `0x180043a21`: `onecoreuap\printscan\print\workflow\broker\psa_lib\printsupportvirtualprintersession.cpp`
- `0x180043a39`: `onecoreuap\printscan\print\workflow\broker\psa_lib\printsupportvirtualprintersession.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
IStream *__fastcall winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportVirtualPrinterSession::GetPrintDeviceCapabilities(
        __int64 a1,
        IStream *a2)
{
  __int64 v3; // rdx
  wil::details::in1diag3 *v4; // r10
  const unsigned __int16 *v5; // rax
  int PdcFilePath; // eax
  const WCHAR *v7; // rax
  HRESULT v8; // eax
  int pstmTemplate; // [rsp+20h] [rbp-50h]
  int pstmTemplatea; // [rsp+20h] [rbp-50h]
  IStream *ppstm[2]; // [rsp+30h] [rbp-40h] BYREF
  _OWORD v13[2]; // [rsp+40h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+8h]

  ppstm[0] = a2;
  if ( !winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportVirtualPrinterSession::VirtualPrinterSessionStateHandler::IsSessionActive(*(winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportVirtualPrinterSession::VirtualPrinterSessionStateHandler **)(a1 + 320)) )
    wil::details::in1diag3::Throw_Hr(
      v4,
      (void *)0xA2,
      (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\psa_lib\\printsupportvirtualprintersession.cpp",
      (const char *)0x8000000ELL,
      pstmTemplate);
  v13[0] = 0;
  v13[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v13[0]) = 0;
  v5 = winrt::hstring::c_str((winrt::hstring *)(v3 + 88));
  PdcFilePath = GetPdcFilePath(v5, v13);
  if ( PdcFilePath < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xA5,
      (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\psa_lib\\printsupportvirtualprintersession.cpp",
      (const char *)(unsigned int)PdcFilePath,
      pstmTemplate);
  ppstm[0] = 0;
  v7 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v13);
  v8 = SHCreateStreamOnFileEx(v7, 0x40u, 0, 0, 0, ppstm);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xAD,
      (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\psa_lib\\printsupportvirtualprintersession.cpp",
      (const char *)(unsigned int)v8,
      pstmTemplatea);
  StreamUtils::GetHStringFromStream(a2, ppstm[0]);
  if ( ppstm[0] )
    winrt::com_ptr<ProtocolActivatedEventArgsImpl>::unconditional_release_ref(ppstm);
  std::wstring::_Tidy_deallocate(v13);
  return a2;
}

```

## disassembly

```asm
0x18004390c  mov     [rsp-8+arg_10], rbx
0x180043911  push    rbp
0x180043912  mov     rbp, rsp
0x180043915  sub     rsp, 70h
0x180043919  mov     rax, cs:__security_cookie
0x180043920  xor     rax, rsp
0x180043923  mov     [rbp+var_10], rax
0x180043927  mov     rbx, rdx
0x18004392a  mov     rdx, rcx
0x18004392d  mov     [rbp+var_40], rbx
0x180043931  mov     r10, [rbp+8]
0x180043935  mov     rcx, [rcx+140h]; this
0x18004393c  call    ?IsSessionActive@VirtualPrinterSessionStateHandler@PrintSupportVirtualPrinterSession@implementation@PrintSupport@Printing@Internal@Graphics@Windows@winrt@@QEAA_NXZ; winrt::Windows::Graphics::Internal::Printing::PrintSupport::implementation::PrintSupportVirtualPrinterSession::VirtualPrinterSessionStateHandler::IsSessionActive(void)
0x180043941  test    al, al
0x180043943  jz      loc_180043A1B
0x180043949  xorps   xmm0, xmm0
0x18004394c  movups  [rbp+var_30], xmm0
0x180043950  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180043958  movdqu  [rbp+var_20], xmm1
0x18004395d  xor     eax, eax
0x18004395f  mov     word ptr [rbp+var_30], ax
0x180043963  lea     rcx, [rdx+58h]; this
0x180043967  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x18004396c  mov     rcx, rax
0x18004396f  lea     rdx, [rbp+var_30]
0x180043973  call    ?GetPdcFilePath@@YAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GetPdcFilePath(ushort const *,std::wstring &)
0x180043978  mov     rcx, [rbp+8]; this
0x18004397c  test    eax, eax
0x18004397e  js      loc_180043A36
0x180043984  mov     [rbp+var_40], 0
0x18004398c  lea     rcx, [rbp+var_30]
0x180043990  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180043995  mov     rcx, rax; pszFile
0x180043998  lea     rax, [rbp+var_40]
0x18004399c  mov     [rsp+70h+ppstm], rax; ppstm
0x1800439a1  mov     [rsp+70h+pstmTemplate], 0; int
0x1800439aa  xor     r9d, r9d; fCreate
0x1800439ad  xor     r8d, r8d; dwAttributes
0x1800439b0  lea     edx, [r9+40h]; grfMode
0x1800439b4  call    cs:__imp_SHCreateStreamOnFileEx
0x1800439ba  mov     rcx, [rbp+8]; this
0x1800439be  test    eax, eax
0x1800439c0  js      short loc_180043A06
0x1800439c2  mov     rdx, [rbp+var_40]
0x1800439c6  mov     rcx, rbx
0x1800439c9  call    ?GetHStringFromStream@StreamUtils@@YA?AUhstring@winrt@@PEAUIStream@@@Z; StreamUtils::GetHStringFromStream(IStream *)
0x1800439ce  nop
0x1800439cf  cmp     [rbp+var_40], 0
0x1800439d4  jz      short loc_1800439E0
0x1800439d6  lea     rcx, [rbp+var_40]
0x1800439da  call    ?unconditional_release_ref@?$com_ptr@VProtocolActivatedEventArgsImpl@@@winrt@@AEAAXXZ; winrt::com_ptr<ProtocolActivatedEventArgsImpl>::unconditional_release_ref(void)
0x1800439df  nop
0x1800439e0  lea     rcx, [rbp+var_30]
0x1800439e4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800439e9  mov     rax, rbx
0x1800439ec  mov     rcx, [rbp+var_10]
0x1800439f0  xor     rcx, rsp; StackCookie
0x1800439f3  call    __security_check_cookie
0x1800439f8  mov     rbx, [rsp+70h+arg_10]
0x180043a00  add     rsp, 70h
0x180043a04  pop     rbp
0x180043a05  retn
0x180043a06  mov     r9d, eax; char *
0x180043a09  lea     r8, aOnecoreuapPrin_20; "onecoreuap\\printscan\\print\\workflow"...
0x180043a10  mov     edx, 0ADh; void *
0x180043a15  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180043a1b  mov     r9d, 8000000Eh; char *
0x180043a21  lea     r8, aOnecoreuapPrin_20; "onecoreuap\\printscan\\print\\workflow"...
0x180043a28  mov     edx, 0A2h; void *
0x180043a2d  mov     rcx, r10; this
0x180043a30  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180043a36  mov     r9d, eax; char *
0x180043a39  lea     r8, aOnecoreuapPrin_20; "onecoreuap\\printscan\\print\\workflow"...
0x180043a40  mov     edx, 0A5h; void *
0x180043a45  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
