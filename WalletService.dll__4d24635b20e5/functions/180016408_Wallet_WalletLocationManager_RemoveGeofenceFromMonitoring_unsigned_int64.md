# Wallet::WalletLocationManager::RemoveGeofenceFromMonitoring(unsigned __int64)

- ea: `0x180016408`
- end: `0x18001661b`
- name: `?RemoveGeofenceFromMonitoring@WalletLocationManager@Wallet@@AEAAJ_K@Z`
- size: `531`
- prototype: `__int64 __fastcall(Wallet::WalletLocationManager *__hidden this, unsigned __int64)`
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180016260`
- `0x180016c90`

## callees

- `0x180003ae4`
- `0x1800043b8`
- `0x180008cc0`
- `0x180014510`
- `0x180014c98`
- `0x180016408`
- `0x180036cf4`
- `0x180043090`
- `0x180045010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18001654b`
- `msvcrt!_wcsicmp` at `0x18001654b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x18001652d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsStringHasEmbeddedNull` at `0x18001652d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001653e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001653e`

## string_xrefs

- `0x1800165b7`: `Wallet::WalletLocationManager::RemoveGeofenceFromMonitoring`

## pseudocode

```c
__int64 __fastcall Wallet::WalletLocationManager::RemoveGeofenceFromMonitoring(
        Wallet::WalletLocationManager *this,
        __int64 a2)
{
  __int64 v2; // rdi
  __int64 (__fastcall *v5)(__int64, __int64, __int64 *); // rbx
  __int64 *v6; // rax
  __int64 v7; // rdx
  int v8; // ebx
  int v9; // eax
  unsigned int i; // edi
  int v11; // eax
  const wchar_t *StringRawBuffer; // rax
  int v13; // eax
  __int64 v15; // [rsp+30h] [rbp-49h] BYREF
  HSTRING string; // [rsp+38h] [rbp-41h] BYREF
  __int64 v17; // [rsp+40h] [rbp-39h] BYREF
  unsigned int v18; // [rsp+48h] [rbp-31h] BYREF
  BOOL hasEmbedNull; // [rsp+4Ch] [rbp-2Dh] BYREF
  __int64 v20[2]; // [rsp+50h] [rbp-29h] BYREF
  wchar_t String2[40]; // [rsp+60h] [rbp-19h] BYREF

  v2 = *((_QWORD *)this + 10);
  v20[0] = 0;
  v5 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v2 + 64LL);
  v6 = ce::pointerTo<IWalletNotification>(v20);
  v8 = v5(v2, a2, v6);
  if ( v8 >= 0 )
  {
    v8 = 0;
    if ( (int)Wallet::Utils::GetTStringProperty<IWalletItem,enum __MIDL___MIDL_itf_wallettypes_0000_0000_0010>(
                v20[0],
                v7,
                String2) >= 0 )
    {
      v15 = 0;
      v18 = 0;
      v9 = Wallet::WalletLocationManager::CheckInitializeGeofenceMonitor(this, 0);
      if ( v9 < 0
        || (v9 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 11) + 56LL))(
                   *((_QWORD *)this + 11),
                   &v15),
            v9 < 0)
        || (v9 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v15 + 56LL))(v15, &v18), v9 < 0) )
      {
        v8 = v9;
      }
      else
      {
        for ( i = 0; i < v18; ++i )
        {
          v17 = 0;
          string = 0;
          v11 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v15 + 48LL))(v15, i, &v17);
          if ( v11 < 0
            || (v11 = (*(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v17 + 72LL))(v17, &string), v11 < 0) )
          {
            v8 = v11;
            goto LABEL_15;
          }
          hasEmbedNull = 0;
          WindowsStringHasEmbeddedNull(string, &hasEmbedNull);
          if ( hasEmbedNull )
          {
            v8 = -2147024809;
LABEL_15:
            Windows::Internal::String::~String(&string);
            ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(&v17);
            goto LABEL_20;
          }
          StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
          if ( !_wcsicmp(StringRawBuffer, String2) )
          {
            v13 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v15 + 96LL))(v15, i);
            if ( v13 < 0 )
              v8 = v13;
            goto LABEL_15;
          }
          Windows::Internal::String::~String(&string);
          ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(&v17);
        }
        wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy(
          3,
          "Wallet::WalletLocationManager::RemoveGeofenceFromMonitoring",
          349,
          this,
          "Geofence %S not found",
          String2);
        v8 = -2143682560;
      }
