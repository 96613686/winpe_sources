# LogSuccessfulInstall

- ea: `0x18001fe58`
- end: `0x18002030f`
- name: `LogSuccessfulInstall`
- size: `1207`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, installer_update`

## callers

- `0x18001f258`

## callees

- `0x180001b50`
- `0x180001dd8`
- `0x1800027c0`
- `0x180008e3c`
- `0x18000d954`
- `0x18000d9b4`
- `0x18000df60`
- `0x1800182b0`
- `0x18001d89c`
- `0x18001fe58`
- `0x180026d3c`
- `0x1800275e4`
- `0x180027d2c`
- `0x1800286d8`
- `0x180028dc4`
- `0x180029840`

## string_xrefs

- `0x18001ff5b`: `NetworkInterfaceInstallResult`
- `0x18001ff76`: `NetworkInterfaceInstallResult`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall LogSuccessfulInstall(char *a1, __int64 *a2)
{
  int ValueDword; // ebx
  int v4; // edi
  int v5; // esi
  int v6; // r14d
  __int64 v7; // rax
  __int64 v8; // r10
  const wchar_t *v9; // rax
  bool v10; // r12
  __int64 ValueString; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // r8
  __int64 v15; // rcx
  __int64 v16; // r8
  __int64 v17; // r9
  __int64 v19; // rax
  __int64 v20; // r10
  char v21[4]; // [rsp+70h] [rbp-F8h] BYREF
  int v22; // [rsp+74h] [rbp-F4h] BYREF
  int v23; // [rsp+78h] [rbp-F0h] BYREF
  int v24; // [rsp+7Ch] [rbp-ECh] BYREF
  int v25; // [rsp+80h] [rbp-E8h] BYREF
  __int64 *v26; // [rsp+88h] [rbp-E0h] BYREF
  __int64 *v27; // [rsp+90h] [rbp-D8h] BYREF
  __int64 *v28; // [rsp+98h] [rbp-D0h] BYREF
  _BYTE v29[32]; // [rsp+A0h] [rbp-C8h] BYREF
  HKEY v30; // [rsp+C0h] [rbp-A8h] BYREF
  __int64 *v31[2]; // [rsp+C8h] [rbp-A0h] BYREF
  _BYTE v32[32]; // [rsp+D8h] [rbp-90h] BYREF
  _BYTE v33[32]; // [rsp+F8h] [rbp-70h] BYREF
  _BYTE v34[32]; // [rsp+118h] [rbp-50h] BYREF

  v26 = a2;
  v21[0] = 2;
  std::wstring::wstring((__int64)v34, (__int64)L"<none>");
  std::wstring::wstring((__int64)v33, (__int64)L"<none>");
  std::wstring::wstring((__int64)v32, (__int64)L"<none>");
  ValueDword = -1;
  v22 = -1;
  v4 = -1;
  v23 = -1;
  v5 = -1;
  v24 = -1;
  v6 = -1;
  v25 = -1;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    v7 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
    WPP_SF_S(*(_QWORD *)(v8 + 16), 32, WPP_ebd892180d513f9593fffe48317335f2_Traceguids, v7);
  }
  v9 = (const wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
  try
  {
    NetSetupDevice::NetSetupDevice((NetSetupDevice *)v31, v9, 0);
    NetSetupDevice::OpenSoftwareKey((NetSetupDevice *)v31, (RegistryKey *)&v30, 3u, a1);
    v10 = RegistryKey::ValueExists((RegistryKey *)&v30, L"NetworkInterfaceInstallResult");
    v21[0] = v10;
    RegistryKey::DeleteValue(&v30, L"NetworkInterfaceInstallResult");
    if ( RegistryKey::ValueExists((RegistryKey *)&v30, L"DriverDesc") )
    {
      ValueString = RegistryKey::GetValueString(&v30, (__int64)v29, L"DriverDesc", 0);
      std::wstring::operator=(v34, ValueString);
      std::wstring::_Tidy_deallocate((__int64)v29);
    }
    if ( RegistryKey::ValueExists((RegistryKey *)&v30, L"ProviderName") )
    {
      v12 = RegistryKey::GetValueString(&v30, (__int64)v29, L"ProviderName", 0);
      std::wstring::operator=(v33, v12);
      std::wstring::_Tidy_deallocate((__int64)v29);
    }
    if ( RegistryKey::ValueExists((RegistryKey *)&v30, L"BusType") )
    {
      v13 = RegistryKey::GetValueString(&v30, (__int64)v29, L"BusType", 0);
      std::wstring::operator=(v32, v13);
      std::wstring::_Tidy_deallocate((__int64)v29);
    }
    if ( RegistryKey::ValueExists((RegistryKey *)&v30, L"Characteristics") )
    {
      ValueDword = RegistryKey::GetValueDword(&v30, L"Characteristics", 0, 0);
      v22 = ValueDword;
    }
    if ( RegistryKey::ValueExists((RegistryKey *)&v30, L"*IfType") )
    {
      v4 = RegistryKey::GetValueDword(&v30, L"*IfType", 0, 0);
      v23 = v4;
    }
    if ( RegistryKey::ValueExists((RegistryKey *)&v30, L"*MediaType") )
    {
      v5 = RegistryKey::GetValueDword(&v30, L"*MediaType", 0, 0);
      v24 = v5;
    }
    if ( RegistryKey::ValueExists((RegistryKey *)&v30, L"*PhysicalMediaType") )
    {
      v6 = RegistryKey::GetValueDword(&v30, L"*PhysicalMediaType", 0, 0);
      v25 = v6;
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v30);
  }
  catch ( ... )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      v19 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
      WPP_SF_S(*(_QWORD *)(v20 + 16), 33, WPP_ebd892180d513f9593fffe48317335f2_Traceguids, v19);
    }
    v10 = v21[0];
    ValueDword = v22;
    v4 = v23;
    v5 = v24;
    v6 = v25;
  }
  if ( (unsigned int)dword_180049000 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180049000, 0x400000000000LL, v14) )
  {
    v25 = v6;
    v24 = v5;
    v23 = v4;
    v22 = ValueDword;
    v26 = (__int64 *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
    v27 = (__int64 *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
    v28 = (__int64 *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
    v21[0] = v10;
    v31[0] = (__int64 *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
    LODWORD(v30) = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<1>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v15,
      (int)&byte_1800419AF,
      v16,
      v17,
      (__int64)&v30,
      v31,
      (__int64)v21,
      &v28,
      &v27,
      &v26,
      (__int64)&v22,
      (__int64)&v23,
      (__int64)&v24,
      (__int64)&v25);
  }
  std::wstring::_Tidy_deallocate((__int64)v32);
  std::wstring::_Tidy_deallocate((__int64)v33);
  return std::wstring::_Tidy_deallocate((__int64)v34);
}

```

