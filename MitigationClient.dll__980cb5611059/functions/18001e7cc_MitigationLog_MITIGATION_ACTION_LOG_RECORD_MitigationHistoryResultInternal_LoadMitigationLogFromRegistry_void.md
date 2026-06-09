# MitigationLog<_MITIGATION_ACTION_LOG_RECORD,MitigationHistoryResultInternal>::LoadMitigationLogFromRegistry(void)

- ea: `0x18001e7cc`
- end: `0x18001ed0d`
- name: `?LoadMitigationLogFromRegistry@?$MitigationLog@U_MITIGATION_ACTION_LOG_RECORD@@UMitigationHistoryResultInternal@@@@QEAAJXZ`
- size: `1345`
- prototype: ``
- caller_count: `5`
- callee_count: `19`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x18001b4a4`
- `0x180034a94`
- `0x180045438`
- `0x180052830`
- `0x180052f44`

## callees

- `0x18000a6e0`
- `0x18000abc4`
- `0x18000abfc`
- `0x18000b2b4`
- `0x18001208c`
- `0x180013a7c`
- `0x180013b04`
- `0x1800189ac`
- `0x18001964c`
- `0x1800198b0`
- `0x18001e7cc`
- `0x18001fb04`
- `0x180029abc`
- `0x180029cc8`
- `0x180029eb0`
- `0x18002a35c`
- `0x18002a488`
- `0x180042a64`
- `0x18004ff28`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001e87f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001e994`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001ebb6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001e87f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001e994`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001ebb6`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18001ec4b`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18001ec4b`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall MitigationLog<_MITIGATION_ACTION_LOG_RECORD,MitigationHistoryResultInternal>::LoadMitigationLogFromRegistry(
        __int64 a1)
{
  int MitigationRegistryPath; // eax
  unsigned int v3; // ebx
  __int64 v4; // r9
  __int64 v5; // rdx
  const WCHAR *v6; // rax
  unsigned int ValueW; // eax
  char v8; // r14
  __int64 v9; // rax
  DWORD v10; // edx
  char v11; // bl
  PVOID pvData; // rbx
  const WCHAR *v13; // rax
  int v14; // esi
  __int64 v15; // rdx
  unsigned __int64 v16; // rdx
  unsigned __int64 v17; // rdx
  __int64 v18; // rax
  void *v19; // rcx
  unsigned __int64 v21; // r15
  unsigned __int64 v22; // rbx
  void *v23; // rax
  void *v24; // rsi
  const WCHAR *v25; // rax
  unsigned int v26; // eax
  unsigned __int64 v27; // rdx
  __int128 *v28; // rcx
  __int128 *v29; // rax
  __int128 v30; // xmm2
  __int128 v31; // xmm3
  __int128 v32; // xmm4
  unsigned int pdwType; // [rsp+20h] [rbp-39h]
  DWORD pdwTypea; // [rsp+20h] [rbp-39h]
  unsigned int pdwTypeb; // [rsp+20h] [rbp-39h]
  DWORD pcbData; // [rsp+40h] [rbp-19h] BYREF
  DWORD v37; // [rsp+44h] [rbp-15h] BYREF
  __int64 v38; // [rsp+48h] [rbp-11h] BYREF
  unsigned int v39; // [rsp+50h] [rbp-9h] BYREF
  PVOID v40; // [rsp+58h] [rbp-1h] BYREF
  _BYTE v41[32]; // [rsp+60h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  v37 = 0;
  pcbData = 0;
  if ( *(_BYTE *)(a1 + 40) )
    return 0;
  std::wstring::wstring((__int64)v41);
  MitigationRegistryPath = MitigationRegUtils::GetMitigationRegistryPath(*(_DWORD *)(a1 + 80), (__int64)v41);
  v3 = MitigationRegistryPath;
  if ( MitigationRegistryPath < 0 )
  {
    v4 = (unsigned int)MitigationRegistryPath;
    v5 = 435;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\inc\\MitigationLog.h",
      (const char *)v4,
      pdwType);
    goto LABEL_62;
  }
  v6 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v41);
  ValueW = RegGetValueW(HKEY_LOCAL_MACHINE, v6, L"Log", 8u, &v37, 0, &pcbData);
  if ( ValueW == 2 )
  {
LABEL_37:
    std::wstring::_Tidy_deallocate(v41);
    return 0;
  }
  if ( !ValueW )
  {
    if ( v37 != 3 )
    {
      v3 = -2147023886;
      v4 = 2147943410LL;
      v5 = 456;
      goto LABEL_9;
    }
    v39 = 0;
    v8 = 1;
    v40 = (PVOID)-2147483646LL;
    if ( (int)MitigationRegUtils::GetMitigationRegDWORD(&v40, *(unsigned int *)(a1 + 80), L"RecordsCount", &v39) >= 0 )
    {
      v9 = v39;
    }
    else
    {
      v9 = 0;
      v39 = 0;
      v8 = 0;
    }
    v10 = pcbData;
    if ( 48 * v9 == pcbData )
    {
      v11 = 0;
    }
    else
    {
      v11 = 1;
      MicrosoftTelemetryAssertTriggeredNoArgs(48 * v9);
      v10 = pcbData;
    }
    if ( ((unsigned __int8)v11 & (unsigned __int8)v8) != 0 )
    {
      MitigationExecutionContext::DispatchEarlyFailureEvent(13, 2147942413LL);
      wil::make_unique_nothrow<unsigned char [0]>(&v40, pcbData);
      pvData = v40;
      if ( !v40 )
      {
        v3 = -2147024882;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1E7,
          (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\inc\\MitigationLog.h",
          (const char *)0x8007000ELL,
          0);
        goto LABEL_62;
      }
      v13 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v41);
      if ( !RegGetValueW(HKEY_LOCAL_MACHINE, v13, L"Log", 8u, &v37, pvData, &pcbData) )
      {
        v38 = -2147483646;
        pdwTypea = pcbData;
        v14 = MitigationRegUtils::SetMitigationRegBinary(&v38, *(unsigned int *)(a1 + 84), L"Log", pvData);
        if ( v14 < 0 )
        {
          v15 = 501;
LABEL_21:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v15,
            (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\inc\\MitigationLog.h",
            (const char *)(unsigned int)v14,
            pdwTypea);
          if ( pvData )
            operator delete(pvData, v16);
          v3 = v14;
          goto LABEL_62;
        }
      }
      v38 = -2147483646;
      pdwTypea = 0;
      v14 = MitigationRegUtils::SetMitigationRegDWORD(&v38, *(unsigned int *)(a1 + 84), L"RecordsCount", 0);
      if ( v14 < 0 )
      {
        v15 = 504;
        goto LABEL_21;
      }
      v38 = -2147483646;
      pdwTypea = 0;
      v14 = MitigationRegUtils::SetMitigationRegDWORD(&v38, *(unsigned int *)(a1 + 84), L"ExpectedRecordsCount", v39);
      if ( v14 < 0 )
      {
        v15 = 505;
        goto LABEL_21;
      }
      v38 = -2147483646;
      v14 = MitigationRegUtils::DeleteMitigationRegValue(&v38, *(unsigned int *)(a1 + 80), L"Log");
      if ( v14 < 0 )
      {
        v15 = 508;
        goto LABEL_21;
      }
      v38 = -2147483646;
      pdwTypea = 0;
      v14 = MitigationRegUtils::SetMitigationRegDWORD(&v38, *(unsigned int *)(a1 + 80), L"RecordsCount", 0);
      if ( v14 < 0 )
      {
        v15 = 509;
        goto LABEL_21;
      }
      v18 = *(_QWORD *)(a1 + 16);
      if ( v18 != *(_QWORD *)(a1 + 24) )
        *(_QWORD *)(a1 + 24) = v18;
      *(_BYTE *)(a1 + 40) = 1;
      if ( !pvData )
        goto LABEL_37;
      v19 = pvData;
      goto LABEL_36;
    }
    if ( !v10 )
      goto LABEL_37;
    v21 = v10 / 0x30;
    v22 = 48 * v21;
    if ( !is_mul_ok(v21, 0x30u) )
      v22 = -1;
    v23 = operator new[](v22, (const struct std::nothrow_t *)&std::nothrow);
    v24 = v23;
    if ( v23 )
      memset_0(v23, 0, v22);
    else
      v24 = 0;
    v40 = v24;
    if ( !v24 )
    {
      v3 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x20F,
        (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\inc\\MitigationLog.h",
        (const char *)0x8007000ELL,
        0);
      goto LABEL_62;
    }
    v25 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v41);
    v26 = RegGetValueW(HKEY_LOCAL_MACHINE, v25, L"Log", 8u, &v37, v24, &pcbData);
    if ( v26 )
    {
      v3 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x21A,
             (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\inc\\MitigationLog.h",
             (const char *)v26,
             pdwTypeb);
    }
    else
    {
      if ( v37 == 3 )
      {
        std::vector<_MITIGATION_ACTION_LOG_RECORD>::_Assign_counted_range<_MITIGATION_ACTION_LOG_RECORD *>(
          a1 + 16,
          v24,
          v21);
        v17 = *(_QWORD *)(a1 + 24);
        if ( 0xAAAAAAAAAAAAAAABuLL * ((__int64)(v17 - *(_QWORD *)(a1 + 16)) >> 4) > 1
          && CompareFileTime((const FILETIME *)(*(_QWORD *)(a1 + 16) + 36LL), (const FILETIME *)(v17 - 12)) == 1 )
        {
          v28 = *(__int128 **)(a1 + 16);
          v29 = *(__int128 **)(a1 + 24);
          while ( v28 != v29 )
          {
            v29 -= 3;
            if ( v28 == v29 )
              break;
            v30 = *v28;
            v31 = v28[1];
            v32 = v28[2];
            *v28 = *v29;
            v28[1] = v29[1];
            v28[2] = v29[2];
            *v29 = v30;
            v29[1] = v31;
            v29[2] = v32;
            v28 += 3;
          }
        }
        *(_BYTE *)(a1 + 40) = 1;
        if ( !v8 )
        {
          v38 = -2147483646;
          MitigationRegUtils::SetMitigationRegDWORD(
            &v38,
            *(unsigned int *)(a1 + 80),
            L"RecordsCount",
            0xAAAAAAAAAAAAAAABuLL * ((__int64)(*(_QWORD *)(a1 + 24) - *(_QWORD *)(a1 + 16)) >> 4));
        }
        v19 = v24;
LABEL_36:
        operator delete(v19, v17);
        goto LABEL_37;
      }
      v3 = -2147023886;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x21D,
        (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\inc\\MitigationLog.h",
        (const char *)0x800703F2LL,
        pdwTypeb);
    }
    operator delete(v24, v27);
    goto LABEL_62;
  }
  v3 = wil::details::in1diag3::Return_Win32(
         retaddr,
         (void *)0x1C6,
         (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\inc\\MitigationLog.h",
         (const char *)ValueW,
         pdwType);
LABEL_62:
  std::wstring::_Tidy_deallocate(v41);
  return v3;
}

