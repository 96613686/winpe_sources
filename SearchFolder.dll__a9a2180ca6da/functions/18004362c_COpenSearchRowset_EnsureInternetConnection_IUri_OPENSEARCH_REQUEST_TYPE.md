# COpenSearchRowset::_EnsureInternetConnection(IUri *,OPENSEARCH_REQUEST_TYPE)

- ea: `0x18004362c`
- end: `0x180043828`
- name: `?_EnsureInternetConnection@COpenSearchRowset@@AEAAJPEAUIUri@@W4OPENSEARCH_REQUEST_TYPE@@@Z`
- size: `508`
- prototype: `__int64 __fastcall(__int64, __int64 *, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800451b0`

## callees

- `0x180006900`
- `0x1800076dc`
- `0x18000ecc4`
- `0x18000eec0`
- `0x18002fa14`
- `0x1800435e8`
- `0x18004362c`
- `0x180051010`

## import_xrefs

- `SHLWAPI!__imp_StrCmpICW` at `0x1800436ca`
- `SHLWAPI!__imp_StrCmpICW` at `0x1800436ca`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x18004370e`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x18004370e`
- `OLEAUT32!__imp_SysFreeString` at `0x1800437f9`
- `OLEAUT32!__imp_SysFreeString` at `0x1800437f9`
- `WININET!InternetConnectW` at `0x1800437bb`
- `WININET!InternetConnectW` at `0x1800437bb`
- `WININET!InternetOpenW` at `0x180043767`
- `WININET!InternetOpenW` at `0x180043767`

## pseudocode

