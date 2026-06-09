# BrSignalBrokerEvent

- ea: `0x180017090`
- end: `0x1800171cf`
- name: `BrSignalBrokerEvent`
- size: `319`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180004ae0`
- `0x1800058e0`
- `0x180009e94`
- `0x18000e538`
- `0x1800126e0`
- `0x180017090`
- `0x180018ec0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 __fastcall BrSignalBrokerEvent(
        void *a1,
        const struct _GUID *a2,
        const unsigned __int8 *a3,
        struct _GUID *a4,
        unsigned int a5,
        unsigned __int8 *a6)
{
  __int64 v10; // r9
  std::_Ref_count_base *v11; // rcx
  __int128 *v12; // r8
  __int64 v13; // rcx
  struct _RTL_SRWLOCK *v14; // r8
  __int64 v15; // r9
  int v17; // [rsp+40h] [rbp-68h] BYREF
  struct _RTL_SRWLOCK *v18; // [rsp+48h] [rbp-60h] BYREF
  std::_Ref_count_base *v19; // [rsp+50h] [rbp-58h]
  const struct _GUID *v20; // [rsp+68h] [rbp-40h] BYREF

  v20 = a2;
  Broker::BrokerBase::GetInstance(&v18, a1);
  Broker::BrokerBase::SignalEvent(v18, a2, a3, a4, a6, a5);
  v11 = v19;
  if ( v19 )
    std::_Ref_count_base::_Decref(v19);
  if ( dword_180028000 )
  {
    v12 = &BLP_TRACELOGGING_INVALID_GUID;
    if ( a1 )
      v12 = (__int128 *)a1;
    if ( (unsigned int)dword_180028000 > 4 && (unsigned __int8)tlgKeywordOn(v11, 8, v12, v10) )
    {
      v17 = 0;
      v20 = a2;
      v18 = v14;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
        v13,
        byte_180021C64,
        (__int64)v14,
        v15,
        (__int64 *)&v18,
        (__int64 *)&v20,
        (__int64)&v17);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180017090  mov     [rsp+arg_0], rcx
0x180017095  push    rbx
0x180017096  push    rsi
0x180017097  push    rdi
0x180017098  push    r12
0x18001709a  push    r14
0x18001709c  push    r15
0x18001709e  sub     rsp, 78h
0x1800170a2  mov     r15, r9
0x1800170a5  mov     r14, r8
0x1800170a8  mov     rsi, rdx
0x1800170ab  mov     rdi, rcx
0x1800170ae  mov     [rsp+0A8h+var_40], rdx
0x1800170b3  mov     r12, [rsp+0A8h+arg_28]
0x1800170bb  xor     ebx, ebx
0x1800170bd  mov     rdx, rcx
0x1800170c0  lea     rcx, [rsp+0A8h+var_60]
0x1800170c5  call    ?GetInstance@BrokerBase@Broker@@SA?AV?$shared_ptr@VBrokerBase@Broker@@@std@@AEBU_GUID@@@Z; Broker::BrokerBase::GetInstance(_GUID const &)
0x1800170ca  nop
0x1800170cb  mov     eax, [rsp+0A8h+arg_20]
0x1800170d2  mov     [rsp+0A8h+var_80], eax; unsigned int
0x1800170d6  mov     [rsp+0A8h+var_88], r12; unsigned __int8 *
0x1800170db  mov     r9, r15; struct _GUID *
0x1800170de  mov     r8, r14; unsigned __int8 *
0x1800170e1  mov     rdx, rsi; struct _GUID *
0x1800170e4  mov     rcx, [rsp+0A8h+var_60]; this
0x1800170e9  call    ?SignalEvent@BrokerBase@Broker@@QEAAXAEBU_GUID@@PEBEPEBU3@1K@Z; Broker::BrokerBase::SignalEvent(_GUID const &,uchar const *,_GUID const *,uchar const *,ulong)
0x1800170ee  nop
0x1800170ef  mov     rcx, [rsp+0A8h+var_58]; this
0x1800170f4  test    rcx, rcx
0x1800170f7  jz      short loc_1800170FF
0x1800170f9  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800170fe  nop
0x1800170ff  jmp     short loc_180017140
0x180017101  mov     ebx, [rsp+0A8h+var_68]
0x180017105  mov     rcx, cs:WPP_GLOBAL_Control
0x18001710c  test    dword ptr [rcx+1Ch], 800h
0x180017113  jz      short loc_180017133
0x180017115  cmp     byte ptr [rcx+19h], 2
0x180017119  jb      short loc_180017133
0x18001711b  mov     edx, 1Dh
0x180017120  mov     r9d, ebx
0x180017123  lea     r8, WPP_8595d4a22dff35b4ac96cc1b50bbb660_Traceguids
0x18001712a  mov     rcx, [rcx+10h]
0x18001712e  call    WPP_SF_d
0x180017133  mov     rsi, [rsp+0A8h+var_40]
0x180017138  mov     rdi, [rsp+0A8h+arg_0]
0x180017140  mov     eax, cs:dword_180028000
0x180017146  test    eax, eax
0x180017148  jz      short loc_1800171A9
0x18001714a  lea     r8, BLP_TRACELOGGING_INVALID_GUID
0x180017151  test    rdi, rdi
0x180017154  cmovnz  r8, rdi
0x180017158  mov     eax, cs:dword_180028000
0x18001715e  cmp     eax, 4
0x180017161  jbe     short loc_1800171A9
0x180017163  mov     edx, 8
0x180017168  call    _tlgKeywordOn
0x18001716d  test    al, al
0x18001716f  jz      short loc_1800171A9
0x180017171  mov     [rsp+0A8h+var_68], ebx
0x180017175  mov     [rsp+0A8h+var_40], rsi
0x18001717a  mov     [rsp+0A8h+var_60], r8
0x18001717f  lea     rax, [rsp+0A8h+var_68]
0x180017184  mov     [rsp+0A8h+var_78], rax
0x180017189  lea     rax, [rsp+0A8h+var_40]
0x18001718e  mov     qword ptr [rsp+0A8h+var_80], rax
0x180017193  lea     rax, [rsp+0A8h+var_60]
0x180017198  mov     [rsp+0A8h+var_88], rax
0x18001719d  lea     rdx, byte_180021C64
0x1800171a4  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &)
0x1800171a9  mov     eax, ebx
0x1800171ab  add     rsp, 78h
0x1800171af  pop     r15
0x1800171b1  pop     r14
0x1800171b3  pop     r12
0x1800171b5  pop     rdi
0x1800171b6  pop     rsi
0x1800171b7  pop     rbx
0x1800171b8  retn
0x1800171b9  jmp     loc_180017101
0x1800171be  mov     ebx, [rsp+0A8h+var_68]
0x1800171c2  test    ebx, ebx
0x1800171c4  jz      loc_180017133
0x1800171ca  jmp     loc_180017105
```
