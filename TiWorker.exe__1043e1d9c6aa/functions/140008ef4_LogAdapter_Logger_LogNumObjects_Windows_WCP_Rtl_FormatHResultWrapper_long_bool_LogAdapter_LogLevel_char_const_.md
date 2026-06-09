# LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)

- ea: `0x140008ef4`
- end: `0x14000907b`
- name: `??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z`
- size: `391`
- prototype: `__int64 __fastcall(__int64, __int64, int, __int64, __int64)`
- caller_count: `49`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x140009364`
- `0x1400094f4`
- `0x14000c8d0`
- `0x14000e05c`
- `0x14000e0d4`
- `0x14000e728`
- `0x14000e824`
- `0x14000ebe0`
- `0x14000ed6c`
- `0x14000f02c`
- `0x14000f5b0`
- `0x140010fe0`
- `0x14001121c`
- `0x140011550`
- `0x140011a30`
- `0x140011ee8`
- `0x140012328`
- `0x1400123a4`
- `0x140012678`
- `0x1400129b8`
- `0x140012c58`
- `0x14001344c`
- `0x140013a18`
- `0x140013d48`
- `0x1400144ec`
- `0x1400146f4`
- `0x1400149ec`
- `0x140014d18`
- `0x140014ef0`
- `0x140015108`
- `0x140015228`
- `0x140016bf8`
- `0x140016d8c`
- `0x140017004`
- `0x14001726c`
- `0x140017464`
- `0x1400177d8`
- `0x140017a88`
- `0x140017c00`
- `0x140017ec8`
- `0x140018090`
- `0x140018298`
- `0x140018468`
- `0x140018740`
- `0x14001887c`
- `0x1400189c8`
- `0x140023db0`
- `0x140023e70`
- `0x140024efc`

## callees

- `0x140002310`
- `0x140006204`
- `0x14000641c`
- `0x140006b54`
- `0x140008ef4`
- `0x1400090a0`
- `0x140009784`
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
0x140008ef4  mov     [rsp-18h+arg_8], rbx
0x140008ef9  mov     [rsp-18h+arg_10], rsi
0x140008efe  push    rbp
0x140008eff  push    rdi
0x140008f00  push    r14
0x140008f02  mov     rbp, rsp
0x140008f05  sub     rsp, 80h
0x140008f0c  mov     rax, cs:__security_cookie
0x140008f13  xor     rax, rsp
0x140008f16  mov     [rbp+var_8], rax
0x140008f1a  mov     r14, [rbp+arg_20]
0x140008f1e  lea     rax, [rcx+1040h]
0x140008f25  mov     rdi, rcx
0x140008f28  mov     [rbp+var_60], rax
0x140008f2c  lea     rcx, [rbp+var_60]; this
0x140008f30  mov     [rbp+var_10], 0
0x140008f37  mov     rsi, r9
0x140008f3a  mov     [rbp+var_58], 0
0x140008f3e  mov     ebx, r8d
0x140008f41  call    ?Acquire@CriticalSectionLockGrant@Rtl@Windows@@QEAAJXZ; Windows::Rtl::CriticalSectionLockGrant::Acquire(void)
0x140008f46  test    eax, eax
0x140008f48  jns     short loc_140008F85
0x140008f4a  lea     rcx, aOnecorePrivate; "OneCore\\Private\\Base\\inc\\LogAdapter"...
0x140008f51  mov     [rbp+var_40], 0C3h
0x140008f59  mov     [rbp+var_50], rcx
0x140008f5d  lea     rdx, [rbp+var_50]
0x140008f61  lea     rcx, aLogadapterLogg_0; "LogAdapter::Logger::LogNumObjects"
0x140008f68  mov     r8d, eax
0x140008f6b  mov     [rbp+var_48], rcx
0x140008f6f  lea     rcx, aQueuelockAcqui; "QueueLock.Acquire()"
0x140008f76  mov     [rbp+var_38], rcx
0x140008f7a  lea     rcx, [rbp+var_10]
0x140008f7e  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x140008f83  jmp     short loc_140008F97
0x140008f85  mov     rax, [rdi]
0x140008f88  mov     rcx, rdi
0x140008f8b  mov     rax, [rax]
0x140008f8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008f93  test    eax, eax
0x140008f95  jns     short loc_140008F9E
0x140008f97  mov     ebx, eax
0x140008f99  jmp     loc_14000904C
0x140008f9e  mov     [rdi+1038h], ebx
0x140008fa4  cmp     qword ptr [rdi+20h], 0
0x140008fa9  jbe     short loc_140008FE1
0x140008fab  mov     rcx, [rdi+8]
0x140008faf  mov     rax, [rcx]
0x140008fb2  mov     rax, [rax+1F0h]
0x140008fb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008fbe  mov     rcx, [rdi+10h]
0x140008fc2  lea     rdx, [rdi+28h]
0x140008fc6  mov     rax, [rcx]
0x140008fc9  mov     rax, [rax+0E0h]
0x140008fd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008fd5  mov     byte ptr [rdi+28h], 0
0x140008fd9  mov     qword ptr [rdi+20h], 0
0x140008fe1  mov     rcx, [rdi+10h]
0x140008fe5  mov     r8, r14
0x140008fe8  mov     rdx, rsi
0x140008feb  call    ??$RtlFormatIntoStream@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Tracing@Windows@@YAXPEAUIRtlFormattedOutputStream@Rtl@1@QEBDAEBU?$FormatHResultWrapper@J@3WCP@1@@Z; Windows::Tracing::RtlFormatIntoStream<Windows::WCP::Rtl::FormatHResultWrapper<long>>(Windows::Rtl::IRtlFormattedOutputStream *,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140008ff0  mov     rcx, [rdi+10h]
0x140008ff4  mov     rax, [rcx]
0x140008ff7  mov     rax, [rax+1F0h]
0x140008ffe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009003  mov     r8d, [rdi+103Ch]
0x14000900a  test    r8d, r8d
0x14000900d  jns     short loc_14000904A
0x14000900f  lea     rcx, aOnecorePrivate; "OneCore\\Private\\Base\\inc\\LogAdapter"...
0x140009016  mov     [rbp+var_20], 0D7h
0x14000901e  mov     [rbp+var_30], rcx
0x140009022  lea     rax, aMFlushsinkHr; "m_FlushSink.Hr()"
0x140009029  lea     rcx, aLogadapterLogg_0; "LogAdapter::Logger::LogNumObjects"
0x140009030  mov     [rbp+var_18], rax
0x140009034  mov     [rbp+var_28], rcx
0x140009038  lea     rdx, [rbp+var_30]
0x14000903c  lea     rcx, [rbp+var_10]
0x140009040  call    ?OriginateHResult@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateHResult(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x140009045  jmp     loc_140008F97
0x14000904a  xor     ebx, ebx
0x14000904c  lea     rcx, [rbp+var_60]; this
0x140009050  call    ??1CriticalSectionLockGrant@Rtl@Windows@@QEAA@XZ; Windows::Rtl::CriticalSectionLockGrant::~CriticalSectionLockGrant(void)
0x140009055  mov     eax, ebx
0x140009057  mov     rcx, [rbp+var_8]
0x14000905b  xor     rcx, rsp; StackCookie
0x14000905e  call    __security_check_cookie
0x140009063  lea     r11, [rsp+80h+var_s0]
0x14000906b  mov     rbx, [r11+28h]
0x14000906f  mov     rsi, [r11+30h]
0x140009073  mov     rsp, r11
0x140009076  pop     r14
0x140009078  pop     rdi
0x140009079  pop     rbp
0x14000907a  retn
```
