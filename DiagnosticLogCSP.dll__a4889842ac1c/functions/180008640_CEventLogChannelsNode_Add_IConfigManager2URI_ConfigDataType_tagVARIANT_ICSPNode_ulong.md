# CEventLogChannelsNode::Add(IConfigManager2URI *,ConfigDataType,tagVARIANT,ICSPNode * *,ulong *)

- ea: `0x180008640`
- end: `0x18000879e`
- name: `?Add@CEventLogChannelsNode@@UEAAJPEAUIConfigManager2URI@@W4ConfigDataType@@UtagVARIANT@@PEAPEAUICSPNode@@PEAK@Z`
- size: `350`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, struct ICSPNode **, unsigned int *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000108c`
- `0x180008640`
- `0x1800087b0`
- `0x180014640`
- `0x180014aac`
- `0x180037010`

## pseudocode

```c
__int64 __fastcall CEventLogChannelsNode::Add(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        struct ICSPNode **a5,
        unsigned int *a6)
{
  unsigned int v7; // r13d
  __int64 v9; // rdi
  struct ICSPNode **v10; // rsi
  unsigned int *v11; // r14
  int v12; // ebx
  const struct CSP_NODE_DATA *NodeMapEntryForURI; // rax
  int NodeInstance; // eax
  int v16; // [rsp+30h] [rbp-38h] BYREF
  struct IConfigManager2URI *v17; // [rsp+38h] [rbp-30h] BYREF
  __int128 v18; // [rsp+40h] [rbp-28h] BYREF
  __int64 v19; // [rsp+50h] [rbp-18h]
  int v20; // [rsp+B8h] [rbp+50h] BYREF

  v7 = a3;
  v9 = a1;
  v17 = 0;
  if ( a2 && (v10 = a5) != 0 && (v11 = a6) != 0 )
  {
    v12 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD, struct IConfigManager2URI **))(**(_QWORD **)(a1 + 24) + 168LL))(
            *(_QWORD *)(a1 + 24),
            a2,
            0,
            0,
            &v17);
    if ( v12 >= 0 )
    {
      a1 = *(_QWORD *)(*(_QWORD *)(v9 + 16) + 32LL);
      if ( a1 && (NodeMapEntryForURI = CspGetNodeMapEntryForURI((const struct CspNodeMapBase *)a1, v17)) != 0 )
      {
        *v10 = 0;
        *v11 = 0;
        if ( *(_DWORD *)(v9 + 44) == 13 )
        {
          NodeInstance = CEventLogChannelsNode::CreateNodeInstance(
                           *(struct CConfigServiceProvider2Impl **)(v9 + 16),
                           v17,
                           NodeMapEntryForURI,
                           1,
                           v10,
                           v11);
        }
        else
        {
          v18 = *(_OWORD *)a4;
          v19 = *(_QWORD *)(a4 + 16);
          NodeInstance = CCSPNodeImpl::Add(v9, a2, v7, (__int64)&v18, v10, v11);
        }
        v12 = NodeInstance;
      }
      else
      {
        v12 = -2046820335;
      }
    }
  }
  else
  {
    v12 = -2147024809;
  }
  if ( (unsigned int)dword_180048E90 > 5 )
  {
    v20 = v12;
    v16 = *(_DWORD *)(v9 + 44);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      a1,
      (__int64)byte_18003EA59,
      a3,
      a4,
      (__int64)&v16,
      (__int64)&v20);
  }
  if ( v17 )
    (*(void (__fastcall **)(struct IConfigManager2URI *))(*(_QWORD *)v17 + 16LL))(v17);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180008640  push    rbp
