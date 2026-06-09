# GetUserSidFromSessionId(ulong,void * *)

- ea: `0x18000d47c`
- end: `0x18000d55d`
- name: `?GetUserSidFromSessionId@@YAJKPEAPEAX@Z`
- size: `225`
- prototype: `__int64 __fastcall(ULONG SessionId, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800144e4`

## callees

- `0x180004170`
- `0x1800058b4`
- `0x18000d404`
- `0x18000d47c`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x18000d50b`
- `ntdll!NtQueryInformationToken` at `0x18000d50b`
- `ntdll!NtClose` at `0x18000d53c`
- `ntdll!NtClose` at `0x18000d53c`
- `ntdll!RtlNtStatusToDosError` at `0x18000d517`
- `ntdll!RtlNtStatusToDosError` at `0x18000d517`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d4d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d4d6`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x18000d4cc`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x18000d4cc`

## pseudocode

```c
__int64 __fastcall GetUserSidFromSessionId(__int64 SessionId, void **a2)
{
  ULONG v2; // ebx
  unsigned int v3; // ebx
  signed int LastError; // eax
  int v5; // eax
  ULONG ReturnLength; // [rsp+30h] [rbp-88h] BYREF
  void *phToken; // [rsp+38h] [rbp-80h] BYREF
  PSID TokenInformation[12]; // [rsp+40h] [rbp-78h] BYREF

  v2 = SessionId;
  phToken = 0;
  ReturnLength = 0;
  SourceSid = 0;
  if ( !(unsigned __int8)IsWTSQueryUserTokenPresent(SessionId, a2) )
  {
    v3 = -2147467263;
    goto LABEL_10;
  }
  if ( WTSQueryUserToken(v2, &phToken) )
  {
    v5 = NtQueryInformationToken(phToken, TokenUser, TokenInformation, 0x54u, &ReturnLength);
    if ( v5 >= 0 )
    {
      v3 = DuplicateSID(TokenInformation[0], &SourceSid);
      goto LABEL_10;
    }
    LastError = RtlNtStatusToDosError(v5);
  }
  else
  {
    LastError = GetLastError();
  }
  v3 = LastError;
  if ( LastError > 0 )
    v3 = (unsigned __int16)LastError | 0x80070000;
LABEL_10:
  if ( phToken )
    NtClose(phToken);
  return v3;
}

```

## disassembly

```asm
0x18000d47c  push    rbx
0x18000d47e  sub     rsp, 0B0h
0x18000d485  mov     rax, cs:__security_cookie
0x18000d48c  xor     rax, rsp
0x18000d48f  mov     [rsp+0B8h+var_18], rax
0x18000d497  mov     ebx, ecx
0x18000d499  mov     [rsp+0B8h+phToken], 0
0x18000d4a2  mov     [rsp+0B8h+var_88], 0
0x18000d4aa  mov     cs:SourceSid, 0
0x18000d4b5  call    IsWTSQueryUserTokenPresent
0x18000d4ba  test    al, al
0x18000d4bc  jnz     short loc_18000D4C5
0x18000d4be  mov     ebx, 80004001h
0x18000d4c3  jmp     short loc_18000D532
0x18000d4c5  lea     rdx, [rsp+0B8h+phToken]; phToken
0x18000d4ca  mov     ecx, ebx; SessionId
0x18000d4cc  call    cs:__imp_WTSQueryUserToken
0x18000d4d2  test    eax, eax
0x18000d4d4  jnz     short loc_18000D4ED
0x18000d4d6  call    cs:__imp_GetLastError
0x18000d4dc  mov     ebx, eax
0x18000d4de  test    eax, eax
0x18000d4e0  jle     short loc_18000D532
0x18000d4e2  movzx   ebx, ax
0x18000d4e5  or      ebx, 80070000h
0x18000d4eb  jmp     short loc_18000D532
0x18000d4ed  mov     rcx, [rsp+0B8h+phToken]; TokenHandle
0x18000d4f2  lea     rax, [rsp+0B8h+var_88]
0x18000d4f7  mov     r9d, 54h ; 'T'; TokenInformationLength
0x18000d4fd  mov     [rsp+0B8h+ReturnLength], rax; ReturnLength
0x18000d502  lea     r8, [rsp+0B8h+TokenInformation]; TokenInformation
0x18000d507  lea     edx, [r9-53h]; TokenInformationClass
0x18000d50b  call    cs:__imp_NtQueryInformationToken
0x18000d511  test    eax, eax
0x18000d513  jns     short loc_18000D51F
0x18000d515  mov     ecx, eax; Status
0x18000d517  call    cs:__imp_RtlNtStatusToDosError
0x18000d51d  jmp     short loc_18000D4DC
0x18000d51f  mov     rcx, [rsp+0B8h+TokenInformation]; SourceSid
0x18000d524  lea     rdx, SourceSid; void **
0x18000d52b  call    ?DuplicateSID@@YAJPEAXPEAPEAX@Z; DuplicateSID(void *,void * *)
0x18000d530  mov     ebx, eax
0x18000d532  mov     rcx, [rsp+0B8h+phToken]; Handle
0x18000d537  test    rcx, rcx
0x18000d53a  jz      short loc_18000D542
0x18000d53c  call    cs:__imp_NtClose
0x18000d542  mov     eax, ebx
0x18000d544  mov     rcx, [rsp+0B8h+var_18]
0x18000d54c  xor     rcx, rsp; StackCookie
0x18000d54f  call    __security_check_cookie
0x18000d554  add     rsp, 0B0h
0x18000d55b  pop     rbx
0x18000d55c  retn
```
