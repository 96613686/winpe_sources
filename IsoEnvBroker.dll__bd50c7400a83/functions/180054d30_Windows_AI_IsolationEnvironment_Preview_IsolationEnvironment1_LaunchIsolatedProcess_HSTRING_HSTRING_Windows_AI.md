# Windows::AI::IsolationEnvironment::Preview::IsolationEnvironment1::LaunchIsolatedProcess(HSTRING__ *,HSTRING__ *,Windows::AI::IsolationEnvironment::Preview::IIsolationProcessCreationResult_Exp * *)

- ea: `0x180054d30`
- end: `0x1800550c6`
- name: `?LaunchIsolatedProcess@IsolationEnvironment1@Preview@IsolationEnvironment@AI@Windows@@UEAAJPEAUHSTRING__@@0PEAPEAUIIsolationProcessCreationResult_Exp@2345@@Z`
- size: `918`
- prototype: `__int64 __fastcall(Windows::AI::IsolationEnvironment::Preview::IsolationEnvironment1 *__hidden this, HSTRING string, HSTRING, struct Windows::AI::IsolationEnvironment::Preview::IIsolationProcessCreationResult_Exp **)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180002a30`
- `0x18000a464`
- `0x1800134e8`
- `0x180034d48`
- `0x180054408`
- `0x180054804`
- `0x180054d30`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180054d97`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180055090`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800550a7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180054d97`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180055090`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800550a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054e36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054f09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054e36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054f09`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180054e49`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180054f1c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180054e49`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180054f1c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180054e41`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180054f14`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180054f64`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180054fd6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005507d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180054e41`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180054f14`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180054f64`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180054fd6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005507d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180054f47`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180054f47`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180054f56`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180054f56`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180054da9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180054df3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180054da9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180054df3`

## string_xrefs

