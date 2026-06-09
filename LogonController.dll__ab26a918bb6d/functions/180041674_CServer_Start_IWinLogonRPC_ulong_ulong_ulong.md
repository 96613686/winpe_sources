# CServer::Start(IWinLogonRPC *,ulong,ulong,ulong)

- ea: `0x180041674`
- end: `0x180041826`
- name: `?Start@CServer@@QEAAJPEAUIWinLogonRPC@@KKK@Z`
- size: `434`
- prototype: `__int64 __fastcall(CServer *__hidden this, struct IWinLogonRPC *, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18001fec0`

## callees

- `0x18000cd1c`
- `0x18000df10`
- `0x180041674`
- `0x18004182c`
- `0x18008ee28`
- `0x18009d010`

## import_xrefs

- `KERNEL32!CreateThread` at `0x180041741`
- `KERNEL32!CreateThread` at `0x180041741`
- `KERNEL32!CloseThreadpoolTimer` at `0x1800417b5`
- `KERNEL32!CloseThreadpoolTimer` at `0x1800417b5`
- `KERNEL32!CreateThreadpoolTimer` at `0x180041798`
- `KERNEL32!CreateThreadpoolTimer` at `0x180041798`
- `KERNEL32!SetThreadpoolTimer` at `0x1800417e6`
- `KERNEL32!SetThreadpoolTimer` at `0x1800417e6`
- `KERNEL32!SetLastError` at `0x1800417bd`
- `KERNEL32!SetLastError` at `0x1800417bd`
- `KERNEL32!GetLastError` at `0x1800417aa`
- `KERNEL32!GetLastError` at `0x1800417aa`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CServer::Start(
        CServer *this,
        struct IWinLogonRPC *a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5)
{
  __int64 v7; // rcx
  __int64 v8; // rcx
  signed int LastErrorError; // ebx
  HANDLE Thread; // rax
  struct _TP_TIMER *ThreadpoolTimer; // rbp
  struct _TP_TIMER *v12; // r14
  DWORD LastError; // ebx
  CServer *v15; // [rsp+50h] [rbp+8h] BYREF
  struct _FILETIME pftDueTime; // [rsp+58h] [rbp+10h] BYREF

  CServer::s_dwTestClientProcessId = a3;
  CServer::s_dwWnfState0 = a4;
  CServer::s_dwWnfState1 = a5;
  if ( *((struct IWinLogonRPC **)this + 10) != a2 )
  {
    if ( a2 )
      (*(void (__fastcall **)(struct IWinLogonRPC *))(*(_QWORD *)a2 + 8LL))(a2);
    v7 = *((_QWORD *)this + 10);
    *((_QWORD *)this + 10) = a2;
    if ( v7 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  }
  v15 = this;
  Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v15);
  v8 = CServer::s_wpSingleton;
  CServer::s_wpSingleton = 0;
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  LastErrorError = Microsoft::WRL::AsWeak<CServer>(this, &CServer::s_wpSingleton);
  if ( LastErrorError >= 0 )
  {
    Thread = CreateThread(0, 0, CServerStart_ThreadProc, 0, 0, 0);
    *((_QWORD *)this + 11) = Thread;
    if ( Thread
      || ((int)GetLastErrorError() > 0
        ? (LastErrorError = (unsigned __int16)GetLastErrorError() | 0x80070000)
        : (LastErrorError = GetLastErrorError()),
          LastErrorError >= 0) )
    {
      if ( a2 )
        (*(void (__fastcall **)(struct IWinLogonRPC *))(*(_QWORD *)a2 + 8LL))(a2);
      ThreadpoolTimer = CreateThreadpoolTimer(lambda_e49372d879d822098adbb9512c539288_::_lambda_invoker_cdecl_, 0, 0);
      v12 = (struct _TP_TIMER *)*((_QWORD *)this + 9);
      if ( v12 )
      {
        LastError = GetLastError();
        CloseThreadpoolTimer(v12);
        SetLastError(LastError);
      }
      *((_QWORD *)this + 9) = ThreadpoolTimer;
      if ( ThreadpoolTimer )
      {
        LastErrorError = 0;
        pftDueTime = (struct _FILETIME)-20000000LL;
        SetThreadpoolTimer(ThreadpoolTimer, &pftDueTime, 0, 0);
      }
      else
      {
        LastErrorError = -2147024882;
      }
      if ( a2 )
        (*(void (__fastcall **)(struct IWinLogonRPC *))(*(_QWORD *)a2 + 16LL))(a2);
    }
  }
  Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(&v15);
  return (unsigned int)LastErrorError;
}

