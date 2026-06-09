# Broker::BrokerBase::OnEventDisable(_BR_EVENT_CALL_REASON,std::shared_ptr<Broker::BrokerEvent> const &)

- ea: `0x180001ff8`
- end: `0x180002204`
- name: `?OnEventDisable@BrokerBase@Broker@@AEAAXW4_BR_EVENT_CALL_REASON@@AEBV?$shared_ptr@VBrokerEvent@Broker@@@std@@@Z`
- size: `524`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002e88`
- `0x1800183bc`

## callees

- `0x180001ff8`
- `0x18000c3b0`
- `0x18000e538`
- `0x18000ee54`
- `0x180011d68`
- `0x1800126e0`
- `0x1800131a0`
- `0x1800149f8`
- `0x1800194c4`
- `0x180019538`
- `0x18001e010`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800021dd`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800021dd`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180002081`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180002081`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Broker::BrokerBase::OnEventDisable(__int64 a1, unsigned int a2, __int64 *a3)
{
  __int64 result; // rax
  __int64 v7; // r9
  __int64 v8; // rcx
  __int64 v9; // r8
  __int64 v10; // r9
  __int64 v11; // r8
  __int64 v12; // r9
  __int64 v13; // rcx
  int v14; // esi
  __int64 v15; // r8
  __int64 v16; // r9
  __int64 v17; // r8
  __int64 v18; // r9
  __int64 v19; // rcx
  void (__fastcall *v20)(_QWORD, _QWORD); // rax
  __int64 v21; // [rsp+40h] [rbp-20h] BYREF
  __int64 v22[3]; // [rsp+48h] [rbp-18h] BYREF
  int v23; // [rsp+90h] [rbp+30h] BYREF
  __int64 v24; // [rsp+98h] [rbp+38h] BYREF

  Broker::BrokerBase::WaitForPendingOperation(a1, a3);
  result = Broker::BrokerEvent::GetState(*a3);
  if ( (_DWORD)result == 1 )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      WPP_SF__guid__guid_DD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        66,
        HIDWORD(*(_QWORD *)(*(_QWORD *)(v7 + 16) + 16LL)),
        *(_QWORD *)(a1 + 8),
        *(_QWORD *)(v7 + 16));
    Broker::BrokerEvent::PendingOperationStart(*a3, 0);
    v22[1] = a1;
    RtlReleaseSRWLockExclusive(a1);
    if ( *(_QWORD *)(a1 + 144) )
    {
      if ( (unsigned int)dword_180028000 > 4 && (unsigned __int8)tlgKeywordOn(v8, 2, v9, v10) )
      {
        v13 = *a3;
        v24 = *(_QWORD *)(*a3 + 40);
        LOBYTE(v23) = a2;
        v21 = *(_QWORD *)(v13 + 16);
        v22[0] = *(_QWORD *)(a1 + 8);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>>(
          v13,
          byte_180021DD9,
          v11,
          v12,
          v22,
          &v21,
          (__int64)&v23,
          (__int64)&v24);
      }
      v14 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(a1 + 144))(
              a2,
              *(_QWORD *)(a1 + 8),
              *(_QWORD *)(*a3 + 16),
              *(_QWORD *)(*a3 + 40));
      if ( (unsigned int)dword_180028000 > 4
        && (unsigned __int8)tlgKeywordOn((unsigned int)dword_180028000, 2, v15, v16) )
      {
        v23 = v14;
        v19 = *a3;
        v24 = *(_QWORD *)(*a3 + 16);
        v22[0] = *(_QWORD *)(a1 + 8);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
          v19,
          byte_180021FF7,
          v17,
          v18,
          v22,
          &v24,
          (__int64)&v23);
      }
      if ( v14 && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
        WPP_SF__guid_DD(*((_QWORD *)WPP_GLOBAL_Control + 2), 67);
    }
    v20 = *(void (__fastcall **)(_QWORD, _QWORD))(a1 + 112);
    if ( v20 )
    {
      if ( !*(_QWORD *)(a1 + 144) )
        v20(*(_QWORD *)(a1 + 8), *(_QWORD *)(*a3 + 16));
    }
    RtlAcquireSRWLockExclusive(a1);
    Broker::BrokerEvent::PendingOperationStop(*a3, 0);
    result = *a3;
    *(_DWORD *)(*a3 + 24) &= ~2u;
  }
  return result;
}

```

