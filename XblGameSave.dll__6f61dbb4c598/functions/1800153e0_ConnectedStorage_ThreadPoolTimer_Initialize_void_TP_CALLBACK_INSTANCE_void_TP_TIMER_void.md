# ConnectedStorage::ThreadPoolTimer::Initialize(void (*)(_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *),void *)

- ea: `0x1800153e0`
- end: `0x180015455`
- name: `?Initialize@ThreadPoolTimer@ConnectedStorage@@QEAAXP6AXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z1@Z`
- size: `117`
- prototype: `void(ConnectedStorage::ThreadPoolTimer *__hidden this, void (*)(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_TIMER *), void *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800157f0`
- `0x180015fd4`
- `0x18006c68c`

## callees

- `0x18000aae4`
- `0x1800153e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015424`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015424`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180015400`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180015400`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180015416`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180015416`

## string_xrefs

- `0x180015436`: `ThreadPoolTimer::Initialize`

## pseudocode

```c
void __fastcall ConnectedStorage::ThreadPoolTimer::Initialize(
        struct _TP_TIMER **this,
        void (*a2)(struct _TP_CALLBACK_INSTANCE *, void *, struct _TP_TIMER *),
        void *a3)
{
  struct _TP_TIMER *v5; // rcx
  PTP_TIMER ThreadpoolTimer; // rax
  signed int LastError; // eax
  const unsigned __int16 *v9; // r8

  v5 = *this;
  if ( v5 )
  {
    CloseThreadpoolTimer(v5);
    *this = 0;
  }
  ThreadpoolTimer = CreateThreadpoolTimer(a2, a3, 0);
  *this = ThreadpoolTimer;
  if ( !ThreadpoolTimer )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    ConnectedStorage::ReportErrorAndThrow(
      (ConnectedStorage *)(unsigned int)LastError,
      (int)L"ThreadPoolTimer::Initialize",
      v9);
  }
}

```

## disassembly

```asm
0x1800153e0  mov     [rsp+arg_0], rbx
0x1800153e5  mov     [rsp+arg_8], rsi
0x1800153ea  push    rdi
0x1800153eb  sub     rsp, 20h
0x1800153ef  mov     rbx, rcx
0x1800153f2  mov     rdi, r8
0x1800153f5  mov     rcx, [rcx]; pti
0x1800153f8  mov     rsi, rdx
0x1800153fb  test    rcx, rcx
0x1800153fe  jz      short loc_18001540D
0x180015400  call    cs:__imp_CloseThreadpoolTimer
0x180015406  mov     qword ptr [rbx], 0
0x18001540d  xor     r8d, r8d; pcbe
0x180015410  mov     rdx, rdi; pv
0x180015413  mov     rcx, rsi; pfnti
0x180015416  call    cs:__imp_CreateThreadpoolTimer
0x18001541c  mov     [rbx], rax
0x18001541f  test    rax, rax
0x180015422  jnz     short loc_180015445
0x180015424  call    cs:__imp_GetLastError
0x18001542a  test    eax, eax
0x18001542c  jle     short loc_180015436
0x18001542e  movzx   eax, ax
0x180015431  or      eax, 80070000h
0x180015436  lea     rdx, aThreadpooltime; "ThreadPoolTimer::Initialize"
0x18001543d  mov     ecx, eax; this
0x18001543f  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x180015445  mov     rbx, [rsp+28h+arg_0]
0x18001544a  mov     rsi, [rsp+28h+arg_8]
0x18001544f  add     rsp, 20h
0x180015453  pop     rdi
0x180015454  retn
```
