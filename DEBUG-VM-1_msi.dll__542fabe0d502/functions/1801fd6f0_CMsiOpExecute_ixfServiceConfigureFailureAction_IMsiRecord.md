# CMsiOpExecute::ixfServiceConfigureFailureAction(IMsiRecord &)

- ea: `0x1801fd6f0`
- end: `0x1801fe219`
- name: `?ixfServiceConfigureFailureAction@CMsiOpExecute@@IEAA?AW4iesEnum@@AEAVIMsiRecord@@@Z`
- size: `2857`
- prototype: ``
- caller_count: `4`
- callee_count: `18`
- tags: `file_ops, registry_config, service_task, installer_update`

## callers

- `0x1800da4bc`
- `0x1800db2d0`
- `0x1800e12c4`
- `0x1801df8c0`

## callees

- `0x180025a18`
- `0x18004295c`
- `0x180061334`
- `0x1800620e4`
- `0x180066db0`
- `0x1800888e8`
- `0x1800af92c`
- `0x1800b8e10`
- `0x1800c2854`
- `0x1800cddb0`
- `0x1800d6ff0`
- `0x1801de458`
- `0x1801e1004`
- `0x1801e113c`
- `0x1801e29b8`
- `0x1801ecb58`
- `0x1801fd6f0`
- `0x18025c010`

## import_xrefs

- `ADVAPI32!CloseServiceHandle` at `0x1801fe02a`
- `ADVAPI32!CloseServiceHandle` at `0x1801fe02a`
- `KERNEL32!GetLastError` at `0x1801fdadd`
- `KERNEL32!GetLastError` at `0x1801fdefa`
- `KERNEL32!GetLastError` at `0x1801fe011`
- `KERNEL32!GetLastError` at `0x1801fdadd`
- `KERNEL32!GetLastError` at `0x1801fdefa`
- `KERNEL32!GetLastError` at `0x1801fe011`

## string_xrefs

- `0x1801fd7c4`: `Changing configuration of failure action for service %s.`
- `0x1801fe017`: `Error: %d. Failed to change configuration of failure action for service %s because handle to the service could be obtained. Check if the service exists on the system.`
- `0x1801fd893`: `Warning: ResetPeriod is <blank>. Trying to change current configuration of failure action for service %s. Replacing with default argument INFINITE`
- `0x1801fdfb4`: `Error: invalid ResetPeriod %d. Failed to change configuration of failure action for service %s`
- `0x1801fda26`: `Error: Number of Actions (%s) != Number of DelayActions (%s). Failed to change configuration of failure action for service %s`
- `0x1801fdae8`: `Error: %d. Failed to change configuration of failure action for service %s`
- `0x1801fdbd6`: `Error <Type: %s; Delay:%s> is an invalid Failure Action. Failed to change configuration of failure action for service %s`
- `0x1801fdf00`: `Error: %d. Failed to change current configuration of failure action for service %s`
- `0x1801fe092`: `Failed to change configuration of failure action for service %s`
- `0x1801fe171`: `Done changing configuration of failure action for service %s`

## pseudocode

