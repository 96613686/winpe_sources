# AhcApiInitProcessData

- ea: `0x14002b268`
- end: `0x14002b84a`
- name: `AhcApiInitProcessData`
- size: `1506`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400497bc`

## callees

- `0x1400079f0`
- `0x14002737c`
- `0x14002b268`
- `0x14003e364`

## import_xrefs

- `ntoskrnl!SeExports` at `0x14002b308`
- `ntoskrnl!SeExports` at `0x14002b46c`
- `ntoskrnl!RtlEqualSid` at `0x14002b485`
- `ntoskrnl!RtlEqualSid` at `0x14002b485`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14002b515`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14002b515`
- `ntoskrnl!ObfDereferenceObject` at `0x14002b7e2`
- `ntoskrnl!ObfDereferenceObject` at `0x14002b7e2`
- `ntoskrnl!ProbeForRead` at `0x14002b37c`
- `ntoskrnl!ProbeForRead` at `0x14002b5a8`
- `ntoskrnl!ProbeForRead` at `0x14002b37c`
- `ntoskrnl!ProbeForRead` at `0x14002b5a8`
- `ntoskrnl!PsProcessType` at `0x14002b502`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14002b649`
- `ntoskrnl!ObOpenObjectByPointer` at `0x14002b649`
- `ntoskrnl!ZwClose` at `0x14002b7f8`
- `ntoskrnl!ZwClose` at `0x14002b80e`
- `ntoskrnl!ZwClose` at `0x14002b7f8`
- `ntoskrnl!ZwClose` at `0x14002b80e`
- `ntoskrnl!PsGetCurrentProcess` at `0x14002b3fe`
- `ntoskrnl!PsGetCurrentProcess` at `0x14002b3fe`
- `ntoskrnl!ZwOpenProcessToken` at `0x14002b423`
- `ntoskrnl!ZwOpenProcessToken` at `0x14002b423`
- `ntoskrnl!ZwQueryInformationToken` at `0x14002b45c`
- `ntoskrnl!ZwQueryInformationToken` at `0x14002b45c`
- `ntoskrnl!SeCaptureSubjectContextEx` at `0x14002b4a2`
- `ntoskrnl!SeCaptureSubjectContextEx` at `0x14002b4a2`
- `ntoskrnl!SePrivilegeCheck` at `0x14002b4c1`
- `ntoskrnl!SePrivilegeCheck` at `0x14002b4c1`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14002b4d7`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14002b4d7`
- `ntoskrnl!KeStackAttachProcess` at `0x14002b540`
- `ntoskrnl!KeStackAttachProcess` at `0x14002b540`
- `ntoskrnl!PsGetProcessPeb` at `0x14002b554`
- `ntoskrnl!PsGetProcessPeb` at `0x14002b554`
- `ntoskrnl!PsGetProcessProtection` at `0x14002b5b7`
- `ntoskrnl!PsGetProcessProtection` at `0x14002b5b7`
- `ntoskrnl!PsGetProcessWow64Process` at `0x14002b603`
- `ntoskrnl!PsGetProcessWow64Process` at `0x14002b603`
- `ntoskrnl!ZwAllocateVirtualMemory` at `0x14002b686`
- `ntoskrnl!ZwAllocateVirtualMemory` at `0x14002b686`
- `ntoskrnl!MmCopyVirtualMemory` at `0x14002b6cf`
- `ntoskrnl!MmCopyVirtualMemory` at `0x14002b6cf`
- `ntoskrnl!KeUnstackDetachProcess` at `0x14002b7a2`
- `ntoskrnl!KeUnstackDetachProcess` at `0x14002b7a2`
- `ntoskrnl!ZwFreeVirtualMemory` at `0x14002b7ce`
- `ntoskrnl!ZwFreeVirtualMemory` at `0x14002b7ce`

## string_xrefs

- `0x14002b6e5`: `Error copying memory [%x]`
- `0x14002b3d7`: `Cannot read user data [%x]`

## pseudocode

