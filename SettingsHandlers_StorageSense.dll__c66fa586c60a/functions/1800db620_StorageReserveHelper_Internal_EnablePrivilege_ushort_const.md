# StorageReserveHelper::Internal::EnablePrivilege(ushort const *)

- ea: `0x1800db620`
- end: `0x1800db6f4`
- name: `?EnablePrivilege@Internal@StorageReserveHelper@@YA_NPEBG@Z`
- size: `212`
- prototype: `bool __fastcall(StorageReserveHelper::Internal *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800dacd0`

## callees

- `0x180006e50`
- `0x180029264`
- `0x180035b90`
- `0x1800db620`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800db656`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800db656`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800db665`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800db665`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x1800db6be`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x1800db6be`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x1800db687`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x1800db687`

## string_xrefs

- `0x1800db67e`: `SeManageVolumePrivilege`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool __fastcall StorageReserveHelper::Internal::EnablePrivilege(
        StorageReserveHelper::Internal *this,
        const unsigned __int16 *a2)
{
  BOOL v2; // edi
  void **v3; // rbx
  HANDLE CurrentProcess; // rax
  HANDLE TokenHandle; // [rsp+30h] [rbp-30h] BYREF
  _LUID Luid; // [rsp+38h] [rbp-28h] BYREF
  _TOKEN_PRIVILEGES NewState; // [rsp+40h] [rbp-20h] BYREF

  TokenHandle = 0;
  v2 = 0;
  v3 = (void **)wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::put(&TokenHandle);
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0x20u, v3) )
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
0x1800db620  mov     [rsp-8+arg_0], rbx
0x1800db625  mov     [rsp-8+arg_8], rdi
0x1800db62a  push    rbp
0x1800db62b  mov     rbp, rsp
0x1800db62e  sub     rsp, 60h
0x1800db632  mov     rax, cs:__security_cookie
0x1800db639  xor     rax, rsp
0x1800db63c  mov     [rbp+var_10], rax
0x1800db640  mov     [rbp+TokenHandle], 0
0x1800db648  xor     edi, edi
0x1800db64a  lea     rcx, [rbp+TokenHandle]
0x1800db64e  call    ?put@?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::put(void)
0x1800db653  mov     rbx, rax
0x1800db656  call    cs:__imp_GetCurrentProcess
0x1800db65c  mov     r8, rbx; TokenHandle
0x1800db65f  lea     edx, [rdi+20h]; DesiredAccess
0x1800db662  mov     rcx, rax; ProcessHandle
0x1800db665  call    cs:__imp_OpenProcessToken
0x1800db66b  test    eax, eax
0x1800db66d  jz      short loc_1800DB6C6
0x1800db66f  xorps   xmm0, xmm0
0x1800db672  movups  xmmword ptr [rbp+NewState.PrivilegeCount], xmm0
0x1800db676  mov     qword ptr [rbp+Luid.LowPart], rdi
0x1800db67a  lea     r8, [rbp+Luid]; lpLuid
0x1800db67e  lea     rdx, aSemanagevolume; "SeManageVolumePrivilege"
0x1800db685  xor     ecx, ecx; lpSystemName
0x1800db687  call    cs:__imp_LookupPrivilegeValueW
0x1800db68d  test    eax, eax
0x1800db68f  jz      short loc_1800DB6C6
0x1800db691  mov     [rbp+NewState.PrivilegeCount], 1
0x1800db698  mov     rax, qword ptr [rbp+Luid.LowPart]
0x1800db69c  mov     qword ptr [rbp+NewState.Privileges.Luid.LowPart], rax
0x1800db6a0  mov     [rbp+NewState.Privileges.Attributes], 2
0x1800db6a7  mov     [rsp+60h+ReturnLength], rdi; ReturnLength
0x1800db6ac  mov     [rsp+60h+PreviousState], rdi; PreviousState
0x1800db6b1  xor     r9d, r9d; BufferLength
0x1800db6b4  lea     r8, [rbp+NewState]; NewState
0x1800db6b8  xor     edx, edx; DisableAllPrivileges
0x1800db6ba  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800db6be  call    cs:__imp_AdjustTokenPrivileges
0x1800db6c4  mov     edi, eax
0x1800db6c6  cmp     edi, 1
0x1800db6c9  setz    bl
0x1800db6cc  lea     rcx, [rbp+TokenHandle]
0x1800db6d0  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800db6d5  nop
0x1800db6d6  mov     al, bl
0x1800db6d8  mov     rcx, [rbp+var_10]
0x1800db6dc  xor     rcx, rsp; StackCookie
0x1800db6df  call    __security_check_cookie
0x1800db6e4  mov     rbx, [rsp+60h+arg_0]
0x1800db6e9  mov     rdi, [rsp+60h+arg_8]
0x1800db6ee  add     rsp, 60h
0x1800db6f2  pop     rbp
0x1800db6f3  retn
```
