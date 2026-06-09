# Notifier::NotifyThread::NotifyLoop(void)

- ea: `0x18001023c`
- end: `0x18001040a`
- name: `?NotifyLoop@NotifyThread@Notifier@@AEAAXXZ`
- size: `462`
- prototype: `void __fastcall(struct IEventObjectChange **this)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x180035590`

## callees

- `0x180003d54`
- `0x180009034`
- `0x18001023c`
- `0x180010410`
- `0x1800104e4`
- `0x180010510`
- `0x1800281e8`
- `0x18003ecb0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001025e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001025e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180010272`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180010272`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800103ab`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800103ab`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800102f0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010336`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800103c3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800102f0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010336`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800103c3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010388`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010388`

## string_xrefs

- `0x180010296`: `com\complus\src\events\tier2\notify.cpp`
- `0x1800103dc`: `com\complus\src\events\Shared\UTSem.h`

## pseudocode

```c
void __fastcall Notifier::NotifyThread::NotifyLoop(struct IEventObjectChange **this)
{
  int v2; // ebx
  DWORD v3; // r14d
  struct Notifier::NotifyThread::NotifyArgs *v4; // rsi
  struct Notifier::NotifyThread::NotifyArgs *v5; // r15
  HANDLE *v6; // [rsp+88h] [rbp+20h]

  v6 = (HANDLE *)(this + 7);
  SetEvent(this[7]);
  v2 = 0;
  while ( 1 )
  {
    do
    {
      v3 = WaitForSingleObjectEx(this[15], 0x1D4C0u, 0);
      if ( v3 == -1 )
        InternalError_Win32(L"com\\complus\\src\\events\\tier2\\notify.cpp", 0x243u, 0x14u, L"WaitForSingleObjectEx");
      if ( !v3 )
      {
        v4 = 0;
        CSemExclusiveES::Lock((CSemExclusiveES *)(this + 9));
        if ( this[16] )
        {
          v4 = (struct Notifier::NotifyThread::NotifyArgs *)this[16];
          this[16] = 0;
          this[17] = 0;
        }
        LeaveCriticalSection((LPCRITICAL_SECTION)(this + 9));
        while ( v4 )
        {
          v5 = *(struct Notifier::NotifyThread::NotifyArgs **)v4;
          *(_QWORD *)v4 = 0;
          Notifier::NotifyThread::ProcessNotifyArgs(this, v4);
          Notifier::NotifyThread::NotifyArgs::~NotifyArgs(v4);
          CoTaskMemFree(v4);
          v4 = v5;
        }
      }
    }
    while ( v3 != 258 && !*((_DWORD *)this + 50) );
    if ( this == (struct IEventObjectChange **)-144LL )
      InternalError(L"com\\complus\\src\\events\\Shared\\UTSem.h", 0x154u, 0x80001203, 0x10u);
    CSemExclusiveES::Lock((CSemExclusiveES *)(this + 18));
    if ( *((_DWORD *)this + 50) )
      break;
    LeaveCriticalSection((LPCRITICAL_SECTION)(this + 18));
  }
  Notifier::NotifyThread::ReleaseEventClasses((Notifier::NotifyThread *)this);
  ResetEvent(*v6);
  LOBYTE(v2) = *((_DWORD *)this + 50) == 0;
  *((_DWORD *)this + 48) = v2;
  LeaveCriticalSection((LPCRITICAL_SECTION)(this + 18));
}

