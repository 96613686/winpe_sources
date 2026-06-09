# _lambda_d499bb7c7bb9030fdb66f37c3eece255_::operator()(long,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *> *)

- ea: `0x18001b108`
- end: `0x18001b7dc`
- name: `??R_lambda_d499bb7c7bb9030fdb66f37c3eece255_@@QEBA@JPEAU?$IAsyncOperation@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@Foundation@Windows@@@Z`
- size: `1748`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001afc0`

## callees

- `0x1800076ac`
- `0x1800096ec`
- `0x18000c3f8`
- `0x180014c28`
- `0x180015000`
- `0x180019dfc`
- `0x18001ac98`
- `0x18001b108`
- `0x18001f3f8`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001b1a3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001b348`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001b362`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001b5e6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001b75d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001b7bb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001b1a3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001b348`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001b362`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001b5e6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001b75d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001b7bb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001b2f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001b37f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001b530`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001b560`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001b614`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001b628`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001b663`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001b677`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001b2f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001b37f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001b530`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001b560`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001b614`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001b628`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001b663`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001b677`

## string_xrefs

- `0x18001b161`: `ShellCommon\private\Shell\inc\tokenbrokersingleton.h`
- `0x18001b1ea`: `ShellCommon\private\Shell\inc\tokenbrokersingleton.h`
- `0x18001b28b`: `ShellCommon\private\Shell\inc\tokenbrokersingleton.h`
- `0x18001b329`: `ShellCommon\private\Shell\inc\tokenbrokersingleton.h`
- `0x18001b3ab`: `ShellCommon\private\Shell\inc\tokenbrokersingleton.h`
- `0x18001b3ff`: `ShellCommon\private\Shell\inc\tokenbrokersingleton.h`
- `0x18001b456`: `ShellCommon\private\Shell\inc\tokenbrokersingleton.h`
- `0x18001b4a7`: `ShellCommon\private\Shell\inc\tokenbrokersingleton.h`
- `0x18001b64d`: `ShellCommon\private\Shell\inc\tokenbrokersingleton.h`
- `0x18001b690`: `ShellCommon\private\Shell\inc\tokenbrokersingleton.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall _lambda_d499bb7c7bb9030fdb66f37c3eece255_::operator()(HSTRING a1, int a2, __int64 a3)
{
  __int64 (__fastcall *v5)(__int64, __int64 *); // rbx
  int v6; // eax
  unsigned int v7; // ebx
  RTL_SRWLOCK *v8; // rcx
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, RTL_SRWLOCK **); // rbx
  int v12; // eax
  __int64 v13; // rdi
  RTL_SRWLOCK *v14; // rbx
  __int64 (__fastcall *v15)(RTL_SRWLOCK *, GUID *, PSRWLOCK *); // rdi
  int v16; // eax
  RTL_SRWLOCK *v17; // rsi
  __int64 (__fastcall *v18)(RTL_SRWLOCK *, __int64); // rdi
  __int64 v19; // rbx
  int v20; // eax
  PSRWLOCK v21; // rdi
  __int64 (__fastcall *v22)(PSRWLOCK, __int64 *); // rbx
  int v23; // eax
  PSRWLOCK v24; // rdi
  __int64 (__fastcall *v25)(PSRWLOCK, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)); // rbx
  int v26; // eax
  __int64 (__fastcall ***v27)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v28)(_QWORD, GUID *, __int64 *); // rdi
  int v29; // eax
  __int64 v30; // rdi
  __int64 (__fastcall *v31)(__int64, __int64 *); // rbx
  int v32; // eax
  __int64 v33; // rdi
  __int64 (__fastcall *v34)(__int64, PSRWLOCK *); // rbx
  int v35; // eax
  PSRWLOCK v36; // rdi
  void (__fastcall *v37)(PSRWLOCK, HSTRING *); // rbx
  PSRWLOCK v38; // rdi
  void (__fastcall *v39)(PSRWLOCK, HSTRING *); // rbx
  const unsigned __int16 *v40; // r8
  const unsigned __int16 *v41; // r8
  HSTRING *v42; // rcx
  int v43; // eax
  PSRWLOCK v44; // [rsp+20h] [rbp-60h] BYREF
  PSRWLOCK v45; // [rsp+28h] [rbp-58h] BYREF
  __int64 v46; // [rsp+30h] [rbp-50h] BYREF
  __int64 (__fastcall ***v47)(_QWORD, GUID *, __int64 *); // [rsp+38h] [rbp-48h] BYREF
  __int64 v48; // [rsp+40h] [rbp-40h] BYREF
  HSTRING string; // [rsp+48h] [rbp-38h] BYREF
  HSTRING v50; // [rsp+50h] [rbp-30h] BYREF
  __int64 v51; // [rsp+58h] [rbp-28h] BYREF
  HSTRING v52[2]; // [rsp+60h] [rbp-20h] BYREF
  char v53; // [rsp+70h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]
  RTL_SRWLOCK *v55; // [rsp+C0h] [rbp+40h] BYREF
  int v56; // [rsp+C8h] [rbp+48h] BYREF
  __int64 v57; // [rsp+D0h] [rbp+50h] BYREF
  PSRWLOCK SRWLock; // [rsp+D8h] [rbp+58h] BYREF

  v56 = a2;
  v52[1] = a1;
  v53 = 1;
  v57 = 0;
  v5 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a3 + 64LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v57);
  v6 = v5(a3, &v57);
  v7 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x121,
      (unsigned int)"ShellCommon\\private\\Shell\\inc\\tokenbrokersingleton.h",
      (const char *)(unsigned int)v6,
      (int)v44);
