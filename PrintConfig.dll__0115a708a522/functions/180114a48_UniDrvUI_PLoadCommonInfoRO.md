# UniDrvUI::PLoadCommonInfoRO

- ea: `0x180114a48`
- end: `0x180114e31`
- name: `UniDrvUI::PLoadCommonInfoRO`
- size: `1001`
- prototype: `_QWORD *__fastcall(void *, wchar_t *, unsigned int, _QWORD *, __int64 *)`
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180114024`

## callees

- `0x180003400`
- `0x180004558`
- `0x180107214`
- `0x180108e2c`
- `0x180114a48`
- `0x1801160c4`
- `0x18014ed04`
- `0x18014ed44`
- `0x18014ee44`
- `0x18014f5dc`
- `0x18014f63c`
- `0x180154838`
- `0x1801558d0`
- `0x180156ee4`
- `0x180157788`
- `0x180157924`
- `0x180157b0c`
- `0x1801588e4`
- `0x180158efc`
- `0x1801cb010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180114d27`
- `KERNEL32!GetLastError` at `0x180114d82`
- `KERNEL32!GetLastError` at `0x180114dc6`
- `KERNEL32!GetLastError` at `0x180114d27`
- `KERNEL32!GetLastError` at `0x180114d82`
- `KERNEL32!GetLastError` at `0x180114dc6`
- `KERNEL32!LocalAlloc` at `0x180114a9b`
- `KERNEL32!LocalAlloc` at `0x180114a9b`

## string_xrefs

- `0x180114a81`: `UniDrvUI::PLoadCommonInfoRO`
- `0x180114b24`: `UniDrvUI::PLoadCommonInfoRO`
- `0x180114b3c`: `UniDrvUI::PLoadCommonInfoRO`
- `0x180114b67`: `UniDrvUI::PLoadCommonInfoRO`
- `0x180114bc1`: `UniDrvUI::PLoadCommonInfoRO`
- `0x180114c39`: `UniDrvUI::PLoadCommonInfoRO`
- `0x180114ccf`: `UniDrvUI::PLoadCommonInfoRO`
- `0x180114de5`: `UniDrvUI::PLoadCommonInfoRO`
- `0x180114df8`: `UniDrvUI::PLoadCommonInfoRO`
- `0x180114b1d`: `The driver is using PrintConfig.dll.`
- `0x180114d3f`: `Cannot get OEM plugins info (hr: 0x%x).`
- `0x180114cfc`: `Get information about OEM plugins and load them.`
- `0x180114b35`: `Attempt to populate the cache change id.`
- `0x180114bba`: `Get the file directly from RemotePrintConfigData if this is a v4 connection.`
- `0x180114d9a`: `Cannot load OEM plugins (hr: 0x%x).`
- `0x180114d5e`: `Preloads the plugins and keeps the DLL loaded.`
- `0x180114b06`: `PrintConfig.dll`

## pseudocode

```c
__int64 *__fastcall UniDrvUI::PLoadCommonInfoRO(void *a1, wchar_t *a2, unsigned __int32 a3, __int64 *a4, __int64 *a5)
{
  __m128i *v9; // rbx
  wchar_t *v10; // rcx
  HLOCAL v11; // rax
  bool matched; // al
  unsigned int v13; // ebp
  __int64 v14; // rax
  __int64 v15; // rdx
  __int64 v16; // r9
  struct RemotePrintConfigData *v17; // rdi
  wchar_t *v18; // rax
  __int64 v19; // rcx
  __int64 inited; // rdi
  __int64 v21; // rsi
  __int64 v22; // rcx
  __int64 v23; // rcx
  _QWORD *v24; // rax
  signed int LastError; // eax
  unsigned __int16 *v26; // rdx
  __int64 v27; // rdx
  __int64 v28; // r8
  __int64 *result; // rax
  signed int v30; // eax
  struct RemotePrintConfigData *v31; // [rsp+30h] [rbp-268h] BYREF
  wchar_t pszSrc[264]; // [rsp+40h] [rbp-258h] BYREF

  DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(
    "UniDrvUI::PLoadCommonInfoRO",
    L"Loads basic information needed by the driver UI.");
  v9 = (__m128i *)LocalAlloc(0x40u, 0x98u);
  if ( !v9 )
    goto LABEL_42;
  v10 = a2;
  if ( !a2 )
    v10 = L"NULL";
  v11 = DuplicateString(v10);
  v9[1].m128i_i64[0] = (__int64)v11;
  if ( !v11 )
  {
LABEL_42:
    DriverUi::DriverUiTelemetry::WriteDbgTraceWarning("UniDrvUI::PLoadCommonInfoRO", L"Memory allocation failed.");
    goto LABEL_43;
  }
  v9[2].m128i_i64[0] = *a4;
  *a4 = 0;
  v9[1].m128i_i32[2] = a3;
  v9[2].m128i_i64[1] = 0;
  memset_0((char *)v9[4].m128i_i64 + 4, 0, 0x4Eu);
  matched = DoesFullPathMatchFile(*(const unsigned __int16 **)(v9[2].m128i_i64[0] + 40), L"PrintConfig.dll");
  v13 = matched;
  if ( matched )
  {
    DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(
      "UniDrvUI::PLoadCommonInfoRO",
      L"The driver is using PrintConfig.dll.");
    v9[1].m128i_i32[2] |= 0x100000u;
    DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(
      "UniDrvUI::PLoadCommonInfoRO",
      L"Attempt to populate the cache change id.");
    if ( (int)GetV4PrinterCacheChangeID(a2, a1, (BYTE *)&v9[4]) >= 0 )
      v9[1].m128i_i32[2] |= 0x200000u;
    DriverUi::DriverUiTelemetry::WriteDbgTraceInfo("UniDrvUI::PLoadCommonInfoRO", L"Retrieve the printer driver ID.");
    if ( (int)GetPrinterDriverIDAsString(a1, &v9[4].m128i_i16[2]) < 0 )
      CopyStringW(&v9[4].m128i_i8[4], L"****  PrinterDriverID Not Found  *****", 39);
  }
  if ( (a3 & 0x8000) != 0 && (v14 = v9[2].m128i_i64[0]) != 0 && *(_QWORD *)(v14 + 40) && v13 )
  {
    DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(
      "UniDrvUI::PLoadCommonInfoRO",
      L"Get the file directly from RemotePrintConfigData if this is a v4 connection.");
    v31 = 0;
    if ( (int)RemotePrintConfigData::CreateRemotePrintConfigData(a1, &v31) >= 0 )
    {
      v17 = v31;
      LOBYTE(v16) = 1;
      v18 = (wchar_t *)(*(__int64 (__fastcall **)(struct RemotePrintConfigData *, __int64, _QWORD, __int64))(*(_QWORD *)v31 + 8LL))(
                         v31,
                         2,
                         0,
                         v16);
      v9[2].m128i_i64[1] = LoadRawBinaryData(v18, v13);
      if ( v17 )
        (*(void (__fastcall **)(struct RemotePrintConfigData *, __int64))(*(_QWORD *)v17 + 32LL))(v17, 1);
    }
  }
  else
  {
    DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(
      "UniDrvUI::PLoadCommonInfoRO",
      L"Go through the GetFilenameByRole because we don't know if this is a connection or a local printer.");
    memset_0(pszSrc, 0, 0x208u);
    if ( (int)GetFilenameByRole(a1, 2u, pszSrc, 0x104u) >= 0 )
      v9[2].m128i_i64[1] = LoadRawBinaryData(pszSrc, v13);
  }
  v19 = v9[2].m128i_i64[1];
  if ( v19 )
  {
    inited = InitBinaryData(v19, v15, 0);
    if ( inited && *(_DWORD *)(inited + 56) )
      v21 = inited + *(unsigned int *)(inited + 56);
    else
      v21 = 0;
    if ( v9[2].m128i_i64[1] && inited && v21 )
    {
      DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(
        "UniDrvUI::PLoadCommonInfoRO",
        L"Calculate the maximum size needed to store JT expansion block.");
      v9[3].m128i_i32[2] = cbCalcJTExpSize(v22, v21, v9[2].m128i_i64[0], (a3 >> 13) & 1);
      DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(
        "UniDrvUI::PLoadCommonInfoRO",
        L"Get information about OEM plugins and load them.");
      v24 = (_QWORD *)PGetOemPluginInfo(v23, *(const wchar_t **)(v9[2].m128i_i64[0] + 40), v9[2].m128i_i64[0]);
      v9[3].m128i_i64[0] = (__int64)v24;
      if ( v24 )
      {
        *v24 = v9;
        DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(
          "UniDrvUI::PLoadCommonInfoRO",
          L"Preloads the plugins and keeps the DLL loaded.");
        if ( (unsigned int)BLoadOEMPluginModulesInternal(0, v9[3].m128i_i64[0], 0) )
        {
          v9->m128i_i32[0] = 16;
          v9->m128i_i64[1] = (__int64)&UniDrvUI::OemUIHelperFuncs;
          result = (__int64 *)v9;
          v9[3].m128i_i32[3] = 1;
          *a5 = inited;
          return result;
        }
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        v26 = L"Cannot load OEM plugins (hr: 0x%x).";
      }
      else
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        v26 = L"Cannot get OEM plugins info (hr: 0x%x).";
      }
      DriverUi::DriverUiTelemetry::WriteDbgTraceWarning("UniDrvUI::PLoadCommonInfoRO", v26, (unsigned int)LastError);
      goto LABEL_32;
    }
  }
  else
  {
    inited = 0;
  }
  v30 = GetLastError();
  if ( v30 > 0 )
    v30 = (unsigned __int16)v30 | 0x80070000;
  DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(
    "UniDrvUI::PLoadCommonInfoRO",
    L"Cannot load printer description data (hr: 0x%x).",
    (unsigned int)v30);
