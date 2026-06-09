# CRollbackTask::TaskRoutine(void)

- ea: `0x18009fe60`
- end: `0x18009ffcc`
- name: `?TaskRoutine@CRollbackTask@@UEAAXXZ`
- size: `364`
- prototype: `void __fastcall(CRollbackTask *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x1800063b0`
- `0x18009e0e8`
- `0x18009fe60`
- `0x1800a06b8`
- `0x1800bd010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009fec8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009fec8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009fea3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009fea3`

## string_xrefs

- `0x18009ff0b`: `com\complus\dtc\dtc\xatm\src\xataskmgr.cpp`
- `0x18009ff70`: `com\complus\dtc\dtc\xatm\src\xataskmgr.cpp`
- `0x18009fef9`: `CRollbackTask::TaskRoutine`
- `0x18009fee4`: `CRollbackTask::TaskRoutine - calling xa_rollback - DLL=%S`
- `0x18009ff50`: `CRollbackTask::TaskRoutine - returned from xa_rollback with error=%d - DLL=%S`

## pseudocode

```c
void __fastcall CRollbackTask::TaskRoutine(CRollbackTask *this)
{
  unsigned int v2; // edi
  int v3; // [rsp+20h] [rbp-38h]
  __int64 v4; // [rsp+28h] [rbp-30h]
  __int64 v5; // [rsp+38h] [rbp-20h]

  v2 = XaRmId(*((_DWORD *)this + 20));
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 11) + 32LL))(*((_QWORD *)this + 11));
  **((_DWORD **)this + 14) = 0;
  EnterCriticalSection(&stru_180153898);
  if ( *((_DWORD *)CTaskManager::GetMyXaOpenState(*((_DWORD *)this + 20)) + 29) )
    **((_DWORD **)this + 14) = -3;
  LeaveCriticalSection(&stru_180153898);
  if ( !**((_DWORD **)this + 14) )
  {
    try
    {
      TraceStringInline(
        11,
        4,
        L"com\\complus\\dtc\\dtc\\xatm\\src\\xataskmgr.cpp",
        1462,
        L"CRollbackTask::TaskRoutine",
        0,
        L"CRollbackTask::TaskRoutine - calling xa_rollback - DLL=%S",
        *((_QWORD *)this + 8));
      **((_DWORD **)this + 14) = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(*((_QWORD *)this + 12) + 72LL))(
                                   *((_QWORD *)this + 13),
                                   v2,
                                   0);
      LODWORD(v5) = **((_DWORD **)this + 14);
      TraceStringInline(
        11,
        4,
        L"com\\complus\\dtc\\dtc\\xatm\\src\\xataskmgr.cpp",
        1466,
        L"CRollbackTask::TaskRoutine",
        0,
        L"CRollbackTask::TaskRoutine - returned from xa_rollback with error=%d - DLL=%S",
        v5,
        *((_QWORD *)this + 8));
    }
    catch ( ... )
    {
      LODWORD(v4) = -2147430315;
      TraceStringInline(
        11,
        1,
        L"com\\complus\\dtc\\dtc\\xatm\\src\\xataskmgr.cpp",
        1471,
        L"CRollbackTask::TaskRoutine",
        v4,
        L"CRollbackTask::TaskRoutine - exception thrown calling xa_rollback - DLL=%S",
        *((_QWORD *)this + 8));
      XA_TRACE_WARNING(0x8000D055, "com\\complus\\dtc\\dtc\\xatm\\src\\xataskmgr.cpp", 1472, *((char **)this + 8), v3);
      DtcXaException("xa_rollback");
    }
  }
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 11) + 40LL))(*((_QWORD *)this + 11));
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 11) + 24LL))(*((_QWORD *)this + 11));
  *((_QWORD *)this + 11) = 0;
  (*(void (__fastcall **)(CRollbackTask *))(*(_QWORD *)this + 16LL))(this);
}

```

## disassembly

