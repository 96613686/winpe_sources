# ConvertOnePlugin(HKEY__ *,std::unique_ptr<ushort,release::Deleter<release::aifree_tag>> const &,std::vector<APPID_PLUGIN_,std::allocator<APPID_PLUGIN_>> &,std::vector<APPID_EXECUTION_CATEGORY_,std::allocator<APPID_EXECUTION_CATEGORY_>> &,std::vector<_GUID,std::allocator<_GUID>> &,std::vector<std::unique_ptr<ushort,release::Deleter<release::aifree_tag>>,std::allocator<std::unique_ptr<ushort,release::Deleter<release::aifree_tag>>>> &,ulong &)

- ea: `0x140003330`
- end: `0x1400036f4`
- name: `?ConvertOnePlugin@@YAKPEAUHKEY__@@AEBV?$unique_ptr@GU?$Deleter@Uaifree_tag@release@@@release@@@std@@AEAV?$vector@UAPPID_PLUGIN_@@V?$allocator@UAPPID_PLUGIN_@@@std@@@3@AEAV?$vector@UAPPID_EXECUTION_CATEGORY_@@V?$allocator@UAPPID_EXECUTION_CATEGORY_@@@std@@@3@AEAV?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@3@AEAV?$vector@V?$unique_ptr@GU?$Deleter@Uaifree_tag@release@@@release@@@std@@V?$allocator@V?$unique_ptr@GU?$Deleter@Uaifree_tag@release@@@release@@@std@@@2@@3@AEAK@Z`
- size: `964`
- prototype: `__int64 __fastcall(HKEY hKey, wchar_t **, __int64, _QWORD *, __int64, _QWORD *, __int64)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, loader_planting`

## callees

