# CheckFileReadyFlag(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *,bool *)

- ea: `0x18004536c`
- end: `0x1800454c9`
- name: `?CheckFileReadyFlag@@YAJPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEA_N@Z`
- size: `349`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180042f30`

## callees

- `0x1800019c0`
- `0x180020c48`
- `0x180021f14`
- `0x180026920`
- `0x18004536c`
- `0x180046c18`
- `0x180052010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004542e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004542e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800453e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004544e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004548a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180045494`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800453e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004544e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004548a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180045494`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004541e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004541e`

## string_xrefs

- `0x1800453c0`: `avcore\mf\photography\components\geotag\lib\geotag.cpp`

## pseudocode

```c
__int64 __fastcall CheckFileReadyFlag(__int64 *a1, bool *a2)
{
  __int64 v2; // rax
  __int64 (__fastcall *v5)(__int64 *, __int64 *); // rbx
  int v6; // eax
  int v7; // ebx
  __int64 v8; // rax
  int HSTRINGFromMap; // eax
  PCWSTR StringRawBuffer; // rax
  __int64 v11; // rax
  HSTRING string; // [rsp+20h] [rbp-40h] BYREF
  __int64 v14; // [rsp+28h] [rbp-38h] BYREF
  HSTRING v15; // [rsp+30h] [rbp-30h] BYREF
  _BYTE v16[32]; // [rsp+38h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]

  v2 = *a1;
  v14 = 0;
  v5 = *(__int64 (__fastcall **)(__int64 *, __int64 *))(v2 + 72);
  Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&v14);
  v6 = v5(a1, &v14);
  v7 = v6;
  if ( v6 >= 0 )
  {
    WindowsDeleteString(0);
    string = 0;
    v8 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v16, &off_18005D698);
    HSTRINGFromMap = GetHSTRINGFromMap(v14, *(_QWORD *)(v8 + 24), &string);
    v7 = HSTRINGFromMap;
    if ( HSTRINGFromMap < 0 )
    {
      if ( HSTRINGFromMap == -2147316576 )
      {
        v15 = 0;
        WindowsDeleteString(0);
        v15 = 0;
        v11 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v16, off_18005D690);
        v7 = GetHSTRINGFromMap(v14, *(_QWORD *)(v11 + 24), &v15);
        if ( v7 >= 0 )
          *a2 = 1;
        WindowsDeleteString(v15);
      }
    }
    else
    {
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      *a2 = (unsigned int)_o__wcsicmp(StringRawBuffer, L"9B66F8B8-B7AE-4827-8D08-5CBD72BCDDDC") != 0;
    }
    WindowsDeleteString(string);
    string = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x198,
      (unsigned int)"avcore\\mf\\photography\\components\\geotag\\lib\\geotag.cpp",
      (const char *)(unsigned int)v6,
      (int)string);
  }
  Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(&v14);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18004536c  mov     [rsp-18h+arg_10], rbx
