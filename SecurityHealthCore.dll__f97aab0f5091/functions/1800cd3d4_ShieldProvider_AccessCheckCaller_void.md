# ShieldProvider::AccessCheckCaller(void *)

- ea: `0x1800cd3d4`
- end: `0x1800cd51b`
- name: `?AccessCheckCaller@ShieldProvider@@YAJPEAX@Z`
- size: `327`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR pSecurityDescriptor, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800111c0`

## callees

- `0x180004710`
- `0x1800cd3d4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800cd432`
- `KERNEL32!GetLastError` at `0x1800cd4ae`
- `KERNEL32!GetLastError` at `0x1800cd432`
- `KERNEL32!GetLastError` at `0x1800cd4ae`
- `KERNEL32!CloseHandle` at `0x1800cd4e5`
- `KERNEL32!CloseHandle` at `0x1800cd4e5`
- `KERNEL32!GetCurrentThread` at `0x1800cd414`
- `KERNEL32!GetCurrentThread` at `0x1800cd414`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800cd428`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800cd428`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x1800cd4a4`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x1800cd4a4`
- `ole32!CoImpersonateClient` at `0x1800cd3fc`
- `ole32!CoImpersonateClient` at `0x1800cd3fc`
- `ole32!CoRevertToSelf` at `0x1800cd4d6`
- `ole32!CoRevertToSelf` at `0x1800cd4d6`

## pseudocode

```c
__int64 __fastcall ShieldProvider::AccessCheckCaller(PSECURITY_DESCRIPTOR pSecurityDescriptor, void *a2)
{
  signed int v3; // ebx
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  signed int v6; // eax
  WINBOOL AccessStatus; // [rsp+40h] [rbp+7h] BYREF
  DWORD GrantedAccess; // [rsp+44h] [rbp+Bh] BYREF
  DWORD PrivilegeSetLength; // [rsp+48h] [rbp+Fh] BYREF
  void *TokenHandle; // [rsp+50h] [rbp+17h] BYREF
  struct _PRIVILEGE_SET PrivilegeSet; // [rsp+58h] [rbp+1Fh] BYREF
  _GENERIC_MAPPING GenericMapping; // [rsp+70h] [rbp+37h] BYREF

  v3 = CoImpersonateClient();
  if ( v3 < 0 )
  {
    if ( v3 == -2147417833 )
      return 0;
  }
  else
  {
    TokenHandle = 0;
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 8u, 0, &TokenHandle) )
      goto LABEL_6;
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    if ( v3 >= 0 )
    {
LABEL_6:
      PrivilegeSetLength = 20;
      GrantedAccess = 0;
      AccessStatus = 0;
      GenericMapping = 0;
      memset(&PrivilegeSet, 0, sizeof(PrivilegeSet));
      if ( AccessCheck(
             pSecurityDescriptor,
             TokenHandle,
             1u,
             &GenericMapping,
             &PrivilegeSet,
             &PrivilegeSetLength,
             &GrantedAccess,
             &AccessStatus) )
      {
        goto LABEL_10;
      }
      v6 = GetLastError();
      v3 = v6;
      if ( v6 > 0 )
        v3 = (unsigned __int16)v6 | 0x80070000;
      if ( v3 >= 0 )
LABEL_10:
        v3 = AccessStatus == 0 ? 0x80070005 : 0;
    }
    CoRevertToSelf();
    if ( TokenHandle )
      CloseHandle(TokenHandle);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800cd3d4  mov     [rsp-8+arg_8], rbx
