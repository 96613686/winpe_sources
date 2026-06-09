# Broker::BrokerBase::InitializeBrokerBI(_BI_READY_BROADCAST_INFO *)

- ea: `0x18000c4c0`
- end: `0x18000c8c1`
- name: `?InitializeBrokerBI@BrokerBase@Broker@@QEAAXPEAU_BI_READY_BROADCAST_INFO@@@Z`
- size: `1025`
- prototype: `void __fastcall(Broker::BrokerBase *__hidden this, struct _BI_READY_BROADCAST_INFO *)`
- caller_count: `1`
- callee_count: `31`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000c420`

## callees

- `0x180004ae0`
- `0x180004d70`
- `0x180004e38`
- `0x180005b50`
- `0x18000c4c0`
- `0x18000c970`
- `0x18000ccbc`
- `0x18000cdac`
- `0x18000ce2c`
- `0x18000ceac`
- `0x18000cf2c`
- `0x18000d060`
- `0x18000d2a8`
- `0x18000d610`
- `0x18000d690`
- `0x18000d6e4`
- `0x18000d700`
- `0x18000dab0`
- `0x18000ed50`
- `0x180011cd4`
- `0x180013bf0`
- `0x180013c70`
- `0x180013cf0`
- `0x180013d70`
- `0x180013df0`
- `0x180013e70`
- `0x180013ef0`
- `0x180014e54`
- `0x180015af0`
- `0x180015b14`
- `0x18001e010`

## import_xrefs

- `ntdll!RtlUnsubscribeWnfStateChangeNotification` at `0x18000c85f`
- `ntdll!RtlUnsubscribeWnfStateChangeNotification` at `0x18000c85f`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000c523`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000c523`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000c753`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18000c753`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c529`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c529`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall Broker::BrokerBase::InitializeBrokerBI(Broker::BrokerBase *this, struct _BI_READY_BROADCAST_INFO *a2)
{
  __int64 v4; // rdi
  _DWORD *v5; // rsi
  __int64 v6; // rax
  std::_Ref_count_base *v7; // rcx
  unsigned int *v8; // r9
  unsigned __int64 *i; // rbx
  void *v10; // rdi
  void (__fastcall *v11)(_QWORD, _QWORD, unsigned __int64, void *); // rax
  void (__fastcall *v12)(_QWORD, _QWORD, void *); // rax
  void (__fastcall *v13)(_QWORD, _QWORD, unsigned __int64, void *); // rax
  unsigned int v14[2]; // [rsp+30h] [rbp-D0h] BYREF
  Broker::BILayer::NotificationChannel::TCallback *v15[2]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v16; // [rsp+48h] [rbp-B8h]
  Broker::BrokerBase *v17; // [rsp+50h] [rbp-B0h] BYREF
  char v18; // [rsp+58h] [rbp-A8h]
  DWORD CurrentThreadId; // [rsp+5Ch] [rbp-A4h]
  __int128 v20; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v21; // [rsp+70h] [rbp-90h]
  _BYTE v22[32]; // [rsp+80h] [rbp-80h] BYREF
  void *v23[2]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v24; // [rsp+B0h] [rbp-50h]
  __int128 v25; // [rsp+B8h] [rbp-48h]
  __int64 v26; // [rsp+C8h] [rbp-38h]
  __int64 v27; // [rsp+D0h] [rbp-30h]
  __int128 v28; // [rsp+D8h] [rbp-28h]
  __int64 v29; // [rsp+E8h] [rbp-18h]
  __int64 v30; // [rsp+F0h] [rbp-10h]

  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    WPP_SF__guid_(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      16,
      &WPP_4753d2a3665d3618996ed9ba7dd16268_Traceguids,
      *((_QWORD *)this + 1));
  v17 = this;
  RtlAcquireSRWLockExclusive(this);
  CurrentThreadId = GetCurrentThreadId();
  v18 = 1;
  if ( *((_BYTE *)this + 328) )
  {
    Broker::ScopedWriteLock::~ScopedWriteLock((Broker::ScopedWriteLock *)&v17);
  }
  else
  {
    *(_OWORD *)v15 = 0;
    v16 = 0;
    std::vector<Broker::BILayer::NotificationChannel::TCallback>::_Buy_nonzero(v15, 12);
    v15[1] = (Broker::BILayer::NotificationChannel::TCallback *)std::_Uninitialized_value_construct_n<std::allocator<Broker::BILayer::NotificationChannel::TCallback>>(v15[0]);
    *(_QWORD *)v14 = 0;
    std::_Tidy_guard<std::vector<Broker::BILayer::NotificationChannel::TCallback>>::~_Tidy_guard<std::vector<Broker::BILayer::NotificationChannel::TCallback>>(v14);
    *(_QWORD *)v14 = this;
    std::function_void___cdecl_unsigned_long_unsigned___int64_unsigned_long_void____::operator___lambda_e3a07c48498026817584494316665233__0_(
      (char *)v15[0] + 128,
      v14);
    *(_QWORD *)v14 = this;
    std::function_void___cdecl_unsigned_long_unsigned___int64_unsigned_long_void____::operator___lambda_c8fa6727609da0ae8cffc4d75127481e__0_(
      (char *)v15[0] + 384,
      v14);
    *(_QWORD *)v14 = this;
    std::function_void___cdecl_unsigned_long_unsigned_short_const___void____::operator___lambda_086782e45ce54d322c9db8eaf3c1da39__0_(
      (char *)v15[0] + 512,
      v14);
    *(_QWORD *)v14 = this;
    std::function_void___cdecl_unsigned_long_unsigned_short_const___void____::operator___lambda_da268ef20010ad47ca16aabf6a390cfd__0_(
      (char *)v15[0] + 768,
      v14);
    *(_QWORD *)v14 = this;
    std::function_void___cdecl_unsigned_long_unsigned_short_const___void____::operator___lambda_287a9fcb3b9e72b62c864a7e4405bdff__0_(
      (char *)v15[0] + 1024,
      v14);
    *(_QWORD *)v14 = this;
    std::function_void___cdecl_unsigned_long_unsigned_short_const___void____::operator___lambda_6c12a6f97ab60b36239838c33a9a7cbd__0_(
      (char *)v15[0] + 1280,
      v14);
    *(_QWORD *)v14 = this;
    std::function_void___cdecl_unsigned_long_unsigned_short_const___void____::operator___lambda_9b54c4c7fe1faac4d10b6394402ba495__0_(
      (char *)v15[0] + 1536,
      v14);
    *(_QWORD *)v14 = this;
    std::function_void___cdecl_unsigned_long_unsigned_short_const___void____::operator___lambda_ee6d6e0aea383208c4c6414728c393b4__0_(
      (char *)v15[0] + 1792,
      v14);
    *(_QWORD *)v14 = this;
    std::function_void___cdecl_unsigned_long_unsigned_short_const___void____::operator___lambda_8d4cd62a7e99ff058dc75304dec8128c__0_(
      (char *)v15[0] + 2048,
      v14);
    *(_QWORD *)v14 = this;
    std::function_void___cdecl__GUID_const____::operator___lambda_2a697d96b2de47a4269a727e77fc3b9f__0_(
      (char *)v15[0] + 2368,
      v14);
    *(_QWORD *)v14 = this;
    std::function_void___cdecl_unsigned_long_unsigned_short_const___void____::operator___lambda_4804ef5c84027b9de6878a69dd9befd8__0_(
      (char *)v15[0] + 2816,
      v14);
    v4 = *((_QWORD *)this + 1);
    v5 = operator new(0x50u);
    *(_QWORD *)v14 = v5;
    *(_OWORD *)v5 = 0;
    v5[2] = 1;
    v5[3] = 1;
    *(_QWORD *)v5 = &std::_Ref_count_obj2<Broker::BILayer::NotificationChannel>::`vftable';
    v6 = std::vector<Broker::BILayer::NotificationChannel::TCallback>::vector<Broker::BILayer::NotificationChannel::TCallback>(
           v22,
           v15);
    Broker::BILayer::NotificationChannel::NotificationChannel(v5 + 4, v4, a2, v6);
    *((_QWORD *)this + 38) = v5 + 4;
    v7 = (std::_Ref_count_base *)*((_QWORD *)this + 39);
    *((_QWORD *)this + 39) = v5;
    if ( v7 )
      std::_Ref_count_base::_Decref(v7);
    if ( !Broker::BrokerBase::BrokerIsRegistered(this) )
      Broker::BrokerBase::RestoreEventsFromBI(this);
    *((_BYTE *)this + 328) = 1;
    RtlReleaseSRWLockExclusive(this);
    v18 = 0;
    Broker::BILayer::EnumerateUserContexts(&v20);
    for ( i = (unsigned __int64 *)v20; i != *((unsigned __int64 **)&v20 + 1); ++i )
    {
      *(_OWORD *)v23 = 0;
      v24 = 0;
      v25 = 0;
      v26 = 0;
      v27 = 7;
      LOWORD(v25) = 0;
      v28 = 0;
      v29 = 0;
      v30 = 7;
      LOWORD(v28) = 0;
      v14[0] = 0;
      if ( Broker::BILayer::QueryUserContext(
             (Broker::BILayer *)*i,
             (unsigned __int64)v23,
             (struct Broker::ApplicationIdentity *)v14,
             v8) )
      {
        v10 = v23[0];
        v11 = (void (__fastcall *)(_QWORD, _QWORD, unsigned __int64, void *))*((_QWORD *)this + 20);
        if ( v11 )
          v11(*((_QWORD *)this + 1), v14[0], *i, v23[0]);
        Broker::BrokerBase::OnUserLogon((struct _RTL_SRWLOCK *)this, *i, v14[0], v10);
        v12 = (void (__fastcall *)(_QWORD, _QWORD, void *))*((_QWORD *)this + 2);
        if ( v12 )
          v12(*((_QWORD *)this + 1), v14[0], v10);
        v13 = (void (__fastcall *)(_QWORD, _QWORD, unsigned __int64, void *))*((_QWORD *)this + 21);
        if ( v13 )
          v13(*((_QWORD *)this + 1), v14[0], *i, v10);
      }
      Broker::ApplicationIdentity::~ApplicationIdentity((Broker::ApplicationIdentity *)v23);
    }
    if ( _InterlockedExchange64((volatile __int64 *)this + 40, 0) )
      RtlUnsubscribeWnfStateChangeNotification();
    if ( (_QWORD)v20 )
    {
      std::_Deallocate<16>(v20, (v21 - v20) & 0xFFFFFFFFFFFFFFF8uLL);
      v20 = 0;
      v21 = 0;
    }
    std::vector<Broker::BILayer::NotificationChannel::TCallback>::_Tidy(v15);
  }
}

