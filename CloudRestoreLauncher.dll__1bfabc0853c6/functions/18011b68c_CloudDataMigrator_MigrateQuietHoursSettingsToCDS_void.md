# CloudDataMigrator::MigrateQuietHoursSettingsToCDS(void)

- ea: `0x18011b68c`
- end: `0x18011bbac`
- name: `?MigrateQuietHoursSettingsToCDS@CloudDataMigrator@@AEAAXXZ`
- size: `1312`
- prototype: `void __fastcall(CloudDataMigrator *__hidden this)`
- caller_count: `1`
- callee_count: `24`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18011ad80`

## callees

- `0x18000c6e0`
- `0x18000cbbc`
- `0x18000d688`
- `0x180014468`
- `0x18001cf84`
- `0x18001d0a8`
- `0x18001faa8`
- `0x18002498c`
- `0x18002a50c`
- `0x180031774`
- `0x180031dc0`
- `0x180035c0c`
- `0x180036a3c`
- `0x18005caac`
- `0x1800653e0`
- `0x18007264c`
- `0x1800821ac`
- `0x1801175bc`
- `0x180117bcc`
- `0x180117fd0`
- `0x180118e0c`
- `0x18011a0d0`
- `0x18011a1dc`
- `0x18011b68c`

## import_xrefs

- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18011b896`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x18011b896`
- `ADVAPI32!RegGetValueW` at `0x18011ba96`
- `ADVAPI32!RegGetValueW` at `0x18011ba96`
- `ADVAPI32!RegEnumKeyExW` at `0x18011b80d`
- `ADVAPI32!RegEnumKeyExW` at `0x18011b80d`
- `ADVAPI32!RegOpenKeyExW` at `0x18011b7b7`
- `ADVAPI32!RegOpenKeyExW` at `0x18011b7b7`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
void __fastcall CloudDataMigrator::MigrateQuietHoursSettingsToCDS(CloudDataMigrator *this)
{
  int v1; // r9d
  _QWORD *v2; // rax
  unsigned int v3; // eax
  DWORD v4; // ebx
  __int64 v5; // rdx
  char v6; // di
  __int64 v7; // rdx
  _QWORD *v8; // rax
  char v9; // bl
  char v10; // cl
  __int64 v11; // rax
  __int64 v12; // rax
  LSTATUS ValueW; // eax
  bool v14; // sf
  __int64 v15; // r8
  int v16; // r9d
  const char *v17; // r9
  unsigned int phkResult; // [rsp+20h] [rbp-3A8h]
  int lpClass; // [rsp+28h] [rbp-3A0h]
  int v20; // [rsp+40h] [rbp-388h] BYREF
  DWORD cchName; // [rsp+48h] [rbp-380h] BYREF
  HKEY hKey[2]; // [rsp+50h] [rbp-378h] BYREF
  int v23; // [rsp+60h] [rbp-368h] BYREF
  _QWORD *v24; // [rsp+68h] [rbp-360h]
  __int64 v25; // [rsp+70h] [rbp-358h]
  __int64 v26; // [rsp+78h] [rbp-350h] BYREF
  __int128 v27; // [rsp+80h] [rbp-348h]
  __int64 v28; // [rsp+90h] [rbp-338h]
  __int64 v29; // [rsp+98h] [rbp-330h]
  _BYTE v30[40]; // [rsp+A0h] [rbp-328h] BYREF
  void *v31[3]; // [rsp+C8h] [rbp-300h] BYREF
  unsigned __int64 v32; // [rsp+E0h] [rbp-2E8h]
  char v33[8]; // [rsp+F0h] [rbp-2D8h] BYREF
  _BYTE v34[16]; // [rsp+F8h] [rbp-2D0h] BYREF
  __int64 v35; // [rsp+108h] [rbp-2C0h]
  char v36; // [rsp+118h] [rbp-2B0h]
  int v37; // [rsp+11Ch] [rbp-2ACh]
  void *v38[3]; // [rsp+140h] [rbp-288h] BYREF
  unsigned __int64 v39; // [rsp+158h] [rbp-270h]
  char v40[8]; // [rsp+160h] [rbp-268h] BYREF
  _BYTE v41[16]; // [rsp+168h] [rbp-260h] BYREF
  __int64 v42; // [rsp+178h] [rbp-250h]
  char v43; // [rsp+188h] [rbp-240h]
  int v44; // [rsp+18Ch] [rbp-23Ch]
  WCHAR Name[256]; // [rsp+1B0h] [rbp-218h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3C8h] [rbp+0h]

  cchName = 0;
  try
  {
    wil::cloud_store::cloud_store(v30);
    std::string::string(v38, &dword_18013829C);
    wil::cloud_store::load_internal<Windows::Data::DoNotDisturb::QuietHoursSettings>(
      (unsigned int)v30,
      (unsigned int)v33,
      7,
      v1,
      (__int64)v38);
    if ( v39 > 0xF )
      std::_Deallocate<16>(v38[0], (struct std::nothrow_t *)(v39 + 1));
    v25 = 0;
    v2 = operator new(0x30u);
    *v2 = v2;
    v2[1] = v2;
    v24 = v2;
    v26 = 0;
    v27 = 0;
    v28 = 7;
    v29 = 8;
    v23 = 1065353216;
    std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::_Assign_grow(
      &v26,
      16,
      v2);
    hKey[0] = 0;
    v3 = RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"Software\\Microsoft\\Windows\\CurrentVersion\\Notifications\\QuietHours\\Profiles",
           0,
           0x20019u,
           hKey);
    if ( v3 )
    {
      v5 = 182;
    }
    else
    {
      v4 = 0;
      memset_0(Name, 0, sizeof(Name));
      while ( 1 )
      {
        cchName = 256;
        v3 = RegEnumKeyExW(hKey[0], v4, Name, &cchName, 0, 0, 0, 0);
        if ( v3 )
          break;
        std::wstring::wstring(v31, Name);
        std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::emplace<std::wstring>(
          &v23,
          v38,
          v31);
        std::wstring::_Tidy_deallocate(v31);
        ++v4;
      }
      if ( v3 == 259 )
      {
LABEL_12:
        v6 = 2;
        v20 = 0;
        RtlGetDeviceFamilyInfoEnum(0, &v20, 0);
        if ( v20 == 10
          && v33[0]
          && (v7 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v34),
              std::wstring::wstring(v31, v7),
              v6 = 3,
              v8 = (_QWORD *)std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::find(
                               &v23,
                               &cchName,
                               v31),
              (_QWORD *)*v8 == v24) )
        {
          v9 = 1;
        }
        else
        {
          v9 = 0;
          if ( (v6 & 1) == 0 )
            goto LABEL_20;
        }
        std::wstring::_Tidy_deallocate(v31);
        v10 = v33[0];
        if ( v9 )
          v10 = 0;
        v33[0] = v10;
LABEL_20:
        if ( v20 == 3 )
        {
          if ( !v33[0] )
            goto LABEL_25;
          v11 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v34);
          if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(
                                  v11,
                                  v35,
                                  L"Microsoft.QuietHoursProfile.AlarmsOnly",
                                  38) )
            std::wstring::_Assign<unsigned short>(v34, L"Microsoft.QuietHoursProfile.PriorityOnly", 40);
        }
        if ( v33[0] )
        {
LABEL_39:
          std::string::string(v31, &dword_18013829C);
          wil::cloud_store::save_internal<Windows::Data::DoNotDisturb::QuietHoursSettings>(
            (unsigned int)v30,
            (unsigned int)v38,
            (unsigned int)v33,
            v16,
            phkResult,
            lpClass,
            (__int64)v31);
          if ( v32 > 0xF )
            std::_Deallocate<16>(v31[0], (struct std::nothrow_t *)(v32 + 1));
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(hKey);
          std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(&v23);
          wil::cloud_store_data<Windows::Data::DoNotDisturb::QuietHoursSettings>::~cloud_store_data<Windows::Data::DoNotDisturb::QuietHoursSettings>(v33);
          wil::cloud_store::~cloud_store((wil::cloud_store *)v30);
          return;
        }
LABEL_25:
        wil::cloud_store::load<Windows::Data::Notifications::QuietHoursSettings>(v30, v40, 5);
        if ( v40[0] )
        {
          if ( v20 == 3 )
          {
            v12 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v41);
            if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(
                                    v12,
                                    v42,
                                    L"Microsoft.QuietHoursProfile.AlarmsOnly",
                                    38) )
              std::wstring::_Assign<unsigned short>(v41, L"Microsoft.QuietHoursProfile.PriorityOnly", 40);
          }
          std::wstring::operator=(v34, v41);
          v36 = v43;
          v37 = v44;
          v33[0] = v40[0];
        }
        else
        {
          memset_0(Name, 0, sizeof(Name));
          cchName = 512;
          ValueW = RegGetValueW(
                     HKEY_LOCAL_MACHINE,
                     L"Software\\Microsoft\\Windows\\CurrentVersion\\Notifications\\QuietHours\\Profiles",
                     L"DefaultProfile",
                     2u,
                     0,
                     Name,
                     &cchName);
          v14 = ValueW < 0;
          if ( ValueW )
          {
            Name[0] = 0;
            if ( ValueW > 0 )
              v14 = 1;
          }
          if ( !v14 )
          {
            v15 = -1;
            do
              ++v15;
            while ( Name[v15] );
            std::wstring::_Assign<unsigned short>(v34, Name, v15);
          }
          v33[0] = 1;
        }
        wil::cloud_store_data<Windows::Data::DoNotDisturb::QuietHoursSettings>::~cloud_store_data<Windows::Data::DoNotDisturb::QuietHoursSettings>(v40);
        goto LABEL_39;
      }
      v5 = 175;
    }
    wil::details::in1diag3::_Log_Win32(
      retaddr,
      (void *)v5,
      (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\clouddatamigrator\\lib\\clouddatamigrator.cpp",
      (const char *)v3,
      phkResult);
    goto LABEL_12;
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0xEB,
      (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\clouddatamigrator\\lib\\clouddatamigrator.cpp",
      v17);
  }
}

```

