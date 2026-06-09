# LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)

- ea: `0x140016a40`
- end: `0x140016bf5`
- name: `??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z`
- size: `437`
- prototype: `__int64 __fastcall(__int64, char, int, struct Windows::Rtl::IRtlFormattedOutputStream *)`
- caller_count: `69`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x14001741c`
- `0x140017448`
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
- `0x14001c6e8`
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
- `0x140016a40`
- `0x1400183c0`
- `0x140026e04`
- `0x14002b010`

## pseudocode

```c
__int64 __fastcall LogAdapter::Logger::LogNumObjects<>(
        __int64 a1,
        char a2,
        int a3,
        struct Windows::Rtl::IRtlFormattedOutputStream *a4)
{
  int v8; // eax
  int v9; // eax
  unsigned int v10; // ebx
  __int64 v11; // r8
  const struct Windows::WCP::Rtl::_RTL_TRACING_PARAMETER *v13; // [rsp+20h] [rbp-60h] BYREF
  char v14; // [rsp+28h] [rbp-58h]
  _QWORD v15[4]; // [rsp+30h] [rbp-50h] BYREF
  _QWORD v16[4]; // [rsp+50h] [rbp-30h] BYREF
  int v17; // [rsp+70h] [rbp-10h] BYREF

  v17 = 0;
  v13 = (const struct Windows::WCP::Rtl::_RTL_TRACING_PARAMETER *)(a1 + 4160);
  v14 = 0;
  v8 = Windows::Rtl::CriticalSectionLockGrant::Acquire((Windows::Rtl::CriticalSectionLockGrant *)&v13);
  if ( v8 >= 0 )
  {
    v9 = (**(__int64 (__fastcall ***)(__int64))a1)(a1);
    if ( v9 >= 0 )
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
        Windows::WCP::Rtl::RtlFormatIntoStreamFromParameterList(*(Windows::WCP::Rtl **)(a1 + 16), a4, 0, 0, v13);
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 16) + 496LL))(*(_QWORD *)(a1 + 16));
        v11 = *(unsigned int *)(a1 + 4156);
        if ( (int)v11 < 0 )
        {
          v16[2] = 215;
          v16[0] = "OneCore\\Private\\Base\\inc\\LogAdapter.h";
          v16[3] = "m_FlushSink.Hr()";
          v16[1] = "LogAdapter::Logger::LogNumObjects";
          v9 = Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateHResult(
                 &v17,
                 v16,
                 v11);
          goto LABEL_4;
        }
      }
      else
      {
        Windows::WCP::Rtl::RtlFormatIntoStreamFromParameterList(*(Windows::WCP::Rtl **)(a1 + 8), a4, 0, 0, v13);
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 8) + 496LL))(*(_QWORD *)(a1 + 8));
      }
      v10 = 0;
      goto LABEL_12;
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
LABEL_4:
  v10 = v9;
LABEL_12:
  Windows::Rtl::CriticalSectionLockGrant::~CriticalSectionLockGrant((Windows::Rtl::CriticalSectionLockGrant *)&v13);
  return v10;
}

