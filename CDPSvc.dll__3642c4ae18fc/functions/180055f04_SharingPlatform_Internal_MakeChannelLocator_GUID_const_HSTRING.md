# SharingPlatform::Internal::MakeChannelLocator(_GUID const &,HSTRING__ *)

- ea: `0x180055f04`
- end: `0x1800560b8`
- name: `?MakeChannelLocator@Internal@SharingPlatform@@YA?AVHString@Wrappers@WRL@Microsoft@@AEBU_GUID@@PEAUHSTRING__@@@Z`
- size: `436`
- prototype: `struct Microsoft::WRL::Wrappers::HString __high(const struct _GUID *, HSTRING)`
- caller_count: `6`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180011de0`
- `0x18001f310`
- `0x18004cd80`
- `0x18004cee0`
- `0x180058340`
- `0x18005bdd0`

## callees

- `0x18000a1a4`
- `0x18000a580`
- `0x180018490`
- `0x1800225a0`
- `0x18003a1ec`
- `0x18003f9c8`
- `0x180048978`
- `0x180055f04`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180055f41`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180055f41`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180055fa9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180055fa9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x180055fdd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x180056005`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x180055fdd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x180056005`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180055f56`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180055fee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005605a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180056095`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180055f56`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180055fee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005605a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180056095`

## pseudocode

```c
HSTRING *__fastcall SharingPlatform::Internal::MakeChannelLocator(HSTRING *a1, const GUID *a2, HSTRING a3)
{
  unsigned __int64 v5; // rdx
  unsigned __int8 v6; // cl
  unsigned __int64 v7; // rcx
  signed int v8; // eax
  HSTRING v9; // rbx
  unsigned int v10; // eax
  unsigned __int64 v11; // rdx
  unsigned __int8 v12; // cl
  HRESULT v13; // ebx
  unsigned __int64 v14; // rdx
  unsigned __int8 v15; // cl
  HRESULT v16; // ebx
  __int64 v17; // rcx
  RemoteSessionTraceProvider *v18; // rax
  __int64 v19; // rcx
  RemoteSessionTraceProvider *v20; // rax
  __int64 v21; // rcx
  RemoteSessionTraceProvider *v22; // rax
  unsigned int v24; // [rsp+20h] [rbp-89h] BYREF
  HSTRING string; // [rsp+28h] [rbp-81h] BYREF
  HSTRING newString; // [rsp+30h] [rbp-79h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+38h] [rbp-71h] BYREF
  HSTRING string2; // [rsp+50h] [rbp-59h]
  HSTRING_HEADER v29; // [rsp+58h] [rbp-51h] BYREF
  HSTRING string1; // [rsp+70h] [rbp-39h]
  OLECHAR sz[40]; // [rsp+80h] [rbp-29h] BYREF

  string = 0;
  if ( StringFromGUID2(a2, sz, 39) == 39 )
  {
    WindowsDeleteString(0);
    newString = 0;
    string2 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L":", 2u, 1u);
    v7 = -1;
    do
      ++v7;
    while ( sz[v7] );
    v8 = ULongLongToUInt(v7, &v24);
    if ( v8 < 0 )
    {
      RaiseException(v8, 1u, 0, 0);
      __debugbreak();
    }
    v9 = string2;
    v10 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v24);
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v29, sz, v10, v24);
    v13 = WindowsConcatString(string1, v9, &newString);
    if ( v13 < 0 )
    {
      if ( RemoteSessionTraceProvider::IsEnabled(v12, v11) )
      {
        v20 = (RemoteSessionTraceProvider *)wil::details::static_lazy<RemoteSessionTraceProvider>::get(
                                              v19,
                                              _lambda_d16ede8d5b83737b43ecc5e6e08d1063_::_lambda_invoker_cdecl_);
        RemoteSessionTraceProvider::LogError_(
          v20,
          L"MakeChannelLocator. WindowsConcatString for channelLocatorPrefix failed; hr = 0x%08x",
          (unsigned int)v13);
      }
    }
    else
    {
      WindowsDeleteString(string);
      string = 0;
      v16 = WindowsConcatString(newString, a3, &string);
      if ( v16 < 0 && RemoteSessionTraceProvider::IsEnabled(v15, v14) )
      {
        v18 = (RemoteSessionTraceProvider *)wil::details::static_lazy<RemoteSessionTraceProvider>::get(
                                              v17,
                                              _lambda_d16ede8d5b83737b43ecc5e6e08d1063_::_lambda_invoker_cdecl_);
        RemoteSessionTraceProvider::LogError_(
          v18,
          L"MakeChannelLocator. WindowsConcatString for channelLocator failed; hr = 0x%08x",
          (unsigned int)v16);
      }
    }
    WindowsDeleteString(newString);
  }
  else if ( RemoteSessionTraceProvider::IsEnabled(v6, v5) )
  {
    v22 = (RemoteSessionTraceProvider *)wil::details::static_lazy<RemoteSessionTraceProvider>::get(
                                          v21,
                                          _lambda_d16ede8d5b83737b43ecc5e6e08d1063_::_lambda_invoker_cdecl_);
    RemoteSessionTraceProvider::LogError_(v22, L"MakeChannelLocator. StringFromGUID2 returned unexpected string length");
  }
  *a1 = string;
  string = 0;
  WindowsDeleteString(0);
  return a1;
}

