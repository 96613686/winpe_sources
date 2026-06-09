# WinStoreAuth::AuthenticationInternal::GetAllXTokens(HSTRING__ * *,HSTRING__ * *)

- ea: `0x18003f6c4`
- end: `0x18003fb03`
- name: `?GetAllXTokens@AuthenticationInternal@WinStoreAuth@@YAJPEAPEAUHSTRING__@@0@Z`
- size: `1087`
- prototype: `__int64 __fastcall(HSTRING *string, HSTRING *, HSTRING *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18003ef6c`

## callees

- `0x180010b84`
- `0x18003f6c4`
- `0x180040e90`
- `0x180042640`
- `0x18004f010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003f7c6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003f7c6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003f705`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003fa22`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003fae2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003f705`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003fa22`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003fae2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003f8cf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003f980`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003f8cf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003f980`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003f761`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003f761`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f83d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f84d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f8fd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f90d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f9ae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f9be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f9ed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f9fd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003fa53`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003fa63`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003faad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003fabd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f83d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f84d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f8fd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f90d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f9ae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f9be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f9ed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003f9fd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003fa53`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003fa63`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003faad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003fabd`

## string_xrefs

- `0x18003f7e8`: `x-xbl-contract-version:2\nAccept:application/json`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall WinStoreAuth::AuthenticationInternal::GetAllXTokens(HSTRING *string, HSTRING *a2, HSTRING *a3)
{
  int SlsValue; // eax
  unsigned int v7; // ebx
  HRESULT v8; // eax
  LPVOID v9; // rcx
  LPVOID v10; // rdi
  __int64 (__fastcall *v11)(LPVOID, const wchar_t *, _QWORD, const char *); // rbx
  int v12; // eax
  LPVOID v13; // rcx
  LPVOID v14; // rcx
  int ppv; // [rsp+20h] [rbp-50h]
  int ppva; // [rsp+20h] [rbp-50h]
  int ppvb; // [rsp+20h] [rbp-50h]
  HSTRING stringa; // [rsp+68h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]
  LPVOID v20; // [rsp+B0h] [rbp+40h] BYREF
  LPVOID pv; // [rsp+B8h] [rbp+48h]

  if ( !WinStoreAuth::AuthenticationInternal::IsPlatformXbox((WinStoreAuth::AuthenticationInternal *)string) )
    return 2147500033LL;
  *string = 0;
  *a2 = 0;
  WindowsDeleteString(0);
  stringa = 0;
  SlsValue = WinStoreAuth::GetSlsValue(6, &stringa);
  v7 = SlsValue;
  if ( SlsValue >= 0 )
  {
    v20 = 0;
    v8 = CoCreateInstance(
           &GUID_0134a8b2_3407_4b45_ad25_e9f7c92a80bc,
           0,
           0x17u,
           &GUID_097ad6b8_203b_4506_a509_02e4b11b6bb5,
           &v20);
    v7 = v8;
    if ( v8 >= 0 )
    {
      pv = 0;
      v10 = v20;
      v11 = *(__int64 (__fastcall **)(LPVOID, const wchar_t *, _QWORD, const char *))(*(_QWORD *)v20 + 104LL);
      pv = 0;
      ppvb = (unsigned int)WindowsGetStringRawBuffer(stringa, 0);
      v12 = v11(v10, L"*", 0, L"GET");
      v7 = v12;
      if ( v12 >= 0 )
      {
        v7 = -2147024809;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x48C,
          (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
          (const char *)0x80070057LL,
          ppvb);
        if ( pv )
          CoTaskMemFree(pv);
        v14 = v20;
        if ( v20 )
        {
          v20 = 0;
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v14 + 16LL))(v14);
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x489,
          (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
          (const char *)(unsigned int)v12,
          ppvb);
        if ( pv )
          CoTaskMemFree(pv);
        v13 = v20;
        if ( v20 )
        {
          v20 = 0;
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v13 + 16LL))(v13);
        }
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x47C,
        (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
        (const char *)(unsigned int)v8,
        ppva);
      v9 = v20;
      if ( v20 )
      {
        v20 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v9 + 16LL))(v9);
      }
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x479,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)(unsigned int)SlsValue,
      ppv);
  }
  WindowsDeleteString(stringa);
  return v7;
}

