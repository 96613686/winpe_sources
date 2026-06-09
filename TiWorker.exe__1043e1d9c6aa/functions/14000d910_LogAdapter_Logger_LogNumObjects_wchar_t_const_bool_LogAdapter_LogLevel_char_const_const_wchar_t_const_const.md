# LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)

- ea: `0x14000d910`
- end: `0x14000dac0`
- name: `??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z`
- size: `432`
- prototype: `__int64 __fastcall(__int64, char, int, __int64, __int64)`
- caller_count: `20`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x14000e0d4`
- `0x14000e728`
- `0x14000ed6c`
- `0x14000f5b0`
- `0x140010fe0`
- `0x14001121c`
- `0x140011550`
- `0x140011a30`
- `0x140011ee8`
- `0x1400123a4`
- `0x1400129b8`
- `0x140012c58`
- `0x14001344c`
- `0x140013a18`
- `0x140013d48`
- `0x1400144ec`
- `0x1400146f4`
- `0x140014d18`
- `0x140015108`
- `0x140015228`

## callees

- `0x140002310`
- `0x140006204`
- `0x14000641c`
- `0x140006b54`
- `0x140009784`
- `0x14000d910`
- `0x14000df6c`
- `0x14002b010`

## pseudocode

```c
__int64 __fastcall LogAdapter::Logger::LogNumObjects<wchar_t const *>(
        __int64 a1,
        char a2,
        int a3,
        __int64 a4,
        __int64 a5)
{
  int v9; // eax
  int v10; // eax
  unsigned int v11; // ebx
  __int64 v12; // r8
  __int64 v14; // [rsp+20h] [rbp-60h] BYREF
  char v15; // [rsp+28h] [rbp-58h]
  _QWORD v16[4]; // [rsp+30h] [rbp-50h] BYREF
  _QWORD v17[4]; // [rsp+50h] [rbp-30h] BYREF
  int v18; // [rsp+70h] [rbp-10h] BYREF

  v14 = a1 + 4160;
  v18 = 0;
  v15 = 0;
  v9 = Windows::Rtl::CriticalSectionLockGrant::Acquire((Windows::Rtl::CriticalSectionLockGrant *)&v14);
  if ( v9 >= 0 )
  {
    v10 = (**(__int64 (__fastcall ***)(__int64))a1)(a1);
    if ( v10 >= 0 )
    {
      if ( a2 )
      {
        *(_DWORD *)(a1 + 4152) = a3;
        if ( *(_QWORD *)(a1 + 32) )
        {
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 8) + 496LL))(*(_QWORD *)(a1 + 8));
          (*(void (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(a1 + 16) + 224LL))(*(_QWORD *)(a1 + 16), a1 + 40);
          *(_BYTE *)(a1 + 40) = 0;
          *(_QWORD *)(a1 + 32) = 0;
        }
        Windows::Tracing::RtlFormatIntoStream<wchar_t *>(*(_QWORD *)(a1 + 16), a4, a5);
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 16) + 496LL))(*(_QWORD *)(a1 + 16));
        v12 = *(unsigned int *)(a1 + 4156);
        if ( (int)v12 < 0 )
        {
          v17[2] = 215;
          v17[0] = "OneCore\\Private\\Base\\inc\\LogAdapter.h";
          v17[3] = "m_FlushSink.Hr()";
          v17[1] = "LogAdapter::Logger::LogNumObjects";
          v10 = Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateHResult(
                  &v18,
                  v17,
                  v12);
          goto LABEL_4;
        }
      }
      else
      {
        Windows::Tracing::RtlFormatIntoStream<wchar_t *>(*(_QWORD *)(a1 + 8), a4, a5);
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 8) + 496LL))(*(_QWORD *)(a1 + 8));
      }
      v11 = 0;
      goto LABEL_12;
    }
  }
  else
  {
    v16[2] = 195;
    v16[0] = "OneCore\\Private\\Base\\inc\\LogAdapter.h";
    v16[1] = "LogAdapter::Logger::LogNumObjects";
    v16[3] = "QueueLock.Acquire()";
    v10 = Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateNtStatus(
            &v18,
            v16,
            (unsigned int)v9);
  }
LABEL_4:
  v11 = v10;
LABEL_12:
  Windows::Rtl::CriticalSectionLockGrant::~CriticalSectionLockGrant((Windows::Rtl::CriticalSectionLockGrant *)&v14);
  return v11;
}

