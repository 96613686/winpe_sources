# wWinMain

- ea: `0x140007a78`
- end: `0x140007d65`
- name: `wWinMain`
- size: `749`
- prototype: `int __stdcall(HINSTANCE hInstance, HINSTANCE hPrevInstance, LPWSTR lpCmdLine, int nShowCmd)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1400012b0`

## callees

- `0x140001460`
- `0x140001484`
- `0x14000175c`
- `0x140001f5c`
- `0x140002b70`
- `0x140003430`
- `0x1400040bc`
- `0x140004f6c`
- `0x1400059c0`
- `0x1400063c4`
- `0x1400063f0`
- `0x14000759c`
- `0x140007a78`
- `0x14000a010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x140007c5a`
- `KERNEL32!EnterCriticalSection` at `0x140007c5a`
- `KERNEL32!LeaveCriticalSection` at `0x140007c9b`
- `KERNEL32!LeaveCriticalSection` at `0x140007c9b`
- `KERNEL32!CreateMutexW` at `0x140007ae3`
- `KERNEL32!CreateMutexW` at `0x140007ae3`
- `KERNEL32!SetLastError` at `0x140007c0f`
- `KERNEL32!SetLastError` at `0x140007c0f`
- `KERNEL32!CloseHandle` at `0x140007c4e`
- `KERNEL32!CloseHandle` at `0x140007cbc`
- `KERNEL32!CloseHandle` at `0x140007d35`
- `KERNEL32!CloseHandle` at `0x140007c4e`
- `KERNEL32!CloseHandle` at `0x140007cbc`
- `KERNEL32!CloseHandle` at `0x140007d35`
- `KERNEL32!GetLastError` at `0x140007b20`
- `KERNEL32!GetLastError` at `0x140007beb`
- `KERNEL32!GetLastError` at `0x140007b20`
- `KERNEL32!GetLastError` at `0x140007beb`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x140007cc2`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x140007d3b`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x140007cc2`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x140007d3b`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x140007a9b`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x140007a9b`

## string_xrefs

- `0x140007abd`: `Windows::Foundation::Initialize(RO_INIT_SINGLETHREADED)`
- `0x140007b31`: `GetLastError() == ERROR_ALREADY_EXISTS`

## pseudocode