```c
__int64 __fastcall AhcApiInitProcessData(__int64 a1)
{
  PVOID v2; // rsi
  __int64 v3; // r15
  ULONG_PTR v4; // r14
  NTSTATUS v5; // ebx
  struct _KPROCESS *CurrentProcess; // rbx
  BOOLEAN v7; // bl
  __int64 ProcessPeb; // rax
  __int64 v9; // r12
  __int64 ULong64FromUser; // rbx
  signed __int32 v11; // eax
  signed __int32 v12; // ett
  __int64 ProcessWow64Process; // r13
  int v14; // eax
  int HandleInformation; // [rsp+28h] [rbp-260h]
  ULONG TokenInformationLength; // [rsp+44h] [rbp-244h] BYREF
  PVOID BaseAddress; // [rsp+48h] [rbp-240h] BYREF
  int v19; // [rsp+50h] [rbp-238h]
  PVOID v20; // [rsp+58h] [rbp-230h]
  ULONG_PTR RegionSize; // [rsp+60h] [rbp-228h] BYREF
  HANDLE ProcessHandle; // [rsp+68h] [rbp-220h] BYREF
  void *TokenHandle; // [rsp+70h] [rbp-218h] BYREF
  PVOID Object; // [rsp+78h] [rbp-210h] BYREF
  __int64 v25; // [rsp+80h] [rbp-208h] BYREF
  struct _KPROCESS *v26; // [rsp+88h] [rbp-200h]
  _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+90h] [rbp-1F8h] BYREF
  _PRIVILEGE_SET RequiredPrivileges; // [rsp+B0h] [rbp-1D8h] BYREF
  _KAPC_STATE ApcState; // [rsp+C8h] [rbp-1C0h] BYREF
  PSID TokenInformation[42]; // [rsp+100h] [rbp-188h] BYREF

  memset(&ApcState, 0, sizeof(ApcState));
  RequiredPrivileges.Privilege[0].Luid = 0;
  RequiredPrivileges.Privilege[0].Attributes = 0;
  memset(&SubjectContext, 0, sizeof(SubjectContext));
  TokenInformationLength = 0;
  ProcessHandle = 0;
  BaseAddress = 0;
  RegionSize = 0;
  v25 = 0;
  v19 = 0;
  TokenHandle = 0;
  RequiredPrivileges.PrivilegeCount = 1;
  RequiredPrivileges.Control = 1;
  RequiredPrivileges.Privilege[0].Luid = SeExports->SeTcbPrivilege;
  RequiredPrivileges.Privilege[0].Attributes = 0;
  memset(&SubjectContext, 0, sizeof(SubjectContext));
  TokenInformationLength = 336;
  v2 = 0;
  if ( !*(_QWORD *)a1 )
    goto LABEL_34;
  v3 = *(_QWORD *)(a1 + 8);
  v4 = *(unsigned int *)(a1 + 16);
  if ( !v3 )
    goto LABEL_7;
  if ( v4 < 0x11D8 )
  {
LABEL_34:
    v5 = -1073741811;
    goto LABEL_35;
  }
  ProbeForRead(*(volatile void **)(a1 + 8), (unsigned int)v4, 4u);
  if ( *(_DWORD *)(v3 + 524) != -1408373333 || *(_DWORD *)(v3 + 520) != 4568 )
  {
    v5 = -1073741811;
    AslLogCallPrintf(1, "AhcApiInitProcessData", 1181, "Invalid user exe data");
    goto LABEL_35;
  }
LABEL_7:
  CurrentProcess = (struct _KPROCESS *)PsGetCurrentProcess();
  v26 = CurrentProcess;
  if ( ZwOpenProcessToken((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0x20008u, &TokenHandle) < 0
    || ZwQueryInformationToken(
         TokenHandle,
         TokenUser,
         TokenInformation,
         TokenInformationLength,
         &TokenInformationLength) < 0
    || !RtlEqualSid(TokenInformation[0], SeExports->SeLocalSystemSid)
    || (SeCaptureSubjectContextEx(0, CurrentProcess, &SubjectContext),
        v7 = SePrivilegeCheck(&RequiredPrivileges, &SubjectContext, 1),
        SeReleaseSubjectContext(&SubjectContext),
        !v7) )
  {
    v5 = -1073741790;
    goto LABEL_35;
  }
  Object = 0;
  v5 = ObReferenceObjectByHandle(*(HANDLE *)a1, 0x438u, (POBJECT_TYPE)PsProcessType, 0, &Object, 0);
  v2 = Object;
  v20 = Object;
  if ( v5 >= 0 )
  {
    KeStackAttachProcess((PRKPROCESS)Object, &ApcState);
    v19 = 1;
    ProcessPeb = PsGetProcessPeb(v2);
    v9 = ProcessPeb;
    if ( !ProcessPeb )
    {
      v5 = -1073741811;
      AslLogCallPrintf(1, "AhcApiInitProcessData", 1255, "Invalid process peb");
      goto LABEL_35;
    }
    ULong64FromUser = RtlReadULong64FromUser(ProcessPeb + 32);
    ProbeForRead((volatile void *)ULong64FromUser, 0x450u, 4u);
    if ( (unsigned __int8)PsGetProcessProtection(v2) == 0x81 && (*(_BYTE *)(v9 + 3) & 0x10) != 0 )
    {
      _m_prefetchw((const void *)(ULong64FromUser + 8));
      v11 = *(_DWORD *)(ULong64FromUser + 8);
      do
      {
        v12 = v11;
        v11 = _InterlockedCompareExchange((volatile signed __int32 *)(ULong64FromUser + 8), v11 | 0x10000000, v11);
      }
      while ( v12 != v11 );
      if ( (v11 & 0x10000000) != 0 )
      {
        v5 = -1073741790;
        goto LABEL_35;
      }
      ProcessWow64Process = PsGetProcessWow64Process(v2, 0x10000000);
      if ( v3 && v4 )
      {
        v5 = ObOpenObjectByPointer(v2, 0x200u, 0, 0x438u, 0, 0, &ProcessHandle);
        if ( v5 < 0 )
          goto LABEL_35;
        RegionSize = v4;
        if ( ZwAllocateVirtualMemory(ProcessHandle, &BaseAddress, 0, &RegionSize, 0x1000u, 4u) < 0 || RegionSize < v4 )
        {
          v5 = -1073741801;
          AslLogCallPrintf(1, "AhcApiInitProcessData", 1329, "Out of memory");
          goto LABEL_35;
        }
        LOBYTE(HandleInformation) = 0;
        v14 = MmCopyVirtualMemory(v26, v3, v2, BaseAddress, v4, HandleInformation, &v25);
        v5 = v14;
        if ( v14 < 0 )
        {
          AslLogCallPrintf(1, "AhcApiInitProcessData", 1346, "Error copying memory [%x]", v14);
          goto LABEL_35;
        }
        *(_QWORD *)(v9 + 728) = BaseAddress;
        if ( ProcessWow64Process )
          *(_DWORD *)(ProcessWow64Process + 488) = (_DWORD)BaseAddress;
      }
      v5 = 0;
    }
    else
    {
      v5 = -1073741790;
    }
  }
LABEL_35:
  if ( v19 )
    KeUnstackDetachProcess(&ApcState);
  if ( v5 < 0 && BaseAddress )
    ZwFreeVirtualMemory(ProcessHandle, &BaseAddress, &RegionSize, 0x8000u);
  if ( v2 )
    ObfDereferenceObject(v2);
  if ( ProcessHandle )
    ZwClose(ProcessHandle);
  if ( TokenHandle )
    ZwClose(TokenHandle);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x14002b268  mov     r11, rsp
0x14002b26b  mov     [r11+10h], rbx
0x14002b26f  mov     [r11+18h], rsi
0x14002b273  push    rdi
0x14002b274  push    r12
0x14002b276  push    r13
0x14002b278  push    r14
0x14002b27a  push    r15
0x14002b27c  sub     rsp, 260h
0x14002b283  mov     rax, cs:__security_cookie
0x14002b28a  xor     rax, rsp
0x14002b28d  mov     [rsp+288h+var_38], rax
0x14002b295  mov     r12, rcx
0x14002b298  xorps   xmm0, xmm0
0x14002b29b  movups  xmmword ptr [rsp+288h+ApcState.ApcListHead.Flink], xmm0
0x14002b2a3  movups  xmmword ptr [rsp+288h+ApcState.ApcListHead.Flink+10h], xmm0
0x14002b2ab  movups  xmmword ptr [rsp+288h+ApcState.Process], xmm0
0x14002b2b3  xor     edi, edi
0x14002b2b5  mov     [r11-1D0h], rdi
0x14002b2bc  mov     [rsp+288h+RequiredPrivileges.Privilege.Attributes], edi
0x14002b2c3  movups  xmmword ptr [rsp+288h+SubjectContext.ClientToken], xmm0
0x14002b2cb  movups  xmmword ptr [rsp+288h+SubjectContext.PrimaryToken], xmm0
0x14002b2d3  mov     [rsp+288h+TokenInformationLength], edi
0x14002b2d7  mov     [rsp+288h+ProcessHandle], rdi
0x14002b2dc  mov     [rsp+288h+BaseAddress], rdi
0x14002b2e1  mov     [rsp+288h+RegionSize], rdi
0x14002b2e6  mov     [r11-208h], rdi
0x14002b2ed  mov     [rsp+288h+var_238], edi
0x14002b2f1  mov     [rsp+288h+TokenHandle], rdi
0x14002b2f6  lea     r13d, [rdi+1]
0x14002b2fa  mov     [r11-1D8h], r13d
0x14002b301  mov     [r11-1D4h], r13d
0x14002b308  mov     rax, cs:__imp_SeExports
0x14002b30f  mov     rcx, [rax]
0x14002b312  mov     rax, [rcx+28h]
0x14002b316  mov     [r11-1D0h], rax
0x14002b31d  mov     [rsp+288h+RequiredPrivileges.Privilege.Attributes], edi
0x14002b324  movups  xmmword ptr [rsp+288h+SubjectContext.ClientToken], xmm0
0x14002b32c  movups  xmmword ptr [rsp+288h+SubjectContext.PrimaryToken], xmm0
0x14002b334  mov     [rsp+288h+TokenInformationLength], 150h
0x14002b33c  mov     esi, edi
0x14002b33e  cmp     [r12], rdi
0x14002b342  jz      loc_14002B78F
0x14002b348  mov     r15, [r12+8]
0x14002b34d  mov     r14d, [r12+10h]
0x14002b352  mov     ebx, 11D8h
0x14002b357  test    r15, r15
0x14002b35a  jz      loc_14002B3FE
0x14002b360  cmp     r14, rbx
0x14002b363  jb      loc_14002B78F
0x14002b369  test    r15, r15
0x14002b36c  jz      loc_14002B3FE
0x14002b372  lea     r8d, [rdi+4]; Alignment
0x14002b376  mov     edx, r14d; Length
0x14002b379  mov     rcx, r15; Address
0x14002b37c  call    cs:__imp_ProbeForRead
0x14002b383  nop     dword ptr [rax+rax+00h]
0x14002b388  cmp     dword ptr [r15+20Ch], 0AC0DEDABh
0x14002b393  jnz     short loc_14002B3A3
0x14002b395  cmp     [r15+208h], ebx
0x14002b39c  jnz     short loc_14002B3A3
0x14002b39e  cmp     r14, rbx
0x14002b3a1  jnb     short loc_14002B3FE
0x14002b3a3  mov     ebx, 0C000000Dh
0x14002b3a8  mov     [rsp+288h+var_248], ebx
0x14002b3ac  lea     r9, aInvalidUserExe; "Invalid user exe data"
0x14002b3b3  mov     r8d, 49Dh
0x14002b3b9  lea     rdx, aAhcapiinitproc; "AhcApiInitProcessData"
0x14002b3c0  mov     ecx, r13d
0x14002b3c3  call    AslLogCallPrintf
0x14002b3c8  jmp     loc_14002B794
0x14002b3cd  mov     ebx, eax
0x14002b3cf  mov     [rsp+288h+var_248], eax
0x14002b3d3  mov     dword ptr [rsp+288h+ReturnLength], eax
0x14002b3d7  lea     r9, aCannotReadUser; "Cannot read user data [%x]"
0x14002b3de  mov     r8d, 4A2h
0x14002b3e4  lea     rdx, aAhcapiinitproc; "AhcApiInitProcessData"
0x14002b3eb  mov     ecx, 1
0x14002b3f0  call    AslLogCallPrintf
0x14002b3f5  xor     edi, edi
0x14002b3f7  mov     esi, edi
0x14002b3f9  jmp     loc_14002B794
0x14002b3fe  call    cs:__imp_PsGetCurrentProcess
0x14002b405  nop     dword ptr [rax+rax+00h]
0x14002b40a  mov     rbx, rax
0x14002b40d  mov     [rsp+288h+var_200], rax
0x14002b415  lea     r8, [rsp+288h+TokenHandle]; TokenHandle
0x14002b41a  mov     edx, 20008h; DesiredAccess
0x14002b41f  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x14002b423  call    cs:__imp_ZwOpenProcessToken
0x14002b42a  nop     dword ptr [rax+rax+00h]
0x14002b42f  test    eax, eax
0x14002b431  jns     short loc_14002B43D
0x14002b433  mov     ebx, 0C0000022h
0x14002b438  jmp     loc_14002B794
0x14002b43d  lea     rax, [rsp+288h+TokenInformationLength]
0x14002b442  mov     [rsp+288h+ReturnLength], rax; ReturnLength
0x14002b447  mov     r9d, [rsp+288h+TokenInformationLength]; TokenInformationLength
0x14002b44c  lea     r8, [rsp+288h+TokenInformation]; TokenInformation
0x14002b454  mov     edx, r13d; TokenInformationClass
0x14002b457  mov     rcx, [rsp+288h+TokenHandle]; TokenHandle
0x14002b45c  call    cs:__imp_ZwQueryInformationToken
0x14002b463  nop     dword ptr [rax+rax+00h]
0x14002b468  test    eax, eax
0x14002b46a  js      short loc_14002B433
0x14002b46c  mov     rax, cs:__imp_SeExports
0x14002b473  mov     rdx, [rax]
0x14002b476  mov     rdx, [rdx+108h]; Sid2
0x14002b47d  mov     rcx, [rsp+288h+TokenInformation]; Sid1
0x14002b485  call    cs:__imp_RtlEqualSid
0x14002b48c  nop     dword ptr [rax+rax+00h]
0x14002b491  test    al, al
0x14002b493  jz      short loc_14002B433
0x14002b495  lea     r8, [rsp+288h+SubjectContext]; SubjectContext
0x14002b49d  mov     rdx, rbx; Process
0x14002b4a0  xor     ecx, ecx; Thread
0x14002b4a2  call    cs:__imp_SeCaptureSubjectContextEx
0x14002b4a9  nop     dword ptr [rax+rax+00h]
0x14002b4ae  mov     r8b, r13b; AccessMode
0x14002b4b1  lea     rdx, [rsp+288h+SubjectContext]; SubjectSecurityContext
0x14002b4b9  lea     rcx, [rsp+288h+RequiredPrivileges]; RequiredPrivileges
0x14002b4c1  call    cs:__imp_SePrivilegeCheck
0x14002b4c8  nop     dword ptr [rax+rax+00h]
0x14002b4cd  mov     bl, al
0x14002b4cf  lea     rcx, [rsp+288h+SubjectContext]; SubjectContext
0x14002b4d7  call    cs:__imp_SeReleaseSubjectContext
0x14002b4de  nop     dword ptr [rax+rax+00h]
0x14002b4e3  test    bl, bl
0x14002b4e5  jz      loc_14002B433
0x14002b4eb  mov     [rsp+288h+Object], rdi
0x14002b4f0  mov     [rsp+288h+HandleInformation], rdi; HandleInformation
0x14002b4f5  lea     rax, [rsp+288h+Object]
0x14002b4fa  mov     [rsp+288h+ReturnLength], rax; Object
0x14002b4ff  xor     r9d, r9d; AccessMode
0x14002b502  mov     r8, cs:__imp_PsProcessType
0x14002b509  mov     r8, [r8]; ObjectType
0x14002b50c  mov     edx, 438h; DesiredAccess
0x14002b511  mov     rcx, [r12]; Handle
0x14002b515  call    cs:__imp_ObReferenceObjectByHandle
0x14002b51c  nop     dword ptr [rax+rax+00h]
0x14002b521  mov     ebx, eax
0x14002b523  mov     rsi, [rsp+288h+Object]
0x14002b528  mov     [rsp+288h+var_230], rsi
0x14002b52d  test    eax, eax
0x14002b52f  js      loc_14002B794
0x14002b535  lea     rdx, [rsp+288h+ApcState]; ApcState
0x14002b53d  mov     rcx, rsi; PROCESS
0x14002b540  call    cs:__imp_KeStackAttachProcess
0x14002b547  nop     dword ptr [rax+rax+00h]
0x14002b54c  mov     [rsp+288h+var_238], r13d
0x14002b551  mov     rcx, rsi
0x14002b554  call    cs:__imp_PsGetProcessPeb
0x14002b55b  nop     dword ptr [rax+rax+00h]
0x14002b560  mov     r12, rax
0x14002b563  test    rax, rax
0x14002b566  jnz     short loc_14002B58E
0x14002b568  mov     ebx, 0C000000Dh
0x14002b56d  lea     r9, aInvalidProcess; "Invalid process peb"
0x14002b574  mov     r8d, 4E7h
0x14002b57a  mov     ecx, r13d
0x14002b57d  lea     rdx, aAhcapiinitproc; "AhcApiInitProcessData"
0x14002b584  call    AslLogCallPrintf
0x14002b589  jmp     loc_14002B794
0x14002b58e  lea     rcx, [rax+20h]
0x14002b592  call    RtlReadULong64FromUser
0x14002b597  mov     rbx, rax
0x14002b59a  mov     edx, 450h; Length
0x14002b59f  mov     r8d, 4; Alignment
0x14002b5a5  mov     rcx, rax; Address
0x14002b5a8  call    cs:__imp_ProbeForRead
0x14002b5af  nop     dword ptr [rax+rax+00h]
0x14002b5b4  mov     rcx, rsi
0x14002b5b7  call    cs:__imp_PsGetProcessProtection
0x14002b5be  nop     dword ptr [rax+rax+00h]
0x14002b5c3  cmp     al, 81h
0x14002b5c5  jnz     loc_14002B775
0x14002b5cb  test    byte ptr [r12+3], 10h
0x14002b5d1  jz      loc_14002B775
0x14002b5d7  prefetchw byte ptr [rbx+8]
0x14002b5db  mov     eax, [rbx+8]
0x14002b5de  mov     edx, 10000000h
0x14002b5e3  mov     ecx, eax
0x14002b5e5  or      ecx, edx
0x14002b5e7  lock cmpxchg [rbx+8], ecx
0x14002b5ec  jnz     short loc_14002B5E3
0x14002b5ee  test    edx, eax
0x14002b5f0  jz      short loc_14002B600
0x14002b5f2  mov     ebx, 0C0000022h
0x14002b5f7  mov     [rsp+288h+var_248], ebx
0x14002b5fb  jmp     loc_14002B794
0x14002b600  mov     rcx, rsi
0x14002b603  call    cs:__imp_PsGetProcessWow64Process
0x14002b60a  nop     dword ptr [rax+rax+00h]
0x14002b60f  mov     r13, rax
0x14002b612  test    r15, r15
0x14002b615  jz      loc_14002B771
0x14002b61b  test    r14, r14
0x14002b61e  jz      loc_14002B771
0x14002b624  lea     rax, [rsp+288h+ProcessHandle]
0x14002b629  mov     [rsp+288h+Handle], rax; Handle
0x14002b62e  mov     byte ptr [rsp+288h+HandleInformation], dil; AccessMode
0x14002b633  mov     [rsp+288h+ReturnLength], rdi; ObjectType
0x14002b638  mov     r9d, 438h; DesiredAccess
0x14002b63e  xor     r8d, r8d; PassedAccessState
0x14002b641  mov     edx, 200h; HandleAttributes
0x14002b646  mov     rcx, rsi; Object
0x14002b649  call    cs:__imp_ObOpenObjectByPointer
0x14002b650  nop     dword ptr [rax+rax+00h]
0x14002b655  mov     ebx, eax
0x14002b657  test    eax, eax
0x14002b659  js      loc_14002B794
0x14002b65f  mov     [rsp+288h+RegionSize], r14
0x14002b664  mov     dword ptr [rsp+288h+HandleInformation], 4; Protect
0x14002b66c  mov     dword ptr [rsp+288h+ReturnLength], 1000h; AllocationType
0x14002b674  lea     r9, [rsp+288h+RegionSize]; RegionSize
0x14002b679  xor     r8d, r8d; ZeroBits
0x14002b67c  lea     rdx, [rsp+288h+BaseAddress]; BaseAddress
0x14002b681  mov     rcx, [rsp+288h+ProcessHandle]; ProcessHandle
0x14002b686  call    cs:__imp_ZwAllocateVirtualMemory
0x14002b68d  nop     dword ptr [rax+rax+00h]
0x14002b692  test    eax, eax
0x14002b694  js      loc_14002B755
0x14002b69a  cmp     [rsp+288h+RegionSize], r14
0x14002b69f  jb      loc_14002B755
0x14002b6a5  lea     rax, [rsp+288h+var_208]
0x14002b6ad  mov     [rsp+288h+Handle], rax
0x14002b6b2  mov     byte ptr [rsp+288h+HandleInformation], dil
0x14002b6b7  mov     [rsp+288h+ReturnLength], r14
0x14002b6bc  mov     r9, [rsp+288h+BaseAddress]
0x14002b6c1  mov     r8, rsi
0x14002b6c4  mov     rdx, r15
0x14002b6c7  mov     rcx, [rsp+288h+var_200]
0x14002b6cf  call    cs:__imp_MmCopyVirtualMemory
0x14002b6d6  nop     dword ptr [rax+rax+00h]
0x14002b6db  mov     ebx, eax
0x14002b6dd  test    eax, eax
0x14002b6df  jns     short loc_14002B708
0x14002b6e1  mov     dword ptr [rsp+288h+ReturnLength], eax
0x14002b6e5  lea     r9, aErrorCopyingMe; "Error copying memory [%x]"
0x14002b6ec  mov     r8d, 542h
0x14002b6f2  lea     rdx, aAhcapiinitproc; "AhcApiInitProcessData"
0x14002b6f9  mov     ecx, 1
0x14002b6fe  call    AslLogCallPrintf
0x14002b703  jmp     loc_14002B794
0x14002b708  mov     rax, [rsp+288h+BaseAddress]
0x14002b70d  mov     [r12+2D8h], rax
0x14002b715  test    r13, r13
0x14002b718  jz      short loc_14002B726
0x14002b71a  mov     rax, [rsp+288h+BaseAddress]
0x14002b71f  mov     [r13+1E8h], eax
0x14002b726  jmp     short loc_14002B771
0x14002b728  mov     ebx, eax
0x14002b72a  mov     dword ptr [rsp+288h+ReturnLength], eax
0x14002b72e  lea     r9, aErrorUpdatingP; "Error updating peb and shim data [%x]"
0x14002b735  mov     r8d, 553h
0x14002b73b  lea     rdx, aAhcapiinitproc; "AhcApiInitProcessData"
0x14002b742  mov     ecx, 1
0x14002b747  call    AslLogCallPrintf
0x14002b74c  xor     edi, edi
0x14002b74e  mov     rsi, [rsp+288h+var_230]
0x14002b753  jmp     short loc_14002B794
0x14002b755  mov     ebx, 0C0000017h
0x14002b75a  lea     r9, aOutOfMemory; "Out of memory"
0x14002b761  mov     r8d, 531h
0x14002b767  mov     ecx, 1
0x14002b76c  jmp     loc_14002B57D
0x14002b771  mov     ebx, edi
0x14002b773  jmp     short loc_14002B794
0x14002b775  mov     ebx, 0C0000022h
0x14002b77a  mov     [rsp+288h+var_248], ebx
0x14002b77e  jmp     short loc_14002B794
0x14002b780  mov     ebx, eax
0x14002b782  mov     [rsp+288h+var_248], eax
0x14002b786  xor     edi, edi
0x14002b788  mov     rsi, [rsp+288h+var_230]
0x14002b78d  jmp     short loc_14002B794
0x14002b78f  mov     ebx, 0C000000Dh
0x14002b794  cmp     [rsp+288h+var_238], edi
0x14002b798  jz      short loc_14002B7AE
0x14002b79a  lea     rcx, [rsp+288h+ApcState]; ApcState
0x14002b7a2  call    cs:__imp_KeUnstackDetachProcess
0x14002b7a9  nop     dword ptr [rax+rax+00h]
0x14002b7ae  test    ebx, ebx
0x14002b7b0  jns     short loc_14002B7DA
0x14002b7b2  cmp     [rsp+288h+BaseAddress], rdi
0x14002b7b7  jz      short loc_14002B7DA
0x14002b7b9  mov     r9d, 8000h; FreeType
0x14002b7bf  lea     r8, [rsp+288h+RegionSize]; RegionSize
0x14002b7c4  lea     rdx, [rsp+288h+BaseAddress]; BaseAddress
0x14002b7c9  mov     rcx, [rsp+288h+ProcessHandle]; ProcessHandle
0x14002b7ce  call    cs:__imp_ZwFreeVirtualMemory
0x14002b7d5  nop     dword ptr [rax+rax+00h]
0x14002b7da  test    rsi, rsi
0x14002b7dd  jz      short loc_14002B7EE
0x14002b7df  mov     rcx, rsi; Object
0x14002b7e2  call    cs:__imp_ObfDereferenceObject
0x14002b7e9  nop     dword ptr [rax+rax+00h]
0x14002b7ee  mov     rcx, [rsp+288h+ProcessHandle]; Handle
0x14002b7f3  test    rcx, rcx
0x14002b7f6  jz      short loc_14002B804
  ... truncated ...
```
