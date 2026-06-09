# ToastHelper::MakeToast(ushort const *,uint,uint)

- ea: `0x180063238`
- end: `0x1800633bb`
- name: `?MakeToast@ToastHelper@@SAJPEBGII@Z`
- size: `387`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180068310`

## callees

- `0x1800094c0`
- `0x18001ab9c`
- `0x18001f5f4`
- `0x1800493d4`
- `0x1800624c8`
- `0x180062bec`
- `0x180062d10`
- `0x180063238`
- `0x1800c7010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006332a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180063381`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006332a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180063381`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006335d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006335d`

## string_xrefs

- `0x180063286`: `Windows.Data.Xml.Dom.XmlDocument`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall ToastHelper::MakeToast(const unsigned __int16 *a1, unsigned int a2, unsigned int a3)
{
  int v6; // eax
  unsigned int v7; // ebx
  __int64 v8; // rdx
  struct Windows::Data::Xml::Dom::IXmlDocument *v9; // rbx
  __int64 (__fastcall *v10)(struct Windows::Data::Xml::Dom::IXmlDocument *, GUID *, __int64 *); // rdi
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, HSTRING *); // rbx
  const unsigned __int16 *StringRawBuffer; // rax
  const unsigned __int16 *v14; // rcx
  HSTRING string; // [rsp+20h] [rbp-40h] BYREF
  __int64 v17; // [rsp+28h] [rbp-38h] BYREF
  struct Windows::Data::Xml::Dom::IXmlDocument *v18; // [rsp+30h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+38h] [rbp-28h] BYREF
  __int64 v20; // [rsp+50h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]

  v18 = 0;
  v17 = 0;
  string = 0;
  v20 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Data.Xml.Dom.XmlDocument",
    0x21u,
    0x20u);
  v6 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>>(v20, &v18);
  v7 = v6;
  if ( v6 >= 0 )
  {
    v6 = ToastHelper::BuildXml(v18, a1, a2, a3);
    v7 = v6;
    if ( v6 >= 0 )
    {
      v9 = v18;
      v10 = **(__int64 (__fastcall ***)(struct Windows::Data::Xml::Dom::IXmlDocument *, GUID *, __int64 *))v18;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v17);
      v6 = v10(v9, &GUID_5cc5b382_e6dd_4991_abef_06d8d2e7bd0c, &v17);
      v7 = v6;
      if ( v6 >= 0 )
      {
        v11 = v17;
        v12 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v17 + 48LL);
        WindowsDeleteString(string);
        string = 0;
        v6 = v12(v11, &string);
        v7 = v6;
        if ( v6 >= 0 )
        {
          StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
          v6 = ToastHelper::LaunchToast(v14, StringRawBuffer);
          v7 = v6;
          if ( v6 >= 0 )
          {
            v7 = 0;
            goto LABEL_13;
          }
          v8 = 114;
        }
        else
        {
          v8 = 113;
        }
      }
      else
      {
        v8 = 112;
      }
    }
    else
    {
      v8 = 111;
    }
  }
  else
  {
    v8 = 109;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)"onecore\\base\\devices\\cam\\core\\toasthelper.cpp",
    (const char *)(unsigned int)v6,
    (int)string);
LABEL_13:
  WindowsDeleteString(string);
  string = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v17);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v18);
  return v7;
}

```

## disassembly

