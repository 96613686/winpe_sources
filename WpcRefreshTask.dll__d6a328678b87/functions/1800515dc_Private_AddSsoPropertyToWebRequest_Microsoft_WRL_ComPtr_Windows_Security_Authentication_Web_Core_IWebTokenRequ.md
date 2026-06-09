# Private::AddSsoPropertyToWebRequest(Microsoft::WRL::ComPtr<Windows::Security::Authentication::Web::Core::IWebTokenRequest> &)

- ea: `0x1800515dc`
- end: `0x180051780`
- name: `?AddSsoPropertyToWebRequest@Private@@YAXAEAV?$ComPtr@UIWebTokenRequest@Core@Web@Authentication@Security@Windows@@@WRL@Microsoft@@@Z`
- size: `420`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800525e4`

## callees

- `0x1800060a0`
- `0x180006ee0`
- `0x18000ecc0`
- `0x18002eb3c`
- `0x180035e0c`
- `0x1800515dc`
- `0x1800ae010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180051647`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180051675`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180051647`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180051675`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Private::AddSsoPropertyToWebRequest(_QWORD *a1)
{
  int v1; // eax
  int v2; // ebx
  _QWORD *v3; // rbx
  __int64 v4; // rdi
  HRESULT v5; // eax
  int v6; // edx
  unsigned int v7; // r8d
  HSTRING v8; // rsi
  HRESULT v9; // eax
  int v10; // edx
  unsigned int v11; // r8d
  __int64 result; // rax
  int v13; // ebx
  _QWORD *v14; // rcx
  _BYTE v15[8]; // [rsp+30h] [rbp-29h] BYREF
  _QWORD *v16; // [rsp+38h] [rbp-21h] BYREF
  HSTRING_HEADER pExceptionObject; // [rsp+40h] [rbp-19h] BYREF
  HSTRING v18; // [rsp+58h] [rbp-1h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+68h] [rbp+Fh] BYREF
  HSTRING string; // [rsp+80h] [rbp+27h] BYREF

  v15[0] = 0;
  v16 = 0;
  v1 = (*(__int64 (__fastcall **)(_QWORD, _QWORD **))(*(_QWORD *)*a1 + 80LL))(*a1, &v16);
  v2 = v1;
  if ( v1 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        10,
        WPP_d559cce52a1433e229f26c816596a62e_Traceguids,
        (unsigned int)v1);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)&pExceptionObject, v2);
    throw (ErrorCodeException *)&pExceptionObject;
  }
  v3 = v16;
  v4 = *v16;
  string = 0;
  v5 = WindowsCreateStringReference(L"windows", 7u, &hstringHeader, &string);
  if ( v5 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v5, v6, v7);
    goto LABEL_17;
  }
  v8 = string;
  v18 = 0;
  v9 = WindowsCreateStringReference(L"ssoappgroup", 0xBu, &pExceptionObject, &v18);
  if ( v9 < 0 )
  {
LABEL_17:
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v9, v10, v11);
    JUMPOUT(0x18005177FLL);
  }
  result = (*(__int64 (__fastcall **)(_QWORD *, HSTRING, HSTRING, _BYTE *))(v4 + 80))(v3, v18, v8, v15);
  v13 = result;
  if ( (int)result < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        11,
        WPP_d559cce52a1433e229f26c816596a62e_Traceguids,
        (unsigned int)result);
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)&pExceptionObject, v13);
    throw (ErrorCodeException *)&pExceptionObject;
  }
  v14 = v16;
  if ( v16 )
  {
    v16 = 0;
    return (*(__int64 (__fastcall **)(_QWORD *))(*v14 + 16LL))(v14);
  }
  return result;
}

