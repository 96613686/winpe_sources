# WinStoreAuth::AuthenticationInternal::GetCurrentIUser(Windows::System::IUser * *)

- ea: `0x1800400c0`
- end: `0x1800403bb`
- name: `?GetCurrentIUser@AuthenticationInternal@WinStoreAuth@@YAJPEAPEAUIUser@System@Windows@@@Z`
- size: `763`
- prototype: `__int64 __fastcall(WinStoreAuth::AuthenticationInternal *__hidden this, struct Windows::System::IUser **)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180043ddc`

## callees

- `0x1800026b0`
- `0x180010b64`
- `0x180010b84`
- `0x18002fbb4`
- `0x1800400c0`
- `0x18004f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040121`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180040121`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180040134`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180040134`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800400f4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800400f4`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180040109`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180040109`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004013e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18004013e`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180040150`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180040150`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004012c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004017f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004038a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004012c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004017f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004038a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800401d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800401d6`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x180040194`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x180040194`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180040210`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180040210`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall WinStoreAuth::AuthenticationInternal::GetCurrentIUser(
        WinStoreAuth::AuthenticationInternal *this,
        struct Windows::System::IUser **a2)
{
  HANDLE CurrentThread; // rax
  void *v4; // rdi
  DWORD LastError; // ebx
  HANDLE CurrentProcess; // rax
  const char *v7; // r9
  unsigned int v8; // ebx
  void *v9; // rcx
  bool v10; // cc
  int v12; // eax
  HRESULT v13; // eax
  int v14; // edx
  unsigned int v15; // r8d
  int ActivationFactory; // eax
  __int64 (__fastcall ***v17)(_QWORD, GUID *, _QWORD *); // rcx
  int v18; // eax
  __int64 v19; // rcx
  __int64 (__fastcall ***v20)(_QWORD, GUID *, _QWORD *); // rcx
  int v21; // eax
  __int64 v22; // rcx
  __int64 (__fastcall ***v23)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 v24; // rcx
  __int64 (__fastcall ***v25)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 (__fastcall ***v26)(_QWORD, GUID *, __int64 *); // [rsp+20h] [rbp-50h] BYREF
  void *TokenHandle; // [rsp+28h] [rbp-48h] BYREF
  __int64 v28; // [rsp+30h] [rbp-40h] BYREF
  __int64 v29; // [rsp+38h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-30h] BYREF
  HSTRING string; // [rsp+58h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]

  v29 = 0;
  *(_QWORD *)this = 0;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0xCu, 1, &TokenHandle) )
  {
    v4 = TokenHandle;
    if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      LastError = GetLastError();
      CloseHandle(v4);
      SetLastError(LastError);
    }
    TokenHandle = 0;
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 0xCu, &TokenHandle) )
    {
      v8 = wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x690,
             (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
             v7);
LABEL_6:
      v9 = TokenHandle;
      v10 = (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL;
LABEL_7:
      if ( v10 )
        CloseHandle(v9);
      return v8;
    }
  }
  v12 = UMgrQueryUserContext(TokenHandle, &v29);
  v8 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x693,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)(unsigned int)v12,
      (int)v26);
    goto LABEL_6;
  }
  v26 = 0;
  string = 0;
  v13 = WindowsCreateStringReference(L"Windows.System.Internal.UserManager", 0x23u, &hstringHeader, &string);
  if ( v13 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v13, v14, v15);
    JUMPOUT(0x1800403BALL);
  }
  ActivationFactory = RoGetActivationFactory(string, &GUID_252e7f79_acfa_4ea2_9a7e_fa27a8a4d3d9, &v26);
  v8 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x696,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)(unsigned int)ActivationFactory,
      (int)v26);
    v17 = v26;
    if ( v26 )
    {
      v26 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v17)[2])(v17);
    }
LABEL_16:
    v9 = TokenHandle;
    v10 = (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL;
    goto LABEL_7;
  }
  v28 = 0;
  v18 = (**v26)(v26, &GUID_100eb64b_b24c_4c38_8964_720d926d05a4, &v28);
  v8 = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x699,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)(unsigned int)v18,
      (int)v26);
    v19 = v28;
    if ( v28 )
    {
      v28 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    }
    v20 = v26;
    if ( v26 )
    {
      v26 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v20)[2])(v20);
    }
    goto LABEL_16;
  }
  v21 = (*(__int64 (__fastcall **)(__int64, __int64, WinStoreAuth::AuthenticationInternal *))(*(_QWORD *)v28 + 160LL))(
          v28,
          v29,
          this);
  v8 = v21;
  if ( v21 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x69B,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)(unsigned int)v21,
      (int)v26);
    v22 = v28;
    if ( v28 )
    {
      v28 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    }
    v23 = v26;
    if ( v26 )
    {
      v26 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v23)[2])(v23);
    }
    goto LABEL_16;
  }
  v24 = v28;
  if ( v28 )
  {
    v28 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  }
  v25 = v26;
  if ( v26 )
  {
    v26 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v25)[2])(v25);
  }
  if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(TokenHandle);
  return 0;
}

