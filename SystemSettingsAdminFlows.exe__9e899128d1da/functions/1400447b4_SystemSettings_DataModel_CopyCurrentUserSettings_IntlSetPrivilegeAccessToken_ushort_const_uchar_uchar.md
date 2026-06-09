# SystemSettings::DataModel::CopyCurrentUserSettings::IntlSetPrivilegeAccessToken(ushort const *,uchar,uchar *)

- ea: `0x1400447b4`
- end: `0x1400448be`
- name: `?IntlSetPrivilegeAccessToken@CopyCurrentUserSettings@DataModel@SystemSettings@@CAKPEBGEPEAE@Z`
- size: `266`
- prototype: `unsigned int __fastcall(const unsigned __int16 *, unsigned __int8, unsigned __int8 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140044000`
- `0x140044b1c`

## callees

- `0x140005f30`
- `0x14000ec98`
- `0x140030704`
- `0x1400447b4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x140044814`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x140044814`
- `KERNEL32!GetLastError` at `0x140044835`
- `KERNEL32!GetLastError` at `0x140044835`
- `KERNEL32!GetCurrentProcess` at `0x140044802`
- `KERNEL32!GetCurrentProcess` at `0x140044802`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x14004487a`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x14004487a`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x14004482b`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x14004482b`

## string_xrefs

- `0x140044824`: `SeRestorePrivilege`

## pseudocode

```c
__int64 __fastcall SystemSettings::DataModel::CopyCurrentUserSettings::IntlSetPrivilegeAccessToken(
        const unsigned __int16 *a1,
        char a2,
        unsigned __int8 *a3)
{
  HANDLE CurrentProcess; // rax
  DWORD LastError; // ebx
  unsigned __int8 v7; // bl
  DWORD BufferLength; // [rsp+30h] [rbp-19h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-11h] BYREF
  struct _LUID Luid; // [rsp+40h] [rbp-9h] BYREF
  struct _TOKEN_PRIVILEGES NewState; // [rsp+48h] [rbp-1h] BYREF
  struct _TOKEN_PRIVILEGES PreviousState; // [rsp+58h] [rbp+Fh] BYREF

  TokenHandle = 0;
  Luid = 0;
  BufferLength = 28;
  NewState = 0;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &TokenHandle,
    0);
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0x28u, &TokenHandle)
    && LookupPrivilegeValueW(0, L"SeRestorePrivilege", &Luid)
    && (v7 = 1,
        NewState.Privileges[0].Luid = Luid,
        NewState.PrivilegeCount = 1,
        NewState.Privileges[0].Attributes = a2 != 0 ? 2 : 0,
        AdjustTokenPrivileges(TokenHandle, 0, &NewState, BufferLength, &PreviousState, &BufferLength)) )
  {
    if ( a3 )
    {
      if ( !PreviousState.PrivilegeCount || (PreviousState.Privileges[0].Attributes & 2) == 0 )
        v7 = 0;
      *a3 = v7;
    }
    LastError = 0;
  }
  else
  {
    LastError = GetLastError();
  }
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  return LastError;
}

```

## disassembly

```asm
0x1400447b4  push    rbp
0x1400447b6  push    rbx
0x1400447b7  push    rsi
0x1400447b8  push    rdi
0x1400447b9  lea     rbp, [rsp-3Fh]
0x1400447be  sub     rsp, 88h
0x1400447c5  mov     rax, cs:__security_cookie
0x1400447cc  xor     rax, rsp
0x1400447cf  mov     [rbp+57h+var_28], rax
0x1400447d3  mov     sil, dl
0x1400447d6  mov     [rbp+57h+TokenHandle], 0
0x1400447de  xorps   xmm0, xmm0
0x1400447e1  mov     qword ptr [rbp+57h+Luid.LowPart], 0
0x1400447e9  xor     edx, edx
0x1400447eb  mov     [rbp+57h+BufferLength], 1Ch
0x1400447f2  lea     rcx, [rbp+57h+TokenHandle]
0x1400447f6  mov     rdi, r8
0x1400447f9  movups  xmmword ptr [rbp+57h+NewState.PrivilegeCount], xmm0
0x1400447fd  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x140044802  call    cs:__imp_GetCurrentProcess
0x140044808  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x14004480c  mov     edx, 28h ; '('; DesiredAccess
0x140044811  mov     rcx, rax; ProcessHandle
0x140044814  call    cs:__imp_OpenProcessToken
0x14004481a  test    eax, eax
0x14004481c  jz      short loc_140044835
0x14004481e  lea     r8, [rbp+57h+Luid]; lpLuid
0x140044822  xor     ecx, ecx; lpSystemName
0x140044824  lea     rdx, aSerestoreprivi; "SeRestorePrivilege"
0x14004482b  call    cs:__imp_LookupPrivilegeValueW
0x140044831  test    eax, eax
0x140044833  jnz     short loc_14004483F
0x140044835  call    cs:__imp_GetLastError
0x14004483b  mov     ebx, eax
0x14004483d  jmp     short loc_14004489B
0x14004483f  mov     rax, qword ptr [rbp+57h+Luid.LowPart]
0x140044843  lea     r8, [rbp+57h+NewState]; NewState
0x140044847  mov     r9d, [rbp+57h+BufferLength]; BufferLength
0x14004484b  neg     sil
0x14004484e  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x140044852  mov     ebx, 1
0x140044857  mov     qword ptr [rbp+57h+NewState.Privileges.Luid.LowPart], rax
0x14004485b  sbb     eax, eax
0x14004485d  and     eax, 2
0x140044860  mov     [rbp+57h+NewState.PrivilegeCount], ebx
0x140044863  mov     [rbp+57h+NewState.Privileges.Attributes], eax
0x140044866  xor     edx, edx; DisableAllPrivileges
0x140044868  lea     rax, [rbp+57h+BufferLength]
0x14004486c  mov     [rsp+0A0h+ReturnLength], rax; ReturnLength
0x140044871  lea     rax, [rbp+57h+var_48]
0x140044875  mov     [rsp+0A0h+PreviousState], rax; PreviousState
0x14004487a  call    cs:__imp_AdjustTokenPrivileges
0x140044880  test    eax, eax
0x140044882  jz      short loc_140044835
0x140044884  test    rdi, rdi
0x140044887  jz      short loc_140044899
0x140044889  cmp     [rbp+57h+var_48.PrivilegeCount], 0
0x14004488d  jbe     short loc_140044895
0x14004488f  test    byte ptr [rbp+57h+var_48.Privileges.Attributes], 2
0x140044893  jnz     short loc_140044897
0x140044895  xor     bl, bl
0x140044897  mov     [rdi], bl
0x140044899  xor     ebx, ebx
0x14004489b  lea     rcx, [rbp+57h+TokenHandle]
0x14004489f  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1400448a4  mov     eax, ebx
0x1400448a6  mov     rcx, [rbp+57h+var_28]
0x1400448aa  xor     rcx, rsp; StackCookie
0x1400448ad  call    __security_check_cookie
0x1400448b2  add     rsp, 88h
0x1400448b9  pop     rdi
0x1400448ba  pop     rsi
0x1400448bb  pop     rbx
0x1400448bc  pop     rbp
0x1400448bd  retn
```
