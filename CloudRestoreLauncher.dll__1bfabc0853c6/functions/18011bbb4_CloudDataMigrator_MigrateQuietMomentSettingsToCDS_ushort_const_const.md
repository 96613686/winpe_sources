# CloudDataMigrator::MigrateQuietMomentSettingsToCDS(ushort const * const)

- ea: `0x18011bbb4`
- end: `0x18011c10d`
- name: `?MigrateQuietMomentSettingsToCDS@CloudDataMigrator@@AEAAXQEBG@Z`
- size: `1369`
- prototype: `void(CloudDataMigrator *__hidden this, const unsigned __int16 *const)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18011ad80`

## callees

- `0x18000c6e0`
- `0x18000d688`
- `0x18000fda0`
- `0x180014468`
- `0x18001cfa4`
- `0x18002a50c`
- `0x180031774`
- `0x180035c0c`
- `0x1800360b8`
- `0x180036a3c`
- `0x18005caac`
- `0x180117c58`
- `0x180118168`
- `0x1801184c4`
- `0x1801185a4`
- `0x180118c68`
- `0x18011a204`
- `0x18011bbb4`

## import_xrefs

- `KERNEL32!CompareStringOrdinal` at `0x18011bd43`
- `KERNEL32!CompareStringOrdinal` at `0x18011bdde`
- `KERNEL32!CompareStringOrdinal` at `0x18011be01`
- `KERNEL32!CompareStringOrdinal` at `0x18011be24`
- `KERNEL32!CompareStringOrdinal` at `0x18011bebb`
- `KERNEL32!CompareStringOrdinal` at `0x18011bede`
- `KERNEL32!CompareStringOrdinal` at `0x18011bf01`
- `KERNEL32!CompareStringOrdinal` at `0x18011bd43`
- `KERNEL32!CompareStringOrdinal` at `0x18011bdde`
- `KERNEL32!CompareStringOrdinal` at `0x18011be01`
- `KERNEL32!CompareStringOrdinal` at `0x18011be24`
- `KERNEL32!CompareStringOrdinal` at `0x18011bebb`
- `KERNEL32!CompareStringOrdinal` at `0x18011bede`
- `KERNEL32!CompareStringOrdinal` at `0x18011bf01`
- `ADVAPI32!RegGetValueW` at `0x18011bd90`
- `ADVAPI32!RegGetValueW` at `0x18011be6d`
- `ADVAPI32!RegGetValueW` at `0x18011bf79`
- `ADVAPI32!RegGetValueW` at `0x18011c01a`
- `ADVAPI32!RegGetValueW` at `0x18011bd90`
- `ADVAPI32!RegGetValueW` at `0x18011be6d`
- `ADVAPI32!RegGetValueW` at `0x18011bf79`
- `ADVAPI32!RegGetValueW` at `0x18011c01a`

## string_xrefs

