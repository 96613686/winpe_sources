# SystemSettings::BatteryUsageHandlers::UsageDataSingleton2::GetAppLogoInfo(SystemSettings::BatteryUsageHandlers::AppIdentity,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x18003fb8c`
- end: `0x18003ff68`
- name: `?GetAppLogoInfo@UsageDataSingleton2@BatteryUsageHandlers@SystemSettings@@QEAA?AUAppLogoInfo@23@UAppIdentity@23@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `988`
- prototype: ``
- caller_count: `2`
- callee_count: `20`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180031fb8`
- `0x1800328d4`

## callees

- `0x1800028d0`
- `0x180004cfc`
- `0x180005a18`
- `0x18001d728`
- `0x18001e360`
- `0x18001e5c8`
- `0x180023c78`
- `0x180036598`
- `0x18003b8e8`
- `0x18003b930`
- `0x18003bc74`
- `0x18003cedc`
- `0x18003fb8c`
- `0x180043258`
- `0x180046650`
- `0x18004719c`
- `0x18005249c`
- `0x180052bd4`
- `0x180053104`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003fc4a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003fd43`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003fd8f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003fe90`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003fc4a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003fd43`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003fd8f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003fe90`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003fd6e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003fe64`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003fd6e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003fe64`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall SystemSettings::BatteryUsageHandlers::UsageDataSingleton2::GetAppLogoInfo(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  unsigned int v7; // r12d
  __int64 v8; // rdx
  __int64 v9; // r8
  SystemSettings::StorageSenseHandlers *v10; // rax
  int v11; // eax
  SystemSettings::StorageSenseHandlers::CAppTileData *v12; // rbx
  int v13; // eax
  char v14; // di
  unsigned int v15; // r13d
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // rax
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // rdi
  __int64 (__fastcall *v22)(__int64, SystemSettings::StorageSenseHandlers::CAppTileData *, __int64 **); // rbx
  int v23; // eax
  __int64 *v24; // rdi
  __int64 (__fastcall *v25)(__int64 *, HSTRING *); // rbx
  int v26; // eax
  PCWSTR StringRawBuffer; // rax
  __int64 v28; // rax
  __int64 v29; // r8
  __int64 v30; // rax
  PCWSTR v31; // rax
  unsigned int v33; // eax
  unsigned int v34; // r8d
  SystemSettings::StorageSenseHandlers::CAppTileData *v35; // [rsp+20h] [rbp-49h] BYREF
  HSTRING string; // [rsp+28h] [rbp-41h] BYREF
  __int64 *v37; // [rsp+30h] [rbp-39h] BYREF
  HSTRING v38; // [rsp+38h] [rbp-31h] BYREF
  __int64 *v39; // [rsp+40h] [rbp-29h] BYREF
  unsigned int v40; // [rsp+48h] [rbp-21h] BYREF
  __int64 v41; // [rsp+50h] [rbp-19h]
  __int64 v42; // [rsp+58h] [rbp-11h]
  _BYTE v43[32]; // [rsp+60h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v37 = (__int64 *)a2;
  v41 = a3;
  v42 = a4;
  LOBYTE(v7) = 0;
  v39 = 0;
  LODWORD(string) = 0;
  if ( !*(_DWORD *)(a3 + 32) )
  {
    v35 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v35);
    v10 = (SystemSettings::StorageSenseHandlers *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(
                                                    a3,
                                                    v8,
                                                    v9);
    v11 = SystemSettings::StorageSenseHandlers::CExecutableInfo::Create(v10, &v35);
    if ( v11 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x908,
        (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\usagedatasingleton.cpp",
        (const char *)(unsigned int)v11,
        (int)v35);
    Microsoft::WRL::ComPtr<IInspectable>::operator=<SystemSettings::StorageSenseHandlers::CExecutableInfo>(
      (__int64 *)&v39,
      (__int64)v35);
    LODWORD(string) = 2;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v35);
    goto LABEL_4;
  }
  if ( *(_DWORD *)(a3 + 32) == 1 )
  {
    v35 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v35);
    v18 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a3, v16, v17);
    if ( (int)SystemSettings::BatteryUsageHandlers::UsageDataSingleton2::GetPackageFromFamilyName(
                &SystemSettings::BatteryUsageHandlers::g_UsageDataSingleton2,
                v18,
                &v35) >= 0 )
    {
      v37 = 0;
      v21 = qword_180079E28;
      v22 = *(__int64 (__fastcall **)(__int64, SystemSettings::StorageSenseHandlers::CAppTileData *, __int64 **))(*(_QWORD *)qword_180079E28 + 48LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v37);
      v23 = v22(v21, v35, &v37);
      if ( v23 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x913,
          (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\usagedatasingleton.cpp",
          (const char *)(unsigned int)v23,
          (int)v35);
      string = 0;
      v24 = v37;
      v25 = *(__int64 (__fastcall **)(__int64 *, HSTRING *))(*v37 + 72);
      WindowsDeleteString(0);
      string = 0;
      v26 = v25(v24, &string);
      if ( v26 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x916,
          (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\usagedatasingleton.cpp",
          (const char *)(unsigned int)v26,
          (int)v35);
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      std::wstring::wstring(a2, (__int64)StringRawBuffer);
      *(_DWORD *)(a2 + 32) = -256;
      *(_DWORD *)(a2 + 36) = 0;
      WindowsDeleteString(string);
      string = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v37);
LABEL_13:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v35);
      goto LABEL_21;
    }
    v28 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a4, v19, v20);
    std::wstring::wstring((__int64)v43, v28);
    std::_Tree<std::_Tmap_traits<std::wstring const,std::wstring,std::less<std::wstring const>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::find(
      &qword_180079DC0,
      &v37,
      v43);
    std::wstring::_Tidy_deallocate(v43);
    if ( v37 == (__int64 *)qword_180079DC0 )
    {
      v30 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a3, v37, v29);
      if ( !(unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(
                               v30,
                               *(_QWORD *)(a3 + 16),
                               L"Microsoft.Office.Desktop_8wekyb3d8bbwe",
                               38) )
      {
        v33 = wil::verify_hresult<long>(2147500037LL);
        wil::details::in1diag3::Throw_Hr(retaddr, (void *)0x930, v34, (const char *)v33, (int)v35);
      }
      std::wstring::wstring(a2, (__int64)&word_180065238);
      *(_DWORD *)(a2 + 32) = -256;
      *(_DWORD *)(a2 + 36) = 0;
      goto LABEL_13;
    }
    Microsoft::WRL::ComPtr<IInspectable>::operator=<SystemSettings::BatteryUsageHandlers::IPackageInfo>(
      (__int64 *)&v39,
      v37 + 8);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v35);
  }
