# Windows::AI::IsolationEnvironment::Preview::IsolationEnvironment2::LaunchIsolatedProcess(HSTRING__ *,HSTRING__ *,Windows::AI::IsolationEnvironment::Preview::IIsolationProcessCreationResult_Exp2 * *)

- ea: `0x18005e6a0`
- end: `0x18005e918`
- name: `?LaunchIsolatedProcess@IsolationEnvironment2@Preview@IsolationEnvironment@AI@Windows@@UEAAJPEAUHSTRING__@@0PEAPEAUIIsolationProcessCreationResult_Exp2@2345@@Z`
- size: `632`
- prototype: `__int64 __fastcall(Windows::AI::IsolationEnvironment::Preview::IsolationEnvironment2 *__hidden this, HSTRING string, HSTRING, struct Windows::AI::IsolationEnvironment::Preview::IIsolationProcessCreationResult_Exp2 **)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000a464`
- `0x1800134e8`
- `0x180034d48`
- `0x18005d580`
- `0x18005d67c`
- `0x18005def4`
- `0x18005e6a0`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005e707`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005e8e2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005e8f9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005e707`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005e8e2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005e8f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e7a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e7a9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005e7bc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005e7bc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005e7b4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005e828`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005e8cf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005e7b4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005e828`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005e8cf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005e719`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005e763`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005e719`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18005e763`

## string_xrefs

