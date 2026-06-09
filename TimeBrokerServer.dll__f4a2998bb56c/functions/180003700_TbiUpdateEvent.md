# _TbiUpdateEvent

- ea: `0x180003700`
- end: `0x1800037f4`
- name: `_TbiUpdateEvent`
- size: `244`
- prototype: `__int64 __fastcall(__int64, const unsigned __int16 *, const struct _GUID *, struct _TbiTimeEventCreationParameters *)`
- caller_count: `0`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000215c`
- `0x180003700`
- `0x180004000`
- `0x180004218`
- `0x1800042e8`
- `0x180004b70`
- `0x180005b30`
- `0x1800112d8`
- `0x180012dd0`

## pseudocode

```c
__int64 __fastcall TbiUpdateEvent(
        __int64 a1,
        const unsigned __int16 *a2,
        const struct _GUID *a3,
        struct _TbiTimeEventCreationParameters *a4)
{
  Broker::Win32Error *v7; // rbx
  Broker::TimeBroker *v8; // rdi
  Broker::ApplicationIdentity *AppId; // rax
  unsigned int v11; // [rsp+20h] [rbp-D8h]
  _BYTE v12[16]; // [rsp+28h] [rbp-D0h] BYREF
  Broker::BILayer::Failure *v13; // [rsp+38h] [rbp-C0h] BYREF
  Broker::Win32Error *v14[4]; // [rsp+40h] [rbp-B8h] BYREF
  _BYTE v15[24]; // [rsp+60h] [rbp-98h] BYREF
  _BYTE v16[32]; // [rsp+78h] [rbp-80h] BYREF
  _BYTE v17[40]; // [rsp+98h] [rbp-60h] BYREF

  v11 = 0;
  try
  {
    Broker::RpcClientToken::RpcClientToken((Broker::RpcClientToken *)v12);
    v7 = *(&Broker::TimeBroker::Instance + 1);
    if ( *(&Broker::TimeBroker::Instance + 1) )
    {
      _InterlockedIncrement((volatile signed __int32 *)*(&Broker::TimeBroker::Instance + 1) + 2);
      v7 = *(&Broker::TimeBroker::Instance + 1);
    }
    v8 = Broker::TimeBroker::Instance;
    v14[1] = Broker::TimeBroker::Instance;
    v14[2] = v7;
    AppId = Broker::RpcClientToken::GetAppId((__int64)v12, (Broker::ApplicationIdentity *)v15, a2);
    Broker::TimeBroker::UpdateEvent(v8, AppId, a3, a4);
    std::wstring::_Tidy_deallocate(v17);
    std::wstring::_Tidy_deallocate(v16);
    std::vector<unsigned char>::_Tidy(v15);
    if ( v7 )
      std::_Ref_count_base::_Decref(v7);
    Broker::RpcClientToken::~RpcClientToken((Broker::RpcClientToken *)v12);
  }
  catch ( std::bad_alloc )
  {
    return 14;
  }
  catch ( Broker::NotFound )
  {
    return 1168;
  }
  catch ( Broker::AccessDenied )
  {
    return 5;
  }
  catch ( Broker::BILayer::Failure *v13 )
  {
    return RtlNtStatusToDosError(*((_DWORD *)v13 + 8));
  }
  catch ( Broker::Win32Error *v14 )
  {
    return *((unsigned int *)v14[0] + 8);
  }
  catch ( ... )
  {
    return 1359;
  }
  return v11;
}

