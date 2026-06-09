# FingerprintCollectorTimer::StartTimer(void)

- ea: `0x18001fac8`
- end: `0x18001fd2b`
- name: `?StartTimer@FingerprintCollectorTimer@@IEAAXXZ`
- size: `611`
- prototype: `void __fastcall(FingerprintCollectorTimer *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18001f180`

## callees

- `0x180001790`
- `0x1800034a0`
- `0x18000a9ec`
- `0x18001140c`
- `0x18001fac8`
- `0x180020020`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001fc3b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001fc3b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001fbd9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001fbd9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimerEx` at `0x18001fc61`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimerEx` at `0x18001fc61`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001fc0c`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001fc0c`

## string_xrefs

- `0x18001fd0d`: `Cannot start if start already started.`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall FingerprintCollectorTimer::StartTimer(FingerprintCollectorTimer *this)
{
  char v2; // di
  _BYTE *v3; // rcx
  bool v4; // dl
  _UNKNOWN **v5; // rax
  bool v6; // dl
  __int64 v7; // rbx
  __int64 v8; // rdx
  __int64 v9; // r8
  unsigned int v10; // eax
  const char *v11; // [rsp+28h] [rbp-E0h]
  struct _FILETIME pftDueTime; // [rsp+50h] [rbp-B8h] BYREF
  _BYTE v13[8]; // [rsp+58h] [rbp-B0h] BYREF
  _QWORD v14[13]; // [rsp+60h] [rbp-A8h] BYREF
  _QWORD *v15; // [rsp+C8h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+0h]

  v2 = 1;
  v3 = WPP_GLOBAL_Control;
  v4 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u;
  v5 = (_UNKNOWN **)WPP_RECORDER_INITIALIZED;
  if ( v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_AND_TRACE_SF_si(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v4,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
    v3 = WPP_GLOBAL_Control;
    v5 = (_UNKNOWN **)WPP_RECORDER_INITIALIZED;
  }
  v6 = v3 != (_BYTE *)&WPP_GLOBAL_Control && v3[25] >= 4u;
  if ( v6 || v5 != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_si(*((_QWORD *)v3 + 2), v6, v5 != &WPP_RECORDER_INITIALIZED, *((_QWORD *)v3 + 5));
  v7 = *((_QWORD *)this + 10);
  v14[0] = off_180038568;
  v14[1] = this;
  v15 = v14;
  AcquireSRWLockExclusive((PSRWLOCK)(v7 + 32));
  pftDueTime = (struct _FILETIME)(v7 + 32);
  if ( *(_BYTE *)(v7 + 40) )
  {
    v10 = wil::verify_hresult<long>(2147549183LL, v8, v9);
    wil::details::in1diag3::Throw_HrMsg(
      retaddr,
      (void *)0x3C,
      (unsigned int)"onecore\\drivers\\bluetooth\\foundation\\lib\\StateMachines.h",
      (const char *)v10,
      (int)"Cannot start if start already started.",
      v11);
  }
  *(_BYTE *)(v7 + 40) = 1;
  *(_BYTE *)(v7 + 168) = 1;
  *(_QWORD *)(v7 + 184) = 0;
  QueryPerformanceCounter((LARGE_INTEGER *)(v7 + 176));
  wistd::function<void (void)>::operator=(v7 + 48, v13);
  *(_QWORD *)(v7 + 192) = 1000LL * *((_QWORD *)this + 12);
  *(_BYTE *)(v7 + 41) = 0;
  if ( v7 != -32 )
    ReleaseSRWLockExclusive((PSRWLOCK)(v7 + 32));
  pftDueTime = (struct _FILETIME)(-10000000LL * *((_QWORD *)this + 12));
  SetThreadpoolTimerEx(*(PTP_TIMER *)(*(_QWORD *)(v7 + 24) + 80LL), &pftDueTime, 0, 0);
  if ( v15 )
    (*(void (__fastcall **)(_QWORD *))(*v15 + 24LL))(v15);
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
    v2 = 0;
  if ( v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_si(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v2,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
}

```

## disassembly

```asm
0x18001fac8  mov     [rsp+arg_8], rbx
0x18001facd  mov     [rsp+arg_10], rbp
0x18001fad2  push    rsi
0x18001fad3  push    rdi
0x18001fad4  push    r12
0x18001fad6  push    r13
0x18001fad8  push    r15
0x18001fada  sub     rsp, 0E0h
0x18001fae1  mov     rax, cs:__security_cookie
0x18001fae8  xor     rax, rsp
0x18001faeb  mov     [rsp+108h+var_38], rax
0x18001faf3  mov     rbp, rcx
0x18001faf6  lea     r15, WPP_GLOBAL_Control
0x18001fafd  mov     edi, 1
0x18001fb02  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fb09  cmp     rcx, r15
0x18001fb0c  jz      short loc_18001FB19
0x18001fb0e  cmp     byte ptr [rcx+19h], 5
0x18001fb12  jb      short loc_18001FB19
0x18001fb14  mov     dl, dil
0x18001fb17  jmp     short loc_18001FB1B
0x18001fb19  xor     dl, dl
0x18001fb1b  lea     r12, WPP_RECORDER_INITIALIZED
0x18001fb22  mov     rax, cs:WPP_RECORDER_INITIALIZED
0x18001fb29  cmp     rax, r12
0x18001fb2c  setnz   r8b
0x18001fb30  lea     r13, WPP_839c6382b2ad3f346a7c505e6bed1a32_Traceguids
0x18001fb37  test    dl, dl
0x18001fb39  jnz     short loc_18001FB40
0x18001fb3b  test    r8b, r8b
0x18001fb3e  jz      short loc_18001FB6C
0x18001fb40  mov     [rsp+108h+var_C0], rbp
0x18001fb45  mov     [rsp+108h+var_D0], r13
0x18001fb4a  mov     [rsp+108h+var_D8], 0Eh
0x18001fb51  mov     r9, [rcx+28h]
0x18001fb55  mov     rcx, [rcx+10h]
0x18001fb59  call    WPP_RECORDER_AND_TRACE_SF_si
0x18001fb5e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fb65  mov     rax, cs:WPP_RECORDER_INITIALIZED
0x18001fb6c  cmp     rcx, r15
0x18001fb6f  jz      short loc_18001FB7C
0x18001fb71  cmp     byte ptr [rcx+19h], 4
0x18001fb75  jb      short loc_18001FB7C
0x18001fb77  mov     dl, dil
0x18001fb7a  jmp     short loc_18001FB7E
0x18001fb7c  xor     dl, dl
0x18001fb7e  cmp     rax, r12
0x18001fb81  setnz   r8b
0x18001fb85  test    dl, dl
0x18001fb87  jnz     short loc_18001FB8E
0x18001fb89  test    r8b, r8b
0x18001fb8c  jz      short loc_18001FBB0
0x18001fb8e  mov     rax, [rbp+48h]
0x18001fb92  mov     [rsp+108h+var_C0], rax
0x18001fb97  mov     [rsp+108h+var_D0], r13
0x18001fb9c  mov     [rsp+108h+var_D8], 0Fh
0x18001fba3  mov     r9, [rcx+28h]
0x18001fba7  mov     rcx, [rcx+10h]
0x18001fbab  call    WPP_RECORDER_AND_TRACE_SF_si
0x18001fbb0  mov     rbx, [rbp+50h]
0x18001fbb4  lea     rax, off_180038568
0x18001fbbb  mov     [rsp+108h+var_A8], rax
0x18001fbc0  mov     [rsp+108h+var_A0], rbp
0x18001fbc5  lea     rax, [rsp+108h+var_A8]
0x18001fbca  mov     [rsp+108h+var_40], rax
0x18001fbd2  lea     rsi, [rbx+20h]
0x18001fbd6  mov     rcx, rsi; SRWLock
0x18001fbd9  call    cs:__imp_AcquireSRWLockExclusive
0x18001fbdf  mov     qword ptr [rsp+108h+pftDueTime.dwLowDateTime], rsi
0x18001fbe4  cmp     byte ptr [rbx+28h], 0
0x18001fbe8  jnz     loc_18001FCF8
0x18001fbee  mov     [rbx+28h], dil
0x18001fbf2  mov     eax, edi
0x18001fbf4  xchg    al, [rbx+0A8h]
0x18001fbfa  mov     qword ptr [rbx+0B8h], 0
0x18001fc05  lea     rcx, [rbx+0B0h]; lpPerformanceCount
0x18001fc0c  call    cs:__imp_QueryPerformanceCounter
0x18001fc12  lea     rcx, [rbx+30h]
0x18001fc16  lea     rdx, [rsp+108h+var_B0]
0x18001fc1b  call    ??4?$function@$$A6AXXZ@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::function<void (void)>::operator=(wistd::function<void (void)> &&)
0x18001fc20  imul    rax, [rbp+60h], 3E8h
0x18001fc28  mov     [rbx+0C0h], rax
0x18001fc2f  mov     byte ptr [rbx+29h], 0
0x18001fc33  test    rsi, rsi
0x18001fc36  jz      short loc_18001FC41
0x18001fc38  mov     rcx, rsi; SRWLock
0x18001fc3b  call    cs:__imp_ReleaseSRWLockExclusive
0x18001fc41  imul    rax, [rbp+60h], 0FFFFFFFFFF676980h
0x18001fc49  mov     qword ptr [rsp+108h+pftDueTime.dwLowDateTime], rax
0x18001fc4e  mov     rcx, [rbx+18h]
0x18001fc52  xor     r9d, r9d; msWindowLength
0x18001fc55  xor     r8d, r8d; msPeriod
0x18001fc58  lea     rdx, [rsp+108h+pftDueTime]; pftDueTime
0x18001fc5d  mov     rcx, [rcx+50h]; pti
0x18001fc61  call    cs:__imp_SetThreadpoolTimerEx
0x18001fc67  nop
0x18001fc68  mov     rcx, [rsp+108h+var_40]
0x18001fc70  test    rcx, rcx
0x18001fc73  jz      short loc_18001FC81
0x18001fc75  mov     rax, [rcx]
0x18001fc78  mov     rax, [rax+18h]
0x18001fc7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fc81  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fc88  cmp     rcx, r15
0x18001fc8b  jz      short loc_18001FC93
0x18001fc8d  cmp     byte ptr [rcx+19h], 5
0x18001fc91  jnb     short loc_18001FC96
0x18001fc93  xor     dil, dil
0x18001fc96  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18001fc9d  setnz   r8b
0x18001fca1  test    dil, dil
0x18001fca4  jnz     short loc_18001FCAB
0x18001fca6  test    r8b, r8b
0x18001fca9  jz      short loc_18001FCCC
0x18001fcab  mov     [rsp+108h+var_C0], rbp
0x18001fcb0  mov     [rsp+108h+var_D0], r13
0x18001fcb5  mov     [rsp+108h+var_D8], 11h
0x18001fcbc  mov     r9, [rcx+28h]
0x18001fcc0  mov     dl, dil
0x18001fcc3  mov     rcx, [rcx+10h]
0x18001fcc7  call    WPP_RECORDER_AND_TRACE_SF_si
0x18001fccc  mov     rcx, [rsp+108h+var_38]
0x18001fcd4  xor     rcx, rsp; StackCookie
0x18001fcd7  call    __security_check_cookie
0x18001fcdc  lea     r11, [rsp+108h+var_28]
0x18001fce4  mov     rbx, [r11+38h]
0x18001fce8  mov     rbp, [r11+40h]
0x18001fcec  mov     rsp, r11
0x18001fcef  pop     r15
0x18001fcf1  pop     r13
0x18001fcf3  pop     r12
0x18001fcf5  pop     rdi
0x18001fcf6  pop     rsi
0x18001fcf7  retn
0x18001fcf8  mov     ecx, 8000FFFFh
0x18001fcfd  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18001fd02  mov     r9d, eax; char *
0x18001fd05  mov     rcx, [rsp+108h]; this
0x18001fd0d  lea     rax, aCannotStartIfS; "Cannot start if start already started."
0x18001fd14  mov     qword ptr [rsp+108h+var_E8], rax; int
0x18001fd19  lea     r8, aOnecoreDrivers_5; "onecore\\drivers\\bluetooth\\foundation"...
0x18001fd20  mov     edx, 3Ch ; '<'; void *
0x18001fd25  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
```
