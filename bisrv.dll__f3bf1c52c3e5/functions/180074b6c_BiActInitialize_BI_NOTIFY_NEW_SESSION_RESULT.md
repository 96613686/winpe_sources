# BiActInitialize(_BI_NOTIFY_NEW_SESSION_RESULT *)

- ea: `0x180074b6c`
- end: `0x18007501a`
- name: `?BiActInitialize@@YAJPEAW4_BI_NOTIFY_NEW_SESSION_RESULT@@@Z`
- size: `1198`
- prototype: `__int64 __fastcall(enum _BI_NOTIFY_NEW_SESSION_RESULT *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18004a39c`

## callees

- `0x18006a69c`
- `0x18006a6ec`
- `0x180070eac`
- `0x180074b6c`
- `0x180075700`
- `0x180095010`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180074fd0`
- `ntdll!RtlFreeHeap` at `0x180074fd0`
- `ntdll!RtlAllocateHeap` at `0x180074c82`
- `ntdll!RtlAllocateHeap` at `0x180074c82`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x180074efb`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x180074efb`
- `api-ms-win-core-com-l1-1-0!CoIncrementMTAUsage` at `0x180074ff1`
- `api-ms-win-core-com-l1-1-0!CoIncrementMTAUsage` at `0x180074ff1`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180074eab`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180074eab`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180075003`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180075003`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180074f3d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180074f3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180074bf4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180074c3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180074bf4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180074c3a`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180074d81`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180074d90`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180074d9f`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180074d81`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180074d90`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180074d9f`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x180074d39`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x180074d39`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180074e88`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180074e88`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180074bea`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180074c30`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180074cdc`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180074d14`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180074bea`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180074c30`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180074cdc`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180074d14`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180074e0a`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180074e35`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180074e60`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180074e0a`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180074e35`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180074e60`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x180074d5e`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x180074d5e`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180074dd5`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x180074dd5`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180074ca3`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180074ca3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180074ba7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180074ba7`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180074bb7`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180074bb7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180074fb3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180074fb3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180074fde`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180074fde`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180074db1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180074db1`

## pseudocode

