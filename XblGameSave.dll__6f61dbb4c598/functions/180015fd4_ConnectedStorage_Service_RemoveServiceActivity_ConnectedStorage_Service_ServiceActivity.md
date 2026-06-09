# ConnectedStorage::Service::RemoveServiceActivity(ConnectedStorage::Service::ServiceActivity)

- ea: `0x180015fd4`
- end: `0x180016080`
- name: `?RemoveServiceActivity@Service@ConnectedStorage@@AEAAXW4ServiceActivity@12@@Z`
- size: `172`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x1800160c8`
- `0x180016d84`
- `0x1800195e0`

## callees

- `0x18000aae4`
- `0x18000cb9c`
- `0x180014e64`
- `0x1800153e0`
- `0x180015fd4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180016079`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180016063`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180016063`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ConnectedStorage::Service::RemoveServiceActivity(__int64 a1, int a2, char *a3)
{
  int v5; // eax
  int v6; // ebx
  const unsigned __int16 *v7; // r8
  struct _TP_TIMER *v8; // rcx
  LPCRITICAL_SECTION v9[3]; // [rsp+20h] [rbp-18h] BYREF
  struct _FILETIME pftDueTime; // [rsp+40h] [rbp+8h] BYREF

  ConnectedStorage::Mutex::Lock::Lock((ConnectedStorage::Mutex::Lock *)v9, (struct _RTL_CRITICAL_SECTION *)a1, a3);
  v5 = *(_DWORD *)(a1 + 384);
  v6 = v5 & ~a2;
  *(_DWORD *)(a1 + 384) = v6;
  if ( !v6 && v5 != 1 )
  {
    *(_DWORD *)(a1 + 384) = 1;
    pftDueTime = 0;
    ConnectedStorage::Service::GetServiceShutdownTime(&pftDueTime);
    ConnectedStorage::ThreadPoolTimer::Initialize(
      (struct _TP_TIMER **)(a1 + 376),
      (void (*)(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_TIMER *))ConnectedStorage::Service::ServiceShutdownTimerCallback,
      0);
    v8 = *(struct _TP_TIMER **)(a1 + 376);
    if ( !v8 )
      ConnectedStorage::ReportErrorAndThrow((ConnectedStorage *)0x8000FFFFLL, (int)L"Not initializated", v7);
    SetThreadpoolTimer(v8, &pftDueTime, 0, 0);
  }
  LeaveCriticalSection(v9[0]);
}

```

## disassembly

```asm
0x180015fd4  mov     [rsp+arg_8], rbx
0x180015fd9  push    rdi
0x180015fda  sub     rsp, 30h
0x180015fde  mov     ebx, edx
0x180015fe0  mov     rdi, rcx
0x180015fe3  mov     rdx, rcx; struct ConnectedStorage::Mutex *
0x180015fe6  lea     rcx, [rsp+38h+var_18]; this
0x180015feb  call    ??0Lock@Mutex@ConnectedStorage@@QEAA@AEAV12@PEAD@Z; ConnectedStorage::Mutex::Lock::Lock(ConnectedStorage::Mutex &,char *)
0x180015ff0  nop
0x180015ff1  mov     eax, [rdi+180h]
0x180015ff7  not     ebx
0x180015ff9  and     ebx, eax
0x180015ffb  mov     [rdi+180h], ebx
0x180016001  jnz     short loc_18001606A
0x180016003  cmp     eax, 1
0x180016006  jz      short loc_18001606A
0x180016008  mov     dword ptr [rdi+180h], 1
0x180016012  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], 0
0x18001601b  lea     rcx, [rsp+38h+pftDueTime]; struct _FILETIME *
0x180016020  call    ?GetServiceShutdownTime@Service@ConnectedStorage@@CAXPEAU_FILETIME@@@Z; ConnectedStorage::Service::GetServiceShutdownTime(_FILETIME *)
0x180016025  lea     rbx, [rdi+178h]
0x18001602c  xor     r8d, r8d; void *
0x18001602f  lea     rdx, ?ServiceShutdownTimerCallback@Service@ConnectedStorage@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; void (*)(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_TIMER *)
0x180016036  mov     rcx, rbx; this
0x180016039  call    ?Initialize@ThreadPoolTimer@ConnectedStorage@@QEAAXP6AXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z1@Z; ConnectedStorage::ThreadPoolTimer::Initialize(void (*)(_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *),void *)
0x18001603e  mov     rcx, [rbx]; pti
0x180016041  test    rcx, rcx
0x180016044  jnz     short loc_180016058
0x180016046  lea     rdx, aNotInitializat; "Not initializated"
0x18001604d  mov     ecx, 8000FFFFh; this
0x180016052  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x180016058  xor     r9d, r9d; msWindowLength
0x18001605b  xor     r8d, r8d; msPeriod
0x18001605e  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x180016063  call    cs:__imp_SetThreadpoolTimer
0x180016069  nop
0x18001606a  mov     rcx, [rsp+38h+var_18]
0x18001606f  mov     rbx, [rsp+38h+arg_8]
0x180016074  add     rsp, 30h
0x180016078  pop     rdi
0x180016079  jmp     cs:__imp_LeaveCriticalSection
```
