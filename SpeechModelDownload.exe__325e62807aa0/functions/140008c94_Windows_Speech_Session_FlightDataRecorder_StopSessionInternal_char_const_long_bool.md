# Windows::Speech::Session::FlightDataRecorder::StopSessionInternal(char const *,long,bool)

- ea: `0x140008c94`
- end: `0x140008dcc`
- name: `?StopSessionInternal@FlightDataRecorder@Session@Speech@Windows@@IEAAXPEBDJ_N@Z`
- size: `312`
- prototype: `void __fastcall(Windows::Speech::Session::FlightDataRecorder *this, const char *, unsigned int, char)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140008c20`
- `0x140019bc0`

## callees

- `0x140003c64`
- `0x140008c94`
- `0x14001d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140008cc6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140008cc6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140008db5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140008db5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140008cde`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140008cde`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x140008d08`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x140008d08`

## pseudocode

```c
void __fastcall Windows::Speech::Session::FlightDataRecorder::StopSessionInternal(
        Windows::Speech::Session::FlightDataRecorder *this,
        const char *a2,
        unsigned int a3,
        char a4)
{
  int v6; // r15d
  struct _RTL_CRITICAL_SECTION *v8; // rdi
  struct _TP_TIMER *v9; // rcx
  int v10; // r9d
  LONGLONG v11; // rbp
  __int64 v12; // rax
  LARGE_INTEGER PerformanceCount; // [rsp+70h] [rbp+8h] BYREF
  unsigned int v14; // [rsp+80h] [rbp+18h] BYREF

  v14 = a3;
  v6 = (int)a2;
  v8 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 112);
  if ( this != (Windows::Speech::Session::FlightDataRecorder *)-112LL )
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
  v9 = (struct _TP_TIMER *)*((_QWORD *)this + 12);
  if ( v9 )
    SetThreadpoolTimer(v9, 0, 0, 0);
  if ( !*((_BYTE *)this + 8) )
  {
    LOBYTE(a2) = 1;
    (**(void (__fastcall ***)(Windows::Speech::Session::FlightDataRecorder *, const char *))this)(this, a2);
  }
  PerformanceCount.QuadPart = 0;
  QueryPerformanceCounter(&PerformanceCount);
  v11 = 10000000 * PerformanceCount.QuadPart / *((_QWORD *)this + 3);
  if ( *((_BYTE *)this + 10) || *((_BYTE *)this + 9) )
    Windows::Speech::Session::FlightDataRecorder::AddEventToEventQueue<unsigned short [3],long>(
      (_DWORD)this,
      v6,
      v11,
      v10,
      (__int64)&v14);
  if ( *((_BYTE *)this + 10) && *((_BYTE *)this + 11) && a4 )
    (*(void (__fastcall **)(Windows::Speech::Session::FlightDataRecorder *, _QWORD))(*(_QWORD *)this + 56LL))(this, a3);
  if ( !*((_BYTE *)this + 14) )
  {
    v12 = *(_QWORD *)this;
    if ( *((_BYTE *)this + 10) )
      (*(void (__fastcall **)(Windows::Speech::Session::FlightDataRecorder *, _QWORD, LONGLONG))(v12 + 48))(
        this,
        a3,
        v11);
    else
      (*(void (__fastcall **)(Windows::Speech::Session::FlightDataRecorder *, _QWORD, LONGLONG))(v12 + 40))(
        this,
        a3,
        v11);
  }
  if ( *((_BYTE *)this + 13) )
    (*(void (__fastcall **)(Windows::Speech::Session::FlightDataRecorder *, _QWORD, LONGLONG))(*(_QWORD *)this + 104LL))(
      this,
      a3,
      v11);
  *((_BYTE *)this + 8) = 0;
  if ( v8 )
    LeaveCriticalSection(v8);
}

