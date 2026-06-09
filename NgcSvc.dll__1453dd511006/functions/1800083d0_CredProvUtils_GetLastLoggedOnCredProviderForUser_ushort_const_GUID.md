# CredProvUtils::GetLastLoggedOnCredProviderForUser(ushort const *,_GUID *)

- ea: `0x1800083d0`
- end: `0x18000860d`
- name: `?GetLastLoggedOnCredProviderForUser@CredProvUtils@@YAJPEBGPEAU_GUID@@@Z`
- size: `573`
- prototype: `int(CredProvUtils *__hidden this, const unsigned __int16 *, struct _GUID *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180042e40`

## callees

- `0x18000782c`
- `0x1800083d0`
- `0x180008620`
- `0x180009610`
- `0x180009be0`
- `0x180009e94`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800084bd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800084bd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800084f3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800084f3`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180008508`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180008508`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008531`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800085b6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800085c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008531`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800085b6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800085c4`

## string_xrefs

- `0x18000842b`: `onecore\shell\auth\credprovcommon\credprovutils\credprovutils.cpp`
- `0x180008541`: `onecore\shell\auth\credprovcommon\credprovutils\credprovutils.cpp`
- `0x180008589`: `onecore\shell\auth\credprovcommon\credprovutils\credprovutils.cpp`
- `0x1800085de`: `onecore\shell\auth\credprovcommon\credprovutils\credprovutils.cpp`

## pseudocode

```c
__int64 __fastcall CredProvUtils::GetLastLoggedOnCredProviderForUser(
        const WCHAR *this,
        unsigned __int16 **a2,
        struct _GUID *a3)
{
  int LogonUIKeyPath; // esi
  __int64 v6; // rdx
  WCHAR *v8; // rbp
  LSTATUS v9; // eax
  GUID *v10; // rdx
  OLECHAR *v11; // rbx
  HRESULT v12; // eax
  unsigned int v13; // edi
  int phkResult; // [rsp+20h] [rbp-48h]
  int phkResulta; // [rsp+20h] [rbp-48h]
  LPVOID lpSubKey[3]; // [rsp+30h] [rbp-38h] BYREF
  LPCOLESTR lpsz[4]; // [rsp+48h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  HKEY hKey; // [rsp+70h] [rbp+8h] BYREF

  if ( this )
  {
    if ( a2 )
    {
      lpSubKey[0] = 0;
      lpSubKey[1] = (LPVOID)-1LL;
      lpSubKey[2] = (LPVOID)-1LL;
      LogonUIKeyPath = CredProvUtils::GetLogonUIKeyPath((CredProvUtils *)lpSubKey, a2);
      if ( LogonUIKeyPath < 0 )
      {
        v6 = 74;
        goto LABEL_5;
      }
      LogonUIKeyPath = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::ConcatFormat(
                         lpSubKey,
                         L"\\%s",
                         L"UserTile");
      if ( LogonUIKeyPath < 0 )
      {
        v6 = 75;
LABEL_5:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v6,
          (unsigned int)"onecore\\shell\\auth\\credprovcommon\\credprovutils\\credprovutils.cpp",
          (const char *)(unsigned int)LogonUIKeyPath,
          phkResult);
        if ( lpSubKey[0] )
          CoTaskMemFree(lpSubKey[0]);
        return (unsigned int)LogonUIKeyPath;
      }
      hKey = 0;
      memset(lpsz, 0, 24);
      v8 = (WCHAR *)lpSubKey[0];
      v9 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, (LPCWSTR)lpSubKey[0], 0, 0x20019u, &hKey);
      LogonUIKeyPath = v9;
      if ( v9 > 0 )
        LogonUIKeyPath = (unsigned __int16)v9 | 0x80070000;
      if ( LogonUIKeyPath < 0
        || (LogonUIKeyPath = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_InitializeFromRegistry(
                               (__int64)lpsz,
                               hKey,
                               this),
            RegCloseKey(hKey),
            LogonUIKeyPath < 0) )
      {
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(lpsz);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(lpSubKey);
        return (unsigned int)LogonUIKeyPath;
      }
      v10 = (GUID *)a2;
      v11 = (OLECHAR *)lpsz[0];
      v12 = CLSIDFromString(lpsz[0], v10);
      v13 = v12;
      if ( v12 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x53,
          (unsigned int)"onecore\\shell\\auth\\credprovcommon\\credprovutils\\credprovutils.cpp",
          (const char *)(unsigned int)v12,
          phkResulta);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(lpsz);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(lpSubKey);
        return v13;
      }
      else
      {
        if ( v11 )
          CoTaskMemFree(v11);
        if ( v8 )
          CoTaskMemFree(v8);
        return 0;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x47,
        (unsigned int)"onecore\\shell\\auth\\credprovcommon\\credprovutils\\credprovutils.cpp",
        (const char *)0x80004003LL,
        phkResult);
      return 2147500035LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x46,
      (unsigned int)"onecore\\shell\\auth\\credprovcommon\\credprovutils\\credprovutils.cpp",
      (const char *)0x80004003LL,
      phkResult);
    return 2147500035LL;
  }
}

```

