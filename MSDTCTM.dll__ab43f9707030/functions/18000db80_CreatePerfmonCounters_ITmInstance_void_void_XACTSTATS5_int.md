# CreatePerfmonCounters(ITmInstance *,void * *,void * *,XACTSTATS5 * *,int)

- ea: `0x18000db80`
- end: `0x18000e022`
- name: `?CreatePerfmonCounters@@YAXPEAUITmInstance@@PEAPEAX1PEAPEAUXACTSTATS5@@H@Z`
- size: `1186`
- prototype: `void __fastcall(struct ITmInstance *, void **, void **, struct XACTSTATS5 **, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000d3d0`

## callees

- `0x18000db80`
- `0x180015230`
- `0x180086b44`
- `0x1800bd010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x18000dd77`
- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x18000dd77`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18000dd2b`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18000dd2b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000dfe9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000dff7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e005`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e010`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000dfe9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000dff7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e005`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e010`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dcbf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dd42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dd8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ddd6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000de55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000df45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dcbf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dd42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dd8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ddd6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000de55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000df45`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dbc3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dbd1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000def6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000df04`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000df7a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000df88`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dfc5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dbc3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dbd1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000def6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000df04`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000df7a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000df88`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dfc5`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18000df2e`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18000df2e`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18000dbb5`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18000dbb5`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x18000ddc4`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x18000ddc4`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18000dcb6`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18000dcb6`

## string_xrefs

- `0x18000dcf1`: `com\complus\dtc\shared\util\security.cpp`
- `0x18000dc1a`: `com\complus\dtc\dtc\dtcuis\src\uiscore.cpp`
- `0x18000dc6b`: `com\complus\dtc\dtc\dtcuis\src\uiscore.cpp`
- `0x18000ddff`: `com\complus\dtc\dtc\dtcuis\src\uiscore.cpp`
- `0x18000de27`: `com\complus\dtc\dtc\dtcuis\src\uiscore.cpp`
- `0x18000ded9`: `com\complus\dtc\dtc\dtcuis\src\uiscore.cpp`
- `0x18000df5d`: `com\complus\dtc\dtc\dtcuis\src\uiscore.cpp`
- `0x18000dfa8`: `com\complus\dtc\dtc\dtcuis\src\uiscore.cpp`
- `0x18000de2e`: `Error OPENING Perfmon Counter Shared Memory`
- `0x18000de6a`: `CreateMutexW failed`
- `0x18000dda3`: `CreateSharedData : OpenMutexW failed`
- `0x18000dd03`: `going to do CreateMutexW`
- `0x18000dd5c`: `CreateMutexW failed with ERROR_ACCESS_DENIED`
- `0x18000dea1`: `successfully done CreateMutexW`
- `0x18000de4c`: `successfully done OpenMutexW`
- `0x18000dee0`: `Error setting security ACLs on Perfmon Counter shared memory`

## pseudocode

