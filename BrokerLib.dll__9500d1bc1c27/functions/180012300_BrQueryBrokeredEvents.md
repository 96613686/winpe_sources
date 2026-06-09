# BrQueryBrokeredEvents

- ea: `0x180012300`
- end: `0x1800124a0`
- name: `BrQueryBrokeredEvents`
- size: `416`
- prototype: `__int64 __fastcall(std::_Ref_count_base *, void *, const unsigned __int16 *, unsigned int, unsigned int *, struct _GUID **)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180004ae0`
- `0x1800058e0`
- `0x180009e94`
- `0x18000efc4`
- `0x18000f978`
- `0x180012300`
- `0x1800126e0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall BrQueryBrokeredEvents(
        std::_Ref_count_base *a1,
        char *a2,
        const unsigned __int16 *a3,
        int a4,
        unsigned int *a5,
        struct _GUID **a6)
{
  std::_Ref_count_base *v9; // rdi
  unsigned int *v10; // rsi
  unsigned int v11; // ebx
  struct _GUID **v12; // r14
  __int128 *v13; // r8
  __int64 v14; // r9
  __int64 v15; // rcx
  Broker::BrokerBase *v16; // r8
  __int64 v17; // r9
  int v19; // [rsp+50h] [rbp-68h] BYREF
  unsigned int v20; // [rsp+54h] [rbp-64h] BYREF
  const WCHAR *v21; // [rsp+58h] [rbp-60h] BYREF
  Broker::BrokerBase *v22; // [rsp+60h] [rbp-58h] BYREF
  std::_Ref_count_base *v23; // [rsp+68h] [rbp-50h]
  Broker::Win32Error *v24; // [rsp+70h] [rbp-48h] BYREF
  std::_Ref_count_base *v25; // [rsp+C0h] [rbp+8h] BYREF
  const WCHAR *v26; // [rsp+D0h] [rbp+18h]
  int v27; // [rsp+D8h] [rbp+20h]

  v27 = a4;
  v26 = a3;
  v25 = a1;
  v9 = a1;
  if ( a1 && (v10 = a5) != 0 && (v11 = 0, (v12 = a6) != 0) )
  {
    try
    {
      Broker::BrokerBase::GetInstance(&v22, a1);
      Broker::BrokerBase::QueryEvents(v22, a3, a2, a4, v10, v12);
      a1 = v23;
      if ( v23 )
        std::_Ref_count_base::_Decref(v23);
    }
    catch ( std::bad_alloc )
    {
      v19 = 14;
      v9 = v25;
      v11 = 14;
    }
    catch ( Broker::InvalidParameter )
    {
      v19 = 87;
      v9 = v25;
      v11 = 87;
    }
    catch ( Broker::Win32Error *v24 )
    {
      a1 = (std::_Ref_count_base *)*((unsigned int *)v24 + 8);
      v19 = *((_DWORD *)v24 + 8);
      v9 = v25;
      v11 = v19;
    }
    catch ( ... )
    {
      v19 = 1287;
      v9 = v25;
      v11 = 1287;
    }
  }
  else
  {
    v11 = 87;
  }
  if ( dword_180028000 )
  {
    v13 = &BLP_TRACELOGGING_INVALID_GUID;
    if ( v9 )
      v13 = (__int128 *)v9;
    if ( a5 )
      v14 = *a5;
    else
      v14 = 0xFFFFFFFFLL;
    if ( (unsigned int)dword_180028000 > 4 && (unsigned __int8)tlgKeywordOn(a1, 8, v13, v14) )
    {
      LODWORD(v25) = v17;
      v19 = v27;
      v21 = v26;
      v20 = v11;
      v22 = v16;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v15,
        byte_180021CE0,
        (__int64)v16,
        v17,
        (__int64 *)&v22,
        (__int64)&v20,
        &v21,
        (__int64)&v19,
        (__int64)&v25);
    }
  }
  if ( v11 && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_8595d4a22dff35b4ac96cc1b50bbb660_Traceguids, v11);
  return v11;
}

```

## disassembly

