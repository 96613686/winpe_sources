# AppReadiness::Groups::OnDemandSyncGroup::IsPackageFamilyFullyRegisteredByUser(Microsoft::WRL::Wrappers::HString &,Windows::Internal::StateRepository::PackageType,Windows::Internal::StateRepository::IPackageFamily *,Windows::Internal::StateRepository::IUser *,Microsoft::WRL::Wrappers::HString &)

- ea: `0x1800346b8`
- end: `0x180034a74`
- name: `?IsPackageFamilyFullyRegisteredByUser@OnDemandSyncGroup@Groups@AppReadiness@@AEAA_NAEAVHString@Wrappers@WRL@Microsoft@@W4PackageType@StateRepository@Internal@Windows@@PEAUIPackageFamily@9Internal@Windows@@PEAUIUser@9Internal@Windows@@0@Z`
- size: `956`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180029b1c`

## callees

- `0x180002958`
- `0x180027780`
- `0x1800346b8`
- `0x180038f14`
- `0x180039eec`
- `0x180049310`
- `0x180063840`
- `0x180079010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800347d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003486c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800347d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003486c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180034813`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180034827`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180034813`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180034827`

## string_xrefs

- `0x180034726`: `onecoreuap\shell\appreadiness\src\groups\ondemandsyncgroup.cpp`
- `0x18003477a`: `onecoreuap\shell\appreadiness\src\groups\ondemandsyncgroup.cpp`
- `0x1800347af`: `onecoreuap\shell\appreadiness\src\groups\ondemandsyncgroup.cpp`
- `0x1800347fd`: `onecoreuap\shell\appreadiness\src\groups\ondemandsyncgroup.cpp`
- `0x180034856`: `onecoreuap\shell\appreadiness\src\groups\ondemandsyncgroup.cpp`
- `0x1800348bb`: `onecoreuap\shell\appreadiness\src\groups\ondemandsyncgroup.cpp`
- `0x1800348fc`: `onecoreuap\shell\appreadiness\src\groups\ondemandsyncgroup.cpp`
- `0x18003493b`: `onecoreuap\shell\appreadiness\src\groups\ondemandsyncgroup.cpp`
- `0x180034986`: `onecoreuap\shell\appreadiness\src\groups\ondemandsyncgroup.cpp`
- `0x1800349d4`: `onecoreuap\shell\appreadiness\src\groups\ondemandsyncgroup.cpp`
- `0x180034a0e`: `onecoreuap\shell\appreadiness\src\groups\ondemandsyncgroup.cpp`
- `0x18003482f`: `failed to get user SID`
- `0x180034844`: `Cannot find a main or optional package with the user although a package in the same family is registered by the user. Either the package is removed before OnDemandSync is finished (race condition) or State Repository contains bad data (eg, PackageUser table has bundle for a user but not main or optional packages for the user). User SID: %ws, registered package full name: %ws`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
char __fastcall AppReadiness::Groups::OnDemandSyncGroup::IsPackageFamilyFullyRegisteredByUser(
        _QWORD *a1,
        HSTRING *a2,
        char a3,
        __int64 a4,
        __int64 a5,
        int a6)
{
  __int64 v9; // rdi
  __int64 v10; // rsi
  __int64 (__fastcall *v11)(__int64, HSTRING, __int64 *); // rbx
  int v12; // eax
  __int64 (__fastcall *v13)(__int64, __int64, __int64, __int64); // rbx
  int v14; // eax
  int v15; // eax
  __int64 (__fastcall *v16)(__int64, HSTRING *); // rbx
  int v17; // eax
  PCWSTR StringRawBuffer; // rbx
  PCWSTR v19; // rax
  int v21; // eax
  int v22; // eax
  int v23; // eax
  __int64 v24; // rdi
  __int64 (__fastcall *v25)(__int64, _QWORD, __int64 *); // rbx
  int v26; // eax
  __int64 v27; // rdi
  __int64 (__fastcall *v28)(__int64, __int64, __int64, __int64 *); // rbx
  int v29; // eax
  int v30; // eax
  int *v31; // [rsp+20h] [rbp-59h]
  int v32; // [rsp+40h] [rbp-39h] BYREF
  __int64 v33; // [rsp+48h] [rbp-31h] BYREF
  int v34[2]; // [rsp+50h] [rbp-29h] BYREF
  HSTRING string; // [rsp+58h] [rbp-21h] BYREF
  __int64 v36; // [rsp+60h] [rbp-19h] BYREF
  __int64 v37; // [rsp+68h] [rbp-11h] BYREF
  _QWORD v38[10]; // [rsp+70h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+4Fh]
  char v40; // [rsp+E0h] [rbp+67h] BYREF

  v33 = 0;
  v9 = a1[46];
  v10 = a5;
  if ( (a3 & 0x21) != 0 )
  {
    v11 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v9 + 176LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v33);
    v12 = v11(v9, *a2, &v33);
    if ( v12 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1C3,
        (unsigned int)"onecoreuap\\shell\\appreadiness\\src\\groups\\ondemandsyncgroup.cpp",
        (const char *)(unsigned int)v12,
        (int)v31);
  }
  else
  {
    *(_QWORD *)v34 = 0;
    v13 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64))(*(_QWORD *)v9 + 408LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v34);
    v31 = v34;
    v14 = v13(v9, v10, a4, 33);
    if ( v14 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1CD,
        (unsigned int)"onecoreuap\\shell\\appreadiness\\src\\groups\\ondemandsyncgroup.cpp",
        (const char *)(unsigned int)v14,
        (int)v34);
    a6 = 0;
    v15 = (*(__int64 (__fastcall **)(_QWORD, int *))(**(_QWORD **)v34 + 56LL))(*(_QWORD *)v34, &a6);
    if ( v15 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1D0,
        (unsigned int)"onecoreuap\\shell\\appreadiness\\src\\groups\\ondemandsyncgroup.cpp",
        (const char *)(unsigned int)v15,
        (int)v34);
    if ( !a6 )
    {
      string = 0;
      v16 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v10 + 64LL);
      WindowsDeleteString(0);
      string = 0;
      v17 = v16(v10, &string);
      if ( v17 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x1D4,
          (unsigned int)"onecoreuap\\shell\\appreadiness\\src\\groups\\ondemandsyncgroup.cpp",
          (const char *)(unsigned int)v17,
          (int)v34);
      StringRawBuffer = WindowsGetStringRawBuffer(*a2, 0);
      if ( string )
        v19 = WindowsGetStringRawBuffer(string, 0);
      else
        v19 = L"failed to get user SID";
      wil::details::in1diag3::Log_HrMsg(
        retaddr,
        (void *)0x1DA,
        (unsigned int)"onecoreuap\\shell\\appreadiness\\src\\groups\\ondemandsyncgroup.cpp",
        (const char *)0x8000FFFFLL,
        (int)"Cannot find a main or optional package with the user although a package in the same family is registered by"
             " the user. Either the package is removed before OnDemandSync is finished (race condition) or State Reposito"
             "ry contains bad data (eg, PackageUser table has bundle for a user but not main or optional packages for the"
             " user). User SID: %ws, registered package full name: %ws",
        (const char *)v19,
        StringRawBuffer);
      WindowsDeleteString(string);
      string = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v34);
      goto LABEL_15;
    }
    if ( a6 != 1 )
      MicrosoftTelemetryAssertTriggeredNoArgs(retaddr);
    v21 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64 *))(**(_QWORD **)v34 + 48LL))(*(_QWORD *)v34, 0, &v33);
    if ( v21 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1E3,
        (unsigned int)"onecoreuap\\shell\\appreadiness\\src\\groups\\ondemandsyncgroup.cpp",
        (const char *)(unsigned int)v21,
        (int)v34);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v34);
  }
  v40 = 0;
  v22 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v33 + 792LL))(v33, &v40);
  if ( v22 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1E7,
      (unsigned int)"onecoreuap\\shell\\appreadiness\\src\\groups\\ondemandsyncgroup.cpp",
      (const char *)(unsigned int)v22,
      (int)v31);
  if ( v40 )
  {
LABEL_15:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v33);
    return 0;
  }
  v38[0] = 0;
  v23 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v33 + 112LL))(v33, v38);
  if ( v23 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1EF,
      (unsigned int)"onecoreuap\\shell\\appreadiness\\src\\groups\\ondemandsyncgroup.cpp",
      (const char *)(unsigned int)v23,
      (int)v31);
  v37 = 0;
  v24 = a1[49];
  v25 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v24 + 88LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
  v26 = v25(v24, v38[0], &v37);
  if ( v26 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1F1,
      (unsigned int)"onecoreuap\\shell\\appreadiness\\src\\groups\\ondemandsyncgroup.cpp",
      (const char *)(unsigned int)v26,
      (int)v31);
  v36 = 0;
  v27 = a1[48];
  v28 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64 *))(*(_QWORD *)v27 + 80LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v36);
  v29 = v28(v27, v10, v37, &v36);
  if ( v29 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1F4,
      (unsigned int)"onecoreuap\\shell\\appreadiness\\src\\groups\\ondemandsyncgroup.cpp",
      (const char *)(unsigned int)v29,
      (int)v31);
  if ( v36 )
  {
    v32 = 0;
    v30 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v36 + 96LL))(v36, &v32);
    if ( v30 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1FD,
        (unsigned int)"onecoreuap\\shell\\appreadiness\\src\\groups\\ondemandsyncgroup.cpp",
        (const char *)(unsigned int)v30,
        (int)v31);
    if ( (v32 & 0x10000000) != 0 )
    {
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v36);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
      goto LABEL_15;
    }
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v36);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v33);
  return 1;
}

