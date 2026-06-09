# ActiveDirectoryHelper::Initialize(void)

- ea: `0x180162a20`
- end: `0x180162bd6`
- name: `?Initialize@ActiveDirectoryHelper@@UEAAJXZ`
- size: `438`
- prototype: `__int64 __fastcall(ActiveDirectoryHelper *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000116c`
- `0x18000202c`
- `0x180162a20`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180162af2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180162b07`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180162b1c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180162b31`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180162af2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180162b07`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180162b1c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180162b31`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180162a47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180162a47`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180162a34`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180162a34`

## string_xrefs

- `0x180162a6b`: `LoadLibrary(activeds.dll)`
- `0x180162a2d`: `activeds.dll`
- `0x180162ae8`: `ADsOpenObject`
- `0x180162a92`: `onecore\termsrv\rdp\win\security\activedirectoryhelper.cpp`
- `0x180162b82`: `onecore\termsrv\rdp\win\security\activedirectoryhelper.cpp`
- `0x180162b90`: `Some required functions are not implemented in activeds.dll`

## pseudocode

```c
__int64 __fastcall ActiveDirectoryHelper::Initialize(ActiveDirectoryHelper *this)
{
  HMODULE LibraryW; // rax
  signed int LastError; // eax
  int v4; // ecx
  int v5; // r8d
  int v6; // r9d
  unsigned int v7; // ebx
  FARPROC ProcAddress; // rax
  HMODULE v9; // rcx
  FARPROC v10; // rax
  HMODULE v11; // rcx
  FARPROC v12; // rax
  HMODULE v13; // rcx
  FARPROC v14; // rax
  int v15; // ecx
  int v16; // r8d
  int v17; // r9d
  bool v18; // zf
  const char *v20; // [rsp+50h] [rbp-18h] BYREF
  _QWORD v21[2]; // [rsp+58h] [rbp-10h] BYREF
  int v22; // [rsp+80h] [rbp+18h] BYREF
  int v23; // [rsp+88h] [rbp+20h] BYREF
  const char *v24; // [rsp+90h] [rbp+28h] BYREF
  const char *v25; // [rsp+98h] [rbp+30h] BYREF

  LibraryW = LoadLibraryW(L"activeds.dll");
  *((_QWORD *)this + 5) = LibraryW;
  if ( LibraryW )
  {
    ProcAddress = GetProcAddress(LibraryW, "ADsOpenObject");
    v9 = (HMODULE)*((_QWORD *)this + 5);
    *((_QWORD *)this + 6) = ProcAddress;
    v10 = GetProcAddress(v9, "ADsBuildEnumerator");
    v11 = (HMODULE)*((_QWORD *)this + 5);
    *((_QWORD *)this + 7) = v10;
    v12 = GetProcAddress(v11, "ADsFreeEnumerator");
    v13 = (HMODULE)*((_QWORD *)this + 5);
    *((_QWORD *)this + 8) = v12;
    v14 = GetProcAddress(v13, "ADsEnumerateNext");
    v18 = *((_QWORD *)this + 6) == 0;
    *((_QWORD *)this + 9) = v14;
    if ( !v18 && *((_QWORD *)this + 7) && *((_QWORD *)this + 8) && v14 )
    {
      return 0;
    }
    else
    {
      v7 = -2147467259;
      if ( (unsigned int)CallbackContext > 2 )
      {
        v22 = 67;
        v24 = "Initialize";
        v23 = -2147467259;
        v25 = "onecore\\termsrv\\rdp\\win\\security\\activedirectoryhelper.cpp";
        v21[0] = "Some required functions are not implemented in activeds.dll";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v15,
          (unsigned int)byte_1802A0DDB,
          v16,
          v17,
          (__int64)v21,
          (__int64)&v23,
          (__int64)&v25,
          (__int64)&v22,
          (__int64)&v24);
      }
    }
  }
  else
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
    if ( (unsigned int)CallbackContext > 2 )
    {
      v22 = 51;
      v24 = "LoadLibrary(activeds.dll)";
      v23 = v7;
      v25 = "Initialize";
      v20 = "onecore\\termsrv\\rdp\\win\\security\\activedirectoryhelper.cpp";
      v21[0] = "Error condition failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v4,
        (unsigned int)byte_1802A0D85,
        v5,
        v6,
        (__int64)v21,
        (__int64)&v23,
        (__int64)&v20,
        (__int64)&v22,
        (__int64)&v25,
        (__int64)&v24);
    }
  }
  return v7;
}

