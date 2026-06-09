# UserOOBEController::DeleteDefaultAccount(void)

- ea: `0x1800238b0`
- end: `0x180023aaf`
- name: `?DeleteDefaultAccount@UserOOBEController@@UEAAJXZ`
- size: `511`
- prototype: `__int64 __fastcall(UserOOBEController *__hidden this)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800032b0`
- `0x180007134`
- `0x18000a5e8`
- `0x18001e7b4`
- `0x18001f6c4`
- `0x1800238b0`
- `0x1800279b8`
- `0x180028684`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002390b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002390b`
- `samcli!NetUserDel` at `0x18002397a`
- `samcli!NetUserDel` at `0x18002397a`
- `USERENV!DeleteProfileW` at `0x1800239e4`
- `USERENV!DeleteProfileW` at `0x1800239e4`
- `api-ms-win-stateseparation-helpers-l1-1-1!DeletePersistedRegistryValue` at `0x180023a23`
- `api-ms-win-stateseparation-helpers-l1-1-1!DeletePersistedRegistryValue` at `0x180023a62`
- `api-ms-win-stateseparation-helpers-l1-1-1!DeletePersistedRegistryValue` at `0x180023a23`
- `api-ms-win-stateseparation-helpers-l1-1-1!DeletePersistedRegistryValue` at `0x180023a62`

## string_xrefs

- `0x180023a4d`: `DefaultAccountSID`
- `0x180023937`: `shell\oobe\user\dll\useroobecontroller.cpp`
- `0x1800239c9`: `shell\oobe\user\dll\useroobecontroller.cpp`
- `0x180023a35`: `shell\oobe\user\dll\useroobecontroller.cpp`
- `0x180023a74`: `shell\oobe\user\dll\useroobecontroller.cpp`

## pseudocode

```c
__int64 __fastcall UserOOBEController::DeleteDefaultAccount(UserOOBEController *this)
{
  int ValueW; // ebx
  bool v2; // sf
  int DefaultAccountSidWithRegistryFallback; // eax
  unsigned __int64 v4; // r9
  __int64 v5; // rdx
  DWORD v6; // eax
  __int64 i; // rcx
  int Error; // eax
  unsigned int v9; // eax
  unsigned int v10; // eax
  unsigned int pdwType; // [rsp+20h] [rbp-258h]
  DWORD pcbData[2]; // [rsp+40h] [rbp-238h] BYREF
  WCHAR username[264]; // [rsp+50h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  pcbData[0] = 514;
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\OOBE",
             L"DefaultAccountSAMName",
             2u,
             0,
             username,
             pcbData);
  if ( ValueW )
  {
    username[0] = 0;
    v2 = ValueW < 0;
    if ( ValueW <= 0 )
      goto LABEL_5;
    ValueW = (unsigned __int16)ValueW | 0x80070000;
  }
  v2 = ValueW < 0;