LABEL_3:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v57);
    Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&SRWLock, *(_QWORD *)a1 + 232LL);
    v8 = SRWLock;
LABEL_4:
    *(_BYTE *)(*(_QWORD *)a1 + 241LL) = 0;
    if ( v8 )
      ReleaseSRWLockExclusive(v8);
    return v7;
  }
  v55 = 0;
  v10 = v57;
  v11 = *(__int64 (__fastcall **)(__int64, RTL_SRWLOCK **))(*(_QWORD *)v57 + 48LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v55);
  v12 = v11(v10, &v55);
  v7 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x123,
      (unsigned int)"ShellCommon\\private\\Shell\\inc\\tokenbrokersingleton.h",
      (const char *)(unsigned int)v12,
      (int)v44);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v55);
    goto LABEL_3;
  }
  v13 = *(_QWORD *)a1;
  v14 = v55;
  if ( *(RTL_SRWLOCK **)(*(_QWORD *)a1 + 248LL) != v55 )
  {
    SRWLock = v55;
    Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&SRWLock);
    SRWLock = *(PSRWLOCK *)(v13 + 248);
    *(_QWORD *)(v13 + 248) = v14;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&SRWLock);
    v14 = v55;
  }
  if ( v14 )
  {
    SRWLock = 0;
    v15 = *(__int64 (__fastcall **)(RTL_SRWLOCK *, GUID *, PSRWLOCK *))v14->Ptr;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&SRWLock);
    v16 = v15(v14, &GUID_7b56d6f8_990b_4eb5_94a7_5621f3a8b824, &SRWLock);
    v7 = v16;
    if ( v16 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x129,
        (unsigned int)"ShellCommon\\private\\Shell\\inc\\tokenbrokersingleton.h",
        (const char *)(unsigned int)v16,
        (int)v44);
LABEL_14:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&SRWLock);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v55);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v57);
      Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&v44, *(_QWORD *)a1 + 232LL);
      v8 = v44;
      goto LABEL_4;
    }
    Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&v45, *(_QWORD *)a1 + 232LL);
    v17 = v55;
    v18 = (__int64 (__fastcall *)(RTL_SRWLOCK *, __int64))*((_QWORD *)v55->Ptr + 7);
    v19 = *(_QWORD *)a1;
    WindowsDeleteString(*(HSTRING *)(*(_QWORD *)a1 + 256LL));
    *(_QWORD *)(v19 + 256) = 0;
    v20 = v18(v17, v19 + 256);
    v7 = v20;
    if ( v20 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x12E,
        (unsigned int)"ShellCommon\\private\\Shell\\inc\\tokenbrokersingleton.h",
        (const char *)(unsigned int)v20,
        (int)v44);
      if ( v45 )
        ReleaseSRWLockExclusive(v45);
      goto LABEL_14;
    }
    if ( v45 )
      ReleaseSRWLockExclusive(v45);
    v48 = 0;
    v21 = SRWLock;
    v22 = (__int64 (__fastcall *)(PSRWLOCK, __int64 *))*((_QWORD *)SRWLock->Ptr + 6);
    WindowsDeleteString(0);
    v48 = 0;
    v23 = v22(v21, &v48);
    v7 = v23;
    if ( v23 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x133,
        (unsigned int)"ShellCommon\\private\\Shell\\inc\\tokenbrokersingleton.h",
        (const char *)(unsigned int)v23,
        (int)v44);
