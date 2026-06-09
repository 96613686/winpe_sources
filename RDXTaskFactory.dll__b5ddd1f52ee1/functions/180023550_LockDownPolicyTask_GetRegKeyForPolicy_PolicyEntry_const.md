# LockDownPolicyTask::GetRegKeyForPolicy(PolicyEntry const &)

- ea: `0x180023550`
- end: `0x180023705`
- name: `?GetRegKeyForPolicy@LockDownPolicyTask@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEBUPolicyEntry@@@Z`
- size: `437`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task`

## callers

- `0x180022f1c`

## callees

- `0x180003390`
- `0x18000b218`
- `0x18001094c`
- `0x180022484`
- `0x180022aa8`
- `0x180023550`
- `0x180023720`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800235ec`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800236b7`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800235ec`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800236b7`

## string_xrefs

- `0x180023600`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\lockdownpolicytask.cpp`
- `0x180023655`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\lockdownpolicytask.cpp`
- `0x1800236cb`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\lockdownpolicytask.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall LockDownPolicyTask::GetRegKeyForPolicy(LockDownPolicyTask *a1, _QWORD *a2, __int64 a3)
{
  unsigned int v4; // eax
  __int64 v5; // rbx
  const unsigned __int16 *UserSid; // rax
  int v7; // eax
  unsigned int v8; // eax
  unsigned int dwOptions; // [rsp+20h] [rbp-E0h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-E0h]
  _QWORD *v12; // [rsp+58h] [rbp-A8h] BYREF
  HKEY phkResult; // [rsp+60h] [rbp-A0h] BYREF
  char v14; // [rsp+68h] [rbp-98h]
  _QWORD *v15; // [rsp+70h] [rbp-90h]
  WCHAR SubKey[264]; // [rsp+80h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1B8h]

  v15 = a2;
  *a2 = 0;
  if ( !*(_DWORD *)a3 )
  {
    v12 = a2;
    phkResult = 0;
    v14 = 1;
    v4 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, *(LPCWSTR *)(a3 + 8), 0, 0, 0, 2u, 0, &phkResult, 0);
    if ( v4 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x77,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\lockdownpolicytask.cpp",
        (const char *)v4,
        dwOptions);
LABEL_10:
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&v12);
    return a2;
  }
  if ( *(_DWORD *)a3 == 1 )
  {
    v5 = *(_QWORD *)(a3 + 8);
    UserSid = LockDownPolicyTask::GetUserSid(a1);
    v7 = StringCchPrintfW(SubKey, 0x104u, L"%s\\%s", UserSid);
    if ( v7 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x7C,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\lockdownpolicytask.cpp",
        (const char *)(unsigned int)v7,
        v5);
    v12 = a2;
    phkResult = 0;
    v14 = 1;
    v8 = RegCreateKeyExW(HKEY_USERS, SubKey, 0, 0, 0, 2u, 0, &phkResult, 0);
    if ( v8 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x7D,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\lockdownpolicytask.cpp",
        (const char *)v8,
        dwOptionsa);
    goto LABEL_10;
  }
  return a2;
}

```

## disassembly

