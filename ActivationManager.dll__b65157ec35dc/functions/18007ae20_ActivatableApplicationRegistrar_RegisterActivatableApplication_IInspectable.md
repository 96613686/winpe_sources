# ActivatableApplicationRegistrar::RegisterActivatableApplication(IInspectable *)

- ea: `0x18007ae20`
- end: `0x18007b049`
- name: `?RegisterActivatableApplication@ActivatableApplicationRegistrar@@UEAAJPEAUIInspectable@@@Z`
- size: `553`
- prototype: `__int64 __fastcall(ActivatableApplicationRegistrar *__hidden this, struct IInspectable *)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, registry_config`

## callees

- `0x18000b5c0`
- `0x18000cbc0`
- `0x1800169e4`
- `0x180017da4`
- `0x180027ce8`
- `0x1800445ac`
- `0x18005ae90`
- `0x18007aca8`
- `0x18007ae20`
- `0x1800a0010`

## import_xrefs

- `api-ms-win-appmodel-runtime-l1-1-1!GetApplicationUserModelIdFromToken` at `0x18007afa0`
- `api-ms-win-appmodel-runtime-l1-1-1!GetApplicationUserModelIdFromToken` at `0x18007afa0`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrOpenProcessTokenForQuery` at `0x18007af07`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrOpenProcessTokenForQuery` at `0x18007af07`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrOpenProcessHandleForAccess` at `0x18007aebd`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrOpenProcessHandleForAccess` at `0x18007aebd`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x18007af51`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x18007af51`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ActivatableApplicationRegistrar::RegisterActivatableApplication(
        ActivatableApplicationRegistrar *this,
        struct IInspectable *a2)
{
  unsigned int *v2; // rdx
  int inited; // ebx
  __int64 v4; // rdx
  int v5; // eax
  int HostIdFromProcessToken; // eax
  __int64 v7; // rdx
  unsigned __int64 *v8; // r8
  unsigned int ApplicationUserModelIdFromToken; // eax
  unsigned int v11; // [rsp+20h] [rbp-E0h]
  HANDLE token; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v13; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v14; // [rsp+50h] [rbp-B0h] BYREF
  UINT32 applicationUserModelIdLength; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v16; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR applicationUserModelId[136]; // [rsp+70h] [rbp-90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+98h]

  LOBYTE(a2) = 0;
  inited = wil::init_once_nothrow__lambda_07cfb4ee289b66859adc8332a269efc3___(this, a2);
  if ( inited >= 0 )
  {
    LODWORD(v13) = 0;
    inited = DevPlat::Shared::GetRPCClientProcessId((DevPlat::Shared *)&v13, v2);
    if ( inited < 0 )
    {
      v4 = 30;
      goto LABEL_3;
    }
    v14 = 0;
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &v14,
      0);
    v5 = UMgrOpenProcessHandleForAccess(1052672, (unsigned int)v13, &v14);
    inited = v5;
    if ( v5 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x21,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\activatableapplicationregistrar.cpp",
        (const char *)(unsigned int)v5,
        v11);
LABEL_21:
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v14);
      return (unsigned int)inited;
    }
    token = 0;
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &token,
      0);
    HostIdFromProcessToken = UMgrOpenProcessTokenForQuery((unsigned int)v13, &token);
    inited = HostIdFromProcessToken;
    if ( HostIdFromProcessToken >= 0 )
    {
      v16 = 0;
      HostIdFromProcessToken = UMgrQueryUserContext(token, &v16);
      inited = HostIdFromProcessToken;
      if ( HostIdFromProcessToken >= 0 )
      {
        v13 = -1;
        HostIdFromProcessToken = DevPlat::Shared::GetHostIdFromProcessToken((DevPlat::Shared *)token, &v13, v8);
        inited = HostIdFromProcessToken;
        if ( HostIdFromProcessToken >= 0 )
        {
          applicationUserModelIdLength = 131;
          ApplicationUserModelIdFromToken = GetApplicationUserModelIdFromToken(
                                              token,
                                              &applicationUserModelIdLength,
                                              applicationUserModelId);
          if ( ApplicationUserModelIdFromToken )
          {
            inited = wil::details::in1diag3::Return_Win32(
                       retaddr,
                       (void *)0x2E,
                       (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\activatableapplic"
                                     "ationregistrar.cpp",
                       (const char *)ApplicationUserModelIdFromToken,
                       v11);
            goto LABEL_11;
          }
          v11 = v13;
          HostIdFromProcessToken = (*(__int64 (__fastcall **)(__int64, __int64, __int64, WCHAR *))(*(_QWORD *)ActivatableApplicationRegistrar::s_activatableActivationStore
                                                                                                 + 24LL))(
                                     ActivatableApplicationRegistrar::s_activatableActivationStore,
                                     v14,
                                     v16,
                                     applicationUserModelId);
          inited = HostIdFromProcessToken;
          if ( HostIdFromProcessToken >= 0 )
          {
            wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&token);
            inited = 0;
            goto LABEL_21;
          }
          v7 = 48;
        }
        else
        {
          v7 = 42;
        }
      }
      else
      {
        v7 = 39;
      }
    }
    else
    {
      v7 = 36;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\activatableapplicationregistrar.cpp",
      (const char *)(unsigned int)HostIdFromProcessToken,
      v11);
