# DetermineVerbHandlerType

- ea: `0x180010ba0`
- end: `0x180010d2c`
- name: `DetermineVerbHandlerType`
- size: `396`
- prototype: `__int64 __fastcall(LPCWSTR pszAssoc)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800086b0`

## callees

- `0x180002ce0`
- `0x1800107ac`
- `0x180010ba0`
- `0x18002b534`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180010c34`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180010c34`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!AssocQueryStringW` at `0x180010c1b`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!AssocQueryStringW` at `0x180010cb7`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!AssocQueryStringW` at `0x180010cf0`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!AssocQueryStringW` at `0x180010c1b`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!AssocQueryStringW` at `0x180010cb7`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!AssocQueryStringW` at `0x180010cf0`

## pseudocode

```c
__int64 __fastcall DetermineVerbHandlerType(LPCWSTR pszAssoc, _DWORD *a2)
{
  HRESULT v4; // ebx
  HRESULT v5; // eax
  HRESULT v6; // eax
  bool v8; // [rsp+30h] [rbp-29h] BYREF
  DWORD pcchOut; // [rsp+34h] [rbp-25h] BYREF
  GUID pclsid; // [rsp+38h] [rbp-21h] BYREF
  WCHAR sz[40]; // [rsp+50h] [rbp-9h] BYREF

  *a2 = 0;
  v8 = 0;
  if ( (int)IsTrustedPackagedApp(pszAssoc, &v8) >= 0 && v8 )
  {
    *a2 = 3;
    return 0;
  }
  pcchOut = 39;
  if ( AssocQueryStringW(0x1000u, ASSOCSTR_DELEGATEEXECUTE, pszAssoc, 0, sz, &pcchOut) < 0 )
  {
    pcchOut = 39;
    v5 = AssocQueryStringW(0x1020u, ASSOCSTR_DROPTARGET, pszAssoc, 0, sz, &pcchOut);
    if ( v5 >= 0
      || v5 == -2147467261
      || (pcchOut = 39, v6 = AssocQueryStringW(0x1020u, ASSOCSTR_COMMAND, pszAssoc, 0, sz, &pcchOut), v6 >= 0)
      || v6 == -2147467261 )
    {
      *a2 = 1;
    }
    return 0;
  }
  pclsid = 0;
  v4 = CLSIDFromString(sz, &pclsid);
  if ( v4 >= 0 )
  {
    if ( !memcmp_0(&pclsid, &CLSID_AppShellVerbHandler, 0x10u) )
    {
      *a2 = 2;
    }
    else if ( memcmp_0(&pclsid, &CLSID_ExecuteUnknown, 0x10u) )
    {
      *a2 = 1;
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180010ba0  mov     [rsp-8+arg_10], rbx
0x180010ba5  mov     [rsp-8+arg_18], rdi
0x180010baa  push    rbp
0x180010bab  lea     rbp, [rsp-57h]
0x180010bb0  sub     rsp, 0B0h
0x180010bb7  mov     rax, cs:__security_cookie
0x180010bbe  xor     rax, rsp
0x180010bc1  mov     [rbp+57h+var_10], rax
0x180010bc5  mov     rdi, rdx
0x180010bc8  mov     dword ptr [rdx], 0
0x180010bce  lea     rdx, [rbp+57h+var_80]; bool *
0x180010bd2  mov     [rbp+57h+var_80], 0
0x180010bd6  mov     rbx, rcx
0x180010bd9  call    ?IsTrustedPackagedApp@@YAJPEBGPEA_N@Z; IsTrustedPackagedApp(ushort const *,bool *)
0x180010bde  test    eax, eax
0x180010be0  js      short loc_180010BF3
0x180010be2  cmp     [rbp+57h+var_80], 0
0x180010be6  jz      short loc_180010BF3
0x180010be8  mov     dword ptr [rdi], 3
0x180010bee  jmp     loc_180010D07
0x180010bf3  xor     r9d, r9d; pszExtra
0x180010bf6  mov     [rbp+57h+var_7C], 27h ; '''
0x180010bfd  lea     rax, [rbp+57h+var_7C]
0x180010c01  mov     r8, rbx; pszAssoc
0x180010c04  mov     [rsp+0B0h+pcchOut], rax; pcchOut
0x180010c09  mov     ecx, 1000h; flags
0x180010c0e  lea     rax, [rbp+57h+sz]
0x180010c12  lea     edx, [r9+12h]; str
0x180010c16  mov     [rsp+0B0h+pszOut], rax; pszOut
0x180010c1b  call    cs:__imp_AssocQueryStringW
0x180010c21  test    eax, eax
0x180010c23  js      short loc_180010C8F
0x180010c25  xorps   xmm0, xmm0
0x180010c28  lea     rdx, [rbp+57h+pclsid]; pclsid
0x180010c2c  lea     rcx, [rbp+57h+sz]; lpsz
0x180010c30  movups  xmmword ptr [rbp+57h+pclsid.Data1], xmm0
0x180010c34  call    cs:__imp_CLSIDFromString
0x180010c3a  mov     ebx, eax
0x180010c3c  test    eax, eax
0x180010c3e  js      loc_180010D09
0x180010c44  mov     r8d, 10h; Size
0x180010c4a  lea     rdx, CLSID_AppShellVerbHandler; Buf2
0x180010c51  lea     rcx, [rbp+57h+pclsid]; Buf1
0x180010c55  call    memcmp_0
0x180010c5a  test    eax, eax
0x180010c5c  jnz     short loc_180010C69
0x180010c5e  mov     dword ptr [rdi], 2
0x180010c64  jmp     loc_180010D09
0x180010c69  mov     r8d, 10h; Size
0x180010c6f  lea     rdx, CLSID_ExecuteUnknown; Buf2
0x180010c76  lea     rcx, [rbp+57h+pclsid]; Buf1
0x180010c7a  call    memcmp_0
0x180010c7f  test    eax, eax
0x180010c81  jz      loc_180010D09
0x180010c87  mov     dword ptr [rdi], 1
0x180010c8d  jmp     short loc_180010D09
0x180010c8f  xor     r9d, r9d; pszExtra
0x180010c92  mov     [rbp+57h+var_7C], 27h ; '''
0x180010c99  lea     rax, [rbp+57h+var_7C]
0x180010c9d  mov     r8, rbx; pszAssoc
0x180010ca0  mov     [rsp+0B0h+pcchOut], rax; pcchOut
0x180010ca5  mov     ecx, 1020h; flags
0x180010caa  lea     rax, [rbp+57h+sz]
0x180010cae  lea     edx, [r9+11h]; str
0x180010cb2  mov     [rsp+0B0h+pszOut], rax; pszOut
0x180010cb7  call    cs:__imp_AssocQueryStringW
0x180010cbd  test    eax, eax
0x180010cbf  jns     short loc_180010D01
0x180010cc1  cmp     eax, 80004003h
0x180010cc6  jz      short loc_180010D01
0x180010cc8  xor     r9d, r9d; pszExtra
0x180010ccb  mov     [rbp+57h+var_7C], 27h ; '''
0x180010cd2  lea     rax, [rbp+57h+var_7C]
0x180010cd6  mov     r8, rbx; pszAssoc
0x180010cd9  mov     [rsp+0B0h+pcchOut], rax; pcchOut
0x180010cde  mov     ecx, 1020h; flags
0x180010ce3  lea     rax, [rbp+57h+sz]
0x180010ce7  lea     edx, [r9+1]; str
0x180010ceb  mov     [rsp+0B0h+pszOut], rax; pszOut
0x180010cf0  call    cs:__imp_AssocQueryStringW
0x180010cf6  test    eax, eax
0x180010cf8  jns     short loc_180010D01
0x180010cfa  cmp     eax, 80004003h
0x180010cff  jnz     short loc_180010D07
0x180010d01  mov     dword ptr [rdi], 1
0x180010d07  xor     ebx, ebx
0x180010d09  mov     eax, ebx
0x180010d0b  mov     rcx, [rbp+57h+var_10]
0x180010d0f  xor     rcx, rsp; StackCookie
0x180010d12  call    __security_check_cookie
0x180010d17  lea     r11, [rsp+0B0h+var_s0]
0x180010d1f  mov     rbx, [r11+20h]
0x180010d23  mov     rdi, [r11+28h]
0x180010d27  mov     rsp, r11
0x180010d2a  pop     rbp
0x180010d2b  retn
```
