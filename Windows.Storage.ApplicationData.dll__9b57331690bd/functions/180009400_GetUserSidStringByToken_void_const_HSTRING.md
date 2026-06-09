# GetUserSidStringByToken(void * const,HSTRING__ * *)

- ea: `0x180009400`
- end: `0x18000960d`
- name: `?GetUserSidStringByToken@@YAJQEAXPEAPEAUHSTRING__@@@Z`
- size: `525`
- prototype: `HRESULT __fastcall(void *const token, HSTRING__ **userSidHString)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180007b10`
- `0x18003f524`

## callees

- `0x180009400`
- `0x180009778`
- `0x18002011c`
- `0x180021efc`
- `0x180021fc4`
- `0x180041620`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800094d9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800094d9`
- `ntdll!RtlValidSid` at `0x180009470`
- `ntdll!RtlValidSid` at `0x180009470`
- `ntdll!RtlConvertSidToUnicodeString` at `0x180009491`
- `ntdll!RtlConvertSidToUnicodeString` at `0x180009491`
- `ntdll!RtlFreeUnicodeString` at `0x180009519`
- `ntdll!RtlFreeUnicodeString` at `0x180009600`
- `ntdll!RtlFreeUnicodeString` at `0x180009519`
- `ntdll!RtlFreeUnicodeString` at `0x180009600`
- `ntdll!NtQueryInformationToken` at `0x180009452`
- `ntdll!NtQueryInformationToken` at `0x180009452`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800094fc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800094fc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800094ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800094ee`

## string_xrefs

- `0x18000954a`: `onecoreuap\base\appmodel\statemanager\winrt\lib\PreComp.h`
- `0x180009570`: `onecoreuap\base\appmodel\statemanager\winrt\lib\PreComp.h`
- `0x1800095dd`: `onecoreuap\base\appmodel\statemanager\winrt\lib\PreComp.h`
- `0x1800095ce`: `SidString %ws`

## pseudocode

```c
HRESULT __fastcall GetUserSidStringByToken(void *const token, HSTRING__ **userSidHString)
{
  NTSTATUS v3; // eax
  const char *v4; // r8
  PSID v5; // rbx
  NTSTATUS v6; // eax
  const char *v7; // r8
  unsigned __int64 v8; // rbx
  wchar_t *Buffer; // rdi
  int v10; // ebx
  unsigned int length; // [rsp+30h] [rbp-B8h] BYREF
  _UNICODE_STRING sidUnicodeString; // [rsp+38h] [rbp-B0h] BYREF
  HSTRING string; // [rsp+48h] [rbp-A0h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+50h] [rbp-98h] BYREF
  PSID tokenInformation[12]; // [rsp+70h] [rbp-78h] BYREF
  void *retaddr; // [rsp+E8h] [rbp+0h]

  if ( token )
  {
    if ( userSidHString )
    {
      length = 0;
      v3 = NtQueryInformationToken(token, TokenUser, tokenInformation, 0x54u, &length);
      if ( v3 < 0 )
      {
        return wil::details::in1diag3::Return_NtStatus(retaddr, 0x55u, v4, v3);
      }
      else
      {
        v5 = tokenInformation[0];
        if ( !RtlValidSid(tokenInformation[0]) )
          MicrosoftTelemetryAssertTriggeredNoArgs();
        sidUnicodeString = 0;
        v6 = RtlConvertSidToUnicodeString(&sidUnicodeString, v5, 1u);
        if ( v6 < 0 )
        {
          return wil::details::in1diag3::Return_NtStatus(retaddr, 0x5Du, v7, v6);
        }
        else
        {
          v8 = -1;
          Buffer = sidUnicodeString.Buffer;
          do
            ++v8;
          while ( sidUnicodeString.Buffer[v8] );
          if ( v8 > 0xFFFFFFFF )
          {
            LODWORD(v8) = -1;
            RaiseException(0xC000000D, 1u, 0, 0);
          }
          WindowsCreateStringReference(Buffer, v8, &hstringHeader, &string);
          v10 = WindowsDuplicateString(string, userSidHString);
          if ( v10 < 0 )
          {
            wil::details::in1diag3::Return_HrMsg(
              retaddr,
              0x65u,
              "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\PreComp.h",
              v10,
              "SidString %ws",
              sidUnicodeString.Buffer);
            RtlFreeUnicodeString(&sidUnicodeString);
            return v10;
          }
          else
          {
            RtlFreeUnicodeString(&sidUnicodeString);
            return 0;
          }
        }
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        0x4Fu,
        "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\PreComp.h",
        -2147024809);
      return -2147024809;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      0x4Eu,
      "onecoreuap\\base\\appmodel\\statemanager\\winrt\\lib\\PreComp.h",
      -2147024809);
    return -2147024809;
  }
}

```

## disassembly