```c
void __fastcall CreatePerfmonCounters(struct ITmInstance *a1, void **a2, void **a3, struct XACTSTATS5 **a4, int a5)
{
  const void *v6; // rcx
  int v10; // eax
  int v11; // eax
  DWORD LastError; // eax
  int v13; // r13d
  signed int v14; // ebp
  int v15; // r15d
  const WCHAR *v16; // rbp
  HANDLE MutexW; // rax
  signed int v18; // eax
  signed int v19; // ebp
  char *v20; // rdx
  unsigned int v21; // r9d
  HANDLE v22; // rax
  signed int v23; // ebx
  unsigned int v24; // r9d
  char *v25; // rdx
  signed int v26; // eax
  int v27; // eax
  struct XACTSTATS5 *v28; // rax
  signed int v29; // eax
  LPVOID v30[3]; // [rsp+30h] [rbp-58h] BYREF
  HANDLE v31; // [rsp+90h] [rbp+8h]
  LPCWSTR lpName; // [rsp+98h] [rbp+10h] BYREF
  LPCWSTR v33; // [rsp+A0h] [rbp+18h] BYREF
  LPVOID pv; // [rsp+A8h] [rbp+20h] BYREF

  v6 = *a4;
  lpName = 0;
  pv = 0;
  v33 = 0;
  v30[0] = 0;
  if ( v6 )
    UnmapViewOfFile(v6);
  if ( *a3 )
    CloseHandle(*a3);
  if ( *a2 )
    CloseHandle(*a2);
  *a4 = 0;
  *a3 = 0;
  *a2 = 0;
  v10 = (*(__int64 (__fastcall **)(struct ITmInstance *, LPCWSTR *, LPVOID *))(*(_QWORD *)a1 + 432LL))(a1, &lpName, &pv);
  if ( v10 < 0 )
  {
    if ( a5 )
      TraceFile(
        v10,
        "Error from pTmInstance->PerfCounterFileMappingName",
        "com\\complus\\dtc\\dtc\\dtcuis\\src\\uiscore.cpp",
        0x1D8u);
    goto LABEL_69;
  }
  v11 = (*(__int64 (__fastcall **)(struct ITmInstance *, LPCWSTR *, LPVOID *))(*(_QWORD *)a1 + 440LL))(a1, &v33, v30);
  if ( v11 < 0 )
  {
    if ( a5 )
      TraceFile(
        v11,
        "Error from pTmInstance->PerfCounterMutexName",
        "com\\complus\\dtc\\dtc\\dtcuis\\src\\uiscore.cpp",
        0x1E2u);
    goto LABEL_69;
  }
  *a2 = CreateFileMappingW((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 4u, 0, 0x1000u, lpName);
  LastError = GetLastError();
  v13 = 0;
  v14 = LastError;
  if ( *a2 )
  {
    LOBYTE(v13) = LastError != 183;
    goto LABEL_15;
  }
  v22 = OpenFileMappingW(2u, 0, lpName);
  *a2 = v22;
  if ( v22 )
  {
LABEL_15:
    v15 = a5;
    v16 = v33;
    if ( a5 )
      TraceFile(0, "going to do CreateMutexW", "com\\complus\\dtc\\shared\\util\\security.cpp", 0x450u);
    *a3 = 0;
    if ( !v16 )
    {
      v19 = -2147024809;
LABEL_64:
      if ( v15 )
        TraceFile(
          v19,
          "Error CREATING Perfmon Counter Mutex",
          "com\\complus\\dtc\\dtc\\dtcuis\\src\\uiscore.cpp",
          0x208u);
      if ( *a2 )
        CloseHandle(*a2);
      *a2 = 0;
      goto LABEL_69;
    }
    MutexW = CreateMutexW(0, 0, v16);
    v31 = MutexW;
    if ( MutexW )
    {
      if ( v15 )
      {
        v24 = 1144;
        v25 = "successfully done CreateMutexW";
        goto LABEL_42;
      }
    }
    else
    {
      if ( GetLastError() != 5 )
      {
        v26 = GetLastError();
        v19 = v26;
        if ( v26 > 0 )
          v19 = (unsigned __int16)v26 | 0x80070000;
        v20 = "CreateMutexW failed";
        v21 = 1136;
LABEL_38:
        TraceFile(v19, v20, "com\\complus\\dtc\\shared\\util\\security.cpp", v21);
        *a3 = 0;
        if ( v19 >= 0 )
          goto LABEL_44;
        goto LABEL_64;
      }
      if ( v15 )
        TraceFile(
          0,
          "CreateMutexW failed with ERROR_ACCESS_DENIED",
          "com\\complus\\dtc\\shared\\util\\security.cpp",
          0x468u);
      MutexW = OpenMutexW(0x100000u, 0, v16);
      v31 = MutexW;
      if ( !MutexW )
      {
        v18 = GetLastError();
        v19 = v18;
        if ( v18 > 0 )
          v19 = (unsigned __int16)v18 | 0x80070000;
        v20 = "CreateSharedData : OpenMutexW failed";
        v21 = 1156;
        goto LABEL_38;
      }
      if ( v15 )
      {
        v24 = 1161;
        v25 = "successfully done OpenMutexW";
LABEL_42:
        TraceFile(0, v25, "com\\complus\\dtc\\shared\\util\\security.cpp", v24);
        MutexW = v31;
      }
    }
    *a3 = MutexW;
LABEL_44:
    if ( v13 && (v27 = SetSddlOnPerfmonResources(a1), v27 < 0) )
    {
      if ( v15 )
        TraceFile(
          v27,
          "Error setting security ACLs on Perfmon Counter shared memory",
          "com\\complus\\dtc\\dtc\\dtcuis\\src\\uiscore.cpp",
          0x218u);
      if ( *a3 )
        CloseHandle(*a3);
      if ( *a2 )
        CloseHandle(*a2);
      *a3 = 0;
      *a2 = 0;
    }
    else
    {
      v28 = (struct XACTSTATS5 *)MapViewOfFile(*a2, 2u, 0, 0, 0x1000u);
      *a4 = v28;
      if ( !v28 )
      {
        if ( v15 )
        {
          v29 = GetLastError();
          if ( v29 > 0 )
            v29 = (unsigned __int16)v29 | 0x80070000;
          TraceFile(
            v29,
            "Error doing MapViewOfFile for Perfmon Counter shared memory",
            "com\\complus\\dtc\\dtc\\dtcuis\\src\\uiscore.cpp",
            0x22Bu);
        }
        if ( *a2 )
          CloseHandle(*a2);
        if ( *a3 )
          CloseHandle(*a3);
        *a2 = 0;
        *a3 = 0;
      }
    }
    goto LABEL_69;
  }
  v23 = GetLastError();
  if ( a5 )
  {
    if ( v14 > 0 )
      v14 = (unsigned __int16)v14 | 0x80070000;
    TraceFile(
      v14,
      "Error CREATING Perfmon Counter Shared Memory",
      "com\\complus\\dtc\\dtc\\dtcuis\\src\\uiscore.cpp",
      0x1FBu);
    if ( v23 > 0 )
      v23 = (unsigned __int16)v23 | 0x80070000;
    TraceFile(
      v23,
      "Error OPENING Perfmon Counter Shared Memory",
      "com\\complus\\dtc\\dtc\\dtcuis\\src\\uiscore.cpp",
      0x1FCu);
  }
LABEL_69:
  CoTaskMemFree((LPVOID)lpName);
  CoTaskMemFree(pv);
  CoTaskMemFree((LPVOID)v33);
  CoTaskMemFree(v30[0]);
}

```

