# COpenTask::TaskRoutine(void)

- ea: `0x18009f590`
- end: `0x18009f6d9`
- name: `?TaskRoutine@COpenTask@@UEAAXXZ`
- size: `329`
- prototype: `void __fastcall(COpenTask *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1800063b0`
- `0x18009e0e8`
- `0x18009f590`
- `0x1800bd010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009f5e1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009f5e1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009f5c3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009f5c3`

## string_xrefs

- `0x18009f60a`: `COpenTask::TaskRoutine`
- `0x18009f5f5`: `COpenTask::TaskRoutine - calling xa_open - DLL=%S`
- `0x18009f662`: `COpenTask::TaskRoutine - returned from xa_open with error=%d - DLL=%S`
- `0x18009f61c`: `com\complus\dtc\dtc\xatm\src\xataskmgr.cpp`
- `0x18009f682`: `com\complus\dtc\dtc\xatm\src\xataskmgr.cpp`

## pseudocode

```c
void __fastcall COpenTask::TaskRoutine(COpenTask *this)
{
  int v2; // [rsp+20h] [rbp-38h]
  __int64 v3; // [rsp+28h] [rbp-30h]
  __int64 v4; // [rsp+38h] [rbp-20h]

  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 11) + 32LL))(*((_QWORD *)this + 11));
  if ( CTaskManager::m_bDoTaskClock )
  {
    EnterCriticalSection(&stru_180153898);
    **((_DWORD **)this + 14) = *((_DWORD *)CTaskManager::GetMyXaOpenState(*((_DWORD *)this + 20)) + 29);
    LeaveCriticalSection(&stru_180153898);
  }
  else
  {
    try
    {
      TraceStringInline(
        11,
        4,
        L"com\\complus\\dtc\\dtc\\xatm\\src\\xataskmgr.cpp",
        1075,
        L"COpenTask::TaskRoutine",
        0,
        L"COpenTask::TaskRoutine - calling xa_open - DLL=%S",
        *((_QWORD *)this + 8));
      **((_DWORD **)this + 14) = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(*((_QWORD *)this + 12) + 40LL))(
                                   *((_QWORD *)this + 13),
                                   *((unsigned int *)this + 20),
                                   0);
      LODWORD(v4) = **((_DWORD **)this + 14);
      TraceStringInline(
        11,
        4,
        L"com\\complus\\dtc\\dtc\\xatm\\src\\xataskmgr.cpp",
        1079,
        L"COpenTask::TaskRoutine",
        0,
        L"COpenTask::TaskRoutine - returned from xa_open with error=%d - DLL=%S",
        v4,
        *((_QWORD *)this + 8));
    }
    catch ( ... )
    {
      LODWORD(v3) = -2147430319;
      TraceStringInline(
        11,
        1,
        L"com\\complus\\dtc\\dtc\\xatm\\src\\xataskmgr.cpp",
        1084,
        L"COpenTask::TaskRoutine",
        v3,
        L"COpenTask::TaskRoutine - exception thrown calling xa_open - DLL=%S",
        *((_QWORD *)this + 8));
      XA_TRACE_WARNING(0x8000D051, "com\\complus\\dtc\\dtc\\xatm\\src\\xataskmgr.cpp", 1085, *((char **)this + 8), v2);
      DtcXaException("xa_open");
    }
  }
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 11) + 40LL))(*((_QWORD *)this + 11));
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 11) + 24LL))(*((_QWORD *)this + 11));
  *((_QWORD *)this + 11) = 0;
  (*(void (__fastcall **)(COpenTask *))(*(_QWORD *)this + 16LL))(this);
}

```

## disassembly

