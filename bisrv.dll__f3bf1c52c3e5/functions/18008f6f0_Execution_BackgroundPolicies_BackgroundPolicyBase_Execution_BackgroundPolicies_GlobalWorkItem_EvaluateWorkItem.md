# Execution::BackgroundPolicies::BackgroundPolicyBase<Execution::BackgroundPolicies::GlobalWorkItem>::EvaluateWorkItem(Execution::BackgroundPolicies::GlobalWorkItem *,bool)

- ea: `0x18008f6f0`
- end: `0x18008fb31`
- name: `?EvaluateWorkItem@?$BackgroundPolicyBase@VGlobalWorkItem@BackgroundPolicies@Execution@@@BackgroundPolicies@Execution@@MEAAJPEAVGlobalWorkItem@23@_N@Z`
- size: `1089`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18001a1f0`
- `0x18001ef7c`
- `0x18003654c`
- `0x180037f34`
- `0x180038010`
- `0x18006b128`
- `0x18008d9dc`
- `0x18008daac`
- `0x18008f6f0`
- `0x180095010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008f7be`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008f8be`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008f9b4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008f9c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008fa1a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008fa2e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008fa61`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008fa90`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008fac5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008fad8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008f7be`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008f8be`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008f9b4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008f9c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008fa1a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008fa2e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008fa61`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008fa90`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008fac5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008fad8`
- `ResourcePolicyClient!CreateResourcePolicyStoreClient` at `0x18008f8fd`
- `ResourcePolicyClient!CreateResourcePolicyStoreClient` at `0x18008f8fd`

## string_xrefs

- `0x18008f93a`: `LmaDefaultModernBackgroundTask`

## pseudocode

```c
__int64 __fastcall Execution::BackgroundPolicies::BackgroundPolicyBase<Execution::BackgroundPolicies::GlobalWorkItem>::EvaluateWorkItem(
        __int64 a1,
        __int64 a2)
{
  unsigned int v4; // ebx
  __int64 v5; // rdx
  __int64 v6; // r9
  _DWORD *v7; // r12
  int v8; // r14d
  __int64 v9; // rdi
  void (__fastcall *v10)(__int64, __int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64)); // rbx
  _DWORD *v11; // rdi
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, PCWSTR, int *); // rbx
  PCWSTR StringRawBuffer; // rax
  int v15; // eax
  HSTRING v16; // rcx
  WCHAR *v17; // rax
  enum DevPlat::Shared::ExecModelAppType *v18; // r9
  int AppModelAppInfoFromPsmKey; // eax
  int v20; // edx
  int v21; // eax
  __int64 v22; // rdx
  unsigned int v23; // eax
  PCWSTR v24; // rax
  HSTRING v25; // rcx
  PCWSTR *v26; // rcx
  PCWSTR *v27; // rax
  PCWSTR v28; // rax
  HSTRING v29; // rcx
  PCWSTR v30; // rax
  HSTRING v31; // rcx
  int v33; // [rsp+20h] [rbp-50h]
  int v34; // [rsp+30h] [rbp-40h] BYREF
  unsigned __int16 v35[2]; // [rsp+34h] [rbp-3Ch] BYREF
  PCWSTR v36; // [rsp+38h] [rbp-38h] BYREF
  PCWSTR v37; // [rsp+40h] [rbp-30h] BYREF
  __int64 v38; // [rsp+48h] [rbp-28h] BYREF
  __int64 v39; // [rsp+50h] [rbp-20h] BYREF
  int v40; // [rsp+58h] [rbp-18h] BYREF
  int v41; // [rsp+5Ch] [rbp-14h] BYREF
  __int64 (__fastcall ***v42[2])(_QWORD, GUID *, __int64); // [rsp+60h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]
  int v44; // [rsp+B8h] [rbp+48h] BYREF
  unsigned int v45; // [rsp+C8h] [rbp+58h] BYREF

  v45 = 49;
  v40 = 0;
  v42[0] = 0;
  v39 = 0;
  v44 = 0;
  v41 = 0;
  if ( a2 )
  {
    *(_DWORD *)(a2 + 116) = 25000;
    v7 = (_DWORD *)(a2 + 112);
    v8 = 1;
    *(_DWORD *)(a2 + 112) = 1;
    v9 = *(_QWORD *)(a1 + 16);
    v10 = *(void (__fastcall **)(__int64, __int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64)))(*(_QWORD *)v9 + 168LL);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v42);
    v10(v9, a2 + 32, v42);
    if ( (*(_BYTE *)(a2 + 104) & 8) != 0 )
    {
      v45 = 42;
      v34 = 1;
      v44 = 1;
LABEL_5:
      v11 = (_DWORD *)(a2 + 116);
      goto LABEL_6;
    }
    v34 = 0;
    if ( v42[0] )
    {
      v15 = Microsoft::WRL::ComPtr<IBackgroundManagerEventSettings>::As<IBackgroundManagerEventSettings2>(
              v42,
              (__int64)&v39);
      v4 = v15;
      if ( v15 < 0 )
      {
        v5 = 471;
        goto LABEL_13;
      }
      v15 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v39 + 32LL))(v39, &v45);
      v4 = v15;
      if ( v15 < 0 )
      {
        v5 = 472;
        goto LABEL_13;
      }
      v11 = (_DWORD *)(a2 + 116);
      v15 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v39 + 72LL))(v39, a2 + 116);
      v4 = v15;
      if ( v15 < 0 )
      {
        v5 = 473;
        goto LABEL_13;
      }
      v15 = (*(__int64 (__fastcall **)(__int64, _DWORD *))(*(_QWORD *)v39 + 80LL))(v39, v7);
      v4 = v15;
      if ( v15 < 0 )
      {
        v5 = 474;
        goto LABEL_13;
      }
      v15 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v39 + 88LL))(v39, &v44);
      v4 = v15;
      if ( v15 < 0 )
      {
        v5 = 475;
        goto LABEL_13;
      }
