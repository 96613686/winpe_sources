# LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)

- ea: `0x140008d38`
- end: `0x140008eed`
- name: `??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z`
- size: `437`
- prototype: `__int64 __fastcall(__int64, char, int, struct Windows::Rtl::IRtlFormattedOutputStream *)`
- caller_count: `47`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x140009084`
- `0x14000c8d0`
- `0x14000e034`
- `0x14000e05c`
- `0x14000e824`
- `0x14000ebe0`
- `0x14000ed6c`
- `0x14000f02c`
- `0x14000f5b0`
- `0x140010d90`
- `0x14001121c`
- `0x140011550`
- `0x140011a30`
- `0x140011d38`
- `0x140011ee8`
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
- `0x140024048`
- `0x140024efc`

## callees

- `0x140002310`
- `0x140006204`
- `0x14000641c`
- `0x140006b54`
- `0x140008d38`
- `0x140009784`
- `0x1400270d4`
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
0x140008d38  mov     [rsp-18h+arg_8], rbx
0x140008d3d  mov     [rsp-18h+arg_10], rsi
0x140008d42  push    rbp
0x140008d43  push    rdi
0x140008d44  push    r14
0x140008d46  mov     rbp, rsp
0x140008d49  sub     rsp, 80h
0x140008d50  mov     rax, cs:__security_cookie
0x140008d57  xor     rax, rsp
0x140008d5a  mov     [rbp+var_8], rax
0x140008d5e  lea     rax, [rcx+1040h]
0x140008d65  mov     [rbp+var_10], 0
0x140008d6c  mov     rdi, rcx
0x140008d6f  mov     [rbp+var_60], rax
0x140008d73  lea     rcx, [rbp+var_60]; this
0x140008d77  mov     [rbp+var_58], 0
0x140008d7b  mov     r14, r9
0x140008d7e  mov     esi, r8d
0x140008d81  mov     bl, dl
0x140008d83  call    ?Acquire@CriticalSectionLockGrant@Rtl@Windows@@QEAAJXZ; Windows::Rtl::CriticalSectionLockGrant::Acquire(void)
0x140008d88  test    eax, eax
0x140008d8a  jns     short loc_140008DC7
0x140008d8c  lea     rcx, aOnecorePrivate; "OneCore\\Private\\Base\\inc\\LogAdapter"...
0x140008d93  mov     [rbp+var_40], 0C3h
0x140008d9b  mov     [rbp+var_50], rcx
0x140008d9f  lea     rdx, [rbp+var_50]
0x140008da3  lea     rcx, aLogadapterLogg_0; "LogAdapter::Logger::LogNumObjects"
0x140008daa  mov     r8d, eax
0x140008dad  mov     [rbp+var_48], rcx
0x140008db1  lea     rcx, aQueuelockAcqui; "QueueLock.Acquire()"
0x140008db8  mov     [rbp+var_38], rcx
0x140008dbc  lea     rcx, [rbp+var_10]
0x140008dc0  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x140008dc5  jmp     short loc_140008DD9
0x140008dc7  mov     rax, [rdi]
0x140008dca  mov     rcx, rdi
0x140008dcd  mov     rax, [rax]
0x140008dd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008dd5  test    eax, eax
0x140008dd7  jns     short loc_140008DE0
0x140008dd9  mov     ebx, eax
0x140008ddb  jmp     loc_140008EBE
0x140008de0  test    bl, bl
0x140008de2  jz      loc_140008E97
0x140008de8  mov     [rdi+1038h], esi
0x140008dee  cmp     qword ptr [rdi+20h], 0
0x140008df3  jbe     short loc_140008E2B
0x140008df5  mov     rcx, [rdi+8]
0x140008df9  mov     rax, [rcx]
0x140008dfc  mov     rax, [rax+1F0h]
0x140008e03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008e08  mov     rcx, [rdi+10h]
0x140008e0c  lea     rdx, [rdi+28h]
0x140008e10  mov     rax, [rcx]
0x140008e13  mov     rax, [rax+0E0h]
0x140008e1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008e1f  mov     byte ptr [rdi+28h], 0
0x140008e23  mov     qword ptr [rdi+20h], 0
0x140008e2b  mov     rcx, [rdi+10h]; this
0x140008e2f  xor     r9d, r9d; unsigned __int64
0x140008e32  xor     r8d, r8d; char *
0x140008e35  mov     rdx, r14; struct Windows::Rtl::IRtlFormattedOutputStream *
0x140008e38  call    ?RtlFormatIntoStreamFromParameterList@Rtl@WCP@Windows@@YAXPEAUIRtlFormattedOutputStream@13@QEBD_KQEBU_RTL_TRACING_PARAMETER@123@@Z; Windows::WCP::Rtl::RtlFormatIntoStreamFromParameterList(Windows::Rtl::IRtlFormattedOutputStream *,char const * const,unsigned __int64,Windows::WCP::Rtl::_RTL_TRACING_PARAMETER const * const)
0x140008e3d  mov     rcx, [rdi+10h]
0x140008e41  mov     rax, [rcx]
0x140008e44  mov     rax, [rax+1F0h]
0x140008e4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008e50  mov     r8d, [rdi+103Ch]
0x140008e57  test    r8d, r8d
0x140008e5a  jns     short loc_140008EBC
0x140008e5c  lea     rcx, aOnecorePrivate; "OneCore\\Private\\Base\\inc\\LogAdapter"...
0x140008e63  mov     [rbp+var_20], 0D7h
0x140008e6b  mov     [rbp+var_30], rcx
0x140008e6f  lea     rax, aMFlushsinkHr; "m_FlushSink.Hr()"
0x140008e76  lea     rcx, aLogadapterLogg_0; "LogAdapter::Logger::LogNumObjects"
0x140008e7d  mov     [rbp+var_18], rax
0x140008e81  mov     [rbp+var_28], rcx
0x140008e85  lea     rdx, [rbp+var_30]
0x140008e89  lea     rcx, [rbp+var_10]
0x140008e8d  call    ?OriginateHResult@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateHResult(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x140008e92  jmp     loc_140008DD9
0x140008e97  mov     rcx, [rdi+8]; this
0x140008e9b  xor     r9d, r9d; unsigned __int64
0x140008e9e  xor     r8d, r8d; char *
0x140008ea1  mov     rdx, r14; struct Windows::Rtl::IRtlFormattedOutputStream *
0x140008ea4  call    ?RtlFormatIntoStreamFromParameterList@Rtl@WCP@Windows@@YAXPEAUIRtlFormattedOutputStream@13@QEBD_KQEBU_RTL_TRACING_PARAMETER@123@@Z; Windows::WCP::Rtl::RtlFormatIntoStreamFromParameterList(Windows::Rtl::IRtlFormattedOutputStream *,char const * const,unsigned __int64,Windows::WCP::Rtl::_RTL_TRACING_PARAMETER const * const)
0x140008ea9  mov     rcx, [rdi+8]
0x140008ead  mov     rax, [rcx]
0x140008eb0  mov     rax, [rax+1F0h]
0x140008eb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008ebc  xor     ebx, ebx
0x140008ebe  lea     rcx, [rbp+var_60]; this
0x140008ec2  call    ??1CriticalSectionLockGrant@Rtl@Windows@@QEAA@XZ; Windows::Rtl::CriticalSectionLockGrant::~CriticalSectionLockGrant(void)
0x140008ec7  mov     eax, ebx
0x140008ec9  mov     rcx, [rbp+var_8]
0x140008ecd  xor     rcx, rsp; StackCookie
0x140008ed0  call    __security_check_cookie
0x140008ed5  lea     r11, [rsp+80h+var_s0]
0x140008edd  mov     rbx, [r11+28h]
0x140008ee1  mov     rsi, [r11+30h]
0x140008ee5  mov     rsp, r11
0x140008ee8  pop     r14
0x140008eea  pop     rdi
0x140008eeb  pop     rbp
0x140008eec  retn
```
