# Windows::Speech::Session::FlightDataRecorder::StartSessionInternal(char const *,bool)

- ea: `0x1400088c4`
- end: `0x140008ac5`
- name: `?StartSessionInternal@FlightDataRecorder@Session@Speech@Windows@@IEAAXPEBD_N@Z`
- size: `513`
- prototype: `void __fastcall(Windows::Speech::Session::FlightDataRecorder *this, const char *, __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x140008860`
- `0x1400192b0`

## callees

- `0x140003b10`
- `0x140005520`
- `0x140005bfc`
- `0x140005ea0`
- `0x14000732c`
- `0x1400088c4`
- `0x14001d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400088f9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400088f9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140008aa8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140008aa8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000892e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000892e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1400089a2`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1400089a2`

## pseudocode

```c
void __fastcall Windows::Speech::Session::FlightDataRecorder::StartSessionInternal(
        Windows::Speech::Session::FlightDataRecorder *this,
        const char *a2,
        __int64 a3)
{
  char v3; // r14
  struct _RTL_CRITICAL_SECTION *v6; // rdi
  struct _TP_TIMER *v7; // rcx
  int v8; // eax
  LARGE_INTEGER v9; // rcx
  LONGLONG v10; // rsi
  __int64 v11; // r8
  __int64 v12; // r8
  LARGE_INTEGER v13; // rcx
  __int64 v14; // rax
  LARGE_INTEGER PerformanceCount; // [rsp+60h] [rbp+30h] BYREF
  __int64 (__fastcall ***QuadPart)(_QWORD, GUID *, __int64 *); // [rsp+78h] [rbp+48h] BYREF

  v3 = a3;
  v6 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 112);
  if ( this != (Windows::Speech::Session::FlightDataRecorder *)-112LL )
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
  if ( *((_BYTE *)this + 8) )
  {
    LOBYTE(a3) = 1;
    (*(void (__fastcall **)(Windows::Speech::Session::FlightDataRecorder *, _QWORD, __int64))(*(_QWORD *)this + 8LL))(
      this,
      *((unsigned int *)this + 4),
      a3);
  }
  v7 = (struct _TP_TIMER *)*((_QWORD *)this + 12);
  if ( v7 )
    SetThreadpoolTimer(v7, (PFILETIME)this + 13, 0, 0);
  if ( *((_BYTE *)this + 10) || *((_BYTE *)this + 9) )
  {
    v8 = Windows::Speech::Session::FlightDataRecorder::EnsureJsonFactoryInit(this);
    PerformanceCount.QuadPart = 0;
    if ( v8 >= 0
      && (***((int (__fastcall ****)(_QWORD, GUID *, LARGE_INTEGER *))this + 9))(
           *((_QWORD *)this + 9),
           &GUID_d44662bc_dce3_59a8_9272_4b210f33908b,
           &PerformanceCount) >= 0 )
    {
      (*(void (__fastcall **)(LARGE_INTEGER))(*(_QWORD *)PerformanceCount.QuadPart + 120LL))(PerformanceCount);
    }
    v9 = PerformanceCount;
    if ( PerformanceCount.QuadPart )
    {
      PerformanceCount.QuadPart = 0;
      (*(void (__fastcall **)(LARGE_INTEGER))(*(_QWORD *)v9.QuadPart + 16LL))(v9);
    }
  }
  PerformanceCount.QuadPart = 0;
  QueryPerformanceCounter(&PerformanceCount);
  v10 = 10000000 * PerformanceCount.QuadPart / *((_QWORD *)this + 3);
  Windows::Speech::Session::FlightDataRecorder::CreateNewSessionId(this);
  if ( *((_BYTE *)this + 13) )
  {
    LOBYTE(v11) = v3;
    (*(void (__fastcall **)(Windows::Speech::Session::FlightDataRecorder *, LONGLONG, __int64))(*(_QWORD *)this + 96LL))(
      this,
      v10,
      v11);
  }
  if ( (*((_BYTE *)this + 10) || *((_BYTE *)this + 9))
    && (int)Windows::Speech::Session::FlightDataRecorder::EnsureJsonFactoryInit(this) >= 0 )
  {
    Windows::Speech::Session::FlightDataRecorder::MakeCoalescedEvent(this, (__int64 *)&PerformanceCount, a2);
    QuadPart = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))PerformanceCount.QuadPart;
    if ( PerformanceCount.QuadPart )
      (*(void (__fastcall **)(LARGE_INTEGER))(*(_QWORD *)PerformanceCount.QuadPart + 8LL))(PerformanceCount);
    Windows::Speech::Session::FlightDataRecorder::AddColumnToCoalescedEvent<bool>(this, (__int64 *)&QuadPart, v12, v3);
    QuadPart = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))PerformanceCount.QuadPart;
    if ( PerformanceCount.QuadPart )
      (*(void (__fastcall **)(LARGE_INTEGER))(*(_QWORD *)PerformanceCount.QuadPart + 8LL))(PerformanceCount);
    Windows::Speech::Session::FlightDataRecorder::AddEventToEventQueue(this, &QuadPart);
    v13 = PerformanceCount;
    if ( PerformanceCount.QuadPart )
    {
      PerformanceCount.QuadPart = 0;
      (*(void (__fastcall **)(LARGE_INTEGER))(*(_QWORD *)v13.QuadPart + 16LL))(v13);
    }
  }
  if ( !*((_BYTE *)this + 14) )
  {
    v14 = *(_QWORD *)this;
    LOBYTE(v11) = v3;
    if ( *((_BYTE *)this + 10) )
      (*(void (__fastcall **)(Windows::Speech::Session::FlightDataRecorder *, LONGLONG, __int64))(v14 + 32))(
        this,
        v10,
        v11);
    else
      (*(void (__fastcall **)(Windows::Speech::Session::FlightDataRecorder *, LONGLONG, __int64))(v14 + 24))(
        this,
        v10,
        v11);
  }
  *((_BYTE *)this + 8) = 1;
  if ( v6 )
    LeaveCriticalSection(v6);
}

