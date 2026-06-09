# WinHttpConnection::CreateUrl(ushort * *)

- ea: `0x180095cbc`
- end: `0x180095e07`
- name: `?CreateUrl@WinHttpConnection@@QEAAJPEAPEAG@Z`
- size: `331`
- prototype: `int(WinHttpConnection *__hidden this, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180098264`

## callees

- `0x180085c44`
- `0x180087188`
- `0x1800871b4`
- `0x18008a9ec`
- `0x18008aa28`
- `0x18008aecc`
- `0x180095cbc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095d32`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095d9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095d32`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095d9d`
- `WINHTTP!WinHttpCreateUrl` at `0x180095d24`
- `WINHTTP!WinHttpCreateUrl` at `0x180095d93`
- `WINHTTP!WinHttpCreateUrl` at `0x180095d24`
- `WINHTTP!WinHttpCreateUrl` at `0x180095d93`

## string_xrefs

- `0x180095dca`: `CopyStringNullSafeW`
- `0x180095ce3`: `WinHttpConnection::CreateUrl`
- `0x180095cfd`: `WinHttpConnection::CreateUrl`
- `0x180095d6c`: `WinHttpConnection::CreateUrl`
- `0x180095de1`: `WinHttpConnection::CreateUrl`
- `0x180095dda`: `WinHttpCreateUrl`

## pseudocode

