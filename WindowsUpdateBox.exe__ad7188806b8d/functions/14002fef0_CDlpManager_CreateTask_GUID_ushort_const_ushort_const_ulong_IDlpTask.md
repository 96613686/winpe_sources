# CDlpManager::CreateTask(_GUID,ushort const *,ushort const *,ulong,IDlpTask * *)

- ea: `0x14002fef0`
- end: `0x1400305ca`
- name: `?CreateTask@CDlpManager@@UEAAJU_GUID@@PEBG1KPEAPEAVIDlpTask@@@Z`
- size: `1754`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this, struct _GUID *, const unsigned __int16 *, OLECHAR *, unsigned int, struct IDlpTask **)`
- caller_count: `0`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400076c8`
- `0x1400135b8`
- `0x14002bd40`
- `0x14002d930`
- `0x14002f83c`
- `0x14002fef0`
- `0x140034ab4`
- `0x140040240`
- `0x140041e6c`
- `0x140082010`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140030541`
- `KERNEL32!HeapFree` at `0x140030541`
- `KERNEL32!GetProcessHeap` at `0x14003052c`
- `KERNEL32!GetProcessHeap` at `0x14003052c`
- `KERNEL32!LeaveCriticalSection` at `0x1400305a2`
- `KERNEL32!LeaveCriticalSection` at `0x1400305a2`
- `KERNEL32!EnterCriticalSection` at `0x14002ff34`
- `KERNEL32!EnterCriticalSection` at `0x14002ff34`
- `OLEAUT32!__imp_SysFreeString` at `0x140030517`
- `OLEAUT32!__imp_SysFreeString` at `0x140030517`

## string_xrefs

- `0x14002ffb6`: `CDlpManager::CreateTask`
- `0x140030095`: `CDlpManager::CreateTask`
- `0x14003032b`: `CDlpManager::CreateTask`
- `0x140030468`: `CDlpManager::CreateTask`
- `0x14003024f`: `CreateTask: Name = [%s], WorkingPath = [%s%s], TransportId = [%s], Flags = [0x%X]`
- `0x1400304ea`: `CreateTask: Error serializing state!  [0x%x]`

## pseudocode

```c
__int64 __fastcall CDlpManager::CreateTask(
        struct _RTL_CRITICAL_SECTION *this,
        struct _GUID *a2,
        const unsigned __int16 *a3,
        OLECHAR *a4,
        unsigned int a5,
        struct IDlpTask **a6)
{
  enum WINDLP_STATE *v9; // rdx
  struct CDlpTask *v10; // rbx
  __int64 v11; // rdi
  __int64 v12; // rsi
  int v13; // r14d
  __int64 v14; // rax
  unsigned int v15; // r15d
  int v16; // eax
  __int64 v17; // rcx
  __int64 v18; // rax
  unsigned int v19; // esi
  int v20; // eax
  struct _RTL_CRITICAL_SECTION *v21; // rsi
  __int64 v22; // rax
  BSTR v23; // r14
  __int64 v24; // rax
  const wchar_t *v25; // rcx
  const int *v26; // r9
  __int64 v27; // rax
  unsigned int v28; // ebx
  int v29; // eax
  struct CDlpTask *v30; // rax
  __int64 v31; // rcx
  __int64 v32; // rax
  unsigned int v33; // edi
  int v34; // eax
  struct CDlpTask *v35; // rax
  __int64 v36; // rax
  HANDLE ProcessHeap; // rax
  __int64 v39; // [rsp+20h] [rbp-99h]
  int v40; // [rsp+20h] [rbp-99h]
  __int64 v41; // [rsp+28h] [rbp-91h]
  __int64 v42; // [rsp+40h] [rbp-79h] BYREF
  __int64 v43; // [rsp+48h] [rbp-71h] BYREF
  struct CDlpTask *v44; // [rsp+50h] [rbp-69h] BYREF
  BSTR bstrString; // [rsp+58h] [rbp-61h] BYREF
  __int64 v46; // [rsp+60h] [rbp-59h] BYREF
  __int128 v47; // [rsp+70h] [rbp-49h] BYREF
  struct IDlpTask **v48; // [rsp+80h] [rbp-39h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+88h] [rbp-31h]
  __int64 v50; // [rsp+90h] [rbp-29h]
  int v51; // [rsp+A8h] [rbp-11h]

