# RestoreHungThread(ulong,_WAITCHAIN_NODE_INFO *)

- ea: `0x14002bc90`
- end: `0x14002c10d`
- name: `?RestoreHungThread@@YAHKPEAU_WAITCHAIN_NODE_INFO@@@Z`
- size: `1149`
- prototype: `__int64 __fastcall(unsigned int, struct _WAITCHAIN_NODE_INFO *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, loader_planting, service_task`

## callers

- `0x140028378`

## callees

- `0x140002470`
- `0x140002728`
- `0x1400030a8`
- `0x14002bc90`
- `0x14002c114`
- `0x14002f5f8`
- `0x140034648`
- `0x14005b770`
- `0x14005b7e8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002bdb1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002be36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002bf81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002bdb1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002be36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002bf81`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14002c0be`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14002c0be`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessTimes` at `0x14002bddc`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessTimes` at `0x14002bddc`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x14002be20`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x14002be20`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002c009`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002c01d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002c0db`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002c009`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002c01d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002c0db`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x14002bf74`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x14002bf74`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x14002bd9a`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x14002be4f`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x14002bd9a`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x14002be4f`
- `ntdll!NtQueryInformationProcess` at `0x14002bee2`
- `ntdll!NtQueryInformationProcess` at `0x14002bee2`
- `ntdll!NtQueryInformationThread` at `0x14002be9e`
- `ntdll!NtQueryInformationThread` at `0x14002be9e`
- `ntdll!RtlNtStatusToDosError` at `0x14002beaa`
- `ntdll!RtlNtStatusToDosError` at `0x14002c076`
- `ntdll!RtlNtStatusToDosError` at `0x14002beaa`
- `ntdll!RtlNtStatusToDosError` at `0x14002c076`

## string_xrefs