## disassembly

```asm
0x180001ff8  mov     [rsp-18h+arg_0], rbx
0x180001ffd  push    rbp
0x180001ffe  push    rsi
0x180001fff  push    rdi
0x180002000  mov     rbp, rsp
0x180002003  sub     rsp, 60h
0x180002007  mov     rdi, r8
0x18000200a  mov     esi, edx
0x18000200c  mov     rbx, rcx
0x18000200f  mov     rdx, r8
0x180002012  call    ?WaitForPendingOperation@BrokerBase@Broker@@AEAAXAEBV?$shared_ptr@VBrokerEvent@Broker@@@std@@@Z; Broker::BrokerBase::WaitForPendingOperation(std::shared_ptr<Broker::BrokerEvent> const &)
0x180002017  mov     r9, [rdi]
0x18000201a  mov     rcx, r9
0x18000201d  call    ?GetState@BrokerEvent@Broker@@QEBA?AW4_BROKERED_EVENT_STATE@@XZ; Broker::BrokerEvent::GetState(void)
0x180002022  cmp     eax, 1
0x180002025  jnz     loc_1800021F4
0x18000202b  mov     rcx, cs:WPP_GLOBAL_Control
0x180002032  test    dword ptr [rcx+1Ch], 800h
0x180002039  jz      short loc_180002070
0x18000203b  cmp     byte ptr [rcx+19h], 5
0x18000203f  jb      short loc_180002070
0x180002041  mov     r9, [r9+10h]
0x180002045  mov     rax, [r9+10h]
0x180002049  mov     r8, rax
0x18000204c  shr     r8, 20h
0x180002050  mov     edx, 42h ; 'B'
0x180002055  mov     dword ptr [rsp+60h+var_30], r8d
0x18000205a  mov     dword ptr [rsp+60h+var_38], eax
0x18000205e  mov     [rsp+60h+var_40], r9
0x180002063  mov     r9, [rbx+8]
0x180002067  mov     rcx, [rcx+10h]
0x18000206b  call    WPP_SF__guid__guid_DD
0x180002070  xor     edx, edx
0x180002072  mov     rcx, [rdi]
0x180002075  call    ?PendingOperationStart@BrokerEvent@Broker@@QEAAXW4_BR_EVENT_PENDING_OPERATION_TYPE@2@@Z; Broker::BrokerEvent::PendingOperationStart(Broker::_BR_EVENT_PENDING_OPERATION_TYPE)
0x18000207a  mov     [rbp+var_10], rbx
0x18000207e  mov     rcx, rbx
0x180002081  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180002087  nop
0x180002088  cmp     qword ptr [rbx+90h], 0
0x180002090  jz      loc_1800021B6
0x180002096  mov     eax, cs:dword_180028000
0x18000209c  cmp     eax, 4
0x18000209f  jbe     short loc_1800020FE
0x1800020a1  mov     edx, 2
0x1800020a6  call    _tlgKeywordOn
0x1800020ab  test    al, al
0x1800020ad  jz      short loc_1800020FE
0x1800020af  mov     rcx, [rdi]
0x1800020b2  mov     rax, [rcx+28h]
0x1800020b6  mov     [rbp+arg_18], rax
0x1800020ba  mov     byte ptr [rbp+arg_10], sil
0x1800020be  mov     rax, [rcx+10h]
0x1800020c2  mov     [rbp+var_20], rax
0x1800020c6  mov     rax, [rbx+8]
0x1800020ca  mov     [rbp+var_18], rax
0x1800020ce  lea     rax, [rbp+arg_18]
0x1800020d2  mov     [rsp+60h+var_28], rax
0x1800020d7  lea     rax, [rbp+arg_10]
0x1800020db  mov     [rsp+60h+var_30], rax
0x1800020e0  lea     rax, [rbp+var_20]
0x1800020e4  mov     [rsp+60h+var_38], rax
0x1800020e9  lea     rax, [rbp+var_18]
0x1800020ed  mov     [rsp+60h+var_40], rax
0x1800020f2  lea     rdx, byte_180021DD9
0x1800020f9  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<8> const &)
0x1800020fe  mov     r8, [rdi]
0x180002101  mov     r9, [r8+28h]
0x180002105  mov     r8, [r8+10h]
0x180002109  mov     rdx, [rbx+8]
0x18000210d  mov     ecx, esi
0x18000210f  mov     rax, [rbx+90h]
0x180002116  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000211b  mov     esi, eax
0x18000211d  mov     ecx, cs:dword_180028000
0x180002123  cmp     ecx, 4
0x180002126  jbe     short loc_180002173
0x180002128  mov     edx, 2
0x18000212d  call    _tlgKeywordOn
0x180002132  test    al, al
0x180002134  jz      short loc_180002173
0x180002136  mov     [rbp+arg_10], esi
0x180002139  mov     rcx, [rdi]
0x18000213c  mov     rdx, [rcx+10h]
0x180002140  mov     [rbp+arg_18], rdx
0x180002144  mov     rax, [rbx+8]
0x180002148  mov     [rbp+var_18], rax
0x18000214c  lea     rax, [rbp+arg_10]
0x180002150  mov     [rsp+60h+var_30], rax
0x180002155  lea     rax, [rbp+arg_18]
0x180002159  mov     [rsp+60h+var_38], rax
0x18000215e  lea     rax, [rbp+var_18]
0x180002162  mov     [rsp+60h+var_40], rax
0x180002167  lea     rdx, byte_180021FF7
0x18000216e  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &)
0x180002173  test    esi, esi
0x180002175  jz      short loc_1800021B6
0x180002177  mov     rcx, cs:WPP_GLOBAL_Control
0x18000217e  test    dword ptr [rcx+1Ch], 800h
0x180002185  jz      short loc_1800021B6
0x180002187  cmp     byte ptr [rcx+19h], 3
0x18000218b  jb      short loc_1800021B6
0x18000218d  mov     rax, [rdi]
0x180002190  mov     r9, [rax+10h]
0x180002194  mov     rax, [r9+10h]
0x180002198  mov     r8, rax
0x18000219b  shr     r8, 20h
0x18000219f  mov     edx, 43h ; 'C'
0x1800021a4  mov     dword ptr [rsp+60h+var_38], r8d
0x1800021a9  mov     dword ptr [rsp+60h+var_40], eax
0x1800021ad  mov     rcx, [rcx+10h]
0x1800021b1  call    WPP_SF__guid_DD
0x1800021b6  mov     rax, [rbx+70h]
0x1800021ba  test    rax, rax
0x1800021bd  jz      short loc_1800021DA
0x1800021bf  cmp     qword ptr [rbx+90h], 0
0x1800021c7  jnz     short loc_1800021DA
0x1800021c9  mov     rdx, [rdi]
0x1800021cc  mov     rdx, [rdx+10h]
0x1800021d0  mov     rcx, [rbx+8]
0x1800021d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800021d9  nop
0x1800021da  mov     rcx, rbx
0x1800021dd  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1800021e3  xor     edx, edx
0x1800021e5  mov     rcx, [rdi]
0x1800021e8  call    ?PendingOperationStop@BrokerEvent@Broker@@QEAAXW4_BR_EVENT_PENDING_OPERATION_TYPE@2@@Z; Broker::BrokerEvent::PendingOperationStop(Broker::_BR_EVENT_PENDING_OPERATION_TYPE)
0x1800021ed  mov     rax, [rdi]
0x1800021f0  and     dword ptr [rax+18h], 0FFFFFFFDh
0x1800021f4  mov     rbx, [rsp+60h+arg_0]
0x1800021fc  add     rsp, 60h
0x180002200  pop     rdi
0x180002201  pop     rsi
0x180002202  pop     rbp
0x180002203  retn
```