- `0x18005e6ea`: `onecoreuap\windows\core\isoenvbroker\lib\v2\isolationenvironment.cpp`
- `0x18005e7f3`: `onecoreuap\windows\core\isoenvbroker\lib\v2\isolationenvironment.cpp`
- `0x18005e861`: `onecoreuap\windows\core\isoenvbroker\lib\v2\isolationenvironment.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::AI::IsolationEnvironment::Preview::IsolationEnvironment2::LaunchIsolatedProcess(
        HSTRING *this,
        HSTRING string,
        HSTRING a3,
        struct Windows::AI::IsolationEnvironment::Preview::IIsolationProcessCreationResult_Exp2 **a4)
{
  unsigned int v8; // ebx
  RTL_SRWLOCK *v9; // rcx
  PCWSTR StringRawBuffer; // rax
  const wchar_t *v12; // rbx
  __int64 v13; // rcx
  wchar_t *v14; // rax
  int v15; // r15d
  void *v16; // r14
  HANDLE *v17; // rdi
  HANDLE v18; // rsi
  DWORD LastError; // ebx
  __int64 v20; // rax
  int v21; // eax
  int v22; // eax
  struct Windows::AI::IsolationEnvironment::Preview::IIsolationProcessCreationResult_Exp2 *v23; // rax
  RTL_SRWLOCK *v24; // rcx
  RTL_SRWLOCK *v25; // rcx
  int v26; // [rsp+20h] [rbp-49h]
  int v27; // [rsp+20h] [rbp-49h]
  int v28; // [rsp+30h] [rbp-39h] BYREF
  __int64 v29; // [rsp+38h] [rbp-31h] BYREF
  HANDLE hObject; // [rsp+40h] [rbp-29h] BYREF
  PSRWLOCK SRWLock; // [rsp+48h] [rbp-21h] BYREF
  unsigned int v32[2]; // [rsp+50h] [rbp-19h] BYREF
  struct Windows::AI::IsolationEnvironment::Preview::IIsolationProcessCreationResult_Exp2 *v33; // [rsp+58h] [rbp-11h] BYREF
  int v34; // [rsp+60h] [rbp-9h] BYREF
  HANDLE *p_hObject; // [rsp+68h] [rbp-1h]
  void *v36; // [rsp+70h] [rbp+7h] BYREF
  char v37; // [rsp+78h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]
  HSTRING v39; // [rsp+D8h] [rbp+6Fh] BYREF

  v39 = string;
  checked_srwlock::lock_exclusive((__int64)this, &SRWLock);
  if ( !ProblematicAdminCheck() )
  {
    v8 = -2147024891;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x64,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\v2\\isolationenvironment.cpp",
      (const char *)0x80070005LL,
      v26);
LABEL_3:
    v9 = SRWLock;
    if ( SRWLock )
    {
      LODWORD(SRWLock[1].Ptr) = 0;
      ReleaseSRWLockExclusive(v9);
    }
    return v8;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  v12 = StringRawBuffer;
  if ( !StringRawBuffer )
    goto LABEL_34;
  v13 = -1;
  do
    ++v13;
  while ( StringRawBuffer[v13] );
  if ( v13 )
  {
    hObject = 0;
    v32[0] = 0;
    v28 = 0;
    p_hObject = &hObject;
    v36 = 0;
    v37 = 1;
    v14 = (wchar_t *)WindowsGetStringRawBuffer(a3, 0);
    v15 = Windows::AI::IsolationEnvironment::Preview::IsolationEnvironment2::CreateWorkerProcess(
            this,
            v12,
            v14,
            &v36,
            v32,
            (enum Windows::AI::IsolationEnvironment::Preview::IsolationProcessCreationStatus_Exp2 *)&v28);
    v34 = v15;
    if ( v37 )
    {
      v16 = v36;
      v17 = p_hObject;
      v18 = *p_hObject;
      if ( *p_hObject )
      {
        LastError = GetLastError();
        CloseHandle(v18);
        SetLastError(LastError);
      }
      *v17 = v16;
    }
    v20 = 0;
    v29 = 0;
    if ( v15 >= 0 )
    {
      v21 = Microsoft::WRL::Details::MakeAndInitialize<Windows::AI::IsolationEnvironment::Preview::WorkerProcess2,Windows::AI::IsolationEnvironment::Preview::IIsolationWorkerProcess_Exp2,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>,unsigned long &,HSTRING__ * &>(
              &v29,
              &hObject,
              (int *)v32,
              &v39);
      v8 = v21;
      if ( v21 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x7D,
          (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\v2\\isolationenvironment.cpp",
          (const char *)(unsigned int)v21,
          v27);
        if ( v29 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
LABEL_18:
        if ( hObject )
          CloseHandle(hObject);
        goto LABEL_3;
      }
      v20 = v29;
    }
    *(_QWORD *)v32 = v20;
    v33 = 0;
    v22 = Microsoft::WRL::Details::MakeAndInitialize<Windows::AI::IsolationEnvironment::Preview::ProcessCreationResult2,Windows::AI::IsolationEnvironment::Preview::IIsolationProcessCreationResult_Exp2,Windows::AI::IsolationEnvironment::Preview::IIsolationWorkerProcess_Exp2 *,enum Windows::AI::IsolationEnvironment::Preview::IsolationProcessCreationStatus_Exp2 &,long &>(
            &v33,
            v32,
            &v28,
            &v34);
    v8 = v22;
    if ( v22 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x85,
        (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\v2\\isolationenvironment.cpp",
        (const char *)(unsigned int)v22,
        v27);
      if ( v33 )
        (*(void (__fastcall **)(struct Windows::AI::IsolationEnvironment::Preview::IIsolationProcessCreationResult_Exp2 *))(*(_QWORD *)v33 + 16LL))(v33);
      if ( v29 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
      goto LABEL_18;
    }
    v23 = v33;
    v33 = 0;
    *a4 = v23;
    if ( v29 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
    if ( hObject )
      CloseHandle(hObject);
    v24 = SRWLock;
    if ( SRWLock )
    {
      LODWORD(SRWLock[1].Ptr) = 0;
      ReleaseSRWLockExclusive(v24);
    }
    return 0;
  }
  else
  {
LABEL_34:
    v25 = SRWLock;
    if ( SRWLock )
    {
      LODWORD(SRWLock[1].Ptr) = 0;
      ReleaseSRWLockExclusive(v25);
    }
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x18005e6a0  mov     [rsp-8+arg_8], rdx
0x18005e6a5  push    rbp
0x18005e6a6  push    rbx
0x18005e6a7  push    rsi
0x18005e6a8  push    rdi
0x18005e6a9  push    r12
0x18005e6ab  push    r13
0x18005e6ad  push    r14
0x18005e6af  push    r15
0x18005e6b1  lea     rbp, [rsp-1Fh]
0x18005e6b6  sub     rsp, 88h
0x18005e6bd  mov     r12, r9
0x18005e6c0  mov     rdi, r8
0x18005e6c3  mov     rbx, rdx
0x18005e6c6  mov     rsi, rcx
0x18005e6c9  lea     rdx, [rbp+57h+SRWLock]
0x18005e6cd  call    ?lock_exclusive@checked_srwlock@@QEAA?AV?$holder@UExclusiveTag@checked_srwlock@@UAcquireTag@2@$0A@@1@XZ; checked_srwlock::lock_exclusive(void)
0x18005e6d2  call    _ProblematicAdminCheck
0x18005e6d7  xor     r13d, r13d
0x18005e6da  test    al, al
0x18005e6dc  jnz     short loc_18005E714
0x18005e6de  mov     rcx, [rbp+5Fh]; this
0x18005e6e2  mov     ebx, 80070005h
0x18005e6e7  mov     r9d, ebx; char *
0x18005e6ea  lea     r8, aOnecoreuapWind_19; "onecoreuap\\windows\\core\\isoenvbroker"...
0x18005e6f1  lea     edx, [r13+64h]; void *
0x18005e6f5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005e6fa  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18005e6fe  test    rcx, rcx
0x18005e701  jz      short loc_18005E70D
0x18005e703  mov     [rcx+8], r13d
0x18005e707  call    cs:__imp_ReleaseSRWLockExclusive
0x18005e70d  mov     eax, ebx
0x18005e70f  jmp     loc_18005E904
0x18005e714  xor     edx, edx; length
0x18005e716  mov     rcx, rbx; string
0x18005e719  call    cs:__imp_WindowsGetStringRawBuffer
0x18005e71f  mov     rbx, rax
0x18005e722  test    rax, rax
0x18005e725  jz      loc_18005E8EC
0x18005e72b  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18005e72f  inc     rcx
0x18005e732  cmp     [rax+rcx*2], r13w
0x18005e737  jnz     short loc_18005E72F
0x18005e739  test    rcx, rcx
0x18005e73c  jz      loc_18005E8EC
0x18005e742  mov     [rbp+57h+hObject], r13
0x18005e746  mov     [rbp+57h+var_70], r13d
0x18005e74a  mov     [rbp+57h+var_90], r13d
0x18005e74e  lea     rax, [rbp+57h+hObject]
0x18005e752  mov     [rbp+57h+var_58], rax
0x18005e756  mov     [rbp+57h+var_50], r13
0x18005e75a  mov     [rbp+57h+var_48], 1
0x18005e75e  xor     edx, edx; length
0x18005e760  mov     rcx, rdi; string
0x18005e763  call    cs:__imp_WindowsGetStringRawBuffer
0x18005e769  lea     rcx, [rbp+57h+var_90]
0x18005e76d  mov     [rsp+0C0h+var_98], rcx; enum Windows::AI::IsolationEnvironment::Preview::IsolationProcessCreationStatus_Exp2 *
0x18005e772  lea     rcx, [rbp+57h+var_70]
0x18005e776  mov     [rsp+0C0h+var_A0], rcx; int
0x18005e77b  lea     r9, [rbp+57h+var_50]; void **
0x18005e77f  mov     r8, rax; wchar_t *
0x18005e782  mov     rdx, rbx; wchar_t *
0x18005e785  mov     rcx, rsi; this
0x18005e788  call    ?CreateWorkerProcess@IsolationEnvironment2@Preview@IsolationEnvironment@AI@Windows@@AEAAJPEB_WPEA_WPEAPEAXPEAKPEAW4IsolationProcessCreationStatus_Exp2@2345@@Z; Windows::AI::IsolationEnvironment::Preview::IsolationEnvironment2::CreateWorkerProcess(wchar_t const *,wchar_t *,void * *,ulong *,Windows::AI::IsolationEnvironment::Preview::IsolationProcessCreationStatus_Exp2 *)
0x18005e78d  mov     r15d, eax
0x18005e790  mov     [rbp+57h+var_60], eax
0x18005e793  cmp     [rbp+57h+var_48], r13b
0x18005e797  jz      short loc_18005E7C5
0x18005e799  mov     r14, [rbp+57h+var_50]
0x18005e79d  mov     rdi, [rbp+57h+var_58]
0x18005e7a1  mov     rsi, [rdi]
0x18005e7a4  test    rsi, rsi
0x18005e7a7  jz      short loc_18005E7C2
0x18005e7a9  call    cs:__imp_GetLastError
0x18005e7af  mov     ebx, eax
0x18005e7b1  mov     rcx, rsi; hObject
0x18005e7b4  call    cs:__imp_CloseHandle
0x18005e7ba  mov     ecx, ebx; dwErrCode
0x18005e7bc  call    cs:__imp_SetLastError
0x18005e7c2  mov     [rdi], r14
0x18005e7c5  mov     rax, r13
0x18005e7c8  mov     [rbp+57h+var_88], rax
0x18005e7cc  test    r15d, r15d
0x18005e7cf  js      short loc_18005E837
0x18005e7d1  lea     r9, [rbp+57h+arg_8]
0x18005e7d5  lea     r8, [rbp+57h+var_70]
0x18005e7d9  lea     rdx, [rbp+57h+hObject]
0x18005e7dd  lea     rcx, [rbp+57h+var_88]
0x18005e7e1  call    ??$MakeAndInitialize@VWorkerProcess2@Preview@IsolationEnvironment@AI@Windows@@UIIsolationWorkerProcess_Exp2@2345@V?$unique_any_t@V?$unique_storage@U?$handle_null_only_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@AEAKAEAPEAUHSTRING__@@@Details@WRL@Microsoft@@YAJPEAPEAUIIsolationWorkerProcess_Exp2@Preview@IsolationEnvironment@AI@Windows@@$$QEAV?$unique_any_t@V?$unique_storage@U?$handle_null_only_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@AEAKAEAPEAUHSTRING__@@@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::AI::IsolationEnvironment::Preview::WorkerProcess2,Windows::AI::IsolationEnvironment::Preview::IIsolationWorkerProcess_Exp2,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,ulong &,HSTRING__ * &>(Windows::AI::IsolationEnvironment::Preview::IIsolationWorkerProcess_Exp2 * *,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_only_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&,ulong &,HSTRING__ * &)
0x18005e7e6  mov     ebx, eax
0x18005e7e8  test    eax, eax
0x18005e7ea  jns     short loc_18005E833
0x18005e7ec  mov     rcx, [rbp+5Fh]; this
0x18005e7f0  mov     r9d, eax; char *
0x18005e7f3  lea     r8, aOnecoreuapWind_19; "onecoreuap\\windows\\core\\isoenvbroker"...
0x18005e7fa  mov     edx, 7Dh ; '}'; void *
0x18005e7ff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005e804  nop
0x18005e805  mov     rcx, [rbp+57h+var_88]
0x18005e809  test    rcx, rcx
0x18005e80c  jz      short loc_18005E81B
0x18005e80e  mov     rax, [rcx]
0x18005e811  mov     rax, [rax+10h]
0x18005e815  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e81a  nop
0x18005e81b  mov     rcx, [rbp+57h+hObject]; hObject
0x18005e81f  test    rcx, rcx
0x18005e822  jz      loc_18005E6FA
0x18005e828  call    cs:__imp_CloseHandle
0x18005e82e  jmp     loc_18005E6FA
0x18005e833  mov     rax, [rbp+57h+var_88]
0x18005e837  mov     qword ptr [rbp+57h+var_70], rax
0x18005e83b  mov     [rbp+57h+var_68], r13
0x18005e83f  lea     r9, [rbp+57h+var_60]
0x18005e843  lea     r8, [rbp+57h+var_90]
0x18005e847  lea     rdx, [rbp+57h+var_70]
0x18005e84b  lea     rcx, [rbp+57h+var_68]
0x18005e84f  call    ??$MakeAndInitialize@VProcessCreationResult2@Preview@IsolationEnvironment@AI@Windows@@UIIsolationProcessCreationResult_Exp2@2345@PEAUIIsolationWorkerProcess_Exp2@2345@AEAW4IsolationProcessCreationStatus_Exp2@2345@AEAJ@Details@WRL@Microsoft@@YAJPEAPEAUIIsolationProcessCreationResult_Exp2@Preview@IsolationEnvironment@AI@Windows@@$$QEAPEAUIIsolationWorkerProcess_Exp2@4567@AEAW4IsolationProcessCreationStatus_Exp2@4567@AEAJ@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::AI::IsolationEnvironment::Preview::ProcessCreationResult2,Windows::AI::IsolationEnvironment::Preview::IIsolationProcessCreationResult_Exp2,Windows::AI::IsolationEnvironment::Preview::IIsolationWorkerProcess_Exp2 *,Windows::AI::IsolationEnvironment::Preview::IsolationProcessCreationStatus_Exp2 &,long &>(Windows::AI::IsolationEnvironment::Preview::IIsolationProcessCreationResult_Exp2 * *,Windows::AI::IsolationEnvironment::Preview::IIsolationWorkerProcess_Exp2 * &&,Windows::AI::IsolationEnvironment::Preview::IsolationProcessCreationStatus_Exp2 &,long &)
0x18005e854  mov     ebx, eax
0x18005e856  test    eax, eax
0x18005e858  jns     short loc_18005E8A4
0x18005e85a  mov     rcx, [rbp+5Fh]; this
0x18005e85e  mov     r9d, eax; char *
0x18005e861  lea     r8, aOnecoreuapWind_19; "onecoreuap\\windows\\core\\isoenvbroker"...
0x18005e868  mov     edx, 85h; void *
0x18005e86d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005e872  nop
0x18005e873  mov     rcx, [rbp+57h+var_68]
0x18005e877  test    rcx, rcx
0x18005e87a  jz      short loc_18005E889
0x18005e87c  mov     rax, [rcx]
0x18005e87f  mov     rax, [rax+10h]
0x18005e883  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e888  nop
0x18005e889  mov     rcx, [rbp+57h+var_88]
0x18005e88d  test    rcx, rcx
0x18005e890  jz      short loc_18005E89F
0x18005e892  mov     rax, [rcx]
0x18005e895  mov     rax, [rax+10h]
0x18005e899  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e89e  nop
0x18005e89f  jmp     loc_18005E81B
0x18005e8a4  mov     rax, [rbp+57h+var_68]
0x18005e8a8  mov     [rbp+57h+var_68], r13
0x18005e8ac  mov     [r12], rax
0x18005e8b0  mov     rcx, [rbp+57h+var_88]
0x18005e8b4  test    rcx, rcx
0x18005e8b7  jz      short loc_18005E8C6
0x18005e8b9  mov     rax, [rcx]
0x18005e8bc  mov     rax, [rax+10h]
0x18005e8c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e8c5  nop
0x18005e8c6  mov     rcx, [rbp+57h+hObject]; hObject
0x18005e8ca  test    rcx, rcx
0x18005e8cd  jz      short loc_18005E8D5
0x18005e8cf  call    cs:__imp_CloseHandle
0x18005e8d5  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18005e8d9  test    rcx, rcx
0x18005e8dc  jz      short loc_18005E8E8
0x18005e8de  mov     [rcx+8], r13d
0x18005e8e2  call    cs:__imp_ReleaseSRWLockExclusive
0x18005e8e8  xor     eax, eax
0x18005e8ea  jmp     short loc_18005E904
0x18005e8ec  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18005e8f0  test    rcx, rcx
0x18005e8f3  jz      short loc_18005E8FF
0x18005e8f5  mov     [rcx+8], r13d
0x18005e8f9  call    cs:__imp_ReleaseSRWLockExclusive
0x18005e8ff  mov     eax, 80070057h
0x18005e904  add     rsp, 88h
0x18005e90b  pop     r15
0x18005e90d  pop     r14
0x18005e90f  pop     r13
0x18005e911  pop     r12
0x18005e913  pop     rdi
0x18005e914  pop     rsi
0x18005e915  pop     rbx
0x18005e916  pop     rbp
0x18005e917  retn
```