```

## disassembly

```asm
0x180162a20  push    rbp
0x180162a22  push    rbx
0x180162a23  mov     rbp, rsp
0x180162a26  sub     rsp, 68h
0x180162a2a  mov     rbx, rcx
0x180162a2d  lea     rcx, aActivedsDll; "activeds.dll"
0x180162a34  call    cs:__imp_LoadLibraryW
0x180162a3a  mov     [rbx+28h], rax
0x180162a3e  test    rax, rax
0x180162a41  jnz     loc_180162AE8
0x180162a47  call    cs:__imp_GetLastError
0x180162a4d  mov     ebx, eax
0x180162a4f  test    eax, eax
0x180162a51  jle     short loc_180162A5C
0x180162a53  movzx   ebx, ax
0x180162a56  or      ebx, 80070000h
0x180162a5c  mov     eax, cs:CallbackContext
0x180162a62  cmp     eax, 2
0x180162a65  jbe     loc_180162BCD
0x180162a6b  lea     rax, aLoadlibraryAct; "LoadLibrary(activeds.dll)"
0x180162a72  mov     [rbp+arg_0], 33h ; '3'
0x180162a79  mov     [rbp+arg_10], rax
0x180162a7d  lea     rdx, byte_1802A0D85
0x180162a84  lea     rax, aInitialize; "Initialize"
0x180162a8b  mov     [rbp+arg_8], ebx
0x180162a8e  mov     [rbp+arg_18], rax
0x180162a92  lea     rax, aOnecoreTermsrv_54; "onecore\\termsrv\\rdp\\win\\security\\a"...
0x180162a99  mov     [rbp+var_18], rax
0x180162a9d  lea     rax, aErrorCondition; "Error condition failed"
0x180162aa4  mov     [rbp+var_10], rax
0x180162aa8  lea     rax, [rbp+arg_10]
0x180162aac  mov     [rsp+68h+var_20], rax
0x180162ab1  lea     rax, [rbp+arg_18]
0x180162ab5  mov     [rsp+68h+var_28], rax
0x180162aba  lea     rax, [rbp+arg_0]
0x180162abe  mov     [rsp+68h+var_30], rax
0x180162ac3  lea     rax, [rbp+var_18]
0x180162ac7  mov     [rsp+68h+var_38], rax
0x180162acc  lea     rax, [rbp+arg_8]
0x180162ad0  mov     [rsp+68h+var_40], rax
0x180162ad5  lea     rax, [rbp+var_10]
0x180162ad9  mov     [rsp+68h+var_48], rax
0x180162ade  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180162ae3  jmp     loc_180162BCD
0x180162ae8  lea     rdx, aAdsopenobject; "ADsOpenObject"
0x180162aef  mov     rcx, rax; hModule
0x180162af2  call    cs:__imp_GetProcAddress
0x180162af8  mov     rcx, [rbx+28h]; hModule
0x180162afc  lea     rdx, aAdsbuildenumer; "ADsBuildEnumerator"
0x180162b03  mov     [rbx+30h], rax
0x180162b07  call    cs:__imp_GetProcAddress
0x180162b0d  mov     rcx, [rbx+28h]; hModule
0x180162b11  lea     rdx, aAdsfreeenumera; "ADsFreeEnumerator"
0x180162b18  mov     [rbx+38h], rax
0x180162b1c  call    cs:__imp_GetProcAddress
0x180162b22  mov     rcx, [rbx+28h]; hModule
0x180162b26  lea     rdx, aAdsenumeratene; "ADsEnumerateNext"
0x180162b2d  mov     [rbx+40h], rax
0x180162b31  call    cs:__imp_GetProcAddress
0x180162b37  cmp     qword ptr [rbx+30h], 0
0x180162b3c  mov     [rbx+48h], rax
0x180162b40  jz      short loc_180162B59
0x180162b42  cmp     qword ptr [rbx+38h], 0
0x180162b47  jz      short loc_180162B59
0x180162b49  cmp     qword ptr [rbx+40h], 0
0x180162b4e  jz      short loc_180162B59
0x180162b50  test    rax, rax
0x180162b53  jz      short loc_180162B59
0x180162b55  xor     ebx, ebx
0x180162b57  jmp     short loc_180162BCD
0x180162b59  mov     eax, cs:CallbackContext
0x180162b5f  mov     ebx, 80004005h
0x180162b64  cmp     eax, 2
0x180162b67  jbe     short loc_180162BCD
0x180162b69  lea     rax, aInitialize; "Initialize"
0x180162b70  mov     [rbp+arg_0], 43h ; 'C'
0x180162b77  mov     [rbp+arg_10], rax
0x180162b7b  lea     rdx, byte_1802A0DDB
0x180162b82  lea     rax, aOnecoreTermsrv_54; "onecore\\termsrv\\rdp\\win\\security\\a"...
0x180162b89  mov     [rbp+arg_8], ebx
0x180162b8c  mov     [rbp+arg_18], rax
0x180162b90  lea     rax, aSomeRequiredFu; "Some required functions are not impleme"...
0x180162b97  mov     [rbp+var_10], rax
0x180162b9b  lea     rax, [rbp+arg_10]
0x180162b9f  mov     [rsp+68h+var_28], rax
0x180162ba4  lea     rax, [rbp+arg_0]
0x180162ba8  mov     [rsp+68h+var_30], rax
0x180162bad  lea     rax, [rbp+arg_18]
0x180162bb1  mov     [rsp+68h+var_38], rax
0x180162bb6  lea     rax, [rbp+arg_8]
0x180162bba  mov     [rsp+68h+var_40], rax
0x180162bbf  lea     rax, [rbp+var_10]
0x180162bc3  mov     [rsp+68h+var_48], rax
0x180162bc8  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180162bcd  mov     eax, ebx
0x180162bcf  add     rsp, 68h
0x180162bd3  pop     rbx
0x180162bd4  pop     rbp
0x180162bd5  retn
```
