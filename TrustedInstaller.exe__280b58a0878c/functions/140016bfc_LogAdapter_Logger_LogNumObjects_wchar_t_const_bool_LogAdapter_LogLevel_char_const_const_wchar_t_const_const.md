# LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)

- ea: `0x140016bfc`
- end: `0x140016ce2`
- name: `??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z`
- size: `230`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64)`
- caller_count: `24`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1400174c0`
- `0x140017ecc`
- `0x140018630`
- `0x140019d84`
- `0x14001a16c`
- `0x14001a4c0`
- `0x14001a7e4`
- `0x14001acbc`
- `0x14001afa4`
- `0x14001e32c`
- `0x14001e898`
- `0x14001e980`
- `0x14001eb74`
- `0x14001f134`
- `0x14001f6ac`
- `0x14001fc6c`
- `0x140022548`
- `0x140022adc`
- `0x140023a48`
- `0x140023c20`
- `0x140023f90`
- `0x140024568`
- `0x140025190`
- `0x140025540`

## callees

- `0x1400023e0`
- `0x14000679c`
- `0x140006e38`
- `0x140016bfc`
- `0x14001731c`
- `0x1400183c0`
- `0x14002b010`

## pseudocode

```c
__int64 __fastcall LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5)
{
  int v7; // eax
  int v8; // eax
  unsigned int v9; // ebx
  __int64 v11; // [rsp+20h] [rbp-40h] BYREF
  char v12; // [rsp+28h] [rbp-38h]
  _QWORD v13[4]; // [rsp+30h] [rbp-30h] BYREF
  int v14; // [rsp+50h] [rbp-10h] BYREF

  v11 = a1 + 4160;
  v14 = 0;
  v12 = 0;
  v7 = Windows::Rtl::CriticalSectionLockGrant::Acquire((Windows::Rtl::CriticalSectionLockGrant *)&v11);
  if ( v7 >= 0 )
  {
    v8 = (**(__int64 (__fastcall ***)(__int64))a1)(a1);
    if ( v8 >= 0 )
    {
      Windows::Tracing::RtlFormatIntoStream<wchar_t *>(*(_QWORD *)(a1 + 8), a4, a5);
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 8) + 496LL))(*(_QWORD *)(a1 + 8));
      v9 = 0;
      goto LABEL_6;
    }
  }
  else
  {
    v13[2] = 195;
    v13[0] = "OneCore\\Private\\Base\\inc\\LogAdapter.h";
    v13[1] = "LogAdapter::Logger::LogNumObjects";
    v13[3] = "QueueLock.Acquire()";
    v8 = Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateNtStatus(
           &v14,
           v13,
           (unsigned int)v7);
  }
  v9 = v8;
LABEL_6:
  Windows::Rtl::CriticalSectionLockGrant::~CriticalSectionLockGrant((Windows::Rtl::CriticalSectionLockGrant *)&v11);
  return v9;
}

```

## disassembly

```asm
0x140016bfc  mov     [rsp-18h+arg_8], rbx
0x140016c01  push    rbp
0x140016c02  push    rsi
0x140016c03  push    rdi
0x140016c04  mov     rbp, rsp
0x140016c07  sub     rsp, 60h
0x140016c0b  mov     rax, cs:__security_cookie
0x140016c12  xor     rax, rsp
0x140016c15  mov     [rbp+var_8], rax
0x140016c19  mov     rsi, [rbp+arg_20]
0x140016c1d  lea     rax, [rcx+1040h]
0x140016c24  mov     rbx, rcx
0x140016c27  mov     [rbp+var_40], rax
0x140016c2b  lea     rcx, [rbp+var_40]; this
0x140016c2f  mov     [rbp+var_10], 0
0x140016c36  mov     rdi, r9
0x140016c39  mov     [rbp+var_38], 0
0x140016c3d  call    ?Acquire@CriticalSectionLockGrant@Rtl@Windows@@QEAAJXZ; Windows::Rtl::CriticalSectionLockGrant::Acquire(void)
0x140016c42  test    eax, eax
0x140016c44  jns     short loc_140016C81
0x140016c46  lea     rcx, aOnecorePrivate; "OneCore\\Private\\Base\\inc\\LogAdapter"...
0x140016c4d  mov     [rbp+var_20], 0C3h
0x140016c55  mov     [rbp+var_30], rcx
0x140016c59  lea     rdx, [rbp+var_30]
0x140016c5d  lea     rcx, aLogadapterLogg_0; "LogAdapter::Logger::LogNumObjects"
0x140016c64  mov     r8d, eax
0x140016c67  mov     [rbp+var_28], rcx
0x140016c6b  lea     rcx, aQueuelockAcqui; "QueueLock.Acquire()"
0x140016c72  mov     [rbp+var_18], rcx
0x140016c76  lea     rcx, [rbp+var_10]
0x140016c7a  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x140016c7f  jmp     short loc_140016C93
0x140016c81  mov     rax, [rbx]
0x140016c84  mov     rcx, rbx
0x140016c87  mov     rax, [rax]
0x140016c8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140016c8f  test    eax, eax
0x140016c91  jns     short loc_140016C97
0x140016c93  mov     ebx, eax
0x140016c95  jmp     short loc_140016CBB
0x140016c97  mov     rcx, [rbx+8]
0x140016c9b  mov     r8, rsi
0x140016c9e  mov     rdx, rdi
0x140016ca1  call    ??$RtlFormatIntoStream@PEA_W@Tracing@Windows@@YAXPEAUIRtlFormattedOutputStream@Rtl@1@QEBDAEBQEA_W@Z; Windows::Tracing::RtlFormatIntoStream<wchar_t *>(Windows::Rtl::IRtlFormattedOutputStream *,char const * const,wchar_t * const &)
0x140016ca6  mov     rcx, [rbx+8]
0x140016caa  mov     rax, [rcx]
0x140016cad  mov     rax, [rax+1F0h]
0x140016cb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140016cb9  xor     ebx, ebx
0x140016cbb  lea     rcx, [rbp+var_40]; this
0x140016cbf  call    ??1CriticalSectionLockGrant@Rtl@Windows@@QEAA@XZ; Windows::Rtl::CriticalSectionLockGrant::~CriticalSectionLockGrant(void)
0x140016cc4  mov     eax, ebx
0x140016cc6  mov     rcx, [rbp+var_8]
0x140016cca  xor     rcx, rsp; StackCookie
0x140016ccd  call    __security_check_cookie
0x140016cd2  mov     rbx, [rsp+60h+arg_8]
0x140016cda  add     rsp, 60h
0x140016cde  pop     rdi
0x140016cdf  pop     rsi
0x140016ce0  pop     rbp
0x140016ce1  retn
```
