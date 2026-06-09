# PSUI::PLoadCommonInfoRO

- ea: `0x18013c7e8`
- end: `0x18013cbd1`
- name: `PSUI::PLoadCommonInfoRO`
- size: `1001`
- prototype: `__m128i *__fastcall(void *, wchar_t *, unsigned __int32, __int64 *, __int64 *)`
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18013bda0`

## callees

- `0x180003400`
- `0x180004558`
- `0x180107214`
- `0x180108e2c`
- `0x1801160c4`
- `0x18013c7e8`
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

- `KERNEL32!GetLastError` at `0x18013cac7`
- `KERNEL32!GetLastError` at `0x18013cb22`
- `KERNEL32!GetLastError` at `0x18013cb66`
- `KERNEL32!GetLastError` at `0x18013cac7`
- `KERNEL32!GetLastError` at `0x18013cb22`
- `KERNEL32!GetLastError` at `0x18013cb66`
- `KERNEL32!LocalAlloc` at `0x18013c83b`
- `KERNEL32!LocalAlloc` at `0x18013c83b`

## string_xrefs

- `0x18013c8bd`: `The driver is using PrintConfig.dll.`
- `0x18013cadf`: `Cannot get OEM plugins info (hr: 0x%x).`
- `0x18013ca9c`: `Get information about OEM plugins and load them.`
- `0x18013c8d5`: `Attempt to populate the cache change id.`
- `0x18013c95a`: `Get the file directly from RemotePrintConfigData if this is a v4 connection.`
- `0x18013cb3a`: `Cannot load OEM plugins (hr: 0x%x).`
- `0x18013cafe`: `Preloads the plugins and keeps the DLL loaded.`
- `0x18013c821`: `PSUI::PLoadCommonInfoRO`
- `0x18013c8c4`: `PSUI::PLoadCommonInfoRO`
- `0x18013c8dc`: `PSUI::PLoadCommonInfoRO`
- `0x18013c907`: `PSUI::PLoadCommonInfoRO`
- `0x18013c961`: `PSUI::PLoadCommonInfoRO`
- `0x18013c9d9`: `PSUI::PLoadCommonInfoRO`
- `0x18013ca6f`: `PSUI::PLoadCommonInfoRO`
- `0x18013cb85`: `PSUI::PLoadCommonInfoRO`
- `0x18013cb98`: `PSUI::PLoadCommonInfoRO`
- `0x18013c8a6`: `PrintConfig.dll`

## pseudocode

```c
__m128i *__fastcall PSUI::PLoadCommonInfoRO(void *a1, wchar_t *a2, unsigned __int32 a3, __int64 *a4, __int64 *a5)
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
  __m128i *result; // rax
  signed int v30; // eax
  struct RemotePrintConfigData *v31; // [rsp+30h] [rbp-268h] BYREF
  wchar_t pszSrc[264]; // [rsp+40h] [rbp-258h] BYREF

  DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(
    "PSUI::PLoadCommonInfoRO",
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
    DriverUi::DriverUiTelemetry::WriteDbgTraceWarning("PSUI::PLoadCommonInfoRO", L"Memory allocation failed.");
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
    DriverUi::DriverUiTelemetry::WriteDbgTraceInfo("PSUI::PLoadCommonInfoRO", L"The driver is using PrintConfig.dll.");
    v9[1].m128i_i32[2] |= 0x100000u;
    DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(
      "PSUI::PLoadCommonInfoRO",
      L"Attempt to populate the cache change id.");
    if ( (int)GetV4PrinterCacheChangeID(a2, a1, (BYTE *)&v9[4]) >= 0 )
      v9[1].m128i_i32[2] |= 0x200000u;
    DriverUi::DriverUiTelemetry::WriteDbgTraceInfo("PSUI::PLoadCommonInfoRO", L"Retrieve the printer driver ID.");
    if ( (int)GetPrinterDriverIDAsString(a1, &v9[4].m128i_i16[2]) < 0 )
      CopyStringW(&v9[4].m128i_i8[4], L"****  PrinterDriverID Not Found  *****", 39);
  }
  if ( (a3 & 0x8000) != 0 && (v14 = v9[2].m128i_i64[0]) != 0 && *(_QWORD *)(v14 + 40) && v13 )
  {
    DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(
      "PSUI::PLoadCommonInfoRO",
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
      "PSUI::PLoadCommonInfoRO",
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
        "PSUI::PLoadCommonInfoRO",
        L"Calculate the maximum size needed to store JT expansion block.");
      v9[3].m128i_i32[2] = cbCalcJTExpSize(v22, v21, v9[2].m128i_i64[0], (a3 >> 13) & 1);
      DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(
        "PSUI::PLoadCommonInfoRO",
        L"Get information about OEM plugins and load them.");
      v24 = (_QWORD *)PGetOemPluginInfo(v23, *(const wchar_t **)(v9[2].m128i_i64[0] + 40), v9[2].m128i_i64[0]);
      v9[3].m128i_i64[0] = (__int64)v24;
      if ( v24 )
      {
        *v24 = v9;
        DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(
          "PSUI::PLoadCommonInfoRO",
          L"Preloads the plugins and keeps the DLL loaded.");
        if ( (unsigned int)BLoadOEMPluginModulesInternal(0, v9[3].m128i_i64[0], 0) )
        {
          v9->m128i_i32[0] = 16;
          v9->m128i_i64[1] = (__int64)&PSUI::OemUIHelperFuncs;
          result = v9;
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
      DriverUi::DriverUiTelemetry::WriteDbgTraceWarning("PSUI::PLoadCommonInfoRO", v26, (unsigned int)LastError);
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
    "PSUI::PLoadCommonInfoRO",
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
0x18013c7e8  push    rbx
0x18013c7ea  push    rbp
0x18013c7eb  push    rsi
0x18013c7ec  push    rdi
0x18013c7ed  push    r12
0x18013c7ef  push    r14
0x18013c7f1  push    r15
0x18013c7f3  sub     rsp, 260h
0x18013c7fa  mov     rax, cs:__security_cookie
0x18013c801  xor     rax, rsp
0x18013c804  mov     [rsp+298h+var_48], rax
0x18013c80c  mov     r12, [rsp+298h+arg_20]
0x18013c814  mov     rdi, rdx
0x18013c817  mov     r14, rcx
0x18013c81a  lea     rdx, aLoadsBasicInfo; "Loads basic information needed by the d"...
0x18013c821  lea     rcx, aPsuiPloadcommo_0; "PSUI::PLoadCommonInfoRO"
0x18013c828  mov     rsi, r9
0x18013c82b  mov     r15d, r8d
0x18013c82e  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18013c833  mov     edx, 98h; uBytes
0x18013c838  lea     ecx, [rdx-58h]; uFlags
0x18013c83b  call    cs:__imp_LocalAlloc
0x18013c842  nop     dword ptr [rax+rax+00h]
0x18013c847  mov     rbx, rax
0x18013c84a  test    rax, rax
0x18013c84d  jz      loc_18013CB91
0x18013c853  lea     rax, aNull_0; "NULL"
0x18013c85a  test    rdi, rdi
0x18013c85d  mov     rcx, rdi
0x18013c860  cmovz   rcx, rax; Src
0x18013c864  call    DuplicateString
0x18013c869  mov     [rbx+10h], rax
0x18013c86d  test    rax, rax
0x18013c870  jz      loc_18013CB91
0x18013c876  mov     rax, [rsi]
0x18013c879  xor     edx, edx; Val
0x18013c87b  mov     [rbx+20h], rax
0x18013c87f  mov     qword ptr [rsi], 0
0x18013c886  lea     rsi, [rbx+44h]
0x18013c88a  mov     rcx, rsi; void *
0x18013c88d  mov     [rbx+18h], r15d
0x18013c891  lea     r8d, [rdx+4Eh]; Size
0x18013c895  mov     qword ptr [rbx+28h], 0
0x18013c89d  call    memset_0
0x18013c8a2  mov     rcx, [rbx+20h]
0x18013c8a6  lea     rdx, aPrintconfigDll_1; "PrintConfig.dll"
0x18013c8ad  mov     rcx, [rcx+28h]; unsigned __int16 *
0x18013c8b1  call    ?DoesFullPathMatchFile@@YA_NPEBG0@Z; DoesFullPathMatchFile(ushort const *,ushort const *)
0x18013c8b6  movzx   ebp, al
0x18013c8b9  test    al, al
0x18013c8bb  jz      short loc_18013C937
0x18013c8bd  lea     rdx, aTheDriverIsUsi; "The driver is using PrintConfig.dll."
0x18013c8c4  lea     rcx, aPsuiPloadcommo_0; "PSUI::PLoadCommonInfoRO"
0x18013c8cb  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18013c8d0  bts     dword ptr [rbx+18h], 14h
0x18013c8d5  lea     rdx, aAttemptToPopul; "Attempt to populate the cache change id"...
0x18013c8dc  lea     rcx, aPsuiPloadcommo_0; "PSUI::PLoadCommonInfoRO"
0x18013c8e3  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18013c8e8  lea     r8, [rbx+40h]
0x18013c8ec  mov     rdx, r14
0x18013c8ef  mov     rcx, rdi
0x18013c8f2  call    GetV4PrinterCacheChangeID
0x18013c8f7  test    eax, eax
0x18013c8f9  js      short loc_18013C900
0x18013c8fb  bts     dword ptr [rbx+18h], 15h
0x18013c900  lea     rdx, aRetrieveThePri; "Retrieve the printer driver ID."
0x18013c907  lea     rcx, aPsuiPloadcommo_0; "PSUI::PLoadCommonInfoRO"
0x18013c90e  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18013c913  mov     rdx, rsi
0x18013c916  mov     rcx, r14
0x18013c919  call    GetPrinterDriverIDAsString
0x18013c91e  test    eax, eax
0x18013c920  jns     short loc_18013C937
0x18013c922  mov     r8d, 27h ; '''
0x18013c928  lea     rdx, aPrinterdriveri_2; "****  PrinterDriverID Not Found  *****"
0x18013c92f  mov     rcx, rsi
0x18013c932  call    CopyStringW
0x18013c937  bt      r15d, 0Fh
0x18013c93c  jnb     loc_18013C9D2
0x18013c942  mov     rax, [rbx+20h]
0x18013c946  test    rax, rax
0x18013c949  jz      loc_18013C9D2
0x18013c94f  cmp     qword ptr [rax+28h], 0
0x18013c954  jz      short loc_18013C9D2
0x18013c956  test    ebp, ebp
0x18013c958  jz      short loc_18013C9D2
0x18013c95a  lea     rdx, aGetTheFileDire; "Get the file directly from RemotePrintC"...
0x18013c961  lea     rcx, aPsuiPloadcommo_0; "PSUI::PLoadCommonInfoRO"
0x18013c968  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18013c96d  lea     rdx, [rsp+298h+var_268]; struct RemotePrintConfigData **
0x18013c972  mov     [rsp+298h+var_268], 0
0x18013c97b  mov     rcx, r14; void *
0x18013c97e  call    ?CreateRemotePrintConfigData@RemotePrintConfigData@@SAJPEAXPEAPEAV1@@Z; RemotePrintConfigData::CreateRemotePrintConfigData(void *,RemotePrintConfigData * *)
0x18013c983  test    eax, eax
0x18013c985  js      loc_18013CA23
0x18013c98b  mov     rdi, [rsp+298h+var_268]
0x18013c990  xor     r8d, r8d
0x18013c993  mov     r9b, 1
0x18013c996  mov     rcx, rdi
0x18013c999  mov     rax, [rdi]
0x18013c99c  lea     edx, [r8+2]
0x18013c9a0  mov     rax, [rax+8]
0x18013c9a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013c9a9  mov     rcx, rax; pszSrc
0x18013c9ac  mov     edx, ebp
0x18013c9ae  call    LoadRawBinaryData
0x18013c9b3  mov     [rbx+28h], rax
0x18013c9b7  test    rdi, rdi
0x18013c9ba  jz      short loc_18013CA23
0x18013c9bc  mov     rax, [rdi]
0x18013c9bf  mov     edx, 1
0x18013c9c4  mov     rcx, rdi
0x18013c9c7  mov     rax, [rax+20h]
0x18013c9cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013c9d0  jmp     short loc_18013CA23
0x18013c9d2  lea     rdx, aGoThroughTheGe; "Go through the GetFilenameByRole becaus"...
0x18013c9d9  lea     rcx, aPsuiPloadcommo_0; "PSUI::PLoadCommonInfoRO"
0x18013c9e0  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18013c9e5  xor     edx, edx; Val
0x18013c9e7  lea     rcx, [rsp+298h+pszSrc]; void *
0x18013c9ec  mov     r8d, 208h; Size
0x18013c9f2  call    memset_0
0x18013c9f7  mov     r9d, 104h
0x18013c9fd  lea     r8, [rsp+298h+pszSrc]
0x18013ca02  mov     edx, 2
0x18013ca07  mov     rcx, r14
0x18013ca0a  call    GetFilenameByRole
0x18013ca0f  test    eax, eax
0x18013ca11  js      short loc_18013CA23
0x18013ca13  mov     edx, ebp
0x18013ca15  lea     rcx, [rsp+298h+pszSrc]; pszSrc
0x18013ca1a  call    LoadRawBinaryData
0x18013ca1f  mov     [rbx+28h], rax
0x18013ca23  mov     rcx, [rbx+28h]
0x18013ca27  test    rcx, rcx
0x18013ca2a  jz      loc_18013CB64
0x18013ca30  xor     r8d, r8d
0x18013ca33  call    InitBinaryData
0x18013ca38  mov     rdi, rax
0x18013ca3b  mov     rax, [rbx+28h]
0x18013ca3f  test    rdi, rdi
0x18013ca42  jz      short loc_18013CA52
0x18013ca44  cmp     dword ptr [rdi+38h], 0
0x18013ca48  jz      short loc_18013CA52
0x18013ca4a  mov     esi, [rdi+38h]
0x18013ca4d  add     rsi, rdi
0x18013ca50  jmp     short loc_18013CA54
0x18013ca52  xor     esi, esi
0x18013ca54  test    rax, rax
0x18013ca57  jz      loc_18013CB66
0x18013ca5d  test    rdi, rdi
0x18013ca60  jz      loc_18013CB66
0x18013ca66  test    rsi, rsi
0x18013ca69  jz      loc_18013CB66
0x18013ca6f  lea     rbp, aPsuiPloadcommo_0; "PSUI::PLoadCommonInfoRO"
0x18013ca76  mov     rcx, rbp; char *
0x18013ca79  lea     rdx, aCalculateTheMa; "Calculate the maximum size needed to st"...
0x18013ca80  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18013ca85  mov     r8, [rbx+20h]
0x18013ca89  mov     rdx, rsi
0x18013ca8c  shr     r15d, 0Dh
0x18013ca90  and     r15d, 1
0x18013ca94  mov     r9d, r15d
0x18013ca97  call    cbCalcJTExpSize
0x18013ca9c  lea     rdx, aGetInformation; "Get information about OEM plugins and l"...
0x18013caa3  mov     [rbx+38h], eax
0x18013caa6  mov     rcx, rbp; char *
0x18013caa9  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18013caae  mov     rdx, [rbx+20h]
0x18013cab2  mov     r8, rdx
0x18013cab5  mov     rdx, [rdx+28h]
0x18013cab9  call    PGetOemPluginInfo
0x18013cabe  mov     [rbx+30h], rax
0x18013cac2  test    rax, rax
0x18013cac5  jnz     short loc_18013CAFE
0x18013cac7  call    cs:__imp_GetLastError
0x18013cace  nop     dword ptr [rax+rax+00h]
0x18013cad3  test    eax, eax
0x18013cad5  jle     short loc_18013CADF
0x18013cad7  movzx   eax, ax
0x18013cada  or      eax, 80070000h
0x18013cadf  lea     rdx, aCannotGetOemPl_0; "Cannot get OEM plugins info (hr: 0x%x)."
0x18013cae6  mov     rcx, rbp; char *
0x18013cae9  mov     r8d, eax
0x18013caec  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18013caf1  mov     rcx, rdi
0x18013caf4  call    FreeBinaryData
0x18013caf9  jmp     loc_18013CBA4
0x18013cafe  lea     rdx, aPreloadsThePlu; "Preloads the plugins and keeps the DLL "...
0x18013cb05  mov     [rax], rbx
0x18013cb08  mov     rcx, rbp; char *
0x18013cb0b  call    ?WriteDbgTraceInfo@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18013cb10  mov     rdx, [rbx+30h]
0x18013cb14  xor     r8d, r8d
0x18013cb17  xor     ecx, ecx; this
0x18013cb19  call    BLoadOEMPluginModulesInternal
0x18013cb1e  test    eax, eax
0x18013cb20  jnz     short loc_18013CB43
0x18013cb22  call    cs:__imp_GetLastError
0x18013cb29  nop     dword ptr [rax+rax+00h]
0x18013cb2e  test    eax, eax
0x18013cb30  jle     short loc_18013CB3A
0x18013cb32  movzx   eax, ax
0x18013cb35  or      eax, 80070000h
0x18013cb3a  lea     rdx, aCannotLoadOemP; "Cannot load OEM plugins (hr: 0x%x)."
0x18013cb41  jmp     short loc_18013CAE6
0x18013cb43  lea     rax, ?OemUIHelperFuncs@PSUI@@3U_OEMUIPROCS@@B; _OEMUIPROCS const PSUI::OemUIHelperFuncs
0x18013cb4a  mov     dword ptr [rbx], 10h
0x18013cb50  mov     [rbx+8], rax
0x18013cb54  mov     rax, rbx
0x18013cb57  mov     dword ptr [rbx+3Ch], 1
0x18013cb5e  mov     [r12], rdi
0x18013cb62  jmp     short loc_18013CBAE
0x18013cb64  xor     edi, edi
0x18013cb66  call    cs:__imp_GetLastError
0x18013cb6d  nop     dword ptr [rax+rax+00h]
0x18013cb72  test    eax, eax
0x18013cb74  jle     short loc_18013CB7E
0x18013cb76  movzx   eax, ax
0x18013cb79  or      eax, 80070000h
0x18013cb7e  lea     rdx, aCannotLoadPrin_1; "Cannot load printer description data (h"...
0x18013cb85  lea     rcx, aPsuiPloadcommo_0; "PSUI::PLoadCommonInfoRO"
0x18013cb8c  jmp     loc_18013CAE9
0x18013cb91  lea     rdx, aMemoryAllocati_1; "Memory allocation failed."
0x18013cb98  lea     rcx, aPsuiPloadcommo_0; "PSUI::PLoadCommonInfoRO"
0x18013cb9f  call    ?WriteDbgTraceWarning@DriverUiTelemetry@DriverUi@@SAXPEADPEAGZZ; DriverUi::DriverUiTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18013cba4  mov     rcx, rbx; hMem
0x18013cba7  call    PSUI__VFreeCommonInfoRO
0x18013cbac  xor     eax, eax
0x18013cbae  mov     rcx, [rsp+298h+var_48]
0x18013cbb6  xor     rcx, rsp; StackCookie
0x18013cbb9  call    __security_check_cookie
0x18013cbbe  add     rsp, 260h
0x18013cbc5  pop     r15
0x18013cbc7  pop     r14
0x18013cbc9  pop     r12
0x18013cbcb  pop     rdi
0x18013cbcc  pop     rsi
0x18013cbcd  pop     rbp
0x18013cbce  pop     rbx
0x18013cbcf  retn
```