```c
__int64 __fastcall WinHttpConnection::CreateUrl(WinHttpConnection *this, unsigned __int16 **a2)
{
  unsigned __int16 *v2; // rdi
  signed int v4; // ebx
  struct $BC2FB811D417144E831EE3AEA4A279C8 *v5; // rbp
  signed int LastError; // eax
  WCHAR *v7; // rax
  signed int v8; // eax
  int v9; // eax
  __int64 v10; // r9
  const wchar_t *v11; // r8
  DWORD pdwUrlLength; // [rsp+58h] [rbp+10h] BYREF

  v2 = 0;
  pdwUrlLength = 0;
  if ( a2 )
  {
    v5 = (struct $BC2FB811D417144E831EE3AEA4A279C8 *)((char *)this + 16);
    v4 = 0;
    *a2 = 0;
    if ( WinHttpCreateUrl((LPURL_COMPONENTS)((char *)this + 16), 0, 0, &pdwUrlLength) )
      goto LABEL_18;
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    if ( v4 == -2147024774 )
    {
      v7 = (WCHAR *)SafeAlloc(2LL * pdwUrlLength + 2);
      v2 = v7;
      if ( !v7 )
      {
        v4 = -2147024882;
        Logger::TraceCritical(L"%s: Out of memory. Allocation failed.", L"WinHttpConnection::CreateUrl");
        goto LABEL_18;
      }
      if ( WinHttpCreateUrl(v5, 0, v7, &pdwUrlLength) )
        goto LABEL_13;
      v8 = GetLastError();
      v4 = v8;
      if ( v8 > 0 )
        v4 = (unsigned __int16)v8 | 0x80070000;
      if ( v4 >= 0 )
      {
LABEL_13:
        v9 = CopyStringNullSafeW(v2, a2);
        v4 = v9;
        if ( v9 >= 0 )
          goto LABEL_18;
        v10 = (unsigned int)v9;
        v11 = L"CopyStringNullSafeW";
LABEL_17:
        Logger::TraceError(L"%s: %s failed with error code: 0x%08x.", L"WinHttpConnection::CreateUrl", v11, v10);
        goto LABEL_18;
      }
    }
    else if ( v4 >= 0 )
    {
      goto LABEL_18;
    }
    v10 = (unsigned int)v4;
    v11 = L"WinHttpCreateUrl";
    goto LABEL_17;
  }
  v4 = -2147024809;
  Logger::TraceError(L"%s: \"%s\" should not be null.", L"WinHttpConnection::CreateUrl", L"url");
  Logger::WriteNullOrEmptyParameterFailureEvent(L"WinHttpConnection::CreateUrl", L"url");
LABEL_18:
  SafeFree(v2);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180095cbc  push    rbx
0x180095cbe  push    rbp
0x180095cbf  push    rsi
0x180095cc0  push    rdi
0x180095cc1  sub     rsp, 28h
0x180095cc5  xor     edi, edi
0x180095cc7  mov     [rsp+48h+pdwUrlLength], 0
0x180095ccf  mov     rsi, rdx
0x180095cd2  test    rdx, rdx
0x180095cd5  jnz     short loc_180095D0E
0x180095cd7  lea     r8, aUrl; "url"
0x180095cde  mov     ebx, 80070057h
0x180095ce3  lea     rdx, aWinhttpconnect_1; "WinHttpConnection::CreateUrl"
0x180095cea  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x180095cf1  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180095cf6  lea     rdx, aUrl; "url"
0x180095cfd  lea     rcx, aWinhttpconnect_1; "WinHttpConnection::CreateUrl"
0x180095d04  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x180095d09  jmp     loc_180095DF4
0x180095d0e  lea     rbp, [rcx+10h]
0x180095d12  xor     ebx, ebx
0x180095d14  mov     [rdx], rbx
0x180095d17  lea     r9, [rsp+48h+pdwUrlLength]; pdwUrlLength
0x180095d1c  xor     edx, edx; dwFlags
0x180095d1e  xor     r8d, r8d; pwszUrl
0x180095d21  mov     rcx, rbp; lpUrlComponents
0x180095d24  call    cs:__imp_WinHttpCreateUrl
0x180095d2a  test    eax, eax
0x180095d2c  jnz     loc_180095DF4
0x180095d32  call    cs:__imp_GetLastError
0x180095d38  mov     ebx, eax
0x180095d3a  test    eax, eax
0x180095d3c  jle     short loc_180095D47
0x180095d3e  movzx   ebx, ax
0x180095d41  or      ebx, 80070000h
0x180095d47  cmp     ebx, 8007007Ah
0x180095d4d  jnz     loc_180095DD3
0x180095d53  mov     ecx, [rsp+48h+pdwUrlLength]
0x180095d57  lea     rcx, ds:2[rcx*2]; unsigned __int64
0x180095d5f  call    ?SafeAlloc@@YAPEAX_K@Z; SafeAlloc(unsigned __int64)
0x180095d64  mov     rdi, rax
0x180095d67  test    rax, rax
0x180095d6a  jnz     short loc_180095D86
0x180095d6c  lea     rdx, aWinhttpconnect_1; "WinHttpConnection::CreateUrl"
0x180095d73  mov     ebx, 8007000Eh
0x180095d78  lea     rcx, aSOutOfMemoryAl_0; "%s: Out of memory. Allocation failed."
0x180095d7f  call    ?TraceCritical@Logger@@SAJPEBGZZ; Logger::TraceCritical(ushort const *,...)
0x180095d84  jmp     short loc_180095DF4
0x180095d86  lea     r9, [rsp+48h+pdwUrlLength]; pdwUrlLength
0x180095d8b  mov     r8, rdi; pwszUrl
0x180095d8e  xor     edx, edx; dwFlags
0x180095d90  mov     rcx, rbp; lpUrlComponents
0x180095d93  call    cs:__imp_WinHttpCreateUrl
0x180095d99  test    eax, eax
0x180095d9b  jnz     short loc_180095DB6
0x180095d9d  call    cs:__imp_GetLastError
0x180095da3  mov     ebx, eax
0x180095da5  test    eax, eax
0x180095da7  jle     short loc_180095DB2
0x180095da9  movzx   ebx, ax
0x180095dac  or      ebx, 80070000h
0x180095db2  test    ebx, ebx
0x180095db4  js      short loc_180095DD7
0x180095db6  mov     rdx, rsi; unsigned __int16 **
0x180095db9  mov     rcx, rdi; unsigned __int16 *
0x180095dbc  call    ?CopyStringNullSafeW@@YAJPEBGPEAPEAG@Z; CopyStringNullSafeW(ushort const *,ushort * *)
0x180095dc1  mov     ebx, eax
0x180095dc3  test    eax, eax
0x180095dc5  jns     short loc_180095DF4
0x180095dc7  mov     r9d, eax
0x180095dca  lea     r8, aCopystringnull; "CopyStringNullSafeW"
0x180095dd1  jmp     short loc_180095DE1
0x180095dd3  test    ebx, ebx
0x180095dd5  jns     short loc_180095DF4
0x180095dd7  mov     r9d, ebx
0x180095dda  lea     r8, aWinhttpcreateu_0; "WinHttpCreateUrl"
0x180095de1  lea     rdx, aWinhttpconnect_1; "WinHttpConnection::CreateUrl"
0x180095de8  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x."
0x180095def  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180095df4  mov     rcx, rdi; void *
0x180095df7  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x180095dfc  mov     eax, ebx
0x180095dfe  add     rsp, 28h
0x180095e02  pop     rdi
0x180095e03  pop     rsi
0x180095e04  pop     rbp
0x180095e05  pop     rbx
0x180095e06  retn
```
