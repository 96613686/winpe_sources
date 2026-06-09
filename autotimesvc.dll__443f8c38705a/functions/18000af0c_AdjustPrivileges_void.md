# AdjustPrivileges(void)

- ea: `0x18000af0c`
- end: `0x18000b046`
- name: `?AdjustPrivileges@@YAJXZ`
- size: `314`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000b264`

## callees

- `0x180001218`
- `0x1800012f0`
- `0x180002a70`
- `0x18000aea0`
- `0x18000af0c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000af4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000afc6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000af4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000afc6`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000af41`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000af41`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000af2f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000af2f`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18000afbc`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18000afbc`

## pseudocode

```c
__int64 AdjustPrivileges(void)
{
  HANDLE CurrentProcess; // rax
  signed int LastError; // ebx
  char *v2; // rdx
  void *TokenHandle; // [rsp+38h] [rbp-28h] BYREF
  struct _TOKEN_PRIVILEGES NewState; // [rsp+40h] [rbp-20h] BYREF

  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0x28u, &TokenHandle) )
  {
    NewState.PrivilegeCount = 1;
    NewState.Privileges[0].Luid = (LUID)12LL;
    NewState.Privileges[0].Attributes = 2;
    if ( AdjustTokenPrivileges(TokenHandle, 0, &NewState, 0x10u, 0, 0) )
    {
      LastError = 0;
      goto LABEL_13;
    }
    LastError = GetLastError();
    if ( (unsigned int)dword_18001C010 > 2 && (unsigned __int8)tlgKeywordOn(&dword_18001C010, 1) )
    {
      v2 = byte_1800169F3;
      goto LABEL_9;
    }
  }
  else
  {
    LastError = GetLastError();
    if ( (unsigned int)dword_18001C010 > 2 && (unsigned __int8)tlgKeywordOn(&dword_18001C010, 1) )
    {
      v2 = &byte_1800168F7;
LABEL_9:
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (__int64)&dword_18001C010,
        (__int64)v2,
        0,
        0);
    }
  }
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
LABEL_13:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18000af0c  mov     [rsp-8+arg_0], rbx
0x18000af11  push    rbp
0x18000af12  mov     rbp, rsp
0x18000af15  sub     rsp, 60h
0x18000af19  mov     rax, cs:__security_cookie
0x18000af20  xor     rax, rsp
0x18000af23  mov     [rbp+var_10], rax
0x18000af27  mov     [rbp+TokenHandle], 0
0x18000af2f  call    cs:__imp_GetCurrentProcess
0x18000af35  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18000af39  mov     edx, 28h ; '('; DesiredAccess
0x18000af3e  mov     rcx, rax; ProcessHandle
0x18000af41  call    cs:__imp_OpenProcessToken
0x18000af47  test    eax, eax
0x18000af49  jnz     short loc_18000AF84
0x18000af4b  call    cs:__imp_GetLastError
0x18000af51  mov     ecx, cs:dword_18001C010
0x18000af57  mov     ebx, eax
0x18000af59  cmp     ecx, 2
0x18000af5c  jbe     loc_18000B013
0x18000af62  mov     edx, 1
0x18000af67  lea     rcx, dword_18001C010
0x18000af6e  call    _tlgKeywordOn
0x18000af73  test    al, al
0x18000af75  jz      loc_18000B013
0x18000af7b  lea     rdx, byte_1800168F7
0x18000af82  jmp     short loc_18000AFF5
0x18000af84  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18000af88  lea     r8, [rbp+NewState]; NewState
0x18000af8c  mov     [rsp+60h+ReturnLength], 0; ReturnLength
0x18000af95  mov     r9d, 10h; BufferLength
0x18000af9b  xor     edx, edx; DisableAllPrivileges
0x18000af9d  mov     [rsp+60h+PreviousState], 0; PreviousState
0x18000afa6  mov     [rbp+NewState.PrivilegeCount], 1
0x18000afad  mov     qword ptr [rbp+NewState.Privileges.Luid.LowPart], 0Ch
0x18000afb5  mov     [rbp+NewState.Privileges.Attributes], 2
0x18000afbc  call    cs:__imp_AdjustTokenPrivileges
0x18000afc2  test    eax, eax
0x18000afc4  jnz     short loc_18000B022
0x18000afc6  call    cs:__imp_GetLastError
0x18000afcc  mov     ecx, cs:dword_18001C010
0x18000afd2  mov     ebx, eax
0x18000afd4  cmp     ecx, 2
0x18000afd7  jbe     short loc_18000B013
0x18000afd9  mov     edx, 1
0x18000afde  lea     rcx, dword_18001C010
0x18000afe5  call    _tlgKeywordOn
0x18000afea  test    al, al
0x18000afec  jz      short loc_18000B013
0x18000afee  lea     rdx, byte_1800169F3
0x18000aff5  xor     r9d, r9d
0x18000aff8  lea     rax, [rbp+var_30]
0x18000affc  xor     r8d, r8d
0x18000afff  mov     [rsp+60h+PreviousState], rax
0x18000b004  lea     rcx, dword_18001C010
0x18000b00b  mov     [rbp+var_30], ebx
0x18000b00e  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18000b013  test    ebx, ebx
0x18000b015  jle     short loc_18000B024
0x18000b017  movzx   ebx, bx
0x18000b01a  or      ebx, 80070000h
0x18000b020  jmp     short loc_18000B024
0x18000b022  xor     ebx, ebx
0x18000b024  lea     rcx, [rbp+TokenHandle]
0x18000b028  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18000b02d  mov     eax, ebx
0x18000b02f  mov     rcx, [rbp+var_10]
0x18000b033  xor     rcx, rsp; StackCookie
0x18000b036  call    __security_check_cookie
0x18000b03b  mov     rbx, [rsp+60h+arg_0]
0x18000b040  add     rsp, 60h
0x18000b044  pop     rbp
0x18000b045  retn
```
