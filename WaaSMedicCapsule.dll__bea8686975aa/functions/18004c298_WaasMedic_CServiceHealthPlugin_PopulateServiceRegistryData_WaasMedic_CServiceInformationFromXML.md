# WaasMedic::CServiceHealthPlugin::PopulateServiceRegistryData(WaasMedic::CServiceInformationFromXML *)

- ea: `0x18004c298`
- end: `0x18004c7e5`
- name: `?PopulateServiceRegistryData@CServiceHealthPlugin@WaasMedic@@AEAAJPEAVCServiceInformationFromXML@2@@Z`
- size: `1357`
- prototype: `__int64 __fastcall(WaasMedic::CServiceHealthPlugin *__hidden this, struct WaasMedic::CServiceInformationFromXML *)`
- caller_count: `1`
- callee_count: `12`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18004ca5c`

## callees

- `0x1800017ac`
- `0x180003bb0`
- `0x1800070cc`
- `0x180007590`
- `0x180009a54`
- `0x180016c9c`
- `0x18002543c`
- `0x180029168`
- `0x1800291a8`
- `0x180029214`
- `0x180029d14`
- `0x18004c298`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004c416`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004c461`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004c416`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004c461`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18004c31c`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18004c31c`

## string_xrefs

- `0x18004c2da`: `onecore\enduser\waasmedic\lib\plugins\servicehealthplugin.cpp`
- `0x18004c332`: `onecore\enduser\waasmedic\lib\plugins\servicehealthplugin.cpp`
- `0x18004c3fa`: `onecore\enduser\waasmedic\lib\plugins\servicehealthplugin.cpp`
- `0x18004c446`: `Failed to write %s.  ErrorCode = 0x%08x`
- `0x18004c475`: `Failed to write %s.  ErrorCode = 0x%08x`
- `0x18004c4b0`: `Failed to write %s.  ErrorCode = 0x%08x`
- `0x18004c4eb`: `Failed to write %s.  ErrorCode = 0x%08x`
- `0x18004c526`: `Failed to write %s.  ErrorCode = 0x%08x`
- `0x18004c561`: `Failed to write %s.  ErrorCode = 0x%08x`
- `0x18004c59c`: `Failed to write %s.  ErrorCode = 0x%08x`
- `0x18004c607`: `Failed to write %s.  ErrorCode = 0x%08x`
- `0x18004c672`: `Failed to write %s.  ErrorCode = 0x%08x`
- `0x18004c6b2`: `Failed to write %s.  ErrorCode = 0x%08x`
- `0x18004c384`: `Failed to write registry with E_ACCESSDENIED.  Retrying after resetting permission.`
- `0x18004c5e6`: `DependOnService`
- `0x18004c600`: `DependOnService`
- `0x18004c651`: `RequiredPrivileges`
- `0x18004c66b`: `RequiredPrivileges`
- `0x18004c505`: `ServiceSidType`
- `0x18004c51f`: `ServiceSidType`
- `0x18004c540`: `ImagePath`
- `0x18004c55a`: `ImagePath`
- `0x18004c30c`: `SYSTEM\CurrentControlSet\Services`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WaasMedic::CServiceHealthPlugin::PopulateServiceRegistryData(
        WaasMedic::CServiceHealthPlugin *this,
        struct WaasMedic::CServiceInformationFromXML *a2)
{
  unsigned int v3; // ebx
  __int64 v4; // rdx
  const WCHAR *v6; // r9
  HRESULT v7; // eax
  __int64 v8; // rcx
  unsigned int v9; // edi
  unsigned int v10; // esi
  int v11; // eax
  HKEY v12; // rcx
  __int64 v13; // r15
  int v14; // edi
  __int64 v15; // r8
  int v16; // r14d
  __int64 v17; // rcx
  int v18; // eax
  int v19; // r14d
  int v20; // r12d
  int v21; // eax
  __int64 v22; // rcx
  int v23; // r14d
  int v24; // eax
  __int64 v25; // rcx
  int v26; // r14d
  int v27; // eax
  __int64 v28; // rcx
  int v29; // r14d
  int v30; // eax
  __int64 v31; // rcx
  int v32; // r14d
  int v33; // eax
  __int64 v34; // rcx
  int v35; // r14d
  _WORD *v36; // r9
  _WORD *v37; // rcx
  int v38; // edx
  __int64 v39; // rax
  __int64 v40; // rax
  int v41; // eax
  int v42; // r14d
  _WORD *v43; // r9
  _WORD *v44; // rcx
  int v45; // edx
  __int64 v46; // rax
  __int64 v47; // rax
  int v48; // eax
  int v49; // r14d
  __int64 v50; // r9
  int v51; // eax
  int v52; // r14d
  const struct _tlgProvider_t *v53; // rax
  const struct _tlgProvider_t *v54; // r10
  __int64 v55; // rax
  const OLECHAR *v56; // rax
  __int64 v57; // rdi
  int v58; // [rsp+20h] [rbp-E0h]
  int v59; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v61; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v62; // [rsp+50h] [rbp-B0h] BYREF
  _OWORD v63[2]; // [rsp+58h] [rbp-A8h] BYREF
  char v64[32]; // [rsp+80h] [rbp-80h] BYREF
  __int64 *v65; // [rsp+A0h] [rbp-60h]
  __int64 v66; // [rsp+A8h] [rbp-58h]
  unsigned __int16 *v67; // [rsp+B0h] [rbp-50h]
  int v68; // [rsp+B8h] [rbp-48h]
  int v69; // [rsp+BCh] [rbp-44h]
  const OLECHAR *v70; // [rsp+C0h] [rbp-40h]
  int v71; // [rsp+C8h] [rbp-38h]
  int v72; // [rsp+CCh] [rbp-34h]
  HKEY *p_hKey; // [rsp+D0h] [rbp-30h]
  __int64 v74; // [rsp+D8h] [rbp-28h]
  unsigned int *v75; // [rsp+E0h] [rbp-20h]
  __int64 v76; // [rsp+E8h] [rbp-18h]
  WCHAR pszPathOut[264]; // [rsp+F0h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+358h] [rbp+258h]

  if ( !a2 )
  {
    v3 = -2147467261;
    v4 = 827;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\plugins\\servicehealthplugin.cpp",
      (const char *)v3,
      v58);
    return v3;
  }
  v6 = (const WCHAR *)*((_QWORD *)a2 + 1);
  if ( !v6 )
  {
    v3 = -2147024773;
    v4 = 829;
    goto LABEL_3;
  }
  v7 = PathCchCombine(pszPathOut, 0x104u, L"SYSTEM\\CurrentControlSet\\Services", v6);
  v9 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x340,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\plugins\\servicehealthplugin.cpp",
      (const char *)(unsigned int)v7,
      v58);
    return v9;
  }
  v10 = 0;
  LOBYTE(v58) = 0;
  v11 = WaasMedic::RegSetDwordValue(v8, pszPathOut, L"Type", *((unsigned int *)a2 + 18));
  v13 = -1;
  v14 = 2;
  if ( v11 >= 0 )
    goto LABEL_22;
  if ( v11 != -2147024891 )
  {
    LogLevelW(2u, L"Failed to write %s.  ErrorCode = 0x%08x", L"Type", (unsigned int)v11);
LABEL_22:
    v20 = 0;
    goto LABEL_23;
  }
  LogLevelW(4u, L"Failed to write registry with E_ACCESSDENIED.  Retrying after resetting permission.");
  hKey = HKEY_LOCAL_MACHINE;
  memset(v63, 0, sizeof(v63));
  v15 = -1;
  do
    ++v15;
  while ( pszPathOut[v15] );
  std::wstring::_Construct<1,unsigned short const *>(v63, pszPathOut, v15);
  v16 = WaasMedic::TakeOwnershipAndRestoreSD(&hKey, v63, 0);
  std::wstring::~wstring(v63);
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x34C,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\plugins\\servicehealthplugin.cpp",
      (const char *)(unsigned int)v16,
      v58);
    if ( hKey )
      RegCloseKey(hKey);
    return (unsigned int)v16;
  }
  v18 = WaasMedic::RegSetDwordValue(v17, pszPathOut, L"Type", *((unsigned int *)a2 + 18));
  v19 = v18;
  if ( v18 < 0 )
  {
    LogLevelW(2u, L"Failed to write %s.  ErrorCode = 0x%08x", L"Type", (unsigned int)v18);
    v10 = v19;
  }
  v12 = hKey;
  if ( hKey )
    RegCloseKey(hKey);
  v20 = 1;
LABEL_23:
  v21 = WaasMedic::RegSetDwordValue(v12, pszPathOut, L"Start", *((unsigned int *)a2 + 14));
  v23 = v21;
  if ( v21 < 0 )
  {
    LogLevelW(2u, L"Failed to write %s.  ErrorCode = 0x%08x", L"Start", (unsigned int)v21);
    v10 = v23;
  }
  v24 = WaasMedic::RegSetDwordValue(v22, pszPathOut, L"ErrorControl", *((unsigned int *)a2 + 13));
  v26 = v24;
  if ( v24 < 0 )
  {
    LogLevelW(2u, L"Failed to write %s.  ErrorCode = 0x%08x", L"ErrorControl", (unsigned int)v24);
    v10 = v26;
  }
  v27 = WaasMedic::RegSetDwordValue(v25, pszPathOut, L"ServiceSidType", *((unsigned int *)a2 + 12));
  v29 = v27;
  if ( v27 < 0 )
  {
    LogLevelW(2u, L"Failed to write %s.  ErrorCode = 0x%08x", L"ServiceSidType", (unsigned int)v27);
    v10 = v29;
  }
  v30 = WaasMedic::RegSetStringValue(v28, pszPathOut, L"ImagePath", *((_QWORD *)a2 + 4), 0);
  v32 = v30;
  if ( v30 < 0 )
  {
    LogLevelW(2u, L"Failed to write %s.  ErrorCode = 0x%08x", L"ImagePath", (unsigned int)v30);
    v10 = v32;
  }
  LOBYTE(v59) = 0;
  v33 = WaasMedic::RegSetStringValue(v31, pszPathOut, L"ObjectName", *((_QWORD *)a2 + 5), v59);
  v35 = v33;
  if ( v33 < 0 )
  {
    LogLevelW(2u, L"Failed to write %s.  ErrorCode = 0x%08x", L"ObjectName", (unsigned int)v33);
    v10 = v35;
  }
  v36 = (_WORD *)*((_QWORD *)a2 + 2);
  if ( v36 )
  {
    v37 = (_WORD *)*((_QWORD *)a2 + 2);
    v38 = 0;
    if ( *v36 )
    {
      do
      {
        v39 = -1;
        do
          ++v39;
        while ( v37[v39] );
        v40 = v39 + 1;
        v37 += v40;
        v38 += v40;
      }
      while ( *v37 );
    }
    v41 = WaasMedic::RegSetMultiSzValue(v37, pszPathOut, L"DependOnService");
    v42 = v41;
    if ( v41 < 0 )
    {
      LogLevelW(2u, L"Failed to write %s.  ErrorCode = 0x%08x", L"DependOnService", (unsigned int)v41);
      v10 = v42;
    }
  }
  v43 = (_WORD *)*((_QWORD *)a2 + 3);
  if ( v43 )
  {
    v44 = (_WORD *)*((_QWORD *)a2 + 3);
    v45 = 0;
    if ( *v43 )
    {
      do
      {
        v46 = -1;
        do
          ++v46;
        while ( v44[v46] );
        v47 = v46 + 1;
        v44 += v47;
        v45 += v47;
      }
      while ( *v44 );
    }
    v48 = WaasMedic::RegSetMultiSzValue(v44, pszPathOut, L"RequiredPrivileges");
    v49 = v48;
    if ( v48 < 0 )
    {
      LogLevelW(2u, L"Failed to write %s.  ErrorCode = 0x%08x", L"RequiredPrivileges", (unsigned int)v48);
      v10 = v49;
    }
  }
  v50 = *((unsigned int *)a2 + 19);
  if ( (_DWORD)v50 )
  {
    v51 = WaasMedic::RegSetDwordValue(v34, pszPathOut, L"LaunchProtected", v50);
    v52 = v51;
    if ( v51 < 0 )
    {
      LogLevelW(2u, L"Failed to write %s.  ErrorCode = 0x%08x", L"LaunchProtected", (unsigned int)v51);
      v10 = v52;
    }
  }
  v53 = WaasMedic::TelemetryProvider::Provider();
  v54 = v53;
  if ( *(_DWORD *)v53 > 5u )
  {
    v55 = *((_QWORD *)v53 + 3);
    if ( (*((_QWORD *)v54 + 2) & 0x400000000000LL) != 0 && (v55 & 0x400000000000LL) == v55 )
    {
      v61 = v10;
      LODWORD(hKey) = v20;
      v56 = (const OLECHAR *)*((_QWORD *)a2 + 1);
      v62 = 0x1000000;
      v75 = &v61;
      v76 = 4;
      p_hKey = &hKey;
      v74 = 4;
      if ( v56 )
      {
        v57 = -1;
        do
          ++v57;
        while ( v56[v57] );
        v14 = 2 * v57 + 2;
      }
      else
      {
        v56 = &word_18006939C;
      }
      v70 = v56;
      v71 = v14;
      v72 = 0;
      do
        ++v13;
      while ( *(&gc_pszVersionString + v13) );
      v67 = &gc_pszVersionString;
      v68 = 2 * v13 + 2;
      v69 = 0;
      v65 = &v62;
      v66 = 8;
      tlgWriteTransfer_EventWriteTransfer(v54, &word_180089FFE, 0, 0, 7, v64);
    }
  }
  return v10;
}

```

