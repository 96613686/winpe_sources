# LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)

- ea: `0x140016fb4`
- end: `0x14001713b`
- name: `??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z`
- size: `391`
- prototype: `__int64 __fastcall(__int64, __int64, int, __int64, __int64)`
- caller_count: `69`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x140017448`
- `0x1400174c0`
- `0x1400178b8`
- `0x140017d40`
- `0x140017ecc`
- `0x140018180`
- `0x140018630`
- `0x140019d84`
- `0x14001a16c`
- `0x14001a4c0`
- `0x14001a7e4`
- `0x14001acbc`
- `0x14001afa4`
- `0x14001c7a8`
- `0x14001c9a0`
- `0x14001cd14`
- `0x14001cfc4`
- `0x14001d13c`
- `0x14001d404`
- `0x14001d5cc`
- `0x14001d7d4`
- `0x14001d9a4`
- `0x14001dc7c`
- `0x14001ddb8`
- `0x14001e050`
- `0x14001e19c`
- `0x14001e32c`
- `0x14001e564`
- `0x14001e898`
- `0x14001e980`
- `0x14001eb74`
- `0x14001ee54`
- `0x14001f134`
- `0x14001f6ac`
- `0x14001f880`
- `0x14001fab0`
- `0x14001fc6c`
- `0x1400200b8`
- `0x14002027c`
- `0x1400203b8`
- `0x1400206cc`
- `0x140020924`
- `0x140020ae8`
- `0x140020c84`
- `0x140020f38`
- `0x140020ffc`
- `0x14002126c`
- `0x140021594`
- `0x14002180c`
- `0x140022498`

## callees

- `0x1400023e0`
- `0x14000679c`
- `0x140006e38`
- `0x140008138`
- `0x140016fb4`
- `0x1400173a4`
- `0x1400183c0`
- `0x14002b010`

## pseudocode

```c
__int64 __fastcall LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        __int64 a1,
        __int64 a2,
        int a3,
        __int64 a4,
        __int64 a5)
{
  int v8; // eax
  int v9; // eax
  unsigned int v10; // ebx
  __int64 v11; // r8
  __int64 v13; // [rsp+20h] [rbp-60h] BYREF
  char v14; // [rsp+28h] [rbp-58h]
  _QWORD v15[4]; // [rsp+30h] [rbp-50h] BYREF
  _QWORD v16[4]; // [rsp+50h] [rbp-30h] BYREF
  int v17; // [rsp+70h] [rbp-10h] BYREF

  v13 = a1 + 4160;
  v17 = 0;
  v14 = 0;
  v8 = Windows::Rtl::CriticalSectionLockGrant::Acquire((Windows::Rtl::CriticalSectionLockGrant *)&v13);
  if ( v8 >= 0 )
  {
    v9 = (**(__int64 (__fastcall ***)(__int64))a1)(a1);
    if ( v9 >= 0 )
    {
      *(_DWORD *)(a1 + 4152) = a3;
      if ( *(_QWORD *)(a1 + 32) )
      {
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 8) + 496LL))(*(_QWORD *)(a1 + 8));
        (*(void (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(a1 + 16) + 224LL))(*(_QWORD *)(a1 + 16), a1 + 40);
        *(_BYTE *)(a1 + 40) = 0;
        *(_QWORD *)(a1 + 32) = 0;
      }
      Windows::Tracing::RtlFormatIntoStream<Windows::WCP::Rtl::FormatHResultWrapper<long>>(*(_QWORD *)(a1 + 16), a4, a5);
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 16) + 496LL))(*(_QWORD *)(a1 + 16));
      v11 = *(unsigned int *)(a1 + 4156);
      if ( (int)v11 >= 0 )
      {
        v10 = 0;
        goto LABEL_10;
      }
      v16[2] = 215;
      v16[0] = "OneCore\\Private\\Base\\inc\\LogAdapter.h";
      v16[3] = "m_FlushSink.Hr()";
      v16[1] = "LogAdapter::Logger::LogNumObjects";
      v9 = Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateHResult(
             &v17,
             v16,
             v11);
    }
  }
  else
  {
    v15[2] = 195;
    v15[0] = "OneCore\\Private\\Base\\inc\\LogAdapter.h";
    v15[1] = "LogAdapter::Logger::LogNumObjects";
    v15[3] = "QueueLock.Acquire()";
    v9 = Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateNtStatus(
           &v17,
           v15,
           (unsigned int)v8);
  }
  v10 = v9;
LABEL_10:
  Windows::Rtl::CriticalSectionLockGrant::~CriticalSectionLockGrant((Windows::Rtl::CriticalSectionLockGrant *)&v13);
  return v10;
}