LABEL_20:
      ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(&v15);
    }
  }
  ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(v20);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180016408  mov     [rsp-8+arg_10], rbx
0x18001640d  mov     [rsp-8+arg_18], rsi
0x180016412  push    rbp
0x180016413  push    rdi
0x180016414  push    r14
0x180016416  lea     rbp, [rsp-47h]
0x18001641b  sub     rsp, 0C0h
0x180016422  mov     rax, cs:__security_cookie
0x180016429  xor     rax, rsp
0x18001642c  mov     [rbp+57h+var_20], rax
0x180016430  mov     rdi, [rcx+50h]
0x180016434  mov     r14, rcx
0x180016437  mov     [rbp+57h+var_80], 0
0x18001643f  lea     rcx, [rbp+57h+var_80]
0x180016443  mov     rsi, rdx
0x180016446  mov     rax, [rdi]
0x180016449  mov     rbx, [rax+40h]
0x18001644d  call    ??$pointerTo@UIWalletNotification@@@ce@@YAPEAPEAUIWalletNotification@@AEAV?$CComPtr@UIWalletNotification@@@ATL@@@Z; ce::pointerTo<IWalletNotification>(ATL::CComPtr<IWalletNotification> &)
0x180016452  mov     r8, rax
0x180016455  mov     rdx, rsi
0x180016458  mov     rax, rbx
0x18001645b  mov     rcx, rdi
0x18001645e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016463  mov     ebx, eax
0x180016465  test    eax, eax
0x180016467  js      loc_1800165EC
0x18001646d  mov     rcx, [rbp+57h+var_80]
0x180016471  lea     r8, [rbp+57h+String2]
0x180016475  xor     ebx, ebx
0x180016477  call    ??$GetTStringProperty@UIWalletItem@@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@@Utils@Wallet@@YAJPEAUIWalletItem@@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@PEAGI@Z; Wallet::Utils::GetTStringProperty<IWalletItem,__MIDL___MIDL_itf_wallettypes_0000_0000_0010>(IWalletItem *,__MIDL___MIDL_itf_wallettypes_0000_0000_0010,ushort *,uint)
0x18001647c  test    eax, eax
0x18001647e  js      loc_1800165EC
0x180016484  xor     edx, edx; struct Windows::Devices::Geolocation::Geofencing::IGeofenceMonitor *
0x180016486  mov     [rbp+57h+var_A0], rbx
0x18001648a  mov     rcx, r14; this
0x18001648d  mov     [rbp+57h+var_88], ebx
0x180016490  call    ?CheckInitializeGeofenceMonitor@WalletLocationManager@Wallet@@AEAAJPEAUIGeofenceMonitor@Geofencing@Geolocation@Devices@Windows@@@Z; Wallet::WalletLocationManager::CheckInitializeGeofenceMonitor(Windows::Devices::Geolocation::Geofencing::IGeofenceMonitor *)
0x180016495  test    eax, eax
0x180016497  js      loc_1800165E1
0x18001649d  mov     rcx, [r14+58h]
0x1800164a1  lea     rdx, [rbp+57h+var_A0]
0x1800164a5  mov     rax, [rcx]
0x1800164a8  mov     rax, [rax+38h]
0x1800164ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800164b1  test    eax, eax
0x1800164b3  js      loc_1800165E1
0x1800164b9  mov     rcx, [rbp+57h+var_A0]
0x1800164bd  lea     rdx, [rbp+57h+var_88]
0x1800164c1  mov     rax, [rcx]
0x1800164c4  mov     rax, [rax+38h]
0x1800164c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800164cd  test    eax, eax
0x1800164cf  js      loc_1800165E1
0x1800164d5  xor     edi, edi
0x1800164d7  cmp     edi, [rbp+57h+var_88]
0x1800164da  jnb     loc_1800165AB
0x1800164e0  mov     rcx, [rbp+57h+var_A0]
0x1800164e4  lea     r8, [rbp+57h+var_90]
0x1800164e8  mov     [rbp+57h+var_90], rbx
0x1800164ec  mov     edx, edi
0x1800164ee  mov     [rbp+57h+string], rbx
0x1800164f2  mov     rax, [rcx]
0x1800164f5  mov     rax, [rax+30h]
0x1800164f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800164fe  test    eax, eax
0x180016500  js      loc_1800165A7
0x180016506  mov     rcx, [rbp+57h+var_90]
0x18001650a  lea     rdx, [rbp+57h+string]
0x18001650e  mov     rax, [rcx]
0x180016511  mov     rax, [rax+48h]
0x180016515  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001651a  test    eax, eax
0x18001651c  js      loc_1800165A7
0x180016522  mov     rcx, [rbp+57h+string]; string
0x180016526  lea     rdx, [rbp+57h+hasEmbedNull]; hasEmbedNull
0x18001652a  mov     [rbp+57h+hasEmbedNull], ebx
0x18001652d  call    cs:__imp_WindowsStringHasEmbeddedNull
0x180016533  cmp     [rbp+57h+hasEmbedNull], ebx
0x180016536  jnz     short loc_18001659C
0x180016538  mov     rcx, [rbp+57h+string]; string
0x18001653c  xor     edx, edx; length
0x18001653e  call    cs:__imp_WindowsGetStringRawBuffer
0x180016544  mov     rcx, rax; String1
0x180016547  lea     rdx, [rbp+57h+String2]; String2
0x18001654b  call    cs:__imp__wcsicmp
0x180016551  test    eax, eax
0x180016553  jz      short loc_18001656E
0x180016555  lea     rcx, [rbp+57h+string]; this
0x180016559  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18001655e  lea     rcx, [rbp+57h+var_90]
0x180016562  call    ??1?$CComPtrBase@VWalletItemManager@Wallet@@@ATL@@QEAA@XZ; ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(void)
0x180016567  inc     edi
0x180016569  jmp     loc_1800164D7
0x18001656e  mov     rcx, [rbp+57h+var_A0]
0x180016572  mov     edx, edi
0x180016574  mov     rax, [rcx]
0x180016577  mov     rax, [rax+60h]
0x18001657b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016580  lea     rcx, [rbp+57h+string]; this
0x180016584  test    eax, eax
0x180016586  js      short loc_180016598
0x180016588  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18001658d  lea     rcx, [rbp+57h+var_90]
0x180016591  call    ??1?$CComPtrBase@VWalletItemManager@Wallet@@@ATL@@QEAA@XZ; ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(void)
0x180016596  jmp     short loc_1800165E3
0x180016598  mov     ebx, eax
0x18001659a  jmp     short loc_180016588
0x18001659c  mov     ebx, 80070057h
0x1800165a1  lea     rcx, [rbp+57h+string]
0x1800165a5  jmp     short loc_180016588
0x1800165a7  mov     ebx, eax
0x1800165a9  jmp     short loc_1800165A1
0x1800165ab  lea     rax, [rbp+57h+String2]
0x1800165af  mov     r9, r14
0x1800165b2  mov     [rsp+0D0h+var_A8], rax
0x1800165b7  lea     rdx, aWalletWalletlo; "Wallet::WalletLocationManager::RemoveGe"...
0x1800165be  lea     rax, aGeofenceSNotFo; "Geofence %S not found"
0x1800165c5  mov     r8d, 15Dh
0x1800165cb  mov     ecx, 3
0x1800165d0  mov     [rsp+0D0h+var_B0], rax
0x1800165d5  call    ?destroy@?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@UEAAXXZ; wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::destroy(void)
0x1800165da  mov     ebx, 803A0000h
0x1800165df  jmp     short loc_1800165E3
0x1800165e1  mov     ebx, eax
0x1800165e3  lea     rcx, [rbp+57h+var_A0]
0x1800165e7  call    ??1?$CComPtrBase@VWalletItemManager@Wallet@@@ATL@@QEAA@XZ; ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(void)
0x1800165ec  lea     rcx, [rbp+57h+var_80]
0x1800165f0  call    ??1?$CComPtrBase@VWalletItemManager@Wallet@@@ATL@@QEAA@XZ; ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(void)
0x1800165f5  mov     eax, ebx
0x1800165f7  mov     rcx, [rbp+57h+var_20]
0x1800165fb  xor     rcx, rsp; StackCookie
0x1800165fe  call    __security_check_cookie
0x180016603  lea     r11, [rsp+0D0h+var_10]
0x18001660b  mov     rbx, [r11+30h]
0x18001660f  mov     rsi, [r11+38h]
0x180016613  mov     rsp, r11
0x180016616  pop     r14
0x180016618  pop     rdi
0x180016619  pop     rbp
0x18001661a  retn
```
