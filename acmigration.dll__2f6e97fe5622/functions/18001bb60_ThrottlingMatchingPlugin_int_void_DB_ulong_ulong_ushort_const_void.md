# ThrottlingMatchingPlugin(int *,void *,_DB *,ulong,ulong,ushort const *,void *)

- ea: `0x18001bb60`
- end: `0x18001c681`
- name: `?ThrottlingMatchingPlugin@@YAHPEAHPEAXPEAU_DB@@KKPEBG1@Z`
- size: `2849`
- prototype: `__int64 __fastcall(int *, void *, struct _DB *, unsigned int, unsigned int, LPCWSTR lpCmdLine, void *)`
- caller_count: `0`
- callee_count: `17`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180001cf0`
- `0x180002120`
- `0x180002874`
- `0x18000b5fc`
- `0x18000b720`
- `0x18000c3c8`
- `0x18000c534`
- `0x18001bb60`
- `0x18001c688`
- `0x180041644`
- `0x180044964`
- `0x1800543c0`
- `0x180054594`
- `0x1800545f8`
- `0x18005da34`
- `0x18005de60`
- `0x180065120`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001be1f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001be38`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001be70`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001be9a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001bec1`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001bee5`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001bf0c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001be1f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001be38`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001be70`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001be9a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001bec1`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001bee5`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001bf0c`
- `api-ms-win-crt-private-l1-1-0!_o_wcstod` at `0x18001c0d2`
- `api-ms-win-crt-private-l1-1-0!_o_wcstod` at `0x18001c0d2`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001c0bf`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001c111`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001c11b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001c0bf`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001c111`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001c11b`
- `KERNEL32!LocalFree` at `0x18001c5f5`
- `KERNEL32!LocalFree` at `0x18001c5f5`
- `KERNEL32!GetLastError` at `0x18001c59a`
- `KERNEL32!GetLastError` at `0x18001c59a`
- `ADVAPI32!RegGetValueW` at `0x18001c3a3`
- `ADVAPI32!RegGetValueW` at `0x18001c3a3`
- `SHELL32!CommandLineToArgvW` at `0x18001bd68`
- `SHELL32!CommandLineToArgvW` at `0x18001bd68`

## string_xrefs

- `0x18001c5ae`: `CommandLineToArgvW failed %d, %ws, numArgs=%d`
- `0x18001bd47`: `Commandline: %ws`
- `0x18001bd18`: `compat`
- `0x18001bc75`: `Enter ThrottlingMatchingPlugin.`
- `0x18001bc80`: `ThrottlingMatchingPlugin`
- `0x18001c5d2`: `ThrottlingMatchingPlugin`
- `0x18001c61e`: `CommandLine is null/empty.`
- `0x18001c1c1`: `Failed to compare dates. [0x%x]`
- `0x18001c3b4`: `Failed to query the DeviceId from registry. [0x%x]`
- `0x18001c604`: `ThrottlingMatchingPlugin Matched = %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
__int64 __fastcall ThrottlingMatchingPlugin(
        int *a1,
        void *a2,
        struct _DB *a3,
        unsigned int a4,
        unsigned int a5,
        LPCWSTR lpCmdLine,
        void *a7)
{
  _QWORD *v8; // rax
  const wchar_t **v9; // rax
  const wchar_t **v10; // r14
  unsigned int v11; // r13d
  int *v12; // r12
  int v13; // r12d
  int v14; // eax
  const wchar_t *v15; // rcx
  int v16; // edx
  const wchar_t *v17; // r13
  __int64 v18; // r12
  __int64 v19; // r8
  __int64 v20; // r8
  int OneSettingsValue; // eax
  __int64 v22; // rcx
  double v23; // xmm7_8
  __int64 v24; // rcx
  _DWORD *v25; // rax
  unsigned __int16 *v26; // r12
  int v27; // eax
  const wchar_t *v28; // r12
  struct _DB *v29; // r13
  unsigned int FirstTag; // eax
  int v31; // eax
  int v32; // eax
  LSTATUS ValueW; // eax
  int v34; // eax
  unsigned __int64 v35; // rdx
  double v36; // xmm6_8
  double v37; // xmm6_8
  LPDWORD pdwType; // [rsp+20h] [rbp-2B8h]
  int pcbData; // [rsp+30h] [rbp-2A8h]
  int v42; // [rsp+48h] [rbp-290h]
  int pNumArgs; // [rsp+4Ch] [rbp-28Ch] BYREF
  const wchar_t *v44; // [rsp+50h] [rbp-288h]
  const wchar_t *v45; // [rsp+58h] [rbp-280h]
  int v46; // [rsp+60h] [rbp-278h] BYREF
  unsigned int v47; // [rsp+64h] [rbp-274h]
  DWORD v48; // [rsp+68h] [rbp-270h] BYREF
  const wchar_t *v49; // [rsp+70h] [rbp-268h]
  _QWORD v50[2]; // [rsp+78h] [rbp-260h] BYREF
  const wchar_t *v51; // [rsp+88h] [rbp-250h]
  _WORD *v52; // [rsp+90h] [rbp-248h] BYREF
  unsigned __int16 *v53; // [rsp+98h] [rbp-240h]
  const wchar_t *v54; // [rsp+A0h] [rbp-238h]
  struct _DB *v55; // [rsp+A8h] [rbp-230h]
  int *v56; // [rsp+B0h] [rbp-228h]
  const wchar_t **v57; // [rsp+B8h] [rbp-220h] BYREF
  __int128 v58; // [rsp+C8h] [rbp-210h] BYREF
  __int64 v59; // [rsp+D8h] [rbp-200h]
  __int64 v60; // [rsp+E0h] [rbp-1F8h]
  __int128 v61; // [rsp+E8h] [rbp-1F0h] BYREF
  __int64 v62; // [rsp+F8h] [rbp-1E0h]
  __int64 v63; // [rsp+100h] [rbp-1D8h]
  __int64 v64; // [rsp+108h] [rbp-1D0h]
  GUID Guid; // [rsp+110h] [rbp-1C8h] BYREF
  GUID v66; // [rsp+120h] [rbp-1B8h] BYREF
  __int128 v67; // [rsp+130h] [rbp-1A8h] BYREF
  __int64 v68; // [rsp+140h] [rbp-198h]
  __int64 v69; // [rsp+148h] [rbp-190h]
  __int128 v70; // [rsp+150h] [rbp-188h] BYREF
  __int64 v71; // [rsp+160h] [rbp-178h]
  unsigned __int64 v72; // [rsp+168h] [rbp-170h]
  _BYTE pvData[128]; // [rsp+170h] [rbp-168h] BYREF
  _BYTE v74[128]; // [rsp+1F0h] [rbp-E8h] BYREF

  v64 = -2;
  v47 = a4;
  v55 = a3;
  v56 = a1;
  pNumArgs = 0;
  v46 = 0;
  v52 = 0;
  Guid = 0;
  v66 = 0;
  memset_0(v74, 0, sizeof(v74));
  memset_0(pvData, 0, sizeof(pvData));
  v48 = 128;
  v50[1] = 0;
  v8 = operator new(0x40u);
  *v8 = v8;
  v8[1] = v8;
  v8[2] = v8;
  *((_WORD *)v8 + 12) = 257;
  v50[0] = v8;
  v70 = 0;
  v71 = 0;
  v72 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v70, &psz, 0);
  AslLogCallPrintf(3, "ThrottlingMatchingPlugin", 193, "Enter ThrottlingMatchingPlugin.");
  *a1 = 0;
  v67 = 0;
  v68 = 0;
  v69 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v67, L"PercentageFromOneSettings", 25);
  std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::insert<0,0>(
    v50,
    &v57,
    &v67);
  std::wstring::~wstring(&v67);
  if ( !lpCmdLine || (v44 = 0, v53 = 0, v54 = 0, v45 = 0, v51 = L"compat", v49 = L"appraiser", v42 = 0, !*lpCmdLine) )
  {
    AslLogCallPrintf(1, "ThrottlingMatchingPlugin", 200, "CommandLine is null/empty.");
    goto LABEL_85;
  }
  AslLogCallPrintf(3, "ThrottlingMatchingPlugin", 204, "Commandline: %ws", lpCmdLine);
  v9 = (const wchar_t **)CommandLineToArgvW(lpCmdLine, &pNumArgs);
  v10 = v9;
  v57 = v9;
  v11 = pNumArgs;
  if ( !v9 || pNumArgs < 2 )
  {
    pcbData = pNumArgs;
    LODWORD(pdwType) = GetLastError();
    AslLogCallPrintf(
      1,
      "ThrottlingMatchingPlugin",
      215,
      "CommandLineToArgvW failed %d, %ws, numArgs=%d",
      pdwType,
      lpCmdLine,
      pcbData);
    v12 = a1;
    if ( v10 )
      goto LABEL_82;
    goto LABEL_83;
  }
  if ( !wcscmp_0(L"Features", *v9) )
  {
    v12 = a1;
    if ( (unsigned __int8)AppCompatUtility::SupportAllFeatures(v50, v11, v10) )
      *a1 = 1;
    goto LABEL_82;
  }
  if ( (v11 & 0x80000001) != 0 )
  {
    AslLogCallPrintf(1, "ThrottlingMatchingPlugin", 233, "Wrong arguments number: %d", v11);
    v12 = a1;
    goto LABEL_82;
  }
  v13 = 0;
  if ( (int)(v11 - 1) <= 0 )
  {
LABEL_80:
    AslLogCallPrintf(1, "ThrottlingMatchingPlugin", 306, "-Percentage parameter is mandatory.");
    v12 = a1;
    goto LABEL_82;
  }
  do
  {
    if ( (unsigned int)_o__wcsicmp(L"-Percentage", v10[v13]) )
    {
      if ( (unsigned int)_o__wcsicmp(L"-StartDate", v10[v13]) )
      {
        if ( (unsigned int)_o__wcsicmp(L"-SdbId", v10[v13]) )
        {
          if ( !(unsigned int)_o__wcsicmp(L"-OneSettingsValueName", v10[v13]) )
          {
            v15 = v10[v13 + 1];
            v45 = v15;
LABEL_26:
            v16 = v42;
            goto LABEL_27;
          }
          if ( (unsigned int)_o__wcsicmp(L"-OneSettingsPartner", v10[v13]) )
          {
            if ( (unsigned int)_o__wcsicmp(L"-OneSettingsFeature", v10[v13]) )
            {
              AslLogCallPrintf(1, "ThrottlingMatchingPlugin", 272, "Unknown switch: %ws", v10[v13]);
              v12 = a1;
              goto LABEL_82;
            }
            v49 = v10[v13 + 1];
          }
          else
          {
            v51 = v10[v13 + 1];
          }
        }
        else
        {
          v54 = v10[v13 + 1];
        }
      }
      else
      {
        v53 = (unsigned __int16 *)v10[v13 + 1];
      }
      v15 = v45;
      goto LABEL_26;
    }
    v14 = _o__wcsicmp(L"FromOneSettings", v10[v13 + 1]);
    v15 = v45;
    if ( v14 )
    {
      v17 = v10[v13 + 1];
      v44 = v17;
      v16 = v42;
      goto LABEL_28;
    }
    v16 = 1;
    v42 = 1;
LABEL_27:
    v17 = v44;
LABEL_28:
    v13 += 2;
  }
  while ( v13 < pNumArgs - 1 );
  if ( v16 )
  {
    if ( !v15 )
    {
      AslLogCallPrintf(
        1,
        "ThrottlingMatchingPlugin",
        285,
        "-OneSettingsValueName parameter is mandatory when using -Percentage FromOneSettings.");
      v12 = a1;
      goto LABEL_82;
    }
    v45 = (const wchar_t *)&v67;
    v67 = 0;
    v68 = 0;
    v69 = 0;
    v18 = -1;
    v19 = -1;
    do
      ++v19;
    while ( v15[v19] );
    std::wstring::_Construct<1,unsigned short const *>(&v67, v15, v19);
    v44 = (const wchar_t *)&v58;
    v58 = 0;
    v59 = 0;
    v60 = 0;
    v20 = -1;
    do
      ++v20;
    while ( v49[v20] );
    std::wstring::_Construct<1,unsigned short const *>(&v58, v49, v20);
    v61 = 0;
    v62 = 0;
    v63 = 0;
    do
      ++v18;
    while ( v51[v18] );
    std::wstring::_Construct<1,unsigned short const *>(&v61, v51, v18);
    OneSettingsValue = AppCompatUtility::GetOneSettingsValue(&v70, &v61, &v58, &v67);
    if ( OneSettingsValue )
    {
      AslLogCallPrintf(1, "ThrottlingMatchingPlugin", 297, "Failed to get OneSettings value. [0x%x]", OneSettingsValue);
      v12 = a1;
      goto LABEL_82;
    }
    v17 = (const wchar_t *)&v70;
    if ( v72 > 7 )
      v17 = (const wchar_t *)v70;
  }
  if ( !v17 )
    goto LABEL_80;
  *(_DWORD *)_o__errno(v15) = 0;
  v23 = _o_wcstod(v17, &v52);
  if ( *v52 )
  {
    LODWORD(pdwType) = (unsigned __int16)*v52;
    AslLogCallPrintf(
      1,
      "ThrottlingMatchingPlugin",
      317,
      "Failed to convert Percentage from string to double. Failed to parse at '%wc'.",
      pdwType);
    v12 = a1;
    goto LABEL_82;
  }
  if ( *(_DWORD *)_o__errno(v22) )
  {
    v25 = (_DWORD *)_o__errno(v24);
    AslLogCallPrintf(
      1,
      "ThrottlingMatchingPlugin",
      322,
      "Failed to convert Percentage from string to double. [0x%x]",
      *v25);
    v12 = a1;
    goto LABEL_82;
  }
  if ( v23 < 0.0 || v23 > 100.0 )
  {
    AslLogCallPrintf(1, "ThrottlingMatchingPlugin", 327, "Percentage must be in the 0.0 to 100.0 range.");
    v12 = a1;
  }
  else
  {
    AslLogCallPrintf(3, "ThrottlingMatchingPlugin", 331, "Percentage: %lf", v23);
    v26 = v53;
    if ( v53 )
    {
      AslLogCallPrintf(3, "ThrottlingMatchingPlugin", 335, "StartDate: %ws", v53);
      v27 = TodayIsBeforeDate(&v46, v26);
      if ( v27 )
      {
        AslLogCallPrintf(1, "ThrottlingMatchingPlugin", 340, "Failed to compare dates. [0x%x]", v27);
        v12 = a1;
        goto LABEL_82;
      }
      if ( v46 )
      {
        AslLogCallPrintf(
          3,
          "ThrottlingMatchingPlugin",
          346,
          "StartDate is earlier than current date. Matching as FALSE.");
        v12 = a1;
        goto LABEL_82;
      }
    }
    v28 = v54;
    if ( v54 )
    {
      v32 = AslGuidFromString(&Guid);
      if ( v32 < 0 )
      {
        AslLogCallPrintf(
          3,
          "ThrottlingMatchingPlugin",
          403,
          "Failed to convert string to GUID. [0x%x]",
          v32 | 0x10000000);
        v12 = a1;
        goto LABEL_82;
      }
    }
    else
    {
      if ( !v47 || (v29 = v55) == 0 )
      {
        AslLogCallPrintf(3, "ThrottlingMatchingPlugin", 385, "ParentTagId or Pdb is NULL. Can't get GUID from entry.");
        goto LABEL_66;
      }
      FirstTag = SdbFindFirstTag(v55, v47, 36868);
      if ( !FirstTag )
      {
LABEL_66:
        AslLogCallPrintf(1, "ThrottlingMatchingPlugin", 390, "Failed to get a SdbId. Can't do Throttling calculation.");
        v12 = a1;
        goto LABEL_82;
      }
      if ( !(unsigned int)SdbReadBinaryTag(v29, FirstTag, &Guid, 16) )
      {
        AslLogCallPrintf(3, "ThrottlingMatchingPlugin", 363, "Couldn't get GUID from Sdb Entry.");
        goto LABEL_66;
      }
      v31 = AslGuidToString(v74, 64, &Guid);
      if ( v31 < 0 )
        AslLogCallPrintf(
          3,
          "ThrottlingMatchingPlugin",
          378,
          "Failed to convert GUID to string. [0x%x]",
          v31 | 0x10000000);
      else
        v28 = (const wchar_t *)v74;
      if ( !v28 )
        goto LABEL_66;
    }
    AslLogCallPrintf(3, "ThrottlingMatchingPlugin", 408, "SdbId: %ws", v28);
    ValueW = RegGetValueW(
               HKEY_LOCAL_MACHINE,
               L"SOFTWARE\\Microsoft\\SQMClient",
               L"MachineId",
               0x20000002u,
               0,
               pvData,
               &v48);
    if ( ValueW )
    {
      AslLogCallPrintf(1, "ThrottlingMatchingPlugin", 426, "Failed to query the DeviceId from registry. [0x%x]", ValueW);
      v12 = a1;
    }
    else
    {
      AslLogCallPrintf(3, "ThrottlingMatchingPlugin", 429, "DeviceId: %ws", pvData);
      v34 = AslGuidFromString(&v66);
      if ( v34 >= 0 )
      {
        v35 = (v66.Data4[7] ^ (unsigned __int64)Guid.Data4[7])
            + (((v66.Data4[6] ^ (unsigned __int64)Guid.Data4[6])
              + (((v66.Data4[5] ^ (unsigned __int64)Guid.Data4[5])
                + (((v66.Data4[4] ^ (unsigned __int64)Guid.Data4[4])
                  + (((v66.Data4[3] ^ (unsigned __int64)Guid.Data4[3])
                    + ((v66.Data4[2] ^ (unsigned __int64)Guid.Data4[2]) << 8)) << 8)) << 8)) << 8)) << 8);
        if ( (v35 & 0x8000000000000000uLL) != 0LL )
          v36 = (double)(int)(v35 & 1 | (v35 >> 1)) + (double)(int)(v35 & 1 | (v35 >> 1));
        else
          v36 = (double)(int)v35;
        v37 = v36 * 100.0 / 2.81474976710655e14;
        AslLogCallPrintf(3, "ThrottlingMatchingPlugin", 457, "DeviceValue: %lf", v37);
        v12 = a1;
        if ( v23 >= v37 )
          *a1 = 1;
      }
      else
      {
        AslLogCallPrintf(
          3,
          "ThrottlingMatchingPlugin",
          435,
          "Failed to convert string to GUID. [0x%x]",
          v34 | 0x10000000);
        v12 = a1;
      }
    }
  }