```

## disassembly

```asm
0x180003700  push    rbx
0x180003702  push    rsi
0x180003703  push    rdi
0x180003704  push    r14
0x180003706  push    r15
0x180003708  sub     rsp, 0D0h
0x18000370f  mov     rax, cs:__security_cookie
0x180003716  xor     rax, rsp
0x180003719  mov     [rsp+0F8h+var_38], rax
0x180003721  mov     r15, r9
0x180003724  mov     r14, r8
0x180003727  mov     rsi, rdx
0x18000372a  mov     [rsp+0F8h+var_D8], 0
0x180003732  lea     rcx, [rsp+0F8h+var_D0]; this
0x180003737  call    ??0RpcClientToken@Broker@@QEAA@XZ; Broker::RpcClientToken::RpcClientToken(void)
0x18000373c  nop
0x18000373d  mov     rbx, qword ptr cs:?Instance@TimeBroker@Broker@@0V?$shared_ptr@VTimeBroker@Broker@@@std@@A+8; std::shared_ptr<Broker::TimeBroker> Broker::TimeBroker::Instance
0x180003744  test    rbx, rbx
0x180003747  jz      short loc_180003754
0x180003749  lock inc dword ptr [rbx+8]
0x18000374d  mov     rbx, qword ptr cs:?Instance@TimeBroker@Broker@@0V?$shared_ptr@VTimeBroker@Broker@@@std@@A+8; std::shared_ptr<Broker::TimeBroker> Broker::TimeBroker::Instance
0x180003754  mov     rdi, qword ptr cs:?Instance@TimeBroker@Broker@@0V?$shared_ptr@VTimeBroker@Broker@@@std@@A; std::shared_ptr<Broker::TimeBroker> Broker::TimeBroker::Instance
0x18000375b  mov     [rsp+0F8h+var_B0], rdi
0x180003760  mov     [rsp+0F8h+var_A8], rbx
0x180003765  mov     r8, rsi
0x180003768  lea     rdx, [rsp+0F8h+var_98]
0x18000376d  lea     rcx, [rsp+0F8h+var_D0]
0x180003772  call    ?GetAppId@RpcClientToken@Broker@@QEAA?AUApplicationIdentity@2@PEBG_N@Z; Broker::RpcClientToken::GetAppId(ushort const *,bool)
0x180003777  nop
0x180003778  mov     r9, r15; struct _TbiTimeEventCreationParameters *
0x18000377b  mov     r8, r14; struct _GUID *
0x18000377e  mov     rdx, rax; struct Broker::ApplicationIdentity *
0x180003781  mov     rcx, rdi; this
0x180003784  call    ?UpdateEvent@TimeBroker@Broker@@QEAAXAEBUApplicationIdentity@2@AEBU_GUID@@AEAU_TbiTimeEventCreationParameters@@@Z; Broker::TimeBroker::UpdateEvent(Broker::ApplicationIdentity const &,_GUID const &,_TbiTimeEventCreationParameters &)
0x180003789  nop
0x18000378a  lea     rcx, [rsp+0F8h+var_60]
0x180003792  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180003797  lea     rcx, [rsp+0F8h+var_80]
0x18000379c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800037a1  lea     rcx, [rsp+0F8h+var_98]
0x1800037a6  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800037ab  nop
0x1800037ac  test    rbx, rbx
0x1800037af  jz      short loc_1800037BA
0x1800037b1  mov     rcx, rbx; this
0x1800037b4  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800037b9  nop
0x1800037ba  lea     rcx, [rsp+0F8h+var_D0]; this
0x1800037bf  call    ??1RpcClientToken@Broker@@QEAA@XZ; Broker::RpcClientToken::~RpcClientToken(void)
0x1800037c4  nop
0x1800037c5  jmp     short loc_1800037D1
0x1800037c7  jmp     short loc_1800037D1
0x1800037c9  jmp     short loc_1800037D1
0x1800037cb  jmp     short loc_1800037D1
0x1800037cd  jmp     short loc_1800037D1
0x1800037cf  jmp     short $+2
0x1800037d1  mov     eax, [rsp+0F8h+var_D8]
0x1800037d5  mov     rcx, [rsp+0F8h+var_38]
0x1800037dd  xor     rcx, rsp; StackCookie
0x1800037e0  call    __security_check_cookie
0x1800037e5  add     rsp, 0D0h
0x1800037ec  pop     r15
0x1800037ee  pop     r14
0x1800037f0  pop     rdi
0x1800037f1  pop     rsi
0x1800037f2  pop     rbx
0x1800037f3  retn
```
