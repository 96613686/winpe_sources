# CGnssPnPManagerImpl::OnDeviceInterfaceArrival(CGnssPnPManagerImpl::GnssDeviceInterfaceProperty const &,bool)

- ea: `0x1800e7ea0`
- end: `0x1800e84c8`
- name: `?OnDeviceInterfaceArrival@CGnssPnPManagerImpl@@AEAAJAEBUGnssDeviceInterfaceProperty@1@_N@Z`
- size: `1576`
- prototype: `__int64 __fastcall(CGnssPnPManagerImpl *this, const struct CGnssPnPManagerImpl::GnssDeviceInterfaceProperty *, char)`
- caller_count: `0`
- callee_count: `28`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x1800044a4`
- `0x1800045c8`
- `0x1800048ec`
- `0x180019704`
- `0x180020994`
- `0x180020af8`
- `0x180020c64`
- `0x180022da4`
- `0x18004a264`
- `0x18006807c`
- `0x18008bc40`
- `0x18008c07c`
- `0x18009c344`
- `0x1800a0a88`
- `0x1800a98c0`
- `0x1800aa5ac`
- `0x1800d2468`
- `0x1800dc7c8`
- `0x1800df99c`
- `0x1800e720c`
- `0x1800e7990`
- `0x1800e7aac`
- `0x1800e7e64`
- `0x1800e7ea0`
- `0x1800e8d18`
- `0x1800e9160`
- `0x1800e9198`
- `0x18015e010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800e81f0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800e81f0`
- `api-ms-win-core-sysinfo-l1-2-3!GetOsManufacturingMode` at `0x1800e7f10`
- `api-ms-win-core-sysinfo-l1-2-3!GetOsManufacturingMode` at `0x1800e7f10`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x1800e82cd`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x1800e82cd`
- `api-ms-win-devices-config-l1-1-1!CM_Register_Notification` at `0x1800e82a1`
- `api-ms-win-devices-config-l1-1-1!CM_Register_Notification` at `0x1800e82a1`

## pseudocode

```c
__int64 __fastcall CGnssPnPManagerImpl::OnDeviceInterfaceArrival(
        CGnssPnPManagerImpl *this,
        const struct CGnssPnPManagerImpl::GnssDeviceInterfaceProperty *a2,
        char a3)
{
  __int64 result; // rax
  char v7; // r14
  __int64 v8; // rdx
  const char *v9; // r9
  bool v10; // si
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // rdx
  int v14; // ecx
  int v15; // r8d
  int v16; // eax
  __int64 v17; // rdx
  unsigned int v18; // ebx
  __int64 v19; // rdx
  __int64 v20; // rax
  __int64 v21; // r8
  __int64 (__fastcall *v22)(__int64, _QWORD, char *, __int64 *); // r10
  __int64 v23; // r11
  int v24; // eax
  __int64 **v25; // r14
  const WCHAR *v26; // rax
  HANDLE FileW; // rax
  __int64 v28; // rdx
  void *v29; // rdx
  unsigned int v30; // r8d
  const char *v31; // r9
  __int64 v32; // rcx
  CONFIGRET v33; // ebx
  signed int v34; // eax
  __int64 (__fastcall *v35)(__int64, __int64, __int128 *, __int64 *); // r10
  __int64 v36; // r11
  int v37; // eax
  int v38; // ebx
  __int64 v39; // rdx
  __int64 v40; // rdx
  __int64 v41; // rdx
  __int64 v42; // rcx
  int *dwCreationDisposition; // [rsp+20h] [rbp-268h]
  int dwCreationDispositiona; // [rsp+20h] [rbp-268h]
  __int64 v45; // [rsp+68h] [rbp-220h] BYREF
  int v46[2]; // [rsp+70h] [rbp-218h] BYREF
  __int64 v47; // [rsp+78h] [rbp-210h] BYREF
  char v48; // [rsp+80h] [rbp-208h]
  _QWORD v49[3]; // [rsp+88h] [rbp-200h] BYREF
  _DWORD v50[4]; // [rsp+A0h] [rbp-1E8h] BYREF
  __int64 v51; // [rsp+B0h] [rbp-1D8h]
  int v52; // [rsp+240h] [rbp-48h] BYREF
  __int128 v53; // [rsp+248h] [rbp-40h] BYREF
  __int64 v54; // [rsp+258h] [rbp-30h]
  __int64 v55; // [rsp+260h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+0h]

  if ( *((_BYTE *)this + 352) )
    return 0;
  if ( *((_BYTE *)this + 24) && a3 )
    return 0;
  try
  {
    v7 = `CGnssPnPManagerImpl::OnDeviceInterfaceArrival'::`3'::_lambda_1_::operator()();
    v52 = 0;
    v10 = (unsigned int)GetOsManufacturingMode(&v52) && v52;
    if ( (unsigned int)dword_1801DDF30 > 5 )
    {
      v45 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 32, v8);
      *(_QWORD *)v46 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2, v11);
      dwCreationDisposition = v46;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>>(
        v12,
        byte_1801B03F1);
    }
    if ( v7 && v10 )
    {
      if ( (unsigned int)dword_1801DDF30 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1801DDF30, 0x400000000000LL) )
      {
        v45 = 0x1000000;
        *(_QWORD *)v46 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2, v13);
        v49[0] = 1;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
          v14,
          (unsigned int)word_1801B021A,
          v15,
          (unsigned int)v49,
          (__int64)v46,
          (__int64)&v45);
      }
      return 0;
    }
    if ( !*((_QWORD *)a2 + 2) )
      return 2147942487LL;
    std::_Tree<std::_Tmap_traits<std::wstring,bool,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,bool>>,0>>::_Emplace<std::wstring const &,bool const &>(
      (char *)this + 8,
      &v47,
      a2,
      (char *)a2 + 32);
    if ( !v48 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x10B,
        (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\gnssadapter\\gnsspnpmanager.cpp",
        (const char *)0x8000FFFFLL,
        (int)dwCreationDisposition);
    v53 = 0;
    v54 = 0;
    v55 = 7;
    LOWORD(v53) = 0;
    v16 = CGnssPnPManagerImpl::SelectDevice(this, &v53);
    v18 = v16;
    if ( v16 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x111,
        (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\gnssadapter\\gnsspnpmanager.cpp",
        (const char *)(unsigned int)v16,
        (int)dwCreationDisposition);
      std::wstring::_Tidy_deallocate(&v53);
      return v18;
    }
    if ( *((_BYTE *)this + 24) )
    {
      std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 32, v17);
      v20 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v53, v19);
      if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(v20, v54, v21, *((_QWORD *)this + 6)) )
      {
LABEL_26:
        std::wstring::_Tidy_deallocate(&v53);
        return 0;
      }
      std::shared_ptr<GEOFENCE_DISTANCE>::shared_ptr<GEOFENCE_DISTANCE>(&v47, (char *)this + 72);
      v24 = v22(v23, 0, (char *)this + 32, &v47);
      if ( v24 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x11A,
          (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\gnssadapter\\gnsspnpmanager.cpp",
          (const char *)(unsigned int)v24,
          (int)dwCreationDisposition);
      CGnssPnPManagerImpl::CleanupFileHandles(this);
      *((_BYTE *)this + 24) = 0;
      std::wstring::_Eos((char *)this + 32, 0);
    }
    v25 = (__int64 **)((char *)this + 72);
    v26 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v53, v17);
    FileW = CreateFileW(v26, 0xC0000000, 3u, 0, 3u, 0x40000000u, 0);
    wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::reset(
      (char *)this + 72,
      FileW);
    if ( (unsigned __int8)wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::is_valid(
                            (char *)this + 72,
                            v28) )
    {
      memset_0(v50, 0, 0x1A0u);
      v50[0] = 416;
      v50[2] = 1;
      if ( *v25 )
        v32 = **v25;
      else
        v32 = 0;
      v51 = v32;
      wil::details::unique_storage<wil::details::resource_policy<HCMNOTIFICATION__ *,unsigned long (*)(HCMNOTIFICATION__ *),&unsigned long CM_Unregister_Notification(HCMNOTIFICATION__ *),wistd::integral_constant<unsigned __int64,0>,HCMNOTIFICATION__ *,HCMNOTIFICATION__ *,0,std::nullptr_t>>::reset(
        (char *)this + 64,
        0);
      v33 = CM_Register_Notification(v50, this, &CGnssPnPManagerImpl::PnPNotificationCallback, (char *)this + 64);
      if ( v33 )
      {
        std::_Tree<std::_Tmap_traits<std::wstring,bool,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,bool>>,0>>::erase(
          (char *)this + 8,
          &v53);
        CGnssPnPManagerImpl::CleanupFileHandles(this);
        v34 = CM_MapCrToWin32Err(v33, 0xDu);
        if ( v34 > 0 )
          v34 = (unsigned __int16)v34 | 0x80070000;
        wil::details::in1diag3::Log_Hr(
          retaddr,
          (void *)0x13F,
          (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\gnssadapter\\gnsspnpmanager.cpp",
          (const char *)(unsigned int)v34,
          dwCreationDispositiona);
        std::wstring::_Tidy_deallocate(&v53);
        return 0;
      }
      std::shared_ptr<GEOFENCE_DISTANCE>::shared_ptr<GEOFENCE_DISTANCE>(&v47, (char *)this + 72);
      v37 = v35(v36, 1, &v53, &v47);
      v38 = v37;
      if ( v37 >= 0 )
      {
        *((_BYTE *)this + 24) = 1;
        std::wstring::operator=((char *)this + 32, &v53);
        ResettableTimer::Reset((CGnssPnPManagerImpl *)((char *)this + 400));
      }
      else
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x147,
          (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\gnssadapter\\gnsspnpmanager.cpp",
          (const char *)(unsigned int)v37,
          dwCreationDispositiona);
        CGnssPnPManagerImpl::CleanupFileHandles(this);
        if ( !*((_DWORD *)this + 136) )
        {
          std::wstring::operator=((char *)this + 360, **((_QWORD **)this + 1) + 32LL);
          *((_BYTE *)this + 392) = *(_BYTE *)(**((_QWORD **)this + 1) + 64LL);
          ++*((_DWORD *)this + 136);
          ResettableTimer::SetDueTimeFromNow((char *)this + 400, 0x2710u);
        }
        std::_Tree<std::_Tmap_traits<std::wstring,bool,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,bool>>,0>>::erase(
          (char *)this + 8,
          &v53);
      }
      if ( (unsigned int)dword_1801DDF30 > 5 )
      {
        v46[0] = v38;
        v49[0] = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 32, v39);
        v49[1] = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v53, v40);
        LODWORD(v45) = *((unsigned __int8 *)this + 392);
        v47 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 360, v41);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>>(
          v42,
          byte_1801B0351);
      }
      goto LABEL_26;
    }
    std::_Tree<std::_Tmap_traits<std::wstring,bool,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,bool>>,0>>::erase(
      (char *)this + 8,
      &v53);
    wil::details::in1diag3::Log_GetLastError(retaddr, v29, v30, v31);
    std::wstring::_Tidy_deallocate(&v53);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x16E,
                           (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\gnssadapter\\gnsspnpmanager.cpp",
                           v9);
  }
  return result;
}