```

## disassembly

```asm
0x140008c94  mov     [rsp+arg_8], rbx
0x140008c99  mov     [rsp+arg_10], r8d
0x140008c9e  push    rbp
0x140008c9f  push    rsi
0x140008ca0  push    rdi
0x140008ca1  push    r14
0x140008ca3  push    r15
0x140008ca5  sub     rsp, 40h
0x140008ca9  mov     r14b, r9b
0x140008cac  mov     esi, r8d
0x140008caf  mov     r15, rdx
0x140008cb2  mov     rbx, rcx
0x140008cb5  lea     rdi, [rcx+70h]
0x140008cb9  mov     [rsp+68h+var_38], rdi
0x140008cbe  test    rdi, rdi
0x140008cc1  jz      short loc_140008CCD
0x140008cc3  mov     rcx, rdi; lpCriticalSection
0x140008cc6  call    cs:__imp_EnterCriticalSection
0x140008ccc  nop
0x140008ccd  mov     rcx, [rbx+60h]; pti
0x140008cd1  test    rcx, rcx
0x140008cd4  jz      short loc_140008CE4
0x140008cd6  xor     r9d, r9d; msWindowLength
0x140008cd9  xor     r8d, r8d; msPeriod
0x140008cdc  xor     edx, edx; pftDueTime
0x140008cde  call    cs:__imp_SetThreadpoolTimer
0x140008ce4  cmp     byte ptr [rbx+8], 0
0x140008ce8  jnz     short loc_140008CFA
0x140008cea  mov     rax, [rbx]
0x140008ced  mov     dl, 1
0x140008cef  mov     rcx, rbx
0x140008cf2  mov     rax, [rax]
0x140008cf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008cfa  mov     qword ptr [rsp+68h+PerformanceCount], 0
0x140008d03  lea     rcx, [rsp+68h+PerformanceCount]; lpPerformanceCount
0x140008d08  call    cs:__imp_QueryPerformanceCounter
0x140008d0e  imul    rax, qword ptr [rsp+68h+PerformanceCount], 989680h
0x140008d17  cqo
0x140008d19  idiv    qword ptr [rbx+18h]
0x140008d1d  mov     rbp, rax
0x140008d20  cmp     byte ptr [rbx+0Ah], 0
0x140008d24  jnz     short loc_140008D2C
0x140008d26  cmp     byte ptr [rbx+9], 0
0x140008d2a  jz      short loc_140008D47
0x140008d2c  lea     rax, [rsp+68h+arg_10]
0x140008d34  mov     [rsp+68h+var_48], rax
0x140008d39  mov     r8, rbp
0x140008d3c  mov     rdx, r15
0x140008d3f  mov     rcx, rbx
0x140008d42  call    ??$AddEventToEventQueue@$$BY02GJ@FlightDataRecorder@Session@Speech@Windows@@IEAAXPEBD_KAEAY02$$CBGAEBJ@Z; Windows::Speech::Session::FlightDataRecorder::AddEventToEventQueue<ushort [3],long>(char const *,unsigned __int64,ushort const (&)[3],long const &)
0x140008d47  cmp     byte ptr [rbx+0Ah], 0
0x140008d4b  jz      short loc_140008D69
0x140008d4d  cmp     byte ptr [rbx+0Bh], 0
0x140008d51  jz      short loc_140008D69
0x140008d53  test    r14b, r14b
0x140008d56  jz      short loc_140008D69
0x140008d58  mov     rax, [rbx]
0x140008d5b  mov     edx, esi
0x140008d5d  mov     rcx, rbx
0x140008d60  mov     rax, [rax+38h]
0x140008d64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008d69  cmp     byte ptr [rbx+0Eh], 0
0x140008d6d  jnz     short loc_140008D8F
0x140008d6f  mov     rax, [rbx]
0x140008d72  mov     r8, rbp
0x140008d75  mov     edx, esi
0x140008d77  mov     rcx, rbx
0x140008d7a  cmp     byte ptr [rbx+0Ah], 0
0x140008d7e  jnz     short loc_140008D86
0x140008d80  mov     rax, [rax+28h]
0x140008d84  jmp     short loc_140008D8A
0x140008d86  mov     rax, [rax+30h]
0x140008d8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008d8f  cmp     byte ptr [rbx+0Dh], 0
0x140008d93  jz      short loc_140008DA9
0x140008d95  mov     rax, [rbx]
0x140008d98  mov     r8, rbp
0x140008d9b  mov     edx, esi
0x140008d9d  mov     rcx, rbx
0x140008da0  mov     rax, [rax+68h]
0x140008da4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008da9  mov     byte ptr [rbx+8], 0
0x140008dad  test    rdi, rdi
0x140008db0  jz      short loc_140008DBB
0x140008db2  mov     rcx, rdi; lpCriticalSection
0x140008db5  call    cs:__imp_LeaveCriticalSection
0x140008dbb  mov     rbx, [rsp+68h+arg_8]
0x140008dc0  add     rsp, 40h
0x140008dc4  pop     r15
0x140008dc6  pop     r14
0x140008dc8  pop     rdi
0x140008dc9  pop     rsi
0x140008dca  pop     rbp
0x140008dcb  retn
```
