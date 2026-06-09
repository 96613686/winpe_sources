# SystemSettings::StorageSenseHandlers::CAppSizesList::_FilterList(void)

- ea: `0x1800476ec`
- end: `0x1800479e9`
- name: `?_FilterList@CAppSizesList@StorageSenseHandlers@SystemSettings@@AEAAJXZ`
- size: `765`
- prototype: `__int64 __fastcall(SystemSettings::StorageSenseHandlers::CAppSizesList *__hidden this)`
- caller_count: `2`
- callee_count: `14`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18003dd60`
- `0x180045810`

## callees

- `0x180006e50`
- `0x18000c964`
- `0x180019fa8`
- `0x18001a530`
- `0x18001f53c`
- `0x18001fc0c`
- `0x1800248c0`
- `0x18003d36c`
- `0x1800440c0`
- `0x180044d90`
- `0x180046280`
- `0x1800476ec`
- `0x18004947c`
- `0x180049d8c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004772c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800478d4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004772c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800478d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsTrimStringEnd` at `0x1800477ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsTrimStringEnd` at `0x1800477ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsTrimStringStart` at `0x1800477ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsTrimStringStart` at `0x1800477ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180047778`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800477cf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180047824`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800479b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180047778`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800477cf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180047824`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800479b9`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall SystemSettings::StorageSenseHandlers::CAppSizesList::_FilterList(
        SystemSettings::StorageSenseHandlers::CAppSizesList *this)
{
  char *v2; // rbx
  HSTRING *v3; // rbx
  HSTRING v4; // r8
  HSTRING v5; // r8
  int v6; // eax
  int v7; // r12d
  char v8; // r14
  unsigned int i; // esi
  __int64 v10; // rbx
  SystemSettings::StorageSenseHandlers::CAppSizesList *v11; // rcx
  HSTRING string; // [rsp+20h] [rbp-39h] BYREF
  HSTRING v14; // [rsp+28h] [rbp-31h] BYREF
  unsigned int v15; // [rsp+30h] [rbp-29h] BYREF
  struct SystemSettings::StorageSenseHandlers::CPackageSizeSetting *v16; // [rsp+38h] [rbp-21h] BYREF
  char *v17; // [rsp+40h] [rbp-19h] BYREF
  _QWORD v18[3]; // [rsp+48h] [rbp-11h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+60h] [rbp+7h] BYREF
  HSTRING trimString; // [rsp+78h] [rbp+1Fh]

  string = 0;
  v2 = (char *)this + 1072;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 1072));
  v17 = v2;
  v3 = (HSTRING *)((char *)this + 1056);
  if ( (unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(
                       *((Microsoft::WRL::Wrappers::Details **)this + 132),
                       0,
                       v4)
    || *((_DWORD *)this + 260) != -2 )
  {
    if ( (unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(
                         (Microsoft::WRL::Wrappers::Details *)*v3,
                         0,
                         v5) )
    {
      WindowsDeleteString(string);
      string = 0;
      trimString = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L" ", 2u, 1u);
      WindowsTrimStringStart(*v3, trimString, &string);
      trimString = 0;
      v14 = string;
      Microsoft::WRL::Wrappers::HString::Set((HSTRING *)this + 132, &v14);
      WindowsDeleteString(string);
      string = 0;
      trimString = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L" ", 2u, 1u);
      WindowsTrimStringEnd(*v3, trimString, &string);
      trimString = 0;
      v14 = string;
      Microsoft::WRL::Wrappers::HString::Set((HSTRING *)this + 131, &v14);
      WindowsDeleteString(*v3);
      *v3 = 0;
    }
    else
    {
      v14 = (HSTRING)*((_QWORD *)this + 131);
      Microsoft::WRL::Wrappers::HString::Set(&string, &v14);
    }
    v6 = *((_DWORD *)this + 260);
    if ( v6 != -2 )
    {
      *((_DWORD *)this + 259) = v6;
      *((_DWORD *)this + 260) = -2;
      SystemSettings::DataModel::CSettingBase::OnValueChanged(this, L"IsDriveSelected");
      SystemSettings::DataModel::CSettingBase::OnValueChanged(this, L"DiskFreeSpace");
    }
    v7 = *((_DWORD *)this + 259);
    SystemSettings::StorageSenseHandlers::SortModes(v18);
    if ( *(__int64 (__fastcall **)(const void *, const void *))(v18[0] + 16LL * *((int *)this + 256) + 8) == compareSizeDescending
      || (v8 = 0,
          *(__int64 (__fastcall **)(const void *, const void *))(v18[0] + 16LL * *((int *)this + 256) + 8) == compareSizeAscending) )
    {
      v8 = 1;
    }
    Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&v17);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 1112));
    v14 = (HSTRING)((char *)this + 1112);
    if ( v8 )
    {
      *((_BYTE *)this + 804) = 1;
      SystemSettings::DataModel::CSettingBase::OnValueChanged(this, (const unsigned __int16 *)&stru_18010B738);
    }
    v16 = 0;
    v15 = 0;
    Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::get_Size(
      *((_QWORD *)this + 26),
      &v15);
    *((_DWORD *)this + 200) = 0;
    for ( i = 0; i < v15; ++i )
    {
      v10 = *((_QWORD *)this + 26);
      Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v16);
      Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::GetAt(
        v10,
        i,
        &v16);
      if ( SystemSettings::StorageSenseHandlers::CAppSizesList::_UpdateAppVisibility(v11, v16, string, v7) )
        ++*((_DWORD *)this + 200);
      SystemSettings::StorageSenseHandlers::CAppSizesList::NotifyTotalAppsUpdated(this);
    }
    Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&v14);
    if ( v8 )
    {
      *((_BYTE *)this + 804) = 0;
      SystemSettings::DataModel::CSettingBase::OnValueChanged(this, (const unsigned __int16 *)&stru_18010B738);
    }
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v16);
    Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&v14);
    std::vector<SystemSettings::StorageSenseHandlers::AppSortModes>::_Tidy(v18);
  }
  else
  {
    Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&v17);
  }
  Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&v17);
  WindowsDeleteString(string);
  return 0;
}

```

