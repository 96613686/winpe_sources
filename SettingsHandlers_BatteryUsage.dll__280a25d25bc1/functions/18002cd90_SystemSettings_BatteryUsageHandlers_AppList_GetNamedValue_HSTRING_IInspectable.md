# SystemSettings::BatteryUsageHandlers::AppList::GetNamedValue(HSTRING__ *,IInspectable * *)

- ea: `0x18002cd90`
- end: `0x18002cfe1`
- name: `?GetNamedValue@AppList@BatteryUsageHandlers@SystemSettings@@UEAAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z`
- size: `593`
- prototype: `int(SystemSettings::BatteryUsageHandlers::AppList *__hidden this, HSTRING, struct IInspectable **)`
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, loader_planting`

## callees

- `0x1800033a0`
- `0x18000a13c`
- `0x18000ef50`
- `0x18000fa78`
- `0x1800150cc`
- `0x180015108`
- `0x1800177e0`
- `0x180017834`
- `0x180019b4c`
- `0x180019c5c`
- `0x18001c4d4`
- `0x18001e4a0`
- `0x18001e860`
- `0x18002cd90`
- `0x1800403c4`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsPromoteStringBuffer` at `0x18002cf0a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPromoteStringBuffer` at `0x18002cf0a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPreallocateStringBuffer` at `0x18002cea4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsPreallocateStringBuffer` at `0x18002cea4`

## string_xrefs

- `0x18002cfac`: `SystemSettings_BatterySaver_ListEmpty_Usage`
- `0x18002cf9a`: `SystemSettings_BatterySaver_ListEmpty_Always`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SystemSettings::BatteryUsageHandlers::AppList::GetNamedValue(
        SystemSettings::BatteryUsageHandlers::AppList *this,
        SystemSettings::DataModel *a2,
        struct IInspectable **a3)
{
  const unsigned __int16 *v6; // r8
  __int64 v7; // rcx
  HRESULT Size; // ebx
  __int64 v9; // rdx
  int v10; // eax
  int ResourceStringValue; // edi
  __int64 v12; // rdx
  __int64 v14; // rax
  SystemSettings::BatteryUsageHandlers::UsageDataSingleton *v15; // rcx
  const unsigned __int16 *v16; // rcx
  HSTRING string; // [rsp+20h] [rbp-50h] BYREF
  __int64 v18; // [rsp+28h] [rbp-48h] BYREF
  _QWORD v19[3]; // [rsp+38h] [rbp-38h] BYREF
  _BYTE v20[32]; // [rsp+50h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]
  WCHAR *charBuffer; // [rsp+A0h] [rbp+30h] BYREF
  HSTRING_BUFFER bufferHandle; // [rsp+A8h] [rbp+38h] BYREF

  *a3 = 0;
  if ( !SystemSettings::DataModel::IsHstringEqual(a2, (const WCHAR *)&stru_180068410, (const unsigned __int16 *)a3) )
  {
    if ( !SystemSettings::DataModel::IsHstringEqual(a2, (const WCHAR *)&stru_180068498, v6) )
      return (unsigned int)SystemSettings::DataModel::CDataSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::GetNamedValue(
                             this,
                             a2,
                             a3);
    LODWORD(charBuffer) = 0;
    LODWORD(bufferHandle) = 0;
    Size = Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::get_Size(
             *((_QWORD *)this + 26),
             &charBuffer);
    if ( Size < 0 )
    {
      v9 = 90;
      goto LABEL_5;
    }
    Size = SystemSettings::BatteryUsageHandlers::UsageDataSingleton::GetAppSource(v15, (unsigned int *)&bufferHandle);
    if ( Size < 0 )
    {
      v9 = 92;
      goto LABEL_5;
    }
    if ( (_DWORD)bufferHandle == 2 )
    {
      if ( (_DWORD)charBuffer )
        return 0;
      v16 = L"SystemSettings_BatterySaver_ListEmpty_Always";
    }
    else
    {
      if ( (_DWORD)bufferHandle || (_DWORD)charBuffer )
        return 0;
      v16 = L"SystemSettings_BatterySaver_ListEmpty_Usage";
    }
    SystemSettings::DataModel::PropValueHelper::CreateString(v16, a3);
    return 0;
  }
  LODWORD(charBuffer) = 0;
  v7 = *((_QWORD *)this + 26);
  if ( !v7 )
    return 0;
  Size = Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::get_Size(
           v7,
           &charBuffer);
  if ( Size < 0 )
  {
    v9 = 47;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\applist.cpp",
      (const char *)(unsigned int)Size,
      (int)string);
    return (unsigned int)Size;
  }
  Size = 0;
  if ( !(_DWORD)charBuffer )
    return (unsigned int)Size;
  v10 = *((_DWORD *)this + 154);
  if ( !v10 )
  {
    ResourceStringValue = SystemSettings::DataModel::BatteryUsageHelper::GetResourceStringValue(0x2417u, a3);
    if ( ResourceStringValue >= 0 )
      return (unsigned int)Size;
    v12 = 53;
LABEL_10:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\applist.cpp",
      (const char *)(unsigned int)ResourceStringValue,
      (int)string);
    return (unsigned int)ResourceStringValue;
  }
  if ( v10 != 1 )
  {
    std::vector<std::future<std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity,SystemSettings::BatteryUsageHandlers::AppStaticInfo>>>::vector<std::future<std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity,SystemSettings::BatteryUsageHandlers::AppStaticInfo>>>(v19);
    charBuffer = 0;
    bufferHandle = 0;
    string = 0;
    Size = WindowsPreallocateStringBuffer(0x100u, &charBuffer, &bufferHandle);
    if ( Size >= 0 )
    {
      memset_0(charBuffer, 0, 0x200u);
      Size = SystemSettings::DataModel::BatteryUsageHelper::GetResourceString(0x2419u);
      if ( Size >= 0 )
      {
        v18 = *((unsigned int *)this + 154);
        v14 = std::vector<unsigned short>::vector<unsigned short>(v20, v19);
        Size = SystemSettings::DataModel::BatteryUsageHelper::PrepResourceString(v14, &charBuffer, &v18);
        if ( Size >= 0 )
        {
          Size = WindowsPromoteStringBuffer(bufferHandle, &string);
          if ( Size >= 0 )
            Size = SystemSettings::DataModel::PropValueHelper::CreateString(string, a3);
        }
      }
    }
    std::vector<unsigned short>::_Tidy(v19);
    return (unsigned int)Size;
  }
  ResourceStringValue = SystemSettings::DataModel::BatteryUsageHelper::GetResourceStringValue(0x2418u, a3);
  if ( ResourceStringValue < 0 )
  {
    v12 = 57;
    goto LABEL_10;
  }
  return (unsigned int)Size;
}

