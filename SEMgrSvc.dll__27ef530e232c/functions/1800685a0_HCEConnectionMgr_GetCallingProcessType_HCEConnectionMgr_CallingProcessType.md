# HCEConnectionMgr::GetCallingProcessType(HCEConnectionMgr::_CallingProcessType *)

- ea: `0x1800685a0`
- end: `0x180068731`
- name: `?GetCallingProcessType@HCEConnectionMgr@@MEAAJPEAW4_CallingProcessType@1@@Z`
- size: `401`
- prototype: `__int64 __fastcall(HCEConnectionMgr *__hidden this, enum HCEConnectionMgr::_CallingProcessType *)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800049a0`
- `0x1800685a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068649`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068649`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180068629`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180068629`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18006863f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18006863f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800686ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800686ed`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x180068668`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x180068668`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x1800686c0`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x1800686c0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800686d9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800686d9`
- `RPCRT4!RpcRevertToSelf` at `0x180068700`
- `RPCRT4!RpcRevertToSelf` at `0x180068700`
- `RPCRT4!RpcImpersonateClient` at `0x18006860f`
- `RPCRT4!RpcImpersonateClient` at `0x18006860f`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180068682`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180068682`

## pseudocode

```c
__int64 __fastcall HCEConnectionMgr::GetCallingProcessType(
        HCEConnectionMgr *this,
        enum HCEConnectionMgr::_CallingProcessType *a2)
{
  char v3; // di
  signed int v4; // ebx
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  DWORD AccessMask; // [rsp+40h] [rbp-29h] BYREF
  WINBOOL AccessStatus; // [rsp+44h] [rbp-25h] BYREF
  void *TokenHandle; // [rsp+48h] [rbp-21h] BYREF
  ULONG SecurityDescriptorSize; // [rsp+50h] [rbp-19h] BYREF
  DWORD GrantedAccess; // [rsp+54h] [rbp-15h] BYREF
  DWORD PrivilegeSetLength; // [rsp+58h] [rbp-11h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+60h] [rbp-9h] BYREF
  _GENERIC_MAPPING GenericMapping; // [rsp+68h] [rbp-1h] BYREF
  struct _PRIVILEGE_SET PrivilegeSet; // [rsp+78h] [rbp+Fh] BYREF

  AccessStatus = 0;
  *(_QWORD *)&GenericMapping.GenericExecute = 0;
  memset(&PrivilegeSet, 0, sizeof(PrivilegeSet));
  TokenHandle = 0;
  SecurityDescriptor = 0;
  SecurityDescriptorSize = 0;
  GrantedAccess = 0;
  PrivilegeSetLength = 20;
  AccessMask = 0x80000000;
  *(_QWORD *)&GenericMapping.GenericRead = 0x20000;
  if ( RpcImpersonateClient(0) )
  {
    v3 = 0;
    v4 = -2147024891;
  }
  else
  {
    v3 = 1;
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle)
      && (MapGenericMask(&AccessMask, &GenericMapping),
          ConvertStringSecurityDescriptorToSecurityDescriptorW(
            L"O:SYG:SYD:(A;;RC;;;SY)(A;;RC;;;LS)(A;;RC;;;S-1-5-80-1988685059-1921232356-378231328-2704142597-890457928)",
            1u,
            &SecurityDescriptor,
            &SecurityDescriptorSize))
      && AccessCheck(
           SecurityDescriptor,
           TokenHandle,
           AccessMask,
           &GenericMapping,
           &PrivilegeSet,
           &PrivilegeSetLength,
           &GrantedAccess,
           &AccessStatus) )
    {
      v4 = 0;
    }
    else
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
    }
  }
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    CloseHandle(TokenHandle);
    TokenHandle = 0;
  }
  if ( v3 )
    RpcRevertToSelf();
  if ( v4 >= 0 )
    *(_DWORD *)a2 = (AccessStatus != 0) + 1;
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800685a0  push    rbp
0x1800685a2  push    rbx
0x1800685a3  push    rsi
0x1800685a4  push    rdi
0x1800685a5  lea     rbp, [rsp-3Fh]
0x1800685aa  sub     rsp, 0A8h
0x1800685b1  mov     rax, cs:__security_cookie
0x1800685b8  xor     rax, rsp
0x1800685bb  mov     [rbp+57h+var_30], rax
0x1800685bf  xor     eax, eax
0x1800685c1  mov     [rbp+57h+var_7C], 0
0x1800685c8  xorps   xmm0, xmm0
0x1800685cb  mov     [rbp+57h+var_48.Privilege.Attributes], eax
0x1800685ce  xor     ecx, ecx; BindingHandle
0x1800685d0  mov     qword ptr [rbp+57h+GenericMapping.GenericExecute], rax
0x1800685d4  movups  xmmword ptr [rbp+57h+var_48.PrivilegeCount], xmm0
0x1800685d8  mov     rsi, rdx
0x1800685db  mov     [rbp+57h+TokenHandle], 0
0x1800685e3  mov     [rbp+57h+SecurityDescriptor], 0
0x1800685eb  mov     [rbp+57h+SecurityDescriptorSize], 0
0x1800685f2  mov     [rbp+57h+var_6C], 0
0x1800685f9  mov     [rbp+57h+var_68], 14h
0x180068600  mov     [rbp+57h+AccessMask], 80000000h
0x180068607  mov     qword ptr [rbp+57h+GenericMapping.GenericRead], 20000h
0x18006860f  call    cs:__imp_RpcImpersonateClient
0x180068615  test    eax, eax
0x180068617  jz      short loc_180068626
0x180068619  xor     dil, dil
0x18006861c  mov     ebx, 80070005h
0x180068621  jmp     loc_1800686D0
0x180068626  mov     dil, 1
0x180068629  call    cs:__imp_GetCurrentThread
0x18006862f  mov     edx, 8; DesiredAccess
0x180068634  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x180068638  mov     rcx, rax; ThreadHandle
0x18006863b  lea     r8d, [rdx-7]; OpenAsSelf
0x18006863f  call    cs:__imp_OpenThreadToken
0x180068645  test    eax, eax
0x180068647  jnz     short loc_180068660
0x180068649  call    cs:__imp_GetLastError
0x18006864f  mov     ebx, eax
0x180068651  test    eax, eax
0x180068653  jle     short loc_1800686D0
0x180068655  movzx   ebx, ax
0x180068658  or      ebx, 80070000h
0x18006865e  jmp     short loc_1800686D0
0x180068660  lea     rdx, [rbp+57h+GenericMapping]; GenericMapping
0x180068664  lea     rcx, [rbp+57h+AccessMask]; AccessMask
0x180068668  call    cs:__imp_MapGenericMask
0x18006866e  lea     r9, [rbp+57h+SecurityDescriptorSize]; SecurityDescriptorSize
0x180068672  mov     edx, 1; StringSDRevision
0x180068677  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x18006867b  lea     rcx, aOSygSydARcSyAR; "O:SYG:SYD:(A;;RC;;;SY)(A;;RC;;;LS)(A;;R"...
0x180068682  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180068688  test    eax, eax
0x18006868a  jz      short loc_180068649
0x18006868c  mov     r8d, [rbp+57h+AccessMask]; DesiredAccess
0x180068690  lea     rax, [rbp+57h+var_7C]
0x180068694  mov     rdx, [rbp+57h+TokenHandle]; ClientToken
0x180068698  lea     r9, [rbp+57h+GenericMapping]; GenericMapping
0x18006869c  mov     rcx, [rbp+57h+SecurityDescriptor]; pSecurityDescriptor
0x1800686a0  mov     [rsp+0C0h+AccessStatus], rax; AccessStatus
0x1800686a5  lea     rax, [rbp+57h+var_6C]
0x1800686a9  mov     [rsp+0C0h+GrantedAccess], rax; GrantedAccess
0x1800686ae  lea     rax, [rbp+57h+var_68]
0x1800686b2  mov     [rsp+0C0h+PrivilegeSetLength], rax; PrivilegeSetLength
0x1800686b7  lea     rax, [rbp+57h+var_48]
0x1800686bb  mov     [rsp+0C0h+PrivilegeSet], rax; PrivilegeSet
0x1800686c0  call    cs:__imp_AccessCheck
0x1800686c6  test    eax, eax
0x1800686c8  jz      loc_180068649
0x1800686ce  xor     ebx, ebx
0x1800686d0  mov     rcx, [rbp+57h+SecurityDescriptor]; hMem
0x1800686d4  test    rcx, rcx
0x1800686d7  jz      short loc_1800686DF
0x1800686d9  call    cs:__imp_LocalFree
0x1800686df  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x1800686e3  lea     rax, [rcx-1]
0x1800686e7  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800686eb  ja      short loc_1800686FB
0x1800686ed  call    cs:__imp_CloseHandle
0x1800686f3  mov     [rbp+57h+TokenHandle], 0
0x1800686fb  test    dil, dil
0x1800686fe  jz      short loc_180068706
0x180068700  call    cs:__imp_RpcRevertToSelf
0x180068706  test    ebx, ebx
0x180068708  js      short loc_180068717
0x18006870a  mov     ecx, [rbp+57h+var_7C]
0x18006870d  neg     ecx
0x18006870f  sbb     edx, edx
0x180068711  neg     edx
0x180068713  inc     edx
0x180068715  mov     [rsi], edx
0x180068717  mov     eax, ebx
0x180068719  mov     rcx, [rbp+57h+var_30]
0x18006871d  xor     rcx, rsp; StackCookie
0x180068720  call    __security_check_cookie
0x180068725  add     rsp, 0A8h
0x18006872c  pop     rdi
0x18006872d  pop     rsi
0x18006872e  pop     rbx
0x18006872f  pop     rbp
0x180068730  retn
```