```c
__int64 __fastcall BiActInitialize(enum _BI_NOTIFY_NEW_SESSION_RESULT *a1)
{
  PSID *v1; // rsi
  struct _ACL *v3; // r14
  char v4; // r12
  HANDLE CurrentProcess; // rax
  int Error; // ebx
  signed int v7; // eax
  signed int LastError; // eax
  __int64 v9; // rbx
  PSID *Heap; // rax
  PSID *v11; // r15
  PSID *v12; // rbx
  DWORD LengthSid; // ebx
  DWORD v14; // ebx
  DWORD v15; // ebx
  struct _ACL *v16; // rax
  ATL::CAtlModule *v17; // rax
  ATL::CAtlModule *v18; // rbx
  ATL::CAtlComModule *v19; // rcx
  LPVOID ppv; // [rsp+50h] [rbp-10h] BYREF
  __int64 v22; // [rsp+58h] [rbp-8h] BYREF
  DWORD TokenInformationLength; // [rsp+A8h] [rbp+48h] BYREF
  DWORD ReturnLength; // [rsp+B0h] [rbp+50h] BYREF
  void *TokenHandle; // [rsp+B8h] [rbp+58h] BYREF

  v1 = 0;
  TokenHandle = 0;
  v22 = 0;
  ppv = 0;
  v3 = 0;
  TokenInformationLength = 0;
  v4 = 0;
  ReturnLength = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
  {
    Error = ResultFromKnownLastError();
    *(_DWORD *)a1 = 769;
    goto LABEL_48;
  }
  if ( GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength)
    || (v7 = GetLastError(), Error = v7, v7 == 122) )
  {
    if ( GetTokenInformation(TokenHandle, TokenPrimaryGroup, 0, 0, &ReturnLength)
      || (LastError = GetLastError(), Error = LastError, LastError == 122) )
    {
      v9 = (TokenInformationLength + 7) & 0xFFFFFFF8;
      Heap = (PSID *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, (unsigned int)v9 + ReturnLength + 40);
      v1 = Heap;
      if ( Heap )
      {
        if ( !InitializeSecurityDescriptor(Heap, 1u) )
        {
          Error = ResultFromKnownLastError();
          *(_DWORD *)a1 = 773;
          goto LABEL_48;
        }
        v11 = v1 + 5;
        if ( !GetTokenInformation(TokenHandle, TokenUser, v1 + 5, TokenInformationLength, &TokenInformationLength) )
        {
          Error = ResultFromKnownLastError();
          *(_DWORD *)a1 = 774;
          goto LABEL_48;
        }
        v12 = (PSID *)((char *)v11 + v9);
        if ( !GetTokenInformation(TokenHandle, TokenPrimaryGroup, v12, ReturnLength, &ReturnLength) )
        {
          Error = ResultFromKnownLastError();
          *(_DWORD *)a1 = 775;
          goto LABEL_48;
        }
        if ( !SetSecurityDescriptorOwner(v1, *v11, 0) )
        {
          Error = ResultFromKnownLastError();
          *(_DWORD *)a1 = 776;
          goto LABEL_48;
        }
        if ( !SetSecurityDescriptorGroup(v1, *v12, 0) )
        {
          Error = ResultFromKnownLastError();
          *(_DWORD *)a1 = 777;
          goto LABEL_48;
        }
        LengthSid = GetLengthSid(qword_1800A4CB0);
        v14 = GetLengthSid(qword_1800A4CC0) + LengthSid;
        v15 = GetLengthSid(qword_1800A4C90) + 32 + v14;
        v16 = (struct _ACL *)LocalAlloc(0x40u, v15);
        v3 = v16;
        if ( v16 )
        {
          if ( !InitializeAcl(v16, v15, 2u) )
          {
            Error = ResultFromKnownLastError();
            *(_DWORD *)a1 = 779;
            goto LABEL_48;
          }
          if ( !AddAccessAllowedAce(v3, 2u, 1u, qword_1800A4CB0) )
          {
            Error = ResultFromKnownLastError();
            *(_DWORD *)a1 = 780;
            goto LABEL_48;
          }
          if ( !AddAccessAllowedAce(v3, 2u, 1u, qword_1800A4CC0) )
          {
            Error = ResultFromKnownLastError();
            *(_DWORD *)a1 = 781;
            goto LABEL_48;
          }
          if ( !AddAccessAllowedAce(v3, 2u, 1u, qword_1800A4C90) )
          {
            Error = ResultFromKnownLastError();
            *(_DWORD *)a1 = 782;
            goto LABEL_48;
          }
          if ( !SetSecurityDescriptorDacl(v1, 1, v3, 0) )
          {
            Error = ResultFromKnownLastError();
            *(_DWORD *)a1 = 783;
            goto LABEL_48;
          }
          Error = CoInitializeEx(0, 4u);
          if ( Error < 0 )
          {
            *(_DWORD *)a1 = 784;
            goto LABEL_48;
          }
          v4 = 1;
          Error = CoInitializeSecurity(v1, -1, 0, 0, 4u, 2u, 0, 0x3000u, 0);
          if ( (int)(Error + 0x80000000) >= 0 && Error != -2147417831 )
          {
            *(_DWORD *)a1 = 785;
            goto LABEL_48;
          }
          if ( CoCreateInstance(&CLSID_GlobalOptions, 0, 1u, &GUID_0000015b_0000_0000_c000_000000000046, &ppv) >= 0 )
          {
            (*(void (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)ppv + 24LL))(ppv, 5, 1);
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
          }
          v17 = (ATL::CAtlModule *)operator new(0x48u);
          v18 = v17;
          if ( v17 )
          {
            ATL::CAtlModule::CAtlModule(v17);
            *(_QWORD *)v18 = &CActAtlModule::`vftable';
            ATL::CAtlComModule::ExecuteObjectMain(v19, 1);
            Error = 0;
            goto LABEL_48;
          }
          *(_DWORD *)a1 = 786;
        }
        else
        {
          *(_DWORD *)a1 = 778;
        }
      }
      else
      {
        *(_DWORD *)a1 = 772;
      }
      Error = -2147024882;
    }
    else
    {
      if ( LastError > 0 )
        Error = (unsigned __int16)LastError | 0x80070000;
      *(_DWORD *)a1 = 771;
    }
  }
  else
  {
    if ( v7 > 0 )
      Error = (unsigned __int16)v7 | 0x80070000;
    *(_DWORD *)a1 = 770;
  }
