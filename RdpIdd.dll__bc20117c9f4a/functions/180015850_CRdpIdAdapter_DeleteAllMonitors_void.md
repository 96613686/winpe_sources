# CRdpIdAdapter::DeleteAllMonitors(void)

- ea: `0x180015850`
- end: `0x180015a80`
- name: `?DeleteAllMonitors@CRdpIdAdapter@@AEAAXXZ`
- size: `560`
- prototype: `void __fastcall(CRdpIdAdapter *__hidden this)`
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18001a860`
- `0x18001adec`
- `0x18001d938`

## callees

- `0x180001af0`
- `0x18000402c`
- `0x18000d614`
- `0x18000e5e4`
- `0x180012f34`
- `0x180015850`
- `0x180021570`
- `0x180027168`

## string_xrefs

- `0x180015938`: `AdapterDeleteMonitors: %d`
- `0x180015931`: `CRdpIdAdapter::DeleteAllMonitors`

## pseudocode

```c
void __fastcall CRdpIdAdapter::DeleteAllMonitors(CRdpIdAdapter *this)
{
  _DWORD *v2; // r8
  int v3; // r8d
  int v4; // r9d
  char *v5; // r14
  _DWORD *v6; // rdx
  __int64 *v7; // rbx
  __int64 *v8; // rsi
  __int64 *v9; // rdi
  __int64 *v10; // rax
  __int64 *v11; // rcx
  int v12; // r8d
  __int64 v13; // rax
  __int64 *i; // rax
  __int64 j; // rax
  _QWORD *v16; // rbx
  __int64 v17; // [rsp+50h] [rbp-10h] BYREF
  const char *v18; // [rsp+58h] [rbp-8h] BYREF
  int v19; // [rsp+A0h] [rbp+40h] BYREF
  __int64 v20; // [rsp+A8h] [rbp+48h] BYREF
  GUID *v21; // [rsp+B0h] [rbp+50h] BYREF
  const char *v22; // [rsp+B8h] [rbp+58h] BYREF

  v2 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
  if ( *v2 > 4u && (unsigned __int8)tlgKeywordOn(v2, 0x470000000000LL) )
  {
    v20 = *((_QWORD *)this + 21);
    v19 = *((_DWORD *)this + 129);
    v21 = &RdpIddLoggingProviderWithCorrelationId::g_CorrelationId;
    v22 = "RdpIdd";
    v18 = "Checkpoint";
    v17 = 0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
      v3,
      (unsigned int)word_18004DA62,
      v3,
      v4,
      (__int64)&v18,
      (__int64)&v17,
      (__int64)&v22,
      (__int64)&v21,
      (__int64)&v19,
      (__int64)&v20);
  }
  v5 = (char *)this + 160;
  Rdp::Modern::Utils::CInflightRecorder::pushN(
    (Rdp::Modern::Utils::CInflightRecorder *)&Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
    (wchar_t *)L"AdapterDeleteMonitors: %d",
    "CRdpIdAdapter::DeleteAllMonitors",
    "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
    0x432u,
    *((_QWORD *)this + 21));
  v7 = (__int64 *)*((_QWORD *)this + 20);
  v8 = (__int64 *)*v7;
  while ( v7 != v8 )
  {
    if ( *((_BYTE *)v7 + 25) )
    {
      v9 = (__int64 *)v7[2];
    }
    else
    {
      v9 = (__int64 *)*v7;
      if ( *(_BYTE *)(*v7 + 25) )
      {
        v10 = (__int64 *)v7[1];
        v9 = v7;
        if ( !*((_BYTE *)v10 + 25) )
        {
          v11 = v7;
          do
          {
            if ( v11 != (__int64 *)*v10 )
              break;
            v11 = v10;
            v9 = v10;
            v10 = (__int64 *)v10[1];
          }
          while ( !*((_BYTE *)v10 + 25) );
        }
        if ( !*((_BYTE *)v9 + 25) )
          v9 = v10;
      }
      else
      {
        while ( !*(_BYTE *)(v9[2] + 25) )
          v9 = (__int64 *)v9[2];
      }
    }
    CRdpIdMonitor::RemoveMonitor((CRdpIdMonitor *)v9[6], (char)v6);
    v6 = (_DWORD *)*((_QWORD *)this + 23);
    v12 = *(_DWORD *)(v9[6] + 284);
    v19 = v12;
    if ( v6 == *((_DWORD **)this + 24) )
    {
      std::vector<unsigned int>::_Emplace_reallocate<unsigned int>((char *)this + 176, v6, &v19);
    }
    else
    {
      *v6 = v12;
      *((_QWORD *)this + 23) += 4LL;
    }
    if ( *((_BYTE *)v7 + 25) )
    {
      v7 = (__int64 *)v7[2];
    }
    else
    {
      v13 = *v7;
      if ( *(_BYTE *)(*v7 + 25) )
      {
        for ( i = (__int64 *)v7[1]; !*((_BYTE *)i + 25) && v7 == (__int64 *)*i; i = (__int64 *)i[1] )
          v7 = i;
        if ( !*((_BYTE *)v7 + 25) )
          v7 = i;
      }
      else
      {
        v7 = (__int64 *)*v7;
        for ( j = *(_QWORD *)(v13 + 16); !*(_BYTE *)(j + 25); j = v7[2] )
          v7 = (__int64 *)v7[2];
      }
    }
  }
  v16 = *(_QWORD **)v5;
  std::_Tree_val<std::_Tree_simple_types<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>,void *>>>(
    (char *)this + 160,
    (char *)this + 160,
    *(_QWORD *)(*(_QWORD *)v5 + 8LL));
  v16[1] = v16;
  *v16 = v16;
  v16[2] = v16;
  *((_QWORD *)this + 21) = 0;
}