```

## disassembly

```asm
0x140016a40  mov     [rsp-18h+arg_8], rbx
0x140016a45  mov     [rsp-18h+arg_10], rsi
0x140016a4a  push    rbp
0x140016a4b  push    rdi
0x140016a4c  push    r14
0x140016a4e  mov     rbp, rsp
0x140016a51  sub     rsp, 80h
0x140016a58  mov     rax, cs:__security_cookie
0x140016a5f  xor     rax, rsp
0x140016a62  mov     [rbp+var_8], rax
0x140016a66  lea     rax, [rcx+1040h]
0x140016a6d  mov     [rbp+var_10], 0
0x140016a74  mov     rdi, rcx
0x140016a77  mov     [rbp+var_60], rax
0x140016a7b  lea     rcx, [rbp+var_60]; this
0x140016a7f  mov     [rbp+var_58], 0
0x140016a83  mov     r14, r9
0x140016a86  mov     esi, r8d
0x140016a89  mov     bl, dl
0x140016a8b  call    ?Acquire@CriticalSectionLockGrant@Rtl@Windows@@QEAAJXZ; Windows::Rtl::CriticalSectionLockGrant::Acquire(void)
0x140016a90  test    eax, eax
0x140016a92  jns     short loc_140016ACF
0x140016a94  lea     rcx, aOnecorePrivate; "OneCore\\Private\\Base\\inc\\LogAdapter"...
0x140016a9b  mov     [rbp+var_40], 0C3h
0x140016aa3  mov     [rbp+var_50], rcx
0x140016aa7  lea     rdx, [rbp+var_50]
0x140016aab  lea     rcx, aLogadapterLogg_0; "LogAdapter::Logger::LogNumObjects"
0x140016ab2  mov     r8d, eax
0x140016ab5  mov     [rbp+var_48], rcx
0x140016ab9  lea     rcx, aQueuelockAcqui; "QueueLock.Acquire()"
0x140016ac0  mov     [rbp+var_38], rcx
0x140016ac4  lea     rcx, [rbp+var_10]
0x140016ac8  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x140016acd  jmp     short loc_140016AE1
0x140016acf  mov     rax, [rdi]
0x140016ad2  mov     rcx, rdi
0x140016ad5  mov     rax, [rax]
0x140016ad8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140016add  test    eax, eax
0x140016adf  jns     short loc_140016AE8
0x140016ae1  mov     ebx, eax
0x140016ae3  jmp     loc_140016BC6
0x140016ae8  test    bl, bl
0x140016aea  jz      loc_140016B9F
0x140016af0  mov     [rdi+1038h], esi
0x140016af6  cmp     qword ptr [rdi+20h], 0
0x140016afb  jbe     short loc_140016B33
0x140016afd  mov     rcx, [rdi+8]
0x140016b01  mov     rax, [rcx]
0x140016b04  mov     rax, [rax+1F0h]
0x140016b0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140016b10  mov     rcx, [rdi+10h]
0x140016b14  lea     rdx, [rdi+28h]
0x140016b18  mov     rax, [rcx]
0x140016b1b  mov     rax, [rax+0E0h]
0x140016b22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140016b27  mov     byte ptr [rdi+28h], 0
0x140016b2b  mov     qword ptr [rdi+20h], 0
0x140016b33  mov     rcx, [rdi+10h]; this
0x140016b37  xor     r9d, r9d; unsigned __int64
0x140016b3a  xor     r8d, r8d; char *
0x140016b3d  mov     rdx, r14; struct Windows::Rtl::IRtlFormattedOutputStream *
0x140016b40  call    ?RtlFormatIntoStreamFromParameterList@Rtl@WCP@Windows@@YAXPEAUIRtlFormattedOutputStream@13@QEBD_KQEBU_RTL_TRACING_PARAMETER@123@@Z; Windows::WCP::Rtl::RtlFormatIntoStreamFromParameterList(Windows::Rtl::IRtlFormattedOutputStream *,char const * const,unsigned __int64,Windows::WCP::Rtl::_RTL_TRACING_PARAMETER const * const)
0x140016b45  mov     rcx, [rdi+10h]
0x140016b49  mov     rax, [rcx]
0x140016b4c  mov     rax, [rax+1F0h]
0x140016b53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140016b58  mov     r8d, [rdi+103Ch]
0x140016b5f  test    r8d, r8d
0x140016b62  jns     short loc_140016BC4
0x140016b64  lea     rcx, aOnecorePrivate; "OneCore\\Private\\Base\\inc\\LogAdapter"...
0x140016b6b  mov     [rbp+var_20], 0D7h
0x140016b73  mov     [rbp+var_30], rcx
0x140016b77  lea     rax, aMFlushsinkHr; "m_FlushSink.Hr()"
0x140016b7e  lea     rcx, aLogadapterLogg_0; "LogAdapter::Logger::LogNumObjects"
0x140016b85  mov     [rbp+var_18], rax
0x140016b89  mov     [rbp+var_28], rcx
0x140016b8d  lea     rdx, [rbp+var_30]
0x140016b91  lea     rcx, [rbp+var_10]
0x140016b95  call    ?OriginateHResult@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateHResult(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x140016b9a  jmp     loc_140016AE1
0x140016b9f  mov     rcx, [rdi+8]; this
0x140016ba3  xor     r9d, r9d; unsigned __int64
0x140016ba6  xor     r8d, r8d; char *
0x140016ba9  mov     rdx, r14; struct Windows::Rtl::IRtlFormattedOutputStream *
0x140016bac  call    ?RtlFormatIntoStreamFromParameterList@Rtl@WCP@Windows@@YAXPEAUIRtlFormattedOutputStream@13@QEBD_KQEBU_RTL_TRACING_PARAMETER@123@@Z; Windows::WCP::Rtl::RtlFormatIntoStreamFromParameterList(Windows::Rtl::IRtlFormattedOutputStream *,char const * const,unsigned __int64,Windows::WCP::Rtl::_RTL_TRACING_PARAMETER const * const)
0x140016bb1  mov     rcx, [rdi+8]
0x140016bb5  mov     rax, [rcx]
0x140016bb8  mov     rax, [rax+1F0h]
0x140016bbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140016bc4  xor     ebx, ebx
0x140016bc6  lea     rcx, [rbp+var_60]; this
0x140016bca  call    ??1CriticalSectionLockGrant@Rtl@Windows@@QEAA@XZ; Windows::Rtl::CriticalSectionLockGrant::~CriticalSectionLockGrant(void)
0x140016bcf  mov     eax, ebx
0x140016bd1  mov     rcx, [rbp+var_8]
0x140016bd5  xor     rcx, rsp; StackCookie
0x140016bd8  call    __security_check_cookie
0x140016bdd  lea     r11, [rsp+80h+var_s0]
0x140016be5  mov     rbx, [r11+28h]
0x140016be9  mov     rsi, [r11+30h]
0x140016bed  mov     rsp, r11
0x140016bf0  pop     r14
0x140016bf2  pop     rdi
0x140016bf3  pop     rbp
0x140016bf4  retn
```
