# _lambda_aa571c738cee2e5ea4b1fd3ab2626ecb_::operator()_wpc::Sync::Internal::SyncLogger::WaitForDesktopShellInit_

- ea: `0x180028f04`
- end: `0x180029198`
- name: `_lambda_aa571c738cee2e5ea4b1fd3ab2626ecb_::operator()_wpc::Sync::Internal::SyncLogger::WaitForDesktopShellInit_`
- size: `660`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002c7e0`

## callees

- `0x1800060a0`
- `0x180006ee0`
- `0x18000d294`
- `0x18000ecc0`
- `0x18001ccf0`
- `0x180028f04`
- `0x180029798`
- `0x18002aed4`
- `0x180035e0c`
- `0x18003ae74`
- `0x1800ae010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029134`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029134`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800290ec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800290ec`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180029019`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180029019`
- `ntdll!NtQueryWnfStateData` at `0x180028f57`
- `ntdll!NtQueryWnfStateData` at `0x180028f57`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void lambda_aa571c738cee2e5ea4b1fd3ab2626ecb_::operator()_wpc::Sync::Internal::SyncLogger::WaitForDesktopShellInit_()
{
  int v0; // edi
  bool v1; // si
  unsigned int v2; // ebx
  __int64 v3; // rcx
  int v4; // eax
  char *v5; // rbx
  signed int LastError; // eax
  unsigned int v7; // ebx
  int v8; // [rsp+20h] [rbp-E0h]
  int v9; // [rsp+20h] [rbp-E0h]
  char *v10; // [rsp+30h] [rbp-D0h] BYREF
  char *v11; // [rsp+38h] [rbp-C8h] BYREF
  void **v12; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE hObject; // [rsp+48h] [rbp-B8h]
  _BYTE pExceptionObject[40]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v15[8]; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v16[13]; // [rsp+80h] [rbp-80h] BYREF
  _QWORD *v17; // [rsp+E8h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+28h]

  LODWORD(v10) = 0;
  LODWORD(v11) = 0;
  v8 = 0;
  v0 = NtQueryWnfStateData(&WNF_SHEL_LOGON_COMPLETE, 0, 0, &v11) | 0x10000000;
  if ( (int)(v0 + 0x80000000) < 0 || v0 == -805306333 )
  {
    LOBYTE(v8) = 0;
    wil::details::in1diag3::Log_HrIfMsg(
      retaddr,
      (void *)0x2AC,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\Resource.h",
      (const char *)0x8000FFFFLL,
      v8,
      (bool)"Inconsistent state data size in wnf_query",
      v10);
    v2 = (unsigned int)v11;
    v1 = (_DWORD)v11 && !(_DWORD)v10;
    v0 = 0;
  }
  else
  {
    v1 = 0;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2AA,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\Resource.h",
      (const char *)(unsigned int)v0,
      0);
    v2 = 0;
  }
  if ( v0 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x353,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\Resource.h",
      (const char *)(unsigned int)v0,
      v9);
  if ( !v1 )
  {
    v12 = &Threading::Event::`vftable';
    hObject = CreateEventW(0, 0, 0, 0);
    if ( !hObject )
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 11, WPP_594e823998983b615095027d76415771_Traceguids, v7);
      ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v7);
      throw (ErrorCodeException *)pExceptionObject;
    }
    v16[0] = &wistd::__function::__func<_lambda_e7c533f4004fa4ddf71b293f5524a2bd_,void (void)>::`vftable';
    v16[1] = &v12;
    v17 = v16;
    v10 = 0;
    v4 = wil::details::make_wnf_subscription_state<wil::details::empty_wnf_state>(v3, v15, v2, &v10);
    if ( v4 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x43C,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\Resource.h",
        (const char *)(unsigned int)v4,
        v9);
    v5 = v10;
    v11 = v10;
    if ( v17 )
      (*(void (__fastcall **)(_QWORD *))(*v17 + 24LL))(v17);
    v10 = (char *)((__int64 (__fastcall *)(void ***))v12[1])(&v12);
    Private::WaitImpl(&v10, &v11, qword_180107A30, 1);
    if ( v5 )
      (**(void (__fastcall ***)(char *, __int64))v5)(v5, 1);
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
  }
}

```

## disassembly