```c
__int64 __fastcall CMsiOpExecute::ixfServiceConfigureFailureAction(CMsiOpExecute *a1, __int64 *a2)
{
  const struct IMsiString *v3; // r12
  const struct IMsiString *v4; // rbx
  const struct IMsiString *ServiceDisplayNameW; // rdi
  const struct IMsiString *v6; // rbx
  const struct IMsiString *v7; // rsi
  void *v8; // r15
  const unsigned __int16 *v9; // rax
  const struct IMsiString *v10; // r14
  SC_HANDLE ServiceHandle; // rax
  __int64 v12; // rcx
  const unsigned __int16 *v13; // rax
  int v14; // eax
  const unsigned __int16 *v15; // r14
  __int64 v16; // rax
  __int64 v17; // rcx
  __int64 v18; // rax
  __int64 v19; // rcx
  const struct IMsiString *v20; // r14
  CMsiOpExecute *v21; // rcx
  CMsiOpExecute *v22; // rcx
  unsigned __int16 **v23; // rax
  int v24; // r14d
  const unsigned __int16 *v25; // r15
  MsiString *v26; // rax
  const unsigned __int16 *v27; // r14
  MsiString *v28; // rax
  const unsigned __int16 *v29; // rax
  char v30; // r14
  const unsigned __int16 *v31; // r14
  DWORD v32; // eax
  char v33; // r14
  int i; // eax
  __int64 v35; // r14
  int IntegerValue; // eax
  const unsigned __int16 *v37; // rax
  void (__fastcall *v38)(struct IMsiRecord *, __int64, __int64); // r15
  __int64 v39; // r14
  void (__fastcall *v40)(struct IMsiRecord *, __int64, __int64); // r15
  __int64 v41; // rax
  struct IMsiRecord *v42; // r13
  __int64 v43; // r14
  MsiString *v44; // rax
  __int64 v45; // rcx
  const unsigned __int16 **v46; // r15
  void (__fastcall *v47)(struct IMsiRecord *, __int64, _QWORD); // r14
  MsiString *v48; // rax
  void (__fastcall *v49)(struct IMsiRecord *, __int64, _QWORD); // r14
  MsiString *v50; // rax
  bool v51; // zf
  unsigned int v52; // r13d
  int v53; // r14d
  MsiString *v54; // rax
  unsigned int v55; // r13d
  int v56; // r14d
  MsiString *v57; // rax
  __int64 v58; // r9
  const unsigned __int16 *v59; // r14
  DWORD LastError; // eax
  const unsigned __int16 *v61; // r9
  __int64 v62; // rcx
  const unsigned __int16 *v63; // rax
  const unsigned __int16 *v64; // rax
  const unsigned __int16 *v66; // rax
  _DWORD *v67; // [rsp+60h] [rbp-69h]
  __int64 v68; // [rsp+68h] [rbp-61h] BYREF
  __int64 v69; // [rsp+70h] [rbp-59h] BYREF
  int v70; // [rsp+78h] [rbp-51h]
  int v71; // [rsp+7Ch] [rbp-4Dh]
  __int64 v72; // [rsp+80h] [rbp-49h] BYREF
  SC_HANDLE hSCObject; // [rsp+88h] [rbp-41h]
  void *v74; // [rsp+90h] [rbp-39h]
  void *v75; // [rsp+98h] [rbp-31h]
  const struct IMsiString *v76; // [rsp+A0h] [rbp-29h] BYREF
  __int64 v77; // [rsp+A8h] [rbp-21h]
  __int64 v78; // [rsp+B0h] [rbp-19h]
  _DWORD v79[2]; // [rsp+B8h] [rbp-11h] BYREF
  __int64 v80; // [rsp+C0h] [rbp-9h]
  __int64 v81; // [rsp+C8h] [rbp-1h]
  int v82; // [rsp+D0h] [rbp+7h]
  int v83; // [rsp+D4h] [rbp+Bh]
  _DWORD *v84; // [rsp+D8h] [rbp+Fh]
  int v86; // [rsp+138h] [rbp+6Fh] BYREF
  unsigned int *v87; // [rsp+140h] [rbp+77h] BYREF
  struct IMsiRecord *SharedRecord; // [rsp+148h] [rbp+7Fh] BYREF

  LODWORD(SharedRecord) = 0;
  v3 = (const struct IMsiString *)(*(__int64 (__fastcall **)(__int64 *, __int64))(*a2 + 72))(a2, 2);
  v76 = v3;
  v4 = (const struct IMsiString *)(*(__int64 (__fastcall **)(__int64 *, __int64))(*a2 + 72))(a2, 1);
  ServiceDisplayNameW = GetServiceDisplayNameW(v4, v3);
  (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v4 + 16LL))(v4);
  v6 = (const struct IMsiString *)&MsiString::s_NullString;
  v7 = (const struct IMsiString *)&MsiString::s_NullString;
  MsiString::MsiString((MsiString *)&v69, &Default);
  MsiString::MsiString((MsiString *)&v68, &Default);
  v8 = 0;
  v75 = 0;
  v74 = 0;
  if ( g_dmDiagnosticMode )
  {
    v9 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v3 + 80LL))(v3);
    DebugString(
      10,
      0,
      0,
      L"Changing configuration of failure action for service %s.",
      v9,
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      0,
      0);
  }
  v10 = (const struct IMsiString *)(*(__int64 (__fastcall **)(__int64 *, __int64))(*a2 + 72))(a2, 1);
  ServiceHandle = GetServiceHandle(v10, v3, 3u);
  v12 = *(_QWORD *)v10;
  hSCObject = ServiceHandle;
  (*(void (__fastcall **)(const struct IMsiString *))(v12 + 16))(v10);
  if ( (unsigned __int64)hSCObject - 1 > 0xFFFFFFFFFFFFFFFDuLL )
  {
    if ( !g_dmDiagnosticMode )
      goto LABEL_42;
    v59 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v3 + 80LL))(v3);
    LastError = GetLastError();
    v61 = L"Error: %d. Failed to change configuration of failure action for service %s because handle to the service could"
           " be obtained. Check if the service exists on the system.";
LABEL_41:
    DebugString(
      9,
      0,
      0,
      v61,
      (const unsigned __int16 *)LastError,
      v59,
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      0,
      0);
LABEL_42:
    v33 = 0;
    goto LABEL_51;
  }
  if ( (*(unsigned int (__fastcall **)(__int64 *, __int64))(*a2 + 32))(a2, 4) )
  {
    if ( g_dmDiagnosticMode )
    {
      v13 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v3 + 80LL))(v3);
      DebugString(
        9,
        0,
        0,
        L"Warning: ResetPeriod is <blank>. Trying to change current configuration of failure action for service %s. Replac"
         "ing with default argument INFINITE",
        v13,
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        0,
        0);
    }
    v71 = -1;
  }
  else
  {
    v14 = (*(__int64 (__fastcall **)(__int64 *, __int64))(*a2 + 56))(a2, 4);
    v15 = (const unsigned __int16 *)v14;
    v71 = v14;
    if ( v14 < 0 )
    {
      if ( g_dmDiagnosticMode )
      {
        v63 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v3 + 80LL))(v3);
        DebugString(
          9,
          0,
          0,
          L"Error: invalid ResetPeriod %d. Failed to change configuration of failure action for service %s",
          v15,
          v63,
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          0,
          0);
      }
      goto LABEL_48;
    }
  }
  v16 = (*(__int64 (__fastcall **)(__int64 *, __int64))(*a2 + 80))(a2, 5);
  v17 = *a2;
  v78 = v16;
  v18 = (*(__int64 (__fastcall **)(__int64 *, __int64))(v17 + 80))(a2, 6);
  v19 = *a2;
  v77 = v18;
  v7 = (const struct IMsiString *)(*(__int64 (__fastcall **)(__int64 *, __int64))(v19 + 72))(a2, 7);
  (*(void (__fastcall **)(void *))(MsiString::s_NullString + 16LL))(&MsiString::s_NullString);
  v20 = (const struct IMsiString *)(*(__int64 (__fastcall **)(__int64 *, __int64))(*a2 + 72))(a2, 8);
  (*(void (__fastcall **)(void *))(MsiString::s_NullString + 16LL))(&MsiString::s_NullString);
  v86 = 0;
  LODWORD(v87) = 0;
  v6 = v20;
  v74 = CMsiOpExecute::NewArgumentArray(v21, v7, &v86);
  v23 = CMsiOpExecute::NewArgumentArray(v22, v20, (int *)&v87);
  v24 = v86;
  v75 = v23;
  if ( v86 != (_DWORD)v87 )
  {
    if ( g_dmDiagnosticMode )
    {
      v25 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v3 + 80LL))(v3);
      v26 = MsiString::MsiString((MsiString *)&v72, (int)v87);
      v27 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)v26 + 80LL))(*(_QWORD *)v26);
      v28 = MsiString::MsiString((MsiString *)&SharedRecord, v86);
      v29 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)v28 + 80LL))(*(_QWORD *)v28);
      DebugString(
        9,
        0,
        0,
        L"Error: Number of Actions (%s) != Number of DelayActions (%s). Failed to change configuration of failure action for service %s",
        v29,
        v27,
        v25,
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        0,
        0);
      v30 = 3;
    }
    else
    {
      v30 = 0;
    }
    if ( (v30 & 2) != 0 )
    {
      v30 &= ~2u;
      (*(void (__fastcall **)(struct IMsiRecord *))(*(_QWORD *)SharedRecord + 16LL))(SharedRecord);
    }
    if ( (v30 & 1) != 0 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v72 + 16LL))(v72);
LABEL_48:
    v33 = 0;
    v8 = 0;
    goto LABEL_51;
  }
  v67 = operator new(saturated_mul(v86, 8u));
  if ( v67 )
  {
    for ( i = 0; ; i = v70 + 1 )
    {
      v70 = i;
      if ( i >= v24 )
        break;
      v35 = i;
      LODWORD(v87) = 0;
      LODWORD(SharedRecord) = 0;
      LODWORD(v72) = GetIntegerValue(*((const unsigned __int16 **)v74 + i), (enum Bool *)&v87);
      IntegerValue = GetIntegerValue(*((const unsigned __int16 **)v75 + v35), (enum Bool *)&SharedRecord);
      if ( !(_DWORD)v87 || !(_DWORD)SharedRecord || IntegerValue < 0 )
      {
        if ( g_dmDiagnosticMode )
        {
          v37 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v3 + 80LL))(v3);
          DebugString(
            9,
            0,
            0,
            L"Error <Type: %s; Delay:%s> is an invalid Failure Action. Failed to change configuration of failure action for service %s",
            *((const unsigned __int16 **)v74 + v35),
            *((const unsigned __int16 **)v75 + v35),
            v37,
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            0,
            0);
        }
        goto LABEL_20;
      }
      v67[2 * v35] = v72;
      v67[2 * v35 + 1] = IntegerValue;
      v24 = v86;
    }
    SharedRecord = CMsiOpExecute::GetSharedRecord(a1, 8);
    v38 = *(void (__fastcall **)(struct IMsiRecord *, __int64, __int64))(*(_QWORD *)SharedRecord + 120LL);
    v39 = (*(__int64 (__fastcall **)(__int64 *, __int64))(*a2 + 72))(a2, 1);
    v38(SharedRecord, 1, v39);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
    v40 = *(void (__fastcall **)(struct IMsiRecord *, __int64, __int64))(*(_QWORD *)SharedRecord + 120LL);
    v41 = (*(__int64 (__fastcall **)(__int64 *, __int64))(*a2 + 72))(a2, 2);
    v42 = SharedRecord;
    v43 = v41;
    v40(SharedRecord, 2, v41);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
    v87 = 0;
    v44 = MsiString::MsiString((MsiString *)&v72, (const struct MsiString *)&v76);
    if ( !(unsigned __int8)CMsiOpExecute::QueryServiceConfiguration(v45, hSCObject, v44, 2, &v87) )
      goto LABEL_20;
    v46 = (const unsigned __int16 **)v87;
    (*(void (__fastcall **)(struct IMsiRecord *, __int64, _QWORD))(*(_QWORD *)v42 + 104LL))(v42, 4, *v87);
    v47 = *(void (__fastcall **)(struct IMsiRecord *, __int64, _QWORD))(*(_QWORD *)v42 + 120LL);
    v48 = MsiString::MsiString((MsiString *)&v87, v46[1]);
    v47(v42, 5, *(_QWORD *)v48);
    (*(void (__fastcall **)(unsigned int *))(*(_QWORD *)v87 + 16LL))(v87);
    v49 = *(void (__fastcall **)(struct IMsiRecord *, __int64, _QWORD))(*(_QWORD *)v42 + 120LL);
    v50 = MsiString::MsiString((MsiString *)&v87, v46[2]);
    v49(v42, 6, *(_QWORD *)v50);
    (*(void (__fastcall **)(unsigned int *))(*(_QWORD *)v87 + 16LL))(v87);
    v51 = *((_DWORD *)v46 + 6) == 0;
    LODWORD(v87) = 0;
    if ( !v51 )
    {
      v52 = (unsigned int)v87;
      do
      {
        v53 = *(_DWORD *)&v46[4][4 * v52];
        MsiString::operator+=(&v69, &dword_1802BEC74);
        v54 = MsiString::MsiString((MsiString *)&v87, v53);
        MsiString::operator+=(&v69, v54);
        (*(void (__fastcall **)(unsigned int *))(*(_QWORD *)v87 + 16LL))(v87);
        ++v52;
      }
      while ( v52 < *((_DWORD *)v46 + 6) );
      v42 = SharedRecord;
    }
    MsiString::operator+=(&v69, &dword_1802BEC74);
    (*(void (__fastcall **)(struct IMsiRecord *, __int64, __int64))(*(_QWORD *)v42 + 120LL))(v42, 7, v69);
    v51 = *((_DWORD *)v46 + 6) == 0;
    LODWORD(v87) = 0;
    if ( !v51 )
    {
      v55 = (unsigned int)v87;
      do
      {
        v56 = *(_DWORD *)&v46[4][4 * v55 + 2];
        MsiString::operator+=(&v68, &dword_1802BEC74);
        v57 = MsiString::MsiString((MsiString *)&v87, v56);
        MsiString::operator+=(&v68, v57);
        (*(void (__fastcall **)(unsigned int *))(*(_QWORD *)v87 + 16LL))(v87);
        ++v55;
      }
      while ( v55 < *((_DWORD *)v46 + 6) );
      v42 = SharedRecord;
    }
    MsiString::operator+=(&v68, &dword_1802BEC74);
    (*(void (__fastcall **)(struct IMsiRecord *, __int64, __int64))(*(_QWORD *)v42 + 120LL))(v42, 8, v68);
    v8 = v67;
    v82 = v86;
    v79[0] = v71;
    v81 = v77;
    v80 = v78;
    v79[1] = 0;
    v83 = 0;
    v84 = v67;
    if ( (unsigned int)((__int64 (__fastcall *)(SC_HANDLE, __int64, _DWORD *))ADVAPI32::ChangeServiceConfig2W)(
                         hSCObject,
                         2,
                         v79) )
    {
      v33 = 1;
      v62 = *((_QWORD *)a1 + 4);
      if ( !v62 )
        goto LABEL_51;
      LOBYTE(v58) = 1;
      if ( (unsigned __int8)WriteScriptRecord(v62, 151, v42, v58, *((_QWORD *)a1 + 2)) )
        goto LABEL_51;
      goto LABEL_42;
    }
    if ( !g_dmDiagnosticMode )
      goto LABEL_42;
    v59 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v3 + 80LL))(v3);
    LastError = GetLastError();
    v61 = L"Error: %d. Failed to change current configuration of failure action for service %s";
    goto LABEL_41;
  }
  if ( g_dmDiagnosticMode )
  {
    v31 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v3 + 80LL))(v3);
    v32 = GetLastError();
    DebugString(
      9,
      0,
      0,
      L"Error: %d. Failed to change configuration of failure action for service %s",
      (const unsigned __int16 *)v32,
      v31,
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      0,
      0);
  }
LABEL_20:
  v8 = v67;
  v33 = 0;
LABEL_51:
  CloseServiceHandle(hSCObject);
  if ( v74 )
    operator delete(v74);
  if ( v75 )
    operator delete(v75);
  if ( v8 )
    operator delete(v8);
  if ( v33 )
  {
    if ( g_dmDiagnosticMode )
    {
      v66 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v3 + 80LL))(v3);
      DebugString(
        10,
        0,
        0,
        L"Done changing configuration of failure action for service %s",
        v66,
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        0,
        0);
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v68 + 16LL))(v68);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v69 + 16LL))(v69);
    (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v6 + 16LL))(v6);
    (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v7 + 16LL))(v7);
    (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)ServiceDisplayNameW + 16LL))(ServiceDisplayNameW);
    (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v3 + 16LL))(v3);
    return 1;
  }
  else
  {
    if ( g_dmDiagnosticMode )
    {
      v64 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v3 + 80LL))(v3);
      DebugString(
        9,
        0,
        0,
        L"Failed to change configuration of failure action for service %s",
        v64,
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        0,
        0);
    }
    CMsiOpExecute::DispatchError(a1, 0x1000000, 1939, ServiceDisplayNameW, v3);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v68 + 16LL))(v68);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v69 + 16LL))(v69);
    (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v6 + 16LL))(v6);
    (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v7 + 16LL))(v7);
    (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)ServiceDisplayNameW + 16LL))(ServiceDisplayNameW);
    (*(void (__fastcall **)(const struct IMsiString *))(*(_QWORD *)v3 + 16LL))(v3);
    return 3;
  }
}

```

