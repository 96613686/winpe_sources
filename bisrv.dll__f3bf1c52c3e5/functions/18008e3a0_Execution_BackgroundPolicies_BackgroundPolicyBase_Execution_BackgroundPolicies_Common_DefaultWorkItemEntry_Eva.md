# Execution::BackgroundPolicies::BackgroundPolicyBase<Execution::BackgroundPolicies::Common::DefaultWorkItemEntry>::EvaluateWorkItem(Execution::BackgroundPolicies::Common::DefaultWorkItemEntry *,bool)

- ea: `0x18008e3a0`
- end: `0x18008e7e1`
- name: `?EvaluateWorkItem@?$BackgroundPolicyBase@VDefaultWorkItemEntry@Common@BackgroundPolicies@Execution@@@BackgroundPolicies@Execution@@MEAAJPEAVDefaultWorkItemEntry@Common@23@_N@Z`
- size: `1089`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18001a1f0`
- `0x18001ef7c`
- `0x18003654c`
- `0x180038010`
- `0x18006b844`
- `0x18006b86c`
- `0x18008d9dc`
- `0x18008daac`
- `0x18008e3a0`
- `0x180095010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008e46e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008e56e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008e664`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008e677`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008e6ca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008e6de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008e711`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008e740`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008e775`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008e788`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008e46e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008e56e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008e664`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008e677`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008e6ca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008e6de`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008e711`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008e740`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008e775`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008e788`
- `ResourcePolicyClient!CreateResourcePolicyStoreClient` at `0x18008e5ad`
- `ResourcePolicyClient!CreateResourcePolicyStoreClient` at `0x18008e5ad`

## string_xrefs

- `0x18008e5ea`: `LmaDefaultModernBackgroundTask`

## pseudocode

```c
__int64 __fastcall Execution::BackgroundPolicies::BackgroundPolicyBase<Execution::BackgroundPolicies::Common::DefaultWorkItemEntry>::EvaluateWorkItem(
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
      if ( !(unsigned __int8)Execution::BackgroundPolicies::BackgroundPolicyBase<Execution::BackgroundPolicies::Common::DefaultWorkItemEntry>::HasBatterySaverOverride(
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
          && !(unsigned __int8)Execution::BackgroundPolicies::BackgroundPolicyBase<Execution::BackgroundPolicies::Common::DefaultWorkItemEntry>::IsAllowedInQuietingMode(
                                 a1,
                                 a2) )
        {
          v30 = WindowsGetStringRawBuffer(*(HSTRING *)(a2 + 72), 0);
          v34 = 2;
          goto LABEL_53;
        }
        if ( !(unsigned __int8)Execution::BackgroundPolicies::BackgroundPolicyBase<Execution::BackgroundPolicies::Common::DefaultWorkItemEntry>::HasBatterySaverOverride(
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
0x18008e3a0  mov     [rsp-38h+arg_0], rbx
0x18008e3a5  push    rbp
0x18008e3a6  push    rsi
0x18008e3a7  push    rdi
0x18008e3a8  push    r12
0x18008e3aa  push    r13
0x18008e3ac  push    r14
0x18008e3ae  push    r15
0x18008e3b0  mov     rbp, rsp
0x18008e3b3  sub     rsp, 70h
0x18008e3b7  xor     eax, eax
0x18008e3b9  mov     [rbp+arg_18], 31h ; '1'
0x18008e3c0  mov     [rbp+var_18], eax
0x18008e3c3  mov     rsi, rdx
0x18008e3c6  mov     [rbp+var_10], rax
0x18008e3ca  mov     r15, rcx
0x18008e3cd  mov     [rbp+var_20], rax
0x18008e3d1  mov     [rbp+arg_8], eax
0x18008e3d4  mov     [rbp+var_14], eax
0x18008e3d7  test    rdx, rdx
0x18008e3da  jnz     short loc_18008E3EE
0x18008e3dc  mov     ebx, 80070057h
0x18008e3e1  mov     edx, 1BBh
0x18008e3e6  mov     r9d, ebx
0x18008e3e9  jmp     loc_18008E4C3
0x18008e3ee  mov     dword ptr [rdx+74h], 61A8h
0x18008e3f5  lea     r12, [rdx+70h]
0x18008e3f9  mov     r14d, 1
0x18008e3ff  mov     [r12], r14d
0x18008e403  mov     rdi, [rcx+10h]
0x18008e407  lea     rcx, [rbp+var_10]
0x18008e40b  mov     rax, [rdi]
0x18008e40e  mov     rbx, [rax+0A8h]
0x18008e415  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18008e41a  lea     r13, [rsi+20h]
0x18008e41e  mov     rcx, rdi
0x18008e421  mov     rdx, r13
0x18008e424  lea     r8, [rbp+var_10]
0x18008e428  mov     rax, rbx
0x18008e42b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e430  test    byte ptr [rsi+68h], 8
0x18008e434  jz      short loc_18008E499
0x18008e436  mov     [rbp+arg_18], 2Ah ; '*'
0x18008e43d  mov     [rbp+var_40], r14d
0x18008e441  mov     [rbp+arg_8], r14d
0x18008e445  lea     rdi, [rsi+74h]
0x18008e449  test    byte ptr [rsi+50h], 80h
0x18008e44d  jz      short loc_18008E45A
0x18008e44f  or      dword ptr [r12], 10h
0x18008e454  mov     dword ptr [rdi], 0
0x18008e45a  mov     rdi, [r15+10h]
0x18008e45e  xor     edx, edx; length
0x18008e460  mov     rcx, [rsi+40h]; string
0x18008e464  mov     rax, [rdi]
0x18008e467  mov     rbx, [rax+0B8h]
0x18008e46e  call    cs:__imp_WindowsGetStringRawBuffer
0x18008e474  lea     r8, [rbp+var_14]
0x18008e478  mov     rcx, rdi
0x18008e47b  mov     rdx, rax
0x18008e47e  mov     rax, rbx
0x18008e481  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e486  xor     edi, edi
0x18008e488  mov     ebx, eax
0x18008e48a  test    eax, eax
0x18008e48c  jns     loc_18008E62C
0x18008e492  mov     edx, 214h
0x18008e497  jmp     short loc_18008E4C0
0x18008e499  xor     edi, edi
0x18008e49b  mov     [rbp+var_40], edi
0x18008e49e  cmp     [rbp+var_10], rdi
0x18008e4a2  jz      loc_18008E565
0x18008e4a8  lea     rdx, [rbp+var_20]
0x18008e4ac  lea     rcx, [rbp+var_10]
0x18008e4b0  call    ??$As@UIBackgroundManagerEventSettings2@@@?$ComPtr@UIBackgroundManagerEventSettings@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIBackgroundManagerEventSettings2@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IBackgroundManagerEventSettings>::As<IBackgroundManagerEventSettings2>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IBackgroundManagerEventSettings2>>)
0x18008e4b5  mov     ebx, eax
0x18008e4b7  test    eax, eax
0x18008e4b9  jns     short loc_18008E4D8
0x18008e4bb  mov     edx, 1D7h; void *
0x18008e4c0  mov     r9d, eax; char *
0x18008e4c3  mov     rcx, [rbp+38h]; this
0x18008e4c7  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\background\\bi\\backg"...
0x18008e4ce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008e4d3  jmp     loc_18008E7B5
0x18008e4d8  mov     rcx, [rbp+var_20]
0x18008e4dc  lea     rdx, [rbp+arg_18]
0x18008e4e0  mov     rax, [rcx]
0x18008e4e3  mov     rax, [rax+20h]
0x18008e4e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e4ec  mov     ebx, eax
0x18008e4ee  test    eax, eax
0x18008e4f0  jns     short loc_18008E4F9
0x18008e4f2  mov     edx, 1D8h
0x18008e4f7  jmp     short loc_18008E4C0
0x18008e4f9  mov     rcx, [rbp+var_20]
0x18008e4fd  lea     rdi, [rsi+74h]
0x18008e501  mov     rdx, rdi
0x18008e504  mov     rax, [rcx]
0x18008e507  mov     rax, [rax+48h]
0x18008e50b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e510  mov     ebx, eax
0x18008e512  test    eax, eax
0x18008e514  jns     short loc_18008E51D
0x18008e516  mov     edx, 1D9h
0x18008e51b  jmp     short loc_18008E4C0
0x18008e51d  mov     rcx, [rbp+var_20]
0x18008e521  mov     rdx, r12
0x18008e524  mov     rax, [rcx]
0x18008e527  mov     rax, [rax+50h]
0x18008e52b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e530  mov     ebx, eax
0x18008e532  test    eax, eax
0x18008e534  jns     short loc_18008E53D
0x18008e536  mov     edx, 1DAh
0x18008e53b  jmp     short loc_18008E4C0
0x18008e53d  mov     rcx, [rbp+var_20]
0x18008e541  lea     rdx, [rbp+arg_8]
0x18008e545  mov     rax, [rcx]
0x18008e548  mov     rax, [rax+58h]
0x18008e54c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e551  mov     ebx, eax
0x18008e553  test    eax, eax
0x18008e555  jns     loc_18008E449
0x18008e55b  mov     edx, 1DBh
0x18008e560  jmp     loc_18008E4C0
0x18008e565  mov     rcx, [rsi+30h]; string
0x18008e569  xor     edx, edx; length
0x18008e56b  mov     dword ptr [rbp+var_3C], edi
0x18008e56e  call    cs:__imp_WindowsGetStringRawBuffer
0x18008e574  mov     rcx, [rsi+60h]; this
0x18008e578  lea     r8, [rbp+var_3C]; unsigned __int16 *
0x18008e57c  mov     rdx, rax; void *
0x18008e57f  call    ?GetAppModelAppInfoFromPsmKey@Shared@DevPlat@@YAJPEAXPEBGPEAW4ExecModelAppType@12@@Z; DevPlat::Shared::GetAppModelAppInfoFromPsmKey(void *,ushort const *,DevPlat::Shared::ExecModelAppType *)
0x18008e584  mov     edx, dword ptr [rbp+var_3C]
0x18008e587  test    eax, eax
0x18008e589  cmovs   edx, edi
0x18008e58c  cmp     edx, 2
0x18008e58f  jnz     loc_18008E445
0x18008e595  lea     rcx, [rbp+var_28]
0x18008e599  mov     dword ptr [rbp+var_3C], 39h ; '9'
0x18008e5a0  mov     [rbp+var_28], rdi
0x18008e5a4  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18008e5a9  lea     rcx, [rbp+var_28]
0x18008e5ad  call    cs:__imp_CreateResourcePolicyStoreClient
0x18008e5b3  mov     ebx, eax
0x18008e5b5  test    eax, eax
0x18008e5b7  jns     short loc_18008E5DF
0x18008e5b9  mov     edx, 1F8h; void *
0x18008e5be  mov     rcx, [rbp+38h]; this
0x18008e5c2  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\background\\bi\\backg"...
0x18008e5c9  mov     r9d, eax; char *
0x18008e5cc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008e5d1  lea     rcx, [rbp+var_28]
0x18008e5d5  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18008e5da  jmp     loc_18008E7B5
0x18008e5df  mov     rcx, [rbp+var_28]
0x18008e5e3  lea     r9, [rbp+var_3C]
0x18008e5e7  xor     r8d, r8d
0x18008e5ea  lea     rdx, aLmadefaultmode; "LmaDefaultModernBackgroundTask"
0x18008e5f1  mov     rax, [rcx]
0x18008e5f4  mov     rax, [rax+18h]
0x18008e5f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e5fd  mov     ebx, eax
0x18008e5ff  test    eax, eax
0x18008e601  jns     short loc_18008E60A
0x18008e603  mov     edx, 1FBh
0x18008e608  jmp     short loc_18008E5BE
0x18008e60a  mov     eax, dword ptr [rbp+var_3C]
0x18008e60d  lea     rcx, [rbp+var_28]
0x18008e611  mov     [r12], edi
0x18008e615  lea     rdi, [rsi+74h]
0x18008e619  mov     dword ptr [rdi], 0
0x18008e61f  mov     [rbp+arg_18], eax
0x18008e622  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18008e627  jmp     loc_18008E449
0x18008e62c  mov     rcx, [r15+10h]
0x18008e630  lea     rdx, [rbp+var_18]
0x18008e634  mov     rax, [rcx]
0x18008e637  mov     rax, [rax+90h]
0x18008e63e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e643  mov     ebx, eax
0x18008e645  test    eax, eax
0x18008e647  jns     short loc_18008E653
0x18008e649  mov     edx, 215h
0x18008e64e  jmp     loc_18008E4C0
0x18008e653  cmp     [rbp+arg_8], edi
0x18008e656  jnz     short loc_18008E6AA
0x18008e658  test    byte ptr [rsi+50h], 20h
0x18008e65c  jz      short loc_18008E6AA
0x18008e65e  mov     rcx, [rsi+48h]; string
0x18008e662  xor     edx, edx; length
0x18008e664  call    cs:__imp_WindowsGetStringRawBuffer
0x18008e66a  mov     rcx, [rsi+30h]; string
0x18008e66e  xor     edx, edx; length
0x18008e670  mov     [rbp+var_38], rax
0x18008e674  mov     [rbp+var_40], edi
0x18008e677  call    cs:__imp_WindowsGetStringRawBuffer
0x18008e67d  mov     [rbp+var_30], rax
0x18008e681  lea     rcx, [rbp+var_30]
0x18008e685  lea     rax, [rbp+var_38]
0x18008e689  mov     rdx, r13
0x18008e68c  mov     qword ptr [rsp+70h+var_50], rax
0x18008e691  lea     r9, [rbp+var_40]
0x18008e695  lea     r8, [rsi+54h]
0x18008e699  call    ??$OnPolicyDropped@PEBGAEAU_GUID@@AEAKW4PolicyDropReason@BmTraceProvider@Execution@@PEBG@BmTraceProvider@Execution@@SAX$$QEAPEBGAEAU_GUID@@AEAK$$QEAW4PolicyDropReason@01@0@Z; Execution::BmTraceProvider::OnPolicyDropped<ushort const *,_GUID &,ulong &,Execution::BmTraceProvider::PolicyDropReason,ushort const *>(ushort const * &&,_GUID &,ulong &,Execution::BmTraceProvider::PolicyDropReason &&,ushort const * &&)
0x18008e69e  mov     dword ptr [rsi+6Ch], 2
0x18008e6a5  jmp     loc_18008E7B3
0x18008e6aa  mov     rdx, rsi
0x18008e6ad  mov     rcx, r15
0x18008e6b0  call    ?HasBatterySaverOverride@?$BackgroundPolicyBase@VDefaultWorkItemEntry@Common@BackgroundPolicies@Execution@@@BackgroundPolicies@Execution@@IEAA_NPEAVDefaultWorkItemEntry@Common@23@@Z; Execution::BackgroundPolicies::BackgroundPolicyBase<Execution::BackgroundPolicies::Common::DefaultWorkItemEntry>::HasBatterySaverOverride(Execution::BackgroundPolicies::Common::DefaultWorkItemEntry *)
0x18008e6b5  test    al, al
0x18008e6b7  jnz     short loc_18008E6F2
0x18008e6b9  test    byte ptr [rsi+50h], 10h
0x18008e6bd  jz      short loc_18008E6F2
0x18008e6bf  cmp     [rbp+arg_8], edi
0x18008e6c2  jnz     short loc_18008E6F2
0x18008e6c4  mov     rcx, [rsi+48h]; string
0x18008e6c8  xor     edx, edx; length
0x18008e6ca  call    cs:__imp_WindowsGetStringRawBuffer
0x18008e6d0  mov     rcx, [rsi+30h]; string
0x18008e6d4  xor     edx, edx; length
0x18008e6d6  mov     [rbp+var_30], rax
0x18008e6da  mov     [rbp+var_40], r14d
0x18008e6de  call    cs:__imp_WindowsGetStringRawBuffer
0x18008e6e4  mov     [rbp+var_38], rax
0x18008e6e8  lea     rcx, [rbp+var_38]
0x18008e6ec  lea     rax, [rbp+var_30]
0x18008e6f0  jmp     short loc_18008E689
0x18008e6f2  cmp     [rbp+var_40], edi
0x18008e6f5  jnz     short loc_18008E74C
0x18008e6f7  cmp     [rbp+var_18], edi
0x18008e6fa  jz      short loc_18008E720
0x18008e6fc  mov     rdx, rsi
0x18008e6ff  mov     rcx, r15
0x18008e702  call    ?IsAllowedInQuietingMode@?$BackgroundPolicyBase@VDefaultWorkItemEntry@Common@BackgroundPolicies@Execution@@@BackgroundPolicies@Execution@@IEAA_NPEAVDefaultWorkItemEntry@Common@23@@Z; Execution::BackgroundPolicies::BackgroundPolicyBase<Execution::BackgroundPolicies::Common::DefaultWorkItemEntry>::IsAllowedInQuietingMode(Execution::BackgroundPolicies::Common::DefaultWorkItemEntry *)
0x18008e707  test    al, al
0x18008e709  jnz     short loc_18008E720
0x18008e70b  mov     rcx, [rsi+48h]; string
0x18008e70f  xor     edx, edx; length
0x18008e711  call    cs:__imp_WindowsGetStringRawBuffer
0x18008e717  mov     [rbp+var_40], 2
0x18008e71e  jmp     short loc_18008E77E
0x18008e720  mov     rdx, rsi
0x18008e723  mov     rcx, r15
0x18008e726  call    ?HasBatterySaverOverride@?$BackgroundPolicyBase@VDefaultWorkItemEntry@Common@BackgroundPolicies@Execution@@@BackgroundPolicies@Execution@@IEAA_NPEAVDefaultWorkItemEntry@Common@23@@Z; Execution::BackgroundPolicies::BackgroundPolicyBase<Execution::BackgroundPolicies::Common::DefaultWorkItemEntry>::HasBatterySaverOverride(Execution::BackgroundPolicies::Common::DefaultWorkItemEntry *)
0x18008e72b  test    al, al
0x18008e72d  jnz     short loc_18008E74C
0x18008e72f  cmp     [rbp+var_14], edi
0x18008e732  jz      short loc_18008E74C
0x18008e734  test    byte ptr [rsi+50h], 2
0x18008e738  jnz     short loc_18008E74C
0x18008e73a  mov     rcx, [rsi+48h]; string
0x18008e73e  xor     edx, edx; length
0x18008e740  call    cs:__imp_WindowsGetStringRawBuffer
0x18008e746  mov     [rbp+var_40], r14d
0x18008e74a  jmp     short loc_18008E77E
0x18008e74c  mov     rcx, [r15+10h]
0x18008e750  xor     r9d, r9d
0x18008e753  mov     r8d, [rbp+arg_18]
0x18008e757  mov     rdx, r13
0x18008e75a  mov     rax, [rcx]
0x18008e75d  mov     rax, [rax+28h]
0x18008e761  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e766  test    eax, eax
0x18008e768  js      short loc_18008E76F
0x18008e76a  mov     r14d, edi
0x18008e76d  jmp     short loc_18008E7AF
0x18008e76f  mov     rcx, [rsi+48h]; string
0x18008e773  xor     edx, edx; length
0x18008e775  call    cs:__imp_WindowsGetStringRawBuffer
0x18008e77b  mov     [rbp+var_40], edi
0x18008e77e  mov     rcx, [rsi+30h]; string
0x18008e782  xor     edx, edx; length
0x18008e784  mov     [rbp+var_30], rax
0x18008e788  call    cs:__imp_WindowsGetStringRawBuffer
0x18008e78e  mov     [rbp+var_38], rax
0x18008e792  lea     r9, [rbp+var_40]
0x18008e796  lea     rax, [rbp+var_30]
0x18008e79a  mov     rdx, r13
0x18008e79d  lea     r8, [rsi+54h]
0x18008e7a1  mov     qword ptr [rsp+70h+var_50], rax
0x18008e7a6  lea     rcx, [rbp+var_38]
0x18008e7aa  call    ??$OnPolicyBuffered@PEBGAEAU_GUID@@AEAKW4PolicyBufferingReason@BmTraceProvider@Execution@@PEBG@BmTraceProvider@Execution@@SAX$$QEAPEBGAEAU_GUID@@AEAK$$QEAW4PolicyBufferingReason@01@0@Z; Execution::BmTraceProvider::OnPolicyBuffered<ushort const *,_GUID &,ulong &,Execution::BmTraceProvider::PolicyBufferingReason,ushort const *>(ushort const * &&,_GUID &,ulong &,Execution::BmTraceProvider::PolicyBufferingReason &&,ushort const * &&)
0x18008e7af  mov     [rsi+6Ch], r14d
0x18008e7b3  mov     ebx, edi
0x18008e7b5  lea     rcx, [rbp+var_20]
0x18008e7b9  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18008e7be  lea     rcx, [rbp+var_10]
0x18008e7c2  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18008e7c7  mov     eax, ebx
0x18008e7c9  mov     rbx, [rsp+70h+arg_0]
0x18008e7d1  add     rsp, 70h
0x18008e7d5  pop     r15
0x18008e7d7  pop     r14
0x18008e7d9  pop     r13
0x18008e7db  pop     r12
0x18008e7dd  pop     rdi
0x18008e7de  pop     rsi
0x18008e7df  pop     rbp
0x18008e7e0  retn
```