## disassembly

```asm
0x18000db80  mov     rax, rsp
0x18000db83  push    rbx
0x18000db84  push    rsi
0x18000db85  push    rdi
0x18000db86  push    r14
0x18000db88  push    r15
0x18000db8a  sub     rsp, 60h
0x18000db8e  xor     r15d, r15d
0x18000db91  mov     rsi, rcx
0x18000db94  mov     rcx, [r9]; lpBaseAddress
0x18000db97  mov     r14, r9
0x18000db9a  mov     [rax+10h], r15
0x18000db9e  mov     rdi, r8
0x18000dba1  mov     [rax+20h], r15
0x18000dba5  mov     rbx, rdx
0x18000dba8  mov     [rax+18h], r15
0x18000dbac  mov     [rax-58h], r15
0x18000dbb0  test    rcx, rcx
0x18000dbb3  jz      short loc_18000DBBB
0x18000dbb5  call    cs:__imp_UnmapViewOfFile
0x18000dbbb  mov     rcx, [rdi]; hObject
0x18000dbbe  test    rcx, rcx
0x18000dbc1  jz      short loc_18000DBC9
0x18000dbc3  call    cs:__imp_CloseHandle
0x18000dbc9  mov     rcx, [rbx]; hObject
0x18000dbcc  test    rcx, rcx
0x18000dbcf  jz      short loc_18000DBD7
0x18000dbd1  call    cs:__imp_CloseHandle
0x18000dbd7  mov     [r14], r15
0x18000dbda  lea     r8, [rsp+88h+pv]
0x18000dbe2  mov     [rdi], r15
0x18000dbe5  lea     rdx, [rsp+88h+arg_8]
0x18000dbed  mov     [rbx], r15
0x18000dbf0  mov     rcx, rsi
0x18000dbf3  mov     rax, [rsi]
0x18000dbf6  mov     rax, [rax+1B0h]
0x18000dbfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dc02  test    eax, eax
0x18000dc04  jns     short loc_18000DC34
0x18000dc06  cmp     [rsp+88h+arg_20], r15d
0x18000dc0e  jz      loc_18000DFE1
0x18000dc14  mov     r9d, 1D8h; unsigned int
0x18000dc1a  lea     r8, aComComplusDtcD_84; "com\\complus\\dtc\\dtc\\dtcuis\\src\\ui"...
0x18000dc21  lea     rdx, aErrorFromPtmin_2; "Error from pTmInstance->PerfCounterFile"...
0x18000dc28  mov     ecx, eax; int
0x18000dc2a  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x18000dc2f  jmp     loc_18000DFE1
0x18000dc34  mov     rax, [rsi]
0x18000dc37  lea     r8, [rsp+88h+var_58]
0x18000dc3c  lea     rdx, [rsp+88h+arg_10]
0x18000dc44  mov     rcx, rsi
0x18000dc47  mov     rax, [rax+1B8h]
0x18000dc4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dc53  test    eax, eax
0x18000dc55  jns     short loc_18000DC85
0x18000dc57  cmp     [rsp+88h+arg_20], r15d
0x18000dc5f  jz      loc_18000DFE1
0x18000dc65  mov     r9d, 1E2h; unsigned int
0x18000dc6b  lea     r8, aComComplusDtcD_84; "com\\complus\\dtc\\dtc\\dtcuis\\src\\ui"...
0x18000dc72  lea     rdx, aErrorFromPtmin; "Error from pTmInstance->PerfCounterMute"...
0x18000dc79  mov     ecx, eax; int
0x18000dc7b  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x18000dc80  jmp     loc_18000DFE1
0x18000dc85  mov     rax, [rsp+88h+arg_8]
0x18000dc8d  xor     r9d, r9d; dwMaximumSizeHigh
0x18000dc90  mov     [rsp+88h+lpName], rax; lpName
0x18000dc95  xor     edx, edx; lpFileMappingAttributes
0x18000dc97  mov     [rsp+88h+var_30], rbp
0x18000dc9c  mov     rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x18000dca3  mov     r8d, 4; flProtect
0x18000dca9  mov     [rsp+88h+dwMaximumSizeLow], 1000h; dwMaximumSizeLow
0x18000dcb1  mov     [rsp+88h+var_40], r13
0x18000dcb6  call    cs:__imp_CreateFileMappingW
0x18000dcbc  mov     [rbx], rax
0x18000dcbf  call    cs:__imp_GetLastError
0x18000dcc5  mov     r13d, r15d
0x18000dcc8  mov     ebp, eax
0x18000dcca  cmp     [rbx], r15
0x18000dccd  jz      loc_18000DDB5
0x18000dcd3  cmp     eax, 0B7h
0x18000dcd8  setnz   r13b
0x18000dcdc  mov     r15d, [rsp+88h+arg_20]
0x18000dce4  mov     rbp, [rsp+88h+arg_10]
0x18000dcec  mov     [rsp+88h+var_38], r12
0x18000dcf1  lea     r12, aComComplusDtcS_7; "com\\complus\\dtc\\shared\\util\\securi"...
0x18000dcf8  test    r15d, r15d
0x18000dcfb  jz      short loc_18000DD14
0x18000dcfd  mov     r9d, 450h; unsigned int
0x18000dd03  lea     rdx, aGoingToDoCreat; "going to do CreateMutexW"
0x18000dd0a  mov     r8, r12; char *
0x18000dd0d  xor     ecx, ecx; int
0x18000dd0f  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x18000dd14  mov     qword ptr [rdi], 0
0x18000dd1b  test    rbp, rbp
0x18000dd1e  jz      loc_18000DF98
0x18000dd24  mov     r8, rbp; lpName
0x18000dd27  xor     edx, edx; bInitialOwner
0x18000dd29  xor     ecx, ecx; lpMutexAttributes
0x18000dd2b  call    cs:__imp_CreateMutexW
0x18000dd31  mov     [rsp+88h+arg_0], rax
0x18000dd39  test    rax, rax
0x18000dd3c  jnz     loc_18000DE96
0x18000dd42  call    cs:__imp_GetLastError
0x18000dd48  cmp     eax, 5
0x18000dd4b  jnz     loc_18000DE55
0x18000dd51  test    r15d, r15d
0x18000dd54  jz      short loc_18000DD6D
0x18000dd56  mov     r9d, 468h; unsigned int
0x18000dd5c  lea     rdx, aCreatemutexwFa_0; "CreateMutexW failed with ERROR_ACCESS_D"...
0x18000dd63  mov     r8, r12; char *
0x18000dd66  xor     ecx, ecx; int
0x18000dd68  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x18000dd6d  mov     r8, rbp; lpName
0x18000dd70  xor     edx, edx; bInheritHandle
0x18000dd72  mov     ecx, 100000h; dwDesiredAccess
0x18000dd77  call    cs:__imp_OpenMutexW
0x18000dd7d  mov     [rsp+88h+arg_0], rax
0x18000dd85  test    rax, rax
0x18000dd88  jnz     loc_18000DE41
0x18000dd8e  call    cs:__imp_GetLastError
0x18000dd94  mov     ebp, eax
0x18000dd96  test    eax, eax
0x18000dd98  jle     short loc_18000DDA3
0x18000dd9a  movzx   ebp, ax
0x18000dd9d  or      ebp, 80070000h
0x18000dda3  lea     rdx, aCreatesharedda; "CreateSharedData : OpenMutexW failed"
0x18000ddaa  mov     r9d, 484h
0x18000ddb0  jmp     loc_18000DE77
0x18000ddb5  mov     r8, [rsp+88h+arg_8]; lpName
0x18000ddbd  xor     edx, edx; bInheritHandle
0x18000ddbf  mov     ecx, 2; dwDesiredAccess
0x18000ddc4  call    cs:__imp_OpenFileMappingW
0x18000ddca  mov     [rbx], rax
0x18000ddcd  test    rax, rax
0x18000ddd0  jnz     loc_18000DCDC
0x18000ddd6  call    cs:__imp_GetLastError
0x18000dddc  mov     ebx, eax
0x18000ddde  cmp     [rsp+88h+arg_20], r13d
0x18000dde6  jz      loc_18000DFD7
0x18000ddec  test    ebp, ebp
0x18000ddee  jle     short loc_18000DDF9
0x18000ddf0  movzx   ebp, bp
0x18000ddf3  or      ebp, 80070000h
0x18000ddf9  mov     r9d, 1FBh; unsigned int
0x18000ddff  lea     r8, aComComplusDtcD_84; "com\\complus\\dtc\\dtc\\dtcuis\\src\\ui"...
0x18000de06  lea     rdx, aErrorCreatingP; "Error CREATING Perfmon Counter Shared M"...
0x18000de0d  mov     ecx, ebp; int
0x18000de0f  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x18000de14  test    ebx, ebx
0x18000de16  jle     short loc_18000DE21
0x18000de18  movzx   ebx, bx
0x18000de1b  or      ebx, 80070000h
0x18000de21  mov     r9d, 1FCh; unsigned int
0x18000de27  lea     r8, aComComplusDtcD_84; "com\\complus\\dtc\\dtc\\dtcuis\\src\\ui"...
0x18000de2e  lea     rdx, aErrorOpeningPe; "Error OPENING Perfmon Counter Shared Me"...
0x18000de35  mov     ecx, ebx; int
0x18000de37  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x18000de3c  jmp     loc_18000DFD7
0x18000de41  test    r15d, r15d
0x18000de44  jz      short loc_18000DEBA
0x18000de46  mov     r9d, 489h
0x18000de4c  lea     rdx, aSuccessfullyDo_0; "successfully done OpenMutexW"
0x18000de53  jmp     short loc_18000DEA8
0x18000de55  call    cs:__imp_GetLastError
0x18000de5b  mov     ebp, eax
0x18000de5d  test    eax, eax
0x18000de5f  jle     short loc_18000DE6A
0x18000de61  movzx   ebp, ax
0x18000de64  or      ebp, 80070000h
0x18000de6a  lea     rdx, aCreatemutexwFa; "CreateMutexW failed"
0x18000de71  mov     r9d, 470h; unsigned int
0x18000de77  mov     ecx, ebp; int
0x18000de79  mov     r8, r12; char *
0x18000de7c  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x18000de81  mov     rax, [rsp+88h+arg_0]
0x18000de89  mov     [rdi], rax
0x18000de8c  test    ebp, ebp
0x18000de8e  js      loc_18000DF9D
0x18000de94  jmp     short loc_18000DEBD
0x18000de96  test    r15d, r15d
0x18000de99  jz      short loc_18000DEBA
0x18000de9b  mov     r9d, 478h; unsigned int
0x18000dea1  lea     rdx, aSuccessfullyDo; "successfully done CreateMutexW"
0x18000dea8  mov     r8, r12; char *
0x18000deab  xor     ecx, ecx; int
0x18000dead  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x18000deb2  mov     rax, [rsp+88h+arg_0]
0x18000deba  mov     [rdi], rax
0x18000debd  test    r13d, r13d
0x18000dec0  jz      short loc_18000DF17
0x18000dec2  mov     rcx, rsi; struct ITmInstance *
0x18000dec5  call    ?SetSddlOnPerfmonResources@@YAJPEAUITmInstance@@@Z; SetSddlOnPerfmonResources(ITmInstance *)
0x18000deca  test    eax, eax
0x18000decc  jns     short loc_18000DF17
0x18000dece  test    r15d, r15d
0x18000ded1  jz      short loc_18000DEEE
0x18000ded3  mov     r9d, 218h; unsigned int
0x18000ded9  lea     r8, aComComplusDtcD_84; "com\\complus\\dtc\\dtc\\dtcuis\\src\\ui"...
0x18000dee0  lea     rdx, aErrorSettingSe; "Error setting security ACLs on Perfmon "...
0x18000dee7  mov     ecx, eax; int
0x18000dee9  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x18000deee  mov     rcx, [rdi]; hObject
0x18000def1  test    rcx, rcx
0x18000def4  jz      short loc_18000DEFC
0x18000def6  call    cs:__imp_CloseHandle
0x18000defc  mov     rcx, [rbx]; hObject
0x18000deff  test    rcx, rcx
0x18000df02  jz      short loc_18000DF0A
0x18000df04  call    cs:__imp_CloseHandle
0x18000df0a  xor     eax, eax
0x18000df0c  mov     [rdi], rax
0x18000df0f  mov     [rbx], rax
0x18000df12  jmp     loc_18000DFD2
0x18000df17  mov     rcx, [rbx]; hFileMappingObject
0x18000df1a  xor     r9d, r9d; dwFileOffsetLow
0x18000df1d  xor     r8d, r8d; dwFileOffsetHigh
0x18000df20  mov     qword ptr [rsp+88h+dwMaximumSizeLow], 1000h; dwNumberOfBytesToMap
0x18000df29  mov     edx, 2; dwDesiredAccess
0x18000df2e  call    cs:__imp_MapViewOfFile
0x18000df34  mov     [r14], rax
0x18000df37  test    rax, rax
0x18000df3a  jnz     loc_18000DFD2
0x18000df40  test    r15d, r15d
0x18000df43  jz      short loc_18000DF72
0x18000df45  call    cs:__imp_GetLastError
0x18000df4b  test    eax, eax
0x18000df4d  jle     short loc_18000DF57
0x18000df4f  movzx   eax, ax
0x18000df52  or      eax, 80070000h
0x18000df57  mov     r9d, 22Bh; unsigned int
0x18000df5d  lea     r8, aComComplusDtcD_84; "com\\complus\\dtc\\dtc\\dtcuis\\src\\ui"...
0x18000df64  lea     rdx, aErrorDoingMapv; "Error doing MapViewOfFile for Perfmon C"...
0x18000df6b  mov     ecx, eax; int
0x18000df6d  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x18000df72  mov     rcx, [rbx]; hObject
0x18000df75  test    rcx, rcx
0x18000df78  jz      short loc_18000DF80
0x18000df7a  call    cs:__imp_CloseHandle
0x18000df80  mov     rcx, [rdi]; hObject
0x18000df83  test    rcx, rcx
0x18000df86  jz      short loc_18000DF8E
0x18000df88  call    cs:__imp_CloseHandle
0x18000df8e  xor     eax, eax
0x18000df90  mov     [rbx], rax
0x18000df93  mov     [rdi], rax
0x18000df96  jmp     short loc_18000DFD2
0x18000df98  mov     ebp, 80070057h
0x18000df9d  test    r15d, r15d
0x18000dfa0  jz      short loc_18000DFBD
0x18000dfa2  mov     r9d, 208h; unsigned int
0x18000dfa8  lea     r8, aComComplusDtcD_84; "com\\complus\\dtc\\dtc\\dtcuis\\src\\ui"...
0x18000dfaf  lea     rdx, aErrorCreatingP_0; "Error CREATING Perfmon Counter Mutex"
0x18000dfb6  mov     ecx, ebp; int
0x18000dfb8  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x18000dfbd  mov     rcx, [rbx]; hObject
0x18000dfc0  test    rcx, rcx
0x18000dfc3  jz      short loc_18000DFCB
0x18000dfc5  call    cs:__imp_CloseHandle
0x18000dfcb  mov     qword ptr [rbx], 0
0x18000dfd2  mov     r12, [rsp+88h+var_38]
0x18000dfd7  mov     rbp, [rsp+88h+var_30]
0x18000dfdc  mov     r13, [rsp+88h+var_40]
0x18000dfe1  mov     rcx, [rsp+88h+arg_8]; pv
0x18000dfe9  call    cs:__imp_CoTaskMemFree
0x18000dfef  mov     rcx, [rsp+88h+pv]; pv
0x18000dff7  call    cs:__imp_CoTaskMemFree
0x18000dffd  mov     rcx, [rsp+88h+arg_10]; pv
0x18000e005  call    cs:__imp_CoTaskMemFree
0x18000e00b  mov     rcx, [rsp+88h+var_58]; pv
0x18000e010  call    cs:__imp_CoTaskMemFree
0x18000e016  add     rsp, 60h
0x18000e01a  pop     r15
0x18000e01c  pop     r14
0x18000e01e  pop     rdi
0x18000e01f  pop     rsi
0x18000e020  pop     rbx
0x18000e021  retn
```