```c
int __stdcall wWinMain(HINSTANCE hInstance, HINSTANCE hPrevInstance, LPWSTR lpCmdLine, int nShowCmd)
{
  int v4; // eax
  int LastError; // ebx
  HANDLE MutexW; // rdi
  __int64 **v7; // rax
  int v8; // eax
  __int64 v9; // rcx
  __int64 v10; // r8
  int v11; // eax
  void (__fastcall ***v12)(_QWORD, __int64); // rsi
  void (__fastcall ***v13)(_QWORD, __int64); // rbx
  DWORD v14; // r14d
  void *i; // rbx
  __int64 *v16; // rcx
  __int64 v17; // rdx
  wil::details *v19; // [rsp+28h] [rbp-A1h]
  wil::details *v20; // [rsp+28h] [rbp-A1h]
  int v21[2]; // [rsp+30h] [rbp-99h] BYREF
  char v22[8]; // [rsp+38h] [rbp-91h] BYREF
  _QWORD v23[13]; // [rsp+40h] [rbp-89h] BYREF
  _QWORD *v24; // [rsp+A8h] [rbp-21h]
  void (__fastcall ***v25)(_QWORD, __int64); // [rsp+B0h] [rbp-19h] BYREF
  __int64 **v26; // [rsp+B8h] [rbp-11h]
  __int64 v27; // [rsp+C0h] [rbp-9h]
  struct _RTL_CRITICAL_SECTION CriticalSection; // [rsp+C8h] [rbp-1h] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+128h] [rbp+5Fh]

  v4 = RoInitialize(0, hPrevInstance, lpCmdLine, nShowCmd);
  LastError = v4;
  if ( v4 < 0 )
  {
    LODWORD(v19) = v4;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0xBD,
      (unsigned int)"drivers\\mobilepc\\location\\product\\winactiondialog\\exe\\actiondialog.cpp",
      "wWinMain",
      "Windows::Foundation::Initialize(RO_INIT_SINGLETHREADED)",
      v19,
      v21[0]);
    return LastError;
  }
  MutexW = CreateMutexW(0, 0, L"ACTIONDIALOG_MUTEX");
  if ( !MutexW )
  {
    LastError = wil::details::in1diag5::Return_GetLastError(
                  retaddr,
                  (void *)0xC3,
                  (unsigned int)"drivers\\mobilepc\\location\\product\\winactiondialog\\exe\\actiondialog.cpp",
                  "wWinMain",
                  "nullptr == hMutex.m_h",
                  (const char *)v19);
LABEL_27:
    RoUninitialize();
    return LastError;
  }
  if ( GetLastError() == 183 )
  {
    LastError = wil::details::in1diag5::Return_GetLastError(
                  retaddr,
                  (void *)0xC4,
                  (unsigned int)"drivers\\mobilepc\\location\\product\\winactiondialog\\exe\\actiondialog.cpp",
                  "wWinMain",
                  "GetLastError() == ERROR_ALREADY_EXISTS",
                  (const char *)v19);
LABEL_26:
    CloseHandle(MutexW);
    goto LABEL_27;
  }
  memset_0(&v25, 0, 0x40u);
  v7 = (__int64 **)operator new(0x18u);
  *v7 = (__int64 *)v7;
  v7[1] = (__int64 *)v7;
  v26 = v7;
  memset(&CriticalSection, 0, sizeof(CriticalSection));
  v8 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)&CriticalSection);
  if ( v8 < 0 )
    ATL::AtlThrowImpl(v8);
  *(_QWORD *)v21 = 0;
  v23[0] = ___7____func_V_lambda_1___1__Initialize_ActionDialogManager__QEAAJXZ___A6AXXZ___function_wistd__6B_;
  v23[1] = &v25;
  v24 = v23;
  v11 = wil::details::make_wnf_subscription_state<wil::details::empty_wnf_state>(v9, v22, v10, v21);
  v12 = v25;
  v13 = 0;
  if ( v11 >= 0 )
    v13 = *(void (__fastcall ****)(_QWORD, __int64))v21;
  if ( v25 )
  {
    v14 = GetLastError();
    if ( v12 )
      (**v12)(v12, 1);
    SetLastError(v14);
  }
  v25 = v13;
  if ( v24 )
  {
    (*(void (__fastcall **)(_QWORD *))(*v24 + 24LL))(v24);
    v13 = v25;
  }
  if ( !v13 )
  {
    LastError = -2147024882;
    LODWORD(v19) = -2147024882;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x45,
      (unsigned int)"drivers\\mobilepc\\location\\product\\winactiondialog\\exe\\actiondialog.cpp",
      "ActionDialogManager::Initialize",
      "_recalculateWnf",
      v19,
      v21[0]);
    LODWORD(v20) = -2147024882;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0xC7,
      (unsigned int)"drivers\\mobilepc\\location\\product\\winactiondialog\\exe\\actiondialog.cpp",
      "wWinMain",
      "adm.Initialize()",
      v20,
      v21[0]);
    ActionDialogManager::~ActionDialogManager((ActionDialogManager *)&v25);
    goto LABEL_26;
  }
  ActionDialogManager::WnfCallback((ActionDialogManager *)&v25);
  for ( i = 0; ; ActionDialogManager::HandlePromptSync(i) )
  {
    if ( i )
    {
      CloseHandle(i);
      i = 0;
    }
    EnterCriticalSection(&CriticalSection);
    if ( v27 )
    {
      v16 = *v26;
      v17 = **v26;
      i = (void *)(*v26)[2];
      --v27;
      *(_QWORD *)v16[1] = v17;
      *(_QWORD *)(v17 + 8) = v16[1];
      operator delete(v16);
    }
    LeaveCriticalSection(&CriticalSection);
    if ( !i )
      break;
  }
  ActionDialogManager::~ActionDialogManager((ActionDialogManager *)&v25);
  CloseHandle(MutexW);
  RoUninitialize();
  return 0;
}

```