## disassembly

```asm
0x18001fe58  mov     r11, rsp
0x18001fe5b  mov     [r11+18h], rbx
0x18001fe5f  push    rsi
0x18001fe60  push    rdi
0x18001fe61  push    r12
0x18001fe63  push    r14
0x18001fe65  push    r15
0x18001fe67  sub     rsp, 140h
0x18001fe6e  mov     rax, cs:__security_cookie
0x18001fe75  xor     rax, rsp
0x18001fe78  mov     [rsp+168h+var_30], rax
0x18001fe80  mov     r15, rdx
0x18001fe83  mov     r12, rcx
0x18001fe86  mov     [rsp+168h+var_E0], rdx
0x18001fe8e  mov     [rsp+168h+var_F8], 2
0x18001fe93  lea     rbx, aNone; "<none>"
0x18001fe9a  mov     rdx, rbx
0x18001fe9d  lea     rcx, [r11-50h]
0x18001fea1  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001fea6  nop
0x18001fea7  mov     rdx, rbx
0x18001feaa  lea     rcx, [rsp+168h+var_70]
0x18001feb2  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001feb7  nop
0x18001feb8  mov     rdx, rbx
0x18001febb  lea     rcx, [rsp+168h+var_90]
0x18001fec3  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001fec8  nop
0x18001fec9  or      ebx, 0FFFFFFFFh
0x18001fecc  mov     [rsp+168h+var_F4], ebx
0x18001fed0  mov     edi, ebx
0x18001fed2  mov     [rsp+168h+var_F0], ebx
0x18001fed6  mov     esi, ebx
0x18001fed8  mov     [rsp+168h+var_EC], ebx
0x18001fedc  mov     r14d, ebx
0x18001fedf  mov     [rsp+168h+var_E8], ebx
0x18001fee6  lea     rax, WPP_GLOBAL_Control
0x18001feed  mov     r10, cs:WPP_GLOBAL_Control
0x18001fef4  cmp     r10, rax
0x18001fef7  jz      short loc_18001FF21
0x18001fef9  cmp     byte ptr [r10+19h], 4
0x18001fefe  jb      short loc_18001FF21
0x18001ff00  mov     rcx, r15
0x18001ff03  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001ff08  mov     edx, 20h ; ' '
0x18001ff0d  mov     r9, rax
0x18001ff10  lea     r8, WPP_ebd892180d513f9593fffe48317335f2_Traceguids
0x18001ff17  mov     rcx, [r10+10h]
0x18001ff1b  call    WPP_SF_S
0x18001ff20  nop
0x18001ff21  mov     rcx, r15
0x18001ff24  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001ff29  xor     r8d, r8d; bool
0x18001ff2c  mov     rdx, rax; wchar_t *
0x18001ff2f  lea     rcx, [rsp+168h+var_A0]; this
0x18001ff37  call    ??0NetSetupDevice@@QEAA@PEB_W_N@Z; NetSetupDevice::NetSetupDevice(wchar_t const *,bool)
0x18001ff3c  mov     r9, r12
0x18001ff3f  mov     r8d, 3
0x18001ff45  lea     rdx, [rsp+168h+var_A8]
0x18001ff4d  lea     rcx, [rsp+168h+var_A0]
0x18001ff55  call    ?OpenSoftwareKey@NetSetupDevice@@QEAA?AVRegistryKey@@KPEAXW4DeviceKeyFailPolicy@1@@Z; NetSetupDevice::OpenSoftwareKey(ulong,void *,NetSetupDevice::DeviceKeyFailPolicy)
0x18001ff5a  nop
0x18001ff5b  lea     rdx, aNetworkinterfa; "NetworkInterfaceInstallResult"
0x18001ff62  lea     rcx, [rsp+168h+var_A8]; this
0x18001ff6a  call    ?ValueExists@RegistryKey@@QEBA_NPEB_W@Z; RegistryKey::ValueExists(wchar_t const *)
0x18001ff6f  mov     r12b, al
0x18001ff72  mov     [rsp+168h+var_F8], al
0x18001ff76  lea     rdx, aNetworkinterfa; "NetworkInterfaceInstallResult"
0x18001ff7d  lea     rcx, [rsp+168h+var_A8]; this
0x18001ff85  call    ?DeleteValue@RegistryKey@@QEBAXPEB_W@Z; RegistryKey::DeleteValue(wchar_t const *)
0x18001ff8a  lea     rdx, aDriverdesc; "DriverDesc"
0x18001ff91  lea     rcx, [rsp+168h+var_A8]; this
0x18001ff99  call    ?ValueExists@RegistryKey@@QEBA_NPEB_W@Z; RegistryKey::ValueExists(wchar_t const *)
0x18001ff9e  test    al, al
0x18001ffa0  jz      short loc_18001FFDE
0x18001ffa2  xor     r9d, r9d
0x18001ffa5  lea     r8, aDriverdesc; "DriverDesc"
0x18001ffac  lea     rdx, [rsp+168h+var_C8]
0x18001ffb4  lea     rcx, [rsp+168h+var_A8]
0x18001ffbc  call    ?GetValueString@RegistryKey@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WW4MissingValueDisposition@1@@Z; RegistryKey::GetValueString(wchar_t const *,RegistryKey::MissingValueDisposition)
0x18001ffc1  mov     rdx, rax
0x18001ffc4  lea     rcx, [rsp+168h+var_50]
0x18001ffcc  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18001ffd1  lea     rcx, [rsp+168h+var_C8]
0x18001ffd9  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001ffde  lea     rdx, aProvidername; "ProviderName"
0x18001ffe5  lea     rcx, [rsp+168h+var_A8]; this
0x18001ffed  call    ?ValueExists@RegistryKey@@QEBA_NPEB_W@Z; RegistryKey::ValueExists(wchar_t const *)
0x18001fff2  test    al, al
0x18001fff4  jz      short loc_180020032
0x18001fff6  xor     r9d, r9d
0x18001fff9  lea     r8, aProvidername; "ProviderName"
0x180020000  lea     rdx, [rsp+168h+var_C8]
0x180020008  lea     rcx, [rsp+168h+var_A8]
0x180020010  call    ?GetValueString@RegistryKey@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WW4MissingValueDisposition@1@@Z; RegistryKey::GetValueString(wchar_t const *,RegistryKey::MissingValueDisposition)
0x180020015  mov     rdx, rax
0x180020018  lea     rcx, [rsp+168h+var_70]
0x180020020  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180020025  lea     rcx, [rsp+168h+var_C8]
0x18002002d  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180020032  lea     rdx, aBustype; "BusType"
0x180020039  lea     rcx, [rsp+168h+var_A8]; this
0x180020041  call    ?ValueExists@RegistryKey@@QEBA_NPEB_W@Z; RegistryKey::ValueExists(wchar_t const *)
0x180020046  test    al, al
0x180020048  jz      short loc_180020086
0x18002004a  xor     r9d, r9d
0x18002004d  lea     r8, aBustype; "BusType"
0x180020054  lea     rdx, [rsp+168h+var_C8]
0x18002005c  lea     rcx, [rsp+168h+var_A8]
0x180020064  call    ?GetValueString@RegistryKey@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_WW4MissingValueDisposition@1@@Z; RegistryKey::GetValueString(wchar_t const *,RegistryKey::MissingValueDisposition)
0x180020069  mov     rdx, rax
0x18002006c  lea     rcx, [rsp+168h+var_90]
0x180020074  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180020079  lea     rcx, [rsp+168h+var_C8]
0x180020081  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180020086  lea     rdx, aCharacteristic; "Characteristics"
0x18002008d  lea     rcx, [rsp+168h+var_A8]; this
0x180020095  call    ?ValueExists@RegistryKey@@QEBA_NPEB_W@Z; RegistryKey::ValueExists(wchar_t const *)
0x18002009a  test    al, al
0x18002009c  jz      short loc_1800200BE
0x18002009e  xor     r9d, r9d
0x1800200a1  xor     r8d, r8d
0x1800200a4  lea     rdx, aCharacteristic; "Characteristics"
0x1800200ab  lea     rcx, [rsp+168h+var_A8]
0x1800200b3  call    ?GetValueDword@RegistryKey@@QEBAKPEB_WW4EncodingOptions@1@W4MissingValueDisposition@1@@Z; RegistryKey::GetValueDword(wchar_t const *,RegistryKey::EncodingOptions,RegistryKey::MissingValueDisposition)
0x1800200b8  mov     ebx, eax
0x1800200ba  mov     [rsp+168h+var_F4], eax
0x1800200be  lea     rdx, aIftype; "*IfType"
0x1800200c5  lea     rcx, [rsp+168h+var_A8]; this
0x1800200cd  call    ?ValueExists@RegistryKey@@QEBA_NPEB_W@Z; RegistryKey::ValueExists(wchar_t const *)
0x1800200d2  test    al, al
0x1800200d4  jz      short loc_1800200F6
0x1800200d6  xor     r9d, r9d
0x1800200d9  xor     r8d, r8d
0x1800200dc  lea     rdx, aIftype; "*IfType"
0x1800200e3  lea     rcx, [rsp+168h+var_A8]
0x1800200eb  call    ?GetValueDword@RegistryKey@@QEBAKPEB_WW4EncodingOptions@1@W4MissingValueDisposition@1@@Z; RegistryKey::GetValueDword(wchar_t const *,RegistryKey::EncodingOptions,RegistryKey::MissingValueDisposition)
0x1800200f0  mov     edi, eax
0x1800200f2  mov     [rsp+168h+var_F0], eax
0x1800200f6  lea     rdx, aMediatype; "*MediaType"
0x1800200fd  lea     rcx, [rsp+168h+var_A8]; this
0x180020105  call    ?ValueExists@RegistryKey@@QEBA_NPEB_W@Z; RegistryKey::ValueExists(wchar_t const *)
0x18002010a  test    al, al
0x18002010c  jz      short loc_18002012E
0x18002010e  xor     r9d, r9d
0x180020111  xor     r8d, r8d
0x180020114  lea     rdx, aMediatype; "*MediaType"
0x18002011b  lea     rcx, [rsp+168h+var_A8]
0x180020123  call    ?GetValueDword@RegistryKey@@QEBAKPEB_WW4EncodingOptions@1@W4MissingValueDisposition@1@@Z; RegistryKey::GetValueDword(wchar_t const *,RegistryKey::EncodingOptions,RegistryKey::MissingValueDisposition)
0x180020128  mov     esi, eax
0x18002012a  mov     [rsp+168h+var_EC], eax
0x18002012e  lea     rdx, aPhysicalmediat; "*PhysicalMediaType"
0x180020135  lea     rcx, [rsp+168h+var_A8]; this
0x18002013d  call    ?ValueExists@RegistryKey@@QEBA_NPEB_W@Z; RegistryKey::ValueExists(wchar_t const *)
0x180020142  test    al, al
0x180020144  jz      short loc_18002016A
0x180020146  xor     r9d, r9d
0x180020149  xor     r8d, r8d
0x18002014c  lea     rdx, aPhysicalmediat; "*PhysicalMediaType"
0x180020153  lea     rcx, [rsp+168h+var_A8]
0x18002015b  call    ?GetValueDword@RegistryKey@@QEBAKPEB_WW4EncodingOptions@1@W4MissingValueDisposition@1@@Z; RegistryKey::GetValueDword(wchar_t const *,RegistryKey::EncodingOptions,RegistryKey::MissingValueDisposition)
0x180020160  mov     r14d, eax
0x180020163  mov     [rsp+168h+var_E8], eax
0x18002016a  lea     rcx, [rsp+168h+var_A8]
0x180020172  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180020177  nop
0x180020178  jmp     short loc_18002019B
0x18002017a  mov     r12b, [rsp+168h+var_F8]
0x18002017f  mov     ebx, [rsp+168h+var_F4]
0x180020183  mov     edi, [rsp+168h+var_F0]
0x180020187  mov     esi, [rsp+168h+var_EC]
0x18002018b  mov     r14d, [rsp+168h+var_E8]
0x180020193  mov     r15, [rsp+168h+var_E0]
0x18002019b  mov     eax, cs:dword_180049000
0x1800201a1  cmp     eax, 5
0x1800201a4  jbe     loc_1800202BE
0x1800201aa  mov     rdx, 400000000000h
0x1800201b4  lea     rcx, dword_180049000
0x1800201bb  call    _tlgKeywordOn
0x1800201c0  test    al, al
0x1800201c2  jz      loc_1800202BE
0x1800201c8  mov     [rsp+168h+var_E8], r14d
0x1800201d0  mov     [rsp+168h+var_EC], esi
0x1800201d4  mov     [rsp+168h+var_F0], edi
0x1800201d8  mov     [rsp+168h+var_F4], ebx
0x1800201dc  lea     rcx, [rsp+168h+var_90]
0x1800201e4  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800201e9  mov     [rsp+168h+var_E0], rax
0x1800201f1  lea     rcx, [rsp+168h+var_70]
0x1800201f9  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800201fe  mov     [rsp+168h+var_D8], rax
0x180020206  lea     rcx, [rsp+168h+var_50]
0x18002020e  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180020213  mov     [rsp+168h+var_D0], rax
0x18002021b  mov     [rsp+168h+var_F8], r12b
0x180020220  mov     rcx, r15
0x180020223  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180020228  mov     [rsp+168h+var_A0], rax
0x180020230  mov     dword ptr [rsp+168h+var_A8], 0
0x18002023b  lea     rax, [rsp+168h+var_E8]
0x180020243  mov     [rsp+168h+var_100], rax
0x180020248  lea     rax, [rsp+168h+var_EC]
0x18002024d  mov     [rsp+168h+var_108], rax
0x180020252  lea     rax, [rsp+168h+var_F0]
0x180020257  mov     [rsp+168h+var_110], rax
0x18002025c  lea     rax, [rsp+168h+var_F4]
0x180020261  mov     [rsp+168h+var_118], rax
0x180020266  lea     rax, [rsp+168h+var_E0]
0x18002026e  mov     [rsp+168h+var_120], rax
0x180020273  lea     rax, [rsp+168h+var_D8]
0x18002027b  mov     [rsp+168h+var_128], rax
0x180020280  lea     rax, [rsp+168h+var_D0]
0x180020288  mov     [rsp+168h+var_130], rax
0x18002028d  lea     rax, [rsp+168h+var_F8]
0x180020292  mov     [rsp+168h+var_138], rax
0x180020297  lea     rax, [rsp+168h+var_A0]
0x18002029f  mov     [rsp+168h+var_140], rax
0x1800202a4  lea     rax, [rsp+168h+var_A8]
0x1800202ac  mov     [rsp+168h+var_148], rax
0x1800202b1  lea     rdx, byte_1800419AF
0x1800202b8  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@_W@@U?$_tlgWrapperByVal@$00@@U2@U2@U2@U1@U1@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapperByVal@$00@@4443333@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<1>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<1> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800202bd  nop
0x1800202be  lea     rcx, [rsp+168h+var_90]
0x1800202c6  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800202cb  nop
0x1800202cc  lea     rcx, [rsp+168h+var_70]
0x1800202d4  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800202d9  nop
0x1800202da  lea     rcx, [rsp+168h+var_50]
0x1800202e2  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800202e7  mov     rcx, [rsp+168h+var_30]
0x1800202ef  xor     rcx, rsp; StackCookie
0x1800202f2  call    __security_check_cookie
0x1800202f7  mov     rbx, [rsp+168h+arg_10]
0x1800202ff  add     rsp, 140h
0x180020306  pop     r15
0x180020308  pop     r14
0x18002030a  pop     r12
0x18002030c  pop     rdi
0x18002030d  pop     rsi
0x18002030e  retn
```
