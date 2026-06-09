# AipValidateClientService(void *,ulong)

- ea: `0x18001a730`
- end: `0x18001a8db`
- name: `?AipValidateClientService@@YAKPEAXK@Z`
- size: `427`
- prototype: `unsigned int __fastcall(void *, unsigned int)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18003c480`
- `0x18003c4a0`
- `0x18003c4b0`

## callees

- `0x18000a230`
- `0x18001a730`
- `0x180042950`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18001a843`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18001a843`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a853`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a853`
- `ntdll!NtClose` at `0x18001a879`
- `ntdll!NtClose` at `0x18001a892`
- `ntdll!NtClose` at `0x18001a8ac`
- `ntdll!NtClose` at `0x18001a879`
- `ntdll!NtClose` at `0x18001a892`
- `ntdll!NtClose` at `0x18001a8ac`
- `ntdll!NtDuplicateToken` at `0x18001a81c`
- `ntdll!NtDuplicateToken` at `0x18001a81c`
- `ntdll!NtOpenProcessToken` at `0x18001a7a9`
- `ntdll!NtOpenProcessToken` at `0x18001a7a9`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18001a7bb`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18001a7bb`

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
  ClientInformation = AiGetClientInformation(a1, &ProcessHandle, 0, 0, 0);
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
    if ( !CheckTokenMembership(Handle, (char *)&g_pServiceInfo + 72 * v2, &IsMember) )
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
0x18001a730  mov     [rsp-8+arg_10], rbx
0x18001a735  push    rbp
0x18001a736  push    rsi
0x18001a737  push    r14
0x18001a739  lea     rbp, [rsp-47h]
0x18001a73e  sub     rsp, 0A0h
0x18001a745  mov     rax, cs:__security_cookie
0x18001a74c  xor     rax, rsp
0x18001a74f  mov     [rbp+57h+var_20], rax
0x18001a753  xor     r14d, r14d
0x18001a756  mov     esi, edx
0x18001a758  xorps   xmm0, xmm0
0x18001a75b  mov     [rbp+57h+ProcessHandle], r14
0x18001a75f  xor     eax, eax
0x18001a761  mov     [rbp+57h+TokenHandle], r14
0x18001a765  lea     rdx, [rbp+57h+ProcessHandle]; void **
0x18001a769  mov     [rbp+57h+Handle], r14
0x18001a76d  xor     r9d, r9d; unsigned int *
0x18001a770  mov     [rbp+57h+IsMember], r14d
0x18001a774  xor     r8d, r8d; void **
0x18001a777  mov     [rbp+57h+var_30], rax
0x18001a77b  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18001a77f  mov     [rbp+57h+var_28], eax
0x18001a782  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18001a786  mov     qword ptr [rsp+0B0h+TokenType], r14; unsigned int *
0x18001a78b  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18001a78f  call    ?AiGetClientInformation@@YAKPEAXPEAPEAX1PEAK2@Z; AiGetClientInformation(void *,void * *,void * *,ulong *,ulong *)
0x18001a794  mov     ebx, eax
0x18001a796  test    eax, eax
0x18001a798  jnz     loc_18001A870
0x18001a79e  mov     rcx, [rbp+57h+ProcessHandle]; ProcessHandle
0x18001a7a2  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x18001a7a6  lea     edx, [rax+0Ah]; DesiredAccess
0x18001a7a9  call    cs:__imp_NtOpenProcessToken
0x18001a7b0  nop     dword ptr [rax+rax+00h]
0x18001a7b5  test    eax, eax
0x18001a7b7  jns     short loc_18001A7CE
0x18001a7b9  mov     ecx, eax; Status
0x18001a7bb  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x18001a7c2  nop     dword ptr [rax+rax+00h]
0x18001a7c7  mov     ebx, eax
0x18001a7c9  jmp     loc_18001A870
0x18001a7ce  mov     ecx, 2
0x18001a7d3  mov     dword ptr [rbp+57h+var_30], 0Ch
0x18001a7da  lea     rax, [rbp+57h+var_30]
0x18001a7de  mov     dword ptr [rbp+57h+var_30+4], ecx
0x18001a7e1  mov     [rbp+57h+ObjectAttributes.SecurityQualityOfService], rax
0x18001a7e5  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18001a7e9  lea     rax, [rbp+57h+Handle]
0x18001a7ed  mov     word ptr [rbp+57h+var_28], 1
0x18001a7f3  mov     [rsp+0B0h+NewTokenHandle], rax; NewTokenHandle
0x18001a7f8  xor     r9d, r9d; EffectiveOnly
0x18001a7fb  mov     [rsp+0B0h+TokenType], ecx; TokenType
0x18001a7ff  xor     edx, edx; DesiredAccess
0x18001a801  mov     rcx, [rbp+57h+TokenHandle]; ExistingTokenHandle
0x18001a805  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18001a80c  mov     [rbp+57h+ObjectAttributes.RootDirectory], r14
0x18001a810  mov     [rbp+57h+ObjectAttributes.Attributes], r14d
0x18001a814  mov     [rbp+57h+ObjectAttributes.ObjectName], r14
0x18001a818  mov     [rbp+57h+ObjectAttributes.SecurityDescriptor], r14
0x18001a81c  call    cs:__imp_NtDuplicateToken
0x18001a823  nop     dword ptr [rax+rax+00h]
0x18001a828  test    eax, eax
0x18001a82a  js      short loc_18001A7B9
0x18001a82c  lea     rcx, [rsi+rsi*8]
0x18001a830  lea     rax, ?g_pServiceInfo@@3PAU_SERVICE_INFO@@A; _SERVICE_INFO near * g_pServiceInfo
0x18001a837  lea     rdx, [rax+rcx*8]; SidToCheck
0x18001a83b  mov     rcx, [rbp+57h+Handle]; TokenHandle
0x18001a83f  lea     r8, [rbp+57h+IsMember]; IsMember
0x18001a843  call    cs:__imp_CheckTokenMembership
0x18001a84a  nop     dword ptr [rax+rax+00h]
0x18001a84f  test    eax, eax
0x18001a851  jnz     short loc_18001A864
0x18001a853  call    cs:__imp_GetLastError
0x18001a85a  nop     dword ptr [rax+rax+00h]
0x18001a85f  jmp     loc_18001A7C7
0x18001a864  cmp     [rbp+57h+IsMember], r14d
0x18001a868  mov     eax, 5
0x18001a86d  cmovz   ebx, eax
0x18001a870  mov     rcx, [rbp+57h+Handle]; Handle
0x18001a874  test    rcx, rcx
0x18001a877  jz      short loc_18001A889
0x18001a879  call    cs:__imp_NtClose
0x18001a880  nop     dword ptr [rax+rax+00h]
0x18001a885  mov     [rbp+57h+Handle], r14
0x18001a889  mov     rcx, [rbp+57h+TokenHandle]; Handle
0x18001a88d  test    rcx, rcx
0x18001a890  jz      short loc_18001A8A2
0x18001a892  call    cs:__imp_NtClose
0x18001a899  nop     dword ptr [rax+rax+00h]
0x18001a89e  mov     [rbp+57h+TokenHandle], r14
0x18001a8a2  cmp     [rbp+57h+ProcessHandle], r14
0x18001a8a6  jz      short loc_18001A8B8
0x18001a8a8  mov     rcx, [rbp+57h+ProcessHandle]; Handle
0x18001a8ac  call    cs:__imp_NtClose
0x18001a8b3  nop     dword ptr [rax+rax+00h]
0x18001a8b8  mov     eax, ebx
0x18001a8ba  mov     rcx, [rbp+57h+var_20]
0x18001a8be  xor     rcx, rsp; StackCookie
0x18001a8c1  call    __security_check_cookie
0x18001a8c6  mov     rbx, [rsp+0B0h+arg_10]
0x18001a8ce  add     rsp, 0A0h
0x18001a8d5  pop     r14
0x18001a8d7  pop     rsi
0x18001a8d8  pop     rbp
0x18001a8d9  retn
```