LABEL_5:
  if ( !v2 )
  {
    *(_QWORD *)pcbData = 0;
    DefaultAccountSidWithRegistryFallback = UserOOBEController::s_GetDefaultAccountSidWithRegistryFallback((unsigned __int16 **)pcbData);
    ValueW = DefaultAccountSidWithRegistryFallback;
    if ( DefaultAccountSidWithRegistryFallback >= 0 )
    {
      v6 = NetUserDel(0, username);
      if ( !v6 || v6 == 2221 )
      {
        if ( DeleteProfileW(*(LPCWSTR *)pcbData, 0, 0)
          || (Error = ResultFromKnownLastError(), ValueW = Error, Error == -2147024894) )
        {
          v9 = DeletePersistedRegistryValue(
                 L"OOBE",
                 L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\OOBE",
                 L"DefaultAccountSAMName");
          if ( v9 )
          {
            ValueW = wil::details::in1diag3::Return_Win32(
                       retaddr,
                       (void *)0x106,
                       (unsigned int)"shell\\oobe\\user\\dll\\useroobecontroller.cpp",
                       (const char *)v9,
                       pdwType);
          }
          else
          {
            v10 = DeletePersistedRegistryValue(
                    L"OOBE",
                    L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\OOBE",
                    L"DefaultAccountSID");
            if ( v10 )
              wil::details::in1diag3::_Log_Win32(
                retaddr,
                (void *)0x107,
                (unsigned int)"shell\\oobe\\user\\dll\\useroobecontroller.cpp",
                (const char *)v10,
                pdwType);
            ValueW = 0;
          }
          goto LABEL_29;
        }
        if ( Error >= 0 )
        {
LABEL_29:
          wil::details::unique_storage<wil::details::resource_policy<_TOKEN_GROUPS *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_TOKEN_GROUPS *,_TOKEN_GROUPS *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TOKEN_GROUPS *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_TOKEN_GROUPS *,_TOKEN_GROUPS *,0,std::nullptr_t>>(pcbData);
          return (unsigned int)ValueW;
        }
        v4 = (unsigned int)Error;
        v5 = 258;
      }
      else
      {
        for ( i = 0; ; i = (unsigned int)(i + 1) )
        {
          if ( (unsigned int)i >= 0x7A )
          {
            ValueW = -805306139;
            goto LABEL_18;
          }
          if ( LODWORD(ErrorMap[i]) == v6 )
            break;
        }
        ValueW = HIDWORD(ErrorMap[i]) | 0x10000000;
        if ( ErrorMap[i] >= 0 )
          goto LABEL_29;
LABEL_18:
        v4 = (unsigned int)ValueW;
        v5 = 251;
      }
    }
    else
    {
      v4 = (unsigned int)DefaultAccountSidWithRegistryFallback;
      v5 = 243;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"shell\\oobe\\user\\dll\\useroobecontroller.cpp",
      (const char *)v4,
      pdwType);
    goto LABEL_29;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xF1,
    (unsigned int)"shell\\oobe\\user\\dll\\useroobecontroller.cpp",
    (const char *)(unsigned int)ValueW,
    pdwType);
  return (unsigned int)ValueW;
}