## disassembly

```asm
0x18004c298  push    rbp
0x18004c29a  push    rbx
0x18004c29b  push    rsi
0x18004c29c  push    rdi
0x18004c29d  push    r12
0x18004c29f  push    r13
0x18004c2a1  push    r14
0x18004c2a3  push    r15
0x18004c2a5  lea     rbp, [rsp-218h]
0x18004c2ad  sub     rsp, 318h
0x18004c2b4  mov     rax, cs:__security_cookie
0x18004c2bb  xor     rax, rsp
0x18004c2be  mov     [rbp+250h+var_50], rax
0x18004c2c5  mov     rbx, rdx
0x18004c2c8  xor     r13d, r13d
0x18004c2cb  test    rdx, rdx
0x18004c2ce  jnz     short loc_18004C2F7
0x18004c2d0  mov     ebx, 80004003h
0x18004c2d5  mov     edx, 33Bh; void *
0x18004c2da  lea     r8, aOnecoreEnduser_40; "onecore\\enduser\\waasmedic\\lib\\plugi"...
0x18004c2e1  mov     r9d, ebx; char *
0x18004c2e4  mov     rcx, [rbp+258h]; this
0x18004c2eb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004c2f0  mov     eax, ebx
0x18004c2f2  jmp     loc_18004C7C2
0x18004c2f7  mov     r9, [rdx+8]; pszMore
0x18004c2fb  test    r9, r9
0x18004c2fe  jnz     short loc_18004C30C
0x18004c300  mov     ebx, 8007007Bh
0x18004c305  mov     edx, 33Dh
0x18004c30a  jmp     short loc_18004C2DA
0x18004c30c  lea     r8, pszPathIn; "SYSTEM\\CurrentControlSet\\Services"
0x18004c313  mov     edx, 104h; cchPathOut
0x18004c318  lea     rcx, [rbp+250h+pszPathOut]; pszPathOut
0x18004c31c  call    cs:__imp_PathCchCombine
0x18004c322  mov     edi, eax
0x18004c324  test    eax, eax
0x18004c326  jns     short loc_18004C34A
0x18004c328  mov     rcx, [rbp+258h]; this
0x18004c32f  mov     r9d, eax; char *
0x18004c332  lea     r8, aOnecoreEnduser_40; "onecore\\enduser\\waasmedic\\lib\\plugi"...
0x18004c339  mov     edx, 340h; void *
0x18004c33e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004c343  mov     eax, edi
0x18004c345  jmp     loc_18004C7C2
0x18004c34a  mov     esi, r13d
0x18004c34d  mov     byte ptr [rsp+350h+var_330], r13b; int
0x18004c352  mov     r9d, [rbx+48h]
0x18004c356  lea     r12, aType_1; "Type"
0x18004c35d  mov     r8, r12
0x18004c360  lea     rdx, [rbp+250h+pszPathOut]
0x18004c364  call    ?RegSetDwordValue@WaasMedic@@YAJPEAUHKEY__@@PEBG1K_NW4RegistryHiveType@1@@Z; WaasMedic::RegSetDwordValue(HKEY__ *,ushort const *,ushort const *,ulong,bool,WaasMedic::RegistryHiveType)
0x18004c369  or      r15, 0FFFFFFFFFFFFFFFFh
0x18004c36d  lea     edi, [r15+3]
0x18004c371  test    eax, eax
0x18004c373  jns     loc_18004C483
0x18004c379  cmp     eax, 80070005h
0x18004c37e  jnz     loc_18004C46F
0x18004c384  lea     rdx, aFailedToWriteR; "Failed to write registry with E_ACCESSD"...
0x18004c38b  lea     ecx, [rdi+2]; unsigned __int8
0x18004c38e  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18004c393  mov     [rsp+350h+hKey], 0FFFFFFFF80000002h
0x18004c39c  xorps   xmm0, xmm0
0x18004c39f  movups  [rsp+350h+var_2F8], xmm0
0x18004c3a4  xorps   xmm1, xmm1
0x18004c3a7  movdqu  [rsp+350h+var_2E8], xmm1
0x18004c3ad  lea     rax, [rbp+250h+pszPathOut]
0x18004c3b1  mov     r8, r15
0x18004c3b4  inc     r8
0x18004c3b7  cmp     [rax+r8*2], r13w
0x18004c3bc  jnz     short loc_18004C3B4
0x18004c3be  lea     rdx, [rbp+250h+pszPathOut]
0x18004c3c2  lea     rcx, [rsp+350h+var_2F8]
0x18004c3c7  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18004c3cc  xor     r8d, r8d
0x18004c3cf  lea     rdx, [rsp+350h+var_2F8]
0x18004c3d4  lea     rcx, [rsp+350h+hKey]
0x18004c3d9  call    ?TakeOwnershipAndRestoreSD@WaasMedic@@YAJAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@Z; WaasMedic::TakeOwnershipAndRestoreSD(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,std::wstring const &,void *)
0x18004c3de  mov     r14d, eax
0x18004c3e1  lea     rcx, [rsp+350h+var_2F8]; void *
0x18004c3e6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004c3eb  test    r14d, r14d
0x18004c3ee  jns     short loc_18004C424
0x18004c3f0  mov     rcx, [rbp+258h]; this
0x18004c3f7  mov     r9d, r14d; char *
0x18004c3fa  lea     r8, aOnecoreEnduser_40; "onecore\\enduser\\waasmedic\\lib\\plugi"...
0x18004c401  mov     edx, 34Ch; void *
0x18004c406  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004c40b  nop
0x18004c40c  mov     rcx, [rsp+350h+hKey]; hKey
0x18004c411  test    rcx, rcx
0x18004c414  jz      short loc_18004C41C
0x18004c416  call    cs:__imp_RegCloseKey
0x18004c41c  mov     eax, r14d
0x18004c41f  jmp     loc_18004C7C2
0x18004c424  mov     byte ptr [rsp+350h+var_330], r13b
0x18004c429  mov     r9d, [rbx+48h]
0x18004c42d  mov     r8, r12
0x18004c430  lea     rdx, [rbp+250h+pszPathOut]
0x18004c434  call    ?RegSetDwordValue@WaasMedic@@YAJPEAUHKEY__@@PEBG1K_NW4RegistryHiveType@1@@Z; WaasMedic::RegSetDwordValue(HKEY__ *,ushort const *,ushort const *,ulong,bool,WaasMedic::RegistryHiveType)
0x18004c439  mov     r14d, eax
0x18004c43c  test    eax, eax
0x18004c43e  jns     short loc_18004C457
0x18004c440  mov     r9d, eax
0x18004c443  mov     r8, r12
0x18004c446  lea     rdx, aFailedToWriteS; "Failed to write %s.  ErrorCode = 0x%08x"
0x18004c44d  mov     ecx, edi; unsigned __int8
0x18004c44f  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18004c454  mov     esi, r14d
0x18004c457  mov     rcx, [rsp+350h+hKey]; hKey
0x18004c45c  test    rcx, rcx
0x18004c45f  jz      short loc_18004C467
0x18004c461  call    cs:__imp_RegCloseKey
0x18004c467  mov     r12d, 1
0x18004c46d  jmp     short loc_18004C486
0x18004c46f  mov     r9d, eax
0x18004c472  mov     r8, r12
0x18004c475  lea     rdx, aFailedToWriteS; "Failed to write %s.  ErrorCode = 0x%08x"
0x18004c47c  mov     ecx, edi; unsigned __int8
0x18004c47e  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18004c483  mov     r12d, r13d
0x18004c486  mov     byte ptr [rsp+350h+var_330], r13b
0x18004c48b  mov     r9d, [rbx+38h]
0x18004c48f  lea     r8, aStart_0; "Start"
0x18004c496  lea     rdx, [rbp+250h+pszPathOut]
0x18004c49a  call    ?RegSetDwordValue@WaasMedic@@YAJPEAUHKEY__@@PEBG1K_NW4RegistryHiveType@1@@Z; WaasMedic::RegSetDwordValue(HKEY__ *,ushort const *,ushort const *,ulong,bool,WaasMedic::RegistryHiveType)
0x18004c49f  mov     r14d, eax
0x18004c4a2  test    eax, eax
0x18004c4a4  jns     short loc_18004C4C1
0x18004c4a6  mov     r9d, eax
0x18004c4a9  lea     r8, aStart_0; "Start"
0x18004c4b0  lea     rdx, aFailedToWriteS; "Failed to write %s.  ErrorCode = 0x%08x"
0x18004c4b7  mov     ecx, edi; unsigned __int8
0x18004c4b9  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18004c4be  mov     esi, r14d
0x18004c4c1  mov     byte ptr [rsp+350h+var_330], r13b
0x18004c4c6  mov     r9d, [rbx+34h]
0x18004c4ca  lea     r8, aErrorcontrol_0; "ErrorControl"
0x18004c4d1  lea     rdx, [rbp+250h+pszPathOut]
0x18004c4d5  call    ?RegSetDwordValue@WaasMedic@@YAJPEAUHKEY__@@PEBG1K_NW4RegistryHiveType@1@@Z; WaasMedic::RegSetDwordValue(HKEY__ *,ushort const *,ushort const *,ulong,bool,WaasMedic::RegistryHiveType)
0x18004c4da  mov     r14d, eax
0x18004c4dd  test    eax, eax
0x18004c4df  jns     short loc_18004C4FC
0x18004c4e1  mov     r9d, eax
0x18004c4e4  lea     r8, aErrorcontrol_0; "ErrorControl"
0x18004c4eb  lea     rdx, aFailedToWriteS; "Failed to write %s.  ErrorCode = 0x%08x"
0x18004c4f2  mov     ecx, edi; unsigned __int8
0x18004c4f4  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18004c4f9  mov     esi, r14d
0x18004c4fc  mov     byte ptr [rsp+350h+var_330], r13b
0x18004c501  mov     r9d, [rbx+30h]
0x18004c505  lea     r8, aServicesidtype; "ServiceSidType"
0x18004c50c  lea     rdx, [rbp+250h+pszPathOut]
0x18004c510  call    ?RegSetDwordValue@WaasMedic@@YAJPEAUHKEY__@@PEBG1K_NW4RegistryHiveType@1@@Z; WaasMedic::RegSetDwordValue(HKEY__ *,ushort const *,ushort const *,ulong,bool,WaasMedic::RegistryHiveType)
0x18004c515  mov     r14d, eax
0x18004c518  test    eax, eax
0x18004c51a  jns     short loc_18004C537
0x18004c51c  mov     r9d, eax
0x18004c51f  lea     r8, aServicesidtype; "ServiceSidType"
0x18004c526  lea     rdx, aFailedToWriteS; "Failed to write %s.  ErrorCode = 0x%08x"
0x18004c52d  mov     ecx, edi; unsigned __int8
0x18004c52f  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18004c534  mov     esi, r14d
0x18004c537  mov     byte ptr [rsp+350h+var_330], r13b
0x18004c53c  mov     r9, [rbx+20h]
0x18004c540  lea     r8, aImagepath_0; "ImagePath"
0x18004c547  lea     rdx, [rbp+250h+pszPathOut]
0x18004c54b  call    ?RegSetStringValue@WaasMedic@@YAJPEAUHKEY__@@PEBG11_NW4RegistryHiveType@1@@Z; WaasMedic::RegSetStringValue(HKEY__ *,ushort const *,ushort const *,ushort const *,bool,WaasMedic::RegistryHiveType)
0x18004c550  mov     r14d, eax
0x18004c553  test    eax, eax
0x18004c555  jns     short loc_18004C572
0x18004c557  mov     r9d, eax
0x18004c55a  lea     r8, aImagepath_0; "ImagePath"
0x18004c561  lea     rdx, aFailedToWriteS; "Failed to write %s.  ErrorCode = 0x%08x"
0x18004c568  mov     ecx, edi; unsigned __int8
0x18004c56a  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18004c56f  mov     esi, r14d
0x18004c572  mov     byte ptr [rsp+350h+var_330], r13b
0x18004c577  mov     r9, [rbx+28h]
0x18004c57b  lea     r8, aObjectname_0; "ObjectName"
0x18004c582  lea     rdx, [rbp+250h+pszPathOut]
0x18004c586  call    ?RegSetStringValue@WaasMedic@@YAJPEAUHKEY__@@PEBG11_NW4RegistryHiveType@1@@Z; WaasMedic::RegSetStringValue(HKEY__ *,ushort const *,ushort const *,ushort const *,bool,WaasMedic::RegistryHiveType)
0x18004c58b  mov     r14d, eax
0x18004c58e  test    eax, eax
0x18004c590  jns     short loc_18004C5AD
0x18004c592  mov     r9d, eax
0x18004c595  lea     r8, aObjectname_0; "ObjectName"
0x18004c59c  lea     rdx, aFailedToWriteS; "Failed to write %s.  ErrorCode = 0x%08x"
0x18004c5a3  mov     ecx, edi; unsigned __int8
0x18004c5a5  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18004c5aa  mov     esi, r14d
0x18004c5ad  mov     r9, [rbx+10h]
0x18004c5b1  test    r9, r9
0x18004c5b4  jz      short loc_18004C618
0x18004c5b6  mov     rcx, r9
0x18004c5b9  mov     rdx, r13
0x18004c5bc  cmp     [r9], r13w
0x18004c5c0  jz      short loc_18004C5DF
0x18004c5c2  mov     rax, r15
0x18004c5c5  inc     rax
0x18004c5c8  cmp     [rcx+rax*2], r13w
0x18004c5cd  jnz     short loc_18004C5C5
0x18004c5cf  inc     rax
0x18004c5d2  lea     rcx, [rcx+rax*2]
0x18004c5d6  add     rdx, rax
0x18004c5d9  cmp     [rcx], r13w
0x18004c5dd  jnz     short loc_18004C5C2
0x18004c5df  lea     eax, [rdx+1]
0x18004c5e2  mov     [rsp+350h+var_330], eax
0x18004c5e6  lea     r8, aDependonservic_0; "DependOnService"
0x18004c5ed  lea     rdx, [rbp+250h+pszPathOut]
0x18004c5f1  call    ?RegSetMultiSzValue@WaasMedic@@YAJPEAUHKEY__@@PEBG11H_NW4RegistryHiveType@1@@Z; WaasMedic::RegSetMultiSzValue(HKEY__ *,ushort const *,ushort const *,ushort const *,int,bool,WaasMedic::RegistryHiveType)
0x18004c5f6  mov     r14d, eax
0x18004c5f9  test    eax, eax
0x18004c5fb  jns     short loc_18004C618
0x18004c5fd  mov     r9d, eax
0x18004c600  lea     r8, aDependonservic_0; "DependOnService"
0x18004c607  lea     rdx, aFailedToWriteS; "Failed to write %s.  ErrorCode = 0x%08x"
0x18004c60e  mov     ecx, edi; unsigned __int8
0x18004c610  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18004c615  mov     esi, r14d
0x18004c618  mov     r9, [rbx+18h]
0x18004c61c  test    r9, r9
0x18004c61f  jz      short loc_18004C683
0x18004c621  mov     rcx, r9
0x18004c624  mov     rdx, r13
0x18004c627  cmp     [r9], r13w
0x18004c62b  jz      short loc_18004C64A
0x18004c62d  mov     rax, r15
0x18004c630  inc     rax
0x18004c633  cmp     [rcx+rax*2], r13w
0x18004c638  jnz     short loc_18004C630
0x18004c63a  inc     rax
0x18004c63d  lea     rcx, [rcx+rax*2]
0x18004c641  add     rdx, rax
0x18004c644  cmp     [rcx], r13w
0x18004c648  jnz     short loc_18004C62D
0x18004c64a  lea     eax, [rdx+1]
0x18004c64d  mov     [rsp+350h+var_330], eax
0x18004c651  lea     r8, aRequiredprivil_0; "RequiredPrivileges"
0x18004c658  lea     rdx, [rbp+250h+pszPathOut]
0x18004c65c  call    ?RegSetMultiSzValue@WaasMedic@@YAJPEAUHKEY__@@PEBG11H_NW4RegistryHiveType@1@@Z; WaasMedic::RegSetMultiSzValue(HKEY__ *,ushort const *,ushort const *,ushort const *,int,bool,WaasMedic::RegistryHiveType)
0x18004c661  mov     r14d, eax
0x18004c664  test    eax, eax
0x18004c666  jns     short loc_18004C683
0x18004c668  mov     r9d, eax
0x18004c66b  lea     r8, aRequiredprivil_0; "RequiredPrivileges"
0x18004c672  lea     rdx, aFailedToWriteS; "Failed to write %s.  ErrorCode = 0x%08x"
0x18004c679  mov     ecx, edi; unsigned __int8
0x18004c67b  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18004c680  mov     esi, r14d
0x18004c683  mov     r9d, [rbx+4Ch]
0x18004c687  test    r9d, r9d
0x18004c68a  jz      short loc_18004C6C3
0x18004c68c  mov     byte ptr [rsp+350h+var_330], r13b
0x18004c691  lea     r8, aLaunchprotecte_1; "LaunchProtected"
0x18004c698  lea     rdx, [rbp+250h+pszPathOut]
0x18004c69c  call    ?RegSetDwordValue@WaasMedic@@YAJPEAUHKEY__@@PEBG1K_NW4RegistryHiveType@1@@Z; WaasMedic::RegSetDwordValue(HKEY__ *,ushort const *,ushort const *,ulong,bool,WaasMedic::RegistryHiveType)
0x18004c6a1  mov     r14d, eax
0x18004c6a4  test    eax, eax
0x18004c6a6  jns     short loc_18004C6C3
0x18004c6a8  mov     r9d, eax
0x18004c6ab  lea     r8, aLaunchprotecte_1; "LaunchProtected"
0x18004c6b2  lea     rdx, aFailedToWriteS; "Failed to write %s.  ErrorCode = 0x%08x"
0x18004c6b9  mov     ecx, edi; unsigned __int8
0x18004c6bb  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18004c6c0  mov     esi, r14d
0x18004c6c3  call    ?Provider@TelemetryProvider@WaasMedic@@SAPEBU_tlgProvider_t@@XZ; WaasMedic::TelemetryProvider::Provider(void)
0x18004c6c8  mov     r10, rax
0x18004c6cb  mov     ecx, [rax]
0x18004c6cd  cmp     ecx, 5
0x18004c6d0  jbe     loc_18004C7C0
0x18004c6d6  mov     rax, [rax+18h]
0x18004c6da  mov     rcx, [r10+10h]
0x18004c6de  mov     rdx, 400000000000h
0x18004c6e8  test    rdx, rcx
0x18004c6eb  jz      loc_18004C7C0
0x18004c6f1  mov     rcx, rax
0x18004c6f4  and     rcx, rdx
0x18004c6f7  cmp     rcx, rax
0x18004c6fa  jnz     loc_18004C7C0
0x18004c700  mov     [rsp+350h+var_308], esi
0x18004c704  mov     dword ptr [rsp+350h+hKey], r12d
0x18004c709  mov     rax, [rbx+8]
0x18004c70d  mov     [rsp+350h+var_300], 1000000h
0x18004c716  lea     rcx, [rsp+350h+var_308]
0x18004c71b  mov     [rbp+250h+var_270], rcx
0x18004c71f  mov     [rbp+250h+var_268], 4
0x18004c727  lea     rcx, [rsp+350h+hKey]
0x18004c72c  mov     [rbp+250h+var_280], rcx
0x18004c730  mov     [rbp+250h+var_278], 4
0x18004c738  test    rax, rax
0x18004c73b  jz      short loc_18004C753
0x18004c73d  mov     rdi, r15
0x18004c740  inc     rdi
0x18004c743  cmp     [rax+rdi*2], r13w
0x18004c748  jnz     short loc_18004C740
0x18004c74a  lea     edi, ds:2[rdi*2]
0x18004c751  jmp     short loc_18004C75A
0x18004c753  lea     rax, word_18006939C
  ... truncated ...
```
