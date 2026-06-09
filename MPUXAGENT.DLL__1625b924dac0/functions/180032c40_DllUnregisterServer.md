# DllUnregisterServer

- ea: `0x180032c40`
- end: `0x180032d9f`
- name: `DllUnregisterServer`
- size: `351`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180004158`
- `0x180004260`
- `0x1800095a0`
- `0x1800322c4`
- `0x180032c40`
- `0x180032da0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180032d38`
- `ADVAPI32!RegCloseKey` at `0x180032d4a`
- `ADVAPI32!RegCloseKey` at `0x180032d38`
- `ADVAPI32!RegCloseKey` at `0x180032d4a`
- `RPCRT4!NdrDllUnregisterProxy` at `0x180032d70`
- `RPCRT4!NdrDllUnregisterProxy` at `0x180032d70`

## pseudocode

```c
HRESULT __stdcall DllUnregisterServer()
{
  HRESULT v0; // ebp
  __int64 (**v1)[2]; // rsi
  int v2; // ebx
  char v3; // di
  int v4; // eax
  HRESULT v5; // ebx
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  int v8; // eax
  HKEY hKey; // [rsp+30h] [rbp-18h] BYREF

  v0 = 0;
  v1 = &off_180096E70;
  v2 = 0;
  v3 = 1;
  do
  {
    v4 = sub_1800322C4((__int64 *)*v1);
    v1 += 7;
    if ( v4 < 0 )
      v0 = v4;
    ++v2;
  }
  while ( !v2 );
  hKey = 0;
  v5 = sub_180004158(&hKey, 0xFFFFFFFF80000000uLL, L"AppID", 0x10000, 0, 0);
  if ( v5 < 0 )
  {
    v6 = off_180096D60;
    if ( off_180096D60 != (_UNKNOWN *)&off_180096D60 && (*((_BYTE *)off_180096D60 + 28) & 1) != 0 )
    {
      v7 = 42;
LABEL_13:
      sub_180032DA0(v6[2], v7, qword_180084400, (unsigned int)v5);
      goto LABEL_14;
    }
    goto LABEL_14;
  }
  v5 = sub_180004260(hKey, L"{1111A26D-EF95-4A45-9F55-21E52ADF9887}");
  if ( v5 < 0 )
  {
    v6 = off_180096D60;
    if ( off_180096D60 != (_UNKNOWN *)&off_180096D60 && (*((_BYTE *)off_180096D60 + 28) & 1) != 0 )
    {
      v7 = 43;
      goto LABEL_13;
    }
LABEL_14:
    if ( hKey )
      RegCloseKey(hKey);
    goto LABEL_19;
  }
  if ( hKey )
    RegCloseKey(hKey);
  v5 = 0;
  v3 = 0;
LABEL_19:
  if ( !v3 )
    v5 = v0;
  v8 = NdrDllUnregisterProxy(hDll, (const ProxyFileInfo **)&pProxyFileList, &pclsid);
  if ( v8 < 0 )
    return v8;
  return v5;
}

```

## disassembly

```asm
0x180032c40  mov     [rsp+arg_0], rbx
0x180032c45  mov     [rsp+arg_8], rbp
0x180032c4a  mov     [rsp+arg_10], rsi
0x180032c4f  push    rdi
0x180032c50  sub     rsp, 40h
0x180032c54  mov     rax, cs:__security_cookie
0x180032c5b  xor     rax, rsp
0x180032c5e  mov     [rsp+48h+var_10], rax
0x180032c63  xor     ebp, ebp
0x180032c65  lea     rsi, off_180096E70
0x180032c6c  xor     ebx, ebx
0x180032c6e  lea     edi, [rbp+1]
0x180032c71  mov     rcx, [rsi]
0x180032c74  call    sub_1800322C4
0x180032c79  test    eax, eax
0x180032c7b  lea     rsi, [rsi+38h]
0x180032c7f  cmovs   ebp, eax
0x180032c82  add     ebx, edi
0x180032c84  cmp     ebx, edi
0x180032c86  jb      short loc_180032C71
0x180032c88  mov     [rsp+48h+var_20], 0
0x180032c90  lea     r8, aAppid; "AppID"
0x180032c97  mov     r9d, 10000h
0x180032c9d  mov     [rsp+48h+var_28], 0
0x180032ca6  mov     rdx, 0FFFFFFFF80000000h
0x180032cad  mov     [rsp+48h+hKey], 0
0x180032cb6  lea     rcx, [rsp+48h+hKey]
0x180032cbb  call    sub_180004158
0x180032cc0  mov     ebx, eax
0x180032cc2  test    eax, eax
0x180032cc4  jns     short loc_180032CE6
0x180032cc6  mov     rcx, cs:off_180096D60
0x180032ccd  lea     rax, off_180096D60
0x180032cd4  cmp     rcx, rax
0x180032cd7  jz      short loc_180032D2E
0x180032cd9  test    [rcx+1Ch], dil
0x180032cdd  jz      short loc_180032D2E
0x180032cdf  mov     edx, 2Ah ; '*'
0x180032ce4  jmp     short loc_180032D1B
0x180032ce6  mov     rcx, [rsp+48h+hKey]
0x180032ceb  lea     rdx, a1111a26dEf954a; "{1111A26D-EF95-4A45-9F55-21E52ADF9887}"
0x180032cf2  call    sub_180004260
0x180032cf7  mov     ebx, eax
0x180032cf9  test    eax, eax
0x180032cfb  jns     short loc_180032D40
0x180032cfd  mov     rcx, cs:off_180096D60
0x180032d04  lea     rax, off_180096D60
0x180032d0b  cmp     rcx, rax
0x180032d0e  jz      short loc_180032D2E
0x180032d10  test    [rcx+1Ch], dil
0x180032d14  jz      short loc_180032D2E
0x180032d16  mov     edx, 2Bh ; '+'
0x180032d1b  mov     rcx, [rcx+10h]
0x180032d1f  lea     r8, qword_180084400
0x180032d26  mov     r9d, ebx
0x180032d29  call    sub_180032DA0
0x180032d2e  mov     rcx, [rsp+48h+hKey]; hKey
0x180032d33  test    rcx, rcx
0x180032d36  jz      short loc_180032D55
0x180032d38  call    cs:RegCloseKey
0x180032d3e  jmp     short loc_180032D55
0x180032d40  mov     rcx, [rsp+48h+hKey]; hKey
0x180032d45  test    rcx, rcx
0x180032d48  jz      short loc_180032D50
0x180032d4a  call    cs:RegCloseKey
0x180032d50  xor     ebx, ebx
0x180032d52  xor     dil, dil
0x180032d55  mov     rcx, cs:hDll; hDll
0x180032d5c  lea     r8, pclsid; pclsid
0x180032d63  test    dil, dil
0x180032d66  lea     rdx, pProxyFileList; pProxyFileList
0x180032d6d  cmovz   ebx, ebp
0x180032d70  call    cs:NdrDllUnregisterProxy
0x180032d76  test    eax, eax
0x180032d78  cmovs   ebx, eax
0x180032d7b  mov     eax, ebx
0x180032d7d  mov     rcx, [rsp+48h+var_10]
0x180032d82  xor     rcx, rsp; StackCookie
0x180032d85  call    __security_check_cookie
0x180032d8a  mov     rbx, [rsp+48h+arg_0]
0x180032d8f  mov     rbp, [rsp+48h+arg_8]
0x180032d94  mov     rsi, [rsp+48h+arg_10]
0x180032d99  add     rsp, 40h
0x180032d9d  pop     rdi
0x180032d9e  retn
```
