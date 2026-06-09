# FlightDriverClientAPI::RemoveDrvpkgidFlightIdsMapping(CCoSimpleArray<Microsoft::WRL::ComPtr<FlightDriverPkgIdMapping>,4294967294,CSimpleArrayStandardCompareHelper<Microsoft::WRL::ComPtr<FlightDriverPkgIdMapping>>> *,HKEY__ * const)

- ea: `0x180031614`
- end: `0x1800319c7`
- name: `?RemoveDrvpkgidFlightIdsMapping@FlightDriverClientAPI@@CAJPEAV?$CCoSimpleArray@V?$ComPtr@VFlightDriverPkgIdMapping@@@WRL@Microsoft@@$0PPPPPPPO@V?$CSimpleArrayStandardCompareHelper@V?$ComPtr@VFlightDriverPkgIdMapping@@@WRL@Microsoft@@@@@@QEAUHKEY__@@@Z`
- size: `947`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x1800320cc`

## callees

- `0x180005020`
- `0x18000cc8c`
- `0x18001c6f4`
- `0x18001ec78`
- `0x18002610c`
- `0x180026154`
- `0x18002f328`
- `0x18002f364`
- `0x1800314e0`
- `0x180031614`
- `0x180032294`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800317f6`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800317f6`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18003178c`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18003178c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18003190b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18003190b`

## string_xrefs

- `0x18003164a`: `onecore\base\flighting\flightsettings\broker\libs\driverclientapi\flightdriverclientapi.cpp`
- `0x1800316e0`: `onecore\base\flighting\flightsettings\broker\libs\driverclientapi\flightdriverclientapi.cpp`
- `0x180031940`: `onecore\base\flighting\flightsettings\broker\libs\driverclientapi\flightdriverclientapi.cpp`
- `0x18003199f`: `onecore\base\flighting\flightsettings\broker\libs\driverclientapi\flightdriverclientapi.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall FlightDriverClientAPI::RemoveDrvpkgidFlightIdsMapping(__int64 *a1, HKEY a2)
{
  HKEY v2; // r12
  signed int v4; // ebx
  LPWSTR v5; // rdi
  LPCWSTR *v6; // rsi
  __int64 v7; // r14
  __int64 v8; // r13
  __int64 v9; // rdx
  const struct std::nothrow_t *v10; // rdx
  LSTATUS v11; // eax
  DWORD v12; // eax
  DWORD i; // esi
  __int64 v14; // rbx
  __int64 v15; // r12
  LPCWSTR *v16; // r14
  LSTATUS v17; // eax
  __int64 v18; // rdx
  const struct std::nothrow_t *v19; // rdx
  int lpcSubKeys; // [rsp+20h] [rbp-99h]
  __int64 v22[3]; // [rsp+60h] [rbp-59h] BYREF
  _QWORD v23[3]; // [rsp+78h] [rbp-41h] BYREF
  _QWORD v24[3]; // [rsp+90h] [rbp-29h] BYREF
  LPCWSTR *v25; // [rsp+A8h] [rbp-11h] BYREF
  __int64 v26; // [rsp+B0h] [rbp-9h]
  __int64 v27; // [rsp+B8h] [rbp-1h]
  __int64 v28; // [rsp+C0h] [rbp+7h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]
  DWORD cValues; // [rsp+120h] [rbp+67h] BYREF
  HKEY v31; // [rsp+128h] [rbp+6Fh]
  DWORD cchValueName; // [rsp+130h] [rbp+77h] BYREF
  LPWSTR lpValueName; // [rsp+138h] [rbp+7Fh] BYREF

  v31 = a2;
  v2 = a2;
  if ( !a1 )
  {
    v4 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x397,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\driverclientapi\\flightdriverclientapi.cpp",
      (const char *)0x80070057LL,
      lpcSubKeys);
    return (unsigned int)v4;
  }
  cValues = 0;
  wil::make_unique_nothrow<unsigned short [0]>(&lpValueName, 0x3FFFu);
  v5 = lpValueName;
  if ( !lpValueName )
  {
    v4 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x39C,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\driverclientapi\\flightdriverclientapi.cpp",
      (const char *)0x8007000ELL,
      lpcSubKeys);
    return (unsigned int)v4;
  }
  cchValueName = 0x3FFF;
  v6 = 0;
  v25 = 0;
  v7 = 0;
  v26 = 0;
  v27 = 0;
  v8 = 0;
  v28 = 0;
  memset(v22, 0, sizeof(v22));
  memset(v24, 0, sizeof(v24));
  memset(v23, 0, sizeof(v23));
  v4 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
         v24,
         L"FlightIds",
         -1);
  if ( v4 < 0 )
  {
    v9 = 935;
    goto LABEL_6;
  }
  v4 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
         v23,
         L"FlightIdsHash",
         -1);
  if ( v4 < 0 )
  {
    v9 = 936;
    goto LABEL_6;
  }
  v11 = RegQueryInfoKeyW(v2, 0, 0, 0, 0, 0, 0, &cValues, 0, 0, 0, 0);
  v4 = v11;
  if ( v11 )
  {
    if ( v11 > 0 )
      v4 = (unsigned __int16)v11 | 0x80070000;
    if ( v4 >= 0 )
      goto LABEL_7;
    v9 = 952;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\driverclientapi\\flightdriverclientapi.cpp",
      (const char *)(unsigned int)v4,
      lpcSubKeys);