```asm
0x180009400  push    rsi
0x180009402  sub     rsp, 0E0h
0x180009409  mov     rax, cs:__security_cookie
0x180009410  xor     rax, rsp
0x180009413  mov     [rsp+0E8h+var_18], rax
0x18000941b  mov     rsi, userSidHString
0x18000941e  test    token, token
0x180009421  jz      loc_180009542
0x180009427  test    userSidHString, userSidHString
0x18000942a  jz      loc_180009568
0x180009430  lea     rax, [rsp+0E8h+length]
0x180009435  mov     [rsp+0E8h+length], 0
0x18000943d  mov     r9d, 54h ; 'T'; TokenInformationLength
0x180009443  mov     [rsp+0E8h+ReturnLength], rax; ReturnLength
0x180009448  lea     r8, [rsp+0E8h+tokenInformation]; TokenInformation
0x18000944d  mov     edx, 1; TokenInformationClass
0x180009452  call    cs:__imp_NtQueryInformationToken
0x180009458  test    eax, eax
0x18000945a  js      loc_18000958E
0x180009460  mov     [rsp+0E8h+arg_10], rbx
0x180009468  mov     rbx, [rsp+0E8h+tokenInformation]
0x18000946d  mov     token, rbx; Sid
0x180009470  call    cs:__imp_RtlValidSid
0x180009476  test    al, al
0x180009478  jz      loc_1800095A5
0x18000947e  xorps   xmm0, xmm0
0x180009481  lea     token, [rsp+0E8h+sidUnicodeString]; UnicodeString
0x180009486  mov     r8b, 1; AllocateDestinationString
0x180009489  mov     userSidHString, rbx; Sid
0x18000948c  movups  xmmword ptr [rsp+0E8h+sidUnicodeString.Length], xmm0
0x180009491  call    cs:__imp_RtlConvertSidToUnicodeString
0x180009497  test    eax, eax
0x180009499  js      loc_1800095AF
0x18000949f  mov     [rsp+0E8h+arg_18], rdi
0x1800094a7  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x1800094ae  mov     rdi, [rsp+0E8h+sidUnicodeString.Buffer]
0x1800094b3  inc     rbx
0x1800094b6  cmp     word ptr [rdi+rbx*2], 0
0x1800094bb  jnz     short loc_1800094B3
0x1800094bd  mov     eax, 0FFFFFFFFh
0x1800094c2  cmp     rbx, rax
0x1800094c5  jbe     short loc_1800094DF
0x1800094c7  xor     r9d, r9d; lpArguments
0x1800094ca  xor     r8d, r8d; nNumberOfArguments
0x1800094cd  mov     edx, 1; dwExceptionFlags
0x1800094d2  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800094d7  mov     ebx, eax
0x1800094d9  call    cs:__imp_RaiseException
0x1800094df  lea     r9, [rsp+0E8h+string]; string
0x1800094e4  mov     edx, ebx; length
0x1800094e6  lea     r8, [rsp+0E8h+hstringHeader]; hstringHeader
0x1800094eb  mov     token, rdi; sourceString
0x1800094ee  call    cs:__imp_WindowsCreateStringReference
0x1800094f4  mov     token, [rsp+0E8h+string]; string
0x1800094f9  mov     userSidHString, rsi; newString
0x1800094fc  call    cs:__imp_WindowsDuplicateString
0x180009502  mov     rdi, [rsp+0E8h+arg_18]
0x18000950a  mov     ebx, eax
0x18000950c  test    eax, eax
0x18000950e  js      loc_1800095C9
0x180009514  lea     token, [rsp+0E8h+sidUnicodeString]; UnicodeString
0x180009519  call    cs:__imp_RtlFreeUnicodeString
0x18000951f  xor     eax, eax
0x180009521  mov     rbx, [rsp+0E8h+arg_10]
0x180009529  mov     token, [rsp+0E8h+var_18]
0x180009531  xor     token, rsp; StackCookie
0x180009534  call    __security_check_cookie
0x180009539  add     rsp, 0E0h
0x180009540  pop     rsi
0x180009541  retn
0x180009542  mov     token, [rsp+0E8h]; callerReturnAddress
0x18000954a  lea     r8, aOnecoreuapBase_22; "onecoreuap\\base\\appmodel\\statemanage"...
0x180009551  mov     r9d, 80070057h; hr
0x180009557  mov     edx, 4Eh ; 'N'; lineNumber
0x18000955c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009561  mov     eax, 80070057h
0x180009566  jmp     short loc_180009529
0x180009568  mov     token, [rsp+0E8h]; callerReturnAddress
0x180009570  lea     r8, aOnecoreuapBase_22; "onecoreuap\\base\\appmodel\\statemanage"...
0x180009577  mov     r9d, 80070057h; hr
0x18000957d  mov     edx, 4Fh ; 'O'; lineNumber
0x180009582  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009587  mov     eax, 80070057h
0x18000958c  jmp     short loc_180009529
0x18000958e  mov     token, [rsp+0E8h]; callerReturnAddress
0x180009596  mov     r9d, eax; callerReturnAddress
0x180009599  mov     edx, 55h ; 'U'; lineNumber
0x18000959e  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800095a3  jmp     short loc_180009529
0x1800095a5  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "RtlValidSid(sid)")
0x1800095aa  jmp     loc_18000947E
0x1800095af  mov     token, [rsp+0E8h]; callerReturnAddress
0x1800095b7  mov     r9d, eax; callerReturnAddress
0x1800095ba  mov     edx, 5Dh ; ']'; lineNumber
0x1800095bf  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800095c4  jmp     loc_180009521
0x1800095c9  mov     userSidHString, [rsp+0E8h+sidUnicodeString.Buffer]
0x1800095ce  lea     rax, aSidstringWs; "SidString %ws"
0x1800095d5  mov     token, [rsp+0E8h]; callerReturnAddress
0x1800095dd  lea     r8, aOnecoreuapBase_22; "onecoreuap\\base\\appmodel\\statemanage"...
0x1800095e4  mov     [rsp+0E8h+var_C0], userSidHString
0x1800095e9  mov     r9d, ebx; hr
0x1800095ec  mov     edx, 65h ; 'e'; lineNumber
0x1800095f1  mov     [rsp+0E8h+ReturnLength], rax; formatString
0x1800095f6  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800095fb  lea     token, [rsp+0E8h+sidUnicodeString]; UnicodeString
0x180009600  call    cs:__imp_RtlFreeUnicodeString
0x180009606  mov     eax, ebx
0x180009608  jmp     loc_180009521
```
