# CCommitTask::TaskRoutine(void)

- ea: `0x18009f250`
- end: `0x18009f478`
- name: `?TaskRoutine@CCommitTask@@UEAAXXZ`
- size: `552`
- prototype: `void __fastcall(CCommitTask *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1800063b0`
- `0x18009e0e8`
- `0x18009f250`
- `0x1800a06b8`
- `0x1800bd010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009f2b9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009f2b9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009f294`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009f294`

## string_xrefs

- `0x18009f306`: `com\complus\dtc\dtc\xatm\src\xataskmgr.cpp`
- `0x18009f36f`: `com\complus\dtc\dtc\xatm\src\xataskmgr.cpp`
- `0x18009f3b8`: `com\complus\dtc\dtc\xatm\src\xataskmgr.cpp`
- `0x18009f41c`: `com\complus\dtc\dtc\xatm\src\xataskmgr.cpp`
- `0x18009f2f4`: `CCommitTask::TaskRoutine`
- `0x18009f3a6`: `CCommitTask::TaskRoutine`
- `0x18009f2df`: `CCommitTask::TaskRoutine - calling xa_commit(TMONEPHASE) - DLL=%S`
- `0x18009f34f`: `CCommitTask::TaskRoutine - returned from xa_commit(TMONEPHASE) with error=%d - DLL=%S`
- `0x18009f3fc`: `CCommitTask::TaskRoutine - returned from xa_commit with error=%d - DLL=%S`
- `0x18009f391`: `CCommitTask::TaskRoutine - calling xa_commit - DLL=%S`

## pseudocode

```c
void __fastcall CCommitTask::TaskRoutine(CCommitTask *this)
{
  unsigned int v2; // r15d
  int v3; // [rsp+20h] [rbp-38h]
  __int64 v4; // [rsp+28h] [rbp-30h]
  int v5; // [rsp+20h] [rbp-38h]
  __int64 v6; // [rsp+28h] [rbp-30h]
  __int64 v7; // [rsp+38h] [rbp-20h]
  __int64 v8; // [rsp+38h] [rbp-20h]

  v2 = XaRmId(*((_DWORD *)this + 20));
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 11) + 32LL))(*((_QWORD *)this + 11));
  **((_DWORD **)this + 15) = 0;
  EnterCriticalSection(&stru_180153898);
  if ( *((_DWORD *)CTaskManager::GetMyXaOpenState(*((_DWORD *)this + 20)) + 29) )
    **((_DWORD **)this + 15) = -3;
  LeaveCriticalSection(&stru_180153898);
  if ( !**((_DWORD **)this + 15) )
  {
    if ( *((_DWORD *)this + 28) == 1 )
    {
      try
      {
        TraceStringInline(
          11,
          4,
          L"com\\complus\\dtc\\dtc\\xatm\\src\\xataskmgr.cpp",
          1351,
          L"CCommitTask::TaskRoutine",
          0,
          L"CCommitTask::TaskRoutine - calling xa_commit(TMONEPHASE) - DLL=%S",
          *((_QWORD *)this + 8));
        **((_DWORD **)this + 15) = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64))(*((_QWORD *)this + 12) + 88LL))(
                                     *((_QWORD *)this + 13),
                                     v2,
                                     0x40000000);
        LODWORD(v7) = **((_DWORD **)this + 15);
        TraceStringInline(
          11,
          4,
          L"com\\complus\\dtc\\dtc\\xatm\\src\\xataskmgr.cpp",
          1355,
          L"CCommitTask::TaskRoutine",
          0,
          L"CCommitTask::TaskRoutine - returned from xa_commit(TMONEPHASE) with error=%d - DLL=%S",
          v7,
          *((_QWORD *)this + 8));
      }
      catch ( ... )
      {
        LODWORD(v6) = -2147430316;
        TraceStringInline(
          11,
          1,
          L"com\\complus\\dtc\\dtc\\xatm\\src\\xataskmgr.cpp",
          1360,
          L"CCommitTask::TaskRoutine",
          v6,
          L"CCommitTask::TaskRoutine - exception thrown calling xa_commit(TMONEPHASE) - DLL=%S",
          *((_QWORD *)this + 8));
        XA_TRACE_WARNING(0x8000D054, "com\\complus\\dtc\\dtc\\xatm\\src\\xataskmgr.cpp", 1361, *((char **)this + 8), v5);
        DtcXaException("xa_commit");
      }
    }
    else
    {
      try
      {
        TraceStringInline(
          11,
          4,
          L"com\\complus\\dtc\\dtc\\xatm\\src\\xataskmgr.cpp",
          1370,
          L"CCommitTask::TaskRoutine",
          0,
          L"CCommitTask::TaskRoutine - calling xa_commit - DLL=%S",
          *((_QWORD *)this + 8));
        **((_DWORD **)this + 15) = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(*((_QWORD *)this + 12) + 88LL))(
                                     *((_QWORD *)this + 13),
                                     v2,
                                     0);
        LODWORD(v8) = **((_DWORD **)this + 15);
        TraceStringInline(
          11,
          4,
          L"com\\complus\\dtc\\dtc\\xatm\\src\\xataskmgr.cpp",
          1374,
          L"CCommitTask::TaskRoutine",
          0,
          L"CCommitTask::TaskRoutine - returned from xa_commit with error=%d - DLL=%S",
          v8,
          *((_QWORD *)this + 8));
      }
      catch ( ... )
      {
        LODWORD(v4) = -2147430316;
        TraceStringInline(
          11,
          1,
          L"com\\complus\\dtc\\dtc\\xatm\\src\\xataskmgr.cpp",
          1379,
          L"CCommitTask::TaskRoutine",
          v4,
          L"CCommitTask::TaskRoutine - exception thrown calling xa_commit - DLL=%S",
          *((_QWORD *)this + 8));
        XA_TRACE_WARNING(0x8000D054, "com\\complus\\dtc\\dtc\\xatm\\src\\xataskmgr.cpp", 1380, *((char **)this + 8), v3);
        DtcXaException("xa_commit");
      }
    }
  }
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 11) + 40LL))(*((_QWORD *)this + 11));
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 11) + 24LL))(*((_QWORD *)this + 11));
  *((_QWORD *)this + 11) = 0;
  (*(void (__fastcall **)(CCommitTask *))(*(_QWORD *)this + 16LL))(this);
}

