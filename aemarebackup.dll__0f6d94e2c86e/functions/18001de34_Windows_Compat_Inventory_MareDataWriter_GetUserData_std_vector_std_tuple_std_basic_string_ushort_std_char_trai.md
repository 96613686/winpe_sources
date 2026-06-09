# Windows::Compat::Inventory::MareDataWriter::GetUserData(std::vector<std::tuple<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::tuple<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *)

- ea: `0x18001de34`
- end: `0x18001e2d9`
- name: `?GetUserData@MareDataWriter@Inventory@Compat@Windows@@SAJAEAV?$vector@V?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V12@@std@@V?$allocator@V?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V12@@std@@@2@@std@@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@6@@Z`
- size: `1189`
- prototype: `__int64 __fastcall(void **, _QWORD *)`
- caller_count: `5`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180017778`
- `0x1800257a8`
- `0x180025a20`
- `0x18002d0b4`
- `0x18002f614`

## callees

- `0x180004ea0`
- `0x18000527c`
- `0x180005914`
- `0x180006eac`
- `0x180006f14`
- `0x18000f988`
- `0x18000fb60`
- `0x180010274`
- `0x180010eb4`
- `0x18001209c`
- `0x1800134b8`
- `0x18001de34`
- `0x1800276cc`
- `0x180027d3c`
- `0x18004c020`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001df0b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001df0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001def8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dfa0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001def8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dfa0`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18001e1e2`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18001e1e2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001df37`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001df37`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001e137`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001e137`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001dede`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001df03`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e269`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001dede`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001df03`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e269`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001dff4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001dff4`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18001dfd4`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18001dfd4`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18001df96`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18001df96`

## string_xrefs

- `0x18001dfaa`: `ConvertStringSidToSidW failed %d`
- `0x18001deb7`: `Expect non-null jsonDir on first call`
- `0x18001dec4`: `Windows::Compat::Inventory::MareDataWriter::GetUserData`
- `0x18001df54`: `Windows::Compat::Inventory::MareDataWriter::GetUserData`
- `0x18001e152`: `Windows::Compat::Inventory::MareDataWriter::GetUserData`
- `0x18001df43`: `RegOpenKeyExW failed %d`
- `0x18001e05b`: `.json`
- `0x18001e129`: `ProfileImagePath`
- `0x18001dfb7`: `Windows::Compat::Inventory::MareDataWriter::IsWellKnownSid`

## pseudocode

