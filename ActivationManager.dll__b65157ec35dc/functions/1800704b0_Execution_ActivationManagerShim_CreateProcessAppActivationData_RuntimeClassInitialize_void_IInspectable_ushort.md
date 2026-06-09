# Execution::ActivationManagerShim::CreateProcessAppActivationData::RuntimeClassInitialize(void *,IInspectable *,ushort const *)

- ea: `0x1800704b0`
- end: `0x18007075a`
- name: `?RuntimeClassInitialize@CreateProcessAppActivationData@ActivationManagerShim@Execution@@QEAAJPEAXPEAUIInspectable@@PEBG@Z`
- size: `682`
- prototype: `__int64 __fastcall(Execution::ActivationManagerShim::CreateProcessAppActivationData *this, void *, struct IInspectable *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180068f8c`

## callees

- `0x18000b5c0`
- `0x18000cbc0`
- `0x180011328`
- `0x180017da4`
- `0x180027bd0`
- `0x180027ce8`
- `0x18003f63c`
- `0x180044408`
- `0x1800445ac`
- `0x1800483cc`
- `0x18005ae90`
- `0x1800690ec`
- `0x1800704b0`
- `0x18007b560`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180070503`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18007050c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180070503`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18007050c`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180070577`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180070577`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180070538`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180070538`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180070661`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800706aa`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180070661`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800706aa`
- `api-ms-win-appmodel-runtime-l1-1-1!GetApplicationUserModelIdFromToken` at `0x1800705de`
- `api-ms-win-appmodel-runtime-l1-1-1!GetApplicationUserModelIdFromToken` at `0x1800705de`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrOpenProcessTokenForQuery` at `0x180070592`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrOpenProcessTokenForQuery` at `0x180070592`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x1800705b1`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x1800705b1`

## string_xrefs

- `0x180070655`: `Windows.CommandLineLaunch`

## pseudocode

```c
__int64 __fastcall Execution::ActivationManagerShim::CreateProcessAppActivationData::RuntimeClassInitialize(
        Execution::ActivationManagerShim::CreateProcessAppActivationData *this,
        void *a2,
        struct IInspectable *a3,
        const unsigned __int16 *a4)
{
  HANDLE *v8; // r15
  HANDLE CurrentProcess; // rbx
  HANDLE v10; // rax
  const char *v11; // r9
  DWORD ProcessId; // ebx
  int UserContext; // eax
  unsigned int v15; // ebx
  __int64 v16; // rdx
  unsigned int ApplicationUserModelIdFromToken; // eax
  unsigned __int64 *v18; // r8
  __int64 v19; // r9
  DWORD dwDesiredAccess; // [rsp+20h] [rbp-E0h]
  HANDLE token; // [rsp+40h] [rbp-C0h] BYREF
  UINT32 applicationUserModelIdLength; // [rsp+48h] [rbp-B8h] BYREF
  const unsigned __int16 *v23; // [rsp+50h] [rbp-B0h]
  char *v24; // [rsp+58h] [rbp-A8h] BYREF
  HANDLE TargetHandle; // [rsp+60h] [rbp-A0h] BYREF
  char v26; // [rsp+68h] [rbp-98h]
  WCHAR applicationUserModelId[136]; // [rsp+70h] [rbp-90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+C8h]

  v23 = a4;
  v8 = (HANDLE *)((char *)this + 80);
  v24 = (char *)this + 80;
  TargetHandle = 0;
  v26 = 1;
  CurrentProcess = GetCurrentProcess();
  v10 = GetCurrentProcess();
  LODWORD(CurrentProcess) = DuplicateHandle(v10, a2, CurrentProcess, &TargetHandle, 0x100400u, 0, 0);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&v24);
  if ( !(_DWORD)CurrentProcess )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0xF4,
             (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\ActivationManagerShim.h",
             v11);
  token = 0;
  ProcessId = GetProcessId(*v8);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &token,
    0);
  UserContext = UMgrOpenProcessTokenForQuery(ProcessId, &token);
  v15 = UserContext;
  if ( UserContext < 0 )
  {
    v16 = 250;
    goto LABEL_19;
  }
  UserContext = UMgrQueryUserContext(token, (char *)this + 48);
  v15 = UserContext;
  if ( UserContext < 0 )
  {
    v16 = 252;
    goto LABEL_19;
  }
  applicationUserModelIdLength = 131;
  ApplicationUserModelIdFromToken = GetApplicationUserModelIdFromToken(
                                      token,
                                      &applicationUserModelIdLength,
                                      applicationUserModelId);
  if ( !ApplicationUserModelIdFromToken )
  {
    UserContext = Microsoft::WRL::Wrappers::HString::Set<131>((Execution::ActivationManagerShim::CreateProcessAppActivationData *)((char *)this + 56));
    v15 = UserContext;
    if ( UserContext >= 0 )
    {
      UserContext = DevPlat::Shared::GetHostIdFromProcessToken((DevPlat::Shared *)token, (char *)this + 72, v18);
      v15 = UserContext;
      if ( UserContext >= 0 )
      {
        if ( CompareStringOrdinal(a4, -1, L"Windows.CommandLineLaunch", -1, 1) == 2 )
        {
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease((char *)this + 96);
          UserContext = GetHamActivityForProcessHandle(
                          L"AppExecutionAlias",
                          token,
                          (struct HamActivityWrapper **)this + 12);
          v15 = UserContext;
          if ( UserContext < 0 )
          {
            v16 = 263;
            goto LABEL_19;
          }
        }
        else
        {
          if ( CompareStringOrdinal(a4, -1, L"Windows.Launch", -1, 1) != 2 )
          {
            v15 = -2147024809;
            v19 = 2147942487LL;
            v16 = 271;
            goto LABEL_22;
          }
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease((char *)this + 96);
          UserContext = GetHamActivityForProcessHandle(L"Activation", token, (struct HamActivityWrapper **)this + 12);
          v15 = UserContext;
          if ( UserContext < 0 )
          {
            v16 = 267;
            goto LABEL_19;
          }
        }
        Microsoft::WRL::Wrappers::HString::Set<unsigned short const *>((HSTRING *)this + 8);
        Microsoft::WRL::ComPtr<IInspectable>::operator=((char *)this + 88, a3);
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&token);
        return 0;
      }
      v16 = 259;
    }
    else
    {
      v16 = 257;
    }