```

## disassembly

```asm
0x1800400c0  mov     [rsp-18h+arg_8], rbx
0x1800400c5  mov     [rsp-18h+arg_10], rsi
0x1800400ca  push    rbp
0x1800400cb  push    rdi
0x1800400cc  push    r14
0x1800400ce  mov     rbp, rsp
0x1800400d1  sub     rsp, 70h
0x1800400d5  mov     rax, cs:__security_cookie
0x1800400dc  xor     rax, rsp
0x1800400df  mov     [rbp+var_10], rax
0x1800400e3  mov     rsi, rcx
0x1800400e6  xor     r14d, r14d
0x1800400e9  mov     [rbp+var_38], r14
0x1800400ed  mov     [rcx], r14
0x1800400f0  mov     [rbp+TokenHandle], r14
0x1800400f4  call    cs:__imp_GetCurrentThread
0x1800400fa  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800400fe  lea     edx, [r14+0Ch]; DesiredAccess
0x180040102  lea     r8d, [r14+1]; OpenAsSelf
0x180040106  mov     rcx, rax; ThreadHandle
0x180040109  call    cs:__imp_OpenThreadToken
0x18004010f  test    eax, eax
0x180040111  jnz     short loc_18004018C
0x180040113  mov     rdi, [rbp+TokenHandle]
0x180040117  lea     rax, [rdi-1]
0x18004011b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18004011f  ja      short loc_18004013A
0x180040121  call    cs:__imp_GetLastError
0x180040127  mov     ebx, eax
0x180040129  mov     rcx, rdi; hObject
0x18004012c  call    cs:__imp_CloseHandle
0x180040132  mov     ecx, ebx; dwErrCode
0x180040134  call    cs:__imp_SetLastError
0x18004013a  mov     [rbp+TokenHandle], r14
0x18004013e  call    cs:__imp_GetCurrentProcess
0x180040144  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180040148  mov     edx, 0Ch; DesiredAccess
0x18004014d  mov     rcx, rax; ProcessHandle
0x180040150  call    cs:__imp_OpenProcessToken
0x180040156  test    eax, eax
0x180040158  jnz     short loc_18004018C
0x18004015a  mov     rcx, [rbp+18h]; this
0x18004015e  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x180040165  mov     edx, 690h; void *
0x18004016a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18004016f  mov     ebx, eax
0x180040171  mov     rcx, [rbp+TokenHandle]; hObject
0x180040175  lea     rdx, [rcx-1]
0x180040179  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18004017d  ja      short loc_180040185
0x18004017f  call    cs:__imp_CloseHandle
0x180040185  mov     eax, ebx
0x180040187  jmp     loc_180040392
0x18004018c  lea     rdx, [rbp+var_38]
0x180040190  mov     rcx, [rbp+TokenHandle]
0x180040194  call    cs:__imp_UMgrQueryUserContext
0x18004019a  mov     ebx, eax
0x18004019c  test    eax, eax
0x18004019e  jns     short loc_1800401BA
0x1800401a0  mov     rcx, [rbp+18h]; this
0x1800401a4  mov     r9d, eax; char *
0x1800401a7  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x1800401ae  mov     edx, 693h; void *
0x1800401b3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800401b8  jmp     short loc_180040171
0x1800401ba  mov     [rbp+var_50], r14
0x1800401be  mov     [rbp+string], r14
0x1800401c2  lea     r9, [rbp+string]; string
0x1800401c6  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800401ca  mov     edx, 23h ; '#'; length
0x1800401cf  lea     rcx, ?RuntimeClass_Windows_System_Internal_UserManager@@3QBGB; "Windows.System.Internal.UserManager"
0x1800401d6  call    cs:__imp_WindowsCreateStringReference
0x1800401dc  test    eax, eax
0x1800401de  js      loc_1800403B3
0x1800401e4  mov     rbx, [rbp+string]
0x1800401e8  mov     rcx, [rbp+var_50]
0x1800401ec  test    rcx, rcx
0x1800401ef  jz      short loc_180040202
0x1800401f1  mov     [rbp+var_50], r14
0x1800401f5  mov     rax, [rcx]
0x1800401f8  mov     rax, [rax+10h]
0x1800401fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040201  nop
0x180040202  lea     r8, [rbp+var_50]
0x180040206  lea     rdx, _GUID_252e7f79_acfa_4ea2_9a7e_fa27a8a4d3d9
0x18004020d  mov     rcx, rbx
0x180040210  call    cs:__imp_RoGetActivationFactory
0x180040216  mov     ebx, eax
0x180040218  test    eax, eax
0x18004021a  jns     short loc_180040260
0x18004021c  mov     rcx, [rbp+18h]; this
0x180040220  mov     r9d, eax; char *
0x180040223  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18004022a  mov     edx, 696h; void *
0x18004022f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180040234  nop
0x180040235  mov     rcx, [rbp+var_50]
0x180040239  test    rcx, rcx
0x18004023c  jz      short loc_18004024F
0x18004023e  mov     [rbp+var_50], r14
0x180040242  mov     rax, [rcx]
0x180040245  mov     rax, [rax+10h]
0x180040249  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004024e  nop
0x18004024f  mov     rcx, [rbp+TokenHandle]
0x180040253  lea     rax, [rcx-1]
0x180040257  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18004025b  jmp     loc_18004017D
0x180040260  mov     [rbp+var_40], r14
0x180040264  mov     rcx, [rbp+var_50]
0x180040268  mov     rax, [rcx]
0x18004026b  lea     r8, [rbp+var_40]
0x18004026f  lea     rdx, _GUID_100eb64b_b24c_4c38_8964_720d926d05a4
0x180040276  mov     rax, [rax]
0x180040279  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004027e  mov     ebx, eax
0x180040280  test    eax, eax
0x180040282  jns     short loc_1800402D6
0x180040284  mov     rcx, [rbp+18h]; this
0x180040288  mov     r9d, eax; char *
0x18004028b  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x180040292  mov     edx, 699h; void *
0x180040297  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004029c  nop
0x18004029d  mov     rcx, [rbp+var_40]
0x1800402a1  test    rcx, rcx
0x1800402a4  jz      short loc_1800402B7
0x1800402a6  mov     [rbp+var_40], r14
0x1800402aa  mov     rax, [rcx]
0x1800402ad  mov     rax, [rax+10h]
0x1800402b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800402b6  nop
0x1800402b7  mov     rcx, [rbp+var_50]
0x1800402bb  test    rcx, rcx
0x1800402be  jz      short loc_1800402D1
0x1800402c0  mov     [rbp+var_50], r14
0x1800402c4  mov     rax, [rcx]
0x1800402c7  mov     rax, [rax+10h]
0x1800402cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800402d0  nop
0x1800402d1  jmp     loc_18004024F
0x1800402d6  mov     rcx, [rbp+var_40]
0x1800402da  mov     rax, [rcx]
0x1800402dd  mov     r8, rsi
0x1800402e0  mov     rdx, [rbp+var_38]
0x1800402e4  mov     rax, [rax+0A0h]
0x1800402eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800402f0  mov     ebx, eax
0x1800402f2  test    eax, eax
0x1800402f4  jns     short loc_180040348
0x1800402f6  mov     rcx, [rbp+18h]; this
0x1800402fa  mov     r9d, eax; char *
0x1800402fd  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x180040304  mov     edx, 69Bh; void *
0x180040309  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004030e  nop
0x18004030f  mov     rcx, [rbp+var_40]
0x180040313  test    rcx, rcx
0x180040316  jz      short loc_180040329
0x180040318  mov     [rbp+var_40], r14
0x18004031c  mov     rax, [rcx]
0x18004031f  mov     rax, [rax+10h]
0x180040323  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040328  nop
0x180040329  mov     rcx, [rbp+var_50]
0x18004032d  test    rcx, rcx
0x180040330  jz      short loc_180040343
0x180040332  mov     [rbp+var_50], r14
0x180040336  mov     rax, [rcx]
0x180040339  mov     rax, [rax+10h]
0x18004033d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040342  nop
0x180040343  jmp     loc_18004024F
0x180040348  mov     rcx, [rbp+var_40]
0x18004034c  test    rcx, rcx
0x18004034f  jz      short loc_180040362
0x180040351  mov     [rbp+var_40], r14
0x180040355  mov     rax, [rcx]
0x180040358  mov     rax, [rax+10h]
0x18004035c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040361  nop
0x180040362  mov     rcx, [rbp+var_50]
0x180040366  test    rcx, rcx
0x180040369  jz      short loc_18004037C
0x18004036b  mov     [rbp+var_50], r14
0x18004036f  mov     rax, [rcx]
0x180040372  mov     rax, [rax+10h]
0x180040376  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004037b  nop
0x18004037c  mov     rcx, [rbp+TokenHandle]; hObject
0x180040380  lea     rax, [rcx-1]
0x180040384  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180040388  ja      short loc_180040390
0x18004038a  call    cs:__imp_CloseHandle
0x180040390  xor     eax, eax
0x180040392  mov     rcx, [rbp+var_10]
0x180040396  xor     rcx, rsp; StackCookie
0x180040399  call    __security_check_cookie
0x18004039e  lea     r11, [rsp+70h+var_s0]
0x1800403a3  mov     rbx, [r11+28h]
0x1800403a7  mov     rsi, [r11+30h]
0x1800403ab  mov     rsp, r11
0x1800403ae  pop     r14
0x1800403b0  pop     rdi
0x1800403b1  pop     rbp
0x1800403b2  retn
0x1800403b3  mov     ecx, eax; this
0x1800403b5  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
