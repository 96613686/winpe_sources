# Broker::TimeBroker::QueryCTriggerTime(Broker::ApplicationIdentity const &,_CBROKERED_EVENT_ID const &,_FILETIME &,_FILETIME &)

- ea: `0x180004e5c`
- end: `0x18000509c`
- name: `?QueryCTriggerTime@TimeBroker@Broker@@QEAAXAEBUApplicationIdentity@2@AEBU_CBROKERED_EVENT_ID@@AEAU_FILETIME@@2@Z`
- size: `576`
- prototype: `void __fastcall(Broker::TimeBroker *__hidden this, const struct Broker::ApplicationIdentity *, const struct _CBROKERED_EVENT_ID *, struct _FILETIME *, struct _FILETIME *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180004be0`

## callees

- `0x180004e5c`
- `0x180005b30`
- `0x180005b90`
- `0x180013978`

## import_xrefs

- `BrokerLib!BrLockBroker` at `0x180004edc`
- `BrokerLib!BrLockBroker` at `0x180004edc`
- `BrokerLib!BrFindBrokeredEvent2` at `0x180004f1d`
- `BrokerLib!BrFindBrokeredEvent2` at `0x180004f1d`
- `BrokerLib!BrGetBrokeredEventInfo2` at `0x180004f4e`
- `BrokerLib!BrGetBrokeredEventInfo2` at `0x180004f4e`

## pseudocode

```c
void __fastcall Broker::TimeBroker::QueryCTriggerTime(
        Broker::TimeBroker *this,
        const struct Broker::ApplicationIdentity *a2,
        const struct _CBROKERED_EVENT_ID *a3,
        struct _FILETIME *a4,
        struct _FILETIME *a5)
{
  std::_Ref_count_base *v9; // rbx
  int v10; // eax
  int BrokeredEvent2; // eax
  struct _FILETIME **v12; // rcx
  __int64 v13; // rax
  std::_Ref_count_base *v14; // rbx
  struct _FILETIME v15; // rdx
  __int64 v16; // [rsp+38h] [rbp-49h] BYREF
  void **pExceptionObject; // [rsp+40h] [rbp-41h] BYREF
  __int128 v18; // [rsp+48h] [rbp-39h]
  int v19; // [rsp+58h] [rbp-29h]
  __int128 v20; // [rsp+60h] [rbp-21h]
  void **v21; // [rsp+70h] [rbp-11h] BYREF
  __int128 v22; // [rsp+78h] [rbp-9h]
  int v23; // [rsp+88h] [rbp+7h]
  int v24; // [rsp+90h] [rbp+Fh]
  int v25; // [rsp+E0h] [rbp+5Fh] BYREF

  v16 = 0;
  v20 = 0;
  if ( !*((_QWORD *)this + 24) )
  {
    v18 = 0;
    v19 = 3;
    pExceptionObject = &Broker::NotFound::`vftable';
    throw (Broker::NotFound *)&pExceptionObject;
  }
  v25 = 1;
  v9 = *(&Broker::TimeBroker::Instance + 1);
  if ( *(&Broker::TimeBroker::Instance + 1) )
  {
    _InterlockedIncrement((volatile signed __int32 *)*(&Broker::TimeBroker::Instance + 1) + 2);
    v9 = *(&Broker::TimeBroker::Instance + 1);
  }
  pExceptionObject = (void **)Broker::TimeBroker::Instance;
  *(_QWORD *)&v18 = v9;
  v10 = BrLockBroker(*((_QWORD *)Broker::TimeBroker::Instance + 24));
  if ( v10 )
  {
    v22 = 0;
    v23 = 1;
    v21 = &Broker::Win32Error::`vftable';
    v24 = v10;
    throw (Broker::Win32Error *)&v21;
  }
  if ( v9 )
    std::_Ref_count_base::_Decref(v9);
  BrokeredEvent2 = BrFindBrokeredEvent2(*((_QWORD *)this + 24), *(_QWORD *)a3, *(_QWORD *)a2);
  if ( BrokeredEvent2 == 5 )
  {
    v18 = 0;
    v19 = 5;
    pExceptionObject = &Broker::AccessDenied::`vftable';
    throw (Broker::AccessDenied *)&pExceptionObject;
  }
  if ( BrokeredEvent2 )
  {
    v18 = 0;
    v19 = 3;
    pExceptionObject = &Broker::NotFound::`vftable';
    throw (Broker::NotFound *)&pExceptionObject;
  }
  if ( (unsigned int)BrGetBrokeredEventInfo2(*((_QWORD *)this + 24), 0, 0, 0, &v16) )
  {
    v18 = 0;
    v19 = 3;
    pExceptionObject = &Broker::NotFound::`vftable';
    throw (Broker::NotFound *)&pExceptionObject;
  }
  v12 = (struct _FILETIME **)v16;
  v13 = *(_QWORD *)(v16 + 8);
  if ( v13 )
    _InterlockedIncrement((volatile signed __int32 *)(v13 + 8));
  v14 = (std::_Ref_count_base *)v12[1];
  v15 = (*v12)[4];
  *a4 = (*v12)[3];
  *a5 = v15;
  Broker::TimeBroker::BrokerLock::~BrokerLock((Broker::TimeBroker::BrokerLock *)&v25);
  if ( v14 )
    std::_Ref_count_base::_Decref(v14);
}

