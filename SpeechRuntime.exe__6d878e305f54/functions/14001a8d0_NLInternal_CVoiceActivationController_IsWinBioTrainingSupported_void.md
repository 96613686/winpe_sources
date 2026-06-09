# NLInternal::CVoiceActivationController::IsWinBioTrainingSupported(void)

- ea: `0x14001a8d0`
- end: `0x14001aa20`
- name: `?IsWinBioTrainingSupported@CVoiceActivationController@NLInternal@@AEAAHXZ`
- size: `336`
- prototype: `__int64 __fastcall(NLInternal::CVoiceActivationController *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14001b600`

## callees

- `0x140002d30`
- `0x140011ea8`
- `0x140019e28`
- `0x14001a8d0`
- `0x14001af50`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x14001a99f`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x14001a99f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001a9a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001a9a9`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x14001a945`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x14001a945`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001a9f2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001a9f2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001a9e5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001a9e5`

## string_xrefs

- `0x14001a9b2`: `IsWinBioTraingSupported AccessCheck failure %i\n`
- `0x14001a9c9`: `SID Training blocked due to WinBio enrollment restrictions\n`

## pseudocode

```c
__int64 __fastcall NLInternal::CVoiceActivationController::IsWinBioTrainingSupported(
        NLInternal::CVoiceActivationController *this)
{
  unsigned int v1; // ebx
  DWORD LastError; // eax
  DWORD GrantedAccess; // [rsp+40h] [rbp+7h] BYREF
  WINBOOL AccessStatus; // [rsp+44h] [rbp+Bh] BYREF
  DWORD PrivilegeSetLength; // [rsp+48h] [rbp+Fh] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+50h] [rbp+17h] BYREF
  LPCWSTR StringSecurityDescriptor; // [rsp+58h] [rbp+1Fh] BYREF
  _GENERIC_MAPPING GenericMapping; // [rsp+60h] [rbp+27h] BYREF
  struct _PRIVILEGE_SET PrivilegeSet; // [rsp+70h] [rbp+37h] BYREF

  AccessStatus = 0;
  v1 = 1;
  GrantedAccess = 0;
  SecurityDescriptor = 0;
  GenericMapping.GenericRead = 4;
  GenericMapping.GenericWrite = 116;
  GenericMapping.GenericExecute = 12;
  GenericMapping.GenericAll = 124;
  StringSecurityDescriptor = 0;
  CSpDynamicString::operator=((CSpDynamicString *)&StringSecurityDescriptor);
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(StringSecurityDescriptor, 1u, &SecurityDescriptor, 0) )
  {
    PrivilegeSetLength = 20;
    memset(&PrivilegeSet, 0, sizeof(PrivilegeSet));
    if ( AccessCheck(
           SecurityDescriptor,
           (HANDLE)0xFFFFFFFFFFFFFFFALL,
           0x2000000u,
           &GenericMapping,
           &PrivilegeSet,
           &PrivilegeSetLength,
           &GrantedAccess,
           &AccessStatus) )
    {
      if ( (GrantedAccess & 0x10) == 0 )
      {
        DoTraceMessage(8, "SID Training blocked due to WinBio enrollment restrictions\n");
        v1 = 0;
      }
    }
    else
    {
      LastError = GetLastError();
      DoTraceMessage(2, "IsWinBioTraingSupported AccessCheck failure %i\n", LastError);
    }
  }
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  CloseHandle((HANDLE)0xFFFFFFFFFFFFFFFALL);
  CSpDynamicString::_free((CSpDynamicString *)&StringSecurityDescriptor);
  return v1;
}