0x180045371  push    rbp
0x180045372  push    rsi
0x180045373  push    rdi
0x180045374  mov     rbp, rsp
0x180045377  sub     rsp, 60h
0x18004537b  mov     rax, cs:__security_cookie
0x180045382  xor     rax, rsp
0x180045385  mov     [rbp+var_8], rax
0x180045389  mov     rax, [rcx]
0x18004538c  mov     rdi, rcx
0x18004538f  lea     rcx, [rbp+var_38]
0x180045393  mov     [rbp+var_38], 0
0x18004539b  mov     rsi, rdx
0x18004539e  mov     rbx, [rax+48h]
0x1800453a2  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x1800453a7  lea     rdx, [rbp+var_38]
0x1800453ab  mov     rcx, rdi
0x1800453ae  mov     rax, rbx
0x1800453b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800453b6  mov     ebx, eax
0x1800453b8  test    eax, eax
0x1800453ba  jns     short loc_1800453D9
0x1800453bc  mov     rcx, [rbp+18h]; this
0x1800453c0  lea     r8, aAvcoreMfPhotog; "avcore\\mf\\photography\\components\\ge"...
0x1800453c7  mov     r9d, eax; char *
0x1800453ca  mov     edx, 198h; void *
0x1800453cf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800453d4  jmp     loc_1800454A2
0x1800453d9  xor     ecx, ecx; string
0x1800453db  mov     [rbp+string], 0
0x1800453e3  call    cs:__imp_WindowsDeleteString
0x1800453e9  lea     rdx, off_18005D698; "System.ItemSubType"
0x1800453f0  mov     [rbp+string], 0
0x1800453f8  lea     rcx, [rbp+var_28]
0x1800453fc  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180045401  mov     rcx, [rbp+var_38]
0x180045405  lea     r8, [rbp+string]
0x180045409  mov     rdx, [rax+18h]
0x18004540d  call    ?GetHSTRINGFromMap@@YAJPEAU?$IMapView@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEAUHSTRING__@@PEAPEAU5@@Z; GetHSTRINGFromMap(Windows::Foundation::Collections::IMapView<HSTRING__ *,IInspectable *> *,HSTRING__ *,HSTRING__ * *)
0x180045412  mov     ebx, eax
0x180045414  test    eax, eax
0x180045416  js      short loc_18004543D
0x180045418  mov     rcx, [rbp+string]; string
0x18004541c  xor     edx, edx; length
0x18004541e  call    cs:__imp_WindowsGetStringRawBuffer
0x180045424  mov     rcx, rax
0x180045427  lea     rdx, a9b66f8b8B7ae48; "9B66F8B8-B7AE-4827-8D08-5CBD72BCDDDC"
0x18004542e  call    cs:__imp__o__wcsicmp
0x180045434  test    eax, eax
0x180045436  setnz   cl
0x180045439  mov     [rsi], cl
0x18004543b  jmp     short loc_180045490
0x18004543d  cmp     eax, 80028CA0h
0x180045442  jnz     short loc_180045490
0x180045444  xor     ecx, ecx; string
0x180045446  mov     [rbp+var_30], 0
0x18004544e  call    cs:__imp_WindowsDeleteString
0x180045454  lea     rdx, off_18005D690; "System.Image.Dimensions"
0x18004545b  mov     [rbp+var_30], 0
0x180045463  lea     rcx, [rbp+var_28]
0x180045467  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18004546c  mov     rcx, [rbp+var_38]
0x180045470  lea     r8, [rbp+var_30]
0x180045474  mov     rdx, [rax+18h]
0x180045478  call    ?GetHSTRINGFromMap@@YAJPEAU?$IMapView@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@PEAUHSTRING__@@PEAPEAU5@@Z; GetHSTRINGFromMap(Windows::Foundation::Collections::IMapView<HSTRING__ *,IInspectable *> *,HSTRING__ *,HSTRING__ * *)
0x18004547d  mov     ebx, eax
0x18004547f  test    eax, eax
0x180045481  js      short loc_180045486
0x180045483  mov     byte ptr [rsi], 1
0x180045486  mov     rcx, [rbp+var_30]; string
0x18004548a  call    cs:__imp_WindowsDeleteString
0x180045490  mov     rcx, [rbp+string]; string
0x180045494  call    cs:__imp_WindowsDeleteString
0x18004549a  mov     [rbp+string], 0
0x1800454a2  lea     rcx, [rbp+var_38]
0x1800454a6  call    ?InternalRelease@?$ComPtr@UID3D11DeviceContext@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ID3D11DeviceContext>::InternalRelease(void)
0x1800454ab  mov     eax, ebx
0x1800454ad  mov     rcx, [rbp+var_8]
0x1800454b1  xor     rcx, rsp; StackCookie
0x1800454b4  call    __security_check_cookie
0x1800454b9  mov     rbx, [rsp+60h+arg_10]
0x1800454c1  add     rsp, 60h
0x1800454c5  pop     rdi
0x1800454c6  pop     rsi
0x1800454c7  pop     rbp
0x1800454c8  retn
```