  v50 = -2;
  *(_QWORD *)&v47 = a2;
  v48 = a6;
  lpCriticalSection = this + 5;
  EnterCriticalSection(this + 5);
  LODWORD(v43) = 1;
  v51 = 1;
  v10 = 0;
  v44 = 0;
  v11 = 0;
  v46 = 0;
  v12 = 0;
  v42 = 0;
  bstrString = 0;
  if ( a6 )
  {
    if ( a5 )
    {
      v13 = -2147024809;
      if ( !((__int64 (__fastcall *)(struct _RTL_CRITICAL_SECTION *))this[2].DebugInfo->ProcessLocksList.Flink)(&this[2]) )
        goto LABEL_74;
      v14 = ((__int64 (__fastcall *)(struct _RTL_CRITICAL_SECTION *))this[2].DebugInfo->ProcessLocksList.Flink)(&this[2]);
      v15 = 0;
      if ( !v14 )
        goto LABEL_7;
      v40 = 613;
      goto LABEL_5;
    }
    v13 = CDlpManager::CheckInitialized((CDlpManager *)this, v9);
    if ( v13 >= 0 )
    {
      if ( a3 && !*a3 )
      {
        v13 = -2147024809;
        if ( !((__int64 (__fastcall *)(struct _RTL_CRITICAL_SECTION *))this[2].DebugInfo->ProcessLocksList.Flink)(&this[2]) )
          goto LABEL_74;
        v14 = ((__int64 (__fastcall *)(struct _RTL_CRITICAL_SECTION *))this[2].DebugInfo->ProcessLocksList.Flink)(&this[2]);
        v15 = 0;
        if ( !v14 )
          goto LABEL_7;
        v40 = 621;
        goto LABEL_5;
      }
      if ( a4
        || (v13 = ((__int64 (__fastcall *)(struct _RTL_CRITICAL_SECTION *, BSTR *))this->DebugInfo[5].ProcessLocksList.Blink)(
                    this,
                    &bstrString),
            v13 >= 0) )
      {
        v13 = CDlpHelpersT<CEmptyType>::GuidToSString(v47, &v42);
        v21 = this + 2;
        v22 = ((__int64 (__fastcall *)(struct _RTL_CRITICAL_SECTION *))this[2].DebugInfo->ProcessLocksList.Flink)(&this[2]);
        if ( v13 >= 0 )
        {
          if ( v22 )
          {
            v23 = a4;
            if ( !a4 )
              v23 = bstrString;
            v24 = ((__int64 (__fastcall *)(struct _RTL_CRITICAL_SECTION *))v21->DebugInfo->ProcessLocksList.Flink)(this + 2);
            v25 = (const wchar_t *)&dword_1400860C4;
            if ( !a4 )
              v25 = L"(inherited) ";
            v26 = (const int *)a3;
            if ( !a3 )
              v26 = &dword_1400860C4;
            CDlpLogT<CEmptyType>::DlpLogFormat(
              v24,
              2,
              L"CreateTask: Name = [%s], WorkingPath = [%s%s], TransportId = [%s], Flags = [0x%X]",
              v26,
              v25,
              v23,
              v42,
              0);
          }
          if ( !a3
            || (*(unsigned int (__fastcall **)(struct _RTL_CRITICAL_SECTION *, const unsigned __int16 *, __int64 *))&this->DebugInfo[5].Type)(
                 this,
                 a3,
                 &v46) == -2147023728 )
          {
            v13 = CDlpTask::CreateInstance((struct IDlpManagerInternal *)this, this[13].RecursionCount, &v44);
            if ( v13 < 0 )
            {
              if ( ((__int64 (__fastcall *)(struct _RTL_CRITICAL_SECTION *))v21->DebugInfo->ProcessLocksList.Flink)(this + 2) )
              {
                v27 = ((__int64 (__fastcall *)(struct _RTL_CRITICAL_SECTION *))v21->DebugInfo->ProcessLocksList.Flink)(this + 2);
                v28 = 0;
                if ( v27 )
                {
                  LODWORD(v41) = v13;
                  LODWORD(v39) = 649;
                  v29 = CDlpLogT<CEmptyType>::DlpLogFormat(
                          v27,
                          4,
                          L"%s(%d): Result = 0x%X",
                          L"CDlpManager::CreateTask",
                          v39,
                          v41);
                  v28 = v29;
                  if ( v29 < 0 )
                    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v29);
                }
                CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v28);
              }
              v10 = v44;
              goto LABEL_74;
            }
            v47 = *(_OWORD *)v47;
            v10 = v44;
            v13 = CDlpTask::Initialize(v44, &v47, a3, a4, 0, 1);
            if ( v13 >= 0 )
            {
              if ( v10 )
              {
                v30 = v10;
                LOBYTE(v43) = 0;
              }
              else
              {
                v30 = 0;
              }
              v31 = 0;
              if ( !(_BYTE)v43 )
                v31 = (__int64)v30;
              v43 = v31;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 8LL))(v31);
              v13 = CArray<DP_COM<IUnknown>,DP_COM<IUnknown>,CAdaptorDefault,CPoliciesDefault>::Append(
                      (__int64)&this[13].LockCount,
                      &v43);
              if ( v13 >= 0 )
              {
                v35 = v10;
                v10 = 0;
                *v48 = v35;
                v13 = (*(__int64 (__fastcall **)(struct _RTL_CRITICAL_SECTION *, _QWORD))&this->DebugInfo[5].Flags)(
                        this,
                        0);
                if ( v13 < 0 )
                {
                  if ( ((__int64 (__fastcall *)(struct _RTL_CRITICAL_SECTION *))v21->DebugInfo->ProcessLocksList.Flink)(this + 2) )
                  {
                    v36 = ((__int64 (__fastcall *)(struct _RTL_CRITICAL_SECTION *))v21->DebugInfo->ProcessLocksList.Flink)(this + 2);
                    CDlpLogT<CEmptyType>::DlpLogFormat(
                      v36,
                      4,
                      L"CreateTask: Error serializing state!  [0x%x]",
                      (unsigned int)v13);
                  }
                  v13 = 0;
                }
              }
              else if ( ((__int64 (__fastcall *)(struct _RTL_CRITICAL_SECTION *))v21->DebugInfo->ProcessLocksList.Flink)(this + 2) )
              {
                v32 = ((__int64 (__fastcall *)(struct _RTL_CRITICAL_SECTION *))v21->DebugInfo->ProcessLocksList.Flink)(this + 2);
                v33 = 0;
                if ( v32 )
                {
                  LODWORD(v41) = v13;
                  LODWORD(v39) = 663;
                  v34 = CDlpLogT<CEmptyType>::DlpLogFormat(
                          v32,
                          4,
                          L"%s(%d): Result = 0x%X",
                          L"CDlpManager::CreateTask",
                          v39,
                          v41);
                  v33 = v34;
                  if ( v34 < 0 )
                    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v34);
                }
                CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v33);
              }
              v11 = v43;
              goto LABEL_74;
            }
            if ( !((__int64 (__fastcall *)(struct _RTL_CRITICAL_SECTION *))v21->DebugInfo->ProcessLocksList.Flink)(this + 2) )
              goto LABEL_74;
            v18 = ((__int64 (__fastcall *)(struct _RTL_CRITICAL_SECTION *))v21->DebugInfo->ProcessLocksList.Flink)(this + 2);
            v19 = 0;
            if ( !v18 )
            {
LABEL_19:
              v17 = v19;
              goto LABEL_8;
            }
            LODWORD(v41) = v13;
            LODWORD(v39) = 657;
          }
          else
          {
            v13 = -2147024713;
            if ( !((__int64 (__fastcall *)(struct _RTL_CRITICAL_SECTION *))v21->DebugInfo->ProcessLocksList.Flink)(this + 2) )
              goto LABEL_74;
            v18 = ((__int64 (__fastcall *)(struct _RTL_CRITICAL_SECTION *))v21->DebugInfo->ProcessLocksList.Flink)(this + 2);
            v19 = 0;
            if ( !v18 )
              goto LABEL_19;
            LODWORD(v41) = -2147024713;
            LODWORD(v39) = 642;
          }
        }
        else
        {
          if ( !v22 )
            goto LABEL_74;
          v18 = ((__int64 (__fastcall *)(struct _RTL_CRITICAL_SECTION *))v21->DebugInfo->ProcessLocksList.Flink)(this + 2);
          v19 = 0;
          if ( !v18 )
            goto LABEL_19;
          LODWORD(v41) = v13;
          LODWORD(v39) = 629;
        }
      }
      else
      {
        if ( !((__int64 (__fastcall *)(struct _RTL_CRITICAL_SECTION *))this[2].DebugInfo->ProcessLocksList.Flink)(&this[2]) )
          goto LABEL_75;
        v18 = ((__int64 (__fastcall *)(struct _RTL_CRITICAL_SECTION *))this[2].DebugInfo->ProcessLocksList.Flink)(&this[2]);
        v19 = 0;
        if ( !v18 )
          goto LABEL_19;
        LODWORD(v41) = v13;
        LODWORD(v39) = 626;
      }
    }
    else
    {
      if ( !((__int64 (__fastcall *)(struct _RTL_CRITICAL_SECTION *))this[2].DebugInfo->ProcessLocksList.Flink)(&this[2]) )
        goto LABEL_75;
      v18 = ((__int64 (__fastcall *)(struct _RTL_CRITICAL_SECTION *))this[2].DebugInfo->ProcessLocksList.Flink)(&this[2]);
      v19 = 0;
      if ( !v18 )
        goto LABEL_19;
      LODWORD(v41) = v13;
      LODWORD(v39) = 617;
    }
    v20 = CDlpLogT<CEmptyType>::DlpLogFormat(v18, 4, L"%s(%d): Result = 0x%X", L"CDlpManager::CreateTask", v39, v41);
    v19 = v20;
    if ( v20 < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v20);
    goto LABEL_19;
  }
  v13 = -2147024809;
  if ( ((__int64 (__fastcall *)(struct _RTL_CRITICAL_SECTION *))this[2].DebugInfo->ProcessLocksList.Flink)(&this[2]) )
  {
    v14 = ((__int64 (__fastcall *)(struct _RTL_CRITICAL_SECTION *))this[2].DebugInfo->ProcessLocksList.Flink)(&this[2]);
    v15 = 0;
    if ( !v14 )
    {
LABEL_7:
      v17 = v15;
LABEL_8:
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v17);
      goto LABEL_74;
    }
    v40 = 612;
