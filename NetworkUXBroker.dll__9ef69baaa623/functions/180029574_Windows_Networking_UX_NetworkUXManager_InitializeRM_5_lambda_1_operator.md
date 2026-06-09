# _Windows::Networking::UX::NetworkUXManager::_InitializeRM_::_5_::_lambda_1_::operator()

- ea: `0x180029574`
- end: `0x180029769`
- name: `_Windows::Networking::UX::NetworkUXManager::_InitializeRM_::_5_::_lambda_1_::operator()`
- size: `501`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180032f50`

## callees

- `0x18000955c`
- `0x18000e768`
- `0x180023f20`
- `0x180028fac`
- `0x180029574`
- `0x18002d5f0`
- `0x18003338c`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800295bb`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800295bb`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x180029652`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x180029652`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Networking::UX::NetworkUXManager::_InitializeRM_::_5_::_lambda_1_::operator()(_QWORD *a1)
{
  int AgileReference; // eax
  unsigned int v3; // ebx
  __int64 v4; // rdx
  __int64 *v5; // rax
  __int64 *v6; // rbx
  LPVOID v7; // rsi
  __int64 v8; // rbx
  __int64 v9; // rcx
  int ppv; // [rsp+20h] [rbp-30h]
  int v12; // [rsp+30h] [rbp-20h] BYREF
  int v13; // [rsp+34h] [rbp-1Ch] BYREF
  LPVOID v14; // [rsp+38h] [rbp-18h] BYREF
  __int64 v15; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  int v17; // [rsp+78h] [rbp+28h] BYREF
  unsigned int v18; // [rsp+80h] [rbp+30h] BYREF
  __int64 *v19; // [rsp+88h] [rbp+38h] BYREF

  v14 = 0;
  v17 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v14);
  AgileReference = CoCreateInstance(&CLSID_RadioManagementAPI, 0, 4u, &GUID_db3afbfb_08e6_46c6_aa70_bf9a34c30ab7, &v14);
  v3 = AgileReference;
  if ( AgileReference >= 0 )
  {
    AgileReference = (*(__int64 (__fastcall **)(LPVOID, int *))(*(_QWORD *)v14 + 24LL))(v14, &v17);
    v3 = AgileReference;
    if ( AgileReference >= 0 )
    {
      if ( v17 )
      {
        *(_BYTE *)(*a1 + 320LL) = 1;
        v19 = (__int64 *)(*a1 + 304LL);
        v5 = Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::AgileRef>::operator Microsoft::WRL::AgileRef *(&v19);
        v6 = v5;
        v7 = v14;
        if ( v14 )
        {
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v5);
          AgileReference = RoGetAgileReference(0, &GUID_db3afbfb_08e6_46c6_aa70_bf9a34c30ab7, v7, v6);
          v3 = AgileReference;
          if ( AgileReference < 0 )
          {
            v4 = 794;
            goto LABEL_5;
          }
        }
        else
        {
          v15 = 0;
          v19 = (__int64 *)*v5;
          *v5 = 0;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v19);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v15);
        }
        v8 = *a1;
        Microsoft::WRL::ComPtr<Windows::Networking::UX::RadioManagerNotifySink>::InternalRelease(*a1 + 312LL);
        AgileReference = Microsoft::WRL::Details::MakeAndInitialize<Windows::Networking::UX::RadioManagerNotifySink,Windows::Networking::UX::RadioManagerNotifySink,Windows::Networking::UX::NetworkUXManager * const,Microsoft::WRL::ComPtr<IUIRadioManager> &>(
                           (__int64 *)(v8 + 312),
                           a1,
                           (__int64)&v14);
        v3 = AgileReference;
        if ( AgileReference < 0 )
        {
          v4 = 796;
          goto LABEL_5;
        }
        v18 = 0;
        v12 = 0;
        v13 = 0;
        AgileReference = (*(__int64 (__fastcall **)(LPVOID, int *, int *, unsigned int *))(*(_QWORD *)v14 + 40LL))(
                           v14,
                           &v12,
                           &v13,
                           &v18);
        v3 = AgileReference;
        if ( AgileReference < 0 )
        {
          v4 = 800;
          goto LABEL_5;
        }
        LODWORD(v19) = 0;
        AgileReference = Windows::Networking::UX::NetworkUXManager::_GetAirplaneModeStatusChangeReasonFromRmUiReason(
                           v9,
                           v18,
                           &v19);
        v3 = AgileReference;
        if ( AgileReference < 0 )
        {
          v4 = 803;
          goto LABEL_5;
        }
        *(_DWORD *)(*a1 + 324LL) = (_DWORD)v19;
        *(_BYTE *)(*a1 + 328LL) = v12 == 0;
        *(_BYTE *)(*a1 + 329LL) = v13 != 0;
      }
      v3 = 0;
      goto LABEL_19;
    }
    v4 = 790;
  }
  else
  {
    v4 = 789;
  }
LABEL_5:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v4,
    (unsigned int)"onecoreuap\\net\\ux\\uxmanager\\lib\\networkuxmanager.cpp",
    (const char *)(unsigned int)AgileReference,
    ppv);
LABEL_19:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v14);
  return v3;
}

```