```

## disassembly

```asm
0x18001e7cc  mov     [rsp-8+arg_8], rbx
0x18001e7d1  mov     [rsp-8+arg_10], rsi
0x18001e7d6  push    rbp
0x18001e7d7  push    rdi
0x18001e7d8  push    r13
0x18001e7da  push    r14
0x18001e7dc  push    r15
0x18001e7de  lea     rbp, [rsp-37h]
0x18001e7e3  sub     rsp, 90h
0x18001e7ea  mov     rax, cs:__security_cookie
0x18001e7f1  xor     rax, rsp
0x18001e7f4  mov     [rbp+57h+var_30], rax
0x18001e7f8  mov     rdi, rcx
0x18001e7fb  mov     [rbp+57h+var_6C], 0
0x18001e802  mov     [rbp+57h+var_70], 0
0x18001e809  cmp     byte ptr [rcx+28h], 0
0x18001e80d  jnz     loc_18001EAD1
0x18001e813  lea     rcx, [rbp+57h+var_50]
0x18001e817  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001e81c  nop
0x18001e81d  lea     rdx, [rbp+57h+var_50]
0x18001e821  mov     ecx, [rdi+50h]
0x18001e824  call    ?GetMitigationRegistryPath@MitigationRegUtils@@SAJW4MitigationRegistryKey@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MitigationRegUtils::GetMitigationRegistryPath(MitigationRegistryKey,std::wstring &)
0x18001e829  mov     ebx, eax
0x18001e82b  test    eax, eax
0x18001e82d  jns     short loc_18001E83C
0x18001e82f  mov     r9d, eax
0x18001e832  mov     edx, 1B3h
0x18001e837  jmp     loc_18001E8C4
0x18001e83c  lea     rcx, [rbp+57h+var_50]
0x18001e840  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001e845  mov     rdx, rax; lpSubKey
0x18001e848  lea     rax, [rbp+57h+var_70]
0x18001e84c  mov     [rsp+0B0h+pcbData], rax; pcbData
0x18001e851  mov     [rsp+0B0h+pvData], 0; pvData
0x18001e85a  lea     rax, [rbp+57h+var_6C]
0x18001e85e  mov     [rsp+0B0h+pdwType], rax; int
0x18001e863  mov     esi, 8
0x18001e868  mov     r9d, esi; dwFlags
0x18001e86b  lea     r15, ValueName; "Log"
0x18001e872  mov     r8, r15; lpValue
0x18001e875  mov     r13, 0FFFFFFFF80000002h
0x18001e87c  mov     rcx, r13; hkey
0x18001e87f  call    cs:__imp_RegGetValueW
0x18001e885  cmp     eax, 2
0x18001e888  jz      loc_18001EAC8
0x18001e88e  test    eax, eax
0x18001e890  jz      short loc_18001E8B1
0x18001e892  mov     rcx, [rbp+5Fh]; this
0x18001e896  mov     r9d, eax; char *
0x18001e899  lea     r8, aOnecoreBaseDia_13; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18001e8a0  mov     edx, 1C6h; void *
0x18001e8a5  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001e8aa  mov     ebx, eax
0x18001e8ac  jmp     loc_18001ECFD
0x18001e8b1  cmp     [rbp+57h+var_6C], 3
0x18001e8b5  jz      short loc_18001E8D9
0x18001e8b7  mov     ebx, 800703F2h
0x18001e8bc  mov     r9d, ebx; char *
0x18001e8bf  mov     edx, 1C8h; void *
0x18001e8c4  lea     r8, aOnecoreBaseDia_13; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18001e8cb  mov     rcx, [rbp+5Fh]; this
0x18001e8cf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e8d4  jmp     loc_18001ECFD
0x18001e8d9  mov     [rbp+57h+var_60], 0
0x18001e8e0  mov     r14b, 1
0x18001e8e3  mov     [rbp+57h+var_58], r13
0x18001e8e7  mov     [rsp+0B0h+pdwType], 0; int
0x18001e8f0  lea     r9, [rbp+57h+var_60]
0x18001e8f4  lea     r8, aRecordscount; "RecordsCount"
0x18001e8fb  mov     edx, [rdi+50h]
0x18001e8fe  lea     rcx, [rbp+57h+var_58]
0x18001e902  call    ?GetMitigationRegDWORD@MitigationRegUtils@@SAJAEBQEAUHKEY__@@W4MitigationRegistryKey@@PEBGPEAK2@Z; MitigationRegUtils::GetMitigationRegDWORD(HKEY__ * const &,MitigationRegistryKey,ushort const *,ulong *,ushort const *)
0x18001e907  test    eax, eax
0x18001e909  jns     short loc_18001E915
0x18001e90b  xor     eax, eax
0x18001e90d  mov     [rbp+57h+var_60], eax
0x18001e910  xor     r14b, r14b
0x18001e913  jmp     short loc_18001E918
0x18001e915  mov     eax, [rbp+57h+var_60]
0x18001e918  lea     rcx, [rax+rax*2]
0x18001e91c  shl     rcx, 4
0x18001e920  mov     edx, [rbp+57h+var_70]
0x18001e923  cmp     rcx, rdx
0x18001e926  jz      short loc_18001E934
0x18001e928  mov     bl, 1
0x18001e92a  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "!isInvalidState")
0x18001e92f  mov     edx, [rbp+57h+var_70]
0x18001e932  jmp     short loc_18001E936
0x18001e934  xor     bl, bl
0x18001e936  test    r14b, bl
0x18001e939  jz      loc_18001EB1E
0x18001e93f  mov     edx, 8007000Dh
0x18001e944  mov     ecx, 0Dh
0x18001e949  call    ?DispatchEarlyFailureEvent@MitigationExecutionContext@@SAXW4FailureBucketId@@J@Z; MitigationExecutionContext::DispatchEarlyFailureEvent(FailureBucketId,long)
0x18001e94e  mov     edx, [rbp+57h+var_70]
0x18001e951  lea     rcx, [rbp+57h+var_58]
0x18001e955  call    ??$make_unique_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<uchar [0]>(unsigned __int64)
0x18001e95a  nop
0x18001e95b  mov     rbx, [rbp+57h+var_58]
0x18001e95f  test    rbx, rbx
0x18001e962  jz      loc_18001EAFB
0x18001e968  lea     rcx, [rbp+57h+var_50]
0x18001e96c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001e971  mov     rdx, rax; lpSubKey
0x18001e974  lea     rax, [rbp+57h+var_70]
0x18001e978  mov     [rsp+0B0h+pcbData], rax; pcbData
0x18001e97d  mov     [rsp+0B0h+pvData], rbx; pvData
0x18001e982  lea     rax, [rbp+57h+var_6C]
0x18001e986  mov     [rsp+0B0h+pdwType], rax; pdwType
0x18001e98b  mov     r9d, esi; dwFlags
0x18001e98e  mov     r8, r15; lpValue
0x18001e991  mov     rcx, r13; hkey
0x18001e994  call    cs:__imp_RegGetValueW
0x18001e99a  test    eax, eax
0x18001e99c  jnz     short loc_18001E9EE
0x18001e99e  mov     eax, [rbp+57h+var_70]
0x18001e9a1  mov     [rbp+57h+var_68], r13
0x18001e9a5  mov     dword ptr [rsp+0B0h+pdwType], eax; int
0x18001e9a9  mov     r9, rbx
0x18001e9ac  mov     r8, r15
0x18001e9af  mov     edx, [rdi+54h]
0x18001e9b2  lea     rcx, [rbp+57h+var_68]
0x18001e9b6  call    ?SetMitigationRegBinary@MitigationRegUtils@@SAJAEBQEAUHKEY__@@W4MitigationRegistryKey@@PEBGPEAXK@Z; MitigationRegUtils::SetMitigationRegBinary(HKEY__ * const &,MitigationRegistryKey,ushort const *,void *,ulong)
0x18001e9bb  mov     esi, eax
0x18001e9bd  test    eax, eax
0x18001e9bf  jns     short loc_18001E9EE
0x18001e9c1  mov     edx, 1F5h; void *
0x18001e9c6  mov     rcx, [rbp+5Fh]; this
0x18001e9ca  mov     r9d, esi; char *
0x18001e9cd  lea     r8, aOnecoreBaseDia_13; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18001e9d4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e9d9  nop
0x18001e9da  test    rbx, rbx
0x18001e9dd  jz      short loc_18001E9E7
0x18001e9df  mov     rcx, rbx; void *
0x18001e9e2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001e9e7  mov     ebx, esi
0x18001e9e9  jmp     loc_18001ECFD
0x18001e9ee  mov     [rbp+57h+var_68], r13
0x18001e9f2  mov     [rsp+0B0h+pdwType], 0
0x18001e9fb  xor     r9d, r9d
0x18001e9fe  lea     r8, aRecordscount; "RecordsCount"
0x18001ea05  mov     edx, [rdi+54h]
0x18001ea08  lea     rcx, [rbp+57h+var_68]
0x18001ea0c  call    ?SetMitigationRegDWORD@MitigationRegUtils@@SAJAEBQEAUHKEY__@@W4MitigationRegistryKey@@PEBGK2@Z; MitigationRegUtils::SetMitigationRegDWORD(HKEY__ * const &,MitigationRegistryKey,ushort const *,ulong,ushort const *)
0x18001ea11  mov     esi, eax
0x18001ea13  test    eax, eax
0x18001ea15  jns     short loc_18001EA1E
0x18001ea17  mov     edx, 1F8h
0x18001ea1c  jmp     short loc_18001E9C6
0x18001ea1e  mov     [rbp+57h+var_68], r13
0x18001ea22  mov     [rsp+0B0h+pdwType], 0
0x18001ea2b  mov     r9d, [rbp+57h+var_60]
0x18001ea2f  lea     r8, aExpectedrecord; "ExpectedRecordsCount"
0x18001ea36  mov     edx, [rdi+54h]
0x18001ea39  lea     rcx, [rbp+57h+var_68]
0x18001ea3d  call    ?SetMitigationRegDWORD@MitigationRegUtils@@SAJAEBQEAUHKEY__@@W4MitigationRegistryKey@@PEBGK2@Z; MitigationRegUtils::SetMitigationRegDWORD(HKEY__ * const &,MitigationRegistryKey,ushort const *,ulong,ushort const *)
0x18001ea42  mov     esi, eax
0x18001ea44  test    eax, eax
0x18001ea46  jns     short loc_18001EA52
0x18001ea48  mov     edx, 1F9h
0x18001ea4d  jmp     loc_18001E9C6
0x18001ea52  mov     [rbp+57h+var_68], r13
0x18001ea56  mov     r8, r15
0x18001ea59  mov     edx, [rdi+50h]
0x18001ea5c  lea     rcx, [rbp+57h+var_68]
0x18001ea60  call    ?DeleteMitigationRegValue@MitigationRegUtils@@SAJAEBQEAUHKEY__@@W4MitigationRegistryKey@@PEBG@Z; MitigationRegUtils::DeleteMitigationRegValue(HKEY__ * const &,MitigationRegistryKey,ushort const *)
0x18001ea65  mov     esi, eax
0x18001ea67  test    eax, eax
0x18001ea69  jns     short loc_18001EA75
0x18001ea6b  mov     edx, 1FCh
0x18001ea70  jmp     loc_18001E9C6
0x18001ea75  mov     [rbp+57h+var_68], r13
0x18001ea79  mov     [rsp+0B0h+pdwType], 0
0x18001ea82  xor     r9d, r9d
0x18001ea85  lea     r8, aRecordscount; "RecordsCount"
0x18001ea8c  mov     edx, [rdi+50h]
0x18001ea8f  lea     rcx, [rbp+57h+var_68]
0x18001ea93  call    ?SetMitigationRegDWORD@MitigationRegUtils@@SAJAEBQEAUHKEY__@@W4MitigationRegistryKey@@PEBGK2@Z; MitigationRegUtils::SetMitigationRegDWORD(HKEY__ * const &,MitigationRegistryKey,ushort const *,ulong,ushort const *)
0x18001ea98  mov     esi, eax
0x18001ea9a  test    eax, eax
0x18001ea9c  jns     short loc_18001EAA8
0x18001ea9e  mov     edx, 1FDh
0x18001eaa3  jmp     loc_18001E9C6
0x18001eaa8  mov     rax, [rdi+10h]
0x18001eaac  cmp     rax, [rdi+18h]
0x18001eab0  jz      short loc_18001EAB6
0x18001eab2  mov     [rdi+18h], rax
0x18001eab6  mov     byte ptr [rdi+28h], 1
0x18001eaba  test    rbx, rbx
0x18001eabd  jz      short loc_18001EAC8
0x18001eabf  mov     rcx, rbx; void *
0x18001eac2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001eac7  nop
0x18001eac8  lea     rcx, [rbp+57h+var_50]
0x18001eacc  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001ead1  xor     eax, eax
0x18001ead3  mov     rcx, [rbp+57h+var_30]
0x18001ead7  xor     rcx, rsp; StackCookie
0x18001eada  call    __security_check_cookie
0x18001eadf  lea     r11, [rsp+0B0h+var_20]
0x18001eae7  mov     rbx, [r11+38h]
0x18001eaeb  mov     rsi, [r11+40h]
0x18001eaef  mov     rsp, r11
0x18001eaf2  pop     r15
0x18001eaf4  pop     r14
0x18001eaf6  pop     r13
0x18001eaf8  pop     rdi
0x18001eaf9  pop     rbp
0x18001eafa  retn
0x18001eafb  mov     rcx, [rbp+5Fh]; this
0x18001eaff  mov     ebx, 8007000Eh
0x18001eb04  mov     r9d, ebx; char *
0x18001eb07  lea     r8, aOnecoreBaseDia_13; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18001eb0e  mov     edx, 1E7h; void *
0x18001eb13  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001eb18  nop
0x18001eb19  jmp     loc_18001ECFD
0x18001eb1e  test    edx, edx
0x18001eb20  jz      short loc_18001EAC8
0x18001eb22  mov     ecx, edx
0x18001eb24  mov     rax, 0AAAAAAAAAAAAAAABh
0x18001eb2e  mul     rcx
0x18001eb31  shr     rdx, 5
0x18001eb35  mov     r15d, edx
0x18001eb38  mov     eax, 30h ; '0'
0x18001eb3d  mul     r15
0x18001eb40  mov     rbx, rax
0x18001eb43  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18001eb4a  cmovb   rbx, rax
0x18001eb4e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001eb55  mov     rcx, rbx; unsigned __int64
0x18001eb58  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001eb5d  mov     rsi, rax
0x18001eb60  test    rax, rax
0x18001eb63  jz      short loc_18001EB74
0x18001eb65  mov     r8, rbx; Size
0x18001eb68  xor     edx, edx; Val
0x18001eb6a  mov     rcx, rax; void *
0x18001eb6d  call    memset_0
0x18001eb72  jmp     short loc_18001EB76
0x18001eb74  xor     esi, esi
0x18001eb76  mov     [rbp+57h+var_58], rsi
0x18001eb7a  test    rsi, rsi
0x18001eb7d  jz      loc_18001ECDF
0x18001eb83  lea     rcx, [rbp+57h+var_50]
0x18001eb87  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001eb8c  mov     rdx, rax; lpSubKey
0x18001eb8f  lea     rax, [rbp+57h+var_70]
0x18001eb93  mov     [rsp+0B0h+pcbData], rax; pcbData
0x18001eb98  mov     [rsp+0B0h+pvData], rsi; pvData
0x18001eb9d  lea     rax, [rbp+57h+var_6C]
0x18001eba1  mov     [rsp+0B0h+pdwType], rax; int
0x18001eba6  mov     r9d, 8; dwFlags
0x18001ebac  lea     r8, ValueName; "Log"
0x18001ebb3  mov     rcx, r13; hkey
0x18001ebb6  call    cs:__imp_RegGetValueW
0x18001ebbc  test    eax, eax
0x18001ebbe  jz      short loc_18001EBE7
0x18001ebc0  mov     rcx, [rbp+5Fh]; this
0x18001ebc4  mov     r9d, eax; char *
0x18001ebc7  lea     r8, aOnecoreBaseDia_13; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18001ebce  mov     edx, 21Ah; void *
0x18001ebd3  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001ebd8  mov     ebx, eax
0x18001ebda  mov     rcx, rsi; void *
0x18001ebdd  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001ebe2  jmp     loc_18001ECFD
0x18001ebe7  cmp     [rbp+57h+var_6C], 3
0x18001ebeb  jz      short loc_18001EC0C
0x18001ebed  mov     rcx, [rbp+5Fh]; this
0x18001ebf1  mov     ebx, 800703F2h
0x18001ebf6  mov     r9d, ebx; char *
0x18001ebf9  lea     r8, aOnecoreBaseDia_13; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18001ec00  mov     edx, 21Dh; void *
0x18001ec05  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ec0a  jmp     short loc_18001EBDA
0x18001ec0c  lea     rbx, [rdi+10h]
0x18001ec10  mov     r8, r15
0x18001ec13  mov     rdx, rsi
0x18001ec16  mov     rcx, rbx
0x18001ec19  call    ??$_Assign_counted_range@PEAU_MITIGATION_ACTION_LOG_RECORD@@@?$vector@U_MITIGATION_ACTION_LOG_RECORD@@V?$allocator@U_MITIGATION_ACTION_LOG_RECORD@@@std@@@std@@AEAAXPEAU_MITIGATION_ACTION_LOG_RECORD@@_K@Z; std::vector<_MITIGATION_ACTION_LOG_RECORD>::_Assign_counted_range<_MITIGATION_ACTION_LOG_RECORD *>(_MITIGATION_ACTION_LOG_RECORD *,unsigned __int64)
0x18001ec1e  mov     rcx, [rbx]
0x18001ec21  mov     rdx, [rbx+8]
0x18001ec25  mov     rax, rdx
0x18001ec28  sub     rax, rcx
0x18001ec2b  sar     rax, 4
0x18001ec2f  mov     r15, 0AAAAAAAAAAAAAAABh
0x18001ec39  imul    rax, r15
0x18001ec3d  cmp     rax, 1
0x18001ec41  jbe     short loc_18001EC9D
0x18001ec43  add     rdx, 0FFFFFFFFFFFFFFF4h; lpFileTime2
0x18001ec47  add     rcx, 24h ; '$'; lpFileTime1
0x18001ec4b  call    cs:__imp_CompareFileTime
0x18001ec51  cmp     eax, 1
0x18001ec54  jnz     short loc_18001EC9D
0x18001ec56  mov     rcx, [rbx]
0x18001ec59  mov     rax, [rdi+18h]
0x18001ec5d  jmp     short loc_18001EC98
  ... truncated ...
```
