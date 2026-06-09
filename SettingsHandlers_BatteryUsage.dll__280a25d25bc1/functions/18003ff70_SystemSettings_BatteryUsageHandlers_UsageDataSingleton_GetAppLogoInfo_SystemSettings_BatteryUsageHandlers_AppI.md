# SystemSettings::BatteryUsageHandlers::UsageDataSingleton::GetAppLogoInfo(SystemSettings::BatteryUsageHandlers::AppIdentity,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x18003ff70`
- end: `0x18004034c`
- name: `?GetAppLogoInfo@UsageDataSingleton@BatteryUsageHandlers@SystemSettings@@QEAA?AUAppLogoInfo@23@UAppIdentity@23@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `988`
- prototype: ``
- caller_count: `2`
- callee_count: `20`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002bc6c`
- `0x18002da38`

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
- `0x18003ff70`
- `0x1800434e4`
- `0x180046650`
- `0x18004719c`
- `0x18005249c`
- `0x180052bd4`
- `0x180053104`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004002e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180040127`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180040173`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180040274`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004002e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180040127`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180040173`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180040274`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180040152`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180040248`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180040152`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180040248`

## pseudocode

```c
__int64 __fastcall SystemSettings::BatteryUsageHandlers::UsageDataSingleton::GetAppLogoInfo(
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
        (void *)0x34A,
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
    if ( (int)SystemSettings::BatteryUsageHandlers::UsageDataSingleton::GetPackageFromFamilyName(
                &SystemSettings::BatteryUsageHandlers::g_UsageDataSingleton,
                v18,
                &v35) >= 0 )
    {
      v37 = 0;
      v21 = qword_180079C00;
      v22 = *(__int64 (__fastcall **)(__int64, SystemSettings::StorageSenseHandlers::CAppTileData *, __int64 **))(*(_QWORD *)qword_180079C00 + 48LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v37);
      v23 = v22(v21, v35, &v37);
      if ( v23 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x355,
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
          (void *)0x358,
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
      &qword_180079B90,
      &v37,
      v43);
    std::wstring::_Tidy_deallocate(v43);
    if ( v37 == (__int64 *)qword_180079B90 )
    {
      v30 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a3, v37, v29);
      if ( !(unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(
                               v30,
                               *(_QWORD *)(a3 + 16),
                               L"Microsoft.Office.Desktop_8wekyb3d8bbwe",
                               38) )
      {
        v33 = wil::verify_hresult<long>(2147500037LL);
        wil::details::in1diag3::Throw_Hr(retaddr, (void *)0x372, v34, (const char *)v33, (int)v35);
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
        (void *)0x37E,
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
0x18003ff70  mov     [rsp-8+arg_0], rbx
0x18003ff75  push    rbp
0x18003ff76  push    rsi
0x18003ff77  push    rdi
0x18003ff78  push    r12
0x18003ff7a  push    r13
0x18003ff7c  push    r14
0x18003ff7e  push    r15
0x18003ff80  lea     rbp, [rsp-27h]
0x18003ff85  sub     rsp, 90h
0x18003ff8c  mov     rax, cs:__security_cookie
0x18003ff93  xor     rax, rsp
0x18003ff96  mov     [rbp+57h+var_40], rax
0x18003ff9a  mov     r15, r9
0x18003ff9d  mov     r14, r8
0x18003ffa0  mov     rsi, rdx
0x18003ffa3  mov     [rbp+57h+var_90], rdx
0x18003ffa7  mov     [rbp+57h+var_70], r8
0x18003ffab  mov     [rbp+57h+var_68], r9
0x18003ffaf  xor     r12d, r12d
0x18003ffb2  mov     [rbp+57h+var_80], r12
0x18003ffb6  mov     dword ptr [rbp+57h+string], r12d
0x18003ffba  cmp     [r8+20h], r12d
0x18003ffbe  jnz     loc_1800400A1
0x18003ffc4  mov     [rbp+57h+var_A0], r12
0x18003ffc8  lea     rcx, [rbp+57h+var_A0]
0x18003ffcc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003ffd1  mov     rcx, r14
0x18003ffd4  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003ffd9  lea     rdx, [rbp+57h+var_A0]; struct SystemSettings::StorageSenseHandlers::CExecutableInfo **
0x18003ffdd  mov     rcx, rax; this
0x18003ffe0  call    ?Create@CExecutableInfo@StorageSenseHandlers@SystemSettings@@SAJPEBGPEAPEAV123@@Z; SystemSettings::StorageSenseHandlers::CExecutableInfo::Create(ushort const *,SystemSettings::StorageSenseHandlers::CExecutableInfo * *)
0x18003ffe5  mov     rcx, [rbp+5Fh]; this
0x18003ffe9  test    eax, eax
0x18003ffeb  js      loc_1800402F8
0x18003fff1  mov     rdx, [rbp+57h+var_A0]
0x18003fff5  lea     rcx, [rbp+57h+var_80]
0x18003fff9  call    ??$?4VCExecutableInfo@StorageSenseHandlers@SystemSettings@@@?$ComPtr@UIInspectable@@@WRL@Microsoft@@QEAAAEAV012@PEAVCExecutableInfo@StorageSenseHandlers@SystemSettings@@@Z; Microsoft::WRL::ComPtr<IInspectable>::operator=<SystemSettings::StorageSenseHandlers::CExecutableInfo>(SystemSettings::StorageSenseHandlers::CExecutableInfo *)
0x18003fffe  mov     dword ptr [rbp+57h+string], 2
0x180040005  lea     rcx, [rbp+57h+var_A0]
0x180040009  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004000e  mov     rax, [rbp+57h+var_80]
0x180040012  mov     [rbp+57h+var_90], rax
0x180040016  lea     r8, [rbp+57h+var_90]
0x18004001a  lea     rdx, [rbp+57h+string]
0x18004001e  lea     rcx, [rbp+57h+var_A0]
0x180040022  call    ??$Make@VCAppTileData@StorageSenseHandlers@SystemSettings@@W4AppListType@23@PEAUIInspectable@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@VCAppTileData@StorageSenseHandlers@SystemSettings@@@12@$$QEAW4AppListType@StorageSenseHandlers@SystemSettings@@$$QEAPEAUIInspectable@@@Z; Microsoft::WRL::Details::Make<SystemSettings::StorageSenseHandlers::CAppTileData,SystemSettings::StorageSenseHandlers::AppListType,IInspectable *>(SystemSettings::StorageSenseHandlers::AppListType &&,IInspectable * &&)
0x180040027  nop
0x180040028  mov     [rbp+57h+var_88], r12
0x18004002c  xor     ecx, ecx; string
0x18004002e  call    cs:__imp_WindowsDeleteString
0x180040034  mov     [rbp+57h+var_88], r12
0x180040038  lea     rdx, [rbp+57h+var_88]; HSTRING *
0x18004003c  mov     rbx, [rbp+57h+var_A0]
0x180040040  mov     rcx, rbx; this
0x180040043  call    ?GetLogoPath@CAppTileData@StorageSenseHandlers@SystemSettings@@QEAAJPEAPEAUHSTRING__@@@Z; SystemSettings::StorageSenseHandlers::CAppTileData::GetLogoPath(HSTRING__ * *)
0x180040048  test    eax, eax
0x18004004a  jns     short loc_18004006B
0x18004004c  xor     r8d, r8d; unsigned int
0x18004004f  lea     rdx, word_180065238; unsigned __int16 *
0x180040056  lea     rcx, [rbp+57h+var_88]; this
0x18004005a  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x18004005f  mov     rcx, [rbp+5Fh]; this
0x180040063  test    eax, eax
0x180040065  js      loc_18004030D
0x18004006b  mov     [rbp+57h+var_78], r12d
0x18004006f  lea     rdx, [rbp+57h+var_78]; unsigned int *
0x180040073  mov     rcx, rbx; this
0x180040076  call    ?GetLogoBackground@CAppTileData@StorageSenseHandlers@SystemSettings@@QEAAJPEAI@Z; SystemSettings::StorageSenseHandlers::CAppTileData::GetLogoBackground(uint *)
0x18004007b  test    eax, eax
0x18004007d  js      loc_180040238
0x180040083  mov     edi, [rbp+57h+var_78]
0x180040086  mov     r12d, edi
0x180040089  shr     r12d, 18h
0x18004008d  mov     r13d, edi
0x180040090  shr     r13d, 8
0x180040094  mov     eax, edi
0x180040096  shr     eax, 10h
0x180040099  mov     dword ptr [rbp+57h+string], eax
0x18004009c  jmp     loc_180040242
0x1800400a1  cmp     dword ptr [r8+20h], 1
0x1800400a6  jnz     loc_18004000E
0x1800400ac  mov     [rbp+57h+var_A0], r12
0x1800400b0  lea     rcx, [rbp+57h+var_A0]
0x1800400b4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800400b9  mov     rcx, r14
0x1800400bc  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800400c1  lea     r8, [rbp+57h+var_A0]
0x1800400c5  mov     rdx, rax
0x1800400c8  lea     rcx, ?g_UsageDataSingleton@BatteryUsageHandlers@SystemSettings@@3VUsageDataSingleton@12@A; SystemSettings::BatteryUsageHandlers::UsageDataSingleton SystemSettings::BatteryUsageHandlers::g_UsageDataSingleton
0x1800400cf  call    ?GetPackageFromFamilyName@UsageDataSingleton@BatteryUsageHandlers@SystemSettings@@QEAAJPEBGPEAV?$ComPtr@UIPackage@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Z; SystemSettings::BatteryUsageHandlers::UsageDataSingleton::GetPackageFromFamilyName(ushort const *,Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage> *)
0x1800400d4  test    eax, eax
0x1800400d6  js      loc_180040195
0x1800400dc  mov     [rbp+57h+var_90], r12
0x1800400e0  mov     rdi, cs:qword_180079C00
0x1800400e7  mov     rax, [rdi]
0x1800400ea  mov     rbx, [rax+30h]
0x1800400ee  lea     rcx, [rbp+57h+var_90]
0x1800400f2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800400f7  lea     r8, [rbp+57h+var_90]
0x1800400fb  mov     rdx, [rbp+57h+var_A0]
0x1800400ff  mov     rcx, rdi
0x180040102  mov     rax, rbx
0x180040105  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004010a  mov     rcx, [rbp+5Fh]; this
0x18004010e  test    eax, eax
0x180040110  js      loc_180040322
0x180040116  mov     [rbp+57h+string], r12
0x18004011a  mov     rdi, [rbp+57h+var_90]
0x18004011e  mov     rax, [rdi]
0x180040121  mov     rbx, [rax+48h]
0x180040125  xor     ecx, ecx; string
0x180040127  call    cs:__imp_WindowsDeleteString
0x18004012d  mov     [rbp+57h+string], r12
0x180040131  lea     rdx, [rbp+57h+string]
0x180040135  mov     rcx, rdi
0x180040138  mov     rax, rbx
0x18004013b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040140  mov     rcx, [rbp+5Fh]; this
0x180040144  test    eax, eax
0x180040146  js      loc_180040337
0x18004014c  xor     edx, edx; length
0x18004014e  mov     rcx, [rbp+57h+string]; string
0x180040152  call    cs:__imp_WindowsGetStringRawBuffer
0x180040158  mov     rdx, rax
0x18004015b  mov     rcx, rsi
0x18004015e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180040163  mov     dword ptr [rsi+20h], 0FFFFFF00h
0x18004016a  xor     eax, eax
0x18004016c  mov     [rsi+24h], eax
0x18004016f  mov     rcx, [rbp+57h+string]; string
0x180040173  call    cs:__imp_WindowsDeleteString
0x180040179  mov     [rbp+57h+string], r12
0x18004017d  lea     rcx, [rbp+57h+var_90]
0x180040181  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180040186  nop
0x180040187  lea     rcx, [rbp+57h+var_A0]
0x18004018b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180040190  jmp     loc_180040297
0x180040195  mov     rcx, r15
0x180040198  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004019d  mov     rdx, rax
0x1800401a0  lea     rcx, [rbp+57h+var_60]
0x1800401a4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800401a9  lea     r8, [rbp+57h+var_60]
0x1800401ad  lea     rdx, [rbp+57h+var_90]
0x1800401b1  lea     rcx, qword_180079B90
0x1800401b8  call    ?find@?$_Tree@V?$_Tmap_traits@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring const,std::wstring,std::less<std::wstring const>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::find(std::wstring const &)
0x1800401bd  lea     rcx, [rbp+57h+var_60]
0x1800401c1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800401c6  mov     rdx, [rbp+57h+var_90]
0x1800401ca  cmp     rdx, cs:qword_180079B90
0x1800401d1  jz      short loc_1800401EF
0x1800401d3  add     rdx, 40h ; '@'
0x1800401d7  lea     rcx, [rbp+57h+var_80]
0x1800401db  call    ??$?4UIPackageInfo@BatteryUsageHandlers@SystemSettings@@@?$ComPtr@UIInspectable@@@WRL@Microsoft@@QEAAAEAV012@AEBV?$ComPtr@UIPackageInfo@BatteryUsageHandlers@SystemSettings@@@12@@Z; Microsoft::WRL::ComPtr<IInspectable>::operator=<SystemSettings::BatteryUsageHandlers::IPackageInfo>(Microsoft::WRL::ComPtr<SystemSettings::BatteryUsageHandlers::IPackageInfo> const &)
0x1800401e0  nop
0x1800401e1  lea     rcx, [rbp+57h+var_A0]
0x1800401e5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800401ea  jmp     loc_18004000E
0x1800401ef  mov     rcx, r14
0x1800401f2  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800401f7  mov     r9d, 26h ; '&'
0x1800401fd  lea     r8, aMicrosoftOffic; "Microsoft.Office.Desktop_8wekyb3d8bbwe"
0x180040204  mov     rdx, [r14+10h]
0x180040208  mov     rcx, rax
0x18004020b  call    ??$_Traits_equal@U?$char_traits@G@std@@@std@@YA_NQEBG_K01@Z; std::_Traits_equal<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x180040210  test    al, al
0x180040212  jz      loc_1800402DC
0x180040218  lea     rdx, word_180065238
0x18004021f  mov     rcx, rsi
0x180040222  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180040227  mov     dword ptr [rsi+20h], 0FFFFFF00h
0x18004022e  xor     eax, eax
0x180040230  mov     [rsi+24h], eax
0x180040233  jmp     loc_180040187
0x180040238  mov     dil, 0FFh
0x18004023b  mov     r13b, dil
0x18004023e  mov     byte ptr [rbp+57h+string], dil
0x180040242  xor     edx, edx; length
0x180040244  mov     rcx, [rbp+57h+var_88]; string
0x180040248  call    cs:__imp_WindowsGetStringRawBuffer
0x18004024e  mov     rdx, rax
0x180040251  mov     rcx, rsi
0x180040254  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180040259  mov     [rsi+20h], r12b
0x18004025d  mov     [rsi+21h], dil
0x180040261  mov     [rsi+22h], r13b
0x180040265  mov     eax, dword ptr [rbp+57h+string]
0x180040268  mov     [rsi+23h], al
0x18004026b  xor     eax, eax
0x18004026d  mov     [rsi+24h], eax
0x180040270  mov     rcx, [rbp+57h+var_88]; string
0x180040274  call    cs:__imp_WindowsDeleteString
0x18004027a  mov     [rbp+57h+var_88], 0
0x180040282  test    rbx, rbx
0x180040285  jz      short loc_180040297
0x180040287  mov     rax, [rbx]
0x18004028a  mov     rcx, rbx
0x18004028d  mov     rax, [rax+10h]
0x180040291  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040296  nop
0x180040297  lea     rcx, [rbp+57h+var_80]
0x18004029b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800402a0  nop
0x1800402a1  mov     rcx, r14
0x1800402a4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800402a9  nop
0x1800402aa  mov     rcx, r15
0x1800402ad  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800402b2  mov     rax, rsi
0x1800402b5  mov     rcx, [rbp+57h+var_40]
0x1800402b9  xor     rcx, rsp; StackCookie
0x1800402bc  call    __security_check_cookie
0x1800402c1  mov     rbx, [rsp+0C0h+arg_0]
0x1800402c9  add     rsp, 90h
0x1800402d0  pop     r15
0x1800402d2  pop     r14
0x1800402d4  pop     r13
0x1800402d6  pop     r12
0x1800402d8  pop     rdi
0x1800402d9  pop     rsi
0x1800402da  pop     rbp
0x1800402db  retn
0x1800402dc  mov     ecx, 80004005h
0x1800402e1  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1800402e6  mov     r9d, eax; char *
0x1800402e9  mov     rcx, [rbp+5Fh]; this
0x1800402ed  mov     edx, 372h; void *
0x1800402f2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800402f8  mov     r9d, eax; char *
0x1800402fb  lea     r8, aOnecoreuapShel_8; "onecoreuap\\shell\\coresettinghandlers"...
0x180040302  mov     edx, 34Ah; void *
0x180040307  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18004030d  mov     r9d, eax; char *
0x180040310  lea     r8, aOnecoreuapShel_8; "onecoreuap\\shell\\coresettinghandlers"...
0x180040317  mov     edx, 37Eh; void *
0x18004031c  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180040322  mov     r9d, eax; char *
0x180040325  lea     r8, aOnecoreuapShel_8; "onecoreuap\\shell\\coresettinghandlers"...
0x18004032c  mov     edx, 355h; void *
0x180040331  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180040337  mov     r9d, eax; char *
0x18004033a  lea     r8, aOnecoreuapShel_8; "onecoreuap\\shell\\coresettinghandlers"...
0x180040341  mov     edx, 358h; void *
0x180040346  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