LABEL_82:
  LocalFree(v10);
LABEL_83:
  AslLogCallPrintf(3, "ThrottlingMatchingPlugin", 481, "ThrottlingMatchingPlugin Matched = %d", *v12);
LABEL_85:
  std::wstring::~wstring(&v70);
  std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(v50);
  return 1;
}

```

## disassembly

```asm
0x18001bb60  mov     rax, rsp
0x18001bb63  push    rbx
0x18001bb64  push    rsi
0x18001bb65  push    rdi
0x18001bb66  push    r12
0x18001bb68  push    r13
0x18001bb6a  push    r14
0x18001bb6c  push    r15
0x18001bb6e  sub     rsp, 2A0h
0x18001bb75  mov     qword ptr [rax-1D0h], 0FFFFFFFFFFFFFFFEh
0x18001bb80  movaps  xmmword ptr [rax-48h], xmm6
0x18001bb84  movaps  xmmword ptr [rax-58h], xmm7
0x18001bb88  mov     rax, cs:__security_cookie
0x18001bb8f  xor     rax, rsp
0x18001bb92  mov     [rsp+2D8h+var_68], rax
0x18001bb9a  mov     [rsp+2D8h+var_274], r9d
0x18001bb9f  mov     [rsp+2D8h+var_230], r8
0x18001bba7  mov     r14, rcx
0x18001bbaa  mov     [rsp+2D8h+var_298], rcx
0x18001bbaf  mov     [rsp+2D8h+var_228], rcx
0x18001bbb7  mov     r12, [rsp+2D8h+lpCmdLine]
0x18001bbbf  xor     ebx, ebx
0x18001bbc1  mov     [rsp+2D8h+pNumArgs], ebx
0x18001bbc5  mov     [rsp+2D8h+var_278], ebx
0x18001bbc9  mov     [rsp+2D8h+var_248], rbx
0x18001bbd1  xorps   xmm0, xmm0
0x18001bbd4  movups  xmmword ptr [rsp+2D8h+Guid.Data1], xmm0
0x18001bbdc  xorps   xmm1, xmm1
0x18001bbdf  movups  xmmword ptr [rsp+2D8h+var_1B8.Data1], xmm1
0x18001bbe7  mov     edi, 80h
0x18001bbec  mov     r8d, edi; Size
0x18001bbef  xor     edx, edx; Val
0x18001bbf1  lea     rcx, [rsp+2D8h+var_E8]; void *
0x18001bbf9  call    memset_0
0x18001bbfe  mov     r8d, edi; Size
0x18001bc01  xor     edx, edx; Val
0x18001bc03  lea     rcx, [rsp+2D8h+var_168]; void *
0x18001bc0b  call    memset_0
0x18001bc10  mov     [rsp+2D8h+var_270], edi
0x18001bc14  mov     [rsp+2D8h+var_260], rbx
0x18001bc19  mov     [rsp+2D8h+var_258], rbx
0x18001bc21  lea     ecx, [rbx+40h]; Size
0x18001bc24  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001bc29  mov     [rax], rax
0x18001bc2c  mov     [rax+8], rax
0x18001bc30  mov     [rax+10h], rax
0x18001bc34  lea     esi, [rbx+1]
0x18001bc37  mov     word ptr [rax+18h], 101h
0x18001bc3d  mov     [rsp+2D8h+var_260], rax
0x18001bc42  xorps   xmm0, xmm0
0x18001bc45  movups  [rsp+2D8h+var_188], xmm0
0x18001bc4d  mov     [rsp+2D8h+var_178], rbx
0x18001bc55  mov     [rsp+2D8h+var_170], rbx
0x18001bc5d  xor     r8d, r8d
0x18001bc60  lea     rdx, psz
0x18001bc67  lea     rcx, [rsp+2D8h+var_188]
0x18001bc6f  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001bc74  nop
0x18001bc75  lea     r9, aEnterThrottlin; "Enter ThrottlingMatchingPlugin."
0x18001bc7c  lea     r8d, [rdi+41h]
0x18001bc80  lea     rdi, aThrottlingmatc_1; "ThrottlingMatchingPlugin"
0x18001bc87  mov     rdx, rdi
0x18001bc8a  lea     r15d, [rbx+3]
0x18001bc8e  mov     ecx, r15d
0x18001bc91  call    AslLogCallPrintf
0x18001bc96  mov     [r14], ebx
0x18001bc99  xorps   xmm0, xmm0
0x18001bc9c  movups  [rsp+2D8h+var_1A8], xmm0
0x18001bca4  mov     [rsp+2D8h+var_198], rbx
0x18001bcac  mov     [rsp+2D8h+var_190], rbx
0x18001bcb4  lea     r8d, [rbx+19h]
0x18001bcb8  lea     rdx, aPercentagefrom; "PercentageFromOneSettings"
0x18001bcbf  lea     rcx, [rsp+2D8h+var_1A8]
0x18001bcc7  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001bccc  nop
0x18001bccd  lea     r8, [rsp+2D8h+var_1A8]
0x18001bcd5  lea     rdx, [rsp+2D8h+var_220]
0x18001bcdd  lea     rcx, [rsp+2D8h+var_260]
0x18001bce2  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::insert<0,0>(std::wstring &&)
0x18001bce7  nop
0x18001bce8  lea     rcx, [rsp+2D8h+var_1A8]; void *
0x18001bcf0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001bcf5  test    r12, r12
0x18001bcf8  jz      loc_18001C61E
0x18001bcfe  mov     [rsp+2D8h+var_288], rbx
0x18001bd03  mov     [rsp+2D8h+var_240], rbx
0x18001bd0b  mov     [rsp+2D8h+var_238], rbx
0x18001bd13  mov     [rsp+2D8h+var_280], rbx
0x18001bd18  lea     rax, aCompat; "compat"
0x18001bd1f  mov     [rsp+2D8h+var_250], rax
0x18001bd27  lea     rax, aAppraiser; "appraiser"
0x18001bd2e  mov     [rsp+2D8h+var_268], rax
0x18001bd33  mov     [rsp+2D8h+var_290], ebx
0x18001bd37  cmp     bx, [r12]
0x18001bd3c  jz      loc_18001C61E
0x18001bd42  mov     [rsp+2D8h+pdwType], r12
0x18001bd47  lea     r9, aCommandlineWs; "Commandline: %ws"
0x18001bd4e  mov     r8d, 0CCh
0x18001bd54  mov     rdx, rdi
0x18001bd57  mov     ecx, r15d
0x18001bd5a  call    AslLogCallPrintf
0x18001bd5f  nop
0x18001bd60  lea     rdx, [rsp+2D8h+pNumArgs]; pNumArgs
0x18001bd65  mov     rcx, r12; lpCmdLine
0x18001bd68  call    cs:__imp_CommandLineToArgvW
0x18001bd6e  mov     r14, rax
0x18001bd71  mov     [rsp+2D8h+var_220], rax
0x18001bd79  mov     r13d, [rsp+2D8h+pNumArgs]
0x18001bd7e  test    rax, rax
0x18001bd81  jz      loc_18001C59A
0x18001bd87  cmp     r13d, 2
0x18001bd8b  jl      loc_18001C59A
0x18001bd91  mov     rdx, [rax]; String2
0x18001bd94  lea     rcx, aFeatures; "Features"
0x18001bd9b  call    wcscmp_0
0x18001bda0  test    eax, eax
0x18001bda2  jnz     short loc_18001BDC6
0x18001bda4  mov     r8, r14
0x18001bda7  mov     edx, r13d
0x18001bdaa  lea     rcx, [rsp+2D8h+var_260]
0x18001bdaf  call    ?SupportAllFeatures@AppCompatUtility@@YA_NAEBV?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@HPEAPEAG@Z; AppCompatUtility::SupportAllFeatures(std::set<std::wstring> const &,int,ushort * *)
0x18001bdb4  mov     r12, [rsp+2D8h+var_298]
0x18001bdb9  test    al, al
0x18001bdbb  jz      short loc_18001BDC1
0x18001bdbd  mov     [r12], esi
0x18001bdc1  jmp     loc_18001C5F2
0x18001bdc6  mov     eax, r13d
0x18001bdc9  and     eax, 80000001h
0x18001bdce  jge     short loc_18001BDD7
0x18001bdd0  sub     eax, esi
0x18001bdd2  or      eax, 0FFFFFFFEh
0x18001bdd5  add     eax, esi
0x18001bdd7  test    eax, eax
0x18001bdd9  jz      short loc_18001BE02
0x18001bddb  mov     dword ptr [rsp+2D8h+pdwType], r13d
0x18001bde0  lea     r9, aWrongArguments; "Wrong arguments number: %d"
0x18001bde7  mov     r8d, 0E9h
0x18001bded  mov     rdx, rdi
0x18001bdf0  mov     ecx, esi
0x18001bdf2  call    AslLogCallPrintf
0x18001bdf7  nop
0x18001bdf8  mov     r12, [rsp+2D8h+var_298]
0x18001bdfd  jmp     loc_18001C5F2
0x18001be02  mov     r12d, ebx
0x18001be05  lea     eax, [r13-1]
0x18001be09  test    eax, eax
0x18001be0b  jle     loc_18001C57B
0x18001be11  movsxd  r13, r12d
0x18001be14  mov     rdx, [r14+r13*8]
0x18001be18  lea     rcx, aPercentage; "-Percentage"
0x18001be1f  call    cs:__imp__o__wcsicmp
0x18001be25  test    eax, eax
0x18001be27  jnz     short loc_18001BE65
0x18001be29  movsxd  r13, r12d
0x18001be2c  mov     rdx, [r14+r13*8+8]
0x18001be31  lea     rcx, aFromonesetting; "FromOneSettings"
0x18001be38  call    cs:__imp__o__wcsicmp
0x18001be3e  mov     rcx, [rsp+2D8h+var_280]
0x18001be43  test    eax, eax
0x18001be45  jnz     short loc_18001BE52
0x18001be47  mov     edx, esi
0x18001be49  mov     [rsp+2D8h+var_290], edx
0x18001be4d  jmp     loc_18001BF30
0x18001be52  mov     r13, [r14+r13*8+8]
0x18001be57  mov     [rsp+2D8h+var_288], r13
0x18001be5c  mov     edx, [rsp+2D8h+var_290]
0x18001be60  jmp     loc_18001BF35
0x18001be65  mov     rdx, [r14+r13*8]
0x18001be69  lea     rcx, aStartdate; "-StartDate"
0x18001be70  call    cs:__imp__o__wcsicmp
0x18001be76  test    eax, eax
0x18001be78  jnz     short loc_18001BE8F
0x18001be7a  movsxd  rax, r12d
0x18001be7d  mov     rax, [r14+rax*8+8]
0x18001be82  mov     [rsp+2D8h+var_240], rax
0x18001be8a  jmp     loc_18001BF27
0x18001be8f  mov     rdx, [r14+r13*8]
0x18001be93  lea     rcx, aSdbid; "-SdbId"
0x18001be9a  call    cs:__imp__o__wcsicmp
0x18001bea0  test    eax, eax
0x18001bea2  jnz     short loc_18001BEB6
0x18001bea4  movsxd  rax, r12d
0x18001bea7  mov     rax, [r14+rax*8+8]
0x18001beac  mov     [rsp+2D8h+var_238], rax
0x18001beb4  jmp     short loc_18001BF27
0x18001beb6  mov     rdx, [r14+r13*8]
0x18001beba  lea     rcx, aOnesettingsval; "-OneSettingsValueName"
0x18001bec1  call    cs:__imp__o__wcsicmp
0x18001bec7  test    eax, eax
0x18001bec9  jnz     short loc_18001BEDA
0x18001becb  movsxd  rax, r12d
0x18001bece  mov     rcx, [r14+rax*8+8]
0x18001bed3  mov     [rsp+2D8h+var_280], rcx
0x18001bed8  jmp     short loc_18001BF2C
0x18001beda  mov     rdx, [r14+r13*8]
0x18001bede  lea     rcx, aOnesettingspar; "-OneSettingsPartner"
0x18001bee5  call    cs:__imp__o__wcsicmp
0x18001beeb  test    eax, eax
0x18001beed  jnz     short loc_18001BF01
0x18001beef  movsxd  rax, r12d
0x18001bef2  mov     rax, [r14+rax*8+8]
0x18001bef7  mov     [rsp+2D8h+var_250], rax
0x18001beff  jmp     short loc_18001BF27
0x18001bf01  mov     rdx, [r14+r13*8]
0x18001bf05  lea     rcx, aOnesettingsfea; "-OneSettingsFeature"
0x18001bf0c  call    cs:__imp__o__wcsicmp
0x18001bf12  test    eax, eax
0x18001bf14  jnz     loc_18001C553
0x18001bf1a  movsxd  rax, r12d
0x18001bf1d  mov     rax, [r14+rax*8+8]
0x18001bf22  mov     [rsp+2D8h+var_268], rax
0x18001bf27  mov     rcx, [rsp+2D8h+var_280]
0x18001bf2c  mov     edx, [rsp+2D8h+var_290]
0x18001bf30  mov     r13, [rsp+2D8h+var_288]
0x18001bf35  add     r12d, 2
0x18001bf39  mov     eax, [rsp+2D8h+pNumArgs]
0x18001bf3d  dec     eax
0x18001bf3f  cmp     r12d, eax
0x18001bf42  jl      loc_18001BE11
0x18001bf48  test    edx, edx
0x18001bf4a  jz      loc_18001C0B6
0x18001bf50  test    rcx, rcx
0x18001bf53  jnz     short loc_18001BF77
0x18001bf55  lea     r9, aOnesettingsval_0; "-OneSettingsValueName parameter is mand"...
0x18001bf5c  mov     r8d, 11Dh
0x18001bf62  mov     rdx, rdi
0x18001bf65  mov     ecx, esi
0x18001bf67  call    AslLogCallPrintf
0x18001bf6c  nop
0x18001bf6d  mov     r12, [rsp+2D8h+var_298]
0x18001bf72  jmp     loc_18001C5F2
0x18001bf77  lea     rax, [rsp+2D8h+var_1A8]
0x18001bf7f  mov     [rsp+2D8h+var_280], rax
0x18001bf84  xorps   xmm0, xmm0
0x18001bf87  movups  [rsp+2D8h+var_1A8], xmm0
0x18001bf8f  mov     [rsp+2D8h+var_198], rbx
0x18001bf97  mov     [rsp+2D8h+var_190], rbx
0x18001bf9f  or      r12, 0FFFFFFFFFFFFFFFFh
0x18001bfa3  mov     r8, r12
0x18001bfa6  inc     r8
0x18001bfa9  cmp     [rcx+r8*2], bx
0x18001bfae  jnz     short loc_18001BFA6
0x18001bfb0  mov     rdx, rcx
0x18001bfb3  lea     rcx, [rsp+2D8h+var_1A8]
0x18001bfbb  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001bfc0  nop
0x18001bfc1  lea     rax, [rsp+2D8h+var_210]
0x18001bfc9  mov     [rsp+2D8h+var_288], rax
0x18001bfce  xorps   xmm0, xmm0
0x18001bfd1  movups  [rsp+2D8h+var_210], xmm0
0x18001bfd9  mov     [rsp+2D8h+var_200], rbx
0x18001bfe1  mov     [rsp+2D8h+var_1F8], rbx
0x18001bfe9  mov     r8, r12
0x18001bfec  mov     rax, [rsp+2D8h+var_268]
0x18001bff1  inc     r8
0x18001bff4  cmp     [rax+r8*2], bx
0x18001bff9  jnz     short loc_18001BFF1
0x18001bffb  mov     rdx, rax
0x18001bffe  lea     rcx, [rsp+2D8h+var_210]
0x18001c006  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001c00b  nop
0x18001c00c  xorps   xmm0, xmm0
0x18001c00f  movups  [rsp+2D8h+var_1F0], xmm0
0x18001c017  mov     [rsp+2D8h+var_1E0], rbx
0x18001c01f  mov     [rsp+2D8h+var_1D8], rbx
0x18001c027  mov     rax, [rsp+2D8h+var_250]
0x18001c02f  inc     r12
0x18001c032  cmp     [rax+r12*2], bx
0x18001c037  jnz     short loc_18001C02F
0x18001c039  mov     r8, r12
0x18001c03c  mov     rdx, rax
0x18001c03f  lea     rcx, [rsp+2D8h+var_1F0]
0x18001c047  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001c04c  nop
0x18001c04d  lea     r9, [rsp+2D8h+var_1A8]
0x18001c055  lea     r8, [rsp+2D8h+var_210]
0x18001c05d  lea     rdx, [rsp+2D8h+var_1F0]
0x18001c065  lea     rcx, [rsp+2D8h+var_188]
0x18001c06d  call    ?GetOneSettingsValue@AppCompatUtility@@YAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V23@11@Z; AppCompatUtility::GetOneSettingsValue(std::wstring &,std::wstring,std::wstring,std::wstring)
0x18001c072  test    eax, eax
0x18001c074  jz      short loc_18001C09C
0x18001c076  mov     dword ptr [rsp+2D8h+pdwType], eax
0x18001c07a  lea     r9, aFailedToGetOne; "Failed to get OneSettings value. [0x%x]"
0x18001c081  mov     r8d, 129h
0x18001c087  mov     rdx, rdi
0x18001c08a  mov     ecx, esi
0x18001c08c  call    AslLogCallPrintf
0x18001c091  nop
0x18001c092  mov     r12, [rsp+2D8h+var_298]
0x18001c097  jmp     loc_18001C5F2
0x18001c09c  lea     r13, [rsp+2D8h+var_188]
0x18001c0a4  cmp     [rsp+2D8h+var_170], 7
0x18001c0ad  cmova   r13, qword ptr [rsp+2D8h+var_188]
0x18001c0b6  test    r13, r13
0x18001c0b9  jz      loc_18001C57B
0x18001c0bf  call    cs:__imp__o__errno
0x18001c0c5  mov     [rax], ebx
0x18001c0c7  lea     rdx, [rsp+2D8h+var_248]
0x18001c0cf  mov     rcx, r13
0x18001c0d2  call    cs:__imp__o_wcstod
  ... truncated ...
```
