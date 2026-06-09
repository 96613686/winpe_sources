# BfsInitializeGlobalFileTable

- ea: `0x14000c9a4`
- end: `0x14000cd1a`
- name: `BfsInitializeGlobalFileTable`
- size: `886`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14001f078`

## callees

- `0x140001008`
- `0x14000c9a4`
- `0x14000cd20`
- `0x140013730`
- `0x14001e008`

## import_xrefs

- `ntoskrnl!ExInitializePushLock` at `0x14000ca95`
- `ntoskrnl!ExInitializePushLock` at `0x14000caa5`
- `ntoskrnl!ExInitializePushLock` at `0x14000ca95`
- `ntoskrnl!ExInitializePushLock` at `0x14000caa5`
- `ntoskrnl!RtlCreateHashTable` at `0x14000cb26`
- `ntoskrnl!RtlCreateHashTable` at `0x14000cb26`
- `ntoskrnl!RtlDeleteHashTable` at `0x14000cc4f`
- `ntoskrnl!RtlDeleteHashTable` at `0x14000cc4f`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000ca26`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000ca26`
- `ntoskrnl!KeSetEvent` at `0x14000cc7f`
- `ntoskrnl!KeSetEvent` at `0x14000cc7f`
- `ntoskrnl!ZwQueryDirectoryFile` at `0x14000cbfb`
- `ntoskrnl!ZwQueryDirectoryFile` at `0x14000cbfb`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000c9f6`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000cb9a`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000c9f6`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000cb9a`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14000cca3`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14000cca3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000cc32`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000cc60`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000cc32`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000cc60`
- `ntoskrnl!ExAllocatePool2` at `0x14000cac5`
- `ntoskrnl!ExAllocatePool2` at `0x14000cb68`
- `ntoskrnl!ExAllocatePool2` at `0x14000cac5`
- `ntoskrnl!ExAllocatePool2` at `0x14000cb68`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000ca58`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000cc90`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000ca58`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000cc90`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14000ca6b`
- `ntoskrnl!ExAcquireRundownProtection` at `0x14000ca6b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000ca7a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000ccaf`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000ca7a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000ccaf`

## pseudocode

