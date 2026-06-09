# IsDeviceAADJoined(bool &,ushort * *)

- ea: `0x18015d678`
- end: `0x18015d896`
- name: `?IsDeviceAADJoined@@YAJAEA_NPEAPEAG@Z`
- size: `542`
- prototype: `__int64 __fastcall(bool *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18015e978`

## callees

- `0x180001308`
- `0x18000202c`
- `0x18015d678`
- `0x18019c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18015d75c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18015d76f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18015d75c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18015d76f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18015d883`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18015d883`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015d6b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015d6b1`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18015d69c`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18015d69c`

## string_xrefs

- `0x18015d695`: `netapi32.dll`
- `0x18015d6d5`: `LoadLibrary(netapi32.dll)`
- `0x18015d6f9`: `onecore\termsrv\rdp\win\security\rdsaadauthserver.cpp`
- `0x18015d7d1`: `onecore\termsrv\rdp\win\security\rdsaadauthserver.cpp`
- `0x18015d840`: `NetGetAadJoinInformation or NetFreeAadJoinInformation is not implemented in netapi32.dll`

## pseudocode

```c
__int64 __fastcall IsDeviceAADJoined(bool *a1, unsigned __int16 **a2)
{
  HMODULE LibraryW; // rax
  HMODULE v4; // rsi
  void (*v5)(void); // r14
  signed int LastError; // eax
  int v7; // ecx
  int v8; // r8d
  int v9; // r9d
  signed int v10; // ebx
  __int16 *v11; // rdx
  const char **v12; // rax
  FARPROC ProcAddress; // rbx
  FARPROC v14; // rax
  int v15; // ecx
  int v16; // r8d
  int v17; // r9d
  bool v18; // al
  const char **v20; // [rsp+30h] [rbp-40h]
  const char **v21; // [rsp+40h] [rbp-30h]
  const char **v22; // [rsp+48h] [rbp-28h]
  const char *v23; // [rsp+50h] [rbp-20h] BYREF
  const char *v24; // [rsp+58h] [rbp-18h] BYREF
  const char *v25; // [rsp+60h] [rbp-10h] BYREF
  const char *v26; // [rsp+68h] [rbp-8h] BYREF
  const char *v27; // [rsp+A8h] [rbp+38h] BYREF
  signed int v28; // [rsp+B0h] [rbp+40h] BYREF
  _DWORD *v29; // [rsp+B8h] [rbp+48h] BYREF

  v27 = (const char *)a2;
  v29 = 0;
  LibraryW = LoadLibraryW(L"netapi32.dll");
  v4 = LibraryW;
  if ( LibraryW )
  {
    ProcAddress = GetProcAddress(LibraryW, "NetGetAadJoinInformation");
    v14 = GetProcAddress(v4, "NetFreeAadJoinInformation");
    v5 = (void (*)(void))v14;
    if ( ProcAddress && v14 )
    {
      v10 = ((__int64 (__fastcall *)(_QWORD, _DWORD **))ProcAddress)(0, &v29);
      if ( v10 < 0 )
      {
        v7 = (int)CallbackContext;
        if ( (unsigned int)CallbackContext <= 2 )
          goto LABEL_19;
        LODWORD(v27) = 937;
        v26 = "NetGetAadJoinInformation failed";
        v11 = &word_18029F8D6;
        v25 = "IsDeviceAADJoined";
        v24 = "onecore\\termsrv\\rdp\\win\\security\\rdsaadauthserver.cpp";
        v23 = "Error HResult failed";
        v22 = &v26;
        v21 = &v25;
        v20 = &v24;
        v12 = &v23;
        goto LABEL_6;
      }
      if ( !v29 || (v18 = 1, *v29 != 1) )
        v18 = 0;
      *a1 = v18;
    }
    else
    {
      if ( (unsigned int)CallbackContext > 4 )
      {
        v27 = "NetGetAadJoinInformation or NetFreeAadJoinInformation is not implemented in netapi32.dll";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          v15,
          (unsigned int)qword_18029F978,
          v16,
          v17,
          (__int64)&v27);
      }
      *a1 = 0;
      v10 = 0;
    }
  }
  else
  {
    v5 = 0;
    LastError = GetLastError();
    v10 = LastError;
    if ( LastError > 0 )
      v10 = (unsigned __int16)LastError | 0x80070000;
    if ( (unsigned int)CallbackContext > 2 )
    {
      LODWORD(v27) = 919;
      v23 = "LoadLibrary(netapi32.dll)";
      v11 = (__int16 *)&byte_18029F927;
      v24 = "IsDeviceAADJoined";
      v25 = "onecore\\termsrv\\rdp\\win\\security\\rdsaadauthserver.cpp";
      v26 = "Error condition failed";
      v22 = &v23;
      v21 = &v24;
      v20 = &v25;
      v12 = &v26;
LABEL_6:
      v28 = v10;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v7,
        (_DWORD)v11,
        v8,
        v9,
        (__int64)v12,
        (__int64)&v28,
        (__int64)v20,
        (__int64)&v27,
        (__int64)v21,
        (__int64)v22);
    }
  }
LABEL_19:
  if ( v29 && v5 )
    v5();
  if ( v4 )
    FreeLibrary(v4);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18015d678  mov     [rsp-28h+arg_8], rdx
0x18015d67d  push    rbp
0x18015d67e  push    rbx
0x18015d67f  push    rsi
0x18015d680  push    rdi
0x18015d681  push    r14
0x18015d683  mov     rbp, rsp
0x18015d686  sub     rsp, 70h
0x18015d68a  mov     rdi, rcx
0x18015d68d  mov     [rbp+arg_18], 0
0x18015d695  lea     rcx, aNetapi32Dll; "netapi32.dll"
0x18015d69c  call    cs:__imp_LoadLibraryW
0x18015d6a2  mov     rsi, rax
0x18015d6a5  test    rax, rax
0x18015d6a8  jnz     loc_18015D752
0x18015d6ae  xor     r14d, r14d
0x18015d6b1  call    cs:__imp_GetLastError
0x18015d6b7  mov     ebx, eax
0x18015d6b9  test    eax, eax
0x18015d6bb  jle     short loc_18015D6C6
0x18015d6bd  movzx   ebx, ax
0x18015d6c0  or      ebx, 80070000h
0x18015d6c6  mov     eax, cs:CallbackContext
0x18015d6cc  cmp     eax, 2
0x18015d6cf  jbe     loc_18015D865
0x18015d6d5  lea     rax, aLoadlibraryNet; "LoadLibrary(netapi32.dll)"
0x18015d6dc  mov     dword ptr [rbp+arg_8], 397h
0x18015d6e3  mov     [rbp+var_20], rax
0x18015d6e7  lea     rdx, byte_18029F927
0x18015d6ee  lea     rax, aIsdeviceaadjoi; "IsDeviceAADJoined"
0x18015d6f5  mov     [rbp+var_18], rax
0x18015d6f9  lea     rax, aOnecoreTermsrv_7; "onecore\\termsrv\\rdp\\win\\security\\r"...
0x18015d700  mov     [rbp+var_10], rax
0x18015d704  lea     rax, aErrorCondition; "Error condition failed"
0x18015d70b  mov     [rbp+var_8], rax
0x18015d70f  lea     rax, [rbp+var_20]
0x18015d713  mov     [rsp+70h+var_28], rax
0x18015d718  lea     rax, [rbp+var_18]
0x18015d71c  mov     [rsp+70h+var_30], rax
0x18015d721  lea     rax, [rbp+arg_8]
0x18015d725  mov     [rsp+70h+var_38], rax
0x18015d72a  lea     rax, [rbp+var_10]
0x18015d72e  mov     [rsp+70h+var_40], rax
0x18015d733  lea     rax, [rbp+arg_10]
0x18015d737  mov     [rsp+70h+var_48], rax
0x18015d73c  lea     rax, [rbp+var_8]
0x18015d740  mov     [rsp+70h+var_50], rax
0x18015d745  mov     [rbp+arg_10], ebx
0x18015d748  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18015d74d  jmp     loc_18015D865
0x18015d752  lea     rdx, aNetgetaadjoini; "NetGetAadJoinInformation"
0x18015d759  mov     rcx, rsi; hModule
0x18015d75c  call    cs:__imp_GetProcAddress
0x18015d762  lea     rdx, aNetfreeaadjoin; "NetFreeAadJoinInformation"
0x18015d769  mov     rcx, rsi; hModule
0x18015d76c  mov     rbx, rax
0x18015d76f  call    cs:__imp_GetProcAddress
0x18015d775  mov     r14, rax
0x18015d778  test    rbx, rbx
0x18015d77b  jz      loc_18015D835
0x18015d781  test    rax, rax
0x18015d784  jz      loc_18015D835
0x18015d78a  lea     rdx, [rbp+arg_18]
0x18015d78e  xor     ecx, ecx
0x18015d790  mov     rax, rbx
0x18015d793  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015d798  mov     ebx, eax
0x18015d79a  test    eax, eax
0x18015d79c  jns     short loc_18015D81D
0x18015d79e  mov     ecx, cs:CallbackContext
0x18015d7a4  cmp     ecx, 2
0x18015d7a7  jbe     loc_18015D865
0x18015d7ad  lea     rax, aNetgetaadjoini_1; "NetGetAadJoinInformation failed"
0x18015d7b4  mov     dword ptr [rbp+arg_8], 3A9h
0x18015d7bb  mov     [rbp+var_8], rax
0x18015d7bf  lea     rdx, word_18029F8D6
0x18015d7c6  lea     rax, aIsdeviceaadjoi; "IsDeviceAADJoined"
0x18015d7cd  mov     [rbp+var_10], rax
0x18015d7d1  lea     rax, aOnecoreTermsrv_7; "onecore\\termsrv\\rdp\\win\\security\\r"...
0x18015d7d8  mov     [rbp+var_18], rax
0x18015d7dc  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18015d7e3  mov     [rbp+var_20], rax
0x18015d7e7  lea     rax, [rbp+var_8]
0x18015d7eb  mov     [rsp+70h+var_28], rax
0x18015d7f0  lea     rax, [rbp+var_10]
0x18015d7f4  mov     [rsp+70h+var_30], rax
0x18015d7f9  lea     rax, [rbp+arg_8]
0x18015d7fd  mov     [rsp+70h+var_38], rax
0x18015d802  lea     rax, [rbp+var_18]
0x18015d806  mov     [rsp+70h+var_40], rax
0x18015d80b  lea     rax, [rbp+arg_10]
0x18015d80f  mov     [rsp+70h+var_48], rax
0x18015d814  lea     rax, [rbp+var_20]
0x18015d818  jmp     loc_18015D740
0x18015d81d  mov     rcx, [rbp+arg_18]
0x18015d821  test    rcx, rcx
0x18015d824  jz      short loc_18015D82F
0x18015d826  mov     eax, 1
0x18015d82b  cmp     [rcx], eax
0x18015d82d  jz      short loc_18015D831
0x18015d82f  xor     al, al
0x18015d831  mov     [rdi], al
0x18015d833  jmp     short loc_18015D865
0x18015d835  mov     eax, cs:CallbackContext
0x18015d83b  cmp     eax, 4
0x18015d83e  jbe     short loc_18015D860
0x18015d840  lea     rax, aNetgetaadjoini_0; "NetGetAadJoinInformation or NetFreeAadJ"...
0x18015d847  mov     [rbp+arg_8], rax
0x18015d84b  lea     rdx, qword_18029F978
0x18015d852  lea     rax, [rbp+arg_8]
0x18015d856  mov     [rsp+70h+var_50], rax
0x18015d85b  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18015d860  mov     byte ptr [rdi], 0
0x18015d863  xor     ebx, ebx
0x18015d865  mov     rcx, [rbp+arg_18]
0x18015d869  test    rcx, rcx
0x18015d86c  jz      short loc_18015D87B
0x18015d86e  test    r14, r14
0x18015d871  jz      short loc_18015D87B
0x18015d873  mov     rax, r14
0x18015d876  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015d87b  test    rsi, rsi
0x18015d87e  jz      short loc_18015D889
0x18015d880  mov     rcx, rsi; hLibModule
0x18015d883  call    cs:__imp_FreeLibrary
0x18015d889  mov     eax, ebx
0x18015d88b  add     rsp, 70h
0x18015d88f  pop     r14
0x18015d891  pop     rdi
0x18015d892  pop     rsi
0x18015d893  pop     rbx
0x18015d894  pop     rbp
0x18015d895  retn
```