```c
__int64 __fastcall Windows::Compat::Inventory::MareDataWriter::GetUserData(void **a1, _QWORD *a2)
{
  void *v4; // rcx
  __int64 v5; // rax
  int v7; // ebx
  const char *v8; // r9
  __int64 v9; // r8
  DWORD v10; // r14d
  DWORD i; // edx
  char v12; // di
  DWORD LastError; // eax
  __int64 v14; // r8
  WELL_KNOWN_SID_TYPE v15; // ebx
  __int64 v16; // rdx
  unsigned __int64 v17; // rcx
  _QWORD *v18; // r9
  __int64 v19; // rax
  const WCHAR *v20; // rdx
  LSTATUS ValueW; // eax
  int v22; // ecx
  LSTATUS v23; // eax
  PHKEY phkResult; // [rsp+20h] [rbp-E0h]
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  DWORD pcbData; // [rsp+50h] [rbp-B0h] BYREF
  PSID Sid; // [rsp+58h] [rbp-A8h] BYREF
  LPCWSTR lpSubKey[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v30; // [rsp+70h] [rbp-90h]
  _OWORD v31[2]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE Src[32]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR StringSid[264]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE pvData[528]; // [rsp+2D0h] [rbp+1D0h] BYREF

  hKey = 0;
  if ( dword_18011C0EC > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_18011C0EC);
    if ( dword_18011C0EC == -1 )
    {
      atexit(Windows::Compat::Inventory::MareDataWriter::GetUserData_::_2_::_dynamic_atexit_destructor_for__userData__);
      Init_thread_footer(&dword_18011C0EC);
    }
  }
  v4 = qword_18011C0F0;
  v5 = qword_18011C0F8;
  if ( qword_18011C0F0 != (void *)qword_18011C0F8 )
    goto LABEL_39;
  if ( !a2 )
  {
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::MareDataWriter::GetUserData",
      720,
      "Expect non-null jsonDir on first call");
    return 2147549183LL;
  }
  hKey = 0;
  v7 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\ProfileList",
         0,
         0x20019u,
         &hKey);
  if ( v7 )
  {
    v8 = "RegOpenKeyExW failed %d";
    v9 = 727;
    goto LABEL_7;
  }
  v10 = 0;
  for ( i = 0; ; i = v10 )
  {
    cchName = 260;
    v23 = RegEnumKeyExW(hKey, i, StringSid, &cchName, 0, 0, 0, 0);
    v7 = v23;
    if ( v23 )
      break;
    v12 = 0;
    Sid = 0;
    if ( ConvertStringSidToSidW(StringSid, &Sid) )
    {
      v15 = WinNullSid;
      while ( !IsWellKnownSid(Sid, v15) )
      {
        if ( (unsigned int)++v15 > (WinAuthenticationAuthorityAssertedSid|WinSelfSid) )
          goto LABEL_17;
      }
      v12 = 1;
    }
    else
    {
      LastError = GetLastError();
      AslLogCallPrintf(
        1,
        "Windows::Compat::Inventory::MareDataWriter::IsWellKnownSid",
        786,
        "ConvertStringSidToSidW failed %d",
        LastError);
    }
LABEL_17:
    if ( Sid )
      LocalFree(Sid);
    if ( !v12 )
    {
      v16 = a2[2];
      v17 = -1;
      do
        ++v17;
      while ( StringSid[v17] );
      if ( 0x7FFFFFFFFFFFFFFELL - v16 < v17 )
        std::_Xlen_string();
      if ( a2[3] <= 7u )
        v18 = a2;
      else
        v18 = (_QWORD *)*a2;
      std::wstring::wstring(Src, v16, v14, v18, v16, StringSid, v17);
      v19 = std::wstring::append(Src, L".json");
      v31[0] = *(_OWORD *)v19;
      v31[1] = *(_OWORD *)(v19 + 16);
      *(_QWORD *)(v19 + 16) = 0;
      *(_QWORD *)(v19 + 24) = 7;
      *(_WORD *)v19 = 0;
      std::wstring::~wstring(Src);
      memset_0(pvData, 0, 0x208u);
      pcbData = 520;
      *(_OWORD *)lpSubKey = 0;
      v30 = 0;
      std::wstring::_Construct<1,unsigned short const *>(
        lpSubKey,
        L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\ProfileList");
      std::wstring::append(lpSubKey, (void *)L"\\");
      std::wstring::append(lpSubKey, StringSid);
      v20 = (const WCHAR *)lpSubKey;
      if ( *((_QWORD *)&v30 + 1) > 7u )
        v20 = lpSubKey[0];
      ValueW = RegGetValueW(HKEY_LOCAL_MACHINE, v20, L"ProfileImagePath", 2u, 0, pvData, &pcbData);
      if ( ValueW )
      {
        AslLogCallPrintf(
          3,
          "Windows::Compat::Inventory::MareDataWriter::GetUserData",
          751,
          "RegGetValueW failed [%d]",
          ValueW);
      }
      else if ( qword_18011C0F8 == qword_18011C100 )
      {
        std::vector<std::tuple<std::wstring,std::wstring,std::wstring>>::_Emplace_reallocate<unsigned short (&)[260],unsigned short (&)[260],std::wstring &>(
          v22,
          qword_18011C0F8,
          (unsigned int)StringSid,
          (unsigned int)pvData,
          (__int64)v31);
      }
      else
      {
        std::_Default_allocator_traits<std::allocator<std::tuple<std::wstring,std::wstring,std::wstring>>>::construct<std::tuple<std::wstring,std::wstring,std::wstring>,unsigned short (&)[260],unsigned short (&)[260],std::wstring &>(
          v22,
          qword_18011C0F8,
          (unsigned int)StringSid,
          (unsigned int)pvData,
          (__int64)v31);
        qword_18011C0F8 += 96;
      }
      std::wstring::~wstring(lpSubKey);
      std::wstring::~wstring(v31);
    }
    ++v10;
  }
  if ( v23 == 259 )
  {
    v5 = qword_18011C0F8;
    v4 = qword_18011C0F0;
LABEL_39:
    if ( a1 != &qword_18011C0F0 )
    {
      std::vector<std::tuple<std::wstring,std::wstring,std::wstring>>::_Assign_counted_range<std::tuple<std::wstring,std::wstring,std::wstring> *>(
        a1,
        v4,
        0xAAAAAAAAAAAAAAABuLL * ((v5 - (__int64)v4) >> 5));
      v5 = qword_18011C0F8;
      v4 = qword_18011C0F0;
    }
    v7 = v4 == (void *)v5;
    goto LABEL_42;
  }
  v8 = "RegEnumKeyExW failed [%d]";
  v9 = 764;
LABEL_7:
  LODWORD(phkResult) = v7;
  AslLogCallPrintf(1, "Windows::Compat::Inventory::MareDataWriter::GetUserData", v9, v8, phkResult);
  if ( v7 > 0 )
    v7 = (unsigned __int16)v7 | 0x80070000;
LABEL_42:
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18001de34  mov     [rsp-8+arg_10], rbx
0x18001de39  mov     [rsp-8+arg_18], rsi
0x18001de3e  push    rbp
0x18001de3f  push    rdi
0x18001de40  push    r12
0x18001de42  push    r14
0x18001de44  push    r15
0x18001de46  lea     rbp, [rsp-3F0h]
0x18001de4e  sub     rsp, 4F0h
0x18001de55  mov     rax, cs:__security_cookie
0x18001de5c  xor     rax, rsp
0x18001de5f  mov     [rbp+410h+var_30], rax
0x18001de66  mov     rsi, rdx
0x18001de69  mov     r15, rcx
0x18001de6c  xor     r12d, r12d
0x18001de6f  mov     [rsp+510h+hKey], r12
0x18001de74  mov     ecx, cs:_tls_index
0x18001de7a  mov     rax, gs:58h
0x18001de83  mov     edx, 4
0x18001de88  mov     rax, [rax+rcx*8]
0x18001de8c  mov     eax, [rdx+rax]
0x18001de8f  cmp     cs:dword_18011C0EC, eax
0x18001de95  jg      loc_18001E2A2
0x18001de9b  mov     rcx, cs:qword_18011C0F0
0x18001dea2  mov     rax, cs:qword_18011C0F8
0x18001dea9  cmp     rcx, rax
0x18001deac  jnz     loc_18001E219
0x18001deb2  test    rsi, rsi
0x18001deb5  jnz     short loc_18001DEEE
0x18001deb7  lea     r9, aExpectNonNullJ; "Expect non-null jsonDir on first call"
0x18001debe  mov     r8d, 2D0h
0x18001dec4  lea     rdx, aWindowsCompatI_32; "Windows::Compat::Inventory::MareDataWri"...
0x18001decb  lea     ecx, [rsi+1]
0x18001dece  call    AslLogCallPrintf
0x18001ded3  nop
0x18001ded4  mov     rcx, [rsp+510h+hKey]; hKey
0x18001ded9  test    rcx, rcx
0x18001dedc  jz      short loc_18001DEE4
0x18001dede  call    cs:__imp_RegCloseKey
0x18001dee4  mov     eax, 8000FFFFh
0x18001dee9  jmp     loc_18001E271
0x18001deee  mov     rdi, [rsp+510h+hKey]
0x18001def3  test    rdi, rdi
0x18001def6  jz      short loc_18001DF11
0x18001def8  call    cs:__imp_GetLastError
0x18001defe  mov     ebx, eax
0x18001df00  mov     rcx, rdi; hKey
0x18001df03  call    cs:__imp_RegCloseKey
0x18001df09  mov     ecx, ebx; dwErrCode
0x18001df0b  call    cs:__imp_SetLastError
0x18001df11  mov     [rsp+510h+hKey], r12
0x18001df16  lea     rax, [rsp+510h+hKey]
0x18001df1b  mov     [rsp+510h+phkResult], rax; phkResult
0x18001df20  mov     r9d, 20019h; samDesired
0x18001df26  xor     r8d, r8d; ulOptions
0x18001df29  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18001df30  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001df37  call    cs:__imp_RegOpenKeyExW
0x18001df3d  mov     ebx, eax
0x18001df3f  test    eax, eax
0x18001df41  jz      short loc_18001DF7B
0x18001df43  lea     r9, aRegopenkeyexwF; "RegOpenKeyExW failed %d"
0x18001df4a  mov     r8d, 2D7h
0x18001df50  mov     dword ptr [rsp+510h+phkResult], ebx
0x18001df54  lea     rdx, aWindowsCompatI_32; "Windows::Compat::Inventory::MareDataWri"...
0x18001df5b  mov     ecx, 1
0x18001df60  call    AslLogCallPrintf
0x18001df65  test    ebx, ebx
0x18001df67  jle     loc_18001E25C
0x18001df6d  movzx   ebx, bx
0x18001df70  or      ebx, 80070000h
0x18001df76  jmp     loc_18001E25C
0x18001df7b  mov     r14d, r12d
0x18001df7e  xor     edx, edx
0x18001df80  jmp     loc_18001E1B8
0x18001df85  mov     dil, r12b
0x18001df88  mov     [rsp+510h+Sid], r12
0x18001df8d  lea     rdx, [rsp+510h+Sid]; Sid
0x18001df92  lea     rcx, [rbp+410h+StringSid]; StringSid
0x18001df96  call    cs:__imp_ConvertStringSidToSidW
0x18001df9c  test    eax, eax
0x18001df9e  jnz     short loc_18001DFCA
0x18001dfa0  call    cs:__imp_GetLastError
0x18001dfa6  mov     dword ptr [rsp+510h+phkResult], eax
0x18001dfaa  lea     r9, aConvertstrings; "ConvertStringSidToSidW failed %d"
0x18001dfb1  mov     r8d, 312h
0x18001dfb7  lea     rdx, aWindowsCompatI_10; "Windows::Compat::Inventory::MareDataWri"...
0x18001dfbe  mov     ecx, 1
0x18001dfc3  call    AslLogCallPrintf
0x18001dfc8  jmp     short loc_18001DFEA
0x18001dfca  mov     ebx, r12d
0x18001dfcd  mov     edx, ebx; WellKnownSidType
0x18001dfcf  mov     rcx, [rsp+510h+Sid]; pSid
0x18001dfd4  call    cs:__imp_IsWellKnownSid
0x18001dfda  test    eax, eax
0x18001dfdc  jnz     short loc_18001DFE7
0x18001dfde  inc     ebx
0x18001dfe0  cmp     ebx, 77h ; 'w'
0x18001dfe3  jbe     short loc_18001DFCD
0x18001dfe5  jmp     short loc_18001DFEA
0x18001dfe7  mov     dil, 1
0x18001dfea  mov     rcx, [rsp+510h+Sid]; hMem
0x18001dfef  test    rcx, rcx
0x18001dff2  jz      short loc_18001DFFA
0x18001dff4  call    cs:__imp_LocalFree
0x18001dffa  test    dil, dil
0x18001dffd  jnz     loc_18001E1B2
0x18001e003  mov     rdx, [rsi+10h]
0x18001e007  lea     rax, [rbp+410h+StringSid]
0x18001e00b  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18001e00f  inc     rcx
0x18001e012  cmp     [rax+rcx*2], r12w
0x18001e017  jnz     short loc_18001E00F
0x18001e019  mov     rax, 7FFFFFFFFFFFFFFEh
0x18001e023  sub     rax, rdx
0x18001e026  cmp     rax, rcx
0x18001e029  jb      loc_18001E29C
0x18001e02f  cmp     qword ptr [rsi+18h], 7
0x18001e034  jbe     short loc_18001E03B
0x18001e036  mov     r9, [rsi]
0x18001e039  jmp     short loc_18001E03E
0x18001e03b  mov     r9, rsi
0x18001e03e  mov     [rsp+510h+pcbData], rcx
0x18001e043  lea     rax, [rbp+410h+StringSid]
0x18001e047  mov     [rsp+510h+pvData], rax
0x18001e04c  mov     [rsp+510h+phkResult], rdx
0x18001e051  lea     rcx, [rbp+410h+Src]
0x18001e055  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x18001e05a  nop
0x18001e05b  lea     rdx, aJson_0; ".json"
0x18001e062  lea     rcx, [rbp+410h+Src]; Src
0x18001e066  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18001e06b  movups  xmm0, xmmword ptr [rax]
0x18001e06e  movups  [rbp+410h+var_490], xmm0
0x18001e072  movups  xmm1, xmmword ptr [rax+10h]
0x18001e076  movups  [rbp+410h+var_480], xmm1
0x18001e07a  mov     [rax+10h], r12
0x18001e07e  mov     qword ptr [rax+18h], 7
0x18001e086  mov     [rax], r12w
0x18001e08a  lea     rcx, [rbp+410h+Src]
0x18001e08e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001e093  xor     edx, edx; Val
0x18001e095  mov     r8d, 208h; Size
0x18001e09b  lea     rcx, [rbp+410h+var_240]; void *
0x18001e0a2  call    memset_0
0x18001e0a7  mov     [rsp+510h+var_4C0], 208h
0x18001e0af  xorps   xmm0, xmm0
0x18001e0b2  movups  xmmword ptr [rsp+510h+lpSubKey], xmm0
0x18001e0b7  xorps   xmm1, xmm1
0x18001e0ba  movdqu  [rsp+510h+var_4A0], xmm1
0x18001e0c0  mov     r8d, 38h ; '8'
0x18001e0c6  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18001e0cd  lea     rcx, [rsp+510h+lpSubKey]
0x18001e0d2  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001e0d7  nop
0x18001e0d8  lea     rdx, SubBlock; "\\"
0x18001e0df  lea     rcx, [rsp+510h+lpSubKey]; Src
0x18001e0e4  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18001e0e9  lea     rdx, [rbp+410h+StringSid]; void *
0x18001e0ed  lea     rcx, [rsp+510h+lpSubKey]; Src
0x18001e0f2  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18001e0f7  lea     rdx, [rsp+510h+lpSubKey]
0x18001e0fc  cmp     qword ptr [rsp+510h+var_4A0+8], 7
0x18001e102  cmova   rdx, [rsp+510h+lpSubKey]; lpSubKey
0x18001e108  lea     rax, [rsp+510h+var_4C0]
0x18001e10d  mov     [rsp+510h+pcbData], rax; pcbData
0x18001e112  lea     rax, [rbp+410h+var_240]
0x18001e119  mov     [rsp+510h+pvData], rax; pvData
0x18001e11e  mov     [rsp+510h+phkResult], r12; pdwType
0x18001e123  mov     r9d, 2; dwFlags
0x18001e129  lea     r8, aProfileimagepa; "ProfileImagePath"
0x18001e130  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18001e137  call    cs:__imp_RegGetValueW
0x18001e13d  test    eax, eax
0x18001e13f  jz      short loc_18001E165
0x18001e141  mov     dword ptr [rsp+510h+phkResult], eax
0x18001e145  lea     r9, aReggetvaluewFa; "RegGetValueW failed [%d]"
0x18001e14c  mov     r8d, 2EFh
0x18001e152  lea     rdx, aWindowsCompatI_32; "Windows::Compat::Inventory::MareDataWri"...
0x18001e159  mov     ecx, 3
0x18001e15e  call    AslLogCallPrintf
0x18001e163  jmp     short loc_18001E19E
0x18001e165  mov     rdx, cs:qword_18011C0F8
0x18001e16c  lea     rax, [rbp+410h+var_490]
0x18001e170  lea     r9, [rbp+410h+var_240]
0x18001e177  lea     r8, [rbp+410h+StringSid]
0x18001e17b  mov     [rsp+510h+phkResult], rax
0x18001e180  cmp     rdx, cs:qword_18011C100
0x18001e187  jz      short loc_18001E198
0x18001e189  call    ??$construct@V?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V12@@std@@AEAY0BAE@GAEAY0BAE@GAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@?$_Default_allocator_traits@V?$allocator@V?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V12@@std@@@std@@@std@@SAXAEAV?$allocator@V?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V12@@std@@@1@QEAV?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V12@@1@AEAY0BAE@G2AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Default_allocator_traits<std::allocator<std::tuple<std::wstring,std::wstring,std::wstring>>>::construct<std::tuple<std::wstring,std::wstring,std::wstring>,ushort (&)[260],ushort (&)[260],std::wstring &>(std::allocator<std::tuple<std::wstring,std::wstring,std::wstring>> &,std::tuple<std::wstring,std::wstring,std::wstring> * const,ushort (&)[260],ushort (&)[260],std::wstring &)
0x18001e18e  add     cs:qword_18011C0F8, 60h ; '`'
0x18001e196  jmp     short loc_18001E19E
0x18001e198  call    ??$_Emplace_reallocate@AEAY0BAE@GAEAY0BAE@GAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V12@@std@@V?$allocator@V?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V12@@std@@@2@@std@@AEAAPEAV?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V12@@1@QEAV21@AEAY0BAE@G1AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::vector<std::tuple<std::wstring,std::wstring,std::wstring>>::_Emplace_reallocate<ushort (&)[260],ushort (&)[260],std::wstring &>(std::tuple<std::wstring,std::wstring,std::wstring> * const,ushort (&)[260],ushort (&)[260],std::wstring &)
0x18001e19d  nop
0x18001e19e  lea     rcx, [rsp+510h+lpSubKey]
0x18001e1a3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001e1a8  nop
0x18001e1a9  lea     rcx, [rbp+410h+var_490]
0x18001e1ad  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001e1b2  inc     r14d
0x18001e1b5  mov     edx, r14d; dwIndex
0x18001e1b8  mov     [rsp+510h+lpftLastWriteTime], r12; lpftLastWriteTime
0x18001e1bd  mov     [rsp+510h+pcbData], r12; lpcchClass
0x18001e1c2  mov     [rsp+510h+pvData], r12; lpClass
0x18001e1c7  mov     [rsp+510h+phkResult], r12; lpReserved
0x18001e1cc  mov     [rsp+510h+cchName], 104h
0x18001e1d4  lea     r9, [rsp+510h+cchName]; lpcchName
0x18001e1d9  lea     r8, [rbp+410h+StringSid]; lpName
0x18001e1dd  mov     rcx, [rsp+510h+hKey]; hKey
0x18001e1e2  call    cs:__imp_RegEnumKeyExW
0x18001e1e8  test    eax, eax
0x18001e1ea  mov     ebx, eax
0x18001e1ec  jz      loc_18001DF85
0x18001e1f2  cmp     eax, 103h
0x18001e1f7  jz      short loc_18001E20B
0x18001e1f9  lea     r9, aRegenumkeyexwF; "RegEnumKeyExW failed [%d]"
0x18001e200  mov     r8d, 2FCh
0x18001e206  jmp     loc_18001DF50
0x18001e20b  mov     rax, cs:qword_18011C0F8
0x18001e212  mov     rcx, cs:qword_18011C0F0
0x18001e219  lea     rdx, qword_18011C0F0
0x18001e220  cmp     r15, rdx
0x18001e223  jz      short loc_18001E253
0x18001e225  sub     rax, rcx
0x18001e228  sar     rax, 5
0x18001e22c  mov     r8, 0AAAAAAAAAAAAAAABh
0x18001e236  imul    r8, rax
0x18001e23a  mov     rdx, rcx
0x18001e23d  mov     rcx, r15
0x18001e240  call    ??$_Assign_counted_range@PEAV?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V12@@std@@@?$vector@V?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V12@@std@@V?$allocator@V?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V12@@std@@@2@@std@@AEAAXPEAV?$tuple@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V12@@1@_K@Z; std::vector<std::tuple<std::wstring,std::wstring,std::wstring>>::_Assign_counted_range<std::tuple<std::wstring,std::wstring,std::wstring> *>(std::tuple<std::wstring,std::wstring,std::wstring> *,unsigned __int64)
0x18001e245  mov     rax, cs:qword_18011C0F8
0x18001e24c  mov     rcx, cs:qword_18011C0F0
0x18001e253  mov     ebx, r12d
0x18001e256  cmp     rcx, rax
0x18001e259  setz    bl
0x18001e25c  mov     rdi, [rsp+510h+hKey]
0x18001e261  test    rdi, rdi
0x18001e264  jz      short loc_18001E26F
0x18001e266  mov     rcx, rdi; hKey
0x18001e269  call    cs:__imp_RegCloseKey
0x18001e26f  mov     eax, ebx
0x18001e271  mov     rcx, [rbp+410h+var_30]
0x18001e278  xor     rcx, rsp; StackCookie
0x18001e27b  call    __security_check_cookie
0x18001e280  lea     r11, [rsp+510h+var_20]
0x18001e288  mov     rbx, [r11+40h]
0x18001e28c  mov     rsi, [r11+48h]
0x18001e290  mov     rsp, r11
0x18001e293  pop     r15
0x18001e295  pop     r14
0x18001e297  pop     r12
0x18001e299  pop     rdi
0x18001e29a  pop     rbp
0x18001e29b  retn
0x18001e29c  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
0x18001e2a2  lea     rcx, dword_18011C0EC
0x18001e2a9  call    _Init_thread_header
0x18001e2ae  cmp     cs:dword_18011C0EC, 0FFFFFFFFh
0x18001e2b5  jnz     loc_18001DE9B
0x18001e2bb  lea     rcx, _Windows__Compat__Inventory__MareDataWriter__GetUserData____2____dynamic_atexit_destructor_for__userData__; void (__cdecl *)()
0x18001e2c2  call    atexit
0x18001e2c7  lea     rcx, dword_18011C0EC
0x18001e2ce  call    _Init_thread_footer
0x18001e2d3  jmp     loc_18001DE9B
```
