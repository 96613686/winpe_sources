# CUserIdentityProvider::ClearWAMTicketCacheForAppId(ushort const *)

- ea: `0x1800b16f8`
- end: `0x1800b1864`
- name: `?ClearWAMTicketCacheForAppId@CUserIdentityProvider@@CAJPEBG@Z`
- size: `364`
- prototype: `__int64 __fastcall(LPCOLESTR lpsz)`
- caller_count: `3`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800b151c`
- `0x1800b1664`
- `0x1800b8540`

## callees

- `0x180004b80`
- `0x18000b19c`
- `0x18000cc8c`
- `0x1800afa30`
- `0x1800b0b00`
- `0x1800b16f8`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b1750`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b1750`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800b177e`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800b177e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800b1737`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800b1737`

## string_xrefs

- `0x1800b1730`: `Windows.Internal.Security.WebAuthentication.AuthenticationManager`
- `0x1800b1796`: `onecore\base\flighting\flightsettings\broker\lib\useridentityprovider.cpp`
- `0x1800b1820`: `onecore\base\flighting\flightsettings\broker\lib\useridentityprovider.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CUserIdentityProvider::ClearWAMTicketCacheForAppId(LPCOLESTR lpsz)
{
  int v2; // eax
  unsigned int v3; // ebx
  __int64 v4; // rdx
  __int64 v5; // rdi
  __int64 (__fastcall *v6)(__int64, __int64 *); // rbx
  int v7; // eax
  __int64 v8; // rdx
  __int64 v10; // [rsp+20h] [rbp-50h] BYREF
  __int64 v11; // [rsp+28h] [rbp-48h] BYREF
  GUID pclsid; // [rsp+30h] [rbp-40h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+8h]

  v11 = 0;
  if ( WindowsCreateStringReference(
         L"Windows.Internal.Security.WebAuthentication.AuthenticationManager",
         0x41u,
         (HSTRING_HEADER *)&hstringHeader.Reserved.Reserved2[8],
         (HSTRING *)&hstringHeader) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v2 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Internal::Security::WebAuthentication::IAuthenticationManager>>(
         (__int64)hstringHeader.Reserved.Reserved1,
         &v11);
  v3 = v2;
  if ( v2 >= 0 )
  {
    pclsid = 0;
    v2 = CLSIDFromString(lpsz, &pclsid);
    v3 = v2;
    if ( v2 < 0 )
    {
      v4 = 961;
      goto LABEL_7;
    }
    *(GUID *)&hstringHeader.Reserved.Reserved1 = pclsid;
    v2 = (*(__int64 (__fastcall **)(__int64, HSTRING_HEADER *))(*(_QWORD *)v11 + 72LL))(v11, &hstringHeader);
    v3 = v2;
    if ( v2 < 0 )
    {
      v4 = 962;
      goto LABEL_7;
    }
    v10 = 0;
    v5 = v11;
    v6 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v11 + 48LL);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v10);
    v7 = v6(v5, &v10);
    v3 = v7;
    if ( v7 >= 0 )
    {
      v7 = WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(v10);
      v3 = v7;
      if ( v7 >= 0 )
      {
LABEL_15:
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v10);
        goto LABEL_16;
      }
      v8 = 967;
    }
    else
    {
      v8 = 965;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\useridentityprovider.cpp",
      (const char *)(unsigned int)v7,
      v10);
    goto LABEL_15;
  }
  v4 = 958;
LABEL_7:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v4,
    (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\useridentityprovider.cpp",
    (const char *)(unsigned int)v2,
    v10);
LABEL_16:
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v11);
  return v3;
}

```

## disassembly