LABEL_32:
  FreeBinaryData(inited, v27, v28);
LABEL_43:
  PSUI::VFreeCommonInfoRO(v9);
  return 0;
}

```

## disassembly

```asm
0x180114a48  push    rbx
0x180114a4a  push    rbp
0x180114a4b  push    rsi
0x180114a4c  push    rdi
0x180114a4d  push    r12
0x180114a4f  push    r14
0x180114a51  push    r15
0x180114a53  sub     rsp, 260h
0x180114a5a  mov     rax, cs:__security_cookie
0x180114a61  xor     rax, rsp
0x180114a64  mov     [rsp+298h+var_48], rax
0x180114a6c  mov     r12, [rsp+298h+arg_20]
0x180114a74  mov     rdi, rdx
0x180114a77  mov     r14, rcx
0x180114a7a  lea     rdx, aLoadsBasicInfo; "Loads basic information needed by the d"...
0x180114a81  lea     rcx, aUnidrvuiPloadc; "UniDrvUI::PLoadCommonInfoRO"
0x180114a88  mov     rsi, r9
0x180114a8b  mov     r15d, r8d
0x180114a8e  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180114a93  mov     edx, 98h; uBytes
0x180114a98  lea     ecx, [rdx-58h]; uFlags
0x180114a9b  call    cs:__imp_LocalAlloc
0x180114aa2  nop     dword ptr [rax+rax+00h]
0x180114aa7  mov     rbx, rax
0x180114aaa  test    rax, rax
0x180114aad  jz      loc_180114DF1
0x180114ab3  lea     rax, aNull_0; "NULL"
0x180114aba  test    rdi, rdi
0x180114abd  mov     rcx, rdi
0x180114ac0  cmovz   rcx, rax; Src
0x180114ac4  call    DuplicateString
0x180114ac9  mov     [rbx+10h], rax
0x180114acd  test    rax, rax
0x180114ad0  jz      loc_180114DF1
0x180114ad6  mov     rax, [rsi]
0x180114ad9  xor     edx, edx; Val
0x180114adb  mov     [rbx+20h], rax
0x180114adf  mov     qword ptr [rsi], 0
0x180114ae6  lea     rsi, [rbx+44h]
0x180114aea  mov     rcx, rsi; void *
0x180114aed  mov     [rbx+18h], r15d
0x180114af1  lea     r8d, [rdx+4Eh]; Size
0x180114af5  mov     qword ptr [rbx+28h], 0
0x180114afd  call    memset_0
0x180114b02  mov     rcx, [rbx+20h]
0x180114b06  lea     rdx, aPrintconfigDll_1; "PrintConfig.dll"
0x180114b0d  mov     rcx, [rcx+28h]; unsigned __int16 *
0x180114b11  call    ?DoesFullPathMatchFile@@YA_NPEBG0@Z; DoesFullPathMatchFile(ushort const *,ushort const *)
0x180114b16  movzx   ebp, al
0x180114b19  test    al, al
0x180114b1b  jz      short loc_180114B97
0x180114b1d  lea     rdx, aTheDriverIsUsi; "The driver is using PrintConfig.dll."
0x180114b24  lea     rcx, aUnidrvuiPloadc; "UniDrvUI::PLoadCommonInfoRO"
0x180114b2b  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180114b30  bts     dword ptr [rbx+18h], 14h
0x180114b35  lea     rdx, aAttemptToPopul; "Attempt to populate the cache change id"...
0x180114b3c  lea     rcx, aUnidrvuiPloadc; "UniDrvUI::PLoadCommonInfoRO"
0x180114b43  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180114b48  lea     r8, [rbx+40h]
0x180114b4c  mov     rdx, r14
0x180114b4f  mov     rcx, rdi
0x180114b52  call    GetV4PrinterCacheChangeID
0x180114b57  test    eax, eax
0x180114b59  js      short loc_180114B60
0x180114b5b  bts     dword ptr [rbx+18h], 15h
0x180114b60  lea     rdx, aRetrieveThePri; "Retrieve the printer driver ID."
0x180114b67  lea     rcx, aUnidrvuiPloadc; "UniDrvUI::PLoadCommonInfoRO"
0x180114b6e  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180114b73  mov     rdx, rsi
0x180114b76  mov     rcx, r14
0x180114b79  call    GetPrinterDriverIDAsString
0x180114b7e  test    eax, eax
0x180114b80  jns     short loc_180114B97
0x180114b82  mov     r8d, 27h ; '''
0x180114b88  lea     rdx, aPrinterdriveri_1; "****  PrinterDriverID Not Found  *****"
0x180114b8f  mov     rcx, rsi
0x180114b92  call    CopyStringW
0x180114b97  bt      r15d, 0Fh
0x180114b9c  jnb     loc_180114C32
0x180114ba2  mov     rax, [rbx+20h]
0x180114ba6  test    rax, rax
0x180114ba9  jz      loc_180114C32
0x180114baf  cmp     qword ptr [rax+28h], 0
0x180114bb4  jz      short loc_180114C32
0x180114bb6  test    ebp, ebp
0x180114bb8  jz      short loc_180114C32
0x180114bba  lea     rdx, aGetTheFileDire; "Get the file directly from RemotePrintC"...
0x180114bc1  lea     rcx, aUnidrvuiPloadc; "UniDrvUI::PLoadCommonInfoRO"
0x180114bc8  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180114bcd  lea     rdx, [rsp+298h+var_268]; struct RemotePrintConfigData **
0x180114bd2  mov     [rsp+298h+var_268], 0
0x180114bdb  mov     rcx, r14; void *
0x180114bde  call    ?CreateRemotePrintConfigData@RemotePrintConfigData@@SAJPEAXPEAPEAV1@@Z; RemotePrintConfigData::CreateRemotePrintConfigData(void *,RemotePrintConfigData * *)
0x180114be3  test    eax, eax
0x180114be5  js      loc_180114C83
0x180114beb  mov     rdi, [rsp+298h+var_268]
0x180114bf0  xor     r8d, r8d
0x180114bf3  mov     r9b, 1
0x180114bf6  mov     rcx, rdi
0x180114bf9  mov     rax, [rdi]
0x180114bfc  lea     edx, [r8+2]
0x180114c00  mov     rax, [rax+8]
0x180114c04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180114c09  mov     rcx, rax; pszSrc
0x180114c0c  mov     edx, ebp
0x180114c0e  call    LoadRawBinaryData
0x180114c13  mov     [rbx+28h], rax
0x180114c17  test    rdi, rdi
0x180114c1a  jz      short loc_180114C83
0x180114c1c  mov     rax, [rdi]
0x180114c1f  mov     edx, 1
0x180114c24  mov     rcx, rdi
0x180114c27  mov     rax, [rax+20h]
0x180114c2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180114c30  jmp     short loc_180114C83
0x180114c32  lea     rdx, aGoThroughTheGe; "Go through the GetFilenameByRole becaus"...
0x180114c39  lea     rcx, aUnidrvuiPloadc; "UniDrvUI::PLoadCommonInfoRO"
0x180114c40  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180114c45  xor     edx, edx; Val
0x180114c47  lea     rcx, [rsp+298h+pszSrc]; void *
0x180114c4c  mov     r8d, 208h; Size
0x180114c52  call    memset_0
0x180114c57  mov     r9d, 104h
0x180114c5d  lea     r8, [rsp+298h+pszSrc]
0x180114c62  mov     edx, 2
0x180114c67  mov     rcx, r14
0x180114c6a  call    GetFilenameByRole
0x180114c6f  test    eax, eax
0x180114c71  js      short loc_180114C83
0x180114c73  mov     edx, ebp
0x180114c75  lea     rcx, [rsp+298h+pszSrc]; pszSrc
0x180114c7a  call    LoadRawBinaryData
0x180114c7f  mov     [rbx+28h], rax
0x180114c83  mov     rcx, [rbx+28h]
0x180114c87  test    rcx, rcx
0x180114c8a  jz      loc_180114DC4
0x180114c90  xor     r8d, r8d
0x180114c93  call    InitBinaryData
0x180114c98  mov     rdi, rax
0x180114c9b  mov     rax, [rbx+28h]
0x180114c9f  test    rdi, rdi
0x180114ca2  jz      short loc_180114CB2
0x180114ca4  cmp     dword ptr [rdi+38h], 0
0x180114ca8  jz      short loc_180114CB2
0x180114caa  mov     esi, [rdi+38h]
0x180114cad  add     rsi, rdi
0x180114cb0  jmp     short loc_180114CB4
0x180114cb2  xor     esi, esi
0x180114cb4  test    rax, rax
0x180114cb7  jz      loc_180114DC6
0x180114cbd  test    rdi, rdi
0x180114cc0  jz      loc_180114DC6
0x180114cc6  test    rsi, rsi
0x180114cc9  jz      loc_180114DC6
0x180114ccf  lea     rbp, aUnidrvuiPloadc; "UniDrvUI::PLoadCommonInfoRO"
0x180114cd6  mov     rcx, rbp; char *
0x180114cd9  lea     rdx, aCalculateTheMa; "Calculate the maximum size needed to st"...
0x180114ce0  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180114ce5  mov     r8, [rbx+20h]
0x180114ce9  mov     rdx, rsi
0x180114cec  shr     r15d, 0Dh
0x180114cf0  and     r15d, 1
0x180114cf4  mov     r9d, r15d
0x180114cf7  call    cbCalcJTExpSize
0x180114cfc  lea     rdx, aGetInformation; "Get information about OEM plugins and l"...
0x180114d03  mov     [rbx+38h], eax
0x180114d06  mov     rcx, rbp; char *
0x180114d09  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180114d0e  mov     rdx, [rbx+20h]
0x180114d12  mov     r8, rdx
0x180114d15  mov     rdx, [rdx+28h]
0x180114d19  call    PGetOemPluginInfo
0x180114d1e  mov     [rbx+30h], rax
0x180114d22  test    rax, rax
0x180114d25  jnz     short loc_180114D5E
0x180114d27  call    cs:__imp_GetLastError
0x180114d2e  nop     dword ptr [rax+rax+00h]
0x180114d33  test    eax, eax
0x180114d35  jle     short loc_180114D3F
0x180114d37  movzx   eax, ax
0x180114d3a  or      eax, 80070000h
0x180114d3f  lea     rdx, aCannotGetOemPl_0; "Cannot get OEM plugins info (hr: 0x%x)."
0x180114d46  mov     rcx, rbp; char *
0x180114d49  mov     r8d, eax
0x180114d4c  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180114d51  mov     rcx, rdi
0x180114d54  call    FreeBinaryData
0x180114d59  jmp     loc_180114E04
0x180114d5e  lea     rdx, aPreloadsThePlu; "Preloads the plugins and keeps the DLL "...
0x180114d65  mov     [rax], rbx
0x180114d68  mov     rcx, rbp; char *
0x180114d6b  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180114d70  mov     rdx, [rbx+30h]
0x180114d74  xor     r8d, r8d
0x180114d77  xor     ecx, ecx; this
0x180114d79  call    BLoadOEMPluginModulesInternal
0x180114d7e  test    eax, eax
0x180114d80  jnz     short loc_180114DA3
0x180114d82  call    cs:__imp_GetLastError
0x180114d89  nop     dword ptr [rax+rax+00h]
0x180114d8e  test    eax, eax
0x180114d90  jle     short loc_180114D9A
0x180114d92  movzx   eax, ax
0x180114d95  or      eax, 80070000h
0x180114d9a  lea     rdx, aCannotLoadOemP; "Cannot load OEM plugins (hr: 0x%x)."
0x180114da1  jmp     short loc_180114D46
0x180114da3  lea     rax, ?OemUIHelperFuncs@UniDrvUI@@3U_OEMUIPROCS@@B; _OEMUIPROCS const UniDrvUI::OemUIHelperFuncs
0x180114daa  mov     dword ptr [rbx], 10h
0x180114db0  mov     [rbx+8], rax
0x180114db4  mov     rax, rbx
0x180114db7  mov     dword ptr [rbx+3Ch], 1
0x180114dbe  mov     [r12], rdi
0x180114dc2  jmp     short loc_180114E0E
0x180114dc4  xor     edi, edi
0x180114dc6  call    cs:__imp_GetLastError
0x180114dcd  nop     dword ptr [rax+rax+00h]
0x180114dd2  test    eax, eax
0x180114dd4  jle     short loc_180114DDE
0x180114dd6  movzx   eax, ax
0x180114dd9  or      eax, 80070000h
0x180114dde  lea     rdx, aCannotLoadPrin_1; "Cannot load printer description data (h"...
0x180114de5  lea     rcx, aUnidrvuiPloadc; "UniDrvUI::PLoadCommonInfoRO"
0x180114dec  jmp     loc_180114D49
0x180114df1  lea     rdx, aMemoryAllocati_1; "Memory allocation failed."
0x180114df8  lea     rcx, aUnidrvuiPloadc; "UniDrvUI::PLoadCommonInfoRO"
0x180114dff  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180114e04  mov     rcx, rbx; hMem
0x180114e07  call    PSUI__VFreeCommonInfoRO
0x180114e0c  xor     eax, eax
0x180114e0e  mov     rcx, [rsp+298h+var_48]
0x180114e16  xor     rcx, rsp; StackCookie
0x180114e19  call    __security_check_cookie
0x180114e1e  add     rsp, 260h
0x180114e25  pop     r15
0x180114e27  pop     r14
0x180114e29  pop     r12
0x180114e2b  pop     rdi
0x180114e2c  pop     rsi
0x180114e2d  pop     rbp
0x180114e2e  pop     rbx
0x180114e2f  retn
```
