# MitigationLog<_AVAILABLE_MITIGATION_RECORD,MitigationResultInternal>::LoadMitigationLogFromRegistry(void)

- ea: `0x18001e27c`
- end: `0x18001e7c5`
- name: `?LoadMitigationLogFromRegistry@?$MitigationLog@U_AVAILABLE_MITIGATION_RECORD@@UMitigationResultInternal@@@@QEAAJXZ`
- size: `1353`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `11`
- callee_count: `19`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x18001b2f0`
- `0x18001b924`
- `0x18001d5d8`
- `0x18001d984`
- `0x18001f63c`
- `0x180020b20`
- `0x180034680`
- `0x1800349d8`
- `0x180050ec4`
- `0x1800513d0`
- `0x180051828`

## callees

- `0x18000a6e0`
- `0x18000abc4`
- `0x18000abfc`
- `0x18000b2b4`
- `0x18001208c`
- `0x180013a7c`
- `0x180013b04`
- `0x1800188b8`
- `0x18001964c`
- `0x1800198b0`
- `0x18001e27c`
- `0x18001fb04`
- `0x180029abc`
- `0x180029cc8`
- `0x180029eb0`
- `0x18002a35c`
- `0x18002a488`
- `0x180042a64`
- `0x18004ff28`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001e32f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001e440`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001e662`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001e32f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001e440`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001e662`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18001e6f7`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18001e6f7`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall MitigationLog<_AVAILABLE_MITIGATION_RECORD,MitigationResultInternal>::LoadMitigationLogFromRegistry(
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
  unsigned int pdwType; // [rsp+20h] [rbp-69h]
  DWORD pdwTypea; // [rsp+20h] [rbp-69h]
  unsigned int pdwTypeb; // [rsp+20h] [rbp-69h]
  DWORD pcbData; // [rsp+40h] [rbp-49h] BYREF
  DWORD v36; // [rsp+44h] [rbp-45h] BYREF
  __int64 v37; // [rsp+48h] [rbp-41h] BYREF
  unsigned int v38; // [rsp+50h] [rbp-39h] BYREF
  PVOID v39[3]; // [rsp+58h] [rbp-31h] BYREF
  _OWORD v40[2]; // [rsp+70h] [rbp-19h]
  _BYTE v41[32]; // [rsp+90h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v36 = 0;
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
  ValueW = RegGetValueW(HKEY_LOCAL_MACHINE, v6, L"Log", 8u, &v36, 0, &pcbData);
  if ( ValueW == 2 )
  {
LABEL_37:
    std::wstring::_Tidy_deallocate(v41);
    return 0;
  }
  if ( !ValueW )
  {
    if ( v36 != 3 )
    {
      v3 = -2147023886;
      v4 = 2147943410LL;
      v5 = 456;
      goto LABEL_9;
    }
    v38 = 0;
    v8 = 1;
    v39[0] = (PVOID)-2147483646LL;
    if ( (int)MitigationRegUtils::GetMitigationRegDWORD(v39, *(unsigned int *)(a1 + 80), L"RecordsCount", &v38) >= 0 )
    {
      v9 = v38;
    }
    else
    {
      v9 = 0;
      v38 = 0;
      v8 = 0;
    }
    v10 = pcbData;
    if ( 44 * v9 == pcbData )
    {
      v11 = 0;
    }
    else
    {
      v11 = 1;
      MicrosoftTelemetryAssertTriggeredNoArgs(44 * v9);
      v10 = pcbData;
    }
    if ( ((unsigned __int8)v11 & (unsigned __int8)v8) != 0 )
    {
      MitigationExecutionContext::DispatchEarlyFailureEvent(13, 2147942413LL);
      wil::make_unique_nothrow<unsigned char [0]>(v39, pcbData);
      pvData = v39[0];
      if ( !v39[0] )
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
      if ( !RegGetValueW(HKEY_LOCAL_MACHINE, v13, L"Log", 8u, &v36, pvData, &pcbData) )
      {
        v37 = -2147483646;
        pdwTypea = pcbData;
        v14 = MitigationRegUtils::SetMitigationRegBinary(&v37, *(unsigned int *)(a1 + 84), L"Log", pvData);
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
      v37 = -2147483646;
      pdwTypea = 0;
      v14 = MitigationRegUtils::SetMitigationRegDWORD(&v37, *(unsigned int *)(a1 + 84), L"RecordsCount", 0);
      if ( v14 < 0 )
      {
        v15 = 504;
        goto LABEL_21;
      }
      v37 = -2147483646;
      pdwTypea = 0;
      v14 = MitigationRegUtils::SetMitigationRegDWORD(&v37, *(unsigned int *)(a1 + 84), L"ExpectedRecordsCount", v38);
      if ( v14 < 0 )
      {
        v15 = 505;
        goto LABEL_21;
      }
      v37 = -2147483646;
      v14 = MitigationRegUtils::DeleteMitigationRegValue(&v37, *(unsigned int *)(a1 + 80), L"Log");
      if ( v14 < 0 )
      {
        v15 = 508;
        goto LABEL_21;
      }
      v37 = -2147483646;
      pdwTypea = 0;
      v14 = MitigationRegUtils::SetMitigationRegDWORD(&v37, *(unsigned int *)(a1 + 80), L"RecordsCount", 0);
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
    v21 = v10 / 0x2C;
    v22 = 44 * v21;
    if ( !is_mul_ok(v21, 0x2Cu) )
      v22 = -1;
    v23 = operator new[](v22, (const struct std::nothrow_t *)&std::nothrow);
    v24 = v23;
    if ( v23 )
      memset_0(v23, 0, v22);
    else
      v24 = 0;
    v39[0] = v24;
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
    v26 = RegGetValueW(HKEY_LOCAL_MACHINE, v25, L"Log", 8u, &v36, v24, &pcbData);
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
      if ( v36 == 3 )
      {
        std::vector<_AVAILABLE_MITIGATION_RECORD>::_Assign_counted_range<_AVAILABLE_MITIGATION_RECORD *>(
          a1 + 16,
          v24,
          v21);
        v17 = *(_QWORD *)(a1 + 24);
        if ( (unsigned __int64)(0x2E8BA2E8BA2E8BA3LL * ((__int64)(v17 - *(_QWORD *)(a1 + 16)) >> 2)) > 1
          && CompareFileTime((const FILETIME *)(*(_QWORD *)(a1 + 16) + 24LL), (const FILETIME *)(v17 - 20)) == 1 )
        {
          v28 = *(__int128 **)(a1 + 16);
          v29 = *(__int128 **)(a1 + 24);
          while ( v28 != v29 )
          {
            v29 = (__int128 *)((char *)v29 - 44);
            if ( v28 == v29 )
              break;
            v30 = *v28;
            v40[0] = v28[1];
            *(_OWORD *)((char *)v40 + 12) = *(__int128 *)((char *)v28 + 28);
            v31 = *(_OWORD *)((char *)v40 + 12);
            *v28 = *v29;
            v28[1] = v29[1];
            *(__int128 *)((char *)v28 + 28) = *(__int128 *)((char *)v29 + 28);
            *v29 = v30;
            v29[1] = v40[0];
            *(__int128 *)((char *)v29 + 28) = v31;
            v28 = (__int128 *)((char *)v28 + 44);
          }
        }
        *(_BYTE *)(a1 + 40) = 1;
        if ( !v8 )
        {
          v37 = -2147483646;
          MitigationRegUtils::SetMitigationRegDWORD(
            &v37,
            *(unsigned int *)(a1 + 80),
            L"RecordsCount",
            0x2E8BA2E8BA2E8BA3LL * ((__int64)(*(_QWORD *)(a1 + 24) - *(_QWORD *)(a1 + 16)) >> 2));
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
0x18001e27c  mov     [rsp-8+arg_8], rbx
0x18001e281  mov     [rsp-8+arg_10], rsi
0x18001e286  push    rbp
0x18001e287  push    rdi
0x18001e288  push    r13
0x18001e28a  push    r14
0x18001e28c  push    r15
0x18001e28e  lea     rbp, [rsp-37h]
0x18001e293  sub     rsp, 0C0h
0x18001e29a  mov     rax, cs:__security_cookie
0x18001e2a1  xor     rax, rsp
0x18001e2a4  mov     [rbp+57h+var_30], rax
0x18001e2a8  mov     rdi, rcx
0x18001e2ab  mov     [rbp+57h+var_9C], 0
0x18001e2b2  mov     [rbp+57h+var_A0], 0
0x18001e2b9  cmp     byte ptr [rcx+28h], 0
0x18001e2bd  jnz     loc_18001E57D
0x18001e2c3  lea     rcx, [rbp+57h+var_50]
0x18001e2c7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001e2cc  nop
0x18001e2cd  lea     rdx, [rbp+57h+var_50]
0x18001e2d1  mov     ecx, [rdi+50h]
0x18001e2d4  call    ?GetMitigationRegistryPath@MitigationRegUtils@@SAJW4MitigationRegistryKey@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MitigationRegUtils::GetMitigationRegistryPath(MitigationRegistryKey,std::wstring &)
0x18001e2d9  mov     ebx, eax
0x18001e2db  test    eax, eax
0x18001e2dd  jns     short loc_18001E2EC
0x18001e2df  mov     r9d, eax
0x18001e2e2  mov     edx, 1B3h
0x18001e2e7  jmp     loc_18001E374
0x18001e2ec  lea     rcx, [rbp+57h+var_50]
0x18001e2f0  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001e2f5  mov     rdx, rax; lpSubKey
0x18001e2f8  lea     rax, [rbp+57h+var_A0]
0x18001e2fc  mov     [rsp+0E0h+pcbData], rax; pcbData
0x18001e301  mov     [rsp+0E0h+pvData], 0; pvData
0x18001e30a  lea     rax, [rbp+57h+var_9C]
0x18001e30e  mov     [rsp+0E0h+pdwType], rax; int
0x18001e313  mov     esi, 8
0x18001e318  mov     r9d, esi; dwFlags
0x18001e31b  lea     r15, ValueName; "Log"
0x18001e322  mov     r8, r15; lpValue
0x18001e325  mov     r13, 0FFFFFFFF80000002h
0x18001e32c  mov     rcx, r13; hkey
0x18001e32f  call    cs:__imp_RegGetValueW
0x18001e335  cmp     eax, 2
0x18001e338  jz      loc_18001E574
0x18001e33e  test    eax, eax
0x18001e340  jz      short loc_18001E361
0x18001e342  mov     rcx, [rbp+5Fh]; this
0x18001e346  mov     r9d, eax; char *
0x18001e349  lea     r8, aOnecoreBaseDia_13; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18001e350  mov     edx, 1C6h; void *
0x18001e355  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001e35a  mov     ebx, eax
0x18001e35c  jmp     loc_18001E7B5
0x18001e361  cmp     [rbp+57h+var_9C], 3
0x18001e365  jz      short loc_18001E389
0x18001e367  mov     ebx, 800703F2h
0x18001e36c  mov     r9d, ebx; char *
0x18001e36f  mov     edx, 1C8h; void *
0x18001e374  lea     r8, aOnecoreBaseDia_13; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18001e37b  mov     rcx, [rbp+5Fh]; this
0x18001e37f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e384  jmp     loc_18001E7B5
0x18001e389  mov     [rbp+57h+var_90], 0
0x18001e390  mov     r14b, 1
0x18001e393  mov     [rbp+57h+var_88], r13
0x18001e397  mov     [rsp+0E0h+pdwType], 0; int
0x18001e3a0  lea     r9, [rbp+57h+var_90]
0x18001e3a4  lea     r8, aRecordscount; "RecordsCount"
0x18001e3ab  mov     edx, [rdi+50h]
0x18001e3ae  lea     rcx, [rbp+57h+var_88]
0x18001e3b2  call    ?GetMitigationRegDWORD@MitigationRegUtils@@SAJAEBQEAUHKEY__@@W4MitigationRegistryKey@@PEBGPEAK2@Z; MitigationRegUtils::GetMitigationRegDWORD(HKEY__ * const &,MitigationRegistryKey,ushort const *,ulong *,ushort const *)
0x18001e3b7  test    eax, eax
0x18001e3b9  jns     short loc_18001E3C5
0x18001e3bb  xor     eax, eax
0x18001e3bd  mov     [rbp+57h+var_90], eax
0x18001e3c0  xor     r14b, r14b
0x18001e3c3  jmp     short loc_18001E3C8
0x18001e3c5  mov     eax, [rbp+57h+var_90]
0x18001e3c8  imul    rcx, rax, 2Ch ; ','
0x18001e3cc  mov     edx, [rbp+57h+var_A0]
0x18001e3cf  cmp     rcx, rdx
0x18001e3d2  jz      short loc_18001E3E0
0x18001e3d4  mov     bl, 1
0x18001e3d6  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "!isInvalidState")
0x18001e3db  mov     edx, [rbp+57h+var_A0]
0x18001e3de  jmp     short loc_18001E3E2
0x18001e3e0  xor     bl, bl
0x18001e3e2  test    r14b, bl
0x18001e3e5  jz      loc_18001E5CA
0x18001e3eb  mov     edx, 8007000Dh
0x18001e3f0  mov     ecx, 0Dh
0x18001e3f5  call    ?DispatchEarlyFailureEvent@MitigationExecutionContext@@SAXW4FailureBucketId@@J@Z; MitigationExecutionContext::DispatchEarlyFailureEvent(FailureBucketId,long)
0x18001e3fa  mov     edx, [rbp+57h+var_A0]
0x18001e3fd  lea     rcx, [rbp+57h+var_88]
0x18001e401  call    ??$make_unique_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<uchar [0]>(unsigned __int64)
0x18001e406  nop
0x18001e407  mov     rbx, [rbp+57h+var_88]
0x18001e40b  test    rbx, rbx
0x18001e40e  jz      loc_18001E5A7
0x18001e414  lea     rcx, [rbp+57h+var_50]
0x18001e418  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001e41d  mov     rdx, rax; lpSubKey
0x18001e420  lea     rax, [rbp+57h+var_A0]
0x18001e424  mov     [rsp+0E0h+pcbData], rax; pcbData
0x18001e429  mov     [rsp+0E0h+pvData], rbx; pvData
0x18001e42e  lea     rax, [rbp+57h+var_9C]
0x18001e432  mov     [rsp+0E0h+pdwType], rax; pdwType
0x18001e437  mov     r9d, esi; dwFlags
0x18001e43a  mov     r8, r15; lpValue
0x18001e43d  mov     rcx, r13; hkey
0x18001e440  call    cs:__imp_RegGetValueW
0x18001e446  test    eax, eax
0x18001e448  jnz     short loc_18001E49A
0x18001e44a  mov     eax, [rbp+57h+var_A0]
0x18001e44d  mov     [rbp+57h+var_98], r13
0x18001e451  mov     dword ptr [rsp+0E0h+pdwType], eax; int
0x18001e455  mov     r9, rbx
0x18001e458  mov     r8, r15
0x18001e45b  mov     edx, [rdi+54h]
0x18001e45e  lea     rcx, [rbp+57h+var_98]
0x18001e462  call    ?SetMitigationRegBinary@MitigationRegUtils@@SAJAEBQEAUHKEY__@@W4MitigationRegistryKey@@PEBGPEAXK@Z; MitigationRegUtils::SetMitigationRegBinary(HKEY__ * const &,MitigationRegistryKey,ushort const *,void *,ulong)
0x18001e467  mov     esi, eax
0x18001e469  test    eax, eax
0x18001e46b  jns     short loc_18001E49A
0x18001e46d  mov     edx, 1F5h; void *
0x18001e472  mov     rcx, [rbp+5Fh]; this
0x18001e476  mov     r9d, esi; char *
0x18001e479  lea     r8, aOnecoreBaseDia_13; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18001e480  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e485  nop
0x18001e486  test    rbx, rbx
0x18001e489  jz      short loc_18001E493
0x18001e48b  mov     rcx, rbx; void *
0x18001e48e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001e493  mov     ebx, esi
0x18001e495  jmp     loc_18001E7B5
0x18001e49a  mov     [rbp+57h+var_98], r13
0x18001e49e  mov     [rsp+0E0h+pdwType], 0
0x18001e4a7  xor     r9d, r9d
0x18001e4aa  lea     r8, aRecordscount; "RecordsCount"
0x18001e4b1  mov     edx, [rdi+54h]
0x18001e4b4  lea     rcx, [rbp+57h+var_98]
0x18001e4b8  call    ?SetMitigationRegDWORD@MitigationRegUtils@@SAJAEBQEAUHKEY__@@W4MitigationRegistryKey@@PEBGK2@Z; MitigationRegUtils::SetMitigationRegDWORD(HKEY__ * const &,MitigationRegistryKey,ushort const *,ulong,ushort const *)
0x18001e4bd  mov     esi, eax
0x18001e4bf  test    eax, eax
0x18001e4c1  jns     short loc_18001E4CA
0x18001e4c3  mov     edx, 1F8h
0x18001e4c8  jmp     short loc_18001E472
0x18001e4ca  mov     [rbp+57h+var_98], r13
0x18001e4ce  mov     [rsp+0E0h+pdwType], 0
0x18001e4d7  mov     r9d, [rbp+57h+var_90]
0x18001e4db  lea     r8, aExpectedrecord; "ExpectedRecordsCount"
0x18001e4e2  mov     edx, [rdi+54h]
0x18001e4e5  lea     rcx, [rbp+57h+var_98]
0x18001e4e9  call    ?SetMitigationRegDWORD@MitigationRegUtils@@SAJAEBQEAUHKEY__@@W4MitigationRegistryKey@@PEBGK2@Z; MitigationRegUtils::SetMitigationRegDWORD(HKEY__ * const &,MitigationRegistryKey,ushort const *,ulong,ushort const *)
0x18001e4ee  mov     esi, eax
0x18001e4f0  test    eax, eax
0x18001e4f2  jns     short loc_18001E4FE
0x18001e4f4  mov     edx, 1F9h
0x18001e4f9  jmp     loc_18001E472
0x18001e4fe  mov     [rbp+57h+var_98], r13
0x18001e502  mov     r8, r15
0x18001e505  mov     edx, [rdi+50h]
0x18001e508  lea     rcx, [rbp+57h+var_98]
0x18001e50c  call    ?DeleteMitigationRegValue@MitigationRegUtils@@SAJAEBQEAUHKEY__@@W4MitigationRegistryKey@@PEBG@Z; MitigationRegUtils::DeleteMitigationRegValue(HKEY__ * const &,MitigationRegistryKey,ushort const *)
0x18001e511  mov     esi, eax
0x18001e513  test    eax, eax
0x18001e515  jns     short loc_18001E521
0x18001e517  mov     edx, 1FCh
0x18001e51c  jmp     loc_18001E472
0x18001e521  mov     [rbp+57h+var_98], r13
0x18001e525  mov     [rsp+0E0h+pdwType], 0
0x18001e52e  xor     r9d, r9d
0x18001e531  lea     r8, aRecordscount; "RecordsCount"
0x18001e538  mov     edx, [rdi+50h]
0x18001e53b  lea     rcx, [rbp+57h+var_98]
0x18001e53f  call    ?SetMitigationRegDWORD@MitigationRegUtils@@SAJAEBQEAUHKEY__@@W4MitigationRegistryKey@@PEBGK2@Z; MitigationRegUtils::SetMitigationRegDWORD(HKEY__ * const &,MitigationRegistryKey,ushort const *,ulong,ushort const *)
0x18001e544  mov     esi, eax
0x18001e546  test    eax, eax
0x18001e548  jns     short loc_18001E554
0x18001e54a  mov     edx, 1FDh
0x18001e54f  jmp     loc_18001E472
0x18001e554  mov     rax, [rdi+10h]
0x18001e558  cmp     rax, [rdi+18h]
0x18001e55c  jz      short loc_18001E562
0x18001e55e  mov     [rdi+18h], rax
0x18001e562  mov     byte ptr [rdi+28h], 1
0x18001e566  test    rbx, rbx
0x18001e569  jz      short loc_18001E574
0x18001e56b  mov     rcx, rbx; void *
0x18001e56e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001e573  nop
0x18001e574  lea     rcx, [rbp+57h+var_50]
0x18001e578  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001e57d  xor     eax, eax
0x18001e57f  mov     rcx, [rbp+57h+var_30]
0x18001e583  xor     rcx, rsp; StackCookie
0x18001e586  call    __security_check_cookie
0x18001e58b  lea     r11, [rsp+0E0h+var_20]
0x18001e593  mov     rbx, [r11+38h]
0x18001e597  mov     rsi, [r11+40h]
0x18001e59b  mov     rsp, r11
0x18001e59e  pop     r15
0x18001e5a0  pop     r14
0x18001e5a2  pop     r13
0x18001e5a4  pop     rdi
0x18001e5a5  pop     rbp
0x18001e5a6  retn
0x18001e5a7  mov     rcx, [rbp+5Fh]; this
0x18001e5ab  mov     ebx, 8007000Eh
0x18001e5b0  mov     r9d, ebx; char *
0x18001e5b3  lea     r8, aOnecoreBaseDia_13; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18001e5ba  mov     edx, 1E7h; void *
0x18001e5bf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e5c4  nop
0x18001e5c5  jmp     loc_18001E7B5
0x18001e5ca  test    edx, edx
0x18001e5cc  jz      short loc_18001E574
0x18001e5ce  mov     ecx, edx
0x18001e5d0  mov     rax, 2E8BA2E8BA2E8BA3h
0x18001e5da  mul     rcx
0x18001e5dd  shr     rdx, 3
0x18001e5e1  mov     r15d, edx
0x18001e5e4  mov     eax, 2Ch ; ','
0x18001e5e9  mul     r15
0x18001e5ec  mov     rbx, rax
0x18001e5ef  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18001e5f6  cmovb   rbx, rax
0x18001e5fa  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001e601  mov     rcx, rbx; unsigned __int64
0x18001e604  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001e609  mov     rsi, rax
0x18001e60c  test    rax, rax
0x18001e60f  jz      short loc_18001E620
0x18001e611  mov     r8, rbx; Size
0x18001e614  xor     edx, edx; Val
0x18001e616  mov     rcx, rax; void *
0x18001e619  call    memset_0
0x18001e61e  jmp     short loc_18001E622
0x18001e620  xor     esi, esi
0x18001e622  mov     [rbp+57h+var_88], rsi
0x18001e626  test    rsi, rsi
0x18001e629  jz      loc_18001E797
0x18001e62f  lea     rcx, [rbp+57h+var_50]
0x18001e633  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001e638  mov     rdx, rax; lpSubKey
0x18001e63b  lea     rax, [rbp+57h+var_A0]
0x18001e63f  mov     [rsp+0E0h+pcbData], rax; pcbData
0x18001e644  mov     [rsp+0E0h+pvData], rsi; pvData
0x18001e649  lea     rax, [rbp+57h+var_9C]
0x18001e64d  mov     [rsp+0E0h+pdwType], rax; int
0x18001e652  mov     r9d, 8; dwFlags
0x18001e658  lea     r8, ValueName; "Log"
0x18001e65f  mov     rcx, r13; hkey
0x18001e662  call    cs:__imp_RegGetValueW
0x18001e668  test    eax, eax
0x18001e66a  jz      short loc_18001E693
0x18001e66c  mov     rcx, [rbp+5Fh]; this
0x18001e670  mov     r9d, eax; char *
0x18001e673  lea     r8, aOnecoreBaseDia_13; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18001e67a  mov     edx, 21Ah; void *
0x18001e67f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001e684  mov     ebx, eax
0x18001e686  mov     rcx, rsi; void *
0x18001e689  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001e68e  jmp     loc_18001E7B5
0x18001e693  cmp     [rbp+57h+var_9C], 3
0x18001e697  jz      short loc_18001E6B8
0x18001e699  mov     rcx, [rbp+5Fh]; this
0x18001e69d  mov     ebx, 800703F2h
0x18001e6a2  mov     r9d, ebx; char *
0x18001e6a5  lea     r8, aOnecoreBaseDia_13; "onecore\\base\\diagnosis\\mitigation\\c"...
0x18001e6ac  mov     edx, 21Dh; void *
0x18001e6b1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e6b6  jmp     short loc_18001E686
0x18001e6b8  lea     rbx, [rdi+10h]
0x18001e6bc  mov     r8, r15
0x18001e6bf  mov     rdx, rsi
0x18001e6c2  mov     rcx, rbx
0x18001e6c5  call    ??$_Assign_counted_range@PEAU_AVAILABLE_MITIGATION_RECORD@@@?$vector@U_AVAILABLE_MITIGATION_RECORD@@V?$allocator@U_AVAILABLE_MITIGATION_RECORD@@@std@@@std@@AEAAXPEAU_AVAILABLE_MITIGATION_RECORD@@_K@Z; std::vector<_AVAILABLE_MITIGATION_RECORD>::_Assign_counted_range<_AVAILABLE_MITIGATION_RECORD *>(_AVAILABLE_MITIGATION_RECORD *,unsigned __int64)
0x18001e6ca  mov     rcx, [rbx]
0x18001e6cd  mov     rdx, [rbx+8]
0x18001e6d1  mov     rax, rdx
0x18001e6d4  sub     rax, rcx
0x18001e6d7  sar     rax, 2
0x18001e6db  mov     r15, 2E8BA2E8BA2E8BA3h
0x18001e6e5  imul    rax, r15
0x18001e6e9  cmp     rax, 1
0x18001e6ed  jbe     short loc_18001E755
0x18001e6ef  add     rdx, 0FFFFFFFFFFFFFFECh; lpFileTime2
0x18001e6f3  add     rcx, 18h; lpFileTime1
0x18001e6f7  call    cs:__imp_CompareFileTime
0x18001e6fd  cmp     eax, 1
0x18001e700  jnz     short loc_18001E755
0x18001e702  mov     rcx, [rbx]
0x18001e705  mov     rax, [rdi+18h]
0x18001e709  jmp     short loc_18001E750
0x18001e70b  sub     rax, 2Ch ; ','
  ... truncated ...
```