- `0x18011bef5`: `QuietMomentScheduled`
- `0x18011bf64`: `DefaultQuietMomentScheduledProfile`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall CloudDataMigrator::MigrateQuietMomentSettingsToCDS(CloudDataMigrator *this, const WCHAR *a2)
{
  __int64 v3; // rbx
  LSTATUS ValueW; // eax
  bool v5; // sf
  LSTATUS v6; // eax
  bool v7; // sf
  LSTATUS v8; // eax
  bool v9; // sf
  __int64 v10; // r8
  const unsigned __int16 *v11; // rdx
  LSTATUS v12; // eax
  bool v13; // sf
  const char *v14; // r9
  const char *v15; // r9
  int bIgnoreCase; // [rsp+20h] [rbp-3F8h]
  DWORD pcbData; // [rsp+40h] [rbp-3D8h] BYREF
  _BYTE v18[40]; // [rsp+48h] [rbp-3D0h] BYREF
  char v19; // [rsp+70h] [rbp-3A8h] BYREF
  char v20; // [rsp+71h] [rbp-3A7h]
  _BYTE v21[32]; // [rsp+78h] [rbp-3A0h] BYREF
  __int64 v22; // [rsp+98h] [rbp-380h]
  __int64 v23; // [rsp+A0h] [rbp-378h]
  int v24; // [rsp+A8h] [rbp-370h]
  char v25; // [rsp+ACh] [rbp-36Ch]
  void *v26[3]; // [rsp+E0h] [rbp-338h] BYREF
  unsigned __int64 v27; // [rsp+F8h] [rbp-320h]
  _BYTE v28[8]; // [rsp+120h] [rbp-2F8h] BYREF
  _BYTE v29[32]; // [rsp+128h] [rbp-2F0h] BYREF
  __int64 v30; // [rsp+148h] [rbp-2D0h]
  __int64 v31; // [rsp+150h] [rbp-2C8h]
  int v32; // [rsp+158h] [rbp-2C0h]
  char v33; // [rsp+15Ch] [rbp-2BCh]
  _BYTE v34[64]; // [rsp+190h] [rbp-288h] BYREF
  _WORD pvData[256]; // [rsp+1D0h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+418h] [rbp+0h]

  try
  {
    wil::cloud_store::cloud_store(v18);
    wil::make_cloud_store_data_reference<Windows::Data::DoNotDisturb::QuietMoment>(v34, a2);
    std::string::string(v26, &dword_18013829C);
    wil::cloud_store::load_internal<Windows::Data::DoNotDisturb::QuietMoment>(
      (unsigned int)v18,
      (unsigned int)&v19,
      7,
      (unsigned int)v34,
      (__int64)v26);
    if ( v27 > 0xF )
      std::_Deallocate<16>(v26[0], (struct std::nothrow_t *)(v27 + 1));
    if ( v19 )
      goto LABEL_42;
    wil::make_cloud_store_data_reference<Windows::Data::Notifications::QuietHoursProfile>(v26, a2);
    wil::cloud_store::load<Windows::Data::Notifications::QuietMoment>(v18, v28, v26, 5);
    if ( v28[0] )
    {
      v20 = v28[1];
      std::wstring::operator=(v21, v29);
      v25 = v33;
      v22 = v30;
      v23 = v31;
      v24 = v32;
      v19 = v28[0];
LABEL_41:
      wil::cloud_store_data<Windows::Data::DoNotDisturb::QuietMoment>::~cloud_store_data<Windows::Data::DoNotDisturb::QuietMoment>(v28);
      Windows::Data::Platform::ItemReference<Windows::Data::Notifications::QuietHoursProfile>::~ItemReference<Windows::Data::Notifications::QuietHoursProfile>(v26);
LABEL_42:
      wil::cloud_store::save<Windows::Data::DoNotDisturb::QuietMoment>(v18, v26, &v19, v34);
      wil::cloud_store_data<Windows::Data::DoNotDisturb::QuietMoment>::~cloud_store_data<Windows::Data::DoNotDisturb::QuietMoment>(&v19);
      Windows::Data::Platform::ItemReference<Windows::Data::Notifications::QuietHoursProfile>::~ItemReference<Windows::Data::Notifications::QuietHoursProfile>(v34);
      wil::cloud_store::~cloud_store((wil::cloud_store *)v18);
      return;
    }
    memset_0(pvData, 0, sizeof(pvData));
    v3 = -1;
    if ( CompareStringOrdinal(a2, -1, L"QuietMomentEmergency", -1, 1) == 2 )
    {
      v20 = 1;
      pcbData = 512;
      ValueW = RegGetValueW(
                 HKEY_LOCAL_MACHINE,
                 L"Software\\Microsoft\\Windows\\CurrentVersion\\Notifications\\QuietHours\\Profiles",
                 L"OffProfile",
                 2u,
                 0,
                 pvData,
                 &pcbData);
      v5 = ValueW < 0;
      if ( ValueW )
      {
        pvData[0] = 0;
        if ( ValueW > 0 )
          v5 = 1;
      }
      if ( v5 )
        goto LABEL_40;
      do
        ++v3;
      while ( pvData[v3] );
    }
    else
    {
      if ( CompareStringOrdinal(a2, -1, L"QuietMomentFullScreen", -1, 1) == 2
        || CompareStringOrdinal(a2, -1, L"QuietMomentPresentation", -1, 1) == 2 )
      {
        v20 = 1;
        pcbData = 512;
        v12 = RegGetValueW(
                HKEY_LOCAL_MACHINE,
                L"Software\\Microsoft\\Windows\\CurrentVersion\\Notifications\\QuietHours\\Profiles",
                L"DefaultQuietMomentProfile",
                2u,
                0,
                pvData,
                &pcbData);
        v13 = v12 < 0;
        if ( v12 )
        {
          pvData[0] = 0;
          if ( v12 > 0 )
            v13 = 1;
        }
        if ( !v13 )
        {
          do
            ++v3;
          while ( pvData[v3] );
          std::wstring::_Assign<unsigned short>(v21, pvData, v3);
        }
        goto LABEL_40;
      }
      if ( CompareStringOrdinal(a2, -1, L"QuietMomentGame", -1, 1) == 2 )
      {
        v20 = 1;
        pcbData = 512;
        v6 = RegGetValueW(
               HKEY_LOCAL_MACHINE,
               L"Software\\Microsoft\\Windows\\CurrentVersion\\Notifications\\QuietHours\\Profiles",
               L"DefaultQuietMomentGameProfile",
               2u,
               0,
               pvData,
               &pcbData);
        v7 = v6 < 0;
        if ( v6 )
        {
          pvData[0] = 0;
          if ( v6 > 0 )
            v7 = 1;
        }
        if ( v7 )
          goto LABEL_40;
        do
          ++v3;
        while ( pvData[v3] );
      }
      else
      {
        if ( CompareStringOrdinal(a2, -1, L"QuietMomentPostOOBE", -1, 1) == 2
          || CompareStringOrdinal(a2, -1, L"QuietMomentFocus", -1, 1) == 2 )
        {
          v20 = 1;
          v10 = 40;
          v11 = L"Microsoft.QuietHoursProfile.PriorityOnly";
          goto LABEL_32;
        }
        if ( CompareStringOrdinal(a2, -1, L"QuietMomentScheduled", -1, 1) != 2 )
        {
          v15 = (const char *)(unsigned int)wil::verify_hresult<long>(2147549183LL);
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x13A,
            (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\clouddatamigrator\\lib\\clouddatamigrator.cpp",
            v15,
            bIgnoreCase);
        }
        v20 = 0;
        v22 = 828000000000LL;
        v23 = 252000000000LL;
        v24 = 0;
        pcbData = 512;
        v8 = RegGetValueW(
               HKEY_LOCAL_MACHINE,
               L"Software\\Microsoft\\Windows\\CurrentVersion\\Notifications\\QuietHours\\Profiles",
               L"DefaultQuietMomentScheduledProfile",
               2u,
               0,
               pvData,
               &pcbData);
        v9 = v8 < 0;
        if ( v8 )
        {
          pvData[0] = 0;
          if ( v8 > 0 )
            v9 = 1;
        }
        if ( v9 )
          goto LABEL_40;
        do
          ++v3;
        while ( pvData[v3] );
      }
    }
    v10 = v3;
    v11 = pvData;
LABEL_32:
    std::wstring::_Assign<unsigned short>(v21, v11, v10);
LABEL_40:
    v19 = 1;
    goto LABEL_41;
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x141,
      (unsigned int)"pcshell\\shell\\cloudrestorelauncher\\clouddatamigrator\\lib\\clouddatamigrator.cpp",
      v14);
  }
}