LABEL_22:
      Windows::Internal::String::~String((Windows::Internal::String *)&v48);
      goto LABEL_14;
    }
    v47 = 0;
    v24 = SRWLock;
    v25 = (__int64 (__fastcall *)(PSRWLOCK, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))*((_QWORD *)SRWLock->Ptr
                                                                                                  + 7);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v47);
    v26 = v25(v24, &v47);
    v7 = v26;
    if ( v26 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x136,
        (unsigned int)"ShellCommon\\private\\Shell\\inc\\tokenbrokersingleton.h",
        (const char *)(unsigned int)v26,
        (int)v44);
LABEL_25:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v47);
      goto LABEL_22;
    }
    v51 = 0;
    v27 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v47;
    v28 = **v47;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v51);
    v29 = v28(v27, &GUID_e9bdaaf0_cbf6_5c72_be90_29cbf3a1319b, &v51);
    v7 = v29;
    if ( v29 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x138,
        (unsigned int)"ShellCommon\\private\\Shell\\inc\\tokenbrokersingleton.h",
        (const char *)(unsigned int)v29,
        (int)v44);
LABEL_28:
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v51);
      goto LABEL_25;
    }
    v46 = 0;
    v30 = v51;
    v31 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v51 + 48LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v46);
    v32 = v31(v30, &v46);
    v7 = v32;
    if ( v32 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x13A,
        (unsigned int)"ShellCommon\\private\\Shell\\inc\\tokenbrokersingleton.h",
        (const char *)(unsigned int)v32,
        (int)v44);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v46);
      goto LABEL_28;
    }
    LOBYTE(v56) = 0;
    while ( 1 )
    {
      if ( (*(unsigned int (__fastcall **)(__int64, int *))(*(_QWORD *)v46 + 56LL))(v46, &v56) || !(_BYTE)v56 )
      {
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v46);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v51);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v47);
        Windows::Internal::String::~String((Windows::Internal::String *)&v48);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&SRWLock);
        break;
      }
      v45 = 0;
      v33 = v46;
      v34 = *(__int64 (__fastcall **)(__int64, PSRWLOCK *))(*(_QWORD *)v46 + 48LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v45);
      v35 = v34(v33, &v45);
      v7 = v35;
      if ( v35 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x141,
          (unsigned int)"ShellCommon\\private\\Shell\\inc\\tokenbrokersingleton.h",
          (const char *)(unsigned int)v35,
          (int)v44);
        goto LABEL_46;
      }
      v50 = 0;
      v36 = v45;
      v37 = (void (__fastcall *)(PSRWLOCK, HSTRING *))*((_QWORD *)v45->Ptr + 6);
      WindowsDeleteString(0);
      v50 = 0;
      v37(v36, &v50);
      string = 0;
      v38 = v45;
      v39 = (void (__fastcall *)(PSRWLOCK, HSTRING *))*((_QWORD *)v45->Ptr + 7);
      WindowsDeleteString(0);
      string = 0;
      v39(v38, &string);
      Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&v44, *(_QWORD *)a1 + 232LL);
      if ( SystemSettings::DataModel::IsHstringEqual((SystemSettings::DataModel *)v50, (HSTRING)&stru_18005BD70, v40) )
      {
        v42 = (HSTRING *)(*(_QWORD *)a1 + 264LL);
      }
      else
      {
        if ( !SystemSettings::DataModel::IsHstringEqual((SystemSettings::DataModel *)v50, (HSTRING)&stru_18005BD88, v41) )
          goto LABEL_40;
        v42 = (HSTRING *)(*(_QWORD *)a1 + 272LL);
      }
      v52[0] = string;
      Microsoft::WRL::Wrappers::HString::Set(v42, v52);