```asm
0x180012300  mov     rax, rsp
0x180012303  mov     [rax+20h], r9d
0x180012307  mov     [rax+18h], r8
0x18001230b  mov     [rax+8], rcx
0x18001230f  push    rbx
0x180012310  push    rsi
0x180012311  push    rdi
0x180012312  push    r12
0x180012314  push    r13
0x180012316  push    r14
0x180012318  push    r15
0x18001231a  sub     rsp, 80h
0x180012321  mov     r15d, r9d
0x180012324  mov     r12, r8
0x180012327  mov     r13, rdx
0x18001232a  mov     rdi, rcx
0x18001232d  test    rcx, rcx
0x180012330  jz      short loc_180012399
0x180012332  mov     rsi, [rsp+0B8h+arg_20]
0x18001233a  test    rsi, rsi
0x18001233d  jz      short loc_180012399
0x18001233f  xor     ebx, ebx
0x180012341  mov     r14, [rsp+0B8h+arg_28]
0x180012349  test    r14, r14
0x18001234c  jz      short loc_180012399
0x18001234e  mov     rdx, rcx
0x180012351  lea     rcx, [rax-58h]
0x180012355  call    ?GetInstance@BrokerBase@Broker@@SA?AV?$shared_ptr@VBrokerBase@Broker@@@std@@AEBU_GUID@@@Z; Broker::BrokerBase::GetInstance(_GUID const &)
0x18001235a  nop
0x18001235b  mov     [rsp+0B8h+var_90], r14; struct _GUID **
0x180012360  mov     [rsp+0B8h+var_98], rsi; unsigned int *
0x180012365  mov     r9d, r15d; unsigned int
0x180012368  mov     r8, r13; void *
0x18001236b  mov     rdx, r12; unsigned __int16 *
0x18001236e  mov     rcx, [rsp+0B8h+var_58]; this
0x180012373  call    ?QueryEvents@BrokerBase@Broker@@QEAAXPEBGPEAXKPEAKPEAPEAU_GUID@@@Z; Broker::BrokerBase::QueryEvents(ushort const *,void *,ulong,ulong *,_GUID * *)
0x180012378  nop
0x180012379  mov     rcx, [rsp+0B8h+var_50]; this
0x18001237e  test    rcx, rcx
0x180012381  jz      short loc_180012389
0x180012383  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180012388  nop
0x180012389  jmp     short loc_18001239E
0x18001238b  mov     rdi, [rsp+0B8h+arg_0]
0x180012393  mov     ebx, [rsp+0B8h+var_68]
0x180012397  jmp     short loc_18001239E
0x180012399  mov     ebx, 57h ; 'W'
0x18001239e  mov     eax, cs:dword_180028000
0x1800123a4  test    eax, eax
0x1800123a6  jz      loc_180012459
0x1800123ac  lea     r8, BLP_TRACELOGGING_INVALID_GUID
0x1800123b3  test    rdi, rdi
0x1800123b6  cmovnz  r8, rdi
0x1800123ba  cmp     [rsp+0B8h+arg_20], 0
0x1800123c3  jnz     short loc_1800123CB
0x1800123c5  or      r9d, 0FFFFFFFFh
0x1800123c9  jmp     short loc_1800123D6
0x1800123cb  mov     rax, [rsp+0B8h+arg_20]
0x1800123d3  mov     r9d, [rax]
0x1800123d6  mov     eax, cs:dword_180028000
0x1800123dc  cmp     eax, 4
0x1800123df  jbe     short loc_180012459
0x1800123e1  mov     edx, 8
0x1800123e6  call    _tlgKeywordOn
0x1800123eb  test    al, al
0x1800123ed  jz      short loc_180012459
0x1800123ef  mov     dword ptr [rsp+0B8h+arg_0], r9d
0x1800123f7  mov     eax, [rsp+0B8h+arg_18]
0x1800123fe  mov     [rsp+0B8h+var_68], eax
0x180012402  mov     rax, [rsp+0B8h+arg_10]
0x18001240a  mov     [rsp+0B8h+var_60], rax
0x18001240f  mov     [rsp+0B8h+var_64], ebx
0x180012413  mov     [rsp+0B8h+var_58], r8
0x180012418  lea     rax, [rsp+0B8h+arg_0]
0x180012420  mov     [rsp+0B8h+var_78], rax
0x180012425  lea     rax, [rsp+0B8h+var_68]
0x18001242a  mov     [rsp+0B8h+var_80], rax
0x18001242f  lea     rax, [rsp+0B8h+var_60]
0x180012434  mov     [rsp+0B8h+var_88], rax
0x180012439  lea     rax, [rsp+0B8h+var_64]
0x18001243e  mov     [rsp+0B8h+var_90], rax
0x180012443  lea     rax, [rsp+0B8h+var_58]
0x180012448  mov     [rsp+0B8h+var_98], rax
0x18001244d  lea     rdx, byte_180021CE0
0x180012454  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@44@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180012459  test    ebx, ebx
0x18001245b  jz      short loc_18001248B
0x18001245d  mov     rcx, cs:WPP_GLOBAL_Control
0x180012464  test    dword ptr [rcx+1Ch], 800h
0x18001246b  jz      short loc_18001248B
0x18001246d  cmp     byte ptr [rcx+19h], 2
0x180012471  jb      short loc_18001248B
0x180012473  mov     edx, 1Fh
0x180012478  mov     r9d, ebx
0x18001247b  lea     r8, WPP_8595d4a22dff35b4ac96cc1b50bbb660_Traceguids
0x180012482  mov     rcx, [rcx+10h]
0x180012486  call    WPP_SF_d
0x18001248b  mov     eax, ebx
0x18001248d  add     rsp, 80h
0x180012494  pop     r15
0x180012496  pop     r14
0x180012498  pop     r13
0x18001249a  pop     r12
0x18001249c  pop     rdi
0x18001249d  pop     rsi
0x18001249e  pop     rbx
0x18001249f  retn
```
