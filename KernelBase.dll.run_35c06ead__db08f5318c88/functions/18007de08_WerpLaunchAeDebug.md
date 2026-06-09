# WerpLaunchAeDebug

- ea: `0x18007de08`
- end: `0x18007e7a6`
- name: `WerpLaunchAeDebug`
- size: `2462`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `reparse_path, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180117b10`

## callees

- `0x180012f90`
- `0x1800134a0`
- `0x180048f30`
- `0x18007dd40`
- `0x18007de08`
- `0x18007e7b0`
- `0x18007ed6c`
- `0x18007ee00`
- `0x18007ee60`
- `0x18007f610`
- `0x1800ae1a0`
- `0x1800e23d0`
- `0x1800f5640`
- `0x1801177b0`
- `0x180127568`
- `0x18012d119`
- `0x180188f10`

## import_xrefs

- `ntdll!RtlSetLastWin32Error` at `0x18007e489`
- `ntdll!RtlSetLastWin32Error` at `0x18007e489`
- `ntdll!RtlSetCurrentTransaction` at `0x18007e2c7`
- `ntdll!RtlSetCurrentTransaction` at `0x18007e6ed`
- `ntdll!RtlSetCurrentTransaction` at `0x18007e2c7`
- `ntdll!RtlSetCurrentTransaction` at `0x18007e6ed`
- `ntdll!NtQuerySystemInformation` at `0x18007dfcd`
- `ntdll!NtQuerySystemInformation` at `0x18007dfcd`
- `ntdll!RtlGetCurrentTransaction` at `0x18007e2bb`
- `ntdll!RtlGetCurrentTransaction` at `0x18007e2bb`
- `ntdll!RtlDetermineDosPathNameType_U` at `0x18007e1ed`
- `ntdll!RtlDetermineDosPathNameType_U` at `0x18007e1ed`
- `ntdll!DbgPrintEx` at `0x18007e24f`
- `ntdll!DbgPrintEx` at `0x18007e2b0`
- `ntdll!DbgPrintEx` at `0x18007e3ad`
- `ntdll!DbgPrintEx` at `0x18007e3e1`
- `ntdll!DbgPrintEx` at `0x18007e464`
- `ntdll!DbgPrintEx` at `0x18007e24f`
- `ntdll!DbgPrintEx` at `0x18007e2b0`
- `ntdll!DbgPrintEx` at `0x18007e3ad`
- `ntdll!DbgPrintEx` at `0x18007e3e1`
- `ntdll!DbgPrintEx` at `0x18007e464`
- `ntdll!NtQueryInformationProcess` at `0x18007e37b`
- `ntdll!NtQueryInformationProcess` at `0x18007e37b`
- `ntdll!RtlGetNtSystemRoot` at `0x18007e1ff`
- `ntdll!RtlGetNtSystemRoot` at `0x18007e1ff`
- `ntdll!NtWaitForMultipleObjects` at `0x18007e682`
- `ntdll!NtWaitForMultipleObjects` at `0x18007e682`
- `ntdll!NtAllocateVirtualMemory` at `0x18007df1d`
- `ntdll!NtAllocateVirtualMemory` at `0x18007e03b`
- `ntdll!NtAllocateVirtualMemory` at `0x18007df1d`
- `ntdll!NtAllocateVirtualMemory` at `0x18007e03b`

## string_xrefs

- `0x18007e22c`: `WER/CrashAPI/%u:%u: ERROR StringCchPrintf failed while printing the debugger path with 0x%x\n`
- `0x18007e4b7`: `WER/CrashAPI/%u:%u: ERROR InitializeProcThreadAttributeList failed: 0x%x\n`
- `0x18007e527`: `WER/CrashAPI/%u:%u: ERROR InitializeProcThreadAttributeList failed: 0x%x\n`
- `0x18007e205`: `%s\system32\%s`
- `0x18007e28d`: `WER/CrashAPI/%u:%u: ERROR StringCchPrintf failed while printng the debugger commandline with 0x%x\n`
- `0x18007e578`: `WER/CrashAPI/%u:%u: ERROR UpdateProcThreadAttribute failed: 0x%x\n`

## pseudocode