```asm
0x18009fe60  mov     [rsp+arg_8], rbx
0x18009fe65  mov     [rsp+arg_10], rdi
0x18009fe6a  mov     [rsp+arg_0], rcx
0x18009fe6f  push    r12
0x18009fe71  sub     rsp, 50h
0x18009fe75  mov     rbx, rcx
0x18009fe78  mov     ecx, [rcx+50h]; unsigned int
0x18009fe7b  call    ?XaRmId@@YAKI@Z; XaRmId(uint)
0x18009fe80  mov     edi, eax
0x18009fe82  mov     rcx, [rbx+58h]
0x18009fe86  mov     rdx, [rcx]
0x18009fe89  mov     rax, [rdx+20h]
0x18009fe8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009fe92  mov     rcx, [rbx+70h]
0x18009fe96  mov     dword ptr [rcx], 0
0x18009fe9c  lea     rcx, stru_180153898; lpCriticalSection
0x18009fea3  call    cs:__imp_EnterCriticalSection
0x18009fea9  mov     ecx, [rbx+50h]; unsigned int
0x18009feac  call    ?GetMyXaOpenState@CTaskManager@@SAPEAVCXaOpenState@@I@Z; CTaskManager::GetMyXaOpenState(uint)
0x18009feb1  cmp     dword ptr [rax+74h], 0
0x18009feb5  jz      short loc_18009FEC1
0x18009feb7  mov     rax, [rbx+70h]
0x18009febb  mov     dword ptr [rax], 0FFFFFFFDh
0x18009fec1  lea     rcx, stru_180153898; lpCriticalSection
0x18009fec8  call    cs:__imp_LeaveCriticalSection
0x18009fece  mov     rax, [rbx+70h]
0x18009fed2  cmp     dword ptr [rax], 0
0x18009fed5  jnz     loc_18009FF85
0x18009fedb  mov     rax, [rbx+40h]
0x18009fedf  mov     [rsp+58h+var_20], rax
0x18009fee4  lea     rax, aCrollbacktaskT_0; "CRollbackTask::TaskRoutine - calling xa"...
0x18009feeb  mov     [rsp+58h+var_28], rax
0x18009fef0  mov     [rsp+58h+var_30], 0
0x18009fef9  lea     r12, aCrollbacktaskT; "CRollbackTask::TaskRoutine"
0x18009ff00  mov     [rsp+58h+var_38], r12
0x18009ff05  mov     r9d, 5B6h
0x18009ff0b  lea     r8, aComComplusDtcD_0; "com\\complus\\dtc\\dtc\\xatm\\src\\xata"...
0x18009ff12  mov     edx, 4
0x18009ff17  lea     ecx, [rdx+7]
0x18009ff1a  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18009ff1f  mov     rax, [rbx+60h]
0x18009ff23  xor     r8d, r8d
0x18009ff26  mov     edx, edi
0x18009ff28  mov     rcx, [rbx+68h]
0x18009ff2c  mov     rax, [rax+48h]
0x18009ff30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ff35  mov     r9, [rbx+70h]
0x18009ff39  mov     [r9], eax
0x18009ff3c  mov     r9, [rbx+70h]
0x18009ff40  mov     rax, [rbx+40h]
0x18009ff44  mov     [rsp+58h+var_18], rax
0x18009ff49  mov     eax, [r9]
0x18009ff4c  mov     dword ptr [rsp+58h+var_20], eax
0x18009ff50  lea     rax, aCrollbacktaskT_2; "CRollbackTask::TaskRoutine - returned f"...
0x18009ff57  mov     [rsp+58h+var_28], rax
0x18009ff5c  mov     [rsp+58h+var_30], 0
0x18009ff65  mov     [rsp+58h+var_38], r12
0x18009ff6a  mov     r9d, 5BAh
0x18009ff70  lea     r8, aComComplusDtcD_0; "com\\complus\\dtc\\dtc\\xatm\\src\\xata"...
0x18009ff77  mov     edx, 4
0x18009ff7c  lea     ecx, [rdx+7]
0x18009ff7f  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18009ff84  nop
0x18009ff85  mov     rcx, [rbx+58h]
0x18009ff89  mov     rax, [rcx]
0x18009ff8c  mov     rax, [rax+28h]
0x18009ff90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ff95  mov     rcx, [rbx+58h]
0x18009ff99  mov     rax, [rcx]
0x18009ff9c  mov     rax, [rax+18h]
0x18009ffa0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ffa5  mov     qword ptr [rbx+58h], 0
0x18009ffad  mov     rax, [rbx]
0x18009ffb0  mov     rcx, rbx
0x18009ffb3  mov     rax, [rax+10h]
0x18009ffb7  mov     rbx, [rsp+58h+arg_8]
0x18009ffbc  mov     rdi, [rsp+58h+arg_10]
0x18009ffc1  add     rsp, 50h
0x18009ffc5  pop     r12
0x18009ffc7  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
