# Windows::System::ShutdownManagerImpl::CancelShutdown(void)

- ea: `0x18000d810`
- end: `0x18000d94b`
- name: `?CancelShutdown@ShutdownManagerImpl@System@Windows@@UEAAJXZ`
- size: `315`
- prototype: `__int64 __fastcall(Windows::System::ShutdownManagerImpl *__hidden this)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180002dc0`
- `0x18000d164`
- `0x18000d450`
- `0x18000d810`
- `0x18000ea90`
- `0x18000ee00`
- `0x18000f824`
- `0x18001c6a8`

## import_xrefs

- `ntdll!RtlAcquirePrivilege` at `0x18000d8ac`
- `ntdll!RtlAcquirePrivilege` at `0x18000d8ac`
- `ntdll!RtlReleasePrivilege` at `0x18000d915`
- `ntdll!RtlReleasePrivilege` at `0x18000d915`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d8cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d8cc`
- `api-ms-win-core-shutdown-l1-1-0!AbortSystemShutdownW` at `0x18000d8c2`
- `api-ms-win-core-shutdown-l1-1-0!AbortSystemShutdownW` at `0x18000d8c2`

## pseudocode

```c
__int64 __fastcall Windows::System::ShutdownManagerImpl::CancelShutdown(Windows::System::ShutdownManagerImpl *this)
{
  int v1; // edi
  int HasSystemManagementCapability; // ebx
  NTSTATUS v3; // eax
  signed int LastError; // eax
  int v6; // [rsp+20h] [rbp-E0h] BYREF
  ULONG Privilege; // [rsp+24h] [rbp-DCh] BYREF
  PVOID ReturnedState; // [rsp+28h] [rbp-D8h] BYREF
  _QWORD v9[42]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+A8h]

  Privilege = 19;
  ReturnedState = 0;
  v1 = -1073741727;
  LOBYTE(v6) = 0;
  wil::ActivityBase<Windows::System::SysAdminTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Windows::System::SysAdminTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v9,
    "CancelShutdownActivity");
  v9[0] = &Windows::System::SysAdminTraceLoggingProvider::CancelShutdownActivity::`vftable';
  Windows::System::SysAdminTraceLoggingProvider::CancelShutdownActivity::StartActivity((Windows::System::SysAdminTraceLoggingProvider::CancelShutdownActivity *)v9);
  HasSystemManagementCapability = Windows::System::SystemManagementUtil::HasSystemManagementCapability((unsigned __int8 *)&v6);
  if ( HasSystemManagementCapability < 0 )
    goto LABEL_10;
  if ( !(_BYTE)v6 )
  {
    HasSystemManagementCapability = -2147024891;
LABEL_10:
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xA1,
      (unsigned int)"onecoreuap\\windows\\iot\\winrt\\sysadmin\\lib\\shutdownmanager\\shutdownmanagerimpl.cpp",
      (const char *)(unsigned int)HasSystemManagementCapability,
      v6);
    goto LABEL_11;
  }
  v3 = RtlAcquirePrivilege(&Privilege, 1u, 0, &ReturnedState);
  v1 = v3;
  if ( v3 >= 0 )
  {
    if ( AbortSystemShutdownW(0) )
      goto LABEL_11;
    LastError = GetLastError();
    HasSystemManagementCapability = LastError;
    if ( LastError > 0 )
      HasSystemManagementCapability = (unsigned __int16)LastError | 0x80070000;
  }
  else
  {
    HasSystemManagementCapability = v3 | 0x10000000;
  }
  if ( HasSystemManagementCapability < 0 )
    goto LABEL_10;
LABEL_11:
  wil::ActivityBase<Windows::System::SysAdminTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
    v9,
    (unsigned int)HasSystemManagementCapability);
  if ( v1 >= 0 )
    RtlReleasePrivilege(ReturnedState);
  Windows::System::SysAdminTraceLoggingProvider::CancelShutdownActivity::~CancelShutdownActivity((Windows::System::SysAdminTraceLoggingProvider::CancelShutdownActivity *)v9);
  return (unsigned int)HasSystemManagementCapability;
}

```

## disassembly