```

## disassembly

```asm
0x18001023c  mov     [rsp+arg_0], rcx
0x180010241  push    rbx
0x180010242  push    rsi
0x180010243  push    rdi
0x180010244  push    r14
0x180010246  push    r15
0x180010248  sub     rsp, 40h
0x18001024c  mov     rdi, rcx
0x18001024f  add     rcx, 38h ; '8'
0x180010253  mov     [rsp+68h+arg_18], rcx
0x18001025b  mov     rcx, [rcx]; hEvent
0x18001025e  call    cs:__imp_SetEvent
0x180010264  xor     ebx, ebx
0x180010266  xor     r8d, r8d; bAlertable
0x180010269  mov     edx, 1D4C0h; dwMilliseconds
0x18001026e  mov     rcx, [rdi+78h]; hHandle
0x180010272  call    cs:__imp_WaitForSingleObjectEx
0x180010278  mov     r14d, eax
0x18001027b  mov     [rsp+68h+arg_8], eax
0x18001027f  cmp     eax, 0FFFFFFFFh
0x180010282  jnz     short loc_1800102A2
0x180010284  mov     r8d, 14h; unsigned __int16
0x18001028a  lea     r9, aWaitforsingleo_0; "WaitForSingleObjectEx"
0x180010291  mov     edx, 243h; unsigned int
0x180010296  lea     rcx, aComComplusSrcE_7; "com\\complus\\src\\events\\tier2\\notif"...
0x18001029d  call    ?InternalError_Win32@@YA_NPEBGKG0@Z; InternalError_Win32(ushort const *,ulong,ushort,ushort const *)
0x1800102a2  test    r14d, r14d
0x1800102a5  jz      short loc_1800102FF
0x1800102a7  cmp     r14d, 102h
0x1800102ae  jz      short loc_1800102BC
0x1800102b0  cmp     [rdi+0C8h], ebx
0x1800102b6  jz      loc_1800103ED
0x1800102bc  mov     [rsp+68h+var_38], 1
0x1800102c4  lea     rsi, [rdi+90h]
0x1800102cb  mov     [rsp+68h+var_30], rsi
0x1800102d0  test    rsi, rsi
0x1800102d3  jz      loc_1800103CB
0x1800102d9  mov     rcx, rsi; this
0x1800102dc  call    ?Lock@CSemExclusiveES@@QEAAXXZ; CSemExclusiveES::Lock(void)
0x1800102e1  cmp     [rdi+0C8h], ebx
0x1800102e7  jnz     loc_180010398
0x1800102ed  mov     rcx, rsi; lpCriticalSection
0x1800102f0  call    cs:__imp_LeaveCriticalSection
0x1800102f6  mov     [rsp+68h+var_38], ebx
0x1800102fa  jmp     loc_1800103ED
0x1800102ff  mov     rsi, rbx
0x180010302  mov     [rsp+68h+var_40], rbx
0x180010307  lea     rcx, [rdi+48h]; this
0x18001030b  call    ?Lock@CSemExclusiveES@@QEAAXXZ; CSemExclusiveES::Lock(void)
0x180010310  mov     rax, [rdi+80h]
0x180010317  test    rax, rax
0x18001031a  jz      short loc_180010332
0x18001031c  mov     rsi, rax
0x18001031f  mov     [rsp+68h+var_40], rax
0x180010324  mov     [rdi+80h], rbx
0x18001032b  mov     [rdi+88h], rbx
0x180010332  lea     rcx, [rdi+48h]; lpCriticalSection
0x180010336  call    cs:__imp_LeaveCriticalSection
0x18001033c  test    rsi, rsi
0x18001033f  jz      loc_1800102A7
0x180010345  mov     [rsp+68h+var_48], ebx
0x180010349  mov     r15, [rsi]
0x18001034c  mov     [rsp+68h+arg_10], r15
0x180010354  mov     [rsi], rbx
0x180010357  mov     rdx, rsi; struct Notifier::NotifyThread::NotifyArgs *
0x18001035a  mov     rcx, rdi; this
0x18001035d  call    ?ProcessNotifyArgs@NotifyThread@Notifier@@AEAAJPEAUNotifyArgs@12@@Z; Notifier::NotifyThread::ProcessNotifyArgs(Notifier::NotifyThread::NotifyArgs *)
0x180010362  jmp     short loc_18001037D
0x180010364  xor     ebx, ebx
0x180010366  mov     rdi, [rsp+68h+arg_0]
0x18001036b  mov     r14d, [rsp+68h+arg_8]
0x180010370  mov     rsi, [rsp+68h+var_40]
0x180010375  mov     r15, [rsp+68h+arg_10]
0x18001037d  mov     rcx, rsi; this
0x180010380  call    ??1NotifyArgs@NotifyThread@Notifier@@QEAA@XZ; Notifier::NotifyThread::NotifyArgs::~NotifyArgs(void)
0x180010385  mov     rcx, rsi; pv
0x180010388  call    cs:__imp_CoTaskMemFree
0x18001038e  mov     rsi, r15
0x180010391  mov     [rsp+68h+var_40], r15
0x180010396  jmp     short loc_18001033C
0x180010398  mov     rcx, rdi; this
0x18001039b  call    ?ReleaseEventClasses@NotifyThread@Notifier@@AEAAXXZ; Notifier::NotifyThread::ReleaseEventClasses(void)
0x1800103a0  mov     rcx, [rsp+68h+arg_18]
0x1800103a8  mov     rcx, [rcx]; hEvent
0x1800103ab  call    cs:__imp_ResetEvent
0x1800103b1  cmp     [rdi+0C8h], ebx
0x1800103b7  setz    bl
0x1800103ba  mov     [rdi+0C0h], ebx
0x1800103c0  mov     rcx, rsi; lpCriticalSection
0x1800103c3  call    cs:__imp_LeaveCriticalSection
0x1800103c9  jmp     short loc_1800103FE
0x1800103cb  mov     edx, 154h; unsigned int
0x1800103d0  mov     r9d, 10h; unsigned __int16
0x1800103d6  mov     r8d, 80001203h; unsigned int
0x1800103dc  lea     rcx, aComComplusSrcE_4; "com\\complus\\src\\events\\Shared\\UTSe"...
0x1800103e3  call    ?InternalError@@YA_NPEBGKKG@Z; InternalError(ushort const *,ulong,ulong,ushort)
0x1800103e8  jmp     loc_1800102D9
0x1800103ed  jmp     loc_180010266
0x1800103f2  xor     ebx, ebx
0x1800103f4  mov     rdi, [rsp+68h+arg_0]
0x1800103f9  jmp     loc_180010266
0x1800103fe  add     rsp, 40h
0x180010402  pop     r15
0x180010404  pop     r14
0x180010406  pop     rdi
0x180010407  pop     rsi
0x180010408  pop     rbx
0x180010409  retn
0x180043e4e  push    rbp
0x180043e50  sub     rsp, 20h
0x180043e54  mov     rbp, rdx
0x180043e57  lea     rdx, [rbp+20h]; int *
0x180043e5b  call    ?ExceptionFilter@@YAKPEAU_EXCEPTION_POINTERS@@AEAJ@Z; ExceptionFilter(_EXCEPTION_POINTERS *,long &)
0x180043e60  nop
0x180043e61  add     rsp, 20h
0x180043e65  pop     rbp
0x180043e66  retn
0x180043e68  push    rbp
0x180043e6a  sub     rsp, 20h
0x180043e6e  mov     rbp, rdx
0x180043e71  lea     rdx, [rbp+24h]; int *
0x180043e75  call    ?ExceptionFilter@@YAKPEAU_EXCEPTION_POINTERS@@AEAJ@Z; ExceptionFilter(_EXCEPTION_POINTERS *,long &)
0x180043e7a  nop
0x180043e7b  add     rsp, 20h
0x180043e7f  pop     rbp
0x180043e80  retn
```
