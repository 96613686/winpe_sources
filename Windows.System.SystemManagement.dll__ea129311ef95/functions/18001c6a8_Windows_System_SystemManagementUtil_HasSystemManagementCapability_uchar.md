# Windows::System::SystemManagementUtil::HasSystemManagementCapability(uchar *)

- ea: `0x18001c6a8`
- end: `0x18001c7b2`
- name: `?HasSystemManagementCapability@SystemManagementUtil@System@Windows@@SAJPEAE@Z`
- size: `266`
- prototype: `__int64 __fastcall(unsigned __int8 *)`
- caller_count: `9`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000d670`
- `0x18000d810`
- `0x18000db70`
- `0x180010bb0`
- `0x180014750`
- `0x180014ce0`
- `0x180017760`
- `0x180018020`
- `0x180022cd0`

## callees

- `0x180003be4`
- `0x18001c6a8`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18001c780`
- `ntdll!RtlNtStatusToDosError` at `0x18001c780`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c73a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c73a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001c730`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001c730`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001c719`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001c719`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c79f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c79f`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18001c74f`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18001c74f`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18001c70d`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18001c70d`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x18001c774`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x18001c774`
- `ext-ms-win-shell-embeddedmode-l1-1-0!IsEmbeddedModeAllowed` at `0x18001c6f0`
- `ext-ms-win-shell-embeddedmode-l1-1-0!IsEmbeddedModeAllowed` at `0x18001c6f0`

## pseudocode

```c
__int64 __fastcall Windows::System::SystemManagementUtil::HasSystemManagementCapability(unsigned __int8 *a1)
{
  int v2; // ebx
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  NTSTATUS v5; // eax
  signed int v6; // eax
  int v8; // [rsp+30h] [rbp+8h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp+10h] BYREF

  TokenHandle = 0;
  v8 = 0;
  if ( !a1 )
    return (unsigned int)-2147024809;
  *a1 = 0;
  if ( !(unsigned __int8)IsIsEmbeddedModeAllowedPresent() )
  {
    v2 = -2147467263;
    goto LABEL_19;
  }
  v2 = IsEmbeddedModeAllowed(&v8);
  if ( v2 >= 0 )
  {
    if ( !v8 )
    {
      v2 = -2147024891;
      goto LABEL_19;
    }
    v2 = CoImpersonateClient();
    if ( v2 >= 0 )
    {
      CurrentThread = GetCurrentThread();
      if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
      {
        LastError = GetLastError();
        v2 = LastError;
        if ( LastError > 0 )
          v2 = (unsigned __int16)LastError | 0x80070000;
      }
      CoRevertToSelf();
      if ( v2 < 0 )
        goto LABEL_19;
      goto LABEL_16;
    }
  }
  if ( v2 == -2147417833 )
  {
    v2 = 0;
LABEL_16:
    v5 = CapabilityCheck(TokenHandle, L"systemManagement", a1);
    if ( v5 < 0 )
    {
      v6 = RtlNtStatusToDosError(v5);
      v2 = v6;
      if ( v6 > 0 )
        v2 = (unsigned __int16)v6 | 0x80070000;
    }
  }
LABEL_19:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18001c6a8  mov     [rsp+arg_10], rbx
0x18001c6ad  push    rdi
0x18001c6ae  sub     rsp, 20h
0x18001c6b2  mov     [rsp+28h+TokenHandle], 0
0x18001c6bb  mov     rdi, rcx
0x18001c6be  mov     [rsp+28h+arg_0], 0
0x18001c6c6  test    rcx, rcx
0x18001c6c9  jnz     short loc_18001C6D5
0x18001c6cb  mov     ebx, 80070057h
0x18001c6d0  jmp     loc_18001C7A5
0x18001c6d5  mov     byte ptr [rcx], 0
0x18001c6d8  call    IsIsEmbeddedModeAllowedPresent
0x18001c6dd  test    al, al
0x18001c6df  jnz     short loc_18001C6EB
0x18001c6e1  mov     ebx, 80004001h
0x18001c6e6  jmp     loc_18001C795
0x18001c6eb  lea     rcx, [rsp+28h+arg_0]
0x18001c6f0  call    cs:__imp_IsEmbeddedModeAllowed
0x18001c6f6  mov     ebx, eax
0x18001c6f8  test    eax, eax
0x18001c6fa  js      short loc_18001C75B
0x18001c6fc  cmp     [rsp+28h+arg_0], 0
0x18001c701  jnz     short loc_18001C70D
0x18001c703  mov     ebx, 80070005h
0x18001c708  jmp     loc_18001C795
0x18001c70d  call    cs:__imp_CoImpersonateClient
0x18001c713  mov     ebx, eax
0x18001c715  test    eax, eax
0x18001c717  js      short loc_18001C75B
0x18001c719  call    cs:__imp_GetCurrentThread
0x18001c71f  mov     edx, 8; DesiredAccess
0x18001c724  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x18001c729  mov     rcx, rax; ThreadHandle
0x18001c72c  lea     r8d, [rdx-7]; OpenAsSelf
0x18001c730  call    cs:__imp_OpenThreadToken
0x18001c736  test    eax, eax
0x18001c738  jnz     short loc_18001C74F
0x18001c73a  call    cs:__imp_GetLastError
0x18001c740  mov     ebx, eax
0x18001c742  test    eax, eax
0x18001c744  jle     short loc_18001C74F
0x18001c746  movzx   ebx, ax
0x18001c749  or      ebx, 80070000h
0x18001c74f  call    cs:__imp_CoRevertToSelf
0x18001c755  test    ebx, ebx
0x18001c757  js      short loc_18001C795
0x18001c759  jmp     short loc_18001C765
0x18001c75b  cmp     ebx, 80010117h
0x18001c761  jnz     short loc_18001C795
0x18001c763  xor     ebx, ebx
0x18001c765  mov     rcx, [rsp+28h+TokenHandle]
0x18001c76a  lea     rdx, aSystemmanageme; "systemManagement"
0x18001c771  mov     r8, rdi
0x18001c774  call    cs:__imp_CapabilityCheck
0x18001c77a  test    eax, eax
0x18001c77c  jns     short loc_18001C795
0x18001c77e  mov     ecx, eax; Status
0x18001c780  call    cs:__imp_RtlNtStatusToDosError
0x18001c786  mov     ebx, eax
0x18001c788  test    eax, eax
0x18001c78a  jle     short loc_18001C795
0x18001c78c  movzx   ebx, ax
0x18001c78f  or      ebx, 80070000h
0x18001c795  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x18001c79a  test    rcx, rcx
0x18001c79d  jz      short loc_18001C7A5
0x18001c79f  call    cs:__imp_CloseHandle
0x18001c7a5  mov     eax, ebx
0x18001c7a7  mov     rbx, [rsp+28h+arg_10]
0x18001c7ac  add     rsp, 20h
0x18001c7b0  pop     rdi
0x18001c7b1  retn
```