0x180008642  push    rbx
0x180008643  push    rsi
0x180008644  push    rdi
0x180008645  push    r12
0x180008647  push    r13
0x180008649  push    r14
0x18000864b  push    r15
0x18000864d  mov     rbp, rsp
0x180008650  sub     rsp, 68h
0x180008654  mov     r12, r9
0x180008657  mov     r13d, r8d
0x18000865a  mov     r15, rdx
0x18000865d  mov     rdi, rcx
0x180008660  mov     [rbp+var_30], 0
0x180008668  test    rdx, rdx
0x18000866b  jz      loc_18000873D
0x180008671  mov     rsi, [rbp+arg_20]
0x180008675  test    rsi, rsi
0x180008678  jz      loc_18000873D
0x18000867e  mov     r14, [rbp+arg_28]
0x180008682  test    r14, r14
0x180008685  jz      loc_18000873D
0x18000868b  mov     rcx, [rcx+18h]
0x18000868f  mov     rax, [rcx]
0x180008692  lea     rdx, [rbp+var_30]
0x180008696  mov     [rsp+68h+var_48], rdx
0x18000869b  xor     r9d, r9d
0x18000869e  xor     r8d, r8d
0x1800086a1  mov     rdx, r15
0x1800086a4  mov     rax, [rax+0A8h]
0x1800086ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800086b0  mov     ebx, eax
0x1800086b2  test    eax, eax
0x1800086b4  js      loc_180008742
0x1800086ba  mov     rax, [rdi+10h]
0x1800086be  mov     rcx, [rax+20h]; struct CspNodeMapBase *
0x1800086c2  test    rcx, rcx
0x1800086c5  jz      short loc_180008736
0x1800086c7  mov     rdx, [rbp+var_30]; struct IConfigManager2URI *
0x1800086cb  call    ?CspGetNodeMapEntryForURI@@YAPEBUCSP_NODEMAP_ENTRY@@PEBVCspNodeMapBase@@PEAUIConfigManager2URI@@@Z; CspGetNodeMapEntryForURI(CspNodeMapBase const *,IConfigManager2URI *)
0x1800086d0  test    rax, rax
0x1800086d3  jz      short loc_180008736
0x1800086d5  mov     qword ptr [rsi], 0
0x1800086dc  mov     dword ptr [r14], 0
0x1800086e3  mov     [rsp+68h+var_40], r14; unsigned int *
0x1800086e8  mov     [rsp+68h+var_48], rsi; struct ICSPNode **
0x1800086ed  cmp     dword ptr [rdi+2Ch], 0Dh
0x1800086f1  jz      short loc_18000871E
0x1800086f3  movups  xmm0, xmmword ptr [r12]
0x1800086f8  movaps  [rbp+var_28], xmm0
0x1800086fc  movsd   xmm1, qword ptr [r12+10h]
0x180008703  movsd   [rbp+var_18], xmm1
0x180008708  lea     r9, [rbp+var_28]
0x18000870c  mov     r8d, r13d
0x18000870f  mov     rdx, r15
0x180008712  mov     rcx, rdi
0x180008715  call    ?Add@CCSPNodeImpl@@UEAAJPEAUIConfigManager2URI@@W4ConfigDataType@@UtagVARIANT@@PEAPEAUICSPNode@@PEAK@Z; CCSPNodeImpl::Add(IConfigManager2URI *,ConfigDataType,tagVARIANT,ICSPNode * *,ulong *)
0x18000871a  mov     ebx, eax
0x18000871c  jmp     short loc_180008742
0x18000871e  mov     r9d, 1; int
0x180008724  mov     r8, rax; struct CSP_NODE_DATA *
0x180008727  mov     rdx, [rbp+var_30]; struct IConfigManager2URI *
0x18000872b  mov     rcx, [rdi+10h]; struct CConfigServiceProvider2Impl *
0x18000872f  call    ?CreateNodeInstance@CEventLogChannelsNode@@SAJPEAVCConfigServiceProvider2Impl@@PEAUIConfigManager2URI@@PEBUCSP_NODE_DATA@@HPEAPEAUICSPNode@@PEAK@Z; CEventLogChannelsNode::CreateNodeInstance(CConfigServiceProvider2Impl *,IConfigManager2URI *,CSP_NODE_DATA const *,int,ICSPNode * *,ulong *)
0x180008734  jmp     short loc_18000871A
0x180008736  mov     ebx, 86000011h
0x18000873b  jmp     short loc_180008742
0x18000873d  mov     ebx, 80070057h
0x180008742  mov     eax, cs:dword_180048E90
0x180008748  cmp     eax, 5
0x18000874b  jbe     short loc_180008775
0x18000874d  mov     [rbp+arg_8], ebx
0x180008750  mov     eax, [rdi+2Ch]
0x180008753  mov     [rbp+var_38], eax
0x180008756  lea     rax, [rbp+arg_8]
0x18000875a  mov     [rsp+68h+var_40], rax
0x18000875f  lea     rax, [rbp+var_38]
0x180008763  mov     [rsp+68h+var_48], rax
0x180008768  lea     rdx, byte_18003EA59
0x18000876f  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180008774  nop
0x180008775  mov     rcx, [rbp+var_30]
0x180008779  test    rcx, rcx
0x18000877c  jz      short loc_18000878B
0x18000877e  mov     rax, [rcx]
0x180008781  mov     rax, [rax+10h]
0x180008785  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000878a  nop
0x18000878b  mov     eax, ebx
0x18000878d  add     rsp, 68h
0x180008791  pop     r15
0x180008793  pop     r14
0x180008795  pop     r13
0x180008797  pop     r12
0x180008799  pop     rdi
0x18000879a  pop     rsi
0x18000879b  pop     rbx
0x18000879c  pop     rbp
0x18000879d  retn
```
