# IsDeviceAADJoined(bool &,ushort * *)

- ea: `0x18008bf98`
- end: `0x18008c3ee`
- name: `?IsDeviceAADJoined@@YAJAEA_NPEAPEAG@Z`
- size: `1110`
- prototype: `__int64 __fastcall(bool *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x18008b024`
- `0x18008d4e0`

## callees

- `0x180001aa0`
- `0x180002550`
- `0x180038984`
- `0x18004a888`
- `0x1800787d4`
- `0x180078820`
- `0x18008bf98`
- `0x180162010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008c083`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008c096`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008c083`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008c096`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18008c3cf`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18008c3cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008bfd8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008bfd8`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18008bfc3`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18008bfc3`

## string_xrefs

- `0x18008c020`: `onecore\termsrv\rdp\win\security\rdsaadauthserver.cpp`
- `0x18008c0f8`: `onecore\termsrv\rdp\win\security\rdsaadauthserver.cpp`
- `0x18008c1b9`: `onecore\termsrv\rdp\win\security\rdsaadauthserver.cpp`
- `0x18008c26b`: `onecore\termsrv\rdp\win\security\rdsaadauthserver.cpp`
- `0x18008c306`: `onecore\termsrv\rdp\win\security\rdsaadauthserver.cpp`
- `0x18008bfb9`: `netapi32.dll`
- `0x18008bffc`: `LoadLibrary(netapi32.dll)`
- `0x18008c382`: `NetGetAadJoinInformation or NetFreeAadJoinInformation is not implemented in netapi32.dll`
- `0x18008c2df`: `StringCchCopyW`

## pseudocode

```c
__int64 __fastcall IsDeviceAADJoined(bool *a1, unsigned __int16 **a2)
{
  HMODULE LibraryW; // rax
  HMODULE v5; // r14
  void (*v6)(void); // r15
  signed int LastError; // eax
  int v8; // ecx
  int v9; // r8d
  int v10; // r9d
  signed int v11; // ebx
  __int16 *v12; // rdx
  const char **v13; // rax
  FARPROC ProcAddress; // rbx
  FARPROC v15; // rax
  int v16; // r9d
  __int64 v17; // rcx
  const unsigned __int16 *v18; // rcx
  unsigned __int64 v19; // rbx
  unsigned __int16 *v20; // rax
  unsigned __int16 *v21; // rsi
  int v22; // ecx
  int v23; // r8d
  int v24; // r9d
  const char **v26; // [rsp+30h] [rbp-50h]
  const char **v27; // [rsp+40h] [rbp-40h]
  const char **v28; // [rsp+48h] [rbp-38h]
  __int64 v29; // [rsp+50h] [rbp-30h] BYREF
  const char *v30; // [rsp+58h] [rbp-28h] BYREF
  const char *v31; // [rsp+60h] [rbp-20h] BYREF
  const char *v32; // [rsp+68h] [rbp-18h] BYREF
  _QWORD v33[2]; // [rsp+70h] [rbp-10h] BYREF
  unsigned __int64 v34; // [rsp+C0h] [rbp+40h] BYREF
  signed int v35; // [rsp+C8h] [rbp+48h] BYREF

  v29 = 0;
  LibraryW = LoadLibraryW(L"netapi32.dll");
  v5 = LibraryW;
  if ( LibraryW )
  {
    ProcAddress = GetProcAddress(LibraryW, "NetGetAadJoinInformation");
    v15 = GetProcAddress(v5, "NetFreeAadJoinInformation");
    v6 = (void (*)(void))v15;
    if ( ProcAddress && v15 )
    {
      v11 = ((__int64 (__fastcall *)(_QWORD, __int64 *))ProcAddress)(0, &v29);
      if ( v11 < 0 )
      {
        v8 = (int)CallbackContext;
        if ( (unsigned int)CallbackContext <= 2 )
          goto LABEL_31;
        LODWORD(v34) = 937;
        v33[0] = "NetGetAadJoinInformation failed";
        v12 = (__int16 *)&dword_1801AD26C;
        v32 = "IsDeviceAADJoined";
        v31 = "onecore\\termsrv\\rdp\\win\\security\\rdsaadauthserver.cpp";
        v30 = "Error HResult failed";
        v28 = (const char **)v33;
        v27 = &v32;
        v26 = &v31;
        v13 = &v30;
        goto LABEL_6;
      }
      v17 = v29;
      if ( v29 && *(_DWORD *)v29 == 1 )
      {
        *a1 = 1;
        if ( !a2 )
          goto LABEL_31;
        v18 = *(const unsigned __int16 **)(v17 + 16);
        v34 = 0;
        v11 = StringCchLengthW(v18, 0x104u, &v34);
        if ( v11 < 0 )
        {
          if ( (unsigned int)CallbackContext <= 2 )
            goto LABEL_31;
          LODWORD(v34) = 949;
          v33[0] = "StringCchLengthW failed";
          v12 = (__int16 *)byte_1801AD21B;
          v32 = "IsDeviceAADJoined";
          v31 = "onecore\\termsrv\\rdp\\win\\security\\rdsaadauthserver.cpp";
          v30 = "Error HResult failed";
          v28 = (const char **)v33;
          v27 = &v32;
          v26 = &v31;
          v13 = &v30;
          goto LABEL_6;
        }
        v19 = v34 + 1;
        v20 = (unsigned __int16 *)operator new(saturated_mul(v34 + 1, 2u));
        v21 = v20;
        if ( !v20 )
        {
          v11 = -2147024882;
          if ( (unsigned int)CallbackContext <= 2 )
            goto LABEL_31;
          LODWORD(v34) = 954;
          v33[0] = "pszDeviceId allocation failed";
          v12 = word_1801AD1CA;
          v32 = "IsDeviceAADJoined";
          v31 = "onecore\\termsrv\\rdp\\win\\security\\rdsaadauthserver.cpp";
          v30 = "Error condition failed";
          v28 = (const char **)v33;
          v27 = &v32;
          v26 = &v31;
          v13 = &v30;
          goto LABEL_6;
        }
        v11 = StringCchCopyW(v20, v19, *(const unsigned __int16 **)(v29 + 16));
        if ( v11 >= 0 )
        {
          *a2 = v21;
        }
        else
        {
          if ( (unsigned int)CallbackContext > 2 )
          {
            LODWORD(v34) = 957;
            v33[0] = "StringCchCopyW";
            v35 = v11;
            v32 = "IsDeviceAADJoined";
            v31 = "onecore\\termsrv\\rdp\\win\\security\\rdsaadauthserver.cpp";
            v30 = "Error HResult failed";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
              v22,
              (unsigned int)byte_1801AD179,
              v23,
              v24,
              (__int64)&v30,
              (__int64)&v35,
              (__int64)&v31,
              (__int64)&v34,
              (__int64)&v32,
              (__int64)v33);
          }
          operator delete(v21);
        }
      }
      else
      {
        *a1 = 0;
        if ( a2 )
          *a2 = 0;
      }
    }
    else
    {
      if ( (unsigned int)CallbackContext > 4 )
      {
        v34 = (unsigned __int64)"NetGetAadJoinInformation or NetFreeAadJoinInformation is not implemented in netapi32.dll";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          (unsigned int)&CallbackContext,
          (unsigned int)byte_1801AD2BD,
          0,
          v16,
          (__int64)&v34);
      }
      *a1 = 0;
      v11 = 0;
    }
  }
  else
  {
    v6 = 0;
    LastError = GetLastError();
    v11 = LastError;
    if ( LastError > 0 )
      v11 = (unsigned __int16)LastError | 0x80070000;
    if ( (unsigned int)CallbackContext > 2 )
    {
      LODWORD(v34) = 919;
      v30 = "LoadLibrary(netapi32.dll)";
      v12 = word_1801AD2E2;
      v31 = "IsDeviceAADJoined";
      v32 = "onecore\\termsrv\\rdp\\win\\security\\rdsaadauthserver.cpp";
      v33[0] = "Error condition failed";
      v28 = &v30;
      v27 = &v31;
      v26 = &v32;
      v13 = (const char **)v33;
LABEL_6:
      v35 = v11;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v8,
        (_DWORD)v12,
        v9,
        v10,
        (__int64)v13,
        (__int64)&v35,
        (__int64)v26,
        (__int64)&v34,
        (__int64)v27,
        (__int64)v28);
    }
  }
