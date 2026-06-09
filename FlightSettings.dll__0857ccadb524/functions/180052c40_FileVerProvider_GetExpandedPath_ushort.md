# FileVerProvider::GetExpandedPath(ushort * *)

- ea: `0x180052c40`
- end: `0x180052e38`
- name: `?GetExpandedPath@FileVerProvider@@AEAAJPEAPEAG@Z`
- size: `504`
- prototype: `__int64 __fastcall(FileVerProvider *__hidden this, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180052e40`

## callees

- `0x180004b80`
- `0x180006354`
- `0x18000cc6c`
- `0x18000cc8c`
- `0x18001c6f4`
- `0x180022ed8`
- `0x1800254ac`
- `0x180046664`
- `0x180052c40`

## import_xrefs

- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180052d5d`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180052dd3`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180052d5d`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180052dd3`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180052cbd`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180052cbd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180052cb0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180052d21`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180052d4c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180052cb0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180052d21`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180052d4c`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x180052d08`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x180052d08`

## string_xrefs

- `0x180052cd1`: `onecore\base\flighting\flightsettings\broker\libs\ctac\fileverprovider.cpp`
- `0x180052d6d`: `onecore\base\flighting\flightsettings\broker\libs\ctac\fileverprovider.cpp`
- `0x180052da9`: `onecore\base\flighting\flightsettings\broker\libs\ctac\fileverprovider.cpp`
- `0x180052de1`: `onecore\base\flighting\flightsettings\broker\libs\ctac\fileverprovider.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall FileVerProvider::GetExpandedPath(HSTRING *this, unsigned __int16 **a2)
{
  unsigned int LastError; // ebx
  __int64 v5; // r9
  __int64 v6; // rdx
  const OLECHAR *StringRawBuffer; // rax
  HRESULT v8; // eax
  PCWSTR v9; // rax
  const WCHAR *v10; // rdi
  DWORD v11; // eax
  __int64 v12; // rcx
  const char *v13; // r9
  DWORD v14; // esi
  int v15; // eax
  unsigned __int16 *v16; // rbx
  const char *v17; // r9
  LPWSTR lpDst; // [rsp+20h] [rbp-40h] BYREF
  PWSTR ppszPath; // [rsp+28h] [rbp-38h] BYREF
  __int64 v21; // [rsp+30h] [rbp-30h]
  __int64 v22; // [rsp+38h] [rbp-28h]
  GUID pclsid; // [rsp+40h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]

  ppszPath = 0;
  v21 = 0;
  v22 = 0;
  if ( *((_BYTE *)this + 32) )
  {
    if ( !(unsigned __int8)IsSHGetKnownFolderPathPresent() )
    {
      LastError = -2147467263;
      v5 = 2147500033LL;
      v6 = 98;
LABEL_7:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v6,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\fileverprovider.cpp",
        (const char *)v5,
        (int)lpDst);
      goto LABEL_22;
    }
    pclsid = 0;
    StringRawBuffer = WindowsGetStringRawBuffer(this[3], 0);
    v8 = CLSIDFromString(StringRawBuffer, &pclsid);
    LastError = v8;
    if ( v8 < 0 )
    {
      v6 = 103;
LABEL_6:
      v5 = (unsigned int)v8;
      goto LABEL_7;
    }
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&ppszPath);
    v21 = -1;
    v22 = -1;
    v8 = SHGetKnownFolderPath(&pclsid, 0, 0, &ppszPath);
    LastError = v8;
    if ( v8 < 0 )
    {
      v6 = 107;
      goto LABEL_6;
    }
    v9 = WindowsGetStringRawBuffer(this[2], 0);
    v8 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Concat(&ppszPath, v9);
    LastError = v8;
    if ( v8 < 0 )
    {
      v6 = 111;
      goto LABEL_6;
    }
    v10 = ppszPath;
  }
  else
  {
    v10 = WindowsGetStringRawBuffer(this[2], 0);
  }
  v11 = ExpandEnvironmentStringsW(v10, 0, 0);
  v14 = v11;
  if ( v11 )
  {
    lpDst = 0;
    v15 = _AllocArray<unsigned short,CTCoAllocPolicy>(v12, 1, v11, &lpDst);
    LastError = v15;
    if ( v15 >= 0 )
    {
      v16 = lpDst;
      if ( ExpandEnvironmentStringsW(v10, lpDst, v14) )
      {
        lpDst = 0;
        *a2 = v16;
        CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&lpDst);
        LastError = 0;
        goto LABEL_22;
      }
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x84,
                    (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\fileverprovider.cpp",
                    v17);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x81,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\fileverprovider.cpp",
        (const char *)(unsigned int)v15,
        (int)lpDst);
    }
    CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&lpDst);
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x7D,
                  (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\fileverprovider.cpp",
                  v13);
  }
LABEL_22:
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&ppszPath);
  return LastError;
}

```