- `0x14000112c`
- `0x1400013b8`
- `0x1400022ac`
- `0x140003330`
- `0x140005ebc`
- `0x140006e60`
- `0x140006f14`
- `0x140006fa0`
- `0x140007040`
- `0x140007d00`
- `0x140008ef4`
- `0x140013b10`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140003536`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140003536`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400033c5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400034ca`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400033c5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400034ca`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140003425`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140003425`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400033e8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000348a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400034ed`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000354a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140003569`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400036ad`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400036cc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400033e8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000348a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400034ed`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000354a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140003569`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400036ad`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400036cc`

## pseudocode

```c
__int64 __fastcall ConvertOnePlugin(
        HKEY hKey,
        wchar_t **a2,
        __int64 a3,
        _QWORD *a4,
        __int64 a5,
        _QWORD *a6,
        __int64 a7)
{
  unsigned int v11; // ebx
  HKEY v12; // rbx
  unsigned int StringValue; // edi
  HKEY v14; // rdi
  unsigned int v15; // esi
  unsigned int v16; // r8d
  __int64 v17; // r9
  __int64 v18; // rdx
  HKEY phkResult; // [rsp+60h] [rbp-91h] BYREF
  DWORD cbData; // [rsp+68h] [rbp-89h] BYREF
  __int64 v21; // [rsp+70h] [rbp-81h] BYREF
  DWORD Type; // [rsp+78h] [rbp-79h] BYREF
  DWORD cSubKeys; // [rsp+7Ch] [rbp-75h] BYREF
  int v24; // [rsp+80h] [rbp-71h] BYREF
  int v25; // [rsp+84h] [rbp-6Dh] BYREF
  HKEY hKeya; // [rsp+88h] [rbp-69h] BYREF
  HKEY v27; // [rsp+90h] [rbp-61h] BYREF
  __int64 v28; // [rsp+98h] [rbp-59h] BYREF
  __int64 v29; // [rsp+A0h] [rbp-51h] BYREF
  struct _GUID *v30; // [rsp+A8h] [rbp-49h] BYREF
  __int64 v31; // [rsp+B0h] [rbp-41h]
  struct _GUID v32; // [rsp+B8h] [rbp-39h] BYREF
  BYTE Data[24]; // [rsp+C8h] [rbp-29h] BYREF

  v31 = a3;
  cbData = 0;
  Type = 0;
  hKeya = 0;
  v32 = 0;
  memset(Data, 0, 20);
  if ( !(unsigned int)WSZtoGUID(*a2, &v32) )
    return 1010;
  phkResult = 0;
  v11 = RegOpenKeyExW(hKey, *a2, 0, 0x20019u, &phkResult);
  std::unique_ptr<HKEY__,release::Deleter<void>>::reset(&hKeya, phkResult);
  if ( v11 )
  {
    if ( hKeya )
      RegCloseKey(hKeya);
    return v11;
  }
  cbData = 4;
  v12 = hKeya;
  if ( !RegQueryValueExW(hKeya, L"Flags", 0, &Type, Data, &cbData) && (Type != 4 || cbData != 4) )
    *(_DWORD *)Data = 0;
  v21 = 0;
  phkResult = 0;
  StringValue = ReadStringValue(v12, L"Name", (unsigned __int16 **)&phkResult);
  std::unique_ptr<unsigned short,release::Deleter<release::aifree_tag>>::reset(&v21, phkResult);
  if ( StringValue )
    goto LABEL_12;
  std::vector<std::unique_ptr<unsigned short,release::Deleter<release::aifree_tag>>>::push_back(a6, &v21);
  v27 = 0;
  phkResult = 0;
  StringValue = RegOpenKeyExW(v12, L"ExecutionCategories", 0, 0x20019u, &phkResult);
  std::unique_ptr<HKEY__,release::Deleter<void>>::reset(&v27, phkResult);
  if ( StringValue )
  {
    if ( v27 )
      RegCloseKey(v27);
LABEL_12:
    if ( v21 )
      AiFree(v21);
    if ( v12 )
      RegCloseKey(v12);
    return StringValue;
  }
  cSubKeys = 0;
  v14 = v27;
  v15 = RegQueryInfoKeyW(v27, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
  if ( v15 )
    goto LABEL_21;
  if ( cSubKeys )
  {
    *(_DWORD *)&Data[16] = cSubKeys;
    *(_DWORD *)&Data[12] = -1227133513 * ((__int64)(a4[1] - *a4) >> 2);
    v15 = ForEachSubKeyCount<unsigned long (HKEY__ *,std::unique_ptr<unsigned short,release::Deleter<release::aifree_tag>> const &,std::vector<APPID_EXECUTION_CATEGORY_> &,std::vector<_GUID> &,unsigned long &),std::vector<APPID_EXECUTION_CATEGORY_> &,std::vector<_GUID> &,unsigned long &>(
            v14,
            a5,
            a7);
    if ( v15 )
    {
LABEL_21:
      if ( v14 )
        RegCloseKey(v14);
      if ( v21 )
        AiFree(v21);
      if ( v12 )
        RegCloseKey(v12);
      return v15;
    }
    if ( *(_DWORD *)&Data[16] )
    {
      do
      {
        if ( (unsigned int)dword_140020000 > 4 && (unsigned __int8)tlgKeywordOn(&dword_140020000) )
        {
          v18 = v17 + 28LL * v16;
          v24 = *(_DWORD *)(v18 + 24);
          v25 = *(_DWORD *)(v18 + 16);
          v28 = v18;
          LODWORD(phkResult) = *(_DWORD *)Data;
          v29 = *(_QWORD *)(*a6 + 8 * ((__int64)(a6[1] - *a6) >> 3) - 8);
          v30 = &v32;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            (unsigned int)&dword_140020000,
            (unsigned int)&word_14001A74E,
            (unsigned int)&ActivityId,
            v17,
            (__int64)&v30,
            (__int64)&v29,
            (__int64)&phkResult,
            (__int64)&v28,
            (__int64)&v25,
            (__int64)&v24);
        }
        ++v15;
      }
      while ( v15 < *(_DWORD *)&Data[16] );
    }
  }
  else
  {
    *(_QWORD *)&Data[12] = 0;
  }
  std::vector<APPID_PLUGIN_>::push_back(v31, &v32);
  if ( v14 )
    RegCloseKey(v14);
  if ( v21 )
    AiFree(v21);
  if ( v12 )
    RegCloseKey(v12);
  return 0;
}