## disassembly

```asm
0x1800083d0  mov     rax, rsp
0x1800083d3  mov     [rax+20h], rbx
0x1800083d7  push    rdi
0x1800083d8  sub     rsp, 60h
0x1800083dc  mov     rbx, rdx
0x1800083df  mov     rdi, rcx
0x1800083e2  test    rcx, rcx
0x1800083e5  jz      loc_180008584
0x1800083eb  test    rdx, rdx
0x1800083ee  jz      loc_18000853C
0x1800083f4  mov     [rax+10h], rbp
0x1800083f8  lea     rcx, [rax-38h]; this
0x1800083fc  xor     ebp, ebp
0x1800083fe  mov     [rax+18h], rsi
0x180008402  mov     [rax-38h], rbp
0x180008406  mov     qword ptr [rax-30h], 0FFFFFFFFFFFFFFFFh
0x18000840e  mov     qword ptr [rax-28h], 0FFFFFFFFFFFFFFFFh
0x180008416  call    ?GetLogonUIKeyPath@CredProvUtils@@YAJPEAPEAG@Z; CredProvUtils::GetLogonUIKeyPath(ushort * *)
0x18000841b  mov     esi, eax
0x18000841d  test    eax, eax
0x18000841f  jns     short loc_180008465
0x180008421  mov     edx, 4Ah ; 'J'; void *
0x180008426  mov     rcx, [rsp+68h]; this
0x18000842b  lea     r8, aOnecoreShellAu; "onecore\\shell\\auth\\credprovcommon\\c"...
0x180008432  mov     r9d, esi; char *
0x180008435  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000843a  mov     rcx, [rsp+68h+lpSubKey]; pv
0x18000843f  test    rcx, rcx
0x180008442  jnz     loc_180008531
0x180008448  mov     eax, esi
0x18000844a  mov     rbp, [rsp+68h+arg_8]
0x18000844f  mov     rsi, [rsp+68h+arg_10]
0x180008457  mov     rbx, [rsp+68h+arg_18]
0x18000845f  add     rsp, 60h
0x180008463  pop     rdi
0x180008464  retn
0x180008465  lea     r8, aUsertile; "UserTile"
0x18000846c  lea     rdx, aS_0; "\\%s"
0x180008473  lea     rcx, [rsp+68h+lpSubKey]
0x180008478  call    ?ConcatFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::ConcatFormat(ushort const *,...)
0x18000847d  mov     esi, eax
0x18000847f  test    eax, eax
0x180008481  js      loc_1800085CF
0x180008487  mov     [rsp+68h+hKey], rbp
0x18000848c  lea     rax, [rsp+68h+hKey]
0x180008491  mov     [rsp+68h+lpsz], rbp
0x180008496  mov     r9d, 20019h; samDesired
0x18000849c  mov     [rsp+68h+var_18], rbp
0x1800084a1  xor     r8d, r8d; ulOptions
0x1800084a4  mov     [rsp+68h+var_10], rbp
0x1800084a9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800084b0  mov     rbp, [rsp+68h+lpSubKey]
0x1800084b5  mov     rdx, rbp; lpSubKey
0x1800084b8  mov     qword ptr [rsp+68h+phkResult], rax; int
0x1800084bd  call    cs:__imp_RegOpenKeyExW
0x1800084c3  mov     esi, eax
0x1800084c5  test    eax, eax
0x1800084c7  jle     short loc_1800084D2
0x1800084c9  movzx   esi, ax
0x1800084cc  or      esi, 80070000h
0x1800084d2  test    esi, esi
0x1800084d4  js      loc_18000856B
0x1800084da  mov     rdx, [rsp+68h+hKey]
0x1800084df  lea     rcx, [rsp+68h+lpsz]
0x1800084e4  mov     r8, rdi
0x1800084e7  call    ?_InitializeFromRegistry@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEAUHKEY__@@PEBG_N@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_InitializeFromRegistry(HKEY__ *,ushort const *,bool)
0x1800084ec  mov     rcx, [rsp+68h+hKey]; hKey
0x1800084f1  mov     esi, eax
0x1800084f3  call    cs:__imp_RegCloseKey
0x1800084f9  test    esi, esi
0x1800084fb  js      short loc_18000856B
0x1800084fd  mov     rdx, rbx; pclsid
0x180008500  mov     rbx, [rsp+68h+lpsz]
0x180008505  mov     rcx, rbx; lpsz
0x180008508  call    cs:__imp_CLSIDFromString
0x18000850e  mov     edi, eax
0x180008510  test    eax, eax
0x180008512  js      loc_1800085D9
0x180008518  test    rbx, rbx
0x18000851b  jnz     loc_1800085B3
0x180008521  test    rbp, rbp
0x180008524  jnz     loc_1800085C1
0x18000852a  xor     eax, eax
0x18000852c  jmp     loc_18000844A
0x180008531  call    cs:__imp_CoTaskMemFree
0x180008537  jmp     loc_180008448
0x18000853c  mov     rcx, [rsp+68h]; this
0x180008541  lea     r8, aOnecoreShellAu; "onecore\\shell\\auth\\credprovcommon\\c"...
0x180008548  mov     r9d, 80004003h; char *
0x18000854e  mov     edx, 47h ; 'G'; void *
0x180008553  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008558  mov     eax, 80004003h
0x18000855d  mov     rbx, [rsp+68h+arg_18]
0x180008565  add     rsp, 60h
0x180008569  pop     rdi
0x18000856a  retn
0x18000856b  lea     rcx, [rsp+68h+lpsz]
0x180008570  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180008575  lea     rcx, [rsp+68h+lpSubKey]
0x18000857a  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18000857f  jmp     loc_180008448
0x180008584  mov     rcx, [rsp+68h]; this
0x180008589  lea     r8, aOnecoreShellAu; "onecore\\shell\\auth\\credprovcommon\\c"...
0x180008590  mov     r9d, 80004003h; char *
0x180008596  mov     edx, 46h ; 'F'; void *
0x18000859b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800085a0  mov     rbx, [rsp+68h+arg_18]
0x1800085a8  mov     eax, 80004003h
0x1800085ad  add     rsp, 60h
0x1800085b1  pop     rdi
0x1800085b2  retn
0x1800085b3  mov     rcx, rbx; pv
0x1800085b6  call    cs:__imp_CoTaskMemFree
0x1800085bc  jmp     loc_180008521
0x1800085c1  mov     rcx, rbp; pv
0x1800085c4  call    cs:__imp_CoTaskMemFree
0x1800085ca  jmp     loc_18000852A
0x1800085cf  mov     edx, 4Bh ; 'K'
0x1800085d4  jmp     loc_180008426
0x1800085d9  mov     rcx, [rsp+68h]; this
0x1800085de  lea     r8, aOnecoreShellAu; "onecore\\shell\\auth\\credprovcommon\\c"...
0x1800085e5  mov     r9d, edi; char *
0x1800085e8  mov     edx, 53h ; 'S'; void *
0x1800085ed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800085f2  lea     rcx, [rsp+68h+lpsz]
0x1800085f7  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800085fc  lea     rcx, [rsp+68h+lpSubKey]
0x180008601  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180008606  mov     eax, edi
0x180008608  jmp     loc_18000844A
```
