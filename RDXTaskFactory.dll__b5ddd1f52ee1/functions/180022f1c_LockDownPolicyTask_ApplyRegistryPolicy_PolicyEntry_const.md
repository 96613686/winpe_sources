# LockDownPolicyTask::ApplyRegistryPolicy(PolicyEntry const &)

- ea: `0x180022f1c`
- end: `0x180023156`
- name: `?ApplyRegistryPolicy@LockDownPolicyTask@@AEAAXAEBUPolicyEntry@@@Z`
- size: `570`
- prototype: `void __fastcall(LockDownPolicyTask *__hidden this, const struct PolicyEntry *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180022ddc`

## callees

- `0x180008bbc`
- `0x18001094c`
- `0x18001e58c`
- `0x180022484`
- `0x180022aa8`
- `0x180022f1c`
- `0x1800233cc`
- `0x180023550`
- `0x180050010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180022fc5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800230de`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180022fc5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800230de`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002309b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002309b`

## string_xrefs

- `0x180022fd6`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\lockdownpolicytask.cpp`
- `0x18002303e`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\lockdownpolicytask.cpp`
- `0x1800230ac`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\lockdownpolicytask.cpp`
- `0x1800230ef`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\lockdownpolicytask.cpp`
- `0x180023144`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\lockdownpolicytask.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall LockDownPolicyTask::ApplyRegistryPolicy(LockDownPolicyTask *this, const struct PolicyEntry *a2)
{
  DWORD cbData; // edi
  const BYTE *v5; // rsi
  DWORD v6; // r14d
  __int64 v7; // rdi
  unsigned int v8; // eax
  __int64 v9; // rax
  int v10; // eax
  unsigned int v11; // eax
  unsigned int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // r8
  int lpData; // [rsp+20h] [rbp-60h]
  unsigned int lpDataa; // [rsp+20h] [rbp-60h]
  unsigned int lpDatab; // [rsp+20h] [rbp-60h]
  unsigned int lpDatac; // [rsp+20h] [rbp-60h]
  HKEY hKey; // [rsp+50h] [rbp-30h] BYREF
  __int64 v20; // [rsp+58h] [rbp-28h] BYREF
  HKEY *v21; // [rsp+60h] [rbp-20h] BYREF
  HKEY phkResult; // [rsp+68h] [rbp-18h] BYREF
  char v23; // [rsp+70h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]
  HKEY v25; // [rsp+C8h] [rbp+48h] BYREF
  HKEY v26; // [rsp+D0h] [rbp+50h] BYREF
  __int64 *v27; // [rsp+D8h] [rbp+58h] BYREF

  if ( (*((_DWORD *)a2 + 1) & 0xE) == 0 || (((*((_DWORD *)a2 + 1) & 0xE) - 1LL) & *((_DWORD *)a2 + 1) & 0xE) != 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x87,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\lockdownpolicytask.cpp",
      (const char *)0x80070057LL,
      lpData);
  LockDownPolicyTask::GetRegKeyForPolicy(this, &hKey, a2);
  cbData = 4;
  if ( (*((_BYTE *)a2 + 4) & 2) != 0 )
  {
    v5 = (const BYTE *)a2 + 24;
    v6 = 4;
  }
  else if ( (*((_BYTE *)a2 + 4) & 4) != 0 )
  {
    v20 = *((int *)a2 + 6);
    v5 = (const BYTE *)&v20;
    cbData = 8;
    v6 = 11;
  }
  else
  {
    v5 = (const BYTE *)*((_QWORD *)a2 + 4);
    v7 = -1;
    do
      ++v7;
    while ( *(_WORD *)&v5[2 * v7] );
    cbData = 2 * v7;
    v6 = 1;
  }
  v8 = RegSetValueExW(hKey, *((LPCWSTR *)a2 + 2), 0, v6, v5, cbData);
  if ( v8 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0xA3,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\lockdownpolicytask.cpp",
      (const char *)v8,
      lpDataa);
  if ( (*((_BYTE *)a2 + 4) & 1) != 0 )
  {
    LockDownPolicyTask::GetGroupPolicyObject(this);
    v26 = 0;
    v9 = *v27;
    v21 = &v26;
    phkResult = 0;
    v23 = 1;
    v10 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, HKEY *))(v9 + 120))(
            v27,
            2 - (unsigned int)(*(_DWORD *)a2 != 0),
            &phkResult);
    if ( v10 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xA9,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\lockdownpolicytask.cpp",
        (const char *)(unsigned int)v10,
        lpDataa);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&v21);
    v25 = 0;
    v21 = &v25;
    phkResult = 0;
    v23 = 1;
    v11 = RegCreateKeyExW(v26, *((LPCWSTR *)a2 + 1), 0, 0, 0, 2u, 0, &phkResult, 0);
    if ( v11 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0xAB,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\lockdownpolicytask.cpp",
        (const char *)v11,
        lpDatab);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&v21);
    v12 = RegSetValueExW(v25, *((LPCWSTR *)a2 + 2), 0, v6, v5, cbData);
    if ( v12 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0xAC,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\lockdownpolicytask.cpp",
        (const char *)v12,
        lpDatac);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v25);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v26);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27, v13, v14);
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
}