```

## disassembly

```asm
0x1800515dc  push    rbp
0x1800515de  push    rbx
0x1800515df  push    rsi
0x1800515e0  push    rdi
0x1800515e1  lea     rbp, [rsp-3Fh]
0x1800515e6  sub     rsp, 98h
0x1800515ed  mov     rax, cs:__security_cookie
0x1800515f4  xor     rax, rsp
0x1800515f7  mov     [rbp+57h+var_28], rax
0x1800515fb  mov     [rbp+57h+var_80], 0
0x1800515ff  mov     [rbp+57h+var_78], 0
0x180051607  mov     rcx, [rcx]
0x18005160a  mov     rax, [rcx]
0x18005160d  lea     rdx, [rbp+57h+var_78]
0x180051611  mov     rax, [rax+50h]
0x180051615  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005161a  mov     ebx, eax
0x18005161c  test    eax, eax
0x18005161e  js      loc_180051723
0x180051624  mov     rbx, [rbp+57h+var_78]
0x180051628  mov     rdi, [rbx]
0x18005162b  mov     [rbp+57h+string], 0
0x180051633  lea     r9, [rbp+57h+string]; string
0x180051637  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18005163b  mov     edx, 7; length
0x180051640  lea     rcx, sourceString; "windows"
0x180051647  call    cs:__imp_WindowsCreateStringReference
0x18005164d  test    eax, eax
0x18005164f  js      loc_180051770
0x180051655  mov     rsi, [rbp+57h+string]
0x180051659  mov     [rbp+57h+var_58], 0
0x180051661  lea     r9, [rbp+57h+var_58]; string
0x180051665  lea     r8, [rbp+57h+pExceptionObject]; hstringHeader
0x180051669  mov     edx, 0Bh; length
0x18005166e  lea     rcx, aSsoappgroup; "ssoappgroup"
0x180051675  call    cs:__imp_WindowsCreateStringReference
0x18005167b  test    eax, eax
0x18005167d  js      loc_180051778
0x180051683  lea     r9, [rbp+57h+var_80]
0x180051687  mov     r8, rsi
0x18005168a  mov     rdx, [rbp+57h+var_58]
0x18005168e  mov     rcx, rbx
0x180051691  mov     rax, [rdi+50h]
0x180051695  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005169a  mov     ebx, eax
0x18005169c  test    eax, eax
0x18005169e  js      short loc_1800516D6
0x1800516a0  mov     rcx, [rbp+57h+var_78]
0x1800516a4  test    rcx, rcx
0x1800516a7  jz      short loc_1800516BE
0x1800516a9  mov     [rbp+57h+var_78], 0
0x1800516b1  mov     rax, [rcx]
0x1800516b4  mov     rax, [rax+10h]
0x1800516b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800516bd  nop
0x1800516be  mov     rcx, [rbp+57h+var_28]
0x1800516c2  xor     rcx, rsp; StackCookie
0x1800516c5  call    __security_check_cookie
0x1800516ca  add     rsp, 98h
0x1800516d1  pop     rdi
0x1800516d2  pop     rsi
0x1800516d3  pop     rbx
0x1800516d4  pop     rbp
0x1800516d5  retn
0x1800516d6  lea     rdx, WPP_GLOBAL_Control
0x1800516dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800516e4  cmp     rcx, rdx
0x1800516e7  jz      short loc_180051707
0x1800516e9  test    byte ptr [rcx+1Ch], 1
0x1800516ed  jz      short loc_180051707
0x1800516ef  mov     edx, 0Bh
0x1800516f4  mov     r9d, ebx
0x1800516f7  lea     r8, WPP_d559cce52a1433e229f26c816596a62e_Traceguids
0x1800516fe  mov     rcx, [rcx+10h]
0x180051702  call    WPP_SF_d
0x180051707  mov     edx, ebx; int
0x180051709  lea     rcx, [rbp+57h+pExceptionObject]; this
0x18005170d  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x180051712  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x180051719  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18005171d  call    _CxxThrowException_0
0x180051723  lea     rdx, WPP_GLOBAL_Control
0x18005172a  mov     rcx, cs:WPP_GLOBAL_Control
0x180051731  cmp     rcx, rdx
0x180051734  jz      short loc_180051754
0x180051736  test    byte ptr [rcx+1Ch], 1
0x18005173a  jz      short loc_180051754
0x18005173c  mov     edx, 0Ah
0x180051741  mov     r9d, ebx
0x180051744  lea     r8, WPP_d559cce52a1433e229f26c816596a62e_Traceguids
0x18005174b  mov     rcx, [rcx+10h]
0x18005174f  call    WPP_SF_d
0x180051754  mov     edx, ebx; int
0x180051756  lea     rcx, [rbp+57h+pExceptionObject]; this
0x18005175a  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x18005175f  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x180051766  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18005176a  call    _CxxThrowException_0
0x180051770  mov     ecx, eax; this
0x180051772  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x180051777  nop
0x180051778  mov     ecx, eax; this
0x18005177a  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
