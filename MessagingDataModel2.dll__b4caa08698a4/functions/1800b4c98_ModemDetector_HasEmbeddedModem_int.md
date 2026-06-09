# ModemDetector::HasEmbeddedModem(int *)

- ea: `0x1800b4c98`
- end: `0x1800b4f6b`
- name: `?HasEmbeddedModem@ModemDetector@@SAJPEAH@Z`
- size: `723`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `3`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180063800`
- `0x180063e30`
- `0x1800b5290`

## callees

- `0x180030bd0`
- `0x18006b108`
- `0x1800b4890`
- `0x1800b4a7c`
- `0x1800b4c98`
- `0x1800b4f74`
- `0x1800c6940`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800b4cee`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800b4da3`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800b4cee`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800b4da3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b4d3a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b4ec4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b4f2e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b4d3a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b4ec4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b4f2e`

## pseudocode

```c
__int64 __fastcall ModemDetector::HasEmbeddedModem(int *a1)
{
  int ActivationFactory; // eax
  int v2; // ebx
  __int64 v3; // rcx
  void (*v4)(void); // rax
  __int64 v5; // rdi
  __int64 (__fastcall *v6)(__int64, HSTRING *); // rbx
  int v7; // eax
  int v8; // eax
  __int64 v9; // rcx
  void (*v10)(void); // rax
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, HSTRING, _QWORD); // rbx
  int v13; // eax
  int (__fastcall ***v14)(_QWORD, GUID *, __int64 *); // rdi
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v18; // rcx
  __int64 v19; // rcx
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-29h] BYREF
  __int64 v21; // [rsp+48h] [rbp-11h]
  int *v22; // [rsp+50h] [rbp-9h] BYREF
  __int64 v23; // [rsp+58h] [rbp-1h] BYREF
  HSTRING string; // [rsp+60h] [rbp+7h] BYREF
  __int64 v25; // [rsp+68h] [rbp+Fh] BYREF
  int (__fastcall ***v26)(_QWORD, GUID *, __int64 *); // [rsp+70h] [rbp+17h] BYREF
  __int64 v27; // [rsp+78h] [rbp+1Fh] BYREF

  v22 = a1;
  *a1 = 0;
  v23 = 0;
  v21 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Networking.NetworkOperators.MobileBroadbandModem",
    0x39u,
    0x38u);
  ActivationFactory = RoGetActivationFactory(v21, &GUID_f99ed637_d6f1_4a78_8cbc_6421a65063c8, &v23);
  v2 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    Log_HREvent_97(ActivationFactory);
    v3 = v23;
    if ( v23 )
    {
      v23 = 0;
      v4 = *(void (**)(void))(*(_QWORD *)v3 + 16LL);
LABEL_25:
      v4();
      return (unsigned int)v2;
    }
    return (unsigned int)v2;
  }
  v5 = v23;
  string = 0;
  v6 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v23 + 48LL);
  WindowsDeleteString(0);
  string = 0;
  v7 = v6(v5, &string);
  v2 = v7;
  if ( v7 < 0 )
  {
    Log_HREvent_97(v7);
    goto LABEL_23;
  }
  v25 = 0;
  v21 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Devices.Enumeration.DeviceInformation",
    0x2Eu,
    0x2Du);
  v8 = RoGetActivationFactory(v21, &GUID_c17f100e_3a46_4a78_8013_769dc9b97390, &v25);
  v2 = v8;
  if ( v8 < 0 )
  {
    Log_HREvent_97(v8);
    v9 = v25;
    if ( !v25 )
      goto LABEL_23;
    v25 = 0;
    v10 = *(void (**)(void))(*(_QWORD *)v9 + 16LL);
    goto LABEL_22;
  }
  v11 = v25;
  v26 = 0;
  v12 = *(__int64 (__fastcall **)(__int64, HSTRING, _QWORD))(*(_QWORD *)v25 + 80LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26);
  v13 = v12(v11, string, &v26);
  v2 = v13;
  if ( v13 < 0 )
  {
    Log_HREvent_97(v13);
LABEL_20:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26);
    v18 = v25;
    if ( !v25 )
      goto LABEL_23;
    v25 = 0;
    v10 = *(void (**)(void))(*(_QWORD *)v18 + 16LL);
LABEL_22:
    v10();
