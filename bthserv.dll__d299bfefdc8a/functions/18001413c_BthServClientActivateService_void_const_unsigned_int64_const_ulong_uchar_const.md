# BthServClientActivateService(void * const,unsigned __int64 const *,ulong,uchar * const)

- ea: `0x18001413c`
- end: `0x18001472c`
- name: `?BthServClientActivateService@@YAKQEAXPEB_KKQEAE@Z`
- size: `1520`
- prototype: `__int64 __fastcall(void *const, const unsigned __int64 *, DWORD, unsigned __int8 *const)`
- caller_count: `2`
- callee_count: `22`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180011f90`
- `0x180025e24`

## callees

- `0x180001790`
- `0x1800024ac`
- `0x1800086d8`
- `0x180010cac`
- `0x180013644`
- `0x180013970`
- `0x180013aa8`
- `0x180013bd4`
- `0x180013dd0`
- `0x180013efc`
- `0x180013f88`
- `0x18001413c`
- `0x180016664`
- `0x1800166f0`
- `0x180016710`
- `0x180016730`
- `0x180034034`
- `0x180034110`
- `0x18003428c`
- `0x180034300`
- `0x180034d20`
- `0x1800350bc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180014513`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180014513`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800145ec`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800145ec`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800145cc`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800145cc`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180014239`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x1800142f8`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180014239`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x1800142f8`

## string_xrefs

- `0x18001422b`: `System\CurrentControlSet\Services\BTHPORT\Parameters`
- `0x1800142ea`: `System\CurrentControlSet\Services\BTHPORT\Parameters`
- `0x180014649`: `onecore\drivers\wdm\bluetooth\user\bthserv\server\dll\db.cpp`
- `0x18001465d`: `onecore\drivers\wdm\bluetooth\user\bthserv\server\dll\db.cpp`
- `0x180014671`: `onecore\drivers\wdm\bluetooth\user\bthserv\server\dll\db.cpp`
- `0x180014685`: `onecore\drivers\wdm\bluetooth\user\bthserv\server\dll\db.cpp`
- `0x1800146dd`: `onecore\drivers\wdm\bluetooth\user\bthserv\server\dll\db.cpp`
- `0x1800146f1`: `onecore\drivers\wdm\bluetooth\user\bthserv\server\dll\db.cpp`
- `0x180014705`: `onecore\drivers\wdm\bluetooth\user\bthserv\server\dll\db.cpp`
- `0x180014719`: `onecore\drivers\wdm\bluetooth\user\bthserv\server\dll\db.cpp`
- `0x18001444b`: `CachedServices`

## pseudocode

