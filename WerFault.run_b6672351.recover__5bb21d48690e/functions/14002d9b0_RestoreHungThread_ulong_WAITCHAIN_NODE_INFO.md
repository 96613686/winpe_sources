# RestoreHungThread(ulong,_WAITCHAIN_NODE_INFO *)

- ea: `0x14002d9b0`
- end: `0x14002de8e`
- name: `?RestoreHungThread@@YAHKPEAU_WAITCHAIN_NODE_INFO@@@Z`
- size: `1246`
- prototype: `__int64 __fastcall(unsigned int, struct _WAITCHAIN_NODE_INFO *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, loader_planting, service_task`

## callers

- `0x140029e40`

## callees

- `0x140002490`
- `0x140002748`
- `0x1400030f8`
- `0x14002d9b0`
- `0x14002de94`
- `0x140031694`
- `0x140036b28`
- `0x14005f510`
- `0x14005f588`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002dad7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002db6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002dcdd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002dad7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002db6e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002dcdd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14002de32`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14002de32`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessTimes` at `0x14002db08`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessTimes` at `0x14002db08`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x14002db52`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x14002db52`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002dd6b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002dd85`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002de55`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002dd6b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002dd85`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002de55`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x14002dcca`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x14002dcca`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x14002daba`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x14002db8d`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x14002daba`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x14002db8d`
- `ntdll!NtQueryInformationProcess` at `0x14002dc32`
- `ntdll!NtQueryInformationProcess` at `0x14002dc32`
- `ntdll!NtQueryInformationThread` at `0x14002dbe2`
- `ntdll!NtQueryInformationThread` at `0x14002dbe2`
- `ntdll!RtlNtStatusToDosError` at `0x14002dbf4`
- `ntdll!RtlNtStatusToDosError` at `0x14002dde4`
- `ntdll!RtlNtStatusToDosError` at `0x14002dbf4`
- `ntdll!RtlNtStatusToDosError` at `0x14002dde4`

## string_xrefs

