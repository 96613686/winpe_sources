# Microsoft::Diagnostics::EscalationWorkItem::CreateActionDirectory(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,Microsoft::Diagnostics::IActionDef const &,bool,Microsoft::Diagnostics::EscalationWorkItemState const &,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &)

- ea: `0x18009c1dc`
- end: `0x18009c4a8`
- name: `?CreateActionDirectory@EscalationWorkItem@Diagnostics@Microsoft@@AEAAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBVIActionDef@23@_NAEBVEscalationWorkItemState@23@AEAV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Z`
- size: `716`
- prototype: ``
- caller_count: `2`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18016add0`
- `0x18016e098`

## callees

- `0x180020150`
- `0x18002cae0`
- `0x18002df00`
- `0x180064e34`
- `0x180064e6c`
- `0x180064e8c`
- `0x180081924`
- `0x18008abf4`
- `0x18009c1dc`
- `0x18009c4b0`
- `0x18009c6bc`
- `0x18009c7e4`
- `0x18009c8c0`
- `0x1800f9c3c`
- `0x1801abcac`
- `0x1801c2d0c`
- `0x18020aac0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009c414`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009c414`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009c38e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009c38e`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18009c3f0`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18009c3f0`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18009c46b`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18009c46b`

## string_xrefs

- `0x18009c3db`: `onecore\base\telemetry\utc\service\scenarios\base\escalationworkitem.cpp`
- `0x18009c402`: `onecore\base\telemetry\utc\service\scenarios\base\escalationworkitem.cpp`
- `0x18009c436`: `onecore\base\telemetry\utc\service\scenarios\base\escalationworkitem.cpp`
- `0x18009c458`: `onecore\base\telemetry\utc\service\scenarios\base\escalationworkitem.cpp`
- `0x18009c47d`: `onecore\base\telemetry\utc\service\scenarios\base\escalationworkitem.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Microsoft::Diagnostics::EscalationWorkItem::CreateActionDirectory(
        __int64 a1,
        _QWORD *a2,
        _QWORD *a3,
        char a4,
        __int64 a5,
        void **a6)
{
  _QWORD *v9; // rcx
  int appended; // eax
  unsigned int v11; // ebx
  __int64 v12; // r8
  _QWORD *v13; // rax
  _QWORD *v14; // rax
  char *v15; // rcx
  const char *v17; // r9
  DWORD LastError; // eax
  int v19; // eax
  const char *v20; // r9
  ULONG v21; // [rsp+20h] [rbp-59h]
  ULONG v22; // [rsp+20h] [rbp-59h]
  int v23[4]; // [rsp+30h] [rbp-49h] BYREF
  __int64 v24; // [rsp+40h] [rbp-39h]
  HLOCAL hMem; // [rsp+50h] [rbp-29h] BYREF
  int v26[4]; // [rsp+58h] [rbp-21h] BYREF
  __int64 v27; // [rsp+68h] [rbp-11h]
  _QWORD Src[4]; // [rsp+70h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+4Fh]

  std::wstring::operator=(a2, a1 + 544);
  if ( a3[14] <= 7u )
    v9 = a3 + 11;
  else
    v9 = (_QWORD *)a3[11];
  *(_QWORD *)v23 = v9;
  *(_QWORD *)&v23[2] = a3[13];
  appended = Microsoft::Diagnostics::Utils::String::AppendPath(a2, v23);
  v11 = appended;
  if ( appended < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x22E,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\escalationworkitem.cpp",
      (const char *)(unsigned int)appended,
      v21);
    return v11;
  }
  if ( (unsigned __int64)(*(_QWORD *)(a5 + 224) - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL && !RevertToSelf() )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0x233,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\escalationworkitem.cpp",
      v17);
  std::wstring::wstring(Src);
  std::wstring::_Append<wchar_t>(Src);
  if ( *(_QWORD *)(a5 + 248) )
  {
    std::wstring::append(Src, L"(A;OICI;GA;;;");
    std::wstring::operator std::wstring_view(a5 + 232, v23, v12);
    std::wstring::_Append<wchar_t>(Src);
    std::wstring::append(Src, L")");
  }
  v13 = Src;
  if ( Src[3] > 7u )
    v13 = (_QWORD *)Src[0];
  *(_QWORD *)v23 = v13;
  *(_QWORD *)&v23[2] = Src[2];
  Microsoft::Diagnostics::Utils::Os::CreateSecurityDecriptorFromSddl(&hMem);
  *(_QWORD *)v23 = 24;
  *(_QWORD *)&v23[2] = hMem;
  v24 = 0;
  *(_OWORD *)v26 = *(_OWORD *)v23;
  v27 = 0;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    a6,
    -1);
  if ( a2[3] <= 7u )
    v14 = a2;
  else
    v14 = (_QWORD *)*a2;
  *(_QWORD *)v23 = v14;
  *(_QWORD *)&v23[2] = a2[2];
  if ( !(unsigned int)CreateDirectoryAndGetHandle((__int64 *)v23, (__int64)v26, a6, 393216, 3u) )
  {
    LastError = GetLastError();
    if ( LastError == 183 )
    {
      if ( a4 )
      {
        v11 = -2017128401;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x255,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\escalationworkitem.cpp",
          (const char *)0x87C5102FLL,
          v22);
LABEL_30:
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(&hMem);
        std::wstring::_Tidy_deallocate(Src);
        return v11;
      }
    }
    else if ( LastError )
    {
      v19 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x259,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\escalationworkitem.cpp",
              (const char *)LastError,
              v22);
