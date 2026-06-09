# MigrateEnabledRegkeyToPolicy(void)

- ea: `0x1800607fc`
- end: `0x180060b4e`
- name: `?MigrateEnabledRegkeyToPolicy@@YAXXZ`
- size: `850`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180062ba8`

## callees

- `0x180002520`
- `0x18000e4ec`
- `0x1800138a8`
- `0x180028aa0`
- `0x1800532e8`
- `0x180058328`
- `0x1800607fc`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180060922`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180060922`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180060857`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180060857`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180060a95`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180060a95`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800608e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800608e4`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180060a36`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180060a36`

## string_xrefs

- `0x180060849`: `SYSTEM\CurrentControlSet\Services\IsoEnvBroker`
- `0x1800608dd`: `Windows.Internal.CapabilityAccess.Management.CapabilityConsentManager`
- `0x180060ab6`: `onecoreuap\windows\core\isoenvbroker\lib\common\isoenvbrokersvc.cpp`
- `0x180060acb`: `onecoreuap\windows\core\isoenvbroker\lib\common\isoenvbrokersvc.cpp`
- `0x180060ae8`: `onecoreuap\windows\core\isoenvbroker\lib\common\isoenvbrokersvc.cpp`
- `0x180060afd`: `onecoreuap\windows\core\isoenvbroker\lib\common\isoenvbrokersvc.cpp`
- `0x180060b12`: `onecoreuap\windows\core\isoenvbroker\lib\common\isoenvbrokersvc.cpp`
- `0x180060b27`: `onecoreuap\windows\core\isoenvbroker\lib\common\isoenvbrokersvc.cpp`
- `0x180060b3c`: `onecoreuap\windows\core\isoenvbroker\lib\common\isoenvbrokersvc.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
void MigrateEnabledRegkeyToPolicy(void)
{
  int v0; // eax
  __int64 v1; // rdx
  __int64 v2; // rdx
  __int64 v3; // rcx
  int v4; // esi
  HRESULT v5; // eax
  int v6; // edx
  unsigned int v7; // r8d
  int ActivationFactory; // eax
  unsigned int v9; // r8d
  wil::details::in1diag3 *v10; // rcx
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, PVOID, __int64 *); // rbx
  HSTRING_HEADER *v13; // rax
  int v14; // eax
  int v15; // eax
  unsigned int v16; // r8d
  __int64 v17; // rbx
  __int64 (__fastcall *v18)(__int64, PVOID, __int64 *); // rdi
  __int64 v19; // rcx
  HSTRING_HEADER *v20; // rax
  int v21; // eax
  int v22; // eax
  int v23; // eax
  __int64 v24; // rcx
  __int64 v25; // rcx
  int phkResult; // [rsp+20h] [rbp-29h]
  int phkResulta; // [rsp+20h] [rbp-29h]
  __int64 v28; // [rsp+30h] [rbp-19h] BYREF
  __int64 v29; // [rsp+38h] [rbp-11h] BYREF
  int v30; // [rsp+40h] [rbp-9h] BYREF
  int v31; // [rsp+44h] [rbp-5h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-1h] BYREF
  int Data; // [rsp+50h] [rbp+7h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+58h] [rbp+Fh] BYREF
  HSTRING string; // [rsp+70h] [rbp+27h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID59214605>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID59214605>::GetImpl'::`2'::impl) )
  {
    hKey = 0;
    v0 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Services\\IsoEnvBroker", 0, 0xF003Fu, &hKey);
    if ( v0 > 0 )
      v0 = (unsigned __int16)v0 | 0x80070000;
    if ( v0 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1D0,
        (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\common\\isoenvbrokersvc.cpp",
        (const char *)(unsigned int)v0,
        phkResult);
    v30 = 0;
    if ( wil::reg::get_value_nothrow<unsigned long,0>((__int64)retaddr, v1, L"MigratedEnableRegkeyToPolicy", &v30) >= 0
      && v30 )
    {
      goto LABEL_23;
    }
    v31 = 0;
    if ( wil::reg::get_value_nothrow<unsigned long,0>(v3, v2, L"Enabled", &v31) < 0 )
      goto LABEL_23;
    v4 = -(v31 != 0);
    v29 = 0;
    string = 0;
    v5 = WindowsCreateStringReference(
           L"Windows.Internal.CapabilityAccess.Management.CapabilityConsentManager",
           0x45u,
           &hstringHeader,
           &string);
    if ( v5 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v5, v6, v7);
    }
    else
    {
      ActivationFactory = RoGetActivationFactory(string, &GUID_ef1a89c8_29b1_4ab0_94a7_851b33527a2e, &v29);
      v10 = retaddr;
      if ( ActivationFactory >= 0 )
      {
        v28 = 0;
        v11 = v29;
        v12 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v29 + 48LL);
        v13 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                &hstringHeader,
                (const WCHAR **)&c_szPolicyMcpAccess,
                v9);
        v14 = v12(v11, v13[1].Reserved.Reserved1, &v28);
        if ( v14 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0x1F4,
            (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\common\\isoenvbrokersvc.cpp",
            (const char *)(unsigned int)v14,
            phkResult);
        v15 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v28 + 112LL))(v28, (unsigned int)(v4 + 2));
        if ( v15 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0x1F5,
            (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\common\\isoenvbrokersvc.cpp",
            (const char *)(unsigned int)v15,
            phkResult);
        v17 = v29;
        v18 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v29 + 48LL);
        v19 = v28;
        if ( v28 )
        {
          v28 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
        }
        v20 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                &hstringHeader,
                (const WCHAR **)&c_szPolicyCuaAccess,
                v16);
        v21 = v18(v17, v20[1].Reserved.Reserved1, &v28);
        if ( v21 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0x1FA,
            (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\common\\isoenvbrokersvc.cpp",
            (const char *)(unsigned int)v21,
            phkResult);
        v22 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v28 + 112LL))(v28, (unsigned int)(v4 + 2));
        if ( v22 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0x1FB,
            (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\common\\isoenvbrokersvc.cpp",
            (const char *)(unsigned int)v22,
            phkResult);
        Data = 1;
        v23 = RegSetKeyValueW(hKey, 0, L"MigratedEnableRegkeyToPolicy", 4u, &Data, 4u);
        if ( v23 > 0 )
          v23 = (unsigned __int16)v23 | 0x80070000;
        if ( v23 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0x201,
            (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\common\\isoenvbrokersvc.cpp",
            (const char *)(unsigned int)v23,
            phkResulta);
        v24 = v28;
        if ( v28 )
        {
          v28 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
        }
        v25 = v29;
        if ( v29 )
        {
          v29 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
        }
LABEL_23:
        if ( hKey )
          RegCloseKey(hKey);
        return;
      }
    }
    wil::details::in1diag3::_Throw_Hr(
      v10,
      (void *)0x1ED,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\common\\isoenvbrokersvc.cpp",
      (const char *)(unsigned int)ActivationFactory,
      phkResult);
  }
}

