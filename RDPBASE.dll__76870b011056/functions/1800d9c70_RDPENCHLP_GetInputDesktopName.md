# RDPENCHLP_GetInputDesktopName

- ea: `0x1800d9c70`
- end: `0x1800d9e09`
- name: `RDPENCHLP_GetInputDesktopName`
- size: `409`
- prototype: `__int64 __fastcall(PVOID pvInfo, DWORD nLength)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180004970`
- `0x1800d9c70`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d9cc6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d9d68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d9cc6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d9d68`
- `ext-ms-win-ntuser-windowstation-l1-1-1!OpenInputDesktop` at `0x1800d9c93`
- `ext-ms-win-ntuser-windowstation-l1-1-1!OpenInputDesktop` at `0x1800d9c93`
- `ext-ms-win-ntuser-windowstation-l1-1-0!CloseDesktop` at `0x1800d9d5d`
- `ext-ms-win-ntuser-windowstation-l1-1-0!CloseDesktop` at `0x1800d9d5d`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x1800d9cb8`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x1800d9cb8`

## string_xrefs

- `0x1800d9da2`: `Failed to open the input desktop (%d)`

## pseudocode

```c
__int64 __fastcall RDPENCHLP_GetInputDesktopName(_WORD *pvInfo, DWORD nLength)
{
  HDESK v4; // rax
  HDESK v5; // rdi
  signed int LastError; // ebx
  int v7; // ecx
  int v8; // r8d
  int v9; // r9d
  int v10; // ecx
  int v11; // r8d
  int v12; // r9d
  const char *v14; // [rsp+50h] [rbp-20h] BYREF
  const char *v15; // [rsp+58h] [rbp-18h] BYREF
  _QWORD v16[2]; // [rsp+60h] [rbp-10h] BYREF
  signed int v17; // [rsp+A0h] [rbp+30h] BYREF
  int v18; // [rsp+B0h] [rbp+40h] BYREF
  int v19; // [rsp+B8h] [rbp+48h] BYREF

  *pvInfo = 0;
  v4 = OpenInputDesktop(0, 0, 0x81u);
  v5 = v4;
  if ( v4 )
  {
    LastError = 0;
    if ( !GetUserObjectInformationW(v4, 2, pvInfo, nLength, 0) )
    {
      LastError = GetLastError();
      if ( (unsigned int)CallbackContext > 2 )
      {
        v17 = LastError;
        v14 = "RDPENCHLP_GetInputDesktopName";
        v18 = 53;
        v15 = "onecore\\termsrv\\rdpplatform\\rdpenc\\enchlpr\\encdskhlp.cpp";
        v16[0] = "Failed to query  the input desktop name (%d)";
        v19 = -2147467259;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v7,
          (unsigned int)qword_1801BBA70,
          v8,
          v9,
          (__int64)v16,
          (__int64)&v19,
          (__int64)&v15,
          (__int64)&v18,
          (__int64)&v14,
          (__int64)&v17);
      }
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
    }
    CloseDesktop(v5);
  }
  else
  {
    LastError = GetLastError();
    if ( (unsigned int)CallbackContext > 2 )
    {
      v17 = LastError;
      v16[0] = "RDPENCHLP_GetInputDesktopName";
      v18 = 60;
      v15 = "onecore\\termsrv\\rdpplatform\\rdpenc\\enchlpr\\encdskhlp.cpp";
      v14 = "Failed to open the input desktop (%d)";
      v19 = -2147467259;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v10,
        (unsigned int)&word_1801BBA1E,
        v11,
        v12,
        (__int64)&v14,
        (__int64)&v19,
        (__int64)&v15,
        (__int64)&v18,
        (__int64)v16,
        (__int64)&v17);
    }
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x1800d9c70  push    rbp
0x1800d9c72  push    rbx
0x1800d9c73  push    rsi
0x1800d9c74  push    rdi
0x1800d9c75  push    r14
0x1800d9c77  mov     rbp, rsp
0x1800d9c7a  sub     rsp, 70h
0x1800d9c7e  xor     eax, eax
0x1800d9c80  mov     r14d, edx
0x1800d9c83  mov     [rcx], ax
0x1800d9c86  mov     rsi, rcx
0x1800d9c89  xor     ecx, ecx; dwFlags
0x1800d9c8b  xor     edx, edx; fInherit
0x1800d9c8d  mov     r8d, 81h; dwDesiredAccess
0x1800d9c93  call    cs:__imp_OpenInputDesktop
0x1800d9c99  mov     rdi, rax
0x1800d9c9c  test    rax, rax
0x1800d9c9f  jz      loc_1800D9D68
0x1800d9ca5  xor     ebx, ebx
0x1800d9ca7  mov     r9d, r14d; nLength
0x1800d9caa  mov     r8, rsi; pvInfo
0x1800d9cad  mov     [rsp+70h+lpnLengthNeeded], rbx; lpnLengthNeeded
0x1800d9cb2  mov     rcx, rax; hObj
0x1800d9cb5  lea     edx, [rbx+2]; nIndex
0x1800d9cb8  call    cs:__imp_GetUserObjectInformationW
0x1800d9cbe  test    eax, eax
0x1800d9cc0  jnz     loc_1800D9D5A
0x1800d9cc6  call    cs:__imp_GetLastError
0x1800d9ccc  mov     ebx, eax
0x1800d9cce  mov     eax, cs:CallbackContext
0x1800d9cd4  cmp     eax, 2
0x1800d9cd7  jbe     short loc_1800D9D4D
0x1800d9cd9  lea     rax, aRdpenchlpGetin_0; "RDPENCHLP_GetInputDesktopName"
0x1800d9ce0  mov     [rbp+arg_0], ebx
0x1800d9ce3  mov     [rbp+var_20], rax
0x1800d9ce7  lea     rdx, qword_1801BBA70
0x1800d9cee  lea     rax, aOnecoreTermsrv_48; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1800d9cf5  mov     [rbp+arg_10], 35h ; '5'
0x1800d9cfc  mov     [rbp+var_18], rax
0x1800d9d00  lea     rax, aFailedToQueryT_4; "Failed to query  the input desktop name"...
0x1800d9d07  mov     [rbp+var_10], rax
0x1800d9d0b  lea     rax, [rbp+arg_0]
0x1800d9d0f  mov     [rsp+70h+var_28], rax
0x1800d9d14  lea     rax, [rbp+var_20]
0x1800d9d18  mov     [rsp+70h+var_30], rax
0x1800d9d1d  lea     rax, [rbp+arg_10]
0x1800d9d21  mov     [rsp+70h+var_38], rax
0x1800d9d26  lea     rax, [rbp+var_18]
0x1800d9d2a  mov     [rsp+70h+var_40], rax
0x1800d9d2f  lea     rax, [rbp+arg_18]
0x1800d9d33  mov     [rsp+70h+var_48], rax
0x1800d9d38  lea     rax, [rbp+var_10]
0x1800d9d3c  mov     [rsp+70h+lpnLengthNeeded], rax
0x1800d9d41  mov     [rbp+arg_18], 80004005h
0x1800d9d48  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800d9d4d  test    ebx, ebx
0x1800d9d4f  jle     short loc_1800D9D5A
0x1800d9d51  movzx   ebx, bx
0x1800d9d54  or      ebx, 80070000h
0x1800d9d5a  mov     rcx, rdi; hDesktop
0x1800d9d5d  call    cs:__imp_CloseDesktop
0x1800d9d63  jmp     loc_1800D9DFC
0x1800d9d68  call    cs:__imp_GetLastError
0x1800d9d6e  mov     ebx, eax
0x1800d9d70  mov     eax, cs:CallbackContext
0x1800d9d76  cmp     eax, 2
0x1800d9d79  jbe     short loc_1800D9DEF
0x1800d9d7b  lea     rax, aRdpenchlpGetin_0; "RDPENCHLP_GetInputDesktopName"
0x1800d9d82  mov     [rbp+arg_0], ebx
0x1800d9d85  mov     [rbp+var_10], rax
0x1800d9d89  lea     rdx, word_1801BBA1E
0x1800d9d90  lea     rax, aOnecoreTermsrv_48; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1800d9d97  mov     [rbp+arg_10], 3Ch ; '<'
0x1800d9d9e  mov     [rbp+var_18], rax
0x1800d9da2  lea     rax, aFailedToOpenTh; "Failed to open the input desktop (%d)"
0x1800d9da9  mov     [rbp+var_20], rax
0x1800d9dad  lea     rax, [rbp+arg_0]
0x1800d9db1  mov     [rsp+70h+var_28], rax
0x1800d9db6  lea     rax, [rbp+var_10]
0x1800d9dba  mov     [rsp+70h+var_30], rax
0x1800d9dbf  lea     rax, [rbp+arg_10]
0x1800d9dc3  mov     [rsp+70h+var_38], rax
0x1800d9dc8  lea     rax, [rbp+var_18]
0x1800d9dcc  mov     [rsp+70h+var_40], rax
0x1800d9dd1  lea     rax, [rbp+arg_18]
0x1800d9dd5  mov     [rsp+70h+var_48], rax
0x1800d9dda  lea     rax, [rbp+var_20]
0x1800d9dde  mov     [rsp+70h+lpnLengthNeeded], rax
0x1800d9de3  mov     [rbp+arg_18], 80004005h
0x1800d9dea  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800d9def  test    ebx, ebx
0x1800d9df1  jle     short loc_1800D9DFC
0x1800d9df3  movzx   ebx, bx
0x1800d9df6  or      ebx, 80070000h
0x1800d9dfc  mov     eax, ebx
0x1800d9dfe  add     rsp, 70h
0x1800d9e02  pop     r14
0x1800d9e04  pop     rdi
0x1800d9e05  pop     rsi
0x1800d9e06  pop     rbx
0x1800d9e07  pop     rbp
0x1800d9e08  retn
```
