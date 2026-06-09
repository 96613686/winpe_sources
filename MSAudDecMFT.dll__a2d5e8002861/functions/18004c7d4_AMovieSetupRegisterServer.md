# AMovieSetupRegisterServer

- ea: `0x18004c7d4`
- end: `0x18004caed`
- name: `AMovieSetupRegisterServer`
- size: `793`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800566d8`

## callees

- `0x18004c7d4`
- `0x18004d320`
- `0x180056128`
- `0x180056188`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004c8f8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004c9f8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004ca8a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004c8f8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004c9f8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004ca8a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004c87e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004c984`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004c87e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004c984`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004c90f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004ca0f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004ca9d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004caae`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004c90f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004ca0f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004ca9d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004caae`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18004c80e`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18004c80e`

## string_xrefs

- `0x18004ca61`: `ThreadingModel`
- `0x18004c831`: `CLSID\%ls`

## pseudocode

```c
__int64 __fastcall AMovieSetupRegisterServer(const GUID *a1, __int64 a2, __int64 a3)
{
  LSTATUS v5; // eax
  __int64 result; // rax
  LSTATUS v7; // ebx
  HKEY v8; // rcx
  LSTATUS v9; // ebx
  unsigned __int64 v10; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  HKEY phkResult; // [rsp+60h] [rbp-A0h] BYREF
  OLECHAR sz[40]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR SubKey[264]; // [rsp+C0h] [rbp-40h] BYREF

  StringFromGUID2(a1, sz, 39);
  hKey = 0;
  StringCchPrintfW(SubKey, 0x104u, L"CLSID\\%ls", sz);
  v5 = RegCreateKeyExW(HKEY_CLASSES_ROOT, SubKey, 0, 0, 0, 0x2000000u, 0, &hKey, 0);
  if ( v5 )
    return v5 | 0x80070000;
  StringCchPrintfW(SubKey, 0x104u, L"%ls", a2);
  v10 = 0;
  result = StringCchLengthW(SubKey, 0x104u, &v10);
  if ( (int)result >= 0 )
  {
    v7 = RegSetValueExW(hKey, 0, 0, 1u, (const BYTE *)SubKey, 2 * v10 + 2);
    if ( v7
      || (phkResult = 0,
          StringCchPrintfW(SubKey, 0x104u, L"%ls", L"InprocServer32"),
          (v7 = RegCreateKeyExW(hKey, SubKey, 0, 0, 0, 0x2000000u, 0, &phkResult, 0)) != 0) )
    {
      v8 = hKey;
    }
    else
    {
      StringCchPrintfW(SubKey, 0x104u, L"%ls", a3);
      v10 = 0;
      result = StringCchLengthW(SubKey, 0x104u, &v10);
      if ( (int)result < 0 )
        return result;
      v7 = RegSetValueExW(phkResult, 0, 0, v7 + 1, (const BYTE *)SubKey, 2 * v10 + 2);
      if ( !v7 )
      {
        StringCchPrintfW(SubKey, 0x104u, L"%ls", L"Both");
        v10 = 0;
        result = StringCchLengthW(SubKey, 0x104u, &v10);
        if ( (int)result < 0 )
          return result;
        v9 = RegSetValueExW(phkResult, L"ThreadingModel", 0, 1u, (const BYTE *)SubKey, 2 * v10 + 2);
        RegCloseKey(hKey);
        RegCloseKey(phkResult);
        if ( v9 > 0 )
          return (unsigned __int16)v9 | 0x80070000;
        return (unsigned int)v9;
      }
      RegCloseKey(hKey);
      v8 = phkResult;
    }
    RegCloseKey(v8);
    return v7 | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x18004c7d4  mov     [rsp-8+arg_18], rbx
0x18004c7d9  push    rbp
0x18004c7da  push    rdi
0x18004c7db  push    r14
0x18004c7dd  lea     rbp, [rsp-1E0h]
0x18004c7e5  sub     rsp, 2E0h
0x18004c7ec  mov     rax, cs:__security_cookie
0x18004c7f3  xor     rax, rsp
0x18004c7f6  mov     [rbp+1F0h+var_20], rax
0x18004c7fd  mov     rdi, r8
0x18004c800  mov     rbx, rdx
0x18004c803  mov     r8d, 27h ; '''; cchMax
0x18004c809  lea     rdx, [rsp+2F0h+sz]; lpsz
0x18004c80e  call    cs:__imp_StringFromGUID2
0x18004c815  nop     dword ptr [rax+rax+00h]
0x18004c81a  mov     r14d, 104h
0x18004c820  mov     [rsp+2F0h+hKey], 0
0x18004c829  mov     edx, r14d; unsigned __int64
0x18004c82c  lea     r9, [rsp+2F0h+sz]
0x18004c831  lea     r8, aClsidLs; "CLSID\\%ls"
0x18004c838  lea     rcx, [rbp+1F0h+SubKey]; Buffer
0x18004c83c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004c841  mov     [rsp+2F0h+lpdwDisposition], 0; lpdwDisposition
0x18004c84a  lea     rax, [rsp+2F0h+hKey]
0x18004c84f  mov     [rsp+2F0h+phkResult], rax; phkResult
0x18004c854  lea     rdx, [rbp+1F0h+SubKey]; lpSubKey
0x18004c858  mov     [rsp+2F0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18004c861  xor     r9d, r9d; lpClass
0x18004c864  mov     [rsp+2F0h+samDesired], 2000000h; samDesired
0x18004c86c  xor     r8d, r8d; Reserved
0x18004c86f  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18004c876  mov     [rsp+2F0h+dwOptions], 0; dwOptions
0x18004c87e  call    cs:__imp_RegCreateKeyExW
0x18004c885  nop     dword ptr [rax+rax+00h]
0x18004c88a  test    eax, eax
0x18004c88c  jz      short loc_18004C898
0x18004c88e  or      eax, 80070000h
0x18004c893  jmp     loc_18004CAC9
0x18004c898  mov     r9, rbx
0x18004c89b  lea     r8, aLs; "%ls"
0x18004c8a2  mov     rdx, r14; unsigned __int64
0x18004c8a5  lea     rcx, [rbp+1F0h+SubKey]; Buffer
0x18004c8a9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004c8ae  lea     r8, [rsp+2F0h+var_2A0]; unsigned __int64 *
0x18004c8b3  mov     [rsp+2F0h+var_2A0], 0
0x18004c8bc  mov     rdx, r14; unsigned __int64
0x18004c8bf  lea     rcx, [rbp+1F0h+SubKey]; unsigned __int16 *
0x18004c8c3  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18004c8c8  test    eax, eax
0x18004c8ca  js      loc_18004CAC9
0x18004c8d0  mov     eax, dword ptr [rsp+2F0h+var_2A0]
0x18004c8d4  mov     r9d, 1; dwType
0x18004c8da  mov     rcx, [rsp+2F0h+hKey]; hKey
0x18004c8df  xor     r8d, r8d; Reserved
0x18004c8e2  xor     edx, edx; lpValueName
0x18004c8e4  lea     eax, ds:2[rax*2]
0x18004c8eb  mov     [rsp+2F0h+samDesired], eax; cbData
0x18004c8ef  lea     rax, [rbp+1F0h+SubKey]
0x18004c8f3  mov     qword ptr [rsp+2F0h+dwOptions], rax; lpData
0x18004c8f8  call    cs:__imp_RegSetValueExW
0x18004c8ff  nop     dword ptr [rax+rax+00h]
0x18004c904  mov     ebx, eax
0x18004c906  test    eax, eax
0x18004c908  jz      short loc_18004C926
0x18004c90a  mov     rcx, [rsp+2F0h+hKey]; hKey
0x18004c90f  call    cs:__imp_RegCloseKey
0x18004c916  nop     dword ptr [rax+rax+00h]
0x18004c91b  or      ebx, 80070000h
0x18004c921  jmp     loc_18004CAC7
0x18004c926  lea     r9, aInprocserver32; "InprocServer32"
0x18004c92d  mov     [rsp+2F0h+var_290], 0
0x18004c936  lea     r8, aLs; "%ls"
0x18004c93d  mov     rdx, r14; unsigned __int64
0x18004c940  lea     rcx, [rbp+1F0h+SubKey]; Buffer
0x18004c944  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004c949  mov     rcx, [rsp+2F0h+hKey]; hKey
0x18004c94e  lea     rax, [rsp+2F0h+var_290]
0x18004c953  mov     [rsp+2F0h+lpdwDisposition], 0; lpdwDisposition
0x18004c95c  lea     rdx, [rbp+1F0h+SubKey]; lpSubKey
0x18004c960  mov     [rsp+2F0h+phkResult], rax; phkResult
0x18004c965  xor     r9d, r9d; lpClass
0x18004c968  mov     [rsp+2F0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18004c971  xor     r8d, r8d; Reserved
0x18004c974  mov     [rsp+2F0h+samDesired], 2000000h; samDesired
0x18004c97c  mov     [rsp+2F0h+dwOptions], 0; dwOptions
0x18004c984  call    cs:__imp_RegCreateKeyExW
0x18004c98b  nop     dword ptr [rax+rax+00h]
0x18004c990  mov     ebx, eax
0x18004c992  test    eax, eax
0x18004c994  jnz     loc_18004C90A
0x18004c99a  mov     r9, rdi
0x18004c99d  lea     r8, aLs; "%ls"
0x18004c9a4  mov     rdx, r14; unsigned __int64
0x18004c9a7  lea     rcx, [rbp+1F0h+SubKey]; Buffer
0x18004c9ab  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004c9b0  lea     r8, [rsp+2F0h+var_2A0]; unsigned __int64 *
0x18004c9b5  mov     [rsp+2F0h+var_2A0], 0
0x18004c9be  mov     rdx, r14; unsigned __int64
0x18004c9c1  lea     rcx, [rbp+1F0h+SubKey]; unsigned __int16 *
0x18004c9c5  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18004c9ca  test    eax, eax
0x18004c9cc  js      loc_18004CAC9
0x18004c9d2  mov     eax, dword ptr [rsp+2F0h+var_2A0]
0x18004c9d6  lea     r9d, [rbx+1]; dwType
0x18004c9da  mov     rcx, [rsp+2F0h+var_290]; hKey
0x18004c9df  xor     r8d, r8d; Reserved
0x18004c9e2  xor     edx, edx; lpValueName
0x18004c9e4  lea     eax, ds:2[rax*2]
0x18004c9eb  mov     [rsp+2F0h+samDesired], eax; cbData
0x18004c9ef  lea     rax, [rbp+1F0h+SubKey]
0x18004c9f3  mov     qword ptr [rsp+2F0h+dwOptions], rax; lpData
0x18004c9f8  call    cs:__imp_RegSetValueExW
0x18004c9ff  nop     dword ptr [rax+rax+00h]
0x18004ca04  mov     ebx, eax
0x18004ca06  test    eax, eax
0x18004ca08  jz      short loc_18004CA25
0x18004ca0a  mov     rcx, [rsp+2F0h+hKey]; hKey
0x18004ca0f  call    cs:__imp_RegCloseKey
0x18004ca16  nop     dword ptr [rax+rax+00h]
0x18004ca1b  mov     rcx, [rsp+2F0h+var_290]
0x18004ca20  jmp     loc_18004C90F
0x18004ca25  lea     r9, aBoth; "Both"
0x18004ca2c  mov     rdx, r14; unsigned __int64
0x18004ca2f  lea     r8, aLs; "%ls"
0x18004ca36  lea     rcx, [rbp+1F0h+SubKey]; Buffer
0x18004ca3a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004ca3f  lea     r8, [rsp+2F0h+var_2A0]; unsigned __int64 *
0x18004ca44  mov     [rsp+2F0h+var_2A0], 0
0x18004ca4d  mov     rdx, r14; unsigned __int64
0x18004ca50  lea     rcx, [rbp+1F0h+SubKey]; unsigned __int16 *
0x18004ca54  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18004ca59  test    eax, eax
0x18004ca5b  js      short loc_18004CAC9
0x18004ca5d  mov     eax, dword ptr [rsp+2F0h+var_2A0]
0x18004ca61  lea     rdx, ValueName; "ThreadingModel"
0x18004ca68  mov     rcx, [rsp+2F0h+var_290]; hKey
0x18004ca6d  mov     r9d, 1; dwType
0x18004ca73  xor     r8d, r8d; Reserved
0x18004ca76  lea     eax, ds:2[rax*2]
0x18004ca7d  mov     [rsp+2F0h+samDesired], eax; cbData
0x18004ca81  lea     rax, [rbp+1F0h+SubKey]
0x18004ca85  mov     qword ptr [rsp+2F0h+dwOptions], rax; lpData
0x18004ca8a  call    cs:__imp_RegSetValueExW
0x18004ca91  nop     dword ptr [rax+rax+00h]
0x18004ca96  mov     rcx, [rsp+2F0h+hKey]; hKey
0x18004ca9b  mov     ebx, eax
0x18004ca9d  call    cs:__imp_RegCloseKey
0x18004caa4  nop     dword ptr [rax+rax+00h]
0x18004caa9  mov     rcx, [rsp+2F0h+var_290]; hKey
0x18004caae  call    cs:__imp_RegCloseKey
0x18004cab5  nop     dword ptr [rax+rax+00h]
0x18004caba  test    ebx, ebx
0x18004cabc  jle     short loc_18004CAC7
0x18004cabe  movzx   ebx, bx
0x18004cac1  or      ebx, 80070000h
0x18004cac7  mov     eax, ebx
0x18004cac9  mov     rcx, [rbp+1F0h+var_20]
0x18004cad0  xor     rcx, rsp; StackCookie
0x18004cad3  call    __security_check_cookie
0x18004cad8  mov     rbx, [rsp+2F0h+arg_18]
0x18004cae0  add     rsp, 2E0h
0x18004cae7  pop     r14
0x18004cae9  pop     rdi
0x18004caea  pop     rbp
0x18004caeb  retn
```
