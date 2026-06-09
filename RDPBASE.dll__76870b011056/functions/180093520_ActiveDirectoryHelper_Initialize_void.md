# ActiveDirectoryHelper::Initialize(void)

- ea: `0x180093520`
- end: `0x1800936d6`
- name: `?Initialize@ActiveDirectoryHelper@@UEAAJXZ`
- size: `438`
- prototype: `__int64 __fastcall(ActiveDirectoryHelper *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800018a4`
- `0x180001aa0`
- `0x180093520`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800935f2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180093607`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18009361c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180093631`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800935f2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180093607`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18009361c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180093631`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180093547`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180093547`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180093534`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180093534`

## string_xrefs

- `0x18009352d`: `activeds.dll`
- `0x18009356b`: `LoadLibrary(activeds.dll)`
- `0x180093592`: `onecore\termsrv\rdp\win\security\activedirectoryhelper.cpp`
- `0x180093682`: `onecore\termsrv\rdp\win\security\activedirectoryhelper.cpp`
- `0x1800935e8`: `ADsOpenObject`
- `0x180093690`: `Some required functions are not implemented in activeds.dll`

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
          (unsigned int)word_1801AEE22,
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
        (unsigned int)&unk_1801AEE70,
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
0x180093520  push    rbp
0x180093522  push    rbx
0x180093523  mov     rbp, rsp
0x180093526  sub     rsp, 68h
0x18009352a  mov     rbx, rcx
0x18009352d  lea     rcx, aActivedsDll; "activeds.dll"
0x180093534  call    cs:__imp_LoadLibraryW
0x18009353a  mov     [rbx+28h], rax
0x18009353e  test    rax, rax
0x180093541  jnz     loc_1800935E8
0x180093547  call    cs:__imp_GetLastError
0x18009354d  mov     ebx, eax
0x18009354f  test    eax, eax
0x180093551  jle     short loc_18009355C
0x180093553  movzx   ebx, ax
0x180093556  or      ebx, 80070000h
0x18009355c  mov     eax, cs:CallbackContext
0x180093562  cmp     eax, 2
0x180093565  jbe     loc_1800936CD
0x18009356b  lea     rax, aLoadlibraryAct; "LoadLibrary(activeds.dll)"
0x180093572  mov     [rbp+arg_0], 33h ; '3'
0x180093579  mov     [rbp+arg_10], rax
0x18009357d  lea     rdx, unk_1801AEE70
0x180093584  lea     rax, aInitialize; "Initialize"
0x18009358b  mov     [rbp+arg_8], ebx
0x18009358e  mov     [rbp+arg_18], rax
0x180093592  lea     rax, aOnecoreTermsrv_56; "onecore\\termsrv\\rdp\\win\\security\\a"...
0x180093599  mov     [rbp+var_18], rax
0x18009359d  lea     rax, aErrorCondition; "Error condition failed"
0x1800935a4  mov     [rbp+var_10], rax
0x1800935a8  lea     rax, [rbp+arg_10]
0x1800935ac  mov     [rsp+68h+var_20], rax
0x1800935b1  lea     rax, [rbp+arg_18]
0x1800935b5  mov     [rsp+68h+var_28], rax
0x1800935ba  lea     rax, [rbp+arg_0]
0x1800935be  mov     [rsp+68h+var_30], rax
0x1800935c3  lea     rax, [rbp+var_18]
0x1800935c7  mov     [rsp+68h+var_38], rax
0x1800935cc  lea     rax, [rbp+arg_8]
0x1800935d0  mov     [rsp+68h+var_40], rax
0x1800935d5  lea     rax, [rbp+var_10]
0x1800935d9  mov     [rsp+68h+var_48], rax
0x1800935de  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1800935e3  jmp     loc_1800936CD
0x1800935e8  lea     rdx, aAdsopenobject; "ADsOpenObject"
0x1800935ef  mov     rcx, rax; hModule
0x1800935f2  call    cs:__imp_GetProcAddress
0x1800935f8  mov     rcx, [rbx+28h]; hModule
0x1800935fc  lea     rdx, aAdsbuildenumer; "ADsBuildEnumerator"
0x180093603  mov     [rbx+30h], rax
0x180093607  call    cs:__imp_GetProcAddress
0x18009360d  mov     rcx, [rbx+28h]; hModule
0x180093611  lea     rdx, aAdsfreeenumera; "ADsFreeEnumerator"
0x180093618  mov     [rbx+38h], rax
0x18009361c  call    cs:__imp_GetProcAddress
0x180093622  mov     rcx, [rbx+28h]; hModule
0x180093626  lea     rdx, aAdsenumeratene; "ADsEnumerateNext"
0x18009362d  mov     [rbx+40h], rax
0x180093631  call    cs:__imp_GetProcAddress
0x180093637  cmp     qword ptr [rbx+30h], 0
0x18009363c  mov     [rbx+48h], rax
0x180093640  jz      short loc_180093659
0x180093642  cmp     qword ptr [rbx+38h], 0
0x180093647  jz      short loc_180093659
0x180093649  cmp     qword ptr [rbx+40h], 0
0x18009364e  jz      short loc_180093659
0x180093650  test    rax, rax
0x180093653  jz      short loc_180093659
0x180093655  xor     ebx, ebx
0x180093657  jmp     short loc_1800936CD
0x180093659  mov     eax, cs:CallbackContext
0x18009365f  mov     ebx, 80004005h
0x180093664  cmp     eax, 2
0x180093667  jbe     short loc_1800936CD
0x180093669  lea     rax, aInitialize; "Initialize"
0x180093670  mov     [rbp+arg_0], 43h ; 'C'
0x180093677  mov     [rbp+arg_10], rax
0x18009367b  lea     rdx, word_1801AEE22
0x180093682  lea     rax, aOnecoreTermsrv_56; "onecore\\termsrv\\rdp\\win\\security\\a"...
0x180093689  mov     [rbp+arg_8], ebx
0x18009368c  mov     [rbp+arg_18], rax
0x180093690  lea     rax, aSomeRequiredFu; "Some required functions are not impleme"...
0x180093697  mov     [rbp+var_10], rax
0x18009369b  lea     rax, [rbp+arg_10]
0x18009369f  mov     [rsp+68h+var_28], rax
0x1800936a4  lea     rax, [rbp+arg_0]
0x1800936a8  mov     [rsp+68h+var_30], rax
0x1800936ad  lea     rax, [rbp+arg_18]
0x1800936b1  mov     [rsp+68h+var_38], rax
0x1800936b6  lea     rax, [rbp+arg_8]
0x1800936ba  mov     [rsp+68h+var_40], rax
0x1800936bf  lea     rax, [rbp+var_10]
0x1800936c3  mov     [rsp+68h+var_48], rax
0x1800936c8  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800936cd  mov     eax, ebx
0x1800936cf  add     rsp, 68h
0x1800936d3  pop     rbx
0x1800936d4  pop     rbp
0x1800936d5  retn
```