- `0x14002c064`: `\WindowsErrorReportingServicePort`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_BOOL8 __fastcall RestoreHungThread(int a1, struct _WAITCHAIN_NODE_INFO *a2)
{
  char *v4; // r15
  __int64 v5; // rax
  __int64 v6; // rsi
  unsigned int IsSocketRestorable; // ebx
  __int64 v8; // rax
  char *v9; // rcx
  DWORD LastError; // eax
  char *v11; // r15
  char *v12; // r14
  unsigned __int64 v13; // r13
  NTSTATUS v14; // eax
  int v15; // r9d
  int v16; // esi
  const void *v17; // rax
  unsigned __int64 v18; // r12
  __int64 *v19; // rax
  const struct std::nothrow_t *v20; // rdx
  __int64 v21; // rdi
  const struct std::nothrow_t *v22; // rdx
  unsigned __int64 v23; // rcx
  unsigned int v24; // r9d
  int v25; // eax
  NTSTATUS v26; // ecx
  unsigned int lpUserTime; // [rsp+20h] [rbp-E0h]
  wchar_t *v29; // [rsp+28h] [rbp-D8h]
  char *hObject; // [rsp+40h] [rbp-C0h]
  LPCVOID ProcessInformation; // [rsp+48h] [rbp-B8h] BYREF
  ULONG ReturnLength; // [rsp+50h] [rbp-B0h] BYREF
  int v33; // [rsp+54h] [rbp-ACh] BYREF
  struct _FILETIME ExitTime; // [rsp+58h] [rbp-A8h] BYREF
  struct _FILETIME CreationTime; // [rsp+60h] [rbp-A0h] BYREF
  void *v36; // [rsp+68h] [rbp-98h] BYREF
  _OWORD ThreadInformation[3]; // [rsp+70h] [rbp-90h] BYREF
  char *v38; // [rsp+A0h] [rbp-60h]
  char *v39; // [rsp+A8h] [rbp-58h]
  _QWORD v40[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v41; // [rsp+C0h] [rbp-40h]
  _BYTE Src[1408]; // [rsp+D0h] [rbp-30h] BYREF
  _DWORD v43[12]; // [rsp+650h] [rbp+550h] BYREF
  DWORD ProcessId; // [rsp+680h] [rbp+580h]
  struct _FILETIME v45; // [rsp+684h] [rbp+584h]
  _SOCKADDR_INET v46; // [rsp+68Ch] [rbp+58Ch] BYREF
  union _SOCKADDR_INET v47; // [rsp+6A8h] [rbp+5A8h] BYREF
  _DWORD v48[352]; // [rsp+BD0h] [rbp+AD0h] BYREF

  v4 = 0;
  CreationTime = 0;
  ExitTime = 0;
  memset_0(v43, 0, 0x578u);
  memset_0(v48, 0, 0x578u);
  if ( a2
    && (v5 = (unsigned int)(a1 - 2), (unsigned int)v5 <= 0xE)
    && (v6 = v5, IsSocketRestorable = 8, a2[v5].ObjectType == WctThreadType) )
  {
    v8 = (unsigned int)(a1 - 1);
    if ( a2[v8].ObjectType == WctSocketIoType && a2[v8].LockObject.Alertable )
    {
      memset_0(Src, 0, 0x578u);
      memcpy_0(v43, Src, 0x578u);
      v43[0] = 91751760;
      v43[10] = 268435463;
      ProcessId = a2[v6].ThreadObject.ProcessId;
      v9 = (char *)OpenProcess(0x400u, 0, ProcessId);
      hObject = v9;
      if ( v9 == (char *)-1LL
        || v9 + 1 == (char *)1
        || !GetProcessTimes(v9, &CreationTime, &ExitTime, &ExitTime, &ExitTime) )
      {
        LastError = GetLastError();
        goto LABEL_8;
      }
      v45 = CreationTime;
      v33 = 0;
      v11 = 0;
      v12 = 0;
      v41 = 0;
      if ( a2[v6].ObjectType == WctThreadType )
      {
        v11 = (char *)OpenThread(0x40u, 0, a2[v6].ThreadObject.ThreadId);
        v38 = v11;
        if ( v11 == (char *)-1LL
          || v11 + 1 == (char *)1
          || (v12 = (char *)OpenProcess(0x450u, 0, a2[v6].ThreadObject.ProcessId),
              v39 = v12,
              v12 == (char *)-1LL || v12 + 1 == (char *)1) )
        {
          IsSocketRestorable = GetLastError();
        }
        else
        {
          v40[0] = v11;
          v40[1] = v12;
          ReturnLength = 0;
          memset(ThreadInformation, 0, sizeof(ThreadInformation));
          v13 = -1;
          v14 = NtQueryInformationThread(v11, ThreadBasicInformation, ThreadInformation, 0x30u, &ReturnLength);
          if ( v14 )
          {
            IsSocketRestorable = RtlNtStatusToDosError(v14);
LABEL_35:
            if ( !IsSocketRestorable )
              IsSocketRestorable = WctIsSocketRestorable(
                                     (struct _WCT_CLIENT_HANDLE *)v40,
                                     v13,
                                     &v33,
                                     v15,
                                     lpUserTime,
                                     v29,
                                     &v46,
                                     &v47);
            goto LABEL_39;
          }
          if ( *((_QWORD *)&ThreadInformation[0] + 1) )
          {
            ProcessInformation = 0;
            if ( NtQueryInformationProcess(v12, ProcessWow64Information, &ProcessInformation, 8u, 0) >= 0
              && ProcessInformation )
            {
              v16 = 1;
              v17 = (const void *)(*((_QWORD *)&ThreadInformation[0] + 1) + 0x2000LL);
            }
            else
            {
              v16 = 0;
              v17 = (const void *)*((_QWORD *)&ThreadInformation[0] + 1);
            }
            ProcessInformation = v17;
            v18 = -(__int64)(v16 != 0) & 0xFFFFFFFFFFFFF7C0uLL;
            v19 = (__int64 *)utl::make_unique<unsigned char [0],0>(&v36, v18 + 6256);
            v21 = *v19;
            *v19 = 0;
            if ( v36 )
              operator delete(v36, v20);
            if ( !v21 )
              goto LABEL_39;
            if ( ReadProcessMemory(v12, ProcessInformation, (LPVOID)v21, v18 + 6256, 0) )
            {
              if ( (_BYTE)v16 )
                v23 = *(unsigned int *)(v21 + 3948);
              else
                v23 = *(_QWORD *)(v21 + 5944);
              if ( ((v23 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
              {
                IsSocketRestorable = 0;
                v13 = v23;
              }
              else
              {
                IsSocketRestorable = 1168;
              }
            }
            else
            {
              IsSocketRestorable = GetLastError();
            }
            operator delete((void *)v21, v22);
            goto LABEL_35;
          }
          IsSocketRestorable = 13;
        }
      }
      else
      {
        IsSocketRestorable = 87;
      }
LABEL_39:
      if ( (unsigned __int64)(v12 + 1) > 1 )
        CloseHandle(v12);
      if ( (unsigned __int64)(v11 + 1) > 1 )
        CloseHandle(v11);
      if ( IsSocketRestorable )
        goto LABEL_9;
      memset_0(Src, 0, 0x578u);
      memcpy_0(v48, Src, 0x578u);
      v48[0] = 91751760;
      v25 = WersvcSendMessage(
              L"\\WindowsErrorReportingServicePort",
              (struct _WERSVC_MSG *)v43,
              (struct _WERSVC_MSG *)v48,
              v24);
      if ( v25 >= 0 )
      {
        if ( v25 == 258 )
        {
          IsSocketRestorable = 1235;
          goto LABEL_9;
        }
        if ( v48[10] != 268435463 )
        {
          IsSocketRestorable = 50;
          goto LABEL_9;
        }
        v26 = v48[11];
      }
      else
      {
        v26 = v25;
      }
      LastError = RtlNtStatusToDosError(v26);
LABEL_8:
      IsSocketRestorable = LastError;
LABEL_9:
      v4 = hObject;
      goto LABEL_54;
    }
    IsSocketRestorable = 1168;
  }
  else
  {
    IsSocketRestorable = 87;
  }
LABEL_54:
  SetLastError(IsSocketRestorable);
  if ( (unsigned __int64)(v4 + 1) > 1 )
    CloseHandle(v4);
  return IsSocketRestorable == 0;
}

```

## disassembly

```asm
0x14002bc90  mov     [rsp-8+arg_10], rbx
0x14002bc95  push    rbp
0x14002bc96  push    rsi
0x14002bc97  push    rdi
0x14002bc98  push    r12
0x14002bc9a  push    r13
0x14002bc9c  push    r14
0x14002bc9e  push    r15
0x14002bca0  lea     rbp, [rsp-1060h]
0x14002bca8  mov     eax, 1160h
0x14002bcad  call    _alloca_probe
0x14002bcb2  sub     rsp, rax
0x14002bcb5  mov     rax, cs:__security_cookie
0x14002bcbc  xor     rax, rsp
0x14002bcbf  mov     [rbp+1090h+var_40], rax
0x14002bcc6  mov     rdi, rdx
0x14002bcc9  mov     r14d, ecx
0x14002bccc  xor     r12d, r12d
0x14002bccf  mov     r15d, r12d
0x14002bcd2  mov     qword ptr [rsp+1190h+CreationTime.dwLowDateTime], r12
0x14002bcd7  mov     qword ptr [rsp+1190h+ExitTime.dwLowDateTime], r12
0x14002bcdc  mov     r13d, 578h
0x14002bce2  mov     r8d, r13d; Size
0x14002bce5  xor     edx, edx; Val
0x14002bce7  lea     rcx, [rbp+1090h+var_B40]; void *
0x14002bcee  call    memset_0
0x14002bcf3  mov     r8d, r13d; Size
0x14002bcf6  xor     edx, edx; Val
0x14002bcf8  lea     rcx, [rbp+1090h+var_5C0]; void *
0x14002bcff  call    memset_0
0x14002bd04  test    rdi, rdi
0x14002bd07  jz      loc_14002C0B7
0x14002bd0d  lea     eax, [r14-2]
0x14002bd11  cmp     eax, 0Eh
0x14002bd14  ja      loc_14002C0B7
0x14002bd1a  imul    rsi, rax, 118h
0x14002bd21  lea     ebx, [r12+8]
0x14002bd26  cmp     [rsi+rdi], ebx
0x14002bd29  jnz     loc_14002C0B7
0x14002bd2f  lea     ecx, [r14-1]
0x14002bd33  imul    rax, rcx, 118h
0x14002bd3a  cmp     dword ptr [rax+rdi], 0Bh
0x14002bd3e  jnz     loc_14002C0B0
0x14002bd44  cmp     [rax+rdi+110h], r12d
0x14002bd4c  jz      loc_14002C0B0
0x14002bd52  mov     r8d, r13d; Size
0x14002bd55  xor     edx, edx; Val
0x14002bd57  lea     rcx, [rbp+1090h+Src]; void *
0x14002bd5b  call    memset_0
0x14002bd60  lea     rcx, [rbp+1090h+var_B40]; void *
0x14002bd67  lea     rdx, [rbp+1090h+Src]; Src
0x14002bd6b  mov     r8d, r13d; Size
0x14002bd6e  call    memcpy_0
0x14002bd73  mov     [rbp+1090h+var_B40], 5780550h
0x14002bd7d  mov     [rbp+1090h+var_B18], 10000007h
0x14002bd87  mov     r8d, [rsi+rdi+8]; dwProcessId
0x14002bd8c  mov     [rbp+1090h+var_B10], r8d
0x14002bd93  xor     edx, edx; bInheritHandle
0x14002bd95  mov     ecx, 400h; dwDesiredAccess
0x14002bd9a  call    cs:__imp_OpenProcess
0x14002bda0  mov     rcx, rax; hProcess
0x14002bda3  mov     [rsp+1190h+hObject], rax
0x14002bda8  inc     rax
0x14002bdab  cmp     rax, 1
0x14002bdaf  ja      short loc_14002BDC3
0x14002bdb1  call    cs:__imp_GetLastError
0x14002bdb7  mov     ebx, eax
0x14002bdb9  mov     r15, [rsp+1190h+hObject]
0x14002bdbe  jmp     loc_14002C0BC
0x14002bdc3  lea     rax, [rsp+1190h+ExitTime]
0x14002bdc8  mov     [rsp+1190h+lpUserTime], rax; lpUserTime
0x14002bdcd  lea     r9, [rsp+1190h+ExitTime]; lpKernelTime
0x14002bdd2  lea     r8, [rsp+1190h+ExitTime]; lpExitTime
0x14002bdd7  lea     rdx, [rsp+1190h+CreationTime]; lpCreationTime
0x14002bddc  call    cs:__imp_GetProcessTimes
0x14002bde2  test    eax, eax
0x14002bde4  jz      short loc_14002BDB1
0x14002bde6  mov     eax, [rsp+1190h+CreationTime.dwLowDateTime]
0x14002bdea  mov     [rbp+1090h+var_B0C], eax
0x14002bdf0  mov     eax, [rsp+1190h+CreationTime.dwHighDateTime]
0x14002bdf4  mov     [rbp+1090h+var_B08], eax
0x14002bdfa  mov     [rsp+1190h+var_113C], r12d
0x14002bdff  mov     r15, r12
0x14002be02  mov     r14, r12
0x14002be05  xorps   xmm0, xmm0
0x14002be08  movdqu  [rbp+1090h+var_10D0], xmm0
0x14002be0d  cmp     [rsi+rdi], ebx
0x14002be10  jnz     loc_14002BFF7
0x14002be16  mov     r8d, [rsi+rdi+0Ch]; dwThreadId
0x14002be1b  xor     edx, edx; bInheritHandle
0x14002be1d  lea     ecx, [rdx+40h]; dwDesiredAccess
0x14002be20  call    cs:__imp_OpenThread
0x14002be26  mov     r15, rax
0x14002be29  mov     [rbp+1090h+var_10F0], rax
0x14002be2d  inc     rax
0x14002be30  cmp     rax, 1
0x14002be34  ja      short loc_14002BE43
0x14002be36  call    cs:__imp_GetLastError
0x14002be3c  mov     ebx, eax
0x14002be3e  jmp     loc_14002BFFC
0x14002be43  mov     r8d, [rsi+rdi+8]; dwProcessId
0x14002be48  xor     edx, edx; bInheritHandle
0x14002be4a  mov     ecx, 450h; dwDesiredAccess
0x14002be4f  call    cs:__imp_OpenProcess
0x14002be55  mov     r14, rax
0x14002be58  mov     [rbp+1090h+var_10E8], rax
0x14002be5c  inc     rax
0x14002be5f  cmp     rax, 1
0x14002be63  jbe     short loc_14002BE36
0x14002be65  mov     [rbp+1090h+var_10E0], r15
0x14002be69  mov     [rbp+1090h+var_10D8], r14
0x14002be6d  mov     [rsp+1190h+ReturnLength], r12d
0x14002be72  xorps   xmm0, xmm0
0x14002be75  movups  [rsp+1190h+ThreadInformation], xmm0
0x14002be7a  movups  [rbp+1090h+var_1110], xmm0
0x14002be7e  movups  [rbp+1090h+var_1100], xmm0
0x14002be82  or      r13, 0FFFFFFFFFFFFFFFFh
0x14002be86  lea     rax, [rsp+1190h+ReturnLength]
0x14002be8b  mov     [rsp+1190h+lpUserTime], rax; ReturnLength
0x14002be90  lea     r9d, [r13+31h]; ThreadInformationLength
0x14002be94  lea     r8, [rsp+1190h+ThreadInformation]; ThreadInformation
0x14002be99  xor     edx, edx; ThreadInformationClass
0x14002be9b  mov     rcx, r15; ThreadHandle
0x14002be9e  call    cs:__imp_NtQueryInformationThread
0x14002bea4  test    eax, eax
0x14002bea6  jz      short loc_14002BEB7
0x14002bea8  mov     ecx, eax; Status
0x14002beaa  call    cs:__imp_RtlNtStatusToDosError
0x14002beb0  mov     ebx, eax
0x14002beb2  jmp     loc_14002BFC0
0x14002beb7  cmp     qword ptr [rsp+1190h+ThreadInformation+8], r12
0x14002bebc  jnz     short loc_14002BEC8
0x14002bebe  mov     ebx, 0Dh
0x14002bec3  jmp     loc_14002BFEF
0x14002bec8  mov     [rsp+1190h+ProcessInformation], r12
0x14002becd  mov     [rsp+1190h+lpUserTime], r12; ReturnLength
0x14002bed2  mov     r9d, ebx; ProcessInformationLength
0x14002bed5  lea     r8, [rsp+1190h+ProcessInformation]; ProcessInformation
0x14002beda  mov     edx, 1Ah; ProcessInformationClass
0x14002bedf  mov     rcx, r14; ProcessHandle
0x14002bee2  call    cs:__imp_NtQueryInformationProcess
0x14002bee8  test    eax, eax
0x14002beea  js      short loc_14002BF05
0x14002beec  cmp     [rsp+1190h+ProcessInformation], r12
0x14002bef1  jz      short loc_14002BF05
0x14002bef3  mov     esi, 1
0x14002bef8  mov     rax, qword ptr [rsp+1190h+ThreadInformation+8]
0x14002befd  add     rax, 2000h
0x14002bf03  jmp     short loc_14002BF0D
0x14002bf05  mov     esi, r12d
0x14002bf08  mov     rax, qword ptr [rsp+1190h+ThreadInformation+8]
0x14002bf0d  mov     [rsp+1190h+ProcessInformation], rax
0x14002bf12  mov     eax, esi
0x14002bf14  neg     eax
0x14002bf16  sbb     r12, r12
0x14002bf19  and     r12, 0FFFFFFFFFFFFF7C0h
0x14002bf20  lea     rdx, [r12+1870h]
0x14002bf28  lea     rcx, [rsp+1190h+var_1128]
0x14002bf2d  call    ??$make_unique@$$BY0A@E$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@0@_K@Z; utl::make_unique<uchar [0],0>(unsigned __int64)
0x14002bf32  mov     rdi, [rax]
0x14002bf35  mov     qword ptr [rax], 0
0x14002bf3c  mov     rcx, [rsp+1190h+var_1128]; void *
0x14002bf41  test    rcx, rcx
0x14002bf44  jz      short loc_14002BF4B
0x14002bf46  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14002bf4b  test    rdi, rdi
0x14002bf4e  jnz     short loc_14002BF58
0x14002bf50  xor     r12d, r12d
0x14002bf53  jmp     loc_14002BFEF
0x14002bf58  mov     [rsp+1190h+lpUserTime], 0; unsigned int
0x14002bf61  lea     r9, [r12+1870h]; nSize
0x14002bf69  mov     r8, rdi; lpBuffer
0x14002bf6c  mov     rdx, [rsp+1190h+ProcessInformation]; lpBaseAddress
0x14002bf71  mov     rcx, r14; hProcess
0x14002bf74  call    cs:__imp_ReadProcessMemory
0x14002bf7a  xor     r12d, r12d
0x14002bf7d  test    eax, eax
0x14002bf7f  jnz     short loc_14002BF8B
0x14002bf81  call    cs:__imp_GetLastError
0x14002bf87  mov     ebx, eax
0x14002bf89  jmp     short loc_14002BFB8
0x14002bf8b  test    sil, sil
0x14002bf8e  jz      short loc_14002BF98
0x14002bf90  mov     ecx, [rdi+0F6Ch]
0x14002bf96  jmp     short loc_14002BF9F
0x14002bf98  mov     rcx, [rdi+1738h]
0x14002bf9f  lea     rax, [rcx+1]
0x14002bfa3  test    rax, 0FFFFFFFFFFFFFFFEh
0x14002bfa9  jnz     short loc_14002BFB2
0x14002bfab  mov     ebx, 490h
0x14002bfb0  jmp     short loc_14002BFB8
0x14002bfb2  mov     ebx, r12d
0x14002bfb5  mov     r13, rcx
0x14002bfb8  mov     rcx, rdi; void *
0x14002bfbb  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14002bfc0  test    ebx, ebx
0x14002bfc2  jnz     short loc_14002BFEF
0x14002bfc4  lea     rax, [rbp+1090h+var_AE8]
0x14002bfcb  mov     [rsp+1190h+var_1158], rax; union _SOCKADDR_INET *
0x14002bfd0  lea     rax, [rbp+1090h+var_B04]
0x14002bfd7  mov     [rsp+1190h+var_1160], rax; union _SOCKADDR_INET *
0x14002bfdc  lea     r8, [rsp+1190h+var_113C]; int *
0x14002bfe1  mov     rdx, r13; unsigned __int64
0x14002bfe4  lea     rcx, [rbp+1090h+var_10E0]; struct _WCT_CLIENT_HANDLE *
0x14002bfe8  call    ?WctIsSocketRestorable@@YAKPEAU_WCT_CLIENT_HANDLE@@_KPEAHHKPEA_WPEAT_SOCKADDR_INET@@4@Z; WctIsSocketRestorable(_WCT_CLIENT_HANDLE *,unsigned __int64,int *,int,ulong,wchar_t *,_SOCKADDR_INET *,_SOCKADDR_INET *)
0x14002bfed  mov     ebx, eax
0x14002bfef  mov     r13d, 578h
0x14002bff5  jmp     short loc_14002BFFC
0x14002bff7  mov     ebx, 57h ; 'W'
0x14002bffc  lea     rax, [r14+1]
0x14002c000  cmp     rax, 1
0x14002c004  jbe     short loc_14002C010
0x14002c006  mov     rcx, r14; hObject
0x14002c009  call    cs:__imp_CloseHandle
0x14002c00f  nop
0x14002c010  lea     rax, [r15+1]
0x14002c014  cmp     rax, 1
0x14002c018  jbe     short loc_14002C023
0x14002c01a  mov     rcx, r15; hObject
0x14002c01d  call    cs:__imp_CloseHandle
0x14002c023  test    ebx, ebx
0x14002c025  jnz     loc_14002BDB9
0x14002c02b  mov     r8, r13; Size
0x14002c02e  xor     edx, edx; Val
0x14002c030  lea     rcx, [rbp+1090h+Src]; void *
0x14002c034  call    memset_0
0x14002c039  lea     rcx, [rbp+1090h+var_5C0]; void *
0x14002c040  lea     rdx, [rbp+1090h+Src]; Src
0x14002c044  mov     r8, r13; Size
0x14002c047  call    memcpy_0
0x14002c04c  mov     [rbp+1090h+var_5C0], 5780550h
0x14002c056  lea     r8, [rbp+1090h+var_5C0]; struct _WERSVC_MSG *
0x14002c05d  lea     rdx, [rbp+1090h+var_B40]; struct _WERSVC_MSG *
0x14002c064  lea     rcx, aWindowserrorre; "\\WindowsErrorReportingServicePort"
0x14002c06b  call    ?WersvcSendMessage@@YAJPEB_WPEAU_WERSVC_MSG@@1K@Z; WersvcSendMessage(wchar_t const *,_WERSVC_MSG *,_WERSVC_MSG *,ulong)
0x14002c070  test    eax, eax
0x14002c072  jns     short loc_14002C081
0x14002c074  mov     ecx, eax; Status
0x14002c076  call    cs:__imp_RtlNtStatusToDosError
0x14002c07c  jmp     loc_14002BDB7
0x14002c081  cmp     eax, 102h
0x14002c086  jnz     short loc_14002C092
0x14002c088  mov     ebx, 4D3h
0x14002c08d  jmp     loc_14002BDB9
0x14002c092  cmp     [rbp+1090h+var_598], 10000007h
0x14002c09c  jz      short loc_14002C0A8
0x14002c09e  mov     ebx, 32h ; '2'
0x14002c0a3  jmp     loc_14002BDB9
0x14002c0a8  mov     ecx, [rbp+1090h+var_594]
0x14002c0ae  jmp     short loc_14002C076
0x14002c0b0  mov     ebx, 490h
0x14002c0b5  jmp     short loc_14002C0BC
0x14002c0b7  mov     ebx, 57h ; 'W'
0x14002c0bc  mov     ecx, ebx; dwErrCode
0x14002c0be  call    cs:__imp_SetLastError
0x14002c0c4  nop
0x14002c0c5  mov     edi, r12d
0x14002c0c8  test    ebx, ebx
0x14002c0ca  setz    dil
0x14002c0ce  lea     rdx, [r15+1]
0x14002c0d2  cmp     rdx, 1
0x14002c0d6  jbe     short loc_14002C0E1
0x14002c0d8  mov     rcx, r15; hObject
0x14002c0db  call    cs:__imp_CloseHandle
0x14002c0e1  mov     eax, edi
0x14002c0e3  mov     rcx, [rbp+1090h+var_40]
0x14002c0ea  xor     rcx, rsp; StackCookie
0x14002c0ed  call    __security_check_cookie
0x14002c0f2  mov     rbx, [rsp+1190h+arg_10]
0x14002c0fa  add     rsp, 1160h
0x14002c101  pop     r15
0x14002c103  pop     r14
0x14002c105  pop     r13
0x14002c107  pop     r12
0x14002c109  pop     rdi
0x14002c10a  pop     rsi
0x14002c10b  pop     rbp
0x14002c10c  retn
```
