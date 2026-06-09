# AipValidateClientService(void *,ulong)

- ea: `0x18001ab00`
- end: `0x18001acab`
- name: `?AipValidateClientService@@YAKPEAXK@Z`
- size: `427`
- prototype: `unsigned int __fastcall(void *, unsigned int)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18003e050`
- `0x18003e070`
- `0x18003e080`

## callees

- `0x18000a230`
- `0x18001ab00`
- `0x1800444e0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18001ac13`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18001ac13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ac23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ac23`
- `ntdll!NtClose` at `0x18001ac49`
- `ntdll!NtClose` at `0x18001ac62`
- `ntdll!NtClose` at `0x18001ac7c`
- `ntdll!NtClose` at `0x18001ac49`
- `ntdll!NtClose` at `0x18001ac62`
- `ntdll!NtClose` at `0x18001ac7c`
- `ntdll!NtDuplicateToken` at `0x18001abec`
- `ntdll!NtDuplicateToken` at `0x18001abec`
- `ntdll!NtOpenProcessToken` at `0x18001ab79`
- `ntdll!NtOpenProcessToken` at `0x18001ab79`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18001ab8b`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18001ab8b`

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
0x18001ab00  mov     [rsp-8+arg_10], rbx
0x18001ab05  push    rbp
0x18001ab06  push    rsi
0x18001ab07  push    r14
0x18001ab09  lea     rbp, [rsp-47h]
0x18001ab0e  sub     rsp, 0A0h
0x18001ab15  mov     rax, cs:__security_cookie
0x18001ab1c  xor     rax, rsp
0x18001ab1f  mov     [rbp+57h+var_20], rax
0x18001ab23  xor     r14d, r14d
0x18001ab26  mov     esi, edx
0x18001ab28  xorps   xmm0, xmm0
0x18001ab2b  mov     [rbp+57h+ProcessHandle], r14
0x18001ab2f  xor     eax, eax
0x18001ab31  mov     [rbp+57h+TokenHandle], r14
0x18001ab35  lea     rdx, [rbp+57h+ProcessHandle]; void **
0x18001ab39  mov     [rbp+57h+Handle], r14
0x18001ab3d  xor     r9d, r9d; unsigned int *
0x18001ab40  mov     [rbp+57h+IsMember], r14d
0x18001ab44  xor     r8d, r8d; void **
0x18001ab47  mov     [rbp+57h+var_30], rax
0x18001ab4b  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18001ab4f  mov     [rbp+57h+var_28], eax
0x18001ab52  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18001ab56  mov     qword ptr [rsp+0B0h+TokenType], r14; unsigned int *
0x18001ab5b  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18001ab5f  call    ?AiGetClientInformation@@YAKPEAXPEAPEAX1PEAK2@Z; AiGetClientInformation(void *,void * *,void * *,ulong *,ulong *)
0x18001ab64  mov     ebx, eax
0x18001ab66  test    eax, eax
0x18001ab68  jnz     loc_18001AC40
0x18001ab6e  mov     rcx, [rbp+57h+ProcessHandle]; ProcessHandle
0x18001ab72  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x18001ab76  lea     edx, [rax+0Ah]; DesiredAccess
0x18001ab79  call    cs:__imp_NtOpenProcessToken
0x18001ab80  nop     dword ptr [rax+rax+00h]
0x18001ab85  test    eax, eax
0x18001ab87  jns     short loc_18001AB9E
0x18001ab89  mov     ecx, eax; Status
0x18001ab8b  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x18001ab92  nop     dword ptr [rax+rax+00h]
0x18001ab97  mov     ebx, eax
0x18001ab99  jmp     loc_18001AC40
0x18001ab9e  mov     ecx, 2
0x18001aba3  mov     dword ptr [rbp+57h+var_30], 0Ch
0x18001abaa  lea     rax, [rbp+57h+var_30]
0x18001abae  mov     dword ptr [rbp+57h+var_30+4], ecx
0x18001abb1  mov     [rbp+57h+ObjectAttributes.SecurityQualityOfService], rax
0x18001abb5  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18001abb9  lea     rax, [rbp+57h+Handle]
0x18001abbd  mov     word ptr [rbp+57h+var_28], 1
0x18001abc3  mov     [rsp+0B0h+NewTokenHandle], rax; NewTokenHandle
0x18001abc8  xor     r9d, r9d; EffectiveOnly
0x18001abcb  mov     [rsp+0B0h+TokenType], ecx; TokenType
0x18001abcf  xor     edx, edx; DesiredAccess
0x18001abd1  mov     rcx, [rbp+57h+TokenHandle]; ExistingTokenHandle
0x18001abd5  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18001abdc  mov     [rbp+57h+ObjectAttributes.RootDirectory], r14
0x18001abe0  mov     [rbp+57h+ObjectAttributes.Attributes], r14d
0x18001abe4  mov     [rbp+57h+ObjectAttributes.ObjectName], r14
0x18001abe8  mov     [rbp+57h+ObjectAttributes.SecurityDescriptor], r14
0x18001abec  call    cs:__imp_NtDuplicateToken
0x18001abf3  nop     dword ptr [rax+rax+00h]
0x18001abf8  test    eax, eax
0x18001abfa  js      short loc_18001AB89
0x18001abfc  lea     rcx, [rsi+rsi*8]
0x18001ac00  lea     rax, ?g_pServiceInfo@@3PAU_SERVICE_INFO@@A; _SERVICE_INFO near * g_pServiceInfo
0x18001ac07  lea     rdx, [rax+rcx*8]; SidToCheck
0x18001ac0b  mov     rcx, [rbp+57h+Handle]; TokenHandle
0x18001ac0f  lea     r8, [rbp+57h+IsMember]; IsMember
0x18001ac13  call    cs:__imp_CheckTokenMembership
0x18001ac1a  nop     dword ptr [rax+rax+00h]
0x18001ac1f  test    eax, eax
0x18001ac21  jnz     short loc_18001AC34
0x18001ac23  call    cs:__imp_GetLastError
0x18001ac2a  nop     dword ptr [rax+rax+00h]
0x18001ac2f  jmp     loc_18001AB97
0x18001ac34  cmp     [rbp+57h+IsMember], r14d
0x18001ac38  mov     eax, 5
0x18001ac3d  cmovz   ebx, eax
0x18001ac40  mov     rcx, [rbp+57h+Handle]; Handle
0x18001ac44  test    rcx, rcx
0x18001ac47  jz      short loc_18001AC59
0x18001ac49  call    cs:__imp_NtClose
0x18001ac50  nop     dword ptr [rax+rax+00h]
0x18001ac55  mov     [rbp+57h+Handle], r14
0x18001ac59  mov     rcx, [rbp+57h+TokenHandle]; Handle
0x18001ac5d  test    rcx, rcx
0x18001ac60  jz      short loc_18001AC72
0x18001ac62  call    cs:__imp_NtClose
0x18001ac69  nop     dword ptr [rax+rax+00h]
0x18001ac6e  mov     [rbp+57h+TokenHandle], r14
0x18001ac72  cmp     [rbp+57h+ProcessHandle], r14
0x18001ac76  jz      short loc_18001AC88
0x18001ac78  mov     rcx, [rbp+57h+ProcessHandle]; Handle
0x18001ac7c  call    cs:__imp_NtClose
0x18001ac83  nop     dword ptr [rax+rax+00h]
0x18001ac88  mov     eax, ebx
0x18001ac8a  mov     rcx, [rbp+57h+var_20]
0x18001ac8e  xor     rcx, rsp; StackCookie
0x18001ac91  call    __security_check_cookie
0x18001ac96  mov     rbx, [rsp+0B0h+arg_10]
0x18001ac9e  add     rsp, 0A0h
0x18001aca5  pop     r14
0x18001aca7  pop     rsi
0x18001aca8  pop     rbp
0x18001aca9  retn
```