LABEL_5:
    v16 = CDlpLogT<CEmptyType>::DlpLogFormat(
            v14,
            4,
            L"%s(%d): Result = 0x%X",
            L"CDlpManager::CreateTask",
            v40,
            -2147024809);
    v15 = v16;
    if ( v16 < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v16);
    goto LABEL_7;
  }
LABEL_74:
  v12 = v42;
LABEL_75:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v13);
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  if ( v12 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, (LPVOID)(v12 - 4));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v46 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
    v46 = 0;
  }
  if ( v11 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  if ( v10 )
    (*(void (__fastcall **)(struct CDlpTask *))(*(_QWORD *)v10 + 16LL))(v10);
  if ( v51 )
  {
    LeaveCriticalSection(lpCriticalSection);
    v51 = 0;
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x14002fef0  push    rbp
0x14002fef2  push    rbx
0x14002fef3  push    rsi
0x14002fef4  push    rdi
0x14002fef5  push    r12
0x14002fef7  push    r13
0x14002fef9  push    r14
0x14002fefb  push    r15
0x14002fefd  lea     rbp, [rsp-0Fh]
0x14002ff02  sub     rsp, 0C8h
0x14002ff09  mov     [rbp+47h+var_70], 0FFFFFFFFFFFFFFFEh
0x14002ff11  mov     r13, r9
0x14002ff14  mov     r12, r8
0x14002ff17  mov     qword ptr [rbp+47h+var_90], rdx
0x14002ff1b  mov     r15, rcx
0x14002ff1e  mov     r14, [rbp+47h+arg_28]
0x14002ff22  mov     [rbp+47h+var_80], r14
0x14002ff26  lea     rax, [rcx+0C8h]
0x14002ff2d  mov     [rbp+47h+lpCriticalSection], rax
0x14002ff31  mov     rcx, rax; lpCriticalSection
0x14002ff34  call    cs:__imp_EnterCriticalSection
0x14002ff3b  nop     dword ptr [rax+rax+00h]
0x14002ff40  mov     eax, 1
0x14002ff45  mov     dword ptr [rbp+47h+var_B8], eax
0x14002ff48  mov     [rbp+47h+var_58], eax
0x14002ff4b  xor     eax, eax
0x14002ff4d  mov     ebx, eax
0x14002ff4f  mov     [rbp+47h+var_B0], rax
0x14002ff53  mov     edi, eax
0x14002ff55  mov     [rbp+47h+var_A0], rax
0x14002ff59  mov     esi, eax
0x14002ff5b  mov     [rbp+47h+var_C0], rax
0x14002ff5f  mov     [rbp+47h+bstrString], rax
0x14002ff63  test    r14, r14
0x14002ff66  jnz     loc_14002FFEC
0x14002ff6c  mov     esi, 80070057h
0x14002ff71  mov     r14d, esi
0x14002ff74  mov     rax, [r15+50h]
0x14002ff78  lea     rcx, [r15+50h]
0x14002ff7c  mov     rax, [rax+10h]
0x14002ff80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002ff85  xor     r12d, r12d
0x14002ff88  test    rax, rax
0x14002ff8b  jz      loc_140030502
0x14002ff91  mov     rax, [r15+50h]
0x14002ff95  lea     rcx, [r15+50h]
0x14002ff99  mov     rax, [rax+10h]
0x14002ff9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002ffa2  mov     r15d, r12d
0x14002ffa5  test    rax, rax
0x14002ffa8  jz      short loc_14002FFDF
0x14002ffaa  mov     dword ptr [rsp+100h+var_D8], esi
0x14002ffae  mov     dword ptr [rsp+100h+var_E0], 264h
0x14002ffb6  lea     r9, aCdlpmanagerCre_2; "CDlpManager::CreateTask"
0x14002ffbd  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x14002ffc4  mov     edx, 4
0x14002ffc9  mov     rcx, rax
0x14002ffcc  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x14002ffd1  test    eax, eax
0x14002ffd3  mov     r15d, eax
0x14002ffd6  jns     short loc_14002FFDF
0x14002ffd8  mov     ecx, eax
0x14002ffda  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x14002ffdf  mov     ecx, r15d
0x14002ffe2  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14002ffe7  jmp     loc_140030502
0x14002ffec  cmp     [rbp+47h+arg_20], eax
0x14002ffef  jz      short loc_140030040
0x14002fff1  mov     esi, 80070057h
0x14002fff6  mov     r14d, esi
0x14002fff9  mov     rax, [r15+50h]
0x14002fffd  lea     rcx, [r15+50h]
0x140030001  mov     rax, [rax+10h]
0x140030005  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003000a  xor     r12d, r12d
0x14003000d  test    rax, rax
0x140030010  jz      loc_140030502
0x140030016  mov     rax, [r15+50h]
0x14003001a  lea     rcx, [r15+50h]
0x14003001e  mov     rax, [rax+10h]
0x140030022  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140030027  mov     r15d, r12d
0x14003002a  test    rax, rax
0x14003002d  jz      short loc_14002FFDF
0x14003002f  mov     dword ptr [rsp+100h+var_D8], esi
0x140030033  mov     dword ptr [rsp+100h+var_E0], 265h
0x14003003b  jmp     loc_14002FFB6
0x140030040  mov     rcx, r15; this
0x140030043  call    ?CheckInitialized@CDlpManager@@AEAAJPEAW4WINDLP_STATE@@@Z; CDlpManager::CheckInitialized(WINDLP_STATE *)
0x140030048  mov     r14d, eax
0x14003004b  xor     eax, eax
0x14003004d  test    r14d, r14d
0x140030050  jns     short loc_1400300C4
0x140030052  mov     rcx, [r15+50h]
0x140030056  mov     rax, [rcx+10h]
0x14003005a  lea     rcx, [r15+50h]
0x14003005e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140030063  xor     r12d, r12d
0x140030066  test    rax, rax
0x140030069  jz      loc_140030506
0x14003006f  mov     rax, [r15+50h]
0x140030073  lea     rcx, [r15+50h]
0x140030077  mov     rax, [rax+10h]
0x14003007b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140030080  mov     esi, r12d
0x140030083  test    rax, rax
0x140030086  jz      short loc_1400300BD
0x140030088  mov     dword ptr [rsp+100h+var_D8], r14d
0x14003008d  mov     dword ptr [rsp+100h+var_E0], 269h
0x140030095  lea     r9, aCdlpmanagerCre_2; "CDlpManager::CreateTask"
0x14003009c  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x1400300a3  mov     edx, 4
0x1400300a8  mov     rcx, rax
0x1400300ab  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x1400300b0  mov     esi, eax
0x1400300b2  test    eax, eax
0x1400300b4  jns     short loc_1400300BD
0x1400300b6  mov     ecx, eax
0x1400300b8  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1400300bd  mov     ecx, esi
0x1400300bf  jmp     loc_14002FFE2
0x1400300c4  test    r12, r12
0x1400300c7  jz      short loc_140030123
0x1400300c9  cmp     [r12], ax
0x1400300ce  jnz     short loc_140030123
0x1400300d0  mov     esi, 80070057h
0x1400300d5  mov     r14d, esi
0x1400300d8  mov     rax, [r15+50h]
0x1400300dc  lea     rcx, [r15+50h]
0x1400300e0  mov     rax, [rax+10h]
0x1400300e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400300e9  xor     r12d, r12d
0x1400300ec  test    rax, rax
0x1400300ef  jz      loc_140030502
0x1400300f5  mov     rax, [r15+50h]
0x1400300f9  lea     rcx, [r15+50h]
0x1400300fd  mov     rax, [rax+10h]
0x140030101  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140030106  mov     r15d, r12d
0x140030109  test    rax, rax
0x14003010c  jz      loc_14002FFDF
0x140030112  mov     dword ptr [rsp+100h+var_D8], esi
0x140030116  mov     dword ptr [rsp+100h+var_E0], 26Dh
0x14003011e  jmp     loc_14002FFB6
0x140030123  test    r13, r13
0x140030126  jnz     short loc_140030191
0x140030128  mov     rax, [r15]
0x14003012b  lea     rdx, [rbp+47h+bstrString]
0x14003012f  mov     rcx, r15
0x140030132  mov     rax, [rax+108h]
0x140030139  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003013e  mov     r14d, eax
0x140030141  test    eax, eax
0x140030143  jns     short loc_140030191
0x140030145  mov     rax, [r15+50h]
0x140030149  lea     rcx, [r15+50h]
0x14003014d  mov     rax, [rax+10h]
0x140030151  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140030156  xor     r12d, r12d
0x140030159  test    rax, rax
0x14003015c  jz      loc_140030506
0x140030162  mov     rax, [r15+50h]
0x140030166  lea     rcx, [r15+50h]
0x14003016a  mov     rax, [rax+10h]
0x14003016e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140030173  mov     esi, r12d
0x140030176  test    rax, rax
0x140030179  jz      loc_1400300BD
0x14003017f  mov     dword ptr [rsp+100h+var_D8], r14d
0x140030184  mov     dword ptr [rsp+100h+var_E0], 272h
0x14003018c  jmp     loc_140030095
0x140030191  lea     rdx, [rbp+47h+var_C0]
0x140030195  mov     rcx, qword ptr [rbp+47h+var_90]
0x140030199  call    ?GuidToSString@?$CDlpHelpersT@VCEmptyType@@@@SAJPEBU_GUID@@PEAPEAG@Z; CDlpHelpersT<CEmptyType>::GuidToSString(_GUID const *,ushort * *)
0x14003019e  mov     r14d, eax
0x1400301a1  lea     rsi, [r15+50h]
0x1400301a5  mov     rax, [rsi]
0x1400301a8  mov     rax, [rax+10h]
0x1400301ac  mov     rcx, rsi
0x1400301af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400301b4  test    r14d, r14d
0x1400301b7  jns     short loc_1400301F2
0x1400301b9  xor     r12d, r12d
0x1400301bc  test    rax, rax
0x1400301bf  jz      loc_140030502
0x1400301c5  mov     rax, [rsi]
0x1400301c8  mov     rcx, rsi
0x1400301cb  mov     rax, [rax+10h]
0x1400301cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400301d4  mov     esi, r12d
0x1400301d7  test    rax, rax
0x1400301da  jz      loc_1400300BD
0x1400301e0  mov     dword ptr [rsp+100h+var_D8], r14d
0x1400301e5  mov     dword ptr [rsp+100h+var_E0], 275h
0x1400301ed  jmp     loc_140030095
0x1400301f2  test    rax, rax
0x1400301f5  jz      short loc_140030263
0x1400301f7  test    r13, r13
0x1400301fa  mov     r14, r13
0x1400301fd  jnz     short loc_140030203
0x1400301ff  mov     r14, [rbp+47h+bstrString]
0x140030203  mov     rax, [rsi]
0x140030206  mov     rcx, rsi
0x140030209  mov     rax, [rax+10h]
0x14003020d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140030212  lea     rdx, aInherited; "(inherited) "
0x140030219  lea     r8, dword_1400860C4
0x140030220  mov     rcx, r8
0x140030223  test    r13, r13
0x140030226  cmovz   rcx, rdx
0x14003022a  mov     r9, r12
0x14003022d  test    r12, r12
0x140030230  cmovz   r9, r8
0x140030234  mov     [rsp+100h+var_C8], 0
0x14003023c  mov     rdx, [rbp+47h+var_C0]
0x140030240  mov     [rsp+100h+var_D0], rdx
0x140030245  mov     [rsp+100h+var_D8], r14
0x14003024a  mov     [rsp+100h+var_E0], rcx
0x14003024f  lea     r8, aCreatetaskName; "CreateTask: Name = [%s], WorkingPath = "...
0x140030256  mov     edx, 2
0x14003025b  mov     rcx, rax
0x14003025e  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x140030263  test    r12, r12
0x140030266  jz      short loc_1400302D6
0x140030268  mov     rax, [r15]
0x14003026b  lea     r8, [rbp+47h+var_A0]
0x14003026f  mov     rdx, r12
0x140030272  mov     rcx, r15
0x140030275  mov     rax, [rax+0F0h]
0x14003027c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140030281  cmp     eax, 80070490h
0x140030286  jz      short loc_1400302D6
0x140030288  mov     r14d, 800700B7h
0x14003028e  mov     rax, [rsi]
0x140030291  mov     rcx, rsi
0x140030294  mov     rax, [rax+10h]
0x140030298  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003029d  xor     r12d, r12d
0x1400302a0  test    rax, rax
0x1400302a3  jz      loc_140030502
0x1400302a9  mov     rax, [rsi]
0x1400302ac  mov     rcx, rsi
0x1400302af  mov     rax, [rax+10h]
0x1400302b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400302b8  mov     esi, r12d
0x1400302bb  test    rax, rax
0x1400302be  jz      loc_1400300BD
0x1400302c4  mov     dword ptr [rsp+100h+var_D8], r14d
0x1400302c9  mov     dword ptr [rsp+100h+var_E0], 282h
0x1400302d1  jmp     loc_140030095
0x1400302d6  lea     r8, [rbp+47h+var_B0]; struct CDlpTask **
0x1400302da  mov     edx, [r15+214h]; unsigned int
0x1400302e1  mov     rcx, r15; struct IDlpManagerInternal *
0x1400302e4  call    ?CreateInstance@CDlpTask@@SAJPEAVIDlpManagerInternal@@KPEAPEAV1@@Z; CDlpTask::CreateInstance(IDlpManagerInternal *,ulong,CDlpTask * *)
0x1400302e9  mov     r14d, eax
0x1400302ec  test    eax, eax
0x1400302ee  jns     short loc_140030363
0x1400302f0  mov     rax, [rsi]
0x1400302f3  mov     rcx, rsi
0x1400302f6  mov     rax, [rax+10h]
0x1400302fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400302ff  xor     r12d, r12d
0x140030302  test    rax, rax
0x140030305  jz      short loc_14003035A
0x140030307  mov     rax, [rsi]
0x14003030a  mov     rcx, rsi
0x14003030d  mov     rax, [rax+10h]
0x140030311  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140030316  mov     ebx, r12d
0x140030319  test    rax, rax
0x14003031c  jz      short loc_140030353
0x14003031e  mov     dword ptr [rsp+100h+var_D8], r14d
0x140030323  mov     dword ptr [rsp+100h+var_E0], 289h
0x14003032b  lea     r9, aCdlpmanagerCre_2; "CDlpManager::CreateTask"
0x140030332  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x140030339  lea     edx, [r12+4]
0x14003033e  mov     rcx, rax
0x140030341  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x140030346  mov     ebx, eax
0x140030348  test    eax, eax
0x14003034a  jns     short loc_140030353
0x14003034c  mov     ecx, eax
0x14003034e  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x140030353  mov     ecx, ebx
0x140030355  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14003035a  mov     rbx, [rbp+47h+var_B0]
0x14003035e  jmp     loc_140030502
0x140030363  mov     rax, qword ptr [rbp+47h+var_90]
0x140030367  movups  xmm0, xmmword ptr [rax]
0x14003036a  movdqu  [rbp+47h+var_90], xmm0
0x14003036f  mov     dword ptr [rsp+100h+var_D8], 1
0x140030377  mov     dword ptr [rsp+100h+var_E0], 0
0x14003037f  mov     r9, r13
0x140030382  mov     r8, r12
0x140030385  lea     rdx, [rbp+47h+var_90]
0x140030389  mov     rbx, [rbp+47h+var_B0]
0x14003038d  mov     rcx, rbx
0x140030390  call    ?Initialize@CDlpTask@@QEAAJU_GUID@@PEBG1W4WINDLP_STATE@@H@Z; CDlpTask::Initialize(_GUID,ushort const *,ushort const *,WINDLP_STATE,int)
0x140030395  mov     r14d, eax
0x140030398  xor     r12d, r12d
  ... truncated ...
```