LABEL_4:
  v37 = v39;
  Microsoft::WRL::Details::Make<SystemSettings::StorageSenseHandlers::CAppTileData,enum SystemSettings::StorageSenseHandlers::AppListType,IInspectable *>(
    &v35,
    (unsigned int *)&string,
    &v37);
  v38 = 0;
  WindowsDeleteString(0);
  v38 = 0;
  v12 = v35;
  if ( (int)SystemSettings::StorageSenseHandlers::CAppTileData::GetLogoPath(v35, &v38) < 0 )
  {
    v13 = Microsoft::WRL::Wrappers::HString::Set((Microsoft::WRL::Wrappers::HString *)&v38, &word_180065238, 0);
    if ( v13 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x93C,
        (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\usagedatasingleton.cpp",
        (const char *)(unsigned int)v13,
        (int)v35);
  }
  v40 = 0;
  if ( (int)SystemSettings::StorageSenseHandlers::CAppTileData::GetLogoBackground(v12, &v40) < 0 )
  {
    v14 = -1;
    LOBYTE(v15) = -1;
    LOBYTE(string) = -1;
  }
  else
  {
    v14 = v40;
    v7 = HIBYTE(v40);
    v15 = v40 >> 8;
    LODWORD(string) = HIWORD(v40);
  }
  v31 = WindowsGetStringRawBuffer(v38, 0);
  std::wstring::wstring(a2, (__int64)v31);
  *(_BYTE *)(a2 + 32) = v7;
  *(_BYTE *)(a2 + 33) = v14;
  *(_BYTE *)(a2 + 34) = v15;
  *(_BYTE *)(a2 + 35) = (_BYTE)string;
  *(_DWORD *)(a2 + 36) = 0;
  WindowsDeleteString(v38);
  v38 = 0;
  if ( v12 )
    (*(void (__fastcall **)(SystemSettings::StorageSenseHandlers::CAppTileData *))(*(_QWORD *)v12 + 16LL))(v12);
LABEL_21:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
  std::wstring::_Tidy_deallocate(a3);
  std::wstring::_Tidy_deallocate(a4);
  return a2;
}