```c
__int64 __fastcall BfsInitializeGlobalFileTable(__int64 a1, __int64 a2, __int64 a3)
{
  signed __int64 v4; // rax
  __int64 v5; // rax
  int UserPolicyEntriesToGlobalFileTable; // edi
  BOOLEAN v8; // r13
  char v9; // r12
  __int64 Pool2; // rax
  int v11; // ecx
  int v12; // r8d
  int v13; // r9d
  PRTL_DYNAMIC_HASH_TABLE *v14; // r15
  __int64 FileInformation; // r14
  NTSTATUS i; // eax
  unsigned __int64 v17; // rax
  __int64 v18; // rdx
  int v19; // ecx
  int v20; // r8d
  int v21; // r9d
  int Timeout; // [rsp+20h] [rbp-A9h]
  int Timeouta; // [rsp+20h] [rbp-A9h]
  PFLT_FILTER v24; // [rsp+60h] [rbp-69h] BYREF
  HANDLE FileHandle; // [rsp+68h] [rbp-61h]
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp-59h] BYREF
  struct _UNICODE_STRING v27; // [rsp+80h] [rbp-49h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+90h] [rbp-39h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v29; // [rsp+A0h] [rbp-29h] BYREF
  PFLT_FILTER *v30; // [rsp+C0h] [rbp-9h]
  __int64 v31; // [rsp+C8h] [rbp-1h]

  v24 = gBfsFilterHandle;
  IoStatusBlock = 0;
  DestinationString = 0;
  v27 = 0;
  RtlInitUnicodeString(&DestinationString, L"S-1-*");
  v4 = _InterlockedCompareExchange64((volatile signed __int64 *)(a3 + 64), -1, 0);
  if ( v4 == -1 )
  {
    KeWaitForSingleObject((PVOID)(a3 + 16), Executive, 0, 0, 0);
    v5 = *(_QWORD *)(a3 + 64);
    if ( !v5 || v5 == -1 )
      return 3221225473LL;
    return 0;
  }
  if ( v4 )
    return 0;
  UserPolicyEntriesToGlobalFileTable = 0;
  KeEnterCriticalRegion();
  v8 = ExAcquireRundownProtection(&gBfsRundownProtection);
  KeLeaveCriticalRegion();
  if ( v8 )
  {
    v9 = 0;
    ExInitializePushLock((PULONG_PTR)a3);
    ExInitializePushLock((PULONG_PTR)(a3 + 8));
    Pool2 = ExAllocatePool2(256, 40, 1416848962);
    v14 = (PRTL_DYNAMIC_HASH_TABLE *)(a3 + 40);
    *(_QWORD *)(a3 + 40) = Pool2;
    if ( Pool2 )
    {
      if ( RtlCreateHashTable((PRTL_DYNAMIC_HASH_TABLE *)(a3 + 40), 0, 0) )
      {
        v9 = 1;
        *(_QWORD *)(a3 + 56) = a3 + 48;
        *(_QWORD *)(a3 + 48) = a3 + 48;
        FileHandle = (HANDLE)BfsGetRootDirectory();
        FileInformation = ExAllocatePool2(256, 390, 1316185666);
        for ( i = ZwQueryDirectoryFile(
                    FileHandle,
                    0,
                    0,
                    0,
                    &IoStatusBlock,
                    (PVOID)FileInformation,
                    0x186u,
                    FileNamesInformation,
                    0,
                    &DestinationString,
                    1u);
              ;
              i = ZwQueryDirectoryFile(
                    FileHandle,
                    0,
                    0,
                    0,
                    &IoStatusBlock,
                    (PVOID)FileInformation,
                    0x186u,
                    FileNamesInformation,
                    0,
                    &DestinationString,
                    0) )
        {
          UserPolicyEntriesToGlobalFileTable = i;
          if ( i < 0 )
          {
            if ( i == -2147483642 || i == -1073741809 )
              UserPolicyEntriesToGlobalFileTable = 0;
            _InterlockedExchange64((volatile __int64 *)(a3 + 64), 1);
            goto LABEL_23;
          }
          v17 = *(unsigned int *)(FileInformation + 8);
          if ( (_DWORD)v17 )
          {
            *(_WORD *)(FileInformation + 2 * (v17 >> 1) + 12) = 0;
            RtlInitUnicodeString(&v27, (PCWSTR)(FileInformation + 12));
            UserPolicyEntriesToGlobalFileTable = BfsLoadUserPolicyEntriesToGlobalFileTable(
                                                   (int)v24,
                                                   v18,
                                                   a3,
                                                   (__int64)&v27);
            if ( UserPolicyEntriesToGlobalFileTable < 0 )
              break;
          }
        }
        if ( (unsigned int)dword_140019000 > 3 )
        {
          LODWORD(v24) = UserPolicyEntriesToGlobalFileTable;
          v30 = &v24;
          v31 = 4;
          tlgWriteTransfer_EtwWriteTransfer(v19, (int)&byte_140016D91, v20, v21, Timeouta, &v29);
        }
LABEL_23:
        if ( FileInformation )
          ExFreePoolWithTag((PVOID)FileInformation, 0);
        if ( UserPolicyEntriesToGlobalFileTable >= 0 )
          goto LABEL_31;
        goto LABEL_26;
      }
      UserPolicyEntriesToGlobalFileTable = -1073741823;
    }
    else
    {
      UserPolicyEntriesToGlobalFileTable = -1073741801;
    }
    if ( (unsigned int)dword_140019000 > 3 )
    {
      LODWORD(v24) = UserPolicyEntriesToGlobalFileTable;
      v30 = &v24;
      v31 = 4;
      tlgWriteTransfer_EtwWriteTransfer(v11, (int)&byte_140016D91, v12, v13, Timeout, &v29);
    }
LABEL_26:
    if ( *v14 )
    {
      if ( v9 )
        RtlDeleteHashTable(*v14);
      ExFreePoolWithTag(*v14, 0);
      *v14 = 0;
    }
    _InterlockedExchange64((volatile __int64 *)(a3 + 64), 0);
  }
LABEL_31:
  KeSetEvent((PRKEVENT)(a3 + 16), 0, 0);
  if ( v8 )
  {
    KeEnterCriticalRegion();
    ExReleaseRundownProtection(&gBfsRundownProtection);
    KeLeaveCriticalRegion();
  }
  return (unsigned int)UserPolicyEntriesToGlobalFileTable;
}

```