```

## disassembly

```asm
0x180015850  push    rbp
0x180015852  push    rbx
0x180015853  push    rsi
0x180015854  push    rdi
0x180015855  push    r12
0x180015857  push    r14
0x180015859  push    r15
0x18001585b  mov     rbp, rsp
0x18001585e  sub     rsp, 60h
0x180015862  mov     r15, rcx
0x180015865  call    ?get@?$static_lazy@VRdpIddLoggingProvider@@@details@wil@@QEAAPEAVRdpIddLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<RdpIddLoggingProvider>::get(void (*)(void))
0x18001586a  xor     r12d, r12d
0x18001586d  mov     r8, [rax+8]
0x180015871  mov     eax, [r8]
0x180015874  cmp     eax, 4
0x180015877  jbe     loc_18001591A
0x18001587d  mov     rdx, 470000000000h
0x180015887  mov     rcx, r8
0x18001588a  call    _tlgKeywordOn
0x18001588f  test    al, al
0x180015891  jz      loc_18001591A
0x180015897  mov     rax, [r15+0A8h]
0x18001589e  lea     rdx, word_18004DA62
0x1800158a5  mov     [rbp+arg_8], rax
0x1800158a9  mov     rcx, r8
0x1800158ac  mov     eax, [r15+204h]
0x1800158b3  mov     [rbp+arg_0], eax
0x1800158b6  lea     rax, ?g_CorrelationId@RdpIddLoggingProviderWithCorrelationId@@2U_GUID@@A; _GUID RdpIddLoggingProviderWithCorrelationId::g_CorrelationId
0x1800158bd  mov     [rbp+arg_10], rax
0x1800158c1  lea     rax, aRdpidd; "RdpIdd"
0x1800158c8  mov     [rbp+arg_18], rax
0x1800158cc  lea     rax, aCheckpoint; "Checkpoint"
0x1800158d3  mov     [rbp+var_8], rax
0x1800158d7  lea     rax, [rbp+arg_8]
0x1800158db  mov     [rsp+60h+var_18], rax
0x1800158e0  lea     rax, [rbp+arg_0]
0x1800158e4  mov     [rsp+60h+var_20], rax
0x1800158e9  lea     rax, [rbp+arg_10]
0x1800158ed  mov     [rsp+60h+var_28], rax
0x1800158f2  lea     rax, [rbp+arg_18]
0x1800158f6  mov     [rsp+60h+var_30], rax
0x1800158fb  lea     rax, [rbp+var_10]
0x1800158ff  mov     [rsp+60h+var_38], rax
0x180015904  lea     rax, [rbp+var_8]
0x180015908  mov     qword ptr [rsp+60h+var_40], rax
0x18001590d  mov     [rbp+var_10], 1000000h
0x180015915  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x18001591a  lea     r14, [r15+0A0h]
0x180015921  mov     rax, [r14+8]
0x180015925  lea     r9, aOnecoreuapTerm_15; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x18001592c  mov     [rsp+60h+var_38], rax
0x180015931  lea     r8, aCrdpidadapterD_0; "CRdpIdAdapter::DeleteAllMonitors"
0x180015938  lea     rdx, aAdapterdeletem; "AdapterDeleteMonitors: %d"
0x18001593f  mov     [rsp+60h+var_40], 432h; unsigned int
0x180015947  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x18001594e  call    ?pushN@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1IZZ; Rdp::Modern::Utils::CInflightRecorder::pushN(ushort const *,char const *,char const *,uint,...)
0x180015953  mov     rbx, [r14]
0x180015956  mov     rsi, [rbx]
0x180015959  cmp     rbx, rsi
0x18001595c  jz      loc_180015A4F
0x180015962  cmp     [rbx+19h], r12b
0x180015966  jz      short loc_18001596E
0x180015968  mov     rdi, [rbx+10h]
0x18001596c  jmp     short loc_1800159B5
0x18001596e  mov     rdi, [rbx]
0x180015971  cmp     [rdi+19h], r12b
0x180015975  jz      short loc_1800159AB
0x180015977  mov     rax, [rbx+8]
0x18001597b  mov     rdi, rbx
0x18001597e  cmp     [rax+19h], r12b
0x180015982  jnz     short loc_18001599C
0x180015984  mov     rcx, rbx
0x180015987  cmp     rcx, [rax]
0x18001598a  jnz     short loc_18001599C
0x18001598c  mov     rcx, rax
0x18001598f  mov     rdi, rax
0x180015992  mov     rax, [rax+8]
0x180015996  cmp     [rax+19h], r12b
0x18001599a  jz      short loc_180015987
0x18001599c  cmp     [rdi+19h], r12b
0x1800159a0  jnz     short loc_1800159B5
0x1800159a2  mov     rdi, rax
0x1800159a5  jmp     short loc_1800159B5
0x1800159a7  mov     rdi, [rdi+10h]
0x1800159ab  mov     rax, [rdi+10h]
0x1800159af  cmp     [rax+19h], r12b
0x1800159b3  jz      short loc_1800159A7
0x1800159b5  mov     rcx, [rdi+30h]; this
0x1800159b9  call    ?RemoveMonitor@CRdpIdMonitor@@QEAAX_N@Z; CRdpIdMonitor::RemoveMonitor(bool)
0x1800159be  mov     rax, [rdi+30h]
0x1800159c2  lea     rcx, [r15+0B0h]
0x1800159c9  mov     rdx, [rcx+8]
0x1800159cd  mov     r8d, [rax+11Ch]
0x1800159d4  mov     [rbp+arg_0], r8d
0x1800159d8  cmp     rdx, [rcx+10h]
0x1800159dc  jz      short loc_1800159E8
0x1800159de  mov     [rdx], r8d
0x1800159e1  add     qword ptr [rcx+8], 4
0x1800159e6  jmp     short loc_1800159F1
0x1800159e8  lea     r8, [rbp+arg_0]
0x1800159ec  call    ??$_Emplace_reallocate@I@?$vector@IV?$allocator@I@std@@@std@@AEAAPEAIQEAI$$QEAI@Z; std::vector<uint>::_Emplace_reallocate<uint>(uint * const,uint &&)
0x1800159f1  cmp     [rbx+19h], r12b
0x1800159f5  jz      short loc_180015A00
0x1800159f7  mov     rbx, [rbx+10h]
0x1800159fb  jmp     loc_180015959
0x180015a00  mov     rax, [rbx]
0x180015a03  cmp     [rax+19h], r12b
0x180015a07  jz      short loc_180015A33
0x180015a09  mov     rax, [rbx+8]
0x180015a0d  jmp     short loc_180015A1B
0x180015a0f  cmp     rbx, [rax]
0x180015a12  jnz     short loc_180015A21
0x180015a14  mov     rbx, rax
0x180015a17  mov     rax, [rax+8]
0x180015a1b  cmp     [rax+19h], r12b
0x180015a1f  jz      short loc_180015A0F
0x180015a21  cmp     [rbx+19h], r12b
0x180015a25  jnz     loc_180015959
0x180015a2b  mov     rbx, rax
0x180015a2e  jmp     loc_180015959
0x180015a33  mov     rbx, rax
0x180015a36  mov     rax, [rax+10h]
0x180015a3a  jmp     short loc_180015A44
0x180015a3c  mov     rbx, [rbx+10h]
0x180015a40  mov     rax, [rbx+10h]
0x180015a44  cmp     [rax+19h], r12b
0x180015a48  jz      short loc_180015A3C
0x180015a4a  jmp     loc_180015959
0x180015a4f  mov     rbx, [r14]
0x180015a52  mov     rdx, r14
0x180015a55  mov     rcx, r14
0x180015a58  mov     r8, [rbx+8]
0x180015a5c  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBURDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBURDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBURDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBURDP_MONITORCONFIG_MONITOR_ID@@V?$shared_ptr@VCRdpIdMonitor@@@std@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>,void *>>>(std::allocator<std::_Tree_node<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>,void *>> &,std::_Tree_node<std::pair<RDP_MONITORCONFIG_MONITOR_ID const,std::shared_ptr<CRdpIdMonitor>>,void *> *)
0x180015a61  mov     [rbx+8], rbx
0x180015a65  mov     [rbx], rbx
0x180015a68  mov     [rbx+10h], rbx
0x180015a6c  mov     [r14+8], r12
0x180015a70  add     rsp, 60h
0x180015a74  pop     r15
0x180015a76  pop     r14
0x180015a78  pop     r12
0x180015a7a  pop     rdi
0x180015a7b  pop     rsi
0x180015a7c  pop     rbx
0x180015a7d  pop     rbp
0x180015a7e  retn
```
