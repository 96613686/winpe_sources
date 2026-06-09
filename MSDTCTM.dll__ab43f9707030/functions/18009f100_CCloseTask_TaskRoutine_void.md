# CCloseTask::TaskRoutine(void)

- ea: `0x18009f100`
- end: `0x18009f24a`
- name: `?TaskRoutine@CCloseTask@@UEAAXXZ`
- size: `330`
- prototype: `void __fastcall(CCloseTask *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1800063b0`
- `0x18009e0e8`
- `0x18009f100`
- `0x1800bd010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009f151`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009f151`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009f133`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009f133`

## string_xrefs

- `0x18009f18c`: `com\complus\dtc\dtc\xatm\src\xataskmgr.cpp`
- `0x18009f1f3`: `com\complus\dtc\dtc\xatm\src\xataskmgr.cpp`
- `0x18009f17a`: `CCloseTask::TaskRoutine`
- `0x18009f165`: `CCloseTask::TaskRoutine - calling xa_close - DLL=%S`
- `0x18009f1d3`: `CCloseTask::TaskRoutine - returned from xa_close with error=%d - DLL=%S`

## pseudocode

```c
void __fastcall CCloseTask::TaskRoutine(CCloseTask *this)
{
  int v2; // [rsp+20h] [rbp-38h]
  __int64 v3; // [rsp+28h] [rbp-30h]
  __int64 v4; // [rsp+38h] [rbp-20h]

  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 11) + 32LL))(*((_QWORD *)this + 11));
  if ( CTaskManager::m_bDoTaskClock )
  {
    EnterCriticalSection(&stru_180153898);
    **((_DWORD **)this + 14) = *((_DWORD *)CTaskManager::GetMyXaOpenState(*((_DWORD *)this + 20)) + 30);
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
        1165,
        L"CCloseTask::TaskRoutine",
        0,
        L"CCloseTask::TaskRoutine - calling xa_close - DLL=%S",
        *((_QWORD *)this + 8));
      **((_DWORD **)this + 14) = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(*((_QWORD *)this + 12) + 48LL))(
                                   *((_QWORD *)this + 13),
                                   *((unsigned __int16 *)this + 40),
                                   0);
      LODWORD(v4) = **((_DWORD **)this + 14);
      TraceStringInline(
        11,
        4,
        L"com\\complus\\dtc\\dtc\\xatm\\src\\xataskmgr.cpp",
        1169,
        L"CCloseTask::TaskRoutine",
        0,
        L"CCloseTask::TaskRoutine - returned from xa_close with error=%d - DLL=%S",
        v4,
        *((_QWORD *)this + 8));
    }
    catch ( ... )
    {
      LODWORD(v3) = -2147430318;
      TraceStringInline(
        11,
        1,
        L"com\\complus\\dtc\\dtc\\xatm\\src\\xataskmgr.cpp",
        1174,
        L"CCloseTask::TaskRoutine",
        v3,
        L"CCloseTask::TaskRoutine - exception thrown calling xa_close - DLL=%S",
        *((_QWORD *)this + 8));
      XA_TRACE_WARNING(0x8000D052, "com\\complus\\dtc\\dtc\\xatm\\src\\xataskmgr.cpp", 1175, *((char **)this + 8), v2);
      DtcXaException("xa_close");
    }
  }
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 11) + 40LL))(*((_QWORD *)this + 11));
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 11) + 24LL))(*((_QWORD *)this + 11));
  *((_QWORD *)this + 11) = 0;
  (*(void (__fastcall **)(CCloseTask *))(*(_QWORD *)this + 16LL))(this);
}