```

## disassembly

```asm
0x1800e7ea0  mov     [rsp+arg_10], rbx
0x1800e7ea5  mov     [rsp+arg_18], rsi
0x1800e7eaa  push    rdi
0x1800e7eab  push    r14
0x1800e7ead  push    r15
0x1800e7eaf  sub     rsp, 270h
0x1800e7eb6  mov     rax, cs:__security_cookie
0x1800e7ebd  xor     rax, rsp
0x1800e7ec0  mov     [rsp+288h+var_20], rax
0x1800e7ec8  mov     r15b, r8b
0x1800e7ecb  mov     rbx, rdx
0x1800e7ece  mov     rdi, rcx
0x1800e7ed1  mov     al, [rcx+160h]
0x1800e7ed7  nop
0x1800e7ed8  test    al, al
0x1800e7eda  jz      short loc_1800E7EE3
0x1800e7edc  xor     eax, eax
0x1800e7ede  jmp     loc_1800E849E
0x1800e7ee3  cmp     byte ptr [rcx+18h], 0
0x1800e7ee7  jz      short loc_1800E7EF5
0x1800e7ee9  test    r15b, r15b
0x1800e7eec  jz      short loc_1800E7EF5
0x1800e7eee  xor     eax, eax
0x1800e7ef0  jmp     loc_1800E849E
0x1800e7ef5  call    ??R_lambda_1_@?2??OnDeviceInterfaceArrival@CGnssPnPManagerImpl@@AEAAJAEBUGnssDeviceInterfaceProperty@2@_N@Z@QEBA_NXZ; `CGnssPnPManagerImpl::OnDeviceInterfaceArrival(CGnssPnPManagerImpl::GnssDeviceInterfaceProperty const &,bool)'::`3'::_lambda_1_::operator()(void)
0x1800e7efa  mov     r14b, al
0x1800e7efd  mov     [rsp+288h+var_48], 0
0x1800e7f08  lea     rcx, [rsp+288h+var_48]
0x1800e7f10  call    cs:__imp_GetOsManufacturingMode
0x1800e7f16  test    eax, eax
0x1800e7f18  jz      short loc_1800E7F29
0x1800e7f1a  cmp     [rsp+288h+var_48], 0
0x1800e7f22  jz      short loc_1800E7F29
0x1800e7f24  mov     sil, 1
0x1800e7f27  jmp     short loc_1800E7F2C
0x1800e7f29  xor     sil, sil
0x1800e7f2c  mov     eax, cs:dword_1801DDF30
0x1800e7f32  cmp     eax, 5
0x1800e7f35  jbe     loc_1800E7FC5
0x1800e7f3b  mov     [rsp+288h+var_227], sil
0x1800e7f40  mov     [rsp+288h+var_226], r14b
0x1800e7f45  lea     rcx, [rdi+20h]
0x1800e7f49  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800e7f4e  mov     [rsp+288h+var_220], rax
0x1800e7f53  mov     al, [rdi+18h]
0x1800e7f56  mov     [rsp+288h+var_225], al
0x1800e7f5a  mov     [rsp+288h+var_224], r15b
0x1800e7f5f  mov     al, [rbx+20h]
0x1800e7f62  mov     [rsp+288h+var_228], al
0x1800e7f66  mov     rcx, rbx
0x1800e7f69  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800e7f6e  mov     qword ptr [rsp+288h+var_218], rax
0x1800e7f73  lea     rax, [rsp+288h+var_227]
0x1800e7f78  mov     [rsp+288h+var_238], rax
0x1800e7f7d  lea     rax, [rsp+288h+var_226]
0x1800e7f82  mov     [rsp+288h+var_240], rax
0x1800e7f87  lea     rax, [rsp+288h+var_220]
0x1800e7f8c  mov     [rsp+288h+var_248], rax
0x1800e7f91  lea     rax, [rsp+288h+var_225]
0x1800e7f96  mov     [rsp+288h+var_250], rax
0x1800e7f9b  lea     rax, [rsp+288h+var_224]
0x1800e7fa0  mov     [rsp+288h+hTemplateFile], rax
0x1800e7fa5  lea     rax, [rsp+288h+var_228]
0x1800e7faa  mov     qword ptr [rsp+288h+dwFlagsAndAttributes], rax
0x1800e7faf  lea     rax, [rsp+288h+var_218]
0x1800e7fb4  mov     qword ptr [rsp+288h+dwCreationDisposition], rax; int
0x1800e7fb9  lea     rdx, byte_1801B03F1
0x1800e7fc0  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$00@@U2@U2@U1@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$00@@44344@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapSz<ushort>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &)
0x1800e7fc5  test    r14b, r14b
0x1800e7fc8  jz      short loc_1800E8045
0x1800e7fca  test    sil, sil
0x1800e7fcd  jz      short loc_1800E8045
0x1800e7fcf  mov     eax, cs:dword_1801DDF30
0x1800e7fd5  cmp     eax, 5
0x1800e7fd8  jbe     short loc_1800E803E
0x1800e7fda  mov     rdx, 400000000000h
0x1800e7fe4  lea     rcx, dword_1801DDF30
0x1800e7feb  call    _tlgKeywordOn
0x1800e7ff0  test    al, al
0x1800e7ff2  jz      short loc_1800E803E
0x1800e7ff4  mov     [rsp+288h+var_220], 1000000h
0x1800e7ffd  mov     rcx, rbx
0x1800e8000  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800e8005  mov     qword ptr [rsp+288h+var_218], rax
0x1800e800a  mov     [rsp+288h+var_200], 1
0x1800e8016  lea     rax, [rsp+288h+var_220]
0x1800e801b  mov     qword ptr [rsp+288h+dwFlagsAndAttributes], rax
0x1800e8020  lea     rax, [rsp+288h+var_218]
0x1800e8025  mov     qword ptr [rsp+288h+dwCreationDisposition], rax
0x1800e802a  lea     r9, [rsp+288h+var_200]
0x1800e8032  lea     rdx, word_1801B021A
0x1800e8039  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBX1IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteAgg@@YAJ011I2@ZPEBX@@SAJPEBU_tlgProvider_t@@PEBX1AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,void const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteAgg(_tlgProvider_t const *,void const *,void const *,uint,_EVENT_DATA_DESCRIPTOR *),void const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,void const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &)
0x1800e803e  xor     eax, eax
0x1800e8040  jmp     loc_1800E849E
0x1800e8045  cmp     qword ptr [rbx+10h], 0
0x1800e804a  jnz     short loc_1800E8056
0x1800e804c  mov     eax, 80070057h
0x1800e8051  jmp     loc_1800E849E
0x1800e8056  lea     r9, [rbx+20h]
0x1800e805a  lea     rcx, [rdi+8]
0x1800e805e  mov     r8, rbx
0x1800e8061  lea     rdx, [rsp+288h+var_210]
0x1800e8066  call    ??$_Emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEB_N@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_NU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@std@@PEAX@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@AEB_N@Z; std::_Tree<std::_Tmap_traits<std::wstring,bool,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,bool>>,0>>::_Emplace<std::wstring const &,bool const &>(std::wstring const &,bool const &)
0x1800e806b  mov     rcx, [rsp+288h]; this
0x1800e8073  lea     rsi, aOnecoreuapDriv_67; "onecoreuap\\drivers\\mobilepc\\location"...
0x1800e807a  cmp     [rsp+288h+var_208], 0
0x1800e8082  jnz     short loc_1800E8097
0x1800e8084  mov     r9d, 8000FFFFh; char *
0x1800e808a  mov     r8, rsi; unsigned int
0x1800e808d  mov     edx, 10Bh; void *
0x1800e8092  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800e8097  xorps   xmm0, xmm0
0x1800e809a  movups  [rsp+288h+var_40], xmm0
0x1800e80a2  mov     [rsp+288h+var_30], 0
0x1800e80ae  mov     [rsp+288h+var_28], 7
0x1800e80ba  xor     eax, eax
0x1800e80bc  mov     word ptr [rsp+288h+var_40], ax
0x1800e80c4  lea     rdx, [rsp+288h+var_40]
0x1800e80cc  mov     rcx, rdi
0x1800e80cf  call    ?SelectDevice@CGnssPnPManagerImpl@@AEBAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CGnssPnPManagerImpl::SelectDevice(std::wstring &)
0x1800e80d4  mov     ebx, eax
0x1800e80d6  test    eax, eax
0x1800e80d8  jns     short loc_1800E8107
0x1800e80da  mov     rcx, [rsp+288h]; this
0x1800e80e2  mov     r9d, eax; char *
0x1800e80e5  mov     r8, rsi; unsigned int
0x1800e80e8  mov     edx, 111h; void *
0x1800e80ed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e80f2  nop
0x1800e80f3  lea     rcx, [rsp+288h+var_40]
0x1800e80fb  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e8100  mov     eax, ebx
0x1800e8102  jmp     loc_1800E849E
0x1800e8107  cmp     byte ptr [rdi+18h], 0
0x1800e810b  jz      loc_1800E81B8
0x1800e8111  lea     rbx, [rdi+20h]
0x1800e8115  mov     rcx, rbx
0x1800e8118  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800e811d  mov     r8, rax
0x1800e8120  lea     rcx, [rsp+288h+var_40]
0x1800e8128  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800e812d  mov     rcx, rax
0x1800e8130  mov     r9, [rbx+10h]
0x1800e8134  mov     rdx, [rsp+288h+var_30]
0x1800e813c  call    ??$_Traits_equal@U?$char_traits@G@std@@@std@@YA_NQEBG_K01@Z; std::_Traits_equal<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x1800e8141  test    al, al
0x1800e8143  jz      short loc_1800E8159
0x1800e8145  lea     rcx, [rsp+288h+var_40]
0x1800e814d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e8152  xor     eax, eax
0x1800e8154  jmp     loc_1800E849E
0x1800e8159  mov     r11, [rdi+58h]
0x1800e815d  mov     rax, [r11]
0x1800e8160  mov     r10, [rax]
0x1800e8163  lea     rdx, [rdi+48h]
0x1800e8167  lea     rcx, [rsp+288h+var_210]
0x1800e816c  call    ??0?$shared_ptr@UGEOFENCE_DISTANCE@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<GEOFENCE_DISTANCE>::shared_ptr<GEOFENCE_DISTANCE>(std::shared_ptr<GEOFENCE_DISTANCE> const &)
0x1800e8171  lea     r9, [rsp+288h+var_210]
0x1800e8176  mov     r8, rbx
0x1800e8179  xor     edx, edx
0x1800e817b  mov     rcx, r11
0x1800e817e  mov     rax, r10
0x1800e8181  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e8186  mov     rcx, [rsp+288h]; this
0x1800e818e  test    eax, eax
0x1800e8190  jns     short loc_1800E81A2
0x1800e8192  mov     r9d, eax; char *
0x1800e8195  mov     r8, rsi; unsigned int
0x1800e8198  mov     edx, 11Ah; void *
0x1800e819d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800e81a2  mov     rcx, rdi; this
0x1800e81a5  call    ?CleanupFileHandles@CGnssPnPManagerImpl@@AEAAJXZ; CGnssPnPManagerImpl::CleanupFileHandles(void)
0x1800e81aa  mov     byte ptr [rdi+18h], 0
0x1800e81ae  xor     edx, edx
0x1800e81b0  mov     rcx, rbx
0x1800e81b3  call    ?_Eos@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAX_K@Z; std::wstring::_Eos(unsigned __int64)
0x1800e81b8  lea     r14, [rdi+48h]
0x1800e81bc  lea     rcx, [rsp+288h+var_40]
0x1800e81c4  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800e81c9  mov     rcx, rax; lpFileName
0x1800e81cc  mov     [rsp+288h+hTemplateFile], 0; hTemplateFile
0x1800e81d5  mov     [rsp+288h+dwFlagsAndAttributes], 40000000h; dwFlagsAndAttributes
0x1800e81dd  mov     r8d, 3; dwShareMode
0x1800e81e3  mov     [rsp+288h+dwCreationDisposition], r8d; int
0x1800e81e8  xor     r9d, r9d; lpSecurityAttributes
0x1800e81eb  mov     edx, 0C0000000h; dwDesiredAccess
0x1800e81f0  call    cs:__imp_CreateFileW
0x1800e81f6  mov     rdx, rax
0x1800e81f9  mov     rcx, r14
0x1800e81fc  call    ?reset@?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::reset(void *)
0x1800e8201  mov     rcx, r14
0x1800e8204  call    ?is_valid@?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEBA_NXZ; wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::is_valid(void)
0x1800e8209  test    al, al
0x1800e820b  jnz     short loc_1800E8240
0x1800e820d  lea     rcx, [rdi+8]
0x1800e8211  lea     rdx, [rsp+288h+var_40]
0x1800e8219  call    ?erase@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_NU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@std@@@2@$0A@@std@@@std@@QEAA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,bool,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,bool>>,0>>::erase(std::wstring const &)
0x1800e821e  mov     rcx, [rsp+288h]; this
0x1800e8226  call    ?Log_GetLastError@in1diag3@details@wil@@YAKPEAXIPEBD@Z; wil::details::in1diag3::Log_GetLastError(void *,uint,char const *)
0x1800e822b  nop
0x1800e822c  lea     rcx, [rsp+288h+var_40]
0x1800e8234  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e8239  xor     eax, eax
0x1800e823b  jmp     loc_1800E849E
0x1800e8240  mov     ebx, 1A0h
0x1800e8245  mov     r8d, ebx; Size
0x1800e8248  xor     edx, edx; Val
0x1800e824a  lea     rcx, [rsp+288h+var_1E8]; void *
0x1800e8252  call    memset_0
0x1800e8257  mov     [rsp+288h+var_1E8], ebx
0x1800e825e  mov     [rsp+288h+var_1E0], 1
0x1800e8269  mov     rax, [r14]
0x1800e826c  test    rax, rax
0x1800e826f  jz      short loc_1800E8276
0x1800e8271  mov     rcx, [rax]
0x1800e8274  jmp     short loc_1800E8278
0x1800e8276  xor     ecx, ecx
0x1800e8278  mov     [rsp+288h+var_1D8], rcx
0x1800e8280  xor     edx, edx
0x1800e8282  lea     rcx, [rdi+40h]
0x1800e8286  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHCMNOTIFICATION__@@P6AKPEAU1@@Z$1?CM_Unregister_Notification@@YAK0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHCMNOTIFICATION__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HCMNOTIFICATION__ *,ulong (*)(HCMNOTIFICATION__ *),&CM_Unregister_Notification(HCMNOTIFICATION__ *),wistd::integral_constant<unsigned __int64,0>,HCMNOTIFICATION__ *,HCMNOTIFICATION__ *,0,std::nullptr_t>>::reset(HCMNOTIFICATION__ *)
0x1800e828b  lea     r9, [rdi+40h]
0x1800e828f  lea     r8, ?PnPNotificationCallback@CGnssPnPManagerImpl@@CAKPEAUHCMNOTIFICATION__@@PEAXW4_CM_NOTIFY_ACTION@@PEAU_CM_NOTIFY_EVENT_DATA@@K@Z; CGnssPnPManagerImpl::PnPNotificationCallback(HCMNOTIFICATION__ *,void *,_CM_NOTIFY_ACTION,_CM_NOTIFY_EVENT_DATA *,ulong)
0x1800e8296  mov     rdx, rdi
0x1800e8299  lea     rcx, [rsp+288h+var_1E8]
0x1800e82a1  call    cs:__imp_CM_Register_Notification
0x1800e82a7  mov     ebx, eax
0x1800e82a9  test    eax, eax
0x1800e82ab  jz      short loc_1800E830C
0x1800e82ad  lea     rcx, [rdi+8]
0x1800e82b1  lea     rdx, [rsp+288h+var_40]
0x1800e82b9  call    ?erase@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_NU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@std@@@2@$0A@@std@@@std@@QEAA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,bool,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,bool>>,0>>::erase(std::wstring const &)
0x1800e82be  mov     rcx, rdi; this
0x1800e82c1  call    ?CleanupFileHandles@CGnssPnPManagerImpl@@AEAAJXZ; CGnssPnPManagerImpl::CleanupFileHandles(void)
0x1800e82c6  mov     edx, 0Dh; DefaultErr
0x1800e82cb  mov     ecx, ebx; CmReturnCode
0x1800e82cd  call    cs:__imp_CM_MapCrToWin32Err
0x1800e82d3  test    eax, eax
0x1800e82d5  jle     short loc_1800E82DF
0x1800e82d7  movzx   eax, ax
0x1800e82da  or      eax, 80070000h
0x1800e82df  mov     rcx, [rsp+288h]; this
0x1800e82e7  mov     r9d, eax; char *
0x1800e82ea  mov     r8, rsi; unsigned int
0x1800e82ed  mov     edx, 13Fh; void *
0x1800e82f2  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x1800e82f7  nop
0x1800e82f8  lea     rcx, [rsp+288h+var_40]
0x1800e8300  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800e8305  xor     eax, eax
0x1800e8307  jmp     loc_1800E849E
0x1800e830c  mov     r11, [rdi+58h]
0x1800e8310  mov     rax, [r11]
0x1800e8313  mov     r10, [rax]
0x1800e8316  mov     rdx, r14
0x1800e8319  lea     rcx, [rsp+288h+var_210]
0x1800e831e  call    ??0?$shared_ptr@UGEOFENCE_DISTANCE@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<GEOFENCE_DISTANCE>::shared_ptr<GEOFENCE_DISTANCE>(std::shared_ptr<GEOFENCE_DISTANCE> const &)
0x1800e8323  lea     r9, [rsp+288h+var_210]
0x1800e8328  lea     r8, [rsp+288h+var_40]
0x1800e8330  mov     edx, 1
0x1800e8335  mov     rcx, r11
0x1800e8338  mov     rax, r10
0x1800e833b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e8340  mov     ebx, eax
0x1800e8342  mov     rcx, [rsp+288h]; this
0x1800e834a  test    eax, eax
0x1800e834c  jns     short loc_1800E83C0
0x1800e834e  mov     r9d, eax; char *
0x1800e8351  mov     r8, rsi; unsigned int
0x1800e8354  mov     edx, 147h; void *
0x1800e8359  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800e835e  mov     rcx, rdi; this
0x1800e8361  call    ?CleanupFileHandles@CGnssPnPManagerImpl@@AEAAJXZ; CGnssPnPManagerImpl::CleanupFileHandles(void)
0x1800e8366  cmp     dword ptr [rdi+220h], 0
0x1800e836d  jnz     short loc_1800E83AD
0x1800e836f  mov     rax, [rdi+8]
0x1800e8373  mov     rdx, [rax]
0x1800e8376  add     rdx, 20h ; ' '
0x1800e837a  lea     rcx, [rdi+168h]
0x1800e8381  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800e8386  mov     rax, [rdi+8]
0x1800e838a  mov     rcx, [rax]
0x1800e838d  mov     al, [rcx+40h]
0x1800e8390  mov     [rdi+188h], al
0x1800e8396  inc     dword ptr [rdi+220h]
0x1800e839c  lea     rcx, [rdi+190h]; pv
0x1800e83a3  mov     edx, 2710h; unsigned int
0x1800e83a8  call    ?SetDueTimeFromNow@ResettableTimer@@QEAAJK@Z; ResettableTimer::SetDueTimeFromNow(ulong)
0x1800e83ad  lea     rcx, [rdi+8]
0x1800e83b1  lea     rdx, [rsp+288h+var_40]
0x1800e83b9  call    ?erase@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_NU?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@std@@@2@$0A@@std@@@std@@QEAA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,bool,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,bool>>,0>>::erase(std::wstring const &)
0x1800e83be  jmp     short loc_1800E83E1
0x1800e83c0  mov     byte ptr [rdi+18h], 1
0x1800e83c4  lea     rcx, [rdi+20h]
0x1800e83c8  lea     rdx, [rsp+288h+var_40]
0x1800e83d0  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800e83d5  lea     rcx, [rdi+190h]; this
0x1800e83dc  call    ?Reset@ResettableTimer@@QEAAXXZ; ResettableTimer::Reset(void)
0x1800e83e1  mov     eax, cs:dword_1801DDF30
0x1800e83e7  cmp     eax, 5
  ... truncated ...
```
