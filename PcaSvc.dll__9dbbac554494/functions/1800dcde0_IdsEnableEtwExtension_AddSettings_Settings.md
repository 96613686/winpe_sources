# IdsEnableEtwExtension::AddSettings(Settings *)

- ea: `0x1800dcde0`
- end: `0x1800dd407`
- name: `?AddSettings@IdsEnableEtwExtension@@UEAAKPEAVSettings@@@Z`
- size: `1575`
- prototype: `unsigned int __fastcall(IdsEnableEtwExtension *__hidden this, struct Settings *)`
- caller_count: `0`
- callee_count: `17`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180012920`
- `0x1800182e0`
- `0x180018768`
- `0x1800d9f08`
- `0x1800d9f20`
- `0x1800da020`
- `0x1800da288`
- `0x1800da2a4`
- `0x1800da2c0`
- `0x1800da2dc`
- `0x1800da2f8`
- `0x1800da5bc`
- `0x1800da644`
- `0x1800dcde0`
- `0x1800dde50`
- `0x1800ddec4`
- `0x1800f1f10`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800dcf1a`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800dd151`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800dd1fe`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800dd25f`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800dd27e`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800dd29c`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800dd2b4`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800dd2f6`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800dd309`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800dd36e`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800dd37d`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800dd390`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800dd3d8`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800dcf1a`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800dd151`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800dd1fe`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800dd25f`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800dd27e`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800dd29c`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800dd2b4`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800dd2f6`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800dd309`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800dd36e`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800dd37d`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800dd390`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800dd3d8`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800dd0ee`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800dd0ee`

## string_xrefs

- `0x1800dcf7d`: `IdsEnableEtwExtension::AddSettings: logFileSizeMB=%u\n`
- `0x1800dcef3`: `IdsEnableEtwExtension::AddSettings: extension is disabled\n`
- `0x1800dd39b`: `IdsEnableEtwExtension::AddSettings: missing or invalid /enableetw/enabled\n`
- `0x1800dd3ad`: `IdsEnableEtwExtension::AddSettings: missing or invalid /enableetw configuration\n`
- `0x1800dce29`: `IdsEnableEtwExtension::AddSettings`
- `0x1800dcf00`: `IdsEnableEtwExtension::AddSettings`
- `0x1800dcf8a`: `IdsEnableEtwExtension::AddSettings`
- `0x1800dd121`: `IdsEnableEtwExtension::AddSettings`
- `0x1800dd231`: `IdsEnableEtwExtension::AddSettings`
- `0x1800dd2d1`: `IdsEnableEtwExtension::AddSettings`
- `0x1800dd354`: `IdsEnableEtwExtension::AddSettings`
- `0x1800dd3ba`: `IdsEnableEtwExtension::AddSettings`
- `0x1800dce1e`: `IdsEnableEtwExtension::AddSettings failed: null settings\n`
- `0x1800dd347`: `IdsEnableEtwExtension::AddSettings succeeded, %zu providers\n`
- `0x1800dd224`: `IdsEnableEtwExtension::AddSettings: provider[%zu] eventIds=%zu\n`
- `0x1800dd114`: `IdsEnableEtwExtension::AddSettings: invalid GUID '%ws' at provider[%zu]: 0x%08X\n`
- `0x1800dd2c4`: `IdsEnableEtwExtension::AddSettings: provider[%zu] missing guid, skipping\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=25
__int64 __fastcall IdsEnableEtwExtension::AddSettings(IdsEnableEtwExtension *this, struct Settings *a2)
{
  struct Settings *v2; // r15
  IdsEnableEtwExtension *v3; // r14
  __int64 v5; // rdx
  SettingEntry *v6; // rbx
  __int64 v7; // rdx
  SettingEntry *v8; // rdi
  SettingEntry *v9; // rcx
  bool Bool; // al
  __int64 v11; // rdx
  SettingEntry *v12; // rsi
  SettingEntry *v13; // rcx
  int Integer; // eax
  __int64 v15; // rdx
  SettingEntry *v16; // r13
  SettingEntry *v17; // rcx
  __int64 v18; // rdx
  SettingEntry *v19; // r12
  __int64 v20; // rcx
  __int64 v21; // rdi
  IdsEnableEtwExtension *v22; // rbx
  void *v23; // r14
  __int64 v24; // rdx
  SettingEntry *v25; // rsi
  const OLECHAR *v26; // rcx
  HRESULT v27; // eax
  LPCOLESTR *v28; // rcx
  __int64 v29; // rdx
  __int64 v30; // rdx
  SettingEntry *v31; // r12
  SettingEntry *v32; // rcx
  __int64 i; // rdi
  SettingEntry *v34; // r15
  __int64 v35; // rdx
  __int64 v36; // [rsp+30h] [rbp-D0h]
  __int16 v37; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v38; // [rsp+48h] [rbp-B8h]
  SettingEntry *v39; // [rsp+50h] [rbp-B0h] BYREF
  SettingEntry *v40; // [rsp+58h] [rbp-A8h] BYREF
  SettingEntry *v41; // [rsp+60h] [rbp-A0h] BYREF
  SettingEntry *v42; // [rsp+68h] [rbp-98h] BYREF
  IdsEnableEtwExtension *v43; // [rsp+70h] [rbp-90h]
  SettingEntry *v44; // [rsp+78h] [rbp-88h] BYREF
  void *v45; // [rsp+80h] [rbp-80h] BYREF
  SettingEntry *v46; // [rsp+88h] [rbp-78h] BYREF
  SettingEntry *v47; // [rsp+90h] [rbp-70h] BYREF
  SettingEntry *v48; // [rsp+98h] [rbp-68h] BYREF
  struct Settings *v49; // [rsp+A0h] [rbp-60h]
  LPCOLESTR lpsz[3]; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int64 v51; // [rsp+C0h] [rbp-40h]
  _BYTE v52[32]; // [rsp+C8h] [rbp-38h] BYREF
  GUID pclsid; // [rsp+E8h] [rbp-18h] BYREF
  __int128 v54; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v55; // [rsp+108h] [rbp+8h]
  _BYTE v56[32]; // [rsp+110h] [rbp+10h] BYREF

  v2 = a2;
  v49 = a2;
  v3 = this;
  v43 = this;
  if ( !a2 )
  {
    AslLogCallPrintf(
      3,
      (unsigned int)"IdsEnableEtwExtension::AddSettings",
      57,
      (unsigned int)"IdsEnableEtwExtension::AddSettings failed: null settings\n");
    return 87;
  }
  std::wstring::wstring((__int64)lpsz, (__int64)L"/enableetw");
  Settings::QueryEntry(v2, &v40, 0, lpsz);
  LOBYTE(v5) = 1;
  std::wstring::_Tidy(lpsz, v5, 0);
  v6 = v40;
  if ( v40 && SettingEntry::IsObject(v40) )
  {
    std::wstring::wstring((__int64)v52, (__int64)L"/enabled");
    Settings::QueryEntry(v2, &v41, v6, v52);
    LOBYTE(v7) = 1;
    std::wstring::_Tidy(v52, v7, 0);
    v8 = v41;
    if ( !v41 || !SettingEntry::IsBool(v41) )
    {
      AslLogCallPrintf(
        3,
        (unsigned int)"IdsEnableEtwExtension::AddSettings",
        71,
        (unsigned int)"IdsEnableEtwExtension::AddSettings: missing or invalid /enableetw/enabled\n");
LABEL_9:
      if ( v8 )
        operator delete(v8);
      goto LABEL_63;
    }
    Bool = SettingEntry::GetBool(v9);
    *((_BYTE *)v3 + 17) = Bool;
    if ( !Bool )
    {
      AslLogCallPrintf(
        3,
        (unsigned int)"IdsEnableEtwExtension::AddSettings",
        79,
        (unsigned int)"IdsEnableEtwExtension::AddSettings: extension is disabled\n");
      goto LABEL_9;
    }
    std::wstring::wstring((__int64)lpsz, (__int64)L"/logfilesize");
    Settings::QueryEntry(v2, &v42, v6, lpsz);
    LOBYTE(v11) = 1;
    std::wstring::_Tidy(lpsz, v11, 0);
    v12 = v42;
    if ( v42 && SettingEntry::IsInteger(v42) )
    {
      Integer = SettingEntry::GetInteger(v13);
      *((_DWORD *)v3 + 5) = Integer;
      AslLogCallPrintf(
        3,
        (unsigned int)"IdsEnableEtwExtension::AddSettings",
        88,
        (unsigned int)"IdsEnableEtwExtension::AddSettings: logFileSizeMB=%u\n",
        Integer);
    }
    std::wstring::wstring((__int64)v52, (__int64)L"/alsorealtime");
    Settings::QueryEntry(v2, &v44, v6, v52);
    LOBYTE(v15) = 1;
    std::wstring::_Tidy(v52, v15, 0);
    v16 = v44;
    if ( v44 && SettingEntry::IsBool(v44) )
      *((_BYTE *)v3 + 24) = SettingEntry::GetBool(v17);
    std::wstring::wstring((__int64)v56, (__int64)L"/providers");
    Settings::QueryEntry(v2, &v39, v6, v56);
    LOBYTE(v18) = 1;
    std::wstring::_Tidy(v56, v18, 0);
    v19 = v39;
    if ( !v39 || !SettingEntry::IsArray(v39) )
    {
LABEL_55:
      AslLogCallPrintf(
        3,
        (unsigned int)"IdsEnableEtwExtension::AddSettings",
        158,
        (unsigned int)"IdsEnableEtwExtension::AddSettings succeeded, %zu providers\n",
        0xCCCCCCCCCCCCCCCDuLL * ((__int64)(*((_QWORD *)v3 + 5) - *((_QWORD *)v3 + 4)) >> 3));
      if ( v19 )
        operator delete(v19);
      if ( v16 )
        operator delete(v16);
      if ( v12 )
        operator delete(v12);
      goto LABEL_9;
    }
    v21 = 0;
    v38 = 0;
    v22 = v43;
    while ( 1 )
    {
      while ( 1 )
      {
        Settings::QueryArrayEntry(v20, &v45, v19, v21);
        v23 = v45;
        if ( !v45 )
        {
          v6 = v40;
          v8 = v41;
          v12 = v42;
          v3 = v43;
          goto LABEL_55;
        }
        std::wstring::wstring((__int64)v52, (__int64)L"/guid");
        Settings::QueryEntry(v2, &v46, v23, v52);
        LOBYTE(v24) = 1;
        std::wstring::_Tidy(v52, v24, 0);
        v25 = v46;
        if ( v46 )
        {
          if ( SettingEntry::IsString(v46) )
            break;
        }
        AslLogCallPrintf(
          3,
          (unsigned int)"IdsEnableEtwExtension::AddSettings",
          114,
          (unsigned int)"IdsEnableEtwExtension::AddSettings: provider[%zu] missing guid, skipping\n",
          v21++);
        v38 = v21;
        if ( v25 )
          goto LABEL_50;
LABEL_52:
        if ( v23 )
          goto LABEL_48;
      }
      pclsid = 0;
      v54 = 0;
      v55 = 0;
      SettingEntry::GetString(v25, lpsz);
      v26 = (const OLECHAR *)lpsz;
      if ( v51 >= 8 )
        v26 = lpsz[0];
      v27 = CLSIDFromString(v26, &pclsid);
      if ( v27 < 0 )
      {
        v28 = lpsz;
        if ( v51 >= 8 )
          v28 = (LPCOLESTR *)lpsz[0];
        LODWORD(v36) = v27;
        AslLogCallPrintf(
          1,
          (unsigned int)"IdsEnableEtwExtension::AddSettings",
          125,
          (unsigned int)"IdsEnableEtwExtension::AddSettings: invalid GUID '%ws' at provider[%zu]: 0x%08X\n",
          v28,
          v21++,
          v36);
        v38 = v21;
        LOBYTE(v29) = 1;
        std::wstring::_Tidy(lpsz, v29, 0);
        v20 = v54;
        if ( (_QWORD)v54 )
        {
          operator delete((void *)v54);
          v54 = 0;
          v55 = 0;
        }
LABEL_50:
        if ( v25 )
          operator delete(v25);
        goto LABEL_52;
      }
      std::wstring::wstring((__int64)v52, (__int64)L"/eventids");
      Settings::QueryEntry(v2, &v47, v23, v52);
      LOBYTE(v30) = 1;
      std::wstring::_Tidy(v52, v30, 0);
      v31 = v47;
      if ( v47 && SettingEntry::IsArray(v47) )
      {
        for ( i = 0; ; ++i )
        {
          Settings::QueryArrayEntry(v32, &v48, v31, i);
          v34 = v48;
          if ( !v48 )
            break;
          if ( SettingEntry::IsInteger(v48) )
          {
            v37 = SettingEntry::GetInteger(v32);
            std::vector<unsigned short>::push_back(&v54, &v37);
          }
          if ( v34 )
            operator delete(v34);
        }
        v2 = v49;
        v21 = v38;
      }
      AslLogCallPrintf(
        3,
        (unsigned int)"IdsEnableEtwExtension::AddSettings",
        151,
        (unsigned int)"IdsEnableEtwExtension::AddSettings: provider[%zu] eventIds=%zu\n",
        v21,
        (__int64)(*((_QWORD *)&v54 + 1) - v54) >> 1);
      std::vector<IdsEtwProviderEntry>::push_back((char *)v22 + 32, &pclsid);
      v38 = ++v21;
      if ( v31 )
        operator delete(v31);
      LOBYTE(v35) = 1;
      std::wstring::_Tidy(lpsz, v35, 0);
      v20 = v54;
      if ( (_QWORD)v54 )
      {
        operator delete((void *)v54);
        v54 = 0;
        v55 = 0;
      }
      if ( v25 )
        operator delete(v25);
      v19 = v39;
      if ( v23 )
LABEL_48:
        operator delete(v23);
    }
  }
  AslLogCallPrintf(
    3,
    (unsigned int)"IdsEnableEtwExtension::AddSettings",
    64,
    (unsigned int)"IdsEnableEtwExtension::AddSettings: missing or invalid /enableetw configuration\n");
  if ( v6 )
  {
LABEL_63:
    if ( v6 )
      operator delete(v6);
  }
  return 0;
}

