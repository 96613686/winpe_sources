# StorageReserveHelper::Internal::EnablePrivilege(ushort const *)

- ea: `0x18002ab10`
- end: `0x18002abe8`
- name: `?EnablePrivilege@Internal@StorageReserveHelper@@YA_NPEBG@Z`
- size: `216`
- prototype: `bool __fastcall(StorageReserveHelper::Internal *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180028560`

## callees

- `0x1800050f0`
- `0x180010440`
- `0x1800168c8`
- `0x18002ab10`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18002abb7`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18002abb7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002ab4c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002ab4c`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18002ab5e`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18002ab5e`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x18002ab80`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x18002ab80`

## string_xrefs

- `0x18002ab77`: `SeManageVolumePrivilege`

## pseudocode

```c
bool __fastcall StorageReserveHelper::Internal::EnablePrivilege(
        StorageReserveHelper::Internal *this,
        const unsigned __int16 *a2)
{
  BOOL v2; // ebx
  HANDLE CurrentProcess; // rax
  void *TokenHandle; // [rsp+30h] [rbp-30h] BYREF
  struct _LUID Luid; // [rsp+38h] [rbp-28h] BYREF
  struct _TOKEN_PRIVILEGES NewState; // [rsp+40h] [rbp-20h] BYREF

  v2 = 0;
  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0x20u, &TokenHandle) )
  {
    NewState = 0;
    Luid = 0;
    if ( LookupPrivilegeValueW(0, L"SeManageVolumePrivilege", &Luid) )
    {
      NewState.PrivilegeCount = 1;
      NewState.Privileges[0].Luid = Luid;
      NewState.Privileges[0].Attributes = 2;
      v2 = AdjustTokenPrivileges(TokenHandle, 0, &NewState, 0, 0, 0);
    }
  }
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  return v2;
}

```

## disassembly

```asm
0x18002ab10  mov     [rsp-8+arg_0], rbx
0x18002ab15  push    rbp
0x18002ab16  mov     rbp, rsp
0x18002ab19  sub     rsp, 60h
0x18002ab1d  mov     rax, cs:__security_cookie
0x18002ab24  xor     rax, rsp
0x18002ab27  mov     [rbp+var_10], rax
0x18002ab2b  mov     [rbp+TokenHandle], 0
0x18002ab33  xor     ebx, ebx
0x18002ab35  mov     rcx, [rbp+TokenHandle]; hObject
0x18002ab39  lea     rax, [rcx-1]
0x18002ab3d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002ab41  ja      short loc_18002AB48
0x18002ab43  call    ?close_reset@?$close_invoke_helper@$00P6AHPEAX@Z$1?CloseHandle@@YAH0@ZPEAX@details@wil@@SAXPEAX@Z; wil::details::close_invoke_helper<1,int (*)(void *),&CloseHandle(void *),void *>::close_reset(void *)
0x18002ab48  mov     [rbp+TokenHandle], rbx
0x18002ab4c  call    cs:__imp_GetCurrentProcess
0x18002ab52  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18002ab56  mov     edx, 20h ; ' '; DesiredAccess
0x18002ab5b  mov     rcx, rax; ProcessHandle
0x18002ab5e  call    cs:__imp_OpenProcessToken
0x18002ab64  test    eax, eax
0x18002ab66  jz      short loc_18002ABBF
0x18002ab68  xorps   xmm0, xmm0
0x18002ab6b  movups  xmmword ptr [rbp+NewState.PrivilegeCount], xmm0
0x18002ab6f  mov     qword ptr [rbp+Luid.LowPart], rbx
0x18002ab73  lea     r8, [rbp+Luid]; lpLuid
0x18002ab77  lea     rdx, aSemanagevolume; "SeManageVolumePrivilege"
0x18002ab7e  xor     ecx, ecx; lpSystemName
0x18002ab80  call    cs:__imp_LookupPrivilegeValueW
0x18002ab86  test    eax, eax
0x18002ab88  jz      short loc_18002ABBF
0x18002ab8a  mov     [rbp+NewState.PrivilegeCount], 1
0x18002ab91  mov     rax, qword ptr [rbp+Luid.LowPart]
0x18002ab95  mov     qword ptr [rbp+NewState.Privileges.Luid.LowPart], rax
0x18002ab99  mov     [rbp+NewState.Privileges.Attributes], 2
0x18002aba0  mov     [rsp+60h+ReturnLength], rbx; ReturnLength
0x18002aba5  mov     [rsp+60h+PreviousState], rbx; PreviousState
0x18002abaa  xor     r9d, r9d; BufferLength
0x18002abad  lea     r8, [rbp+NewState]; NewState
0x18002abb1  xor     edx, edx; DisableAllPrivileges
0x18002abb3  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18002abb7  call    cs:__imp_AdjustTokenPrivileges
0x18002abbd  mov     ebx, eax
0x18002abbf  cmp     ebx, 1
0x18002abc2  setz    bl
0x18002abc5  lea     rcx, [rbp+TokenHandle]
0x18002abc9  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002abce  nop
0x18002abcf  mov     al, bl
0x18002abd1  mov     rcx, [rbp+var_10]
0x18002abd5  xor     rcx, rsp; StackCookie
0x18002abd8  call    __security_check_cookie
0x18002abdd  mov     rbx, [rsp+60h+arg_0]
0x18002abe2  add     rsp, 60h
0x18002abe6  pop     rbp
0x18002abe7  retn
```