```asm
0x180023550  push    rbp
0x180023552  push    rbx
0x180023553  push    rdi
0x180023554  lea     rbp, [rsp-1A0h]
0x18002355c  sub     rsp, 2A0h
0x180023563  mov     rax, cs:__security_cookie
0x18002356a  xor     rax, rsp
0x18002356d  mov     [rbp+1B0h+var_20], rax
0x180023574  mov     rbx, r8
0x180023577  mov     rdi, rdx
0x18002357a  mov     [rsp+2B0h+var_240], rdx
0x18002357f  mov     [rsp+2B0h+var_260], 0
0x180023587  mov     qword ptr [rdx], 0
0x18002358e  mov     [rsp+2B0h+var_260], 1
0x180023596  cmp     dword ptr [r8], 0
0x18002359a  jnz     short loc_180023617
0x18002359c  mov     [rsp+2B0h+var_258], rdx
0x1800235a1  mov     [rsp+2B0h+var_250], 0
0x1800235aa  mov     [rsp+2B0h+var_248], 1
0x1800235af  mov     [rsp+2B0h+lpdwDisposition], 0; lpdwDisposition
0x1800235b8  lea     rax, [rsp+2B0h+var_250]
0x1800235bd  mov     [rsp+2B0h+phkResult], rax; phkResult
0x1800235c2  mov     [rsp+2B0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800235cb  mov     [rsp+2B0h+samDesired], 2; samDesired
0x1800235d3  mov     [rsp+2B0h+dwOptions], 0; unsigned int
0x1800235db  xor     r9d, r9d; lpClass
0x1800235de  xor     r8d, r8d; Reserved
0x1800235e1  mov     rdx, [rbx+8]; lpSubKey
0x1800235e5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800235ec  call    cs:__imp_RegCreateKeyExW
0x1800235f2  mov     rcx, [rbp+1B8h]; this
0x1800235f9  test    eax, eax
0x1800235fb  jz      short loc_180023612
0x1800235fd  mov     r9d, eax; char *
0x180023600  lea     r8, aPcshellShellRe_3; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180023607  mov     edx, 77h ; 'w'; void *
0x18002360c  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180023612  jmp     loc_1800236DD
0x180023617  cmp     dword ptr [r8], 1
0x18002361b  jnz     loc_1800236E7
0x180023621  mov     rbx, [r8+8]
0x180023625  call    ?GetUserSid@LockDownPolicyTask@@AEAAPEBGXZ; LockDownPolicyTask::GetUserSid(void)
0x18002362a  mov     qword ptr [rsp+2B0h+dwOptions], rbx; int
0x18002362f  mov     r9, rax
0x180023632  lea     r8, aSS; "%s\\%s"
0x180023639  mov     edx, 104h; unsigned __int64
0x18002363e  lea     rcx, [rbp+1B0h+SubKey]; unsigned __int16 *
0x180023642  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180023647  mov     rcx, [rbp+1B8h]; this
0x18002364e  test    eax, eax
0x180023650  jns     short loc_180023667
0x180023652  mov     r9d, eax; char *
0x180023655  lea     r8, aPcshellShellRe_3; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18002365c  mov     edx, 7Ch ; '|'; void *
0x180023661  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180023667  mov     [rsp+2B0h+var_258], rdi
0x18002366c  mov     [rsp+2B0h+var_250], 0
0x180023675  mov     [rsp+2B0h+var_248], 1
0x18002367a  mov     [rsp+2B0h+lpdwDisposition], 0; lpdwDisposition
0x180023683  lea     rax, [rsp+2B0h+var_250]
0x180023688  mov     [rsp+2B0h+phkResult], rax; phkResult
0x18002368d  mov     [rsp+2B0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180023696  mov     [rsp+2B0h+samDesired], 2; samDesired
0x18002369e  mov     [rsp+2B0h+dwOptions], 0; unsigned int
0x1800236a6  xor     r9d, r9d; lpClass
0x1800236a9  xor     r8d, r8d; Reserved
0x1800236ac  lea     rdx, [rbp+1B0h+SubKey]; lpSubKey
0x1800236b0  mov     rcx, 0FFFFFFFF80000003h; hKey
0x1800236b7  call    cs:__imp_RegCreateKeyExW
0x1800236bd  mov     rcx, [rbp+1B8h]; this
0x1800236c4  test    eax, eax
0x1800236c6  jz      short loc_1800236DD
0x1800236c8  mov     r9d, eax; char *
0x1800236cb  lea     r8, aPcshellShellRe_3; "pcshell\\shell\\retaildemo\\desktoptask"...
0x1800236d2  mov     edx, 7Dh ; '}'; void *
0x1800236d7  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x1800236dd  lea     rcx, [rsp+2B0h+var_258]
0x1800236e2  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x1800236e7  mov     rax, rdi
0x1800236ea  mov     rcx, [rbp+1B0h+var_20]
0x1800236f1  xor     rcx, rsp; StackCookie
0x1800236f4  call    __security_check_cookie
0x1800236f9  add     rsp, 2A0h
0x180023700  pop     rdi
0x180023701  pop     rbx
0x180023702  pop     rbp
0x180023703  retn
```