```

## disassembly

```asm
0x18002cd90  mov     [rsp-18h+arg_0], rbx
0x18002cd95  push    rbp
0x18002cd96  push    rsi
0x18002cd97  push    rdi
0x18002cd98  mov     rbp, rsp
0x18002cd9b  sub     rsp, 70h
0x18002cd9f  mov     rdi, r8
0x18002cda2  mov     rbx, rdx
0x18002cda5  mov     rsi, rcx
0x18002cda8  mov     qword ptr [r8], 0
0x18002cdaf  lea     rdx, stru_180068410; HSTRING
0x18002cdb6  mov     rcx, rbx; this
0x18002cdb9  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x18002cdbe  test    al, al
0x18002cdc0  jz      loc_18002CF32
0x18002cdc6  mov     dword ptr [rbp+charBuffer], 0
0x18002cdcd  mov     rcx, [rsi+0D0h]
0x18002cdd4  test    rcx, rcx
0x18002cdd7  jz      loc_18002CFBB
0x18002cddd  lea     rdx, [rbp+charBuffer]
0x18002cde1  call    ?get_Size@?$Vector@PEAUISettingItem@DataModel@SystemSettings@@U?$DefaultEqualityPredicate@PEAUISettingItem@DataModel@SystemSettings@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUISettingItem@DataModel@SystemSettings@@@5678@U?$VectorOptions@PEAUISettingItem@DataModel@SystemSettings@@$00$00$0A@@5678@@Internal@Collections@Foundation@Windows@@UEAAJPEAI@Z; Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::get_Size(uint *)
0x18002cde6  mov     ebx, eax
0x18002cde8  test    eax, eax
0x18002cdea  jns     short loc_18002CE09
0x18002cdec  mov     edx, 2Fh ; '/'; void *
0x18002cdf1  mov     rcx, [rbp+18h]; this
0x18002cdf5  mov     r9d, ebx; char *
0x18002cdf8  lea     r8, aOnecoreuapShel_21; "onecoreuap\\shell\\coresettinghandlers"...
0x18002cdff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ce04  jmp     loc_18002CFCF
0x18002ce09  xor     ebx, ebx
0x18002ce0b  cmp     dword ptr [rbp+charBuffer], ebx
0x18002ce0e  jz      loc_18002CFCF
0x18002ce14  mov     eax, [rsi+268h]
0x18002ce1a  test    eax, eax
0x18002ce1c  jnz     short loc_18002CE52
0x18002ce1e  mov     rdx, rdi; struct IInspectable **
0x18002ce21  mov     ecx, 2417h; unsigned int
0x18002ce26  call    ?GetResourceStringValue@BatteryUsageHelper@DataModel@SystemSettings@@SAJIPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::BatteryUsageHelper::GetResourceStringValue(uint,IInspectable * *)
0x18002ce2b  mov     edi, eax
0x18002ce2d  test    eax, eax
0x18002ce2f  jns     loc_18002CFCF
0x18002ce35  lea     edx, [rbx+35h]; void *
0x18002ce38  lea     r8, aOnecoreuapShel_21; "onecoreuap\\shell\\coresettinghandlers"...
0x18002ce3f  mov     r9d, edi; char *
0x18002ce42  mov     rcx, [rbp+18h]; this
0x18002ce46  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ce4b  mov     eax, edi
0x18002ce4d  jmp     loc_18002CFD1
0x18002ce52  cmp     eax, 1
0x18002ce55  jnz     short loc_18002CE75
0x18002ce57  mov     rdx, rdi; struct IInspectable **
0x18002ce5a  mov     ecx, 2418h; unsigned int
0x18002ce5f  call    ?GetResourceStringValue@BatteryUsageHelper@DataModel@SystemSettings@@SAJIPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::BatteryUsageHelper::GetResourceStringValue(uint,IInspectable * *)
0x18002ce64  mov     edi, eax
0x18002ce66  test    eax, eax
0x18002ce68  jns     loc_18002CFCF
0x18002ce6e  mov     edx, 39h ; '9'
0x18002ce73  jmp     short loc_18002CE38
0x18002ce75  lea     rcx, [rbp+var_38]
0x18002ce79  call    ??0?$vector@V?$future@U?$pair@UAppIdentity@BatteryUsageHandlers@SystemSettings@@UAppStaticInfo@23@@std@@@std@@V?$allocator@V?$future@U?$pair@UAppIdentity@BatteryUsageHandlers@SystemSettings@@UAppStaticInfo@23@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::future<std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity,SystemSettings::BatteryUsageHandlers::AppStaticInfo>>>::vector<std::future<std::pair<SystemSettings::BatteryUsageHandlers::AppIdentity,SystemSettings::BatteryUsageHandlers::AppStaticInfo>>>(void)
0x18002ce7e  nop
0x18002ce7f  mov     [rbp+charBuffer], 0
0x18002ce87  mov     [rbp+bufferHandle], 0
0x18002ce8f  mov     [rbp+string], 0
0x18002ce97  lea     r8, [rbp+bufferHandle]; bufferHandle
0x18002ce9b  lea     rdx, [rbp+charBuffer]; charBuffer
0x18002ce9f  mov     ecx, 100h; length
0x18002cea4  call    cs:__imp_WindowsPreallocateStringBuffer
0x18002ceaa  mov     ebx, eax
0x18002ceac  test    eax, eax
0x18002ceae  js      short loc_18002CF24
0x18002ceb0  xor     edx, edx; Val
0x18002ceb2  mov     r8d, 200h; Size
0x18002ceb8  mov     rcx, [rbp+charBuffer]; void *
0x18002cebc  call    memset_0
0x18002cec1  lea     rdx, [rbp+var_38]
0x18002cec5  mov     ecx, 2419h; uID
0x18002ceca  call    ?GetResourceString@BatteryUsageHelper@DataModel@SystemSettings@@SAJIAEAV?$vector@GV?$allocator@G@std@@@std@@@Z; SystemSettings::DataModel::BatteryUsageHelper::GetResourceString(uint,std::vector<ushort> &)
0x18002cecf  mov     ebx, eax
0x18002ced1  test    eax, eax
0x18002ced3  js      short loc_18002CF24
0x18002ced5  mov     eax, [rsi+268h]
0x18002cedb  mov     [rbp+var_48], rax
0x18002cedf  lea     rdx, [rbp+var_38]
0x18002cee3  lea     rcx, [rbp+var_20]
0x18002cee7  call    ??0?$vector@GV?$allocator@G@std@@@std@@QEAA@AEBV01@@Z; std::vector<ushort>::vector<ushort>(std::vector<ushort> const &)
0x18002ceec  lea     r8, [rbp+var_48]
0x18002cef0  lea     rdx, [rbp+charBuffer]
0x18002cef4  mov     rcx, rax
0x18002cef7  call    ?PrepResourceString@BatteryUsageHelper@DataModel@SystemSettings@@SAJV?$vector@GV?$allocator@G@std@@@std@@PEAPEAGQEAPEAX@Z; SystemSettings::DataModel::BatteryUsageHelper::PrepResourceString(std::vector<ushort>,ushort * *,void * * const)
0x18002cefc  mov     ebx, eax
0x18002cefe  test    eax, eax
0x18002cf00  js      short loc_18002CF24
0x18002cf02  lea     rdx, [rbp+string]; string
0x18002cf06  mov     rcx, [rbp+bufferHandle]; bufferHandle
0x18002cf0a  call    cs:__imp_WindowsPromoteStringBuffer
0x18002cf10  mov     ebx, eax
0x18002cf12  test    eax, eax
0x18002cf14  js      short loc_18002CF24
0x18002cf16  mov     rdx, rdi; struct IInspectable **
0x18002cf19  mov     rcx, [rbp+string]; HSTRING
0x18002cf1d  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(HSTRING__ *,IInspectable * *)
0x18002cf22  mov     ebx, eax
0x18002cf24  lea     rcx, [rbp+var_38]
0x18002cf28  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x18002cf2d  jmp     loc_18002CFCF
0x18002cf32  lea     rdx, stru_180068498; HSTRING
0x18002cf39  mov     rcx, rbx; this
0x18002cf3c  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x18002cf41  test    al, al
0x18002cf43  jz      short loc_18002CFBF
0x18002cf45  mov     dword ptr [rbp+charBuffer], 0
0x18002cf4c  mov     dword ptr [rbp+bufferHandle], 0
0x18002cf53  lea     rdx, [rbp+charBuffer]
0x18002cf57  mov     rcx, [rsi+0D0h]
0x18002cf5e  call    ?get_Size@?$Vector@PEAUISettingItem@DataModel@SystemSettings@@U?$DefaultEqualityPredicate@PEAUISettingItem@DataModel@SystemSettings@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUISettingItem@DataModel@SystemSettings@@@5678@U?$VectorOptions@PEAUISettingItem@DataModel@SystemSettings@@$00$00$0A@@5678@@Internal@Collections@Foundation@Windows@@UEAAJPEAI@Z; Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::get_Size(uint *)
0x18002cf63  mov     ebx, eax
0x18002cf65  test    eax, eax
0x18002cf67  jns     short loc_18002CF73
0x18002cf69  mov     edx, 5Ah ; 'Z'
0x18002cf6e  jmp     loc_18002CDF1
0x18002cf73  lea     rdx, [rbp+bufferHandle]; unsigned int *
0x18002cf77  call    ?GetAppSource@UsageDataSingleton@BatteryUsageHandlers@SystemSettings@@QEAAJPEAK@Z; SystemSettings::BatteryUsageHandlers::UsageDataSingleton::GetAppSource(ulong *)
0x18002cf7c  mov     ebx, eax
0x18002cf7e  test    eax, eax
0x18002cf80  jns     short loc_18002CF8C
0x18002cf82  mov     edx, 5Ch ; '\'
0x18002cf87  jmp     loc_18002CDF1
0x18002cf8c  mov     eax, dword ptr [rbp+bufferHandle]
0x18002cf8f  cmp     eax, 2
0x18002cf92  jnz     short loc_18002CFA3
0x18002cf94  cmp     dword ptr [rbp+charBuffer], 0
0x18002cf98  jnz     short loc_18002CFBB
0x18002cf9a  lea     rcx, aSystemsettings_4; "SystemSettings_BatterySaver_ListEmpty_A"...
0x18002cfa1  jmp     short loc_18002CFB3
0x18002cfa3  test    eax, eax
0x18002cfa5  jnz     short loc_18002CFBB
0x18002cfa7  cmp     dword ptr [rbp+charBuffer], eax
0x18002cfaa  jnz     short loc_18002CFBB
0x18002cfac  lea     rcx, aSystemsettings_34; "SystemSettings_BatterySaver_ListEmpty_U"...
0x18002cfb3  mov     rdx, rdi; struct IInspectable **
0x18002cfb6  call    ?CreateString@PropValueHelper@DataModel@SystemSettings@@SAJPEBGPEAPEAUIInspectable@@@Z; SystemSettings::DataModel::PropValueHelper::CreateString(ushort const *,IInspectable * *)
0x18002cfbb  xor     ebx, ebx
0x18002cfbd  jmp     short loc_18002CFCF
0x18002cfbf  mov     r8, rdi
0x18002cfc2  mov     rdx, rbx
0x18002cfc5  mov     rcx, rsi
0x18002cfc8  call    ?GetNamedValue@?$CDataSettingBase@P6AJPEBUSettingDBItem@DataModel@SystemSettings@@PEAPEAUISettingItem@23@@Z@DataModel@SystemSettings@@MEAAJPEAUHSTRING__@@PEAPEAUIInspectable@@@Z; SystemSettings::DataModel::CDataSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::GetNamedValue(HSTRING__ *,IInspectable * *)
0x18002cfcd  mov     ebx, eax
0x18002cfcf  mov     eax, ebx
0x18002cfd1  mov     rbx, [rsp+70h+arg_0]
0x18002cfd9  add     rsp, 70h
0x18002cfdd  pop     rdi
0x18002cfde  pop     rsi
0x18002cfdf  pop     rbp
0x18002cfe0  retn
```