## disassembly

```asm
0x18011b68c  mov     [rsp+arg_0], rbx
0x18011b691  mov     [rsp+arg_8], rsi
0x18011b696  push    rdi
0x18011b697  sub     rsp, 3C0h
0x18011b69e  mov     rax, cs:__security_cookie
0x18011b6a5  xor     rax, rsp
0x18011b6a8  mov     [rsp+3C8h+var_18], rax
0x18011b6b0  xor     esi, esi
0x18011b6b2  mov     [rsp+3C8h+cchName], esi
0x18011b6b6  mov     dword ptr [rsp+3C8h+lpcchClass], 7530h
0x18011b6be  lea     rcx, [rsp+3C8h+var_328]
0x18011b6c6  call    ??0cloud_store@wil@@QEAA@W4PartitionKind@Cloud@Storage@Internal@Windows@@PEBG1W4CloudStoreOptions@3456@II@Z; wil::cloud_store::cloud_store(Windows::Internal::Storage::Cloud::PartitionKind,ushort const *,ushort const *,Windows::Internal::Storage::Cloud::CloudStoreOptions,uint,uint)
0x18011b6cb  nop
0x18011b6cc  lea     rdx, dword_18013829C
0x18011b6d3  lea     rcx, [rsp+3C8h+var_288]
0x18011b6db  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18011b6e0  nop
0x18011b6e1  lea     rax, [rsp+3C8h+var_288]
0x18011b6e9  mov     [rsp+3C8h+phkResult], rax
0x18011b6ee  lea     ebx, [rsi+7]
0x18011b6f1  mov     r8d, ebx
0x18011b6f4  lea     rdx, [rsp+3C8h+var_2D8]
0x18011b6fc  lea     rcx, [rsp+3C8h+var_328]
0x18011b704  call    ??$load_internal@UQuietHoursSettings@DoNotDisturb@Data@Windows@@@cloud_store@wil@@AEAA?AV?$cloud_store_data@UQuietHoursSettings@DoNotDisturb@Data@Windows@@@1@W4cloud_store_load_options@1@PEBU?$ItemReference@UQuietHoursSettings@DoNotDisturb@Data@Windows@@@Platform@Data@Windows@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; wil::cloud_store::load_internal<Windows::Data::DoNotDisturb::QuietHoursSettings>(wil::cloud_store_load_options,Windows::Data::Platform::ItemReference<Windows::Data::DoNotDisturb::QuietHoursSettings> const *,std::string const &)
0x18011b709  nop
0x18011b70a  mov     rdx, [rsp+3C8h+var_270]
0x18011b712  cmp     rdx, 0Fh
0x18011b716  jbe     short loc_18011B729
0x18011b718  inc     rdx
0x18011b71b  mov     rcx, [rsp+3C8h+var_288]
0x18011b723  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18011b728  nop
0x18011b729  mov     [rsp+3C8h+var_368], 0
0x18011b731  mov     [rsp+3C8h+var_360], rsi
0x18011b736  mov     [rsp+3C8h+var_358], rsi
0x18011b73b  mov     ecx, 30h ; '0'; Size
0x18011b740  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18011b745  mov     [rax], rax
0x18011b748  mov     [rax+8], rax
0x18011b74c  mov     [rsp+3C8h+var_360], rax
0x18011b751  mov     [rsp+3C8h+var_350], rsi
0x18011b756  xorps   xmm0, xmm0
0x18011b759  movdqa  [rsp+3C8h+var_348], xmm0
0x18011b762  mov     [rsp+3C8h+var_338], rbx
0x18011b76a  mov     [rsp+3C8h+var_330], 8
0x18011b776  mov     [rsp+3C8h+var_368], 3F800000h
0x18011b77e  mov     r8, rax
0x18011b781  mov     edx, 10h
0x18011b786  lea     rcx, [rsp+3C8h+var_350]
0x18011b78b  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>)
0x18011b790  nop
0x18011b791  mov     [rsp+3C8h+hKey], rsi
0x18011b796  lea     rax, [rsp+3C8h+hKey]
0x18011b79b  mov     [rsp+3C8h+phkResult], rax; unsigned int
0x18011b7a0  mov     r9d, 20019h; samDesired
0x18011b7a6  xor     r8d, r8d; ulOptions
0x18011b7a9  lea     rdx, aSoftwareMicros_20; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18011b7b0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18011b7b7  call    cs:__imp_RegOpenKeyExW
0x18011b7bd  test    eax, eax
0x18011b7bf  jnz     loc_18011B867
0x18011b7c5  mov     ebx, esi
0x18011b7c7  xor     edx, edx; Val
0x18011b7c9  mov     r8d, 200h; Size
0x18011b7cf  lea     rcx, [rsp+3C8h+Name]; void *
0x18011b7d7  call    memset_0
0x18011b7dc  mov     edi, 100h
0x18011b7e1  mov     [rsp+3C8h+cchName], edi
0x18011b7e5  mov     [rsp+3C8h+lpftLastWriteTime], rsi; lpftLastWriteTime
0x18011b7ea  mov     [rsp+3C8h+lpcchClass], rsi; lpcchClass
0x18011b7ef  mov     [rsp+3C8h+lpClass], rsi; lpClass
0x18011b7f4  mov     [rsp+3C8h+phkResult], rsi; lpReserved
0x18011b7f9  lea     r9, [rsp+3C8h+cchName]; lpcchName
0x18011b7fe  lea     r8, [rsp+3C8h+Name]; lpName
0x18011b806  mov     edx, ebx; dwIndex
0x18011b808  mov     rcx, [rsp+3C8h+hKey]; hKey
0x18011b80d  call    cs:__imp_RegEnumKeyExW
0x18011b813  test    eax, eax
0x18011b815  jnz     short loc_18011B859
0x18011b817  lea     rdx, [rsp+3C8h+Name]
0x18011b81f  lea     rcx, [rsp+3C8h+var_300]
0x18011b827  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18011b82c  nop
0x18011b82d  lea     r8, [rsp+3C8h+var_300]
0x18011b835  lea     rdx, [rsp+3C8h+var_288]
0x18011b83d  lea     rcx, [rsp+3C8h+var_368]
0x18011b842  call    ??$emplace@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::emplace<std::wstring>(std::wstring &&)
0x18011b847  nop
0x18011b848  lea     rcx, [rsp+3C8h+var_300]
0x18011b850  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18011b855  inc     ebx
0x18011b857  jmp     short loc_18011B7E1
0x18011b859  cmp     eax, 103h
0x18011b85e  jz      short loc_18011B883
0x18011b860  mov     edx, 0AFh
0x18011b865  jmp     short loc_18011B86C
0x18011b867  mov     edx, 0B6h; void *
0x18011b86c  mov     r9d, eax; char *
0x18011b86f  lea     r8, aPcshellShellCl_4; "pcshell\\shell\\cloudrestorelauncher\\c"...
0x18011b876  mov     rcx, [rsp+3C8h]; this
0x18011b87e  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x18011b883  mov     edi, 2
0x18011b888  mov     [rsp+3C8h+var_388], esi
0x18011b88c  xor     r8d, r8d
0x18011b88f  lea     rdx, [rsp+3C8h+var_388]
0x18011b894  xor     ecx, ecx
0x18011b896  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x18011b89c  cmp     [rsp+3C8h+var_388], 0Ah
0x18011b8a1  jnz     short loc_18011B8F4
0x18011b8a3  cmp     [rsp+3C8h+var_2D8], sil
0x18011b8ab  jz      short loc_18011B8F4
0x18011b8ad  lea     rcx, [rsp+3C8h+var_2D0]
0x18011b8b5  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18011b8ba  mov     rdx, rax
0x18011b8bd  lea     rcx, [rsp+3C8h+var_300]
0x18011b8c5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18011b8ca  mov     edi, 3
0x18011b8cf  lea     r8, [rsp+3C8h+var_300]
0x18011b8d7  lea     rdx, [rsp+3C8h+cchName]
0x18011b8dc  lea     rcx, [rsp+3C8h+var_368]
0x18011b8e1  call    ?find@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::find(std::wstring const &)
0x18011b8e6  mov     rcx, [rsp+3C8h+var_360]
0x18011b8eb  cmp     [rax], rcx
0x18011b8ee  jnz     short loc_18011B8F4
0x18011b8f0  mov     bl, 1
0x18011b8f2  jmp     short loc_18011B8FD
0x18011b8f4  mov     bl, sil
0x18011b8f7  test    dil, 1
0x18011b8fb  jz      short loc_18011B91E
0x18011b8fd  lea     rcx, [rsp+3C8h+var_300]
0x18011b905  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18011b90a  movzx   ecx, [rsp+3C8h+var_2D8]
0x18011b912  test    bl, bl
0x18011b914  cmovnz  ecx, esi
0x18011b917  mov     [rsp+3C8h+var_2D8], cl
0x18011b91e  cmp     [rsp+3C8h+var_388], 3
0x18011b923  jnz     short loc_18011B977
0x18011b925  cmp     [rsp+3C8h+var_2D8], sil
0x18011b92d  jz      short loc_18011B985
0x18011b92f  lea     rcx, [rsp+3C8h+var_2D0]
0x18011b937  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18011b93c  mov     rcx, rax
0x18011b93f  mov     r9d, 26h ; '&'
0x18011b945  lea     r8, aMicrosoftQuiet; "Microsoft.QuietHoursProfile.AlarmsOnly"
0x18011b94c  mov     rdx, [rsp+3C8h+var_2C0]
0x18011b954  call    ??$_Traits_equal@U?$char_traits@G@std@@@std@@YA_NQEBG_K01@Z; std::_Traits_equal<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x18011b959  test    al, al
0x18011b95b  jz      short loc_18011B977
0x18011b95d  mov     r8d, 28h ; '('
0x18011b963  lea     rdx, aMicrosoftQuiet_0; "Microsoft.QuietHoursProfile.PriorityOnl"...
0x18011b96a  lea     rcx, [rsp+3C8h+var_2D0]
0x18011b972  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18011b977  cmp     [rsp+3C8h+var_2D8], sil
0x18011b97f  jnz     loc_18011BAF6
0x18011b985  mov     r8d, 5
0x18011b98b  lea     rdx, [rsp+3C8h+var_268]
0x18011b993  lea     rcx, [rsp+3C8h+var_328]
0x18011b99b  call    ??$load@UQuietHoursSettings@Notifications@Data@Windows@@@cloud_store@wil@@QEAA?AV?$cloud_store_data@UQuietHoursSettings@Notifications@Data@Windows@@@1@W4cloud_store_load_options@1@PEBD@Z; wil::cloud_store::load<Windows::Data::Notifications::QuietHoursSettings>(wil::cloud_store_load_options,char const *)
0x18011b9a0  nop
0x18011b9a1  cmp     [rsp+3C8h+var_268], sil
0x18011b9a9  jz      loc_18011BA42
0x18011b9af  cmp     [rsp+3C8h+var_388], 3
0x18011b9b4  jnz     short loc_18011B9FE
0x18011b9b6  lea     rcx, [rsp+3C8h+var_260]
0x18011b9be  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18011b9c3  mov     rcx, rax
0x18011b9c6  mov     r9d, 26h ; '&'
0x18011b9cc  lea     r8, aMicrosoftQuiet; "Microsoft.QuietHoursProfile.AlarmsOnly"
0x18011b9d3  mov     rdx, [rsp+3C8h+var_250]
0x18011b9db  call    ??$_Traits_equal@U?$char_traits@G@std@@@std@@YA_NQEBG_K01@Z; std::_Traits_equal<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x18011b9e0  test    al, al
0x18011b9e2  jz      short loc_18011B9FE
0x18011b9e4  mov     r8d, 28h ; '('
0x18011b9ea  lea     rdx, aMicrosoftQuiet_0; "Microsoft.QuietHoursProfile.PriorityOnl"...
0x18011b9f1  lea     rcx, [rsp+3C8h+var_260]
0x18011b9f9  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18011b9fe  lea     rdx, [rsp+3C8h+var_260]
0x18011ba06  lea     rcx, [rsp+3C8h+var_2D0]
0x18011ba0e  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18011ba13  mov     al, [rsp+3C8h+var_240]
0x18011ba1a  mov     [rsp+3C8h+var_2B0], al
0x18011ba21  mov     eax, [rsp+3C8h+var_23C]
0x18011ba28  mov     [rsp+3C8h+var_2AC], eax
0x18011ba2f  mov     al, [rsp+3C8h+var_268]
0x18011ba36  mov     [rsp+3C8h+var_2D8], al
0x18011ba3d  jmp     loc_18011BAE9
0x18011ba42  xor     edx, edx; Val
0x18011ba44  mov     r8d, 200h; Size
0x18011ba4a  lea     rcx, [rsp+3C8h+Name]; void *
0x18011ba52  call    memset_0
0x18011ba57  mov     [rsp+3C8h+cchName], 200h
0x18011ba5f  lea     rax, [rsp+3C8h+cchName]
0x18011ba64  mov     [rsp+3C8h+lpcchClass], rax; pcbData
0x18011ba69  lea     rax, [rsp+3C8h+Name]
0x18011ba71  mov     [rsp+3C8h+lpClass], rax; pvData
0x18011ba76  mov     [rsp+3C8h+phkResult], rsi; pdwType
0x18011ba7b  mov     r9d, 2; dwFlags
0x18011ba81  lea     r8, aDefaultprofile; "DefaultProfile"
0x18011ba88  lea     rdx, aSoftwareMicros_20; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18011ba8f  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18011ba96  call    cs:__imp_RegGetValueW
0x18011ba9c  test    eax, eax
0x18011ba9e  jz      short loc_18011BAB4
0x18011baa0  mov     [rsp+3C8h+Name], si
0x18011baa8  jle     short loc_18011BAB4
0x18011baaa  movzx   eax, ax
0x18011baad  or      eax, 80070000h
0x18011bab2  test    eax, eax
0x18011bab4  js      short loc_18011BAE1
0x18011bab6  lea     rax, [rsp+3C8h+Name]
0x18011babe  or      r8, 0FFFFFFFFFFFFFFFFh
0x18011bac2  inc     r8
0x18011bac5  cmp     [rax+r8*2], si
0x18011baca  jnz     short loc_18011BAC2
0x18011bacc  lea     rdx, [rsp+3C8h+Name]
0x18011bad4  lea     rcx, [rsp+3C8h+var_2D0]
0x18011badc  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18011bae1  mov     [rsp+3C8h+var_2D8], 1
0x18011bae9  lea     rcx, [rsp+3C8h+var_268]
0x18011baf1  call    ??1?$cloud_store_data@UQuietHoursSettings@DoNotDisturb@Data@Windows@@@wil@@QEAA@XZ; wil::cloud_store_data<Windows::Data::DoNotDisturb::QuietHoursSettings>::~cloud_store_data<Windows::Data::DoNotDisturb::QuietHoursSettings>(void)
0x18011baf6  lea     rdx, dword_18013829C
0x18011bafd  lea     rcx, [rsp+3C8h+var_300]
0x18011bb05  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18011bb0a  nop
0x18011bb0b  lea     rax, [rsp+3C8h+var_300]
0x18011bb13  mov     [rsp+3C8h+lpcchClass], rax
0x18011bb18  lea     r8, [rsp+3C8h+var_2D8]
0x18011bb20  lea     rdx, [rsp+3C8h+var_288]
0x18011bb28  lea     rcx, [rsp+3C8h+var_328]
0x18011bb30  call    ??$save_internal@UQuietHoursSettings@DoNotDisturb@Data@Windows@@@cloud_store@wil@@AEAA?AVcloud_store_save_result@1@AEBV?$cloud_store_data@UQuietHoursSettings@DoNotDisturb@Data@Windows@@@1@PEBU?$ItemReference@UQuietHoursSettings@DoNotDisturb@Data@Windows@@@Platform@Data@Windows@@W4cloud_store_save_options@1@_KAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; wil::cloud_store::save_internal<Windows::Data::DoNotDisturb::QuietHoursSettings>(wil::cloud_store_data<Windows::Data::DoNotDisturb::QuietHoursSettings> const &,Windows::Data::Platform::ItemReference<Windows::Data::DoNotDisturb::QuietHoursSettings> const *,wil::cloud_store_save_options,unsigned __int64,std::string const &)
0x18011bb35  nop
0x18011bb36  mov     rdx, [rsp+3C8h+var_2E8]
0x18011bb3e  cmp     rdx, 0Fh
0x18011bb42  jbe     short loc_18011BB55
0x18011bb44  inc     rdx
0x18011bb47  mov     rcx, [rsp+3C8h+var_300]
0x18011bb4f  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18011bb54  nop
0x18011bb55  lea     rcx, [rsp+3C8h+hKey]
0x18011bb5a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18011bb5f  nop
0x18011bb60  lea     rcx, [rsp+3C8h+var_368]
0x18011bb65  call    ??1?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(void)
0x18011bb6a  nop
0x18011bb6b  lea     rcx, [rsp+3C8h+var_2D8]
0x18011bb73  call    ??1?$cloud_store_data@UQuietHoursSettings@DoNotDisturb@Data@Windows@@@wil@@QEAA@XZ; wil::cloud_store_data<Windows::Data::DoNotDisturb::QuietHoursSettings>::~cloud_store_data<Windows::Data::DoNotDisturb::QuietHoursSettings>(void)
0x18011bb78  nop
0x18011bb79  lea     rcx, [rsp+3C8h+var_328]; this
0x18011bb81  call    ??1cloud_store@wil@@QEAA@XZ; wil::cloud_store::~cloud_store(void)
0x18011bb86  nop
0x18011bb87  mov     rcx, [rsp+3C8h+var_18]
0x18011bb8f  xor     rcx, rsp; StackCookie
0x18011bb92  call    __security_check_cookie
0x18011bb97  lea     r11, [rsp+3C8h+var_8]
0x18011bb9f  mov     rbx, [r11+10h]
0x18011bba3  mov     rsi, [r11+18h]
0x18011bba7  mov     rsp, r11
0x18011bbaa  pop     rdi
0x18011bbab  retn
```
