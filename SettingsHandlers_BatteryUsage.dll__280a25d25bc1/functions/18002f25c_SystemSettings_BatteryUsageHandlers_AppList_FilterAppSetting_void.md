# SystemSettings::BatteryUsageHandlers::AppList::_FilterAppSetting(void)

- ea: `0x18002f25c`
- end: `0x18002f422`
- name: `?_FilterAppSetting@AppList@BatteryUsageHandlers@SystemSettings@@AEAAJXZ`
- size: `454`
- prototype: `__int64 __fastcall(SystemSettings::BatteryUsageHandlers::AppList *__hidden this)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18002d320`
- `0x1800307bc`

## callees

- `0x180004cfc`
- `0x18000a13c`
- `0x18001e860`
- `0x180022c0c`
- `0x180028198`
- `0x18002c7c0`
- `0x18002e2b0`
- `0x18002f25c`
- `0x180030ec8`
- `0x18004038c`

## import_xrefs

- `msvcp_win!_Xtime_get_ticks` at `0x18002f26b`
- `msvcp_win!_Xtime_get_ticks` at `0x18002f329`
- `msvcp_win!_Xtime_get_ticks` at `0x18002f26b`
- `msvcp_win!_Xtime_get_ticks` at `0x18002f329`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002f38b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002f3ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002f38b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002f3ee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002f3b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002f3b8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SystemSettings::BatteryUsageHandlers::AppList::_FilterAppSetting(
        SystemSettings::BatteryUsageHandlers::AppList *this)
{
  __int64 ticks; // r15
  SystemSettings::BatteryUsageHandlers::UsageDataSingleton *v3; // rcx
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
  AppSearchString = SystemSettings::BatteryUsageHandlers::UsageDataSingleton::GetAppSearchString(v3, &v13);
  v5 = AppSearchString;
  if ( AppSearchString >= 0 )
  {
    v19 = 0;
    v17 = 0;
    Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::get_Size(
      *((_QWORD *)this + 26),
      &v17);
    *((_DWORD *)this + 154) = 0;
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
          ++*((_DWORD *)this + 154);
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
          (char *)this + 616);
        WindowsDeleteString(string);
        string = 0;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v19);
        result = 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1D2,
          (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\applist.cpp",
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
                             (void *)0x1DC,
                             (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\applist.cpp",
                             v12);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1BC,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\applist.cpp",
      (const char *)(unsigned int)AppSearchString,
      (int)v13);
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x18002f25c  push    rbx
0x18002f25e  push    rsi
0x18002f25f  push    rdi
0x18002f260  push    r14
0x18002f262  push    r15
0x18002f264  sub     rsp, 40h
0x18002f268  mov     r14, rcx
0x18002f26b  call    cs:__imp__Xtime_get_ticks
0x18002f271  mov     r15, rax
0x18002f274  mov     [rsp+68h+var_48], 0; int
0x18002f27d  lea     rdx, [rsp+68h+var_48]; HSTRING *
0x18002f282  call    ?GetAppSearchString@UsageDataSingleton@BatteryUsageHandlers@SystemSettings@@QEAAJPEAPEAUHSTRING__@@@Z; SystemSettings::BatteryUsageHandlers::UsageDataSingleton::GetAppSearchString(HSTRING__ * *)
0x18002f287  mov     ebx, eax
0x18002f289  test    eax, eax
0x18002f28b  jns     short loc_18002F2AD
0x18002f28d  mov     rcx, [rsp+68h]; this
0x18002f292  mov     r9d, eax; char *
0x18002f295  lea     r8, aOnecoreuapShel_21; "onecoreuap\\shell\\coresettinghandlers"...
0x18002f29c  mov     edx, 1BCh; void *
0x18002f2a1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f2a6  mov     eax, ebx
0x18002f2a8  jmp     loc_18002F415
0x18002f2ad  mov     [rsp+68h+arg_18], 0
0x18002f2b9  mov     [rsp+68h+arg_8], 0
0x18002f2c1  lea     rdx, [rsp+68h+arg_8]
0x18002f2c6  mov     rcx, [r14+0D0h]
0x18002f2cd  call    ?get_Size@?$Vector@PEAUISettingItem@DataModel@SystemSettings@@U?$DefaultEqualityPredicate@PEAUISettingItem@DataModel@SystemSettings@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUISettingItem@DataModel@SystemSettings@@@5678@U?$VectorOptions@PEAUISettingItem@DataModel@SystemSettings@@$00$00$0A@@5678@@Internal@Collections@Foundation@Windows@@UEAAJPEAI@Z; Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::get_Size(uint *)
0x18002f2d2  lea     rsi, [r14+268h]
0x18002f2d9  mov     dword ptr [rsi], 0
0x18002f2df  xor     edi, edi
0x18002f2e1  cmp     edi, [rsp+68h+arg_8]
0x18002f2e5  jnb     short loc_18002F329
0x18002f2e7  mov     rbx, [r14+0D0h]
0x18002f2ee  lea     rcx, [rsp+68h+arg_18]
0x18002f2f6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002f2fb  lea     r8, [rsp+68h+arg_18]
0x18002f303  mov     edx, edi
0x18002f305  mov     rcx, rbx
0x18002f308  call    ?GetAt@?$Vector@PEAUISettingItem@DataModel@SystemSettings@@U?$DefaultEqualityPredicate@PEAUISettingItem@DataModel@SystemSettings@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUISettingItem@DataModel@SystemSettings@@@5678@U?$VectorOptions@PEAUISettingItem@DataModel@SystemSettings@@$00$00$0A@@5678@@Internal@Collections@Foundation@Windows@@UEAAJIPEAPEAUISettingItem@DataModel@SystemSettings@@@Z; Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::GetAt(uint,SystemSettings::DataModel::ISettingItem * *)
0x18002f30d  mov     r8, [rsp+68h+var_48]; HSTRING
0x18002f312  mov     rdx, [rsp+68h+arg_18]; struct SystemSettings::BatteryUsageHandlers::AppListEntry *
0x18002f31a  call    ?_UpdateAppVisibility@AppList@BatteryUsageHandlers@SystemSettings@@AEAA_NPEAVAppListEntry@23@PEAUHSTRING__@@@Z; SystemSettings::BatteryUsageHandlers::AppList::_UpdateAppVisibility(SystemSettings::BatteryUsageHandlers::AppListEntry *,HSTRING__ *)
0x18002f31f  test    al, al
0x18002f321  jz      short loc_18002F325
0x18002f323  inc     dword ptr [rsi]
0x18002f325  inc     edi
0x18002f327  jmp     short loc_18002F2E1
0x18002f329  call    cs:__imp__Xtime_get_ticks
0x18002f32f  sub     rax, r15
0x18002f332  mov     [rsp+68h+var_40], rax
0x18002f337  lea     rdx, [rsp+68h+var_40]
0x18002f33c  lea     rcx, [rsp+68h+var_38]
0x18002f341  call    ??$?0_JU?$ratio@$00$0JIJGIA@@std@@$0A@@?$duration@NU?$ratio@$00$00@std@@@chrono@std@@QEAA@AEBV?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@12@@Z; std::chrono::duration<double,std::ratio<1,1>>::duration<double,std::ratio<1,1>>(std::chrono::duration<__int64,std::ratio<1,10000000>> const &)
0x18002f346  mov     [rsp+68h+string], 0
0x18002f352  lea     rdx, [rsp+68h+var_48]; HSTRING *
0x18002f357  lea     rcx, [rsp+68h+string]; newString
0x18002f35f  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x18002f364  mov     ebx, eax
0x18002f366  test    eax, eax
0x18002f368  jns     short loc_18002F3AE
0x18002f36a  mov     rcx, [rsp+68h]; this
0x18002f36f  mov     r9d, eax; char *
0x18002f372  lea     r8, aOnecoreuapShel_21; "onecoreuap\\shell\\coresettinghandlers"...
0x18002f379  mov     edx, 1D2h; void *
0x18002f37e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f383  mov     rcx, [rsp+68h+string]; string
0x18002f38b  call    cs:__imp_WindowsDeleteString
0x18002f391  mov     [rsp+68h+string], 0
0x18002f39d  lea     rcx, [rsp+68h+arg_18]
0x18002f3a5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002f3aa  mov     eax, ebx
0x18002f3ac  jmp     short loc_18002F415
0x18002f3ae  xor     edx, edx; length
0x18002f3b0  mov     rcx, [rsp+68h+string]; string
0x18002f3b8  call    cs:__imp_WindowsGetStringRawBuffer
0x18002f3be  mov     [rsp+68h+var_40], rax
0x18002f3c3  movsd   xmm0, [rsp+68h+var_38]
0x18002f3c9  movsd   [rsp+68h+var_38], xmm0
0x18002f3cf  mov     r9, rsi
0x18002f3d2  lea     r8, [rsp+68h+arg_8]
0x18002f3d7  lea     rdx, [rsp+68h+var_40]
0x18002f3dc  lea     rcx, [rsp+68h+var_38]
0x18002f3e1  call    ??$AppUsageListFiltered@NPEBGAEAIAEAI@UsageGraphTelemetry@@SAX$$QEAN$$QEAPEBGAEAI2@Z; UsageGraphTelemetry::AppUsageListFiltered<double,ushort const *,uint &,uint &>(double &&,ushort const * &&,uint &,uint &)
0x18002f3e6  mov     rcx, [rsp+68h+string]; string
0x18002f3ee  call    cs:__imp_WindowsDeleteString
0x18002f3f4  mov     [rsp+68h+string], 0
0x18002f400  lea     rcx, [rsp+68h+arg_18]
0x18002f408  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002f40d  xor     eax, eax
0x18002f40f  jmp     short loc_18002F415
0x18002f411  mov     eax, [rsp+68h+arg_8]
0x18002f415  add     rsp, 40h
0x18002f419  pop     r15
0x18002f41b  pop     r14
0x18002f41d  pop     rdi
0x18002f41e  pop     rsi
0x18002f41f  pop     rbx
0x18002f420  retn
```