```

## disassembly

```asm
0x180055f04  push    rbp
0x180055f06  push    rbx
0x180055f07  push    rsi
0x180055f08  push    rdi
0x180055f09  push    r14
0x180055f0b  lea     rbp, [rsp-37h]
0x180055f10  sub     rsp, 0E0h
0x180055f17  mov     rax, cs:__security_cookie
0x180055f1e  xor     rax, rsp
0x180055f21  mov     [rbp+57h+var_30], rax
0x180055f25  mov     rax, rdx
0x180055f28  xor     r14d, r14d
0x180055f2b  mov     rsi, r8
0x180055f2e  mov     [rsp+100h+string], r14
0x180055f33  mov     rdi, rcx
0x180055f36  lea     rdx, [rbp+57h+sz]; lpsz
0x180055f3a  mov     rcx, rax; rguid
0x180055f3d  lea     r8d, [r14+27h]; cchMax
0x180055f41  call    cs:__imp_StringFromGUID2
0x180055f47  cmp     eax, 27h ; '''
0x180055f4a  jnz     loc_180056062
0x180055f50  xor     ecx, ecx; string
0x180055f52  mov     [rbp+57h+newString], r14
0x180055f56  call    cs:__imp_WindowsDeleteString
0x180055f5c  lea     ebx, [r14+1]
0x180055f60  mov     [rbp+57h+newString], r14
0x180055f64  mov     r9d, ebx; unsigned int
0x180055f67  mov     [rbp+57h+string2], r14
0x180055f6b  lea     r8d, [r14+2]; unsigned int
0x180055f6f  lea     rdx, sourceString; ":"
0x180055f76  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180055f7a  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180055f7f  lea     rax, [rbp+57h+sz]
0x180055f83  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180055f87  inc     rcx; unsigned __int64
0x180055f8a  cmp     [rax+rcx*2], r14w
0x180055f8f  jnz     short loc_180055F87
0x180055f91  lea     rdx, [rsp+100h+var_E0]; unsigned int *
0x180055f96  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x180055f9b  test    eax, eax
0x180055f9d  jns     short loc_180055FB0
0x180055f9f  xor     r9d, r9d; lpArguments
0x180055fa2  xor     r8d, r8d; nNumberOfArguments
0x180055fa5  mov     edx, ebx; dwExceptionFlags
0x180055fa7  mov     ecx, eax; dwExceptionCode
0x180055fa9  call    cs:__imp_RaiseException
0x180055faf  int     3; Trap to Debugger
0x180055fb0  mov     ecx, [rsp+100h+var_E0]; unsigned int
0x180055fb4  mov     rbx, [rbp+57h+string2]
0x180055fb8  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180055fbd  mov     r9d, [rsp+100h+var_E0]; unsigned int
0x180055fc2  lea     rdx, [rbp+57h+sz]; sourceString
0x180055fc6  mov     r8d, eax; unsigned int
0x180055fc9  lea     rcx, [rbp+57h+var_A8]; hstringHeader
0x180055fcd  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180055fd2  mov     rcx, [rbp+57h+string1]; string1
0x180055fd6  lea     r8, [rbp+57h+newString]; newString
0x180055fda  mov     rdx, rbx; string2
0x180055fdd  call    cs:__imp_WindowsConcatString
0x180055fe3  mov     ebx, eax
0x180055fe5  test    eax, eax
0x180055fe7  js      short loc_18005602F
0x180055fe9  mov     rcx, [rsp+100h+string]; string
0x180055fee  call    cs:__imp_WindowsDeleteString
0x180055ff4  mov     rcx, [rbp+57h+newString]; string1
0x180055ff8  lea     r8, [rsp+100h+string]; newString
0x180055ffd  mov     rdx, rsi; string2
0x180056000  mov     [rsp+100h+string], r14
0x180056005  call    cs:__imp_WindowsConcatString
0x18005600b  mov     ebx, eax
0x18005600d  test    eax, eax
0x18005600f  jns     short loc_180056056
0x180056011  call    ?IsEnabled@RemoteSessionTraceProvider@@SA_NE_K@Z; RemoteSessionTraceProvider::IsEnabled(uchar,unsigned __int64)
0x180056016  test    al, al
0x180056018  jz      short loc_180056056
0x18005601a  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_d16ede8d5b83737b43ecc5e6e08d1063_@@CA@XZ; _lambda_d16ede8d5b83737b43ecc5e6e08d1063_::_lambda_invoker_cdecl_(void)
0x180056021  call    ?get@?$static_lazy@VRemoteSessionTraceProvider@@@details@wil@@QEAAPEAVRemoteSessionTraceProvider@@P6AXXZ@Z; wil::details::static_lazy<RemoteSessionTraceProvider>::get(void (*)(void))
0x180056026  lea     rdx, aMakechannelloc; "MakeChannelLocator. WindowsConcatString"...
0x18005602d  jmp     short loc_18005604B
0x18005602f  call    ?IsEnabled@RemoteSessionTraceProvider@@SA_NE_K@Z; RemoteSessionTraceProvider::IsEnabled(uchar,unsigned __int64)
0x180056034  test    al, al
0x180056036  jz      short loc_180056056
0x180056038  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_d16ede8d5b83737b43ecc5e6e08d1063_@@CA@XZ; _lambda_d16ede8d5b83737b43ecc5e6e08d1063_::_lambda_invoker_cdecl_(void)
0x18005603f  call    ?get@?$static_lazy@VRemoteSessionTraceProvider@@@details@wil@@QEAAPEAVRemoteSessionTraceProvider@@P6AXXZ@Z; wil::details::static_lazy<RemoteSessionTraceProvider>::get(void (*)(void))
0x180056044  lea     rdx, aMakechannelloc_1; "MakeChannelLocator. WindowsConcatString"...
0x18005604b  mov     r8d, ebx
0x18005604e  mov     rcx, rax; this
0x180056051  call    ?LogError_@RemoteSessionTraceProvider@@QEAAXPEBGZZ; RemoteSessionTraceProvider::LogError_(ushort const *,...)
0x180056056  mov     rcx, [rbp+57h+newString]; string
0x18005605a  call    cs:__imp_WindowsDeleteString
0x180056060  jmp     short loc_180056086
0x180056062  call    ?IsEnabled@RemoteSessionTraceProvider@@SA_NE_K@Z; RemoteSessionTraceProvider::IsEnabled(uchar,unsigned __int64)
0x180056067  test    al, al
0x180056069  jz      short loc_180056086
0x18005606b  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_d16ede8d5b83737b43ecc5e6e08d1063_@@CA@XZ; _lambda_d16ede8d5b83737b43ecc5e6e08d1063_::_lambda_invoker_cdecl_(void)
0x180056072  call    ?get@?$static_lazy@VRemoteSessionTraceProvider@@@details@wil@@QEAAPEAVRemoteSessionTraceProvider@@P6AXXZ@Z; wil::details::static_lazy<RemoteSessionTraceProvider>::get(void (*)(void))
0x180056077  lea     rdx, aMakechannelloc_0; "MakeChannelLocator. StringFromGUID2 ret"...
0x18005607e  mov     rcx, rax; this
0x180056081  call    ?LogError_@RemoteSessionTraceProvider@@QEAAXPEBGZZ; RemoteSessionTraceProvider::LogError_(ushort const *,...)
0x180056086  mov     rcx, [rsp+100h+string]
0x18005608b  mov     [rdi], rcx
0x18005608e  xor     ecx, ecx; string
0x180056090  mov     [rsp+100h+string], r14
0x180056095  call    cs:__imp_WindowsDeleteString
0x18005609b  mov     rax, rdi
0x18005609e  mov     rcx, [rbp+57h+var_30]
0x1800560a2  xor     rcx, rsp; StackCookie
0x1800560a5  call    __security_check_cookie
0x1800560aa  add     rsp, 0E0h
0x1800560b1  pop     r14
0x1800560b3  pop     rdi
0x1800560b4  pop     rsi
0x1800560b5  pop     rbx
0x1800560b6  pop     rbp
0x1800560b7  retn
```