LABEL_6:
      if ( *(char *)(a2 + 80) < 0 )
      {
        *v7 |= 0x10u;
        *v11 = 0;
      }
      v12 = *(_QWORD *)(a1 + 16);
      v13 = *(__int64 (__fastcall **)(__int64, PCWSTR, int *))(*(_QWORD *)v12 + 184LL);
      StringRawBuffer = WindowsGetStringRawBuffer(*(HSTRING *)(a2 + 64), 0);
      v15 = v13(v12, StringRawBuffer, &v41);
      v4 = v15;
      if ( v15 < 0 )
      {
        v5 = 532;
LABEL_13:
        v6 = (unsigned int)v15;
        goto LABEL_14;
      }
      v15 = (*(__int64 (__fastcall **)(_QWORD, int *))(**(_QWORD **)(a1 + 16) + 144LL))(*(_QWORD *)(a1 + 16), &v40);
      v4 = v15;
      if ( v15 < 0 )
      {
        v5 = 533;
        goto LABEL_13;
      }
      if ( !v44 && (*(_BYTE *)(a2 + 80) & 0x20) != 0 )
      {
        v24 = WindowsGetStringRawBuffer(*(HSTRING *)(a2 + 72), 0);
        v25 = *(HSTRING *)(a2 + 48);
        v36 = v24;
        v34 = 0;
        v37 = WindowsGetStringRawBuffer(v25, 0);
        v26 = &v37;
        v27 = &v36;
LABEL_37:
        Execution::BmTraceProvider::OnPolicyDropped<unsigned short const *,_GUID &,unsigned long &,enum Execution::BmTraceProvider::PolicyDropReason,unsigned short const *>(
          (_DWORD)v26,
          a2 + 32,
          a2 + 84,
          (unsigned int)&v34,
          (__int64)v27);
        *(_DWORD *)(a2 + 108) = 2;
LABEL_55:
        v4 = 0;
        goto LABEL_56;
      }
      if ( !(unsigned __int8)Execution::BackgroundPolicies::BackgroundPolicyBase<Execution::BackgroundPolicies::GlobalWorkItem>::HasBatterySaverOverride(
                               a1,
                               a2)
        && (*(_BYTE *)(a2 + 80) & 0x10) != 0
        && !v44 )
      {
        v28 = WindowsGetStringRawBuffer(*(HSTRING *)(a2 + 72), 0);
        v29 = *(HSTRING *)(a2 + 48);
        v37 = v28;
        v34 = 1;
        v36 = WindowsGetStringRawBuffer(v29, 0);
        v26 = &v36;
        v27 = &v37;
        goto LABEL_37;
      }
      if ( !v34 )
      {
        if ( v40
          && !(unsigned __int8)Execution::BackgroundPolicies::BackgroundPolicyBase<Execution::BackgroundPolicies::GlobalWorkItem>::IsAllowedInQuietingMode(
                                 a1,
                                 a2) )
        {
          v30 = WindowsGetStringRawBuffer(*(HSTRING *)(a2 + 72), 0);
          v34 = 2;
          goto LABEL_53;
        }
        if ( !(unsigned __int8)Execution::BackgroundPolicies::BackgroundPolicyBase<Execution::BackgroundPolicies::GlobalWorkItem>::HasBatterySaverOverride(
                                 a1,
                                 a2)
          && v41
          && (*(_BYTE *)(a2 + 80) & 2) == 0 )
        {
          v30 = WindowsGetStringRawBuffer(*(HSTRING *)(a2 + 72), 0);
          v34 = 1;
          goto LABEL_53;
        }
      }
      if ( (*(int (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD))(**(_QWORD **)(a1 + 16) + 40LL))(
             *(_QWORD *)(a1 + 16),
             a2 + 32,
             v45,
             0) >= 0 )
      {
        v8 = 0;
LABEL_54:
        *(_DWORD *)(a2 + 108) = v8;
        goto LABEL_55;
      }
      v30 = WindowsGetStringRawBuffer(*(HSTRING *)(a2 + 72), 0);
      v34 = 0;