```asm
0x18009f590  mov     [rsp+arg_8], rbx
0x18009f595  mov     [rsp+arg_0], rcx
0x18009f59a  push    r15
0x18009f59c  sub     rsp, 50h
0x18009f5a0  mov     rbx, rcx
0x18009f5a3  mov     rcx, [rcx+58h]
0x18009f5a7  mov     rax, [rcx]
0x18009f5aa  mov     rax, [rax+20h]
0x18009f5ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f5b3  cmp     cs:?m_bDoTaskClock@CTaskManager@@0HA, 0; int CTaskManager::m_bDoTaskClock
0x18009f5ba  jz      short loc_18009F5EC
0x18009f5bc  lea     rcx, stru_180153898; lpCriticalSection
0x18009f5c3  call    cs:__imp_EnterCriticalSection
0x18009f5c9  mov     ecx, [rbx+50h]; unsigned int
0x18009f5cc  call    ?GetMyXaOpenState@CTaskManager@@SAPEAVCXaOpenState@@I@Z; CTaskManager::GetMyXaOpenState(uint)
0x18009f5d1  mov     rdx, [rbx+70h]
0x18009f5d5  mov     eax, [rax+74h]
0x18009f5d8  mov     [rdx], eax
0x18009f5da  lea     rcx, stru_180153898; lpCriticalSection
0x18009f5e1  call    cs:__imp_LeaveCriticalSection
0x18009f5e7  jmp     loc_18009F697
0x18009f5ec  mov     rax, [rbx+40h]
0x18009f5f0  mov     [rsp+58h+var_20], rax
0x18009f5f5  lea     rax, aCopentaskTaskr_2; "COpenTask::TaskRoutine - calling xa_ope"...
0x18009f5fc  mov     [rsp+58h+var_28], rax
0x18009f601  mov     [rsp+58h+var_30], 0
0x18009f60a  lea     r15, aCopentaskTaskr_0; "COpenTask::TaskRoutine"
0x18009f611  mov     [rsp+58h+var_38], r15
0x18009f616  mov     r9d, 433h
0x18009f61c  lea     r8, aComComplusDtcD_0; "com\\complus\\dtc\\dtc\\xatm\\src\\xata"...
0x18009f623  mov     edx, 4
0x18009f628  lea     ecx, [rdx+7]
0x18009f62b  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18009f630  mov     rax, [rbx+60h]
0x18009f634  xor     r8d, r8d
0x18009f637  mov     edx, [rbx+50h]
0x18009f63a  mov     rcx, [rbx+68h]
0x18009f63e  mov     rax, [rax+28h]
0x18009f642  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f647  mov     r9, [rbx+70h]
0x18009f64b  mov     [r9], eax
0x18009f64e  mov     r9, [rbx+70h]
0x18009f652  mov     rax, [rbx+40h]
0x18009f656  mov     [rsp+58h+var_18], rax
0x18009f65b  mov     eax, [r9]
0x18009f65e  mov     dword ptr [rsp+58h+var_20], eax
0x18009f662  lea     rax, aCopentaskTaskr; "COpenTask::TaskRoutine - returned from "...
0x18009f669  mov     [rsp+58h+var_28], rax
0x18009f66e  mov     [rsp+58h+var_30], 0
0x18009f677  mov     [rsp+58h+var_38], r15
0x18009f67c  mov     r9d, 437h
0x18009f682  lea     r8, aComComplusDtcD_0; "com\\complus\\dtc\\dtc\\xatm\\src\\xata"...
0x18009f689  mov     edx, 4
0x18009f68e  lea     ecx, [rdx+7]
0x18009f691  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18009f696  nop
0x18009f697  mov     rcx, [rbx+58h]
0x18009f69b  mov     rax, [rcx]
0x18009f69e  mov     rax, [rax+28h]
0x18009f6a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f6a7  mov     rcx, [rbx+58h]
0x18009f6ab  mov     rax, [rcx]
0x18009f6ae  mov     rax, [rax+18h]
0x18009f6b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f6b7  mov     qword ptr [rbx+58h], 0
0x18009f6bf  mov     rax, [rbx]
0x18009f6c2  mov     rcx, rbx
0x18009f6c5  mov     rax, [rax+10h]
0x18009f6c9  mov     rbx, [rsp+58h+arg_8]
0x18009f6ce  add     rsp, 50h
0x18009f6d2  pop     r15
0x18009f6d4  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
