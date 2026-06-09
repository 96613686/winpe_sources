# Windows::AI::IsolationEnvironment::IsolationEnvironment::LaunchIsolatedProcess(HSTRING__ *,HSTRING__ *,Windows::AI::IsolationEnvironment::IIsolationProcessCreationResult * *)

- ea: `0x180049e70`
- end: `0x18004a11d`
- name: `?LaunchIsolatedProcess@IsolationEnvironment@1AI@Windows@@UEAAJPEAUHSTRING__@@0PEAPEAUIIsolationProcessCreationResult@123@@Z`
- size: `685`
- prototype: `__int64 __fastcall(Windows::AI::IsolationEnvironment::IsolationEnvironment *__hidden this, HSTRING string, HSTRING, struct Windows::AI::IsolationEnvironment::IIsolationProcessCreationResult **)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000a464`
- `0x180013230`
- `0x1800134e8`
- `0x180032e60`
- `0x180048870`
- `0x18004896c`
- `0x180048edc`
- `0x180049024`
- `0x180049e70`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180049f11`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004a0e7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004a0fe`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180049f11`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004a0e7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004a0fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049fae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049fae`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180049fc1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180049fc1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180049fb9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004a02d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004a0d4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180049fb9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004a02d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004a0d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180049f1e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180049f68`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180049f1e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180049f68`

## string_xrefs

- `0x180049ebe`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\isolationenvironment.cpp`
- `0x180049ef3`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\isolationenvironment.cpp`
- `0x180049ff8`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\isolationenvironment.cpp`
- `0x18004a066`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\isolationenvironment.cpp`

## pseudocode

