# ShouldSecureBootSkipUpdateOnHP(int *,ushort const * *,ushort * *)

- ea: `0x18003d444`
- end: `0x18003d874`
- name: `?ShouldSecureBootSkipUpdateOnHP@@YAJPEAHPEAPEBGPEAPEAG@Z`
- size: `1072`
- prototype: `__int64 __fastcall(int *, const unsigned __int16 **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18003d8e0`

## callees

- `0x1800394b0`
- `0x18003c0b8`
- `0x18003c254`
- `0x18003c688`
- `0x18003c99c`
- `0x18003d0e8`
- `0x18003d444`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003d7f8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003d811`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003d82a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003d843`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003d7f8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003d811`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003d82a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003d843`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003d7ea`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003d803`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003d81c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003d835`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003d7ea`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003d803`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003d81c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003d835`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x18003d4dd`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x18003d4fa`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x18003d5b5`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x18003d5f6`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x18003d693`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x18003d4dd`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x18003d4fa`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x18003d5b5`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x18003d5f6`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrIW` at `0x18003d693`

## string_xrefs

- `0x18003d753`: `HPCommercialBIOS`
- `0x18003d4ba`: `SystemManufacturerRegistryFailed`
- `0x18003d515`: `SystemManufacturer is not HP or Hewlett-Packard, will proceed with update installation`
- `0x18003d578`: `BIOSReleaseDate is newer than 2027, will proceed with update installation`
- `0x18003d55a`: `BIOSReleaseDateRegistryFailed`
- `0x18003d59f`: `SystemVersionRegistryFailed`
- `0x18003d5e0`: `BaseBoardProductRegistryFailed`
- `0x18003d67c`: `SystemFamilyRegistryFailed`
- `0x18003d61f`: `BaseBoard is Z series containing fix, will proceed with the update installation`
- `0x18003d851`: `ShouldSecureBootSkipUpdateOnHP`
- `0x18003d783`: `ShouldSecureBootSkipUpdateOnHP returned: %x\nSystemManufacturer: %ls\nSystemVersion: %ls\nSystemFamily: %ls\nBIOSReleaseDate: %ls\nBaseBoardProduct: %ls\nBiosYear: %d\nisHP: %d\nisHewlettPackard: %d\nhasHPCommercialBIOS: %d\nisSystemFamily103C: %d\nisOEMStringEDK2_1: %d\nisHPCommercialBaseBoard: %d\nisSystemVersionSBKPFV3: %d\npShouldSkipUpdate: %d\npSkipReason: %ls`

## pseudocode

