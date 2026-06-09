# AipValidateClientService(void *,ulong)

- ea: `0x18001cb90`
- end: `0x18001cd0a`
- name: `?AipValidateClientService@@YAKPEAXK@Z`
- size: `378`
- prototype: `__int64 __fastcall(void *, unsigned int)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180040d20`
- `0x180040d40`
- `0x180040d50`

## callees

- `0x180009d50`
- `0x18001cb90`
- `0x180046e50`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cc9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cc9b`
- `ntdll!NtClose` at `0x18001ccbb`
- `ntdll!NtClose` at `0x18001ccce`
- `ntdll!NtClose` at `0x18001cce2`
- `ntdll!NtClose` at `0x18001ccbb`
- `ntdll!NtClose` at `0x18001ccce`
- `ntdll!NtClose` at `0x18001cce2`
- `ntdll!NtDuplicateToken` at `0x18001cc70`
- `ntdll!NtDuplicateToken` at `0x18001cc70`
- `ntdll!NtOpenProcessToken` at `0x18001cc09`
- `ntdll!NtOpenProcessToken` at `0x18001cc09`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18001cc15`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18001cc15`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18001cc91`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18001cc91`

## pseudocode

```c
__int64 __fastcall AipValidateClientService(void *a1, unsigned int a2)
{
  __int64 v2; // rsi
  unsigned int ClientInformation; // ebx
  int v4; // eax
  ULONG LastError; // eax
  WINBOOL IsMember; // [rsp+30h] [rbp-29h] BYREF
  HANDLE Handle; // [rsp+38h] [rbp-21h] BYREF
  void *TokenHandle; // [rsp+40h] [rbp-19h] BYREF
  HANDLE ProcessHandle; // [rsp+48h] [rbp-11h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-9h] BYREF
  __int64 v12; // [rsp+80h] [rbp+27h] BYREF
  int v13; // [rsp+88h] [rbp+2Fh]

  v2 = a2;
  ProcessHandle = 0;
  TokenHandle = 0;
  Handle = 0;
  IsMember = 0;
  v12 = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v13 = 0;
  ClientInformation = AiGetClientInformation(a1, &ProcessHandle, 0, 0, 0);// RPC auth audit: validates actual local client PID/process token and service SID membership; does not trust caller-supplied identity fields.
  if ( !ClientInformation )
  {
    v4 = NtOpenProcessToken(ProcessHandle, 0xAu, &TokenHandle);
    if ( v4 < 0
      || (v12 = 0x20000000CLL,
          ObjectAttributes.SecurityQualityOfService = &v12,
          LOWORD(v13) = 1,
          ObjectAttributes.Length = 48,
          memset(&ObjectAttributes.RootDirectory, 0, 20),
          ObjectAttributes.SecurityDescriptor = 0,
          v4 = NtDuplicateToken(TokenHandle, 0, &ObjectAttributes, 0, TokenImpersonation, &Handle),
          v4 < 0) )
    {
      LastError = RtlNtStatusToDosErrorNoTeb(v4);
LABEL_4:
      ClientInformation = LastError;
      goto LABEL_10;
    }
    if ( !CheckTokenMembership(Handle, &g_pServiceInfo + 9 * v2, &IsMember) )
    {
      LastError = GetLastError();
      goto LABEL_4;
    }
    if ( !IsMember )
      ClientInformation = 5;
  }
LABEL_10:
  if ( Handle )
  {
    NtClose(Handle);
    Handle = 0;
  }
  if ( TokenHandle )
  {
    NtClose(TokenHandle);
    TokenHandle = 0;
  }
  if ( ProcessHandle )
    NtClose(ProcessHandle);
  return ClientInformation;
}

