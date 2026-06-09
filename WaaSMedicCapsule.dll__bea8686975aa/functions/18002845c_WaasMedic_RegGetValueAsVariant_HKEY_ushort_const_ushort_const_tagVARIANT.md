# WaasMedic::RegGetValueAsVariant(HKEY__ *,ushort const *,ushort const *,tagVARIANT *)

- ea: `0x18002845c`
- end: `0x18002888e`
- name: `?RegGetValueAsVariant@WaasMedic@@YAJPEAUHKEY__@@PEBG1PEAUtagVARIANT@@@Z`
- size: `1074`
- prototype: `__int64 __fastcall(WaasMedic *__hidden this, HKEY, const unsigned __int16 *, const unsigned __int16 *, struct tagVARIANT *)`
- caller_count: `2`
- callee_count: `14`
- tags: `registry_config, installer_update`

## callers

- `0x1800212f0`
- `0x1800223b0`

## callees

- `0x180002150`
- `0x180003bb0`
- `0x180004708`
- `0x180005ee5`
- `0x180016c9c`
- `0x1800251a8`
- `0x18002543c`
- `0x18002845c`
- `0x180028964`
- `0x180028b78`
- `0x180028d24`
- `0x180028dc4`
- `0x180029098`
- `0x180060700`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-2-0!GetNativeSystemInfo` at `0x18002860e`
- `api-ms-win-core-sysinfo-l1-2-0!GetNativeSystemInfo` at `0x18002860e`
- `OLEAUT32!__imp_SysAllocString` at `0x18002876d`
- `OLEAUT32!__imp_SysAllocString` at `0x18002876d`
- `OLEAUT32!__imp_VariantInit` at `0x1800284d0`
- `OLEAUT32!__imp_VariantInit` at `0x1800284d0`
- `OLEAUT32!__imp_VariantClear` at `0x18002879f`
- `OLEAUT32!__imp_VariantClear` at `0x18002879f`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1800286d0`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1800286d0`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800286ef`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800286ef`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18002871c`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18002871c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180028532`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180028532`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800284f3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002866b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800284f3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002866b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800286a8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002885c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800286a8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002885c`

## string_xrefs

- `0x1800287af`: `RegUtil: Error when attempting to get registry value as VARIANT. Sub key: [%s] Value name: [%s]. hr=0x%08X`

## pseudocode

```c
__int64 __fastcall WaasMedic::RegGetValueAsVariant(WaasMedic *this, const WCHAR *a2, WCHAR *a3, VARIANTARG *a4)
{
  LSTATUS v8; // eax
  int DwordValue; // ebx
  LSTATUS v10; // eax
  __int64 v11; // rcx
  unsigned __int16 *v12; // r9
  int v13; // edi
  void *v14; // r15
  REGSAM v15; // r9d
  LSTATUS v16; // eax
  int BinaryValue; // eax
  SAFEARRAY *v18; // rax
  SAFEARRAY *v19; // rdi
  void *v20; // rdx
  int StringValue; // eax
  BSTR v22; // rax
  const struct _tlgProvider_t *v23; // rax
  int v24; // r9d
  WCHAR *phkResult; // [rsp+20h] [rbp-E0h]
  const unsigned __int16 *lpcbData; // [rsp+28h] [rbp-D8h]
  bool v27; // [rsp+30h] [rbp-D0h]
  size_t Size; // [rsp+50h] [rbp-B0h] BYREF
  HKEY v29; // [rsp+58h] [rbp-A8h] BYREF
  DWORD Type; // [rsp+60h] [rbp-A0h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+68h] [rbp-98h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-90h] BYREF
  const WCHAR *v33; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 *v34; // [rsp+80h] [rbp-80h] BYREF
  __int64 v35; // [rsp+88h] [rbp-78h] BYREF
  struct _SYSTEM_INFO SystemInfo; // [rsp+90h] [rbp-70h] BYREF
  OLECHAR psz[2088]; // [rsp+C0h] [rbp-40h] BYREF

  hKey = 0;
  Type = 0;
  memset_0(psz, 0, 0x104Au);
  LODWORD(Size) = 0;
  if ( !a4 )
    return 2147500035LL;
  VariantInit(a4);
  v8 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a2, 0, 1u, &hKey);
  DwordValue = v8;
  if ( v8 )
  {
    if ( v8 > 0 )
      DwordValue = (unsigned __int16)v8 | 0x80070000;
    goto LABEL_47;
  }
  Type = 0;
  v10 = RegQueryValueExW(hKey, a3, 0, &Type, 0, 0);
  DwordValue = v10;
  if ( v10 )
  {
    if ( v10 > 0 )
      DwordValue = (unsigned __int16)v10 | 0x80070000;
    if ( DwordValue < 0 )
      goto LABEL_47;
  }
  switch ( Type )
  {
    case 1u:
      StringValue = WaasMedic::RegQueryStringValue(v11, a2, a3, psz);
LABEL_42:
      DwordValue = StringValue;
      if ( StringValue < 0 || !psz[0] )
        goto LABEL_47;
      v22 = SysAllocString(psz);
      a4->llVal = (LONGLONG)v22;
      if ( v22 )
      {
        a4->vt = 8;
        goto LABEL_47;
      }
      goto LABEL_45;
    case 2u:
      StringValue = WaasMedic::RegQueryStringValueWithDefaultAndExpand(
                      (WaasMedic *)hKey,
                      (HKEY)a3,
                      psz,
                      v12,
                      phkResult,
                      lpcbData,
                      v27);
      goto LABEL_42;
    case 3u:
      v29 = 0;
      if ( !a2 )
      {
        DwordValue = -2147467261;
        goto LABEL_47;
      }
      v14 = 0;
      rgsabound = 0;
      LODWORD(Size) = 0;
      if ( !dword_180098D58 )
      {
        dword_180098D54 = 0;
        memset(&SystemInfo, 0, sizeof(SystemInfo));
        GetNativeSystemInfo(&SystemInfo);
        if ( SystemInfo.wProcessorArchitecture == 6 || SystemInfo.wProcessorArchitecture == 9 )
          dword_180098D54 = 1;
        dword_180098D58 = 1;
      }
      v15 = 1;
      if ( dword_180098D54 )
        v15 = 257;
      v16 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a2, 0, v15, &v29);
      DwordValue = v16;
      if ( v16 )
      {
        if ( v16 > 0 )
          DwordValue = (unsigned __int16)v16 | 0x80070000;
      }
      else
      {
        BinaryValue = WaasMedic::RegQueryBinaryValue(
                        v29,
                        (HKEY)a3,
                        (const unsigned __int16 *)&rgsabound,
                        (unsigned __int8 **)&Size,
                        (unsigned int *)phkResult);
        v14 = (void *)rgsabound;
        DwordValue = BinaryValue;
      }
      if ( v29 )
        RegCloseKey(v29);
      if ( DwordValue >= 0 )
      {
        rgsabound.lLbound = 0;
        rgsabound.cElements = Size;
        v18 = SafeArrayCreate(0x11u, 1u, &rgsabound);
        v19 = v18;
        if ( v18 )
        {
          v29 = 0;
          DwordValue = SafeArrayAccessData(v18, (void **)&v29);
          if ( DwordValue >= 0 )
          {
            memcpy_0(v29, v14, (unsigned int)Size);
            WaasMedic::SafeFree((WaasMedic *)v14, v20);
            DwordValue = SafeArrayUnaccessData(v19);
            if ( DwordValue >= 0 )
            {
              a4->llVal = (LONGLONG)v19;
              a4->vt = 8209;
            }
          }
          goto LABEL_47;
        }
LABEL_45:
        v13 = -2147024882;
        goto LABEL_50;
      }