```

## disassembly

```asm
0x140003330  push    rbp
0x140003332  push    rbx
0x140003333  push    rsi
0x140003334  push    rdi
0x140003335  push    r12
0x140003337  push    r13
0x140003339  push    r14
0x14000333b  push    r15
0x14000333d  lea     rbp, [rsp-7]
0x140003342  sub     rsp, 0F8h
0x140003349  mov     rax, cs:__security_cookie
0x140003350  xor     rax, rsp
0x140003353  mov     [rbp+3Fh+var_50], rax
0x140003357  mov     r14, r9
0x14000335a  mov     [rbp+3Fh+var_80], r8
0x14000335e  mov     rbx, rdx
0x140003361  mov     rdi, rcx
0x140003364  mov     r12, [rbp+3Fh+arg_20]
0x140003368  mov     r15, [rbp+3Fh+arg_28]
0x14000336c  mov     r13, [rbp+3Fh+arg_30]
0x140003370  xor     esi, esi
0x140003372  mov     [rsp+130h+cbData], esi
0x140003376  mov     [rbp+3Fh+Type], esi
0x140003379  mov     [rbp+3Fh+hKey], rsi
0x14000337d  xorps   xmm0, xmm0
0x140003380  xor     eax, eax
0x140003382  movups  xmmword ptr [rbp+3Fh+var_78.Data1], xmm0
0x140003386  movups  xmmword ptr [rbp+3Fh+Data], xmm0
0x14000338a  mov     [rbp+3Fh+var_58], eax
0x14000338d  lea     rdx, [rbp+3Fh+var_78]; struct _GUID *
0x140003391  mov     rcx, [rbx]; Buffer
0x140003394  call    ?WSZtoGUID@@YAHPEBGPEAU_GUID@@@Z; WSZtoGUID(ushort const *,_GUID *)
0x140003399  test    eax, eax
0x14000339b  jnz     short loc_1400033A7
0x14000339d  mov     eax, 3F2h
0x1400033a2  jmp     loc_1400036D4
0x1400033a7  mov     [rsp+130h+var_D0], rsi
0x1400033ac  lea     rax, [rsp+130h+var_D0]
0x1400033b1  mov     [rsp+130h+phkResult], rax; phkResult
0x1400033b6  mov     r9d, 20019h; samDesired
0x1400033bc  xor     r8d, r8d; ulOptions
0x1400033bf  mov     rdx, [rbx]; lpSubKey
0x1400033c2  mov     rcx, rdi; hKey
0x1400033c5  call    cs:__imp_RegOpenKeyExW
0x1400033cb  mov     ebx, eax
0x1400033cd  mov     rdx, [rsp+130h+var_D0]
0x1400033d2  lea     rcx, [rbp+3Fh+hKey]
0x1400033d6  call    ?reset@?$unique_ptr@UHKEY__@@U?$Deleter@X@release@@@std@@QEAAXPEAUHKEY__@@@Z; std::unique_ptr<HKEY__,release::Deleter<void>>::reset(HKEY__ *)
0x1400033db  test    ebx, ebx
0x1400033dd  jz      short loc_1400033F5
0x1400033df  mov     rcx, [rbp+3Fh+hKey]; hKey
0x1400033e3  test    rcx, rcx
0x1400033e6  jz      short loc_1400033EE
0x1400033e8  call    cs:__imp_RegCloseKey
0x1400033ee  mov     eax, ebx
0x1400033f0  jmp     loc_1400036D4
0x1400033f5  mov     [rsp+130h+cbData], 4
0x1400033fd  lea     rax, [rsp+130h+cbData]
0x140003402  mov     [rsp+130h+lpcbData], rax; lpcbData
0x140003407  lea     rax, [rbp+3Fh+Data]
0x14000340b  mov     [rsp+130h+phkResult], rax; lpData
0x140003410  lea     r9, [rbp+3Fh+Type]; lpType
0x140003414  xor     r8d, r8d; lpReserved
0x140003417  lea     rdx, ValueName; "Flags"
0x14000341e  mov     rbx, [rbp+3Fh+hKey]
0x140003422  mov     rcx, rbx; hKey
0x140003425  call    cs:__imp_RegQueryValueExW
0x14000342b  test    eax, eax
0x14000342d  jnz     short loc_14000343F
0x14000342f  cmp     [rbp+3Fh+Type], 4
0x140003433  jnz     short loc_14000343C
0x140003435  cmp     [rsp+130h+cbData], 4
0x14000343a  jz      short loc_14000343F
0x14000343c  mov     dword ptr [rbp+3Fh+Data], esi
0x14000343f  mov     [rsp+130h+var_C0], rsi
0x140003444  mov     [rsp+130h+var_D0], rsi
0x140003449  lea     r8, [rsp+130h+var_D0]; unsigned __int16 **
0x14000344e  lea     rdx, aName; "Name"
0x140003455  mov     rcx, rbx; hKey
0x140003458  call    ?ReadStringValue@@YAKPEAUHKEY__@@PEBGPEAPEAG@Z; ReadStringValue(HKEY__ *,ushort const *,ushort * *)
0x14000345d  mov     edi, eax
0x14000345f  mov     rdx, [rsp+130h+var_D0]
0x140003464  lea     rcx, [rsp+130h+var_C0]
0x140003469  call    ?reset@?$unique_ptr@GU?$Deleter@Uaifree_tag@release@@@release@@@std@@QEAAXPEAG@Z; std::unique_ptr<ushort,release::Deleter<release::aifree_tag>>::reset(ushort *)
0x14000346e  test    edi, edi
0x140003470  jz      short loc_140003497
0x140003472  mov     rcx, [rsp+130h+var_C0]
0x140003477  test    rcx, rcx
0x14000347a  jz      short loc_140003482
0x14000347c  call    AiFree
0x140003481  nop
0x140003482  test    rbx, rbx
0x140003485  jz      short loc_140003490
0x140003487  mov     rcx, rbx; hKey
0x14000348a  call    cs:__imp_RegCloseKey
0x140003490  mov     eax, edi
0x140003492  jmp     loc_1400036D4
0x140003497  lea     rdx, [rsp+130h+var_C0]
0x14000349c  mov     rcx, r15
0x14000349f  call    ?push_back@?$vector@V?$unique_ptr@GU?$Deleter@Uaifree_tag@release@@@release@@@std@@V?$allocator@V?$unique_ptr@GU?$Deleter@Uaifree_tag@release@@@release@@@std@@@2@@std@@QEAAX$$QEAV?$unique_ptr@GU?$Deleter@Uaifree_tag@release@@@release@@@2@@Z; std::vector<std::unique_ptr<ushort,release::Deleter<release::aifree_tag>>>::push_back(std::unique_ptr<ushort,release::Deleter<release::aifree_tag>> &&)
0x1400034a4  mov     [rbp+3Fh+var_A0], rsi
0x1400034a8  mov     [rsp+130h+var_D0], rsi
0x1400034ad  lea     rax, [rsp+130h+var_D0]
0x1400034b2  mov     [rsp+130h+phkResult], rax; phkResult
0x1400034b7  mov     r9d, 20019h; samDesired
0x1400034bd  xor     r8d, r8d; ulOptions
0x1400034c0  lea     rdx, aExecutioncateg; "ExecutionCategories"
0x1400034c7  mov     rcx, rbx; hKey
0x1400034ca  call    cs:__imp_RegOpenKeyExW
0x1400034d0  mov     edi, eax
0x1400034d2  mov     rdx, [rsp+130h+var_D0]
0x1400034d7  lea     rcx, [rbp+3Fh+var_A0]
0x1400034db  call    ?reset@?$unique_ptr@UHKEY__@@U?$Deleter@X@release@@@std@@QEAAXPEAUHKEY__@@@Z; std::unique_ptr<HKEY__,release::Deleter<void>>::reset(HKEY__ *)
0x1400034e0  test    edi, edi
0x1400034e2  jz      short loc_1400034F8
0x1400034e4  mov     rcx, [rbp+3Fh+var_A0]; hKey
0x1400034e8  test    rcx, rcx
0x1400034eb  jz      short loc_140003472
0x1400034ed  call    cs:__imp_RegCloseKey
0x1400034f3  jmp     loc_140003472
0x1400034f8  mov     [rbp+3Fh+cSubKeys], esi
0x1400034fb  mov     [rsp+130h+lpftLastWriteTime], rsi; lpftLastWriteTime
0x140003500  mov     [rsp+130h+lpcbSecurityDescriptor], rsi; lpcbSecurityDescriptor
0x140003505  mov     [rsp+130h+lpcbMaxValueLen], rsi; lpcbMaxValueLen
0x14000350a  mov     [rsp+130h+lpcbMaxValueNameLen], rsi; lpcbMaxValueNameLen
0x14000350f  mov     [rsp+130h+lpcValues], rsi; lpcValues
0x140003514  mov     [rsp+130h+lpcbMaxClassLen], rsi; lpcbMaxClassLen
0x140003519  mov     [rsp+130h+lpcbData], rsi; lpcbMaxSubKeyLen
0x14000351e  lea     rax, [rbp+3Fh+cSubKeys]
0x140003522  mov     [rsp+130h+phkResult], rax; lpcSubKeys
0x140003527  xor     r9d, r9d; lpReserved
0x14000352a  xor     r8d, r8d; lpcchClass
0x14000352d  xor     edx, edx; lpClass
0x14000352f  mov     rdi, [rbp+3Fh+var_A0]
0x140003533  mov     rcx, rdi; hKey
0x140003536  call    cs:__imp_RegQueryInfoKeyW
0x14000353c  mov     esi, eax
0x14000353e  test    eax, eax
0x140003540  jz      short loc_140003576
0x140003542  test    rdi, rdi
0x140003545  jz      short loc_140003551
0x140003547  mov     rcx, rdi; hKey
0x14000354a  call    cs:__imp_RegCloseKey
0x140003550  nop
0x140003551  mov     rcx, [rsp+130h+var_C0]
0x140003556  test    rcx, rcx
0x140003559  jz      short loc_140003561
0x14000355b  call    AiFree
0x140003560  nop
0x140003561  test    rbx, rbx
0x140003564  jz      short loc_14000356F
0x140003566  mov     rcx, rbx; hKey
0x140003569  call    cs:__imp_RegCloseKey
0x14000356f  mov     eax, esi
0x140003571  jmp     loc_1400036D4
0x140003576  mov     edx, [rbp+3Fh+cSubKeys]
0x140003579  test    edx, edx
0x14000357b  jz      loc_14000368F
0x140003581  mov     [rbp+3Fh+var_58], edx
0x140003584  mov     rax, [r14+8]
0x140003588  sub     rax, [r14]
0x14000358b  sar     rax, 2
0x14000358f  mov     rcx, 6DB6DB6DB6DB6DB7h
0x140003599  imul    rax, rcx
0x14000359d  mov     dword ptr [rbp+3Fh+Data+0Ch], eax
0x1400035a0  mov     [rsp+130h+lpcbData], r13; __int64
0x1400035a5  mov     [rsp+130h+phkResult], r12; __int64
0x1400035aa  mov     r9, r14
0x1400035ad  mov     rcx, rdi; hKey
0x1400035b0  call    ??$ForEachSubKeyCount@$$A6AKPEAUHKEY__@@AEBV?$unique_ptr@GU?$Deleter@Uaifree_tag@release@@@release@@@std@@AEAV?$vector@UAPPID_EXECUTION_CATEGORY_@@V?$allocator@UAPPID_EXECUTION_CATEGORY_@@@std@@@3@AEAV?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@3@AEAK@ZAEAV43@AEAV53@AEAK@@YAKPEAUHKEY__@@KA6AK0AEBV?$unique_ptr@GU?$Deleter@Uaifree_tag@release@@@release@@@std@@AEAV?$vector@UAPPID_EXECUTION_CATEGORY_@@V?$allocator@UAPPID_EXECUTION_CATEGORY_@@@std@@@2@AEAV?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@2@AEAK@Z234@Z; ForEachSubKeyCount<ulong (HKEY__ *,std::unique_ptr<ushort,release::Deleter<release::aifree_tag>> const &,std::vector<APPID_EXECUTION_CATEGORY_> &,std::vector<_GUID> &,ulong &),std::vector<APPID_EXECUTION_CATEGORY_> &,std::vector<_GUID> &,ulong &>(HKEY__ *,ulong,ulong (&)(HKEY__ *,std::unique_ptr<ushort,release::Deleter<release::aifree_tag>> const &,std::vector<APPID_EXECUTION_CATEGORY_> &,std::vector<_GUID> &,ulong &),std::vector<APPID_EXECUTION_CATEGORY_> &,std::vector<_GUID> &,ulong &)
0x1400035b5  mov     esi, eax
0x1400035b7  test    eax, eax
0x1400035b9  jnz     short loc_140003542
0x1400035bb  cmp     [rbp+3Fh+var_58], eax
0x1400035be  jbe     loc_140003697
0x1400035c4  mov     r8d, dword ptr [rbp+3Fh+Data+0Ch]
0x1400035c8  add     r8d, esi
0x1400035cb  mov     r9, [r14]
0x1400035ce  mov     eax, cs:dword_140020000
0x1400035d4  cmp     eax, 4
0x1400035d7  jbe     loc_140003682
0x1400035dd  lea     rcx, dword_140020000
0x1400035e4  call    _tlgKeywordOn
0x1400035e9  test    al, al
0x1400035eb  jz      loc_140003682
0x1400035f1  mov     eax, r8d
0x1400035f4  imul    rdx, rax, 1Ch
0x1400035f8  add     rdx, r9
0x1400035fb  mov     eax, [rdx+18h]
0x1400035fe  mov     [rbp+3Fh+var_B0], eax
0x140003601  mov     eax, [rdx+10h]
0x140003604  mov     [rbp+3Fh+var_AC], eax
0x140003607  mov     [rbp+3Fh+var_98], rdx
0x14000360b  mov     eax, dword ptr [rbp+3Fh+Data]
0x14000360e  mov     dword ptr [rsp+130h+var_D0], eax
0x140003612  mov     rcx, [r15]
0x140003615  mov     rax, [r15+8]
0x140003619  sub     rax, rcx
0x14000361c  sar     rax, 3
0x140003620  mov     rax, [rcx+rax*8-8]
0x140003625  mov     [rbp+3Fh+var_90], rax
0x140003629  lea     rax, [rbp+3Fh+var_78]
0x14000362d  mov     [rbp+3Fh+var_88], rax
0x140003631  lea     rax, [rbp+3Fh+var_B0]
0x140003635  mov     [rsp+130h+lpcbMaxValueLen], rax
0x14000363a  lea     rax, [rbp+3Fh+var_AC]
0x14000363e  mov     [rsp+130h+lpcbMaxValueNameLen], rax
0x140003643  lea     rax, [rbp+3Fh+var_98]
0x140003647  mov     [rsp+130h+lpcValues], rax
0x14000364c  lea     rax, [rsp+130h+var_D0]
0x140003651  mov     [rsp+130h+lpcbMaxClassLen], rax
0x140003656  lea     rax, [rbp+3Fh+var_90]
0x14000365a  mov     [rsp+130h+lpcbData], rax
0x14000365f  lea     rax, [rbp+3Fh+var_88]
0x140003663  mov     [rsp+130h+phkResult], rax
0x140003668  lea     r8, ActivityId
0x14000366f  lea     rdx, word_14001A74E
0x140003676  lea     rcx, dword_140020000
0x14000367d  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U1@U3@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@355@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140003682  inc     esi
0x140003684  cmp     esi, [rbp+3Fh+var_58]
0x140003687  jb      loc_1400035C4
0x14000368d  jmp     short loc_140003697
0x14000368f  mov     qword ptr [rbp+3Fh+Data+0Ch], 0
0x140003697  lea     rdx, [rbp+3Fh+var_78]
0x14000369b  mov     rcx, [rbp+3Fh+var_80]
0x14000369f  call    ?push_back@?$vector@UAPPID_PLUGIN_@@V?$allocator@UAPPID_PLUGIN_@@@std@@@std@@QEAAXAEBUAPPID_PLUGIN_@@@Z; std::vector<APPID_PLUGIN_>::push_back(APPID_PLUGIN_ const &)
0x1400036a4  nop
0x1400036a5  test    rdi, rdi
0x1400036a8  jz      short loc_1400036B4
0x1400036aa  mov     rcx, rdi; hKey
0x1400036ad  call    cs:__imp_RegCloseKey
0x1400036b3  nop
0x1400036b4  mov     rcx, [rsp+130h+var_C0]
0x1400036b9  test    rcx, rcx
0x1400036bc  jz      short loc_1400036C4
0x1400036be  call    AiFree
0x1400036c3  nop
0x1400036c4  test    rbx, rbx
0x1400036c7  jz      short loc_1400036D2
0x1400036c9  mov     rcx, rbx; hKey
0x1400036cc  call    cs:__imp_RegCloseKey
0x1400036d2  xor     eax, eax
0x1400036d4  mov     rcx, [rbp+3Fh+var_50]
0x1400036d8  xor     rcx, rsp; StackCookie
0x1400036db  call    __security_check_cookie
0x1400036e0  add     rsp, 0F8h
0x1400036e7  pop     r15
0x1400036e9  pop     r14
0x1400036eb  pop     r13
0x1400036ed  pop     r12
0x1400036ef  pop     rdi
0x1400036f0  pop     rsi
0x1400036f1  pop     rbx
0x1400036f2  pop     rbp
0x1400036f3  retn
```