```

## disassembly

```asm
0x18011bbb4  push    rbx
0x18011bbb6  push    rsi
0x18011bbb7  push    rdi
0x18011bbb8  push    r12
0x18011bbba  push    r14
0x18011bbbc  push    r15
0x18011bbbe  sub     rsp, 3E8h
0x18011bbc5  mov     rax, cs:__security_cookie
0x18011bbcc  xor     rax, rsp
0x18011bbcf  mov     [rsp+418h+var_48], rax
0x18011bbd7  mov     rdi, rdx
0x18011bbda  xor     esi, esi
0x18011bbdc  mov     dword ptr [rsp+418h+pcbData], 7530h
0x18011bbe4  lea     rcx, [rsp+418h+var_3D0]
0x18011bbe9  call    ??0cloud_store@wil@@QEAA@W4PartitionKind@Cloud@Storage@Internal@Windows@@PEBG1W4CloudStoreOptions@3456@II@Z; wil::cloud_store::cloud_store(Windows::Internal::Storage::Cloud::PartitionKind,ushort const *,ushort const *,Windows::Internal::Storage::Cloud::CloudStoreOptions,uint,uint)
0x18011bbee  nop
0x18011bbef  mov     rdx, rdi
0x18011bbf2  lea     rcx, [rsp+418h+var_288]
0x18011bbfa  call    ??$make_cloud_store_data_reference@UQuietMoment@DoNotDisturb@Data@Windows@@@wil@@YA?AU?$ItemReference@UQuietMoment@DoNotDisturb@Data@Windows@@@Platform@Data@Windows@@PEBG0@Z; wil::make_cloud_store_data_reference<Windows::Data::DoNotDisturb::QuietMoment>(ushort const *,ushort const *)
0x18011bbff  nop
0x18011bc00  lea     rdx, dword_18013829C
0x18011bc07  lea     rcx, [rsp+418h+var_338]
0x18011bc0f  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18011bc14  nop
0x18011bc15  lea     rax, [rsp+418h+var_338]
0x18011bc1d  mov     qword ptr [rsp+418h+bIgnoreCase], rax
0x18011bc22  lea     r9, [rsp+418h+var_288]
0x18011bc2a  lea     r8d, [rsi+7]
0x18011bc2e  lea     rdx, [rsp+418h+var_3A8]
0x18011bc33  lea     rcx, [rsp+418h+var_3D0]
0x18011bc38  call    ??$load_internal@UQuietMoment@DoNotDisturb@Data@Windows@@@cloud_store@wil@@AEAA?AV?$cloud_store_data@UQuietMoment@DoNotDisturb@Data@Windows@@@1@W4cloud_store_load_options@1@PEBU?$ItemReference@UQuietMoment@DoNotDisturb@Data@Windows@@@Platform@Data@Windows@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; wil::cloud_store::load_internal<Windows::Data::DoNotDisturb::QuietMoment>(wil::cloud_store_load_options,Windows::Data::Platform::ItemReference<Windows::Data::DoNotDisturb::QuietMoment> const *,std::string const &)
0x18011bc3d  nop
0x18011bc3e  mov     rdx, [rsp+418h+var_320]
0x18011bc46  cmp     rdx, 0Fh
0x18011bc4a  jbe     short loc_18011BC5D
0x18011bc4c  inc     rdx
0x18011bc4f  mov     rcx, [rsp+418h+var_338]
0x18011bc57  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18011bc5c  nop
0x18011bc5d  cmp     [rsp+418h+var_3A8], sil
0x18011bc62  jnz     loc_18011C080
0x18011bc68  mov     rdx, rdi
0x18011bc6b  lea     rcx, [rsp+418h+var_338]
0x18011bc73  call    ??$make_cloud_store_data_reference@UQuietHoursProfile@Notifications@Data@Windows@@@wil@@YA?AU?$ItemReference@UQuietHoursProfile@Notifications@Data@Windows@@@Platform@Data@Windows@@PEBG0@Z; wil::make_cloud_store_data_reference<Windows::Data::Notifications::QuietHoursProfile>(ushort const *,ushort const *)
0x18011bc78  nop
0x18011bc79  mov     r9d, 5
0x18011bc7f  lea     r8, [rsp+418h+var_338]
0x18011bc87  lea     rdx, [rsp+418h+var_2F8]
0x18011bc8f  lea     rcx, [rsp+418h+var_3D0]
0x18011bc94  call    ??$load@UQuietMoment@Notifications@Data@Windows@@@cloud_store@wil@@QEAA?AV?$cloud_store_data@UQuietMoment@Notifications@Data@Windows@@@1@AEBU?$ItemReference@UQuietMoment@Notifications@Data@Windows@@@Platform@Data@Windows@@W4cloud_store_load_options@1@PEBD@Z; wil::cloud_store::load<Windows::Data::Notifications::QuietMoment>(Windows::Data::Platform::ItemReference<Windows::Data::Notifications::QuietMoment> const &,wil::cloud_store_load_options,char const *)
0x18011bc99  nop
0x18011bc9a  cmp     [rsp+418h+var_2F8], sil
0x18011bca2  jz      short loc_18011BD0D
0x18011bca4  mov     al, [rsp+418h+var_2F7]
0x18011bcab  mov     [rsp+418h+var_3A7], al
0x18011bcaf  lea     rdx, [rsp+418h+var_2F0]
0x18011bcb7  lea     rcx, [rsp+418h+var_3A0]
0x18011bcbc  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18011bcc1  mov     al, [rsp+418h+var_2BC]
0x18011bcc8  mov     [rsp+418h+var_36C], al
0x18011bccf  mov     rax, [rsp+418h+var_2D0]
0x18011bcd7  mov     [rsp+418h+var_380], rax
0x18011bcdf  mov     rax, [rsp+418h+var_2C8]
0x18011bce7  mov     [rsp+418h+var_378], rax
0x18011bcef  mov     eax, [rsp+418h+var_2C0]
0x18011bcf6  mov     [rsp+418h+var_370], eax
0x18011bcfd  mov     al, [rsp+418h+var_2F8]
0x18011bd04  mov     [rsp+418h+var_3A8], al
0x18011bd08  jmp     loc_18011C065
0x18011bd0d  mov     r12d, 200h
0x18011bd13  mov     r8d, r12d; Size
0x18011bd16  xor     edx, edx; Val
0x18011bd18  lea     rcx, [rsp+418h+var_248]; void *
0x18011bd20  call    memset_0
0x18011bd25  mov     r14d, 1
0x18011bd2b  mov     [rsp+418h+bIgnoreCase], r14d; bIgnoreCase
0x18011bd30  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18011bd34  mov     r9d, ebx; cchCount2
0x18011bd37  lea     r8, aQuietmomenteme; "QuietMomentEmergency"
0x18011bd3e  mov     edx, ebx; cchCount1
0x18011bd40  mov     rcx, rdi; lpString1
0x18011bd43  call    cs:__imp_CompareStringOrdinal
0x18011bd49  lea     r15d, [r14+1]
0x18011bd4d  cmp     eax, r15d
0x18011bd50  jnz     short loc_18011BDCA
0x18011bd52  mov     [rsp+418h+var_3A7], r14b
0x18011bd57  mov     [rsp+418h+var_3D8], r12d
0x18011bd5c  lea     rax, [rsp+418h+var_3D8]
0x18011bd61  mov     [rsp+418h+pcbData], rax; pcbData
0x18011bd66  lea     rax, [rsp+418h+var_248]
0x18011bd6e  mov     [rsp+418h+pvData], rax; pvData
0x18011bd73  mov     qword ptr [rsp+418h+bIgnoreCase], rsi; pdwType
0x18011bd78  mov     r9d, r15d; dwFlags
0x18011bd7b  lea     r8, aOffprofile; "OffProfile"
0x18011bd82  lea     rdx, aSoftwareMicros_20; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18011bd89  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18011bd90  call    cs:__imp_RegGetValueW
0x18011bd96  test    eax, eax
0x18011bd98  jz      short loc_18011BDAE
0x18011bd9a  mov     [rsp+418h+var_248], si
0x18011bda2  jle     short loc_18011BDAE
0x18011bda4  movzx   eax, ax
0x18011bda7  or      eax, 80070000h
0x18011bdac  test    eax, eax
0x18011bdae  js      loc_18011C060
0x18011bdb4  lea     rax, [rsp+418h+var_248]
0x18011bdbc  inc     rbx
0x18011bdbf  cmp     [rax+rbx*2], si
0x18011bdc3  jnz     short loc_18011BDBC
0x18011bdc5  jmp     loc_18011BFAE
0x18011bdca  mov     [rsp+418h+bIgnoreCase], r14d; bIgnoreCase
0x18011bdcf  mov     r9d, ebx; cchCount2
0x18011bdd2  lea     r8, aQuietmomentful; "QuietMomentFullScreen"
0x18011bdd9  mov     edx, ebx; cchCount1
0x18011bddb  mov     rcx, rdi; lpString1
0x18011bdde  call    cs:__imp_CompareStringOrdinal
0x18011bde4  cmp     eax, r15d
0x18011bde7  jz      loc_18011BFDC
0x18011bded  mov     [rsp+418h+bIgnoreCase], r14d; bIgnoreCase
0x18011bdf2  mov     r9d, ebx; cchCount2
0x18011bdf5  lea     r8, aQuietmomentpre; "QuietMomentPresentation"
0x18011bdfc  mov     edx, ebx; cchCount1
0x18011bdfe  mov     rcx, rdi; lpString1
0x18011be01  call    cs:__imp_CompareStringOrdinal
0x18011be07  cmp     eax, r15d
0x18011be0a  jz      loc_18011BFDC
0x18011be10  mov     [rsp+418h+bIgnoreCase], r14d; bIgnoreCase
0x18011be15  mov     r9d, ebx; cchCount2
0x18011be18  lea     r8, aQuietmomentgam; "QuietMomentGame"
0x18011be1f  mov     edx, ebx; cchCount1
0x18011be21  mov     rcx, rdi; lpString1
0x18011be24  call    cs:__imp_CompareStringOrdinal
0x18011be2a  cmp     eax, r15d
0x18011be2d  jnz     short loc_18011BEA7
0x18011be2f  mov     [rsp+418h+var_3A7], r14b
0x18011be34  mov     [rsp+418h+var_3D8], r12d
0x18011be39  lea     rax, [rsp+418h+var_3D8]
0x18011be3e  mov     [rsp+418h+pcbData], rax; pcbData
0x18011be43  lea     rax, [rsp+418h+var_248]
0x18011be4b  mov     [rsp+418h+pvData], rax; pvData
0x18011be50  mov     qword ptr [rsp+418h+bIgnoreCase], rsi; pdwType
0x18011be55  mov     r9d, r15d; dwFlags
0x18011be58  lea     r8, aDefaultquietmo_0; "DefaultQuietMomentGameProfile"
0x18011be5f  lea     rdx, aSoftwareMicros_20; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18011be66  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18011be6d  call    cs:__imp_RegGetValueW
0x18011be73  test    eax, eax
0x18011be75  jz      short loc_18011BE8B
0x18011be77  mov     [rsp+418h+var_248], si
0x18011be7f  jle     short loc_18011BE8B
0x18011be81  movzx   eax, ax
0x18011be84  or      eax, 80070000h
0x18011be89  test    eax, eax
0x18011be8b  js      loc_18011C060
0x18011be91  lea     rax, [rsp+418h+var_248]
0x18011be99  inc     rbx
0x18011be9c  cmp     [rax+rbx*2], si
0x18011bea0  jnz     short loc_18011BE99
0x18011bea2  jmp     loc_18011BFAE
0x18011bea7  mov     [rsp+418h+bIgnoreCase], r14d; bIgnoreCase
0x18011beac  mov     r9d, ebx; cchCount2
0x18011beaf  lea     r8, aQuietmomentpos; "QuietMomentPostOOBE"
0x18011beb6  mov     edx, ebx; cchCount1
0x18011beb8  mov     rcx, rdi; lpString1
0x18011bebb  call    cs:__imp_CompareStringOrdinal
0x18011bec1  cmp     eax, r15d
0x18011bec4  jz      loc_18011BFC8
0x18011beca  mov     [rsp+418h+bIgnoreCase], r14d; bIgnoreCase
0x18011becf  mov     r9d, ebx; cchCount2
0x18011bed2  lea     r8, aQuietmomentfoc; "QuietMomentFocus"
0x18011bed9  mov     edx, ebx; cchCount1
0x18011bedb  mov     rcx, rdi; lpString1
0x18011bede  call    cs:__imp_CompareStringOrdinal
0x18011bee4  cmp     eax, r15d
0x18011bee7  jz      loc_18011BFC8
0x18011beed  mov     [rsp+418h+bIgnoreCase], r14d; int
0x18011bef2  mov     r9d, ebx; cchCount2
0x18011bef5  lea     r8, aQuietmomentsch; "QuietMomentScheduled"
0x18011befc  mov     edx, ebx; cchCount1
0x18011befe  mov     rcx, rdi; lpString1
0x18011bf01  call    cs:__imp_CompareStringOrdinal
0x18011bf07  cmp     eax, r15d
0x18011bf0a  jnz     loc_18011C0E5
0x18011bf10  mov     [rsp+418h+var_3A7], sil
0x18011bf15  mov     rax, 0C0C8A55800h
0x18011bf1f  mov     [rsp+418h+var_380], rax
0x18011bf27  mov     rax, 3AAC5ED800h
0x18011bf31  mov     [rsp+418h+var_378], rax
0x18011bf39  mov     [rsp+418h+var_370], esi
0x18011bf40  mov     [rsp+418h+var_3D8], r12d
0x18011bf45  lea     rax, [rsp+418h+var_3D8]
0x18011bf4a  mov     [rsp+418h+pcbData], rax; pcbData
0x18011bf4f  lea     rax, [rsp+418h+var_248]
0x18011bf57  mov     [rsp+418h+pvData], rax; pvData
0x18011bf5c  mov     qword ptr [rsp+418h+bIgnoreCase], rsi; pdwType
0x18011bf61  mov     r9d, r15d; dwFlags
0x18011bf64  lea     r8, aDefaultquietmo; "DefaultQuietMomentScheduledProfile"
0x18011bf6b  lea     rdx, aSoftwareMicros_20; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18011bf72  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18011bf79  call    cs:__imp_RegGetValueW
0x18011bf7f  test    eax, eax
0x18011bf81  jz      short loc_18011BF97
0x18011bf83  mov     [rsp+418h+var_248], si
0x18011bf8b  jle     short loc_18011BF97
0x18011bf8d  movzx   eax, ax
0x18011bf90  or      eax, 80070000h
0x18011bf95  test    eax, eax
0x18011bf97  js      loc_18011C060
0x18011bf9d  lea     rax, [rsp+418h+var_248]
0x18011bfa5  inc     rbx
0x18011bfa8  cmp     [rax+rbx*2], si
0x18011bfac  jnz     short loc_18011BFA5
0x18011bfae  mov     r8, rbx
0x18011bfb1  lea     rdx, [rsp+418h+var_248]
0x18011bfb9  lea     rcx, [rsp+418h+var_3A0]
0x18011bfbe  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18011bfc3  jmp     loc_18011C060
0x18011bfc8  mov     [rsp+418h+var_3A7], r14b
0x18011bfcd  mov     r8d, 28h ; '('
0x18011bfd3  lea     rdx, aMicrosoftQuiet_0; "Microsoft.QuietHoursProfile.PriorityOnl"...
0x18011bfda  jmp     short loc_18011BFB9
0x18011bfdc  mov     [rsp+418h+var_3A7], r14b
0x18011bfe1  mov     [rsp+418h+var_3D8], r12d
0x18011bfe6  lea     rax, [rsp+418h+var_3D8]
0x18011bfeb  mov     [rsp+418h+pcbData], rax; pcbData
0x18011bff0  lea     rax, [rsp+418h+var_248]
0x18011bff8  mov     [rsp+418h+pvData], rax; pvData
0x18011bffd  mov     qword ptr [rsp+418h+bIgnoreCase], rsi; pdwType
0x18011c002  mov     r9d, r15d; dwFlags
0x18011c005  lea     r8, aDefaultquietmo_1; "DefaultQuietMomentProfile"
0x18011c00c  lea     rdx, aSoftwareMicros_20; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18011c013  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18011c01a  call    cs:__imp_RegGetValueW
0x18011c020  test    eax, eax
0x18011c022  jz      short loc_18011C038
0x18011c024  mov     [rsp+418h+var_248], si
0x18011c02c  jle     short loc_18011C038
0x18011c02e  movzx   eax, ax
0x18011c031  or      eax, 80070000h
0x18011c036  test    eax, eax
0x18011c038  js      short loc_18011C060
0x18011c03a  lea     rax, [rsp+418h+var_248]
0x18011c042  inc     rbx
0x18011c045  cmp     [rax+rbx*2], si
0x18011c049  jnz     short loc_18011C042
0x18011c04b  mov     r8, rbx
0x18011c04e  lea     rdx, [rsp+418h+var_248]
0x18011c056  lea     rcx, [rsp+418h+var_3A0]
0x18011c05b  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18011c060  mov     [rsp+418h+var_3A8], r14b
0x18011c065  lea     rcx, [rsp+418h+var_2F8]
0x18011c06d  call    ??1?$cloud_store_data@UQuietMoment@DoNotDisturb@Data@Windows@@@wil@@QEAA@XZ; wil::cloud_store_data<Windows::Data::DoNotDisturb::QuietMoment>::~cloud_store_data<Windows::Data::DoNotDisturb::QuietMoment>(void)
0x18011c072  nop
0x18011c073  lea     rcx, [rsp+418h+var_338]
0x18011c07b  call    ??1?$ItemReference@UQuietHoursProfile@Notifications@Data@Windows@@@Platform@Data@Windows@@QEAA@XZ; Windows::Data::Platform::ItemReference<Windows::Data::Notifications::QuietHoursProfile>::~ItemReference<Windows::Data::Notifications::QuietHoursProfile>(void)
0x18011c080  lea     r9, [rsp+418h+var_288]
0x18011c088  lea     r8, [rsp+418h+var_3A8]
0x18011c08d  lea     rdx, [rsp+418h+var_338]
0x18011c095  lea     rcx, [rsp+418h+var_3D0]
0x18011c09a  call    ??$save@UQuietMoment@DoNotDisturb@Data@Windows@@@cloud_store@wil@@QEAA?AVcloud_store_save_result@1@AEBV?$cloud_store_data@UQuietMoment@DoNotDisturb@Data@Windows@@@1@AEBU?$ItemReference@UQuietMoment@DoNotDisturb@Data@Windows@@@Platform@Data@Windows@@W4cloud_store_save_options@1@_KPEBD@Z; wil::cloud_store::save<Windows::Data::DoNotDisturb::QuietMoment>(wil::cloud_store_data<Windows::Data::DoNotDisturb::QuietMoment> const &,Windows::Data::Platform::ItemReference<Windows::Data::DoNotDisturb::QuietMoment> const &,wil::cloud_store_save_options,unsigned __int64,char const *)
0x18011c09f  nop
0x18011c0a0  lea     rcx, [rsp+418h+var_3A8]
0x18011c0a5  call    ??1?$cloud_store_data@UQuietMoment@DoNotDisturb@Data@Windows@@@wil@@QEAA@XZ; wil::cloud_store_data<Windows::Data::DoNotDisturb::QuietMoment>::~cloud_store_data<Windows::Data::DoNotDisturb::QuietMoment>(void)
0x18011c0aa  nop
0x18011c0ab  lea     rcx, [rsp+418h+var_288]
0x18011c0b3  call    ??1?$ItemReference@UQuietHoursProfile@Notifications@Data@Windows@@@Platform@Data@Windows@@QEAA@XZ; Windows::Data::Platform::ItemReference<Windows::Data::Notifications::QuietHoursProfile>::~ItemReference<Windows::Data::Notifications::QuietHoursProfile>(void)
0x18011c0b8  nop
0x18011c0b9  lea     rcx, [rsp+418h+var_3D0]; this
0x18011c0be  call    ??1cloud_store@wil@@QEAA@XZ; wil::cloud_store::~cloud_store(void)
0x18011c0c3  nop
0x18011c0c4  mov     rcx, [rsp+418h+var_48]
0x18011c0cc  xor     rcx, rsp; StackCookie
0x18011c0cf  call    __security_check_cookie
0x18011c0d4  add     rsp, 3E8h
0x18011c0db  pop     r15
0x18011c0dd  pop     r14
0x18011c0df  pop     r12
0x18011c0e1  pop     rdi
0x18011c0e2  pop     rsi
0x18011c0e3  pop     rbx
0x18011c0e4  retn
0x18011c0e5  mov     ecx, 8000FFFFh
0x18011c0ea  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18011c0ef  mov     r9d, eax; char *
0x18011c0f2  mov     rcx, [rsp+418h]; this
0x18011c0fa  lea     r8, aPcshellShellCl_4; "pcshell\\shell\\cloudrestorelauncher\\c"...
0x18011c101  mov     edx, 13Ah; void *
0x18011c106  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
