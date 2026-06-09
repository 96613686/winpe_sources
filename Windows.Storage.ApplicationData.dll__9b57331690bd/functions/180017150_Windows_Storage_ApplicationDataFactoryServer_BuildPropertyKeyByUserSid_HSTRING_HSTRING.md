# Windows::Storage::ApplicationDataFactoryServer::BuildPropertyKeyByUserSid(HSTRING__ *,HSTRING__ * *)

- ea: `0x180017150`
- end: `0x180017249`
- name: `?BuildPropertyKeyByUserSid@ApplicationDataFactoryServer@Storage@Windows@@CAJPEAUHSTRING__@@PEAPEAU4@@Z`
- size: `249`
- prototype: `__int64 __fastcall(HSTRING userSid, HSTRING__ **propertyKeyString)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x18001e9b4`

## callees

- `0x180009778`
- `0x180017150`
- `0x180021efc`
- `0x180041620`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180017200`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180017200`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180017193`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180017193`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180017214`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180017214`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x1800171a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x1800171a8`

## pseudocode

```c
__int64 __fastcall Windows::Storage::ApplicationDataFactoryServer::BuildPropertyKeyByUserSid(
        HSTRING userSid,
        HSTRING__ **propertyKeyString)
{
  int v4; // ebx
  unsigned int v6; // edx
  PCWSTR StringRawBuffer; // rax
  HSTRING string; // [rsp+30h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+38h] [rbp-30h] BYREF
  void *retaddr; // [rsp+68h] [rbp+0h]

  if ( !userSid )
  {
    v6 = 300;
LABEL_9:
    v4 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      v6,
      "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.applicationdatafactory.server.cpp",
      -2147024809);
    return (unsigned int)v4;
  }
  if ( !propertyKeyString )
  {
    v6 = 301;
    goto LABEL_9;
  }
  if ( WindowsCreateStringReference(L"Windows.Storage.ApplicationData", 0x1Fu, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v4 = WindowsConcatString(string, userSid, propertyKeyString);
  if ( v4 < 0 )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(userSid, 0);
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      0x12Fu,
      "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\windows.storage.applicationdatafactory.server.cpp",
      v4,
      "WindowsConcatString %ws",
      StringRawBuffer);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180017150  mov     [rsp+arg_10], rbx
0x180017155  push    rdi
0x180017156  sub     rsp, 60h
0x18001715a  mov     rax, cs:__security_cookie
0x180017161  xor     rax, rsp
0x180017164  mov     [rsp+68h+var_18], rax
0x180017169  mov     rbx, propertyKeyString
0x18001716c  mov     rdi, userSid
0x18001716f  test    userSid, userSid
0x180017172  jz      short loc_1800171D1
0x180017174  test    propertyKeyString, propertyKeyString
0x180017177  jz      loc_180017208
0x18001717d  lea     r9, [rsp+68h+string]; string
0x180017182  mov     edx, 1Fh; length
0x180017187  lea     r8, [rsp+68h+hstringHeader]; hstringHeader
0x18001718c  lea     userSid, ?RuntimeClass_Windows_Storage_ApplicationData@@3QBGB; "Windows.Storage.ApplicationData"
0x180017193  call    cs:__imp_WindowsCreateStringReference
0x180017199  test    eax, eax
0x18001719b  js      short loc_1800171F1
0x18001719d  mov     userSid, [rsp+68h+string]; string1
0x1800171a2  mov     r8, rbx; newString
0x1800171a5  mov     propertyKeyString, rdi; string2
0x1800171a8  call    cs:__imp_WindowsConcatString
0x1800171ae  mov     ebx, eax
0x1800171b0  test    eax, eax
0x1800171b2  js      short loc_18001720F
0x1800171b4  mov     eax, ebx
0x1800171b6  mov     userSid, [rsp+68h+var_18]
0x1800171bb  xor     userSid, rsp; StackCookie
0x1800171be  call    __security_check_cookie
0x1800171c3  mov     rbx, [rsp+68h+arg_10]
0x1800171cb  add     rsp, 60h
0x1800171cf  pop     rdi
0x1800171d0  retn
0x1800171d1  mov     edx, 12Ch; lineNumber
0x1800171d6  mov     userSid, [rsp+68h]; callerReturnAddress
0x1800171db  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\appmodel\\statemanage"...
0x1800171e2  mov     ebx, 80070057h
0x1800171e7  mov     r9d, ebx; hr
0x1800171ea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800171ef  jmp     short loc_1800171B4
0x1800171f1  xor     r9d, r9d; lpArguments
0x1800171f4  xor     r8d, r8d; nNumberOfArguments
0x1800171f7  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800171fc  lea     edx, [r9+1]; dwExceptionFlags
0x180017200  call    cs:__imp_RaiseException
0x180017206  jmp     short loc_18001719D
0x180017208  mov     edx, 12Dh
0x18001720d  jmp     short loc_1800171D6
0x18001720f  xor     edx, edx; length
0x180017211  mov     userSid, rdi; string
0x180017214  call    cs:__imp_WindowsGetStringRawBuffer
0x18001721a  mov     userSid, [rsp+68h]; callerReturnAddress
0x18001721f  lea     r8, aOnecoreuapBase_1; "onecoreuap\\base\\appmodel\\statemanage"...
0x180017226  mov     [rsp+68h+var_40], rax
0x18001722b  mov     r9d, ebx; hr
0x18001722e  lea     rax, aWindowsconcats_0; "WindowsConcatString %ws"
0x180017235  mov     edx, 12Fh; lineNumber
0x18001723a  mov     [rsp+68h+formatString], rax; formatString
0x18001723f  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180017244  jmp     loc_1800171B4
```