```

## disassembly

```asm
0x180022f1c  push    rbp
0x180022f1e  push    rbx
0x180022f1f  push    rsi
0x180022f20  push    rdi
0x180022f21  push    r12
0x180022f23  push    r14
0x180022f25  push    r15
0x180022f27  mov     rbp, rsp
0x180022f2a  sub     rsp, 80h
0x180022f31  mov     rbx, rdx
0x180022f34  mov     r15, rcx
0x180022f37  mov     eax, [rdx+4]
0x180022f3a  and     eax, 0Eh
0x180022f3d  jz      loc_18002313A
0x180022f43  mov     r8d, eax
0x180022f46  dec     rax
0x180022f49  test    r8, rax
0x180022f4c  jnz     loc_18002313A
0x180022f52  mov     r8, rdx
0x180022f55  lea     rdx, [rbp+hKey]
0x180022f59  call    ?GetRegKeyForPolicy@LockDownPolicyTask@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEBUPolicyEntry@@@Z; LockDownPolicyTask::GetRegKeyForPolicy(PolicyEntry const &)
0x180022f5e  nop
0x180022f5f  xor     r12d, r12d
0x180022f62  lea     edi, [r12+4]
0x180022f67  test    byte ptr [rbx+4], 2
0x180022f6b  jz      short loc_180022F76
0x180022f6d  lea     rsi, [rbx+18h]
0x180022f71  mov     r14d, edi
0x180022f74  jmp     short loc_180022FAE
0x180022f76  test    [rbx+4], dil
0x180022f7a  jz      short loc_180022F93
0x180022f7c  movsxd  rax, dword ptr [rbx+18h]
0x180022f80  mov     [rbp+var_28], rax
0x180022f84  lea     rsi, [rbp+var_28]
0x180022f88  mov     edi, 8
0x180022f8d  lea     r14d, [rdi+3]
0x180022f91  jmp     short loc_180022FAE
0x180022f93  mov     rsi, [rbx+20h]
0x180022f97  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180022f9b  inc     rdi
0x180022f9e  cmp     [rsi+rdi*2], r12w
0x180022fa3  jnz     short loc_180022F9B
0x180022fa5  add     rdi, rdi
0x180022fa8  mov     r14d, 1
0x180022fae  mov     [rsp+80h+cbData], edi; cbData
0x180022fb2  mov     [rsp+80h+lpData], rsi; int
0x180022fb7  mov     r9d, r14d; dwType
0x180022fba  xor     r8d, r8d; Reserved
0x180022fbd  mov     rdx, [rbx+10h]; lpValueName
0x180022fc1  mov     rcx, [rbp+hKey]; hKey
0x180022fc5  call    cs:__imp_RegSetValueExW
0x180022fcb  mov     rcx, [rbp+38h]; this
0x180022fcf  test    eax, eax
0x180022fd1  jz      short loc_180022FE8
0x180022fd3  mov     r9d, eax; char *
0x180022fd6  lea     r8, aPcshellShellRe_3; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180022fdd  mov     edx, 0A3h; void *
0x180022fe2  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180022fe8  test    byte ptr [rbx+4], 1
0x180022fec  jz      loc_18002311F
0x180022ff2  mov     r8d, [rbx]
0x180022ff5  lea     rdx, [rbp+arg_18]
0x180022ff9  mov     rcx, r15
0x180022ffc  call    ?GetGroupPolicyObject@LockDownPolicyTask@@AEAA?AV?$ComPtr@UIGroupPolicyObject2@@@WRL@Microsoft@@W4PolicyType@@@Z; LockDownPolicyTask::GetGroupPolicyObject(PolicyType)
0x180023001  nop
0x180023002  mov     [rbp+arg_10], r12
0x180023006  mov     rcx, [rbp+arg_18]
0x18002300a  mov     rax, [rcx]
0x18002300d  lea     rdx, [rbp+arg_10]
0x180023011  mov     [rbp+var_20], rdx
0x180023015  mov     [rbp+var_18], r12
0x180023019  mov     [rbp+var_10], 1
0x18002301d  mov     edx, [rbx]
0x18002301f  neg     edx
0x180023021  sbb     edx, edx
0x180023023  add     edx, 2
0x180023026  lea     r8, [rbp+var_18]
0x18002302a  mov     rax, [rax+78h]
0x18002302e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023033  mov     rcx, [rbp+38h]; this
0x180023037  test    eax, eax
0x180023039  jns     short loc_180023050
0x18002303b  mov     r9d, eax; char *
0x18002303e  lea     r8, aPcshellShellRe_3; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180023045  mov     edx, 0A9h; void *
0x18002304a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180023050  lea     rcx, [rbp+var_20]
0x180023054  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x180023059  mov     [rbp+arg_8], r12
0x18002305d  lea     rax, [rbp+arg_8]
0x180023061  mov     [rbp+var_20], rax
0x180023065  mov     [rbp+var_18], r12
0x180023069  mov     [rbp+var_10], 1
0x18002306d  mov     [rsp+80h+lpdwDisposition], r12; lpdwDisposition
0x180023072  lea     rax, [rbp+var_18]
0x180023076  mov     [rsp+80h+phkResult], rax; phkResult
0x18002307b  mov     [rsp+80h+lpSecurityAttributes], r12; lpSecurityAttributes
0x180023080  mov     [rsp+80h+cbData], 2; samDesired
0x180023088  mov     dword ptr [rsp+80h+lpData], r12d; unsigned int
0x18002308d  xor     r9d, r9d; lpClass
0x180023090  xor     r8d, r8d; Reserved
0x180023093  mov     rdx, [rbx+8]; lpSubKey
0x180023097  mov     rcx, [rbp+arg_10]; hKey
0x18002309b  call    cs:__imp_RegCreateKeyExW
0x1800230a1  mov     rcx, [rbp+38h]; this
0x1800230a5  test    eax, eax
0x1800230a7  jz      short loc_1800230BE
0x1800230a9  mov     r9d, eax; char *
0x1800230ac  lea     r8, aPcshellShellRe_3; "pcshell\\shell\\retaildemo\\desktoptask"...
0x1800230b3  mov     edx, 0ABh; void *
0x1800230b8  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x1800230be  lea     rcx, [rbp+var_20]
0x1800230c2  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x1800230c7  mov     [rsp+80h+cbData], edi; cbData
0x1800230cb  mov     [rsp+80h+lpData], rsi; unsigned int
0x1800230d0  mov     r9d, r14d; dwType
0x1800230d3  xor     r8d, r8d; Reserved
0x1800230d6  mov     rdx, [rbx+10h]; lpValueName
0x1800230da  mov     rcx, [rbp+arg_8]; hKey
0x1800230de  call    cs:__imp_RegSetValueExW
0x1800230e4  mov     rcx, [rbp+38h]; this
0x1800230e8  test    eax, eax
0x1800230ea  jz      short loc_180023101
0x1800230ec  mov     r9d, eax; char *
0x1800230ef  lea     r8, aPcshellShellRe_3; "pcshell\\shell\\retaildemo\\desktoptask"...
0x1800230f6  mov     edx, 0ACh; void *
0x1800230fb  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180023101  lea     rcx, [rbp+arg_8]
0x180023105  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002310a  nop
0x18002310b  lea     rcx, [rbp+arg_10]
0x18002310f  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180023114  nop
0x180023115  lea     rcx, [rbp+arg_18]
0x180023119  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002311e  nop
0x18002311f  lea     rcx, [rbp+hKey]
0x180023123  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180023128  add     rsp, 80h
0x18002312f  pop     r15
0x180023131  pop     r14
0x180023133  pop     r12
0x180023135  pop     rdi
0x180023136  pop     rsi
0x180023137  pop     rbx
0x180023138  pop     rbp
0x180023139  retn
0x18002313a  mov     rcx, [rbp+38h]; this
0x18002313e  mov     r9d, 80070057h; char *
0x180023144  lea     r8, aPcshellShellRe_3; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18002314b  mov     edx, 87h; void *
0x180023150  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
