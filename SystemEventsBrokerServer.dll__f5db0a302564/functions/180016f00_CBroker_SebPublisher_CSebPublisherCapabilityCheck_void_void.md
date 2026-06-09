# CBroker::SebPublisher::CSebPublisherCapabilityCheck(void *,void *)

- ea: `0x180016f00`
- end: `0x180017086`
- name: `?CSebPublisherCapabilityCheck@SebPublisher@CBroker@@CAJPEAX0@Z`
- size: `390`
- prototype: `__int64 __fastcall(void *, void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180016f00`
- `0x18001cf50`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016f8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016f8d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017041`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017041`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x180016fdc`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x180016fdc`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x18001701d`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x18001701d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180016faf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180016faf`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180016fc3`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180016fc3`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180016f83`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180016f83`
- `RPCRT4!RpcImpersonateClient` at `0x180016f9c`
- `RPCRT4!RpcImpersonateClient` at `0x180016f9c`
- `RPCRT4!RpcRevertToSelf` at `0x18001704c`
- `RPCRT4!RpcRevertToSelf` at `0x18001704c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001705d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001705d`

## pseudocode

```c
// Hidden C++ exception states: #wind=10 #try_helpers=1
__int64 __fastcall CBroker::SebPublisher::CSebPublisherCapabilityCheck(void *a1, void *a2)
{
  char v2; // di
  unsigned int LastError; // ebx
  HANDLE CurrentThread; // rax
  DWORD AccessMask; // [rsp+40h] [rbp+7h] BYREF
  DWORD PrivilegeSetLength; // [rsp+44h] [rbp+Bh] BYREF
  WINBOOL AccessStatus; // [rsp+48h] [rbp+Fh] BYREF
  DWORD GrantedAccess; // [rsp+4Ch] [rbp+13h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp+17h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+58h] [rbp+1Fh] BYREF
  struct _GENERIC_MAPPING GenericMapping; // [rsp+60h] [rbp+27h] BYREF
  struct _PRIVILEGE_SET PrivilegeSet; // [rsp+70h] [rbp+37h] BYREF

  AccessStatus = 0;
  PrivilegeSetLength = 0;
  GrantedAccess = 0;
  AccessMask = 0;
  GenericMapping.GenericRead = 0x20000;
  GenericMapping.GenericWrite = 0x20000;
  memset(&PrivilegeSet, 0, sizeof(PrivilegeSet));
  GenericMapping.GenericExecute = 0x20000;
  v2 = 0;
  GenericMapping.GenericAll = 2031616;
  TokenHandle = (void *)-1LL;
  SecurityDescriptor = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
          L"D:(A;;GR;;;SY)(A;;GR;;;AC)(A;;GR;;;AU)(A;;GR;;;S-1-5-80-2226967063-754826275-1661302337-2802353169-2369347280)",
          1u,
          &SecurityDescriptor,
          0) )
    goto LABEL_2;
  LastError = RpcImpersonateClient(0);
  if ( !LastError )
  {
    v2 = 1;
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle)
      || (AccessMask = 0x80000000,
          MapGenericMask(&AccessMask, &GenericMapping),
          PrivilegeSetLength = 20,
          !AccessCheck(
             SecurityDescriptor,
             TokenHandle,
             AccessMask,
             &GenericMapping,
             &PrivilegeSet,
             &PrivilegeSetLength,
             &GrantedAccess,
             &AccessStatus)) )
    {
LABEL_2:
      LastError = GetLastError();
      goto LABEL_7;
    }
    LastError = AccessStatus == 0 ? 5 : 0;
  }
LABEL_7:
  if ( TokenHandle != (void *)-1LL )
    CloseHandle(TokenHandle);
  if ( v2 )
    LastError = RpcRevertToSelf();
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  return LastError;
}

```

## disassembly