LABEL_40:
      if ( v44 )
      {
        ReleaseSRWLockExclusive(v44);
        v44 = 0;
      }
      v43 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v46 + 64LL))(v46, &v56);
      v7 = v43;
      if ( v43 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x157,
          (unsigned int)"ShellCommon\\private\\Shell\\inc\\tokenbrokersingleton.h",
          (const char *)(unsigned int)v43,
          (int)v44);
        WindowsDeleteString(string);
        string = 0;
        WindowsDeleteString(v50);
        v50 = 0;
LABEL_46:
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v45);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v46);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v51);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v47);
        Windows::Internal::String::~String((Windows::Internal::String *)&v48);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&SRWLock);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v55);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v57);
        Microsoft::WRL::Wrappers::SRWLock::LockExclusive(v52, *(_QWORD *)a1 + 232LL);
        v8 = (RTL_SRWLOCK *)v52[0];
        goto LABEL_4;
      }
      WindowsDeleteString(string);
      string = 0;
      WindowsDeleteString(v50);
      v50 = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v45);
    }
  }
  Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&SRWLock, *(_QWORD *)a1 + 232LL);
  *(_BYTE *)(*(_QWORD *)a1 + 240LL) = 1;
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  v56 = 2;
  SRWLock = (PSRWLOCK)&v56;
  SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::WorkAccess::MDMHTMLReportSettingPhase>::_Notify<_lambda_7d9b1dafe109be445bee74074bc960ae_>(
    *(_QWORD *)a1,
    &SRWLock);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v55);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v57);
  Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&SRWLock, *(_QWORD *)a1 + 232LL);
  *(_BYTE *)(*(_QWORD *)a1 + 241LL) = 0;
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  return 0;
}