LABEL_11:
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&token);
    goto LABEL_21;
  }
  v4 = 27;
LABEL_3:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v4,
    (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\activatableapplicationregistrar.cpp",
    (const char *)(unsigned int)inited,
    v11);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x18007ae20  mov     [rsp-8+arg_0], rbx
0x18007ae25  mov     [rsp-8+arg_10], rdi
0x18007ae2a  push    rbp
0x18007ae2b  lea     rbp, [rsp-90h]
0x18007ae33  sub     rsp, 190h
0x18007ae3a  mov     rax, cs:__security_cookie
0x18007ae41  xor     rax, rsp
0x18007ae44  mov     [rbp+90h+var_10], rax
0x18007ae4b  mov     rdi, rdx
0x18007ae4e  xor     dl, dl
0x18007ae50  call    wil__init_once_nothrow__lambda_07cfb4ee289b66859adc8332a269efc3___
0x18007ae55  mov     ebx, eax
0x18007ae57  test    eax, eax
0x18007ae59  jns     short loc_18007AE7B
0x18007ae5b  mov     edx, 1Bh; void *
0x18007ae60  lea     r8, aOnecoreuapBase_24; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18007ae67  mov     r9d, ebx; char *
0x18007ae6a  mov     rcx, [rbp+98h]; this
0x18007ae71  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007ae76  jmp     loc_18007B023
0x18007ae7b  mov     dword ptr [rsp+190h+var_148], 0
0x18007ae83  lea     rcx, [rsp+190h+var_148]; this
0x18007ae88  call    ?GetRPCClientProcessId@Shared@DevPlat@@YAJPEAK@Z; DevPlat::Shared::GetRPCClientProcessId(ulong *)
0x18007ae8d  mov     ebx, eax
0x18007ae8f  test    eax, eax
0x18007ae91  jns     short loc_18007AE9A
0x18007ae93  mov     edx, 1Eh
0x18007ae98  jmp     short loc_18007AE60
0x18007ae9a  mov     [rsp+190h+var_140], 0
0x18007aea3  xor     edx, edx
0x18007aea5  lea     rcx, [rsp+190h+var_140]
0x18007aeaa  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18007aeaf  lea     r8, [rsp+190h+var_140]
0x18007aeb4  mov     edx, dword ptr [rsp+190h+var_148]
0x18007aeb8  mov     ecx, 101000h
0x18007aebd  call    cs:__imp_UMgrOpenProcessHandleForAccess
0x18007aec3  mov     ebx, eax
0x18007aec5  test    eax, eax
0x18007aec7  jns     short loc_18007AEE9
0x18007aec9  mov     rcx, [rbp+98h]; this
0x18007aed0  mov     r9d, eax; char *
0x18007aed3  lea     r8, aOnecoreuapBase_24; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18007aeda  mov     edx, 21h ; '!'; void *
0x18007aedf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007aee4  jmp     loc_18007B019
0x18007aee9  mov     [rsp+190h+token], 0
0x18007aef2  xor     edx, edx
0x18007aef4  lea     rcx, [rsp+190h+token]
0x18007aef9  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18007aefe  lea     rdx, [rsp+190h+token]
0x18007af03  mov     ecx, dword ptr [rsp+190h+var_148]
0x18007af07  call    cs:__imp_UMgrOpenProcessTokenForQuery
0x18007af0d  mov     ebx, eax
0x18007af0f  test    eax, eax
0x18007af11  jns     short loc_18007AF3E
0x18007af13  mov     edx, 24h ; '$'; void *
0x18007af18  lea     r8, aOnecoreuapBase_24; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18007af1f  mov     r9d, eax; char *
0x18007af22  mov     rcx, [rbp+98h]; this
0x18007af29  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007af2e  nop
0x18007af2f  lea     rcx, [rsp+190h+token]
0x18007af34  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18007af39  jmp     loc_18007B019
0x18007af3e  mov     [rsp+190h+var_130], 0
0x18007af47  lea     rdx, [rsp+190h+var_130]
0x18007af4c  mov     rcx, [rsp+190h+token]
0x18007af51  call    cs:__imp_UMgrQueryUserContext
0x18007af57  mov     ebx, eax
0x18007af59  test    eax, eax
0x18007af5b  jns     short loc_18007AF64
0x18007af5d  mov     edx, 27h ; '''
0x18007af62  jmp     short loc_18007AF18
0x18007af64  mov     [rsp+190h+var_148], 0FFFFFFFFFFFFFFFFh
0x18007af6d  lea     rdx, [rsp+190h+var_148]; void *
0x18007af72  mov     rcx, [rsp+190h+token]; this
0x18007af77  call    ?GetHostIdFromProcessToken@Shared@DevPlat@@YAJPEAXPEA_K@Z; DevPlat::Shared::GetHostIdFromProcessToken(void *,unsigned __int64 *)
0x18007af7c  mov     ebx, eax
0x18007af7e  test    eax, eax
0x18007af80  jns     short loc_18007AF89
0x18007af82  mov     edx, 2Ah ; '*'
0x18007af87  jmp     short loc_18007AF18
0x18007af89  mov     [rsp+190h+applicationUserModelIdLength], 83h
0x18007af91  lea     r8, [rsp+190h+applicationUserModelId]; applicationUserModelId
0x18007af96  lea     rdx, [rsp+190h+applicationUserModelIdLength]; applicationUserModelIdLength
0x18007af9b  mov     rcx, [rsp+190h+token]; token
0x18007afa0  call    cs:__imp_GetApplicationUserModelIdFromToken
0x18007afa6  test    eax, eax
0x18007afa8  jz      short loc_18007AFCC
0x18007afaa  mov     rcx, [rbp+98h]; this
0x18007afb1  mov     r9d, eax; char *
0x18007afb4  lea     r8, aOnecoreuapBase_24; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18007afbb  mov     edx, 2Eh ; '.'; void *
0x18007afc0  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18007afc5  mov     ebx, eax
0x18007afc7  jmp     loc_18007AF2F
0x18007afcc  mov     rcx, cs:?s_activatableActivationStore@ActivatableApplicationRegistrar@@0V?$ComPtr@UIActivatableApplicationStore@@@WRL@Microsoft@@A; Microsoft::WRL::ComPtr<IActivatableApplicationStore> ActivatableApplicationRegistrar::s_activatableActivationStore
0x18007afd3  mov     rax, [rcx]
0x18007afd6  mov     [rsp+190h+var_168], rdi
0x18007afdb  mov     r9, [rsp+190h+var_148]
0x18007afe0  mov     [rsp+190h+var_170], r9
0x18007afe5  lea     r9, [rsp+190h+applicationUserModelId]
0x18007afea  mov     r8, [rsp+190h+var_130]
0x18007afef  mov     rdx, [rsp+190h+var_140]
0x18007aff4  mov     rax, [rax+18h]
0x18007aff8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007affd  mov     ebx, eax
0x18007afff  test    eax, eax
0x18007b001  jns     short loc_18007B00D
0x18007b003  mov     edx, 30h ; '0'
0x18007b008  jmp     loc_18007AF18
0x18007b00d  lea     rcx, [rsp+190h+token]
0x18007b012  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18007b017  xor     ebx, ebx
0x18007b019  lea     rcx, [rsp+190h+var_140]
0x18007b01e  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18007b023  mov     eax, ebx
0x18007b025  mov     rcx, [rbp+90h+var_10]
0x18007b02c  xor     rcx, rsp; StackCookie
0x18007b02f  call    __security_check_cookie
0x18007b034  lea     r11, [rsp+190h+var_s0]
0x18007b03c  mov     rbx, [r11+10h]
0x18007b040  mov     rdi, [r11+20h]
0x18007b044  mov     rsp, r11
0x18007b047  pop     rbp
0x18007b048  retn
```