## disassembly

```asm
0x180052c40  mov     [rsp-18h+arg_10], rbx
0x180052c45  mov     [rsp-18h+arg_18], rsi
0x180052c4a  push    rbp
0x180052c4b  push    rdi
0x180052c4c  push    r14
0x180052c4e  mov     rbp, rsp
0x180052c51  sub     rsp, 60h
0x180052c55  mov     rax, cs:__security_cookie
0x180052c5c  xor     rax, rsp
0x180052c5f  mov     [rbp+var_10], rax
0x180052c63  mov     r14, rdx
0x180052c66  mov     rdi, rcx
0x180052c69  mov     [rbp+ppszPath], 0
0x180052c71  mov     [rbp+var_30], 0
0x180052c79  mov     [rbp+var_28], 0
0x180052c81  cmp     byte ptr [rcx+20h], 0
0x180052c85  jz      loc_180052D46
0x180052c8b  call    IsSHGetKnownFolderPathPresent
0x180052c90  test    al, al
0x180052c92  jnz     short loc_180052CA3
0x180052c94  mov     ebx, 80004001h
0x180052c99  mov     r9d, ebx
0x180052c9c  mov     edx, 62h ; 'b'
0x180052ca1  jmp     short loc_180052CD1
0x180052ca3  xorps   xmm0, xmm0
0x180052ca6  movups  xmmword ptr [rbp+pclsid.Data1], xmm0
0x180052caa  xor     edx, edx; length
0x180052cac  mov     rcx, [rdi+18h]; string
0x180052cb0  call    cs:__imp_WindowsGetStringRawBuffer
0x180052cb6  lea     rdx, [rbp+pclsid]; pclsid
0x180052cba  mov     rcx, rax; lpsz
0x180052cbd  call    cs:__imp_CLSIDFromString
0x180052cc3  mov     ebx, eax
0x180052cc5  test    eax, eax
0x180052cc7  jns     short loc_180052CE6
0x180052cc9  mov     edx, 67h ; 'g'; void *
0x180052cce  mov     r9d, eax; char *
0x180052cd1  lea     r8, aOnecoreBaseFli_103; "onecore\\base\\flighting\\flightsetting"...
0x180052cd8  mov     rcx, [rbp+18h]; this
0x180052cdc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180052ce1  jmp     loc_180052E0C
0x180052ce6  lea     rcx, [rbp+ppszPath]
0x180052cea  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180052cef  or      rax, 0FFFFFFFFFFFFFFFFh
0x180052cf3  mov     [rbp+var_30], rax
0x180052cf7  mov     [rbp+var_28], rax
0x180052cfb  lea     r9, [rbp+ppszPath]; ppszPath
0x180052cff  xor     r8d, r8d; hToken
0x180052d02  xor     edx, edx; dwFlags
0x180052d04  lea     rcx, [rbp+pclsid]; rfid
0x180052d08  call    cs:__imp_SHGetKnownFolderPath
0x180052d0e  mov     ebx, eax
0x180052d10  test    eax, eax
0x180052d12  jns     short loc_180052D1B
0x180052d14  mov     edx, 6Bh ; 'k'
0x180052d19  jmp     short loc_180052CCE
0x180052d1b  xor     edx, edx; length
0x180052d1d  mov     rcx, [rdi+10h]; string
0x180052d21  call    cs:__imp_WindowsGetStringRawBuffer
0x180052d27  mov     rdx, rax
0x180052d2a  lea     rcx, [rbp+ppszPath]
0x180052d2e  call    ?Concat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBG@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::Concat(ushort const *)
0x180052d33  mov     ebx, eax
0x180052d35  test    eax, eax
0x180052d37  jns     short loc_180052D40
0x180052d39  mov     edx, 6Fh ; 'o'
0x180052d3e  jmp     short loc_180052CCE
0x180052d40  mov     rdi, [rbp+ppszPath]
0x180052d44  jmp     short loc_180052D55
0x180052d46  xor     edx, edx; length
0x180052d48  mov     rcx, [rcx+10h]; string
0x180052d4c  call    cs:__imp_WindowsGetStringRawBuffer
0x180052d52  mov     rdi, rax
0x180052d55  xor     r8d, r8d; nSize
0x180052d58  xor     edx, edx; lpDst
0x180052d5a  mov     rcx, rdi; lpSrc
0x180052d5d  call    cs:__imp_ExpandEnvironmentStringsW
0x180052d63  mov     esi, eax
0x180052d65  test    eax, eax
0x180052d67  jnz     short loc_180052D83
0x180052d69  mov     rcx, [rbp+18h]; this
0x180052d6d  lea     r8, aOnecoreBaseFli_103; "onecore\\base\\flighting\\flightsetting"...
0x180052d74  lea     edx, [rax+7Dh]; void *
0x180052d77  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180052d7c  mov     ebx, eax
0x180052d7e  jmp     loc_180052E0C
0x180052d83  mov     [rbp+lpDst], 0
0x180052d8b  mov     r8, rsi
0x180052d8e  lea     r9, [rbp+lpDst]
0x180052d92  mov     edx, 1
0x180052d97  call    ??$_AllocArray@GVCTCoAllocPolicy@@@@YAJPEAXK_KPEAPEAG@Z; _AllocArray<ushort,CTCoAllocPolicy>(void *,ulong,unsigned __int64,ushort * *)
0x180052d9c  mov     ebx, eax
0x180052d9e  test    eax, eax
0x180052da0  jns     short loc_180052DC6
0x180052da2  mov     rcx, [rbp+18h]; this
0x180052da6  mov     r9d, eax; char *
0x180052da9  lea     r8, aOnecoreBaseFli_103; "onecore\\base\\flighting\\flightsetting"...
0x180052db0  mov     edx, 81h; void *
0x180052db5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180052dba  nop
0x180052dbb  lea     rcx, [rbp+lpDst]
0x180052dbf  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x180052dc4  jmp     short loc_180052E0C
0x180052dc6  mov     r8d, esi; nSize
0x180052dc9  mov     rbx, [rbp+lpDst]
0x180052dcd  mov     rdx, rbx; lpDst
0x180052dd0  mov     rcx, rdi; lpSrc
0x180052dd3  call    cs:__imp_ExpandEnvironmentStringsW
0x180052dd9  test    eax, eax
0x180052ddb  jnz     short loc_180052DF6
0x180052ddd  mov     rcx, [rbp+18h]; this
0x180052de1  lea     r8, aOnecoreBaseFli_103; "onecore\\base\\flighting\\flightsetting"...
0x180052de8  mov     edx, 84h; void *
0x180052ded  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180052df2  mov     ebx, eax
0x180052df4  jmp     short loc_180052DBB
0x180052df6  mov     [rbp+lpDst], 0
0x180052dfe  mov     [r14], rbx
0x180052e01  lea     rcx, [rbp+lpDst]
0x180052e05  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x180052e0a  xor     ebx, ebx
0x180052e0c  lea     rcx, [rbp+ppszPath]
0x180052e10  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180052e15  mov     eax, ebx
0x180052e17  mov     rcx, [rbp+var_10]
0x180052e1b  xor     rcx, rsp; StackCookie
0x180052e1e  call    __security_check_cookie
0x180052e23  lea     r11, [rsp+60h+var_s0]
0x180052e28  mov     rbx, [r11+30h]
0x180052e2c  mov     rsi, [r11+38h]
0x180052e30  mov     rsp, r11
0x180052e33  pop     r14
0x180052e35  pop     rdi
0x180052e36  pop     rbp
0x180052e37  retn
```
