# CWindowsPolicyManager::RpcSetAccessibilityAudioMonoMixState(int)

- ea: `0x180044970`
- end: `0x180044bbc`
- name: `?RpcSetAccessibilityAudioMonoMixState@CWindowsPolicyManager@@UEAAJH@Z`
- size: `588`
- prototype: `__int64 __fastcall(CWindowsPolicyManager *__hidden this, int)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180001c74`
- `0x180001d40`
- `0x180003554`
- `0x180003694`
- `0x180003b60`
- `0x18000a384`
- `0x180012844`
- `0x18001d070`
- `0x1800232a0`
- `0x1800427e4`
- `0x180044970`
- `0x18004c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180044b7d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180044b7d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180044aca`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180044aca`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180044a41`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180044a41`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180044b28`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180044b28`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180044a6e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180044afb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180044b8c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180044b9b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180044a6e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180044afb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180044b8c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180044b9b`
- `RPCRT4!RpcRevertToSelf` at `0x180044a74`
- `RPCRT4!RpcRevertToSelf` at `0x180044ba1`
- `RPCRT4!RpcRevertToSelf` at `0x180044a74`
- `RPCRT4!RpcRevertToSelf` at `0x180044ba1`
- `RPCRT4!RpcImpersonateClient` at `0x1800449fa`
- `RPCRT4!RpcImpersonateClient` at `0x1800449fa`

## string_xrefs

- `0x180044b1d`: `AccessibilityMonoMixState`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CWindowsPolicyManager::RpcSetAccessibilityAudioMonoMixState(CWindowsPolicyManager *this, int a2)
{
  int Process; // eax
  unsigned int v3; // ebx
  __int64 v4; // rdx
  unsigned int v5; // eax
  unsigned int v6; // edi
  bool v7; // bl
  unsigned int v8; // eax
  unsigned int v9; // eax
  unsigned int v10; // eax
  __int64 v11; // rdx
  __int64 v12; // rcx
  int v13; // ebx
  unsigned int dwOptions; // [rsp+20h] [rbp-50h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-50h]
  struct IAudioProcess *v17; // [rsp+50h] [rbp-20h] BYREF
  struct TSSession *v18; // [rsp+58h] [rbp-18h] BYREF
  LPCRITICAL_SECTION lpCriticalSection[2]; // [rsp+60h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]
  int Data; // [rsp+98h] [rbp+28h] BYREF
  HKEY phkResult; // [rsp+A0h] [rbp+30h] BYREF
  HKEY hKey; // [rsp+A8h] [rbp+38h] BYREF

  Data = a2;
  v17 = 0;
  Process = CWindowsPolicyManager::RpcGetProcess(this, 0, &v17);
  v3 = Process;
  if ( Process < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x25A,
      (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\windowspolicymanager.cpp",
      (const char *)(unsigned int)Process,
      dwOptions);
    goto LABEL_31;
  }
  v5 = (*(__int64 (__fastcall **)(struct IAudioProcess *))(*(_QWORD *)v17 + 48LL))(v17);
  v6 = v5;
  if ( !v5 )
    goto LABEL_30;
  if ( !TsSessionIdAreAccessibilityAudioSettingsInitialized(v5) )
    TsSessionIdInitAccessibilityAudioSettings(v6, 0);
  v7 = Data != 0;
  if ( TsSessionIdGetAccessibilityAudioMonoMixState(v6) == v7 )
    goto LABEL_30;
  v8 = RpcImpersonateClient(0);
  if ( v8 )
  {
    v3 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x26B,
           (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\windowspolicymanager.cpp",
           (const char *)v8,
           dwOptions);
    goto LABEL_31;
  }
  phkResult = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &phkResult,
    0);
  v9 = RegOpenCurrentUser(0xF003Fu, &phkResult);
  if ( !v9 )
  {
    hKey = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hKey,
      0);
    v10 = RegCreateKeyExW(phkResult, L"Software\\Microsoft\\Multimedia\\Audio", 0, 0, 0, 0xF003Fu, 0, &hKey, 0);
    if ( v10 )
    {
      v11 = 627;
      goto LABEL_16;
    }
    v10 = RegSetValueExW(hKey, L"AccessibilityMonoMixState", 0, 4u, (const BYTE *)&Data, 4u);
    if ( v10 )
    {
      v11 = 629;
LABEL_16:
      v3 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v11,
             (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\windowspolicymanager.cpp",
             (const char *)v10,
             dwOptionsa);
      if ( hKey )
        RegCloseKey(hKey);
      goto LABEL_11;
    }
    v13 = Data;
    CWindowsPolicyManager::Lock(v12, lpCriticalSection);
    v18 = 0;
    if ( (int)TsSessionFromSessionId(v6, 1, &v18) >= 0 && *((_DWORD *)v18 + 268) )
      *((_DWORD *)v18 + 269) = v13;
    if ( lpCriticalSection[0] )
      LeaveCriticalSection(lpCriticalSection[0]);
    if ( hKey )
      RegCloseKey(hKey);
    if ( phkResult )
      RegCloseKey(phkResult);
    RpcRevertToSelf();