LABEL_7:
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v23);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v24);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v22);
    CTSimpleArray<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>,4294967294,CTPolicyCoTaskMem<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>>,CSimpleArrayStandardCompareHelper<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>>,CSimpleArrayStandardMergeHelper<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>>>::RemoveAll(&v25);
    if ( v5 )
      operator delete(v5, v10);
    return (unsigned int)v4;
  }
  v12 = cValues;
  if ( cValues )
  {
    for ( i = 0; ; ++i )
    {
      if ( i >= v12 )
      {
        v6 = v25;
        goto LABEL_38;
      }
      cchValueName = 0x3FFF;
      *v5 = 0;
      if ( !RegEnumValueW(v2, i, v5, &cchValueName, 0, 0, 0, 0) )
        break;
LABEL_34:
      v12 = cValues;
    }
    v4 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(v22, v5, -1);
    if ( v4 < 0 )
    {
      v9 = 975;
    }
    else
    {
      v14 = *a1;
      v15 = *a1 + 8 * a1[1];
      while ( v14 != v15 )
      {
        if ( (unsigned int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::CompareOrdinal(
                             v22,
                             *(_QWORD *)(*(_QWORD *)v14 + 16LL),
                             -1) == 2
          || (unsigned int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::CompareOrdinal(
                             v22,
                             v24) == 2
          || (unsigned int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::CompareOrdinal(
                             v22,
                             v23) == 2 )
        {
          goto LABEL_33;
        }
        v14 += 8;
      }
      if ( (unsigned int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::CompareOrdinal(
                           v22,
                           v24) == 2
        || (unsigned int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::CompareOrdinal(
                           v22,
                           v23) == 2 )
      {
        goto LABEL_33;
      }
      if ( v7 != v8 )
        goto LABEL_32;
      v4 = CTSimpleArray<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>,4294967294,CTPolicyCoTaskMem<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>>,CSimpleArrayStandardCompareHelper<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>>,CSimpleArrayStandardMergeHelper<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>>>::_EnsureCapacity(
             &v25,
             v7 + 1);
      if ( v4 >= 0 )
      {
        v8 = v28;
        v7 = v26;
LABEL_32:
        v26 = ++v7;
        CTSimpleArray<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>,4294967294,CTPolicyCoTaskMem<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>>,CSimpleArrayStandardCompareHelper<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>>,CSimpleArrayStandardMergeHelper<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>>>::_InternalSetAtIndex<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>> &&>(
          (__int64 *)&v25,
          v7 - 1,
          v22);
LABEL_33:
        v2 = v31;
        goto LABEL_34;
      }
      v9 = 993;
    }
    goto LABEL_6;
  }
LABEL_38:
  v16 = &v6[3 * v7];
  while ( v6 != v16 )
  {
    if ( !*v6 )
    {
      v4 = -2147024809;
      v18 = 1009;
      goto LABEL_48;
    }
    v17 = RegDeleteValueW(v2, *v6);
    v4 = v17;
    if ( v17 )
    {
      if ( v17 > 0 )
        v4 = (unsigned __int16)v17 | 0x80070000;
      if ( v4 < 0 )
      {
        v18 = 1011;
LABEL_48:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v18,
          (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\driverclientapi\\flightdriverclientapi.cpp",
          (const char *)(unsigned int)v4,
          lpcSubKeys);
        v9 = 1000;
        goto LABEL_6;
      }
    }
    v6 += 3;
  }
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v23);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v24);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v22);
  CTSimpleArray<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>,4294967294,CTPolicyCoTaskMem<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>>,CSimpleArrayStandardCompareHelper<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>>,CSimpleArrayStandardMergeHelper<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>>>::RemoveAll(&v25);
  if ( v5 )
    operator delete(v5, v19);
  return 0;
}

```

## disassembly

```asm
0x180031614  mov     [rsp-8+arg_8], rdx
0x180031619  push    rbp
0x18003161a  push    rbx
0x18003161b  push    rsi
0x18003161c  push    rdi
0x18003161d  push    r12
0x18003161f  push    r13
0x180031621  push    r14
0x180031623  push    r15
0x180031625  lea     rbp, [rsp-1Fh]
0x18003162a  sub     rsp, 0D8h
0x180031631  mov     r12, rdx
0x180031634  mov     r15, rcx
0x180031637  xor     ebx, ebx
0x180031639  test    rcx, rcx
0x18003163c  jnz     short loc_180031660
0x18003163e  mov     rcx, [rbp+5Fh]; this
0x180031642  mov     ebx, 80070057h
0x180031647  mov     r9d, ebx; char *
0x18003164a  lea     r8, aOnecoreBaseFli_49; "onecore\\base\\flighting\\flightsetting"...
0x180031651  mov     edx, 397h; void *
0x180031656  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003165b  jmp     loc_1800319B1
0x180031660  mov     [rbp+57h+cValues], ebx
0x180031663  mov     esi, 3FFFh
0x180031668  mov     edx, esi
0x18003166a  lea     rcx, [rbp+57h+lpValueName]
0x18003166e  call    ??$make_unique_nothrow@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<ushort [0]>(unsigned __int64)
0x180031673  nop
0x180031674  mov     rdi, [rbp+57h+lpValueName]
0x180031678  test    rdi, rdi
0x18003167b  jz      loc_180031993
0x180031681  mov     [rbp+57h+cchValueName], esi
0x180031684  mov     rsi, rbx
0x180031687  mov     [rbp+57h+var_68], rbx
0x18003168b  mov     r14, rbx
0x18003168e  mov     [rbp+57h+var_60], rbx
0x180031692  mov     [rbp+57h+var_58], rbx
0x180031696  mov     r13, rbx
0x180031699  mov     [rbp+57h+var_50], rbx
0x18003169d  mov     [rbp+57h+var_B0], rbx
0x1800316a1  mov     [rbp+57h+var_A8], rbx
0x1800316a5  mov     [rbp+57h+var_A0], rbx
0x1800316a9  mov     [rbp+57h+var_80], rbx
0x1800316ad  mov     [rbp+57h+var_78], rbx
0x1800316b1  mov     [rbp+57h+var_70], rbx
0x1800316b5  mov     [rbp+57h+var_98], rbx
0x1800316b9  mov     [rbp+57h+var_90], rbx
0x1800316bd  mov     [rbp+57h+var_88], rbx
0x1800316c1  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800316c5  lea     rdx, aFlightids; "FlightIds"
0x1800316cc  lea     rcx, [rbp+57h+var_80]
0x1800316d0  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x1800316d5  mov     ebx, eax
0x1800316d7  test    eax, eax
0x1800316d9  jns     short loc_180031732
0x1800316db  mov     edx, 3A7h; void *
0x1800316e0  lea     r8, aOnecoreBaseFli_49; "onecore\\base\\flighting\\flightsetting"...
0x1800316e7  mov     r9d, ebx; char *
0x1800316ea  mov     rcx, [rbp+5Fh]; this
0x1800316ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800316f3  nop
0x1800316f4  lea     rcx, [rbp+57h+var_98]
0x1800316f8  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800316fd  nop
0x1800316fe  lea     rcx, [rbp+57h+var_80]
0x180031702  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180031707  nop
0x180031708  lea     rcx, [rbp+57h+var_B0]
0x18003170c  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180031711  nop
0x180031712  lea     rcx, [rbp+57h+var_68]
0x180031716  call    ?RemoveAll@?$CTSimpleArray@V?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@V?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@@V?$CSimpleArrayStandardCompareHelper@V?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@@V?$CSimpleArrayStandardMergeHelper@V?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@@@@QEAAXXZ; CTSimpleArray<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>,4294967294,CTPolicyCoTaskMem<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>>,CSimpleArrayStandardCompareHelper<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>>,CSimpleArrayStandardMergeHelper<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>>>::RemoveAll(void)
0x18003171b  nop
0x18003171c  test    rdi, rdi
0x18003171f  jz      loc_1800319B1
0x180031725  mov     rcx, rdi; void *
0x180031728  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003172d  jmp     loc_1800319B1
0x180031732  or      r8, 0FFFFFFFFFFFFFFFFh
0x180031736  lea     rdx, aFlightidshash; "FlightIdsHash"
0x18003173d  lea     rcx, [rbp+57h+var_98]
0x180031741  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x180031746  mov     ebx, eax
0x180031748  xor     ecx, ecx
0x18003174a  test    eax, eax
0x18003174c  jns     short loc_180031755
0x18003174e  mov     edx, 3A8h
0x180031753  jmp     short loc_1800316E0
0x180031755  mov     [rsp+110h+lpftLastWriteTime], rcx; lpftLastWriteTime
0x18003175a  mov     [rsp+110h+lpcbSecurityDescriptor], rcx; lpcbSecurityDescriptor
0x18003175f  mov     [rsp+110h+lpcbMaxValueLen], rcx; lpcbMaxValueLen
0x180031764  mov     [rsp+110h+lpcbMaxValueNameLen], rcx; lpcbMaxValueNameLen
0x180031769  lea     rax, [rbp+57h+cValues]
0x18003176d  mov     [rsp+110h+lpcValues], rax; lpcValues
0x180031772  mov     [rsp+110h+lpcbMaxClassLen], rcx; lpcbMaxClassLen
0x180031777  mov     [rsp+110h+lpcbMaxSubKeyLen], rcx; lpcbMaxSubKeyLen
0x18003177c  mov     [rsp+110h+lpcSubKeys], rcx; int
0x180031781  xor     r9d, r9d; lpReserved
0x180031784  xor     r8d, r8d; lpcchClass
0x180031787  xor     edx, edx; lpClass
0x180031789  mov     rcx, r12; hKey
0x18003178c  call    cs:__imp_RegQueryInfoKeyW
0x180031792  mov     ebx, eax
0x180031794  test    eax, eax
0x180031796  jz      short loc_1800317B5
0x180031798  jle     short loc_1800317A3
0x18003179a  movzx   ebx, ax
0x18003179d  or      ebx, 80070000h
0x1800317a3  test    ebx, ebx
0x1800317a5  jns     loc_1800316F4
0x1800317ab  mov     edx, 3B8h
0x1800317b0  jmp     loc_1800316E0
0x1800317b5  mov     eax, [rbp+57h+cValues]
0x1800317b8  test    eax, eax
0x1800317ba  jz      loc_1800318F3
0x1800317c0  xor     esi, esi
0x1800317c2  cmp     esi, eax
0x1800317c4  jnb     loc_1800318EF
0x1800317ca  mov     [rbp+57h+cchValueName], 3FFFh
0x1800317d1  xor     eax, eax
0x1800317d3  mov     [rdi], ax
0x1800317d6  mov     [rsp+110h+lpcValues], rax; lpcbData
0x1800317db  mov     [rsp+110h+lpcbMaxClassLen], rax; lpData
0x1800317e0  mov     [rsp+110h+lpcbMaxSubKeyLen], rax; lpType
0x1800317e5  mov     [rsp+110h+lpcSubKeys], rax; lpReserved
0x1800317ea  lea     r9, [rbp+57h+cchValueName]; lpcchValueName
0x1800317ee  mov     r8, rdi; lpValueName
0x1800317f1  mov     edx, esi; dwIndex
0x1800317f3  mov     rcx, r12; hKey
0x1800317f6  call    cs:__imp_RegEnumValueW
0x1800317fc  test    eax, eax
0x1800317fe  jnz     loc_1800318D1
0x180031804  or      r8, 0FFFFFFFFFFFFFFFFh
0x180031808  mov     rdx, rdi
0x18003180b  lea     rcx, [rbp+57h+var_B0]
0x18003180f  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x180031814  mov     ebx, eax
0x180031816  test    eax, eax
0x180031818  js      loc_1800318E5
0x18003181e  mov     rbx, [r15]
0x180031821  mov     rax, [r15+8]
0x180031825  lea     r12, [rbx+rax*8]
0x180031829  lea     rcx, [rbp+57h+var_B0]
0x18003182d  cmp     rbx, r12
0x180031830  jz      short loc_180031875
0x180031832  mov     rdx, [rbx]
0x180031835  or      r8, 0FFFFFFFFFFFFFFFFh
0x180031839  mov     rdx, [rdx+10h]
0x18003183d  call    ?CompareOrdinal@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBAHPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::CompareOrdinal(ushort const *,unsigned __int64)
0x180031842  cmp     eax, 2
0x180031845  jz      loc_1800318CD
0x18003184b  lea     rdx, [rbp+57h+var_80]
0x18003184f  lea     rcx, [rbp+57h+var_B0]
0x180031853  call    ?CompareOrdinal@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBAHAEBV123@@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::CompareOrdinal(Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> const &)
0x180031858  cmp     eax, 2
0x18003185b  jz      short loc_1800318CD
0x18003185d  lea     rdx, [rbp+57h+var_98]
0x180031861  lea     rcx, [rbp+57h+var_B0]
0x180031865  call    ?CompareOrdinal@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBAHAEBV123@@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::CompareOrdinal(Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> const &)
0x18003186a  cmp     eax, 2
0x18003186d  jz      short loc_1800318CD
0x18003186f  add     rbx, 8
0x180031873  jmp     short loc_180031829
0x180031875  lea     rdx, [rbp+57h+var_80]
0x180031879  call    ?CompareOrdinal@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBAHAEBV123@@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::CompareOrdinal(Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> const &)
0x18003187e  cmp     eax, 2
0x180031881  jz      short loc_1800318CD
0x180031883  lea     rdx, [rbp+57h+var_98]
0x180031887  lea     rcx, [rbp+57h+var_B0]
0x18003188b  call    ?CompareOrdinal@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEBAHAEBV123@@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::CompareOrdinal(Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> const &)
0x180031890  cmp     eax, 2
0x180031893  jz      short loc_1800318CD
0x180031895  cmp     r14, r13
0x180031898  jnz     short loc_1800318B5
0x18003189a  lea     rdx, [r14+1]
0x18003189e  lea     rcx, [rbp+57h+var_68]
0x1800318a2  call    ?_EnsureCapacity@?$CTSimpleArray@V?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@V?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@@V?$CSimpleArrayStandardCompareHelper@V?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@@V?$CSimpleArrayStandardMergeHelper@V?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@@@@QEAAJ_K0@Z; CTSimpleArray<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>,4294967294,CTPolicyCoTaskMem<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>>,CSimpleArrayStandardCompareHelper<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>>,CSimpleArrayStandardMergeHelper<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>>>::_EnsureCapacity(unsigned __int64,unsigned __int64)
0x1800318a7  mov     ebx, eax
0x1800318a9  test    eax, eax
0x1800318ab  js      short loc_1800318DB
0x1800318ad  mov     r13, [rbp+57h+var_50]
0x1800318b1  mov     r14, [rbp+57h+var_60]
0x1800318b5  inc     r14
0x1800318b8  mov     [rbp+57h+var_60], r14
0x1800318bc  lea     rdx, [r14-1]
0x1800318c0  lea     r8, [rbp+57h+var_B0]
0x1800318c4  lea     rcx, [rbp+57h+var_68]
0x1800318c8  call    ??$_InternalSetAtIndex@$$QEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@?$CTSimpleArray@V?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@V?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@@V?$CSimpleArrayStandardCompareHelper@V?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@@V?$CSimpleArrayStandardMergeHelper@V?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@@@@QEAAX_K$$QEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@Z; CTSimpleArray<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>,4294967294,CTPolicyCoTaskMem<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>>,CSimpleArrayStandardCompareHelper<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>>,CSimpleArrayStandardMergeHelper<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>>>::_InternalSetAtIndex<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &&>(unsigned __int64,Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &&)
0x1800318cd  mov     r12, [rbp+57h+arg_8]
0x1800318d1  inc     esi
0x1800318d3  mov     eax, [rbp+57h+cValues]
0x1800318d6  jmp     loc_1800317C2
0x1800318db  mov     edx, 3E1h
0x1800318e0  jmp     loc_1800316E0
0x1800318e5  mov     edx, 3CFh
0x1800318ea  jmp     loc_1800316E0
0x1800318ef  mov     rsi, [rbp+57h+var_68]
0x1800318f3  lea     rax, [r14+r14*2]
0x1800318f7  lea     r14, [rsi+rax*8]
0x1800318fb  cmp     rsi, r14
0x1800318fe  jz      short loc_18003195A
0x180031900  mov     rdx, [rsi]; lpValueName
0x180031903  test    rdx, rdx
0x180031906  jz      short loc_180031933
0x180031908  mov     rcx, r12; hKey
0x18003190b  call    cs:__imp_RegDeleteValueW
0x180031911  mov     ebx, eax
0x180031913  test    eax, eax
0x180031915  jz      short loc_180031926
0x180031917  jle     short loc_180031922
0x180031919  movzx   ebx, ax
0x18003191c  or      ebx, 80070000h
0x180031922  test    ebx, ebx
0x180031924  js      short loc_18003192C
0x180031926  add     rsi, 18h
0x18003192a  jmp     short loc_1800318FB
0x18003192c  mov     edx, 3F3h
0x180031931  jmp     short loc_18003193D
0x180031933  mov     ebx, 80070057h
0x180031938  mov     edx, 3F1h; void *
0x18003193d  mov     r9d, ebx; char *
0x180031940  lea     r8, aOnecoreBaseFli_49; "onecore\\base\\flighting\\flightsetting"...
0x180031947  mov     rcx, [rbp+5Fh]; this
0x18003194b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180031950  mov     edx, 3E8h
0x180031955  jmp     loc_1800316E0
0x18003195a  lea     rcx, [rbp+57h+var_98]
0x18003195e  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180031963  nop
0x180031964  lea     rcx, [rbp+57h+var_80]
0x180031968  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18003196d  nop
0x18003196e  lea     rcx, [rbp+57h+var_B0]
0x180031972  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180031977  nop
0x180031978  lea     rcx, [rbp+57h+var_68]
0x18003197c  call    ?RemoveAll@?$CTSimpleArray@V?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@V?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@@V?$CSimpleArrayStandardCompareHelper@V?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@@V?$CSimpleArrayStandardMergeHelper@V?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@@@@QEAAXXZ; CTSimpleArray<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>,4294967294,CTPolicyCoTaskMem<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>>,CSimpleArrayStandardCompareHelper<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>>,CSimpleArrayStandardMergeHelper<Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>>>::RemoveAll(void)
0x180031981  nop
0x180031982  test    rdi, rdi
0x180031985  jz      short loc_18003198F
0x180031987  mov     rcx, rdi; void *
0x18003198a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003198f  xor     eax, eax
0x180031991  jmp     short loc_1800319B3
0x180031993  mov     rcx, [rbp+5Fh]; this
0x180031997  mov     ebx, 8007000Eh
0x18003199c  mov     r9d, ebx; char *
0x18003199f  lea     r8, aOnecoreBaseFli_49; "onecore\\base\\flighting\\flightsetting"...
0x1800319a6  mov     edx, 39Ch; void *
0x1800319ab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800319b0  nop
0x1800319b1  mov     eax, ebx
0x1800319b3  add     rsp, 0D8h
0x1800319ba  pop     r15
0x1800319bc  pop     r14
0x1800319be  pop     r13
0x1800319c0  pop     r12
0x1800319c2  pop     rdi
0x1800319c3  pop     rsi
0x1800319c4  pop     rbx
0x1800319c5  pop     rbp
0x1800319c6  retn
```