```

## disassembly

```asm
0x18001b108  mov     [rsp-38h+arg_8], edx
0x18001b10c  push    rbp
0x18001b10d  push    rbx
0x18001b10e  push    rsi
0x18001b10f  push    rdi
0x18001b110  push    r12
0x18001b112  push    r14
0x18001b114  push    r15
0x18001b116  mov     rbp, rsp
0x18001b119  sub     rsp, 80h
0x18001b120  mov     rdi, r8
0x18001b123  mov     r14, rcx
0x18001b126  mov     [rbp+var_18], rcx
0x18001b12a  mov     [rbp+var_10], 1
0x18001b12e  xor     r12d, r12d
0x18001b131  mov     [rbp+arg_10], r12
0x18001b135  mov     rax, [r8]
0x18001b138  mov     rbx, [rax+40h]
0x18001b13c  lea     rcx, [rbp+arg_10]
0x18001b140  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001b145  lea     rdx, [rbp+arg_10]
0x18001b149  mov     rcx, rdi
0x18001b14c  mov     rax, rbx
0x18001b14f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b154  mov     ebx, eax
0x18001b156  test    eax, eax
0x18001b158  jns     short loc_18001B1B6
0x18001b15a  mov     rcx, [rbp+38h]; this
0x18001b15e  mov     r9d, eax; char *
0x18001b161  lea     r8, aShellcommonPri; "ShellCommon\\private\\Shell\\inc\\token"...
0x18001b168  mov     edx, 121h; void *
0x18001b16d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b172  nop
0x18001b173  lea     rcx, [rbp+arg_10]
0x18001b177  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001b17c  nop
0x18001b17d  mov     rdx, [r14]
0x18001b180  add     rdx, 0E8h
0x18001b187  lea     rcx, [rbp+SRWLock]
0x18001b18b  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x18001b190  mov     rcx, [rbp+SRWLock]; SRWLock
0x18001b194  mov     rax, [r14]
0x18001b197  mov     [rax+0F1h], r12b
0x18001b19e  test    rcx, rcx
0x18001b1a1  jz      short loc_18001B1AF
0x18001b1a3  call    cs:__imp_ReleaseSRWLockExclusive
0x18001b1aa  nop     dword ptr [rax+rax+00h]
0x18001b1af  mov     eax, ebx
0x18001b1b1  jmp     loc_18001B7C9
0x18001b1b6  mov     [rbp+arg_0], r12
0x18001b1ba  mov     rdi, [rbp+arg_10]
0x18001b1be  mov     rax, [rdi]
0x18001b1c1  mov     rbx, [rax+30h]
0x18001b1c5  lea     rcx, [rbp+arg_0]
0x18001b1c9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001b1ce  lea     rdx, [rbp+arg_0]
0x18001b1d2  mov     rcx, rdi
0x18001b1d5  mov     rax, rbx
0x18001b1d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b1dd  mov     ebx, eax
0x18001b1df  test    eax, eax
0x18001b1e1  jns     short loc_18001B20A
0x18001b1e3  mov     rcx, [rbp+38h]; this
0x18001b1e7  mov     r9d, eax; char *
0x18001b1ea  lea     r8, aShellcommonPri; "ShellCommon\\private\\Shell\\inc\\token"...
0x18001b1f1  mov     edx, 123h; void *
0x18001b1f6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b1fb  nop
0x18001b1fc  lea     rcx, [rbp+arg_0]
0x18001b200  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001b205  jmp     loc_18001B173
0x18001b20a  mov     rdi, [r14]
0x18001b20d  mov     rbx, [rbp+arg_0]
0x18001b211  cmp     [rdi+0F8h], rbx
0x18001b218  jz      short loc_18001B246
0x18001b21a  mov     [rbp+SRWLock], rbx
0x18001b21e  lea     rcx, [rbp+SRWLock]
0x18001b222  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x18001b227  mov     rax, [rdi+0F8h]
0x18001b22e  mov     [rbp+SRWLock], rax
0x18001b232  mov     [rdi+0F8h], rbx
0x18001b239  lea     rcx, [rbp+SRWLock]
0x18001b23d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001b242  mov     rbx, [rbp+arg_0]
0x18001b246  mov     r15d, 0E8h
0x18001b24c  test    rbx, rbx
0x18001b24f  jz      loc_18001B73B
0x18001b255  mov     [rbp+SRWLock], r12
0x18001b259  mov     rax, [rbx]
0x18001b25c  mov     rdi, [rax]
0x18001b25f  lea     rcx, [rbp+SRWLock]
0x18001b263  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001b268  lea     r8, [rbp+SRWLock]
0x18001b26c  lea     rdx, _GUID_7b56d6f8_990b_4eb5_94a7_5621f3a8b824
0x18001b273  mov     rcx, rbx
0x18001b276  mov     rax, rdi
0x18001b279  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b27e  mov     ebx, eax
0x18001b280  test    eax, eax
0x18001b282  jns     short loc_18001B2D2
0x18001b284  mov     rcx, [rbp+38h]; this
0x18001b288  mov     r9d, eax; char *
0x18001b28b  lea     r8, aShellcommonPri; "ShellCommon\\private\\Shell\\inc\\token"...
0x18001b292  lea     edx, [r15+41h]; void *
0x18001b296  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b29b  nop
0x18001b29c  lea     rcx, [rbp+SRWLock]
0x18001b2a0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001b2a5  nop
0x18001b2a6  lea     rcx, [rbp+arg_0]
0x18001b2aa  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001b2af  nop
0x18001b2b0  lea     rcx, [rbp+arg_10]
0x18001b2b4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001b2b9  nop
0x18001b2ba  mov     rdx, [r14]
0x18001b2bd  add     rdx, r15
0x18001b2c0  lea     rcx, [rbp+var_60]
0x18001b2c4  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x18001b2c9  mov     rcx, [rbp+var_60]
0x18001b2cd  jmp     loc_18001B194
0x18001b2d2  mov     rdx, [r14]
0x18001b2d5  add     rdx, r15
0x18001b2d8  lea     rcx, [rbp+var_58]
0x18001b2dc  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x18001b2e1  nop
0x18001b2e2  mov     rsi, [rbp+arg_0]
0x18001b2e6  mov     rax, [rsi]
0x18001b2e9  mov     rdi, [rax+38h]
0x18001b2ed  mov     rbx, [r14]
0x18001b2f0  mov     rcx, [rbx+100h]; string
0x18001b2f7  call    cs:__imp_WindowsDeleteString
0x18001b2fe  nop     dword ptr [rax+rax+00h]
0x18001b303  mov     [rbx+100h], r12
0x18001b30a  lea     rdx, [rbx+100h]
0x18001b311  mov     rcx, rsi
0x18001b314  mov     rax, rdi
0x18001b317  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b31c  mov     ebx, eax
0x18001b31e  test    eax, eax
0x18001b320  jns     short loc_18001B359
0x18001b322  mov     rcx, [rbp+38h]; this
0x18001b326  mov     r9d, eax; char *
0x18001b329  lea     r8, aShellcommonPri; "ShellCommon\\private\\Shell\\inc\\token"...
0x18001b330  mov     edx, 12Eh; void *
0x18001b335  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b33a  nop
0x18001b33b  mov     rcx, [rbp+var_58]; SRWLock
0x18001b33f  test    rcx, rcx
0x18001b342  jz      loc_18001B29C
0x18001b348  call    cs:__imp_ReleaseSRWLockExclusive
0x18001b34f  nop     dword ptr [rax+rax+00h]
0x18001b354  jmp     loc_18001B29C
0x18001b359  mov     rcx, [rbp+var_58]; SRWLock
0x18001b35d  test    rcx, rcx
0x18001b360  jz      short loc_18001B36E
0x18001b362  call    cs:__imp_ReleaseSRWLockExclusive
0x18001b369  nop     dword ptr [rax+rax+00h]
0x18001b36e  mov     [rbp+var_40], r12
0x18001b372  mov     rdi, [rbp+SRWLock]
0x18001b376  mov     rax, [rdi]
0x18001b379  mov     rbx, [rax+30h]
0x18001b37d  xor     ecx, ecx; string
0x18001b37f  call    cs:__imp_WindowsDeleteString
0x18001b386  nop     dword ptr [rax+rax+00h]
0x18001b38b  mov     [rbp+var_40], r12
0x18001b38f  lea     rdx, [rbp+var_40]
0x18001b393  mov     rcx, rdi
0x18001b396  mov     rax, rbx
0x18001b399  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b39e  mov     ebx, eax
0x18001b3a0  test    eax, eax
0x18001b3a2  jns     short loc_18001B3CB
0x18001b3a4  mov     rcx, [rbp+38h]; this
0x18001b3a8  mov     r9d, eax; char *
0x18001b3ab  lea     r8, aShellcommonPri; "ShellCommon\\private\\Shell\\inc\\token"...
0x18001b3b2  mov     edx, 133h; void *
0x18001b3b7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b3bc  nop
0x18001b3bd  lea     rcx, [rbp+var_40]; this
0x18001b3c1  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18001b3c6  jmp     loc_18001B29C
0x18001b3cb  mov     [rbp+var_48], r12
0x18001b3cf  mov     rdi, [rbp+SRWLock]
0x18001b3d3  mov     rax, [rdi]
0x18001b3d6  mov     rbx, [rax+38h]
0x18001b3da  lea     rcx, [rbp+var_48]
0x18001b3de  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001b3e3  lea     rdx, [rbp+var_48]
0x18001b3e7  mov     rcx, rdi
0x18001b3ea  mov     rax, rbx
0x18001b3ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b3f2  mov     ebx, eax
0x18001b3f4  test    eax, eax
0x18001b3f6  jns     short loc_18001B41C
0x18001b3f8  mov     rcx, [rbp+38h]; this
0x18001b3fc  mov     r9d, eax; char *
0x18001b3ff  lea     r8, aShellcommonPri; "ShellCommon\\private\\Shell\\inc\\token"...
0x18001b406  mov     edx, 136h; void *
0x18001b40b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b410  nop
0x18001b411  lea     rcx, [rbp+var_48]
0x18001b415  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001b41a  jmp     short loc_18001B3BD
0x18001b41c  mov     [rbp+var_28], r12
0x18001b420  mov     rbx, [rbp+var_48]
0x18001b424  mov     rax, [rbx]
0x18001b427  mov     rdi, [rax]
0x18001b42a  lea     rcx, [rbp+var_28]
0x18001b42e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001b433  lea     r8, [rbp+var_28]
0x18001b437  lea     rdx, _GUID_e9bdaaf0_cbf6_5c72_be90_29cbf3a1319b
0x18001b43e  mov     rcx, rbx
0x18001b441  mov     rax, rdi
0x18001b444  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b449  mov     ebx, eax
0x18001b44b  test    eax, eax
0x18001b44d  jns     short loc_18001B473
0x18001b44f  mov     rcx, [rbp+38h]; this
0x18001b453  mov     r9d, eax; char *
0x18001b456  lea     r8, aShellcommonPri; "ShellCommon\\private\\Shell\\inc\\token"...
0x18001b45d  mov     edx, 138h; void *
0x18001b462  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b467  nop
0x18001b468  lea     rcx, [rbp+var_28]
0x18001b46c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001b471  jmp     short loc_18001B411
0x18001b473  mov     [rbp+var_50], r12
0x18001b477  mov     rdi, [rbp+var_28]
0x18001b47b  mov     rax, [rdi]
0x18001b47e  mov     rbx, [rax+30h]
0x18001b482  lea     rcx, [rbp+var_50]
0x18001b486  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001b48b  lea     rdx, [rbp+var_50]
0x18001b48f  mov     rcx, rdi
0x18001b492  mov     rax, rbx
0x18001b495  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b49a  mov     ebx, eax
0x18001b49c  test    eax, eax
0x18001b49e  jns     short loc_18001B4C4
0x18001b4a0  mov     rcx, [rbp+38h]; this
0x18001b4a4  mov     r9d, eax; char *
0x18001b4a7  lea     r8, aShellcommonPri; "ShellCommon\\private\\Shell\\inc\\token"...
0x18001b4ae  mov     edx, 13Ah; void *
0x18001b4b3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b4b8  nop
0x18001b4b9  lea     rcx, [rbp+var_50]
0x18001b4bd  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001b4c2  jmp     short loc_18001B468
0x18001b4c4  mov     byte ptr [rbp+arg_8], r12b
0x18001b4c8  mov     rcx, [rbp+var_50]
0x18001b4cc  mov     rax, [rcx]
0x18001b4cf  lea     rdx, [rbp+arg_8]
0x18001b4d3  mov     rax, [rax+38h]
0x18001b4d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b4dc  test    eax, eax
0x18001b4de  jnz     loc_18001B70A
0x18001b4e4  cmp     byte ptr [rbp+arg_8], r12b
0x18001b4e8  jz      loc_18001B70A
0x18001b4ee  mov     [rbp+var_58], r12
0x18001b4f2  mov     rdi, [rbp+var_50]
0x18001b4f6  mov     rax, [rdi]
0x18001b4f9  mov     rbx, [rax+30h]
0x18001b4fd  lea     rcx, [rbp+var_58]
0x18001b501  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001b506  lea     rdx, [rbp+var_58]
0x18001b50a  mov     rcx, rdi
0x18001b50d  mov     rax, rbx
0x18001b510  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b515  mov     ebx, eax
0x18001b517  test    eax, eax
0x18001b519  js      loc_18001B689
0x18001b51f  mov     [rbp+var_30], r12
0x18001b523  mov     rdi, [rbp+var_58]
0x18001b527  mov     rax, [rdi]
0x18001b52a  mov     rbx, [rax+30h]
0x18001b52e  xor     ecx, ecx; string
0x18001b530  call    cs:__imp_WindowsDeleteString
0x18001b537  nop     dword ptr [rax+rax+00h]
0x18001b53c  mov     [rbp+var_30], r12
0x18001b540  lea     rdx, [rbp+var_30]
0x18001b544  mov     rcx, rdi
0x18001b547  mov     rax, rbx
0x18001b54a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b54f  mov     [rbp+string], r12
0x18001b553  mov     rdi, [rbp+var_58]
0x18001b557  mov     rax, [rdi]
0x18001b55a  mov     rbx, [rax+38h]
0x18001b55e  xor     ecx, ecx; string
0x18001b560  call    cs:__imp_WindowsDeleteString
0x18001b567  nop     dword ptr [rax+rax+00h]
0x18001b56c  mov     [rbp+string], r12
0x18001b570  lea     rdx, [rbp+string]
0x18001b574  mov     rcx, rdi
0x18001b577  mov     rax, rbx
0x18001b57a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b57f  mov     rdx, [r14]
0x18001b582  add     rdx, r15
0x18001b585  lea     rcx, [rbp+var_60]
0x18001b589  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
  ... truncated ...
```