- `0x180054d7a`: `onecoreuap\windows\core\isoenvbroker\lib\v1\isolationenvironment.cpp`
- `0x180054fa1`: `onecoreuap\windows\core\isoenvbroker\lib\v1\isolationenvironment.cpp`
- `0x18005500f`: `onecoreuap\windows\core\isoenvbroker\lib\v1\isolationenvironment.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::AI::IsolationEnvironment::Preview::IsolationEnvironment1::LaunchIsolatedProcess(
        Windows::AI::IsolationEnvironment::Preview::IsolationEnvironment1 *this,
        HSTRING string,
        HSTRING a3,
        struct Windows::AI::IsolationEnvironment::Preview::IIsolationProcessCreationResult_Exp **a4)
{
  struct Windows::AI::IsolationEnvironment::Preview::IIsolationProcessCreationResult_Exp **v4; // r13
  int v8; // ebx
  RTL_SRWLOCK *v9; // rcx
  PCWSTR StringRawBuffer; // rax
  const wchar_t *v12; // rbx
  __int64 v13; // rcx
  wchar_t *v14; // rax
  void *v15; // r14
  HANDLE *v16; // rdi
  HANDLE v17; // rsi
  DWORD LastError; // ebx
  _QWORD *v19; // rax
  _QWORD *v20; // rsi
  HSTRING *v21; // r14
  void **v22; // r15
  HANDLE v23; // rbx
  void *v24; // r13
  DWORD v25; // edi
  int v26; // eax
  struct Windows::AI::IsolationEnvironment::Preview::IIsolationProcessCreationResult_Exp *v27; // rax
  RTL_SRWLOCK *v28; // rcx
  RTL_SRWLOCK *v29; // rcx
  int v30; // [rsp+20h] [rbp-59h]
  int v31; // [rsp+20h] [rbp-59h]
  HANDLE hObject; // [rsp+30h] [rbp-49h] BYREF
  int v33; // [rsp+38h] [rbp-41h] BYREF
  __int64 v34; // [rsp+40h] [rbp-39h] BYREF
  PSRWLOCK SRWLock; // [rsp+48h] [rbp-31h] BYREF
  unsigned int v36[2]; // [rsp+50h] [rbp-29h] BYREF
  struct Windows::AI::IsolationEnvironment::Preview::IIsolationProcessCreationResult_Exp *v37; // [rsp+58h] [rbp-21h] BYREF
  int v38; // [rsp+60h] [rbp-19h] BYREF
  HANDLE *p_hObject; // [rsp+68h] [rbp-11h]
  void *v40; // [rsp+70h] [rbp-9h] BYREF
  char v41; // [rsp+78h] [rbp-1h]
  char v42; // [rsp+80h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v4 = a4;
  checked_srwlock::lock_exclusive(this, &SRWLock);
  if ( !ProblematicAdminCheck() )
  {
    v8 = -2147024891;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x45,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\v1\\isolationenvironment.cpp",
      (const char *)0x80070005LL,
      v30);
LABEL_3:
    v9 = SRWLock;
    if ( SRWLock )
    {
      LODWORD(SRWLock[1].Ptr) = 0;
      ReleaseSRWLockExclusive(v9);
    }
    return (unsigned int)v8;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  v12 = StringRawBuffer;
  if ( !StringRawBuffer )
    goto LABEL_45;
  v13 = -1;
  do
    ++v13;
  while ( StringRawBuffer[v13] );
  if ( v13 )
  {
    hObject = 0;
    v36[0] = 0;
    v33 = 0;
    p_hObject = &hObject;
    v40 = 0;
    v41 = 1;
    v14 = (wchar_t *)WindowsGetStringRawBuffer(a3, 0);
    v38 = Windows::AI::IsolationEnvironment::Preview::IsolationEnvironment1::CreateWorkerProcess(
            this,
            v12,
            v14,
            &v40,
            v36,
            (enum Windows::AI::IsolationEnvironment::Preview::IsolationProcessCreationStatus_Exp *)&v33);
    if ( v41 )
    {
      v15 = v40;
      v16 = p_hObject;
      v17 = *p_hObject;
      if ( *p_hObject )
      {
        LastError = GetLastError();
        CloseHandle(v17);
        SetLastError(LastError);
      }
      *v16 = v15;
    }
    v34 = 0;
    v19 = operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
    v20 = v19;
    if ( !v19 )
    {
      v8 = -2147024882;
LABEL_28:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5E,
        (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\v1\\isolationenvironment.cpp",
        (const char *)(unsigned int)v8,
        v31);
      if ( v34 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
LABEL_30:
      if ( hObject )
        CloseHandle(hObject);
      goto LABEL_3;
    }
    v19[4] = 1;
    *v19 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::AI::IsolationEnvironment::Preview::IIsolationWorkerProcess_Exp,Windows::Foundation::IClosable>::`vftable';
    v19[1] = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::AI::IsolationEnvironment::Preview::IIsolationWorkerProcess_Exp,Windows::Foundation::IClosable>::`vftable'{for `IWeakReferenceSource'};
    v19[2] = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::AI::IsolationEnvironment::Preview::IIsolationWorkerProcess_Exp,Windows::Foundation::IClosable>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Windows::Foundation::IClosable>'};
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_ + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *v20 = &Windows::AI::IsolationEnvironment::Preview::WorkerProcess1::`vftable';
    v20[1] = &Windows::AI::IsolationEnvironment::Preview::WorkerProcess1::`vftable'{for `IWeakReferenceSource'};
    v20[2] = &Windows::AI::IsolationEnvironment::Preview::WorkerProcess1::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Windows::Foundation::IClosable>'};
    v21 = (HSTRING *)(v20 + 5);
    v20[5] = 0;
    v22 = (void **)(v20 + 7);
    v20[7] = 0;
    v23 = hObject;
    hObject = 0;
    if ( v20 + 7 != (_QWORD *)&v42 )
    {
      v24 = *v22;
      if ( *v22 )
      {
        v25 = GetLastError();
        CloseHandle(v24);
        SetLastError(v25);
      }
      *v22 = v23;
      v23 = 0;
      v4 = a4;
    }
    *((_DWORD *)v20 + 12) = v36[0];
    if ( !string || string != *v21 )
    {
      WindowsDeleteString(*v21);
      *v21 = 0;
      WindowsDuplicateString(string, (HSTRING *)v20 + 5);
    }
    if ( v23 )
      CloseHandle(v23);
    v8 = (*(__int64 (__fastcall **)(_QWORD *, GUID *, __int64 *))*v20)(
           v20,
           &GUID_44a1b74d_7fbb_5f27_aaee_e470474e325f,
           &v34);
    (*(void (__fastcall **)(_QWORD *))(*v20 + 16LL))(v20);
    if ( v8 < 0 )
      goto LABEL_28;
    *(_QWORD *)v36 = v34;
    v37 = 0;
    v26 = Microsoft::WRL::Details::MakeAndInitialize<Windows::AI::IsolationEnvironment::Preview::ProcessCreationResult1,Windows::AI::IsolationEnvironment::Preview::IIsolationProcessCreationResult_Exp,Windows::AI::IsolationEnvironment::Preview::IIsolationWorkerProcess_Exp *,enum Windows::AI::IsolationEnvironment::Preview::IsolationProcessCreationStatus_Exp &,long &>(
            &v37,
            v36,
            &v33,
            &v38);
    v8 = v26;
    if ( v26 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x65,
        (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\v1\\isolationenvironment.cpp",
        (const char *)(unsigned int)v26,
        v31);
      if ( v37 )
        (*(void (__fastcall **)(struct Windows::AI::IsolationEnvironment::Preview::IIsolationProcessCreationResult_Exp *))(*(_QWORD *)v37 + 16LL))(v37);
      if ( v34 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
      goto LABEL_30;
    }
    v27 = v37;
    v37 = 0;
    *v4 = v27;
    if ( v34 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
    if ( hObject )
      CloseHandle(hObject);
    v28 = SRWLock;
    if ( SRWLock )
    {
      LODWORD(SRWLock[1].Ptr) = 0;
      ReleaseSRWLockExclusive(v28);
    }
    return 0;
  }
  else
  {
LABEL_45:
    v29 = SRWLock;
    if ( SRWLock )
    {
      LODWORD(SRWLock[1].Ptr) = 0;
      ReleaseSRWLockExclusive(v29);
    }
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x180054d30  mov     [rsp-8+arg_18], r9
0x180054d35  push    rbp
0x180054d36  push    rbx
0x180054d37  push    rsi
0x180054d38  push    rdi
0x180054d39  push    r12
0x180054d3b  push    r13
0x180054d3d  push    r14
0x180054d3f  push    r15
0x180054d41  lea     rbp, [rsp-1Fh]
0x180054d46  sub     rsp, 98h
0x180054d4d  mov     r13, r9
0x180054d50  mov     rdi, r8
0x180054d53  mov     r12, rdx
0x180054d56  mov     rsi, rcx
0x180054d59  lea     rdx, [rbp+57h+SRWLock]
0x180054d5d  call    ?lock_exclusive@checked_srwlock@@QEAA?AV?$holder@UExclusiveTag@checked_srwlock@@UAcquireTag@2@$0A@@1@XZ; checked_srwlock::lock_exclusive(void)
0x180054d62  call    _ProblematicAdminCheck
0x180054d67  xor     r15d, r15d
0x180054d6a  test    al, al
0x180054d6c  jnz     short loc_180054DA4
0x180054d6e  mov     rcx, [rbp+5Fh]; this
0x180054d72  mov     ebx, 80070005h
0x180054d77  mov     r9d, ebx; char *
0x180054d7a  lea     r8, aOnecoreuapWind_21; "onecoreuap\\windows\\core\\isoenvbroker"...
0x180054d81  lea     edx, [r15+45h]; void *
0x180054d85  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180054d8a  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x180054d8e  test    rcx, rcx
0x180054d91  jz      short loc_180054D9D
0x180054d93  mov     [rcx+8], r15d
0x180054d97  call    cs:__imp_ReleaseSRWLockExclusive
0x180054d9d  mov     eax, ebx
0x180054d9f  jmp     loc_1800550B2
0x180054da4  xor     edx, edx; length
0x180054da6  mov     rcx, r12; string
0x180054da9  call    cs:__imp_WindowsGetStringRawBuffer
0x180054daf  mov     rbx, rax
0x180054db2  test    rax, rax
0x180054db5  jz      loc_18005509A
0x180054dbb  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180054dbf  inc     rcx
0x180054dc2  cmp     [rax+rcx*2], r15w
0x180054dc7  jnz     short loc_180054DBF
0x180054dc9  test    rcx, rcx
0x180054dcc  jz      loc_18005509A
0x180054dd2  mov     [rbp+57h+hObject], r15
0x180054dd6  mov     [rbp+57h+var_80], r15d
0x180054dda  mov     [rbp+57h+var_98], r15d
0x180054dde  lea     rax, [rbp+57h+hObject]
0x180054de2  mov     [rbp+57h+var_68], rax
0x180054de6  mov     [rbp+57h+var_60], r15
0x180054dea  mov     [rbp+57h+var_58], 1
0x180054dee  xor     edx, edx; length
0x180054df0  mov     rcx, rdi; string
0x180054df3  call    cs:__imp_WindowsGetStringRawBuffer
0x180054df9  lea     rcx, [rbp+57h+var_98]
0x180054dfd  mov     [rsp+0D0h+var_A8], rcx; enum Windows::AI::IsolationEnvironment::Preview::IsolationProcessCreationStatus_Exp *
0x180054e02  lea     rcx, [rbp+57h+var_80]
0x180054e06  mov     [rsp+0D0h+var_B0], rcx; int
0x180054e0b  lea     r9, [rbp+57h+var_60]; void **
0x180054e0f  mov     r8, rax; wchar_t *
0x180054e12  mov     rdx, rbx; wchar_t *
0x180054e15  mov     rcx, rsi; this
0x180054e18  call    ?CreateWorkerProcess@IsolationEnvironment1@Preview@IsolationEnvironment@AI@Windows@@AEAAJPEB_WPEA_WPEAPEAXPEAKPEAW4IsolationProcessCreationStatus_Exp@2345@@Z; Windows::AI::IsolationEnvironment::Preview::IsolationEnvironment1::CreateWorkerProcess(wchar_t const *,wchar_t *,void * *,ulong *,Windows::AI::IsolationEnvironment::Preview::IsolationProcessCreationStatus_Exp *)
0x180054e1d  mov     [rbp+57h+var_70], eax
0x180054e20  cmp     [rbp+57h+var_58], r15b
0x180054e24  jz      short loc_180054E52
0x180054e26  mov     r14, [rbp+57h+var_60]
0x180054e2a  mov     rdi, [rbp+57h+var_68]
0x180054e2e  mov     rsi, [rdi]
0x180054e31  test    rsi, rsi
0x180054e34  jz      short loc_180054E4F
0x180054e36  call    cs:__imp_GetLastError
0x180054e3c  mov     ebx, eax
0x180054e3e  mov     rcx, rsi; hObject
0x180054e41  call    cs:__imp_CloseHandle
0x180054e47  mov     ecx, ebx; dwErrCode
0x180054e49  call    cs:__imp_SetLastError
0x180054e4f  mov     [rdi], r14
0x180054e52  mov     [rbp+57h+var_90], r15
0x180054e56  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180054e5d  mov     ecx, 40h ; '@'; unsigned __int64
0x180054e62  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180054e67  mov     rsi, rax
0x180054e6a  test    rax, rax
0x180054e6d  jnz     short loc_180054E79
0x180054e6f  mov     ebx, 8007000Eh
0x180054e74  jmp     loc_180054F9A
0x180054e79  mov     qword ptr [rax+20h], 1
0x180054e81  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIIsolationWorkerProcess_Exp@Preview@IsolationEnvironment@AI@Windows@@UIClosable@Foundation@8@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::AI::IsolationEnvironment::Preview::IIsolationWorkerProcess_Exp,Windows::Foundation::IClosable>::`vftable'
0x180054e88  mov     [rsi], rax
0x180054e8b  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIIsolationWorkerProcess_Exp@Preview@IsolationEnvironment@AI@Windows@@UIClosable@Foundation@8@@WRL@Microsoft@@6BIWeakReferenceSource@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::AI::IsolationEnvironment::Preview::IIsolationWorkerProcess_Exp,Windows::Foundation::IClosable>::`vftable'{for `IWeakReferenceSource'}
0x180054e92  mov     [rsi+8], rax
0x180054e96  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIIsolationWorkerProcess_Exp@Preview@IsolationEnvironment@AI@Windows@@UIClosable@Foundation@8@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIClosable@Foundation@Windows@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,Windows::AI::IsolationEnvironment::Preview::IIsolationWorkerProcess_Exp,Windows::Foundation::IClosable>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Windows::Foundation::IClosable>'}
0x180054e9d  mov     [rsi+10h], rax
0x180054ea1  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180054ea8  test    rcx, rcx
0x180054eab  jz      short loc_180054EBA
0x180054ead  mov     rax, [rcx]
0x180054eb0  mov     rax, [rax+8]
0x180054eb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054eb9  nop
0x180054eba  lea     rax, ??_7WorkerProcess1@Preview@IsolationEnvironment@AI@Windows@@6B@; const Windows::AI::IsolationEnvironment::Preview::WorkerProcess1::`vftable'
0x180054ec1  mov     [rsi], rax
0x180054ec4  lea     rax, ??_7WorkerProcess1@Preview@IsolationEnvironment@AI@Windows@@6BIWeakReferenceSource@@@; const Windows::AI::IsolationEnvironment::Preview::WorkerProcess1::`vftable'{for `IWeakReferenceSource'}
0x180054ecb  mov     [rsi+8], rax
0x180054ecf  lea     rax, ??_7WorkerProcess1@Preview@IsolationEnvironment@AI@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIClosable@Foundation@Windows@@@Details@WRL@Microsoft@@@; const Windows::AI::IsolationEnvironment::Preview::WorkerProcess1::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Windows::Foundation::IClosable>'}
0x180054ed6  mov     [rsi+10h], rax
0x180054eda  lea     r14, [rsi+28h]
0x180054ede  mov     [r14], r15
0x180054ee1  lea     r15, [rsi+38h]
0x180054ee5  mov     qword ptr [r15], 0
0x180054eec  mov     rbx, [rbp+57h+hObject]
0x180054ef0  mov     [rbp+57h+hObject], 0
0x180054ef8  lea     rax, [rbp+57h+var_50]
0x180054efc  cmp     r15, rax
0x180054eff  jz      short loc_180054F31
0x180054f01  mov     r13, [r15]
0x180054f04  test    r13, r13
0x180054f07  jz      short loc_180054F22
0x180054f09  call    cs:__imp_GetLastError
0x180054f0f  mov     edi, eax
0x180054f11  mov     rcx, r13; hObject
0x180054f14  call    cs:__imp_CloseHandle
0x180054f1a  mov     ecx, edi; dwErrCode
0x180054f1c  call    cs:__imp_SetLastError
0x180054f22  mov     [r15], rbx
0x180054f25  xor     r15d, r15d
0x180054f28  mov     ebx, r15d
0x180054f2b  mov     r13, [rbp+57h+arg_18]
0x180054f2f  jmp     short loc_180054F34
0x180054f31  xor     r15d, r15d
0x180054f34  mov     eax, [rbp+57h+var_80]
0x180054f37  mov     [rsi+30h], eax
0x180054f3a  test    r12, r12
0x180054f3d  jz      short loc_180054F44
0x180054f3f  cmp     r12, [r14]
0x180054f42  jz      short loc_180054F5C
0x180054f44  mov     rcx, [r14]; string
0x180054f47  call    cs:__imp_WindowsDeleteString
0x180054f4d  mov     [r14], r15
0x180054f50  mov     rdx, r14; newString
0x180054f53  mov     rcx, r12; string
0x180054f56  call    cs:__imp_WindowsDuplicateString
0x180054f5c  test    rbx, rbx
0x180054f5f  jz      short loc_180054F6B
0x180054f61  mov     rcx, rbx; hObject
0x180054f64  call    cs:__imp_CloseHandle
0x180054f6a  nop
0x180054f6b  mov     rax, [rsi]
0x180054f6e  lea     r8, [rbp+57h+var_90]
0x180054f72  lea     rdx, _GUID_44a1b74d_7fbb_5f27_aaee_e470474e325f
0x180054f79  mov     rcx, rsi
0x180054f7c  mov     rax, [rax]
0x180054f7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054f84  mov     ebx, eax
0x180054f86  mov     rax, [rsi]
0x180054f89  mov     rcx, rsi
0x180054f8c  mov     rax, [rax+10h]
0x180054f90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054f95  nop
0x180054f96  test    ebx, ebx
0x180054f98  jns     short loc_180054FE1
0x180054f9a  mov     rcx, [rbp+5Fh]; this
0x180054f9e  mov     r9d, ebx; char *
0x180054fa1  lea     r8, aOnecoreuapWind_21; "onecoreuap\\windows\\core\\isoenvbroker"...
0x180054fa8  mov     edx, 5Eh ; '^'; void *
0x180054fad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180054fb2  nop
0x180054fb3  mov     rcx, [rbp+57h+var_90]
0x180054fb7  test    rcx, rcx
0x180054fba  jz      short loc_180054FC9
0x180054fbc  mov     rax, [rcx]
0x180054fbf  mov     rax, [rax+10h]
0x180054fc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054fc8  nop
0x180054fc9  mov     rcx, [rbp+57h+hObject]; hObject
0x180054fcd  test    rcx, rcx
0x180054fd0  jz      loc_180054D8A
0x180054fd6  call    cs:__imp_CloseHandle
0x180054fdc  jmp     loc_180054D8A
0x180054fe1  mov     rax, [rbp+57h+var_90]
0x180054fe5  mov     qword ptr [rbp+57h+var_80], rax
0x180054fe9  mov     [rbp+57h+var_78], r15
0x180054fed  lea     r9, [rbp+57h+var_70]
0x180054ff1  lea     r8, [rbp+57h+var_98]
0x180054ff5  lea     rdx, [rbp+57h+var_80]
0x180054ff9  lea     rcx, [rbp+57h+var_78]
0x180054ffd  call    ??$MakeAndInitialize@VProcessCreationResult1@Preview@IsolationEnvironment@AI@Windows@@UIIsolationProcessCreationResult_Exp@2345@PEAUIIsolationWorkerProcess_Exp@2345@AEAW4IsolationProcessCreationStatus_Exp@2345@AEAJ@Details@WRL@Microsoft@@YAJPEAPEAUIIsolationProcessCreationResult_Exp@Preview@IsolationEnvironment@AI@Windows@@$$QEAPEAUIIsolationWorkerProcess_Exp@4567@AEAW4IsolationProcessCreationStatus_Exp@4567@AEAJ@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::AI::IsolationEnvironment::Preview::ProcessCreationResult1,Windows::AI::IsolationEnvironment::Preview::IIsolationProcessCreationResult_Exp,Windows::AI::IsolationEnvironment::Preview::IIsolationWorkerProcess_Exp *,Windows::AI::IsolationEnvironment::Preview::IsolationProcessCreationStatus_Exp &,long &>(Windows::AI::IsolationEnvironment::Preview::IIsolationProcessCreationResult_Exp * *,Windows::AI::IsolationEnvironment::Preview::IIsolationWorkerProcess_Exp * &&,Windows::AI::IsolationEnvironment::Preview::IsolationProcessCreationStatus_Exp &,long &)
0x180055002  mov     ebx, eax
0x180055004  test    eax, eax
0x180055006  jns     short loc_180055052
0x180055008  mov     rcx, [rbp+5Fh]; this
0x18005500c  mov     r9d, eax; char *
0x18005500f  lea     r8, aOnecoreuapWind_21; "onecoreuap\\windows\\core\\isoenvbroker"...
0x180055016  mov     edx, 65h ; 'e'; void *
0x18005501b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180055020  nop
0x180055021  mov     rcx, [rbp+57h+var_78]
0x180055025  test    rcx, rcx
0x180055028  jz      short loc_180055037
0x18005502a  mov     rax, [rcx]
0x18005502d  mov     rax, [rax+10h]
0x180055031  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055036  nop
0x180055037  mov     rcx, [rbp+57h+var_90]
0x18005503b  test    rcx, rcx
0x18005503e  jz      short loc_18005504D
0x180055040  mov     rax, [rcx]
0x180055043  mov     rax, [rax+10h]
0x180055047  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005504c  nop
0x18005504d  jmp     loc_180054FC9
0x180055052  mov     rax, [rbp+57h+var_78]
0x180055056  mov     [rbp+57h+var_78], r15
0x18005505a  mov     [r13+0], rax
0x18005505e  mov     rcx, [rbp+57h+var_90]
0x180055062  test    rcx, rcx
0x180055065  jz      short loc_180055074
0x180055067  mov     rax, [rcx]
0x18005506a  mov     rax, [rax+10h]
0x18005506e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055073  nop
0x180055074  mov     rcx, [rbp+57h+hObject]; hObject
0x180055078  test    rcx, rcx
0x18005507b  jz      short loc_180055083
0x18005507d  call    cs:__imp_CloseHandle
0x180055083  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x180055087  test    rcx, rcx
0x18005508a  jz      short loc_180055096
0x18005508c  mov     [rcx+8], r15d
0x180055090  call    cs:__imp_ReleaseSRWLockExclusive
0x180055096  xor     eax, eax
0x180055098  jmp     short loc_1800550B2
0x18005509a  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18005509e  test    rcx, rcx
0x1800550a1  jz      short loc_1800550AD
0x1800550a3  mov     [rcx+8], r15d
0x1800550a7  call    cs:__imp_ReleaseSRWLockExclusive
0x1800550ad  mov     eax, 80070057h
0x1800550b2  add     rsp, 98h
0x1800550b9  pop     r15
0x1800550bb  pop     r14
0x1800550bd  pop     r13
0x1800550bf  pop     r12
0x1800550c1  pop     rdi
0x1800550c2  pop     rsi
0x1800550c3  pop     rbx
0x1800550c4  pop     rbp
0x1800550c5  retn
```