- `0x14002ddd2`: `\WindowsErrorReportingServicePort`

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
0x14002d9b0  mov     [rsp-8+arg_10], rbx
0x14002d9b5  push    rbp
0x14002d9b6  push    rsi
0x14002d9b7  push    rdi
0x14002d9b8  push    r12
0x14002d9ba  push    r13
0x14002d9bc  push    r14
0x14002d9be  push    r15
0x14002d9c0  lea     rbp, [rsp-1060h]
0x14002d9c8  mov     eax, 1160h
0x14002d9cd  call    _alloca_probe
0x14002d9d2  sub     rsp, rax
0x14002d9d5  mov     rax, cs:__security_cookie
0x14002d9dc  xor     rax, rsp
0x14002d9df  mov     [rbp+1090h+var_40], rax
0x14002d9e6  mov     rdi, rdx
0x14002d9e9  mov     r14d, ecx
0x14002d9ec  xor     r12d, r12d
0x14002d9ef  mov     r15d, r12d
0x14002d9f2  mov     qword ptr [rsp+1190h+CreationTime.dwLowDateTime], r12
0x14002d9f7  mov     qword ptr [rsp+1190h+ExitTime.dwLowDateTime], r12
0x14002d9fc  mov     r13d, 578h
0x14002da02  mov     r8d, r13d; Size
0x14002da05  xor     edx, edx; Val
0x14002da07  lea     rcx, [rbp+1090h+var_B40]; void *
0x14002da0e  call    memset_0
0x14002da13  mov     r8d, r13d; Size
0x14002da16  xor     edx, edx; Val
0x14002da18  lea     rcx, [rbp+1090h+var_5C0]; void *
0x14002da1f  call    memset_0
0x14002da24  test    rdi, rdi
0x14002da27  jz      loc_14002DE2B
0x14002da2d  lea     eax, [r14-2]
0x14002da31  cmp     eax, 0Eh
0x14002da34  ja      loc_14002DE2B
0x14002da3a  imul    rsi, rax, 118h
0x14002da41  lea     ebx, [r12+8]
0x14002da46  cmp     [rsi+rdi], ebx
0x14002da49  jnz     loc_14002DE2B
0x14002da4f  lea     ecx, [r14-1]
0x14002da53  imul    rax, rcx, 118h
0x14002da5a  cmp     dword ptr [rax+rdi], 0Bh
0x14002da5e  jnz     loc_14002DE24
0x14002da64  cmp     [rax+rdi+110h], r12d
0x14002da6c  jz      loc_14002DE24
0x14002da72  mov     r8d, r13d; Size
0x14002da75  xor     edx, edx; Val
0x14002da77  lea     rcx, [rbp+1090h+Src]; void *
0x14002da7b  call    memset_0
0x14002da80  lea     rcx, [rbp+1090h+var_B40]; void *
0x14002da87  lea     rdx, [rbp+1090h+Src]; Src
0x14002da8b  mov     r8d, r13d; Size
0x14002da8e  call    memcpy_0
0x14002da93  mov     [rbp+1090h+var_B40], 5780550h
0x14002da9d  mov     [rbp+1090h+var_B18], 10000007h
0x14002daa7  mov     r8d, [rsi+rdi+8]; dwProcessId
0x14002daac  mov     [rbp+1090h+var_B10], r8d
0x14002dab3  xor     edx, edx; bInheritHandle
0x14002dab5  mov     ecx, 400h; dwDesiredAccess
0x14002daba  call    cs:__imp_OpenProcess
0x14002dac1  nop     dword ptr [rax+rax+00h]
0x14002dac6  mov     rcx, rax; hProcess
0x14002dac9  mov     [rsp+1190h+hObject], rax
0x14002dace  inc     rax
0x14002dad1  cmp     rax, 1
0x14002dad5  ja      short loc_14002DAEF
0x14002dad7  call    cs:__imp_GetLastError
0x14002dade  nop     dword ptr [rax+rax+00h]
0x14002dae3  mov     ebx, eax
0x14002dae5  mov     r15, [rsp+1190h+hObject]
0x14002daea  jmp     loc_14002DE30
0x14002daef  lea     rax, [rsp+1190h+ExitTime]
0x14002daf4  mov     [rsp+1190h+lpUserTime], rax; lpUserTime
0x14002daf9  lea     r9, [rsp+1190h+ExitTime]; lpKernelTime
0x14002dafe  lea     r8, [rsp+1190h+ExitTime]; lpExitTime
0x14002db03  lea     rdx, [rsp+1190h+CreationTime]; lpCreationTime
0x14002db08  call    cs:__imp_GetProcessTimes
0x14002db0f  nop     dword ptr [rax+rax+00h]
0x14002db14  test    eax, eax
0x14002db16  jz      short loc_14002DAD7
0x14002db18  mov     eax, [rsp+1190h+CreationTime.dwLowDateTime]
0x14002db1c  mov     [rbp+1090h+var_B0C], eax
0x14002db22  mov     eax, [rsp+1190h+CreationTime.dwHighDateTime]
0x14002db26  mov     [rbp+1090h+var_B08], eax
0x14002db2c  mov     [rsp+1190h+var_113C], r12d
0x14002db31  mov     r15, r12
0x14002db34  mov     r14, r12
0x14002db37  xorps   xmm0, xmm0
0x14002db3a  movdqu  [rbp+1090h+var_10D0], xmm0
0x14002db3f  cmp     [rsi+rdi], ebx
0x14002db42  jnz     loc_14002DD59
0x14002db48  mov     r8d, [rsi+rdi+0Ch]; dwThreadId
0x14002db4d  xor     edx, edx; bInheritHandle
0x14002db4f  lea     ecx, [rdx+40h]; dwDesiredAccess
0x14002db52  call    cs:__imp_OpenThread
0x14002db59  nop     dword ptr [rax+rax+00h]
0x14002db5e  mov     r15, rax
0x14002db61  mov     [rbp+1090h+var_10F0], rax
0x14002db65  inc     rax
0x14002db68  cmp     rax, 1
0x14002db6c  ja      short loc_14002DB81
0x14002db6e  call    cs:__imp_GetLastError
0x14002db75  nop     dword ptr [rax+rax+00h]
0x14002db7a  mov     ebx, eax
0x14002db7c  jmp     loc_14002DD5E
0x14002db81  mov     r8d, [rsi+rdi+8]; dwProcessId
0x14002db86  xor     edx, edx; bInheritHandle
0x14002db88  mov     ecx, 450h; dwDesiredAccess
0x14002db8d  call    cs:__imp_OpenProcess
0x14002db94  nop     dword ptr [rax+rax+00h]
0x14002db99  mov     r14, rax
0x14002db9c  mov     [rbp+1090h+var_10E8], rax
0x14002dba0  inc     rax
0x14002dba3  cmp     rax, 1
0x14002dba7  jbe     short loc_14002DB6E
0x14002dba9  mov     [rbp+1090h+var_10E0], r15
0x14002dbad  mov     [rbp+1090h+var_10D8], r14
0x14002dbb1  mov     [rsp+1190h+ReturnLength], r12d
0x14002dbb6  xorps   xmm0, xmm0
0x14002dbb9  movups  [rsp+1190h+ThreadInformation], xmm0
0x14002dbbe  movups  [rbp+1090h+var_1110], xmm0
0x14002dbc2  movups  [rbp+1090h+var_1100], xmm0
0x14002dbc6  or      r13, 0FFFFFFFFFFFFFFFFh
0x14002dbca  lea     rax, [rsp+1190h+ReturnLength]
0x14002dbcf  mov     [rsp+1190h+lpUserTime], rax; ReturnLength
0x14002dbd4  lea     r9d, [r13+31h]; ThreadInformationLength
0x14002dbd8  lea     r8, [rsp+1190h+ThreadInformation]; ThreadInformation
0x14002dbdd  xor     edx, edx; ThreadInformationClass
0x14002dbdf  mov     rcx, r15; ThreadHandle
0x14002dbe2  call    cs:__imp_NtQueryInformationThread
0x14002dbe9  nop     dword ptr [rax+rax+00h]
0x14002dbee  test    eax, eax
0x14002dbf0  jz      short loc_14002DC07
0x14002dbf2  mov     ecx, eax; Status
0x14002dbf4  call    cs:__imp_RtlNtStatusToDosError
0x14002dbfb  nop     dword ptr [rax+rax+00h]
0x14002dc00  mov     ebx, eax
0x14002dc02  jmp     loc_14002DD22
0x14002dc07  cmp     qword ptr [rsp+1190h+ThreadInformation+8], r12
0x14002dc0c  jnz     short loc_14002DC18
0x14002dc0e  mov     ebx, 0Dh
0x14002dc13  jmp     loc_14002DD51
0x14002dc18  mov     [rsp+1190h+ProcessInformation], r12
0x14002dc1d  mov     [rsp+1190h+lpUserTime], r12; ReturnLength
0x14002dc22  mov     r9d, ebx; ProcessInformationLength
0x14002dc25  lea     r8, [rsp+1190h+ProcessInformation]; ProcessInformation
0x14002dc2a  mov     edx, 1Ah; ProcessInformationClass
0x14002dc2f  mov     rcx, r14; ProcessHandle
0x14002dc32  call    cs:__imp_NtQueryInformationProcess
0x14002dc39  nop     dword ptr [rax+rax+00h]
0x14002dc3e  test    eax, eax
0x14002dc40  js      short loc_14002DC5B
0x14002dc42  cmp     [rsp+1190h+ProcessInformation], r12
0x14002dc47  jz      short loc_14002DC5B
0x14002dc49  mov     esi, 1
0x14002dc4e  mov     rax, qword ptr [rsp+1190h+ThreadInformation+8]
0x14002dc53  add     rax, 2000h
0x14002dc59  jmp     short loc_14002DC63
0x14002dc5b  mov     esi, r12d
0x14002dc5e  mov     rax, qword ptr [rsp+1190h+ThreadInformation+8]
0x14002dc63  mov     [rsp+1190h+ProcessInformation], rax
0x14002dc68  mov     eax, esi
0x14002dc6a  neg     eax
0x14002dc6c  sbb     r12, r12
0x14002dc6f  and     r12, 0FFFFFFFFFFFFF7C0h
0x14002dc76  lea     rdx, [r12+1870h]
0x14002dc7e  lea     rcx, [rsp+1190h+var_1128]
0x14002dc83  call    ??$make_unique@$$BY0A@E$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@0@_K@Z; utl::make_unique<uchar [0],0>(unsigned __int64)
0x14002dc88  mov     rdi, [rax]
0x14002dc8b  mov     qword ptr [rax], 0
0x14002dc92  mov     rcx, [rsp+1190h+var_1128]; void *
0x14002dc97  test    rcx, rcx
0x14002dc9a  jz      short loc_14002DCA1
0x14002dc9c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14002dca1  test    rdi, rdi
0x14002dca4  jnz     short loc_14002DCAE
0x14002dca6  xor     r12d, r12d
0x14002dca9  jmp     loc_14002DD51
0x14002dcae  mov     [rsp+1190h+lpUserTime], 0; unsigned int
0x14002dcb7  lea     r9, [r12+1870h]; nSize
0x14002dcbf  mov     r8, rdi; lpBuffer
0x14002dcc2  mov     rdx, [rsp+1190h+ProcessInformation]; lpBaseAddress
0x14002dcc7  mov     rcx, r14; hProcess
0x14002dcca  call    cs:__imp_ReadProcessMemory
0x14002dcd1  nop     dword ptr [rax+rax+00h]
0x14002dcd6  xor     r12d, r12d
0x14002dcd9  test    eax, eax
0x14002dcdb  jnz     short loc_14002DCED
0x14002dcdd  call    cs:__imp_GetLastError
0x14002dce4  nop     dword ptr [rax+rax+00h]
0x14002dce9  mov     ebx, eax
0x14002dceb  jmp     short loc_14002DD1A
0x14002dced  test    sil, sil
0x14002dcf0  jz      short loc_14002DCFA
0x14002dcf2  mov     ecx, [rdi+0F6Ch]
0x14002dcf8  jmp     short loc_14002DD01
0x14002dcfa  mov     rcx, [rdi+1738h]
0x14002dd01  lea     rax, [rcx+1]
0x14002dd05  test    rax, 0FFFFFFFFFFFFFFFEh
0x14002dd0b  jnz     short loc_14002DD14
0x14002dd0d  mov     ebx, 490h
0x14002dd12  jmp     short loc_14002DD1A
0x14002dd14  mov     ebx, r12d
0x14002dd17  mov     r13, rcx
0x14002dd1a  mov     rcx, rdi; void *
0x14002dd1d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14002dd22  test    ebx, ebx
0x14002dd24  jnz     short loc_14002DD51
0x14002dd26  lea     rax, [rbp+1090h+var_AE8]
0x14002dd2d  mov     [rsp+1190h+var_1158], rax; union _SOCKADDR_INET *
0x14002dd32  lea     rax, [rbp+1090h+var_B04]
0x14002dd39  mov     [rsp+1190h+var_1160], rax; union _SOCKADDR_INET *
0x14002dd3e  lea     r8, [rsp+1190h+var_113C]; int *
0x14002dd43  mov     rdx, r13; unsigned __int64
0x14002dd46  lea     rcx, [rbp+1090h+var_10E0]; struct _WCT_CLIENT_HANDLE *
0x14002dd4a  call    ?WctIsSocketRestorable@@YAKPEAU_WCT_CLIENT_HANDLE@@_KPEAHHKPEA_WPEAT_SOCKADDR_INET@@4@Z; WctIsSocketRestorable(_WCT_CLIENT_HANDLE *,unsigned __int64,int *,int,ulong,wchar_t *,_SOCKADDR_INET *,_SOCKADDR_INET *)
0x14002dd4f  mov     ebx, eax
0x14002dd51  mov     r13d, 578h
0x14002dd57  jmp     short loc_14002DD5E
0x14002dd59  mov     ebx, 57h ; 'W'
0x14002dd5e  lea     rax, [r14+1]
0x14002dd62  cmp     rax, 1
0x14002dd66  jbe     short loc_14002DD78
0x14002dd68  mov     rcx, r14; hObject
0x14002dd6b  call    cs:__imp_CloseHandle
0x14002dd72  nop     dword ptr [rax+rax+00h]
0x14002dd77  nop
0x14002dd78  lea     rax, [r15+1]
0x14002dd7c  cmp     rax, 1
0x14002dd80  jbe     short loc_14002DD91
0x14002dd82  mov     rcx, r15; hObject
0x14002dd85  call    cs:__imp_CloseHandle
0x14002dd8c  nop     dword ptr [rax+rax+00h]
0x14002dd91  test    ebx, ebx
0x14002dd93  jnz     loc_14002DAE5
0x14002dd99  mov     r8, r13; Size
0x14002dd9c  xor     edx, edx; Val
0x14002dd9e  lea     rcx, [rbp+1090h+Src]; void *
0x14002dda2  call    memset_0
0x14002dda7  lea     rcx, [rbp+1090h+var_5C0]; void *
0x14002ddae  lea     rdx, [rbp+1090h+Src]; Src
0x14002ddb2  mov     r8, r13; Size
0x14002ddb5  call    memcpy_0
0x14002ddba  mov     [rbp+1090h+var_5C0], 5780550h
0x14002ddc4  lea     r8, [rbp+1090h+var_5C0]; struct _WERSVC_MSG *
0x14002ddcb  lea     rdx, [rbp+1090h+var_B40]; struct _WERSVC_MSG *
0x14002ddd2  lea     rcx, aWindowserrorre; "\\WindowsErrorReportingServicePort"
0x14002ddd9  call    ?WersvcSendMessage@@YAJPEB_WPEAU_WERSVC_MSG@@1K@Z; WersvcSendMessage(wchar_t const *,_WERSVC_MSG *,_WERSVC_MSG *,ulong)
0x14002ddde  test    eax, eax
0x14002dde0  jns     short loc_14002DDF5
0x14002dde2  mov     ecx, eax; Status
0x14002dde4  call    cs:__imp_RtlNtStatusToDosError
0x14002ddeb  nop     dword ptr [rax+rax+00h]
0x14002ddf0  jmp     loc_14002DAE3
0x14002ddf5  cmp     eax, 102h
0x14002ddfa  jnz     short loc_14002DE06
0x14002ddfc  mov     ebx, 4D3h
0x14002de01  jmp     loc_14002DAE5
0x14002de06  cmp     [rbp+1090h+var_598], 10000007h
0x14002de10  jz      short loc_14002DE1C
0x14002de12  mov     ebx, 32h ; '2'
0x14002de17  jmp     loc_14002DAE5
0x14002de1c  mov     ecx, [rbp+1090h+var_594]
0x14002de22  jmp     short loc_14002DDE4
0x14002de24  mov     ebx, 490h
0x14002de29  jmp     short loc_14002DE30
0x14002de2b  mov     ebx, 57h ; 'W'
0x14002de30  mov     ecx, ebx; dwErrCode
0x14002de32  call    cs:__imp_SetLastError
0x14002de39  nop     dword ptr [rax+rax+00h]
0x14002de3e  nop
0x14002de3f  mov     edi, r12d
0x14002de42  test    ebx, ebx
0x14002de44  setz    dil
0x14002de48  lea     rdx, [r15+1]
0x14002de4c  cmp     rdx, 1
0x14002de50  jbe     short loc_14002DE61
0x14002de52  mov     rcx, r15; hObject
0x14002de55  call    cs:__imp_CloseHandle
0x14002de5c  nop     dword ptr [rax+rax+00h]
0x14002de61  mov     eax, edi
0x14002de63  mov     rcx, [rbp+1090h+var_40]
0x14002de6a  xor     rcx, rsp; StackCookie
0x14002de6d  call    __security_check_cookie
0x14002de72  mov     rbx, [rsp+1190h+arg_10]
0x14002de7a  add     rsp, 1160h
0x14002de81  pop     r15
0x14002de83  pop     r14
0x14002de85  pop     r13
0x14002de87  pop     r12
0x14002de89  pop     rdi
0x14002de8a  pop     rsi
0x14002de8b  pop     rbp
0x14002de8c  retn
```