```

## disassembly

```asm
0x1800238b0  push    rbx
0x1800238b2  sub     rsp, 270h
0x1800238b9  mov     rax, cs:__security_cookie
0x1800238c0  xor     rax, rsp
0x1800238c3  mov     [rsp+278h+var_18], rax
0x1800238cb  lea     rax, [rsp+278h+var_238]
0x1800238d0  mov     [rsp+278h+var_238], 202h
0x1800238d8  mov     [rsp+278h+pcbData], rax; pcbData
0x1800238dd  lea     r8, aDefaultaccount_0; "DefaultAccountSAMName"
0x1800238e4  lea     rax, [rsp+278h+username]
0x1800238e9  mov     r9d, 2; dwFlags
0x1800238ef  mov     [rsp+278h+pvData], rax; pvData
0x1800238f4  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800238fb  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180023902  mov     [rsp+278h+pdwType], 0; unsigned int
0x18002390b  call    cs:__imp_RegGetValueW
0x180023911  mov     ebx, eax
0x180023913  test    eax, eax
0x180023915  jz      short loc_18002392B
0x180023917  xor     eax, eax
0x180023919  mov     [rsp+278h+username], ax
0x18002391e  test    ebx, ebx
0x180023920  jle     short loc_18002392D
0x180023922  movzx   ebx, bx
0x180023925  or      ebx, 80070000h
0x18002392b  test    ebx, ebx
0x18002392d  jns     short loc_180023950
0x18002392f  mov     rcx, [rsp+278h]; this
0x180023937  lea     r8, aShellOobeUserD_0; "shell\\oobe\\user\\dll\\useroobecontrol"...
0x18002393e  mov     r9d, ebx; char *
0x180023941  mov     edx, 0F1h; void *
0x180023946  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002394b  jmp     loc_180023A94
0x180023950  lea     rcx, [rsp+278h+var_238]; unsigned __int16 **
0x180023955  mov     qword ptr [rsp+278h+var_238], 0
0x18002395e  call    ?s_GetDefaultAccountSidWithRegistryFallback@UserOOBEController@@CAJPEAPEAG@Z; UserOOBEController::s_GetDefaultAccountSidWithRegistryFallback(ushort * *)
0x180023963  mov     ebx, eax
0x180023965  test    eax, eax
0x180023967  jns     short loc_180023973
0x180023969  mov     r9d, eax
0x18002396c  mov     edx, 0F3h
0x180023971  jmp     short loc_1800239C1
0x180023973  lea     rdx, [rsp+278h+username]; username
0x180023978  xor     ecx, ecx; servername
0x18002397a  call    cs:__imp_NetUserDel
0x180023980  test    eax, eax
0x180023982  jz      short loc_1800239DA
0x180023984  cmp     eax, 8ADh
0x180023989  jz      short loc_1800239DA
0x18002398b  xor     ecx, ecx
0x18002398d  lea     rdx, ErrorMap
0x180023994  cmp     ecx, 7Ah ; 'z'
0x180023997  jnb     short loc_1800239B4
0x180023999  cmp     [rdx+rcx*8], eax
0x18002399c  jz      short loc_1800239A2
0x18002399e  inc     ecx
0x1800239a0  jmp     short loc_180023994
0x1800239a2  mov     ebx, [rdx+rcx*8+4]
0x1800239a6  or      ebx, 10000000h
0x1800239ac  jge     loc_180023A8A
0x1800239b2  jmp     short loc_1800239B9
0x1800239b4  mov     ebx, 0D00000E5h
0x1800239b9  mov     r9d, ebx; char *
0x1800239bc  mov     edx, 0FBh; void *
0x1800239c1  mov     rcx, [rsp+278h]; this
0x1800239c9  lea     r8, aShellOobeUserD_0; "shell\\oobe\\user\\dll\\useroobecontrol"...
0x1800239d0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800239d5  jmp     loc_180023A8A
0x1800239da  mov     rcx, qword ptr [rsp+278h+var_238]; lpSidString
0x1800239df  xor     r8d, r8d; lpComputerName
0x1800239e2  xor     edx, edx; lpProfilePath
0x1800239e4  call    cs:__imp_DeleteProfileW
0x1800239ea  test    eax, eax
0x1800239ec  jnz     short loc_180023A0E
0x1800239ee  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800239f3  mov     ebx, eax
0x1800239f5  cmp     eax, 80070002h
0x1800239fa  jz      short loc_180023A0E
0x1800239fc  test    eax, eax
0x1800239fe  jns     loc_180023A8A
0x180023a04  mov     r9d, eax
0x180023a07  mov     edx, 102h
0x180023a0c  jmp     short loc_1800239C1
0x180023a0e  lea     r8, aDefaultaccount_0; "DefaultAccountSAMName"
0x180023a15  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180023a1c  lea     rcx, aOobe_0; "OOBE"
0x180023a23  call    cs:__imp_DeletePersistedRegistryValue
0x180023a29  test    eax, eax
0x180023a2b  jz      short loc_180023A4D
0x180023a2d  mov     rcx, [rsp+278h]; this
0x180023a35  lea     r8, aShellOobeUserD_0; "shell\\oobe\\user\\dll\\useroobecontrol"...
0x180023a3c  mov     r9d, eax; char *
0x180023a3f  mov     edx, 106h; void *
0x180023a44  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180023a49  mov     ebx, eax
0x180023a4b  jmp     short loc_180023A8A
0x180023a4d  lea     r8, aDefaultaccount_1; "DefaultAccountSID"
0x180023a54  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180023a5b  lea     rcx, aOobe_0; "OOBE"
0x180023a62  call    cs:__imp_DeletePersistedRegistryValue
0x180023a68  test    eax, eax
0x180023a6a  jz      short loc_180023A88
0x180023a6c  mov     rcx, [rsp+278h]; this
0x180023a74  lea     r8, aShellOobeUserD_0; "shell\\oobe\\user\\dll\\useroobecontrol"...
0x180023a7b  mov     r9d, eax; char *
0x180023a7e  mov     edx, 107h; void *
0x180023a83  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180023a88  xor     ebx, ebx
0x180023a8a  lea     rcx, [rsp+278h+var_238]
0x180023a8f  call    ??1?$unique_storage@U?$resource_policy@PEAU_TOKEN_GROUPS@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_TOKEN_GROUPS *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_TOKEN_GROUPS *,_TOKEN_GROUPS *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TOKEN_GROUPS *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_TOKEN_GROUPS *,_TOKEN_GROUPS *,0,std::nullptr_t>>(void)
0x180023a94  mov     eax, ebx
0x180023a96  mov     rcx, [rsp+278h+var_18]
0x180023a9e  xor     rcx, rsp; StackCookie
0x180023aa1  call    __security_check_cookie
0x180023aa6  add     rsp, 270h
0x180023aad  pop     rbx
0x180023aae  retn
```
