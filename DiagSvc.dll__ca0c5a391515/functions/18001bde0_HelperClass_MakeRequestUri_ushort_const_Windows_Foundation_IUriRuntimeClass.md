# HelperClass::MakeRequestUri(ushort const *,Windows::Foundation::IUriRuntimeClass * *)

- ea: `0x18001bde0`
- end: `0x18001bec7`
- name: `?MakeRequestUri@HelperClass@@SAJPEBGPEAPEAUIUriRuntimeClass@Foundation@Windows@@@Z`
- size: `231`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct Windows::Foundation::IUriRuntimeClass **)`
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180011b80`
- `0x180016d70`
- `0x180017e20`

## callees

- `0x180003fc0`
- `0x18000517c`
- `0x18000ade0`
- `0x180014044`
- `0x18001bde0`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001be60`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001be60`

## string_xrefs

- `0x18001be31`: `Windows.Foundation.Uri`

## pseudocode

```c
__int64 __fastcall HelperClass::MakeRequestUri(
        const unsigned __int16 *a1,
        struct Windows::Foundation::IUriRuntimeClass **a2)
{
  int ActivationFactory; // ebx
  __int64 v4; // rbx
  __int64 v5; // rdi
  __int64 (__fastcall *v6)(__int64, _QWORD, struct Windows::Foundation::IUriRuntimeClass **); // rbx
  __int64 v7; // rax
  __int64 v9; // [rsp+20h] [rbp-48h] BYREF
  const unsigned __int16 *v10; // [rsp+28h] [rbp-40h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-38h] BYREF
  __int64 v12; // [rsp+48h] [rbp-20h]

  v10 = a1;
  if ( a1 )
  {
    v9 = 0;
    v12 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Windows.Foundation.Uri", 0x17u, 0x16u);
    v4 = v12;
    Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&v9);
    ActivationFactory = RoGetActivationFactory(v4, &GUID_44a9796f_723e_4fdf_a218_033e75b0c084, &v9);
    if ( ActivationFactory >= 0 )
    {
      v5 = v9;
      v6 = *(__int64 (__fastcall **)(__int64, _QWORD, struct Windows::Foundation::IUriRuntimeClass **))(*(_QWORD *)v9 + 48LL);
      v7 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v10);
      ActivationFactory = v6(v5, *(_QWORD *)(v7 + 24), a2);
    }
    Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&v9);
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x18001bde0  mov     [rsp+arg_10], rbx
0x18001bde5  mov     [rsp+arg_18], rsi
0x18001bdea  push    rdi
0x18001bdeb  sub     rsp, 60h
0x18001bdef  mov     rax, cs:__security_cookie
0x18001bdf6  xor     rax, rsp
0x18001bdf9  mov     [rsp+68h+var_18], rax
0x18001bdfe  mov     rsi, rdx
0x18001be01  mov     [rsp+68h+var_40], rcx
0x18001be06  test    rcx, rcx
0x18001be09  jnz     short loc_18001BE15
0x18001be0b  mov     ebx, 80070057h
0x18001be10  jmp     loc_18001BEA6
0x18001be15  mov     [rsp+68h+var_48], 0
0x18001be1e  mov     [rsp+68h+var_20], 0
0x18001be27  mov     r9d, 16h; unsigned int
0x18001be2d  lea     r8d, [r9+1]; unsigned int
0x18001be31  lea     rdx, ?RuntimeClass_Windows_Foundation_Uri@@3QBGB; "Windows.Foundation.Uri"
0x18001be38  lea     rcx, [rsp+68h+hstringHeader]; hstringHeader
0x18001be3d  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18001be42  mov     rbx, [rsp+68h+var_20]
0x18001be47  lea     rcx, [rsp+68h+var_48]
0x18001be4c  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x18001be51  lea     r8, [rsp+68h+var_48]
0x18001be56  lea     rdx, _GUID_44a9796f_723e_4fdf_a218_033e75b0c084
0x18001be5d  mov     rcx, rbx
0x18001be60  call    cs:__imp_RoGetActivationFactory
0x18001be66  mov     ebx, eax
0x18001be68  test    eax, eax
0x18001be6a  js      short loc_18001BE9C
0x18001be6c  mov     rdi, [rsp+68h+var_48]
0x18001be71  mov     rax, [rdi]
0x18001be74  mov     rbx, [rax+30h]
0x18001be78  lea     rdx, [rsp+68h+var_40]
0x18001be7d  lea     rcx, [rsp+68h+hstringHeader]
0x18001be82  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18001be87  nop
0x18001be88  mov     r8, rsi
0x18001be8b  mov     rdx, [rax+18h]
0x18001be8f  mov     rcx, rdi
0x18001be92  mov     rax, rbx
0x18001be95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001be9a  mov     ebx, eax
0x18001be9c  lea     rcx, [rsp+68h+var_48]
0x18001bea1  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x18001bea6  mov     eax, ebx
0x18001bea8  mov     rcx, [rsp+68h+var_18]
0x18001bead  xor     rcx, rsp; StackCookie
0x18001beb0  call    __security_check_cookie
0x18001beb5  lea     r11, [rsp+68h+var_8]
0x18001beba  mov     rbx, [r11+20h]
0x18001bebe  mov     rsi, [r11+28h]
0x18001bec2  mov     rsp, r11
0x18001bec5  pop     rdi
0x18001bec6  retn
```