```c
__int64 __fastcall BthServClientActivateService(
        void *const a1,
        const unsigned __int64 *a2,
        DWORD a3,
        unsigned __int8 *const a4)
{
  bool v7; // al
  int v8; // eax
  int IsStreamRecord; // eax
  int v10; // eax
  int PersistedRegistryLocationW; // eax
  __int64 v12; // r8
  unsigned __int64 v13; // r9
  char *v14; // rbx
  unsigned int v15; // eax
  __int64 v16; // rdx
  __int64 v17; // r8
  char **v18; // r9
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rdx
  __int64 v22; // rax
  const WCHAR *v23; // rdx
  unsigned int v24; // eax
  int AttributeInStream; // eax
  __int64 v26; // r8
  __int64 v27; // r9
  unsigned int v28; // eax
  int v29; // eax
  unsigned int v30; // eax
  wil *v31; // rcx
  __int64 result; // rax
  signed int v33; // eax
  int dwOptions; // [rsp+20h] [rbp-1A8h]
  int dwOptionsa; // [rsp+20h] [rbp-1A8h]
  unsigned int dwOptionsb; // [rsp+20h] [rbp-1A8h]
  int dwOptionsc; // [rsp+20h] [rbp-1A8h]
  unsigned int dwOptionsd; // [rsp+20h] [rbp-1A8h]
  unsigned int v39[2]; // [rsp+50h] [rbp-178h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-170h] BYREF
  __int64 v41; // [rsp+60h] [rbp-168h]
  char *v42[2]; // [rsp+68h] [rbp-160h] BYREF
  __int64 v43; // [rsp+78h] [rbp-150h]
  unsigned __int64 v44; // [rsp+80h] [rbp-148h]
  LPCWSTR lpSubKey[4]; // [rsp+88h] [rbp-140h] BYREF
  char *v46[4]; // [rsp+A8h] [rbp-120h] BYREF
  char *v47[4]; // [rsp+C8h] [rbp-100h] BYREF
  char *v48[4]; // [rsp+E8h] [rbp-E0h] BYREF
  char *v49[4]; // [rsp+108h] [rbp-C0h] BYREF
  char *v50[4]; // [rsp+128h] [rbp-A0h] BYREF
  char *v51[4]; // [rsp+148h] [rbp-80h] BYREF
  void *v52[4]; // [rsp+168h] [rbp-60h] BYREF
  WCHAR ValueName[12]; // [rsp+188h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+0h]

  v7 = !a4 || a3 < 2;
  try
  {
    if ( v7 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x2DC,
        (unsigned int)"onecore\\drivers\\wdm\\bluetooth\\user\\bthserv\\server\\dll\\db.cpp",
        (const char *)0x80070057LL,
        dwOptions);
    v8 = SdpValidateStream((_DWORD)a4, a3, 0, 0, 0);
    if ( v8 < 0 )
      wil::details::in1diag3::_Throw_NtStatus(
        retaddr,
        (void *)0x2DF,
        (unsigned int)"onecore\\drivers\\wdm\\bluetooth\\user\\bthserv\\server\\dll\\db.cpp",
        (const char *)(unsigned int)v8,
        dwOptionsa);
    IsStreamRecord = SdpIsStreamRecord(a4, a3);
    if ( IsStreamRecord < 0 )
      wil::details::in1diag3::_Throw_NtStatus(
        retaddr,
        (void *)0x2E2,
        (unsigned int)"onecore\\drivers\\wdm\\bluetooth\\user\\bthserv\\server\\dll\\db.cpp",
        (const char *)(unsigned int)IsStreamRecord,
        dwOptionsa);
    LOWORD(v39[0]) = 0;
    v10 = SdpVerifyServiceRecord(a4);
    if ( v10 < 0 )
      wil::details::in1diag3::_Throw_NtStatus(
        retaddr,
        (void *)0x2E8,
        (unsigned int)"onecore\\drivers\\wdm\\bluetooth\\user\\bthserv\\server\\dll\\db.cpp",
        (const char *)(unsigned int)v10,
        dwOptionsa);
    memset(v52, 0, 24);
    v39[0] = 0;
    PersistedRegistryLocationW = GetPersistedRegistryLocationW(
                                   L"BluetoothBthPortParams",
                                   L"System\\CurrentControlSet\\Services\\BTHPORT\\Parameters",
                                   0,
                                   0);
    if ( PersistedRegistryLocationW > 0 )
      v13 = (unsigned __int16)PersistedRegistryLocationW | 0x80070000;
    else
      v13 = (unsigned int)PersistedRegistryLocationW;
    if ( PersistedRegistryLocationW != 234 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x20,
        (unsigned int)"onecore\\drivers\\bluetooth\\foundation\\lib\\StateLocationHelpers.h",
        (const char *)v13,
        (int)v39);
    LODWORD(v14) = v52[1];
    if ( (void *)v39[0] < (void *)((char *)v52[1] - (char *)v52[0]) )
    {
      v14 = (char *)v52[0] + v39[0];
LABEL_19:
      v52[1] = v14;
      goto LABEL_20;
    }
    if ( (void *)v39[0] > (void *)((char *)v52[1] - (char *)v52[0]) )
    {
      if ( (void *)v39[0] <= (void *)((char *)v52[2] - (char *)v52[0]) )
      {
        memset_0(v52[1], 0, v39[0] - (unsigned __int64)((char *)v52[1] - (char *)v52[0]));
        v14 = (char *)v52[0] + v39[0];
        goto LABEL_19;
      }
      std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(v52, v39[0], v12, v13);
      LODWORD(v14) = v52[1];
    }
LABEL_20:
    v15 = GetPersistedRegistryLocationW(
            L"BluetoothBthPortParams",
            L"System\\CurrentControlSet\\Services\\BTHPORT\\Parameters",
            v52[0],
            (unsigned int)((_DWORD)v14 - LODWORD(v52[0])));
    if ( v15 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x29,
        (unsigned int)"onecore\\drivers\\bluetooth\\foundation\\lib\\StateLocationHelpers.h",
        (const char *)v15,
        (unsigned int)v39);
    std::wstring::wstring(v42, v52[0]);
    std::vector<unsigned char>::~vector<unsigned char>(v52);
    memset(v52, 0, 26);
    StringCchPrintfW((unsigned __int16 *)v52, 0xDu, L"%012llX", *a2 & 0xFFFFFFFFFFFFLL);
    std::wstring::wstring(v48, v52);
    if ( v43 == 0x7FFFFFFFFFFFFFFELL )
      std::_Xlen_string();
    v18 = v42;
    if ( v44 > 7 )
      v18 = (char **)v42[0];
    std::wstring::wstring(v47, v16, v17, v18, v43);
    v19 = std::operator+<unsigned short>(v51, v47, L"Devices");
    v20 = std::operator+<unsigned short>(v50, v19, L"\\");
    std::wstring::wstring(v46, v21, v20, v48);
    v22 = std::operator+<unsigned short>(v49, v46, L"\\");
    std::operator+<unsigned short>(lpSubKey, v22, L"CachedServices");
    std::wstring::~wstring(v49);
    std::wstring::~wstring(v46);
    std::wstring::~wstring(v50);
    std::wstring::~wstring(v51);
    std::wstring::~wstring(v47);
    std::wstring::~wstring(v48);
    hKey = 0;
    v23 = (const WCHAR *)lpSubKey;
    if ( lpSubKey[3] > (LPCWSTR)7 )
      v23 = lpSubKey[0];
    v24 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v23, 0, 0, 0, 0xF003Fu, 0, &hKey, 0);
    if ( v24 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x2FC,
        (unsigned int)"onecore\\drivers\\wdm\\bluetooth\\user\\bthserv\\server\\dll\\db.cpp",
        (const char *)v24,
        dwOptionsb);
    v41 = 0;
    AttributeInStream = SdpFindAttributeInStream(a4, (__int64)v39);
    if ( AttributeInStream < 0 )
      wil::details::in1diag3::_Throw_NtStatus(
        retaddr,
        (void *)0x301,
        (unsigned int)"onecore\\drivers\\wdm\\bluetooth\\user\\bthserv\\server\\dll\\db.cpp",
        (const char *)(unsigned int)AttributeInStream,
        dwOptionsc);
    v39[0] = 0;
    SdpRetrieveUint32(v41 + 1, v39, v26, v27);
    v28 = SdpByteSwapUint32(v39[0]);
    v29 = StringCbPrintfW(ValueName, 0x12u, L"%08x", v28);
    if ( v29 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x30F,
        (unsigned int)"onecore\\drivers\\wdm\\bluetooth\\user\\bthserv\\server\\dll\\db.cpp",
        (const char *)(unsigned int)v29,
        dwOptionsc);
    v30 = RegSetValueExW(hKey, ValueName, 0, 3u, a4, a3);
    if ( v30 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x311,
        (unsigned int)"onecore\\drivers\\wdm\\bluetooth\\user\\bthserv\\server\\dll\\db.cpp",
        (const char *)v30,
        dwOptionsd);
    if ( hKey )
      RegCloseKey(hKey);
    std::wstring::~wstring((char **)lpSubKey);
    std::wstring::~wstring(v42);
    result = 0;
  }
  catch ( ... )
  {
    v33 = wil::ResultFromCaughtException(v31);
    if ( v33 < 0 )
    {
      if ( (v33 & 0x1FFF0000) == 0x70000 )
      {
        v33 = (unsigned __int16)v33;
      }
      else
      {
        if ( (v33 & 0x10000000) == 0 )
          return 87;
        v33 = RtlNtStatusToDosErrorNoTeb(v33 & 0xEFFFFFFF);
      }
      v39[0] = v33;
    }
    else
    {
      v39[0] = 0;
    }
    return v39[0];
  }
  return result;
}

```