```

## disassembly

```asm
0x180004e5c  push    rbp
0x180004e5e  push    rbx
0x180004e5f  push    rsi
0x180004e60  push    rdi
0x180004e61  push    r14
0x180004e63  push    r15
0x180004e65  lea     rbp, [rsp-27h]
0x180004e6a  sub     rsp, 0A8h
0x180004e71  mov     r14, r9
0x180004e74  mov     r15, r8
0x180004e77  mov     rsi, rdx
0x180004e7a  mov     rdi, rcx
0x180004e7d  mov     [rbp+4Fh+var_A0], 0
0x180004e85  mov     [rbp+4Fh+var_98], 0
0x180004e8d  xorps   xmm0, xmm0
0x180004e90  movdqu  [rbp+4Fh+var_70], xmm0
0x180004e95  cmp     qword ptr [rcx+0C0h], 0
0x180004e9d  jz      loc_180004FC2
0x180004ea3  mov     [rbp+4Fh+arg_0], 1
0x180004eaa  mov     rbx, qword ptr cs:?Instance@TimeBroker@Broker@@0V?$shared_ptr@VTimeBroker@Broker@@@std@@A+8; std::shared_ptr<Broker::TimeBroker> Broker::TimeBroker::Instance
0x180004eb1  test    rbx, rbx
0x180004eb4  jz      short loc_180004EC1
0x180004eb6  lock inc dword ptr [rbx+8]
0x180004eba  mov     rbx, qword ptr cs:?Instance@TimeBroker@Broker@@0V?$shared_ptr@VTimeBroker@Broker@@@std@@A+8; std::shared_ptr<Broker::TimeBroker> Broker::TimeBroker::Instance
0x180004ec1  mov     rcx, qword ptr cs:?Instance@TimeBroker@Broker@@0V?$shared_ptr@VTimeBroker@Broker@@@std@@A; std::shared_ptr<Broker::TimeBroker> Broker::TimeBroker::Instance
0x180004ec8  mov     [rbp+4Fh+pExceptionObject], rcx
0x180004ecc  mov     qword ptr [rbp+4Fh+var_88], rbx
0x180004ed0  mov     edx, 1
0x180004ed5  mov     rcx, [rcx+0C0h]
0x180004edc  call    cs:__imp_BrLockBroker
0x180004ee2  test    eax, eax
0x180004ee4  jnz     loc_180004FE9
0x180004eea  test    rbx, rbx
0x180004eed  jz      short loc_180004EF8
0x180004eef  mov     rcx, rbx; this
0x180004ef2  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180004ef7  nop
0x180004ef8  lea     r9, [rsi+18h]
0x180004efc  cmp     qword ptr [r9+18h], 7
0x180004f01  ja      loc_180005016
0x180004f07  lea     rax, [rbp+4Fh+var_A0]
0x180004f0b  mov     [rsp+0D0h+var_B0], rax
0x180004f10  mov     r8, [rsi]
0x180004f13  mov     rdx, [r15]
0x180004f16  mov     rcx, [rdi+0C0h]
0x180004f1d  call    cs:__imp_BrFindBrokeredEvent2
0x180004f23  cmp     eax, 5
0x180004f26  jz      loc_18000501E
0x180004f2c  test    eax, eax
0x180004f2e  jnz     loc_180005048
0x180004f34  lea     rax, [rbp+4Fh+var_98]
0x180004f38  mov     [rsp+0D0h+var_B0], rax
0x180004f3d  xor     r9d, r9d
0x180004f40  xor     r8d, r8d
0x180004f43  mov     rdx, [rbp+4Fh+var_A0]
0x180004f47  mov     rcx, [rdi+0C0h]
0x180004f4e  call    cs:__imp_BrGetBrokeredEventInfo2
0x180004f54  test    eax, eax
0x180004f56  jnz     loc_180005072
0x180004f5c  mov     rcx, [rbp+4Fh+var_98]
0x180004f60  mov     rax, [rcx+8]
0x180004f64  test    rax, rax
0x180004f67  jz      short loc_180004F6D
0x180004f69  lock inc dword ptr [rax+8]
0x180004f6d  mov     rdx, [rcx]
0x180004f70  mov     rbx, [rcx+8]
0x180004f74  mov     rax, [rdx+18h]
0x180004f78  mov     rdx, [rdx+20h]
0x180004f7c  mov     r8, rax
0x180004f7f  shr     r8, 20h
0x180004f83  mov     [r14+4], r8d
0x180004f87  mov     [r14], eax
0x180004f8a  mov     r8, rdx
0x180004f8d  shr     r8, 20h
0x180004f91  mov     rax, [rbp+4Fh+arg_20]
0x180004f95  mov     [rax+4], r8d
0x180004f99  mov     [rax], edx
0x180004f9b  lea     rcx, [rbp+4Fh+arg_0]; this
0x180004f9f  call    ??1BrokerLock@TimeBroker@Broker@@QEAA@XZ; Broker::TimeBroker::BrokerLock::~BrokerLock(void)
0x180004fa4  nop
0x180004fa5  test    rbx, rbx
0x180004fa8  jz      short loc_180004FB2
0x180004faa  mov     rcx, rbx; this
0x180004fad  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180004fb2  add     rsp, 0A8h
0x180004fb9  pop     r15
0x180004fbb  pop     r14
0x180004fbd  pop     rdi
0x180004fbe  pop     rsi
0x180004fbf  pop     rbx
0x180004fc0  pop     rbp
0x180004fc1  retn
0x180004fc2  movups  [rbp+4Fh+var_88], xmm0
0x180004fc6  mov     [rbp+4Fh+var_78], 3
0x180004fcd  lea     rax, ??_7NotFound@Broker@@6B@; const Broker::NotFound::`vftable'
0x180004fd4  mov     [rbp+4Fh+pExceptionObject], rax
0x180004fd8  lea     rdx, _TI3?AUNotFound@Broker@@; pThrowInfo
0x180004fdf  lea     rcx, [rbp+4Fh+pExceptionObject]; pExceptionObject
0x180004fe3  call    _CxxThrowException_0
0x180004fe9  xorps   xmm0, xmm0
0x180004fec  movups  [rbp+4Fh+var_58], xmm0
0x180004ff0  mov     [rbp+4Fh+var_48], 1
0x180004ff7  lea     rcx, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x180004ffe  mov     [rbp+4Fh+var_60], rcx
0x180005002  mov     [rbp+4Fh+var_40], eax
0x180005005  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x18000500c  lea     rcx, [rbp+4Fh+var_60]; pExceptionObject
0x180005010  call    _CxxThrowException_0
0x180005016  mov     r9, [r9]
0x180005019  jmp     loc_180004F07
0x18000501e  xorps   xmm0, xmm0
0x180005021  movups  [rbp+4Fh+var_88], xmm0
0x180005025  mov     [rbp+4Fh+var_78], 5
0x18000502c  lea     rax, ??_7AccessDenied@Broker@@6B@; const Broker::AccessDenied::`vftable'
0x180005033  mov     [rbp+4Fh+pExceptionObject], rax
0x180005037  lea     rdx, _TI3?AUAccessDenied@Broker@@; pThrowInfo
0x18000503e  lea     rcx, [rbp+4Fh+pExceptionObject]; pExceptionObject
0x180005042  call    _CxxThrowException_0
0x180005048  xorps   xmm0, xmm0
0x18000504b  movups  [rbp+4Fh+var_88], xmm0
0x18000504f  mov     [rbp+4Fh+var_78], 3
0x180005056  lea     rax, ??_7NotFound@Broker@@6B@; const Broker::NotFound::`vftable'
0x18000505d  mov     [rbp+4Fh+pExceptionObject], rax
0x180005061  lea     rdx, _TI3?AUNotFound@Broker@@; pThrowInfo
0x180005068  lea     rcx, [rbp+4Fh+pExceptionObject]; pExceptionObject
0x18000506c  call    _CxxThrowException_0
0x180005072  xorps   xmm0, xmm0
0x180005075  movups  [rbp+4Fh+var_88], xmm0
0x180005079  mov     [rbp+4Fh+var_78], 3
0x180005080  lea     rax, ??_7NotFound@Broker@@6B@; const Broker::NotFound::`vftable'
0x180005087  mov     [rbp+4Fh+pExceptionObject], rax
0x18000508b  lea     rdx, _TI3?AUNotFound@Broker@@; pThrowInfo
0x180005092  lea     rcx, [rbp+4Fh+pExceptionObject]; pExceptionObject
0x180005096  call    _CxxThrowException_0
```
