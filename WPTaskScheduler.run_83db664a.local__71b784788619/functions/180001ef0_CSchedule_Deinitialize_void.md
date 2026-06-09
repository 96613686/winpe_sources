# CSchedule::Deinitialize(void)

- ea: `0x180001ef0`
- end: `0x180001ffd`
- name: `?Deinitialize@CSchedule@@QEAAXXZ`
- size: `269`
- prototype: `void __fastcall(CSchedule *__hidden this)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180001ea0`
- `0x180002d90`
- `0x180005d40`

## callees

- `0x180001ef0`
- `0x18000dc54`
- `0x180018560`
- `0x180022010`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180001f8b`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180001f8b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180001fc5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180001fc5`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180001fd7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180001fd7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180001fe4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180001fe4`

## pseudocode

```c
void __fastcall CSchedule::Deinitialize(CSchedule *this, unsigned int a2)
{
  int v2; // r9d
  struct _TP_TIMER *v4; // rcx
  void (__fastcall ***v5)(_QWORD, __int64); // rcx
  __int64 v6; // rcx
  SecurityContext *v7; // rcx
  void *v8; // rcx

  v2 = *((_DWORD *)this + 10);
  if ( v2 != 6 )
  {
    if ( byte_180030D06 < 0 )
      McTemplateU0jqq_EventWriteTransfer((_DWORD)this, (unsigned int)ScheduleStateChange, (_DWORD)this + 16, v2, 6);
    *((_DWORD *)this + 10) = 6;
  }
  v4 = (struct _TP_TIMER *)*((_QWORD *)this + 37);
  if ( v4 )
  {
    SetThreadpoolTimer(v4, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(*((PTP_TIMER *)this + 37), 1);
    CloseThreadpoolTimer(*((PTP_TIMER *)this + 37));
    *((_QWORD *)this + 37) = 0;
  }
  v5 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 25);
  if ( v5 )
    (**v5)(v5, 1);
  v6 = *((_QWORD *)this + 27);
  *((_QWORD *)this + 25) = 0;
  if ( v6 )
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v6 + 64LL))(v6, 1);
  v7 = (SecurityContext *)*((_QWORD *)this + 34);
  *((_QWORD *)this + 27) = 0;
  if ( v7 )
    SecurityContext::`scalar deleting destructor'(v7, a2);
  v8 = (void *)*((_QWORD *)this + 4);
  *((_QWORD *)this + 34) = 0;
  operator delete[](v8);
  *((_QWORD *)this + 4) = 0;
}

```

## disassembly

```asm
0x180001ef0  mov     [rsp+arg_0], rbx
0x180001ef5  push    rdi
0x180001ef6  sub     rsp, 30h
0x180001efa  mov     r9d, [rcx+28h]
0x180001efe  mov     rbx, rcx
0x180001f01  cmp     r9d, 6
0x180001f05  jz      short loc_180001F1B
0x180001f07  cmp     cs:byte_180030D06, 0
0x180001f0e  jl      loc_180001FA0
0x180001f14  mov     dword ptr [rbx+28h], 6
0x180001f1b  mov     rcx, [rbx+128h]; pti
0x180001f22  xor     edi, edi
0x180001f24  test    rcx, rcx
0x180001f27  jnz     loc_180001FBD
0x180001f2d  mov     rcx, [rbx+0C8h]
0x180001f34  test    rcx, rcx
0x180001f37  jz      short loc_180001F49
0x180001f39  mov     rax, [rcx]
0x180001f3c  mov     edx, 1
0x180001f41  mov     rax, [rax]
0x180001f44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f49  mov     rcx, [rbx+0D8h]
0x180001f50  mov     [rbx+0C8h], rdi
0x180001f57  test    rcx, rcx
0x180001f5a  jz      short loc_180001F6D
0x180001f5c  mov     rax, [rcx]
0x180001f5f  mov     edx, 1
0x180001f64  mov     rax, [rax+40h]
0x180001f68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f6d  mov     rcx, [rbx+110h]; this
0x180001f74  mov     [rbx+0D8h], rdi
0x180001f7b  test    rcx, rcx
0x180001f7e  jnz     short loc_180001FF6
0x180001f80  mov     rcx, [rbx+20h]
0x180001f84  mov     [rbx+110h], rdi
0x180001f8b  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180001f91  mov     [rbx+20h], rdi
0x180001f95  mov     rbx, [rsp+38h+arg_0]
0x180001f9a  add     rsp, 30h
0x180001f9e  pop     rdi
0x180001f9f  retn
0x180001fa0  lea     r8, [rcx+10h]
0x180001fa4  mov     [rsp+38h+var_18], 6
0x180001fac  lea     rdx, ScheduleStateChange
0x180001fb3  call    McTemplateU0jqq_EventWriteTransfer
0x180001fb8  jmp     loc_180001F14
0x180001fbd  xor     r9d, r9d; msWindowLength
0x180001fc0  xor     r8d, r8d; msPeriod
0x180001fc3  xor     edx, edx; pftDueTime
0x180001fc5  call    cs:__imp_SetThreadpoolTimer
0x180001fcb  mov     rcx, [rbx+128h]; pti
0x180001fd2  mov     edx, 1; fCancelPendingCallbacks
0x180001fd7  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180001fdd  mov     rcx, [rbx+128h]; pti
0x180001fe4  call    cs:__imp_CloseThreadpoolTimer
0x180001fea  mov     [rbx+128h], rdi
0x180001ff1  jmp     loc_180001F2D
0x180001ff6  call    ??_GSecurityContext@@QEAAPEAXI@Z; SecurityContext::`scalar deleting destructor'(uint)
0x180001ffb  jmp     short loc_180001F80
```
