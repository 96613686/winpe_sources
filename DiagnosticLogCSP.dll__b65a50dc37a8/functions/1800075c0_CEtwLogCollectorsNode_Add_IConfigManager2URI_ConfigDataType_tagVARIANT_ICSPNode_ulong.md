# CEtwLogCollectorsNode::Add(IConfigManager2URI *,ConfigDataType,tagVARIANT,ICSPNode * *,ulong *)

- ea: `0x1800075c0`
- end: `0x18000772f`
- name: `?Add@CEtwLogCollectorsNode@@UEAAJPEAUIConfigManager2URI@@W4ConfigDataType@@UtagVARIANT@@PEAPEAUICSPNode@@PEAK@Z`
- size: `367`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180001090`
- `0x1800075c0`
- `0x180007850`
- `0x180015100`
- `0x180015590`
- `0x180039010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CEtwLogCollectorsNode::Add(
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
        if ( *(_DWORD *)(v9 + 44) == 2 || *(_DWORD *)(v9 + 44) == 8 )
        {
          NodeInstance = CEtwLogCollectorsNode::CreateNodeInstance(
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
  if ( (unsigned int)dword_18004AE90 > 5 )
  {
    v20 = v12;
    v16 = *(_DWORD *)(v9 + 44);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      a1,
      (unsigned __int8 *)byte_180040881,
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
0x1800075c0  push    rbp
0x1800075c2  push    rbx
0x1800075c3  push    rsi
0x1800075c4  push    rdi
0x1800075c5  push    r12
0x1800075c7  push    r13
0x1800075c9  push    r14
0x1800075cb  push    r15
0x1800075cd  mov     rbp, rsp
0x1800075d0  sub     rsp, 68h
0x1800075d4  mov     r12, r9
0x1800075d7  mov     r13d, r8d
0x1800075da  mov     r15, rdx
0x1800075dd  mov     rdi, rcx
0x1800075e0  mov     [rbp+var_30], 0
0x1800075e8  test    rdx, rdx
0x1800075eb  jz      loc_1800076CD
0x1800075f1  mov     rsi, [rbp+arg_20]
0x1800075f5  test    rsi, rsi
0x1800075f8  jz      loc_1800076CD
0x1800075fe  mov     r14, [rbp+arg_28]
0x180007602  test    r14, r14
0x180007605  jz      loc_1800076CD
0x18000760b  mov     rcx, [rcx+18h]
0x18000760f  mov     rax, [rcx]
0x180007612  lea     rdx, [rbp+var_30]
0x180007616  mov     [rsp+68h+var_48], rdx
0x18000761b  xor     r9d, r9d
0x18000761e  xor     r8d, r8d
0x180007621  mov     rdx, r15
0x180007624  mov     rax, [rax+0A8h]
0x18000762b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007630  mov     ebx, eax
0x180007632  test    eax, eax
0x180007634  js      loc_1800076D2
0x18000763a  mov     rax, [rdi+10h]
0x18000763e  mov     rcx, [rax+20h]; struct CspNodeMapBase *
0x180007642  test    rcx, rcx
0x180007645  jz      short loc_1800076C6
0x180007647  mov     rdx, [rbp+var_30]; struct IConfigManager2URI *
0x18000764b  call    ?CspGetNodeMapEntryForURI@@YAPEBUCSP_NODEMAP_ENTRY@@PEBVCspNodeMapBase@@PEAUIConfigManager2URI@@@Z; CspGetNodeMapEntryForURI(CspNodeMapBase const *,IConfigManager2URI *)
0x180007650  test    rax, rax
0x180007653  jz      short loc_1800076C6
0x180007655  mov     qword ptr [rsi], 0
0x18000765c  mov     dword ptr [r14], 0
0x180007663  cmp     dword ptr [rdi+2Ch], 2
0x180007667  jz      short loc_1800076A4
0x180007669  cmp     dword ptr [rdi+2Ch], 8
0x18000766d  jz      short loc_1800076A4
0x18000766f  movups  xmm0, xmmword ptr [r12]
0x180007674  movaps  [rbp+var_28], xmm0
0x180007678  movsd   xmm1, qword ptr [r12+10h]
0x18000767f  movsd   [rbp+var_18], xmm1
0x180007684  mov     [rsp+68h+var_40], r14
0x180007689  mov     [rsp+68h+var_48], rsi
0x18000768e  lea     r9, [rbp+var_28]
0x180007692  mov     r8d, r13d
0x180007695  mov     rdx, r15
0x180007698  mov     rcx, rdi
0x18000769b  call    ?Add@CCSPNodeImpl@@UEAAJPEAUIConfigManager2URI@@W4ConfigDataType@@UtagVARIANT@@PEAPEAUICSPNode@@PEAK@Z; CCSPNodeImpl::Add(IConfigManager2URI *,ConfigDataType,tagVARIANT,ICSPNode * *,ulong *)
0x1800076a0  mov     ebx, eax
0x1800076a2  jmp     short loc_1800076D2
0x1800076a4  mov     [rsp+68h+var_40], r14; unsigned int *
0x1800076a9  mov     [rsp+68h+var_48], rsi; struct ICSPNode **
0x1800076ae  mov     r9d, 1; int
0x1800076b4  mov     r8, rax; struct CSP_NODE_DATA *
0x1800076b7  mov     rdx, [rbp+var_30]; struct IConfigManager2URI *
0x1800076bb  mov     rcx, [rdi+10h]; struct CConfigServiceProvider2Impl *
0x1800076bf  call    ?CreateNodeInstance@CEtwLogCollectorsNode@@SAJPEAVCConfigServiceProvider2Impl@@PEAUIConfigManager2URI@@PEBUCSP_NODE_DATA@@HPEAPEAUICSPNode@@PEAK@Z; CEtwLogCollectorsNode::CreateNodeInstance(CConfigServiceProvider2Impl *,IConfigManager2URI *,CSP_NODE_DATA const *,int,ICSPNode * *,ulong *)
0x1800076c4  jmp     short loc_1800076A0
0x1800076c6  mov     ebx, 86000011h
0x1800076cb  jmp     short loc_1800076D2
0x1800076cd  mov     ebx, 80070057h
0x1800076d2  mov     eax, cs:dword_18004AE90
0x1800076d8  cmp     eax, 5
0x1800076db  jbe     short loc_180007705
0x1800076dd  mov     [rbp+arg_8], ebx
0x1800076e0  mov     eax, [rdi+2Ch]
0x1800076e3  mov     [rbp+var_38], eax
0x1800076e6  lea     rax, [rbp+arg_8]
0x1800076ea  mov     [rsp+68h+var_40], rax
0x1800076ef  lea     rax, [rbp+var_38]
0x1800076f3  mov     [rsp+68h+var_48], rax
0x1800076f8  lea     rdx, byte_180040881
0x1800076ff  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180007704  nop
0x180007705  mov     rcx, [rbp+var_30]
0x180007709  test    rcx, rcx
0x18000770c  jz      short loc_18000771B
0x18000770e  mov     rax, [rcx]
0x180007711  mov     rax, [rax+10h]
0x180007715  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000771a  nop
0x18000771b  mov     eax, ebx
0x18000771d  add     rsp, 68h
0x180007721  pop     r15
0x180007723  pop     r14
0x180007725  pop     r13
0x180007727  pop     r12
0x180007729  pop     rdi
0x18000772a  pop     rsi
0x18000772b  pop     rbx
0x18000772c  pop     rbp
0x18000772d  retn
```