```

## disassembly

```asm
0x180041674  mov     [rsp+arg_10], rbx
0x180041679  mov     [rsp+arg_18], rbp
0x18004167e  push    rsi
0x18004167f  push    rdi
0x180041680  push    r14
0x180041682  sub     rsp, 30h
0x180041686  mov     rdi, rdx
0x180041689  mov     rsi, rcx
0x18004168c  mov     cs:?s_dwTestClientProcessId@CServer@@0KA, r8d; ulong CServer::s_dwTestClientProcessId
0x180041693  mov     cs:?s_dwWnfState0@CServer@@0KA, r9d; ulong CServer::s_dwWnfState0
0x18004169a  mov     eax, [rsp+48h+arg_20]
0x18004169e  mov     cs:?s_dwWnfState1@CServer@@0KA, eax; ulong CServer::s_dwWnfState1
0x1800416a4  cmp     [rcx+50h], rdx
0x1800416a8  jz      short loc_1800416D7
0x1800416aa  test    rdx, rdx
0x1800416ad  jz      short loc_1800416BE
0x1800416af  mov     rax, [rdx]
0x1800416b2  mov     rcx, rdx
0x1800416b5  mov     rax, [rax+8]
0x1800416b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800416be  mov     rcx, [rsi+50h]
0x1800416c2  mov     [rsi+50h], rdi
0x1800416c6  test    rcx, rcx
0x1800416c9  jz      short loc_1800416D7
0x1800416cb  mov     rax, [rcx]
0x1800416ce  mov     rax, [rax+10h]
0x1800416d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800416d7  mov     [rsp+48h+arg_0], rsi
0x1800416dc  lea     rcx, [rsp+48h+arg_0]
0x1800416e1  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x1800416e6  mov     rcx, cs:?s_wpSingleton@CServer@@0VWeakRef@WRL@Microsoft@@A; Microsoft::WRL::WeakRef CServer::s_wpSingleton
0x1800416ed  mov     cs:?s_wpSingleton@CServer@@0VWeakRef@WRL@Microsoft@@A, 0; Microsoft::WRL::WeakRef CServer::s_wpSingleton
0x1800416f8  test    rcx, rcx
0x1800416fb  jz      short loc_180041709
0x1800416fd  mov     rax, [rcx]
0x180041700  mov     rax, [rax+10h]
0x180041704  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041709  lea     rdx, ?s_wpSingleton@CServer@@0VWeakRef@WRL@Microsoft@@A; Microsoft::WRL::WeakRef CServer::s_wpSingleton
0x180041710  mov     rcx, rsi
0x180041713  call    ??$AsWeak@VCServer@@@WRL@Microsoft@@YAJPEAVCServer@@PEAVWeakRef@01@@Z; Microsoft::WRL::AsWeak<CServer>(CServer *,Microsoft::WRL::WeakRef *)
0x180041718  mov     ebx, eax
0x18004171a  test    eax, eax
0x18004171c  js      loc_180041807
0x180041722  mov     [rsp+48h+lpThreadId], 0; lpThreadId
0x18004172b  mov     [rsp+48h+dwCreationFlags], 0; dwCreationFlags
0x180041733  xor     r9d, r9d; lpParameter
0x180041736  lea     r8, _CServerStart_ThreadProc; lpStartAddress
0x18004173d  xor     edx, edx; dwStackSize
0x18004173f  xor     ecx, ecx; lpThreadAttributes
0x180041741  call    cs:__imp_CreateThread
0x180041747  mov     [rsi+58h], rax
0x18004174b  test    rax, rax
0x18004174e  jnz     short loc_180041778
0x180041750  call    ?GetLastErrorError@@YAKXZ; GetLastErrorError(void)
0x180041755  test    eax, eax
0x180041757  jg      short loc_180041762
0x180041759  call    ?GetLastErrorError@@YAKXZ; GetLastErrorError(void)
0x18004175e  mov     ebx, eax
0x180041760  jmp     short loc_180041770
0x180041762  call    ?GetLastErrorError@@YAKXZ; GetLastErrorError(void)
0x180041767  movzx   ebx, ax
0x18004176a  or      ebx, 80070000h
0x180041770  test    ebx, ebx
0x180041772  js      loc_180041807
0x180041778  test    rdi, rdi
0x18004177b  jz      short loc_18004178C
0x18004177d  mov     rax, [rdi]
0x180041780  mov     rcx, rdi
0x180041783  mov     rax, [rax+8]
0x180041787  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004178c  xor     r8d, r8d; pcbe
0x18004178f  xor     edx, edx; pv
0x180041791  lea     rcx, _lambda_e49372d879d822098adbb9512c539288____lambda_invoker_cdecl_; pfnti
0x180041798  call    cs:__imp_CreateThreadpoolTimer
0x18004179e  mov     rbp, rax
0x1800417a1  mov     r14, [rsi+48h]
0x1800417a5  test    r14, r14
0x1800417a8  jz      short loc_1800417C4
0x1800417aa  call    cs:__imp_GetLastError
0x1800417b0  mov     ebx, eax
0x1800417b2  mov     rcx, r14; pti
0x1800417b5  call    cs:__imp_CloseThreadpoolTimer
0x1800417bb  mov     ecx, ebx; dwErrCode
0x1800417bd  call    cs:__imp_SetLastError
0x1800417c3  nop
0x1800417c4  mov     [rsi+48h], rbp
0x1800417c8  test    rbp, rbp
0x1800417cb  jz      short loc_1800417EE
0x1800417cd  xor     ebx, ebx
0x1800417cf  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], 0FFFFFFFFFECED300h
0x1800417d8  xor     r9d, r9d; msWindowLength
0x1800417db  xor     r8d, r8d; msPeriod
0x1800417de  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x1800417e3  mov     rcx, rbp; pti
0x1800417e6  call    cs:__imp_SetThreadpoolTimer
0x1800417ec  jmp     short loc_1800417F3
0x1800417ee  mov     ebx, 8007000Eh
0x1800417f3  test    rdi, rdi
0x1800417f6  jz      short loc_180041807
0x1800417f8  mov     rax, [rdi]
0x1800417fb  mov     rcx, rdi
0x1800417fe  mov     rax, [rax+10h]
0x180041802  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041807  lea     rcx, [rsp+48h+arg_0]
0x18004180c  call    ?InternalRelease@?$ComPtr@UITerminalServiceSessionPickerUX@Controller@Logon@UI@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(void)
0x180041811  mov     eax, ebx
0x180041813  mov     rbx, [rsp+48h+arg_10]
0x180041818  mov     rbp, [rsp+48h+arg_18]
0x18004181d  add     rsp, 30h
0x180041821  pop     r14
0x180041823  pop     rdi
0x180041824  pop     rsi
0x180041825  retn
```