## disassembly

```asm
0x1801fd6f0  mov     [rsp-8+arg_0], rcx
0x1801fd6f5  push    rbp
0x1801fd6f6  push    rbx
0x1801fd6f7  push    rsi
0x1801fd6f8  push    rdi
0x1801fd6f9  push    r12
0x1801fd6fb  push    r13
0x1801fd6fd  push    r14
0x1801fd6ff  push    r15
0x1801fd701  lea     rbp, [rsp-1Fh]
0x1801fd706  sub     rsp, 0E8h
0x1801fd70d  mov     r13, rdx
0x1801fd710  xor     r14d, r14d
0x1801fd713  mov     dword ptr [rbp+57h+arg_18], r14d
0x1801fd717  mov     rcx, r13
0x1801fd71a  mov     rax, [rdx]
0x1801fd71d  lea     edx, [r14+2]
0x1801fd721  mov     rax, [rax+48h]
0x1801fd725  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801fd72a  mov     r12, rax
0x1801fd72d  mov     [rbp+57h+var_80], rax
0x1801fd731  mov     rax, [r13+0]
0x1801fd735  lea     edx, [r14+1]
0x1801fd739  mov     rcx, r13
0x1801fd73c  mov     rax, [rax+48h]
0x1801fd740  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801fd745  mov     rdx, r12; struct IMsiString *
0x1801fd748  mov     rcx, rax; struct IMsiString *
0x1801fd74b  mov     rbx, rax
0x1801fd74e  call    ?GetServiceDisplayNameW@@YAAEBVIMsiString@@AEBV1@0@Z; GetServiceDisplayNameW(IMsiString const &,IMsiString const &)
0x1801fd753  mov     rcx, [rbx]
0x1801fd756  mov     rdi, rax
0x1801fd759  mov     rax, [rcx+10h]
0x1801fd75d  mov     rcx, rbx
0x1801fd760  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801fd765  lea     rbx, ?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x1801fd76c  lea     rdx, Default; unsigned __int16 *
0x1801fd773  mov     rsi, rbx
0x1801fd776  lea     rcx, [rbp+57h+var_B0]; this
0x1801fd77a  call    ??0MsiString@@QEAA@PEBG@Z; MsiString::MsiString(ushort const *)
0x1801fd77f  lea     rdx, Default; unsigned __int16 *
0x1801fd786  lea     rcx, [rbp+57h+var_B8]; this
0x1801fd78a  call    ??0MsiString@@QEAA@PEBG@Z; MsiString::MsiString(ushort const *)
0x1801fd78f  cmp     cs:?g_dmDiagnosticMode@@3HA, r14d; int g_dmDiagnosticMode
0x1801fd796  mov     r15d, r14d
0x1801fd799  mov     [rbp+57h+var_88], r14
0x1801fd79d  mov     [rbp+57h+var_90], r14
0x1801fd7a1  jz      short loc_1801FD7F6
0x1801fd7a3  mov     rax, [r12]
0x1801fd7a7  mov     rcx, r12
0x1801fd7aa  mov     rax, [rax+50h]
0x1801fd7ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801fd7b3  lea     rcx, aNull; "(NULL)"
0x1801fd7ba  mov     [rsp+120h+var_C8], r14; void *
0x1801fd7bf  mov     [rsp+120h+var_D0], r14d; unsigned int
0x1801fd7c4  lea     r9, aChangingConfig_0; "Changing configuration of failure actio"...
0x1801fd7cb  mov     [rsp+120h+var_D8], rcx; unsigned __int16 *
0x1801fd7d0  xor     edx, edx; unsigned __int16
0x1801fd7d2  mov     [rsp+120h+var_E0], rcx; unsigned __int16 *
0x1801fd7d7  xor     r8d, r8d; int
0x1801fd7da  mov     [rsp+120h+var_E8], rcx; unsigned __int16 *
0x1801fd7df  mov     [rsp+120h+var_F0], rcx; unsigned __int16 *
0x1801fd7e4  mov     [rsp+120h+var_F8], rcx; unsigned __int16 *
0x1801fd7e9  lea     ecx, [rdx+0Ah]; int
0x1801fd7ec  mov     [rsp+120h+var_100], rax; unsigned __int16 *
0x1801fd7f1  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1801fd7f6  mov     rax, [r13+0]
0x1801fd7fa  mov     edx, 1
0x1801fd7ff  mov     rcx, r13
0x1801fd802  mov     rax, [rax+48h]
0x1801fd806  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801fd80b  mov     r8d, 3; unsigned int
0x1801fd811  mov     rdx, r12; struct IMsiString *
0x1801fd814  mov     rcx, rax; struct IMsiString *
0x1801fd817  mov     r14, rax
0x1801fd81a  call    ?GetServiceHandle@@YAPEAUSC_HANDLE__@@AEBVIMsiString@@0K@Z; GetServiceHandle(IMsiString const &,IMsiString const &,ulong)
0x1801fd81f  mov     rcx, [r14]
0x1801fd822  mov     [rbp+57h+hSCObject], rax
0x1801fd826  mov     rax, [rcx+10h]
0x1801fd82a  mov     rcx, r14
0x1801fd82d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801fd832  mov     rcx, [rbp+57h+hSCObject]
0x1801fd836  dec     rcx
0x1801fd839  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x1801fd83d  ja      loc_1801FDFEE
0x1801fd843  mov     rcx, [r13+0]
0x1801fd847  mov     edx, 4
0x1801fd84c  mov     rax, [rcx+20h]
0x1801fd850  mov     rcx, r13
0x1801fd853  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801fd858  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1801fd85c  xor     r14d, r14d
0x1801fd85f  mov     r15d, 9
0x1801fd865  test    eax, eax
0x1801fd867  jz      short loc_1801FD8CE
0x1801fd869  cmp     cs:?g_dmDiagnosticMode@@3HA, r14d; int g_dmDiagnosticMode
0x1801fd870  jz      short loc_1801FD8C9
0x1801fd872  mov     rax, [r12]
0x1801fd876  mov     rcx, r12
0x1801fd879  mov     rax, [rax+50h]
0x1801fd87d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801fd882  lea     rcx, aNull; "(NULL)"
0x1801fd889  mov     [rsp+120h+var_C8], r14; void *
0x1801fd88e  mov     [rsp+120h+var_D0], r14d; unsigned int
0x1801fd893  lea     r9, aWarningResetpe; "Warning: ResetPeriod is <blank>. Trying"...
0x1801fd89a  mov     [rsp+120h+var_D8], rcx; unsigned __int16 *
0x1801fd89f  xor     edx, edx; unsigned __int16
0x1801fd8a1  mov     [rsp+120h+var_E0], rcx; unsigned __int16 *
0x1801fd8a6  xor     r8d, r8d; int
0x1801fd8a9  mov     [rsp+120h+var_E8], rcx; unsigned __int16 *
0x1801fd8ae  mov     [rsp+120h+var_F0], rcx; unsigned __int16 *
0x1801fd8b3  mov     [rsp+120h+var_F8], rcx; unsigned __int16 *
0x1801fd8b8  mov     ecx, r15d; int
0x1801fd8bb  mov     [rsp+120h+var_100], rax; unsigned __int16 *
0x1801fd8c0  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1801fd8c5  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1801fd8c9  mov     [rbp+57h+var_A4], ecx
0x1801fd8cc  jmp     short loc_1801FD8F2
0x1801fd8ce  mov     rax, [r13+0]
0x1801fd8d2  mov     edx, 4
0x1801fd8d7  mov     rcx, r13
0x1801fd8da  mov     rax, [rax+38h]
0x1801fd8de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801fd8e3  movsxd  r14, eax
0x1801fd8e6  mov     [rbp+57h+var_A4], r14d
0x1801fd8ea  test    eax, eax
0x1801fd8ec  js      loc_1801FDF87
0x1801fd8f2  mov     rcx, [r13+0]
0x1801fd8f6  mov     edx, 5
0x1801fd8fb  mov     rax, [rcx+50h]
0x1801fd8ff  mov     rcx, r13
0x1801fd902  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801fd907  mov     rcx, [r13+0]
0x1801fd90b  mov     edx, 6
0x1801fd910  mov     [rbp+57h+var_70], rax
0x1801fd914  mov     rax, [rcx+50h]
0x1801fd918  mov     rcx, r13
0x1801fd91b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801fd920  mov     rcx, [r13+0]
0x1801fd924  mov     edx, 7
0x1801fd929  mov     [rbp+57h+var_78], rax
0x1801fd92d  mov     rax, [rcx+48h]
0x1801fd931  mov     rcx, r13
0x1801fd934  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801fd939  mov     rcx, qword ptr cs:?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x1801fd940  mov     rsi, rax
0x1801fd943  mov     rax, [rcx+10h]
0x1801fd947  mov     rcx, rbx
0x1801fd94a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801fd94f  mov     rax, [r13+0]
0x1801fd953  mov     edx, 8
0x1801fd958  mov     rcx, r13
0x1801fd95b  mov     rax, [rax+48h]
0x1801fd95f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801fd964  mov     rcx, qword ptr cs:?s_NullString@MsiString@@0VCMsiStringNullCopy@@A; CMsiStringNullCopy MsiString::s_NullString
0x1801fd96b  mov     r14, rax
0x1801fd96e  mov     rax, [rcx+10h]
0x1801fd972  mov     rcx, rbx
0x1801fd975  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801fd97a  lea     r8, [rbp+57h+arg_8]; int *
0x1801fd97e  mov     [rbp+57h+arg_8], 0
0x1801fd985  mov     rdx, rsi; struct IMsiString *
0x1801fd988  mov     dword ptr [rbp+57h+arg_10], 0
0x1801fd98f  mov     rbx, r14
0x1801fd992  call    ?NewArgumentArray@CMsiOpExecute@@IEAAPEAPEAGAEBVIMsiString@@AEAH@Z; CMsiOpExecute::NewArgumentArray(IMsiString const &,int &)
0x1801fd997  lea     r8, [rbp+57h+arg_10]; int *
0x1801fd99b  mov     [rbp+57h+var_90], rax
0x1801fd99f  mov     rdx, r14; struct IMsiString *
0x1801fd9a2  call    ?NewArgumentArray@CMsiOpExecute@@IEAAPEAPEAGAEBVIMsiString@@AEAH@Z; CMsiOpExecute::NewArgumentArray(IMsiString const &,int &)
0x1801fd9a7  movsxd  r14, [rbp+57h+arg_8]
0x1801fd9ab  mov     [rbp+57h+var_88], rax
0x1801fd9af  cmp     r14d, dword ptr [rbp+57h+arg_10]
0x1801fd9b3  jz      loc_1801FDA9A
0x1801fd9b9  xor     r13d, r13d
0x1801fd9bc  cmp     cs:?g_dmDiagnosticMode@@3HA, r13d; int g_dmDiagnosticMode
0x1801fd9c3  jz      loc_1801FDA5E
0x1801fd9c9  mov     rcx, [r12]
0x1801fd9cd  mov     rax, [rcx+50h]
0x1801fd9d1  mov     rcx, r12
0x1801fd9d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801fd9d9  mov     edx, dword ptr [rbp+57h+arg_10]; int
0x1801fd9dc  lea     rcx, [rbp+57h+var_A0]; this
0x1801fd9e0  mov     r15, rax
0x1801fd9e3  call    ??0MsiString@@QEAA@H@Z; MsiString::MsiString(int)
0x1801fd9e8  mov     rcx, [rax]
0x1801fd9eb  mov     r8, [rcx]
0x1801fd9ee  mov     rax, [r8+50h]
0x1801fd9f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801fd9f7  mov     edx, [rbp+57h+arg_8]; int
0x1801fd9fa  lea     rcx, [rbp+57h+arg_18]; this
0x1801fd9fe  mov     r14, rax
0x1801fda01  call    ??0MsiString@@QEAA@H@Z; MsiString::MsiString(int)
0x1801fda06  mov     rcx, [rax]
0x1801fda09  mov     rdx, [rcx]
0x1801fda0c  mov     rax, [rdx+50h]
0x1801fda10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801fda15  mov     [rsp+120h+var_C8], r13; void *
0x1801fda1a  lea     rcx, aNull; "(NULL)"
0x1801fda21  mov     [rsp+120h+var_D0], r13d; unsigned int
0x1801fda26  lea     r9, aErrorNumberOfA; "Error: Number of Actions (%s) != Number"...
0x1801fda2d  mov     [rsp+120h+var_D8], rcx; unsigned __int16 *
0x1801fda32  xor     edx, edx; unsigned __int16
0x1801fda34  mov     [rsp+120h+var_E0], rcx; unsigned __int16 *
0x1801fda39  xor     r8d, r8d; int
0x1801fda3c  mov     [rsp+120h+var_E8], rcx; unsigned __int16 *
0x1801fda41  mov     [rsp+120h+var_F0], r15; unsigned __int16 *
0x1801fda46  mov     [rsp+120h+var_F8], r14; unsigned __int16 *
0x1801fda4b  lea     ecx, [rdx+9]; int
0x1801fda4e  mov     [rsp+120h+var_100], rax; unsigned __int16 *
0x1801fda53  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1801fda58  lea     r14d, [r13+3]
0x1801fda5c  jmp     short loc_1801FDA61
0x1801fda5e  mov     r14d, r13d
0x1801fda61  test    r14b, 2
0x1801fda65  jz      short loc_1801FDA7B
0x1801fda67  mov     rcx, [rbp+57h+arg_18]
0x1801fda6b  and     r14d, 0FFFFFFFDh
0x1801fda6f  mov     rax, [rcx]
0x1801fda72  mov     rax, [rax+10h]
0x1801fda76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801fda7b  test    r14b, 1
0x1801fda7f  jz      loc_1801FDFE6
0x1801fda85  mov     rcx, [rbp+57h+var_A0]
0x1801fda89  mov     rax, [rcx]
0x1801fda8c  mov     rax, [rax+10h]
0x1801fda90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801fda95  jmp     loc_1801FDFE6
0x1801fda9a  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1801fdaa1  mov     eax, 8
0x1801fdaa6  mul     r14
0x1801fdaa9  cmovb   rax, rcx
0x1801fdaad  mov     rcx, rax; unsigned __int64
0x1801fdab0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1801fdab5  mov     [rbp+57h+var_C0], rax
0x1801fdab9  test    rax, rax
0x1801fdabc  jnz     short loc_1801FDB34
0x1801fdabe  xor     r13d, r13d
0x1801fdac1  cmp     cs:?g_dmDiagnosticMode@@3HA, r13d; int g_dmDiagnosticMode
0x1801fdac8  jz      short loc_1801FDB28
0x1801fdaca  mov     rcx, [r12]
0x1801fdace  mov     rax, [rcx+50h]
0x1801fdad2  mov     rcx, r12
0x1801fdad5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801fdada  mov     r14, rax
0x1801fdadd  call    cs:__imp_GetLastError
0x1801fdae3  mov     [rsp+120h+var_C8], r13; void *
0x1801fdae8  lea     r9, aErrorDFailedTo_5; "Error: %d. Failed to change configurati"...
0x1801fdaef  mov     [rsp+120h+var_D0], r13d; unsigned int
0x1801fdaf4  mov     ecx, eax
0x1801fdaf6  lea     rax, aNull; "(NULL)"
0x1801fdafd  mov     [rsp+120h+var_D8], rax; unsigned __int16 *
0x1801fdb02  mov     [rsp+120h+var_E0], rax; unsigned __int16 *
0x1801fdb07  mov     [rsp+120h+var_E8], rax; unsigned __int16 *
0x1801fdb0c  mov     [rsp+120h+var_F0], rax; unsigned __int16 *
0x1801fdb11  mov     [rsp+120h+var_F8], r14; unsigned __int16 *
0x1801fdb16  mov     [rsp+120h+var_100], rcx; unsigned __int16 *
0x1801fdb1b  xor     edx, edx; unsigned __int16
0x1801fdb1d  xor     r8d, r8d; int
0x1801fdb20  mov     ecx, r15d; int
0x1801fdb23  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1801fdb28  mov     r15, [rbp+57h+var_C0]
0x1801fdb2c  mov     r14b, r13b
0x1801fdb2f  jmp     loc_1801FE026
0x1801fdb34  xor     eax, eax
0x1801fdb36  mov     [rbp+57h+var_A8], eax
0x1801fdb39  cmp     eax, r14d
0x1801fdb3c  jge     loc_1801FDC10
0x1801fdb42  movsxd  r14, eax
0x1801fdb45  lea     rdx, [rbp+57h+arg_10]; enum Bool *
0x1801fdb49  mov     rax, [rbp+57h+var_90]
0x1801fdb4d  mov     dword ptr [rbp+57h+arg_10], 0
0x1801fdb54  mov     dword ptr [rbp+57h+arg_18], 0
0x1801fdb5b  mov     rcx, [rax+r14*8]; unsigned __int16 *
0x1801fdb5f  call    ?GetIntegerValue@@YAHPEBGPEAW4Bool@@@Z; GetIntegerValue(ushort const *,Bool *)
0x1801fdb64  mov     dword ptr [rbp+57h+var_A0], eax
0x1801fdb67  lea     rdx, [rbp+57h+arg_18]; enum Bool *
0x1801fdb6b  mov     rax, [rbp+57h+var_88]
0x1801fdb6f  mov     rcx, [rax+r14*8]; unsigned __int16 *
0x1801fdb73  call    ?GetIntegerValue@@YAHPEBGPEAW4Bool@@@Z; GetIntegerValue(ushort const *,Bool *)
0x1801fdb78  cmp     dword ptr [rbp+57h+arg_10], 0
0x1801fdb7c  mov     ecx, eax
0x1801fdb7e  jz      short loc_1801FDBA5
0x1801fdb80  cmp     dword ptr [rbp+57h+arg_18], 0
0x1801fdb84  jz      short loc_1801FDBA5
0x1801fdb86  test    eax, eax
0x1801fdb88  js      short loc_1801FDBA5
0x1801fdb8a  mov     rax, [rbp+57h+var_C0]
0x1801fdb8e  mov     edx, dword ptr [rbp+57h+var_A0]
0x1801fdb91  mov     [rax+r14*8], edx
0x1801fdb95  mov     [rax+r14*8+4], ecx
0x1801fdb9a  mov     eax, [rbp+57h+var_A8]
0x1801fdb9d  mov     r14d, [rbp+57h+arg_8]
0x1801fdba1  inc     eax
0x1801fdba3  jmp     short loc_1801FDB36
0x1801fdba5  xor     r13d, r13d
0x1801fdba8  cmp     cs:?g_dmDiagnosticMode@@3HA, r13d; int g_dmDiagnosticMode
0x1801fdbaf  jz      loc_1801FDB28
0x1801fdbb5  mov     rax, [r12]
0x1801fdbb9  mov     rcx, r12
0x1801fdbbc  mov     rax, [rax+50h]
  ... truncated ...
```