```

## disassembly

```asm
0x18003f6c4  mov     [rsp-28h+arg_0], rbx
0x18003f6c9  mov     [rsp-28h+arg_8], rsi
0x18003f6ce  push    rbp
0x18003f6cf  push    rdi
0x18003f6d0  push    r12
0x18003f6d2  push    r14
0x18003f6d4  push    r15
0x18003f6d6  mov     rbp, rsp
0x18003f6d9  sub     rsp, 70h
0x18003f6dd  mov     r15, rdx
0x18003f6e0  mov     r14, rcx
0x18003f6e3  call    ?IsPlatformXbox@AuthenticationInternal@WinStoreAuth@@YA_NXZ; WinStoreAuth::AuthenticationInternal::IsPlatformXbox(void)
0x18003f6e8  xor     r12d, r12d
0x18003f6eb  test    al, al
0x18003f6ed  jnz     short loc_18003F6F9
0x18003f6ef  mov     eax, 80004001h
0x18003f6f4  jmp     loc_18003FAEA
0x18003f6f9  mov     [r14], r12
0x18003f6fc  mov     [r15], r12
0x18003f6ff  mov     [rbp+string], r12
0x18003f703  xor     ecx, ecx; string
0x18003f705  call    cs:__imp_WindowsDeleteString
0x18003f70b  mov     [rbp+string], r12
0x18003f70f  lea     rdx, [rbp+string]
0x18003f713  mov     ecx, 6
0x18003f718  call    ?GetSlsValue@WinStoreAuth@@YAJW4SlsIndex@1@PEAPEAUHSTRING__@@@Z; WinStoreAuth::GetSlsValue(WinStoreAuth::SlsIndex,HSTRING__ * *)
0x18003f71d  mov     ebx, eax
0x18003f71f  test    eax, eax
0x18003f721  jns     short loc_18003F740
0x18003f723  mov     rcx, [rbp+28h]; this
0x18003f727  mov     r9d, eax; char *
0x18003f72a  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18003f731  mov     edx, 479h; void *
0x18003f736  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003f73b  jmp     loc_18003FADE
0x18003f740  mov     [rbp+arg_10], r12
0x18003f744  lea     rax, [rbp+arg_10]
0x18003f748  mov     [rsp+70h+ppv], rax; int
0x18003f74d  lea     r9, _GUID_097ad6b8_203b_4506_a509_02e4b11b6bb5; riid
0x18003f754  xor     edx, edx; pUnkOuter
0x18003f756  lea     r8d, [rdx+17h]; dwClsContext
0x18003f75a  lea     rcx, _GUID_0134a8b2_3407_4b45_ad25_e9f7c92a80bc; rclsid
0x18003f761  call    cs:__imp_CoCreateInstance
0x18003f767  mov     ebx, eax
0x18003f769  test    eax, eax
0x18003f76b  jns     short loc_18003F7A5
0x18003f76d  mov     rcx, [rbp+28h]; this
0x18003f771  mov     r9d, eax; char *
0x18003f774  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18003f77b  mov     edx, 47Ch; void *
0x18003f780  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003f785  nop
0x18003f786  mov     rcx, [rbp+arg_10]
0x18003f78a  test    rcx, rcx
0x18003f78d  jz      short loc_18003F7A0
0x18003f78f  mov     [rbp+arg_10], r12
0x18003f793  mov     rax, [rcx]
0x18003f796  mov     rax, [rax+10h]
0x18003f79a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f79f  nop
0x18003f7a0  jmp     loc_18003FADE
0x18003f7a5  mov     [rbp+sourceString], r12
0x18003f7a9  mov     [rbp+pv], r12
0x18003f7ad  mov     rdi, [rbp+arg_10]
0x18003f7b1  mov     rax, [rdi]
0x18003f7b4  mov     rbx, [rax+68h]
0x18003f7b8  mov     [rbp+pv], r12
0x18003f7bc  mov     [rbp+sourceString], r12
0x18003f7c0  xor     edx, edx; length
0x18003f7c2  mov     rcx, [rbp+string]; string
0x18003f7c6  call    cs:__imp_WindowsGetStringRawBuffer
0x18003f7cc  lea     rcx, [rbp+pv]
0x18003f7d0  mov     [rsp+70h+var_28], rcx
0x18003f7d5  lea     rcx, [rbp+sourceString]
0x18003f7d9  mov     [rsp+70h+var_30], rcx
0x18003f7de  mov     [rsp+70h+var_38], r12d
0x18003f7e3  mov     [rsp+70h+var_40], r12
0x18003f7e8  lea     rcx, aXXblContractVe; "x-xbl-contract-version:2\r\nAccept:appl"...
0x18003f7ef  mov     [rsp+70h+var_48], rcx
0x18003f7f4  mov     [rsp+70h+ppv], rax; int
0x18003f7f9  lea     r9, aGet; "GET"
0x18003f800  xor     r8d, r8d
0x18003f803  lea     rdx, asc_180058FBC; "*"
0x18003f80a  mov     rcx, rdi
0x18003f80d  mov     rax, rbx
0x18003f810  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f815  mov     ebx, eax
0x18003f817  test    eax, eax
0x18003f819  jns     short loc_18003F873
0x18003f81b  mov     rcx, [rbp+28h]; this
0x18003f81f  mov     r9d, eax; char *
0x18003f822  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18003f829  mov     edx, 489h; void *
0x18003f82e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003f833  nop
0x18003f834  mov     rcx, [rbp+pv]; pv
0x18003f838  test    rcx, rcx
0x18003f83b  jz      short loc_18003F844
0x18003f83d  call    cs:__imp_CoTaskMemFree
0x18003f843  nop
0x18003f844  mov     rcx, [rbp+sourceString]; pv
0x18003f848  test    rcx, rcx
0x18003f84b  jz      short loc_18003F854
0x18003f84d  call    cs:__imp_CoTaskMemFree
0x18003f853  nop
0x18003f854  mov     rcx, [rbp+arg_10]
0x18003f858  test    rcx, rcx
0x18003f85b  jz      short loc_18003F86E
0x18003f85d  mov     [rbp+arg_10], r12
0x18003f861  mov     rax, [rcx]
0x18003f864  mov     rax, [rax+10h]
0x18003f868  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f86d  nop
0x18003f86e  jmp     loc_18003FADE
0x18003f873  mov     r9, [rbp+sourceString]
0x18003f877  test    r9, r9
0x18003f87a  jz      loc_18003FA86
0x18003f880  mov     esi, 7FFFFFFFh
0x18003f885  mov     edx, esi
0x18003f887  mov     rax, r9
0x18003f88a  cmp     [rax], r12w
0x18003f88e  jz      short loc_18003F89A
0x18003f890  add     rax, 2
0x18003f894  sub     rdx, 1
0x18003f898  jnz     short loc_18003F88A
0x18003f89a  mov     rax, rdx
0x18003f89d  neg     rax
0x18003f8a0  sbb     ebx, ebx
0x18003f8a2  not     ebx
0x18003f8a4  mov     edi, 80070057h
0x18003f8a9  and     ebx, edi
0x18003f8ab  mov     rax, rdx
0x18003f8ae  mov     rcx, rsi
0x18003f8b1  sub     rcx, rdx
0x18003f8b4  neg     rax
0x18003f8b7  sbb     r8, r8
0x18003f8ba  and     r8, rcx
0x18003f8bd  test    rdx, rdx
0x18003f8c0  jz      loc_18003FA8B
0x18003f8c6  mov     edx, r8d; length
0x18003f8c9  mov     r8, r14; string
0x18003f8cc  mov     rcx, r9; sourceString
0x18003f8cf  call    cs:__imp_WindowsCreateString
0x18003f8d5  mov     ebx, eax
0x18003f8d7  test    eax, eax
0x18003f8d9  jns     short loc_18003F933
0x18003f8db  mov     rcx, [rbp+28h]; this
0x18003f8df  mov     r9d, eax; char *
0x18003f8e2  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18003f8e9  mov     edx, 48Dh; void *
0x18003f8ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003f8f3  nop
0x18003f8f4  mov     rcx, [rbp+pv]; pv
0x18003f8f8  test    rcx, rcx
0x18003f8fb  jz      short loc_18003F904
0x18003f8fd  call    cs:__imp_CoTaskMemFree
0x18003f903  nop
0x18003f904  mov     rcx, [rbp+sourceString]; pv
0x18003f908  test    rcx, rcx
0x18003f90b  jz      short loc_18003F914
0x18003f90d  call    cs:__imp_CoTaskMemFree
0x18003f913  nop
0x18003f914  mov     rcx, [rbp+arg_10]
0x18003f918  test    rcx, rcx
0x18003f91b  jz      short loc_18003F92E
0x18003f91d  mov     [rbp+arg_10], r12
0x18003f921  mov     rax, [rcx]
0x18003f924  mov     rax, [rax+10h]
0x18003f928  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f92d  nop
0x18003f92e  jmp     loc_18003FADE
0x18003f933  mov     r9, [rbp+pv]
0x18003f937  test    r9, r9
0x18003f93a  jz      loc_18003FA2F
0x18003f940  mov     rcx, rsi
0x18003f943  mov     rax, r9
0x18003f946  cmp     [rax], r12w
0x18003f94a  jz      short loc_18003F956
0x18003f94c  add     rax, 2
0x18003f950  sub     rcx, 1
0x18003f954  jnz     short loc_18003F946
0x18003f956  mov     rax, rcx
0x18003f959  neg     rax
0x18003f95c  sbb     ebx, ebx
0x18003f95e  not     ebx
0x18003f960  and     ebx, edi
0x18003f962  mov     rax, rcx
0x18003f965  sub     rsi, rcx
0x18003f968  neg     rax
0x18003f96b  sbb     rdx, rdx
0x18003f96e  and     rdx, rsi; length
0x18003f971  test    rcx, rcx
0x18003f974  jz      loc_18003FA31
0x18003f97a  mov     r8, r15; string
0x18003f97d  mov     rcx, r9; sourceString
0x18003f980  call    cs:__imp_WindowsCreateString
0x18003f986  mov     ebx, eax
0x18003f988  test    eax, eax
0x18003f98a  jns     short loc_18003F9E4
0x18003f98c  mov     rcx, [rbp+28h]; this
0x18003f990  mov     r9d, eax; char *
0x18003f993  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18003f99a  mov     edx, 491h; void *
0x18003f99f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003f9a4  nop
0x18003f9a5  mov     rcx, [rbp+pv]; pv
0x18003f9a9  test    rcx, rcx
0x18003f9ac  jz      short loc_18003F9B5
0x18003f9ae  call    cs:__imp_CoTaskMemFree
0x18003f9b4  nop
0x18003f9b5  mov     rcx, [rbp+sourceString]; pv
0x18003f9b9  test    rcx, rcx
0x18003f9bc  jz      short loc_18003F9C5
0x18003f9be  call    cs:__imp_CoTaskMemFree
0x18003f9c4  nop
0x18003f9c5  mov     rcx, [rbp+arg_10]
0x18003f9c9  test    rcx, rcx
0x18003f9cc  jz      short loc_18003F9DF
0x18003f9ce  mov     [rbp+arg_10], r12
0x18003f9d2  mov     rax, [rcx]
0x18003f9d5  mov     rax, [rax+10h]
0x18003f9d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f9de  nop
0x18003f9df  jmp     loc_18003FADE
0x18003f9e4  mov     rcx, [rbp+pv]; pv
0x18003f9e8  test    rcx, rcx
0x18003f9eb  jz      short loc_18003F9F4
0x18003f9ed  call    cs:__imp_CoTaskMemFree
0x18003f9f3  nop
0x18003f9f4  mov     rcx, [rbp+sourceString]; pv
0x18003f9f8  test    rcx, rcx
0x18003f9fb  jz      short loc_18003FA04
0x18003f9fd  call    cs:__imp_CoTaskMemFree
0x18003fa03  nop
0x18003fa04  mov     rcx, [rbp+arg_10]
0x18003fa08  test    rcx, rcx
0x18003fa0b  jz      short loc_18003FA1E
0x18003fa0d  mov     [rbp+arg_10], r12
0x18003fa11  mov     rax, [rcx]
0x18003fa14  mov     rax, [rax+10h]
0x18003fa18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fa1d  nop
0x18003fa1e  mov     rcx, [rbp+string]; string
0x18003fa22  call    cs:__imp_WindowsDeleteString
0x18003fa28  xor     eax, eax
0x18003fa2a  jmp     loc_18003FAEA
0x18003fa2f  mov     ebx, edi
0x18003fa31  mov     rcx, [rbp+28h]; this
0x18003fa35  mov     r9d, ebx; char *
0x18003fa38  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18003fa3f  mov     edx, 490h; void *
0x18003fa44  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003fa49  nop
0x18003fa4a  mov     rcx, [rbp+pv]; pv
0x18003fa4e  test    rcx, rcx
0x18003fa51  jz      short loc_18003FA5A
0x18003fa53  call    cs:__imp_CoTaskMemFree
0x18003fa59  nop
0x18003fa5a  mov     rcx, [rbp+sourceString]; pv
0x18003fa5e  test    rcx, rcx
0x18003fa61  jz      short loc_18003FA6A
0x18003fa63  call    cs:__imp_CoTaskMemFree
0x18003fa69  nop
0x18003fa6a  mov     rcx, [rbp+arg_10]
0x18003fa6e  test    rcx, rcx
0x18003fa71  jz      short loc_18003FA84
0x18003fa73  mov     [rbp+arg_10], r12
0x18003fa77  mov     rax, [rcx]
0x18003fa7a  mov     rax, [rax+10h]
0x18003fa7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fa83  nop
0x18003fa84  jmp     short loc_18003FADE
0x18003fa86  mov     ebx, 80070057h
0x18003fa8b  mov     rcx, [rbp+28h]; this
0x18003fa8f  mov     r9d, ebx; char *
0x18003fa92  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18003fa99  mov     edx, 48Ch; void *
0x18003fa9e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003faa3  nop
0x18003faa4  mov     rcx, [rbp+pv]; pv
0x18003faa8  test    rcx, rcx
0x18003faab  jz      short loc_18003FAB4
0x18003faad  call    cs:__imp_CoTaskMemFree
0x18003fab3  nop
0x18003fab4  mov     rcx, [rbp+sourceString]; pv
0x18003fab8  test    rcx, rcx
0x18003fabb  jz      short loc_18003FAC4
0x18003fabd  call    cs:__imp_CoTaskMemFree
0x18003fac3  nop
0x18003fac4  mov     rcx, [rbp+arg_10]
0x18003fac8  test    rcx, rcx
0x18003facb  jz      short loc_18003FADE
0x18003facd  mov     [rbp+arg_10], r12
0x18003fad1  mov     rdx, [rcx]
0x18003fad4  mov     rax, [rdx+10h]
0x18003fad8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fadd  nop
0x18003fade  mov     rcx, [rbp+string]; string
0x18003fae2  call    cs:__imp_WindowsDeleteString
0x18003fae8  mov     eax, ebx
  ... truncated ...
```