```c
__int64 __fastcall ShouldSecureBootSkipUpdateOnHP(int *a1, const unsigned __int16 **a2, unsigned __int16 **a3)
{
  int v3; // esi
  WCHAR *v4; // r12
  unsigned __int16 *v5; // r13
  int v6; // r15d
  int HWSystemInformationFromRegistry; // r14d
  BOOL v8; // edi
  const unsigned __int16 *v9; // rbx
  int v10; // r9d
  int *v11; // r8
  const unsigned __int16 **v12; // rcx
  PWSTR v13; // rbx
  PWSTR v14; // rax
  int v15; // eax
  int v16; // eax
  PWSTR v17; // rax
  unsigned __int16 *v18; // rbx
  BOOL v19; // ebx
  const unsigned __int16 *v20; // rdx
  _bstr_t::Data_t *v21; // r8
  _bstr_t::Data_t *v22; // r9
  int v23; // eax
  int v24; // ecx
  const unsigned __int16 *v25; // rax
  bool v26; // zf
  WCHAR *v27; // rsi
  WCHAR *v28; // rdi
  HANDLE ProcessHeap; // rax
  HANDLE v30; // rax
  HANDLE v31; // rax
  HANDLE v32; // rax
  BOOL v34; // [rsp+48h] [rbp-89h]
  int v35; // [rsp+50h] [rbp-81h]
  BOOL v36; // [rsp+98h] [rbp-39h]
  BOOL v37; // [rsp+9Ch] [rbp-35h]
  int v38; // [rsp+A0h] [rbp-31h]
  PCWSTR v39; // [rsp+A8h] [rbp-29h] BYREF
  unsigned int BiosYear; // [rsp+B0h] [rbp-21h]
  unsigned __int16 *v41; // [rsp+B8h] [rbp-19h] BYREF
  unsigned __int16 *v42; // [rsp+C0h] [rbp-11h] BYREF
  PCWSTR pszFirst; // [rsp+C8h] [rbp-9h] BYREF
  PCWSTR v44; // [rsp+D0h] [rbp-1h] BYREF
  PWSTR v45; // [rsp+D8h] [rbp+7h]
  PWSTR v46; // [rsp+E0h] [rbp+Fh]
  int v50; // [rsp+150h] [rbp+7Fh] BYREF

  v3 = 0;
  *a1 = 0;
  pszFirst = 0;
  v4 = 0;
  v39 = 0;
  v44 = 0;
  v5 = 0;
  v41 = 0;
  v6 = 0;
  v42 = 0;
  BiosYear = 0;
  v38 = 0;
  v36 = 0;
  v50 = 0;
  v37 = 0;
  HWSystemInformationFromRegistry = GetHWSystemInformationFromRegistry(
                                      L"HARDWARE\\DESCRIPTION\\System\\BIOS",
                                      L"SystemManufacturer",
                                      (unsigned __int16 **)&pszFirst);
  if ( HWSystemInformationFromRegistry < 0 )
  {
    v8 = 0;
    v9 = L"SystemManufacturerRegistryFailed";
LABEL_3:
    v10 = v50;
LABEL_4:
    v11 = a1;
    v12 = a2;
    goto LABEL_40;
  }
  v13 = StrStrIW(pszFirst, L"HP");
  v8 = v13 != 0;
  v14 = StrStrIW(pszFirst, L"Hewlett-Packard");
  v45 = v14;
  LOBYTE(v3) = v14 != 0;
  if ( v13 || v14 )
  {
    v15 = GetHWSystemInformationFromRegistry(L"HARDWARE\\DESCRIPTION\\System\\BIOS", L"BIOSReleaseDate", &v41);
    v5 = v41;
    HWSystemInformationFromRegistry = v15;
    if ( v15 < 0 )
    {
      v9 = L"BIOSReleaseDateRegistryFailed";
      goto LABEL_3;
    }
    BiosYear = GetBiosYear(v41);
    if ( BiosYear >= 0x7EB )
    {
      SBServicingLogMessage(L"BIOSReleaseDate is newer than 2027, will proceed with update installation");
      goto LABEL_8;
    }
    v16 = GetHWSystemInformationFromRegistry(
            L"HARDWARE\\DESCRIPTION\\System\\BIOS",
            L"SystemVersion",
            (unsigned __int16 **)&v39);
    v4 = (WCHAR *)v39;
    HWSystemInformationFromRegistry = v16;
    if ( v16 < 0 )
    {
      v9 = L"SystemVersionRegistryFailed";
      goto LABEL_3;
    }
    v39 = StrStrIW(v39, L"SBKPFV3");
    LOBYTE(v6) = v39 != 0;
    HWSystemInformationFromRegistry = GetHWSystemInformationFromRegistry(
                                        L"HARDWARE\\DESCRIPTION\\System\\BIOS",
                                        L"BaseBoardProduct",
                                        &v42);
    if ( HWSystemInformationFromRegistry < 0 )
    {
      v9 = L"BaseBoardProductRegistryFailed";
      goto LABEL_3;
    }
    v17 = StrStrIW(v4, L"SBKPF");
    v18 = v42;
    if ( v17 && LookupStringInArray((const unsigned __int16 *const *const)&g_HPZSeriesBaseBoardProductList, 4u, v42, 0) )
    {
      SBServicingLogMessage((wchar_t *)L"BaseBoard is Z series containing fix, will proceed with the update installation");
      v11 = a1;
      *a1 = 0;
      goto LABEL_9;
    }
    LODWORD(v41) = LookupStringInArray(
                     (const unsigned __int16 *const *const)&g_HPCommercialBaseBoardProductList,
                     3u,
                     v18,
                     0);
    v19 = (_DWORD)v41 != 0;
    v37 = v19;
    HWSystemInformationFromRegistry = GetHWSystemInformationFromRegistry(
                                        L"HARDWARE\\DESCRIPTION\\System\\BIOS",
                                        L"SystemFamily",
                                        (unsigned __int16 **)&v44);
    if ( HWSystemInformationFromRegistry < 0 )
    {
      v9 = L"SystemFamilyRegistryFailed";
      goto LABEL_3;
    }
    v46 = StrStrIW(v44, L"103C_");
    v36 = v46 != 0;
    v23 = IsHPFeatureEnabled((const unsigned __int16 *)(v46 != 0), v20, v21, v22, &v50, a3);
    v10 = v50;
    HWSystemInformationFromRegistry = v23;
    if ( v23 < 0 )
    {
      v9 = L"IsHPFeatureEnabledOEMStringArray";
      goto LABEL_4;
    }
    if ( v50 || (_DWORD)v41 )
    {
      v11 = a1;
      v26 = v39 == 0;
      v38 = 1;
      *a1 = v39 == 0;
      v25 = L"HPCommercialBIOS";
      if ( !v26 )
        v25 = &sourceString;
    }
    else
    {
      v38 = 0;
      if ( !v45 )
      {
        v11 = a1;
        v12 = a2;
LABEL_38:
        v37 = v19;
        goto LABEL_39;
      }
      if ( !v46 || (v24 = 1, v39) )
        v24 = 0;
      v11 = a1;
      v25 = L"SystemFamily103C_NotSBKPFV3";
      if ( !v24 )
        v25 = &sourceString;
      *a1 = v24;
    }
    v12 = a2;
    *a2 = v25;
    goto LABEL_38;
  }
  SBServicingLogMessage((wchar_t *)L"SystemManufacturer is not HP or Hewlett-Packard, will proceed with update installation");
LABEL_8:
  v11 = a1;
  *a1 = 0;
LABEL_9:
  v10 = v50;
  v12 = a2;
LABEL_39:
  v9 = L"Passed";
LABEL_40:
  v35 = v3;
  v27 = (WCHAR *)pszFirst;
  v34 = v8;
  v28 = (WCHAR *)v44;
  SBServicingLogMessage(
    (wchar_t *)L"ShouldSecureBootSkipUpdateOnHP returned: %x\n"
                "SystemManufacturer: %ls\n"
                "SystemVersion: %ls\n"
                "SystemFamily: %ls\n"
                "BIOSReleaseDate: %ls\n"
                "BaseBoardProduct: %ls\n"
                "BiosYear: %d\n"
                "isHP: %d\n"
                "isHewlettPackard: %d\n"
                "hasHPCommercialBIOS: %d\n"
                "isSystemFamily103C: %d\n"
                "isOEMStringEDK2_1: %d\n"
                "isHPCommercialBaseBoard: %d\n"
                "isSystemVersionSBKPFV3: %d\n"
                "pShouldSkipUpdate: %d\n"
                "pSkipReason: %ls",
    (unsigned int)HWSystemInformationFromRegistry,
    pszFirst,
    v4,
    v44,
    v5,
    v42,
    BiosYear,
    v34,
    v35,
    v38,
    v36,
    v10,
    v37,
    v6,
    *v11,
    *v12);
  if ( v27 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v27);
  }
  if ( v4 )
  {
    v30 = GetProcessHeap();
    HeapFree(v30, 0, v4);
  }
  if ( v28 )
  {
    v31 = GetProcessHeap();
    HeapFree(v31, 0, v28);
  }
  if ( v5 )
  {
    v32 = GetProcessHeap();
    HeapFree(v32, 0, v5);
  }
  if ( HWSystemInformationFromRegistry < 0 )
    SBServicingCoreTelemetryProvider::SBServicingCoreFunctionFailed(L"ShouldSecureBootSkipUpdateOnHP", v9);
  return (unsigned int)HWSystemInformationFromRegistry;
}

```