```

## disassembly

```asm
0x1400088c4  mov     [rsp-28h+arg_8], rbx
0x1400088c9  mov     [rsp-28h+arg_10], rsi
0x1400088ce  push    rbp
0x1400088cf  push    rdi
0x1400088d0  push    r12
0x1400088d2  push    r14
0x1400088d4  push    r15
0x1400088d6  mov     rbp, rsp
0x1400088d9  sub     rsp, 30h
0x1400088dd  mov     r14b, r8b
0x1400088e0  mov     r15, rdx
0x1400088e3  mov     rbx, rcx
0x1400088e6  lea     rdi, [rcx+70h]
0x1400088ea  mov     [rbp+var_10], rdi
0x1400088ee  xor     r12d, r12d
0x1400088f1  test    rdi, rdi
0x1400088f4  jz      short loc_140008900
0x1400088f6  mov     rcx, rdi; lpCriticalSection
0x1400088f9  call    cs:__imp_EnterCriticalSection
0x1400088ff  nop
0x140008900  cmp     [rbx+8], r12b
0x140008904  jz      short loc_14000891B
0x140008906  mov     rax, [rbx]
0x140008909  mov     r8b, 1
0x14000890c  mov     edx, [rbx+10h]
0x14000890f  mov     rcx, rbx
0x140008912  mov     rax, [rax+8]
0x140008916  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000891b  mov     rcx, [rbx+60h]; pti
0x14000891f  test    rcx, rcx
0x140008922  jz      short loc_140008934
0x140008924  lea     rdx, [rbx+68h]; pftDueTime
0x140008928  xor     r9d, r9d; msWindowLength
0x14000892b  xor     r8d, r8d; msPeriod
0x14000892e  call    cs:__imp_SetThreadpoolTimer
0x140008934  cmp     [rbx+0Ah], r12b
0x140008938  jnz     short loc_140008940
0x14000893a  cmp     [rbx+9], r12b
0x14000893e  jz      short loc_14000899A
0x140008940  mov     rcx, rbx; this
0x140008943  call    ?EnsureJsonFactoryInit@FlightDataRecorder@Session@Speech@Windows@@IEAAJXZ; Windows::Speech::Session::FlightDataRecorder::EnsureJsonFactoryInit(void)
0x140008948  mov     qword ptr [rbp+PerformanceCount], r12
0x14000894c  test    eax, eax
0x14000894e  js      short loc_140008980
0x140008950  mov     rcx, [rbx+48h]
0x140008954  mov     rax, [rcx]
0x140008957  lea     r8, [rbp+PerformanceCount]
0x14000895b  lea     rdx, _GUID_d44662bc_dce3_59a8_9272_4b210f33908b
0x140008962  mov     rax, [rax]
0x140008965  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000896a  nop
0x14000896b  test    eax, eax
0x14000896d  js      short loc_140008980
0x14000896f  mov     rcx, qword ptr [rbp+PerformanceCount]
0x140008973  mov     rax, [rcx]
0x140008976  mov     rax, [rax+78h]
0x14000897a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000897f  nop
0x140008980  mov     rcx, qword ptr [rbp+PerformanceCount]
0x140008984  test    rcx, rcx
0x140008987  jz      short loc_14000899A
0x140008989  mov     qword ptr [rbp+PerformanceCount], r12
0x14000898d  mov     rax, [rcx]
0x140008990  mov     rax, [rax+10h]
0x140008994  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008999  nop
0x14000899a  mov     qword ptr [rbp+PerformanceCount], r12
0x14000899e  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1400089a2  call    cs:__imp_QueryPerformanceCounter
0x1400089a8  imul    rax, qword ptr [rbp+PerformanceCount], 989680h
0x1400089b0  cqo
0x1400089b2  idiv    qword ptr [rbx+18h]
0x1400089b6  mov     rsi, rax
0x1400089b9  mov     rcx, rbx; this
0x1400089bc  call    ?CreateNewSessionId@FlightDataRecorder@Session@Speech@Windows@@IEAAXXZ; Windows::Speech::Session::FlightDataRecorder::CreateNewSessionId(void)
0x1400089c1  cmp     [rbx+0Dh], r12b
0x1400089c5  jz      short loc_1400089DC
0x1400089c7  mov     rcx, [rbx]
0x1400089ca  mov     rax, [rcx+60h]
0x1400089ce  mov     r8b, r14b
0x1400089d1  mov     rdx, rsi
0x1400089d4  mov     rcx, rbx
0x1400089d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400089dc  cmp     [rbx+0Ah], r12b
0x1400089e0  jnz     short loc_1400089EC
0x1400089e2  cmp     [rbx+9], r12b
0x1400089e6  jz      loc_140008A75
0x1400089ec  mov     rcx, rbx; this
0x1400089ef  call    ?EnsureJsonFactoryInit@FlightDataRecorder@Session@Speech@Windows@@IEAAJXZ; Windows::Speech::Session::FlightDataRecorder::EnsureJsonFactoryInit(void)
0x1400089f4  test    eax, eax
0x1400089f6  js      short loc_140008A75
0x1400089f8  mov     r9, rsi
0x1400089fb  mov     r8, r15
0x1400089fe  lea     rdx, [rbp+PerformanceCount]
0x140008a02  mov     rcx, rbx
0x140008a05  call    ?MakeCoalescedEvent@FlightDataRecorder@Session@Speech@Windows@@IEAA?AV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@PEBD_K@Z; Windows::Speech::Session::FlightDataRecorder::MakeCoalescedEvent(char const *,unsigned __int64)
0x140008a0a  nop
0x140008a0b  mov     rcx, qword ptr [rbp+PerformanceCount]
0x140008a0f  mov     [rbp+arg_18], rcx
0x140008a13  test    rcx, rcx
0x140008a16  jz      short loc_140008A25
0x140008a18  mov     rax, [rcx]
0x140008a1b  mov     rax, [rax+8]
0x140008a1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008a24  nop
0x140008a25  mov     r9b, r14b
0x140008a28  lea     rdx, [rbp+arg_18]
0x140008a2c  mov     rcx, rbx; this
0x140008a2f  call    ??$AddColumnToCoalescedEvent@_N@FlightDataRecorder@Session@Speech@Windows@@IEAAJV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@PEBG_N@Z; Windows::Speech::Session::FlightDataRecorder::AddColumnToCoalescedEvent<bool>(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>,ushort const *,bool)
0x140008a34  mov     rcx, qword ptr [rbp+PerformanceCount]
0x140008a38  mov     [rbp+arg_18], rcx
0x140008a3c  test    rcx, rcx
0x140008a3f  jz      short loc_140008A4E
0x140008a41  mov     rax, [rcx]
0x140008a44  mov     rax, [rax+8]
0x140008a48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008a4d  nop
0x140008a4e  lea     rdx, [rbp+arg_18]
0x140008a52  mov     rcx, rbx
0x140008a55  call    ?AddEventToEventQueue@FlightDataRecorder@Session@Speech@Windows@@IEAAXV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Z; Windows::Speech::Session::FlightDataRecorder::AddEventToEventQueue(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>)
0x140008a5a  nop
0x140008a5b  mov     rcx, qword ptr [rbp+PerformanceCount]
0x140008a5f  test    rcx, rcx
0x140008a62  jz      short loc_140008A75
0x140008a64  mov     qword ptr [rbp+PerformanceCount], r12
0x140008a68  mov     rax, [rcx]
0x140008a6b  mov     rax, [rax+10h]
0x140008a6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008a74  nop
0x140008a75  cmp     [rbx+0Eh], r12b
0x140008a79  jnz     short loc_140008A9C
0x140008a7b  mov     rax, [rbx]
0x140008a7e  mov     r8b, r14b
0x140008a81  mov     rdx, rsi
0x140008a84  mov     rcx, rbx
0x140008a87  cmp     [rbx+0Ah], r12b
0x140008a8b  jnz     short loc_140008A93
0x140008a8d  mov     rax, [rax+18h]
0x140008a91  jmp     short loc_140008A97
0x140008a93  mov     rax, [rax+20h]
0x140008a97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008a9c  mov     byte ptr [rbx+8], 1
0x140008aa0  test    rdi, rdi
0x140008aa3  jz      short loc_140008AAE
0x140008aa5  mov     rcx, rdi; lpCriticalSection
0x140008aa8  call    cs:__imp_LeaveCriticalSection
0x140008aae  mov     rbx, [rsp+30h+arg_8]
0x140008ab3  mov     rsi, [rsp+30h+arg_10]
0x140008ab8  add     rsp, 30h
0x140008abc  pop     r15
0x140008abe  pop     r14
0x140008ac0  pop     r12
0x140008ac2  pop     rdi
0x140008ac3  pop     rbp
0x140008ac4  retn
```
