# WaasMedic::RegGetValueAsVariant(HKEY__ *,ushort const *,ushort const *,tagVARIANT *)

- ea: `0x1800262dc`
- end: `0x18002670b`
- name: `?RegGetValueAsVariant@WaasMedic@@YAJPEAUHKEY__@@PEBG1PEAUtagVARIANT@@@Z`
- size: `1071`
- prototype: `__int64 __fastcall(WaasMedic *__hidden this, HKEY, const unsigned __int16 *, const unsigned __int16 *, struct tagVARIANT *)`
- caller_count: `2`
- callee_count: `14`
- tags: `registry_config, installer_update`

## callers

- `0x180022434`
- `0x180022fd0`

## callees

- `0x1800023dc`
- `0x1800050a0`
- `0x180005bbc`
- `0x180008d8d`
- `0x18000d04c`
- `0x1800262dc`
- `0x1800267e4`
- `0x1800269f8`
- `0x180026c94`
- `0x180026d34`
- `0x180027008`
- `0x18002a4e4`
- `0x18002e81c`
- `0x18006b240`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800265ed`
- `OLEAUT32!__imp_SysAllocString` at `0x1800265ed`
- `OLEAUT32!__imp_VariantInit` at `0x180026350`
- `OLEAUT32!__imp_VariantInit` at `0x180026350`
- `OLEAUT32!__imp_VariantClear` at `0x18002661f`
- `OLEAUT32!__imp_VariantClear` at `0x18002661f`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180026550`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180026550`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18002656f`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18002656f`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18002659c`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18002659c`
- `api-ms-win-core-sysinfo-l1-2-0!GetNativeSystemInfo` at `0x18002648e`
- `api-ms-win-core-sysinfo-l1-2-0!GetNativeSystemInfo` at `0x18002648e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180026373`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800264eb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180026373`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800264eb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800263b2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800263b2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026528`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800266d9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180026528`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800266d9`

## string_xrefs

- `0x18002662f`: `RegUtil: Error when attempting to get registry value as VARIANT. Sub key: [%s] Value name: [%s]. hr=0x%08X`

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
  __int64 v23; // rcx
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
      if ( !dword_1800A55AC )
      {
        dword_1800A55B0 = 0;
        memset(&SystemInfo, 0, sizeof(SystemInfo));
        GetNativeSystemInfo(&SystemInfo);
        if ( SystemInfo.wProcessorArchitecture == 6 || SystemInfo.wProcessorArchitecture == 9 )
          dword_1800A55B0 = 1;
        dword_1800A55AC = 1;
      }
      v15 = 1;
      if ( dword_1800A55B0 )
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
  v23 = *((_QWORD *)WaasMedic::TelemetryProvider::Instance() + 1);
  if ( *(_DWORD *)v23 > 5u
    && (*(_QWORD *)(v23 + 16) & 0x400000000000LL) != 0
    && (*(_QWORD *)(v23 + 24) & 0x400000000000LL) == *(_QWORD *)(v23 + 24) )
  {
    LODWORD(v29) = v13;
    v34 = &gc_pszVersionString;
    rgsabound = (SAFEARRAYBOUND)a3;
    v33 = a2;
    v35 = 0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      v23,
      (unsigned int)&byte_180092C9F,
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
0x1800262dc  mov     [rsp-8+arg_0], rbx
0x1800262e1  push    rbp
0x1800262e2  push    rsi
0x1800262e3  push    rdi
0x1800262e4  push    r12
0x1800262e6  push    r13
0x1800262e8  push    r14
0x1800262ea  push    r15
0x1800262ec  lea     rbp, [rsp-1020h]
0x1800262f4  mov     eax, 1120h
0x1800262f9  call    _alloca_probe
0x1800262fe  sub     rsp, rax
0x180026301  mov     rax, cs:__security_cookie
0x180026308  xor     rax, rsp
0x18002630b  mov     [rbp+1050h+var_40], rax
0x180026312  mov     r14, r8
0x180026315  lea     rcx, [rbp+1050h+psz]; void *
0x180026319  mov     r12, rdx
0x18002631c  xor     r13d, r13d
0x18002631f  xor     edx, edx; Val
0x180026321  mov     [rsp+1150h+hKey], r13
0x180026326  mov     r8d, 104Ah; Size
0x18002632c  mov     [rsp+1150h+Type], r13d
0x180026331  mov     rsi, r9
0x180026334  call    memset_0
0x180026339  mov     dword ptr [rsp+1150h+Size], r13d
0x18002633e  test    rsi, rsi
0x180026341  jnz     short loc_18002634D
0x180026343  mov     eax, 80004003h
0x180026348  jmp     loc_1800266E1
0x18002634d  mov     rcx, rsi; pvarg
0x180026350  call    cs:__imp_VariantInit
0x180026356  lea     rax, [rsp+1150h+hKey]
0x18002635b  mov     r9d, 1; samDesired
0x180026361  xor     r8d, r8d; ulOptions
0x180026364  mov     [rsp+1150h+phkResult], rax; phkResult
0x180026369  mov     rdx, r12; lpSubKey
0x18002636c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180026373  call    cs:__imp_RegOpenKeyExW
0x180026379  mov     ebx, eax
0x18002637b  test    eax, eax
0x18002637d  jz      short loc_180026393
0x18002637f  jle     loc_180026608
0x180026385  movzx   ebx, ax
0x180026388  or      ebx, 80070000h
0x18002638e  jmp     loc_180026608
0x180026393  mov     rcx, [rsp+1150h+hKey]; hKey
0x180026398  lea     r9, [rsp+1150h+Type]; lpType
0x18002639d  mov     [rsp+1150h+lpcbData], r13; unsigned __int16 *
0x1800263a2  xor     r8d, r8d; lpReserved
0x1800263a5  mov     rdx, r14; lpValueName
0x1800263a8  mov     [rsp+1150h+phkResult], r13; lpSrc
0x1800263ad  mov     [rsp+1150h+Type], r13d
0x1800263b2  call    cs:__imp_RegQueryValueExW
0x1800263b8  mov     ebx, eax
0x1800263ba  mov     edi, 80070000h
0x1800263bf  test    eax, eax
0x1800263c1  jz      short loc_1800263D2
0x1800263c3  jle     short loc_1800263CA
0x1800263c5  movzx   ebx, ax
0x1800263c8  or      ebx, edi
0x1800263ca  test    ebx, ebx
0x1800263cc  js      loc_180026608
0x1800263d2  mov     eax, [rsp+1150h+Type]
0x1800263d6  sub     eax, 1
0x1800263d9  jz      loc_1800265CD
0x1800263df  sub     eax, 1
0x1800263e2  jz      loc_1800265BA
0x1800263e8  sub     eax, 1
0x1800263eb  jz      short loc_180026450
0x1800263ed  sub     eax, 1
0x1800263f0  jz      short loc_18002642B
0x1800263f2  sub     eax, 3
0x1800263f5  jz      short loc_180026421
0x1800263f7  cmp     eax, 4
0x1800263fa  jnz     short loc_180026421
0x1800263fc  mov     rcx, [rsp+1150h+hKey]; this
0x180026401  lea     r8, [rsi+8]; unsigned __int16 *
0x180026405  mov     rdx, r14; HKEY
0x180026408  call    ?RegQueryQwordValue@WaasMedic@@YAJPEAUHKEY__@@PEBGPEA_K@Z; WaasMedic::RegQueryQwordValue(HKEY__ *,ushort const *,unsigned __int64 *)
0x18002640d  mov     ebx, eax
0x18002640f  test    eax, eax
0x180026411  js      loc_180026608
0x180026417  mov     word ptr [rsi], 15h
0x18002641c  jmp     loc_180026608
0x180026421  mov     edi, 80070057h
0x180026426  jmp     loc_18002661C
0x18002642b  mov     rcx, [rsp+1150h+hKey]; this
0x180026430  lea     r8, [rsi+8]; unsigned __int16 *
0x180026434  mov     rdx, r14; HKEY
0x180026437  call    ?RegQueryDwordValue@WaasMedic@@YAJPEAUHKEY__@@PEBGPEAK@Z; WaasMedic::RegQueryDwordValue(HKEY__ *,ushort const *,ulong *)
0x18002643c  mov     ebx, eax
0x18002643e  test    eax, eax
0x180026440  js      loc_180026608
0x180026446  mov     word ptr [rsi], 13h
0x18002644b  jmp     loc_180026608
0x180026450  mov     [rsp+1150h+var_10F8], r13
0x180026455  test    r12, r12
0x180026458  jz      loc_1800265B3
0x18002645e  cmp     cs:dword_1800A55AC, r13d
0x180026465  mov     r15, r13
0x180026468  mov     qword ptr [rsp+1150h+rgsabound.cElements], r13
0x18002646d  mov     dword ptr [rsp+1150h+Size], r13d
0x180026472  jnz     short loc_1800264BE
0x180026474  xorps   xmm0, xmm0
0x180026477  mov     cs:dword_1800A55B0, r13d
0x18002647e  lea     rcx, [rbp+1050h+SystemInfo]; lpSystemInfo
0x180026482  movups  xmmword ptr [rbp+1050h+SystemInfo], xmm0
0x180026486  movups  xmmword ptr [rbp+1050h+SystemInfo.lpMaximumApplicationAddress], xmm0
0x18002648a  movups  xmmword ptr [rbp+1050h+SystemInfo.dwNumberOfProcessors], xmm0
0x18002648e  call    cs:__imp_GetNativeSystemInfo
0x180026494  mov     eax, 6
0x180026499  cmp     ax, word ptr [rbp+1050h+SystemInfo]
0x18002649d  jz      short loc_1800264AA
0x18002649f  mov     eax, 9
0x1800264a4  cmp     ax, word ptr [rbp+1050h+SystemInfo]
0x1800264a8  jnz     short loc_1800264B4
0x1800264aa  mov     cs:dword_1800A55B0, 1
0x1800264b4  mov     cs:dword_1800A55AC, 1
0x1800264be  cmp     cs:dword_1800A55B0, r13d
0x1800264c5  mov     eax, 101h
0x1800264ca  mov     r9d, 1
0x1800264d0  cmovnz  r9d, eax; samDesired
0x1800264d4  lea     rax, [rsp+1150h+var_10F8]
0x1800264d9  xor     r8d, r8d; ulOptions
0x1800264dc  mov     rdx, r12; lpSubKey
0x1800264df  mov     [rsp+1150h+phkResult], rax; unsigned int *
0x1800264e4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800264eb  call    cs:__imp_RegOpenKeyExW
0x1800264f1  mov     ebx, eax
0x1800264f3  test    eax, eax
0x1800264f5  jz      short loc_180026500
0x1800264f7  jle     short loc_18002651E
0x1800264f9  movzx   ebx, ax
0x1800264fc  or      ebx, edi
0x1800264fe  jmp     short loc_18002651E
0x180026500  mov     rcx, [rsp+1150h+var_10F8]; hKey
0x180026505  lea     r9, [rsp+1150h+Size]; unsigned __int8 **
0x18002650a  lea     r8, [rsp+1150h+rgsabound]; unsigned __int16 *
0x18002650f  mov     rdx, r14; HKEY
0x180026512  call    ?RegQueryBinaryValue@WaasMedic@@YAJPEAUHKEY__@@PEBGPEAPEAEPEAK@Z; WaasMedic::RegQueryBinaryValue(HKEY__ *,ushort const *,uchar * *,ulong *)
0x180026517  mov     r15, qword ptr [rsp+1150h+rgsabound.cElements]
0x18002651c  mov     ebx, eax
0x18002651e  mov     rcx, [rsp+1150h+var_10F8]; hKey
0x180026523  test    rcx, rcx
0x180026526  jz      short loc_18002652E
0x180026528  call    cs:__imp_RegCloseKey
0x18002652e  test    ebx, ebx
0x180026530  js      loc_180026608
0x180026536  mov     eax, dword ptr [rsp+1150h+Size]
0x18002653a  lea     r8, [rsp+1150h+rgsabound]; rgsabound
0x18002653f  mov     ecx, 11h; vt
0x180026544  mov     [rsp+1150h+rgsabound.lLbound], r13d
0x180026549  mov     [rsp+1150h+rgsabound.cElements], eax
0x18002654d  lea     edx, [rcx-10h]; cDims
0x180026550  call    cs:__imp_SafeArrayCreate
0x180026556  mov     rdi, rax
0x180026559  test    rax, rax
0x18002655c  jz      loc_1800265FC
0x180026562  lea     rdx, [rsp+1150h+var_10F8]; ppvData
0x180026567  mov     [rsp+1150h+var_10F8], r13
0x18002656c  mov     rcx, rax; psa
0x18002656f  call    cs:__imp_SafeArrayAccessData
0x180026575  mov     ebx, eax
0x180026577  test    eax, eax
0x180026579  js      loc_180026608
0x18002657f  mov     r8d, dword ptr [rsp+1150h+Size]; Size
0x180026584  mov     rdx, r15; Src
0x180026587  mov     rcx, [rsp+1150h+var_10F8]; void *
0x18002658c  call    memcpy_0
0x180026591  mov     rcx, r15; this
0x180026594  call    ?SafeFree@WaasMedic@@YAJPEAX@Z; WaasMedic::SafeFree(void *)
0x180026599  mov     rcx, rdi; psa
0x18002659c  call    cs:__imp_SafeArrayUnaccessData
0x1800265a2  mov     ebx, eax
0x1800265a4  test    eax, eax
0x1800265a6  js      short loc_180026608
0x1800265a8  mov     [rsi+8], rdi
0x1800265ac  mov     word ptr [rsi], 2011h
0x1800265b1  jmp     short loc_180026608
0x1800265b3  mov     ebx, 80004003h
0x1800265b8  jmp     short loc_180026608
0x1800265ba  mov     rcx, [rsp+1150h+hKey]; this
0x1800265bf  lea     r8, [rbp+1050h+psz]; unsigned __int16 *
0x1800265c3  mov     rdx, r14; HKEY
0x1800265c6  call    ?RegQueryStringValueWithDefaultAndExpand@WaasMedic@@YAJPEAUHKEY__@@PEBGPEAGK1_N@Z; WaasMedic::RegQueryStringValueWithDefaultAndExpand(HKEY__ *,ushort const *,ushort *,ulong,ushort const *,bool)
0x1800265cb  jmp     short loc_1800265DC
0x1800265cd  lea     r9, [rbp+1050h+psz]
0x1800265d1  mov     r8, r14
0x1800265d4  mov     rdx, r12
0x1800265d7  call    ?RegQueryStringValue@WaasMedic@@YAJPEAUHKEY__@@PEBG1PEAGKW4RegistryHiveType@1@@Z; WaasMedic::RegQueryStringValue(HKEY__ *,ushort const *,ushort const *,ushort *,ulong,WaasMedic::RegistryHiveType)
0x1800265dc  mov     ebx, eax
0x1800265de  test    eax, eax
0x1800265e0  js      short loc_180026608
0x1800265e2  cmp     [rbp+1050h+psz], r13w
0x1800265e7  jz      short loc_180026608
0x1800265e9  lea     rcx, [rbp+1050h+psz]; psz
0x1800265ed  call    cs:__imp_SysAllocString
0x1800265f3  mov     [rsi+8], rax
0x1800265f7  test    rax, rax
0x1800265fa  jnz     short loc_180026603
0x1800265fc  mov     edi, 8007000Eh
0x180026601  jmp     short loc_18002661C
0x180026603  mov     word ptr [rsi], 8
0x180026608  cmp     ebx, 80070002h
0x18002660e  mov     edi, r13d
0x180026611  cmovnz  edi, ebx
0x180026614  test    edi, edi
0x180026616  jns     loc_1800266CF
0x18002661c  mov     rcx, rsi; pvarg
0x18002661f  call    cs:__imp_VariantClear
0x180026625  mov     r9, r14
0x180026628  mov     dword ptr [rsp+1150h+phkResult], edi
0x18002662c  mov     r8, r12
0x18002662f  lea     rdx, aRegutilErrorWh_1; "RegUtil: Error when attempting to get r"...
0x180026636  mov     ecx, 2; unsigned __int8
0x18002663b  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180026640  call    ?Instance@TelemetryProvider@WaasMedic@@KAPEAV12@XZ; WaasMedic::TelemetryProvider::Instance(void)
0x180026645  mov     rcx, [rax+8]
0x180026649  mov     eax, [rcx]
0x18002664b  cmp     eax, 5
0x18002664e  jbe     short loc_1800266CF
0x180026650  mov     rdx, [rcx+18h]
0x180026654  mov     r8, 400000000000h
0x18002665e  mov     rax, [rcx+10h]
0x180026662  test    r8, rax
0x180026665  jz      short loc_1800266CF
0x180026667  mov     rax, rdx
0x18002666a  and     rax, r8
0x18002666d  cmp     rax, rdx
0x180026670  jnz     short loc_1800266CF
0x180026672  lea     rax, ?gc_pszVersionString@@3PAGA; ushort near * gc_pszVersionString
0x180026679  mov     dword ptr [rsp+1150h+var_10F8], edi
0x18002667d  mov     [rbp+1050h+var_10D0], rax
0x180026681  lea     rdx, byte_180092C9F
0x180026688  lea     rax, [rsp+1150h+var_10F8]
0x18002668d  mov     qword ptr [rsp+1150h+rgsabound.cElements], r14
0x180026692  mov     [rsp+1150h+var_1110], rax
0x180026697  lea     rax, [rsp+1150h+rgsabound]
0x18002669c  mov     [rsp+1150h+var_1118], rax
0x1800266a1  lea     rax, [rsp+1150h+var_10D8]
0x1800266a6  mov     [rsp+1150h+var_1120], rax
0x1800266ab  lea     rax, [rbp+1050h+var_10D0]
0x1800266af  mov     [rsp+1150h+lpcbData], rax
0x1800266b4  lea     rax, [rbp+1050h+var_10C8]
0x1800266b8  mov     [rsp+1150h+phkResult], rax
0x1800266bd  mov     [rsp+1150h+var_10D8], r12
0x1800266c2  mov     [rbp+1050h+var_10C8], 1000000h
0x1800266ca  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U2@U2@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@44AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x1800266cf  mov     rcx, [rsp+1150h+hKey]; hKey
0x1800266d4  test    rcx, rcx
0x1800266d7  jz      short loc_1800266DF
0x1800266d9  call    cs:__imp_RegCloseKey
0x1800266df  mov     eax, edi
0x1800266e1  mov     rcx, [rbp+1050h+var_40]
0x1800266e8  xor     rcx, rsp; StackCookie
0x1800266eb  call    __security_check_cookie
0x1800266f0  mov     rbx, [rsp+1150h+arg_0]
0x1800266f8  add     rsp, 1120h
0x1800266ff  pop     r15
0x180026701  pop     r14
0x180026703  pop     r13
0x180026705  pop     r12
0x180026707  pop     rdi
0x180026708  pop     rsi
0x180026709  pop     rbp
0x18002670a  retn
```