```

## disassembly

```asm
0x1800dcde0  mov     [rsp-8+arg_10], rbx
0x1800dcde5  push    rbp
0x1800dcde6  push    rsi
0x1800dcde7  push    rdi
0x1800dcde8  push    r12
0x1800dcdea  push    r13
0x1800dcdec  push    r14
0x1800dcdee  push    r15
0x1800dcdf0  lea     rbp, [rsp-40h]
0x1800dcdf5  sub     rsp, 140h
0x1800dcdfc  mov     rax, cs:__security_cookie
0x1800dce03  xor     rax, rsp
0x1800dce06  mov     [rbp+70h+var_40], rax
0x1800dce0a  mov     r15, rdx
0x1800dce0d  mov     [rbp+70h+var_D0], rdx
0x1800dce11  mov     r14, rcx
0x1800dce14  mov     [rsp+170h+var_100], rcx
0x1800dce19  test    rdx, rdx
0x1800dce1c  jnz     short loc_1800DCE42
0x1800dce1e  lea     r9, aIdsenableetwex_8; "IdsEnableEtwExtension::AddSettings fail"...
0x1800dce25  lea     r8d, [rdx+39h]
0x1800dce29  lea     rdx, aIdsenableetwex; "IdsEnableEtwExtension::AddSettings"
0x1800dce30  lea     ecx, [r15+3]
0x1800dce34  call    AslLogCallPrintf
0x1800dce39  lea     eax, [r15+57h]
0x1800dce3d  jmp     loc_1800DD3E0
0x1800dce42  lea     rdx, aEnableetw; "/enableetw"
0x1800dce49  lea     rcx, [rbp+70h+lpsz]
0x1800dce4d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x1800dce52  nop
0x1800dce53  lea     r9, [rbp+70h+lpsz]
0x1800dce57  xor     r8d, r8d
0x1800dce5a  lea     rdx, [rsp+170h+var_118]
0x1800dce5f  mov     rcx, r15
0x1800dce62  call    ?QueryEntry@Settings@@QEAA?AV?$unique_ptr@VSettingEntry@@U?$default_delete@VSettingEntry@@@std@@@std@@PEBVSettingEntry@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@@Z; Settings::QueryEntry(SettingEntry const *,std::wstring const &)
0x1800dce67  nop
0x1800dce68  xor     r8d, r8d
0x1800dce6b  mov     dl, 1
0x1800dce6d  lea     rcx, [rbp+70h+lpsz]
0x1800dce71  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800dce76  mov     rbx, [rsp+170h+var_118]
0x1800dce7b  test    rbx, rbx
0x1800dce7e  jz      loc_1800DD3AD
0x1800dce84  mov     rcx, rbx; this
0x1800dce87  call    ?IsObject@SettingEntry@@QEBA_NXZ; SettingEntry::IsObject(void)
0x1800dce8c  test    al, al
0x1800dce8e  jz      loc_1800DD3AD
0x1800dce94  lea     rdx, aEnabled; "/enabled"
0x1800dce9b  lea     rcx, [rbp+70h+var_A8]
0x1800dce9f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x1800dcea4  nop
0x1800dcea5  lea     r9, [rbp+70h+var_A8]
0x1800dcea9  mov     r8, rbx
0x1800dceac  lea     rdx, [rsp+170h+var_110]
0x1800dceb1  mov     rcx, r15
0x1800dceb4  call    ?QueryEntry@Settings@@QEAA?AV?$unique_ptr@VSettingEntry@@U?$default_delete@VSettingEntry@@@std@@@std@@PEBVSettingEntry@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@@Z; Settings::QueryEntry(SettingEntry const *,std::wstring const &)
0x1800dceb9  nop
0x1800dceba  xor     r8d, r8d
0x1800dcebd  mov     dl, 1
0x1800dcebf  lea     rcx, [rbp+70h+var_A8]
0x1800dcec3  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800dcec8  mov     rdi, [rsp+170h+var_110]
0x1800dcecd  test    rdi, rdi
0x1800dced0  jz      loc_1800DD39B
0x1800dced6  mov     rcx, rdi; this
0x1800dced9  call    ?IsBool@SettingEntry@@QEBA_NXZ; SettingEntry::IsBool(void)
0x1800dcede  test    al, al
0x1800dcee0  jz      loc_1800DD39B
0x1800dcee6  call    ?GetBool@SettingEntry@@QEBA_NXZ; SettingEntry::GetBool(void)
0x1800dceeb  mov     [r14+11h], al
0x1800dceef  test    al, al
0x1800dcef1  jnz     short loc_1800DCF26
0x1800dcef3  lea     r9, aIdsenableetwex_1; "IdsEnableEtwExtension::AddSettings: ext"...
0x1800dcefa  mov     r8d, 4Fh ; 'O'
0x1800dcf00  lea     rdx, aIdsenableetwex; "IdsEnableEtwExtension::AddSettings"
0x1800dcf07  mov     ecx, 3
0x1800dcf0c  call    AslLogCallPrintf
0x1800dcf11  nop
0x1800dcf12  test    rdi, rdi
0x1800dcf15  jz      short loc_1800DCF21
0x1800dcf17  mov     rcx, rdi
0x1800dcf1a  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800dcf20  nop
0x1800dcf21  jmp     loc_1800DD3D0
0x1800dcf26  lea     rdx, aLogfilesize; "/logfilesize"
0x1800dcf2d  lea     rcx, [rbp+70h+lpsz]
0x1800dcf31  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x1800dcf36  nop
0x1800dcf37  lea     r9, [rbp+70h+lpsz]
0x1800dcf3b  mov     r8, rbx
0x1800dcf3e  lea     rdx, [rsp+170h+var_108]
0x1800dcf43  mov     rcx, r15
0x1800dcf46  call    ?QueryEntry@Settings@@QEAA?AV?$unique_ptr@VSettingEntry@@U?$default_delete@VSettingEntry@@@std@@@std@@PEBVSettingEntry@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@@Z; Settings::QueryEntry(SettingEntry const *,std::wstring const &)
0x1800dcf4b  nop
0x1800dcf4c  xor     r8d, r8d
0x1800dcf4f  mov     dl, 1
0x1800dcf51  lea     rcx, [rbp+70h+lpsz]
0x1800dcf55  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800dcf5a  mov     rsi, [rsp+170h+var_108]
0x1800dcf5f  test    rsi, rsi
0x1800dcf62  jz      short loc_1800DCF9A
0x1800dcf64  mov     rcx, rsi; this
0x1800dcf67  call    ?IsInteger@SettingEntry@@QEBA_NXZ; SettingEntry::IsInteger(void)
0x1800dcf6c  test    al, al
0x1800dcf6e  jz      short loc_1800DCF9A
0x1800dcf70  call    ?GetInteger@SettingEntry@@QEBAHXZ; SettingEntry::GetInteger(void)
0x1800dcf75  mov     [r14+14h], eax
0x1800dcf79  mov     dword ptr [rsp+170h+var_150], eax
0x1800dcf7d  lea     r9, aIdsenableetwex_14; "IdsEnableEtwExtension::AddSettings: log"...
0x1800dcf84  mov     r8d, 58h ; 'X'
0x1800dcf8a  lea     rdx, aIdsenableetwex; "IdsEnableEtwExtension::AddSettings"
0x1800dcf91  lea     ecx, [r8-55h]
0x1800dcf95  call    AslLogCallPrintf
0x1800dcf9a  lea     rdx, aAlsorealtime; "/alsorealtime"
0x1800dcfa1  lea     rcx, [rbp+70h+var_A8]
0x1800dcfa5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x1800dcfaa  nop
0x1800dcfab  lea     r9, [rbp+70h+var_A8]
0x1800dcfaf  mov     r8, rbx
0x1800dcfb2  lea     rdx, [rsp+170h+var_F8]
0x1800dcfb7  mov     rcx, r15
0x1800dcfba  call    ?QueryEntry@Settings@@QEAA?AV?$unique_ptr@VSettingEntry@@U?$default_delete@VSettingEntry@@@std@@@std@@PEBVSettingEntry@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@@Z; Settings::QueryEntry(SettingEntry const *,std::wstring const &)
0x1800dcfbf  nop
0x1800dcfc0  xor     r8d, r8d
0x1800dcfc3  mov     dl, 1
0x1800dcfc5  lea     rcx, [rbp+70h+var_A8]
0x1800dcfc9  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800dcfce  mov     r13, [rsp+170h+var_F8]
0x1800dcfd3  test    r13, r13
0x1800dcfd6  jz      short loc_1800DCFED
0x1800dcfd8  mov     rcx, r13; this
0x1800dcfdb  call    ?IsBool@SettingEntry@@QEBA_NXZ; SettingEntry::IsBool(void)
0x1800dcfe0  test    al, al
0x1800dcfe2  jz      short loc_1800DCFED
0x1800dcfe4  call    ?GetBool@SettingEntry@@QEBA_NXZ; SettingEntry::GetBool(void)
0x1800dcfe9  mov     [r14+18h], al
0x1800dcfed  lea     rdx, aProviders; "/providers"
0x1800dcff4  lea     rcx, [rbp+70h+var_60]
0x1800dcff8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x1800dcffd  nop
0x1800dcffe  lea     r9, [rbp+70h+var_60]
0x1800dd002  mov     r8, rbx
0x1800dd005  lea     rdx, [rsp+170h+var_120]
0x1800dd00a  mov     rcx, r15
0x1800dd00d  call    ?QueryEntry@Settings@@QEAA?AV?$unique_ptr@VSettingEntry@@U?$default_delete@VSettingEntry@@@std@@@std@@PEBVSettingEntry@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@@Z; Settings::QueryEntry(SettingEntry const *,std::wstring const &)
0x1800dd012  nop
0x1800dd013  xor     r8d, r8d
0x1800dd016  mov     dl, 1
0x1800dd018  lea     rcx, [rbp+70h+var_60]
0x1800dd01c  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800dd021  mov     r12, [rsp+170h+var_120]
0x1800dd026  test    r12, r12
0x1800dd029  jz      loc_1800DD328
0x1800dd02f  mov     rcx, r12; this
0x1800dd032  call    ?IsArray@SettingEntry@@QEBA_NXZ; SettingEntry::IsArray(void)
0x1800dd037  test    al, al
0x1800dd039  jz      loc_1800DD328
0x1800dd03f  xor     edi, edi
0x1800dd041  mov     [rsp+170h+var_128], rdi
0x1800dd046  mov     rbx, [rsp+170h+var_100]
0x1800dd04b  mov     r9, rdi
0x1800dd04e  mov     r8, r12
0x1800dd051  lea     rdx, [rbp+70h+var_F0]
0x1800dd055  call    ?QueryArrayEntry@Settings@@QEAA?AV?$unique_ptr@VSettingEntry@@U?$default_delete@VSettingEntry@@@std@@@std@@PEBVSettingEntry@@_K@Z; Settings::QueryArrayEntry(SettingEntry const *,unsigned __int64)
0x1800dd05a  nop
0x1800dd05b  mov     r14, [rbp+70h+var_F0]
0x1800dd05f  test    r14, r14
0x1800dd062  jz      loc_1800DD314
0x1800dd068  lea     rdx, aGuid; "/guid"
0x1800dd06f  lea     rcx, [rbp+70h+var_A8]
0x1800dd073  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x1800dd078  nop
0x1800dd079  lea     r9, [rbp+70h+var_A8]
0x1800dd07d  mov     r8, r14
0x1800dd080  lea     rdx, [rbp+70h+var_E8]
0x1800dd084  mov     rcx, r15
0x1800dd087  call    ?QueryEntry@Settings@@QEAA?AV?$unique_ptr@VSettingEntry@@U?$default_delete@VSettingEntry@@@std@@@std@@PEBVSettingEntry@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@@Z; Settings::QueryEntry(SettingEntry const *,std::wstring const &)
0x1800dd08c  nop
0x1800dd08d  xor     r8d, r8d
0x1800dd090  mov     dl, 1
0x1800dd092  lea     rcx, [rbp+70h+var_A8]
0x1800dd096  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800dd09b  mov     rsi, [rbp+70h+var_E8]
0x1800dd09f  test    rsi, rsi
0x1800dd0a2  jz      loc_1800DD2BF
0x1800dd0a8  mov     rcx, rsi; this
0x1800dd0ab  call    ?IsString@SettingEntry@@QEBA_NXZ; SettingEntry::IsString(void)
0x1800dd0b0  test    al, al
0x1800dd0b2  jz      loc_1800DD2BF
0x1800dd0b8  xorps   xmm0, xmm0
0x1800dd0bb  movups  xmmword ptr [rbp+70h+pclsid.Data1], xmm0
0x1800dd0bf  xorps   xmm1, xmm1
0x1800dd0c2  movdqu  [rbp+70h+var_78], xmm1
0x1800dd0c7  mov     [rbp+70h+var_68], 0
0x1800dd0cf  lea     rdx, [rbp+70h+lpsz]
0x1800dd0d3  mov     rcx, rsi
0x1800dd0d6  call    ?GetString@SettingEntry@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; SettingEntry::GetString(void)
0x1800dd0db  nop
0x1800dd0dc  lea     rcx, [rbp+70h+lpsz]
0x1800dd0e0  cmp     [rbp+70h+var_B0], 8
0x1800dd0e5  cmovnb  rcx, [rbp+70h+lpsz]; lpsz
0x1800dd0ea  lea     rdx, [rbp+70h+pclsid]; pclsid
0x1800dd0ee  call    cs:__imp_CLSIDFromString
0x1800dd0f4  test    eax, eax
0x1800dd0f6  jns     short loc_1800DD16C
0x1800dd0f8  lea     rcx, [rbp+70h+lpsz]
0x1800dd0fc  cmp     [rbp+70h+var_B0], 8
0x1800dd101  cmovnb  rcx, [rbp+70h+lpsz]
0x1800dd106  mov     [rsp+170h+var_140], eax
0x1800dd10a  mov     [rsp+170h+var_148], rdi
0x1800dd10f  mov     [rsp+170h+var_150], rcx
0x1800dd114  lea     r9, aIdsenableetwex_0; "IdsEnableEtwExtension::AddSettings: inv"...
0x1800dd11b  mov     r8d, 7Dh ; '}'
0x1800dd121  lea     rdx, aIdsenableetwex; "IdsEnableEtwExtension::AddSettings"
0x1800dd128  lea     ecx, [r8-7Ch]
0x1800dd12c  call    AslLogCallPrintf
0x1800dd131  inc     rdi
0x1800dd134  mov     [rsp+170h+var_128], rdi
0x1800dd139  xor     r8d, r8d
0x1800dd13c  mov     dl, 1
0x1800dd13e  lea     rcx, [rbp+70h+lpsz]
0x1800dd142  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800dd147  nop
0x1800dd148  mov     rcx, qword ptr [rbp+70h+var_78]
0x1800dd14c  test    rcx, rcx
0x1800dd14f  jz      short loc_1800DD167
0x1800dd151  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800dd157  xorps   xmm0, xmm0
0x1800dd15a  movdqu  [rbp+70h+var_78], xmm0
0x1800dd15f  mov     [rbp+70h+var_68], 0
0x1800dd167  jmp     loc_1800DD2EE
0x1800dd16c  lea     rdx, aEventids_0; "/eventids"
0x1800dd173  lea     rcx, [rbp+70h+var_A8]
0x1800dd177  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x1800dd17c  nop
0x1800dd17d  lea     r9, [rbp+70h+var_A8]
0x1800dd181  mov     r8, r14
0x1800dd184  lea     rdx, [rbp+70h+var_E0]
0x1800dd188  mov     rcx, r15
0x1800dd18b  call    ?QueryEntry@Settings@@QEAA?AV?$unique_ptr@VSettingEntry@@U?$default_delete@VSettingEntry@@@std@@@std@@PEBVSettingEntry@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@@Z; Settings::QueryEntry(SettingEntry const *,std::wstring const &)
0x1800dd190  nop
0x1800dd191  xor     r8d, r8d
0x1800dd194  mov     dl, 1
0x1800dd196  lea     rcx, [rbp+70h+var_A8]
0x1800dd19a  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800dd19f  mov     r12, [rbp+70h+var_E0]
0x1800dd1a3  test    r12, r12
0x1800dd1a6  jz      short loc_1800DD20F
0x1800dd1a8  mov     rcx, r12; this
0x1800dd1ab  call    ?IsArray@SettingEntry@@QEBA_NXZ; SettingEntry::IsArray(void)
0x1800dd1b0  test    al, al
0x1800dd1b2  jz      short loc_1800DD20F
0x1800dd1b4  xor     edi, edi
0x1800dd1b6  mov     r9, rdi
0x1800dd1b9  mov     r8, r12
0x1800dd1bc  lea     rdx, [rbp+70h+var_D8]
0x1800dd1c0  call    ?QueryArrayEntry@Settings@@QEAA?AV?$unique_ptr@VSettingEntry@@U?$default_delete@VSettingEntry@@@std@@@std@@PEBVSettingEntry@@_K@Z; Settings::QueryArrayEntry(SettingEntry const *,unsigned __int64)
0x1800dd1c5  nop
0x1800dd1c6  mov     r15, [rbp+70h+var_D8]
0x1800dd1ca  test    r15, r15
0x1800dd1cd  jz      short loc_1800DD206
0x1800dd1cf  mov     rcx, r15; this
0x1800dd1d2  call    ?IsInteger@SettingEntry@@QEBA_NXZ; SettingEntry::IsInteger(void)
0x1800dd1d7  test    al, al
0x1800dd1d9  jz      short loc_1800DD1F3
0x1800dd1db  call    ?GetInteger@SettingEntry@@QEBAHXZ; SettingEntry::GetInteger(void)
0x1800dd1e0  mov     [rsp+170h+var_130], ax
0x1800dd1e5  lea     rdx, [rsp+170h+var_130]
0x1800dd1ea  lea     rcx, [rbp+70h+var_78]
0x1800dd1ee  call    ?push_back@?$vector@GV?$allocator@G@std@@@std@@QEAAX$$QEAG@Z; std::vector<ushort>::push_back(ushort &&)
0x1800dd1f3  inc     rdi
0x1800dd1f6  test    r15, r15
0x1800dd1f9  jz      short loc_1800DD1B6
0x1800dd1fb  mov     rcx, r15
0x1800dd1fe  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800dd204  jmp     short loc_1800DD1B6
0x1800dd206  mov     r15, [rbp+70h+var_D0]
0x1800dd20a  mov     rdi, [rsp+170h+var_128]
0x1800dd20f  mov     rax, qword ptr [rbp+70h+var_78+8]
0x1800dd213  sub     rax, qword ptr [rbp+70h+var_78]
0x1800dd217  sar     rax, 1
0x1800dd21a  mov     [rsp+170h+var_148], rax
0x1800dd21f  mov     [rsp+170h+var_150], rdi
0x1800dd224  lea     r9, aIdsenableetwex_11; "IdsEnableEtwExtension::AddSettings: pro"...
0x1800dd22b  mov     r8d, 97h
0x1800dd231  lea     rdx, aIdsenableetwex; "IdsEnableEtwExtension::AddSettings"
0x1800dd238  mov     ecx, 3
0x1800dd23d  call    AslLogCallPrintf
0x1800dd242  lea     rcx, [rbx+20h]
0x1800dd246  lea     rdx, [rbp+70h+pclsid]
0x1800dd24a  call    ?push_back@?$vector@UIdsEtwProviderEntry@@V?$allocator@UIdsEtwProviderEntry@@@std@@@std@@QEAAX$$QEAUIdsEtwProviderEntry@@@Z; std::vector<IdsEtwProviderEntry>::push_back(IdsEtwProviderEntry &&)
0x1800dd24f  inc     rdi
0x1800dd252  mov     [rsp+170h+var_128], rdi
0x1800dd257  test    r12, r12
0x1800dd25a  jz      short loc_1800DD266
0x1800dd25c  mov     rcx, r12
0x1800dd25f  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800dd265  nop
0x1800dd266  xor     r8d, r8d
0x1800dd269  mov     dl, 1
  ... truncated ...
```