```asm
0x180063238  push    rbp
0x18006323a  push    rbx
0x18006323b  push    rsi
0x18006323c  push    rdi
0x18006323d  push    r14
0x18006323f  mov     rbp, rsp
0x180063242  sub     rsp, 60h
0x180063246  mov     rax, cs:__security_cookie
0x18006324d  xor     rax, rsp
0x180063250  mov     [rbp+var_8], rax
0x180063254  mov     r14d, r8d
0x180063257  mov     esi, edx
0x180063259  mov     rdi, rcx
0x18006325c  mov     [rbp+var_30], 0
0x180063264  mov     [rbp+var_38], 0
0x18006326c  mov     [rbp+string], 0
0x180063274  mov     [rbp+var_10], 0
0x18006327c  mov     r9d, 20h ; ' '; unsigned int
0x180063282  lea     r8d, [r9+1]; unsigned int
0x180063286  lea     rdx, ?RuntimeClass_Windows_Data_Xml_Dom_XmlDocument@@3QBGB; "Windows.Data.Xml.Dom.XmlDocument"
0x18006328d  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x180063291  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180063296  lea     rdx, [rbp+var_30]
0x18006329a  mov     rcx, [rbp+var_10]
0x18006329e  call    ??$ActivateInstance@V?$ComPtr@UIXmlDocument@Dom@Xml@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIXmlDocument@Dom@Xml@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlDocument>>)
0x1800632a3  mov     ebx, eax
0x1800632a5  test    eax, eax
0x1800632a7  jns     short loc_1800632B0
0x1800632a9  mov     edx, 6Dh ; 'm'
0x1800632ae  jmp     short loc_1800632CD
0x1800632b0  mov     r9d, r14d; unsigned int
0x1800632b3  mov     r8d, esi; unsigned int
0x1800632b6  mov     rdx, rdi; unsigned __int16 *
0x1800632b9  mov     rcx, [rbp+var_30]; struct Windows::Data::Xml::Dom::IXmlDocument *
0x1800632bd  call    ?BuildXml@ToastHelper@@CAJPEAUIXmlDocument@Dom@Xml@Data@Windows@@PEBGII@Z; ToastHelper::BuildXml(Windows::Data::Xml::Dom::IXmlDocument *,ushort const *,uint,uint)
0x1800632c2  mov     ebx, eax
0x1800632c4  test    eax, eax
0x1800632c6  jns     short loc_1800632E5
0x1800632c8  mov     edx, 6Fh ; 'o'; void *
0x1800632cd  mov     rcx, [rbp+28h]; this
0x1800632d1  mov     r9d, eax; char *
0x1800632d4  lea     r8, aOnecoreBaseDev_42; "onecore\\base\\devices\\cam\\core\\toas"...
0x1800632db  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800632e0  jmp     loc_18006337D
0x1800632e5  mov     rbx, [rbp+var_30]
0x1800632e9  mov     rax, [rbx]
0x1800632ec  mov     rdi, [rax]
0x1800632ef  lea     rcx, [rbp+var_38]
0x1800632f3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800632f8  lea     r8, [rbp+var_38]
0x1800632fc  lea     rdx, _GUID_5cc5b382_e6dd_4991_abef_06d8d2e7bd0c
0x180063303  mov     rcx, rbx
0x180063306  mov     rax, rdi
0x180063309  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006330e  mov     ebx, eax
0x180063310  test    eax, eax
0x180063312  jns     short loc_18006331B
0x180063314  mov     edx, 70h ; 'p'
0x180063319  jmp     short loc_1800632CD
0x18006331b  mov     rdi, [rbp+var_38]
0x18006331f  mov     rax, [rdi]
0x180063322  mov     rbx, [rax+30h]
0x180063326  mov     rcx, [rbp+string]; string
0x18006332a  call    cs:__imp_WindowsDeleteString
0x180063330  mov     [rbp+string], 0
0x180063338  lea     rdx, [rbp+string]
0x18006333c  mov     rcx, rdi
0x18006333f  mov     rax, rbx
0x180063342  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063347  mov     ebx, eax
0x180063349  test    eax, eax
0x18006334b  jns     short loc_180063357
0x18006334d  mov     edx, 71h ; 'q'
0x180063352  jmp     loc_1800632CD
0x180063357  xor     edx, edx; length
0x180063359  mov     rcx, [rbp+string]; string
0x18006335d  call    cs:__imp_WindowsGetStringRawBuffer
0x180063363  mov     rdx, rax; unsigned __int16 *
0x180063366  call    ?LaunchToast@ToastHelper@@CAJPEBG0@Z; ToastHelper::LaunchToast(ushort const *,ushort const *)
0x18006336b  mov     ebx, eax
0x18006336d  test    eax, eax
0x18006336f  jns     short loc_18006337B
0x180063371  mov     edx, 72h ; 'r'
0x180063376  jmp     loc_1800632CD
0x18006337b  xor     ebx, ebx
0x18006337d  mov     rcx, [rbp+string]; string
0x180063381  call    cs:__imp_WindowsDeleteString
0x180063387  mov     [rbp+string], 0
0x18006338f  lea     rcx, [rbp+var_38]
0x180063393  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180063398  nop
0x180063399  lea     rcx, [rbp+var_30]
0x18006339d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800633a2  mov     eax, ebx
0x1800633a4  mov     rcx, [rbp+var_8]
0x1800633a8  xor     rcx, rsp; StackCookie
0x1800633ab  call    __security_check_cookie
0x1800633b0  add     rsp, 60h
0x1800633b4  pop     r14
0x1800633b6  pop     rdi
0x1800633b7  pop     rsi
0x1800633b8  pop     rbx
0x1800633b9  pop     rbp
0x1800633ba  retn
```