LABEL_19:
    v19 = (unsigned int)UserContext;
LABEL_22:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\ActivationManagerShim.h",
      (const char *)v19,
      dwDesiredAccess);
    goto LABEL_23;
  }
  v15 = wil::details::in1diag3::Return_Win32(
          retaddr,
          (void *)0x100,
          (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\ActivationManagerShim.h",
          (const char *)ApplicationUserModelIdFromToken,
          dwDesiredAccess);
LABEL_23:
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&token);
  return v15;
}

```

## disassembly

```asm
0x1800704b0  push    rbp
0x1800704b2  push    rbx
0x1800704b3  push    rsi
0x1800704b4  push    rdi
0x1800704b5  push    r12
0x1800704b7  push    r14
0x1800704b9  push    r15
0x1800704bb  lea     rbp, [rsp-90h]
0x1800704c3  sub     rsp, 190h
0x1800704ca  mov     rax, cs:__security_cookie
0x1800704d1  xor     rax, rsp
0x1800704d4  mov     [rbp+0C0h+var_40], rax
0x1800704db  mov     r14, r9
0x1800704de  mov     r12, r8
0x1800704e1  mov     rdi, rdx
0x1800704e4  mov     rsi, rcx
0x1800704e7  mov     [rsp+1C0h+var_170], r9
0x1800704ec  lea     r15, [rcx+50h]
0x1800704f0  mov     [rsp+1C0h+var_168], r15
0x1800704f5  mov     [rsp+1C0h+TargetHandle], 0
0x1800704fe  mov     [rsp+1C0h+var_158], 1
0x180070503  call    cs:__imp_GetCurrentProcess
0x180070509  mov     rbx, rax
0x18007050c  call    cs:__imp_GetCurrentProcess
0x180070512  mov     [rsp+1C0h+dwOptions], 0; dwOptions
0x18007051a  mov     [rsp+1C0h+bInheritHandle], 0; bInheritHandle
0x180070522  mov     [rsp+1C0h+dwDesiredAccess], 100400h; unsigned int
0x18007052a  lea     r9, [rsp+1C0h+TargetHandle]; lpTargetHandle
0x18007052f  mov     r8, rbx; hTargetProcessHandle
0x180070532  mov     rdx, rdi; hSourceHandle
0x180070535  mov     rcx, rax; hSourceProcessHandle
0x180070538  call    cs:__imp_DuplicateHandle
0x18007053e  mov     ebx, eax
0x180070540  lea     rcx, [rsp+1C0h+var_168]
0x180070545  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x18007054a  test    ebx, ebx
0x18007054c  jnz     short loc_18007056B
0x18007054e  mov     rcx, [rbp+0C8h]; this
0x180070555  lea     r8, aOnecoreuapBase_27; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18007055c  mov     edx, 0F4h; void *
0x180070561  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180070566  jmp     loc_180070739
0x18007056b  mov     [rsp+1C0h+token], 0
0x180070574  mov     rcx, [r15]; Process
0x180070577  call    cs:__imp_GetProcessId
0x18007057d  mov     ebx, eax
0x18007057f  xor     edx, edx
0x180070581  lea     rcx, [rsp+1C0h+token]
0x180070586  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18007058b  lea     rdx, [rsp+1C0h+token]
0x180070590  mov     ecx, ebx
0x180070592  call    cs:__imp_UMgrOpenProcessTokenForQuery
0x180070598  mov     ebx, eax
0x18007059a  test    eax, eax
0x18007059c  jns     short loc_1800705A8
0x18007059e  mov     edx, 0FAh
0x1800705a3  jmp     loc_1800706DE
0x1800705a8  lea     rdx, [rsi+30h]
0x1800705ac  mov     rcx, [rsp+1C0h+token]
0x1800705b1  call    cs:__imp_UMgrQueryUserContext
0x1800705b7  mov     ebx, eax
0x1800705b9  test    eax, eax
0x1800705bb  jns     short loc_1800705C7
0x1800705bd  mov     edx, 0FCh
0x1800705c2  jmp     loc_1800706DE
0x1800705c7  mov     [rsp+1C0h+applicationUserModelIdLength], 83h
0x1800705cf  lea     r8, [rsp+1C0h+applicationUserModelId]; applicationUserModelId
0x1800705d4  lea     rdx, [rsp+1C0h+applicationUserModelIdLength]; applicationUserModelIdLength
0x1800705d9  mov     rcx, [rsp+1C0h+token]; token
0x1800705de  call    cs:__imp_GetApplicationUserModelIdFromToken
0x1800705e4  test    eax, eax
0x1800705e6  jz      short loc_18007060A
0x1800705e8  mov     rcx, [rbp+0C8h]; this
0x1800705ef  mov     r9d, eax; char *
0x1800705f2  lea     r8, aOnecoreuapBase_27; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x1800705f9  mov     edx, 100h; void *
0x1800705fe  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180070603  mov     ebx, eax
0x180070605  jmp     loc_18007072D
0x18007060a  lea     rcx, [rsi+38h]; this
0x18007060e  lea     rdx, [rsp+1C0h+applicationUserModelId]
0x180070613  call    ??$Set@$0ID@@HString@Wrappers@WRL@Microsoft@@QEAAJAEAY0ID@G@Z; Microsoft::WRL::Wrappers::HString::Set<131>(ushort (&)[131])
0x180070618  mov     ebx, eax
0x18007061a  test    eax, eax
0x18007061c  jns     short loc_180070628
0x18007061e  mov     edx, 101h
0x180070623  jmp     loc_1800706DE
0x180070628  lea     rdx, [rsi+48h]; void *
0x18007062c  mov     rcx, [rsp+1C0h+token]; this
0x180070631  call    ?GetHostIdFromProcessToken@Shared@DevPlat@@YAJPEAXPEA_K@Z; DevPlat::Shared::GetHostIdFromProcessToken(void *,unsigned __int64 *)
0x180070636  mov     ebx, eax
0x180070638  test    eax, eax
0x18007063a  jns     short loc_180070646
0x18007063c  mov     edx, 103h
0x180070641  jmp     loc_1800706DE
0x180070646  mov     edi, 1
0x18007064b  mov     [rsp+1C0h+dwDesiredAccess], edi; bIgnoreCase
0x18007064f  or      ebx, 0FFFFFFFFh
0x180070652  mov     r9d, ebx; cchCount2
0x180070655  lea     r8, aWindowsCommand; "Windows.CommandLineLaunch"
0x18007065c  mov     edx, ebx; cchCount1
0x18007065e  mov     rcx, r14; lpString1
0x180070661  call    cs:__imp_CompareStringOrdinal
0x180070667  cmp     eax, 2
0x18007066a  jnz     short loc_180070697
0x18007066c  lea     rcx, [rsi+60h]
0x180070670  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180070675  lea     r8, [rsi+60h]; struct HamActivityWrapper **
0x180070679  mov     rdx, [rsp+1C0h+token]; TokenHandle
0x18007067e  lea     rcx, aAppexecutional; "AppExecutionAlias"
0x180070685  call    ?GetHamActivityForProcessHandle@@YAJPEBGPEAXPEAPEAVHamActivityWrapper@@@Z; GetHamActivityForProcessHandle(ushort const *,void *,HamActivityWrapper * *)
0x18007068a  mov     ebx, eax
0x18007068c  test    eax, eax
0x18007068e  jns     short loc_1800706E3
0x180070690  mov     edx, 107h
0x180070695  jmp     short loc_1800706DE
0x180070697  mov     [rsp+1C0h+dwDesiredAccess], edi; int
0x18007069b  mov     r9d, ebx; cchCount2
0x18007069e  lea     r8, String2; "Windows.Launch"
0x1800706a5  mov     edx, ebx; cchCount1
0x1800706a7  mov     rcx, r14; lpString1
0x1800706aa  call    cs:__imp_CompareStringOrdinal
0x1800706b0  cmp     eax, 2
0x1800706b3  jnz     short loc_18007070C
0x1800706b5  lea     rcx, [rsi+60h]
0x1800706b9  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800706be  lea     r8, [rsi+60h]; struct HamActivityWrapper **
0x1800706c2  mov     rdx, [rsp+1C0h+token]; TokenHandle
0x1800706c7  lea     rcx, aActivation; "Activation"
0x1800706ce  call    ?GetHamActivityForProcessHandle@@YAJPEBGPEAXPEAPEAVHamActivityWrapper@@@Z; GetHamActivityForProcessHandle(ushort const *,void *,HamActivityWrapper * *)
0x1800706d3  mov     ebx, eax
0x1800706d5  test    eax, eax
0x1800706d7  jns     short loc_1800706E3
0x1800706d9  mov     edx, 10Bh
0x1800706de  mov     r9d, eax
0x1800706e1  jmp     short loc_180070719
0x1800706e3  lea     rcx, [rsi+40h]; string
0x1800706e7  lea     rdx, [rsp+1C0h+var_170]
0x1800706ec  call    ??$Set@PEBG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort const *>(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800706f1  lea     rcx, [rsi+58h]
0x1800706f5  mov     rdx, r12
0x1800706f8  call    ??4?$ComPtr@UIInspectable@@@WRL@Microsoft@@QEAAAEAV012@PEAUIInspectable@@@Z; Microsoft::WRL::ComPtr<IInspectable>::operator=(IInspectable *)
0x1800706fd  nop
0x1800706fe  lea     rcx, [rsp+1C0h+token]
0x180070703  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180070708  xor     eax, eax
0x18007070a  jmp     short loc_180070739
0x18007070c  mov     ebx, 80070057h
0x180070711  mov     r9d, ebx; char *
0x180070714  mov     edx, 10Fh; void *
0x180070719  lea     r8, aOnecoreuapBase_27; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180070720  mov     rcx, [rbp+0C8h]; this
0x180070727  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007072c  nop
0x18007072d  lea     rcx, [rsp+1C0h+token]
0x180070732  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180070737  mov     eax, ebx
0x180070739  mov     rcx, [rbp+0C0h+var_40]
0x180070740  xor     rcx, rsp; StackCookie
0x180070743  call    __security_check_cookie
0x180070748  add     rsp, 190h
0x18007074f  pop     r15
0x180070751  pop     r14
0x180070753  pop     r12
0x180070755  pop     rdi
0x180070756  pop     rsi
0x180070757  pop     rbx
0x180070758  pop     rbp
0x180070759  retn
```
