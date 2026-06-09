# CEventLogChannelsNode::Add(IConfigManager2URI *,ConfigDataType,tagVARIANT,ICSPNode * *,ulong *)

- ea: `0x180008840`
- end: `0x18000899f`
- name: `?Add@CEventLogChannelsNode@@UEAAJPEAUIConfigManager2URI@@W4ConfigDataType@@UtagVARIANT@@PEAPEAUICSPNode@@PEAK@Z`
- size: `351`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180001090`
- `0x180008840`
- `0x1800089b0`
- `0x180015100`
- `0x180015590`
- `0x180039010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
                           *(_QWORD *)(v9 + 16),
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
      (unsigned __int8 *)byte_180040A59,
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
0x180008840  push    rbp
0x180008842  push    rbx
0x180008843  push    rsi
0x180008844  push    rdi
0x180008845  push    r12
0x180008847  push    r13
0x180008849  push    r14
0x18000884b  push    r15
0x18000884d  mov     rbp, rsp
0x180008850  sub     rsp, 68h
0x180008854  mov     r12, r9
0x180008857  mov     r13d, r8d
0x18000885a  mov     r15, rdx
0x18000885d  mov     rdi, rcx
0x180008860  mov     [rbp+var_30], 0
0x180008868  test    rdx, rdx
0x18000886b  jz      loc_18000893D
0x180008871  mov     rsi, [rbp+arg_20]
0x180008875  test    rsi, rsi
0x180008878  jz      loc_18000893D
0x18000887e  mov     r14, [rbp+arg_28]
0x180008882  test    r14, r14
0x180008885  jz      loc_18000893D
0x18000888b  mov     rcx, [rcx+18h]
0x18000888f  mov     rax, [rcx]
0x180008892  lea     rdx, [rbp+var_30]
0x180008896  mov     [rsp+68h+var_48], rdx
0x18000889b  xor     r9d, r9d
0x18000889e  xor     r8d, r8d
0x1800088a1  mov     rdx, r15
0x1800088a4  mov     rax, [rax+0A8h]
0x1800088ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800088b0  mov     ebx, eax
0x1800088b2  test    eax, eax
0x1800088b4  js      loc_180008942
0x1800088ba  mov     rax, [rdi+10h]
0x1800088be  mov     rcx, [rax+20h]; struct CspNodeMapBase *
0x1800088c2  test    rcx, rcx
0x1800088c5  jz      short loc_180008936
0x1800088c7  mov     rdx, [rbp+var_30]; struct IConfigManager2URI *
0x1800088cb  call    ?CspGetNodeMapEntryForURI@@YAPEBUCSP_NODEMAP_ENTRY@@PEBVCspNodeMapBase@@PEAUIConfigManager2URI@@@Z; CspGetNodeMapEntryForURI(CspNodeMapBase const *,IConfigManager2URI *)
0x1800088d0  test    rax, rax
0x1800088d3  jz      short loc_180008936
0x1800088d5  mov     qword ptr [rsi], 0
0x1800088dc  mov     dword ptr [r14], 0
0x1800088e3  mov     [rsp+68h+var_40], r14; unsigned int *
0x1800088e8  mov     [rsp+68h+var_48], rsi; struct ICSPNode **
0x1800088ed  cmp     dword ptr [rdi+2Ch], 0Dh
0x1800088f1  jz      short loc_18000891E
0x1800088f3  movups  xmm0, xmmword ptr [r12]
0x1800088f8  movaps  [rbp+var_28], xmm0
0x1800088fc  movsd   xmm1, qword ptr [r12+10h]
0x180008903  movsd   [rbp+var_18], xmm1
0x180008908  lea     r9, [rbp+var_28]
0x18000890c  mov     r8d, r13d
0x18000890f  mov     rdx, r15
0x180008912  mov     rcx, rdi
0x180008915  call    ?Add@CCSPNodeImpl@@UEAAJPEAUIConfigManager2URI@@W4ConfigDataType@@UtagVARIANT@@PEAPEAUICSPNode@@PEAK@Z; CCSPNodeImpl::Add(IConfigManager2URI *,ConfigDataType,tagVARIANT,ICSPNode * *,ulong *)
0x18000891a  mov     ebx, eax
0x18000891c  jmp     short loc_180008942
0x18000891e  mov     r9d, 1; int
0x180008924  mov     r8, rax; struct CSP_NODE_DATA *
0x180008927  mov     rdx, [rbp+var_30]; struct IConfigManager2URI *
0x18000892b  mov     rcx, [rdi+10h]; struct CConfigServiceProvider2Impl *
0x18000892f  call    ?CreateNodeInstance@CEventLogChannelsNode@@SAJPEAVCConfigServiceProvider2Impl@@PEAUIConfigManager2URI@@PEBUCSP_NODE_DATA@@HPEAPEAUICSPNode@@PEAK@Z; CEventLogChannelsNode::CreateNodeInstance(CConfigServiceProvider2Impl *,IConfigManager2URI *,CSP_NODE_DATA const *,int,ICSPNode * *,ulong *)
0x180008934  jmp     short loc_18000891A
0x180008936  mov     ebx, 86000011h
0x18000893b  jmp     short loc_180008942
0x18000893d  mov     ebx, 80070057h
0x180008942  mov     eax, cs:dword_18004AE90
0x180008948  cmp     eax, 5
0x18000894b  jbe     short loc_180008975
0x18000894d  mov     [rbp+arg_8], ebx
0x180008950  mov     eax, [rdi+2Ch]
0x180008953  mov     [rbp+var_38], eax
0x180008956  lea     rax, [rbp+arg_8]
0x18000895a  mov     [rsp+68h+var_40], rax
0x18000895f  lea     rax, [rbp+var_38]
0x180008963  mov     [rsp+68h+var_48], rax
0x180008968  lea     rdx, byte_180040A59
0x18000896f  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180008974  nop
0x180008975  mov     rcx, [rbp+var_30]
0x180008979  test    rcx, rcx
0x18000897c  jz      short loc_18000898B
0x18000897e  mov     rax, [rcx]
0x180008981  mov     rax, [rax+10h]
0x180008985  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000898a  nop
0x18000898b  mov     eax, ebx
0x18000898d  add     rsp, 68h
0x180008991  pop     r15
0x180008993  pop     r14
0x180008995  pop     r13
0x180008997  pop     r12
0x180008999  pop     rdi
0x18000899a  pop     rsi
0x18000899b  pop     rbx
0x18000899c  pop     rbp
0x18000899d  retn
```
