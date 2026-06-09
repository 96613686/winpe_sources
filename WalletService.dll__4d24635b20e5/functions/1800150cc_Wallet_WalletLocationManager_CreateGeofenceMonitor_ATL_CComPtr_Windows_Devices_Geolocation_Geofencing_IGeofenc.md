# Wallet::WalletLocationManager::CreateGeofenceMonitor(ATL::CComPtr<Windows::Devices::Geolocation::Geofencing::IGeofenceMonitor> &)

- ea: `0x1800150cc`
- end: `0x1800151b7`
- name: `?CreateGeofenceMonitor@WalletLocationManager@Wallet@@CAJAEAV?$CComPtr@UIGeofenceMonitor@Geofencing@Geolocation@Devices@Windows@@@ATL@@@Z`
- size: `235`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180014c98`

## callees

- `0x180003ae4`
- `0x1800150cc`
- `0x180043090`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180015117`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180015117`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800150fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800150fe`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180015140`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180015140`

## pseudocode

```c
__int64 __fastcall Wallet::WalletLocationManager::CreateGeofenceMonitor(__int64 a1)
{
  int ActivationFactory; // ebx
  int v3; // eax
  __int64 v5; // [rsp+20h] [rbp-48h] BYREF
  __int64 (__fastcall ***v6)(_QWORD, GUID *, __int64 *); // [rsp+28h] [rbp-40h] BYREF
  HSTRING string; // [rsp+30h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+38h] [rbp-30h] BYREF

  if ( WindowsCreateStringReference(
         L"Windows.Devices.Geolocation.Geofencing.GeofenceMonitor",
         0x36u,
         &hstringHeader,
         &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v6 = 0;
  v5 = 0;
  ActivationFactory = RoGetActivationFactory(string, &GUID_00000035_0000_0000_c000_000000000046, &v6);
  if ( ActivationFactory >= 0 )
  {
    ActivationFactory = (**v6)(v6, &GUID_2dd32fcf_7e75_4899_ace3_2bd0a65cce06, &v5);
    if ( ActivationFactory >= 0 )
    {
      v3 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v5 + 48LL))(v5, a1);
      ActivationFactory = 0;
      if ( v3 < 0 )
        ActivationFactory = v3;
    }
  }
  ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(&v5);
  ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>((__int64 *)&v6);
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x1800150cc  mov     [rsp+arg_8], rbx
0x1800150d1  push    rdi
0x1800150d2  sub     rsp, 60h
0x1800150d6  mov     rax, cs:__security_cookie
0x1800150dd  xor     rax, rsp
0x1800150e0  mov     [rsp+68h+var_18], rax
0x1800150e5  mov     rdi, rcx
0x1800150e8  lea     r9, [rsp+68h+string]; string
0x1800150ed  lea     rcx, ?RuntimeClass_Windows_Devices_Geolocation_Geofencing_GeofenceMonitor@@3QBGB; "Windows.Devices.Geolocation.Geofencing."...
0x1800150f4  mov     edx, 36h ; '6'; length
0x1800150f9  lea     r8, [rsp+68h+hstringHeader]; hstringHeader
0x1800150fe  call    cs:__imp_WindowsCreateStringReference
0x180015104  test    eax, eax
0x180015106  jns     short loc_18001511D
0x180015108  xor     r9d, r9d; lpArguments
0x18001510b  xor     r8d, r8d; nNumberOfArguments
0x18001510e  mov     ecx, 0C000000Dh; dwExceptionCode
0x180015113  lea     edx, [r9+1]; dwExceptionFlags
0x180015117  call    cs:__imp_RaiseException
0x18001511d  mov     rcx, [rsp+68h+string]
0x180015122  lea     r8, [rsp+68h+var_40]
0x180015127  lea     rdx, _GUID_00000035_0000_0000_c000_000000000046
0x18001512e  mov     [rsp+68h+var_40], 0
0x180015137  mov     [rsp+68h+var_48], 0
0x180015140  call    cs:__imp_RoGetActivationFactory
0x180015146  mov     ebx, eax
0x180015148  test    eax, eax
0x18001514a  js      short loc_180015189
0x18001514c  mov     rcx, [rsp+68h+var_40]
0x180015151  lea     r8, [rsp+68h+var_48]
0x180015156  lea     rdx, _GUID_2dd32fcf_7e75_4899_ace3_2bd0a65cce06
0x18001515d  mov     rax, [rcx]
0x180015160  mov     rax, [rax]
0x180015163  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015168  mov     ebx, eax
0x18001516a  test    eax, eax
0x18001516c  js      short loc_180015189
0x18001516e  mov     rcx, [rsp+68h+var_48]
0x180015173  mov     rdx, rdi
0x180015176  mov     rax, [rcx]
0x180015179  mov     rax, [rax+30h]
0x18001517d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015182  xor     ebx, ebx
0x180015184  test    eax, eax
0x180015186  cmovs   ebx, eax
0x180015189  lea     rcx, [rsp+68h+var_48]
0x18001518e  call    ??1?$CComPtrBase@VWalletItemManager@Wallet@@@ATL@@QEAA@XZ; ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(void)
0x180015193  lea     rcx, [rsp+68h+var_40]
0x180015198  call    ??1?$CComPtrBase@VWalletItemManager@Wallet@@@ATL@@QEAA@XZ; ATL::CComPtrBase<Wallet::WalletItemManager>::~CComPtrBase<Wallet::WalletItemManager>(void)
0x18001519d  mov     eax, ebx
0x18001519f  mov     rcx, [rsp+68h+var_18]
0x1800151a4  xor     rcx, rsp; StackCookie
0x1800151a7  call    __security_check_cookie
0x1800151ac  mov     rbx, [rsp+68h+arg_8]
0x1800151b1  add     rsp, 60h
0x1800151b5  pop     rdi
0x1800151b6  retn
```