LABEL_53:
      v31 = *(HSTRING *)(a2 + 48);
      v37 = v30;
      v36 = WindowsGetStringRawBuffer(v31, 0);
      Execution::BmTraceProvider::OnPolicyBuffered<unsigned short const *,_GUID &,unsigned long &,enum Execution::BmTraceProvider::PolicyBufferingReason,unsigned short const *>(
        (unsigned int)&v36,
        a2 + 32,
        a2 + 84,
        (unsigned int)&v34,
        (__int64)&v37);
      goto LABEL_54;
    }
    v16 = *(HSTRING *)(a2 + 48);
    *(_DWORD *)v35 = 0;
    v17 = (WCHAR *)WindowsGetStringRawBuffer(v16, 0);
    AppModelAppInfoFromPsmKey = DevPlat::Shared::GetAppModelAppInfoFromPsmKey(
                                  *(DevPlat::Shared **)(a2 + 96),
                                  v17,
                                  v35,
                                  v18);
    v20 = *(_DWORD *)v35;
    if ( AppModelAppInfoFromPsmKey < 0 )
      v20 = 0;
    if ( v20 != 2 )
      goto LABEL_5;
    *(_DWORD *)v35 = 57;
    v38 = 0;
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v38);
    v21 = CreateResourcePolicyStoreClient(&v38);
    v4 = v21;
    if ( v21 >= 0 )
    {
      v21 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, _QWORD, unsigned __int16 *))(*(_QWORD *)v38 + 24LL))(
              v38,
              L"LmaDefaultModernBackgroundTask",
              0,
              v35);
      v4 = v21;
      if ( v21 >= 0 )
      {
        v23 = *(_DWORD *)v35;
        *v7 = 0;
        v11 = (_DWORD *)(a2 + 116);
        *(_DWORD *)(a2 + 116) = 0;
        v45 = v23;
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v38);
        goto LABEL_6;
      }
      v22 = 507;
    }
    else
    {
      v22 = 504;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v22,
      (unsigned int)"onecoreuap\\base\\background\\bi\\backgroundmanager\\inc\\BackgroundPolicyBase.h",
      (const char *)(unsigned int)v21,
      v33);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v38);
    goto LABEL_56;
  }
  v4 = -2147024809;
  v5 = 443;
  v6 = 2147942487LL;
