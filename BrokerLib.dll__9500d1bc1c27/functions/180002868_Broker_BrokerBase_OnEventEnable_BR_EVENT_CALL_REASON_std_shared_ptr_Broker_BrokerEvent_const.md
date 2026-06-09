# Broker::BrokerBase::OnEventEnable(_BR_EVENT_CALL_REASON,std::shared_ptr<Broker::BrokerEvent> const &)

- ea: `0x180002868`
- end: `0x180002ad4`
- name: `?OnEventEnable@BrokerBase@Broker@@AEAAXW4_BR_EVENT_CALL_REASON@@AEBV?$shared_ptr@VBrokerEvent@Broker@@@std@@@Z`
- size: `620`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x180003760`
- `0x1800178fc`

## callees

- `0x180002868`
- `0x180004ae0`
- `0x18000c3b0`
- `0x18000e538`
- `0x18000ea30`
- `0x18000ed18`
- `0x18001184c`
- `0x180011d68`
- `0x1800126e0`
- `0x1800131a0`
- `0x1800149f8`
- `0x1800165da`
- `0x18001e010`

## pseudocode

```c
void __fastcall Broker::BrokerBase::OnEventEnable(__int64 a1, unsigned int a2, std::_Ref_count_base **a3)
{
  __int64 v6; // r8
  __int64 v7; // r9
  std::_Ref_count_base *v8; // rcx
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // r9
  std::_Ref_count_base *v13; // rax
  __int64 v14; // rcx
  unsigned int v15; // esi
  __int64 v16; // r8
  __int64 v17; // r9
  __int64 v18; // r8
  __int64 v19; // r9
  __int64 v20; // rcx
  void (__fastcall *v21)(_QWORD, _QWORD); // rax
  __int64 v22; // [rsp+40h] [rbp-40h] BYREF
  std::_Ref_count_base *v23; // [rsp+48h] [rbp-38h]
  _BYTE pExceptionObject[48]; // [rsp+50h] [rbp-30h] BYREF
  unsigned int v25; // [rsp+B0h] [rbp+30h] BYREF
  __int64 v26; // [rsp+B8h] [rbp+38h] BYREF

  Broker::BrokerBase::WaitForPendingOperation(a1, a3);
  if ( !(unsigned int)Broker::BrokerEvent::GetState(*a3) )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      WPP_SF__guid__guid_DD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        63,
        HIDWORD(*(_QWORD *)(*(_QWORD *)(v7 + 16) + 16LL)),
        *(_QWORD *)(a1 + 8),
        *(_QWORD *)(v7 + 16));
    v8 = *a3;
    if ( (*(_BYTE *)(*((_QWORD *)*a3 + 2) + 48LL) & 1) != 0 )
    {
      Broker::BrokerEvent::GetAppState(v8, &v22);
      if ( !*(_BYTE *)(v22 + 136) )
      {
        v9 = WPP_GLOBAL_Control;
        if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
          goto LABEL_11;
        v10 = 64;
LABEL_10:
        WPP_SF__guid_DD(v9[2], v10);
LABEL_11:
        if ( v23 )
          std::_Ref_count_base::_Decref(v23);
        return;
      }
      if ( !*(_BYTE *)(v22 + 137) )
      {
        v9 = WPP_GLOBAL_Control;
        if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
          goto LABEL_11;
        v10 = 65;
        goto LABEL_10;
      }
      v8 = v23;
      if ( v23 )
        std::_Ref_count_base::_Decref(v23);
    }
    if ( *(_QWORD *)(a1 + 136) )
    {
      if ( (unsigned int)dword_180028000 > 4 && (unsigned __int8)tlgKeywordOn(v8, 2, v6, v7) )
      {
        v13 = *a3;
        LOBYTE(v25) = a2;
        v14 = *((_QWORD *)v13 + 2);
        v22 = *(_QWORD *)(a1 + 8);
        v26 = v14;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>>(
          v14,
          byte_180022173,
          v11,
          v12,
          &v22,
          &v26,
          (__int64)&v25);
      }
      v15 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(a1 + 136))(
              a2,
              *(_QWORD *)(a1 + 8),
              *((_QWORD *)*a3 + 2),
              *((_QWORD *)*a3 + 5));
      if ( (unsigned int)dword_180028000 > 4
        && (unsigned __int8)tlgKeywordOn((unsigned int)dword_180028000, 2, v16, v17) )
      {
        v20 = (__int64)*a3;
        v22 = *(_QWORD *)(a1 + 8);
        v25 = v15;
        v26 = *(_QWORD *)(v20 + 16);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
          v20,
          byte_180022039,
          v18,
          v19,
          &v22,
          &v26,
          (__int64)&v25);
      }
      if ( v15 )
      {
        Broker::Win32Error::Win32Error((Broker::Win32Error *)pExceptionObject, v15);
        throw (Broker::Win32Error *)pExceptionObject;
      }
    }
    *((_DWORD *)*a3 + 6) |= 2u;
    v21 = *(void (__fastcall **)(_QWORD, _QWORD))(a1 + 104);
    if ( v21 && !*(_QWORD *)(a1 + 136) )
      v21(*(_QWORD *)(a1 + 8), *((_QWORD *)*a3 + 2));
  }
}