LABEL_31:
  if ( v29 && v6 )
    v6();
  if ( v5 )
    FreeLibrary(v5);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18008bf98  mov     [rsp-28h+arg_0], rbx
0x18008bf9d  push    rbp
0x18008bf9e  push    rsi
0x18008bf9f  push    rdi
0x18008bfa0  push    r14
0x18008bfa2  push    r15
0x18008bfa4  mov     rbp, rsp
0x18008bfa7  sub     rsp, 80h
0x18008bfae  mov     rsi, rcx
0x18008bfb1  mov     [rbp+var_30], 0
0x18008bfb9  lea     rcx, aNetapi32Dll; "netapi32.dll"
0x18008bfc0  mov     rdi, rdx
0x18008bfc3  call    cs:__imp_LoadLibraryW
0x18008bfc9  mov     r14, rax
0x18008bfcc  test    rax, rax
0x18008bfcf  jnz     loc_18008C079
0x18008bfd5  xor     r15d, r15d
0x18008bfd8  call    cs:__imp_GetLastError
0x18008bfde  mov     ebx, eax
0x18008bfe0  test    eax, eax
0x18008bfe2  jle     short loc_18008BFED
0x18008bfe4  movzx   ebx, ax
0x18008bfe7  or      ebx, 80070000h
0x18008bfed  mov     eax, cs:CallbackContext
0x18008bff3  cmp     eax, 2
0x18008bff6  jbe     loc_18008C3B1
0x18008bffc  lea     rax, aLoadlibraryNet; "LoadLibrary(netapi32.dll)"
0x18008c003  mov     dword ptr [rbp+arg_10], 397h
0x18008c00a  mov     [rbp+var_28], rax
0x18008c00e  lea     rdx, word_1801AD2E2
0x18008c015  lea     rax, aIsdeviceaadjoi; "IsDeviceAADJoined"
0x18008c01c  mov     [rbp+var_20], rax
0x18008c020  lea     rax, aOnecoreTermsrv_5; "onecore\\termsrv\\rdp\\win\\security\\r"...
0x18008c027  mov     [rbp+var_18], rax
0x18008c02b  lea     rax, aErrorCondition; "Error condition failed"
0x18008c032  mov     [rbp+var_10], rax
0x18008c036  lea     rax, [rbp+var_28]
0x18008c03a  mov     [rsp+80h+var_38], rax
0x18008c03f  lea     rax, [rbp+var_20]
0x18008c043  mov     [rsp+80h+var_40], rax
0x18008c048  lea     rax, [rbp+arg_10]
0x18008c04c  mov     [rsp+80h+var_48], rax
0x18008c051  lea     rax, [rbp+var_18]
0x18008c055  mov     [rsp+80h+var_50], rax
0x18008c05a  lea     rax, [rbp+arg_18]
0x18008c05e  mov     [rsp+80h+var_58], rax
0x18008c063  lea     rax, [rbp+var_10]
0x18008c067  mov     [rsp+80h+var_60], rax
0x18008c06c  mov     [rbp+arg_18], ebx
0x18008c06f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18008c074  jmp     loc_18008C3B1
0x18008c079  lea     rdx, aNetgetaadjoini; "NetGetAadJoinInformation"
0x18008c080  mov     rcx, r14; hModule
0x18008c083  call    cs:__imp_GetProcAddress
0x18008c089  lea     rdx, aNetfreeaadjoin; "NetFreeAadJoinInformation"
0x18008c090  mov     rcx, r14; hModule
0x18008c093  mov     rbx, rax
0x18008c096  call    cs:__imp_GetProcAddress
0x18008c09c  mov     r15, rax
0x18008c09f  test    rbx, rbx
0x18008c0a2  jz      loc_18008C377
0x18008c0a8  test    rax, rax
0x18008c0ab  jz      loc_18008C377
0x18008c0b1  lea     rdx, [rbp+var_30]
0x18008c0b5  xor     ecx, ecx
0x18008c0b7  mov     rax, rbx
0x18008c0ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c0bf  mov     ebx, eax
0x18008c0c1  test    eax, eax
0x18008c0c3  jns     short loc_18008C144
0x18008c0c5  mov     ecx, cs:CallbackContext
0x18008c0cb  cmp     ecx, 2
0x18008c0ce  jbe     loc_18008C3B1
0x18008c0d4  lea     rax, aNetgetaadjoini_1; "NetGetAadJoinInformation failed"
0x18008c0db  mov     dword ptr [rbp+arg_10], 3A9h
0x18008c0e2  mov     [rbp+var_10], rax
0x18008c0e6  lea     rdx, dword_1801AD26C
0x18008c0ed  lea     rax, aIsdeviceaadjoi; "IsDeviceAADJoined"
0x18008c0f4  mov     [rbp+var_18], rax
0x18008c0f8  lea     rax, aOnecoreTermsrv_5; "onecore\\termsrv\\rdp\\win\\security\\r"...
0x18008c0ff  mov     [rbp+var_20], rax
0x18008c103  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18008c10a  mov     [rbp+var_28], rax
0x18008c10e  lea     rax, [rbp+var_10]
0x18008c112  mov     [rsp+80h+var_38], rax
0x18008c117  lea     rax, [rbp+var_18]
0x18008c11b  mov     [rsp+80h+var_40], rax
0x18008c120  lea     rax, [rbp+arg_10]
0x18008c124  mov     [rsp+80h+var_48], rax
0x18008c129  lea     rax, [rbp+var_20]
0x18008c12d  mov     [rsp+80h+var_50], rax
0x18008c132  lea     rax, [rbp+arg_18]
0x18008c136  mov     [rsp+80h+var_58], rax
0x18008c13b  lea     rax, [rbp+var_28]
0x18008c13f  jmp     loc_18008C067
0x18008c144  mov     rcx, [rbp+var_30]
0x18008c148  test    rcx, rcx
0x18008c14b  jz      loc_18008C366
0x18008c151  cmp     dword ptr [rcx], 1
0x18008c154  jnz     loc_18008C366
0x18008c15a  mov     byte ptr [rsi], 1
0x18008c15d  test    rdi, rdi
0x18008c160  jz      loc_18008C3B1
0x18008c166  mov     rcx, [rcx+10h]; unsigned __int16 *
0x18008c16a  lea     r8, [rbp+arg_10]; unsigned __int64 *
0x18008c16e  mov     edx, 104h; unsigned __int64
0x18008c173  mov     [rbp+arg_10], 0
0x18008c17b  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18008c180  mov     ebx, eax
0x18008c182  test    eax, eax
0x18008c184  jns     short loc_18008C205
0x18008c186  mov     eax, cs:CallbackContext
0x18008c18c  cmp     eax, 2
0x18008c18f  jbe     loc_18008C3B1
0x18008c195  lea     rax, aStringcchlengt_5; "StringCchLengthW failed"
0x18008c19c  mov     dword ptr [rbp+arg_10], 3B5h
0x18008c1a3  mov     [rbp+var_10], rax
0x18008c1a7  lea     rdx, byte_1801AD21B
0x18008c1ae  lea     rax, aIsdeviceaadjoi; "IsDeviceAADJoined"
0x18008c1b5  mov     [rbp+var_18], rax
0x18008c1b9  lea     rax, aOnecoreTermsrv_5; "onecore\\termsrv\\rdp\\win\\security\\r"...
0x18008c1c0  mov     [rbp+var_20], rax
0x18008c1c4  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18008c1cb  mov     [rbp+var_28], rax
0x18008c1cf  lea     rax, [rbp+var_10]
0x18008c1d3  mov     [rsp+80h+var_38], rax
0x18008c1d8  lea     rax, [rbp+var_18]
0x18008c1dc  mov     [rsp+80h+var_40], rax
0x18008c1e1  lea     rax, [rbp+arg_10]
0x18008c1e5  mov     [rsp+80h+var_48], rax
0x18008c1ea  lea     rax, [rbp+var_20]
0x18008c1ee  mov     [rsp+80h+var_50], rax
0x18008c1f3  lea     rax, [rbp+arg_18]
0x18008c1f7  mov     [rsp+80h+var_58], rax
0x18008c1fc  lea     rax, [rbp+var_28]
0x18008c200  jmp     loc_18008C067
0x18008c205  mov     rbx, [rbp+arg_10]
0x18008c209  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18008c210  inc     rbx
0x18008c213  mov     eax, 2
0x18008c218  mul     rbx
0x18008c21b  cmovb   rax, rcx
0x18008c21f  mov     rcx, rax; Size
0x18008c222  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18008c227  mov     rsi, rax
0x18008c22a  test    rax, rax
0x18008c22d  jnz     loc_18008C2B7
0x18008c233  mov     eax, cs:CallbackContext
0x18008c239  mov     ebx, 8007000Eh
0x18008c23e  cmp     eax, 2
0x18008c241  jbe     loc_18008C3B1
0x18008c247  lea     rax, aPszdeviceidAll; "pszDeviceId allocation failed"
0x18008c24e  mov     dword ptr [rbp+arg_10], 3BAh
0x18008c255  mov     [rbp+var_10], rax
0x18008c259  lea     rdx, word_1801AD1CA
0x18008c260  lea     rax, aIsdeviceaadjoi; "IsDeviceAADJoined"
0x18008c267  mov     [rbp+var_18], rax
0x18008c26b  lea     rax, aOnecoreTermsrv_5; "onecore\\termsrv\\rdp\\win\\security\\r"...
0x18008c272  mov     [rbp+var_20], rax
0x18008c276  lea     rax, aErrorCondition; "Error condition failed"
0x18008c27d  mov     [rbp+var_28], rax
0x18008c281  lea     rax, [rbp+var_10]
0x18008c285  mov     [rsp+80h+var_38], rax
0x18008c28a  lea     rax, [rbp+var_18]
0x18008c28e  mov     [rsp+80h+var_40], rax
0x18008c293  lea     rax, [rbp+arg_10]
0x18008c297  mov     [rsp+80h+var_48], rax
0x18008c29c  lea     rax, [rbp+var_20]
0x18008c2a0  mov     [rsp+80h+var_50], rax
0x18008c2a5  lea     rax, [rbp+arg_18]
0x18008c2a9  mov     [rsp+80h+var_58], rax
0x18008c2ae  lea     rax, [rbp+var_28]
0x18008c2b2  jmp     loc_18008C067
0x18008c2b7  mov     r8, [rbp+var_30]
0x18008c2bb  mov     rdx, rbx; unsigned __int64
0x18008c2be  mov     rcx, rsi; unsigned __int16 *
0x18008c2c1  mov     r8, [r8+10h]; unsigned __int16 *
0x18008c2c5  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18008c2ca  mov     ebx, eax
0x18008c2cc  test    eax, eax
0x18008c2ce  jns     loc_18008C361
0x18008c2d4  mov     eax, cs:CallbackContext
0x18008c2da  cmp     eax, 2
0x18008c2dd  jbe     short loc_18008C357
0x18008c2df  lea     rax, aStringcchcopyw; "StringCchCopyW"
0x18008c2e6  mov     dword ptr [rbp+arg_10], 3BDh
0x18008c2ed  mov     [rbp+var_10], rax
0x18008c2f1  lea     rdx, byte_1801AD179
0x18008c2f8  lea     rax, aIsdeviceaadjoi; "IsDeviceAADJoined"
0x18008c2ff  mov     [rbp+arg_18], ebx
0x18008c302  mov     [rbp+var_18], rax
0x18008c306  lea     rax, aOnecoreTermsrv_5; "onecore\\termsrv\\rdp\\win\\security\\r"...
0x18008c30d  mov     [rbp+var_20], rax
0x18008c311  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18008c318  mov     [rbp+var_28], rax
0x18008c31c  lea     rax, [rbp+var_10]
0x18008c320  mov     [rsp+80h+var_38], rax
0x18008c325  lea     rax, [rbp+var_18]
0x18008c329  mov     [rsp+80h+var_40], rax
0x18008c32e  lea     rax, [rbp+arg_10]
0x18008c332  mov     [rsp+80h+var_48], rax
0x18008c337  lea     rax, [rbp+var_20]
0x18008c33b  mov     [rsp+80h+var_50], rax
0x18008c340  lea     rax, [rbp+arg_18]
0x18008c344  mov     [rsp+80h+var_58], rax
0x18008c349  lea     rax, [rbp+var_28]
0x18008c34d  mov     [rsp+80h+var_60], rax
0x18008c352  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18008c357  mov     rcx, rsi; Block
0x18008c35a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18008c35f  jmp     short loc_18008C3B1
0x18008c361  mov     [rdi], rsi
0x18008c364  jmp     short loc_18008C3B1
0x18008c366  mov     byte ptr [rsi], 0
0x18008c369  test    rdi, rdi
0x18008c36c  jz      short loc_18008C3B1
0x18008c36e  mov     qword ptr [rdi], 0
0x18008c375  jmp     short loc_18008C3B1
0x18008c377  mov     eax, cs:CallbackContext
0x18008c37d  cmp     eax, 4
0x18008c380  jbe     short loc_18008C3AC
0x18008c382  lea     rax, aNetgetaadjoini_0; "NetGetAadJoinInformation or NetFreeAadJ"...
0x18008c389  xor     r8d, r8d
0x18008c38c  mov     [rbp+arg_10], rax
0x18008c390  lea     rdx, byte_1801AD2BD
0x18008c397  lea     rax, [rbp+arg_10]
0x18008c39b  lea     rcx, CallbackContext
0x18008c3a2  mov     [rsp+80h+var_60], rax
0x18008c3a7  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18008c3ac  mov     byte ptr [rsi], 0
0x18008c3af  xor     ebx, ebx
0x18008c3b1  mov     rcx, [rbp+var_30]
0x18008c3b5  test    rcx, rcx
0x18008c3b8  jz      short loc_18008C3C7
0x18008c3ba  test    r15, r15
0x18008c3bd  jz      short loc_18008C3C7
0x18008c3bf  mov     rax, r15
0x18008c3c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008c3c7  test    r14, r14
0x18008c3ca  jz      short loc_18008C3D5
0x18008c3cc  mov     rcx, r14; hLibModule
0x18008c3cf  call    cs:__imp_FreeLibrary
0x18008c3d5  mov     eax, ebx
0x18008c3d7  mov     rbx, [rsp+80h+arg_0]
0x18008c3df  add     rsp, 80h
0x18008c3e6  pop     r15
0x18008c3e8  pop     r14
0x18008c3ea  pop     rdi
0x18008c3eb  pop     rsi
0x18008c3ec  pop     rbp
0x18008c3ed  retn
```