```c
__int64 __fastcall Windows::AI::IsolationEnvironment::IsolationEnvironment::LaunchIsolatedProcess(
        Windows::AI::IsolationEnvironment::IsolationEnvironment *this,
        HSTRING string,
        HSTRING a3,
        struct Windows::AI::IsolationEnvironment::IIsolationProcessCreationResult **a4)
{
  __int64 v8; // rcx
  unsigned int v9; // ebx
  int v11; // eax
  RTL_SRWLOCK *v12; // rcx
  PCWSTR StringRawBuffer; // rax
  const wchar_t *v14; // rbx
  __int64 v15; // rcx
  wchar_t *v16; // rax
  int v17; // r15d
  void *v18; // r14
  HANDLE *v19; // rdi
  HANDLE v20; // rsi
  DWORD LastError; // ebx
  __int64 v22; // rax
  int v23; // eax
  int v24; // eax
  struct Windows::AI::IsolationEnvironment::IIsolationProcessCreationResult *v25; // rax
  RTL_SRWLOCK *v26; // rcx
  RTL_SRWLOCK *v27; // rcx
  int v28; // [rsp+20h] [rbp-49h]
  int v29; // [rsp+20h] [rbp-49h]
  enum Windows::AI::IsolationEnvironment::IsolationProcessCreationStatus *v30; // [rsp+28h] [rbp-41h]
  int v31; // [rsp+30h] [rbp-39h] BYREF
  __int64 v32; // [rsp+38h] [rbp-31h] BYREF
  HANDLE hObject; // [rsp+40h] [rbp-29h] BYREF
  PSRWLOCK SRWLock; // [rsp+48h] [rbp-21h] BYREF
  unsigned int v35[2]; // [rsp+50h] [rbp-19h] BYREF
  struct Windows::AI::IsolationEnvironment::IIsolationProcessCreationResult *v36; // [rsp+58h] [rbp-11h] BYREF
  int v37; // [rsp+60h] [rbp-9h] BYREF
  HANDLE *p_hObject; // [rsp+68h] [rbp-1h]
  void *v39; // [rsp+70h] [rbp+7h] BYREF
  char v40; // [rsp+78h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]
  HSTRING v42; // [rsp+D8h] [rbp+6Fh] BYREF

  v42 = string;
  v9 = CheckCallingProcessCohort(0, 0);
  if ( (v9 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x5D,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\isolationenvironment.cpp",
      (const char *)v9,
      (int)"Calling user is not in a supported cohort",
      (const char *)v30);
    return v9;
  }
  checked_srwlock::lock_exclusive(v8, &SRWLock);
  v11 = Windows::AI::IsolationEnvironment::IsolationEnvironment::CheckEntry(this);
  v9 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x61,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\isolationenvironment.cpp",
      (const char *)(unsigned int)v11,
      v28);
LABEL_6:
    v12 = SRWLock;
    if ( SRWLock )
    {
      LODWORD(SRWLock[1].Ptr) = 0;
      ReleaseSRWLockExclusive(v12);
    }
    return v9;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  v14 = StringRawBuffer;
  if ( !StringRawBuffer )
    goto LABEL_36;
  v15 = -1;
  do
    ++v15;
  while ( StringRawBuffer[v15] );
  if ( v15 )
  {
    hObject = 0;
    v35[0] = 0;
    v31 = 0;
    p_hObject = &hObject;
    v39 = 0;
    v40 = 1;
    v16 = (wchar_t *)WindowsGetStringRawBuffer(a3, 0);
    v17 = Windows::AI::IsolationEnvironment::IsolationEnvironment::CreateWorkerProcess(
            this,
            v14,
            v16,
            &v39,
            v35,
            (enum Windows::AI::IsolationEnvironment::IsolationProcessCreationStatus *)&v31);
    v37 = v17;
    if ( v40 )
    {
      v18 = v39;
      v19 = p_hObject;
      v20 = *p_hObject;
      if ( *p_hObject )
      {
        LastError = GetLastError();
        CloseHandle(v20);
        SetLastError(LastError);
      }
      *v19 = v18;
    }
    v22 = 0;
    v32 = 0;
    if ( v17 >= 0 )
    {
      v23 = Microsoft::WRL::Details::MakeAndInitialize<Windows::AI::IsolationEnvironment::WorkerProcess,Windows::AI::IsolationEnvironment::IIsolationWorkerProcess,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>,unsigned long &,HSTRING__ * &>(
              &v32,
              &hObject,
              v35,
              &v42);
      v9 = v23;
      if ( v23 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x7A,
          (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\isolationenvironment.cpp",
          (const char *)(unsigned int)v23,
          v29);
        if ( v32 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
LABEL_20:
        if ( hObject )
          CloseHandle(hObject);
        goto LABEL_6;
      }
      v22 = v32;
    }
    *(_QWORD *)v35 = v22;
    v36 = 0;
    v24 = Microsoft::WRL::Details::MakeAndInitialize<Windows::AI::IsolationEnvironment::ProcessCreationResult,Windows::AI::IsolationEnvironment::IIsolationProcessCreationResult,Windows::AI::IsolationEnvironment::IIsolationWorkerProcess *,enum Windows::AI::IsolationEnvironment::IsolationProcessCreationStatus &,long &>(
            &v36,
            v35,
            &v31,
            &v37);
    v9 = v24;
    if ( v24 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x82,
        (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\isolationenvironment.cpp",
        (const char *)(unsigned int)v24,
        v29);
      if ( v36 )
        (*(void (__fastcall **)(struct Windows::AI::IsolationEnvironment::IIsolationProcessCreationResult *))(*(_QWORD *)v36 + 16LL))(v36);
      if ( v32 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
      goto LABEL_20;
    }
    v25 = v36;
    v36 = 0;
    *a4 = v25;
    if ( v32 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
    if ( hObject )
      CloseHandle(hObject);
    v26 = SRWLock;
    if ( SRWLock )
    {
      LODWORD(SRWLock[1].Ptr) = 0;
      ReleaseSRWLockExclusive(v26);
    }
    return 0;
  }
  else
  {
LABEL_36:
    v27 = SRWLock;
    if ( SRWLock )
    {
      LODWORD(SRWLock[1].Ptr) = 0;
      ReleaseSRWLockExclusive(v27);
    }
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x180049e70  mov     [rsp-8+arg_8], rdx
0x180049e75  push    rbp
0x180049e76  push    rbx
0x180049e77  push    rsi
0x180049e78  push    rdi
0x180049e79  push    r12
0x180049e7b  push    r13
0x180049e7d  push    r14
0x180049e7f  push    r15
0x180049e81  lea     rbp, [rsp-1Fh]
0x180049e86  sub     rsp, 88h
0x180049e8d  mov     r12, r9
0x180049e90  mov     r14, r8
0x180049e93  mov     rdi, rdx
0x180049e96  mov     rsi, rcx
0x180049e99  xor     edx, edx; enum Windows::AI::IsolationEnvironment::IsolationUserCohortKind *
0x180049e9b  xor     ecx, ecx; bool
0x180049e9d  call    ?CheckCallingProcessCohort@@YAJ_NPEAW4IsolationUserCohortKind@IsolationEnvironment@AI@Windows@@@Z; CheckCallingProcessCohort(bool,Windows::AI::IsolationEnvironment::IsolationUserCohortKind *)
0x180049ea2  mov     ebx, eax
0x180049ea4  xor     r13d, r13d
0x180049ea7  test    eax, eax
0x180049ea9  jns     short loc_180049ED5
0x180049eab  mov     rcx, [rbp+5Fh]; this
0x180049eaf  lea     rax, aCallingUserIsN; "Calling user is not in a supported coho"...
0x180049eb6  mov     [rsp+0C0h+var_A0], rax; int
0x180049ebb  mov     r9d, ebx; char *
0x180049ebe  lea     r8, aOnecoreuapWind_7; "onecoreuap\\windows\\core\\isoenvbroker"...
0x180049ec5  lea     edx, [r13+5Dh]; void *
0x180049ec9  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180049ece  mov     eax, ebx
0x180049ed0  jmp     loc_18004A109
0x180049ed5  lea     rdx, [rbp+57h+SRWLock]
0x180049ed9  call    ?lock_exclusive@checked_srwlock@@QEAA?AV?$holder@UExclusiveTag@checked_srwlock@@UAcquireTag@2@$0A@@1@XZ; checked_srwlock::lock_exclusive(void)
0x180049ede  mov     rcx, rsi; this
0x180049ee1  call    ?CheckEntry@IsolationEnvironment@1AI@Windows@@AEBAJXZ; Windows::AI::IsolationEnvironment::IsolationEnvironment::CheckEntry(void)
0x180049ee6  mov     ebx, eax
0x180049ee8  test    eax, eax
0x180049eea  jns     short loc_180049F19
0x180049eec  mov     rcx, [rbp+5Fh]; this
0x180049ef0  mov     r9d, eax; char *
0x180049ef3  lea     r8, aOnecoreuapWind_7; "onecoreuap\\windows\\core\\isoenvbroker"...
0x180049efa  mov     edx, 61h ; 'a'; void *
0x180049eff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180049f04  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x180049f08  test    rcx, rcx
0x180049f0b  jz      short loc_180049ECE
0x180049f0d  mov     [rcx+8], r13d
0x180049f11  call    cs:__imp_ReleaseSRWLockExclusive
0x180049f17  jmp     short loc_180049ECE
0x180049f19  xor     edx, edx; length
0x180049f1b  mov     rcx, rdi; string
0x180049f1e  call    cs:__imp_WindowsGetStringRawBuffer
0x180049f24  mov     rbx, rax
0x180049f27  test    rax, rax
0x180049f2a  jz      loc_18004A0F1
0x180049f30  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180049f34  inc     rcx
0x180049f37  cmp     [rax+rcx*2], r13w
0x180049f3c  jnz     short loc_180049F34
0x180049f3e  test    rcx, rcx
0x180049f41  jz      loc_18004A0F1
0x180049f47  mov     [rbp+57h+hObject], r13
0x180049f4b  mov     [rbp+57h+var_70], r13d
0x180049f4f  mov     [rbp+57h+var_90], r13d
0x180049f53  lea     rax, [rbp+57h+hObject]
0x180049f57  mov     [rbp+57h+var_58], rax
0x180049f5b  mov     [rbp+57h+var_50], r13
0x180049f5f  mov     [rbp+57h+var_48], 1
0x180049f63  xor     edx, edx; length
0x180049f65  mov     rcx, r14; string
0x180049f68  call    cs:__imp_WindowsGetStringRawBuffer
0x180049f6e  lea     rcx, [rbp+57h+var_90]
0x180049f72  mov     [rsp+0C0h+var_98], rcx; enum Windows::AI::IsolationEnvironment::IsolationProcessCreationStatus *
0x180049f77  lea     rcx, [rbp+57h+var_70]
0x180049f7b  mov     [rsp+0C0h+var_A0], rcx; int
0x180049f80  lea     r9, [rbp+57h+var_50]; void **
0x180049f84  mov     r8, rax; wchar_t *
0x180049f87  mov     rdx, rbx; wchar_t *
0x180049f8a  mov     rcx, rsi; this
0x180049f8d  call    ?CreateWorkerProcess@IsolationEnvironment@1AI@Windows@@AEAAJPEB_WPEA_WPEAPEAXPEAKPEAW4IsolationProcessCreationStatus@123@@Z; Windows::AI::IsolationEnvironment::IsolationEnvironment::CreateWorkerProcess(wchar_t const *,wchar_t *,void * *,ulong *,Windows::AI::IsolationEnvironment::IsolationProcessCreationStatus *)
0x180049f92  mov     r15d, eax
0x180049f95  mov     [rbp+57h+var_60], eax
0x180049f98  cmp     [rbp+57h+var_48], r13b
0x180049f9c  jz      short loc_180049FCA
0x180049f9e  mov     r14, [rbp+57h+var_50]
0x180049fa2  mov     rdi, [rbp+57h+var_58]
0x180049fa6  mov     rsi, [rdi]
0x180049fa9  test    rsi, rsi
0x180049fac  jz      short loc_180049FC7
0x180049fae  call    cs:__imp_GetLastError
0x180049fb4  mov     ebx, eax
0x180049fb6  mov     rcx, rsi; hObject
0x180049fb9  call    cs:__imp_CloseHandle
0x180049fbf  mov     ecx, ebx; dwErrCode
0x180049fc1  call    cs:__imp_SetLastError
0x180049fc7  mov     [rdi], r14
0x180049fca  mov     rax, r13
0x180049fcd  mov     [rbp+57h+var_88], rax
0x180049fd1  test    r15d, r15d
0x180049fd4  js      short loc_18004A03C
0x180049fd6  lea     r9, [rbp+57h+arg_8]
0x180049fda  lea     r8, [rbp+57h+var_70]
0x180049fde  lea     rdx, [rbp+57h+hObject]
0x180049fe2  lea     rcx, [rbp+57h+var_88]
0x180049fe6  call    ??$MakeAndInitialize@VWorkerProcess@IsolationEnvironment@AI@Windows@@UIIsolationWorkerProcess@234@V?$unique_any_t@V?$unique_storage@U?$handle_null_only_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@AEAKAEAPEAUHSTRING__@@@Details@WRL@Microsoft@@YAJPEAPEAUIIsolationWorkerProcess@IsolationEnvironment@AI@Windows@@$$QEAV?$unique_any_t@V?$unique_storage@U?$handle_null_only_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@AEAKAEAPEAUHSTRING__@@@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::AI::IsolationEnvironment::WorkerProcess,Windows::AI::IsolationEnvironment::IIsolationWorkerProcess,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,ulong &,HSTRING__ * &>(Windows::AI::IsolationEnvironment::IIsolationWorkerProcess * *,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&,ulong &,HSTRING__ * &)
0x180049feb  mov     ebx, eax
0x180049fed  test    eax, eax
0x180049fef  jns     short loc_18004A038
0x180049ff1  mov     rcx, [rbp+5Fh]; this
0x180049ff5  mov     r9d, eax; char *
0x180049ff8  lea     r8, aOnecoreuapWind_7; "onecoreuap\\windows\\core\\isoenvbroker"...
0x180049fff  mov     edx, 7Ah ; 'z'; void *
0x18004a004  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004a009  nop
0x18004a00a  mov     rcx, [rbp+57h+var_88]
0x18004a00e  test    rcx, rcx
0x18004a011  jz      short loc_18004A020
0x18004a013  mov     rax, [rcx]
0x18004a016  mov     rax, [rax+10h]
0x18004a01a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a01f  nop
0x18004a020  mov     rcx, [rbp+57h+hObject]; hObject
0x18004a024  test    rcx, rcx
0x18004a027  jz      loc_180049F04
0x18004a02d  call    cs:__imp_CloseHandle
0x18004a033  jmp     loc_180049F04
0x18004a038  mov     rax, [rbp+57h+var_88]
0x18004a03c  mov     qword ptr [rbp+57h+var_70], rax
0x18004a040  mov     [rbp+57h+var_68], r13
0x18004a044  lea     r9, [rbp+57h+var_60]
0x18004a048  lea     r8, [rbp+57h+var_90]
0x18004a04c  lea     rdx, [rbp+57h+var_70]
0x18004a050  lea     rcx, [rbp+57h+var_68]
0x18004a054  call    ??$MakeAndInitialize@VProcessCreationResult@IsolationEnvironment@AI@Windows@@UIIsolationProcessCreationResult@234@PEAUIIsolationWorkerProcess@234@AEAW4IsolationProcessCreationStatus@234@AEAJ@Details@WRL@Microsoft@@YAJPEAPEAUIIsolationProcessCreationResult@IsolationEnvironment@AI@Windows@@$$QEAPEAUIIsolationWorkerProcess@456@AEAW4IsolationProcessCreationStatus@456@AEAJ@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::AI::IsolationEnvironment::ProcessCreationResult,Windows::AI::IsolationEnvironment::IIsolationProcessCreationResult,Windows::AI::IsolationEnvironment::IIsolationWorkerProcess *,Windows::AI::IsolationEnvironment::IsolationProcessCreationStatus &,long &>(Windows::AI::IsolationEnvironment::IIsolationProcessCreationResult * *,Windows::AI::IsolationEnvironment::IIsolationWorkerProcess * &&,Windows::AI::IsolationEnvironment::IsolationProcessCreationStatus &,long &)
0x18004a059  mov     ebx, eax
0x18004a05b  test    eax, eax
0x18004a05d  jns     short loc_18004A0A9
0x18004a05f  mov     rcx, [rbp+5Fh]; this
0x18004a063  mov     r9d, eax; char *
0x18004a066  lea     r8, aOnecoreuapWind_7; "onecoreuap\\windows\\core\\isoenvbroker"...
0x18004a06d  mov     edx, 82h; void *
0x18004a072  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004a077  nop
0x18004a078  mov     rcx, [rbp+57h+var_68]
0x18004a07c  test    rcx, rcx
0x18004a07f  jz      short loc_18004A08E
0x18004a081  mov     rax, [rcx]
0x18004a084  mov     rax, [rax+10h]
0x18004a088  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a08d  nop
0x18004a08e  mov     rcx, [rbp+57h+var_88]
0x18004a092  test    rcx, rcx
0x18004a095  jz      short loc_18004A0A4
0x18004a097  mov     rax, [rcx]
0x18004a09a  mov     rax, [rax+10h]
0x18004a09e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a0a3  nop
0x18004a0a4  jmp     loc_18004A020
0x18004a0a9  mov     rax, [rbp+57h+var_68]
0x18004a0ad  mov     [rbp+57h+var_68], r13
0x18004a0b1  mov     [r12], rax
0x18004a0b5  mov     rcx, [rbp+57h+var_88]
0x18004a0b9  test    rcx, rcx
0x18004a0bc  jz      short loc_18004A0CB
0x18004a0be  mov     rax, [rcx]
0x18004a0c1  mov     rax, [rax+10h]
0x18004a0c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a0ca  nop
0x18004a0cb  mov     rcx, [rbp+57h+hObject]; hObject
0x18004a0cf  test    rcx, rcx
0x18004a0d2  jz      short loc_18004A0DA
0x18004a0d4  call    cs:__imp_CloseHandle
0x18004a0da  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18004a0de  test    rcx, rcx
0x18004a0e1  jz      short loc_18004A0ED
0x18004a0e3  mov     [rcx+8], r13d
0x18004a0e7  call    cs:__imp_ReleaseSRWLockExclusive
0x18004a0ed  xor     eax, eax
0x18004a0ef  jmp     short loc_18004A109
0x18004a0f1  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18004a0f5  test    rcx, rcx
0x18004a0f8  jz      short loc_18004A104
0x18004a0fa  mov     [rcx+8], r13d
0x18004a0fe  call    cs:__imp_ReleaseSRWLockExclusive
0x18004a104  mov     eax, 80070057h
0x18004a109  add     rsp, 88h
0x18004a110  pop     r15
0x18004a112  pop     r14
0x18004a114  pop     r13
0x18004a116  pop     r12
0x18004a118  pop     rdi
0x18004a119  pop     rsi
0x18004a11a  pop     rbx
0x18004a11b  pop     rbp
0x18004a11c  retn
```
