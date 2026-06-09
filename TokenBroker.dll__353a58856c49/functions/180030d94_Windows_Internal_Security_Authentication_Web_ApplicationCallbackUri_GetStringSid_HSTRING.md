# Windows::Internal::Security::Authentication::Web::ApplicationCallbackUri::GetStringSid(HSTRING__ * *)

- ea: `0x180030d94`
- end: `0x180030eae`
- name: `?GetStringSid@ApplicationCallbackUri@Web@Authentication@Security@Internal@Windows@@QEBAJPEAPEAUHSTRING__@@@Z`
- size: `282`
- prototype: `int(Windows::Internal::Security::Authentication::Web::ApplicationCallbackUri *__hidden this, HSTRING *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180030d30`
- `0x180031088`

## callees

- `0x180030d94`
- `0x18008e690`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180030e2b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180030e2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030e90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030e90`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180030e40`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180030e40`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180030e4e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180030e4e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180030dcc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180030dcc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180030e6b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180030e6b`
- `ntdll!RtlFreeSid` at `0x180030e60`
- `ntdll!RtlFreeSid` at `0x180030e60`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180030df0`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180030df0`
- `ext-ms-win-kernel32-package-l1-1-0!AppContainerDeriveSidFromMoniker` at `0x180030dda`
- `ext-ms-win-kernel32-package-l1-1-0!AppContainerDeriveSidFromMoniker` at `0x180030dda`

## pseudocode

```c
__int64 __fastcall Windows::Internal::Security::Authentication::Web::ApplicationCallbackUri::GetStringSid(
        HSTRING *this,
        HSTRING *a2)
{
  PCWSTR StringRawBuffer; // rax
  int v4; // ebx
  const WCHAR *v5; // rdi
  unsigned __int64 v6; // rbx
  signed int LastError; // eax
  PSID Sid; // [rsp+20h] [rbp-58h] BYREF
  LPWSTR StringSid; // [rsp+28h] [rbp-50h] BYREF
  HSTRING string; // [rsp+30h] [rbp-48h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+38h] [rbp-40h] BYREF

  Sid = 0;
  StringSid = 0;
  if ( !a2 )
    return 2147942487LL;
  StringRawBuffer = WindowsGetStringRawBuffer(*this, 0);
  v4 = AppContainerDeriveSidFromMoniker(StringRawBuffer, &Sid);
  if ( v4 >= 0 )
  {
    if ( ConvertSidToStringSidW(Sid, &StringSid) )
    {
      v5 = StringSid;
      v6 = -1;
      do
        ++v6;
      while ( StringSid[v6] );
      if ( v6 > 0xFFFFFFFF )
      {
        LODWORD(v6) = -1;
        RaiseException(0xC000000D, 1u, 0, 0);
      }
      WindowsCreateStringReference(v5, v6, &hstringHeader, &string);
      v4 = WindowsDuplicateString(string, a2);
    }
    else
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
    }
  }
  if ( Sid )
    RtlFreeSid(Sid);
  LocalFree(StringSid);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180030d94  mov     [rsp+arg_10], rbx
0x180030d99  push    rbp
0x180030d9a  push    rsi
0x180030d9b  push    rdi
0x180030d9c  sub     rsp, 60h
0x180030da0  mov     rax, cs:__security_cookie
0x180030da7  xor     rax, rsp
0x180030daa  mov     [rsp+78h+var_28], rax
0x180030daf  xor     ebp, ebp
0x180030db1  mov     rsi, rdx
0x180030db4  mov     [rsp+78h+Sid], rbp
0x180030db9  mov     [rsp+78h+StringSid], rbp
0x180030dbe  test    rdx, rdx
0x180030dc1  jz      loc_180030EA7
0x180030dc7  mov     rcx, [rcx]; string
0x180030dca  xor     edx, edx; length
0x180030dcc  call    cs:__imp_WindowsGetStringRawBuffer
0x180030dd2  mov     rcx, rax
0x180030dd5  lea     rdx, [rsp+78h+Sid]
0x180030dda  call    cs:__imp_AppContainerDeriveSidFromMoniker
0x180030de0  mov     ebx, eax
0x180030de2  test    eax, eax
0x180030de4  js      short loc_180030E56
0x180030de6  mov     rcx, [rsp+78h+Sid]; Sid
0x180030deb  lea     rdx, [rsp+78h+StringSid]; StringSid
0x180030df0  call    cs:__imp_ConvertSidToStringSidW
0x180030df6  test    eax, eax
0x180030df8  jz      loc_180030E90
0x180030dfe  mov     rdi, [rsp+78h+StringSid]
0x180030e03  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180030e07  inc     rbx
0x180030e0a  cmp     [rdi+rbx*2], bp
0x180030e0e  jnz     short loc_180030E07
0x180030e10  mov     eax, 0FFFFFFFFh
0x180030e15  cmp     rbx, rax
0x180030e18  jbe     short loc_180030E31
0x180030e1a  xor     r9d, r9d; lpArguments
0x180030e1d  xor     r8d, r8d; nNumberOfArguments
0x180030e20  mov     ecx, 0C000000Dh; dwExceptionCode
0x180030e25  mov     ebx, eax
0x180030e27  lea     edx, [r9+1]; dwExceptionFlags
0x180030e2b  call    cs:__imp_RaiseException
0x180030e31  lea     r9, [rsp+78h+string]; string
0x180030e36  mov     edx, ebx; length
0x180030e38  lea     r8, [rsp+78h+hstringHeader]; hstringHeader
0x180030e3d  mov     rcx, rdi; sourceString
0x180030e40  call    cs:__imp_WindowsCreateStringReference
0x180030e46  mov     rcx, [rsp+78h+string]; string
0x180030e4b  mov     rdx, rsi; newString
0x180030e4e  call    cs:__imp_WindowsDuplicateString
0x180030e54  mov     ebx, eax
0x180030e56  mov     rcx, [rsp+78h+Sid]; Sid
0x180030e5b  test    rcx, rcx
0x180030e5e  jz      short loc_180030E66
0x180030e60  call    cs:__imp_RtlFreeSid
0x180030e66  mov     rcx, [rsp+78h+StringSid]; hMem
0x180030e6b  call    cs:__imp_LocalFree
0x180030e71  mov     eax, ebx
0x180030e73  mov     rcx, [rsp+78h+var_28]
0x180030e78  xor     rcx, rsp; StackCookie
0x180030e7b  call    __security_check_cookie
0x180030e80  mov     rbx, [rsp+78h+arg_10]
0x180030e88  add     rsp, 60h
0x180030e8c  pop     rdi
0x180030e8d  pop     rsi
0x180030e8e  pop     rbp
0x180030e8f  retn
0x180030e90  call    cs:__imp_GetLastError
0x180030e96  mov     ebx, eax
0x180030e98  test    eax, eax
0x180030e9a  jle     short loc_180030E56
0x180030e9c  movzx   ebx, ax
0x180030e9f  or      ebx, 80070000h
0x180030ea5  jmp     short loc_180030E56
0x180030ea7  mov     eax, 80070057h
0x180030eac  jmp     short loc_180030E73
```