LABEL_29:
      v11 = v19;
      goto LABEL_30;
    }
  }
  v15 = *(char **)(a5 + 224);
  if ( (unsigned __int64)(v15 - 1) <= 0xFFFFFFFFFFFFFFFDuLL && !ImpersonateLoggedOnUser(v15) )
  {
    v19 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)0x260,
            (unsigned int)"onecore\\base\\telemetry\\utc\\service\\scenarios\\base\\escalationworkitem.cpp",
            v20);
    goto LABEL_29;
  }
  if ( hMem )
    LocalFree(hMem);
  std::wstring::_Tidy_deallocate(Src);
  return 0;
}

```

## disassembly

```asm
0x18009c1dc  mov     [rsp-8+arg_10], rbx
0x18009c1e1  push    rbp
0x18009c1e2  push    rsi
0x18009c1e3  push    rdi
0x18009c1e4  push    r14
0x18009c1e6  push    r15
0x18009c1e8  lea     rbp, [rsp-27h]
0x18009c1ed  sub     rsp, 0A0h
0x18009c1f4  mov     rax, cs:__security_cookie
0x18009c1fb  xor     rax, rsp
0x18009c1fe  mov     [rbp+47h+var_30], rax
0x18009c202  mov     r14b, r9b
0x18009c205  mov     rbx, r8
0x18009c208  mov     rdi, rdx
0x18009c20b  mov     rsi, [rbp+47h+arg_20]
0x18009c20f  mov     r15, qword ptr [rbp+47h+arg_28]
0x18009c213  lea     rdx, [rcx+220h]
0x18009c21a  mov     rcx, rdi
0x18009c21d  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18009c222  cmp     qword ptr [rbx+70h], 7
0x18009c227  jbe     loc_18009C3C3
0x18009c22d  mov     rcx, [rbx+58h]
0x18009c231  mov     qword ptr [rbp+47h+var_90], rcx
0x18009c235  mov     rax, [rbx+68h]
0x18009c239  mov     qword ptr [rbp+47h+var_90+8], rax
0x18009c23d  lea     rdx, [rbp+47h+var_90]
0x18009c241  mov     rcx, rdi
0x18009c244  call    ?AppendPath@String@Utils@Diagnostics@Microsoft@@SAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_string_view@_WU?$char_traits@_W@std@@@6@K@Z; Microsoft::Diagnostics::Utils::String::AppendPath(std::wstring &,std::wstring_view,ulong)
0x18009c249  mov     ebx, eax
0x18009c24b  test    eax, eax
0x18009c24d  js      loc_18009C3D4
0x18009c253  mov     rax, [rsi+0E0h]
0x18009c25a  dec     rax
0x18009c25d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18009c261  jbe     loc_18009C3F0
0x18009c267  lea     rcx, [rbp+47h+Src]; void *
0x18009c26b  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18009c270  nop
0x18009c271  mov     r8d, 41h ; 'A'
0x18009c277  mov     rdx, cs:off_18036C4F8; "O:BAD:P(A;OICI;GA;;;BA)(A;OICI;GA;;;S-1"...
0x18009c27e  lea     rcx, [rbp+47h+Src]; Src
0x18009c282  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x18009c287  lea     rbx, [rsi+0E8h]
0x18009c28e  cmp     qword ptr [rbx+10h], 0
0x18009c293  jz      short loc_18009C2D2
0x18009c295  lea     rdx, aAOiciGa; "(A;OICI;GA;;;"
0x18009c29c  lea     rcx, [rbp+47h+Src]
0x18009c2a0  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::append(wchar_t const * const)
0x18009c2a5  lea     rdx, [rbp+47h+var_90]
0x18009c2a9  mov     rcx, rbx
0x18009c2ac  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x18009c2b1  mov     r8, qword ptr [rbp+47h+var_90+8]
0x18009c2b5  mov     rdx, qword ptr [rbp+47h+var_90]
0x18009c2b9  lea     rcx, [rbp+47h+Src]; Src
0x18009c2bd  call    ??$_Append@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Append<wchar_t>(wchar_t const * const,unsigned __int64)
0x18009c2c2  lea     rdx, asc_180393764; ")"
0x18009c2c9  lea     rcx, [rbp+47h+Src]
0x18009c2cd  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::append(wchar_t const * const)
0x18009c2d2  lea     rax, [rbp+47h+Src]
0x18009c2d6  cmp     [rbp+47h+var_38], 7
0x18009c2db  cmova   rax, [rbp+47h+Src]
0x18009c2e0  mov     qword ptr [rbp+47h+var_90], rax
0x18009c2e4  mov     rax, [rbp+47h+var_40]
0x18009c2e8  mov     qword ptr [rbp+47h+var_90+8], rax
0x18009c2ec  lea     rdx, [rbp+47h+var_90]
0x18009c2f0  lea     rcx, [rbp+47h+hMem]; SecurityDescriptor
0x18009c2f4  call    ?CreateSecurityDecriptorFromSddl@Os@Utils@Diagnostics@Microsoft@@SA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; Microsoft::Diagnostics::Utils::Os::CreateSecurityDecriptorFromSddl(std::wstring_view)
0x18009c2f9  nop
0x18009c2fa  mov     qword ptr [rbp+47h+var_90], 18h
0x18009c302  mov     rax, [rbp+47h+hMem]
0x18009c306  mov     qword ptr [rbp+47h+var_90+8], rax
0x18009c30a  mov     [rbp+47h+var_80], 0
0x18009c312  movups  xmm0, xmmword ptr [rbp+47h+var_90]
0x18009c316  movups  xmmword ptr [rbp+47h+var_68], xmm0
0x18009c31a  movsd   xmm1, [rbp+47h+var_80]
0x18009c31f  movsd   [rbp+47h+var_58], xmm1
0x18009c324  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18009c328  mov     rcx, r15
0x18009c32b  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18009c330  cmp     qword ptr [rdi+18h], 7
0x18009c335  jbe     loc_18009C3CC
0x18009c33b  mov     rax, [rdi]
0x18009c33e  mov     qword ptr [rbp+47h+var_90], rax
0x18009c342  mov     rax, [rdi+10h]
0x18009c346  mov     qword ptr [rbp+47h+var_90+8], rax
0x18009c34a  mov     [rsp+0C0h+var_A0], 3; unsigned int
0x18009c352  mov     r9d, 60000h; int
0x18009c358  mov     r8, r15; int
0x18009c35b  lea     rdx, [rbp+47h+var_68]; int
0x18009c35f  lea     rcx, [rbp+47h+var_90]; int
0x18009c363  call    ?CreateDirectoryAndGetHandle@@YAHV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@PEBU_SECURITY_ATTRIBUTES@@PEAPEAXKK@Z; CreateDirectoryAndGetHandle(std::wstring_view,_SECURITY_ATTRIBUTES const *,void * *,ulong,ulong)
0x18009c368  test    eax, eax
0x18009c36a  jz      loc_18009C414
0x18009c370  mov     rcx, [rsi+0E0h]; hToken
0x18009c377  lea     rax, [rcx-1]
0x18009c37b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18009c37f  jbe     loc_18009C46B
0x18009c385  mov     rcx, [rbp+47h+hMem]; hMem
0x18009c389  test    rcx, rcx
0x18009c38c  jz      short loc_18009C395
0x18009c38e  call    cs:__imp_LocalFree
0x18009c394  nop
0x18009c395  lea     rcx, [rbp+47h+Src]
0x18009c399  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18009c39e  xor     eax, eax
0x18009c3a0  mov     rcx, [rbp+47h+var_30]
0x18009c3a4  xor     rcx, rsp; StackCookie
0x18009c3a7  call    __security_check_cookie
0x18009c3ac  mov     rbx, [rsp+0C0h+arg_10]
0x18009c3b4  add     rsp, 0A0h
0x18009c3bb  pop     r15
0x18009c3bd  pop     r14
0x18009c3bf  pop     rdi
0x18009c3c0  pop     rsi
0x18009c3c1  pop     rbp
0x18009c3c2  retn
0x18009c3c3  lea     rcx, [rbx+58h]
0x18009c3c7  jmp     loc_18009C231
0x18009c3cc  mov     rax, rdi
0x18009c3cf  jmp     loc_18009C33E
0x18009c3d4  mov     rcx, [rbp+4Fh]; this
0x18009c3d8  mov     r9d, ebx; char *
0x18009c3db  lea     r8, aOnecoreBaseTel_134; "onecore\\base\\telemetry\\utc\\service"...
0x18009c3e2  mov     edx, 22Eh; void *
0x18009c3e7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009c3ec  mov     eax, ebx
0x18009c3ee  jmp     short loc_18009C3A0
0x18009c3f0  call    cs:__imp_RevertToSelf
0x18009c3f6  mov     rcx, [rbp+4Fh]; this
0x18009c3fa  test    eax, eax
0x18009c3fc  jnz     loc_18009C267
0x18009c402  lea     r8, aOnecoreBaseTel_134; "onecore\\base\\telemetry\\utc\\service"...
0x18009c409  mov     edx, 233h; void *
0x18009c40e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18009c414  call    cs:__imp_GetLastError
0x18009c41a  cmp     eax, 0B7h
0x18009c41f  jnz     short loc_18009C449
0x18009c421  test    r14b, r14b
0x18009c424  jz      loc_18009C370
0x18009c42a  mov     rcx, [rbp+4Fh]; this
0x18009c42e  mov     ebx, 87C5102Fh
0x18009c433  mov     r9d, ebx; char *
0x18009c436  lea     r8, aOnecoreBaseTel_134; "onecore\\base\\telemetry\\utc\\service"...
0x18009c43d  mov     edx, 255h; void *
0x18009c442  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009c447  jmp     short loc_18009C490
0x18009c449  test    eax, eax
0x18009c44b  jz      loc_18009C370
0x18009c451  mov     rcx, [rbp+4Fh]; this
0x18009c455  mov     r9d, eax; char *
0x18009c458  lea     r8, aOnecoreBaseTel_134; "onecore\\base\\telemetry\\utc\\service"...
0x18009c45f  mov     edx, 259h; void *
0x18009c464  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18009c469  jmp     short loc_18009C48E
0x18009c46b  call    cs:__imp_ImpersonateLoggedOnUser
0x18009c471  test    eax, eax
0x18009c473  jnz     loc_18009C385
0x18009c479  mov     rcx, [rbp+4Fh]; this
0x18009c47d  lea     r8, aOnecoreBaseTel_134; "onecore\\base\\telemetry\\utc\\service"...
0x18009c484  mov     edx, 260h; void *
0x18009c489  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18009c48e  mov     ebx, eax
0x18009c490  lea     rcx, [rbp+47h+hMem]
0x18009c494  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>(void)
0x18009c499  nop
0x18009c49a  lea     rcx, [rbp+47h+Src]
0x18009c49e  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18009c4a3  jmp     loc_18009C3EC
```
