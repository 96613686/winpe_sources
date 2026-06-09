# BrQueryBrokeredEvents2

- ea: `0x1800124b0`
- end: `0x180012659`
- name: `BrQueryBrokeredEvents2`
- size: `425`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180003a60`
- `0x180004ae0`
- `0x1800058e0`
- `0x180009e94`
- `0x18000f978`
- `0x1800124b0`
- `0x1800126e0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall BrQueryBrokeredEvents2(
        __int128 *a1,
        char *a2,
        const unsigned __int16 *a3,
        int a4,
        unsigned int *a5,
        struct _BROKERED_EVENT ***a6)
{
  unsigned int *v9; // rdi
  unsigned int v10; // ebx
  struct _BROKERED_EVENT ***v11; // rsi
  __int128 *v12; // r8
  __int64 v13; // r9
  __int64 v14; // rcx
  Broker::BrokerBase *v15; // r8
  __int64 v16; // r9
  int v18; // [rsp+50h] [rbp-58h] BYREF
  unsigned int v19; // [rsp+54h] [rbp-54h] BYREF
  const WCHAR *v20; // [rsp+58h] [rbp-50h] BYREF
  Broker::BrokerBase *v21; // [rsp+60h] [rbp-48h] BYREF
  std::_Ref_count_base *v22; // [rsp+68h] [rbp-40h]
  Broker::Win32Error *v23; // [rsp+70h] [rbp-38h] BYREF
  __int128 *v24; // [rsp+B0h] [rbp+8h] BYREF
  const WCHAR *v25; // [rsp+C0h] [rbp+18h]
  int v26; // [rsp+C8h] [rbp+20h]

  v26 = a4;
  v25 = a3;
  v24 = a1;
  if ( !a1 || (v9 = a5) == 0 || (v10 = 0, (v11 = a6) == 0) )
  {
    v10 = 87;
LABEL_10:
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_8595d4a22dff35b4ac96cc1b50bbb660_Traceguids, v10);
    goto LABEL_13;
  }
  try
  {
    Broker::BrokerBase::GetInstance(&v21, a1);
    Broker::BrokerBase::QueryEventsNoLock(v21, a3, a2, a4, v9, v11);
    if ( v22 )
      std::_Ref_count_base::_Decref(v22);
  }
  catch ( std::bad_alloc )
  {
    v18 = 14;
    v10 = 14;
    goto LABEL_10;
  }
  catch ( Broker::InvalidParameter )
  {
    v18 = 87;
    v10 = 87;
    goto LABEL_10;
  }
  catch ( Broker::Win32Error *v23 )
  {
    v18 = *((_DWORD *)v23 + 8);
    v10 = v18;
    if ( !v18 )
      goto LABEL_13;
    goto LABEL_10;
  }
  catch ( ... )
  {
    v18 = 1287;
    v10 = 1287;
    goto LABEL_10;
  }
LABEL_13:
  if ( dword_180028000 )
  {
    v12 = &BLP_TRACELOGGING_INVALID_GUID;
    if ( v24 )
      v12 = v24;
    if ( a5 )
      v13 = *a5;
    else
      v13 = 0xFFFFFFFFLL;
    if ( (unsigned int)dword_180028000 > 4 && (unsigned __int8)tlgKeywordOn(v24, 8, v12, v13) )
    {
      LODWORD(v24) = v16;
      v18 = v26;
      v20 = v25;
      v19 = v10;
      v21 = v15;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v14,
        byte_180021C01,
        (__int64)v15,
        v16,
        (__int64 *)&v21,
        (__int64)&v19,
        &v20,
        (__int64)&v18,
        (__int64)&v24);
    }
  }
  return v10;
}

