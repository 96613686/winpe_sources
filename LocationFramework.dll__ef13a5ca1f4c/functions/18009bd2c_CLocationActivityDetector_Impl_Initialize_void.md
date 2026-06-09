# CLocationActivityDetector_Impl::Initialize(void)

- ea: `0x18009bd2c`
- end: `0x18009bfd3`
- name: `?Initialize@CLocationActivityDetector_Impl@@QEAAJXZ`
- size: `679`
- prototype: `__int64 __fastcall(CLocationActivityDetector_Impl *__hidden this)`
- caller_count: `3`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18009b974`
- `0x1800e99dc`
- `0x1800e9a9c`

## callees

- `0x180012310`
- `0x18009bd2c`
- `0x18009c310`
- `0x1800a98c0`
- `0x1800e94b0`
- `0x18015e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009bd72`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009bf07`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009bf43`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009bfaa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009bd72`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009bf07`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009bf43`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009bfaa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009bd5a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009bd5a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18009bdca`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18009bdca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18009bdb1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18009bdb1`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18009bddf`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18009bddf`

## string_xrefs

- `0x18009bf55`: `BlockOnCompletionAndGetResults(pGetSensorOperation.Get(), &_pActivitySensor)`
- `0x18009be5c`: `onecoreuap\drivers\mobilepc\location\product\common\locationhelpers\locationactivitydetector.cpp`
- `0x18009bf68`: `onecoreuap\drivers\mobilepc\location\product\common\locationhelpers\locationactivitydetector.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CLocationActivityDetector_Impl::Initialize(CLocationActivityDetector_Impl *this)
{
  _QWORD *v1; // r14
  struct _RTL_CRITICAL_SECTION *v2; // rsi
  int ActivationFactory; // ebx
  __int64 v5; // rcx
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, __int64 *); // rbx
  int v8; // eax
  __int64 v9; // rcx
  __int64 v10; // rdi
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rcx
  wil::details *v14; // [rsp+28h] [rbp-48h]
  __int64 v15; // [rsp+38h] [rbp-38h] BYREF
  __int64 v16; // [rsp+40h] [rbp-30h] BYREF
  HSTRING hstringHeader[4]; // [rsp+48h] [rbp-28h] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+88h] [rbp+18h]

  v1 = (_QWORD *)((char *)this + 16);
  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 32);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  if ( *v1 )
  {
    if ( v2 )
      LeaveCriticalSection(v2);
    return 1;
  }
  v15 = 0;
  v16 = 0;
  memset(hstringHeader, 0, sizeof(hstringHeader));
  if ( WindowsCreateStringReference(
         L"Windows.Devices.Sensors.ActivitySensor",
         0x26u,
         (HSTRING_HEADER *)&hstringHeader[1],
         hstringHeader) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  ActivationFactory = RoGetActivationFactory(hstringHeader[0], &GUID_a71e0e9d_ee8b_45d1_b25b_08cc0df92ab6, &v15);
  if ( ActivationFactory < 0 )
  {
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v16);
    v5 = v15;
    if ( v15 )
    {
      v15 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    }
LABEL_30:
    if ( v2 )
      LeaveCriticalSection(v2);
    return (unsigned int)ActivationFactory;
  }
  v6 = v15;
  v7 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v15 + 48LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v16);
  v8 = v7(v6, &v16);
  ActivationFactory = v8;
  if ( v8 < 0 )
  {
    LODWORD(v14) = v8;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x3B,
      (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\common\\locationhelpers\\locationactivitydetector.cpp",
      "CLocationActivityDetector_Impl::Initialize",
      "pActivityStatic->GetDefaultAsync(&pGetSensorOperation)",
      v14,
      (int)v2);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v16);
    v9 = v15;
    if ( v15 )
    {
      v15 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    }
    goto LABEL_30;
  }
  v10 = v16;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v1);
  ActivationFactory = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Sensors::ActivitySensor *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Sensors::ActivitySensor *>>(v10);
  if ( ActivationFactory < 0
    || (ActivationFactory = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v10 + 64LL))(v10, v1),
        ActivationFactory < 0) )
  {
    LODWORD(v14) = ActivationFactory;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x3D,
      (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\common\\locationhelpers\\locationactivitydetector.cpp",
      "CLocationActivityDetector_Impl::Initialize",
      "BlockOnCompletionAndGetResults(pGetSensorOperation.Get(), &_pActivitySensor)",
      v14,
      (int)v2);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v16);
    v13 = v15;
    if ( v15 )
    {
      v15 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    }
    goto LABEL_30;
  }
  if ( *v1 )
  {
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v16);
    v12 = v15;
    if ( v15 )
    {
      v15 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    }
    if ( v2 )
      LeaveCriticalSection(v2);
    return 0;
  }
  else
  {
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v16);
    v11 = v15;
    if ( v15 )
    {
      v15 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    }
    if ( v2 )
      LeaveCriticalSection(v2);
    return 2147500035LL;
  }
}

```

## disassembly