```

## disassembly

```asm
0x18003fb8c  mov     [rsp-8+arg_0], rbx
0x18003fb91  push    rbp
0x18003fb92  push    rsi
0x18003fb93  push    rdi
0x18003fb94  push    r12
0x18003fb96  push    r13
0x18003fb98  push    r14
0x18003fb9a  push    r15
0x18003fb9c  lea     rbp, [rsp-27h]
0x18003fba1  sub     rsp, 90h
0x18003fba8  mov     rax, cs:__security_cookie
0x18003fbaf  xor     rax, rsp
0x18003fbb2  mov     [rbp+57h+var_40], rax
0x18003fbb6  mov     r15, r9
0x18003fbb9  mov     r14, r8
0x18003fbbc  mov     rsi, rdx
0x18003fbbf  mov     [rbp+57h+var_90], rdx
0x18003fbc3  mov     [rbp+57h+var_70], r8
0x18003fbc7  mov     [rbp+57h+var_68], r9
0x18003fbcb  xor     r12d, r12d
0x18003fbce  mov     [rbp+57h+var_80], r12
0x18003fbd2  mov     dword ptr [rbp+57h+string], r12d
0x18003fbd6  cmp     [r8+20h], r12d
0x18003fbda  jnz     loc_18003FCBD
0x18003fbe0  mov     [rbp+57h+var_A0], r12
0x18003fbe4  lea     rcx, [rbp+57h+var_A0]
0x18003fbe8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003fbed  mov     rcx, r14
0x18003fbf0  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003fbf5  lea     rdx, [rbp+57h+var_A0]; struct SystemSettings::StorageSenseHandlers::CExecutableInfo **
0x18003fbf9  mov     rcx, rax; this
0x18003fbfc  call    ?Create@CExecutableInfo@StorageSenseHandlers@SystemSettings@@SAJPEBGPEAPEAV123@@Z; SystemSettings::StorageSenseHandlers::CExecutableInfo::Create(ushort const *,SystemSettings::StorageSenseHandlers::CExecutableInfo * *)
0x18003fc01  mov     rcx, [rbp+5Fh]; this
0x18003fc05  test    eax, eax
0x18003fc07  js      loc_18003FF14
0x18003fc0d  mov     rdx, [rbp+57h+var_A0]
0x18003fc11  lea     rcx, [rbp+57h+var_80]
0x18003fc15  call    ??$?4VCExecutableInfo@StorageSenseHandlers@SystemSettings@@@?$ComPtr@UIInspectable@@@WRL@Microsoft@@QEAAAEAV012@PEAVCExecutableInfo@StorageSenseHandlers@SystemSettings@@@Z; Microsoft::WRL::ComPtr<IInspectable>::operator=<SystemSettings::StorageSenseHandlers::CExecutableInfo>(SystemSettings::StorageSenseHandlers::CExecutableInfo *)
0x18003fc1a  mov     dword ptr [rbp+57h+string], 2
0x18003fc21  lea     rcx, [rbp+57h+var_A0]
0x18003fc25  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003fc2a  mov     rax, [rbp+57h+var_80]
0x18003fc2e  mov     [rbp+57h+var_90], rax
0x18003fc32  lea     r8, [rbp+57h+var_90]
0x18003fc36  lea     rdx, [rbp+57h+string]
0x18003fc3a  lea     rcx, [rbp+57h+var_A0]
0x18003fc3e  call    ??$Make@VCAppTileData@StorageSenseHandlers@SystemSettings@@W4AppListType@23@PEAUIInspectable@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@VCAppTileData@StorageSenseHandlers@SystemSettings@@@12@$$QEAW4AppListType@StorageSenseHandlers@SystemSettings@@$$QEAPEAUIInspectable@@@Z; Microsoft::WRL::Details::Make<SystemSettings::StorageSenseHandlers::CAppTileData,SystemSettings::StorageSenseHandlers::AppListType,IInspectable *>(SystemSettings::StorageSenseHandlers::AppListType &&,IInspectable * &&)
0x18003fc43  nop
0x18003fc44  mov     [rbp+57h+var_88], r12
0x18003fc48  xor     ecx, ecx; string
0x18003fc4a  call    cs:__imp_WindowsDeleteString
0x18003fc50  mov     [rbp+57h+var_88], r12
0x18003fc54  lea     rdx, [rbp+57h+var_88]; HSTRING *
0x18003fc58  mov     rbx, [rbp+57h+var_A0]
0x18003fc5c  mov     rcx, rbx; this
0x18003fc5f  call    ?GetLogoPath@CAppTileData@StorageSenseHandlers@SystemSettings@@QEAAJPEAPEAUHSTRING__@@@Z; SystemSettings::StorageSenseHandlers::CAppTileData::GetLogoPath(HSTRING__ * *)
0x18003fc64  test    eax, eax
0x18003fc66  jns     short loc_18003FC87
0x18003fc68  xor     r8d, r8d; unsigned int
0x18003fc6b  lea     rdx, word_180065238; unsigned __int16 *
0x18003fc72  lea     rcx, [rbp+57h+var_88]; this
0x18003fc76  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x18003fc7b  mov     rcx, [rbp+5Fh]; this
0x18003fc7f  test    eax, eax
0x18003fc81  js      loc_18003FF29
0x18003fc87  mov     [rbp+57h+var_78], r12d
0x18003fc8b  lea     rdx, [rbp+57h+var_78]; unsigned int *
0x18003fc8f  mov     rcx, rbx; this
0x18003fc92  call    ?GetLogoBackground@CAppTileData@StorageSenseHandlers@SystemSettings@@QEAAJPEAI@Z; SystemSettings::StorageSenseHandlers::CAppTileData::GetLogoBackground(uint *)
0x18003fc97  test    eax, eax
0x18003fc99  js      loc_18003FE54
0x18003fc9f  mov     edi, [rbp+57h+var_78]
0x18003fca2  mov     r12d, edi
0x18003fca5  shr     r12d, 18h
0x18003fca9  mov     r13d, edi
0x18003fcac  shr     r13d, 8
0x18003fcb0  mov     eax, edi
0x18003fcb2  shr     eax, 10h
0x18003fcb5  mov     dword ptr [rbp+57h+string], eax
0x18003fcb8  jmp     loc_18003FE5E
0x18003fcbd  cmp     dword ptr [r8+20h], 1
0x18003fcc2  jnz     loc_18003FC2A
0x18003fcc8  mov     [rbp+57h+var_A0], r12
0x18003fccc  lea     rcx, [rbp+57h+var_A0]
0x18003fcd0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003fcd5  mov     rcx, r14
0x18003fcd8  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003fcdd  lea     r8, [rbp+57h+var_A0]
0x18003fce1  mov     rdx, rax
0x18003fce4  lea     rcx, ?g_UsageDataSingleton2@BatteryUsageHandlers@SystemSettings@@3VUsageDataSingleton2@12@A; SystemSettings::BatteryUsageHandlers::UsageDataSingleton2 SystemSettings::BatteryUsageHandlers::g_UsageDataSingleton2
0x18003fceb  call    ?GetPackageFromFamilyName@UsageDataSingleton2@BatteryUsageHandlers@SystemSettings@@QEAAJPEBGPEAV?$ComPtr@UIPackage@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Z; SystemSettings::BatteryUsageHandlers::UsageDataSingleton2::GetPackageFromFamilyName(ushort const *,Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage> *)
0x18003fcf0  test    eax, eax
0x18003fcf2  js      loc_18003FDB1
0x18003fcf8  mov     [rbp+57h+var_90], r12
0x18003fcfc  mov     rdi, cs:qword_180079E28
0x18003fd03  mov     rax, [rdi]
0x18003fd06  mov     rbx, [rax+30h]
0x18003fd0a  lea     rcx, [rbp+57h+var_90]
0x18003fd0e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003fd13  lea     r8, [rbp+57h+var_90]
0x18003fd17  mov     rdx, [rbp+57h+var_A0]
0x18003fd1b  mov     rcx, rdi
0x18003fd1e  mov     rax, rbx
0x18003fd21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fd26  mov     rcx, [rbp+5Fh]; this
0x18003fd2a  test    eax, eax
0x18003fd2c  js      loc_18003FF3E
0x18003fd32  mov     [rbp+57h+string], r12
0x18003fd36  mov     rdi, [rbp+57h+var_90]
0x18003fd3a  mov     rax, [rdi]
0x18003fd3d  mov     rbx, [rax+48h]
0x18003fd41  xor     ecx, ecx; string
0x18003fd43  call    cs:__imp_WindowsDeleteString
0x18003fd49  mov     [rbp+57h+string], r12
0x18003fd4d  lea     rdx, [rbp+57h+string]
0x18003fd51  mov     rcx, rdi
0x18003fd54  mov     rax, rbx
0x18003fd57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fd5c  mov     rcx, [rbp+5Fh]; this
0x18003fd60  test    eax, eax
0x18003fd62  js      loc_18003FF53
0x18003fd68  xor     edx, edx; length
0x18003fd6a  mov     rcx, [rbp+57h+string]; string
0x18003fd6e  call    cs:__imp_WindowsGetStringRawBuffer
0x18003fd74  mov     rdx, rax
0x18003fd77  mov     rcx, rsi
0x18003fd7a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003fd7f  mov     dword ptr [rsi+20h], 0FFFFFF00h
0x18003fd86  xor     eax, eax
0x18003fd88  mov     [rsi+24h], eax
0x18003fd8b  mov     rcx, [rbp+57h+string]; string
0x18003fd8f  call    cs:__imp_WindowsDeleteString
0x18003fd95  mov     [rbp+57h+string], r12
0x18003fd99  lea     rcx, [rbp+57h+var_90]
0x18003fd9d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003fda2  nop
0x18003fda3  lea     rcx, [rbp+57h+var_A0]
0x18003fda7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003fdac  jmp     loc_18003FEB3
0x18003fdb1  mov     rcx, r15
0x18003fdb4  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003fdb9  mov     rdx, rax
0x18003fdbc  lea     rcx, [rbp+57h+var_60]
0x18003fdc0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003fdc5  lea     r8, [rbp+57h+var_60]
0x18003fdc9  lea     rdx, [rbp+57h+var_90]
0x18003fdcd  lea     rcx, qword_180079DC0
0x18003fdd4  call    ?find@?$_Tree@V?$_Tmap_traits@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring const,std::wstring,std::less<std::wstring const>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::find(std::wstring const &)
0x18003fdd9  lea     rcx, [rbp+57h+var_60]
0x18003fddd  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003fde2  mov     rdx, [rbp+57h+var_90]
0x18003fde6  cmp     rdx, cs:qword_180079DC0
0x18003fded  jz      short loc_18003FE0B
0x18003fdef  add     rdx, 40h ; '@'
0x18003fdf3  lea     rcx, [rbp+57h+var_80]
0x18003fdf7  call    ??$?4UIPackageInfo@BatteryUsageHandlers@SystemSettings@@@?$ComPtr@UIInspectable@@@WRL@Microsoft@@QEAAAEAV012@AEBV?$ComPtr@UIPackageInfo@BatteryUsageHandlers@SystemSettings@@@12@@Z; Microsoft::WRL::ComPtr<IInspectable>::operator=<SystemSettings::BatteryUsageHandlers::IPackageInfo>(Microsoft::WRL::ComPtr<SystemSettings::BatteryUsageHandlers::IPackageInfo> const &)
0x18003fdfc  nop
0x18003fdfd  lea     rcx, [rbp+57h+var_A0]
0x18003fe01  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003fe06  jmp     loc_18003FC2A
0x18003fe0b  mov     rcx, r14
0x18003fe0e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003fe13  mov     r9d, 26h ; '&'
0x18003fe19  lea     r8, aMicrosoftOffic; "Microsoft.Office.Desktop_8wekyb3d8bbwe"
0x18003fe20  mov     rdx, [r14+10h]
0x18003fe24  mov     rcx, rax
0x18003fe27  call    ??$_Traits_equal@U?$char_traits@G@std@@@std@@YA_NQEBG_K01@Z; std::_Traits_equal<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x18003fe2c  test    al, al
0x18003fe2e  jz      loc_18003FEF8
0x18003fe34  lea     rdx, word_180065238
0x18003fe3b  mov     rcx, rsi
0x18003fe3e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003fe43  mov     dword ptr [rsi+20h], 0FFFFFF00h
0x18003fe4a  xor     eax, eax
0x18003fe4c  mov     [rsi+24h], eax
0x18003fe4f  jmp     loc_18003FDA3
0x18003fe54  mov     dil, 0FFh
0x18003fe57  mov     r13b, dil
0x18003fe5a  mov     byte ptr [rbp+57h+string], dil
0x18003fe5e  xor     edx, edx; length
0x18003fe60  mov     rcx, [rbp+57h+var_88]; string
0x18003fe64  call    cs:__imp_WindowsGetStringRawBuffer
0x18003fe6a  mov     rdx, rax
0x18003fe6d  mov     rcx, rsi
0x18003fe70  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003fe75  mov     [rsi+20h], r12b
0x18003fe79  mov     [rsi+21h], dil
0x18003fe7d  mov     [rsi+22h], r13b
0x18003fe81  mov     eax, dword ptr [rbp+57h+string]
0x18003fe84  mov     [rsi+23h], al
0x18003fe87  xor     eax, eax
0x18003fe89  mov     [rsi+24h], eax
0x18003fe8c  mov     rcx, [rbp+57h+var_88]; string
0x18003fe90  call    cs:__imp_WindowsDeleteString
0x18003fe96  mov     [rbp+57h+var_88], 0
0x18003fe9e  test    rbx, rbx
0x18003fea1  jz      short loc_18003FEB3
0x18003fea3  mov     rax, [rbx]
0x18003fea6  mov     rcx, rbx
0x18003fea9  mov     rax, [rax+10h]
0x18003fead  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003feb2  nop
0x18003feb3  lea     rcx, [rbp+57h+var_80]
0x18003feb7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003febc  nop
0x18003febd  mov     rcx, r14
0x18003fec0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003fec5  nop
0x18003fec6  mov     rcx, r15
0x18003fec9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003fece  mov     rax, rsi
0x18003fed1  mov     rcx, [rbp+57h+var_40]
0x18003fed5  xor     rcx, rsp; StackCookie
0x18003fed8  call    __security_check_cookie
0x18003fedd  mov     rbx, [rsp+0C0h+arg_0]
0x18003fee5  add     rsp, 90h
0x18003feec  pop     r15
0x18003feee  pop     r14
0x18003fef0  pop     r13
0x18003fef2  pop     r12
0x18003fef4  pop     rdi
0x18003fef5  pop     rsi
0x18003fef6  pop     rbp
0x18003fef7  retn
0x18003fef8  mov     ecx, 80004005h
0x18003fefd  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18003ff02  mov     r9d, eax; char *
0x18003ff05  mov     rcx, [rbp+5Fh]; this
0x18003ff09  mov     edx, 930h; void *
0x18003ff0e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003ff14  mov     r9d, eax; char *
0x18003ff17  lea     r8, aOnecoreuapShel_8; "onecoreuap\\shell\\coresettinghandlers"...
0x18003ff1e  mov     edx, 908h; void *
0x18003ff23  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18003ff29  mov     r9d, eax; char *
0x18003ff2c  lea     r8, aOnecoreuapShel_8; "onecoreuap\\shell\\coresettinghandlers"...
0x18003ff33  mov     edx, 93Ch; void *
0x18003ff38  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18003ff3e  mov     r9d, eax; char *
0x18003ff41  lea     r8, aOnecoreuapShel_8; "onecoreuap\\shell\\coresettinghandlers"...
0x18003ff48  mov     edx, 913h; void *
0x18003ff4d  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18003ff53  mov     r9d, eax; char *
0x18003ff56  lea     r8, aOnecoreuapShel_8; "onecoreuap\\shell\\coresettinghandlers"...
0x18003ff5d  mov     edx, 916h; void *
0x18003ff62  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
