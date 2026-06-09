# _lambda_287a9fcb3b9e72b62c864a7e4405bdff_::operator()

- ea: `0x180001208`
- end: `0x1800012c4`
- name: `_lambda_287a9fcb3b9e72b62c864a7e4405bdff_::operator()`
- size: `188`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180018ff0`

## callees

- `0x180001208`
- `0x1800012cc`
- `0x180004d70`
- `0x180006b30`
- `0x180015af0`
- `0x18001e010`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000124b`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18000124b`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180001270`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180001270`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001251`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001251`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall lambda_287a9fcb3b9e72b62c864a7e4405bdff_::operator()(
        Broker::BrokerBase **a1,
        __int64 a2,
        const unsigned __int16 *a3,
        void *a4)
{
  Broker::BrokerBase *v7; // rbx
  void (__fastcall *v8)(_QWORD, const unsigned __int16 *, void *); // rax
  _BYTE v9[96]; // [rsp+30h] [rbp-88h] BYREF

  Broker::ApplicationIdentity::ApplicationIdentity((Broker::ApplicationIdentity *)v9, a4, a3);
  v7 = *a1;
  RtlAcquireSRWLockExclusive(*a1);
  GetCurrentThreadId();
  Broker::BrokerBase::OnAppUninstall(*a1, (const struct Broker::ApplicationIdentity *)v9);
  RtlReleaseSRWLockExclusive(v7);
  v8 = (void (__fastcall *)(_QWORD, const unsigned __int16 *, void *))*((_QWORD *)*a1 + 6);
  if ( v8 )
    v8(*((_QWORD *)*a1 + 1), a3, a4);
  Broker::ApplicationIdentity::~ApplicationIdentity((Broker::ApplicationIdentity *)v9);
}

```

## disassembly

```asm
0x180001208  mov     [rsp+arg_8], rbx
0x18000120d  push    rbp
0x18000120e  push    rsi
0x18000120f  push    rdi
0x180001210  sub     rsp, 0A0h
0x180001217  mov     rax, cs:__security_cookie
0x18000121e  xor     rax, rsp
0x180001221  mov     [rsp+0B8h+var_28], rax
0x180001229  mov     rbp, r9
0x18000122c  mov     rsi, r8
0x18000122f  mov     rdi, rcx
0x180001232  mov     rdx, r9; void *
0x180001235  lea     rcx, [rsp+0B8h+var_88]; this
0x18000123a  call    ??0ApplicationIdentity@Broker@@QEAA@PEAXQEBG@Z; Broker::ApplicationIdentity::ApplicationIdentity(void *,ushort const * const)
0x18000123f  nop
0x180001240  mov     rbx, [rdi]
0x180001243  mov     [rsp+0B8h+var_98], rbx
0x180001248  mov     rcx, rbx
0x18000124b  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180001251  call    cs:__imp_GetCurrentThreadId
0x180001257  mov     [rsp+0B8h+var_8C], eax
0x18000125b  mov     [rsp+0B8h+var_90], 1
0x180001260  lea     rdx, [rsp+0B8h+var_88]; struct Broker::ApplicationIdentity *
0x180001265  mov     rcx, [rdi]; this
0x180001268  call    ?OnAppUninstall@BrokerBase@Broker@@AEAAXAEBUApplicationIdentity@2@@Z; Broker::BrokerBase::OnAppUninstall(Broker::ApplicationIdentity const &)
0x18000126d  mov     rcx, rbx
0x180001270  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180001276  mov     [rsp+0B8h+var_90], 0
0x18000127b  mov     rcx, [rdi]
0x18000127e  mov     rax, [rcx+30h]
0x180001282  test    rax, rax
0x180001285  jz      short loc_180001297
0x180001287  mov     r8, rbp
0x18000128a  mov     rdx, rsi
0x18000128d  mov     rcx, [rcx+8]
0x180001291  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001296  nop
0x180001297  lea     rcx, [rsp+0B8h+var_88]; this
0x18000129c  call    ??1ApplicationIdentity@Broker@@QEAA@XZ; Broker::ApplicationIdentity::~ApplicationIdentity(void)
0x1800012a1  mov     rcx, [rsp+0B8h+var_28]
0x1800012a9  xor     rcx, rsp; StackCookie
0x1800012ac  call    __security_check_cookie
0x1800012b1  mov     rbx, [rsp+0B8h+arg_8]
0x1800012b9  add     rsp, 0A0h
0x1800012c0  pop     rdi
0x1800012c1  pop     rsi
0x1800012c2  pop     rbp
0x1800012c3  retn
```