```c
__int64 __fastcall WerpLaunchAeDebug(__int64 a1, __int64 a2, __int64 a3, _OWORD *a4, ULONG_PTR a5)
{
  _DWORD *v5; // r12
  struct _PROC_THREAD_ATTRIBUTE_LIST *v8; // rdi
  __int64 v9; // rsi
  signed int LastErrorValue; // r14d
  wchar_t *v11; // rbx
  int UniqueProcess; // r13d
  NTSTATUS v13; // eax
  HANDLE v14; // rcx
  char *v15; // rax
  char *v16; // rsi
  NTSTATUS v17; // eax
  _BYTE *v18; // r13
  __int128 v19; // xmm0
  __int64 v20; // rcx
  __int128 v21; // xmm1
  char *v22; // rax
  __int128 v23; // xmm0
  __int128 v24; // xmm1
  __int128 v25; // xmm0
  __int128 v26; // xmm1
  __int128 v27; // xmm0
  __int128 v28; // xmm1
  __int128 v29; // xmm0
  __int128 v30; // xmm1
  __int128 v31; // xmm0
  __int128 v32; // xmm1
  __int128 v33; // xmm0
  __int128 v34; // xmm1
  __int128 v35; // xmm0
  __int128 v36; // xmm1
  __int128 v37; // xmm1
  __int128 v38; // xmm0
  __int128 v39; // xmm1
  __int128 v40; // xmm0
  ULONG_PTR v41; // r14
  const wchar_t *v42; // r15
  __int64 NtSystemRoot; // rax
  int v44; // eax
  const CHAR *v45; // r8
  int v46; // eax
  _DWORD *v47; // r12
  unsigned int v48; // r14d
  unsigned int v49; // r8d
  NTSTATUS InformationProcess; // eax
  int v51; // r9d
  int v52; // eax
  ULONG v53; // eax
  struct _PROC_THREAD_ATTRIBUTE_LIST *v54; // rax
  NTSTATUS v55; // eax
  HANDLE v56; // rcx
  ULONG AllocationType[2]; // [rsp+20h] [rbp-E0h]
  ULONG Protect[2]; // [rsp+28h] [rbp-D8h]
  char ProcessInformation[4]; // [rsp+60h] [rbp-A0h] BYREF
  int Value; // [rsp+64h] [rbp-9Ch] BYREF
  PVOID BaseAddress; // [rsp+68h] [rbp-98h] BYREF
  HANDLE hObject; // [rsp+70h] [rbp-90h] BYREF
  DWORD ProcessId; // [rsp+78h] [rbp-88h]
  ULONG_PTR RegionSize; // [rsp+80h] [rbp-80h] BYREF
  ULONG_PTR Size; // [rsp+88h] [rbp-78h] BYREF
  __int64 CurrentTransaction; // [rsp+90h] [rbp-70h]
  HANDLE v68[2]; // [rsp+98h] [rbp-68h] BYREF
  __int64 v69; // [rsp+A8h] [rbp-58h]
  ULONG_PTR v70; // [rsp+B0h] [rbp-50h] BYREF
  HANDLE Object[2]; // [rsp+B8h] [rbp-48h] BYREF
  struct _SECURITY_ATTRIBUTES EventAttributes; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v73; // [rsp+E0h] [rbp-20h] BYREF
  char v74[8]; // [rsp+E8h] [rbp-18h] BYREF
  const WCHAR *v75; // [rsp+F0h] [rbp-10h]
  struct _PROC_THREAD_ATTRIBUTE_LIST *v76; // [rsp+148h] [rbp+48h]
  __int64 SystemInformation; // [rsp+150h] [rbp+50h] BYREF
  int v78; // [rsp+158h] [rbp+58h]
  _DWORD Buffer[4]; // [rsp+160h] [rbp+60h] BYREF
  __int64 v80; // [rsp+170h] [rbp+70h]
  __int64 v81; // [rsp+178h] [rbp+78h]
  __int64 v82; // [rsp+180h] [rbp+80h]
  __int128 v83; // [rsp+188h] [rbp+88h]
  __int128 v84; // [rsp+198h] [rbp+98h]
  __int128 v85; // [rsp+1A8h] [rbp+A8h]
  __int128 v86; // [rsp+1B8h] [rbp+B8h]
  __int128 v87; // [rsp+1C8h] [rbp+C8h]
  __int128 v88; // [rsp+1D8h] [rbp+D8h]
  __int128 v89; // [rsp+1E8h] [rbp+E8h]
  __int128 v90; // [rsp+1F8h] [rbp+F8h]
  __int128 v91; // [rsp+208h] [rbp+108h]
  __int64 v92; // [rsp+218h] [rbp+118h]
  char v93; // [rsp+220h] [rbp+120h] BYREF

  v5 = 0;
  Size = a5;
  hObject = 0;
  v73 = 0;
  memset_0(v74, 0, 0x68u);
  *(&EventAttributes.nLength + 1) = 0;
  v69 = 0;
  SystemInformation = 0;
  v78 = 0;
  *(&EventAttributes.bInheritHandle + 1) = 0;
  *(_OWORD *)v68 = 0;
  v8 = 0;
  v9 = 0;
  *(_OWORD *)Object = 0;
  CurrentTransaction = 0;
  memset_0(Buffer, 0, 0x590u);
  Value = -1;
  ProcessInformation[0] = 0;
  ProcessId = GetProcessId((HANDLE)0xFFFFFFFFFFFFFFFFLL);
  if ( !ProcessId )
  {
    LastErrorValue = NtCurrentTeb()->LastErrorValue;
    v11 = 0;
    if ( LastErrorValue > 0 )
      LastErrorValue = (unsigned __int16)LastErrorValue | 0x80070000;
    goto LABEL_71;
  }
  RegionSize = 1232;
  BaseAddress = 0;
  UniqueProcess = (int)NtCurrentTeb()->ClientId.UniqueProcess;
  v13 = NtAllocateVirtualMemory((HANDLE)0xFFFFFFFFFFFFFFFFLL, &BaseAddress, 0, &RegionSize, 0x1000u, 4u);
  if ( v13 < 0 )
  {
    BaseSetLastNTError((unsigned int)v13);
    v11 = 0;
    goto LABEL_87;
  }
  v11 = (wchar_t *)BaseAddress;
  if ( !BaseAddress )
  {
LABEL_87:
    LastErrorValue = -2147024882;
    goto LABEL_71;
  }
  v14 = hObject;
  EventAttributes.nLength = 24;
  EventAttributes.lpSecurityDescriptor = 0;
  EventAttributes.bInheritHandle = 1;
  v15 = (char *)hObject + 1;
  hObject = 0;
  if ( (unsigned __int64)v15 > 1 )
    CloseHandle(v14);
  DuplicateHandle(
    (HANDLE)0xFFFFFFFFFFFFFFFFLL,
    (HANDLE)0xFFFFFFFFFFFFFFFELL,
    (HANDLE)0xFFFFFFFFFFFFFFFFLL,
    &hObject,
    0,
    1,
    2u);
  v16 = (char *)CreateEventExW(&EventAttributes, 0, 1u, 0x1F0003u);
  if ( v16 == (char *)-1LL
    || v16 + 1 == (char *)1
    || !a3
    || NtQuerySystemInformation(SystemProcessorInformation, &SystemInformation, 0xCu, 0) < 0 )
  {
    goto LABEL_21;
  }
  Buffer[2] = GetThreadId((HANDLE)0xFFFFFFFFFFFFFFFELL);
  Buffer[1] = (unsigned __int16)SystemInformation;
  v80 = *(_QWORD *)(a3 + 16);
  Buffer[0] = 40;
  Buffer[3] = 0;
  if ( ProcessId == UniqueProcess )
  {
    v81 = a3;
    v5 = Buffer;
    v82 = (__int64)a4;
LABEL_21:
    v18 = 0;
    goto LABEL_22;
  }
  v70 = 1424;
  BaseAddress = 0;
  v17 = NtAllocateVirtualMemory((HANDLE)0xFFFFFFFFFFFFFFFFLL, &BaseAddress, 0, &v70, 0x1000u, 4u);
  if ( v17 < 0 )
  {
    BaseSetLastNTError((unsigned int)v17);
    v18 = 0;
  }
  else
  {
    v18 = BaseAddress;
    if ( BaseAddress )
    {
      v19 = *(_OWORD *)a3;
      v20 = 9;
      v21 = *(_OWORD *)(a3 + 16);
      v92 = *(_QWORD *)(a3 + 144);
      v22 = &v93;
      v83 = v19;
      v23 = *(_OWORD *)(a3 + 32);
      v84 = v21;
      v24 = *(_OWORD *)(a3 + 48);
      v85 = v23;
      v25 = *(_OWORD *)(a3 + 64);
      v86 = v24;
      v26 = *(_OWORD *)(a3 + 80);
      v87 = v25;
      v27 = *(_OWORD *)(a3 + 96);
      v88 = v26;
      v28 = *(_OWORD *)(a3 + 112);
      v89 = v27;
      v29 = *(_OWORD *)(a3 + 128);
      v90 = v28;
      v91 = v29;
      do
      {
        v30 = a4[1];
        *(_OWORD *)v22 = *a4;
        v31 = a4[2];
        *((_OWORD *)v22 + 1) = v30;
        v32 = a4[3];
        *((_OWORD *)v22 + 2) = v31;
        v33 = a4[4];
        *((_OWORD *)v22 + 3) = v32;
        v34 = a4[5];
        *((_OWORD *)v22 + 4) = v33;
        v35 = a4[6];
        *((_OWORD *)v22 + 5) = v34;
        v36 = a4[7];
        a4 += 8;
        *((_OWORD *)v22 + 6) = v35;
        *((_OWORD *)v22 + 7) = v36;
        v22 += 128;
        --v20;
      }
      while ( v20 );
      v37 = a4[1];
      *(_OWORD *)v22 = *a4;
      v38 = a4[2];
      *((_OWORD *)v22 + 1) = v37;
      v39 = a4[3];
      *((_OWORD *)v22 + 2) = v38;
      v40 = a4[4];
      *((_OWORD *)v22 + 3) = v39;
      *((_OWORD *)v22 + 4) = v40;
      RegionSize = v18 - (_BYTE *)Buffer;
      v81 = (__int64)(v18 + 40);
      v82 = (__int64)(v18 + 192);
      if ( WriteProcessMemory((HANDLE)0xFFFFFFFFFFFFFFFFLL, v18, Buffer, 0x590u, &RegionSize) )
      {
        if ( RegionSize == 1424 )
          v5 = v18;
      }
    }
  }
LABEL_22:
  v41 = Size + 4;
  if ( *(_WORD *)(Size + 4) == 34 || RtlDetermineDosPathNameType_U((PCWSTR)(Size + 4)) != RtlPathTypeRelative )
  {
    v42 = (const wchar_t *)v41;
  }
  else
  {
    v42 = v11 + 323;
    NtSystemRoot = RtlGetNtSystemRoot();
    v44 = StringCchPrintfW(v11 + 323, 0x125u, L"%s\\system32\\%s", NtSystemRoot, v41);
    LastErrorValue = v44;
    if ( v44 < 0 )
    {
      Protect[0] = v44;
      v45 = "WER/CrashAPI/%u:%u: ERROR StringCchPrintf failed while printing the debugger path with 0x%x\n";
      AllocationType[0] = 4834;
      goto LABEL_26;
    }
  }
  v46 = StringCchPrintfW(v11, 0x143u, v42, ProcessId, v16, v5);
  LastErrorValue = v46;
  if ( v46 >= 0 )
  {
    CurrentTransaction = RtlGetCurrentTransaction();
    RtlSetCurrentTransaction(0);
    v47 = (_DWORD *)Size;
    LODWORD(v73) = 112;
    v75 = &word_180290A38;
    v48 = (*(_DWORD *)Size & 4) != 0 ? 0x40000 : 0;
    if ( (*(_DWORD *)Size & 4) != 0 )
    {
      v49 = (*(_DWORD *)Size >> 3) & 0xF;
      if ( v49 < 4 || v49 == 5 || v49 == 6 || v49 == 7 )
      {
        Value = (*(_DWORD *)Size >> 3) & 0xF;
      }
      else
      {
        Value = -1;
        if ( v49 == 14 )
        {
          ProcessInformation[0] = 0;
          InformationProcess = NtQueryInformationProcess(
                                 (HANDLE)0xFFFFFFFFFFFFFFFFLL,
                                 ProcessAffinityUpdateMode|ProcessUserModeIOPL,
                                 ProcessInformation,
                                 1u,
                                 0);
          v51 = (int)NtCurrentTeb()->ClientId.UniqueProcess;
          if ( InformationProcess >= 0 )
          {
            DbgPrintEx(
              0x96u,
              2u,
              "WER/CrashAPI/%u:%u: TRACE Faulting process protection/signer: %02x/%02x\n",
              v51,
              4908,
              ProcessInformation[0] & 7,
              (unsigned __int8)ProcessInformation[0] >> 4);
            if ( (ProcessInformation[0] & 7u) >= 3 || (ProcessInformation[0] & 0xF0u) >= 0x90 )
              v52 = -1;
            else
              v52 = *((_DWORD *)qword_1802D6120
                    + 9 * (ProcessInformation[0] & 7)
                    + ((unsigned __int64)(unsigned __int8)ProcessInformation[0] >> 4));
            Value = v52;
          }
          else
          {
            DbgPrintEx(
              0x96u,
              1u,
              "WER/CrashAPI/%u:%u: WARNING NtQueryInformationProcess/ProcessProtectionInformation failed: NTSTATUS %08X\n",
              v51,
              4903,
              InformationProcess);
          }
        }
      }
    }
    DbgPrintEx(
      0x96u,
      2u,
      "WER/CrashAPI/%u:%u: TRACE Mapped protection level %02X -> %08X\n",
      LODWORD(NtCurrentTeb()->ClientId.UniqueProcess),
      4922,
      (*v47 >> 3) & 0xF,
      Value);
    if ( (*(_BYTE *)v47 & 4) != 0 && Value != -1 )
    {
      RtlSetLastWin32Error(0x7Au);
      v53 = NtCurrentTeb()->LastErrorValue;
      Size = 48;
      if ( v53 != 122 )
      {
        Protect[0] = ERROR_HR_FROM_WIN32(NtCurrentTeb()->LastErrorValue);
        v45 = "WER/CrashAPI/%u:%u: ERROR InitializeProcThreadAttributeList failed: 0x%x\n";
        AllocationType[0] = 4937;
        LastErrorValue = Protect[0];
        goto LABEL_26;
      }
      v54 = (struct _PROC_THREAD_ATTRIBUTE_LIST *)VirtualAllocExNuma(
                                                    (HANDLE)0xFFFFFFFFFFFFFFFFLL,
                                                    0,
                                                    0x30u,
                                                    0x1000u,
                                                    4u,
                                                    0xFFFFFFFF);
      v8 = v54;
      if ( !v54 )
      {
        LastErrorValue = -2147024882;
        v45 = "WER/CrashAPI/%u:%u: ERROR Failed to allocate attribute list: 0x%x\n";
        Protect[0] = -2147024882;
        AllocationType[0] = 4950;
        goto LABEL_26;
      }
      if ( !InitializeProcThreadAttributeList(v54, 1u, 0, &Size) )
      {
        Protect[0] = ERROR_HR_FROM_WIN32(NtCurrentTeb()->LastErrorValue);
        v45 = "WER/CrashAPI/%u:%u: ERROR InitializeProcThreadAttributeList failed: 0x%x\n";
        AllocationType[0] = 4962;
        LastErrorValue = Protect[0];
        goto LABEL_26;
      }
      if ( !UpdateProcThreadAttribute(v8, 0, 0x2000Bu, &Value, 4u, 0, 0) )
      {
        Protect[0] = ERROR_HR_FROM_WIN32(NtCurrentTeb()->LastErrorValue);
        v45 = "WER/CrashAPI/%u:%u: ERROR UpdateProcThreadAttribute failed: 0x%x\n";
        AllocationType[0] = 4978;
        LastErrorValue = Protect[0];
        goto LABEL_26;
      }
      v76 = v8;
      v48 |= 0x80000u;
    }
    if ( v68[0] )
      CloseHandle(v68[0]);
    if ( v68[1] )
      CloseHandle(v68[1]);
    v69 = 0;
    *(_OWORD *)v68 = 0;
    if ( (unsigned int)CreateProcessInternalW(0, 0, v11, 0, 0, 1, v48, 0, 0, (__int64)&v73, (__int64)v68) )
    {
      LastErrorValue = 0;
      if ( (unsigned __int64)(v16 + 1) > 1 )
      {
        Object[1] = v68[0];
        Object[0] = v16;
        while ( 1 )
        {
          v55 = NtWaitForMultipleObjects(2u, Object, WaitAny, 1u, 0);
          if ( !v55 )
            break;
          if ( v55 == 1 )
          {
            LastErrorValue = -2147023829;
            goto LABEL_66;
          }
        }
      }
      goto LABEL_66;
    }
    Protect[0] = ERROR_HR_FROM_WIN32(NtCurrentTeb()->LastErrorValue);
    v45 = "WER/CrashAPI/%u:%u: ERROR Debugger spawn failed: 0x%x\n";
    AllocationType[0] = 5003;
    LastErrorValue = Protect[0];
  }
  else
  {
    Protect[0] = v46;
    v45 = "WER/CrashAPI/%u:%u: ERROR StringCchPrintf failed while printng the debugger commandline with 0x%x\n";
    AllocationType[0] = 4855;
  }
LABEL_26:
  DbgPrintEx(
    0x96u,
    0,
    v45,
    LODWORD(NtCurrentTeb()->ClientId.UniqueProcess),
    *(_QWORD *)AllocationType,
    *(_QWORD *)Protect);
LABEL_66:
  if ( v18 )
    VirtualFreeEx((HANDLE)0xFFFFFFFFFFFFFFFFLL, v18, 0, 0x8000u);
  if ( (unsigned __int64)(v16 + 1) > 1 )
    CloseHandle(v16);
  v9 = CurrentTransaction;
LABEL_71:
  v56 = hObject;
  hObject = 0;
  if ( (unsigned __int64)v56 + 1 > 1 )
    CloseHandle(v56);
  if ( v9 )
    RtlSetCurrentTransaction(v9);
  if ( v11 )
    VirtualFreeEx((HANDLE)0xFFFFFFFFFFFFFFFFLL, v11, 0, 0x8000u);
  if ( v8 )
    VirtualFreeEx((HANDLE)0xFFFFFFFFFFFFFFFFLL, v8, 0, 0x8000u);
  if ( v68[0] )
    CloseHandle(v68[0]);
  if ( v68[1] )
    CloseHandle(v68[1]);
  v69 = 0;
  *(_OWORD *)v68 = 0;
  if ( (unsigned __int64)hObject + 1 > 1 )
    CloseHandle(hObject);
  return (unsigned int)LastErrorValue;
}

```

