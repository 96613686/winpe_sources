# Broker::BrokerBase::OnEventDestroy(_BR_EVENT_CALL_REASON,std::shared_ptr<Broker::BrokerEvent> const &)

- ea: `0x180012710`
- end: `0x1800128f4`
- name: `?OnEventDestroy@BrokerBase@Broker@@AEAAXW4_BR_EVENT_CALL_REASON@@AEBV?$shared_ptr@VBrokerEvent@Broker@@@std@@@Z`
- size: `484`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800183bc`

## callees

- `0x18000c3b0`
- `0x18000e538`
- `0x18000ee54`
- `0x180011d68`
- `0x1800126e0`
- `0x180012710`
- `0x1800194c4`
- `0x180019538`
- `0x18001e010`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800128d5`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800128d5`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180012783`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180012783`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Broker::BrokerBase::OnEventDestroy(__int64 a1, unsigned int a2, __int64 *a3)
{
  __int64 v6; // rcx
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 v9; // r8
  __int64 v10; // r9
  __int64 v11; // rcx
  int v12; // esi
  __int64 v13; // r8
  __int64 v14; // r9
  __int64 v15; // r8
  __int64 v16; // r9
  __int64 v17; // rcx
  void (__fastcall *v18)(_QWORD, _QWORD); // rax
  __int64 v20[2]; // [rsp+40h] [rbp-10h] BYREF
  int v21; // [rsp+70h] [rbp+20h] BYREF
  __int64 v22; // [rsp+80h] [rbp+30h] BYREF
  __int64 v23; // [rsp+88h] [rbp+38h] BYREF

  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    WPP_SF__guid__guid_DD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      68,
      HIDWORD(*(_QWORD *)(*(_QWORD *)(*a3 + 16) + 16LL)),
      *(_QWORD *)(a1 + 8),
      *(_QWORD *)(*a3 + 16));
  Broker::BrokerEvent::PendingOperationStart(*a3, 1);
  v20[1] = a1;
  RtlReleaseSRWLockExclusive(a1);
  if ( *(_QWORD *)(a1 + 128) )
  {
    if ( (unsigned int)dword_180028000 > 4 && (unsigned __int8)tlgKeywordOn(v6, 2, v7, v8) )
    {
      v11 = *a3;
      v22 = *(_QWORD *)(*a3 + 40);
      LOBYTE(v21) = a2;
      v23 = *(_QWORD *)(v11 + 16);
      v20[0] = *(_QWORD *)(a1 + 8);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>>(
        v11,
        byte_180021D8C,
        v9,
        v10,
        v20,
        &v23,
        (__int64)&v21,
        (__int64)&v22);
    }
    v12 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(a1 + 128))(
            a2,
            *(_QWORD *)(a1 + 8),
            *(_QWORD *)(*a3 + 16),
            *(_QWORD *)(*a3 + 40));
    if ( (unsigned int)dword_180028000 > 4 && (unsigned __int8)tlgKeywordOn((unsigned int)dword_180028000, 2, v13, v14) )
    {
      v21 = v12;
      v17 = *a3;
      v22 = *(_QWORD *)(*a3 + 16);
      v23 = *(_QWORD *)(a1 + 8);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
        v17,
        byte_180021F7D,
        v15,
        v16,
        &v23,
        &v22,
        (__int64)&v21);
    }
    if ( v12 && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      WPP_SF__guid_DD(*((_QWORD *)WPP_GLOBAL_Control + 2), 69);
  }
  v18 = *(void (__fastcall **)(_QWORD, _QWORD))(a1 + 88);
  if ( v18 )
    v18(*(_QWORD *)(a1 + 8), *(_QWORD *)(*a3 + 16));
  RtlAcquireSRWLockExclusive(a1);
  return Broker::BrokerEvent::PendingOperationStop(*a3, 1);
}

```

## disassembly