```

## disassembly

```asm
0x18009f100  mov     [rsp+arg_8], rbx
0x18009f105  mov     [rsp+arg_0], rcx
0x18009f10a  push    r15
0x18009f10c  sub     rsp, 50h
0x18009f110  mov     rbx, rcx
0x18009f113  mov     rcx, [rcx+58h]
0x18009f117  mov     rax, [rcx]
0x18009f11a  mov     rax, [rax+20h]
0x18009f11e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f123  cmp     cs:?m_bDoTaskClock@CTaskManager@@0HA, 0; int CTaskManager::m_bDoTaskClock
0x18009f12a  jz      short loc_18009F15C
0x18009f12c  lea     rcx, stru_180153898; lpCriticalSection
0x18009f133  call    cs:__imp_EnterCriticalSection
0x18009f139  mov     ecx, [rbx+50h]; unsigned int
0x18009f13c  call    ?GetMyXaOpenState@CTaskManager@@SAPEAVCXaOpenState@@I@Z; CTaskManager::GetMyXaOpenState(uint)
0x18009f141  mov     rdx, [rbx+70h]
0x18009f145  mov     eax, [rax+78h]
0x18009f148  mov     [rdx], eax
0x18009f14a  lea     rcx, stru_180153898; lpCriticalSection
0x18009f151  call    cs:__imp_LeaveCriticalSection
0x18009f157  jmp     loc_18009F208
0x18009f15c  mov     rax, [rbx+40h]
0x18009f160  mov     [rsp+58h+var_20], rax
0x18009f165  lea     rax, aCclosetaskTask; "CCloseTask::TaskRoutine - calling xa_cl"...
0x18009f16c  mov     [rsp+58h+var_28], rax
0x18009f171  mov     [rsp+58h+var_30], 0
0x18009f17a  lea     r15, aCclosetaskTask_0; "CCloseTask::TaskRoutine"
0x18009f181  mov     [rsp+58h+var_38], r15
0x18009f186  mov     r9d, 48Dh
0x18009f18c  lea     r8, aComComplusDtcD_0; "com\\complus\\dtc\\dtc\\xatm\\src\\xata"...
0x18009f193  mov     edx, 4
0x18009f198  lea     ecx, [rdx+7]
0x18009f19b  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18009f1a0  mov     rax, [rbx+60h]
0x18009f1a4  movzx   edx, word ptr [rbx+50h]
0x18009f1a8  xor     r8d, r8d
0x18009f1ab  mov     rcx, [rbx+68h]
0x18009f1af  mov     rax, [rax+30h]
0x18009f1b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f1b8  mov     r9, [rbx+70h]
0x18009f1bc  mov     [r9], eax
0x18009f1bf  mov     r9, [rbx+70h]
0x18009f1c3  mov     rax, [rbx+40h]
0x18009f1c7  mov     [rsp+58h+var_18], rax
0x18009f1cc  mov     eax, [r9]
0x18009f1cf  mov     dword ptr [rsp+58h+var_20], eax
0x18009f1d3  lea     rax, aCclosetaskTask_2; "CCloseTask::TaskRoutine - returned from"...
0x18009f1da  mov     [rsp+58h+var_28], rax
0x18009f1df  mov     [rsp+58h+var_30], 0
0x18009f1e8  mov     [rsp+58h+var_38], r15
0x18009f1ed  mov     r9d, 491h
0x18009f1f3  lea     r8, aComComplusDtcD_0; "com\\complus\\dtc\\dtc\\xatm\\src\\xata"...
0x18009f1fa  mov     edx, 4
0x18009f1ff  lea     ecx, [rdx+7]
0x18009f202  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18009f207  nop
0x18009f208  mov     rcx, [rbx+58h]
0x18009f20c  mov     rax, [rcx]
0x18009f20f  mov     rax, [rax+28h]
0x18009f213  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f218  mov     rcx, [rbx+58h]
0x18009f21c  mov     rax, [rcx]
0x18009f21f  mov     rax, [rax+18h]
0x18009f223  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f228  mov     qword ptr [rbx+58h], 0
0x18009f230  mov     rax, [rbx]
0x18009f233  mov     rcx, rbx
0x18009f236  mov     rax, [rax+10h]
0x18009f23a  mov     rbx, [rsp+58h+arg_8]
0x18009f23f  add     rsp, 50h
0x18009f243  pop     r15
0x18009f245  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
