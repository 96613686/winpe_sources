# Windows::Speech::Session::FlightDataRecorder::StopSessionInternal(char const *,long,bool)

- ea: `0x14000fd30`
- end: `0x14000fe2c`
- name: `?StopSessionInternal@FlightDataRecorder@Session@Speech@Windows@@IEAAXPEBDJ_N@Z`
- size: `252`
- prototype: `void __fastcall(Windows::Speech::Session::FlightDataRecorder *__hidden this, const char *, int, bool)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x14000fcd0`

## callees

- `0x140005378`
- `0x140007884`
- `0x140008164`
- `0x14000b9c0`
- `0x14000c248`
- `0x14000fd30`
- `0x140031010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000fd6e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000fd6e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Windows::Speech::Session::FlightDataRecorder::StopSessionInternal(
        Windows::Speech::Session::FlightDataRecorder *this,
        const char *a2,
        unsigned int a3,
        char a4)
{
  struct _TP_TIMER *v7; // rcx
  unsigned __int64 HighResolutionTimeInHNS; // rdi
  int v9; // r9d
  __int64 v10; // rax
  const char *v11; // [rsp+58h] [rbp+10h] BYREF
  unsigned int v12; // [rsp+60h] [rbp+18h] BYREF

  v12 = a3;
  v11 = a2;
  SpAutoLock::SpAutoLock((SpAutoLock *)&v11, (Windows::Speech::Session::FlightDataRecorder *)((char *)this + 112));
  v7 = (struct _TP_TIMER *)*((_QWORD *)this + 12);
  if ( v7 )
    SetThreadpoolTimer(v7, 0, 0, 0);
  Windows::Speech::Session::FlightDataRecorder::ImplicitStartSessionIfNeeded(this);
  HighResolutionTimeInHNS = Windows::Speech::Session::FlightDataRecorder::GetHighResolutionTimeInHNS(this);
  if ( *((_BYTE *)this + 10) || *((_BYTE *)this + 9) )
    Windows::Speech::Session::FlightDataRecorder::AddEventToEventQueue<unsigned short [3],long>(
      (_DWORD)this,
      (unsigned int)"SpeechRuntime_Stop",
      HighResolutionTimeInHNS,
      v9,
      (__int64)&v12);
  if ( *((_BYTE *)this + 10) && *((_BYTE *)this + 11) && a4 )
    (*(void (__fastcall **)(Windows::Speech::Session::FlightDataRecorder *, _QWORD))(*(_QWORD *)this + 56LL))(this, a3);
  if ( !*((_BYTE *)this + 14) )
  {
    v10 = *(_QWORD *)this;
    if ( *((_BYTE *)this + 10) )
      (*(void (__fastcall **)(Windows::Speech::Session::FlightDataRecorder *, _QWORD, unsigned __int64))(v10 + 48))(
        this,
        a3,
        HighResolutionTimeInHNS);
    else
      (*(void (__fastcall **)(Windows::Speech::Session::FlightDataRecorder *, _QWORD, unsigned __int64))(v10 + 40))(
        this,
        a3,
        HighResolutionTimeInHNS);
  }
  if ( *((_BYTE *)this + 13) )
    (*(void (__fastcall **)(Windows::Speech::Session::FlightDataRecorder *, _QWORD, unsigned __int64))(*(_QWORD *)this + 104LL))(
      this,
      a3,
      HighResolutionTimeInHNS);
  *((_BYTE *)this + 8) = 0;
  SpAutoLock::~SpAutoLock((SpAutoLock *)&v11);
}

```

## disassembly