```c
__int64 __fastcall COpenSearchRowset::_EnsureInternetConnection(__int64 a1, __int64 *a2, int a3)
{
  __int64 v3; // rax
  int Error; // ebx
  __int64 v8; // rax
  HINTERNET v9; // rax
  DWORD v10; // ecx
  HINTERNET v11; // rax
  DWORD dwFlags; // [rsp+20h] [rbp-E0h]
  int v14; // [rsp+40h] [rbp-C0h] BYREF
  LPCWSTR pszStr1; // [rsp+48h] [rbp-B8h] BYREF
  _OSVERSIONINFOW VersionInformation; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR szAgent[56]; // [rsp+170h] [rbp+70h] BYREF

  v3 = *a2;
  v14 = 0;
  Error = (*(__int64 (__fastcall **)(__int64 *, int *))(v3 + 184))(a2, &v14);
  if ( Error >= 0 )
  {
    v8 = *a2;
    pszStr1 = 0;
    Error = (*(__int64 (__fastcall **)(__int64 *, LPCWSTR *))(v8 + 104))(a2, &pszStr1);
    if ( Error >= 0 )
    {
      if ( *(_QWORD *)(a1 + 88)
        && *(_QWORD *)(a1 + 96)
        && !StrCmpICW(pszStr1, (LPCWSTR)(a1 + 108))
        && *(_DWORD *)(a1 + 620) == v14 )
      {
        Error = 0;
      }
      else
      {
        COpenSearchRowset::_CloseConnection((COpenSearchRowset *)a1);
        memset_0(&VersionInformation.dwMajorVersion, 0, 0x110u);
        VersionInformation.dwOSVersionInfoSize = 276;
        if ( GetVersionExW(&VersionInformation) || (Error = ResultFromKnownLastError(), Error >= 0) )
        {
          dwFlags = VersionInformation.dwMinorVersion;
          Error = StringCchPrintfW(
                    szAgent,
                    0x32u,
                    L"Windows-Search (Windows NT %d.%d)",
                    VersionInformation.dwMajorVersion,
                    dwFlags);
          if ( Error >= 0 )
          {
            v9 = InternetOpenW(szAgent, 0, 0, 0, 0);
            *(_QWORD *)(a1 + 88) = v9;
            if ( v9 || (Error = ResultFromKnownLastError(), Error >= 0) )
            {
              v10 = 0x10000000;
              if ( a3 != 1 )
                v10 = 0;
              v11 = InternetConnectW(*(HINTERNET *)(a1 + 88), pszStr1, v14, &psz, &psz, 3u, v10, 0);
              *(_QWORD *)(a1 + 96) = v11;
              if ( v11 || (Error = ResultFromKnownLastError(), Error >= 0) )
              {
                Error = StringCchCopyW((unsigned __int16 *)(a1 + 108), 0x100u, pszStr1);
                *(_DWORD *)(a1 + 620) = v14;
              }
            }
          }
        }
      }
    }
    SysFreeString((BSTR)pszStr1);
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18004362c  mov     [rsp-8+arg_10], rbx
0x180043631  mov     [rsp-8+arg_18], rsi
0x180043636  push    rbp
0x180043637  push    rdi
0x180043638  push    r14
0x18004363a  lea     rbp, [rsp-0F0h]
0x180043642  sub     rsp, 1F0h
0x180043649  mov     rax, cs:__security_cookie
0x180043650  xor     rax, rsp
0x180043653  mov     [rbp+100h+var_20], rax
0x18004365a  mov     rax, [rdx]
0x18004365d  mov     rsi, rdx
0x180043660  mov     rdi, rcx
0x180043663  mov     [rsp+200h+var_1C0], 0
0x18004366b  lea     rdx, [rsp+200h+var_1C0]
0x180043670  mov     rcx, rsi
0x180043673  mov     r14d, r8d
0x180043676  mov     rax, [rax+0B8h]
0x18004367d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043682  mov     ebx, eax
0x180043684  test    eax, eax
0x180043686  js      loc_1800437FF
0x18004368c  mov     rax, [rsi]
0x18004368f  lea     rdx, [rsp+200h+pszStr1]
0x180043694  mov     rcx, rsi
0x180043697  mov     [rsp+200h+pszStr1], 0
0x1800436a0  mov     rax, [rax+68h]
0x1800436a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800436a9  mov     ebx, eax
0x1800436ab  test    eax, eax
0x1800436ad  js      loc_1800437F4
0x1800436b3  cmp     qword ptr [rdi+58h], 0
0x1800436b8  jz      short loc_1800436E7
0x1800436ba  cmp     qword ptr [rdi+60h], 0
0x1800436bf  jz      short loc_1800436E7
0x1800436c1  mov     rcx, [rsp+200h+pszStr1]; pszStr1
0x1800436c6  lea     rdx, [rdi+6Ch]; pszStr2
0x1800436ca  call    cs:__imp_StrCmpICW
0x1800436d0  test    eax, eax
0x1800436d2  jnz     short loc_1800436E7
0x1800436d4  mov     eax, [rsp+200h+var_1C0]
0x1800436d8  cmp     [rdi+26Ch], eax
0x1800436de  jnz     short loc_1800436E7
0x1800436e0  xor     ebx, ebx
0x1800436e2  jmp     loc_1800437F4
0x1800436e7  mov     rcx, rdi; this
0x1800436ea  call    ?_CloseConnection@COpenSearchRowset@@AEAAXXZ; COpenSearchRowset::_CloseConnection(void)
0x1800436ef  xor     edx, edx; Val
0x1800436f1  lea     rcx, [rsp+200h+VersionInformation.dwMajorVersion]; void *
0x1800436f6  mov     r8d, 110h; Size
0x1800436fc  call    memset_0
0x180043701  lea     rcx, [rsp+200h+VersionInformation]; lpVersionInformation
0x180043706  mov     [rsp+200h+VersionInformation.dwOSVersionInfoSize], 114h
0x18004370e  call    cs:__imp_GetVersionExW
0x180043714  test    eax, eax
0x180043716  jnz     short loc_180043727
0x180043718  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18004371d  mov     ebx, eax
0x18004371f  test    eax, eax
0x180043721  js      loc_1800437F4
0x180043727  mov     eax, [rsp+200h+VersionInformation.dwMinorVersion]
0x18004372b  lea     r8, aWindowsSearchW; "Windows-Search (Windows NT %d.%d)"
0x180043732  mov     r9d, [rsp+200h+VersionInformation.dwMajorVersion]
0x180043737  lea     rcx, [rbp+100h+szAgent]; unsigned __int16 *
0x18004373b  mov     edx, 32h ; '2'; unsigned __int64
0x180043740  mov     [rsp+200h+dwFlags], eax
0x180043744  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180043749  mov     ebx, eax
0x18004374b  test    eax, eax
0x18004374d  js      loc_1800437F4
0x180043753  xor     r9d, r9d; lpszProxyBypass
0x180043756  mov     [rsp+200h+dwFlags], 0; dwFlags
0x18004375e  xor     r8d, r8d; lpszProxy
0x180043761  lea     rcx, [rbp+100h+szAgent]; lpszAgent
0x180043765  xor     edx, edx; dwAccessType
0x180043767  call    cs:__imp_InternetOpenW
0x18004376d  mov     [rdi+58h], rax
0x180043771  test    rax, rax
0x180043774  jnz     short loc_180043781
0x180043776  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18004377b  mov     ebx, eax
0x18004377d  test    eax, eax
0x18004377f  js      short loc_1800437F4
0x180043781  movzx   r8d, word ptr [rsp+200h+var_1C0]; nServerPort
0x180043787  lea     r9, psz; lpszUserName
0x18004378e  mov     rdx, [rsp+200h+pszStr1]; lpszServerName
0x180043793  xor     eax, eax
0x180043795  mov     [rsp+200h+dwContext], rax; dwContext
0x18004379a  mov     ecx, 10000000h
0x18004379f  cmp     r14d, 1
0x1800437a3  cmovnz  ecx, eax
0x1800437a6  mov     [rsp+200h+var_1D0], ecx; dwFlags
0x1800437aa  mov     rcx, [rdi+58h]; hInternet
0x1800437ae  mov     [rsp+200h+dwService], 3; dwService
0x1800437b6  mov     qword ptr [rsp+200h+dwFlags], r9; lpszPassword
0x1800437bb  call    cs:__imp_InternetConnectW
0x1800437c1  mov     [rdi+60h], rax
0x1800437c5  test    rax, rax
0x1800437c8  jnz     short loc_1800437D5
0x1800437ca  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800437cf  mov     ebx, eax
0x1800437d1  test    eax, eax
0x1800437d3  js      short loc_1800437F4
0x1800437d5  mov     r8, [rsp+200h+pszStr1]; unsigned __int16 *
0x1800437da  lea     rcx, [rdi+6Ch]; unsigned __int16 *
0x1800437de  mov     edx, 100h; unsigned __int64
0x1800437e3  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800437e8  mov     ebx, eax
0x1800437ea  mov     eax, [rsp+200h+var_1C0]
0x1800437ee  mov     [rdi+26Ch], eax
0x1800437f4  mov     rcx, [rsp+200h+pszStr1]; bstrString
0x1800437f9  call    cs:__imp_SysFreeString
0x1800437ff  mov     eax, ebx
0x180043801  mov     rcx, [rbp+100h+var_20]
0x180043808  xor     rcx, rsp; StackCookie
0x18004380b  call    __security_check_cookie
0x180043810  lea     r11, [rsp+200h+var_10]
0x180043818  mov     rbx, [r11+30h]
0x18004381c  mov     rsi, [r11+38h]
0x180043820  mov     rsp, r11
0x180043823  pop     r14
0x180043825  pop     rdi
0x180043826  pop     rbp
0x180043827  retn
```