```

## disassembly

```asm
0x140016fb4  mov     [rsp-18h+arg_8], rbx
0x140016fb9  mov     [rsp-18h+arg_10], rsi
0x140016fbe  push    rbp
0x140016fbf  push    rdi
0x140016fc0  push    r14
0x140016fc2  mov     rbp, rsp
0x140016fc5  sub     rsp, 80h
0x140016fcc  mov     rax, cs:__security_cookie
0x140016fd3  xor     rax, rsp
0x140016fd6  mov     [rbp+var_8], rax
0x140016fda  mov     r14, [rbp+arg_20]
0x140016fde  lea     rax, [rcx+1040h]
0x140016fe5  mov     rdi, rcx
0x140016fe8  mov     [rbp+var_60], rax
0x140016fec  lea     rcx, [rbp+var_60]; this
0x140016ff0  mov     [rbp+var_10], 0
0x140016ff7  mov     rsi, r9
0x140016ffa  mov     [rbp+var_58], 0
0x140016ffe  mov     ebx, r8d
0x140017001  call    ?Acquire@CriticalSectionLockGrant@Rtl@Windows@@QEAAJXZ; Windows::Rtl::CriticalSectionLockGrant::Acquire(void)
0x140017006  test    eax, eax
0x140017008  jns     short loc_140017045
0x14001700a  lea     rcx, aOnecorePrivate; "OneCore\\Private\\Base\\inc\\LogAdapter"...
0x140017011  mov     [rbp+var_40], 0C3h
0x140017019  mov     [rbp+var_50], rcx
0x14001701d  lea     rdx, [rbp+var_50]
0x140017021  lea     rcx, aLogadapterLogg_0; "LogAdapter::Logger::LogNumObjects"
0x140017028  mov     r8d, eax
0x14001702b  mov     [rbp+var_48], rcx
0x14001702f  lea     rcx, aQueuelockAcqui; "QueueLock.Acquire()"
0x140017036  mov     [rbp+var_38], rcx
0x14001703a  lea     rcx, [rbp+var_10]
0x14001703e  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x140017043  jmp     short loc_140017057
0x140017045  mov     rax, [rdi]
0x140017048  mov     rcx, rdi
0x14001704b  mov     rax, [rax]
0x14001704e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140017053  test    eax, eax
0x140017055  jns     short loc_14001705E
0x140017057  mov     ebx, eax
0x140017059  jmp     loc_14001710C
0x14001705e  mov     [rdi+1038h], ebx
0x140017064  cmp     qword ptr [rdi+20h], 0
0x140017069  jbe     short loc_1400170A1
0x14001706b  mov     rcx, [rdi+8]
0x14001706f  mov     rax, [rcx]
0x140017072  mov     rax, [rax+1F0h]
0x140017079  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001707e  mov     rcx, [rdi+10h]
0x140017082  lea     rdx, [rdi+28h]
0x140017086  mov     rax, [rcx]
0x140017089  mov     rax, [rax+0E0h]
0x140017090  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140017095  mov     byte ptr [rdi+28h], 0
0x140017099  mov     qword ptr [rdi+20h], 0
0x1400170a1  mov     rcx, [rdi+10h]
0x1400170a5  mov     r8, r14
0x1400170a8  mov     rdx, rsi
0x1400170ab  call    ??$RtlFormatIntoStream@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Tracing@Windows@@YAXPEAUIRtlFormattedOutputStream@Rtl@1@QEBDAEBU?$FormatHResultWrapper@J@3WCP@1@@Z; Windows::Tracing::RtlFormatIntoStream<Windows::WCP::Rtl::FormatHResultWrapper<long>>(Windows::Rtl::IRtlFormattedOutputStream *,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1400170b0  mov     rcx, [rdi+10h]
0x1400170b4  mov     rax, [rcx]
0x1400170b7  mov     rax, [rax+1F0h]
0x1400170be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400170c3  mov     r8d, [rdi+103Ch]
0x1400170ca  test    r8d, r8d
0x1400170cd  jns     short loc_14001710A
0x1400170cf  lea     rcx, aOnecorePrivate; "OneCore\\Private\\Base\\inc\\LogAdapter"...
0x1400170d6  mov     [rbp+var_20], 0D7h
0x1400170de  mov     [rbp+var_30], rcx
0x1400170e2  lea     rax, aMFlushsinkHr; "m_FlushSink.Hr()"
0x1400170e9  lea     rcx, aLogadapterLogg_0; "LogAdapter::Logger::LogNumObjects"
0x1400170f0  mov     [rbp+var_18], rax
0x1400170f4  mov     [rbp+var_28], rcx
0x1400170f8  lea     rdx, [rbp+var_30]
0x1400170fc  lea     rcx, [rbp+var_10]
0x140017100  call    ?OriginateHResult@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateHResult(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x140017105  jmp     loc_140017057
0x14001710a  xor     ebx, ebx
0x14001710c  lea     rcx, [rbp+var_60]; this
0x140017110  call    ??1CriticalSectionLockGrant@Rtl@Windows@@QEAA@XZ; Windows::Rtl::CriticalSectionLockGrant::~CriticalSectionLockGrant(void)
0x140017115  mov     eax, ebx
0x140017117  mov     rcx, [rbp+var_8]
0x14001711b  xor     rcx, rsp; StackCookie
0x14001711e  call    __security_check_cookie
0x140017123  lea     r11, [rsp+80h+var_s0]
0x14001712b  mov     rbx, [r11+28h]
0x14001712f  mov     rsi, [r11+30h]
0x140017133  mov     rsp, r11
0x140017136  pop     r14
0x140017138  pop     rdi
0x140017139  pop     rbp
0x14001713a  retn
```