0x1800cd3d9  mov     [rsp-8+arg_10], rdi
0x1800cd3de  push    rbp
0x1800cd3df  lea     rbp, [rsp-57h]
0x1800cd3e4  sub     rsp, 90h
0x1800cd3eb  mov     rax, cs:__security_cookie
0x1800cd3f2  xor     rax, rsp
0x1800cd3f5  mov     [rbp+57h+var_10], rax
0x1800cd3f9  mov     rdi, rcx
0x1800cd3fc  call    cs:__imp_CoImpersonateClient
0x1800cd402  mov     ebx, eax
0x1800cd404  test    eax, eax
0x1800cd406  js      loc_1800CD4ED
0x1800cd40c  mov     [rbp+57h+TokenHandle], 0
0x1800cd414  call    cs:__imp_GetCurrentThread
0x1800cd41a  xor     r8d, r8d; OpenAsSelf
0x1800cd41d  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x1800cd421  mov     rcx, rax; ThreadHandle
0x1800cd424  lea     edx, [r8+8]; DesiredAccess
0x1800cd428  call    cs:__imp_OpenThreadToken
0x1800cd42e  test    eax, eax
0x1800cd430  jnz     short loc_1800CD44F
0x1800cd432  call    cs:__imp_GetLastError
0x1800cd438  mov     ebx, eax
0x1800cd43a  test    eax, eax
0x1800cd43c  jle     short loc_1800CD447
0x1800cd43e  movzx   ebx, ax
0x1800cd441  or      ebx, 80070000h
0x1800cd447  test    ebx, ebx
0x1800cd449  js      loc_1800CD4D6
0x1800cd44f  mov     rdx, [rbp+57h+TokenHandle]; ClientToken
0x1800cd453  lea     r9, [rbp+57h+GenericMapping]; GenericMapping
0x1800cd457  xor     eax, eax
0x1800cd459  mov     [rbp+57h+var_48], 14h
0x1800cd460  mov     [rbp+57h+var_38.Privilege.Attributes], eax
0x1800cd463  xorps   xmm0, xmm0
0x1800cd466  mov     [rbp+57h+var_4C], eax
0x1800cd469  xorps   xmm1, xmm1
0x1800cd46c  mov     [rbp+57h+var_50], eax
0x1800cd46f  mov     r8d, 1; DesiredAccess
0x1800cd475  lea     rax, [rbp+57h+var_50]
0x1800cd479  mov     rcx, rdi; pSecurityDescriptor
0x1800cd47c  mov     [rsp+90h+AccessStatus], rax; AccessStatus
0x1800cd481  lea     rax, [rbp+57h+var_4C]
0x1800cd485  mov     [rsp+90h+GrantedAccess], rax; GrantedAccess
0x1800cd48a  lea     rax, [rbp+57h+var_48]
0x1800cd48e  mov     [rsp+90h+PrivilegeSetLength], rax; PrivilegeSetLength
0x1800cd493  lea     rax, [rbp+57h+var_38]
0x1800cd497  mov     [rsp+90h+PrivilegeSet], rax; PrivilegeSet
0x1800cd49c  movups  xmmword ptr [rbp+57h+GenericMapping.GenericRead], xmm0
0x1800cd4a0  movups  xmmword ptr [rbp+57h+var_38.PrivilegeCount], xmm1
0x1800cd4a4  call    cs:__imp_AccessCheck
0x1800cd4aa  test    eax, eax
0x1800cd4ac  jnz     short loc_1800CD4C7
0x1800cd4ae  call    cs:__imp_GetLastError
0x1800cd4b4  mov     ebx, eax
0x1800cd4b6  test    eax, eax
0x1800cd4b8  jle     short loc_1800CD4C3
0x1800cd4ba  movzx   ebx, ax
0x1800cd4bd  or      ebx, 80070000h
0x1800cd4c3  test    ebx, ebx
0x1800cd4c5  js      short loc_1800CD4D6
0x1800cd4c7  mov     eax, [rbp+57h+var_50]
0x1800cd4ca  neg     eax
0x1800cd4cc  sbb     ebx, ebx
0x1800cd4ce  not     ebx
0x1800cd4d0  and     ebx, 80070005h
0x1800cd4d6  call    cs:__imp_CoRevertToSelf
0x1800cd4dc  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x1800cd4e0  test    rcx, rcx
0x1800cd4e3  jz      short loc_1800CD4F8
0x1800cd4e5  call    cs:__imp_CloseHandle
0x1800cd4eb  jmp     short loc_1800CD4F8
0x1800cd4ed  xor     ecx, ecx
0x1800cd4ef  cmp     ebx, 80010117h
0x1800cd4f5  cmovz   ebx, ecx
0x1800cd4f8  mov     eax, ebx
0x1800cd4fa  mov     rcx, [rbp+57h+var_10]
0x1800cd4fe  xor     rcx, rsp; StackCookie
0x1800cd501  call    __security_check_cookie
0x1800cd506  lea     r11, [rsp+90h+var_s0]
0x1800cd50e  mov     rbx, [r11+18h]
0x1800cd512  mov     rdi, [r11+20h]
0x1800cd516  mov     rsp, r11
0x1800cd519  pop     rbp
0x1800cd51a  retn
```