## disassembly

```asm
0x140007a78  push    rbp
0x140007a7a  push    rbx
0x140007a7b  push    rsi
0x140007a7c  push    rdi
0x140007a7d  push    r14
0x140007a7f  lea     rbp, [rsp-37h]
0x140007a84  sub     rsp, 100h
0x140007a8b  mov     rax, cs:__security_cookie
0x140007a92  xor     rax, rsp
0x140007a95  mov     [rbp+57h+var_30], rax
0x140007a99  xor     ecx, ecx
0x140007a9b  call    cs:__imp_RoInitialize
0x140007aa1  mov     ebx, eax
0x140007aa3  test    eax, eax
0x140007aa5  jns     short loc_140007AD8
0x140007aa7  mov     rcx, [rbp+5Fh]; this
0x140007aab  lea     r9, aWwinmain; "wWinMain"
0x140007ab2  mov     dword ptr [rsp+120h+var_F8], eax; wil::details *
0x140007ab6  lea     r8, aDriversMobilep; "drivers\\mobilepc\\location\\product\\w"...
0x140007abd  lea     rax, aWindowsFoundat; "Windows::Foundation::Initialize(RO_INIT"...
0x140007ac4  mov     edx, 0BDh; void *
0x140007ac9  mov     [rsp+120h+var_100], rax; char *
0x140007ace  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x140007ad3  jmp     loc_140007D41
0x140007ad8  lea     r8, Name; "ACTIONDIALOG_MUTEX"
0x140007adf  xor     edx, edx; bInitialOwner
0x140007ae1  xor     ecx, ecx; lpMutexAttributes
0x140007ae3  call    cs:__imp_CreateMutexW
0x140007ae9  mov     rdi, rax
0x140007aec  test    rax, rax
0x140007aef  jnz     short loc_140007B20
0x140007af1  mov     rcx, [rbp+5Fh]; this
0x140007af5  lea     rax, aNullptrHmutexM; "nullptr == hMutex.m_h"
0x140007afc  lea     r9, aWwinmain; "wWinMain"
0x140007b03  mov     [rsp+120h+var_100], rax; char *
0x140007b08  lea     r8, aDriversMobilep; "drivers\\mobilepc\\location\\product\\w"...
0x140007b0f  mov     edx, 0C3h; void *
0x140007b14  call    ?Return_GetLastError@in1diag5@details@wil@@YAJPEAXIPEBD11@Z; wil::details::in1diag5::Return_GetLastError(void *,uint,char const *,char const *,char const *)
0x140007b19  mov     ebx, eax
0x140007b1b  jmp     loc_140007D3B
0x140007b20  call    cs:__imp_GetLastError
0x140007b26  cmp     eax, 0B7h
0x140007b2b  jnz     short loc_140007B5C
0x140007b2d  mov     rcx, [rbp+5Fh]; this
0x140007b31  lea     rax, aGetlasterrorEr; "GetLastError() == ERROR_ALREADY_EXISTS"
0x140007b38  lea     r9, aWwinmain; "wWinMain"
0x140007b3f  mov     [rsp+120h+var_100], rax; char *
0x140007b44  lea     r8, aDriversMobilep; "drivers\\mobilepc\\location\\product\\w"...
0x140007b4b  mov     edx, 0C4h; void *
0x140007b50  call    ?Return_GetLastError@in1diag5@details@wil@@YAJPEAXIPEBD11@Z; wil::details::in1diag5::Return_GetLastError(void *,uint,char const *,char const *,char const *)
0x140007b55  mov     ebx, eax
0x140007b57  jmp     loc_140007D32
0x140007b5c  xor     edx, edx; Val
0x140007b5e  lea     rcx, [rbp+57h+var_70]; void *
0x140007b62  lea     r8d, [rdx+40h]; Size
0x140007b66  call    memset_0
0x140007b6b  mov     ecx, 18h; Size
0x140007b70  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140007b75  xorps   xmm0, xmm0
0x140007b78  lea     rcx, [rbp+57h+CriticalSection]; this
0x140007b7c  mov     [rax], rax
0x140007b7f  mov     [rax+8], rax
0x140007b83  mov     [rbp+57h+var_68], rax
0x140007b87  xor     eax, eax
0x140007b89  mov     [rbp+57h+CriticalSection.SpinCount], rax
0x140007b8d  movups  xmmword ptr [rbp+57h+CriticalSection.DebugInfo], xmm0
0x140007b91  movups  xmmword ptr [rbp+57h+CriticalSection.OwningThread], xmm0
0x140007b95  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x140007b9a  test    eax, eax
0x140007b9c  js      loc_140007D5D
0x140007ba2  lea     rax, ??_7?$__func@V_lambda_1_@?1??Initialize@ActionDialogManager@@QEAAJXZ@$$A6AXXZ@__function@wistd@@6B@; const wistd::__function::__func<`ActionDialogManager::Initialize(void)'::`2'::_lambda_1_,void (void)>::`vftable'
0x140007ba9  mov     qword ptr [rsp+120h+var_F0], 0; int
0x140007bb2  mov     [rsp+120h+var_E0], rax
0x140007bb7  lea     r9, [rsp+120h+var_F0]
0x140007bbc  lea     rax, [rbp+57h+var_70]
0x140007bc0  mov     [rsp+120h+var_D8], rax
0x140007bc5  lea     rdx, [rsp+120h+var_E8]
0x140007bca  lea     rax, [rsp+120h+var_E0]
0x140007bcf  mov     [rbp+57h+var_78], rax
0x140007bd3  call    ??$make_wnf_subscription_state@Uempty_wnf_state@details@wil@@@details@wil@@YAJAEBU_WNF_STATE_NAME@@$$QEAV?$function@$$A6AXXZ@wistd@@KPEAPEAU?$wnf_subscription_state@Uempty_wnf_state@details@wil@@@01@@Z; wil::details::make_wnf_subscription_state<wil::details::empty_wnf_state>(_WNF_STATE_NAME const &,wistd::function<void (void)> &&,ulong,wil::details::wnf_subscription_state<wil::details::empty_wnf_state> * *)
0x140007bd8  mov     rsi, [rbp+57h+var_70]
0x140007bdc  xor     ebx, ebx
0x140007bde  test    eax, eax
0x140007be0  cmovns  rbx, qword ptr [rsp+120h+var_F0]
0x140007be6  test    rsi, rsi
0x140007be9  jz      short loc_140007C15
0x140007beb  call    cs:__imp_GetLastError
0x140007bf1  mov     r14d, eax
0x140007bf4  test    rsi, rsi
0x140007bf7  jz      short loc_140007C0C
0x140007bf9  mov     rdx, [rsi]
0x140007bfc  mov     rcx, rsi
0x140007bff  mov     rax, [rdx]
0x140007c02  mov     edx, 1
0x140007c07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007c0c  mov     ecx, r14d; dwErrCode
0x140007c0f  call    cs:__imp_SetLastError
0x140007c15  mov     rcx, [rbp+57h+var_78]
0x140007c19  mov     [rbp+57h+var_70], rbx
0x140007c1d  test    rcx, rcx
0x140007c20  jz      short loc_140007C32
0x140007c22  mov     rax, [rcx]
0x140007c25  mov     rax, [rax+18h]
0x140007c29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007c2e  mov     rbx, [rbp+57h+var_70]
0x140007c32  test    rbx, rbx
0x140007c35  jz      loc_140007CCC
0x140007c3b  lea     rcx, [rbp+57h+var_70]; this
0x140007c3f  call    ?WnfCallback@ActionDialogManager@@QEAAJXZ; ActionDialogManager::WnfCallback(void)
0x140007c44  xor     ebx, ebx
0x140007c46  test    rbx, rbx
0x140007c49  jz      short loc_140007C56
0x140007c4b  mov     rcx, rbx; hObject
0x140007c4e  call    cs:__imp_CloseHandle
0x140007c54  xor     ebx, ebx
0x140007c56  lea     rcx, [rbp+57h+CriticalSection]; lpCriticalSection
0x140007c5a  call    cs:__imp_EnterCriticalSection
0x140007c60  mov     r8, [rbp+57h+var_60]
0x140007c64  test    r8, r8
0x140007c67  jz      short loc_140007C97
0x140007c69  mov     rax, [rbp+57h+var_68]
0x140007c6d  dec     r8
0x140007c70  mov     rcx, [rax]; Block
0x140007c73  mov     rdx, [rcx]
0x140007c76  mov     rbx, [rcx+10h]
0x140007c7a  mov     [rbp+57h+var_60], r8
0x140007c7e  mov     rax, [rcx+8]
0x140007c82  mov     [rax], rdx
0x140007c85  mov     rax, [rcx+8]
0x140007c89  mov     [rdx+8], rax
0x140007c8d  mov     edx, 18h
0x140007c92  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140007c97  lea     rcx, [rbp+57h+CriticalSection]; lpCriticalSection
0x140007c9b  call    cs:__imp_LeaveCriticalSection
0x140007ca1  test    rbx, rbx
0x140007ca4  jz      short loc_140007CB0
0x140007ca6  mov     rcx, rbx; void *
0x140007ca9  call    ?HandlePromptSync@ActionDialogManager@@SAJPEAX@Z; ActionDialogManager::HandlePromptSync(void *)
0x140007cae  jmp     short loc_140007C46
0x140007cb0  lea     rcx, [rbp+57h+var_70]; this
0x140007cb4  call    ??1ActionDialogManager@@QEAA@XZ; ActionDialogManager::~ActionDialogManager(void)
0x140007cb9  mov     rcx, rdi; hObject
0x140007cbc  call    cs:__imp_CloseHandle
0x140007cc2  call    cs:__imp_RoUninitialize
0x140007cc8  xor     eax, eax
0x140007cca  jmp     short loc_140007D43
0x140007ccc  mov     rcx, [rbp+5Fh]; this
0x140007cd0  lea     rax, aRecalculatewnf; "_recalculateWnf"
0x140007cd7  mov     ebx, 8007000Eh
0x140007cdc  lea     r9, aActiondialogma_0; "ActionDialogManager::Initialize"
0x140007ce3  mov     dword ptr [rsp+120h+var_F8], ebx; wil::details *
0x140007ce7  lea     r8, aDriversMobilep; "drivers\\mobilepc\\location\\product\\w"...
0x140007cee  mov     edx, 45h ; 'E'; void *
0x140007cf3  mov     [rsp+120h+var_100], rax; char *
0x140007cf8  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x140007cfd  mov     rcx, [rbp+5Fh]; this
0x140007d01  lea     rdx, aAdmInitialize; "adm.Initialize()"
0x140007d08  mov     dword ptr [rsp+120h+var_F8], ebx; wil::details *
0x140007d0c  lea     r9, aWwinmain; "wWinMain"
0x140007d13  mov     [rsp+120h+var_100], rdx; char *
0x140007d18  lea     r8, aDriversMobilep; "drivers\\mobilepc\\location\\product\\w"...
0x140007d1f  mov     edx, 0C7h; void *
0x140007d24  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x140007d29  lea     rcx, [rbp+57h+var_70]; this
0x140007d2d  call    ??1ActionDialogManager@@QEAA@XZ; ActionDialogManager::~ActionDialogManager(void)
0x140007d32  mov     rcx, rdi; hObject
0x140007d35  call    cs:__imp_CloseHandle
0x140007d3b  call    cs:__imp_RoUninitialize
0x140007d41  mov     eax, ebx
0x140007d43  mov     rcx, [rbp+57h+var_30]
0x140007d47  xor     rcx, rsp; StackCookie
0x140007d4a  call    __security_check_cookie
0x140007d4f  add     rsp, 100h
0x140007d56  pop     r14
0x140007d58  pop     rdi
0x140007d59  pop     rsi
0x140007d5a  pop     rbx
0x140007d5b  pop     rbp
0x140007d5c  retn
0x140007d5d  mov     ecx, eax; int
0x140007d5f  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
