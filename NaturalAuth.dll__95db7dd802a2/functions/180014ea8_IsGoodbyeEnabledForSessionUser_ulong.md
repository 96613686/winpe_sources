# IsGoodbyeEnabledForSessionUser(ulong)

- ea: `0x180014ea8`
- end: `0x180015178`
- name: `?IsGoodbyeEnabledForSessionUser@@YA_NK@Z`
- size: `720`
- prototype: `bool __fastcall(ULONG SessionId)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180013f30`

## callees

- `0x1800011c0`
- `0x18000129c`
- `0x1800058b4`
- `0x18000a7d0`
- `0x18000a7f8`
- `0x1800129e8`
- `0x180012a48`
- `0x180012b50`
- `0x180012b74`
- `0x180014ea8`
- `0x18001c4bc`
- `0x180021980`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014f56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014f95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800150d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014f56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014f95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800150d8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180015077`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180015077`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180014ffa`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180014ffa`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800150bc`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800150bc`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180014f8b`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180014f8b`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x180014f41`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x180014f41`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool __fastcall IsGoodbyeEnabledForSessionUser(ULONG SessionId)
{
  bool v2; // si
  BOOL v3; // ebx
  DWORD LastError; // eax
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  unsigned int v7; // r14d
  unsigned int v8; // eax
  NaturalAuthTraceLogging *v9; // rcx
  unsigned int ActivityId; // eax
  int v11; // r9d
  BYTE Data[4]; // [rsp+30h] [rbp-30h] BYREF
  ULONG v14; // [rsp+34h] [rbp-2Ch] BYREF
  HKEY hKey; // [rsp+38h] [rbp-28h] BYREF
  HANDLE hToken; // [rsp+40h] [rbp-20h] BYREF
  void *p_hToken; // [rsp+48h] [rbp-18h] BYREF
  void *phToken; // [rsp+50h] [rbp-10h] BYREF
  char v19; // [rsp+58h] [rbp-8h]
  bool v20; // [rsp+98h] [rbp+38h] BYREF
  DWORD cbData; // [rsp+A0h] [rbp+40h] BYREF
  DWORD Type; // [rsp+A8h] [rbp+48h] BYREF

  hToken = 0;
  v2 = 0;
  hKey = 0;
  cbData = 0;
  Type = 0;
  *(_DWORD *)Data = 0;
  if ( !(unsigned __int8)IsWTSQueryUserTokenPresent() )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_a55972c0645036c47bb3e826c72e1456_Traceguids);
    goto LABEL_28;
  }
  phToken = 0;
  p_hToken = &hToken;
  v19 = 1;
  v3 = WTSQueryUserToken(SessionId, &phToken);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&p_hToken);
  if ( !v3 )
  {
    LastError = GetLastError();
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_28;
    v6 = 11;
    goto LABEL_27;
  }
  if ( !ImpersonateLoggedOnUser(hToken) )
  {
    LastError = GetLastError();
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_28;
    v6 = 12;
LABEL_27:
    WPP_SF_d(v5[2], v6, &WPP_a55972c0645036c47bb3e826c72e1456_Traceguids, LastError);
    goto LABEL_28;
  }
  phToken = 0;
  p_hToken = &hKey;
  v19 = 1;
  v7 = RegOpenKeyExW(
         HKEY_CURRENT_USER,
         L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon",
         0,
         0x20019u,
         (PHKEY)&phToken);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hToken);
  if ( v7 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_a55972c0645036c47bb3e826c72e1456_Traceguids, v7);
  }
  else
  {
    cbData = 4;
    v8 = RegQueryValueExW(hKey, L"EnableGoodbye", 0, &Type, Data, &cbData);
    if ( v8 || Type != 4 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_ll(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, Type, v8, Type);
    }
    else
    {
      v2 = *(_DWORD *)Data != 0;
    }
  }
  if ( !RevertToSelf() && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    LastError = GetLastError();
    v5 = WPP_GLOBAL_Control;
    v6 = 15;
    goto LABEL_27;
  }
LABEL_28:
  if ( (unsigned int)dword_18005C570 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18005C570, 0x400000000000LL) )
  {
    v14 = SessionId;
    v20 = v2;
    ActivityId = (unsigned int)NaturalAuthTraceLogging::GetActivityId(v9);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<1>,_tlgWrapperByVal<4>>(
      (unsigned int)&dword_18005C570,
      (unsigned int)byte_18004F8AD,
      ActivityId,
      v11,
      (__int64)&v20,
      (__int64)&v14);
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hToken);
  return v2;
}