LABEL_30:
    v3 = 0;
    goto LABEL_31;
  }
  v3 = wil::details::in1diag3::Return_Win32(
         retaddr,
         (void *)0x270,
         (unsigned int)"clientcore\\multimedia\\audiocore\\server\\audiosrv\\windowspolicymanager\\windowspolicymanager.cpp",
         (const char *)v9,
         dwOptions);
LABEL_11:
  if ( phkResult )
    RegCloseKey(phkResult);
  RpcRevertToSelf();
LABEL_31:
  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(
    &v17,
    v4);
  return v3;
}

```

## disassembly

```asm
0x180044970  mov     [rsp-18h+Data], edx
0x180044974  push    rbp
0x180044975  push    rbx
0x180044976  push    rdi
0x180044977  mov     rbp, rsp
0x18004497a  sub     rsp, 70h
0x18004497e  mov     [rbp+var_20], 0
0x180044986  lea     r8, [rbp+var_20]; struct IAudioProcess **
0x18004498a  xor     edx, edx; void *
0x18004498c  call    ?RpcGetProcess@CWindowsPolicyManager@@UEAAJPEAXPEAPEAUIAudioProcess@@@Z; CWindowsPolicyManager::RpcGetProcess(void *,IAudioProcess * *)
0x180044991  mov     ebx, eax
0x180044993  test    eax, eax
0x180044995  jns     short loc_1800449B4
0x180044997  mov     rcx, [rbp+18h]; this
0x18004499b  mov     r9d, eax; char *
0x18004499e  lea     r8, aClientcoreMult_2; "clientcore\\multimedia\\audiocore\\serv"...
0x1800449a5  mov     edx, 25Ah; void *
0x1800449aa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800449af  jmp     loc_180044BA9
0x1800449b4  mov     rcx, [rbp+var_20]
0x1800449b8  mov     rax, [rcx]
0x1800449bb  mov     rax, [rax+30h]
0x1800449bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800449c4  mov     edi, eax
0x1800449c6  test    eax, eax
0x1800449c8  jz      loc_180044BA7
0x1800449ce  mov     ecx, eax; unsigned int
0x1800449d0  call    ?TsSessionIdAreAccessibilityAudioSettingsInitialized@@YA_NK@Z; TsSessionIdAreAccessibilityAudioSettingsInitialized(ulong)
0x1800449d5  test    al, al
0x1800449d7  jnz     short loc_1800449E2
0x1800449d9  xor     edx, edx; int
0x1800449db  mov     ecx, edi; unsigned int
0x1800449dd  call    ?TsSessionIdInitAccessibilityAudioSettings@@YAXKH@Z; TsSessionIdInitAccessibilityAudioSettings(ulong,int)
0x1800449e2  cmp     [rbp+Data], 0
0x1800449e6  setnz   bl
0x1800449e9  mov     ecx, edi; unsigned int
0x1800449eb  call    ?TsSessionIdGetAccessibilityAudioMonoMixState@@YA_NK@Z; TsSessionIdGetAccessibilityAudioMonoMixState(ulong)
0x1800449f0  cmp     al, bl
0x1800449f2  jz      loc_180044BA7
0x1800449f8  xor     ecx, ecx; BindingHandle
0x1800449fa  call    cs:__imp_RpcImpersonateClient
0x180044a00  test    eax, eax
0x180044a02  jz      short loc_180044A23
0x180044a04  mov     rcx, [rbp+18h]; this
0x180044a08  mov     r9d, eax; char *
0x180044a0b  lea     r8, aClientcoreMult_2; "clientcore\\multimedia\\audiocore\\serv"...
0x180044a12  mov     edx, 26Bh; void *
0x180044a17  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180044a1c  mov     ebx, eax
0x180044a1e  jmp     loc_180044BA9
0x180044a23  mov     [rbp+phkResult], 0
0x180044a2b  xor     edx, edx
0x180044a2d  lea     rcx, [rbp+phkResult]
0x180044a31  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180044a36  lea     rdx, [rbp+phkResult]; phkResult
0x180044a3a  mov     ebx, 0F003Fh
0x180044a3f  mov     ecx, ebx; samDesired
0x180044a41  call    cs:__imp_RegOpenCurrentUser
0x180044a47  test    eax, eax
0x180044a49  jz      short loc_180044A7F
0x180044a4b  mov     rcx, [rbp+18h]; this
0x180044a4f  mov     r9d, eax; char *
0x180044a52  lea     r8, aClientcoreMult_2; "clientcore\\multimedia\\audiocore\\serv"...
0x180044a59  mov     edx, 270h; void *
0x180044a5e  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180044a63  mov     ebx, eax
0x180044a65  mov     rcx, [rbp+phkResult]; hKey
0x180044a69  test    rcx, rcx
0x180044a6c  jz      short loc_180044A74
0x180044a6e  call    cs:__imp_RegCloseKey
0x180044a74  call    cs:__imp_RpcRevertToSelf
0x180044a7a  jmp     loc_180044BA9
0x180044a7f  mov     [rbp+hKey], 0
0x180044a87  xor     edx, edx
0x180044a89  lea     rcx, [rbp+hKey]
0x180044a8d  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180044a92  mov     [rsp+70h+lpdwDisposition], 0; lpdwDisposition
0x180044a9b  lea     rax, [rbp+hKey]
0x180044a9f  mov     [rsp+70h+var_38], rax; phkResult
0x180044aa4  mov     [rsp+70h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180044aad  mov     [rsp+70h+samDesired], ebx; samDesired
0x180044ab1  mov     [rsp+70h+dwOptions], 0; unsigned int
0x180044ab9  xor     r9d, r9d; lpClass
0x180044abc  xor     r8d, r8d; Reserved
0x180044abf  lea     rdx, SubKey; "Software\\Microsoft\\Multimedia\\Audio"
0x180044ac6  mov     rcx, [rbp+phkResult]; hKey
0x180044aca  call    cs:__imp_RegCreateKeyExW
0x180044ad0  test    eax, eax
0x180044ad2  jz      short loc_180044B06
0x180044ad4  mov     edx, 273h; void *
0x180044ad9  mov     r9d, eax; char *
0x180044adc  lea     r8, aClientcoreMult_2; "clientcore\\multimedia\\audiocore\\serv"...
0x180044ae3  mov     rcx, [rbp+18h]; this
0x180044ae7  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180044aec  mov     rcx, [rbp+hKey]; hKey
0x180044af0  test    rcx, rcx
0x180044af3  mov     ebx, eax
0x180044af5  jz      loc_180044A65
0x180044afb  call    cs:__imp_RegCloseKey
0x180044b01  jmp     loc_180044A65
0x180044b06  mov     r9d, 4; dwType
0x180044b0c  mov     [rsp+70h+samDesired], r9d; cbData
0x180044b11  lea     rax, [rbp+Data]
0x180044b15  mov     qword ptr [rsp+70h+dwOptions], rax; lpData
0x180044b1a  xor     r8d, r8d; Reserved
0x180044b1d  lea     rdx, aAccessibilitym; "AccessibilityMonoMixState"
0x180044b24  mov     rcx, [rbp+hKey]; hKey
0x180044b28  call    cs:__imp_RegSetValueExW
0x180044b2e  test    eax, eax
0x180044b30  jz      short loc_180044B39
0x180044b32  mov     edx, 275h
0x180044b37  jmp     short loc_180044AD9
0x180044b39  mov     ebx, [rbp+Data]
0x180044b3c  lea     rdx, [rbp+lpCriticalSection]
0x180044b40  call    ?Lock@CWindowsPolicyManager@@UEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@XZ; CWindowsPolicyManager::Lock(void)
0x180044b45  mov     [rbp+var_18], 0
0x180044b4d  lea     r8, [rbp+var_18]; struct TSSession **
0x180044b51  mov     edx, 1; int
0x180044b56  mov     ecx, edi; unsigned int
0x180044b58  call    ?TsSessionFromSessionId@@YAJKHPEAPEAVTSSession@@@Z; TsSessionFromSessionId(ulong,int,TSSession * *)
0x180044b5d  test    eax, eax
0x180044b5f  js      short loc_180044B74
0x180044b61  mov     rax, [rbp+var_18]
0x180044b65  cmp     dword ptr [rax+430h], 0
0x180044b6c  jz      short loc_180044B74
0x180044b6e  mov     [rax+434h], ebx
0x180044b74  mov     rcx, [rbp+lpCriticalSection]; lpCriticalSection
0x180044b78  test    rcx, rcx
0x180044b7b  jz      short loc_180044B83
0x180044b7d  call    cs:__imp_LeaveCriticalSection
0x180044b83  mov     rcx, [rbp+hKey]; hKey
0x180044b87  test    rcx, rcx
0x180044b8a  jz      short loc_180044B92
0x180044b8c  call    cs:__imp_RegCloseKey
0x180044b92  mov     rcx, [rbp+phkResult]; hKey
0x180044b96  test    rcx, rcx
0x180044b99  jz      short loc_180044BA1
0x180044b9b  call    cs:__imp_RegCloseKey
0x180044ba1  call    cs:__imp_RpcRevertToSelf
0x180044ba7  xor     ebx, ebx
0x180044ba9  lea     rcx, [rbp+var_20]
0x180044bad  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180044bb2  mov     eax, ebx
0x180044bb4  add     rsp, 70h
0x180044bb8  pop     rdi
0x180044bb9  pop     rbx
0x180044bba  pop     rbp
0x180044bbb  retn
```