```asm
0x180028f04  push    rbp
0x180028f06  push    rbx
0x180028f07  push    rsi
0x180028f08  push    rdi
0x180028f09  lea     rbp, [rsp-8]
0x180028f0e  sub     rsp, 108h
0x180028f15  mov     rax, cs:__security_cookie
0x180028f1c  xor     rax, rsp
0x180028f1f  mov     [rbp+20h+var_30], rax
0x180028f23  mov     dword ptr [rsp+120h+var_F0], 0; char *
0x180028f2b  mov     dword ptr [rsp+120h+var_E8], 0
0x180028f33  lea     rax, [rsp+120h+var_F0]
0x180028f38  mov     qword ptr [rsp+120h+var_F8], rax
0x180028f3d  mov     qword ptr [rsp+120h+var_100], 0; int
0x180028f46  lea     r9, [rsp+120h+var_E8]
0x180028f4b  xor     r8d, r8d
0x180028f4e  xor     edx, edx
0x180028f50  lea     rcx, WNF_SHEL_LOGON_COMPLETE
0x180028f57  call    cs:__imp_NtQueryWnfStateData
0x180028f5d  mov     edi, eax
0x180028f5f  bts     edi, 1Ch
0x180028f63  mov     ecx, 80000000h
0x180028f68  lea     eax, [rdi+rcx]
0x180028f6b  test    ecx, eax
0x180028f6d  jnz     short loc_180028F96
0x180028f6f  cmp     edi, 0D0000023h
0x180028f75  jz      short loc_180028F96
0x180028f77  xor     sil, sil
0x180028f7a  mov     rcx, [rbp+28h]; this
0x180028f7e  mov     r9d, edi; char *
0x180028f81  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\Resou"...
0x180028f88  mov     edx, 2AAh; void *
0x180028f8d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028f92  xor     ebx, ebx
0x180028f94  jmp     short loc_180028FEE
0x180028f96  cmp     dword ptr [rsp+120h+var_E8], 0
0x180028f9b  jz      short loc_180028FA8
0x180028f9d  cmp     dword ptr [rsp+120h+var_F0], 0
0x180028fa2  jz      short loc_180028FA8
0x180028fa4  mov     al, 1
0x180028fa6  jmp     short loc_180028FAA
0x180028fa8  xor     eax, eax
0x180028faa  mov     rcx, [rbp+28h]; this
0x180028fae  lea     rdx, aInconsistentSt; "Inconsistent state data size in wnf_que"...
0x180028fb5  mov     qword ptr [rsp+120h+var_F8], rdx; bool
0x180028fba  mov     byte ptr [rsp+120h+var_100], al; int
0x180028fbe  mov     r9d, 8000FFFFh; char *
0x180028fc4  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\Resou"...
0x180028fcb  mov     edx, 2ACh; void *
0x180028fd0  call    ?Log_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Log_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180028fd5  mov     ebx, dword ptr [rsp+120h+var_E8]
0x180028fd9  test    ebx, ebx
0x180028fdb  jz      short loc_180028FE9
0x180028fdd  cmp     dword ptr [rsp+120h+var_F0], 0
0x180028fe2  jnz     short loc_180028FE9
0x180028fe4  mov     sil, 1
0x180028fe7  jmp     short loc_180028FEC
0x180028fe9  xor     sil, sil
0x180028fec  xor     edi, edi
0x180028fee  mov     rcx, [rbp+28h]; this
0x180028ff2  test    edi, edi
0x180028ff4  js      loc_18002911F
0x180028ffa  test    sil, sil
0x180028ffd  jnz     loc_1800290F2
0x180029003  lea     rax, ??_7Event@Threading@@6B@; const Threading::Event::`vftable'
0x18002900a  mov     [rsp+120h+var_E0], rax
0x18002900f  xor     r9d, r9d; lpName
0x180029012  xor     r8d, r8d; bInitialState
0x180029015  xor     edx, edx; bManualReset
0x180029017  xor     ecx, ecx; lpEventAttributes
0x180029019  call    cs:__imp_CreateEventW
0x18002901f  mov     [rsp+120h+hObject], rax
0x180029024  test    rax, rax
0x180029027  jz      loc_180029134
0x18002902d  lea     rax, ??_7?$__func@V_lambda_e7c533f4004fa4ddf71b293f5524a2bd_@@$$A6AXXZ@__function@wistd@@6B@; const wistd::__function::__func<_lambda_e7c533f4004fa4ddf71b293f5524a2bd_,void (void)>::`vftable'
0x180029034  mov     [rbp+20h+var_A0], rax
0x180029038  lea     rax, [rsp+120h+var_E0]
0x18002903d  mov     [rbp+20h+var_98], rax
0x180029041  lea     rax, [rbp+20h+var_A0]
0x180029045  mov     [rbp+20h+var_38], rax
0x180029049  mov     [rsp+120h+var_F0], 0
0x180029052  lea     r9, [rsp+120h+var_F0]
0x180029057  mov     r8d, ebx
0x18002905a  lea     rdx, [rsp+120h+var_A8]
0x18002905f  call    ??$make_wnf_subscription_state@Uempty_wnf_state@details@wil@@@details@wil@@YAJAEBU_WNF_STATE_NAME@@$$QEAV?$function@$$A6AXXZ@wistd@@KPEAPEAU?$wnf_subscription_state@Uempty_wnf_state@details@wil@@@01@@Z; wil::details::make_wnf_subscription_state<wil::details::empty_wnf_state>(_WNF_STATE_NAME const &,wistd::function<void (void)> &&,ulong,wil::details::wnf_subscription_state<wil::details::empty_wnf_state> * *)
0x180029064  mov     rcx, [rbp+28h]; this
0x180029068  test    eax, eax
0x18002906a  js      loc_18002910A
0x180029070  mov     rbx, [rsp+120h+var_F0]
0x180029075  mov     [rsp+120h+var_E8], rbx
0x18002907a  mov     rcx, [rbp+20h+var_38]
0x18002907e  test    rcx, rcx
0x180029081  jz      short loc_18002908F
0x180029083  mov     rax, [rcx]
0x180029086  mov     rax, [rax+18h]
0x18002908a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002908f  mov     rax, [rsp+120h+var_E0]
0x180029094  lea     rcx, [rsp+120h+var_E0]
0x180029099  mov     rax, [rax+8]
0x18002909d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800290a2  mov     [rsp+120h+var_F0], rax
0x1800290a7  mov     r9d, 1
0x1800290ad  lea     r8, qword_180107A30
0x1800290b4  lea     rdx, [rsp+120h+var_E8]
0x1800290b9  lea     rcx, [rsp+120h+var_F0]
0x1800290be  call    ?WaitImpl@Private@@YA_NPEBQEAX0AEBV?$Optional@VTimeSpan@@@@W4WaitType@1@@Z; Private::WaitImpl(void * const *,void * const *,Optional<TimeSpan> const &,Private::WaitType)
0x1800290c3  nop
0x1800290c4  test    rbx, rbx
0x1800290c7  jz      short loc_1800290DD
0x1800290c9  mov     rax, [rbx]
0x1800290cc  mov     edx, 1
0x1800290d1  mov     rcx, rbx
0x1800290d4  mov     rax, [rax]
0x1800290d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800290dc  nop
0x1800290dd  mov     rcx, [rsp+120h+hObject]; hObject
0x1800290e2  lea     rax, [rcx-1]
0x1800290e6  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800290ea  ja      short loc_1800290F2
0x1800290ec  call    cs:__imp_CloseHandle
0x1800290f2  mov     rcx, [rbp+20h+var_30]
0x1800290f6  xor     rcx, rsp; StackCookie
0x1800290f9  call    __security_check_cookie
0x1800290fe  add     rsp, 108h
0x180029105  pop     rdi
0x180029106  pop     rsi
0x180029107  pop     rbx
0x180029108  pop     rbp
0x180029109  retn
0x18002910a  mov     r9d, eax; char *
0x18002910d  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\Resou"...
0x180029114  mov     edx, 43Ch; void *
0x180029119  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002911f  mov     r9d, edi; char *
0x180029122  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\Resou"...
0x180029129  mov     edx, 353h; void *
0x18002912e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180029134  call    cs:__imp_GetLastError
0x18002913a  mov     ebx, eax
0x18002913c  test    eax, eax
0x18002913e  jle     short loc_180029149
0x180029140  movzx   ebx, ax
0x180029143  or      ebx, 80070000h
0x180029149  lea     rax, WPP_GLOBAL_Control
0x180029150  mov     rcx, cs:WPP_GLOBAL_Control
0x180029157  cmp     rcx, rax
0x18002915a  jz      short loc_18002917A
0x18002915c  test    byte ptr [rcx+1Ch], 1
0x180029160  jz      short loc_18002917A
0x180029162  mov     edx, 0Bh
0x180029167  mov     r9d, ebx
0x18002916a  lea     r8, WPP_594e823998983b615095027d76415771_Traceguids
0x180029171  mov     rcx, [rcx+10h]
0x180029175  call    WPP_SF_d
0x18002917a  mov     edx, ebx; int
0x18002917c  lea     rcx, [rsp+120h+pExceptionObject]; this
0x180029181  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x180029186  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x18002918d  lea     rcx, [rsp+120h+pExceptionObject]; pExceptionObject
0x180029192  call    _CxxThrowException_0
```