```

## disassembly

```asm
0x1800124b0  mov     rax, rsp
0x1800124b3  mov     [rax+10h], rbx
0x1800124b7  mov     [rax+20h], r9d
0x1800124bb  mov     [rax+18h], r8
0x1800124bf  mov     [rax+8], rcx
0x1800124c3  push    rsi
0x1800124c4  push    rdi
0x1800124c5  push    r12
0x1800124c7  push    r14
0x1800124c9  push    r15
0x1800124cb  sub     rsp, 80h
0x1800124d2  mov     r14d, r9d
0x1800124d5  mov     r15, r8
0x1800124d8  mov     r12, rdx
0x1800124db  test    rcx, rcx
0x1800124de  jz      short loc_180012549
0x1800124e0  mov     rdi, [rsp+0A8h+arg_20]
0x1800124e8  test    rdi, rdi
0x1800124eb  jz      short loc_180012549
0x1800124ed  xor     ebx, ebx
0x1800124ef  mov     rsi, [rsp+0A8h+arg_28]
0x1800124f7  test    rsi, rsi
0x1800124fa  jz      short loc_180012549
0x1800124fc  mov     rdx, rcx
0x1800124ff  lea     rcx, [rax-48h]
0x180012503  call    ?GetInstance@BrokerBase@Broker@@SA?AV?$shared_ptr@VBrokerBase@Broker@@@std@@AEBU_GUID@@@Z; Broker::BrokerBase::GetInstance(_GUID const &)
0x180012508  nop
0x180012509  mov     [rsp+0A8h+var_80], rsi; struct _BROKERED_EVENT ***
0x18001250e  mov     [rsp+0A8h+var_88], rdi; unsigned int *
0x180012513  mov     r9d, r14d; unsigned int
0x180012516  mov     r8, r12; void *
0x180012519  mov     rdx, r15; unsigned __int16 *
0x18001251c  mov     rcx, [rsp+0A8h+var_48]; this
0x180012521  call    ?QueryEventsNoLock@BrokerBase@Broker@@QEAAXPEBGPEAXKPEAKPEAPEAPEAU_BROKERED_EVENT@@@Z; Broker::BrokerBase::QueryEventsNoLock(ushort const *,void *,ulong,ulong *,_BROKERED_EVENT * * *)
0x180012526  nop
0x180012527  mov     rcx, [rsp+0A8h+var_40]; this
0x18001252c  test    rcx, rcx
0x18001252f  jz      short loc_180012537
0x180012531  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180012536  nop
0x180012537  jmp     short loc_18001257C
0x180012539  mov     ebx, [rsp+0A8h+var_58]
0x18001253d  jmp     short loc_18001254E
0x18001253f  mov     ebx, [rsp+0A8h+var_58]
0x180012543  test    ebx, ebx
0x180012545  jnz     short loc_18001254E
0x180012547  jmp     short loc_18001257C
0x180012549  mov     ebx, 57h ; 'W'
0x18001254e  mov     rcx, cs:WPP_GLOBAL_Control
0x180012555  test    dword ptr [rcx+1Ch], 800h
0x18001255c  jz      short loc_18001257C
0x18001255e  cmp     byte ptr [rcx+19h], 2
0x180012562  jb      short loc_18001257C
0x180012564  mov     edx, 20h ; ' '
0x180012569  mov     r9d, ebx
0x18001256c  lea     r8, WPP_8595d4a22dff35b4ac96cc1b50bbb660_Traceguids
0x180012573  mov     rcx, [rcx+10h]
0x180012577  call    WPP_SF_d
0x18001257c  mov     eax, cs:dword_180028000
0x180012582  test    eax, eax
0x180012584  jz      loc_18001263F
0x18001258a  mov     rcx, [rsp+0A8h+arg_0]
0x180012592  lea     r8, BLP_TRACELOGGING_INVALID_GUID
0x180012599  test    rcx, rcx
0x18001259c  cmovnz  r8, rcx
0x1800125a0  cmp     [rsp+0A8h+arg_20], 0
0x1800125a9  jnz     short loc_1800125B1
0x1800125ab  or      r9d, 0FFFFFFFFh
0x1800125af  jmp     short loc_1800125BC
0x1800125b1  mov     rax, [rsp+0A8h+arg_20]
0x1800125b9  mov     r9d, [rax]
0x1800125bc  mov     eax, cs:dword_180028000
0x1800125c2  cmp     eax, 4
0x1800125c5  jbe     short loc_18001263F
0x1800125c7  mov     edx, 8
0x1800125cc  call    _tlgKeywordOn
0x1800125d1  test    al, al
0x1800125d3  jz      short loc_18001263F
0x1800125d5  mov     dword ptr [rsp+0A8h+arg_0], r9d
0x1800125dd  mov     eax, [rsp+0A8h+arg_18]
0x1800125e4  mov     [rsp+0A8h+var_58], eax
0x1800125e8  mov     rax, [rsp+0A8h+arg_10]
0x1800125f0  mov     [rsp+0A8h+var_50], rax
0x1800125f5  mov     [rsp+0A8h+var_54], ebx
0x1800125f9  mov     [rsp+0A8h+var_48], r8
0x1800125fe  lea     rax, [rsp+0A8h+arg_0]
0x180012606  mov     [rsp+0A8h+var_68], rax
0x18001260b  lea     rax, [rsp+0A8h+var_58]
0x180012610  mov     [rsp+0A8h+var_70], rax
0x180012615  lea     rax, [rsp+0A8h+var_50]
0x18001261a  mov     [rsp+0A8h+var_78], rax
0x18001261f  lea     rax, [rsp+0A8h+var_54]
0x180012624  mov     [rsp+0A8h+var_80], rax
0x180012629  lea     rax, [rsp+0A8h+var_48]
0x18001262e  mov     [rsp+0A8h+var_88], rax
0x180012633  lea     rdx, byte_180021C01
0x18001263a  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@44@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001263f  mov     eax, ebx
0x180012641  mov     rbx, [rsp+0A8h+arg_8]
0x180012649  add     rsp, 80h
0x180012650  pop     r15
0x180012652  pop     r14
0x180012654  pop     r12
0x180012656  pop     rdi
0x180012657  pop     rsi
0x180012658  retn
```