```asm
0x14000fd30  mov     rax, rsp
0x14000fd33  mov     [rax+8], rbx
0x14000fd37  mov     [rax+18h], r8d
0x14000fd3b  mov     [rax+10h], rdx
0x14000fd3f  push    rbp
0x14000fd40  push    rsi
0x14000fd41  push    rdi
0x14000fd42  sub     rsp, 30h
0x14000fd46  mov     bpl, r9b
0x14000fd49  mov     esi, r8d
0x14000fd4c  mov     rbx, rcx
0x14000fd4f  lea     rdx, [rcx+70h]; struct SpCritSect *
0x14000fd53  lea     rcx, [rax+10h]; this
0x14000fd57  call    ??0SpAutoLock@@QEAA@PEAVSpCritSect@@@Z; SpAutoLock::SpAutoLock(SpCritSect *)
0x14000fd5c  nop
0x14000fd5d  mov     rcx, [rbx+60h]; pti
0x14000fd61  test    rcx, rcx
0x14000fd64  jz      short loc_14000FD74
0x14000fd66  xor     r9d, r9d; msWindowLength
0x14000fd69  xor     r8d, r8d; msPeriod
0x14000fd6c  xor     edx, edx; pftDueTime
0x14000fd6e  call    cs:__imp_SetThreadpoolTimer
0x14000fd74  mov     rcx, rbx; this
0x14000fd77  call    ?ImplicitStartSessionIfNeeded@FlightDataRecorder@Session@Speech@Windows@@IEAAXXZ; Windows::Speech::Session::FlightDataRecorder::ImplicitStartSessionIfNeeded(void)
0x14000fd7c  mov     rcx, rbx; this
0x14000fd7f  call    ?GetHighResolutionTimeInHNS@FlightDataRecorder@Session@Speech@Windows@@IEAA_KXZ; Windows::Speech::Session::FlightDataRecorder::GetHighResolutionTimeInHNS(void)
0x14000fd84  mov     rdi, rax
0x14000fd87  cmp     byte ptr [rbx+0Ah], 0
0x14000fd8b  jnz     short loc_14000FD93
0x14000fd8d  cmp     byte ptr [rbx+9], 0
0x14000fd91  jz      short loc_14000FDAF
0x14000fd93  lea     rax, [rsp+48h+arg_10]
0x14000fd98  mov     [rsp+48h+var_28], rax
0x14000fd9d  mov     r8, rdi
0x14000fda0  lea     rdx, aSpeechruntimeS_0; "SpeechRuntime_Stop"
0x14000fda7  mov     rcx, rbx
0x14000fdaa  call    ??$AddEventToEventQueue@$$BY02GJ@FlightDataRecorder@Session@Speech@Windows@@IEAAXPEBD_KAEAY02$$CBGAEBJ@Z; Windows::Speech::Session::FlightDataRecorder::AddEventToEventQueue<ushort [3],long>(char const *,unsigned __int64,ushort const (&)[3],long const &)
0x14000fdaf  cmp     byte ptr [rbx+0Ah], 0
0x14000fdb3  jz      short loc_14000FDD1
0x14000fdb5  cmp     byte ptr [rbx+0Bh], 0
0x14000fdb9  jz      short loc_14000FDD1
0x14000fdbb  test    bpl, bpl
0x14000fdbe  jz      short loc_14000FDD1
0x14000fdc0  mov     rax, [rbx]
0x14000fdc3  mov     edx, esi
0x14000fdc5  mov     rcx, rbx
0x14000fdc8  mov     rax, [rax+38h]
0x14000fdcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000fdd1  cmp     byte ptr [rbx+0Eh], 0
0x14000fdd5  jnz     short loc_14000FDF7
0x14000fdd7  mov     rax, [rbx]
0x14000fdda  mov     r8, rdi
0x14000fddd  mov     edx, esi
0x14000fddf  mov     rcx, rbx
0x14000fde2  cmp     byte ptr [rbx+0Ah], 0
0x14000fde6  jnz     short loc_14000FDEE
0x14000fde8  mov     rax, [rax+28h]
0x14000fdec  jmp     short loc_14000FDF2
0x14000fdee  mov     rax, [rax+30h]
0x14000fdf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000fdf7  cmp     byte ptr [rbx+0Dh], 0
0x14000fdfb  jz      short loc_14000FE11
0x14000fdfd  mov     rax, [rbx]
0x14000fe00  mov     r8, rdi
0x14000fe03  mov     edx, esi
0x14000fe05  mov     rcx, rbx
0x14000fe08  mov     rax, [rax+68h]
0x14000fe0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000fe11  mov     byte ptr [rbx+8], 0
0x14000fe15  lea     rcx, [rsp+48h+arg_8]; this
0x14000fe1a  call    ??1SpAutoLock@@QEAA@XZ; SpAutoLock::~SpAutoLock(void)
0x14000fe1f  mov     rbx, [rsp+48h+arg_0]
0x14000fe24  add     rsp, 30h
0x14000fe28  pop     rdi
0x14000fe29  pop     rsi
0x14000fe2a  pop     rbp
0x14000fe2b  retn
```