```

## disassembly

```asm
0x18009f250  mov     [rsp+arg_8], rbx
0x18009f255  mov     [rsp+arg_10], r14
0x18009f25a  mov     [rsp+arg_0], rcx
0x18009f25f  push    r15
0x18009f261  sub     rsp, 50h
0x18009f265  mov     rbx, rcx
0x18009f268  mov     ecx, [rcx+50h]; unsigned int
0x18009f26b  call    ?XaRmId@@YAKI@Z; XaRmId(uint)
0x18009f270  mov     r15d, eax
0x18009f273  mov     rcx, [rbx+58h]
0x18009f277  mov     rax, [rcx]
0x18009f27a  mov     rax, [rax+20h]
0x18009f27e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f283  mov     rax, [rbx+78h]
0x18009f287  mov     dword ptr [rax], 0
0x18009f28d  lea     rcx, stru_180153898; lpCriticalSection
0x18009f294  call    cs:__imp_EnterCriticalSection
0x18009f29a  mov     ecx, [rbx+50h]; unsigned int
0x18009f29d  call    ?GetMyXaOpenState@CTaskManager@@SAPEAVCXaOpenState@@I@Z; CTaskManager::GetMyXaOpenState(uint)
0x18009f2a2  cmp     dword ptr [rax+74h], 0
0x18009f2a6  jz      short loc_18009F2B2
0x18009f2a8  mov     rax, [rbx+78h]
0x18009f2ac  mov     dword ptr [rax], 0FFFFFFFDh
0x18009f2b2  lea     rcx, stru_180153898; lpCriticalSection
0x18009f2b9  call    cs:__imp_LeaveCriticalSection
0x18009f2bf  mov     rax, [rbx+78h]
0x18009f2c3  cmp     dword ptr [rax], 0
0x18009f2c6  jnz     loc_18009F431
0x18009f2cc  cmp     dword ptr [rbx+70h], 1
0x18009f2d0  jnz     loc_18009F388
0x18009f2d6  mov     rax, [rbx+40h]
0x18009f2da  mov     [rsp+58h+var_20], rax
0x18009f2df  lea     rax, aCcommittaskTas_3; "CCommitTask::TaskRoutine - calling xa_c"...
0x18009f2e6  mov     [rsp+58h+var_28], rax
0x18009f2eb  mov     [rsp+58h+var_30], 0
0x18009f2f4  lea     r14, aCcommittaskTas_5; "CCommitTask::TaskRoutine"
0x18009f2fb  mov     [rsp+58h+var_38], r14
0x18009f300  mov     r9d, 547h
0x18009f306  lea     r8, aComComplusDtcD_0; "com\\complus\\dtc\\dtc\\xatm\\src\\xata"...
0x18009f30d  mov     edx, 4
0x18009f312  lea     ecx, [rdx+7]
0x18009f315  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18009f31a  mov     rax, [rbx+60h]
0x18009f31e  mov     r8d, 40000000h
0x18009f324  mov     edx, r15d
0x18009f327  mov     rcx, [rbx+68h]
0x18009f32b  mov     rax, [rax+58h]
0x18009f32f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f334  mov     r9, [rbx+78h]
0x18009f338  mov     [r9], eax
0x18009f33b  mov     r9, [rbx+78h]
0x18009f33f  mov     rax, [rbx+40h]
0x18009f343  mov     [rsp+58h+var_18], rax
0x18009f348  mov     eax, [r9]
0x18009f34b  mov     dword ptr [rsp+58h+var_20], eax
0x18009f34f  lea     rax, aCcommittaskTas_1; "CCommitTask::TaskRoutine - returned fro"...
0x18009f356  mov     [rsp+58h+var_28], rax
0x18009f35b  mov     [rsp+58h+var_30], 0
0x18009f364  mov     [rsp+58h+var_38], r14
0x18009f369  mov     r9d, 54Bh
0x18009f36f  lea     r8, aComComplusDtcD_0; "com\\complus\\dtc\\dtc\\xatm\\src\\xata"...
0x18009f376  mov     edx, 4
0x18009f37b  lea     ecx, [rdx+7]
0x18009f37e  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18009f383  jmp     loc_18009F431
0x18009f388  mov     rax, [rbx+40h]
0x18009f38c  mov     [rsp+58h+var_20], rax
0x18009f391  lea     rax, aCcommittaskTas_0; "CCommitTask::TaskRoutine - calling xa_c"...
0x18009f398  mov     [rsp+58h+var_28], rax
0x18009f39d  mov     [rsp+58h+var_30], 0
0x18009f3a6  lea     r14, aCcommittaskTas_5; "CCommitTask::TaskRoutine"
0x18009f3ad  mov     [rsp+58h+var_38], r14
0x18009f3b2  mov     r9d, 55Ah
0x18009f3b8  lea     r8, aComComplusDtcD_0; "com\\complus\\dtc\\dtc\\xatm\\src\\xata"...
0x18009f3bf  mov     edx, 4
0x18009f3c4  lea     ecx, [rdx+7]
0x18009f3c7  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18009f3cc  mov     rax, [rbx+60h]
0x18009f3d0  xor     r8d, r8d
0x18009f3d3  mov     edx, r15d
0x18009f3d6  mov     rcx, [rbx+68h]
0x18009f3da  mov     rax, [rax+58h]
0x18009f3de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f3e3  mov     rcx, [rbx+78h]
0x18009f3e7  mov     [rcx], eax
0x18009f3e9  mov     rcx, [rbx+78h]
0x18009f3ed  mov     rax, [rbx+40h]
0x18009f3f1  mov     [rsp+58h+var_18], rax
0x18009f3f6  mov     eax, [rcx]
0x18009f3f8  mov     dword ptr [rsp+58h+var_20], eax
0x18009f3fc  lea     rax, aCcommittaskTas_4; "CCommitTask::TaskRoutine - returned fro"...
0x18009f403  mov     [rsp+58h+var_28], rax
0x18009f408  mov     [rsp+58h+var_30], 0
0x18009f411  mov     [rsp+58h+var_38], r14
0x18009f416  mov     r9d, 55Eh
0x18009f41c  lea     r8, aComComplusDtcD_0; "com\\complus\\dtc\\dtc\\xatm\\src\\xata"...
0x18009f423  mov     edx, 4
0x18009f428  lea     ecx, [rdx+7]
0x18009f42b  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18009f430  nop
0x18009f431  mov     rcx, [rbx+58h]
0x18009f435  mov     rax, [rcx]
0x18009f438  mov     rax, [rax+28h]
0x18009f43c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f441  mov     rcx, [rbx+58h]
0x18009f445  mov     rax, [rcx]
0x18009f448  mov     rax, [rax+18h]
0x18009f44c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f451  mov     qword ptr [rbx+58h], 0
0x18009f459  mov     rax, [rbx]
0x18009f45c  mov     rcx, rbx
0x18009f45f  mov     rax, [rax+10h]
0x18009f463  mov     rbx, [rsp+58h+arg_8]
0x18009f468  mov     r14, [rsp+58h+arg_10]
0x18009f46d  add     rsp, 50h
0x18009f471  pop     r15
0x18009f473  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