```asm
0x180016f00  mov     [rsp-8+arg_0], rbx
0x180016f05  mov     [rsp-8+arg_8], rdi
0x180016f0a  push    rbp
0x180016f0b  lea     rbp, [rsp-57h]
0x180016f10  sub     rsp, 90h
0x180016f17  mov     rax, cs:__security_cookie
0x180016f1e  xor     rax, rsp
0x180016f21  mov     [rbp+57h+var_8], rax
0x180016f25  xor     eax, eax
0x180016f27  mov     [rbp+57h+var_48], 0
0x180016f2e  xor     r9d, r9d; SecurityDescriptorSize
0x180016f31  mov     [rbp+57h+var_20.Privilege.Attributes], eax
0x180016f34  mov     [rbp+57h+var_4C], eax
0x180016f37  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x180016f3b  mov     eax, 20000h
0x180016f40  mov     [rbp+57h+var_44], 0
0x180016f47  xorps   xmm0, xmm0
0x180016f4a  mov     [rbp+57h+AccessMask], 0
0x180016f51  lea     edx, [r9+1]; StringSDRevision
0x180016f55  mov     [rbp+57h+GenericMapping.GenericRead], eax
0x180016f58  lea     rcx, aDAGrSyAGrAcAGr; "D:(A;;GR;;;SY)(A;;GR;;;AC)(A;;GR;;;AU)("...
0x180016f5f  mov     [rbp+57h+GenericMapping.GenericWrite], eax
0x180016f62  movups  xmmword ptr [rbp+57h+var_20.PrivilegeCount], xmm0
0x180016f66  mov     [rbp+57h+GenericMapping.GenericExecute], eax
0x180016f69  xor     dil, dil
0x180016f6c  mov     [rbp+57h+GenericMapping.GenericAll], 1F0000h
0x180016f73  mov     [rbp+57h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x180016f7b  mov     [rbp+57h+SecurityDescriptor], 0
0x180016f83  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180016f89  test    eax, eax
0x180016f8b  jnz     short loc_180016F9A
0x180016f8d  call    cs:__imp_GetLastError
0x180016f93  mov     ebx, eax
0x180016f95  jmp     loc_180017037
0x180016f9a  xor     ecx, ecx; BindingHandle
0x180016f9c  call    cs:__imp_RpcImpersonateClient
0x180016fa2  mov     ebx, eax
0x180016fa4  test    eax, eax
0x180016fa6  jnz     loc_180017037
0x180016fac  mov     dil, 1
0x180016faf  call    cs:__imp_GetCurrentThread
0x180016fb5  mov     rcx, rax; ThreadHandle
0x180016fb8  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x180016fbc  lea     edx, [rbx+8]; DesiredAccess
0x180016fbf  lea     r8d, [rbx+1]; OpenAsSelf
0x180016fc3  call    cs:__imp_OpenThreadToken
0x180016fc9  test    eax, eax
0x180016fcb  jz      short loc_180016F8D
0x180016fcd  lea     rdx, [rbp+57h+GenericMapping]; GenericMapping
0x180016fd1  mov     [rbp+57h+AccessMask], 80000000h
0x180016fd8  lea     rcx, [rbp+57h+AccessMask]; AccessMask
0x180016fdc  call    cs:__imp_MapGenericMask
0x180016fe2  mov     r8d, [rbp+57h+AccessMask]; DesiredAccess
0x180016fe6  lea     rax, [rbp+57h+var_48]
0x180016fea  mov     rdx, [rbp+57h+TokenHandle]; ClientToken
0x180016fee  lea     r9, [rbp+57h+GenericMapping]; GenericMapping
0x180016ff2  mov     rcx, [rbp+57h+SecurityDescriptor]; pSecurityDescriptor
0x180016ff6  mov     [rsp+90h+AccessStatus], rax; AccessStatus
0x180016ffb  lea     rax, [rbp+57h+var_44]
0x180016fff  mov     [rsp+90h+GrantedAccess], rax; GrantedAccess
0x180017004  lea     rax, [rbp+57h+var_4C]
0x180017008  mov     [rsp+90h+PrivilegeSetLength], rax; PrivilegeSetLength
0x18001700d  lea     rax, [rbp+57h+var_20]
0x180017011  mov     [rsp+90h+PrivilegeSet], rax; PrivilegeSet
0x180017016  mov     [rbp+57h+var_4C], 14h
0x18001701d  call    cs:__imp_AccessCheck
0x180017023  test    eax, eax
0x180017025  jz      loc_180016F8D
0x18001702b  mov     eax, [rbp+57h+var_48]
0x18001702e  neg     eax
0x180017030  sbb     ebx, ebx
0x180017032  not     ebx
0x180017034  and     ebx, 5
0x180017037  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x18001703b  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18001703f  jz      short loc_180017047
0x180017041  call    cs:__imp_CloseHandle
0x180017047  test    dil, dil
0x18001704a  jz      short loc_180017054
0x18001704c  call    cs:__imp_RpcRevertToSelf
0x180017052  mov     ebx, eax
0x180017054  mov     rcx, [rbp+57h+SecurityDescriptor]; hMem
0x180017058  test    rcx, rcx
0x18001705b  jz      short loc_180017063
0x18001705d  call    cs:__imp_LocalFree
0x180017063  mov     eax, ebx
0x180017065  mov     rcx, [rbp+57h+var_8]
0x180017069  xor     rcx, rsp; StackCookie
0x18001706c  call    __security_check_cookie
0x180017071  lea     r11, [rsp+90h+var_s0]
0x180017079  mov     rbx, [r11+10h]
0x18001707d  mov     rdi, [r11+18h]
0x180017081  mov     rsp, r11
0x180017084  pop     rbp
0x180017085  retn
```