## disassembly

```asm
0x18007de08  mov     [rsp-8+arg_0], rbx
0x18007de0d  push    rbp
0x18007de0e  push    rsi
0x18007de0f  push    rdi
0x18007de10  push    r12
0x18007de12  push    r13
0x18007de14  push    r14
0x18007de16  push    r15
0x18007de18  lea     rbp, [rsp-600h]
0x18007de20  sub     rsp, 700h
0x18007de27  mov     rax, cs:__security_cookie
0x18007de2e  xor     rax, rsp
0x18007de31  mov     [rbp+630h+var_40], rax
0x18007de38  mov     rax, [rbp+630h+arg_20]
0x18007de3f  lea     rcx, [rbp+630h+var_648]; void *
0x18007de43  xor     r12d, r12d
0x18007de46  mov     [rbp+630h+Size], rax
0x18007de4a  mov     r15, r8
0x18007de4d  mov     [rsp+730h+hObject], r12
0x18007de52  xor     edx, edx; Val
0x18007de54  mov     [rbp+630h+var_650], r12
0x18007de58  mov     r14, r9
0x18007de5b  lea     r8d, [r12+68h]; Size
0x18007de60  call    memset_0
0x18007de65  xor     eax, eax
0x18007de67  mov     dword ptr [rbp+630h+EventAttributes+4], r12d
0x18007de6b  xorps   xmm0, xmm0
0x18007de6e  mov     [rbp+630h+var_688], rax
0x18007de72  xor     edx, edx; Val
0x18007de74  mov     [rbp+630h+SystemInformation], rax
0x18007de78  mov     r8d, 590h; Size
0x18007de7e  mov     [rbp+630h+var_5D8], eax
0x18007de81  lea     rcx, [rbp+630h+Buffer]; void *
0x18007de85  mov     dword ptr [rbp+630h+EventAttributes+14h], r12d
0x18007de89  movups  xmmword ptr [rbp+630h+var_698], xmm0
0x18007de8d  mov     edi, r12d
0x18007de90  mov     esi, r12d
0x18007de93  movups  xmmword ptr [rbp+630h+Object], xmm0
0x18007de97  mov     [rbp+630h+var_6A0], r12
0x18007de9b  call    memset_0
0x18007dea0  or      rcx, 0FFFFFFFFFFFFFFFFh; Process
0x18007dea4  mov     [rsp+730h+Value], 0FFFFFFFFh
0x18007deac  mov     [rsp+730h+ProcessInformation], r12b
0x18007deb1  call    GetProcessId
0x18007deb6  mov     [rsp+730h+var_6B8], eax
0x18007deba  test    eax, eax
0x18007debc  jnz     short loc_18007DEE3
0x18007debe  mov     r14d, gs:68h
0x18007dec7  mov     ebx, r12d
0x18007deca  test    r14d, r14d
0x18007decd  jle     loc_18007E6CC
0x18007ded3  movzx   r14d, r14w
0x18007ded7  or      r14d, 80070000h
0x18007dede  jmp     loc_18007E6CC
0x18007dee3  mov     rax, gs:30h
0x18007deec  lea     r9, [rbp+630h+RegionSize]; RegionSize
0x18007def0  mov     [rsp+730h+Protect], 4; Protect
0x18007def8  lea     rdx, [rsp+730h+BaseAddress]; BaseAddress
0x18007defd  xor     r8d, r8d; ZeroBits
0x18007df00  mov     [rbp+630h+RegionSize], 4D0h
0x18007df08  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x18007df0c  mov     [rsp+730h+BaseAddress], r12
0x18007df11  mov     r13d, [rax+40h]
0x18007df15  mov     [rsp+730h+AllocationType], 1000h; AllocationType
0x18007df1d  call    cs:__imp_NtAllocateVirtualMemory
0x18007df23  test    eax, eax
0x18007df25  js      loc_18007E791
0x18007df2b  mov     rbx, [rsp+730h+BaseAddress]
0x18007df30  test    rbx, rbx
0x18007df33  jz      loc_18007E79B
0x18007df39  mov     rcx, [rsp+730h+hObject]; hObject
0x18007df3e  mov     [rbp+630h+EventAttributes.nLength], 18h
0x18007df45  mov     [rbp+630h+EventAttributes.lpSecurityDescriptor], rsi
0x18007df49  mov     [rbp+630h+EventAttributes.bInheritHandle], 1
0x18007df50  lea     rax, [rcx+1]
0x18007df54  mov     [rsp+730h+hObject], rsi
0x18007df59  cmp     rax, 1
0x18007df5d  jbe     short loc_18007DF64
0x18007df5f  call    CloseHandle
0x18007df64  or      rax, 0FFFFFFFFFFFFFFFFh
0x18007df68  mov     [rsp+730h+dwOptions], 2; dwOptions
0x18007df70  mov     [rsp+730h+Protect], 1; bInheritHandle
0x18007df78  lea     r9, [rsp+730h+hObject]; lpTargetHandle
0x18007df7d  mov     r8, rax; hTargetProcessHandle
0x18007df80  mov     [rsp+730h+AllocationType], esi; dwDesiredAccess
0x18007df84  mov     rcx, rax; hSourceProcessHandle
0x18007df87  lea     rdx, [rax-1]; hSourceHandle
0x18007df8b  call    DuplicateHandle
0x18007df90  xor     edx, edx; lpName
0x18007df92  lea     rcx, [rbp+630h+EventAttributes]; lpEventAttributes
0x18007df96  mov     r9d, 1F0003h; dwDesiredAccess
0x18007df9c  lea     r8d, [rdx+1]; dwFlags
0x18007dfa0  call    CreateEventExW
0x18007dfa5  mov     rsi, rax
0x18007dfa8  inc     rax
0x18007dfab  cmp     rax, 1
0x18007dfaf  jbe     loc_18007E1D8
0x18007dfb5  test    r15, r15
0x18007dfb8  jz      loc_18007E1D8
0x18007dfbe  xor     r9d, r9d; ReturnLength
0x18007dfc1  lea     rdx, [rbp+630h+SystemInformation]; SystemInformation
0x18007dfc5  lea     r8d, [r9+0Ch]; SystemInformationLength
0x18007dfc9  lea     ecx, [r9+1]; SystemInformationClass
0x18007dfcd  call    cs:__imp_NtQuerySystemInformation
0x18007dfd3  test    eax, eax
0x18007dfd5  js      loc_18007E1D8
0x18007dfdb  mov     rcx, 0FFFFFFFFFFFFFFFEh; Thread
0x18007dfe2  call    GetThreadId
0x18007dfe7  mov     [rbp+630h+var_5C8], eax
0x18007dfea  movzx   eax, word ptr [rbp+630h+SystemInformation]
0x18007dfee  mov     [rbp+630h+var_5CC], eax
0x18007dff1  mov     rax, [r15+10h]
0x18007dff5  mov     [rbp+630h+var_5C0], rax
0x18007dff9  mov     [rbp+630h+Buffer], 28h ; '('
0x18007e000  mov     [rbp+630h+var_5C4], edi
0x18007e003  cmp     [rsp+730h+var_6B8], r13d
0x18007e008  jz      loc_18007E1C9
0x18007e00e  mov     [rsp+730h+Protect], 4; Protect
0x18007e016  lea     r9, [rbp+630h+var_680]; RegionSize
0x18007e01a  xor     r8d, r8d; ZeroBits
0x18007e01d  mov     [rsp+730h+AllocationType], 1000h; AllocationType
0x18007e025  lea     rdx, [rsp+730h+BaseAddress]; BaseAddress
0x18007e02a  mov     [rbp+630h+var_680], 590h
0x18007e032  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x18007e036  mov     [rsp+730h+BaseAddress], rdi
0x18007e03b  call    cs:__imp_NtAllocateVirtualMemory
0x18007e041  test    eax, eax
0x18007e043  js      loc_18007E1BD
0x18007e049  mov     r13, [rsp+730h+BaseAddress]
0x18007e04e  test    r13, r13
0x18007e051  jz      loc_18007E1DB
0x18007e057  movups  xmm0, xmmword ptr [r15]
0x18007e05b  mov     rax, [r15+90h]
0x18007e062  mov     ecx, 9
0x18007e067  movups  xmm1, xmmword ptr [r15+10h]
0x18007e06c  mov     [rbp+630h+var_518], rax
0x18007e073  lea     rax, [rbp+630h+var_510]
0x18007e07a  movups  [rbp+630h+var_5A8], xmm0
0x18007e081  lea     edx, [rcx+77h]
0x18007e084  movups  xmm0, xmmword ptr [r15+20h]
0x18007e089  movups  [rbp+630h+var_598], xmm1
0x18007e090  movups  xmm1, xmmword ptr [r15+30h]
0x18007e095  movups  [rbp+630h+var_588], xmm0
0x18007e09c  movups  xmm0, xmmword ptr [r15+40h]
0x18007e0a1  movups  [rbp+630h+var_578], xmm1
0x18007e0a8  movups  xmm1, xmmword ptr [r15+50h]
0x18007e0ad  movups  [rbp+630h+var_568], xmm0
0x18007e0b4  movups  xmm0, xmmword ptr [r15+60h]
0x18007e0b9  movups  [rbp+630h+var_558], xmm1
0x18007e0c0  movups  xmm1, xmmword ptr [r15+70h]
0x18007e0c5  movups  [rbp+630h+var_548], xmm0
0x18007e0cc  movups  xmm0, xmmword ptr [r15+80h]
0x18007e0d4  movups  [rbp+630h+var_538], xmm1
0x18007e0db  movups  [rbp+630h+var_528], xmm0
0x18007e0e2  movups  xmm0, xmmword ptr [r14]
0x18007e0e6  movups  xmm1, xmmword ptr [r14+10h]
0x18007e0eb  movups  xmmword ptr [rax], xmm0
0x18007e0ee  movups  xmm0, xmmword ptr [r14+20h]
0x18007e0f3  movups  xmmword ptr [rax+10h], xmm1
0x18007e0f7  movups  xmm1, xmmword ptr [r14+30h]
0x18007e0fc  movups  xmmword ptr [rax+20h], xmm0
0x18007e100  movups  xmm0, xmmword ptr [r14+40h]
0x18007e105  movups  xmmword ptr [rax+30h], xmm1
0x18007e109  movups  xmm1, xmmword ptr [r14+50h]
0x18007e10e  movups  xmmword ptr [rax+40h], xmm0
0x18007e112  movups  xmm0, xmmword ptr [r14+60h]
0x18007e117  movups  xmmword ptr [rax+50h], xmm1
0x18007e11b  movups  xmm1, xmmword ptr [r14+70h]
0x18007e120  add     r14, rdx
0x18007e123  movups  xmmword ptr [rax+60h], xmm0
0x18007e127  movups  xmmword ptr [rax+70h], xmm1
0x18007e12b  add     rax, rdx
0x18007e12e  sub     rcx, 1
0x18007e132  jnz     short loc_18007E0E2
0x18007e134  movups  xmm0, xmmword ptr [r14]
0x18007e138  mov     rcx, r13
0x18007e13b  lea     r8, [rbp+630h+Buffer]; lpBuffer
0x18007e13f  movups  xmm1, xmmword ptr [r14+10h]
0x18007e144  mov     rdx, r13; lpBaseAddress
0x18007e147  movups  xmmword ptr [rax], xmm0
0x18007e14a  movups  xmm0, xmmword ptr [r14+20h]
0x18007e14f  movups  xmmword ptr [rax+10h], xmm1
0x18007e153  movups  xmm1, xmmword ptr [r14+30h]
0x18007e158  movups  xmmword ptr [rax+20h], xmm0
0x18007e15c  movups  xmm0, xmmword ptr [r14+40h]
0x18007e161  mov     r14d, 590h
0x18007e167  movups  xmmword ptr [rax+30h], xmm1
0x18007e16b  mov     r9d, r14d; nSize
0x18007e16e  movups  xmmword ptr [rax+40h], xmm0
0x18007e172  lea     rax, [rbp+630h+Buffer]
0x18007e176  sub     rcx, rax
0x18007e179  lea     rax, [rbp+630h+var_5A8]
0x18007e180  add     rax, rcx
0x18007e183  mov     [rbp+630h+RegionSize], rcx
0x18007e187  mov     [rbp+630h+var_5B8], rax
0x18007e18b  lea     rax, [rbp+630h+var_510]
0x18007e192  add     rax, rcx
0x18007e195  or      rcx, 0FFFFFFFFFFFFFFFFh; hProcess
0x18007e199  mov     [rbp+630h+var_5B0], rax
0x18007e1a0  lea     rax, [rbp+630h+RegionSize]
0x18007e1a4  mov     qword ptr [rsp+730h+AllocationType], rax; lpNumberOfBytesWritten
0x18007e1a9  call    WriteProcessMemory
0x18007e1ae  test    eax, eax
0x18007e1b0  jz      short loc_18007E1DB
0x18007e1b2  cmp     [rbp+630h+RegionSize], r14
0x18007e1b6  jnz     short loc_18007E1DB
0x18007e1b8  mov     r12, r13
0x18007e1bb  jmp     short loc_18007E1DB
0x18007e1bd  mov     ecx, eax
0x18007e1bf  call    BaseSetLastNTError
0x18007e1c4  xor     r13d, r13d
0x18007e1c7  jmp     short loc_18007E1DB
0x18007e1c9  mov     [rbp+630h+var_5B8], r15
0x18007e1cd  lea     r12, [rbp+630h+Buffer]
0x18007e1d1  mov     [rbp+630h+var_5B0], r14
0x18007e1d8  mov     r13, rdi
0x18007e1db  mov     r14, [rbp+630h+Size]
0x18007e1df  add     r14, 4
0x18007e1e3  cmp     word ptr [r14], 22h ; '"'
0x18007e1e8  jz      short loc_18007E25D
0x18007e1ea  mov     rcx, r14; Path
0x18007e1ed  call    cs:__imp_RtlDetermineDosPathNameType_U
0x18007e1f3  cmp     eax, 5
0x18007e1f6  jnz     short loc_18007E25D
0x18007e1f8  lea     r15, [rbx+286h]
0x18007e1ff  call    cs:__imp_RtlGetNtSystemRoot
0x18007e205  lea     r8, aSSystem32S; "%s\\system32\\%s"
0x18007e20c  mov     qword ptr [rsp+730h+AllocationType], r14
0x18007e211  mov     r9, rax
0x18007e214  mov     edx, 125h; unsigned __int64
0x18007e219  mov     rcx, r15; wchar_t *
0x18007e21c  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18007e221  mov     r14d, eax
0x18007e224  test    eax, eax
0x18007e226  jns     short loc_18007E260
0x18007e228  mov     [rsp+730h+Protect], eax
0x18007e22c  lea     r8, aWerCrashapiUUE_9; "WER/CrashAPI/%u:%u: ERROR StringCchPrin"...
0x18007e233  mov     [rsp+730h+AllocationType], 12E2h
0x18007e23b  mov     ecx, 96h; ComponentId
0x18007e240  mov     r9, gs:30h
0x18007e249  xor     edx, edx; Level
0x18007e24b  mov     r9d, [r9+40h]
0x18007e24f  call    cs:__imp_DbgPrintEx
0x18007e255  xor     r12d, r12d
0x18007e258  jmp     loc_18007E69C
0x18007e25d  mov     r15, r14
0x18007e260  mov     r9d, [rsp+730h+var_6B8]
0x18007e265  mov     r8, r15; wchar_t *
0x18007e268  mov     qword ptr [rsp+730h+Protect], r12
0x18007e26d  mov     edx, 143h; unsigned __int64
0x18007e272  mov     rcx, rbx; wchar_t *
0x18007e275  mov     qword ptr [rsp+730h+AllocationType], rsi
0x18007e27a  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18007e27f  xor     r12d, r12d
0x18007e282  mov     r14d, eax
0x18007e285  test    eax, eax
0x18007e287  jns     short loc_18007E2BB
0x18007e289  mov     [rsp+730h+Protect], eax
0x18007e28d  lea     r8, aWerCrashapiUUE_30; "WER/CrashAPI/%u:%u: ERROR StringCchPrin"...
0x18007e294  mov     [rsp+730h+AllocationType], 12F7h
0x18007e29c  mov     ecx, 96h; ComponentId
0x18007e2a1  mov     r9, gs:30h
0x18007e2aa  xor     edx, edx; Level
0x18007e2ac  mov     r9d, [r9+40h]
0x18007e2b0  call    cs:__imp_DbgPrintEx
0x18007e2b6  jmp     loc_18007E69C
0x18007e2bb  call    cs:__imp_RtlGetCurrentTransaction
0x18007e2c1  xor     ecx, ecx
0x18007e2c3  mov     [rbp+630h+var_6A0], rax
0x18007e2c7  call    cs:__imp_RtlSetCurrentTransaction
0x18007e2cd  mov     r12, [rbp+630h+Size]
0x18007e2d1  lea     rax, word_180290A38
0x18007e2d8  mov     dword ptr [rbp+630h+var_650], 70h ; 'p'
0x18007e2df  mov     r15d, 96h
0x18007e2e5  mov     [rbp+630h+var_640], rax
0x18007e2e9  mov     r8d, [r12]
0x18007e2ed  mov     edx, r8d
0x18007e2f0  and     edx, 4
0x18007e2f3  mov     ecx, edx
0x18007e2f5  neg     ecx
0x18007e2f7  sbb     r14d, r14d
0x18007e2fa  and     r14d, 40000h
0x18007e301  test    edx, edx
0x18007e303  jz      loc_18007E42A
0x18007e309  shr     r8d, 3
0x18007e30d  and     r8d, 0Fh
0x18007e311  mov     eax, r8d
0x18007e314  jz      loc_18007E425
0x18007e31a  sub     eax, 1
0x18007e31d  jz      loc_18007E425
0x18007e323  sub     eax, 1
0x18007e326  jz      loc_18007E425
0x18007e32c  sub     eax, 1
0x18007e32f  jz      loc_18007E425
0x18007e335  sub     eax, 2
0x18007e338  jz      loc_18007E425
0x18007e33e  sub     eax, 1
0x18007e341  jz      loc_18007E425
0x18007e347  sub     eax, 1
0x18007e34a  jz      loc_18007E425
  ... truncated ...
```