```

## disassembly

```asm
0x1800607fc  push    rbp
0x1800607fe  push    rbx
0x1800607ff  push    rsi
0x180060800  push    rdi
0x180060801  lea     rbp, [rsp-3Fh]
0x180060806  sub     rsp, 88h
0x18006080d  mov     rax, cs:__security_cookie
0x180060814  xor     rax, rsp
0x180060817  mov     [rbp+57h+var_28], rax
0x18006081b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID59214605@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID59214605@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID59214605> `wil::Feature<__WilFeatureTraits_Feature_ID59214605>::GetImpl(void)'::`2'::impl
0x180060822  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ID59214605@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID59214605>::__private_IsEnabled(void)
0x180060827  test    al, al
0x180060829  jz      loc_180060A9B
0x18006082f  mov     [rbp+57h+hKey], 0
0x180060837  lea     rax, [rbp+57h+hKey]
0x18006083b  mov     [rsp+0A0h+phkResult], rax; int
0x180060840  mov     r9d, 0F003Fh; samDesired
0x180060846  xor     r8d, r8d; ulOptions
0x180060849  lea     rdx, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Services\\Is"...
0x180060850  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180060857  call    cs:__imp_RegOpenKeyExW
0x18006085d  test    eax, eax
0x18006085f  jle     short loc_180060869
0x180060861  movzx   eax, ax
0x180060864  or      eax, 80070000h
0x180060869  mov     rcx, [rbp+5Fh]; this
0x18006086d  test    eax, eax
0x18006086f  js      loc_180060AC8
0x180060875  mov     [rbp+57h+var_60], 0
0x18006087c  lea     r9, [rbp+57h+var_60]
0x180060880  lea     r8, aMigratedenable; "MigratedEnableRegkeyToPolicy"
0x180060887  call    ??$get_value_nothrow@K$0A@@reg@wil@@YAJPEAUHKEY__@@PEB_W1PEAK@Z; wil::reg::get_value_nothrow<ulong,0>(HKEY__ *,wchar_t const *,wchar_t const *,ulong *)
0x18006088c  test    eax, eax
0x18006088e  js      short loc_18006089A
0x180060890  cmp     [rbp+57h+var_60], 0
0x180060894  jnz     loc_180060A8C
0x18006089a  mov     [rbp+57h+var_5C], 0
0x1800608a1  lea     r9, [rbp+57h+var_5C]
0x1800608a5  lea     r8, aEnabled; "Enabled"
0x1800608ac  call    ??$get_value_nothrow@K$0A@@reg@wil@@YAJPEAUHKEY__@@PEB_W1PEAK@Z; wil::reg::get_value_nothrow<ulong,0>(HKEY__ *,wchar_t const *,wchar_t const *,ulong *)
0x1800608b1  test    eax, eax
0x1800608b3  js      loc_180060A8C
0x1800608b9  mov     eax, [rbp+57h+var_5C]
0x1800608bc  neg     eax
0x1800608be  sbb     esi, esi
0x1800608c0  mov     [rbp+57h+var_68], 0
0x1800608c8  mov     [rbp+57h+string], 0
0x1800608d0  lea     r9, [rbp+57h+string]; string
0x1800608d4  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x1800608d8  mov     edx, 45h ; 'E'; length
0x1800608dd  lea     rcx, ?RuntimeClass_Windows_Internal_CapabilityAccess_Management_CapabilityConsentManager@@3QB_WB; "Windows.Internal.CapabilityAccess.Manag"...
0x1800608e4  call    cs:__imp_WindowsCreateStringReference
0x1800608ea  test    eax, eax
0x1800608ec  js      loc_180060ADD
0x1800608f2  mov     rbx, [rbp+57h+string]
0x1800608f6  mov     rcx, [rbp+57h+var_68]
0x1800608fa  test    rcx, rcx
0x1800608fd  jz      short loc_180060914
0x1800608ff  mov     [rbp+57h+var_68], 0
0x180060907  mov     rax, [rcx]
0x18006090a  mov     rax, [rax+10h]
0x18006090e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060913  nop
0x180060914  lea     r8, [rbp+57h+var_68]
0x180060918  lea     rdx, _GUID_ef1a89c8_29b1_4ab0_94a7_851b33527a2e
0x18006091f  mov     rcx, rbx
0x180060922  call    cs:__imp_RoGetActivationFactory
0x180060928  mov     rcx, [rbp+5Fh]
0x18006092c  test    eax, eax
0x18006092e  js      loc_180060AE5
0x180060934  mov     [rbp+57h+var_70], 0
0x18006093c  mov     rdi, [rbp+57h+var_68]
0x180060940  mov     rax, [rdi]
0x180060943  mov     rbx, [rax+30h]
0x180060947  lea     rdx, ?c_szPolicyMcpAccess@@3QEB_WEB; wchar_t const * const c_szPolicyMcpAccess
0x18006094e  lea     rcx, [rbp+57h+hstringHeader]
0x180060952  call    ??$?0PEB_W@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEB_WUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(wchar_t const * const &,Microsoft::WRL::Details::Dummy)
0x180060957  nop
0x180060958  lea     r8, [rbp+57h+var_70]
0x18006095c  mov     rdx, [rax+18h]
0x180060960  mov     rcx, rdi
0x180060963  mov     rax, rbx
0x180060966  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006096b  mov     rcx, [rbp+5Fh]; this
0x18006096f  test    eax, eax
0x180060971  js      loc_180060AFA
0x180060977  mov     rcx, [rbp+57h+var_70]
0x18006097b  mov     rax, [rcx]
0x18006097e  lea     edx, [rsi+2]
0x180060981  mov     rax, [rax+70h]
0x180060985  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006098a  mov     rcx, [rbp+5Fh]; this
0x18006098e  test    eax, eax
0x180060990  js      loc_180060B0F
0x180060996  mov     rbx, [rbp+57h+var_68]
0x18006099a  mov     rax, [rbx]
0x18006099d  mov     rdi, [rax+30h]
0x1800609a1  mov     rcx, [rbp+57h+var_70]
0x1800609a5  test    rcx, rcx
0x1800609a8  jz      short loc_1800609BF
0x1800609aa  mov     [rbp+57h+var_70], 0
0x1800609b2  mov     rax, [rcx]
0x1800609b5  mov     rax, [rax+10h]
0x1800609b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800609be  nop
0x1800609bf  lea     rdx, ?c_szPolicyCuaAccess@@3QEB_WEB; wchar_t const * const c_szPolicyCuaAccess
0x1800609c6  lea     rcx, [rbp+57h+hstringHeader]
0x1800609ca  call    ??$?0PEB_W@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEB_WUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(wchar_t const * const &,Microsoft::WRL::Details::Dummy)
0x1800609cf  nop
0x1800609d0  lea     r8, [rbp+57h+var_70]
0x1800609d4  mov     rdx, [rax+18h]
0x1800609d8  mov     rcx, rbx
0x1800609db  mov     rax, rdi
0x1800609de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800609e3  mov     rcx, [rbp+5Fh]; this
0x1800609e7  test    eax, eax
0x1800609e9  js      loc_180060B24
0x1800609ef  mov     rcx, [rbp+57h+var_70]
0x1800609f3  mov     rax, [rcx]
0x1800609f6  lea     edx, [rsi+2]
0x1800609f9  mov     rax, [rax+70h]
0x1800609fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060a02  mov     rcx, [rbp+5Fh]; this
0x180060a06  test    eax, eax
0x180060a08  js      loc_180060B39
0x180060a0e  mov     [rbp+57h+Data], 1
0x180060a15  mov     r9d, 4; dwType
0x180060a1b  mov     [rsp+0A0h+cbData], r9d; cbData
0x180060a20  lea     rax, [rbp+57h+Data]
0x180060a24  mov     [rsp+0A0h+phkResult], rax; int
0x180060a29  lea     r8, aMigratedenable; "MigratedEnableRegkeyToPolicy"
0x180060a30  xor     edx, edx; lpSubKey
0x180060a32  mov     rcx, [rbp+57h+hKey]; hKey
0x180060a36  call    cs:__imp_RegSetKeyValueW
0x180060a3c  test    eax, eax
0x180060a3e  jle     short loc_180060A48
0x180060a40  movzx   eax, ax
0x180060a43  or      eax, 80070000h
0x180060a48  mov     rcx, [rbp+5Fh]; this
0x180060a4c  test    eax, eax
0x180060a4e  js      short loc_180060AB3
0x180060a50  mov     rcx, [rbp+57h+var_70]
0x180060a54  test    rcx, rcx
0x180060a57  jz      short loc_180060A6E
0x180060a59  mov     [rbp+57h+var_70], 0
0x180060a61  mov     rax, [rcx]
0x180060a64  mov     rax, [rax+10h]
0x180060a68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060a6d  nop
0x180060a6e  mov     rcx, [rbp+57h+var_68]
0x180060a72  test    rcx, rcx
0x180060a75  jz      short loc_180060A8C
0x180060a77  mov     [rbp+57h+var_68], 0
0x180060a7f  mov     rax, [rcx]
0x180060a82  mov     rax, [rax+10h]
0x180060a86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060a8b  nop
0x180060a8c  mov     rcx, [rbp+57h+hKey]; hKey
0x180060a90  test    rcx, rcx
0x180060a93  jz      short loc_180060A9B
0x180060a95  call    cs:__imp_RegCloseKey
0x180060a9b  mov     rcx, [rbp+57h+var_28]
0x180060a9f  xor     rcx, rsp; StackCookie
0x180060aa2  call    __security_check_cookie
0x180060aa7  add     rsp, 88h
0x180060aae  pop     rdi
0x180060aaf  pop     rsi
0x180060ab0  pop     rbx
0x180060ab1  pop     rbp
0x180060ab2  retn
0x180060ab3  mov     r9d, eax; char *
0x180060ab6  lea     r8, aOnecoreuapWind_20; "onecoreuap\\windows\\core\\isoenvbroker"...
0x180060abd  mov     edx, 201h; void *
0x180060ac2  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180060ac8  mov     r9d, eax; char *
0x180060acb  lea     r8, aOnecoreuapWind_20; "onecoreuap\\windows\\core\\isoenvbroker"...
0x180060ad2  mov     edx, 1D0h; void *
0x180060ad7  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180060add  mov     ecx, eax; this
0x180060adf  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x180060ae4  nop
0x180060ae5  mov     r9d, eax; char *
0x180060ae8  lea     r8, aOnecoreuapWind_20; "onecoreuap\\windows\\core\\isoenvbroker"...
0x180060aef  mov     edx, 1EDh; void *
0x180060af4  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180060afa  mov     r9d, eax; char *
0x180060afd  lea     r8, aOnecoreuapWind_20; "onecoreuap\\windows\\core\\isoenvbroker"...
0x180060b04  mov     edx, 1F4h; void *
0x180060b09  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180060b0f  mov     r9d, eax; char *
0x180060b12  lea     r8, aOnecoreuapWind_20; "onecoreuap\\windows\\core\\isoenvbroker"...
0x180060b19  mov     edx, 1F5h; void *
0x180060b1e  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180060b24  mov     r9d, eax; char *
0x180060b27  lea     r8, aOnecoreuapWind_20; "onecoreuap\\windows\\core\\isoenvbroker"...
0x180060b2e  mov     edx, 1FAh; void *
0x180060b33  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180060b39  mov     r9d, eax; char *
0x180060b3c  lea     r8, aOnecoreuapWind_20; "onecoreuap\\windows\\core\\isoenvbroker"...
0x180060b43  mov     edx, 1FBh; void *
0x180060b48  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