```

## disassembly

```asm
0x18001cb90  mov     [rsp-8+arg_10], rbx
0x18001cb95  push    rbp
0x18001cb96  push    rsi
0x18001cb97  push    r14
0x18001cb99  lea     rbp, [rsp-47h]
0x18001cb9e  sub     rsp, 0A0h
0x18001cba5  mov     rax, cs:__security_cookie
0x18001cbac  xor     rax, rsp
0x18001cbaf  mov     [rbp+57h+var_20], rax
0x18001cbb3  xor     r14d, r14d
0x18001cbb6  mov     esi, edx
0x18001cbb8  xorps   xmm0, xmm0
0x18001cbbb  mov     [rbp+57h+ProcessHandle], r14
0x18001cbbf  xor     eax, eax
0x18001cbc1  mov     [rbp+57h+TokenHandle], r14
0x18001cbc5  lea     rdx, [rbp+57h+ProcessHandle]; void **
0x18001cbc9  mov     [rbp+57h+Handle], r14
0x18001cbcd  xor     r9d, r9d; unsigned int *
0x18001cbd0  mov     [rbp+57h+IsMember], r14d
0x18001cbd4  xor     r8d, r8d; void **
0x18001cbd7  mov     [rbp+57h+var_30], rax
0x18001cbdb  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18001cbdf  mov     [rbp+57h+var_28], eax
0x18001cbe2  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18001cbe6  mov     qword ptr [rsp+0B0h+TokenType], r14; unsigned int *
0x18001cbeb  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18001cbef  call    ?AiGetClientInformation@@YAKPEAXPEAPEAX1PEAK2@Z; AiGetClientInformation(void *,void * *,void * *,ulong *,ulong *)
0x18001cbf4  mov     ebx, eax; RPC auth audit: validates actual local client PID/process token and service SID membership; does not trust caller-supplied identity fields.
0x18001cbf6  test    eax, eax
0x18001cbf8  jnz     loc_18001CCB2
0x18001cbfe  mov     rcx, [rbp+57h+ProcessHandle]; ProcessHandle
0x18001cc02  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x18001cc06  lea     edx, [rax+0Ah]; DesiredAccess
0x18001cc09  call    cs:__imp_NtOpenProcessToken
0x18001cc0f  test    eax, eax
0x18001cc11  jns     short loc_18001CC22
0x18001cc13  mov     ecx, eax; Status
0x18001cc15  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x18001cc1b  mov     ebx, eax
0x18001cc1d  jmp     loc_18001CCB2
0x18001cc22  mov     ecx, 2
0x18001cc27  mov     dword ptr [rbp+57h+var_30], 0Ch
0x18001cc2e  lea     rax, [rbp+57h+var_30]
0x18001cc32  mov     dword ptr [rbp+57h+var_30+4], ecx
0x18001cc35  mov     [rbp+57h+ObjectAttributes.SecurityQualityOfService], rax
0x18001cc39  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18001cc3d  lea     rax, [rbp+57h+Handle]
0x18001cc41  mov     word ptr [rbp+57h+var_28], 1
0x18001cc47  mov     [rsp+0B0h+NewTokenHandle], rax; NewTokenHandle
0x18001cc4c  xor     r9d, r9d; EffectiveOnly
0x18001cc4f  mov     [rsp+0B0h+TokenType], ecx; TokenType
0x18001cc53  xor     edx, edx; DesiredAccess
0x18001cc55  mov     rcx, [rbp+57h+TokenHandle]; ExistingTokenHandle
0x18001cc59  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18001cc60  mov     [rbp+57h+ObjectAttributes.RootDirectory], r14
0x18001cc64  mov     [rbp+57h+ObjectAttributes.Attributes], r14d
0x18001cc68  mov     [rbp+57h+ObjectAttributes.ObjectName], r14
0x18001cc6c  mov     [rbp+57h+ObjectAttributes.SecurityDescriptor], r14
0x18001cc70  call    cs:__imp_NtDuplicateToken
0x18001cc76  test    eax, eax
0x18001cc78  js      short loc_18001CC13
0x18001cc7a  lea     rcx, [rsi+rsi*8]
0x18001cc7e  lea     rax, ?g_pServiceInfo@@3PAU_SERVICE_INFO@@A; _SERVICE_INFO near * g_pServiceInfo
0x18001cc85  lea     rdx, [rax+rcx*8]; SidToCheck
0x18001cc89  mov     rcx, [rbp+57h+Handle]; TokenHandle
0x18001cc8d  lea     r8, [rbp+57h+IsMember]; IsMember
0x18001cc91  call    cs:__imp_CheckTokenMembership
0x18001cc97  test    eax, eax
0x18001cc99  jnz     short loc_18001CCA6
0x18001cc9b  call    cs:__imp_GetLastError
0x18001cca1  jmp     loc_18001CC1B
0x18001cca6  cmp     [rbp+57h+IsMember], r14d
0x18001ccaa  mov     eax, 5
0x18001ccaf  cmovz   ebx, eax
0x18001ccb2  mov     rcx, [rbp+57h+Handle]; Handle
0x18001ccb6  test    rcx, rcx
0x18001ccb9  jz      short loc_18001CCC5
0x18001ccbb  call    cs:__imp_NtClose
0x18001ccc1  mov     [rbp+57h+Handle], r14
0x18001ccc5  mov     rcx, [rbp+57h+TokenHandle]; Handle
0x18001ccc9  test    rcx, rcx
0x18001cccc  jz      short loc_18001CCD8
0x18001ccce  call    cs:__imp_NtClose
0x18001ccd4  mov     [rbp+57h+TokenHandle], r14
0x18001ccd8  cmp     [rbp+57h+ProcessHandle], r14
0x18001ccdc  jz      short loc_18001CCE8
0x18001ccde  mov     rcx, [rbp+57h+ProcessHandle]; Handle
0x18001cce2  call    cs:__imp_NtClose
0x18001cce8  mov     eax, ebx
0x18001ccea  mov     rcx, [rbp+57h+var_20]
0x18001ccee  xor     rcx, rsp; StackCookie
0x18001ccf1  call    __security_check_cookie
0x18001ccf6  mov     rbx, [rsp+0B0h+arg_10]
0x18001ccfe  add     rsp, 0A0h
0x18001cd05  pop     r14
0x18001cd07  pop     rsi
0x18001cd08  pop     rbp
0x18001cd09  retn
```