```

## disassembly

```asm
0x180002868  mov     [rsp-18h+arg_0], rbx
0x18000286d  mov     [rsp-18h+arg_8], rsi
0x180002872  push    rbp
0x180002873  push    rdi
0x180002874  push    r15
0x180002876  mov     rbp, rsp
0x180002879  sub     rsp, 80h
0x180002880  mov     esi, edx
0x180002882  mov     rdi, r8
0x180002885  mov     rdx, r8
0x180002888  mov     rbx, rcx
0x18000288b  call    ?WaitForPendingOperation@BrokerBase@Broker@@AEAAXAEBV?$shared_ptr@VBrokerEvent@Broker@@@std@@@Z; Broker::BrokerBase::WaitForPendingOperation(std::shared_ptr<Broker::BrokerEvent> const &)
0x180002890  mov     r9, [rdi]
0x180002893  mov     rcx, r9
0x180002896  call    ?GetState@BrokerEvent@Broker@@QEBA?AW4_BROKERED_EVENT_STATE@@XZ; Broker::BrokerEvent::GetState(void)
0x18000289b  test    eax, eax
0x18000289d  jnz     loc_180002AA0
0x1800028a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800028aa  mov     r15d, 800h
0x1800028b0  test    [rcx+1Ch], r15d
0x1800028b4  jz      short loc_1800028EB
0x1800028b6  cmp     byte ptr [rcx+19h], 5
0x1800028ba  jb      short loc_1800028EB
0x1800028bc  mov     r9, [r9+10h]
0x1800028c0  mov     edx, 3Fh ; '?'
0x1800028c5  mov     rcx, [rcx+10h]
0x1800028c9  mov     rax, [r9+10h]
0x1800028cd  mov     r8, rax
0x1800028d0  shr     r8, 20h
0x1800028d4  mov     dword ptr [rsp+80h+var_50], r8d
0x1800028d9  mov     dword ptr [rsp+80h+var_58], eax
0x1800028dd  mov     [rsp+80h+var_60], r9
0x1800028e2  mov     r9, [rbx+8]
0x1800028e6  call    WPP_SF__guid__guid_DD
0x1800028eb  mov     rcx, [rdi]
0x1800028ee  mov     rax, [rcx+10h]
0x1800028f2  test    byte ptr [rax+30h], 1
0x1800028f6  jz      loc_180002996
0x1800028fc  lea     rdx, [rbp+var_40]
0x180002900  call    ?GetAppState@BrokerEvent@Broker@@QEBA?AV?$shared_ptr@VState@ApplicationStateTable@Broker@@@std@@XZ; Broker::BrokerEvent::GetAppState(void)
0x180002905  mov     rcx, [rbp+var_40]
0x180002909  cmp     byte ptr [rcx+88h], 0
0x180002910  jnz     short loc_180002965
0x180002912  mov     rcx, cs:WPP_GLOBAL_Control
0x180002919  test    [rcx+1Ch], r15d
0x18000291d  jz      short loc_18000294E
0x18000291f  cmp     byte ptr [rcx+19h], 4
0x180002923  jb      short loc_18000294E
0x180002925  mov     edx, 40h ; '@'
0x18000292a  mov     rax, [rdi]
0x18000292d  mov     rcx, [rcx+10h]
0x180002931  mov     r9, [rax+10h]
0x180002935  mov     rax, [r9+10h]
0x180002939  mov     r8, rax
0x18000293c  shr     r8, 20h
0x180002940  mov     dword ptr [rsp+80h+var_58], r8d
0x180002945  mov     dword ptr [rsp+80h+var_60], eax
0x180002949  call    WPP_SF__guid_DD
0x18000294e  mov     rcx, [rbp+var_38]; this
0x180002952  test    rcx, rcx
0x180002955  jz      loc_180002AA0
0x18000295b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180002960  jmp     loc_180002AA0
0x180002965  cmp     byte ptr [rcx+89h], 0
0x18000296c  jnz     short loc_180002988
0x18000296e  mov     rcx, cs:WPP_GLOBAL_Control
0x180002975  test    [rcx+1Ch], r15d
0x180002979  jz      short loc_18000294E
0x18000297b  cmp     byte ptr [rcx+19h], 4
0x18000297f  jb      short loc_18000294E
0x180002981  mov     edx, 41h ; 'A'
0x180002986  jmp     short loc_18000292A
0x180002988  mov     rcx, [rbp+var_38]; this
0x18000298c  test    rcx, rcx
0x18000298f  jz      short loc_180002996
0x180002991  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180002996  cmp     qword ptr [rbx+88h], 0
0x18000299e  mov     r15d, 2
0x1800029a4  jz      loc_180002A76
0x1800029aa  mov     eax, cs:dword_180028000
0x1800029b0  cmp     eax, 4
0x1800029b3  jbe     short loc_1800029FF
0x1800029b5  mov     edx, r15d
0x1800029b8  call    _tlgKeywordOn
0x1800029bd  test    al, al
0x1800029bf  jz      short loc_1800029FF
0x1800029c1  mov     rax, [rdi]
0x1800029c4  lea     rdx, byte_180022173
0x1800029cb  mov     byte ptr [rbp+arg_10], sil
0x1800029cf  mov     rcx, [rax+10h]
0x1800029d3  mov     rax, [rbx+8]
0x1800029d7  mov     [rbp+var_40], rax
0x1800029db  lea     rax, [rbp+arg_10]
0x1800029df  mov     [rsp+80h+var_50], rax
0x1800029e4  lea     rax, [rbp+arg_18]
0x1800029e8  mov     [rsp+80h+var_58], rax
0x1800029ed  lea     rax, [rbp+var_40]
0x1800029f1  mov     [rsp+80h+var_60], rax
0x1800029f6  mov     [rbp+arg_18], rcx
0x1800029fa  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$00@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$00@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<1> const &)
0x1800029ff  mov     r8, [rdi]
0x180002a02  mov     ecx, esi
0x180002a04  mov     rdx, [rbx+8]
0x180002a08  mov     rax, [rbx+88h]
0x180002a0f  mov     r9, [r8+28h]
0x180002a13  mov     r8, [r8+10h]
0x180002a17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a1c  mov     ecx, cs:dword_180028000
0x180002a22  mov     esi, eax
0x180002a24  cmp     ecx, 4
0x180002a27  jbe     short loc_180002A72
0x180002a29  mov     rdx, r15
0x180002a2c  call    _tlgKeywordOn
0x180002a31  test    al, al
0x180002a33  jz      short loc_180002A72
0x180002a35  mov     rax, [rbx+8]
0x180002a39  mov     rcx, [rdi]
0x180002a3c  mov     [rbp+var_40], rax
0x180002a40  lea     rax, [rbp+arg_10]
0x180002a44  mov     [rsp+80h+var_50], rax
0x180002a49  lea     rax, [rbp+arg_18]
0x180002a4d  mov     [rsp+80h+var_58], rax
0x180002a52  lea     rax, [rbp+var_40]
0x180002a56  mov     [rbp+arg_10], esi
0x180002a59  mov     rdx, [rcx+10h]
0x180002a5d  mov     [rbp+arg_18], rdx
0x180002a61  lea     rdx, byte_180022039
0x180002a68  mov     [rsp+80h+var_60], rax
0x180002a6d  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &)
0x180002a72  test    esi, esi
0x180002a74  jnz     short loc_180002AB8
0x180002a76  mov     rax, [rdi]
0x180002a79  or      [rax+18h], r15d
0x180002a7d  mov     rax, [rbx+68h]
0x180002a81  test    rax, rax
0x180002a84  jz      short loc_180002AA0
0x180002a86  cmp     qword ptr [rbx+88h], 0
0x180002a8e  jnz     short loc_180002AA0
0x180002a90  mov     rdx, [rdi]
0x180002a93  mov     rcx, [rbx+8]
0x180002a97  mov     rdx, [rdx+10h]
0x180002a9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002aa0  lea     r11, [rsp+80h+var_s0]
0x180002aa8  mov     rbx, [r11+20h]
0x180002aac  mov     rsi, [r11+28h]
0x180002ab0  mov     rsp, r11
0x180002ab3  pop     r15
0x180002ab5  pop     rdi
0x180002ab6  pop     rbp
0x180002ab7  retn
0x180002ab8  mov     edx, esi; unsigned int
0x180002aba  lea     rcx, [rbp+pExceptionObject]; this
0x180002abe  call    ??0Win32Error@Broker@@QEAA@K@Z; Broker::Win32Error::Win32Error(ulong)
0x180002ac3  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x180002aca  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180002ace  call    _CxxThrowException_0
```