## disassembly

```asm
0x14000c9a4  push    rbp
0x14000c9a6  push    rbx
0x14000c9a7  push    rsi
0x14000c9a8  push    rdi
0x14000c9a9  push    r12
0x14000c9ab  push    r13
0x14000c9ad  push    r14
0x14000c9af  push    r15
0x14000c9b1  lea     rbp, [rsp-1Fh]
0x14000c9b6  sub     rsp, 0E8h
0x14000c9bd  mov     rax, cs:__security_cookie
0x14000c9c4  xor     rax, rsp
0x14000c9c7  mov     [rbp+57h+var_50], rax
0x14000c9cb  mov     rax, cs:gBfsFilterHandle
0x14000c9d2  lea     rdx, aS1; "S-1-*"
0x14000c9d9  xorps   xmm0, xmm0
0x14000c9dc  mov     [rbp+57h+var_C0], rax
0x14000c9e0  xorps   xmm1, xmm1
0x14000c9e3  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14000c9e7  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x14000c9eb  mov     rsi, r8
0x14000c9ee  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm1
0x14000c9f2  movups  xmmword ptr [rbp+57h+var_A0.Length], xmm0
0x14000c9f6  call    cs:__imp_RtlInitUnicodeString
0x14000c9fd  nop     dword ptr [rax+rax+00h]
0x14000ca02  or      rdi, 0FFFFFFFFFFFFFFFFh
0x14000ca06  xor     eax, eax
0x14000ca08  lock cmpxchg [rsi+40h], rdi
0x14000ca0e  xor     ebx, ebx
0x14000ca10  cmp     rax, rdi
0x14000ca13  jnz     short loc_14000CA4A
0x14000ca15  lea     rcx, [rsi+10h]; Object
0x14000ca19  mov     [rsp+120h+Timeout], rbx; Timeout
0x14000ca1e  xor     r9d, r9d; Alertable
0x14000ca21  xor     r8d, r8d; WaitMode
0x14000ca24  xor     edx, edx; WaitReason
0x14000ca26  call    cs:__imp_KeWaitForSingleObject
0x14000ca2d  nop     dword ptr [rax+rax+00h]
0x14000ca32  mov     rax, [rsi+40h]
0x14000ca36  test    rax, rax
0x14000ca39  jz      short loc_14000CA40
0x14000ca3b  cmp     rax, rdi
0x14000ca3e  jnz     short loc_14000CA4F
0x14000ca40  mov     eax, 0C0000001h
0x14000ca45  jmp     loc_14000CCBD
0x14000ca4a  test    rax, rax
0x14000ca4d  jz      short loc_14000CA56
0x14000ca4f  xor     eax, eax
0x14000ca51  jmp     loc_14000CCBD
0x14000ca56  mov     edi, ebx
0x14000ca58  call    cs:__imp_KeEnterCriticalRegion
0x14000ca5f  nop     dword ptr [rax+rax+00h]
0x14000ca64  lea     rcx, gBfsRundownProtection; RunRef
0x14000ca6b  call    cs:__imp_ExAcquireRundownProtection
0x14000ca72  nop     dword ptr [rax+rax+00h]
0x14000ca77  mov     r13b, al
0x14000ca7a  call    cs:__imp_KeLeaveCriticalRegion
0x14000ca81  nop     dword ptr [rax+rax+00h]
0x14000ca86  test    r13b, r13b
0x14000ca89  jz      loc_14000CC76
0x14000ca8f  mov     rcx, rsi; PushLock
0x14000ca92  mov     r12b, bl
0x14000ca95  call    cs:__imp_ExInitializePushLock
0x14000ca9c  nop     dword ptr [rax+rax+00h]
0x14000caa1  lea     rcx, [rsi+8]; PushLock
0x14000caa5  call    cs:__imp_ExInitializePushLock
0x14000caac  nop     dword ptr [rax+rax+00h]
0x14000cab1  mov     r14d, 100h
0x14000cab7  mov     edx, 28h ; '('
0x14000cabc  mov     ecx, r14d
0x14000cabf  mov     r8d, 54736642h
0x14000cac5  call    cs:__imp_ExAllocatePool2
0x14000cacc  nop     dword ptr [rax+rax+00h]
0x14000cad1  lea     r15, [rsi+28h]
0x14000cad5  mov     [r15], rax
0x14000cad8  test    rax, rax
0x14000cadb  jnz     short loc_14000CB1E
0x14000cadd  mov     edi, 0C0000017h
0x14000cae2  mov     eax, cs:dword_140019000
0x14000cae8  cmp     eax, 3
0x14000caeb  jbe     loc_14000CC42
0x14000caf1  lea     rax, [rbp+57h+var_C0]
0x14000caf5  mov     dword ptr [rbp+57h+var_C0], edi
0x14000caf8  mov     [rbp+57h+var_60], rax
0x14000cafc  lea     rdx, byte_140016D91; int
0x14000cb03  lea     rax, [rbp+57h+var_80]
0x14000cb07  mov     [rbp+57h+var_58], 4
0x14000cb0f  mov     [rsp+120h+FileInformation], rax; PEVENT_DATA_DESCRIPTOR
0x14000cb14  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000cb19  jmp     loc_14000CC42
0x14000cb1e  xor     r8d, r8d; Flags
0x14000cb21  xor     edx, edx; Shift
0x14000cb23  mov     rcx, r15; HashTable
0x14000cb26  call    cs:__imp_RtlCreateHashTable
0x14000cb2d  nop     dword ptr [rax+rax+00h]
0x14000cb32  test    al, al
0x14000cb34  jnz     short loc_14000CB3D
0x14000cb36  mov     edi, 0C0000001h
0x14000cb3b  jmp     short loc_14000CAE2
0x14000cb3d  lea     rax, [rsi+30h]
0x14000cb41  mov     r12d, 1
0x14000cb47  mov     [rax+8], rax
0x14000cb4b  mov     [rax], rax
0x14000cb4e  call    BfsGetRootDirectory
0x14000cb53  mov     edx, 186h
0x14000cb58  mov     [rbp+57h+FileHandle], rax
0x14000cb5c  mov     r8d, 4E736642h
0x14000cb62  mov     rcx, r14
0x14000cb65  mov     rdi, rax
0x14000cb68  call    cs:__imp_ExAllocatePool2
0x14000cb6f  nop     dword ptr [rax+rax+00h]
0x14000cb74  mov     [rsp+120h+RestartScan], r12b
0x14000cb79  mov     rcx, rdi
0x14000cb7c  mov     r14, rax
0x14000cb7f  jmp     short loc_14000CBC8
0x14000cb81  mov     eax, [r14+8]
0x14000cb85  test    eax, eax
0x14000cb87  jz      short loc_14000CBC0
0x14000cb89  shr     rax, 1
0x14000cb8c  lea     rdx, [r14+0Ch]; SourceString
0x14000cb90  lea     rcx, [rbp+57h+var_A0]; DestinationString
0x14000cb94  mov     [r14+rax*2+0Ch], bx
0x14000cb9a  call    cs:__imp_RtlInitUnicodeString
0x14000cba1  nop     dword ptr [rax+rax+00h]
0x14000cba6  mov     rcx, [rbp+57h+var_C0]
0x14000cbaa  lea     r9, [rbp+57h+var_A0]
0x14000cbae  mov     r8, rsi
0x14000cbb1  call    BfsLoadUserPolicyEntriesToGlobalFileTable
0x14000cbb6  mov     edi, eax
0x14000cbb8  test    eax, eax
0x14000cbba  js      loc_14000CCDE
0x14000cbc0  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x14000cbc4  mov     [rsp+120h+RestartScan], bl; RestartScan
0x14000cbc8  lea     rax, [rbp+57h+DestinationString]
0x14000cbcc  xor     r9d, r9d; ApcContext
0x14000cbcf  mov     [rsp+120h+FileName], rax; FileName
0x14000cbd4  xor     r8d, r8d; ApcRoutine
0x14000cbd7  mov     [rsp+120h+ReturnSingleEntry], bl; ReturnSingleEntry
0x14000cbdb  lea     rax, [rbp+57h+IoStatusBlock]
0x14000cbdf  mov     [rsp+120h+FileInformationClass], 0Ch; FileInformationClass
0x14000cbe7  xor     edx, edx; Event
0x14000cbe9  mov     [rsp+120h+Length], 186h; Length
0x14000cbf1  mov     [rsp+120h+FileInformation], r14; FileInformation
0x14000cbf6  mov     [rsp+120h+Timeout], rax; int
0x14000cbfb  call    cs:__imp_ZwQueryDirectoryFile
0x14000cc02  nop     dword ptr [rax+rax+00h]
0x14000cc07  mov     edi, eax
0x14000cc09  test    eax, eax
0x14000cc0b  jns     loc_14000CB81
0x14000cc11  cmp     eax, 80000006h
0x14000cc16  jz      short loc_14000CC1F
0x14000cc18  cmp     eax, 0C000000Fh
0x14000cc1d  jnz     short loc_14000CC21
0x14000cc1f  mov     edi, ebx
0x14000cc21  mov     rax, r12
0x14000cc24  xchg    rax, [rsi+40h]
0x14000cc28  test    r14, r14
0x14000cc2b  jz      short loc_14000CC3E
0x14000cc2d  xor     edx, edx; Tag
0x14000cc2f  mov     rcx, r14; P
0x14000cc32  call    cs:__imp_ExFreePoolWithTag
0x14000cc39  nop     dword ptr [rax+rax+00h]
0x14000cc3e  test    edi, edi
0x14000cc40  jns     short loc_14000CC76
0x14000cc42  mov     rcx, [r15]; HashTable
0x14000cc45  test    rcx, rcx
0x14000cc48  jz      short loc_14000CC6F
0x14000cc4a  test    r12b, r12b
0x14000cc4d  jz      short loc_14000CC5B
0x14000cc4f  call    cs:__imp_RtlDeleteHashTable
0x14000cc56  nop     dword ptr [rax+rax+00h]
0x14000cc5b  mov     rcx, [r15]; P
0x14000cc5e  xor     edx, edx; Tag
0x14000cc60  call    cs:__imp_ExFreePoolWithTag
0x14000cc67  nop     dword ptr [rax+rax+00h]
0x14000cc6c  mov     [r15], rbx
0x14000cc6f  mov     rax, rbx
0x14000cc72  xchg    rax, [rsi+40h]
0x14000cc76  lea     rcx, [rsi+10h]; Event
0x14000cc7a  xor     r8d, r8d; Wait
0x14000cc7d  xor     edx, edx; Increment
0x14000cc7f  call    cs:__imp_KeSetEvent
0x14000cc86  nop     dword ptr [rax+rax+00h]
0x14000cc8b  test    r13b, r13b
0x14000cc8e  jz      short loc_14000CCBB
0x14000cc90  call    cs:__imp_KeEnterCriticalRegion
0x14000cc97  nop     dword ptr [rax+rax+00h]
0x14000cc9c  lea     rcx, gBfsRundownProtection; RunRef
0x14000cca3  call    cs:__imp_ExReleaseRundownProtection
0x14000ccaa  nop     dword ptr [rax+rax+00h]
0x14000ccaf  call    cs:__imp_KeLeaveCriticalRegion
0x14000ccb6  nop     dword ptr [rax+rax+00h]
0x14000ccbb  mov     eax, edi
0x14000ccbd  mov     rcx, [rbp+57h+var_50]
0x14000ccc1  xor     rcx, rsp; StackCookie
0x14000ccc4  call    __security_check_cookie
0x14000ccc9  add     rsp, 0E8h
0x14000ccd0  pop     r15
0x14000ccd2  pop     r14
0x14000ccd4  pop     r13
0x14000ccd6  pop     r12
0x14000ccd8  pop     rdi
0x14000ccd9  pop     rsi
0x14000ccda  pop     rbx
0x14000ccdb  pop     rbp
0x14000ccdc  retn
0x14000ccde  mov     eax, cs:dword_140019000
0x14000cce4  cmp     eax, 3
0x14000cce7  jbe     loc_14000CC28
0x14000cced  lea     rax, [rbp+57h+var_C0]
0x14000ccf1  mov     dword ptr [rbp+57h+var_C0], edi
0x14000ccf4  mov     [rbp+57h+var_60], rax
0x14000ccf8  lea     rdx, byte_140016D91; int
0x14000ccff  lea     rax, [rbp+57h+var_80]
0x14000cd03  mov     [rbp+57h+var_58], 4
0x14000cd0b  mov     [rsp+120h+FileInformation], rax; PEVENT_DATA_DESCRIPTOR
0x14000cd10  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000cd15  jmp     loc_14000CC28
```