## disassembly

```asm
0x18001413c  mov     [rsp+arg_0], rbx
0x180014141  mov     [rsp+arg_8], rsi
0x180014146  push    rdi
0x180014147  push    r14
0x180014149  push    r15
0x18001414b  sub     rsp, 1B0h
0x180014152  mov     rax, cs:__security_cookie
0x180014159  xor     rax, rsp
0x18001415c  mov     [rsp+1C8h+var_28], rax
0x180014164  mov     r14, r9
0x180014167  mov     esi, r8d
0x18001416a  mov     r15, rdx
0x18001416d  test    r9, r9
0x180014170  jz      short loc_18001417C
0x180014172  cmp     r8d, 2
0x180014176  jb      short loc_18001417C
0x180014178  xor     al, al
0x18001417a  jmp     short loc_18001417E
0x18001417c  mov     al, 1
0x18001417e  mov     rcx, [rsp+1C8h]; this
0x180014186  test    al, al
0x180014188  jnz     loc_180014643
0x18001418e  mov     qword ptr [rsp+1C8h+dwOptions], 0; int
0x180014197  xor     r9d, r9d
0x18001419a  xor     r8d, r8d
0x18001419d  mov     edx, esi
0x18001419f  mov     rcx, r14
0x1800141a2  call    SdpValidateStream
0x1800141a7  mov     rcx, [rsp+1C8h]; this
0x1800141af  test    eax, eax
0x1800141b1  js      loc_18001465A
0x1800141b7  mov     edx, esi
0x1800141b9  mov     rcx, r14
0x1800141bc  call    SdpIsStreamRecord
0x1800141c1  mov     rcx, [rsp+1C8h]; this
0x1800141c9  test    eax, eax
0x1800141cb  js      loc_18001466E
0x1800141d1  xor     eax, eax
0x1800141d3  mov     word ptr [rsp+1C8h+var_178], ax
0x1800141d8  lea     r9, [rsp+1C8h+var_178]
0x1800141dd  lea     r8d, [rax+4]
0x1800141e1  mov     edx, esi
0x1800141e3  mov     rcx, r14; unsigned __int8 *
0x1800141e6  call    SdpVerifyServiceRecord
0x1800141eb  mov     rcx, [rsp+1C8h]; this
0x1800141f3  test    eax, eax
0x1800141f5  js      loc_180014682
0x1800141fb  xorps   xmm0, xmm0
0x1800141fe  movdqu  xmmword ptr [rsp+1C8h+var_60], xmm0
0x180014207  mov     [rsp+1C8h+var_50], 0
0x180014213  mov     [rsp+1C8h+var_178], 0
0x18001421b  lea     rax, [rsp+1C8h+var_178]
0x180014220  mov     qword ptr [rsp+1C8h+dwOptions], rax; int
0x180014225  xor     r9d, r9d
0x180014228  xor     r8d, r8d
0x18001422b  lea     rdx, aSystemCurrentc_5; "System\\CurrentControlSet\\Services\\BT"...
0x180014232  lea     rcx, aBluetoothbthpo; "BluetoothBthPortParams"
0x180014239  call    cs:__imp_GetPersistedRegistryLocationW
0x18001423f  test    eax, eax
0x180014241  jg      short loc_180014248
0x180014243  mov     r9d, eax
0x180014246  jmp     short loc_180014253
0x180014248  movzx   r9d, ax
0x18001424c  or      r9d, 80070000h; char *
0x180014253  mov     rcx, [rsp+1C8h]; this
0x18001425b  cmp     eax, 0EAh
0x180014260  jnz     loc_180014697
0x180014266  mov     edi, [rsp+1C8h+var_178]
0x18001426a  mov     rdx, [rsp+1C8h+var_60]
0x180014272  mov     rbx, [rsp+1C8h+var_60+8]
0x18001427a  mov     rcx, rbx
0x18001427d  sub     rcx, rdx
0x180014280  cmp     rdi, rcx
0x180014283  jnb     short loc_18001428B
0x180014285  lea     rbx, [rdi+rdx]
0x180014289  jmp     short loc_1800142CA
0x18001428b  jbe     short loc_1800142D2
0x18001428d  mov     rax, [rsp+1C8h+var_50]
0x180014295  sub     rax, rdx
0x180014298  cmp     rdi, rax
0x18001429b  jbe     short loc_1800142B7
0x18001429d  mov     rdx, rdi
0x1800142a0  lea     rcx, [rsp+1C8h+var_60]
0x1800142a8  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x1800142ad  mov     rbx, [rsp+1C8h+var_60+8]
0x1800142b5  jmp     short loc_1800142D2
0x1800142b7  sub     rdi, rcx
0x1800142ba  mov     r8, rdi; Size
0x1800142bd  xor     edx, edx; Val
0x1800142bf  mov     rcx, rbx; void *
0x1800142c2  call    memset_0
0x1800142c7  add     rbx, rdi
0x1800142ca  mov     [rsp+1C8h+var_60+8], rbx
0x1800142d2  mov     r8, [rsp+1C8h+var_60]
0x1800142da  sub     ebx, r8d
0x1800142dd  lea     rax, [rsp+1C8h+var_178]
0x1800142e2  mov     qword ptr [rsp+1C8h+dwOptions], rax; int
0x1800142e7  mov     r9d, ebx
0x1800142ea  lea     rdx, aSystemCurrentc_5; "System\\CurrentControlSet\\Services\\BT"...
0x1800142f1  lea     rcx, aBluetoothbthpo; "BluetoothBthPortParams"
0x1800142f8  call    cs:__imp_GetPersistedRegistryLocationW
0x1800142fe  mov     rcx, [rsp+1C8h]; this
0x180014306  test    eax, eax
0x180014308  jnz     loc_1800146A8
0x18001430e  mov     rcx, [rsp+1C8h]; this
0x180014316  test    byte ptr [rsp+1C8h+var_178], 1
0x18001431b  jnz     loc_1800146BC
0x180014321  mov     rdx, [rsp+1C8h+var_60]
0x180014329  lea     rcx, [rsp+1C8h+var_160]
0x18001432e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180014333  nop
0x180014334  lea     rcx, [rsp+1C8h+var_60]
0x18001433c  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x180014341  nop
0x180014342  xorps   xmm0, xmm0
0x180014345  movups  xmmword ptr [rsp+1C8h+var_60], xmm0
0x18001434d  movups  xmmword ptr [rsp+1C8h+var_60+0Ah], xmm0
0x180014355  mov     r9, [r15]
0x180014358  mov     rax, 0FFFFFFFFFFFFh
0x180014362  and     r9, rax
0x180014365  lea     r8, ?c_addressStringFormat@?1??to_wstring_macaddress@wil@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K@Z@4QBGB; "%012llX"
0x18001436c  mov     edx, 0Dh; unsigned __int64
0x180014371  lea     rcx, [rsp+1C8h+var_60]; unsigned __int16 *
0x180014379  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001437e  lea     rdx, [rsp+1C8h+var_60]
0x180014386  lea     rcx, [rsp+1C8h+var_E0]
0x18001438e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180014393  nop
0x180014394  mov     rcx, [rsp+1C8h+var_150]
0x180014399  mov     rax, 7FFFFFFFFFFFFFFEh
0x1800143a3  sub     rax, rcx
0x1800143a6  cmp     rax, 1
0x1800143aa  jb      loc_1800146D4
0x1800143b0  lea     r9, [rsp+1C8h+var_160]
0x1800143b5  cmp     [rsp+1C8h+var_148], 7
0x1800143be  cmova   r9, [rsp+1C8h+var_160]
0x1800143c4  mov     [rsp+1C8h+lpSecurityAttributes], 1
0x1800143cd  mov     qword ptr [rsp+1C8h+dwOptions], rcx
0x1800143d2  lea     rcx, [rsp+1C8h+var_100]
0x1800143da  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x1800143df  nop
0x1800143e0  lea     r8, aDevices; "Devices"
0x1800143e7  lea     rdx, [rsp+1C8h+var_100]
0x1800143ef  lea     rcx, [rsp+1C8h+var_80]
0x1800143f7  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x1800143fc  nop
0x1800143fd  lea     r8, psz; "\\"
0x180014404  mov     rdx, rax
0x180014407  lea     rcx, [rsp+1C8h+var_A0]
0x18001440f  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x180014414  nop
0x180014415  lea     r9, [rsp+1C8h+var_E0]
0x18001441d  mov     r8, rax
0x180014420  lea     rcx, [rsp+1C8h+var_120]
0x180014428  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring &,std::wstring &)
0x18001442d  nop
0x18001442e  lea     r8, psz; "\\"
0x180014435  lea     rdx, [rsp+1C8h+var_120]
0x18001443d  lea     rcx, [rsp+1C8h+var_C0]
0x180014445  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x18001444a  nop
0x18001444b  lea     r8, aCachedservices; "CachedServices"
0x180014452  mov     rdx, rax
0x180014455  lea     rcx, [rsp+1C8h+lpSubKey]
0x18001445d  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x180014462  nop
0x180014463  lea     rcx, [rsp+1C8h+var_C0]
0x18001446b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180014470  nop
0x180014471  lea     rcx, [rsp+1C8h+var_120]
0x180014479  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001447e  nop
0x18001447f  lea     rcx, [rsp+1C8h+var_A0]
0x180014487  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001448c  nop
0x18001448d  lea     rcx, [rsp+1C8h+var_80]
0x180014495  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001449a  nop
0x18001449b  lea     rcx, [rsp+1C8h+var_100]
0x1800144a3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800144a8  nop
0x1800144a9  lea     rcx, [rsp+1C8h+var_E0]
0x1800144b1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800144b6  nop
0x1800144b7  mov     [rsp+1C8h+hKey], 0
0x1800144c0  lea     rdx, [rsp+1C8h+lpSubKey]
0x1800144c8  cmp     [rsp+1C8h+var_128], 7
0x1800144d1  cmova   rdx, [rsp+1C8h+lpSubKey]; lpSubKey
0x1800144da  mov     [rsp+1C8h+lpdwDisposition], 0; lpdwDisposition
0x1800144e3  lea     rax, [rsp+1C8h+hKey]
0x1800144e8  mov     [rsp+1C8h+phkResult], rax; phkResult
0x1800144ed  mov     [rsp+1C8h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800144f6  mov     [rsp+1C8h+samDesired], 0F003Fh; samDesired
0x1800144fe  mov     [rsp+1C8h+dwOptions], 0; unsigned int
0x180014506  xor     r9d, r9d; lpClass
0x180014509  xor     r8d, r8d; Reserved
0x18001450c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180014513  call    cs:__imp_RegCreateKeyExW
0x180014519  mov     rcx, [rsp+1C8h]; this
0x180014521  test    eax, eax
0x180014523  jnz     loc_1800146DA
0x180014529  mov     [rsp+1C8h+var_168], 0
0x180014532  xor     r8d, r8d
0x180014535  lea     rax, [rsp+1C8h+var_178]
0x18001453a  mov     qword ptr [rsp+1C8h+dwOptions], rax; int
0x18001453f  lea     r9, [rsp+1C8h+var_168]
0x180014544  mov     edx, esi
0x180014546  mov     rcx, r14; unsigned __int8 *
0x180014549  call    SdpFindAttributeInStream
0x18001454e  mov     rcx, [rsp+1C8h]; this
0x180014556  test    eax, eax
0x180014558  js      loc_1800146EE
0x18001455e  mov     rcx, [rsp+1C8h+var_168]
0x180014563  inc     rcx
0x180014566  mov     [rsp+1C8h+var_178], 0
0x18001456e  lea     rdx, [rsp+1C8h+var_178]
0x180014573  call    SdpRetrieveUint32
0x180014578  mov     ecx, [rsp+1C8h+var_178]
0x18001457c  call    SdpByteSwapUint32
0x180014581  mov     r9d, eax
0x180014584  lea     r8, a08x; "%08x"
0x18001458b  mov     edx, 12h; unsigned __int64
0x180014590  lea     rcx, [rsp+1C8h+ValueName]; unsigned __int16 *
0x180014598  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001459d  mov     rcx, [rsp+1C8h]; this
0x1800145a5  test    eax, eax
0x1800145a7  js      loc_180014702
0x1800145ad  mov     [rsp+1C8h+samDesired], esi; cbData
0x1800145b1  mov     qword ptr [rsp+1C8h+dwOptions], r14; unsigned int
0x1800145b6  mov     r9d, 3; dwType
0x1800145bc  xor     r8d, r8d; Reserved
0x1800145bf  lea     rdx, [rsp+1C8h+ValueName]; lpValueName
0x1800145c7  mov     rcx, [rsp+1C8h+hKey]; hKey
0x1800145cc  call    cs:__imp_RegSetValueExW
0x1800145d2  mov     rcx, [rsp+1C8h]; this
0x1800145da  test    eax, eax
0x1800145dc  jnz     loc_180014716
0x1800145e2  mov     rcx, [rsp+1C8h+hKey]; hKey
0x1800145e7  test    rcx, rcx
0x1800145ea  jz      short loc_1800145F3
0x1800145ec  call    cs:__imp_RegCloseKey
0x1800145f2  nop
0x1800145f3  lea     rcx, [rsp+1C8h+lpSubKey]
0x1800145fb  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180014600  nop
0x180014601  lea     rcx, [rsp+1C8h+var_160]
0x180014606  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001460b  xor     eax, eax
0x18001460d  jmp     short loc_18001461A
0x18001460f  mov     eax, [rsp+1C8h+var_178]
0x180014613  jmp     short loc_18001461A
0x180014615  mov     eax, 57h ; 'W'
0x18001461a  mov     rcx, [rsp+1C8h+var_28]
0x180014622  xor     rcx, rsp; StackCookie
0x180014625  call    __security_check_cookie
0x18001462a  lea     r11, [rsp+1C8h+var_18]
0x180014632  mov     rbx, [r11+20h]
0x180014636  mov     rsi, [r11+28h]
0x18001463a  mov     rsp, r11
0x18001463d  pop     r15
0x18001463f  pop     r14
0x180014641  pop     rdi
0x180014642  retn
0x180014643  mov     r9d, 80070057h; char *
0x180014649  lea     r8, aOnecoreDrivers_2; "onecore\\drivers\\wdm\\bluetooth\\user"...
0x180014650  mov     edx, 2DCh; void *
0x180014655  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001465a  mov     r9d, eax; char *
0x18001465d  lea     r8, aOnecoreDrivers_2; "onecore\\drivers\\wdm\\bluetooth\\user"...
0x180014664  mov     edx, 2DFh; void *
0x180014669  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x18001466e  mov     r9d, eax; char *
0x180014671  lea     r8, aOnecoreDrivers_2; "onecore\\drivers\\wdm\\bluetooth\\user"...
0x180014678  mov     edx, 2E2h; void *
0x18001467d  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x180014682  mov     r9d, eax; char *
0x180014685  lea     r8, aOnecoreDrivers_2; "onecore\\drivers\\wdm\\bluetooth\\user"...
0x18001468c  mov     edx, 2E8h; void *
0x180014691  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x180014697  lea     r8, aOnecoreDrivers_7; "onecore\\drivers\\bluetooth\\foundation"...
0x18001469e  mov     edx, 20h ; ' '; void *
0x1800146a3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800146a8  mov     r9d, eax; char *
0x1800146ab  lea     r8, aOnecoreDrivers_7; "onecore\\drivers\\bluetooth\\foundation"...
0x1800146b2  mov     edx, 29h ; ')'; void *
0x1800146b7  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x1800146bc  mov     r9d, 8000FFFFh; char *
0x1800146c2  lea     r8, aOnecoreDrivers_7; "onecore\\drivers\\bluetooth\\foundation"...
0x1800146c9  mov     edx, 2Bh ; '+'; void *
0x1800146ce  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800146d4  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
0x1800146da  mov     r9d, eax; char *
0x1800146dd  lea     r8, aOnecoreDrivers_2; "onecore\\drivers\\wdm\\bluetooth\\user"...
0x1800146e4  mov     edx, 2FCh; void *
0x1800146e9  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x1800146ee  mov     r9d, eax; char *
0x1800146f1  lea     r8, aOnecoreDrivers_2; "onecore\\drivers\\wdm\\bluetooth\\user"...
0x1800146f8  mov     edx, 301h; void *
0x1800146fd  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x180014702  mov     r9d, eax; char *
  ... truncated ...
```
