# CRuntimeBroker::CheckClient(bool *)

- ea: `0x14000aef0`
- end: `0x14000b010`
- name: `?CheckClient@CRuntimeBroker@@AEAAJPEA_N@Z`
- size: `288`
- prototype: `int(CRuntimeBroker *__hidden this, bool *)`
- caller_count: `4`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000b2e0`
- `0x14000b320`
- `0x14000b490`
- `0x14000c7e0`

## callees

- `0x140008c80`
- `0x14000aef0`
- `0x14000b018`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!PrivilegeCheck` at `0x14000afa0`
- `api-ms-win-security-base-l1-1-0!PrivilegeCheck` at `0x14000afa0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000af4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000afaa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000af4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000afaa`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x14000af44`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x14000af44`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14000af2e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14000af2e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000afec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000afec`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x14000af63`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x14000af63`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x14000af1e`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x14000af1e`

## pseudocode

```c
__int64 __fastcall CRuntimeBroker::CheckClient(CRuntimeBroker *this, bool *a2)
{
  int v3; // ebx
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  void *v6; // rcx
  CRuntimeBroker *v7; // rcx
  signed int v8; // eax
  WINBOOL pfResult; // [rsp+20h] [rbp-30h] BYREF
  void *TokenHandle; // [rsp+28h] [rbp-28h] BYREF
  struct _PRIVILEGE_SET RequiredPrivileges; // [rsp+30h] [rbp-20h] BYREF

  TokenHandle = 0;
  *a2 = 0;
  v3 = CoImpersonateClient();
  if ( v3 >= 0 )
  {
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
    }
    CoRevertToSelf();
    if ( v3 >= 0 )
    {
      v6 = TokenHandle;
      pfResult = 0;
      *a2 = 0;
      *(_QWORD *)&RequiredPrivileges.Privilege[0].Luid.HighPart = 0;
      RequiredPrivileges.PrivilegeCount = 1;
      RequiredPrivileges.Control = 1;
      RequiredPrivileges.Privilege[0].Luid.LowPart = 20;
      if ( PrivilegeCheck(v6, &RequiredPrivileges, &pfResult) )
      {
        v3 = 0;
        *a2 = pfResult != 0;
LABEL_12:
        if ( !*a2 )
          v3 = CRuntimeBroker::CheckClientAccess(v7, a2, TokenHandle);
        goto LABEL_14;
      }
      v8 = GetLastError();
      v3 = v8;
      if ( v8 > 0 )
        v3 = (unsigned __int16)v8 | 0x80070000;
      if ( v3 >= 0 )
        goto LABEL_12;
    }
  }
LABEL_14:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x14000aef0  mov     [rsp-8+arg_0], rbx
0x14000aef5  mov     [rsp-8+arg_10], rdi
0x14000aefa  push    rbp
0x14000aefb  mov     rbp, rsp
0x14000aefe  sub     rsp, 50h
0x14000af02  mov     rax, cs:__security_cookie
0x14000af09  xor     rax, rsp
0x14000af0c  mov     [rbp+var_8], rax
0x14000af10  mov     rdi, rdx
0x14000af13  mov     [rbp+TokenHandle], 0
0x14000af1b  mov     byte ptr [rdx], 0
0x14000af1e  call    cs:__imp_CoImpersonateClient
0x14000af24  mov     ebx, eax
0x14000af26  test    eax, eax
0x14000af28  js      loc_14000AFE3
0x14000af2e  call    cs:__imp_GetCurrentThread
0x14000af34  mov     edx, 8; DesiredAccess
0x14000af39  lea     r9, [rbp+TokenHandle]; TokenHandle
0x14000af3d  mov     rcx, rax; ThreadHandle
0x14000af40  lea     r8d, [rdx-7]; OpenAsSelf
0x14000af44  call    cs:__imp_OpenThreadToken
0x14000af4a  test    eax, eax
0x14000af4c  jnz     short loc_14000AF63
0x14000af4e  call    cs:__imp_GetLastError
0x14000af54  mov     ebx, eax
0x14000af56  test    eax, eax
0x14000af58  jle     short loc_14000AF63
0x14000af5a  movzx   ebx, ax
0x14000af5d  or      ebx, 80070000h
0x14000af63  call    cs:__imp_CoRevertToSelf
0x14000af69  test    ebx, ebx
0x14000af6b  js      short loc_14000AFE3
0x14000af6d  mov     rcx, [rbp+TokenHandle]; ClientToken
0x14000af71  lea     r8, [rbp+pfResult]; pfResult
0x14000af75  lea     rdx, [rbp+RequiredPrivileges]; RequiredPrivileges
0x14000af79  mov     [rbp+pfResult], 0
0x14000af80  mov     byte ptr [rdi], 0
0x14000af83  mov     qword ptr [rbp+RequiredPrivileges.Privilege.Luid.HighPart], 0
0x14000af8b  mov     [rbp+RequiredPrivileges.PrivilegeCount], 1
0x14000af92  mov     [rbp+RequiredPrivileges.Control], 1
0x14000af99  mov     [rbp+RequiredPrivileges.Privilege.Luid.LowPart], 14h
0x14000afa0  call    cs:__imp_PrivilegeCheck
0x14000afa6  test    eax, eax
0x14000afa8  jnz     short loc_14000AFC5
0x14000afaa  call    cs:__imp_GetLastError
0x14000afb0  mov     ebx, eax
0x14000afb2  test    eax, eax
0x14000afb4  jle     short loc_14000AFBF
0x14000afb6  movzx   ebx, ax
0x14000afb9  or      ebx, 80070000h
0x14000afbf  test    ebx, ebx
0x14000afc1  js      short loc_14000AFE3
0x14000afc3  jmp     short loc_14000AFD0
0x14000afc5  cmp     [rbp+pfResult], 0
0x14000afc9  setnz   al
0x14000afcc  xor     ebx, ebx
0x14000afce  mov     [rdi], al
0x14000afd0  cmp     byte ptr [rdi], 0
0x14000afd3  jnz     short loc_14000AFE3
0x14000afd5  mov     r8, [rbp+TokenHandle]; void *
0x14000afd9  mov     rdx, rdi; bool *
0x14000afdc  call    ?CheckClientAccess@CRuntimeBroker@@AEAAJPEA_NPEAX@Z; CRuntimeBroker::CheckClientAccess(bool *,void *)
0x14000afe1  mov     ebx, eax
0x14000afe3  mov     rcx, [rbp+TokenHandle]; hObject
0x14000afe7  test    rcx, rcx
0x14000afea  jz      short loc_14000AFF2
0x14000afec  call    cs:__imp_CloseHandle
0x14000aff2  mov     eax, ebx
0x14000aff4  mov     rcx, [rbp+var_8]
0x14000aff8  xor     rcx, rsp; StackCookie
0x14000affb  call    __security_check_cookie
0x14000b000  mov     rbx, [rsp+50h+arg_0]
0x14000b005  mov     rdi, [rsp+50h+arg_10]
0x14000b00a  add     rsp, 50h
0x14000b00e  pop     rbp
0x14000b00f  retn
```