LABEL_14:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v5,
    (unsigned int)"onecoreuap\\base\\background\\bi\\backgroundmanager\\inc\\BackgroundPolicyBase.h",
    (const char *)v6,
    v33);
LABEL_56:
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v39);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v42);
  return v4;
}

```

## disassembly

```asm
0x18008f6f0  mov     [rsp-38h+arg_0], rbx
0x18008f6f5  push    rbp
0x18008f6f6  push    rsi
0x18008f6f7  push    rdi
0x18008f6f8  push    r12
0x18008f6fa  push    r13
0x18008f6fc  push    r14
0x18008f6fe  push    r15
0x18008f700  mov     rbp, rsp
0x18008f703  sub     rsp, 70h
0x18008f707  xor     eax, eax
0x18008f709  mov     [rbp+arg_18], 31h ; '1'
0x18008f710  mov     [rbp+var_18], eax
0x18008f713  mov     rsi, rdx
0x18008f716  mov     [rbp+var_10], rax
0x18008f71a  mov     r15, rcx
0x18008f71d  mov     [rbp+var_20], rax
0x18008f721  mov     [rbp+arg_8], eax
0x18008f724  mov     [rbp+var_14], eax
0x18008f727  test    rdx, rdx
0x18008f72a  jnz     short loc_18008F73E
0x18008f72c  mov     ebx, 80070057h
0x18008f731  mov     edx, 1BBh
0x18008f736  mov     r9d, ebx
0x18008f739  jmp     loc_18008F813
0x18008f73e  mov     dword ptr [rdx+74h], 61A8h
0x18008f745  lea     r12, [rdx+70h]
0x18008f749  mov     r14d, 1
0x18008f74f  mov     [r12], r14d
0x18008f753  mov     rdi, [rcx+10h]
0x18008f757  lea     rcx, [rbp+var_10]
0x18008f75b  mov     rax, [rdi]
0x18008f75e  mov     rbx, [rax+0A8h]
0x18008f765  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18008f76a  lea     r13, [rsi+20h]
0x18008f76e  mov     rcx, rdi
0x18008f771  mov     rdx, r13
0x18008f774  lea     r8, [rbp+var_10]
0x18008f778  mov     rax, rbx
0x18008f77b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f780  test    byte ptr [rsi+68h], 8
0x18008f784  jz      short loc_18008F7E9
0x18008f786  mov     [rbp+arg_18], 2Ah ; '*'
0x18008f78d  mov     [rbp+var_40], r14d
0x18008f791  mov     [rbp+arg_8], r14d
0x18008f795  lea     rdi, [rsi+74h]
0x18008f799  test    byte ptr [rsi+50h], 80h
0x18008f79d  jz      short loc_18008F7AA
0x18008f79f  or      dword ptr [r12], 10h
0x18008f7a4  mov     dword ptr [rdi], 0
0x18008f7aa  mov     rdi, [r15+10h]
0x18008f7ae  xor     edx, edx; length
0x18008f7b0  mov     rcx, [rsi+40h]; string
0x18008f7b4  mov     rax, [rdi]
0x18008f7b7  mov     rbx, [rax+0B8h]
0x18008f7be  call    cs:__imp_WindowsGetStringRawBuffer
0x18008f7c4  lea     r8, [rbp+var_14]
0x18008f7c8  mov     rcx, rdi
0x18008f7cb  mov     rdx, rax
0x18008f7ce  mov     rax, rbx
0x18008f7d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f7d6  xor     edi, edi
0x18008f7d8  mov     ebx, eax
0x18008f7da  test    eax, eax
0x18008f7dc  jns     loc_18008F97C
0x18008f7e2  mov     edx, 214h
0x18008f7e7  jmp     short loc_18008F810
0x18008f7e9  xor     edi, edi
0x18008f7eb  mov     [rbp+var_40], edi
0x18008f7ee  cmp     [rbp+var_10], rdi
0x18008f7f2  jz      loc_18008F8B5
0x18008f7f8  lea     rdx, [rbp+var_20]
0x18008f7fc  lea     rcx, [rbp+var_10]
0x18008f800  call    ??$As@UIBackgroundManagerEventSettings2@@@?$ComPtr@UIBackgroundManagerEventSettings@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIBackgroundManagerEventSettings2@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IBackgroundManagerEventSettings>::As<IBackgroundManagerEventSettings2>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IBackgroundManagerEventSettings2>>)
0x18008f805  mov     ebx, eax
0x18008f807  test    eax, eax
0x18008f809  jns     short loc_18008F828
0x18008f80b  mov     edx, 1D7h; void *
0x18008f810  mov     r9d, eax; char *
0x18008f813  mov     rcx, [rbp+38h]; this
0x18008f817  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\background\\bi\\backg"...
0x18008f81e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008f823  jmp     loc_18008FB05
0x18008f828  mov     rcx, [rbp+var_20]
0x18008f82c  lea     rdx, [rbp+arg_18]
0x18008f830  mov     rax, [rcx]
0x18008f833  mov     rax, [rax+20h]
0x18008f837  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f83c  mov     ebx, eax
0x18008f83e  test    eax, eax
0x18008f840  jns     short loc_18008F849
0x18008f842  mov     edx, 1D8h
0x18008f847  jmp     short loc_18008F810
0x18008f849  mov     rcx, [rbp+var_20]
0x18008f84d  lea     rdi, [rsi+74h]
0x18008f851  mov     rdx, rdi
0x18008f854  mov     rax, [rcx]
0x18008f857  mov     rax, [rax+48h]
0x18008f85b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f860  mov     ebx, eax
0x18008f862  test    eax, eax
0x18008f864  jns     short loc_18008F86D
0x18008f866  mov     edx, 1D9h
0x18008f86b  jmp     short loc_18008F810
0x18008f86d  mov     rcx, [rbp+var_20]
0x18008f871  mov     rdx, r12
0x18008f874  mov     rax, [rcx]
0x18008f877  mov     rax, [rax+50h]
0x18008f87b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f880  mov     ebx, eax
0x18008f882  test    eax, eax
0x18008f884  jns     short loc_18008F88D
0x18008f886  mov     edx, 1DAh
0x18008f88b  jmp     short loc_18008F810
0x18008f88d  mov     rcx, [rbp+var_20]
0x18008f891  lea     rdx, [rbp+arg_8]
0x18008f895  mov     rax, [rcx]
0x18008f898  mov     rax, [rax+58h]
0x18008f89c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f8a1  mov     ebx, eax
0x18008f8a3  test    eax, eax
0x18008f8a5  jns     loc_18008F799
0x18008f8ab  mov     edx, 1DBh
0x18008f8b0  jmp     loc_18008F810
0x18008f8b5  mov     rcx, [rsi+30h]; string
0x18008f8b9  xor     edx, edx; length
0x18008f8bb  mov     dword ptr [rbp+var_3C], edi
0x18008f8be  call    cs:__imp_WindowsGetStringRawBuffer
0x18008f8c4  mov     rcx, [rsi+60h]; this
0x18008f8c8  lea     r8, [rbp+var_3C]; unsigned __int16 *
0x18008f8cc  mov     rdx, rax; void *
0x18008f8cf  call    ?GetAppModelAppInfoFromPsmKey@Shared@DevPlat@@YAJPEAXPEBGPEAW4ExecModelAppType@12@@Z; DevPlat::Shared::GetAppModelAppInfoFromPsmKey(void *,ushort const *,DevPlat::Shared::ExecModelAppType *)
0x18008f8d4  mov     edx, dword ptr [rbp+var_3C]
0x18008f8d7  test    eax, eax
0x18008f8d9  cmovs   edx, edi
0x18008f8dc  cmp     edx, 2
0x18008f8df  jnz     loc_18008F795
0x18008f8e5  lea     rcx, [rbp+var_28]
0x18008f8e9  mov     dword ptr [rbp+var_3C], 39h ; '9'
0x18008f8f0  mov     [rbp+var_28], rdi
0x18008f8f4  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18008f8f9  lea     rcx, [rbp+var_28]
0x18008f8fd  call    cs:__imp_CreateResourcePolicyStoreClient
0x18008f903  mov     ebx, eax
0x18008f905  test    eax, eax
0x18008f907  jns     short loc_18008F92F
0x18008f909  mov     edx, 1F8h; void *
0x18008f90e  mov     rcx, [rbp+38h]; this
0x18008f912  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\background\\bi\\backg"...
0x18008f919  mov     r9d, eax; char *
0x18008f91c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008f921  lea     rcx, [rbp+var_28]
0x18008f925  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18008f92a  jmp     loc_18008FB05
0x18008f92f  mov     rcx, [rbp+var_28]
0x18008f933  lea     r9, [rbp+var_3C]
0x18008f937  xor     r8d, r8d
0x18008f93a  lea     rdx, aLmadefaultmode; "LmaDefaultModernBackgroundTask"
0x18008f941  mov     rax, [rcx]
0x18008f944  mov     rax, [rax+18h]
0x18008f948  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f94d  mov     ebx, eax
0x18008f94f  test    eax, eax
0x18008f951  jns     short loc_18008F95A
0x18008f953  mov     edx, 1FBh
0x18008f958  jmp     short loc_18008F90E
0x18008f95a  mov     eax, dword ptr [rbp+var_3C]
0x18008f95d  lea     rcx, [rbp+var_28]
0x18008f961  mov     [r12], edi
0x18008f965  lea     rdi, [rsi+74h]
0x18008f969  mov     dword ptr [rdi], 0
0x18008f96f  mov     [rbp+arg_18], eax
0x18008f972  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18008f977  jmp     loc_18008F799
0x18008f97c  mov     rcx, [r15+10h]
0x18008f980  lea     rdx, [rbp+var_18]
0x18008f984  mov     rax, [rcx]
0x18008f987  mov     rax, [rax+90h]
0x18008f98e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f993  mov     ebx, eax
0x18008f995  test    eax, eax
0x18008f997  jns     short loc_18008F9A3
0x18008f999  mov     edx, 215h
0x18008f99e  jmp     loc_18008F810
0x18008f9a3  cmp     [rbp+arg_8], edi
0x18008f9a6  jnz     short loc_18008F9FA
0x18008f9a8  test    byte ptr [rsi+50h], 20h
0x18008f9ac  jz      short loc_18008F9FA
0x18008f9ae  mov     rcx, [rsi+48h]; string
0x18008f9b2  xor     edx, edx; length
0x18008f9b4  call    cs:__imp_WindowsGetStringRawBuffer
0x18008f9ba  mov     rcx, [rsi+30h]; string
0x18008f9be  xor     edx, edx; length
0x18008f9c0  mov     [rbp+var_38], rax
0x18008f9c4  mov     [rbp+var_40], edi
0x18008f9c7  call    cs:__imp_WindowsGetStringRawBuffer
0x18008f9cd  mov     [rbp+var_30], rax
0x18008f9d1  lea     rcx, [rbp+var_30]
0x18008f9d5  lea     rax, [rbp+var_38]
0x18008f9d9  mov     rdx, r13
0x18008f9dc  mov     qword ptr [rsp+70h+var_50], rax
0x18008f9e1  lea     r9, [rbp+var_40]
0x18008f9e5  lea     r8, [rsi+54h]
0x18008f9e9  call    ??$OnPolicyDropped@PEBGAEAU_GUID@@AEAKW4PolicyDropReason@BmTraceProvider@Execution@@PEBG@BmTraceProvider@Execution@@SAX$$QEAPEBGAEAU_GUID@@AEAK$$QEAW4PolicyDropReason@01@0@Z; Execution::BmTraceProvider::OnPolicyDropped<ushort const *,_GUID &,ulong &,Execution::BmTraceProvider::PolicyDropReason,ushort const *>(ushort const * &&,_GUID &,ulong &,Execution::BmTraceProvider::PolicyDropReason &&,ushort const * &&)
0x18008f9ee  mov     dword ptr [rsi+6Ch], 2
0x18008f9f5  jmp     loc_18008FB03
0x18008f9fa  mov     rdx, rsi
0x18008f9fd  mov     rcx, r15
0x18008fa00  call    ?HasBatterySaverOverride@?$BackgroundPolicyBase@VGlobalWorkItem@BackgroundPolicies@Execution@@@BackgroundPolicies@Execution@@IEAA_NPEAVGlobalWorkItem@23@@Z; Execution::BackgroundPolicies::BackgroundPolicyBase<Execution::BackgroundPolicies::GlobalWorkItem>::HasBatterySaverOverride(Execution::BackgroundPolicies::GlobalWorkItem *)
0x18008fa05  test    al, al
0x18008fa07  jnz     short loc_18008FA42
0x18008fa09  test    byte ptr [rsi+50h], 10h
0x18008fa0d  jz      short loc_18008FA42
0x18008fa0f  cmp     [rbp+arg_8], edi
0x18008fa12  jnz     short loc_18008FA42
0x18008fa14  mov     rcx, [rsi+48h]; string
0x18008fa18  xor     edx, edx; length
0x18008fa1a  call    cs:__imp_WindowsGetStringRawBuffer
0x18008fa20  mov     rcx, [rsi+30h]; string
0x18008fa24  xor     edx, edx; length
0x18008fa26  mov     [rbp+var_30], rax
0x18008fa2a  mov     [rbp+var_40], r14d
0x18008fa2e  call    cs:__imp_WindowsGetStringRawBuffer
0x18008fa34  mov     [rbp+var_38], rax
0x18008fa38  lea     rcx, [rbp+var_38]
0x18008fa3c  lea     rax, [rbp+var_30]
0x18008fa40  jmp     short loc_18008F9D9
0x18008fa42  cmp     [rbp+var_40], edi
0x18008fa45  jnz     short loc_18008FA9C
0x18008fa47  cmp     [rbp+var_18], edi
0x18008fa4a  jz      short loc_18008FA70
0x18008fa4c  mov     rdx, rsi
0x18008fa4f  mov     rcx, r15
0x18008fa52  call    ?IsAllowedInQuietingMode@?$BackgroundPolicyBase@VGlobalWorkItem@BackgroundPolicies@Execution@@@BackgroundPolicies@Execution@@IEAA_NPEAVGlobalWorkItem@23@@Z; Execution::BackgroundPolicies::BackgroundPolicyBase<Execution::BackgroundPolicies::GlobalWorkItem>::IsAllowedInQuietingMode(Execution::BackgroundPolicies::GlobalWorkItem *)
0x18008fa57  test    al, al
0x18008fa59  jnz     short loc_18008FA70
0x18008fa5b  mov     rcx, [rsi+48h]; string
0x18008fa5f  xor     edx, edx; length
0x18008fa61  call    cs:__imp_WindowsGetStringRawBuffer
0x18008fa67  mov     [rbp+var_40], 2
0x18008fa6e  jmp     short loc_18008FACE
0x18008fa70  mov     rdx, rsi
0x18008fa73  mov     rcx, r15
0x18008fa76  call    ?HasBatterySaverOverride@?$BackgroundPolicyBase@VGlobalWorkItem@BackgroundPolicies@Execution@@@BackgroundPolicies@Execution@@IEAA_NPEAVGlobalWorkItem@23@@Z; Execution::BackgroundPolicies::BackgroundPolicyBase<Execution::BackgroundPolicies::GlobalWorkItem>::HasBatterySaverOverride(Execution::BackgroundPolicies::GlobalWorkItem *)
0x18008fa7b  test    al, al
0x18008fa7d  jnz     short loc_18008FA9C
0x18008fa7f  cmp     [rbp+var_14], edi
0x18008fa82  jz      short loc_18008FA9C
0x18008fa84  test    byte ptr [rsi+50h], 2
0x18008fa88  jnz     short loc_18008FA9C
0x18008fa8a  mov     rcx, [rsi+48h]; string
0x18008fa8e  xor     edx, edx; length
0x18008fa90  call    cs:__imp_WindowsGetStringRawBuffer
0x18008fa96  mov     [rbp+var_40], r14d
0x18008fa9a  jmp     short loc_18008FACE
0x18008fa9c  mov     rcx, [r15+10h]
0x18008faa0  xor     r9d, r9d
0x18008faa3  mov     r8d, [rbp+arg_18]
0x18008faa7  mov     rdx, r13
0x18008faaa  mov     rax, [rcx]
0x18008faad  mov     rax, [rax+28h]
0x18008fab1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008fab6  test    eax, eax
0x18008fab8  js      short loc_18008FABF
0x18008faba  mov     r14d, edi
0x18008fabd  jmp     short loc_18008FAFF
0x18008fabf  mov     rcx, [rsi+48h]; string
0x18008fac3  xor     edx, edx; length
0x18008fac5  call    cs:__imp_WindowsGetStringRawBuffer
0x18008facb  mov     [rbp+var_40], edi
0x18008face  mov     rcx, [rsi+30h]; string
0x18008fad2  xor     edx, edx; length
0x18008fad4  mov     [rbp+var_30], rax
0x18008fad8  call    cs:__imp_WindowsGetStringRawBuffer
0x18008fade  mov     [rbp+var_38], rax
0x18008fae2  lea     r9, [rbp+var_40]
0x18008fae6  lea     rax, [rbp+var_30]
0x18008faea  mov     rdx, r13
0x18008faed  lea     r8, [rsi+54h]
0x18008faf1  mov     qword ptr [rsp+70h+var_50], rax
0x18008faf6  lea     rcx, [rbp+var_38]
0x18008fafa  call    ??$OnPolicyBuffered@PEBGAEAU_GUID@@AEAKW4PolicyBufferingReason@BmTraceProvider@Execution@@PEBG@BmTraceProvider@Execution@@SAX$$QEAPEBGAEAU_GUID@@AEAK$$QEAW4PolicyBufferingReason@01@0@Z; Execution::BmTraceProvider::OnPolicyBuffered<ushort const *,_GUID &,ulong &,Execution::BmTraceProvider::PolicyBufferingReason,ushort const *>(ushort const * &&,_GUID &,ulong &,Execution::BmTraceProvider::PolicyBufferingReason &&,ushort const * &&)
0x18008faff  mov     [rsi+6Ch], r14d
0x18008fb03  mov     ebx, edi
0x18008fb05  lea     rcx, [rbp+var_20]
0x18008fb09  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18008fb0e  lea     rcx, [rbp+var_10]
0x18008fb12  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18008fb17  mov     eax, ebx
0x18008fb19  mov     rbx, [rsp+70h+arg_0]
0x18008fb21  add     rsp, 70h
0x18008fb25  pop     r15
0x18008fb27  pop     r14
0x18008fb29  pop     r13
0x18008fb2b  pop     r12
0x18008fb2d  pop     rdi
0x18008fb2e  pop     rsi
0x18008fb2f  pop     rbp
0x18008fb30  retn
```