```

## disassembly

```asm
0x18000c4c0  mov     [rsp-8+arg_10], rbx
0x18000c4c5  push    rbp
0x18000c4c6  push    rsi
0x18000c4c7  push    rdi
0x18000c4c8  push    r14
0x18000c4ca  push    r15
0x18000c4cc  lea     rbp, [rsp-10h]
0x18000c4d1  sub     rsp, 110h
0x18000c4d8  mov     rax, cs:__security_cookie
0x18000c4df  xor     rax, rsp
0x18000c4e2  mov     [rbp+30h+var_30], rax
0x18000c4e6  mov     r15, rdx
0x18000c4e9  mov     r14, rcx
0x18000c4ec  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c4f3  test    dword ptr [rcx+1Ch], 800h
0x18000c4fa  jz      short loc_18000C51B
0x18000c4fc  cmp     byte ptr [rcx+19h], 5
0x18000c500  jb      short loc_18000C51B
0x18000c502  mov     edx, 10h
0x18000c507  mov     r9, [r14+8]
0x18000c50b  lea     r8, WPP_4753d2a3665d3618996ed9ba7dd16268_Traceguids
0x18000c512  mov     rcx, [rcx+10h]
0x18000c516  call    WPP_SF__guid_
0x18000c51b  mov     [rsp+130h+var_E0], r14
0x18000c520  mov     rcx, r14
0x18000c523  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18000c529  call    cs:__imp_GetCurrentThreadId
0x18000c52f  mov     [rsp+130h+var_D4], eax
0x18000c533  mov     [rsp+130h+var_D8], 1
0x18000c538  cmp     byte ptr [r14+148h], 0
0x18000c540  jz      short loc_18000C551
0x18000c542  lea     rcx, [rsp+130h+var_E0]; this
0x18000c547  call    ??1ScopedWriteLock@Broker@@QEAA@XZ; Broker::ScopedWriteLock::~ScopedWriteLock(void)
0x18000c54c  jmp     loc_18000C89E
0x18000c551  xorps   xmm0, xmm0
0x18000c554  movdqu  xmmword ptr [rsp+130h+var_F8], xmm0
0x18000c55a  mov     [rsp+130h+var_E8], 0
0x18000c563  mov     ebx, 0Ch
0x18000c568  mov     edx, ebx
0x18000c56a  lea     rcx, [rsp+130h+var_F8]
0x18000c56f  call    ?_Buy_nonzero@?$vector@UTCallback@NotificationChannel@BILayer@Broker@@V?$allocator@UTCallback@NotificationChannel@BILayer@Broker@@@std@@@std@@AEAAX_K@Z; std::vector<Broker::BILayer::NotificationChannel::TCallback>::_Buy_nonzero(unsigned __int64)
0x18000c574  mov     edx, ebx
0x18000c576  mov     rcx, [rsp+130h+var_F8]; this
0x18000c57b  call    ??$_Uninitialized_value_construct_n@V?$allocator@UTCallback@NotificationChannel@BILayer@Broker@@@std@@@std@@YAPEAUTCallback@NotificationChannel@BILayer@Broker@@PEAU1234@_KAEAV?$allocator@UTCallback@NotificationChannel@BILayer@Broker@@@0@@Z; std::_Uninitialized_value_construct_n<std::allocator<Broker::BILayer::NotificationChannel::TCallback>>(Broker::BILayer::NotificationChannel::TCallback *,unsigned __int64,std::allocator<Broker::BILayer::NotificationChannel::TCallback> &)
0x18000c580  mov     [rsp+130h+var_F8+8], rax
0x18000c585  mov     qword ptr [rsp+130h+var_100], 0
0x18000c58e  lea     rcx, [rsp+130h+var_100]
0x18000c593  call    ??1?$_Tidy_guard@V?$vector@UTCallback@NotificationChannel@BILayer@Broker@@V?$allocator@UTCallback@NotificationChannel@BILayer@Broker@@@std@@@std@@@std@@QEAA@XZ; std::_Tidy_guard<std::vector<Broker::BILayer::NotificationChannel::TCallback>>::~_Tidy_guard<std::vector<Broker::BILayer::NotificationChannel::TCallback>>(void)
0x18000c598  nop
0x18000c599  mov     qword ptr [rsp+130h+var_100], r14
0x18000c59e  mov     rcx, [rsp+130h+var_F8]
0x18000c5a3  sub     rcx, 0FFFFFFFFFFFFFF80h
0x18000c5a7  lea     rdx, [rsp+130h+var_100]
0x18000c5ac  call    std__function_void___cdecl_unsigned_long_unsigned___int64_unsigned_long_void______operator___lambda_e3a07c48498026817584494316665233__0_
0x18000c5b1  mov     qword ptr [rsp+130h+var_100], r14
0x18000c5b6  mov     rcx, [rsp+130h+var_F8]
0x18000c5bb  add     rcx, 180h
0x18000c5c2  lea     rdx, [rsp+130h+var_100]
0x18000c5c7  call    std__function_void___cdecl_unsigned_long_unsigned___int64_unsigned_long_void______operator___lambda_c8fa6727609da0ae8cffc4d75127481e__0_
0x18000c5cc  mov     qword ptr [rsp+130h+var_100], r14
0x18000c5d1  mov     rcx, [rsp+130h+var_F8]
0x18000c5d6  add     rcx, 200h
0x18000c5dd  lea     rdx, [rsp+130h+var_100]
0x18000c5e2  call    std__function_void___cdecl_unsigned_long_unsigned_short_const___void______operator___lambda_086782e45ce54d322c9db8eaf3c1da39__0_
0x18000c5e7  mov     qword ptr [rsp+130h+var_100], r14
0x18000c5ec  mov     rcx, [rsp+130h+var_F8]
0x18000c5f1  add     rcx, 300h
0x18000c5f8  lea     rdx, [rsp+130h+var_100]
0x18000c5fd  call    std__function_void___cdecl_unsigned_long_unsigned_short_const___void______operator___lambda_da268ef20010ad47ca16aabf6a390cfd__0_
0x18000c602  mov     qword ptr [rsp+130h+var_100], r14
0x18000c607  mov     rcx, [rsp+130h+var_F8]
0x18000c60c  add     rcx, 400h
0x18000c613  lea     rdx, [rsp+130h+var_100]
0x18000c618  call    std__function_void___cdecl_unsigned_long_unsigned_short_const___void______operator___lambda_287a9fcb3b9e72b62c864a7e4405bdff__0_
0x18000c61d  mov     qword ptr [rsp+130h+var_100], r14
0x18000c622  mov     rcx, [rsp+130h+var_F8]
0x18000c627  add     rcx, 500h
0x18000c62e  lea     rdx, [rsp+130h+var_100]
0x18000c633  call    std__function_void___cdecl_unsigned_long_unsigned_short_const___void______operator___lambda_6c12a6f97ab60b36239838c33a9a7cbd__0_
0x18000c638  mov     qword ptr [rsp+130h+var_100], r14
0x18000c63d  mov     rcx, [rsp+130h+var_F8]
0x18000c642  add     rcx, 600h
0x18000c649  lea     rdx, [rsp+130h+var_100]
0x18000c64e  call    std__function_void___cdecl_unsigned_long_unsigned_short_const___void______operator___lambda_9b54c4c7fe1faac4d10b6394402ba495__0_
0x18000c653  mov     qword ptr [rsp+130h+var_100], r14
0x18000c658  mov     rcx, [rsp+130h+var_F8]
0x18000c65d  add     rcx, 700h
0x18000c664  lea     rdx, [rsp+130h+var_100]
0x18000c669  call    std__function_void___cdecl_unsigned_long_unsigned_short_const___void______operator___lambda_ee6d6e0aea383208c4c6414728c393b4__0_
0x18000c66e  mov     qword ptr [rsp+130h+var_100], r14
0x18000c673  mov     rcx, [rsp+130h+var_F8]
0x18000c678  add     rcx, 800h
0x18000c67f  lea     rdx, [rsp+130h+var_100]
0x18000c684  call    std__function_void___cdecl_unsigned_long_unsigned_short_const___void______operator___lambda_8d4cd62a7e99ff058dc75304dec8128c__0_
0x18000c689  mov     qword ptr [rsp+130h+var_100], r14
0x18000c68e  mov     rcx, [rsp+130h+var_F8]
0x18000c693  add     rcx, 940h
0x18000c69a  lea     rdx, [rsp+130h+var_100]
0x18000c69f  call    std__function_void___cdecl__GUID_const______operator___lambda_2a697d96b2de47a4269a727e77fc3b9f__0_
0x18000c6a4  mov     qword ptr [rsp+130h+var_100], r14
0x18000c6a9  mov     rcx, [rsp+130h+var_F8]
0x18000c6ae  add     rcx, 0B00h
0x18000c6b5  lea     rdx, [rsp+130h+var_100]
0x18000c6ba  call    std__function_void___cdecl_unsigned_long_unsigned_short_const___void______operator___lambda_4804ef5c84027b9de6878a69dd9befd8__0_
0x18000c6bf  mov     rdi, [r14+8]
0x18000c6c3  lea     ecx, [rbx+44h]; Size
0x18000c6c6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000c6cb  mov     rsi, rax
0x18000c6ce  mov     qword ptr [rsp+130h+var_100], rax
0x18000c6d3  xorps   xmm0, xmm0
0x18000c6d6  movups  xmmword ptr [rax], xmm0
0x18000c6d9  mov     dword ptr [rax+8], 1
0x18000c6e0  mov     dword ptr [rax+0Ch], 1
0x18000c6e7  lea     rax, ??_7?$_Ref_count_obj2@VNotificationChannel@BILayer@Broker@@@std@@6B@; const std::_Ref_count_obj2<Broker::BILayer::NotificationChannel>::`vftable'
0x18000c6ee  mov     [rsi], rax
0x18000c6f1  lea     rbx, [rsi+10h]
0x18000c6f5  lea     rdx, [rsp+130h+var_F8]
0x18000c6fa  lea     rcx, [rbp+30h+var_B0]
0x18000c6fe  call    ??0?$vector@UTCallback@NotificationChannel@BILayer@Broker@@V?$allocator@UTCallback@NotificationChannel@BILayer@Broker@@@std@@@std@@QEAA@AEBV01@@Z; std::vector<Broker::BILayer::NotificationChannel::TCallback>::vector<Broker::BILayer::NotificationChannel::TCallback>(std::vector<Broker::BILayer::NotificationChannel::TCallback> const &)
0x18000c703  mov     r9, rax
0x18000c706  mov     r8, r15
0x18000c709  mov     rdx, rdi
0x18000c70c  mov     rcx, rbx
0x18000c70f  call    ??0NotificationChannel@BILayer@Broker@@QEAA@AEBU_GUID@@PEBU_BI_READY_BROADCAST_INFO@@V?$vector@UTCallback@NotificationChannel@BILayer@Broker@@V?$allocator@UTCallback@NotificationChannel@BILayer@Broker@@@std@@@std@@@Z; Broker::BILayer::NotificationChannel::NotificationChannel(_GUID const &,_BI_READY_BROADCAST_INFO const *,std::vector<Broker::BILayer::NotificationChannel::TCallback>)
0x18000c714  nop
0x18000c715  mov     [r14+130h], rbx
0x18000c71c  mov     rcx, [r14+138h]; this
0x18000c723  mov     [r14+138h], rsi
0x18000c72a  test    rcx, rcx
0x18000c72d  jz      short loc_18000C734
0x18000c72f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000c734  mov     rcx, r14; this
0x18000c737  call    ?BrokerIsRegistered@BrokerBase@Broker@@QEAA_NXZ; Broker::BrokerBase::BrokerIsRegistered(void)
0x18000c73c  test    al, al
0x18000c73e  jnz     short loc_18000C748
0x18000c740  mov     rcx, r14; this
0x18000c743  call    ?RestoreEventsFromBI@BrokerBase@Broker@@AEAAXXZ; Broker::BrokerBase::RestoreEventsFromBI(void)
0x18000c748  mov     byte ptr [r14+148h], 1
0x18000c750  mov     rcx, r14
0x18000c753  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18000c759  mov     [rsp+130h+var_D8], 0
0x18000c75e  lea     rcx, [rsp+130h+var_D0]
0x18000c763  call    ?EnumerateUserContexts@BILayer@Broker@@YA?AV?$vector@_KV?$allocator@_K@std@@@std@@XZ; Broker::BILayer::EnumerateUserContexts(void)
0x18000c768  nop
0x18000c769  mov     rbx, qword ptr [rsp+130h+var_D0]
0x18000c76e  mov     esi, 7
0x18000c773  cmp     rbx, qword ptr [rsp+130h+var_D0+8]
0x18000c778  jz      loc_18000C851
0x18000c77e  xorps   xmm0, xmm0
0x18000c781  movdqa  xmmword ptr [rbp+30h+var_90], xmm0
0x18000c786  mov     [rbp+30h+var_80], 0
0x18000c78e  xorps   xmm1, xmm1
0x18000c791  movups  [rbp+30h+var_78], xmm1
0x18000c795  mov     [rbp+30h+var_68], 0
0x18000c79d  mov     [rbp+30h+var_60], rsi
0x18000c7a1  xor     eax, eax
0x18000c7a3  mov     word ptr [rbp+30h+var_78], ax
0x18000c7a7  movups  [rbp+30h+var_58], xmm0
0x18000c7ab  mov     [rbp+30h+var_48], rax
0x18000c7af  mov     [rbp+30h+var_40], rsi
0x18000c7b3  mov     word ptr [rbp+30h+var_58], ax
0x18000c7b7  mov     [rsp+130h+var_100], eax
0x18000c7bb  lea     r8, [rsp+130h+var_100]; struct Broker::ApplicationIdentity *
0x18000c7c0  lea     rdx, [rbp+30h+var_90]; unsigned __int64
0x18000c7c4  mov     rcx, [rbx]; this
0x18000c7c7  call    ?QueryUserContext@BILayer@Broker@@YA_N_KPEAUApplicationIdentity@2@PEAK@Z; Broker::BILayer::QueryUserContext(unsigned __int64,Broker::ApplicationIdentity *,ulong *)
0x18000c7cc  test    al, al
0x18000c7ce  jz      short loc_18000C83F
0x18000c7d0  mov     rdi, [rbp+30h+var_90]
0x18000c7d4  mov     rax, [r14+0A0h]
0x18000c7db  test    rax, rax
0x18000c7de  jz      short loc_18000C7F3
0x18000c7e0  mov     r9, rdi
0x18000c7e3  mov     r8, [rbx]
0x18000c7e6  mov     edx, [rsp+130h+var_100]
0x18000c7ea  mov     rcx, [r14+8]
0x18000c7ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c7f3  mov     r9, rdi; void *
0x18000c7f6  mov     r8d, [rsp+130h+var_100]; unsigned int
0x18000c7fb  mov     rdx, [rbx]; unsigned __int64
0x18000c7fe  mov     rcx, r14; this
0x18000c801  call    ?OnUserLogon@BrokerBase@Broker@@AEAAX_KKPEAX@Z; Broker::BrokerBase::OnUserLogon(unsigned __int64,ulong,void *)
0x18000c806  mov     rax, [r14+10h]
0x18000c80a  test    rax, rax
0x18000c80d  jz      short loc_18000C81F
0x18000c80f  mov     r8, rdi
0x18000c812  mov     edx, [rsp+130h+var_100]
0x18000c816  mov     rcx, [r14+8]
0x18000c81a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c81f  mov     rax, [r14+0A8h]
0x18000c826  test    rax, rax
0x18000c829  jz      short loc_18000C83F
0x18000c82b  mov     r9, rdi
0x18000c82e  mov     r8, [rbx]
0x18000c831  mov     edx, [rsp+130h+var_100]
0x18000c835  mov     rcx, [r14+8]
0x18000c839  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c83e  nop
0x18000c83f  lea     rcx, [rbp+30h+var_90]; this
0x18000c843  call    ??1ApplicationIdentity@Broker@@QEAA@XZ; Broker::ApplicationIdentity::~ApplicationIdentity(void)
0x18000c848  add     rbx, 8
0x18000c84c  jmp     loc_18000C773
0x18000c851  xor     ecx, ecx
0x18000c853  xchg    rcx, [r14+140h]
0x18000c85a  test    rcx, rcx
0x18000c85d  jz      short loc_18000C866
0x18000c85f  call    cs:__imp_RtlUnsubscribeWnfStateChangeNotification
0x18000c865  nop
0x18000c866  mov     rcx, qword ptr [rsp+130h+var_D0]
0x18000c86b  test    rcx, rcx
0x18000c86e  jz      short loc_18000C893
0x18000c870  mov     rdx, [rsp+130h+var_C0]
0x18000c875  sub     rdx, rcx
0x18000c878  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18000c87c  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000c881  xorps   xmm0, xmm0
0x18000c884  movdqu  [rsp+130h+var_D0], xmm0
0x18000c88a  mov     [rsp+130h+var_C0], 0
0x18000c893  lea     rcx, [rsp+130h+var_F8]
0x18000c898  call    ?_Tidy@?$vector@UTCallback@NotificationChannel@BILayer@Broker@@V?$allocator@UTCallback@NotificationChannel@BILayer@Broker@@@std@@@std@@AEAAXXZ; std::vector<Broker::BILayer::NotificationChannel::TCallback>::_Tidy(void)
0x18000c89d  nop
0x18000c89e  mov     rcx, [rbp+30h+var_30]
0x18000c8a2  xor     rcx, rsp; StackCookie
0x18000c8a5  call    __security_check_cookie
0x18000c8aa  mov     rbx, [rsp+130h+arg_10]
0x18000c8b2  add     rsp, 110h
0x18000c8b9  pop     r15
0x18000c8bb  pop     r14
0x18000c8bd  pop     rdi
0x18000c8be  pop     rsi
0x18000c8bf  pop     rbp
0x18000c8c0  retn
```
