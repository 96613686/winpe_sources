# LogFailedInstall

- ea: `0x18001f984`
- end: `0x18001fe51`
- name: `LogFailedInstall`
- size: `1229`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, installer_update`

## callers

- `0x18002fe40`

## callees

- `0x180001b50`
- `0x180001dd8`
- `0x1800027c0`
- `0x180008e3c`
- `0x18000d954`
- `0x18000d9b4`
- `0x1800182b0`
- `0x18001d89c`
- `0x18001f984`
- `0x180024d5c`
- `0x1800275e4`
- `0x180027d2c`
- `0x1800283fc`
- `0x1800286d8`
- `0x180028dc4`
- `0x180029840`

## string_xrefs

- `0x18001fa8b`: `NetworkInterfaceInstallResult`
- `0x18001fab0`: `NetworkInterfaceInstallResult`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall LogFailedInstall(char *a1, __int64 *a2, __int64 a3)
{
  int ValueDword; // ebx
  int v6; // esi
  int v7; // r14d
  int v8; // r15d
  __int64 v9; // rax
  __int64 v10; // rdx
  int v11; // r8d
  const wchar_t *v12; // rax
  bool v13; // r12
  int *v14; // rdi
  __int64 ValueString; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // r8
  __int64 v19; // rcx
  __int64 v20; // r8
  __int64 v21; // r9
  __int64 v23; // rax
  __int64 v24; // r10
  char v25[4]; // [rsp+70h] [rbp-108h] BYREF
  int v26; // [rsp+74h] [rbp-104h] BYREF
  int v27; // [rsp+78h] [rbp-100h] BYREF
  int v28; // [rsp+7Ch] [rbp-FCh] BYREF
  int v29; // [rsp+80h] [rbp-F8h] BYREF
  __int64 *v30; // [rsp+88h] [rbp-F0h] BYREF
  __int64 *v31; // [rsp+90h] [rbp-E8h] BYREF
  __int64 *v32; // [rsp+98h] [rbp-E0h] BYREF
  _BYTE v33[32]; // [rsp+A0h] [rbp-D8h] BYREF
  HKEY v34; // [rsp+C0h] [rbp-B8h] BYREF
  __int64 *v35[2]; // [rsp+C8h] [rbp-B0h] BYREF
  _BYTE v36[32]; // [rsp+D8h] [rbp-A0h] BYREF
  _BYTE v37[32]; // [rsp+F8h] [rbp-80h] BYREF
  _BYTE v38[32]; // [rsp+118h] [rbp-60h] BYREF

  v30 = a2;
  v31 = (__int64 *)a3;
  v25[0] = 2;
  std::wstring::wstring((__int64)v38, (__int64)L"<none>");
  std::wstring::wstring((__int64)v37, (__int64)L"<none>");
  std::wstring::wstring((__int64)v36, (__int64)L"<none>");
  ValueDword = -1;
  v26 = -1;
  v6 = -1;
  v27 = -1;
  v7 = -1;
  v28 = -1;
  v8 = -1;
  v29 = -1;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    v9 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
    WPP_SF_dS(*(_QWORD *)(v10 + 16), v10, v11, *(_DWORD *)(a3 + 32), v9);
  }
  v12 = (const wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
  try
  {
    NetSetupDevice::NetSetupDevice((NetSetupDevice *)v35, v12, 0);
    NetSetupDevice::OpenSoftwareKey((NetSetupDevice *)v35, (RegistryKey *)&v34, 3u, a1);
    v13 = RegistryKey::ValueExists((RegistryKey *)&v34, L"NetworkInterfaceInstallResult");
    v25[0] = v13;
    v14 = (int *)(a3 + 32);
    RegistryKey::SetValue(&v34, L"NetworkInterfaceInstallResult", *v14, 0);
    if ( RegistryKey::ValueExists((RegistryKey *)&v34, L"DriverDesc") )
    {
      ValueString = RegistryKey::GetValueString(&v34, (__int64)v33, L"DriverDesc", 0);
      std::wstring::operator=(v38, ValueString);
      std::wstring::_Tidy_deallocate((__int64)v33);
    }
    if ( RegistryKey::ValueExists((RegistryKey *)&v34, L"ProviderName") )
    {
      v16 = RegistryKey::GetValueString(&v34, (__int64)v33, L"ProviderName", 0);
      std::wstring::operator=(v37, v16);
      std::wstring::_Tidy_deallocate((__int64)v33);
    }
    if ( RegistryKey::ValueExists((RegistryKey *)&v34, L"BusType") )
    {
      v17 = RegistryKey::GetValueString(&v34, (__int64)v33, L"BusType", 0);
      std::wstring::operator=(v36, v17);
      std::wstring::_Tidy_deallocate((__int64)v33);
    }
    if ( RegistryKey::ValueExists((RegistryKey *)&v34, L"Characteristics") )
    {
      ValueDword = RegistryKey::GetValueDword(&v34, L"Characteristics", 0, 0);
      v26 = ValueDword;
    }
    if ( RegistryKey::ValueExists((RegistryKey *)&v34, L"*IfType") )
    {
      v6 = RegistryKey::GetValueDword(&v34, L"*IfType", 0, 0);
      v27 = v6;
    }
    if ( RegistryKey::ValueExists((RegistryKey *)&v34, L"*MediaType") )
    {
      v7 = RegistryKey::GetValueDword(&v34, L"*MediaType", 0, 0);
      v28 = v7;
    }
    if ( RegistryKey::ValueExists((RegistryKey *)&v34, L"*PhysicalMediaType") )
    {
      v8 = RegistryKey::GetValueDword(&v34, L"*PhysicalMediaType", 0, 0);
      v29 = v8;
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v34);
  }
  catch ( ... )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      v23 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
      WPP_SF_S(*(_QWORD *)(v24 + 16), 35, WPP_ebd892180d513f9593fffe48317335f2_Traceguids, v23);
    }
    v14 = (int *)(v31 + 4);
    v13 = v25[0];
    ValueDword = v26;
    v6 = v27;
    v7 = v28;
    v8 = v29;
  }
  if ( (unsigned int)dword_180049000 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180049000, 0x400000000000LL, v18) )
  {
    v29 = v8;
    v28 = v7;
    v27 = v6;
    v26 = ValueDword;
    v31 = (__int64 *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
    v30 = (__int64 *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
    v32 = (__int64 *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
    v25[0] = v13;
    v35[0] = (__int64 *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
    LODWORD(v34) = *v14;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<1>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v19,
      (int)&word_180041916,
      v20,
      v21,
      (__int64)&v34,
      v35,
      (__int64)v25,
      &v32,
      &v30,
      &v31,
      (__int64)&v26,
      (__int64)&v27,
      (__int64)&v28,
      (__int64)&v29);
  }
  std::wstring::_Tidy_deallocate((__int64)v36);
  std::wstring::_Tidy_deallocate((__int64)v37);
  return std::wstring::_Tidy_deallocate((__int64)v38);
}

```

