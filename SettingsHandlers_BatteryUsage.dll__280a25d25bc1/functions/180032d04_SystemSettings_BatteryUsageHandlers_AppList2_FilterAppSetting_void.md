# SystemSettings::BatteryUsageHandlers::AppList2::_FilterAppSetting(void)

- ea: `0x180032d04`
- end: `0x180032eca`
- name: `?_FilterAppSetting@AppList2@BatteryUsageHandlers@SystemSettings@@AEAAJXZ`
- size: `454`
- prototype: `__int64 __fastcall(SystemSettings::BatteryUsageHandlers::AppList2 *__hidden this)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180032830`
- `0x1800334f0`

## callees

- `0x180004cfc`
- `0x18000a13c`
- `0x18001e860`
- `0x180022c0c`
- `0x180028198`
- `0x18002c7c0`
- `0x18002e2b0`
- `0x180030ec8`
- `0x180032d04`
- `0x180040354`

## import_xrefs

- `msvcp_win!_Xtime_get_ticks` at `0x180032d13`
- `msvcp_win!_Xtime_get_ticks` at `0x180032dd1`
- `msvcp_win!_Xtime_get_ticks` at `0x180032d13`
- `msvcp_win!_Xtime_get_ticks` at `0x180032dd1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180032e33`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180032e96`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180032e33`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180032e96`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180032e60`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180032e60`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SystemSettings::BatteryUsageHandlers::AppList2::_FilterAppSetting(
        SystemSettings::BatteryUsageHandlers::AppList2 *this)
{
  __int64 ticks; // r15
  SystemSettings::BatteryUsageHandlers::UsageDataSingleton2 *v3; // rcx
  int AppSearchString; // eax
  unsigned int v5; // ebx
  __int64 result; // rax
  unsigned int v7; // edi
  __int64 v8; // rbx
  SystemSettings::BatteryUsageHandlers::AppList *v9; // rcx
  int v10; // eax
  unsigned int v11; // ebx
  const char *v12; // r9
  HSTRING v13; // [rsp+20h] [rbp-48h] BYREF
  PCWSTR StringRawBuffer; // [rsp+28h] [rbp-40h] BYREF
  _QWORD v15[7]; // [rsp+30h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  unsigned int v17; // [rsp+78h] [rbp+10h] BYREF
  HSTRING string; // [rsp+80h] [rbp+18h] BYREF
  struct SystemSettings::BatteryUsageHandlers::AppListEntry *v19; // [rsp+88h] [rbp+20h] BYREF

  ticks = _Xtime_get_ticks();
  v13 = 0;
  AppSearchString = SystemSettings::BatteryUsageHandlers::UsageDataSingleton2::GetAppSearchString(v3, &v13);
  v5 = AppSearchString;
  if ( AppSearchString >= 0 )
  {
    v19 = 0;
    v17 = 0;
    Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::get_Size(
      *((_QWORD *)this + 26),
      &v17);
    *((_DWORD *)this + 186) = 0;
    v7 = 0;
    try
    {
      while ( v7 < v17 )
      {
        v8 = *((_QWORD *)this + 26);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
        Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::GetAt(
          v8,
          v7,
          &v19);
        if ( SystemSettings::BatteryUsageHandlers::AppList::_UpdateAppVisibility(v9, v19, v13) )
          ++*((_DWORD *)this + 186);
        ++v7;
      }
      StringRawBuffer = (PCWSTR)(_Xtime_get_ticks() - ticks);
      std::chrono::duration<double,std::ratio<1,1>>::duration<double,std::ratio<1,1>>(v15, &StringRawBuffer);
      string = 0;
      v10 = Microsoft::WRL::Wrappers::HString::Set(&string, &v13);
      v11 = v10;
      if ( v10 >= 0 )
      {
        StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
        UsageGraphTelemetry::AppUsageListFiltered<double,unsigned short const *,unsigned int &,unsigned int &>(
          v15,
          &StringRawBuffer,
          &v17,
          (char *)this + 744);
        WindowsDeleteString(string);
        string = 0;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
        result = 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x230,
          (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\applist2.cpp",
          (const char *)(unsigned int)v10,
          (int)v13);
        WindowsDeleteString(string);
        string = 0;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
        result = v11;
      }
    }
    catch ( ... )
    {
      return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                             retaddr,
                             (void *)0x23A,
                             (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\applist2.cpp",
                             v12);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x21A,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\applist2.cpp",
      (const char *)(unsigned int)AppSearchString,
      (int)v13);
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x180032d04  push    rbx
0x180032d06  push    rsi
0x180032d07  push    rdi
0x180032d08  push    r14
0x180032d0a  push    r15
0x180032d0c  sub     rsp, 40h
0x180032d10  mov     r14, rcx
0x180032d13  call    cs:__imp__Xtime_get_ticks
0x180032d19  mov     r15, rax
0x180032d1c  mov     [rsp+68h+var_48], 0; int
0x180032d25  lea     rdx, [rsp+68h+var_48]; HSTRING *
0x180032d2a  call    ?GetAppSearchString@UsageDataSingleton2@BatteryUsageHandlers@SystemSettings@@QEAAJPEAPEAUHSTRING__@@@Z; SystemSettings::BatteryUsageHandlers::UsageDataSingleton2::GetAppSearchString(HSTRING__ * *)
0x180032d2f  mov     ebx, eax
0x180032d31  test    eax, eax
0x180032d33  jns     short loc_180032D55
0x180032d35  mov     rcx, [rsp+68h]; this
0x180032d3a  mov     r9d, eax; char *
0x180032d3d  lea     r8, aOnecoreuapShel_18; "onecoreuap\\shell\\coresettinghandlers"...
0x180032d44  mov     edx, 21Ah; void *
0x180032d49  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180032d4e  mov     eax, ebx
0x180032d50  jmp     loc_180032EBD
0x180032d55  mov     [rsp+68h+arg_18], 0
0x180032d61  mov     [rsp+68h+arg_8], 0
0x180032d69  lea     rdx, [rsp+68h+arg_8]
0x180032d6e  mov     rcx, [r14+0D0h]
0x180032d75  call    ?get_Size@?$Vector@PEAUISettingItem@DataModel@SystemSettings@@U?$DefaultEqualityPredicate@PEAUISettingItem@DataModel@SystemSettings@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUISettingItem@DataModel@SystemSettings@@@5678@U?$VectorOptions@PEAUISettingItem@DataModel@SystemSettings@@$00$00$0A@@5678@@Internal@Collections@Foundation@Windows@@UEAAJPEAI@Z; Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::get_Size(uint *)
0x180032d7a  lea     rsi, [r14+2E8h]
0x180032d81  mov     dword ptr [rsi], 0
0x180032d87  xor     edi, edi
0x180032d89  cmp     edi, [rsp+68h+arg_8]
0x180032d8d  jnb     short loc_180032DD1
0x180032d8f  mov     rbx, [r14+0D0h]
0x180032d96  lea     rcx, [rsp+68h+arg_18]
0x180032d9e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180032da3  lea     r8, [rsp+68h+arg_18]
0x180032dab  mov     edx, edi
0x180032dad  mov     rcx, rbx
0x180032db0  call    ?GetAt@?$Vector@PEAUISettingItem@DataModel@SystemSettings@@U?$DefaultEqualityPredicate@PEAUISettingItem@DataModel@SystemSettings@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUISettingItem@DataModel@SystemSettings@@@5678@U?$VectorOptions@PEAUISettingItem@DataModel@SystemSettings@@$00$00$0A@@5678@@Internal@Collections@Foundation@Windows@@UEAAJIPEAPEAUISettingItem@DataModel@SystemSettings@@@Z; Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::GetAt(uint,SystemSettings::DataModel::ISettingItem * *)
0x180032db5  mov     r8, [rsp+68h+var_48]; HSTRING
0x180032dba  mov     rdx, [rsp+68h+arg_18]; struct SystemSettings::BatteryUsageHandlers::AppListEntry *
0x180032dc2  call    ?_UpdateAppVisibility@AppList@BatteryUsageHandlers@SystemSettings@@AEAA_NPEAVAppListEntry@23@PEAUHSTRING__@@@Z; SystemSettings::BatteryUsageHandlers::AppList::_UpdateAppVisibility(SystemSettings::BatteryUsageHandlers::AppListEntry *,HSTRING__ *)
0x180032dc7  test    al, al
0x180032dc9  jz      short loc_180032DCD
0x180032dcb  inc     dword ptr [rsi]
0x180032dcd  inc     edi
0x180032dcf  jmp     short loc_180032D89
0x180032dd1  call    cs:__imp__Xtime_get_ticks
0x180032dd7  sub     rax, r15
0x180032dda  mov     [rsp+68h+var_40], rax
0x180032ddf  lea     rdx, [rsp+68h+var_40]
0x180032de4  lea     rcx, [rsp+68h+var_38]
0x180032de9  call    ??$?0_JU?$ratio@$00$0JIJGIA@@std@@$0A@@?$duration@NU?$ratio@$00$00@std@@@chrono@std@@QEAA@AEBV?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@12@@Z; std::chrono::duration<double,std::ratio<1,1>>::duration<double,std::ratio<1,1>>(std::chrono::duration<__int64,std::ratio<1,10000000>> const &)
0x180032dee  mov     [rsp+68h+string], 0
0x180032dfa  lea     rdx, [rsp+68h+var_48]; HSTRING *
0x180032dff  lea     rcx, [rsp+68h+string]; newString
0x180032e07  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x180032e0c  mov     ebx, eax
0x180032e0e  test    eax, eax
0x180032e10  jns     short loc_180032E56
0x180032e12  mov     rcx, [rsp+68h]; this
0x180032e17  mov     r9d, eax; char *
0x180032e1a  lea     r8, aOnecoreuapShel_18; "onecoreuap\\shell\\coresettinghandlers"...
0x180032e21  mov     edx, 230h; void *
0x180032e26  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180032e2b  mov     rcx, [rsp+68h+string]; string
0x180032e33  call    cs:__imp_WindowsDeleteString
0x180032e39  mov     [rsp+68h+string], 0
0x180032e45  lea     rcx, [rsp+68h+arg_18]
0x180032e4d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180032e52  mov     eax, ebx
0x180032e54  jmp     short loc_180032EBD
0x180032e56  xor     edx, edx; length
0x180032e58  mov     rcx, [rsp+68h+string]; string
0x180032e60  call    cs:__imp_WindowsGetStringRawBuffer
0x180032e66  mov     [rsp+68h+var_40], rax
0x180032e6b  movsd   xmm0, [rsp+68h+var_38]
0x180032e71  movsd   [rsp+68h+var_38], xmm0
0x180032e77  mov     r9, rsi
0x180032e7a  lea     r8, [rsp+68h+arg_8]
0x180032e7f  lea     rdx, [rsp+68h+var_40]
0x180032e84  lea     rcx, [rsp+68h+var_38]
0x180032e89  call    ??$AppUsageListFiltered@NPEBGAEAIAEAI@UsageGraphTelemetry@@SAX$$QEAN$$QEAPEBGAEAI2@Z; UsageGraphTelemetry::AppUsageListFiltered<double,ushort const *,uint &,uint &>(double &&,ushort const * &&,uint &,uint &)
0x180032e8e  mov     rcx, [rsp+68h+string]; string
0x180032e96  call    cs:__imp_WindowsDeleteString
0x180032e9c  mov     [rsp+68h+string], 0
0x180032ea8  lea     rcx, [rsp+68h+arg_18]
0x180032eb0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180032eb5  xor     eax, eax
0x180032eb7  jmp     short loc_180032EBD
0x180032eb9  mov     eax, [rsp+68h+arg_8]
0x180032ebd  add     rsp, 40h
0x180032ec1  pop     r15
0x180032ec3  pop     r14
0x180032ec5  pop     rdi
0x180032ec6  pop     rsi
0x180032ec7  pop     rbx
0x180032ec8  retn
```