LABEL_23:
    WindowsDeleteString(string);
    v19 = v23;
    string = 0;
    if ( v23 )
    {
      v23 = 0;
      v4 = *(void (**)(void))(*(_QWORD *)v19 + 16LL);
      goto LABEL_25;
    }
    return (unsigned int)v2;
  }
  v14 = v26;
  v27 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27);
  v2 = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Enumeration::DeviceInformationCollection *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Enumeration::DeviceInformationCollection *>>(v14);
  if ( v2 < 0
    || (v2 = ((__int64 (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, __int64 *), __int64 *))(*v14)[8])(v14, &v27),
        v2 < 0)
    || (hstringHeader.Reserved.Reserved1 = &v23,
        *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = &v22,
        v2 = ForEach_Windows::Devices::Enumeration::DeviceInformation____lambda_57c69da3c1440205844995cc6899c30e____0(
               v27,
               &hstringHeader),
        v2 < 0) )
  {
    Log_HREvent_97(v2);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27);
    goto LABEL_20;
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v26);
  v15 = v25;
  if ( v25 )
  {
    v25 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  }
  WindowsDeleteString(string);
  v16 = v23;
  string = 0;
  if ( v23 )
  {
    v23 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  }
  return 0;
}

```

## disassembly

```asm
0x1800b4c98  push    rbp
0x1800b4c9a  push    rbx
0x1800b4c9b  push    rsi
0x1800b4c9c  push    rdi
0x1800b4c9d  lea     rbp, [rsp-3Fh]
0x1800b4ca2  sub     rsp, 98h
0x1800b4ca9  mov     rax, cs:__security_cookie
0x1800b4cb0  xor     rax, rsp
0x1800b4cb3  mov     [rbp+57h+var_30], rax
0x1800b4cb7  xor     esi, esi
0x1800b4cb9  mov     [rbp+57h+var_60], rcx
0x1800b4cbd  mov     [rcx], esi
0x1800b4cbf  lea     rdx, ?RuntimeClass_Windows_Networking_NetworkOperators_MobileBroadbandModem@@3QBGB; "Windows.Networking.NetworkOperators.Mob"...
0x1800b4cc6  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800b4cca  mov     [rbp+57h+var_58], rsi
0x1800b4cce  mov     [rbp+57h+var_68], rsi
0x1800b4cd2  lea     r9d, [rsi+38h]; unsigned int
0x1800b4cd6  lea     r8d, [rsi+39h]; unsigned int
0x1800b4cda  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800b4cdf  mov     rcx, [rbp+57h+var_68]
0x1800b4ce3  lea     r8, [rbp+57h+var_58]
0x1800b4ce7  lea     rdx, _GUID_f99ed637_d6f1_4a78_8cbc_6421a65063c8
0x1800b4cee  call    cs:__imp_RoGetActivationFactory
0x1800b4cf4  mov     ebx, eax
0x1800b4cf6  test    eax, eax
0x1800b4cf8  jns     short loc_1800B4D29
0x1800b4cfa  lea     r9d, [rsi+16h]
0x1800b4cfe  mov     ecx, eax; int
0x1800b4d00  lea     r8, aOnecoreuapBase_42; "onecoreuap\\base\\appmodel\\messagingom"...
0x1800b4d07  call    Log_HREvent_97
0x1800b4d0c  mov     rcx, [rbp+57h+var_58]
0x1800b4d10  test    rcx, rcx
0x1800b4d13  jz      loc_1800B4F51
0x1800b4d19  mov     [rbp+57h+var_58], rsi
0x1800b4d1d  mov     rdx, [rcx]
0x1800b4d20  mov     rax, [rdx+10h]
0x1800b4d24  jmp     loc_1800B4F4C
0x1800b4d29  mov     rdi, [rbp+57h+var_58]
0x1800b4d2d  xor     ecx, ecx; string
0x1800b4d2f  mov     [rbp+57h+string], rsi
0x1800b4d33  mov     rax, [rdi]
0x1800b4d36  mov     rbx, [rax+30h]
0x1800b4d3a  call    cs:__imp_WindowsDeleteString
0x1800b4d40  lea     rdx, [rbp+57h+string]
0x1800b4d44  mov     [rbp+57h+string], rsi
0x1800b4d48  mov     rcx, rdi
0x1800b4d4b  mov     rax, rbx
0x1800b4d4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4d53  mov     ebx, eax
0x1800b4d55  test    eax, eax
0x1800b4d57  jns     short loc_1800B4D72
0x1800b4d59  mov     r9d, 19h
0x1800b4d5f  lea     r8, aOnecoreuapBase_42; "onecoreuap\\base\\appmodel\\messagingom"...
0x1800b4d66  mov     ecx, eax; int
0x1800b4d68  call    Log_HREvent_97
0x1800b4d6d  jmp     loc_1800B4F2A
0x1800b4d72  mov     r9d, 2Dh ; '-'; unsigned int
0x1800b4d78  mov     [rbp+57h+var_48], rsi
0x1800b4d7c  lea     rdx, ?RuntimeClass_Windows_Devices_Enumeration_DeviceInformation@@3QBGB; "Windows.Devices.Enumeration.DeviceInfor"...
0x1800b4d83  mov     [rbp+57h+var_68], rsi
0x1800b4d87  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800b4d8b  lea     r8d, [r9+1]; unsigned int
0x1800b4d8f  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800b4d94  mov     rcx, [rbp+57h+var_68]
0x1800b4d98  lea     r8, [rbp+57h+var_48]
0x1800b4d9c  lea     rdx, _GUID_c17f100e_3a46_4a78_8013_769dc9b97390
0x1800b4da3  call    cs:__imp_RoGetActivationFactory
0x1800b4da9  mov     ebx, eax
0x1800b4dab  test    eax, eax
0x1800b4dad  jns     short loc_1800B4DE0
0x1800b4daf  mov     r9d, 1Eh
0x1800b4db5  lea     r8, aOnecoreuapBase_42; "onecoreuap\\base\\appmodel\\messagingom"...
0x1800b4dbc  mov     ecx, eax; int
0x1800b4dbe  call    Log_HREvent_97
0x1800b4dc3  mov     rcx, [rbp+57h+var_48]
0x1800b4dc7  test    rcx, rcx
0x1800b4dca  jz      loc_1800B4F2A
0x1800b4dd0  mov     [rbp+57h+var_48], rsi
0x1800b4dd4  mov     rdx, [rcx]
0x1800b4dd7  mov     rax, [rdx+10h]
0x1800b4ddb  jmp     loc_1800B4F25
0x1800b4de0  mov     rdi, [rbp+57h+var_48]
0x1800b4de4  lea     rcx, [rbp+57h+var_40]
0x1800b4de8  mov     [rbp+57h+var_40], rsi
0x1800b4dec  mov     rax, [rdi]
0x1800b4def  mov     rbx, [rax+50h]
0x1800b4df3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800b4df8  mov     rdx, [rbp+57h+string]
0x1800b4dfc  lea     r8, [rbp+57h+var_40]
0x1800b4e00  mov     rcx, rdi
0x1800b4e03  mov     rax, rbx
0x1800b4e06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4e0b  mov     ebx, eax
0x1800b4e0d  test    eax, eax
0x1800b4e0f  jns     short loc_1800B4E2A
0x1800b4e11  mov     r9d, 21h ; '!'
0x1800b4e17  lea     r8, aOnecoreuapBase_42; "onecoreuap\\base\\appmodel\\messagingom"...
0x1800b4e1e  mov     ecx, eax; int
0x1800b4e20  call    Log_HREvent_97
0x1800b4e25  jmp     loc_1800B4F08
0x1800b4e2a  mov     rdi, [rbp+57h+var_40]
0x1800b4e2e  lea     rcx, [rbp+57h+var_38]
0x1800b4e32  mov     [rbp+57h+var_38], rsi
0x1800b4e36  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800b4e3b  mov     rcx, rdi
0x1800b4e3e  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVDeviceInformationCollection@Enumeration@Devices@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVDeviceInformationCollection@Enumeration@Devices@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVDeviceInformationCollection@Enumeration@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Enumeration::DeviceInformationCollection *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Enumeration::DeviceInformationCollection *>>(Windows::Foundation::IAsyncOperation<Windows::Devices::Enumeration::DeviceInformationCollection *> *,tagCOWAIT_FLAGS,void *)
0x1800b4e43  mov     ebx, eax
0x1800b4e45  test    eax, eax
0x1800b4e47  js      loc_1800B4EEB
0x1800b4e4d  mov     rax, [rdi]
0x1800b4e50  lea     rdx, [rbp+57h+var_38]
0x1800b4e54  mov     rcx, rdi
0x1800b4e57  mov     rax, [rax+40h]
0x1800b4e5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4e60  mov     ebx, eax
0x1800b4e62  test    eax, eax
0x1800b4e64  js      loc_1800B4EEB
0x1800b4e6a  mov     rcx, [rbp+57h+var_38]
0x1800b4e6e  lea     rax, [rbp+57h+var_58]
0x1800b4e72  mov     qword ptr [rbp+57h+hstringHeader.Reserved], rax
0x1800b4e76  lea     rdx, [rbp+57h+hstringHeader]
0x1800b4e7a  lea     rax, [rbp+57h+var_60]
0x1800b4e7e  mov     qword ptr [rbp+57h+hstringHeader.Reserved+8], rax
0x1800b4e82  call    ForEach_Windows__Devices__Enumeration__DeviceInformation____lambda_57c69da3c1440205844995cc6899c30e____0
0x1800b4e87  mov     ebx, eax
0x1800b4e89  test    eax, eax
0x1800b4e8b  jns     short loc_1800B4E95
0x1800b4e8d  mov     r9d, 32h ; '2'
0x1800b4e93  jmp     short loc_1800B4EF1
0x1800b4e95  lea     rcx, [rbp+57h+var_38]
0x1800b4e99  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800b4e9e  lea     rcx, [rbp+57h+var_40]
0x1800b4ea2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800b4ea7  mov     rcx, [rbp+57h+var_48]
0x1800b4eab  test    rcx, rcx
0x1800b4eae  jz      short loc_1800B4EC0
0x1800b4eb0  mov     [rbp+57h+var_48], rsi
0x1800b4eb4  mov     rax, [rcx]
0x1800b4eb7  mov     rax, [rax+10h]
0x1800b4ebb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4ec0  mov     rcx, [rbp+57h+string]; string
0x1800b4ec4  call    cs:__imp_WindowsDeleteString
0x1800b4eca  mov     rcx, [rbp+57h+var_58]
0x1800b4ece  mov     [rbp+57h+string], rsi
0x1800b4ed2  test    rcx, rcx
0x1800b4ed5  jz      short loc_1800B4EE7
0x1800b4ed7  mov     [rbp+57h+var_58], rsi
0x1800b4edb  mov     rax, [rcx]
0x1800b4ede  mov     rax, [rax+10h]
0x1800b4ee2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4ee7  xor     eax, eax
0x1800b4ee9  jmp     short loc_1800B4F53
0x1800b4eeb  mov     r9d, 25h ; '%'
0x1800b4ef1  lea     r8, aOnecoreuapBase_42; "onecoreuap\\base\\appmodel\\messagingom"...
0x1800b4ef8  mov     ecx, ebx; int
0x1800b4efa  call    Log_HREvent_97
0x1800b4eff  lea     rcx, [rbp+57h+var_38]
0x1800b4f03  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800b4f08  lea     rcx, [rbp+57h+var_40]
0x1800b4f0c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800b4f11  mov     rcx, [rbp+57h+var_48]
0x1800b4f15  test    rcx, rcx
0x1800b4f18  jz      short loc_1800B4F2A
0x1800b4f1a  mov     [rbp+57h+var_48], rsi
0x1800b4f1e  mov     rax, [rcx]
0x1800b4f21  mov     rax, [rax+10h]
0x1800b4f25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4f2a  mov     rcx, [rbp+57h+string]; string
0x1800b4f2e  call    cs:__imp_WindowsDeleteString
0x1800b4f34  mov     rcx, [rbp+57h+var_58]
0x1800b4f38  mov     [rbp+57h+string], rsi
0x1800b4f3c  test    rcx, rcx
0x1800b4f3f  jz      short loc_1800B4F51
0x1800b4f41  mov     [rbp+57h+var_58], rsi
0x1800b4f45  mov     rax, [rcx]
0x1800b4f48  mov     rax, [rax+10h]
0x1800b4f4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4f51  mov     eax, ebx
0x1800b4f53  mov     rcx, [rbp+57h+var_30]
0x1800b4f57  xor     rcx, rsp; StackCookie
0x1800b4f5a  call    __security_check_cookie
0x1800b4f5f  add     rsp, 98h
0x1800b4f66  pop     rdi
0x1800b4f67  pop     rsi
0x1800b4f68  pop     rbx
0x1800b4f69  pop     rbp
0x1800b4f6a  retn
```