```

## disassembly

```asm
0x180014ea8  push    rbp
0x180014eaa  push    rbx
0x180014eab  push    rsi
0x180014eac  push    r14
0x180014eae  push    r15
0x180014eb0  mov     rbp, rsp
0x180014eb3  sub     rsp, 60h
0x180014eb7  mov     r15d, ecx
0x180014eba  mov     [rbp+hToken], 0
0x180014ec2  xor     sil, sil
0x180014ec5  mov     [rbp+hKey], 0
0x180014ecd  mov     [rbp+cbData], 0
0x180014ed4  mov     [rbp+Type], 0
0x180014edb  mov     dword ptr [rbp+Data], 0
0x180014ee2  call    IsWTSQueryUserTokenPresent
0x180014ee7  test    al, al
0x180014ee9  jnz     short loc_180014F26
0x180014eeb  mov     rcx, cs:WPP_GLOBAL_Control
0x180014ef2  lea     rbx, WPP_GLOBAL_Control
0x180014ef9  cmp     rcx, rbx
0x180014efc  jz      loc_1800150FD
0x180014f02  test    byte ptr [rcx+1Ch], 1
0x180014f06  jz      loc_1800150FD
0x180014f0c  mov     rcx, [rcx+10h]
0x180014f10  lea     r8, WPP_a55972c0645036c47bb3e826c72e1456_Traceguids
0x180014f17  mov     edx, 0Ah
0x180014f1c  call    WPP_SF_
0x180014f21  jmp     loc_1800150FD
0x180014f26  lea     rax, [rbp+hToken]
0x180014f2a  mov     [rbp+phToken], 0
0x180014f32  lea     rdx, [rbp+phToken]; phToken
0x180014f36  mov     [rbp+var_18], rax
0x180014f3a  mov     ecx, r15d; SessionId
0x180014f3d  mov     [rbp+var_8], 1
0x180014f41  call    cs:__imp_WTSQueryUserToken
0x180014f47  lea     rcx, [rbp+var_18]
0x180014f4b  mov     ebx, eax
0x180014f4d  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x180014f52  test    ebx, ebx
0x180014f54  jnz     short loc_180014F87
0x180014f56  call    cs:__imp_GetLastError
0x180014f5c  mov     rcx, cs:WPP_GLOBAL_Control
0x180014f63  lea     rbx, WPP_GLOBAL_Control
0x180014f6a  cmp     rcx, rbx
0x180014f6d  jz      loc_1800150FD
0x180014f73  test    byte ptr [rcx+1Ch], 1
0x180014f77  jz      loc_1800150FD
0x180014f7d  mov     edx, 0Bh
0x180014f82  jmp     loc_1800150EA
0x180014f87  mov     rcx, [rbp+hToken]; hToken
0x180014f8b  call    cs:__imp_ImpersonateLoggedOnUser
0x180014f91  test    eax, eax
0x180014f93  jnz     short loc_180014FC6
0x180014f95  call    cs:__imp_GetLastError
0x180014f9b  mov     rcx, cs:WPP_GLOBAL_Control
0x180014fa2  lea     rbx, WPP_GLOBAL_Control
0x180014fa9  cmp     rcx, rbx
0x180014fac  jz      loc_1800150FD
0x180014fb2  test    byte ptr [rcx+1Ch], 1
0x180014fb6  jz      loc_1800150FD
0x180014fbc  mov     edx, 0Ch
0x180014fc1  jmp     loc_1800150EA
0x180014fc6  lea     rax, [rbp+hKey]
0x180014fca  mov     [rbp+phToken], 0
0x180014fd2  mov     [rbp+var_18], rax
0x180014fd6  lea     rdx, SubKey; "Software\\Microsoft\\Windows NT\\Curren"...
0x180014fdd  lea     rax, [rbp+phToken]
0x180014fe1  mov     [rbp+var_8], 1
0x180014fe5  mov     r9d, 20019h; samDesired
0x180014feb  mov     [rsp+60h+phkResult], rax; phkResult
0x180014ff0  xor     r8d, r8d; ulOptions
0x180014ff3  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180014ffa  call    cs:__imp_RegOpenKeyExW
0x180015000  lea     rcx, [rbp+var_18]
0x180015004  mov     r14d, eax
0x180015007  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x18001500c  lea     rbx, WPP_GLOBAL_Control
0x180015013  test    r14d, r14d
0x180015016  jz      short loc_18001504C
0x180015018  mov     rcx, cs:WPP_GLOBAL_Control
0x18001501f  cmp     rcx, rbx
0x180015022  jz      loc_1800150BC
0x180015028  test    byte ptr [rcx+1Ch], 1
0x18001502c  jz      loc_1800150BC
0x180015032  mov     rcx, [rcx+10h]
0x180015036  lea     r8, WPP_a55972c0645036c47bb3e826c72e1456_Traceguids
0x18001503d  mov     edx, 0Dh
0x180015042  mov     r9d, r14d
0x180015045  call    WPP_SF_d
0x18001504a  jmp     short loc_1800150BC
0x18001504c  mov     rcx, [rbp+hKey]; hKey
0x180015050  lea     rax, [rbp+cbData]
0x180015054  mov     [rsp+60h+lpcbData], rax; lpcbData
0x180015059  lea     r9, [rbp+Type]; lpType
0x18001505d  lea     rax, [rbp+Data]
0x180015061  mov     [rbp+cbData], 4
0x180015068  xor     r8d, r8d; lpReserved
0x18001506b  mov     [rsp+60h+phkResult], rax; lpData
0x180015070  lea     rdx, ValueName; "EnableGoodbye"
0x180015077  call    cs:__imp_RegQueryValueExW
0x18001507d  mov     r8d, [rbp+Type]
0x180015081  test    eax, eax
0x180015083  jnz     short loc_180015094
0x180015085  cmp     r8d, 4
0x180015089  jnz     short loc_180015094
0x18001508b  cmp     dword ptr [rbp+Data], eax
0x18001508e  setnz   sil
0x180015092  jmp     short loc_1800150BC
0x180015094  mov     rcx, cs:WPP_GLOBAL_Control
0x18001509b  cmp     rcx, rbx
0x18001509e  jz      short loc_1800150BC
0x1800150a0  test    byte ptr [rcx+1Ch], 1
0x1800150a4  jz      short loc_1800150BC
0x1800150a6  mov     rcx, [rcx+10h]
0x1800150aa  mov     edx, 0Eh
0x1800150af  mov     r9d, eax
0x1800150b2  mov     dword ptr [rsp+60h+phkResult], r8d
0x1800150b7  call    WPP_SF_ll
0x1800150bc  call    cs:__imp_RevertToSelf
0x1800150c2  test    eax, eax
0x1800150c4  jnz     short loc_1800150FD
0x1800150c6  mov     rax, cs:WPP_GLOBAL_Control
0x1800150cd  cmp     rax, rbx
0x1800150d0  jz      short loc_1800150FD
0x1800150d2  test    byte ptr [rax+1Ch], 1
0x1800150d6  jz      short loc_1800150FD
0x1800150d8  call    cs:__imp_GetLastError
0x1800150de  mov     rcx, cs:WPP_GLOBAL_Control
0x1800150e5  mov     edx, 0Fh
0x1800150ea  mov     rcx, [rcx+10h]
0x1800150ee  lea     r8, WPP_a55972c0645036c47bb3e826c72e1456_Traceguids
0x1800150f5  mov     r9d, eax
0x1800150f8  call    WPP_SF_d
0x1800150fd  mov     eax, cs:dword_18005C570
0x180015103  cmp     eax, 5
0x180015106  jbe     short loc_180015157
0x180015108  mov     rdx, 400000000000h
0x180015112  lea     rcx, dword_18005C570
0x180015119  call    _tlgKeywordOn
0x18001511e  test    al, al
0x180015120  jz      short loc_180015157
0x180015122  mov     [rbp+var_2C], r15d
0x180015126  mov     [rbp+arg_8], sil
0x18001512a  call    ?GetActivityId@NaturalAuthTraceLogging@@YAPEBU_GUID@@XZ; NaturalAuthTraceLogging::GetActivityId(void)
0x18001512f  mov     r8, rax
0x180015132  lea     rdx, byte_18004F8AD
0x180015139  lea     rax, [rbp+var_2C]
0x18001513d  mov     [rsp+60h+lpcbData], rax
0x180015142  lea     rcx, dword_18005C570
0x180015149  lea     rax, [rbp+arg_8]
0x18001514d  mov     [rsp+60h+phkResult], rax
0x180015152  call    ??$Write@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<1>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &)
0x180015157  lea     rcx, [rbp+hKey]
0x18001515b  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180015160  lea     rcx, [rbp+hToken]
0x180015164  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180015169  mov     al, sil
0x18001516c  add     rsp, 60h
0x180015170  pop     r15
0x180015172  pop     r14
0x180015174  pop     rsi
0x180015175  pop     rbx
0x180015176  pop     rbp
0x180015177  retn
```