```

## disassembly

```asm
0x14000d910  mov     [rsp-28h+arg_8], rbx
0x14000d915  push    rbp
0x14000d916  push    rsi
0x14000d917  push    rdi
0x14000d918  push    r14
0x14000d91a  push    r15
0x14000d91c  mov     rbp, rsp
0x14000d91f  sub     rsp, 80h
0x14000d926  mov     rax, cs:__security_cookie
0x14000d92d  xor     rax, rsp
0x14000d930  mov     [rbp+var_8], rax
0x14000d934  mov     r15, [rbp+arg_20]
0x14000d938  lea     rax, [rcx+1040h]
0x14000d93f  mov     rdi, rcx
0x14000d942  mov     [rbp+var_60], rax
0x14000d946  lea     rcx, [rbp+var_60]; this
0x14000d94a  mov     [rbp+var_10], 0
0x14000d951  mov     r14, r9
0x14000d954  mov     [rbp+var_58], 0
0x14000d958  mov     esi, r8d
0x14000d95b  mov     bl, dl
0x14000d95d  call    ?Acquire@CriticalSectionLockGrant@Rtl@Windows@@QEAAJXZ; Windows::Rtl::CriticalSectionLockGrant::Acquire(void)
0x14000d962  test    eax, eax
0x14000d964  jns     short loc_14000D9A1
0x14000d966  lea     rcx, aOnecorePrivate; "OneCore\\Private\\Base\\inc\\LogAdapter"...
0x14000d96d  mov     [rbp+var_40], 0C3h
0x14000d975  mov     [rbp+var_50], rcx
0x14000d979  lea     rdx, [rbp+var_50]
0x14000d97d  lea     rcx, aLogadapterLogg_0; "LogAdapter::Logger::LogNumObjects"
0x14000d984  mov     r8d, eax
0x14000d987  mov     [rbp+var_48], rcx
0x14000d98b  lea     rcx, aQueuelockAcqui; "QueueLock.Acquire()"
0x14000d992  mov     [rbp+var_38], rcx
0x14000d996  lea     rcx, [rbp+var_10]
0x14000d99a  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x14000d99f  jmp     short loc_14000D9B3
0x14000d9a1  mov     rax, [rdi]
0x14000d9a4  mov     rcx, rdi
0x14000d9a7  mov     rax, [rax]
0x14000d9aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d9af  test    eax, eax
0x14000d9b1  jns     short loc_14000D9BA
0x14000d9b3  mov     ebx, eax
0x14000d9b5  jmp     loc_14000DA92
0x14000d9ba  test    bl, bl
0x14000d9bc  jz      loc_14000DA6E
0x14000d9c2  mov     [rdi+1038h], esi
0x14000d9c8  cmp     qword ptr [rdi+20h], 0
0x14000d9cd  jbe     short loc_14000DA05
0x14000d9cf  mov     rcx, [rdi+8]
0x14000d9d3  mov     rax, [rcx]
0x14000d9d6  mov     rax, [rax+1F0h]
0x14000d9dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d9e2  mov     rcx, [rdi+10h]
0x14000d9e6  lea     rdx, [rdi+28h]
0x14000d9ea  mov     rax, [rcx]
0x14000d9ed  mov     rax, [rax+0E0h]
0x14000d9f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d9f9  mov     byte ptr [rdi+28h], 0
0x14000d9fd  mov     qword ptr [rdi+20h], 0
0x14000da05  mov     rcx, [rdi+10h]
0x14000da09  mov     r8, r15
0x14000da0c  mov     rdx, r14
0x14000da0f  call    ??$RtlFormatIntoStream@PEA_W@Tracing@Windows@@YAXPEAUIRtlFormattedOutputStream@Rtl@1@QEBDAEBQEA_W@Z; Windows::Tracing::RtlFormatIntoStream<wchar_t *>(Windows::Rtl::IRtlFormattedOutputStream *,char const * const,wchar_t * const &)
0x14000da14  mov     rcx, [rdi+10h]
0x14000da18  mov     rax, [rcx]
0x14000da1b  mov     rax, [rax+1F0h]
0x14000da22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000da27  mov     r8d, [rdi+103Ch]
0x14000da2e  test    r8d, r8d
0x14000da31  jns     short loc_14000DA90
0x14000da33  lea     rcx, aOnecorePrivate; "OneCore\\Private\\Base\\inc\\LogAdapter"...
0x14000da3a  mov     [rbp+var_20], 0D7h
0x14000da42  mov     [rbp+var_30], rcx
0x14000da46  lea     rax, aMFlushsinkHr; "m_FlushSink.Hr()"
0x14000da4d  lea     rcx, aLogadapterLogg_0; "LogAdapter::Logger::LogNumObjects"
0x14000da54  mov     [rbp+var_18], rax
0x14000da58  mov     [rbp+var_28], rcx
0x14000da5c  lea     rdx, [rbp+var_30]
0x14000da60  lea     rcx, [rbp+var_10]
0x14000da64  call    ?OriginateHResult@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateHResult(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x14000da69  jmp     loc_14000D9B3
0x14000da6e  mov     rcx, [rdi+8]
0x14000da72  mov     r8, r15
0x14000da75  mov     rdx, r14
0x14000da78  call    ??$RtlFormatIntoStream@PEA_W@Tracing@Windows@@YAXPEAUIRtlFormattedOutputStream@Rtl@1@QEBDAEBQEA_W@Z; Windows::Tracing::RtlFormatIntoStream<wchar_t *>(Windows::Rtl::IRtlFormattedOutputStream *,char const * const,wchar_t * const &)
0x14000da7d  mov     rcx, [rdi+8]
0x14000da81  mov     rax, [rcx]
0x14000da84  mov     rax, [rax+1F0h]
0x14000da8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000da90  xor     ebx, ebx
0x14000da92  lea     rcx, [rbp+var_60]; this
0x14000da96  call    ??1CriticalSectionLockGrant@Rtl@Windows@@QEAA@XZ; Windows::Rtl::CriticalSectionLockGrant::~CriticalSectionLockGrant(void)
0x14000da9b  mov     eax, ebx
0x14000da9d  mov     rcx, [rbp+var_8]
0x14000daa1  xor     rcx, rsp; StackCookie
0x14000daa4  call    __security_check_cookie
0x14000daa9  mov     rbx, [rsp+80h+arg_8]
0x14000dab1  add     rsp, 80h
0x14000dab8  pop     r15
0x14000daba  pop     r14
0x14000dabc  pop     rdi
0x14000dabd  pop     rsi
0x14000dabe  pop     rbp
0x14000dabf  retn
```