LABEL_47:
      v13 = 0;
      if ( DwordValue != -2147024894 )
        v13 = DwordValue;
      if ( v13 >= 0 )
        goto LABEL_54;
      goto LABEL_50;
    case 4u:
      DwordValue = WaasMedic::RegQueryDwordValue((WaasMedic *)hKey, (HKEY)a3, &a4->uiVal, (unsigned int *)v12);
      if ( DwordValue >= 0 )
        a4->vt = 19;
      goto LABEL_47;
    case 0xBu:
      DwordValue = WaasMedic::RegQueryQwordValue((WaasMedic *)hKey, (HKEY)a3, &a4->uiVal, (unsigned __int64 *)v12);
      if ( DwordValue >= 0 )
        a4->vt = 21;
      goto LABEL_47;
  }
  v13 = -2147024809;
LABEL_50:
  VariantClear(a4);
  LODWORD(phkResult) = v13;
  LogLevelW(
    2u,
    L"RegUtil: Error when attempting to get registry value as VARIANT. Sub key: [%s] Value name: [%s]. hr=0x%08X",
    a2,
    a3,
    phkResult);
  v23 = WaasMedic::TelemetryProvider::Provider();
  if ( *(_DWORD *)v23 > 5u
    && (*((_QWORD *)v23 + 2) & 0x400000000000LL) != 0
    && (*((_QWORD *)v23 + 3) & 0x400000000000LL) == *((_QWORD *)v23 + 3) )
  {
    LODWORD(v29) = v13;
    v34 = &gc_pszVersionString;
    rgsabound = (SAFEARRAYBOUND)a3;
    v33 = a2;
    v35 = 0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      (_DWORD)v23,
      (unsigned int)&dword_18008918C,
      0,
      v24,
      (__int64)&v35,
      (__int64)&v34,
      (__int64)&v33,
      (__int64)&rgsabound,
      (__int64)&v29);
  }