```asm
0x1800b16f8  mov     [rsp-8+arg_8], rbx
0x1800b16fd  mov     [rsp-8+arg_10], rdi
0x1800b1702  push    rbp
0x1800b1703  mov     rbp, rsp
0x1800b1706  sub     rsp, 70h
0x1800b170a  mov     rax, cs:__security_cookie
0x1800b1711  xor     rax, rsp
0x1800b1714  mov     [rbp+var_10], rax
0x1800b1718  mov     rdi, rcx
0x1800b171b  mov     [rbp+var_48], 0
0x1800b1723  lea     r9, [rbp+hstringHeader]; string
0x1800b1727  lea     r8, [rbp+hstringHeader.Reserved+8]; hstringHeader
0x1800b172b  mov     edx, 41h ; 'A'; length
0x1800b1730  lea     rcx, ?RuntimeClass_Windows_Internal_Security_WebAuthentication_AuthenticationManager@@3QBGB; "Windows.Internal.Security.WebAuthentica"...
0x1800b1737  call    cs:__imp_WindowsCreateStringReference
0x1800b173d  test    eax, eax
0x1800b173f  jns     short loc_1800B1756
0x1800b1741  xor     r9d, r9d; lpArguments
0x1800b1744  xor     r8d, r8d; nNumberOfArguments
0x1800b1747  lea     edx, [r9+1]; dwExceptionFlags
0x1800b174b  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800b1750  call    cs:__imp_RaiseException
0x1800b1756  lea     rdx, [rbp+var_48]
0x1800b175a  mov     rcx, qword ptr [rbp+hstringHeader.Reserved]
0x1800b175e  call    ??$ActivateInstance@V?$ComPtr@UIAuthenticationManager@WebAuthentication@Security@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIAuthenticationManager@WebAuthentication@Security@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Internal::Security::WebAuthentication::IAuthenticationManager>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::Security::WebAuthentication::IAuthenticationManager>>)
0x1800b1763  mov     ebx, eax
0x1800b1765  test    eax, eax
0x1800b1767  jns     short loc_1800B1770
0x1800b1769  mov     edx, 3BEh
0x1800b176e  jmp     short loc_1800B178F
0x1800b1770  xorps   xmm0, xmm0
0x1800b1773  movups  xmmword ptr [rbp+pclsid.Data1], xmm0
0x1800b1777  lea     rdx, [rbp+pclsid]; pclsid
0x1800b177b  mov     rcx, rdi; lpsz
0x1800b177e  call    cs:__imp_CLSIDFromString
0x1800b1784  mov     ebx, eax
0x1800b1786  test    eax, eax
0x1800b1788  jns     short loc_1800B17A7
0x1800b178a  mov     edx, 3C1h; void *
0x1800b178f  mov     rcx, [rbp+8]; this
0x1800b1793  mov     r9d, eax; char *
0x1800b1796  lea     r8, aOnecoreBaseFli_12; "onecore\\base\\flighting\\flightsetting"...
0x1800b179d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b17a2  jmp     loc_1800B183B
0x1800b17a7  mov     rcx, [rbp+var_48]
0x1800b17ab  movaps  xmm0, xmmword ptr [rbp+pclsid.Data1]
0x1800b17af  movdqa  xmmword ptr [rbp+hstringHeader.Reserved], xmm0
0x1800b17b4  mov     rax, [rcx]
0x1800b17b7  lea     rdx, [rbp+hstringHeader]
0x1800b17bb  mov     rax, [rax+48h]
0x1800b17bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b17c4  mov     ebx, eax
0x1800b17c6  test    eax, eax
0x1800b17c8  jns     short loc_1800B17D1
0x1800b17ca  mov     edx, 3C2h
0x1800b17cf  jmp     short loc_1800B178F
0x1800b17d1  mov     [rbp+var_50], 0
0x1800b17d9  mov     rdi, [rbp+var_48]
0x1800b17dd  mov     rax, [rdi]
0x1800b17e0  mov     rbx, [rax+30h]
0x1800b17e4  lea     rcx, [rbp+var_50]
0x1800b17e8  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800b17ed  lea     rdx, [rbp+var_50]
0x1800b17f1  mov     rcx, rdi
0x1800b17f4  mov     rax, rbx
0x1800b17f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b17fc  mov     ebx, eax
0x1800b17fe  test    eax, eax
0x1800b1800  jns     short loc_1800B1809
0x1800b1802  mov     edx, 3C5h
0x1800b1807  jmp     short loc_1800B181D
0x1800b1809  mov     rcx, [rbp+var_50]
0x1800b180d  call    ??$WaitForCompletion@UIAsyncActionCompletedHandler@Foundation@Windows@@UIAsyncAction@23@@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,void *)
0x1800b1812  mov     ebx, eax
0x1800b1814  test    eax, eax
0x1800b1816  jns     short loc_1800B1831
0x1800b1818  mov     edx, 3C7h; void *
0x1800b181d  mov     r9d, eax; char *
0x1800b1820  lea     r8, aOnecoreBaseFli_12; "onecore\\base\\flighting\\flightsetting"...
0x1800b1827  mov     rcx, [rbp+8]; this
0x1800b182b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b1830  nop
0x1800b1831  lea     rcx, [rbp+var_50]
0x1800b1835  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800b183a  nop
0x1800b183b  lea     rcx, [rbp+var_48]
0x1800b183f  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800b1844  mov     eax, ebx
0x1800b1846  mov     rcx, [rbp+var_10]
0x1800b184a  xor     rcx, rsp; StackCookie
0x1800b184d  call    __security_check_cookie
0x1800b1852  lea     r11, [rsp+70h+var_s0]
0x1800b1857  mov     rbx, [r11+18h]
0x1800b185b  mov     rdi, [r11+20h]
0x1800b185f  mov     rsp, r11
0x1800b1862  pop     rbp
0x1800b1863  retn
```