## disassembly

```asm
0x1800476ec  mov     [rsp-8+arg_8], rbx
0x1800476f1  mov     [rsp-8+arg_10], rsi
0x1800476f6  push    rbp
0x1800476f7  push    rdi
0x1800476f8  push    r12
0x1800476fa  push    r13
0x1800476fc  push    r14
0x1800476fe  lea     rbp, [rsp-37h]
0x180047703  sub     rsp, 90h
0x18004770a  mov     rax, cs:__security_cookie
0x180047711  xor     rax, rsp
0x180047714  mov     [rbp+57h+var_30], rax
0x180047718  mov     rdi, rcx
0x18004771b  xor     r13d, r13d
0x18004771e  mov     [rbp+57h+string], r13
0x180047722  lea     rbx, [rcx+430h]
0x180047729  mov     rcx, rbx; lpCriticalSection
0x18004772c  call    cs:__imp_EnterCriticalSection
0x180047732  mov     [rbp+57h+var_70], rbx
0x180047736  lea     rbx, [rdi+420h]
0x18004773d  xor     edx, edx; HSTRING
0x18004773f  mov     rcx, [rbx]; this
0x180047742  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x180047747  test    eax, eax
0x180047749  jnz     short loc_180047762
0x18004774b  cmp     dword ptr [rdi+410h], 0FFFFFFFEh
0x180047752  jnz     short loc_180047762
0x180047754  lea     rcx, [rbp+57h+var_70]; this
0x180047758  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x18004775d  jmp     loc_1800479AB
0x180047762  xor     edx, edx; HSTRING
0x180047764  mov     rcx, [rbx]; this
0x180047767  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x18004776c  test    eax, eax
0x18004776e  jz      loc_18004782F
0x180047774  mov     rcx, [rbp+57h+string]; string
0x180047778  call    cs:__imp_WindowsDeleteString
0x18004777e  mov     [rbp+57h+string], r13
0x180047782  mov     [rbp+57h+trimString], r13
0x180047786  mov     esi, 2
0x18004778b  lea     r9d, [rsi-1]; unsigned int
0x18004778f  mov     r8d, esi; unsigned int
0x180047792  lea     rdx, asc_180108014; " "
0x180047799  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18004779d  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800477a2  lea     r8, [rbp+57h+string]; newString
0x1800477a6  mov     rdx, [rbp+57h+trimString]; trimString
0x1800477aa  mov     rcx, [rbx]; string
0x1800477ad  call    cs:__imp_WindowsTrimStringStart
0x1800477b3  mov     [rbp+57h+trimString], r13
0x1800477b7  mov     rax, [rbp+57h+string]
0x1800477bb  mov     [rbp+57h+var_88], rax
0x1800477bf  lea     rdx, [rbp+57h+var_88]; HSTRING *
0x1800477c3  mov     rcx, rbx; newString
0x1800477c6  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x1800477cb  mov     rcx, [rbp+57h+string]; string
0x1800477cf  call    cs:__imp_WindowsDeleteString
0x1800477d5  mov     [rbp+57h+string], r13
0x1800477d9  mov     [rbp+57h+trimString], r13
0x1800477dd  lea     r9d, [rsi-1]; unsigned int
0x1800477e1  mov     r8d, esi; unsigned int
0x1800477e4  lea     rdx, asc_180108014; " "
0x1800477eb  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800477ef  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800477f4  lea     r8, [rbp+57h+string]; newString
0x1800477f8  mov     rdx, [rbp+57h+trimString]; trimString
0x1800477fc  mov     rcx, [rbx]; string
0x1800477ff  call    cs:__imp_WindowsTrimStringEnd
0x180047805  mov     [rbp+57h+trimString], r13
0x180047809  mov     rax, [rbp+57h+string]
0x18004780d  mov     [rbp+57h+var_88], rax
0x180047811  lea     rcx, [rdi+418h]; newString
0x180047818  lea     rdx, [rbp+57h+var_88]; HSTRING *
0x18004781c  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x180047821  mov     rcx, [rbx]; string
0x180047824  call    cs:__imp_WindowsDeleteString
0x18004782a  mov     [rbx], r13
0x18004782d  jmp     short loc_180047847
0x18004782f  mov     rax, [rdi+418h]
0x180047836  mov     [rbp+57h+var_88], rax
0x18004783a  lea     rdx, [rbp+57h+var_88]; HSTRING *
0x18004783e  lea     rcx, [rbp+57h+string]; newString
0x180047842  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x180047847  mov     eax, [rdi+410h]
0x18004784d  cmp     eax, 0FFFFFFFEh
0x180047850  jz      short loc_180047880
0x180047852  mov     [rdi+40Ch], eax
0x180047858  mov     dword ptr [rdi+410h], 0FFFFFFFEh
0x180047862  lea     rdx, aIsdriveselecte; "IsDriveSelected"
0x180047869  mov     rcx, rdi; this
0x18004786c  call    ?OnValueChanged@CSettingBase@DataModel@SystemSettings@@QEAAXPEBG@Z; SystemSettings::DataModel::CSettingBase::OnValueChanged(ushort const *)
0x180047871  lea     rdx, aDiskfreespace; "DiskFreeSpace"
0x180047878  mov     rcx, rdi; this
0x18004787b  call    ?OnValueChanged@CSettingBase@DataModel@SystemSettings@@QEAAXPEBG@Z; SystemSettings::DataModel::CSettingBase::OnValueChanged(ushort const *)
0x180047880  mov     r12d, [rdi+40Ch]
0x180047887  lea     rcx, [rbp+57h+var_68]
0x18004788b  call    SystemSettings__StorageSenseHandlers__SortModes
0x180047890  nop
0x180047891  movsxd  rcx, dword ptr [rdi+400h]
0x180047898  add     rcx, rcx
0x18004789b  mov     rax, [rbp+57h+var_68]
0x18004789f  lea     rdx, ?compareSizeDescending@@YAHPEBX0@Z; compareSizeDescending(void const *,void const *)
0x1800478a6  cmp     [rax+rcx*8+8], rdx
0x1800478ab  jz      short loc_1800478BE
0x1800478ad  mov     r14b, r13b
0x1800478b0  lea     rdx, ?compareSizeAscending@@YAHPEBX0@Z; compareSizeAscending(void const *,void const *)
0x1800478b7  cmp     [rax+rcx*8+8], rdx
0x1800478bc  jnz     short loc_1800478C1
0x1800478be  mov     r14b, 1
0x1800478c1  lea     rcx, [rbp+57h+var_70]; this
0x1800478c5  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x1800478ca  lea     rbx, [rdi+458h]
0x1800478d1  mov     rcx, rbx; lpCriticalSection
0x1800478d4  call    cs:__imp_EnterCriticalSection
0x1800478da  mov     [rbp+57h+var_88], rbx
0x1800478de  test    r14b, r14b
0x1800478e1  jz      short loc_1800478F9
0x1800478e3  mov     byte ptr [rdi+324h], 1
0x1800478ea  lea     rdx, stru_18010B738; unsigned __int16 *
0x1800478f1  mov     rcx, rdi; this
0x1800478f4  call    ?OnValueChanged@CSettingBase@DataModel@SystemSettings@@QEAAXPEBG@Z; SystemSettings::DataModel::CSettingBase::OnValueChanged(ushort const *)
0x1800478f9  mov     [rbp+57h+var_78], r13
0x1800478fd  mov     [rbp+57h+var_80], r13d
0x180047901  lea     rdx, [rbp+57h+var_80]
0x180047905  mov     rcx, [rdi+0D0h]
0x18004790c  call    ?get_Size@?$Vector@PEAUISettingItem@DataModel@SystemSettings@@U?$DefaultEqualityPredicate@PEAUISettingItem@DataModel@SystemSettings@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUISettingItem@DataModel@SystemSettings@@@5678@U?$VectorOptions@PEAUISettingItem@DataModel@SystemSettings@@$00$00$0A@@5678@@Internal@Collections@Foundation@Windows@@UEAAJPEAI@Z; Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::get_Size(uint *)
0x180047911  mov     [rdi+320h], r13d
0x180047918  mov     esi, r13d
0x18004791b  cmp     [rbp+57h+var_80], r13d
0x18004791f  jbe     short loc_180047968
0x180047921  mov     rbx, [rdi+0D0h]
0x180047928  lea     rcx, [rbp+57h+var_78]
0x18004792c  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x180047931  lea     r8, [rbp+57h+var_78]
0x180047935  mov     edx, esi
0x180047937  mov     rcx, rbx
0x18004793a  call    ?GetAt@?$Vector@PEAUISettingItem@DataModel@SystemSettings@@U?$DefaultEqualityPredicate@PEAUISettingItem@DataModel@SystemSettings@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUISettingItem@DataModel@SystemSettings@@@5678@U?$VectorOptions@PEAUISettingItem@DataModel@SystemSettings@@$00$00$0A@@5678@@Internal@Collections@Foundation@Windows@@UEAAJIPEAPEAUISettingItem@DataModel@SystemSettings@@@Z; Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::GetAt(uint,SystemSettings::DataModel::ISettingItem * *)
0x18004793f  mov     r9d, r12d; int
0x180047942  mov     r8, [rbp+57h+string]; HSTRING
0x180047946  mov     rdx, [rbp+57h+var_78]; struct SystemSettings::StorageSenseHandlers::CPackageSizeSetting *
0x18004794a  call    ?_UpdateAppVisibility@CAppSizesList@StorageSenseHandlers@SystemSettings@@AEAA_NPEAVCPackageSizeSetting@23@PEAUHSTRING__@@H@Z; SystemSettings::StorageSenseHandlers::CAppSizesList::_UpdateAppVisibility(SystemSettings::StorageSenseHandlers::CPackageSizeSetting *,HSTRING__ *,int)
0x18004794f  test    al, al
0x180047951  jz      short loc_180047959
0x180047953  inc     dword ptr [rdi+320h]
0x180047959  mov     rcx, rdi; this
0x18004795c  call    ?NotifyTotalAppsUpdated@CAppSizesList@StorageSenseHandlers@SystemSettings@@AEAAXXZ; SystemSettings::StorageSenseHandlers::CAppSizesList::NotifyTotalAppsUpdated(void)
0x180047961  inc     esi
0x180047963  cmp     esi, [rbp+57h+var_80]
0x180047966  jb      short loc_180047921
0x180047968  lea     rcx, [rbp+57h+var_88]; this
0x18004796c  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x180047971  test    r14b, r14b
0x180047974  jz      short loc_18004798D
0x180047976  mov     [rdi+324h], r13b
0x18004797d  lea     rdx, stru_18010B738; unsigned __int16 *
0x180047984  mov     rcx, rdi; this
0x180047987  call    ?OnValueChanged@CSettingBase@DataModel@SystemSettings@@QEAAXPEBG@Z; SystemSettings::DataModel::CSettingBase::OnValueChanged(ushort const *)
0x18004798c  nop
0x18004798d  lea     rcx, [rbp+57h+var_78]
0x180047991  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x180047996  nop
0x180047997  lea     rcx, [rbp+57h+var_88]; this
0x18004799b  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x1800479a0  nop
0x1800479a1  lea     rcx, [rbp+57h+var_68]
0x1800479a5  call    ?_Tidy@?$vector@UAppSortModes@StorageSenseHandlers@SystemSettings@@V?$allocator@UAppSortModes@StorageSenseHandlers@SystemSettings@@@std@@@std@@AEAAXXZ; std::vector<SystemSettings::StorageSenseHandlers::AppSortModes>::_Tidy(void)
0x1800479aa  nop
0x1800479ab  lea     rcx, [rbp+57h+var_70]; this
0x1800479af  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x1800479b4  nop
0x1800479b5  mov     rcx, [rbp+57h+string]; string
0x1800479b9  call    cs:__imp_WindowsDeleteString
0x1800479bf  xor     eax, eax
0x1800479c1  mov     rcx, [rbp+57h+var_30]
0x1800479c5  xor     rcx, rsp; StackCookie
0x1800479c8  call    __security_check_cookie
0x1800479cd  lea     r11, [rsp+0B0h+var_20]
0x1800479d5  mov     rbx, [r11+38h]
0x1800479d9  mov     rsi, [r11+40h]
0x1800479dd  mov     rsp, r11
0x1800479e0  pop     r14
0x1800479e2  pop     r13
0x1800479e4  pop     r12
0x1800479e6  pop     rdi
0x1800479e7  pop     rbp
0x1800479e8  retn
```