LABEL_54:
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18002845c  mov     [rsp-8+arg_0], rbx
0x180028461  push    rbp
0x180028462  push    rsi
0x180028463  push    rdi
0x180028464  push    r12
0x180028466  push    r13
0x180028468  push    r14
0x18002846a  push    r15
0x18002846c  lea     rbp, [rsp-1020h]
0x180028474  mov     eax, 1120h
0x180028479  call    _alloca_probe
0x18002847e  sub     rsp, rax
0x180028481  mov     rax, cs:__security_cookie
0x180028488  xor     rax, rsp
0x18002848b  mov     [rbp+1050h+var_40], rax
0x180028492  mov     r14, r8
0x180028495  lea     rcx, [rbp+1050h+psz]; void *
0x180028499  mov     r12, rdx
0x18002849c  xor     r13d, r13d
0x18002849f  xor     edx, edx; Val
0x1800284a1  mov     [rsp+1150h+hKey], r13
0x1800284a6  mov     r8d, 104Ah; Size
0x1800284ac  mov     [rsp+1150h+Type], r13d
0x1800284b1  mov     rsi, r9
0x1800284b4  call    memset_0
0x1800284b9  mov     dword ptr [rsp+1150h+Size], r13d
0x1800284be  test    rsi, rsi
0x1800284c1  jnz     short loc_1800284CD
0x1800284c3  mov     eax, 80004003h
0x1800284c8  jmp     loc_180028864
0x1800284cd  mov     rcx, rsi; pvarg
0x1800284d0  call    cs:__imp_VariantInit
0x1800284d6  lea     rax, [rsp+1150h+hKey]
0x1800284db  mov     r9d, 1; samDesired
0x1800284e1  xor     r8d, r8d; ulOptions
0x1800284e4  mov     [rsp+1150h+phkResult], rax; phkResult
0x1800284e9  mov     rdx, r12; lpSubKey
0x1800284ec  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800284f3  call    cs:__imp_RegOpenKeyExW
0x1800284f9  mov     ebx, eax
0x1800284fb  test    eax, eax
0x1800284fd  jz      short loc_180028513
0x1800284ff  jle     loc_180028788
0x180028505  movzx   ebx, ax
0x180028508  or      ebx, 80070000h
0x18002850e  jmp     loc_180028788
0x180028513  mov     rcx, [rsp+1150h+hKey]; hKey
0x180028518  lea     r9, [rsp+1150h+Type]; lpType
0x18002851d  mov     [rsp+1150h+lpcbData], r13; unsigned __int16 *
0x180028522  xor     r8d, r8d; lpReserved
0x180028525  mov     rdx, r14; lpValueName
0x180028528  mov     [rsp+1150h+phkResult], r13; lpSrc
0x18002852d  mov     [rsp+1150h+Type], r13d
0x180028532  call    cs:__imp_RegQueryValueExW
0x180028538  mov     ebx, eax
0x18002853a  mov     edi, 80070000h
0x18002853f  test    eax, eax
0x180028541  jz      short loc_180028552
0x180028543  jle     short loc_18002854A
0x180028545  movzx   ebx, ax
0x180028548  or      ebx, edi
0x18002854a  test    ebx, ebx
0x18002854c  js      loc_180028788
0x180028552  mov     eax, [rsp+1150h+Type]
0x180028556  sub     eax, 1
0x180028559  jz      loc_18002874D
0x18002855f  sub     eax, 1
0x180028562  jz      loc_18002873A
0x180028568  sub     eax, 1
0x18002856b  jz      short loc_1800285D0
0x18002856d  sub     eax, 1
0x180028570  jz      short loc_1800285AB
0x180028572  sub     eax, 3
0x180028575  jz      short loc_1800285A1
0x180028577  cmp     eax, 4
0x18002857a  jnz     short loc_1800285A1
0x18002857c  mov     rcx, [rsp+1150h+hKey]; this
0x180028581  lea     r8, [rsi+8]; unsigned __int16 *
0x180028585  mov     rdx, r14; HKEY
0x180028588  call    ?RegQueryQwordValue@WaasMedic@@YAJPEAUHKEY__@@PEBGPEA_K@Z; WaasMedic::RegQueryQwordValue(HKEY__ *,ushort const *,unsigned __int64 *)
0x18002858d  mov     ebx, eax
0x18002858f  test    eax, eax
0x180028591  js      loc_180028788
0x180028597  mov     word ptr [rsi], 15h
0x18002859c  jmp     loc_180028788
0x1800285a1  mov     edi, 80070057h
0x1800285a6  jmp     loc_18002879C
0x1800285ab  mov     rcx, [rsp+1150h+hKey]; this
0x1800285b0  lea     r8, [rsi+8]; unsigned __int16 *
0x1800285b4  mov     rdx, r14; HKEY
0x1800285b7  call    ?RegQueryDwordValue@WaasMedic@@YAJPEAUHKEY__@@PEBGPEAK@Z; WaasMedic::RegQueryDwordValue(HKEY__ *,ushort const *,ulong *)
0x1800285bc  mov     ebx, eax
0x1800285be  test    eax, eax
0x1800285c0  js      loc_180028788
0x1800285c6  mov     word ptr [rsi], 13h
0x1800285cb  jmp     loc_180028788
0x1800285d0  mov     [rsp+1150h+var_10F8], r13
0x1800285d5  test    r12, r12
0x1800285d8  jz      loc_180028733
0x1800285de  cmp     cs:dword_180098D58, r13d
0x1800285e5  mov     r15, r13
0x1800285e8  mov     qword ptr [rsp+1150h+rgsabound.cElements], r13
0x1800285ed  mov     dword ptr [rsp+1150h+Size], r13d
0x1800285f2  jnz     short loc_18002863E
0x1800285f4  xorps   xmm0, xmm0
0x1800285f7  mov     cs:dword_180098D54, r13d
0x1800285fe  lea     rcx, [rbp+1050h+SystemInfo]; lpSystemInfo
0x180028602  movups  xmmword ptr [rbp+1050h+SystemInfo], xmm0
0x180028606  movups  xmmword ptr [rbp+1050h+SystemInfo.lpMaximumApplicationAddress], xmm0
0x18002860a  movups  xmmword ptr [rbp+1050h+SystemInfo.dwNumberOfProcessors], xmm0
0x18002860e  call    cs:__imp_GetNativeSystemInfo
0x180028614  mov     eax, 6
0x180028619  cmp     ax, word ptr [rbp+1050h+SystemInfo]
0x18002861d  jz      short loc_18002862A
0x18002861f  mov     eax, 9
0x180028624  cmp     ax, word ptr [rbp+1050h+SystemInfo]
0x180028628  jnz     short loc_180028634
0x18002862a  mov     cs:dword_180098D54, 1
0x180028634  mov     cs:dword_180098D58, 1
0x18002863e  cmp     cs:dword_180098D54, r13d
0x180028645  mov     eax, 101h
0x18002864a  mov     r9d, 1
0x180028650  cmovnz  r9d, eax; samDesired
0x180028654  lea     rax, [rsp+1150h+var_10F8]
0x180028659  xor     r8d, r8d; ulOptions
0x18002865c  mov     rdx, r12; lpSubKey
0x18002865f  mov     [rsp+1150h+phkResult], rax; unsigned int *
0x180028664  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002866b  call    cs:__imp_RegOpenKeyExW
0x180028671  mov     ebx, eax
0x180028673  test    eax, eax
0x180028675  jz      short loc_180028680
0x180028677  jle     short loc_18002869E
0x180028679  movzx   ebx, ax
0x18002867c  or      ebx, edi
0x18002867e  jmp     short loc_18002869E
0x180028680  mov     rcx, [rsp+1150h+var_10F8]; hKey
0x180028685  lea     r9, [rsp+1150h+Size]; unsigned __int8 **
0x18002868a  lea     r8, [rsp+1150h+rgsabound]; unsigned __int16 *
0x18002868f  mov     rdx, r14; HKEY
0x180028692  call    ?RegQueryBinaryValue@WaasMedic@@YAJPEAUHKEY__@@PEBGPEAPEAEPEAK@Z; WaasMedic::RegQueryBinaryValue(HKEY__ *,ushort const *,uchar * *,ulong *)
0x180028697  mov     r15, qword ptr [rsp+1150h+rgsabound.cElements]
0x18002869c  mov     ebx, eax
0x18002869e  mov     rcx, [rsp+1150h+var_10F8]; hKey
0x1800286a3  test    rcx, rcx
0x1800286a6  jz      short loc_1800286AE
0x1800286a8  call    cs:__imp_RegCloseKey
0x1800286ae  test    ebx, ebx
0x1800286b0  js      loc_180028788
0x1800286b6  mov     eax, dword ptr [rsp+1150h+Size]
0x1800286ba  lea     r8, [rsp+1150h+rgsabound]; rgsabound
0x1800286bf  mov     ecx, 11h; vt
0x1800286c4  mov     [rsp+1150h+rgsabound.lLbound], r13d
0x1800286c9  mov     [rsp+1150h+rgsabound.cElements], eax
0x1800286cd  lea     edx, [rcx-10h]; cDims
0x1800286d0  call    cs:__imp_SafeArrayCreate
0x1800286d6  mov     rdi, rax
0x1800286d9  test    rax, rax
0x1800286dc  jz      loc_18002877C
0x1800286e2  lea     rdx, [rsp+1150h+var_10F8]; ppvData
0x1800286e7  mov     [rsp+1150h+var_10F8], r13
0x1800286ec  mov     rcx, rax; psa
0x1800286ef  call    cs:__imp_SafeArrayAccessData
0x1800286f5  mov     ebx, eax
0x1800286f7  test    eax, eax
0x1800286f9  js      loc_180028788
0x1800286ff  mov     r8d, dword ptr [rsp+1150h+Size]; Size
0x180028704  mov     rdx, r15; Src
0x180028707  mov     rcx, [rsp+1150h+var_10F8]; void *
0x18002870c  call    memcpy_0
0x180028711  mov     rcx, r15; this
0x180028714  call    ?SafeFree@WaasMedic@@YAJPEAX@Z; WaasMedic::SafeFree(void *)
0x180028719  mov     rcx, rdi; psa
0x18002871c  call    cs:__imp_SafeArrayUnaccessData
0x180028722  mov     ebx, eax
0x180028724  test    eax, eax
0x180028726  js      short loc_180028788
0x180028728  mov     [rsi+8], rdi
0x18002872c  mov     word ptr [rsi], 2011h
0x180028731  jmp     short loc_180028788
0x180028733  mov     ebx, 80004003h
0x180028738  jmp     short loc_180028788
0x18002873a  mov     rcx, [rsp+1150h+hKey]; this
0x18002873f  lea     r8, [rbp+1050h+psz]; unsigned __int16 *
0x180028743  mov     rdx, r14; HKEY
0x180028746  call    ?RegQueryStringValueWithDefaultAndExpand@WaasMedic@@YAJPEAUHKEY__@@PEBGPEAGK1_N@Z; WaasMedic::RegQueryStringValueWithDefaultAndExpand(HKEY__ *,ushort const *,ushort *,ulong,ushort const *,bool)
0x18002874b  jmp     short loc_18002875C
0x18002874d  lea     r9, [rbp+1050h+psz]
0x180028751  mov     r8, r14
0x180028754  mov     rdx, r12
0x180028757  call    ?RegQueryStringValue@WaasMedic@@YAJPEAUHKEY__@@PEBG1PEAGKW4RegistryHiveType@1@@Z; WaasMedic::RegQueryStringValue(HKEY__ *,ushort const *,ushort const *,ushort *,ulong,WaasMedic::RegistryHiveType)
0x18002875c  mov     ebx, eax
0x18002875e  test    eax, eax
0x180028760  js      short loc_180028788
0x180028762  cmp     [rbp+1050h+psz], r13w
0x180028767  jz      short loc_180028788
0x180028769  lea     rcx, [rbp+1050h+psz]; psz
0x18002876d  call    cs:__imp_SysAllocString
0x180028773  mov     [rsi+8], rax
0x180028777  test    rax, rax
0x18002877a  jnz     short loc_180028783
0x18002877c  mov     edi, 8007000Eh
0x180028781  jmp     short loc_18002879C
0x180028783  mov     word ptr [rsi], 8
0x180028788  cmp     ebx, 80070002h
0x18002878e  mov     edi, r13d
0x180028791  cmovnz  edi, ebx
0x180028794  test    edi, edi
0x180028796  jns     loc_180028852
0x18002879c  mov     rcx, rsi; pvarg
0x18002879f  call    cs:__imp_VariantClear
0x1800287a5  mov     r9, r14
0x1800287a8  mov     dword ptr [rsp+1150h+phkResult], edi
0x1800287ac  mov     r8, r12
0x1800287af  lea     rdx, aRegutilErrorWh_1; "RegUtil: Error when attempting to get r"...
0x1800287b6  mov     ecx, 2; unsigned __int8
0x1800287bb  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x1800287c0  call    ?Provider@TelemetryProvider@WaasMedic@@SAPEBU_tlgProvider_t@@XZ; WaasMedic::TelemetryProvider::Provider(void)
0x1800287c5  mov     ecx, [rax]
0x1800287c7  cmp     ecx, 5
0x1800287ca  jbe     loc_180028852
0x1800287d0  mov     rdx, [rax+18h]
0x1800287d4  mov     r8, 400000000000h
0x1800287de  mov     rcx, [rax+10h]
0x1800287e2  test    r8, rcx
0x1800287e5  jz      short loc_180028852
0x1800287e7  mov     rcx, rdx
0x1800287ea  and     rcx, r8
0x1800287ed  cmp     rcx, rdx
0x1800287f0  jnz     short loc_180028852
0x1800287f2  lea     rcx, ?gc_pszVersionString@@3PAGA; ushort near * gc_pszVersionString
0x1800287f9  mov     dword ptr [rsp+1150h+var_10F8], edi
0x1800287fd  mov     [rbp+1050h+var_10D0], rcx
0x180028801  lea     rdx, dword_18008918C
0x180028808  lea     rcx, [rsp+1150h+var_10F8]
0x18002880d  mov     qword ptr [rsp+1150h+rgsabound.cElements], r14
0x180028812  mov     [rsp+1150h+var_1110], rcx
0x180028817  lea     rcx, [rsp+1150h+rgsabound]
0x18002881c  mov     [rsp+1150h+var_1118], rcx
0x180028821  lea     rcx, [rsp+1150h+var_10D8]
0x180028826  mov     [rsp+1150h+var_1120], rcx
0x18002882b  lea     rcx, [rbp+1050h+var_10D0]
0x18002882f  mov     [rsp+1150h+lpcbData], rcx
0x180028834  lea     rcx, [rbp+1050h+var_10C8]
0x180028838  mov     [rsp+1150h+phkResult], rcx
0x18002883d  mov     rcx, rax
0x180028840  mov     [rsp+1150h+var_10D8], r12
0x180028845  mov     [rbp+1050h+var_10C8], 1000000h
0x18002884d  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U2@U2@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@44AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180028852  mov     rcx, [rsp+1150h+hKey]; hKey
0x180028857  test    rcx, rcx
0x18002885a  jz      short loc_180028862
0x18002885c  call    cs:__imp_RegCloseKey
0x180028862  mov     eax, edi
0x180028864  mov     rcx, [rbp+1050h+var_40]
0x18002886b  xor     rcx, rsp; StackCookie
0x18002886e  call    __security_check_cookie
0x180028873  mov     rbx, [rsp+1150h+arg_0]
0x18002887b  add     rsp, 1120h
0x180028882  pop     r15
0x180028884  pop     r14
0x180028886  pop     r13
0x180028888  pop     r12
0x18002888a  pop     rdi
0x18002888b  pop     rsi
0x18002888c  pop     rbp
0x18002888d  retn
```