```asm
0x180012710  mov     [rsp-18h+arg_8], rbx
0x180012715  push    rbp
0x180012716  push    rsi
0x180012717  push    rdi
0x180012718  mov     rbp, rsp
0x18001271b  sub     rsp, 50h
0x18001271f  mov     rdi, r8
0x180012722  mov     esi, edx
0x180012724  mov     rbx, rcx
0x180012727  mov     rcx, cs:WPP_GLOBAL_Control
0x18001272e  test    dword ptr [rcx+1Ch], 800h
0x180012735  jz      short loc_18001276F
0x180012737  cmp     byte ptr [rcx+19h], 5
0x18001273b  jb      short loc_18001276F
0x18001273d  mov     rax, [r8]
0x180012740  mov     r9, [rax+10h]
0x180012744  mov     rax, [r9+10h]
0x180012748  mov     r8, rax
0x18001274b  shr     r8, 20h
0x18001274f  mov     edx, 44h ; 'D'
0x180012754  mov     dword ptr [rsp+50h+var_20], r8d
0x180012759  mov     dword ptr [rsp+50h+var_28], eax
0x18001275d  mov     [rsp+50h+var_30], r9
0x180012762  mov     r9, [rbx+8]
0x180012766  mov     rcx, [rcx+10h]
0x18001276a  call    WPP_SF__guid__guid_DD
0x18001276f  mov     edx, 1
0x180012774  mov     rcx, [rdi]
0x180012777  call    ?PendingOperationStart@BrokerEvent@Broker@@QEAAXW4_BR_EVENT_PENDING_OPERATION_TYPE@2@@Z; Broker::BrokerEvent::PendingOperationStart(Broker::_BR_EVENT_PENDING_OPERATION_TYPE)
0x18001277c  mov     [rbp+var_8], rbx
0x180012780  mov     rcx, rbx
0x180012783  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180012789  nop
0x18001278a  cmp     qword ptr [rbx+80h], 0
0x180012792  jz      loc_1800128B8
0x180012798  mov     eax, cs:dword_180028000
0x18001279e  cmp     eax, 4
0x1800127a1  jbe     short loc_180012800
0x1800127a3  mov     edx, 2
0x1800127a8  call    _tlgKeywordOn
0x1800127ad  test    al, al
0x1800127af  jz      short loc_180012800
0x1800127b1  mov     rcx, [rdi]
0x1800127b4  mov     rax, [rcx+28h]
0x1800127b8  mov     [rbp+arg_10], rax
0x1800127bc  mov     byte ptr [rbp+arg_0], sil
0x1800127c0  mov     rax, [rcx+10h]
0x1800127c4  mov     [rbp+arg_18], rax
0x1800127c8  mov     rax, [rbx+8]
0x1800127cc  mov     [rbp+var_10], rax
0x1800127d0  lea     rax, [rbp+arg_10]
0x1800127d4  mov     [rsp+50h+var_18], rax
0x1800127d9  lea     rax, [rbp+arg_0]
0x1800127dd  mov     [rsp+50h+var_20], rax
0x1800127e2  lea     rax, [rbp+arg_18]
0x1800127e6  mov     [rsp+50h+var_28], rax
0x1800127eb  lea     rax, [rbp+var_10]
0x1800127ef  mov     [rsp+50h+var_30], rax
0x1800127f4  lea     rdx, byte_180021D8C
0x1800127fb  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<8> const &)
0x180012800  mov     r8, [rdi]
0x180012803  mov     r9, [r8+28h]
0x180012807  mov     r8, [r8+10h]
0x18001280b  mov     rdx, [rbx+8]
0x18001280f  mov     ecx, esi
0x180012811  mov     rax, [rbx+80h]
0x180012818  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001281d  mov     esi, eax
0x18001281f  mov     ecx, cs:dword_180028000
0x180012825  cmp     ecx, 4
0x180012828  jbe     short loc_180012875
0x18001282a  mov     edx, 2
0x18001282f  call    _tlgKeywordOn
0x180012834  test    al, al
0x180012836  jz      short loc_180012875
0x180012838  mov     [rbp+arg_0], esi
0x18001283b  mov     rcx, [rdi]
0x18001283e  mov     rdx, [rcx+10h]
0x180012842  mov     [rbp+arg_10], rdx
0x180012846  mov     rax, [rbx+8]
0x18001284a  mov     [rbp+arg_18], rax
0x18001284e  lea     rax, [rbp+arg_0]
0x180012852  mov     [rsp+50h+var_20], rax
0x180012857  lea     rax, [rbp+arg_10]
0x18001285b  mov     [rsp+50h+var_28], rax
0x180012860  lea     rax, [rbp+arg_18]
0x180012864  mov     [rsp+50h+var_30], rax
0x180012869  lea     rdx, byte_180021F7D
0x180012870  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &)
0x180012875  test    esi, esi
0x180012877  jz      short loc_1800128B8
0x180012879  mov     rcx, cs:WPP_GLOBAL_Control
0x180012880  test    dword ptr [rcx+1Ch], 800h
0x180012887  jz      short loc_1800128B8
0x180012889  cmp     byte ptr [rcx+19h], 3
0x18001288d  jb      short loc_1800128B8
0x18001288f  mov     rax, [rdi]
0x180012892  mov     r9, [rax+10h]
0x180012896  mov     rax, [r9+10h]
0x18001289a  mov     r8, rax
0x18001289d  shr     r8, 20h
0x1800128a1  mov     edx, 45h ; 'E'
0x1800128a6  mov     dword ptr [rsp+50h+var_28], r8d
0x1800128ab  mov     dword ptr [rsp+50h+var_30], eax
0x1800128af  mov     rcx, [rcx+10h]
0x1800128b3  call    WPP_SF__guid_DD
0x1800128b8  mov     rax, [rbx+58h]
0x1800128bc  test    rax, rax
0x1800128bf  jz      short loc_1800128D2
0x1800128c1  mov     rdx, [rdi]
0x1800128c4  mov     rdx, [rdx+10h]
0x1800128c8  mov     rcx, [rbx+8]
0x1800128cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800128d1  nop
0x1800128d2  mov     rcx, rbx
0x1800128d5  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1800128db  mov     edx, 1
0x1800128e0  mov     rcx, [rdi]
0x1800128e3  mov     rbx, [rsp+50h+arg_8]
0x1800128e8  add     rsp, 50h
0x1800128ec  pop     rdi
0x1800128ed  pop     rsi
0x1800128ee  pop     rbp
0x1800128ef  jmp     ?PendingOperationStop@BrokerEvent@Broker@@QEAAXW4_BR_EVENT_PENDING_OPERATION_TYPE@2@@Z; Broker::BrokerEvent::PendingOperationStop(Broker::_BR_EVENT_PENDING_OPERATION_TYPE)
```