## disassembly

```asm
0x18003d444  mov     rax, rsp
0x18003d447  mov     [rax+18h], r8
0x18003d44b  mov     [rax+10h], rdx
0x18003d44f  mov     [rax+8], rcx
0x18003d453  push    rbp
0x18003d454  push    rbx
0x18003d455  push    rsi
0x18003d456  push    rdi
0x18003d457  push    r12
0x18003d459  push    r13
0x18003d45b  push    r14
0x18003d45d  push    r15
0x18003d45f  lea     rbp, [rax-5Fh]
0x18003d463  sub     rsp, 0E8h
0x18003d46a  xor     esi, esi
0x18003d46c  lea     r8, [rbp+57h+pszFirst]; unsigned __int16 **
0x18003d470  mov     [rcx], esi
0x18003d472  lea     rdx, aSystemmanufact_0; "SystemManufacturer"
0x18003d479  lea     rcx, aHardwareDescri; "HARDWARE\\DESCRIPTION\\System\\BIOS"
0x18003d480  mov     [rbp+57h+pszFirst], rsi
0x18003d484  mov     r12d, esi
0x18003d487  mov     [rbp+57h+var_80], rsi
0x18003d48b  mov     [rbp+57h+var_58], rsi
0x18003d48f  mov     r13d, esi
0x18003d492  mov     [rbp+57h+var_70], rsi
0x18003d496  mov     r15d, esi
0x18003d499  mov     [rbp+57h+var_68], rsi
0x18003d49d  mov     [rbp+57h+var_78], esi
0x18003d4a0  mov     [rbp+57h+var_88], esi
0x18003d4a3  mov     [rbp+57h+var_90], esi
0x18003d4a6  mov     [rbp+57h+arg_18], esi
0x18003d4a9  mov     [rbp+57h+var_8C], esi
0x18003d4ac  call    ?GetHWSystemInformationFromRegistry@@YAJPEBG0PEAPEAG@Z; GetHWSystemInformationFromRegistry(ushort const *,ushort const *,ushort * *)
0x18003d4b1  mov     r14d, eax
0x18003d4b4  test    eax, eax
0x18003d4b6  jns     short loc_18003D4D2
0x18003d4b8  mov     edi, esi
0x18003d4ba  lea     rbx, aSystemmanufact_1; "SystemManufacturerRegistryFailed"
0x18003d4c1  mov     r9d, [rbp+57h+arg_18]
0x18003d4c5  mov     r8, [rbp+57h+arg_0]
0x18003d4c9  mov     rcx, [rbp+57h+arg_8]
0x18003d4cd  jmp     loc_18003D775
0x18003d4d2  mov     rcx, [rbp+57h+pszFirst]; pszFirst
0x18003d4d6  lea     rdx, aHp; "HP"
0x18003d4dd  call    cs:__imp_StrStrIW
0x18003d4e3  mov     rcx, [rbp+57h+pszFirst]; pszFirst
0x18003d4e7  lea     rdx, aHewlettPackard; "Hewlett-Packard"
0x18003d4ee  test    rax, rax
0x18003d4f1  mov     edi, esi
0x18003d4f3  mov     rbx, rax
0x18003d4f6  setnz   dil
0x18003d4fa  call    cs:__imp_StrStrIW
0x18003d500  test    rax, rax
0x18003d503  mov     [rbp+57h+var_50], rax
0x18003d507  setnz   sil
0x18003d50b  test    rbx, rbx
0x18003d50e  jnz     short loc_18003D535
0x18003d510  test    rax, rax
0x18003d513  jnz     short loc_18003D535
0x18003d515  lea     rcx, aSystemmanufact; "SystemManufacturer is not HP or Hewlett"...
0x18003d51c  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x18003d521  mov     r8, [rbp+57h+arg_0]
0x18003d525  mov     [r8], r12d
0x18003d528  mov     r9d, [rbp+57h+arg_18]
0x18003d52c  mov     rcx, [rbp+57h+arg_8]
0x18003d530  jmp     loc_18003D76E
0x18003d535  lea     rbx, aHardwareDescri; "HARDWARE\\DESCRIPTION\\System\\BIOS"
0x18003d53c  mov     rcx, rbx; unsigned __int16 *
0x18003d53f  lea     r8, [rbp+57h+var_70]; unsigned __int16 **
0x18003d543  lea     rdx, aBiosreleasedat_0; "BIOSReleaseDate"
0x18003d54a  call    ?GetHWSystemInformationFromRegistry@@YAJPEBG0PEAPEAG@Z; GetHWSystemInformationFromRegistry(ushort const *,ushort const *,ushort * *)
0x18003d54f  mov     r13, [rbp+57h+var_70]
0x18003d553  mov     r14d, eax
0x18003d556  test    eax, eax
0x18003d558  jns     short loc_18003D566
0x18003d55a  lea     rbx, aBiosreleasedat; "BIOSReleaseDateRegistryFailed"
0x18003d561  jmp     loc_18003D4C1
0x18003d566  mov     rcx, r13; unsigned __int16 *
0x18003d569  call    ?GetBiosYear@@YAKPEAG@Z; GetBiosYear(ushort *)
0x18003d56e  mov     [rbp+57h+var_78], eax
0x18003d571  cmp     eax, 7EBh
0x18003d576  jb      short loc_18003D581
0x18003d578  lea     rcx, aBiosreleasedat_1; "BIOSReleaseDate is newer than 2027, wil"...
0x18003d57f  jmp     short loc_18003D51C
0x18003d581  lea     r8, [rbp+57h+var_80]; unsigned __int16 **
0x18003d585  mov     rcx, rbx; unsigned __int16 *
0x18003d588  lea     rdx, aSystemversion; "SystemVersion"
0x18003d58f  call    ?GetHWSystemInformationFromRegistry@@YAJPEBG0PEAPEAG@Z; GetHWSystemInformationFromRegistry(ushort const *,ushort const *,ushort * *)
0x18003d594  mov     r12, [rbp+57h+var_80]
0x18003d598  mov     r14d, eax
0x18003d59b  test    eax, eax
0x18003d59d  jns     short loc_18003D5AB
0x18003d59f  lea     rbx, aSystemversionr; "SystemVersionRegistryFailed"
0x18003d5a6  jmp     loc_18003D4C1
0x18003d5ab  lea     rdx, aSbkpfv3; "SBKPFV3"
0x18003d5b2  mov     rcx, r12; pszFirst
0x18003d5b5  call    cs:__imp_StrStrIW
0x18003d5bb  lea     r8, [rbp+57h+var_68]; unsigned __int16 **
0x18003d5bf  mov     rcx, rbx; unsigned __int16 *
0x18003d5c2  lea     rdx, aBaseboardprodu_0; "BaseBoardProduct"
0x18003d5c9  mov     [rbp+57h+var_80], rax
0x18003d5cd  test    rax, rax
0x18003d5d0  setnz   r15b
0x18003d5d4  call    ?GetHWSystemInformationFromRegistry@@YAJPEBG0PEAPEAG@Z; GetHWSystemInformationFromRegistry(ushort const *,ushort const *,ushort * *)
0x18003d5d9  mov     r14d, eax
0x18003d5dc  test    eax, eax
0x18003d5de  jns     short loc_18003D5EC
0x18003d5e0  lea     rbx, aBaseboardprodu; "BaseBoardProductRegistryFailed"
0x18003d5e7  jmp     loc_18003D4C1
0x18003d5ec  lea     rdx, aSbkpf; "SBKPF"
0x18003d5f3  mov     rcx, r12; pszFirst
0x18003d5f6  call    cs:__imp_StrStrIW
0x18003d5fc  mov     rbx, [rbp+57h+var_68]
0x18003d600  test    rax, rax
0x18003d603  jz      short loc_18003D63B
0x18003d605  xor     r9d, r9d; int
0x18003d608  lea     rcx, ?g_HPZSeriesBaseBoardProductList@@3QBQEBGB; unsigned __int16 **
0x18003d60f  mov     r8, rbx; unsigned __int16 *
0x18003d612  lea     edx, [r9+4]; unsigned __int64
0x18003d616  call    ?LookupStringInArray@@YAHQEBQEBG_KPEBGH@Z; LookupStringInArray(ushort const * const * const,unsigned __int64,ushort const *,int)
0x18003d61b  test    eax, eax
0x18003d61d  jz      short loc_18003D63B
0x18003d61f  lea     rcx, aBaseboardIsZSe; "BaseBoard is Z series containing fix, w"...
0x18003d626  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x18003d62b  mov     r8, [rbp+57h+arg_0]
0x18003d62f  mov     dword ptr [r8], 0
0x18003d636  jmp     loc_18003D528
0x18003d63b  xor     r9d, r9d; int
0x18003d63e  lea     rcx, ?g_HPCommercialBaseBoardProductList@@3QBQEBGB; unsigned __int16 **
0x18003d645  mov     r8, rbx; unsigned __int16 *
0x18003d648  lea     edx, [r9+3]; unsigned __int64
0x18003d64c  call    ?LookupStringInArray@@YAHQEBQEBG_KPEBGH@Z; LookupStringInArray(ushort const * const * const,unsigned __int64,ushort const *,int)
0x18003d651  xor     ebx, ebx
0x18003d653  mov     dword ptr [rbp+57h+var_70], eax
0x18003d656  test    eax, eax
0x18003d658  lea     r8, [rbp+57h+var_58]; unsigned __int16 **
0x18003d65c  lea     rdx, aSystemfamily; "SystemFamily"
0x18003d663  setnz   bl
0x18003d666  lea     rcx, aHardwareDescri; "HARDWARE\\DESCRIPTION\\System\\BIOS"
0x18003d66d  mov     [rbp+57h+var_8C], ebx
0x18003d670  call    ?GetHWSystemInformationFromRegistry@@YAJPEBG0PEAPEAG@Z; GetHWSystemInformationFromRegistry(ushort const *,ushort const *,ushort * *)
0x18003d675  mov     r14d, eax
0x18003d678  test    eax, eax
0x18003d67a  jns     short loc_18003D688
0x18003d67c  lea     rbx, aSystemfamilyre; "SystemFamilyRegistryFailed"
0x18003d683  jmp     loc_18003D4C1
0x18003d688  mov     rcx, [rbp+57h+var_58]; pszFirst
0x18003d68c  lea     rdx, a103c; "103C_"
0x18003d693  call    cs:__imp_StrStrIW
0x18003d699  xor     ecx, ecx
0x18003d69b  mov     [rbp+57h+var_48], rax
0x18003d69f  test    rax, rax
0x18003d6a2  mov     rax, [rbp+57h+arg_10]
0x18003d6a6  mov     [rsp+120h+var_F8], rax; unsigned __int16 **
0x18003d6ab  lea     rax, [rbp+57h+arg_18]
0x18003d6af  setnz   cl; unsigned __int16 *
0x18003d6b2  mov     [rsp+120h+var_100], rax; int *
0x18003d6b7  mov     [rbp+57h+var_90], ecx
0x18003d6ba  call    ?IsHPFeatureEnabled@@YAJPEBG000PEAHPEAPEAG@Z; IsHPFeatureEnabled(ushort const *,ushort const *,ushort const *,ushort const *,int *,ushort * *)
0x18003d6bf  mov     r9d, [rbp+57h+arg_18]
0x18003d6c3  xor     r10d, r10d
0x18003d6c6  mov     r14d, eax
0x18003d6c9  test    eax, eax
0x18003d6cb  jns     short loc_18003D6DF
0x18003d6cd  mov     eax, [rbp+57h+var_8C]
0x18003d6d0  lea     rbx, aIshpfeatureena; "IsHPFeatureEnabledOEMStringArray"
0x18003d6d7  mov     [rbp+57h+var_8C], eax
0x18003d6da  jmp     loc_18003D4C5
0x18003d6df  test    r9d, r9d
0x18003d6e2  jnz     short loc_18003D72E
0x18003d6e4  cmp     dword ptr [rbp+57h+var_70], r10d
0x18003d6e8  jnz     short loc_18003D72E
0x18003d6ea  mov     [rbp+57h+var_88], r10d
0x18003d6ee  cmp     [rbp+57h+var_50], r10
0x18003d6f2  jz      short loc_18003D724
0x18003d6f4  cmp     [rbp+57h+var_48], r10
0x18003d6f8  jz      short loc_18003D704
0x18003d6fa  lea     ecx, [r9+1]
0x18003d6fe  cmp     [rbp+57h+var_80], r10
0x18003d702  jz      short loc_18003D707
0x18003d704  mov     ecx, r10d
0x18003d707  mov     r8, [rbp+57h+arg_0]
0x18003d70b  lea     rdx, sourceString
0x18003d712  test    ecx, ecx
0x18003d714  lea     rax, aSystemfamily10; "SystemFamily103C_NotSBKPFV3"
0x18003d71b  cmovz   rax, rdx
0x18003d71f  mov     [r8], ecx
0x18003d722  jmp     short loc_18003D75E
0x18003d724  mov     r8, [rbp+57h+arg_0]
0x18003d728  mov     rcx, [rbp+57h+arg_8]
0x18003d72c  jmp     short loc_18003D765
0x18003d72e  mov     rcx, [rbp+57h+var_80]
0x18003d732  lea     rdx, sourceString
0x18003d739  mov     r8, [rbp+57h+arg_0]
0x18003d73d  mov     eax, r10d
0x18003d740  test    rcx, rcx
0x18003d743  mov     [rbp+57h+var_88], 1
0x18003d74a  setz    al
0x18003d74d  test    rcx, rcx
0x18003d750  mov     [r8], eax
0x18003d753  lea     rax, aHpcommercialbi; "HPCommercialBIOS"
0x18003d75a  cmovnz  rax, rdx
0x18003d75e  mov     rcx, [rbp+57h+arg_8]
0x18003d762  mov     [rcx], rax
0x18003d765  mov     eax, [rbp+57h+var_90]
0x18003d768  mov     [rbp+57h+var_90], eax
0x18003d76b  mov     [rbp+57h+var_8C], ebx
0x18003d76e  lea     rbx, aPassed; "Passed"
0x18003d775  mov     rax, [rcx]
0x18003d778  mov     edx, r14d
0x18003d77b  mov     [rsp+80h], rax
0x18003d783  lea     rcx, aShouldsecurebo_14; "ShouldSecureBootSkipUpdateOnHP returned"...
0x18003d78a  mov     eax, [r8]
0x18003d78d  mov     dword ptr [rsp+120h+var_A8], eax
0x18003d791  mov     eax, [rbp+57h+var_8C]
0x18003d794  mov     [rsp+120h+var_B0], r15d
0x18003d799  mov     [rsp+120h+var_B8], eax
0x18003d79d  mov     eax, [rbp+57h+var_90]
0x18003d7a0  mov     [rsp+120h+var_C0], r9d
0x18003d7a5  mov     r9, r12
0x18003d7a8  mov     [rsp+120h+var_C8], eax
0x18003d7ac  mov     eax, [rbp+57h+var_88]
0x18003d7af  mov     [rsp+120h+var_D0], eax
0x18003d7b3  mov     eax, [rbp+57h+var_78]
0x18003d7b6  mov     [rsp+120h+var_D8], esi
0x18003d7ba  mov     rsi, [rbp+57h+pszFirst]
0x18003d7be  mov     [rsp+120h+var_E0], edi
0x18003d7c2  mov     r8, rsi
0x18003d7c5  mov     rdi, [rbp+57h+var_58]
0x18003d7c9  mov     [rsp+120h+var_E8], eax
0x18003d7cd  mov     rax, [rbp+57h+var_68]
0x18003d7d1  mov     qword ptr [rsp+120h+var_F0], rax
0x18003d7d6  mov     [rsp+120h+var_F8], r13
0x18003d7db  mov     [rsp+120h+var_100], rdi
0x18003d7e0  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x18003d7e5  test    rsi, rsi
0x18003d7e8  jz      short loc_18003D7FE
0x18003d7ea  call    cs:__imp_GetProcessHeap
0x18003d7f0  mov     r8, rsi; lpMem
0x18003d7f3  xor     edx, edx; dwFlags
0x18003d7f5  mov     rcx, rax; hHeap
0x18003d7f8  call    cs:__imp_HeapFree
0x18003d7fe  test    r12, r12
0x18003d801  jz      short loc_18003D817
0x18003d803  call    cs:__imp_GetProcessHeap
0x18003d809  mov     r8, r12; lpMem
0x18003d80c  xor     edx, edx; dwFlags
0x18003d80e  mov     rcx, rax; hHeap
0x18003d811  call    cs:__imp_HeapFree
0x18003d817  test    rdi, rdi
0x18003d81a  jz      short loc_18003D830
0x18003d81c  call    cs:__imp_GetProcessHeap
0x18003d822  mov     r8, rdi; lpMem
0x18003d825  xor     edx, edx; dwFlags
0x18003d827  mov     rcx, rax; hHeap
0x18003d82a  call    cs:__imp_HeapFree
0x18003d830  test    r13, r13
0x18003d833  jz      short loc_18003D849
0x18003d835  call    cs:__imp_GetProcessHeap
0x18003d83b  mov     r8, r13; lpMem
0x18003d83e  xor     edx, edx; dwFlags
0x18003d840  mov     rcx, rax; hHeap
0x18003d843  call    cs:__imp_HeapFree
0x18003d849  test    r14d, r14d
0x18003d84c  jns     short loc_18003D85D
0x18003d84e  mov     rdx, rbx; unsigned __int16 *
0x18003d851  lea     rcx, aShouldsecurebo_0; "ShouldSecureBootSkipUpdateOnHP"
0x18003d858  call    ?SBServicingCoreFunctionFailed@SBServicingCoreTelemetryProvider@@SAXPEBG0@Z; SBServicingCoreTelemetryProvider::SBServicingCoreFunctionFailed(ushort const *,ushort const *)
0x18003d85d  mov     eax, r14d
0x18003d860  add     rsp, 0E8h
0x18003d867  pop     r15
0x18003d869  pop     r14
0x18003d86b  pop     r13
0x18003d86d  pop     r12
0x18003d86f  pop     rdi
0x18003d870  pop     rsi
0x18003d871  pop     rbx
0x18003d872  pop     rbp
0x18003d873  retn
```