LABEL_48:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( v1 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v1);
  if ( v3 )
    LocalFree(v3);
  if ( v4 )
  {
    if ( Error >= 0 )
    {
      Error = CoIncrementMTAUsage(&v22);
      if ( Error < 0 )
        *(_DWORD *)a1 = 787;
    }
    CoUninitialize();
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180074b6c  push    rbp
0x180074b6e  push    rbx
0x180074b6f  push    rsi
0x180074b70  push    rdi
0x180074b71  push    r12
0x180074b73  push    r14
0x180074b75  push    r15
0x180074b77  mov     rbp, rsp
0x180074b7a  sub     rsp, 60h
0x180074b7e  xor     esi, esi
0x180074b80  mov     [rbp+TokenHandle], 0
0x180074b88  mov     [rbp+var_8], rsi
0x180074b8c  mov     rdi, rcx
0x180074b8f  mov     [rbp+ppv], rsi
0x180074b93  xor     r14d, r14d
0x180074b96  mov     [rbp+TokenInformationLength], 0
0x180074b9d  xor     r12b, r12b
0x180074ba0  mov     [rbp+arg_10], 0
0x180074ba7  call    cs:__imp_GetCurrentProcess
0x180074bad  mov     rcx, rax; ProcessHandle
0x180074bb0  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180074bb4  lea     edx, [rsi+8]; DesiredAccess
0x180074bb7  call    cs:__imp_OpenProcessToken
0x180074bbd  test    eax, eax
0x180074bbf  jnz     short loc_180074BD3
0x180074bc1  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180074bc6  mov     ebx, eax
0x180074bc8  mov     dword ptr [rdi], 301h
0x180074bce  jmp     loc_180074FAA
0x180074bd3  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180074bd7  lea     rax, [rbp+TokenInformationLength]
0x180074bdb  xor     r9d, r9d; TokenInformationLength
0x180074bde  mov     [rsp+60h+ReturnLength], rax; ReturnLength
0x180074be3  xor     r8d, r8d; TokenInformation
0x180074be6  lea     edx, [r9+1]; TokenInformationClass
0x180074bea  call    cs:__imp_GetTokenInformation
0x180074bf0  test    eax, eax
0x180074bf2  jnz     short loc_180074C19
0x180074bf4  call    cs:__imp_GetLastError
0x180074bfa  mov     ebx, eax
0x180074bfc  cmp     eax, 7Ah ; 'z'
0x180074bff  jz      short loc_180074C19
0x180074c01  test    eax, eax
0x180074c03  jle     short loc_180074C0E
0x180074c05  movzx   ebx, ax
0x180074c08  or      ebx, 80070000h
0x180074c0e  mov     dword ptr [rdi], 302h
0x180074c14  jmp     loc_180074FAA
0x180074c19  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180074c1d  lea     rax, [rbp+arg_10]
0x180074c21  xor     r9d, r9d; TokenInformationLength
0x180074c24  mov     [rsp+60h+ReturnLength], rax; ReturnLength
0x180074c29  xor     r8d, r8d; TokenInformation
0x180074c2c  lea     edx, [r9+5]; TokenInformationClass
0x180074c30  call    cs:__imp_GetTokenInformation
0x180074c36  test    eax, eax
0x180074c38  jnz     short loc_180074C5F
0x180074c3a  call    cs:__imp_GetLastError
0x180074c40  mov     ebx, eax
0x180074c42  cmp     eax, 7Ah ; 'z'
0x180074c45  jz      short loc_180074C5F
0x180074c47  test    eax, eax
0x180074c49  jle     short loc_180074C54
0x180074c4b  movzx   ebx, ax
0x180074c4e  or      ebx, 80070000h
0x180074c54  mov     dword ptr [rdi], 303h
0x180074c5a  jmp     loc_180074FAA
0x180074c5f  mov     ebx, [rbp+TokenInformationLength]
0x180074c62  xor     edx, edx; Flags
0x180074c64  mov     rcx, gs:60h
0x180074c6d  add     ebx, 7
0x180074c70  mov     r8d, [rbp+arg_10]
0x180074c74  and     ebx, 0FFFFFFF8h
0x180074c77  add     r8d, 28h ; '('
0x180074c7b  add     r8d, ebx; Size
0x180074c7e  mov     rcx, [rcx+30h]; HeapHandle
0x180074c82  call    cs:__imp_RtlAllocateHeap
0x180074c88  mov     rsi, rax
0x180074c8b  test    rax, rax
0x180074c8e  jnz     short loc_180074C9B
0x180074c90  mov     dword ptr [rdi], 304h
0x180074c96  jmp     loc_180074FA5
0x180074c9b  mov     edx, 1; dwRevision
0x180074ca0  mov     rcx, rsi; pSecurityDescriptor
0x180074ca3  call    cs:__imp_InitializeSecurityDescriptor
0x180074ca9  test    eax, eax
0x180074cab  jnz     short loc_180074CBF
0x180074cad  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180074cb2  mov     ebx, eax
0x180074cb4  mov     dword ptr [rdi], 305h
0x180074cba  jmp     loc_180074FAA
0x180074cbf  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x180074cc3  lea     rax, [rbp+TokenInformationLength]
0x180074cc7  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180074ccb  lea     r15, [rsi+28h]
0x180074ccf  mov     r8, r15; TokenInformation
0x180074cd2  mov     [rsp+60h+ReturnLength], rax; ReturnLength
0x180074cd7  mov     edx, 1; TokenInformationClass
0x180074cdc  call    cs:__imp_GetTokenInformation
0x180074ce2  test    eax, eax
0x180074ce4  jnz     short loc_180074CF8
0x180074ce6  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180074ceb  mov     ebx, eax
0x180074ced  mov     dword ptr [rdi], 306h
0x180074cf3  jmp     loc_180074FAA
0x180074cf8  mov     r9d, [rbp+arg_10]; TokenInformationLength
0x180074cfc  lea     rax, [rbp+arg_10]
0x180074d00  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180074d04  add     rbx, r15
0x180074d07  mov     r8, rbx; TokenInformation
0x180074d0a  mov     [rsp+60h+ReturnLength], rax; ReturnLength
0x180074d0f  mov     edx, 5; TokenInformationClass
0x180074d14  call    cs:__imp_GetTokenInformation
0x180074d1a  test    eax, eax
0x180074d1c  jnz     short loc_180074D30
0x180074d1e  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180074d23  mov     ebx, eax
0x180074d25  mov     dword ptr [rdi], 307h
0x180074d2b  jmp     loc_180074FAA
0x180074d30  mov     rdx, [r15]; pOwner
0x180074d33  xor     r8d, r8d; bOwnerDefaulted
0x180074d36  mov     rcx, rsi; pSecurityDescriptor
0x180074d39  call    cs:__imp_SetSecurityDescriptorOwner
0x180074d3f  test    eax, eax
0x180074d41  jnz     short loc_180074D55
0x180074d43  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180074d48  mov     ebx, eax
0x180074d4a  mov     dword ptr [rdi], 308h
0x180074d50  jmp     loc_180074FAA
0x180074d55  mov     rdx, [rbx]; pGroup
0x180074d58  xor     r8d, r8d; bGroupDefaulted
0x180074d5b  mov     rcx, rsi; pSecurityDescriptor
0x180074d5e  call    cs:__imp_SetSecurityDescriptorGroup
0x180074d64  test    eax, eax
0x180074d66  jnz     short loc_180074D7A
0x180074d68  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180074d6d  mov     ebx, eax
0x180074d6f  mov     dword ptr [rdi], 309h
0x180074d75  jmp     loc_180074FAA
0x180074d7a  lea     rcx, qword_1800A4CB0; pSid
0x180074d81  call    cs:__imp_GetLengthSid
0x180074d87  lea     rcx, qword_1800A4CC0; pSid
0x180074d8e  mov     ebx, eax
0x180074d90  call    cs:__imp_GetLengthSid
0x180074d96  lea     rcx, qword_1800A4C90; pSid
0x180074d9d  add     ebx, eax
0x180074d9f  call    cs:__imp_GetLengthSid
0x180074da5  add     eax, 20h ; ' '
0x180074da8  mov     ecx, 40h ; '@'; uFlags
0x180074dad  add     ebx, eax
0x180074daf  mov     edx, ebx; uBytes
0x180074db1  call    cs:__imp_LocalAlloc
0x180074db7  mov     r14, rax
0x180074dba  test    rax, rax
0x180074dbd  jnz     short loc_180074DCA
0x180074dbf  mov     dword ptr [rdi], 30Ah
0x180074dc5  jmp     loc_180074FA5
0x180074dca  mov     r8d, 2; dwAclRevision
0x180074dd0  mov     edx, ebx; nAclLength
0x180074dd2  mov     rcx, r14; pAcl
0x180074dd5  call    cs:__imp_InitializeAcl
0x180074ddb  test    eax, eax
0x180074ddd  jnz     short loc_180074DF1
0x180074ddf  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180074de4  mov     ebx, eax
0x180074de6  mov     dword ptr [rdi], 30Bh
0x180074dec  jmp     loc_180074FAA
0x180074df1  mov     r15d, 1
0x180074df7  lea     r9, qword_1800A4CB0; pSid
0x180074dfe  mov     r8d, r15d; AccessMask
0x180074e01  mov     rcx, r14; pAcl
0x180074e04  lea     ebx, [r15+1]
0x180074e08  mov     edx, ebx; dwAceRevision
0x180074e0a  call    cs:__imp_AddAccessAllowedAce
0x180074e10  test    eax, eax
0x180074e12  jnz     short loc_180074E26
0x180074e14  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180074e19  mov     ebx, eax
0x180074e1b  mov     dword ptr [rdi], 30Ch
0x180074e21  jmp     loc_180074FAA
0x180074e26  lea     r9, qword_1800A4CC0; pSid
0x180074e2d  mov     r8d, r15d; AccessMask
0x180074e30  mov     edx, ebx; dwAceRevision
0x180074e32  mov     rcx, r14; pAcl
0x180074e35  call    cs:__imp_AddAccessAllowedAce
0x180074e3b  test    eax, eax
0x180074e3d  jnz     short loc_180074E51
0x180074e3f  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180074e44  mov     ebx, eax
0x180074e46  mov     dword ptr [rdi], 30Dh
0x180074e4c  jmp     loc_180074FAA
0x180074e51  lea     r9, qword_1800A4C90; pSid
0x180074e58  mov     r8d, r15d; AccessMask
0x180074e5b  mov     edx, ebx; dwAceRevision
0x180074e5d  mov     rcx, r14; pAcl
0x180074e60  call    cs:__imp_AddAccessAllowedAce
0x180074e66  test    eax, eax
0x180074e68  jnz     short loc_180074E7C
0x180074e6a  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180074e6f  mov     ebx, eax
0x180074e71  mov     dword ptr [rdi], 30Eh
0x180074e77  jmp     loc_180074FAA
0x180074e7c  xor     r9d, r9d; bDaclDefaulted
0x180074e7f  mov     r8, r14; pDacl
0x180074e82  mov     edx, r15d; bDaclPresent
0x180074e85  mov     rcx, rsi; pSecurityDescriptor
0x180074e88  call    cs:__imp_SetSecurityDescriptorDacl
0x180074e8e  test    eax, eax
0x180074e90  jnz     short loc_180074EA4
0x180074e92  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180074e97  mov     ebx, eax
0x180074e99  mov     dword ptr [rdi], 30Fh
0x180074e9f  jmp     loc_180074FAA
0x180074ea4  mov     edx, 4; dwCoInit
0x180074ea9  xor     ecx, ecx; pvReserved
0x180074eab  call    cs:__imp_CoInitializeEx
0x180074eb1  mov     ebx, eax
0x180074eb3  test    eax, eax
0x180074eb5  jns     short loc_180074EC2
0x180074eb7  mov     dword ptr [rdi], 310h
0x180074ebd  jmp     loc_180074FAA
0x180074ec2  mov     [rsp+60h+pReserved3], 0; pReserved3
0x180074ecb  xor     r9d, r9d; pReserved1
0x180074ece  mov     [rsp+60h+dwCapabilities], 3000h; dwCapabilities
0x180074ed6  xor     r8d, r8d; asAuthSvc
0x180074ed9  mov     [rsp+60h+pAuthList], 0; pAuthList
0x180074ee2  or      edx, 0FFFFFFFFh; cAuthSvc
0x180074ee5  mov     [rsp+60h+dwImpLevel], 2; dwImpLevel
0x180074eed  mov     rcx, rsi; pSecDesc
0x180074ef0  mov     dword ptr [rsp+60h+ReturnLength], 4; dwAuthnLevel
0x180074ef8  mov     r12b, r15b
0x180074efb  call    cs:__imp_CoInitializeSecurity
0x180074f01  mov     ecx, 80000000h
0x180074f06  mov     ebx, eax
0x180074f08  add     eax, ecx
0x180074f0a  test    ecx, eax
0x180074f0c  jnz     short loc_180074F21
0x180074f0e  cmp     ebx, 80010119h
0x180074f14  jz      short loc_180074F21
0x180074f16  mov     dword ptr [rdi], 311h
0x180074f1c  jmp     loc_180074FAA
0x180074f21  lea     rax, [rbp+ppv]
0x180074f25  mov     r8d, r15d; dwClsContext
0x180074f28  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x180074f2f  mov     [rsp+60h+ReturnLength], rax; ppv
0x180074f34  xor     edx, edx; pUnkOuter
0x180074f36  lea     rcx, CLSID_GlobalOptions; rclsid
0x180074f3d  call    cs:__imp_CoCreateInstance
0x180074f43  test    eax, eax
0x180074f45  js      short loc_180074F6F
0x180074f47  mov     rcx, [rbp+ppv]
0x180074f4b  mov     r8, r15
0x180074f4e  mov     edx, 5
0x180074f53  mov     rax, [rcx]
0x180074f56  mov     rax, [rax+18h]
0x180074f5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074f5f  mov     rcx, [rbp+ppv]
0x180074f63  mov     rax, [rcx]
0x180074f66  mov     rax, [rax+10h]
0x180074f6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180074f6f  mov     ecx, 48h ; 'H'; Size
0x180074f74  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180074f79  mov     rbx, rax
0x180074f7c  test    rax, rax
0x180074f7f  jz      short loc_180074F9F
0x180074f81  mov     rcx, rax; this
0x180074f84  call    ??0CAtlModule@ATL@@QEAA@XZ; ATL::CAtlModule::CAtlModule(void)
0x180074f89  lea     rax, ??_7CActAtlModule@@6B@; const CActAtlModule::`vftable'
0x180074f90  mov     dl, r15b; bool
0x180074f93  mov     [rbx], rax
0x180074f96  call    ?ExecuteObjectMain@CAtlComModule@ATL@@QEAAX_N@Z; ATL::CAtlComModule::ExecuteObjectMain(bool)
0x180074f9b  xor     ebx, ebx
0x180074f9d  jmp     short loc_180074FAA
0x180074f9f  mov     dword ptr [rdi], 312h
0x180074fa5  mov     ebx, 8007000Eh
0x180074faa  mov     rcx, [rbp+TokenHandle]; hObject
0x180074fae  test    rcx, rcx
0x180074fb1  jz      short loc_180074FB9
0x180074fb3  call    cs:__imp_CloseHandle
0x180074fb9  test    rsi, rsi
0x180074fbc  jz      short loc_180074FD6
0x180074fbe  mov     rcx, gs:60h
0x180074fc7  mov     r8, rsi; P
0x180074fca  xor     edx, edx; Flags
0x180074fcc  mov     rcx, [rcx+30h]; HeapHandle
0x180074fd0  call    cs:__imp_RtlFreeHeap
0x180074fd6  test    r14, r14
0x180074fd9  jz      short loc_180074FE4
0x180074fdb  mov     rcx, r14; hMem
0x180074fde  call    cs:__imp_LocalFree
0x180074fe4  test    r12b, r12b
0x180074fe7  jz      short loc_180075009
0x180074fe9  test    ebx, ebx
0x180074feb  js      short loc_180075003
0x180074fed  lea     rcx, [rbp+var_8]
0x180074ff1  call    cs:__imp_CoIncrementMTAUsage
0x180074ff7  mov     ebx, eax
0x180074ff9  test    eax, eax
0x180074ffb  jns     short loc_180075003
0x180074ffd  mov     dword ptr [rdi], 313h
  ... truncated ...
```