```asm
0x18000d810  mov     [rsp-8+arg_0], rbx
0x18000d815  mov     [rsp-8+arg_8], rdi
0x18000d81a  push    rbp
0x18000d81b  lea     rbp, [rsp-0A0h]
0x18000d823  sub     rsp, 1A0h
0x18000d82a  mov     rax, cs:__security_cookie
0x18000d831  xor     rax, rsp
0x18000d834  mov     [rbp+0A0h+var_10], rax
0x18000d83b  lea     rdx, aCancelshutdown; "CancelShutdownActivity"
0x18000d842  mov     [rsp+1A0h+Privilege], 13h
0x18000d84a  lea     rcx, [rsp+1A0h+var_160]
0x18000d84f  mov     [rsp+1A0h+ReturnedState], 0
0x18000d858  mov     edi, 0C0000061h
0x18000d85d  mov     byte ptr [rsp+1A0h+var_180], 0; int
0x18000d862  call    ??0?$ActivityBase@VSysAdminTraceLoggingProvider@System@Windows@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<Windows::System::SysAdminTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Windows::System::SysAdminTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18000d867  lea     rax, ??_7CancelShutdownActivity@SysAdminTraceLoggingProvider@System@Windows@@6B@; const Windows::System::SysAdminTraceLoggingProvider::CancelShutdownActivity::`vftable'
0x18000d86e  lea     rcx, [rsp+1A0h+var_160]; this
0x18000d873  mov     [rsp+1A0h+var_160], rax
0x18000d878  call    ?StartActivity@CancelShutdownActivity@SysAdminTraceLoggingProvider@System@Windows@@QEAAXXZ; Windows::System::SysAdminTraceLoggingProvider::CancelShutdownActivity::StartActivity(void)
0x18000d87d  lea     rcx, [rsp+1A0h+var_180]; unsigned __int8 *
0x18000d882  call    ?HasSystemManagementCapability@SystemManagementUtil@System@Windows@@SAJPEAE@Z; Windows::System::SystemManagementUtil::HasSystemManagementCapability(uchar *)
0x18000d887  mov     ebx, eax
0x18000d889  test    eax, eax
0x18000d88b  js      short loc_18000D8E5
0x18000d88d  cmp     byte ptr [rsp+1A0h+var_180], 0
0x18000d892  jnz     short loc_18000D89B
0x18000d894  mov     ebx, 80070005h
0x18000d899  jmp     short loc_18000D8E5
0x18000d89b  xor     r8d, r8d; Flags
0x18000d89e  lea     r9, [rsp+1A0h+ReturnedState]; ReturnedState
0x18000d8a3  lea     rcx, [rsp+1A0h+Privilege]; Privilege
0x18000d8a8  lea     edx, [r8+1]; NumPriv
0x18000d8ac  call    cs:__imp_RtlAcquirePrivilege
0x18000d8b2  mov     edi, eax
0x18000d8b4  test    eax, eax
0x18000d8b6  jns     short loc_18000D8C0
0x18000d8b8  mov     ebx, eax
0x18000d8ba  bts     ebx, 1Ch
0x18000d8be  jmp     short loc_18000D8E1
0x18000d8c0  xor     ecx, ecx; lpMachineName
0x18000d8c2  call    cs:__imp_AbortSystemShutdownW
0x18000d8c8  test    eax, eax
0x18000d8ca  jnz     short loc_18000D900
0x18000d8cc  call    cs:__imp_GetLastError
0x18000d8d2  mov     ebx, eax
0x18000d8d4  test    eax, eax
0x18000d8d6  jle     short loc_18000D8E1
0x18000d8d8  movzx   ebx, ax
0x18000d8db  or      ebx, 80070000h
0x18000d8e1  test    ebx, ebx
0x18000d8e3  jns     short loc_18000D900
0x18000d8e5  mov     rcx, [rbp+0A8h]; this
0x18000d8ec  lea     r8, aOnecoreuapWind_2; "onecoreuap\\windows\\iot\\winrt\\sysadm"...
0x18000d8f3  mov     r9d, ebx; char *
0x18000d8f6  mov     edx, 0A1h; void *
0x18000d8fb  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000d900  mov     edx, ebx
0x18000d902  lea     rcx, [rsp+1A0h+var_160]
0x18000d907  call    ?Stop@?$ActivityBase@VSysAdminTraceLoggingProvider@System@Windows@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<Windows::System::SysAdminTraceLoggingProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18000d90c  test    edi, edi
0x18000d90e  js      short loc_18000D91B
0x18000d910  mov     rcx, [rsp+1A0h+ReturnedState]; ReturnedState
0x18000d915  call    cs:__imp_RtlReleasePrivilege
0x18000d91b  lea     rcx, [rsp+1A0h+var_160]; this
0x18000d920  call    ??1CancelShutdownActivity@SysAdminTraceLoggingProvider@System@Windows@@QEAA@XZ; Windows::System::SysAdminTraceLoggingProvider::CancelShutdownActivity::~CancelShutdownActivity(void)
0x18000d925  mov     eax, ebx
0x18000d927  mov     rcx, [rbp+0A0h+var_10]
0x18000d92e  xor     rcx, rsp; StackCookie
0x18000d931  call    __security_check_cookie
0x18000d936  lea     r11, [rsp+1A0h+var_s0]
0x18000d93e  mov     rbx, [r11+10h]
0x18000d942  mov     rdi, [r11+18h]
0x18000d946  mov     rsp, r11
0x18000d949  pop     rbp
0x18000d94a  retn
```
