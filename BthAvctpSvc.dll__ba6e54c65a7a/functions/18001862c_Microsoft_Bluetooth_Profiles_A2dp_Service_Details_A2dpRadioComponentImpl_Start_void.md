# Microsoft::Bluetooth::Profiles::A2dp::Service::Details::A2dpRadioComponentImpl::Start(void)

- ea: `0x18001862c`
- end: `0x18001899a`
- name: `?Start@A2dpRadioComponentImpl@Details@Service@A2dp@Profiles@Bluetooth@Microsoft@@QEAAXXZ`
- size: `878`
- prototype: `void __fastcall(Microsoft::Bluetooth::Profiles::A2dp::Service::Details::A2dpRadioComponentImpl *__hidden this)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180017e10`

## callees

- `0x180001dd0`
- `0x180009920`
- `0x18000b69c`
- `0x18000de78`
- `0x18000e16c`
- `0x18000fccc`
- `0x180012554`
- `0x180014fa0`
- `0x1800151f4`
- `0x180015b1c`
- `0x1800163ac`
- `0x180016b0c`
- `0x18001862c`
- `0x180019d20`
- `0x180019f80`
- `0x18001d428`
- `0x18005f010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001868b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800186c6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180018743`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001868b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800186c6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180018743`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800186ff`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001877e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800186ff`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001877e`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall Microsoft::Bluetooth::Profiles::A2dp::Service::Details::A2dpRadioComponentImpl::Start(
        Microsoft::Bluetooth::Profiles::A2dp::Service::Details::A2dpRadioComponentImpl *this)
{
  int v2; // edx
  __int64 v3; // r8
  __int64 *v4; // rax
  __int64 v5; // rcx
  __int64 v6; // rdx
  std::_Ref_count_base *v7; // rcx
  void (__fastcall ***v8)(_QWORD, __int64, _QWORD *); // rdi
  void (__fastcall *v9)(_QWORD, __int64, _QWORD *); // rbx
  __int64 v10; // rax
  std::_Ref_count_base *v11; // rcx
  __int64 v12; // rax
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, _QWORD *, __int64, _OWORD *); // rbx
  __int64 v15; // rax
  __int64 Shared; // rax
  int pvData; // [rsp+50h] [rbp-69h] BYREF
  HKEY hkey; // [rsp+58h] [rbp-61h] BYREF
  DWORD pcbData; // [rsp+60h] [rbp-59h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-51h] BYREF
  __int64 v21; // [rsp+70h] [rbp-49h] BYREF
  std::_Ref_count_base *v22; // [rsp+78h] [rbp-41h]
  _OWORD v23[2]; // [rsp+80h] [rbp-39h] BYREF
  _QWORD v24[10]; // [rsp+A0h] [rbp-19h] BYREF

  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"System\\CurrentControlSet\\Control\\Bluetooth\\Audio\\A2dp",
          0,
          0x20019u,
          &hKey) )
  {
    hkey = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hkey,
      0);
    if ( !RegOpenKeyExW(hKey, L"Sink", 0, 0x20019u, &hkey) )
    {
      pvData = 0;
      pcbData = 4;
      if ( !RegGetValueW(hkey, 0, L"Enabled", 0x10u, 0, &pvData, &pcbData) )
        *((_BYTE *)this + 24) = pvData != 0;
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        &hkey,
        0);
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hkey,
      0);
    if ( !RegOpenKeyExW(hKey, L"Source", 0, 0x20019u, &hkey) )
    {
      pvData = 0;
      pcbData = 4;
      if ( !RegGetValueW(hkey, 0, L"Enabled", 0x10u, 0, &pvData, &pcbData) )
        *((_BYTE *)this + 25) = pvData != 0;
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  if ( *((_BYTE *)this + 24) )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || (LOBYTE(v2) = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u) )
    {
      LOBYTE(v2) = 0;
    }
    LOBYTE(v3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( (_BYTE)v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_AND_TRACE_SF_q(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v2,
        v3,
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        4,
        1,
        10,
        &WPP_21dc346b64563456f091e03a23b35635_Traceguids,
        (char)this);
    LOWORD(pvData) = 4363;
    v4 = (__int64 *)std::make_shared<Microsoft::Bluetooth::Audio::Internal::BluetoothProfileConflictWatcher,unsigned short &>(
                      &v21,
                      &pvData,
                      v3);
    v5 = *v4;
    v6 = v4[1];
    *v4 = 0;
    v4[1] = 0;
    *((_QWORD *)this + 23) = v5;
    v7 = (std::_Ref_count_base *)*((_QWORD *)this + 24);
    *((_QWORD *)this + 24) = v6;
    if ( v7 )
      std::_Ref_count_base::_Decref(v7);
    if ( v22 )
      std::_Ref_count_base::_Decref(v22);
    v8 = (void (__fastcall ***)(_QWORD, __int64, _QWORD *))*((_QWORD *)this + 23);
    v9 = **v8;
    std::weak_ptr<Microsoft::Bluetooth::Foundation::AsyncRequestWithUniqueResultAutoCancel<std::vector<unsigned char>,long>>::weak_ptr<Microsoft::Bluetooth::Foundation::AsyncRequestWithUniqueResultAutoCancel<std::vector<unsigned char>,long>>(
      &v21,
      (_QWORD *)this + 1);
    v10 = v21;
    v11 = v22;
    v21 = 0;
    v22 = 0;
    v24[0] = off_180060C38;
    v24[1] = v10;
    v24[2] = v11;
    v23[0] = 0;
    v24[7] = v24;
    v12 = Microsoft::Bluetooth::Profiles::A2dp::Service::Details::A2dpRadioComponentImpl::BuildConflictingDeviceFilterExpression(
            &hKey,
            (unsigned __int16)pvData);
    v9(v8, v12, v24);
    std::_Func_class<void,enum Microsoft::Bluetooth::Profiles::Avrcp::AvrcpTransportEnumerator::DeviceChangeEventType,unsigned short const *,std::shared_ptr<Microsoft::Bluetooth::Profiles::Avrcp::AvrcpTransport> const &>::_Tidy(v24);
  }
  if ( *((_BYTE *)this + 25) )
  {
    v13 = *((_QWORD *)this + 22);
    v14 = *(__int64 (__fastcall **)(__int64, _QWORD *, __int64, _OWORD *))(*(_QWORD *)v13 + 8LL);
    std::wstring::wstring((__int64)v23, (__int64)L"Audio Source");
    v15 = v14(v13, v24, 259, v23);
    Microsoft::Bluetooth::Foundation::Token::operator=((char *)this + 104, v15);
    Microsoft::Bluetooth::Foundation::Token::~Token((Microsoft::Bluetooth::Foundation::Token *)v24);
    std::wstring::_Tidy_deallocate(v23);
    Shared = Microsoft::Bluetooth::Profiles::A2dp::Service::A2dpDeviceEnumerator::MakeShared(
               &v21,
               &AudioSinkServiceClass_UUID);
    std::shared_ptr<Microsoft::Bluetooth::Foundation::AsyncDeviceInterfaceWatcher>::operator=(
      (char *)this + 200,
      Shared);
    if ( v22 )
      std::_Ref_count_base::_Decref(v22);
  }
}

