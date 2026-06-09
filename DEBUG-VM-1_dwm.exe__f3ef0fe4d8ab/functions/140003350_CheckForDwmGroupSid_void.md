# CheckForDwmGroupSid(void)

- ea: `0x140003350`
- end: `0x140003477`
- name: `?CheckForDwmGroupSid@@YAJXZ`
- size: `295`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14000215c`

## callees

- `0x140002e6c`
- `0x140003350`
- `0x140005530`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400033d4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400033d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400033ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400033ee`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1400033e4`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1400033e4`
- `ntdll!RtlFreeSid` at `0x14000344e`
- `ntdll!RtlFreeSid` at `0x14000344e`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1400033b3`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1400033b3`

## pseudocode

```c
__int64 CheckForDwmGroupSid(void)
{
  NTSTATUS v0; // ebx
  int v1; // ebx
  signed int LastError; // eax
  ULONG SubAuthority2; // [rsp+20h] [rbp-60h]
  WINBOOL IsMember; // [rsp+60h] [rbp-20h] BYREF
  PSID SidToCheck; // [rsp+68h] [rbp-18h] BYREF
  _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+70h] [rbp-10h] BYREF

  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  SidToCheck = 0;
  IsMember = 0;
  v0 = RtlAllocateAndInitializeSid(&IdentifierAuthority, 2u, 0x5Au, 0, 0, 0, 0, 0, 0, 0, &SidToCheck);
  if ( v0 < 0 )
  {
    v1 = v0 | 0x10000000;
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v1, 0x20u, 0);
    goto LABEL_12;
  }
  SetLastError(0);
  if ( CheckTokenMembership(0, SidToCheck, &IsMember) )
  {
    v1 = 0;
    if ( IsMember )
      goto LABEL_12;
    v1 = -2147024891;
    SubAuthority2 = 38;
  }
  else
  {
    LastError = GetLastError();
    v1 = LastError;
    if ( LastError > 0 )
      v1 = (unsigned __int16)LastError | 0x80070000;
    SubAuthority2 = 34;
    if ( v1 >= 0 )
      v1 = -2003304445;
  }
  MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v1, SubAuthority2, 0);
LABEL_12:
  if ( SidToCheck )
    RtlFreeSid(SidToCheck);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x140003350  mov     [rsp-8+arg_0], rbx
0x140003355  mov     [rsp-8+arg_8], rdi
0x14000335a  push    rbp
0x14000335b  mov     rbp, rsp
0x14000335e  sub     rsp, 80h
0x140003365  mov     rax, cs:__security_cookie
0x14000336c  xor     rax, rsp
0x14000336f  mov     [rbp+var_8], rax
0x140003373  xor     edi, edi
0x140003375  mov     word ptr [rbp+IdentifierAuthority.Value+4], 500h
0x14000337b  lea     rax, [rbp+SidToCheck]
0x14000337f  mov     dword ptr [rbp+IdentifierAuthority.Value], edi
0x140003382  mov     [rsp+80h+Sid], rax; Sid
0x140003387  lea     rcx, [rbp+IdentifierAuthority]; IdentifierAuthority
0x14000338b  mov     [rsp+80h+SubAuthority7], edi; SubAuthority7
0x14000338f  xor     r9d, r9d; SubAuthority1
0x140003392  mov     [rsp+80h+SubAuthority6], edi; SubAuthority6
0x140003396  lea     r8d, [rdi+5Ah]; SubAuthority0
0x14000339a  mov     [rsp+80h+SubAuthority5], edi; SubAuthority5
0x14000339e  mov     dl, 2; SubAuthorityCount
0x1400033a0  mov     [rsp+80h+SubAuthority4], edi; SubAuthority4
0x1400033a4  mov     [rsp+80h+SubAuthority3], edi; SubAuthority3
0x1400033a8  mov     [rsp+80h+SubAuthority2], edi; SubAuthority2
0x1400033ac  mov     [rbp+SidToCheck], rdi
0x1400033b0  mov     [rbp+IsMember], edi
0x1400033b3  call    cs:__imp_RtlAllocateAndInitializeSid
0x1400033b9  mov     ebx, eax
0x1400033bb  test    eax, eax
0x1400033bd  jns     short loc_1400033D2
0x1400033bf  mov     qword ptr [rsp+80h+SubAuthority3], rdi
0x1400033c4  bts     ebx, 1Ch
0x1400033c8  mov     [rsp+80h+SubAuthority2], 20h ; ' '
0x1400033d0  jmp     short loc_140003435
0x1400033d2  xor     ecx, ecx; dwErrCode
0x1400033d4  call    cs:__imp_SetLastError
0x1400033da  mov     rdx, [rbp+SidToCheck]; SidToCheck
0x1400033de  lea     r8, [rbp+IsMember]; IsMember
0x1400033e2  xor     ecx, ecx; TokenHandle
0x1400033e4  call    cs:__imp_CheckTokenMembership
0x1400033ea  test    eax, eax
0x1400033ec  jnz     short loc_14000341C
0x1400033ee  call    cs:__imp_GetLastError
0x1400033f4  mov     ebx, eax
0x1400033f6  test    eax, eax
0x1400033f8  jle     short loc_140003403
0x1400033fa  movzx   ebx, ax
0x1400033fd  or      ebx, 80070000h
0x140003403  test    ebx, ebx
0x140003405  mov     qword ptr [rsp+80h+SubAuthority3], rdi
0x14000340a  mov     eax, 88980003h
0x14000340f  mov     [rsp+80h+SubAuthority2], 22h ; '"'
0x140003417  cmovns  ebx, eax
0x14000341a  jmp     short loc_140003435
0x14000341c  mov     ebx, edi
0x14000341e  cmp     [rbp+IsMember], edi
0x140003421  jnz     short loc_140003445
0x140003423  mov     qword ptr [rsp+80h+SubAuthority3], rdi; void *
0x140003428  mov     ebx, 80070005h
0x14000342d  mov     [rsp+80h+SubAuthority2], 26h ; '&'; unsigned int
0x140003435  xor     edx, edx; int *
0x140003437  mov     r9d, ebx; int
0x14000343a  xor     r8d, r8d; unsigned int
0x14000343d  lea     ecx, [rdx+14h]; unsigned int
0x140003440  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x140003445  mov     rcx, [rbp+SidToCheck]; Sid
0x140003449  test    rcx, rcx
0x14000344c  jz      short loc_140003454
0x14000344e  call    cs:__imp_RtlFreeSid
0x140003454  mov     eax, ebx
0x140003456  mov     rcx, [rbp+var_8]
0x14000345a  xor     rcx, rsp; StackCookie
0x14000345d  call    __security_check_cookie
0x140003462  lea     r11, [rsp+80h+var_s0]
0x14000346a  mov     rbx, [r11+10h]
0x14000346e  mov     rdi, [r11+18h]
0x140003472  mov     rsp, r11
0x140003475  pop     rbp
0x140003476  retn
```