## disassembly

```asm
0x18001f984  mov     r11, rsp
0x18001f987  push    rbx
0x18001f988  push    rsi
0x18001f989  push    rdi
0x18001f98a  push    r12
0x18001f98c  push    r13
0x18001f98e  push    r14
0x18001f990  push    r15
0x18001f992  sub     rsp, 140h
0x18001f999  mov     rax, cs:__security_cookie
0x18001f9a0  xor     rax, rsp
0x18001f9a3  mov     [rsp+178h+var_40], rax
0x18001f9ab  mov     rdi, r8
0x18001f9ae  mov     r13, rdx
0x18001f9b1  mov     r12, rcx
0x18001f9b4  mov     [rsp+178h+var_F0], rdx
0x18001f9bc  mov     [rsp+178h+var_E8], r8
0x18001f9c4  mov     [rsp+178h+var_108], 2
0x18001f9c9  lea     rbx, aNone; "<none>"
0x18001f9d0  mov     rdx, rbx
0x18001f9d3  lea     rcx, [r11-60h]
0x18001f9d7  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001f9dc  nop
0x18001f9dd  mov     rdx, rbx
0x18001f9e0  lea     rcx, [rsp+178h+var_80]
0x18001f9e8  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001f9ed  nop
0x18001f9ee  mov     rdx, rbx
0x18001f9f1  lea     rcx, [rsp+178h+var_A0]
0x18001f9f9  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001f9fe  nop
0x18001f9ff  or      ebx, 0FFFFFFFFh
0x18001fa02  mov     [rsp+178h+var_104], ebx
0x18001fa06  mov     esi, ebx
0x18001fa08  mov     [rsp+178h+var_100], ebx
0x18001fa0c  mov     r14d, ebx
0x18001fa0f  mov     [rsp+178h+var_FC], ebx
0x18001fa13  mov     r15d, ebx
0x18001fa16  mov     [rsp+178h+var_F8], ebx
0x18001fa1d  lea     rax, WPP_GLOBAL_Control
0x18001fa24  mov     rdx, cs:WPP_GLOBAL_Control
0x18001fa2b  cmp     rdx, rax
0x18001fa2e  jz      short loc_18001FA51
0x18001fa30  cmp     byte ptr [rdx+19h], 3
0x18001fa34  jb      short loc_18001FA51
0x18001fa36  mov     rcx, r13
0x18001fa39  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001fa3e  mov     [rsp+178h+var_158], rax
0x18001fa43  mov     r9d, [rdi+20h]
0x18001fa47  mov     rcx, [rdx+10h]
0x18001fa4b  call    WPP_SF_dS
0x18001fa50  nop
0x18001fa51  mov     rcx, r13
0x18001fa54  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001fa59  xor     r8d, r8d; bool
0x18001fa5c  mov     rdx, rax; wchar_t *
0x18001fa5f  lea     rcx, [rsp+178h+var_B0]; this
0x18001fa67  call    ??0NetSetupDevice@@QEAA@PEB_W_N@Z; NetSetupDevice::NetSetupDevice(wchar_t const *,bool)
0x18001fa6c  mov     r9, r12
0x18001fa6f  mov     r8d, 3
0x18001fa75  lea     rdx, [rsp+178h+var_B8]
0x18001fa7d  lea     rcx, [rsp+178h+var_B0]
0x18001fa85  call    ?OpenSoftwareKey@NetSetupDevice@@QEAA?AVRegistryKey@@KPEAXW4DeviceKeyFailPolicy@1@@Z; NetSetupDevice::OpenSoftwareKey(ulong,void *,NetSetupDevice::DeviceKeyFailPolicy)
0x18001fa8a  nop
0x18001fa8b  lea     rdx, aNetworkinterfa; "NetworkInterfaceInstallResult"
0x18001fa92  lea     rcx, [rsp+178h+var_B8]; this
0x18001fa9a  call    ?ValueExists@RegistryKey@@QEBA_NPEB_W@Z; RegistryKey::ValueExists(wchar_t const *)
0x18001fa9f  mov     r12b, al
0x18001faa2  mov     [rsp+178h+var_108], al
0x18001faa6  add     rdi, 20h ; ' '
0x18001faaa  xor     r9d, r9d
0x18001faad  mov     r8d, [rdi]
0x18001fab0  lea     rdx, aNetworkinterfa; "NetworkInterfaceInstallResult"
0x18001fab7  lea     rcx, [rsp+178h+var_B8]
0x18001fabf  call    ?SetValue@RegistryKey@@QEBAXPEB_WKW4EncodingOptions@1@@Z; RegistryKey::SetValue(wchar_t const *,ulong,RegistryKey::EncodingOptions)
0x18001fac4  lea     rdx, aDriverdesc; "DriverDesc"
0x18001facb  lea     rcx, [rsp+178h+var_B8]; this
0x18001fad3  call    ?ValueExists@RegistryKey@@QEBA_NPEB_W@Z; RegistryKey::ValueExists(wchar_t const *)
0x18001fad8  test    al, al
0x18001fada  jz      short loc_18001FB18
0x18001fadc  xor     r9d, r9d
0x18001fadf  lea     r8, aDriverdesc; "DriverDesc"
0x18001fae6  lea     rdx, [rsp+178h+var_D8]
0x18001faee  lea     rcx, [rsp+178h+var_B8]
0x18001faf6  call    ?GetValueString@RegistryKey@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WW4MissingValueDisposition@1@@Z; RegistryKey::GetValueString(wchar_t const *,RegistryKey::MissingValueDisposition)
0x18001fafb  mov     rdx, rax
0x18001fafe  lea     rcx, [rsp+178h+var_60]
0x18001fb06  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18001fb0b  lea     rcx, [rsp+178h+var_D8]
0x18001fb13  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001fb18  lea     rdx, aProvidername; "ProviderName"
0x18001fb1f  lea     rcx, [rsp+178h+var_B8]; this
0x18001fb27  call    ?ValueExists@RegistryKey@@QEBA_NPEB_W@Z; RegistryKey::ValueExists(wchar_t const *)
0x18001fb2c  test    al, al
0x18001fb2e  jz      short loc_18001FB6C
0x18001fb30  xor     r9d, r9d
0x18001fb33  lea     r8, aProvidername; "ProviderName"
0x18001fb3a  lea     rdx, [rsp+178h+var_D8]
0x18001fb42  lea     rcx, [rsp+178h+var_B8]
0x18001fb4a  call    ?GetValueString@RegistryKey@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WW4MissingValueDisposition@1@@Z; RegistryKey::GetValueString(wchar_t const *,RegistryKey::MissingValueDisposition)
0x18001fb4f  mov     rdx, rax
0x18001fb52  lea     rcx, [rsp+178h+var_80]
0x18001fb5a  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18001fb5f  lea     rcx, [rsp+178h+var_D8]
0x18001fb67  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001fb6c  lea     rdx, aBustype; "BusType"
0x18001fb73  lea     rcx, [rsp+178h+var_B8]; this
0x18001fb7b  call    ?ValueExists@RegistryKey@@QEBA_NPEB_W@Z; RegistryKey::ValueExists(wchar_t const *)
0x18001fb80  test    al, al
0x18001fb82  jz      short loc_18001FBC0
0x18001fb84  xor     r9d, r9d
0x18001fb87  lea     r8, aBustype; "BusType"
0x18001fb8e  lea     rdx, [rsp+178h+var_D8]
0x18001fb96  lea     rcx, [rsp+178h+var_B8]
0x18001fb9e  call    ?GetValueString@RegistryKey@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WW4MissingValueDisposition@1@@Z; RegistryKey::GetValueString(wchar_t const *,RegistryKey::MissingValueDisposition)
0x18001fba3  mov     rdx, rax
0x18001fba6  lea     rcx, [rsp+178h+var_A0]
0x18001fbae  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18001fbb3  lea     rcx, [rsp+178h+var_D8]
0x18001fbbb  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001fbc0  lea     rdx, aCharacteristic; "Characteristics"
0x18001fbc7  lea     rcx, [rsp+178h+var_B8]; this
0x18001fbcf  call    ?ValueExists@RegistryKey@@QEBA_NPEB_W@Z; RegistryKey::ValueExists(wchar_t const *)
0x18001fbd4  test    al, al
0x18001fbd6  jz      short loc_18001FBF8
0x18001fbd8  xor     r9d, r9d
0x18001fbdb  xor     r8d, r8d
0x18001fbde  lea     rdx, aCharacteristic; "Characteristics"
0x18001fbe5  lea     rcx, [rsp+178h+var_B8]
0x18001fbed  call    ?GetValueDword@RegistryKey@@QEBAKPEB_WW4EncodingOptions@1@W4MissingValueDisposition@1@@Z; RegistryKey::GetValueDword(wchar_t const *,RegistryKey::EncodingOptions,RegistryKey::MissingValueDisposition)
0x18001fbf2  mov     ebx, eax
0x18001fbf4  mov     [rsp+178h+var_104], eax
0x18001fbf8  lea     rdx, aIftype; "*IfType"
0x18001fbff  lea     rcx, [rsp+178h+var_B8]; this
0x18001fc07  call    ?ValueExists@RegistryKey@@QEBA_NPEB_W@Z; RegistryKey::ValueExists(wchar_t const *)
0x18001fc0c  test    al, al
0x18001fc0e  jz      short loc_18001FC30
0x18001fc10  xor     r9d, r9d
0x18001fc13  xor     r8d, r8d
0x18001fc16  lea     rdx, aIftype; "*IfType"
0x18001fc1d  lea     rcx, [rsp+178h+var_B8]
0x18001fc25  call    ?GetValueDword@RegistryKey@@QEBAKPEB_WW4EncodingOptions@1@W4MissingValueDisposition@1@@Z; RegistryKey::GetValueDword(wchar_t const *,RegistryKey::EncodingOptions,RegistryKey::MissingValueDisposition)
0x18001fc2a  mov     esi, eax
0x18001fc2c  mov     [rsp+178h+var_100], eax
0x18001fc30  lea     rdx, aMediatype; "*MediaType"
0x18001fc37  lea     rcx, [rsp+178h+var_B8]; this
0x18001fc3f  call    ?ValueExists@RegistryKey@@QEBA_NPEB_W@Z; RegistryKey::ValueExists(wchar_t const *)
0x18001fc44  test    al, al
0x18001fc46  jz      short loc_18001FC69
0x18001fc48  xor     r9d, r9d
0x18001fc4b  xor     r8d, r8d
0x18001fc4e  lea     rdx, aMediatype; "*MediaType"
0x18001fc55  lea     rcx, [rsp+178h+var_B8]
0x18001fc5d  call    ?GetValueDword@RegistryKey@@QEBAKPEB_WW4EncodingOptions@1@W4MissingValueDisposition@1@@Z; RegistryKey::GetValueDword(wchar_t const *,RegistryKey::EncodingOptions,RegistryKey::MissingValueDisposition)
0x18001fc62  mov     r14d, eax
0x18001fc65  mov     [rsp+178h+var_FC], eax
0x18001fc69  lea     rdx, aPhysicalmediat; "*PhysicalMediaType"
0x18001fc70  lea     rcx, [rsp+178h+var_B8]; this
0x18001fc78  call    ?ValueExists@RegistryKey@@QEBA_NPEB_W@Z; RegistryKey::ValueExists(wchar_t const *)
0x18001fc7d  test    al, al
0x18001fc7f  jz      short loc_18001FCA5
0x18001fc81  xor     r9d, r9d
0x18001fc84  xor     r8d, r8d
0x18001fc87  lea     rdx, aPhysicalmediat; "*PhysicalMediaType"
0x18001fc8e  lea     rcx, [rsp+178h+var_B8]
0x18001fc96  call    ?GetValueDword@RegistryKey@@QEBAKPEB_WW4EncodingOptions@1@W4MissingValueDisposition@1@@Z; RegistryKey::GetValueDword(wchar_t const *,RegistryKey::EncodingOptions,RegistryKey::MissingValueDisposition)
0x18001fc9b  mov     r15d, eax
0x18001fc9e  mov     [rsp+178h+var_F8], eax
0x18001fca5  lea     rcx, [rsp+178h+var_B8]
0x18001fcad  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001fcb2  nop
0x18001fcb3  jmp     short loc_18001FCE3
0x18001fcb5  mov     rdi, [rsp+178h+var_E8]
0x18001fcbd  add     rdi, 20h ; ' '
0x18001fcc1  mov     r12b, [rsp+178h+var_108]
0x18001fcc6  mov     ebx, [rsp+178h+var_104]
0x18001fcca  mov     esi, [rsp+178h+var_100]
0x18001fcce  mov     r14d, [rsp+178h+var_FC]
0x18001fcd3  mov     r15d, [rsp+178h+var_F8]
0x18001fcdb  mov     r13, [rsp+178h+var_F0]
0x18001fce3  mov     eax, cs:dword_180049000
0x18001fce9  cmp     eax, 5
0x18001fcec  jbe     loc_18001FE05
0x18001fcf2  mov     rdx, 400000000000h
0x18001fcfc  lea     rcx, dword_180049000
0x18001fd03  call    _tlgKeywordOn
0x18001fd08  test    al, al
0x18001fd0a  jz      loc_18001FE05
0x18001fd10  mov     [rsp+178h+var_F8], r15d
0x18001fd18  mov     [rsp+178h+var_FC], r14d
0x18001fd1d  mov     [rsp+178h+var_100], esi
0x18001fd21  mov     [rsp+178h+var_104], ebx
0x18001fd25  lea     rcx, [rsp+178h+var_A0]
0x18001fd2d  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001fd32  mov     [rsp+178h+var_E8], rax
0x18001fd3a  lea     rcx, [rsp+178h+var_80]
0x18001fd42  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001fd47  mov     [rsp+178h+var_F0], rax
0x18001fd4f  lea     rcx, [rsp+178h+var_60]
0x18001fd57  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001fd5c  mov     [rsp+178h+var_E0], rax
0x18001fd64  mov     [rsp+178h+var_108], r12b
0x18001fd69  mov     rcx, r13
0x18001fd6c  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001fd71  mov     [rsp+178h+var_B0], rax
0x18001fd79  mov     eax, [rdi]
0x18001fd7b  mov     dword ptr [rsp+178h+var_B8], eax
0x18001fd82  lea     rax, [rsp+178h+var_F8]
0x18001fd8a  mov     [rsp+178h+var_110], rax
0x18001fd8f  lea     rax, [rsp+178h+var_FC]
0x18001fd94  mov     [rsp+178h+var_118], rax
0x18001fd99  lea     rax, [rsp+178h+var_100]
0x18001fd9e  mov     [rsp+178h+var_120], rax
0x18001fda3  lea     rax, [rsp+178h+var_104]
0x18001fda8  mov     [rsp+178h+var_128], rax
0x18001fdad  lea     rax, [rsp+178h+var_E8]
0x18001fdb5  mov     [rsp+178h+var_130], rax
0x18001fdba  lea     rax, [rsp+178h+var_F0]
0x18001fdc2  mov     [rsp+178h+var_138], rax
0x18001fdc7  lea     rax, [rsp+178h+var_E0]
0x18001fdcf  mov     [rsp+178h+var_140], rax
0x18001fdd4  lea     rax, [rsp+178h+var_108]
0x18001fdd9  mov     [rsp+178h+var_148], rax
0x18001fdde  lea     rax, [rsp+178h+var_B0]
0x18001fde6  mov     [rsp+178h+var_150], rax
0x18001fdeb  lea     rax, [rsp+178h+var_B8]
0x18001fdf3  mov     [rsp+178h+var_158], rax
0x18001fdf8  lea     rdx, word_180041916
0x18001fdff  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@_W@@U?$_tlgWrapperByVal@$00@@U2@U2@U2@U1@U1@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapperByVal@$00@@4443333@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<1>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<1> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001fe04  nop
0x18001fe05  lea     rcx, [rsp+178h+var_A0]
0x18001fe0d  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001fe12  nop
0x18001fe13  lea     rcx, [rsp+178h+var_80]
0x18001fe1b  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001fe20  nop
0x18001fe21  lea     rcx, [rsp+178h+var_60]
0x18001fe29  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001fe2e  mov     rcx, [rsp+178h+var_40]
0x18001fe36  xor     rcx, rsp; StackCookie
0x18001fe39  call    __security_check_cookie
0x18001fe3e  add     rsp, 140h
0x18001fe45  pop     r15
0x18001fe47  pop     r14
0x18001fe49  pop     r13
0x18001fe4b  pop     r12
0x18001fe4d  pop     rdi
0x18001fe4e  pop     rsi
0x18001fe4f  pop     rbx
0x18001fe50  retn
```