```

## disassembly

```asm
0x18001862c  mov     [rsp-8+arg_8], rbx
0x180018631  mov     [rsp-8+arg_10], rsi
0x180018636  push    rbp
0x180018637  push    rdi
0x180018638  push    r14
0x18001863a  lea     rbp, [rsp-47h]
0x18001863f  sub     rsp, 100h
0x180018646  mov     rax, cs:__security_cookie
0x18001864d  xor     rax, rsp
0x180018650  mov     [rbp+57h+var_20], rax
0x180018654  mov     rsi, rcx
0x180018657  xor     r14d, r14d
0x18001865a  mov     [rbp+57h+hKey], r14
0x18001865e  xor     edx, edx
0x180018660  lea     rcx, [rbp+57h+hKey]
0x180018664  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180018669  lea     rax, [rbp+57h+hKey]
0x18001866d  mov     [rsp+110h+phkResult], rax; phkResult
0x180018672  mov     edi, 20019h
0x180018677  mov     r9d, edi; samDesired
0x18001867a  xor     r8d, r8d; ulOptions
0x18001867d  lea     rdx, SubKey; "System\\CurrentControlSet\\Control\\Blu"...
0x180018684  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001868b  call    cs:__imp_RegOpenKeyExW
0x180018691  lea     ebx, [r14+4]
0x180018695  test    eax, eax
0x180018697  jnz     loc_18001879B
0x18001869d  mov     [rbp+57h+hkey], r14
0x1800186a1  xor     edx, edx
0x1800186a3  lea     rcx, [rbp+57h+hkey]
0x1800186a7  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800186ac  lea     rax, [rbp+57h+hkey]
0x1800186b0  mov     [rsp+110h+phkResult], rax; phkResult
0x1800186b5  mov     r9d, edi; samDesired
0x1800186b8  xor     r8d, r8d; ulOptions
0x1800186bb  lea     rdx, aSink; "Sink"
0x1800186c2  mov     rcx, [rbp+57h+hKey]; hKey
0x1800186c6  call    cs:__imp_RegOpenKeyExW
0x1800186cc  test    eax, eax
0x1800186ce  jnz     short loc_18001871E
0x1800186d0  mov     [rbp+57h+var_C0], r14d
0x1800186d4  mov     [rbp+57h+var_B0], ebx
0x1800186d7  lea     rax, [rbp+57h+var_B0]
0x1800186db  mov     [rsp+110h+pcbData], rax; pcbData
0x1800186e0  lea     rax, [rbp+57h+var_C0]
0x1800186e4  mov     [rsp+110h+pvData], rax; pvData
0x1800186e9  mov     [rsp+110h+phkResult], r14; pdwType
0x1800186ee  lea     r9d, [r14+10h]; dwFlags
0x1800186f2  lea     r8, Value; "Enabled"
0x1800186f9  xor     edx, edx; lpSubKey
0x1800186fb  mov     rcx, [rbp+57h+hkey]; hkey
0x1800186ff  call    cs:__imp_RegGetValueW
0x180018705  test    eax, eax
0x180018707  jnz     short loc_180018713
0x180018709  cmp     [rbp+57h+var_C0], r14d
0x18001870d  setnz   al
0x180018710  mov     [rsi+18h], al
0x180018713  xor     edx, edx
0x180018715  lea     rcx, [rbp+57h+hkey]
0x180018719  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18001871e  xor     edx, edx
0x180018720  lea     rcx, [rbp+57h+hkey]
0x180018724  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180018729  lea     rax, [rbp+57h+hkey]
0x18001872d  mov     [rsp+110h+phkResult], rax; phkResult
0x180018732  mov     r9d, edi; samDesired
0x180018735  xor     r8d, r8d; ulOptions
0x180018738  lea     rdx, aSource; "Source"
0x18001873f  mov     rcx, [rbp+57h+hKey]; hKey
0x180018743  call    cs:__imp_RegOpenKeyExW
0x180018749  test    eax, eax
0x18001874b  jnz     short loc_180018792
0x18001874d  mov     [rbp+57h+var_C0], r14d
0x180018751  mov     [rbp+57h+var_B0], ebx
0x180018754  lea     rax, [rbp+57h+var_B0]
0x180018758  mov     [rsp+110h+pcbData], rax; pcbData
0x18001875d  lea     rax, [rbp+57h+var_C0]
0x180018761  mov     [rsp+110h+pvData], rax; pvData
0x180018766  mov     [rsp+110h+phkResult], r14; pdwType
0x18001876b  mov     r9d, 10h; dwFlags
0x180018771  lea     r8, Value; "Enabled"
0x180018778  xor     edx, edx; lpSubKey
0x18001877a  mov     rcx, [rbp+57h+hkey]; hkey
0x18001877e  call    cs:__imp_RegGetValueW
0x180018784  test    eax, eax
0x180018786  jnz     short loc_180018792
0x180018788  cmp     [rbp+57h+var_C0], r14d
0x18001878c  setnz   al
0x18001878f  mov     [rsi+19h], al
0x180018792  lea     rcx, [rbp+57h+hkey]
0x180018796  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001879b  lea     rcx, [rbp+57h+hKey]
0x18001879f  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800187a4  cmp     [rsi+18h], r14b
0x1800187a8  jz      loc_1800188E6
0x1800187ae  lea     rax, WPP_GLOBAL_Control
0x1800187b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800187bc  cmp     rcx, rax
0x1800187bf  jz      short loc_1800187CE
0x1800187c1  test    byte ptr [rcx+1Ch], 1
0x1800187c5  jz      short loc_1800187CE
0x1800187c7  cmp     [rcx+19h], bl
0x1800187ca  mov     dl, 1
0x1800187cc  jnb     short loc_1800187D1
0x1800187ce  mov     dl, r14b; int
0x1800187d1  lea     rax, WPP_RECORDER_INITIALIZED
0x1800187d8  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1800187df  setnz   r8b; int
0x1800187e3  test    dl, dl
0x1800187e5  jnz     short loc_1800187EC
0x1800187e7  test    r8b, r8b
0x1800187ea  jz      short loc_18001881D
0x1800187ec  mov     qword ptr [rsp+110h+var_D0], rsi; char
0x1800187f1  lea     rax, WPP_21dc346b64563456f091e03a23b35635_Traceguids
0x1800187f8  mov     [rsp+110h+MessageGuid], rax; MessageGuid
0x1800187fd  mov     word ptr [rsp+110h+pcbData], 0Ah; __int16
0x180018804  mov     dword ptr [rsp+110h+pvData], 1; int
0x18001880c  mov     byte ptr [rsp+110h+phkResult], bl; char
0x180018810  mov     r9, [rcx+28h]; int
0x180018814  mov     rcx, [rcx+10h]; int
0x180018818  call    WPP_RECORDER_AND_TRACE_SF_q
0x18001881d  mov     eax, 110Bh
0x180018822  mov     word ptr [rbp+57h+var_C0], ax
0x180018826  lea     rdx, [rbp+57h+var_C0]
0x18001882a  lea     rcx, [rbp+57h+var_A0]
0x18001882e  call    ??$make_shared@VBluetoothProfileConflictWatcher@Internal@Audio@Bluetooth@Microsoft@@AEAG@std@@YA?AV?$shared_ptr@VBluetoothProfileConflictWatcher@Internal@Audio@Bluetooth@Microsoft@@@0@AEAG@Z; std::make_shared<Microsoft::Bluetooth::Audio::Internal::BluetoothProfileConflictWatcher,ushort &>(ushort &)
0x180018833  mov     rcx, [rax]
0x180018836  mov     rdx, [rax+8]
0x18001883a  mov     [rax], r14
0x18001883d  mov     [rax+8], r14
0x180018841  mov     [rsi+0B8h], rcx
0x180018848  mov     rcx, [rsi+0C0h]; this
0x18001884f  mov     [rsi+0C0h], rdx
0x180018856  test    rcx, rcx
0x180018859  jz      short loc_180018860
0x18001885b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180018860  mov     rcx, [rbp+57h+var_98]; this
0x180018864  test    rcx, rcx
0x180018867  jz      short loc_18001886E
0x180018869  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001886e  mov     rdi, [rsi+0B8h]
0x180018875  mov     rax, [rdi]
0x180018878  mov     rbx, [rax]
0x18001887b  lea     rdx, [rsi+8]
0x18001887f  lea     rcx, [rbp+57h+var_A0]
0x180018883  call    ??$?0V?$AsyncRequestWithUniqueResultAutoCancel@V?$vector@EV?$allocator@E@std@@@std@@J@Foundation@Bluetooth@Microsoft@@$0A@@?$weak_ptr@V?$AsyncRequestWithUniqueResultAutoCancel@V?$vector@EV?$allocator@E@std@@@std@@J@Foundation@Bluetooth@Microsoft@@@std@@QEAA@AEBV?$shared_ptr@V?$AsyncRequestWithUniqueResultAutoCancel@V?$vector@EV?$allocator@E@std@@@std@@J@Foundation@Bluetooth@Microsoft@@@1@@Z; std::weak_ptr<Microsoft::Bluetooth::Foundation::AsyncRequestWithUniqueResultAutoCancel<std::vector<uchar>,long>>::weak_ptr<Microsoft::Bluetooth::Foundation::AsyncRequestWithUniqueResultAutoCancel<std::vector<uchar>,long>>(std::shared_ptr<Microsoft::Bluetooth::Foundation::AsyncRequestWithUniqueResultAutoCancel<std::vector<uchar>,long>> const &)
0x180018888  nop
0x180018889  mov     rax, [rbp+57h+var_A0]
0x18001888d  mov     rcx, [rbp+57h+var_98]
0x180018891  mov     [rbp+57h+var_A0], r14
0x180018895  mov     [rbp+57h+var_98], r14
0x180018899  lea     rdx, off_180060C38
0x1800188a0  mov     [rbp+57h+var_70], rdx
0x1800188a4  mov     [rbp+57h+var_68], rax
0x1800188a8  mov     [rbp+57h+var_60], rcx
0x1800188ac  xorps   xmm0, xmm0
0x1800188af  movdqu  [rbp+57h+var_90], xmm0
0x1800188b4  lea     rax, [rbp+57h+var_70]
0x1800188b8  mov     [rbp+57h+var_38], rax
0x1800188bc  movzx   edx, word ptr [rbp+57h+var_C0]
0x1800188c0  lea     rcx, [rbp+57h+hKey]
0x1800188c4  call    ?BuildConflictingDeviceFilterExpression@A2dpRadioComponentImpl@Details@Service@A2dp@Profiles@Bluetooth@Microsoft@@CA?AV?$unique_ptr@V?$vector@U_DEVPROP_FILTER_EXPRESSION@@V?$allocator@U_DEVPROP_FILTER_EXPRESSION@@@std@@@std@@U?$default_delete@V?$vector@U_DEVPROP_FILTER_EXPRESSION@@V?$allocator@U_DEVPROP_FILTER_EXPRESSION@@@std@@@std@@@2@@std@@G@Z; Microsoft::Bluetooth::Profiles::A2dp::Service::Details::A2dpRadioComponentImpl::BuildConflictingDeviceFilterExpression(ushort)
0x1800188c9  lea     r8, [rbp+57h+var_70]
0x1800188cd  mov     rdx, rax
0x1800188d0  mov     rcx, rdi
0x1800188d3  mov     rax, rbx
0x1800188d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800188db  nop
0x1800188dc  lea     rcx, [rbp+57h+var_70]
0x1800188e0  call    ?_Tidy@?$_Func_class@XW4DeviceChangeEventType@AvrcpTransportEnumerator@Avrcp@Profiles@Bluetooth@Microsoft@@PEBGAEBV?$shared_ptr@VAvrcpTransport@Avrcp@Profiles@Bluetooth@Microsoft@@@std@@@std@@IEAAXXZ; std::_Func_class<void,Microsoft::Bluetooth::Profiles::Avrcp::AvrcpTransportEnumerator::DeviceChangeEventType,ushort const *,std::shared_ptr<Microsoft::Bluetooth::Profiles::Avrcp::AvrcpTransport> const &>::_Tidy(void)
0x1800188e5  nop
0x1800188e6  cmp     [rsi+19h], r14b
0x1800188ea  jz      loc_180018976
0x1800188f0  mov     rdi, [rsi+0B0h]
0x1800188f7  mov     rax, [rdi]
0x1800188fa  mov     rbx, [rax+8]
0x1800188fe  lea     rdx, aAudioSource; "Audio Source"
0x180018905  lea     rcx, [rbp+57h+var_90]
0x180018909  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001890e  nop
0x18001890f  mov     r8d, 103h
0x180018915  lea     r9, [rbp+57h+var_90]
0x180018919  lea     rdx, [rbp+57h+var_70]
0x18001891d  mov     rcx, rdi
0x180018920  mov     rax, rbx
0x180018923  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018928  nop
0x180018929  lea     rcx, [rsi+68h]
0x18001892d  mov     rdx, rax
0x180018930  call    ??4Token@Foundation@Bluetooth@Microsoft@@QEAAAEAV0123@$$QEAV0123@@Z; Microsoft::Bluetooth::Foundation::Token::operator=(Microsoft::Bluetooth::Foundation::Token &&)
0x180018935  nop
0x180018936  lea     rcx, [rbp+57h+var_70]; this
0x18001893a  call    ??1Token@Foundation@Bluetooth@Microsoft@@UEAA@XZ; Microsoft::Bluetooth::Foundation::Token::~Token(void)
0x18001893f  nop
0x180018940  lea     rcx, [rbp+57h+var_90]
0x180018944  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180018949  lea     rdx, AudioSinkServiceClass_UUID
0x180018950  lea     rcx, [rbp+57h+var_A0]
0x180018954  call    ?MakeShared@A2dpDeviceEnumerator@Service@A2dp@Profiles@Bluetooth@Microsoft@@SA?AV?$shared_ptr@VA2dpDeviceEnumerator@Service@A2dp@Profiles@Bluetooth@Microsoft@@@std@@AEBU_GUID@@@Z; Microsoft::Bluetooth::Profiles::A2dp::Service::A2dpDeviceEnumerator::MakeShared(_GUID const &)
0x180018959  lea     rcx, [rsi+0C8h]
0x180018960  mov     rdx, rax
0x180018963  call    ??4?$shared_ptr@VAsyncDeviceInterfaceWatcher@Foundation@Bluetooth@Microsoft@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Microsoft::Bluetooth::Foundation::AsyncDeviceInterfaceWatcher>::operator=(std::shared_ptr<Microsoft::Bluetooth::Foundation::AsyncDeviceInterfaceWatcher> &&)
0x180018968  mov     rcx, [rbp+57h+var_98]; this
0x18001896c  test    rcx, rcx
0x18001896f  jz      short loc_180018976
0x180018971  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180018976  mov     rcx, [rbp+57h+var_20]
0x18001897a  xor     rcx, rsp; StackCookie
0x18001897d  call    __security_check_cookie
0x180018982  lea     r11, [rsp+110h+var_10]
0x18001898a  mov     rbx, [r11+28h]
0x18001898e  mov     rsi, [r11+30h]
0x180018992  mov     rsp, r11
0x180018995  pop     r14
0x180018997  pop     rdi
0x180018998  pop     rbp
0x180018999  retn
```