```

## disassembly

```asm
0x14001a8d0  mov     [rsp-8+arg_0], rbx
0x14001a8d5  push    rbp
0x14001a8d6  lea     rbp, [rsp-57h]
0x14001a8db  sub     rsp, 90h
0x14001a8e2  mov     rax, cs:__security_cookie
0x14001a8e9  xor     rax, rsp
0x14001a8ec  mov     [rbp+57h+var_8], rax
0x14001a8f0  lea     rcx, [rbp+57h+StringSecurityDescriptor]; this
0x14001a8f4  mov     [rbp+57h+var_4C], 0
0x14001a8fb  mov     ebx, 1
0x14001a900  mov     [rbp+57h+var_50], 0
0x14001a907  mov     [rbp+57h+SecurityDescriptor], 0
0x14001a90f  mov     [rbp+57h+GenericMapping.GenericRead], 4
0x14001a916  mov     [rbp+57h+GenericMapping.GenericWrite], 74h ; 't'
0x14001a91d  mov     [rbp+57h+GenericMapping.GenericExecute], 0Ch
0x14001a924  mov     [rbp+57h+GenericMapping.GenericAll], 7Ch ; '|'
0x14001a92b  mov     [rbp+57h+StringSecurityDescriptor], 0
0x14001a933  call    ??4CSpDynamicString@@QEAAPEAGPEBG@Z; CSpDynamicString::operator=(ushort const *)
0x14001a938  mov     rcx, [rbp+57h+StringSecurityDescriptor]; StringSecurityDescriptor
0x14001a93c  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x14001a940  xor     r9d, r9d; SecurityDescriptorSize
0x14001a943  mov     edx, ebx; StringSDRevision
0x14001a945  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x14001a94b  test    eax, eax
0x14001a94d  jz      loc_14001A9DC
0x14001a953  mov     rcx, [rbp+57h+SecurityDescriptor]; pSecurityDescriptor
0x14001a957  lea     r9, [rbp+57h+GenericMapping]; GenericMapping
0x14001a95b  xor     eax, eax
0x14001a95d  mov     [rbp+57h+var_48], 14h
0x14001a964  mov     [rbp+57h+var_20.Privilege.Attributes], eax
0x14001a967  xorps   xmm0, xmm0
0x14001a96a  lea     rax, [rbp+57h+var_4C]
0x14001a96e  mov     rdx, 0FFFFFFFFFFFFFFFAh; ClientToken
0x14001a975  mov     [rsp+90h+AccessStatus], rax; AccessStatus
0x14001a97a  mov     r8d, 2000000h; DesiredAccess
0x14001a980  lea     rax, [rbp+57h+var_50]
0x14001a984  mov     [rsp+90h+GrantedAccess], rax; GrantedAccess
0x14001a989  lea     rax, [rbp+57h+var_48]
0x14001a98d  mov     [rsp+90h+PrivilegeSetLength], rax; PrivilegeSetLength
0x14001a992  lea     rax, [rbp+57h+var_20]
0x14001a996  mov     [rsp+90h+PrivilegeSet], rax; PrivilegeSet
0x14001a99b  movups  xmmword ptr [rbp+57h+var_20.PrivilegeCount], xmm0
0x14001a99f  call    cs:__imp_AccessCheck
0x14001a9a5  test    eax, eax
0x14001a9a7  jnz     short loc_14001A9C3
0x14001a9a9  call    cs:__imp_GetLastError
0x14001a9af  mov     r8d, eax
0x14001a9b2  lea     rdx, aIswinbiotraing; "IsWinBioTraingSupported AccessCheck fai"...
0x14001a9b9  lea     ecx, [rbx+1]; int
0x14001a9bc  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x14001a9c1  jmp     short loc_14001A9DC
0x14001a9c3  test    byte ptr [rbp+57h+var_50], 10h
0x14001a9c7  jnz     short loc_14001A9DC
0x14001a9c9  lea     rdx, aSidTrainingBlo; "SID Training blocked due to WinBio enro"...
0x14001a9d0  mov     ecx, 8; int
0x14001a9d5  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x14001a9da  xor     ebx, ebx
0x14001a9dc  mov     rcx, [rbp+57h+SecurityDescriptor]; hMem
0x14001a9e0  test    rcx, rcx
0x14001a9e3  jz      short loc_14001A9EB
0x14001a9e5  call    cs:__imp_LocalFree
0x14001a9eb  mov     rcx, 0FFFFFFFFFFFFFFFAh; hObject
0x14001a9f2  call    cs:__imp_CloseHandle
0x14001a9f8  lea     rcx, [rbp+57h+StringSecurityDescriptor]; this
0x14001a9fc  call    ?_free@CSpDynamicString@@AEAAXXZ; CSpDynamicString::_free(void)
0x14001aa01  mov     eax, ebx
0x14001aa03  mov     rcx, [rbp+57h+var_8]
0x14001aa07  xor     rcx, rsp; StackCookie
0x14001aa0a  call    __security_check_cookie
0x14001aa0f  mov     rbx, [rsp+90h+arg_0]
0x14001aa17  add     rsp, 90h
0x14001aa1e  pop     rbp
0x14001aa1f  retn
```