```

## disassembly

```asm
0x1800346b8  push    rbp
0x1800346ba  push    rbx
0x1800346bb  push    rsi
0x1800346bc  push    rdi
0x1800346bd  push    r12
0x1800346bf  push    r13
0x1800346c1  push    r14
0x1800346c3  push    r15
0x1800346c5  lea     rbp, [rsp-0Fh]
0x1800346ca  sub     rsp, 88h
0x1800346d1  mov     r12, r9
0x1800346d4  mov     r14, rdx
0x1800346d7  mov     r15, rcx
0x1800346da  xor     r13d, r13d
0x1800346dd  mov     [rbp+47h+var_78], r13
0x1800346e1  mov     rdi, [rcx+170h]
0x1800346e8  mov     rsi, [rbp+47h+arg_20]
0x1800346ec  test    r8b, 21h
0x1800346f0  jz      short loc_180034738
0x1800346f2  mov     rax, [rdi]
0x1800346f5  mov     rbx, [rax+0B0h]
0x1800346fc  lea     rcx, [rbp+47h+var_78]
0x180034700  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180034705  lea     r8, [rbp+47h+var_78]
0x180034709  mov     rdx, [r14]
0x18003470c  mov     rcx, rdi
0x18003470f  mov     rax, rbx
0x180034712  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034717  mov     rcx, [rbp+4Fh]; this
0x18003471b  test    eax, eax
0x18003471d  jns     loc_1800348D6
0x180034723  mov     r9d, eax; char *
0x180034726  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\appreadiness\\src\\g"...
0x18003472d  mov     edx, 1C3h; void *
0x180034732  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180034738  mov     qword ptr [rbp+47h+var_70], r13
0x18003473c  mov     rax, [rdi]
0x18003473f  mov     rbx, [rax+198h]
0x180034746  lea     rcx, [rbp+47h+var_70]
0x18003474a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003474f  lea     rax, [rbp+47h+var_70]
0x180034753  mov     qword ptr [rsp+0C0h+var_A0], rax; int
0x180034758  mov     r9d, 21h ; '!'
0x18003475e  mov     r8, r12
0x180034761  mov     rdx, rsi
0x180034764  mov     rcx, rdi
0x180034767  mov     rax, rbx
0x18003476a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003476f  mov     rcx, [rbp+4Fh]; this
0x180034773  test    eax, eax
0x180034775  jns     short loc_18003478C
0x180034777  mov     r9d, eax; char *
0x18003477a  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\appreadiness\\src\\g"...
0x180034781  mov     edx, 1CDh; void *
0x180034786  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18003478c  mov     [rbp+47h+arg_28], r13d
0x180034790  mov     rcx, qword ptr [rbp+47h+var_70]
0x180034794  mov     rax, [rcx]
0x180034797  lea     rdx, [rbp+47h+arg_28]
0x18003479b  mov     rax, [rax+38h]
0x18003479f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800347a4  mov     rcx, [rbp+4Fh]; this
0x1800347a8  test    eax, eax
0x1800347aa  jns     short loc_1800347C1
0x1800347ac  mov     r9d, eax; char *
0x1800347af  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\appreadiness\\src\\g"...
0x1800347b6  mov     edx, 1D0h; void *
0x1800347bb  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800347c1  mov     eax, [rbp+47h+arg_28]
0x1800347c4  test    eax, eax
0x1800347c6  jnz     loc_180034890
0x1800347cc  mov     [rbp+47h+string], r13
0x1800347d0  mov     rax, [rsi]
0x1800347d3  mov     rbx, [rax+40h]
0x1800347d7  xor     ecx, ecx; string
0x1800347d9  call    cs:__imp_WindowsDeleteString
0x1800347df  mov     [rbp+47h+string], r13
0x1800347e3  lea     rdx, [rbp+47h+string]
0x1800347e7  mov     rcx, rsi
0x1800347ea  mov     rax, rbx
0x1800347ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800347f2  mov     rcx, [rbp+4Fh]; this
0x1800347f6  test    eax, eax
0x1800347f8  jns     short loc_18003480E
0x1800347fa  mov     r9d, eax; char *
0x1800347fd  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\appreadiness\\src\\g"...
0x180034804  mov     edx, 1D4h; void *
0x180034809  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003480e  xor     edx, edx; length
0x180034810  mov     rcx, [r14]; string
0x180034813  call    cs:__imp_WindowsGetStringRawBuffer
0x180034819  mov     rbx, rax
0x18003481c  mov     rcx, [rbp+47h+string]; string
0x180034820  test    rcx, rcx
0x180034823  jz      short loc_18003482F
0x180034825  xor     edx, edx; length
0x180034827  call    cs:__imp_WindowsGetStringRawBuffer
0x18003482d  jmp     short loc_180034836
0x18003482f  lea     rax, aFailedToGetUse; "failed to get user SID"
0x180034836  mov     rcx, [rbp+4Fh]; this
0x18003483a  mov     [rsp+0C0h+var_90], rbx
0x18003483f  mov     [rsp+0C0h+var_98], rax; char *
0x180034844  lea     rax, aCannotFindAMai; "Cannot find a main or optional package "...
0x18003484b  mov     qword ptr [rsp+0C0h+var_A0], rax; int
0x180034850  mov     r9d, 8000FFFFh; char *
0x180034856  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\appreadiness\\src\\g"...
0x18003485d  mov     edx, 1DAh; void *
0x180034862  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x180034867  nop
0x180034868  mov     rcx, [rbp+47h+string]; string
0x18003486c  call    cs:__imp_WindowsDeleteString
0x180034872  mov     [rbp+47h+string], r13
0x180034876  lea     rcx, [rbp+47h+var_70]
0x18003487a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003487f  nop
0x180034880  lea     rcx, [rbp+47h+var_78]
0x180034884  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180034889  xor     al, al
0x18003488b  jmp     loc_180034A60
0x180034890  cmp     eax, 1
0x180034893  jz      short loc_18003489A
0x180034895  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "installedMainOrOptionalPackageCount == 1", "There should be exactly 1 main or optional package registered for a user if a bundle with the same family name is registered for the user.")
0x18003489a  mov     rcx, qword ptr [rbp+47h+var_70]
0x18003489e  mov     rax, [rcx]
0x1800348a1  lea     r8, [rbp+47h+var_78]
0x1800348a5  xor     edx, edx
0x1800348a7  mov     rax, [rax+30h]
0x1800348ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800348b0  mov     rcx, [rbp+4Fh]; this
0x1800348b4  test    eax, eax
0x1800348b6  jns     short loc_1800348CD
0x1800348b8  mov     r9d, eax; char *
0x1800348bb  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\appreadiness\\src\\g"...
0x1800348c2  mov     edx, 1E3h; void *
0x1800348c7  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800348cd  lea     rcx, [rbp+47h+var_70]
0x1800348d1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800348d6  mov     [rbp+47h+arg_10], r13b
0x1800348da  mov     rcx, [rbp+47h+var_78]
0x1800348de  mov     rax, [rcx]
0x1800348e1  lea     rdx, [rbp+47h+arg_10]
0x1800348e5  mov     rax, [rax+318h]
0x1800348ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800348f1  mov     rcx, [rbp+4Fh]; this
0x1800348f5  test    eax, eax
0x1800348f7  jns     short loc_18003490E
0x1800348f9  mov     r9d, eax; char *
0x1800348fc  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\appreadiness\\src\\g"...
0x180034903  mov     edx, 1E7h; void *
0x180034908  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18003490e  cmp     [rbp+47h+arg_10], r13b
0x180034912  jnz     loc_180034880
0x180034918  mov     [rbp+47h+var_50], r13
0x18003491c  mov     rcx, [rbp+47h+var_78]
0x180034920  mov     rax, [rcx]
0x180034923  lea     rdx, [rbp+47h+var_50]
0x180034927  mov     rax, [rax+70h]
0x18003492b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034930  mov     rcx, [rbp+4Fh]; this
0x180034934  test    eax, eax
0x180034936  jns     short loc_18003494D
0x180034938  mov     r9d, eax; char *
0x18003493b  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\appreadiness\\src\\g"...
0x180034942  mov     edx, 1EFh; void *
0x180034947  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18003494d  mov     [rbp+47h+var_58], r13
0x180034951  mov     rdi, [r15+188h]
0x180034958  mov     rax, [rdi]
0x18003495b  mov     rbx, [rax+58h]
0x18003495f  lea     rcx, [rbp+47h+var_58]
0x180034963  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180034968  lea     r8, [rbp+47h+var_58]
0x18003496c  mov     rdx, [rbp+47h+var_50]
0x180034970  mov     rcx, rdi
0x180034973  mov     rax, rbx
0x180034976  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003497b  mov     rcx, [rbp+4Fh]; this
0x18003497f  test    eax, eax
0x180034981  jns     short loc_180034998
0x180034983  mov     r9d, eax; char *
0x180034986  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\appreadiness\\src\\g"...
0x18003498d  mov     edx, 1F1h; void *
0x180034992  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180034998  mov     [rbp+47h+var_60], r13
0x18003499c  mov     rdi, [r15+180h]
0x1800349a3  mov     rax, [rdi]
0x1800349a6  mov     rbx, [rax+50h]
0x1800349aa  lea     rcx, [rbp+47h+var_60]
0x1800349ae  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800349b3  lea     r9, [rbp+47h+var_60]
0x1800349b7  mov     r8, [rbp+47h+var_58]
0x1800349bb  mov     rdx, rsi
0x1800349be  mov     rcx, rdi
0x1800349c1  mov     rax, rbx
0x1800349c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800349c9  mov     rcx, [rbp+4Fh]; this
0x1800349cd  test    eax, eax
0x1800349cf  jns     short loc_1800349E6
0x1800349d1  mov     r9d, eax; char *
0x1800349d4  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\appreadiness\\src\\g"...
0x1800349db  mov     edx, 1F4h; void *
0x1800349e0  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800349e6  mov     rcx, [rbp+47h+var_60]
0x1800349ea  test    rcx, rcx
0x1800349ed  jz      short loc_180034A41
0x1800349ef  mov     [rbp+47h+var_80], r13d
0x1800349f3  mov     rax, [rcx]
0x1800349f6  lea     rdx, [rbp+47h+var_80]
0x1800349fa  mov     rax, [rax+60h]
0x1800349fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034a03  mov     rcx, [rbp+4Fh]; this
0x180034a07  test    eax, eax
0x180034a09  jns     short loc_180034A20
0x180034a0b  mov     r9d, eax; char *
0x180034a0e  lea     r8, aOnecoreuapShel_2; "onecoreuap\\shell\\appreadiness\\src\\g"...
0x180034a15  mov     edx, 1FDh; void *
0x180034a1a  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180034a20  test    [rbp+47h+var_80], 10000000h
0x180034a27  jz      short loc_180034A41
0x180034a29  lea     rcx, [rbp+47h+var_60]
0x180034a2d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180034a32  nop
0x180034a33  lea     rcx, [rbp+47h+var_58]
0x180034a37  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180034a3c  jmp     loc_180034880
0x180034a41  lea     rcx, [rbp+47h+var_60]
0x180034a45  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180034a4a  nop
0x180034a4b  lea     rcx, [rbp+47h+var_58]
0x180034a4f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180034a54  nop
0x180034a55  lea     rcx, [rbp+47h+var_78]
0x180034a59  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180034a5e  mov     al, 1
0x180034a60  add     rsp, 88h
0x180034a67  pop     r15
0x180034a69  pop     r14
0x180034a6b  pop     r13
0x180034a6d  pop     r12
0x180034a6f  pop     rdi
0x180034a70  pop     rsi
0x180034a71  pop     rbx
0x180034a72  pop     rbp
0x180034a73  retn
```