## disassembly

```asm
0x180029574  mov     [rsp-18h+arg_0], rbx
0x180029579  push    rbp
0x18002957a  push    rsi
0x18002957b  push    rdi
0x18002957c  mov     rbp, rsp
0x18002957f  sub     rsp, 50h
0x180029583  mov     rdi, rcx
0x180029586  mov     [rbp+var_18], 0
0x18002958e  mov     [rbp+arg_8], 0
0x180029595  lea     rcx, [rbp+var_18]
0x180029599  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002959e  lea     rax, [rbp+var_18]
0x1800295a2  mov     qword ptr [rsp+50h+ppv], rax; int
0x1800295a7  lea     r9, _GUID_db3afbfb_08e6_46c6_aa70_bf9a34c30ab7; riid
0x1800295ae  xor     edx, edx; pUnkOuter
0x1800295b0  lea     r8d, [rdx+4]; dwClsContext
0x1800295b4  lea     rcx, CLSID_RadioManagementAPI; rclsid
0x1800295bb  call    cs:__imp_CoCreateInstance
0x1800295c1  mov     ebx, eax
0x1800295c3  test    eax, eax
0x1800295c5  jns     short loc_1800295CE
0x1800295c7  mov     edx, 315h
0x1800295cc  jmp     short loc_1800295ED
0x1800295ce  mov     rcx, [rbp+var_18]
0x1800295d2  mov     rax, [rcx]
0x1800295d5  lea     rdx, [rbp+arg_8]
0x1800295d9  mov     rax, [rax+18h]
0x1800295dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800295e2  mov     ebx, eax
0x1800295e4  test    eax, eax
0x1800295e6  jns     short loc_180029605
0x1800295e8  mov     edx, 316h; void *
0x1800295ed  lea     r8, aOnecoreuapNetU_5; "onecoreuap\\net\\ux\\uxmanager\\lib\\ne"...
0x1800295f4  mov     r9d, eax; char *
0x1800295f7  mov     rcx, [rbp+18h]; this
0x1800295fb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029600  jmp     loc_180029751
0x180029605  cmp     [rbp+arg_8], 0
0x180029609  jz      loc_18002974F
0x18002960f  mov     rax, [rdi]
0x180029612  mov     byte ptr [rax+140h], 1
0x180029619  mov     rax, [rdi]
0x18002961c  add     rax, 130h
0x180029622  mov     [rbp+arg_18], rax
0x180029626  lea     rcx, [rbp+arg_18]
0x18002962a  call    ??B?$ComPtrRef@VAgileRef@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAAPEAVAgileRef@23@XZ; Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::AgileRef>::operator Microsoft::WRL::AgileRef *(void)
0x18002962f  mov     rbx, rax
0x180029632  mov     rsi, [rbp+var_18]
0x180029636  test    rsi, rsi
0x180029639  jz      short loc_180029665
0x18002963b  mov     rcx, rax
0x18002963e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180029643  mov     r9, rbx
0x180029646  mov     r8, rsi
0x180029649  lea     rdx, _GUID_db3afbfb_08e6_46c6_aa70_bf9a34c30ab7
0x180029650  xor     ecx, ecx
0x180029652  call    cs:__imp_RoGetAgileReference
0x180029658  mov     ebx, eax
0x18002965a  test    eax, eax
0x18002965c  jns     short loc_18002968D
0x18002965e  mov     edx, 31Ah
0x180029663  jmp     short loc_1800295ED
0x180029665  mov     [rbp+var_10], 0
0x18002966d  mov     rax, [rax]
0x180029670  mov     [rbp+arg_18], rax
0x180029674  mov     qword ptr [rbx], 0
0x18002967b  lea     rcx, [rbp+arg_18]
0x18002967f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180029684  lea     rcx, [rbp+var_10]
0x180029688  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002968d  mov     rbx, [rdi]
0x180029690  lea     rcx, [rbx+138h]
0x180029697  call    ?InternalRelease@?$ComPtr@VRadioManagerNotifySink@UX@Networking@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Networking::UX::RadioManagerNotifySink>::InternalRelease(void)
0x18002969c  lea     r8, [rbp+var_18]
0x1800296a0  mov     rdx, rdi
0x1800296a3  lea     rcx, [rbx+138h]
0x1800296aa  call    ??$MakeAndInitialize@VRadioManagerNotifySink@UX@Networking@Windows@@V1234@QEAVNetworkUXManager@234@AEAV?$ComPtr@UIUIRadioManager@@@WRL@Microsoft@@@Details@WRL@Microsoft@@YAJPEAPEAVRadioManagerNotifySink@UX@Networking@Windows@@$$QEBQEAVNetworkUXManager@456@AEAV?$ComPtr@UIUIRadioManager@@@12@@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::Networking::UX::RadioManagerNotifySink,Windows::Networking::UX::RadioManagerNotifySink,Windows::Networking::UX::NetworkUXManager * const,Microsoft::WRL::ComPtr<IUIRadioManager> &>(Windows::Networking::UX::RadioManagerNotifySink * *,Windows::Networking::UX::NetworkUXManager * const &&,Microsoft::WRL::ComPtr<IUIRadioManager> &)
0x1800296af  mov     ebx, eax
0x1800296b1  test    eax, eax
0x1800296b3  jns     short loc_1800296BF
0x1800296b5  mov     edx, 31Ch
0x1800296ba  jmp     loc_1800295ED
0x1800296bf  mov     [rbp+arg_10], 0
0x1800296c6  mov     [rbp+var_20], 0
0x1800296cd  mov     [rbp+var_1C], 0
0x1800296d4  mov     rcx, [rbp+var_18]
0x1800296d8  mov     rax, [rcx]
0x1800296db  lea     r9, [rbp+arg_10]
0x1800296df  lea     r8, [rbp+var_1C]
0x1800296e3  lea     rdx, [rbp+var_20]
0x1800296e7  mov     rax, [rax+28h]
0x1800296eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800296f0  mov     ebx, eax
0x1800296f2  test    eax, eax
0x1800296f4  jns     short loc_180029700
0x1800296f6  mov     edx, 320h
0x1800296fb  jmp     loc_1800295ED
0x180029700  mov     dword ptr [rbp+arg_18], 0
0x180029707  lea     r8, [rbp+arg_18]
0x18002970b  mov     edx, [rbp+arg_10]
0x18002970e  call    ?_GetAirplaneModeStatusChangeReasonFromRmUiReason@NetworkUXManager@UX@Networking@Windows@@AEAAJW4_RADIO_CHANGE_REASON@@PEAW4AirplaneModeStatusChangeReason@234@@Z; Windows::Networking::UX::NetworkUXManager::_GetAirplaneModeStatusChangeReasonFromRmUiReason(_RADIO_CHANGE_REASON,Windows::Networking::UX::AirplaneModeStatusChangeReason *)
0x180029713  mov     ebx, eax
0x180029715  test    eax, eax
0x180029717  jns     short loc_180029723
0x180029719  mov     edx, 323h
0x18002971e  jmp     loc_1800295ED
0x180029723  mov     rcx, [rdi]
0x180029726  mov     eax, dword ptr [rbp+arg_18]
0x180029729  mov     [rcx+144h], eax
0x18002972f  cmp     [rbp+var_20], 0
0x180029733  setz    cl
0x180029736  mov     rax, [rdi]
0x180029739  mov     [rax+148h], cl
0x18002973f  cmp     [rbp+var_1C], 0
0x180029743  setnz   cl
0x180029746  mov     rax, [rdi]
0x180029749  mov     [rax+149h], cl
0x18002974f  xor     ebx, ebx
0x180029751  lea     rcx, [rbp+var_18]
0x180029755  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002975a  mov     eax, ebx
0x18002975c  mov     rbx, [rsp+50h+arg_0]
0x180029761  add     rsp, 50h
0x180029765  pop     rdi
0x180029766  pop     rsi
0x180029767  pop     rbp
0x180029768  retn
```