```asm
0x18009bd2c  mov     [rsp-18h+arg_8], rbx
0x18009bd31  mov     [rsp-18h+arg_10], rsi
0x18009bd36  push    rbp
0x18009bd37  push    rdi
0x18009bd38  push    r14
0x18009bd3a  mov     rbp, rsp
0x18009bd3d  sub     rsp, 70h
0x18009bd41  mov     rax, cs:__security_cookie
0x18009bd48  xor     rax, rsp
0x18009bd4b  mov     [rbp+var_8], rax
0x18009bd4f  lea     r14, [rcx+10h]
0x18009bd53  lea     rsi, [rcx+20h]
0x18009bd57  mov     rcx, rsi; lpCriticalSection
0x18009bd5a  call    cs:__imp_EnterCriticalSection
0x18009bd60  mov     [rbp+var_40], rsi
0x18009bd64  cmp     qword ptr [r14], 0
0x18009bd68  jz      short loc_18009BD82
0x18009bd6a  test    rsi, rsi
0x18009bd6d  jz      short loc_18009BD78
0x18009bd6f  mov     rcx, rsi; lpCriticalSection
0x18009bd72  call    cs:__imp_LeaveCriticalSection
0x18009bd78  mov     eax, 1
0x18009bd7d  jmp     loc_18009BFB2
0x18009bd82  mov     [rbp+var_38], 0
0x18009bd8a  mov     [rbp+var_30], 0
0x18009bd92  xorps   xmm0, xmm0
0x18009bd95  movups  xmmword ptr [rbp+hstringHeader], xmm0
0x18009bd99  movups  xmmword ptr [rbp+hstringHeader+10h], xmm0
0x18009bd9d  lea     r9, [rbp+hstringHeader]; string
0x18009bda1  lea     r8, [rbp+hstringHeader+8]; hstringHeader
0x18009bda5  mov     edx, 26h ; '&'; length
0x18009bdaa  lea     rcx, ?RuntimeClass_Windows_Devices_Sensors_ActivitySensor@@3QBGB; "Windows.Devices.Sensors.ActivitySensor"
0x18009bdb1  call    cs:__imp_WindowsCreateStringReference
0x18009bdb7  test    eax, eax
0x18009bdb9  jns     short loc_18009BDD0
0x18009bdbb  xor     r9d, r9d; lpArguments
0x18009bdbe  xor     r8d, r8d; nNumberOfArguments
0x18009bdc1  lea     edx, [r9+1]; dwExceptionFlags
0x18009bdc5  mov     ecx, 0C000000Dh; dwExceptionCode
0x18009bdca  call    cs:__imp_RaiseException
0x18009bdd0  lea     r8, [rbp+var_38]
0x18009bdd4  lea     rdx, _GUID_a71e0e9d_ee8b_45d1_b25b_08cc0df92ab6
0x18009bddb  mov     rcx, qword ptr [rbp+hstringHeader]
0x18009bddf  call    cs:__imp_RoGetActivationFactory
0x18009bde5  mov     ebx, eax
0x18009bde7  test    eax, eax
0x18009bde9  jns     short loc_18009BE18
0x18009bdeb  lea     rcx, [rbp+var_30]
0x18009bdef  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18009bdf4  nop
0x18009bdf5  mov     rcx, [rbp+var_38]
0x18009bdf9  test    rcx, rcx
0x18009bdfc  jz      short loc_18009BE13
0x18009bdfe  mov     [rbp+var_38], 0
0x18009be06  mov     rax, [rcx]
0x18009be09  mov     rax, [rax+10h]
0x18009be0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009be12  nop
0x18009be13  jmp     loc_18009BFA2
0x18009be18  mov     rdi, [rbp+var_38]
0x18009be1c  mov     rax, [rdi]
0x18009be1f  mov     rbx, [rax+30h]
0x18009be23  lea     rcx, [rbp+var_30]
0x18009be27  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18009be2c  lea     rdx, [rbp+var_30]
0x18009be30  mov     rcx, rdi
0x18009be33  mov     rax, rbx
0x18009be36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009be3b  mov     ebx, eax
0x18009be3d  test    eax, eax
0x18009be3f  jns     short loc_18009BE9B
0x18009be41  mov     rcx, [rbp+18h]; this
0x18009be45  mov     dword ptr [rsp+70h+var_48], eax; wil::details *
0x18009be49  lea     rax, aPactivitystati; "pActivityStatic->GetDefaultAsync(&pGetS"...
0x18009be50  mov     [rsp+70h+var_50], rax; char *
0x18009be55  lea     r9, aClocationactiv_5; "CLocationActivityDetector_Impl::Initial"...
0x18009be5c  lea     r8, aOnecoreuapDriv_85; "onecoreuap\\drivers\\mobilepc\\location"...
0x18009be63  mov     edx, 3Bh ; ';'; void *
0x18009be68  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18009be6d  nop
0x18009be6e  lea     rcx, [rbp+var_30]
0x18009be72  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18009be77  nop
0x18009be78  mov     rcx, [rbp+var_38]
0x18009be7c  test    rcx, rcx
0x18009be7f  jz      short loc_18009BE96
0x18009be81  mov     [rbp+var_38], 0
0x18009be89  mov     rax, [rcx]
0x18009be8c  mov     rax, [rax+10h]
0x18009be90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009be95  nop
0x18009be96  jmp     loc_18009BFA2
0x18009be9b  mov     rdi, [rbp+var_30]
0x18009be9f  mov     rcx, r14
0x18009bea2  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18009bea7  mov     rcx, rdi
0x18009beaa  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVActivitySensor@Sensors@Devices@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVActivitySensor@Sensors@Devices@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVActivitySensor@Sensors@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Sensors::ActivitySensor *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Sensors::ActivitySensor *>>(Windows::Foundation::IAsyncOperation<Windows::Devices::Sensors::ActivitySensor *> *,tagCOWAIT_FLAGS,void *)
0x18009beaf  mov     ebx, eax
0x18009beb1  test    eax, eax
0x18009beb3  js      loc_18009BF4D
0x18009beb9  mov     rax, [rdi]
0x18009bebc  mov     rdx, r14
0x18009bebf  mov     rcx, rdi
0x18009bec2  mov     rax, [rax+40h]
0x18009bec6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009becb  mov     ebx, eax
0x18009becd  test    eax, eax
0x18009becf  js      short loc_18009BF4D
0x18009bed1  lea     rcx, [rbp+var_30]
0x18009bed5  cmp     qword ptr [r14], 0
0x18009bed9  jnz     short loc_18009BF17
0x18009bedb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18009bee0  nop
0x18009bee1  mov     rcx, [rbp+var_38]
0x18009bee5  test    rcx, rcx
0x18009bee8  jz      short loc_18009BEFF
0x18009beea  mov     [rbp+var_38], 0
0x18009bef2  mov     rax, [rcx]
0x18009bef5  mov     rax, [rax+10h]
0x18009bef9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009befe  nop
0x18009beff  test    rsi, rsi
0x18009bf02  jz      short loc_18009BF0D
0x18009bf04  mov     rcx, rsi; lpCriticalSection
0x18009bf07  call    cs:__imp_LeaveCriticalSection
0x18009bf0d  mov     eax, 80004003h
0x18009bf12  jmp     loc_18009BFB2
0x18009bf17  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18009bf1c  nop
0x18009bf1d  mov     rcx, [rbp+var_38]
0x18009bf21  test    rcx, rcx
0x18009bf24  jz      short loc_18009BF3B
0x18009bf26  mov     [rbp+var_38], 0
0x18009bf2e  mov     rax, [rcx]
0x18009bf31  mov     rax, [rax+10h]
0x18009bf35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009bf3a  nop
0x18009bf3b  test    rsi, rsi
0x18009bf3e  jz      short loc_18009BF49
0x18009bf40  mov     rcx, rsi; lpCriticalSection
0x18009bf43  call    cs:__imp_LeaveCriticalSection
0x18009bf49  xor     eax, eax
0x18009bf4b  jmp     short loc_18009BFB2
0x18009bf4d  mov     rcx, [rbp+18h]; this
0x18009bf51  mov     dword ptr [rsp+70h+var_48], ebx; wil::details *
0x18009bf55  lea     rax, aBlockoncomplet; "BlockOnCompletionAndGetResults(pGetSens"...
0x18009bf5c  mov     [rsp+70h+var_50], rax; char *
0x18009bf61  lea     r9, aClocationactiv_5; "CLocationActivityDetector_Impl::Initial"...
0x18009bf68  lea     r8, aOnecoreuapDriv_85; "onecoreuap\\drivers\\mobilepc\\location"...
0x18009bf6f  mov     edx, 3Dh ; '='; void *
0x18009bf74  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18009bf79  nop
0x18009bf7a  lea     rcx, [rbp+var_30]
0x18009bf7e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18009bf83  nop
0x18009bf84  mov     rcx, [rbp+var_38]
0x18009bf88  test    rcx, rcx
0x18009bf8b  jz      short loc_18009BFA2
0x18009bf8d  mov     [rbp+var_38], 0
0x18009bf95  mov     rax, [rcx]
0x18009bf98  mov     rax, [rax+10h]
0x18009bf9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009bfa1  nop
0x18009bfa2  test    rsi, rsi
0x18009bfa5  jz      short loc_18009BFB0
0x18009bfa7  mov     rcx, rsi; lpCriticalSection
0x18009bfaa  call    cs:__imp_LeaveCriticalSection
0x18009bfb0  mov     eax, ebx
0x18009bfb2  mov     rcx, [rbp+var_8]
0x18009bfb6  xor     rcx, rsp; StackCookie
0x18009bfb9  call    __security_check_cookie
0x18009bfbe  lea     r11, [rsp+70h+var_s0]
0x18009bfc3  mov     rbx, [r11+28h]
0x18009bfc7  mov     rsi, [r11+30h]
0x18009bfcb  mov     rsp, r11
0x18009bfce  pop     r14
0x18009bfd0  pop     rdi
0x18009bfd1  pop     rbp
0x18009bfd2  retn
```
