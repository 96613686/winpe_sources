# CEtwLogCollectorsNode::Add(IConfigManager2URI *,ConfigDataType,tagVARIANT,ICSPNode * *,ulong *)

- ea: `0x180007460`
- end: `0x1800075ce`
- name: `?Add@CEtwLogCollectorsNode@@UEAAJPEAUIConfigManager2URI@@W4ConfigDataType@@UtagVARIANT@@PEAPEAUICSPNode@@PEAK@Z`
- size: `366`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int128 *, struct ICSPNode **, unsigned int *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000108c`
- `0x180007460`
- `0x1800076d0`
- `0x180014640`
- `0x180014aac`
- `0x180037010`

## pseudocode

```c
__int64 __fastcall CEtwLogCollectorsNode::Add(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        __int128 *a4,
        struct ICSPNode **a5,
        unsigned int *a6)
{
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
          v18 = *a4;
          v19 = *((_QWORD *)a4 + 2);
          NodeInstance = CCSPNodeImpl::Add(v9, a2, a3, &v18, v10, v11);
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
      (unsigned int)byte_18003E881,
      a3,
      (_DWORD)a4,
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
0x180007460  push    rbp
0x180007462  push    rbx
0x180007463  push    rsi
0x180007464  push    rdi
0x180007465  push    r12
0x180007467  push    r13
0x180007469  push    r14
0x18000746b  push    r15
0x18000746d  mov     rbp, rsp
0x180007470  sub     rsp, 68h
0x180007474  mov     r12, r9
0x180007477  mov     r13d, r8d
0x18000747a  mov     r15, rdx
0x18000747d  mov     rdi, rcx
0x180007480  mov     [rbp+var_30], 0
0x180007488  test    rdx, rdx
0x18000748b  jz      loc_18000756D
0x180007491  mov     rsi, [rbp+arg_20]
0x180007495  test    rsi, rsi
0x180007498  jz      loc_18000756D
0x18000749e  mov     r14, [rbp+arg_28]
0x1800074a2  test    r14, r14
0x1800074a5  jz      loc_18000756D
0x1800074ab  mov     rcx, [rcx+18h]
0x1800074af  mov     rax, [rcx]
0x1800074b2  lea     rdx, [rbp+var_30]
0x1800074b6  mov     [rsp+68h+var_48], rdx
0x1800074bb  xor     r9d, r9d
0x1800074be  xor     r8d, r8d
0x1800074c1  mov     rdx, r15
0x1800074c4  mov     rax, [rax+0A8h]
0x1800074cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800074d0  mov     ebx, eax
0x1800074d2  test    eax, eax
0x1800074d4  js      loc_180007572
0x1800074da  mov     rax, [rdi+10h]
0x1800074de  mov     rcx, [rax+20h]; struct CspNodeMapBase *
0x1800074e2  test    rcx, rcx
0x1800074e5  jz      short loc_180007566
0x1800074e7  mov     rdx, [rbp+var_30]; struct IConfigManager2URI *
0x1800074eb  call    ?CspGetNodeMapEntryForURI@@YAPEBUCSP_NODEMAP_ENTRY@@PEBVCspNodeMapBase@@PEAUIConfigManager2URI@@@Z; CspGetNodeMapEntryForURI(CspNodeMapBase const *,IConfigManager2URI *)
0x1800074f0  test    rax, rax
0x1800074f3  jz      short loc_180007566
0x1800074f5  mov     qword ptr [rsi], 0
0x1800074fc  mov     dword ptr [r14], 0
0x180007503  cmp     dword ptr [rdi+2Ch], 2
0x180007507  jz      short loc_180007544
0x180007509  cmp     dword ptr [rdi+2Ch], 8
0x18000750d  jz      short loc_180007544
0x18000750f  movups  xmm0, xmmword ptr [r12]
0x180007514  movaps  [rbp+var_28], xmm0
0x180007518  movsd   xmm1, qword ptr [r12+10h]
0x18000751f  movsd   [rbp+var_18], xmm1
0x180007524  mov     [rsp+68h+var_40], r14
0x180007529  mov     [rsp+68h+var_48], rsi
0x18000752e  lea     r9, [rbp+var_28]
0x180007532  mov     r8d, r13d
0x180007535  mov     rdx, r15
0x180007538  mov     rcx, rdi
0x18000753b  call    ?Add@CCSPNodeImpl@@UEAAJPEAUIConfigManager2URI@@W4ConfigDataType@@UtagVARIANT@@PEAPEAUICSPNode@@PEAK@Z; CCSPNodeImpl::Add(IConfigManager2URI *,ConfigDataType,tagVARIANT,ICSPNode * *,ulong *)
0x180007540  mov     ebx, eax
0x180007542  jmp     short loc_180007572
0x180007544  mov     [rsp+68h+var_40], r14; unsigned int *
0x180007549  mov     [rsp+68h+var_48], rsi; struct ICSPNode **
0x18000754e  mov     r9d, 1; int
0x180007554  mov     r8, rax; struct CSP_NODE_DATA *
0x180007557  mov     rdx, [rbp+var_30]; struct IConfigManager2URI *
0x18000755b  mov     rcx, [rdi+10h]; struct CConfigServiceProvider2Impl *
0x18000755f  call    ?CreateNodeInstance@CEtwLogCollectorsNode@@SAJPEAVCConfigServiceProvider2Impl@@PEAUIConfigManager2URI@@PEBUCSP_NODE_DATA@@HPEAPEAUICSPNode@@PEAK@Z; CEtwLogCollectorsNode::CreateNodeInstance(CConfigServiceProvider2Impl *,IConfigManager2URI *,CSP_NODE_DATA const *,int,ICSPNode * *,ulong *)
0x180007564  jmp     short loc_180007540
0x180007566  mov     ebx, 86000011h
0x18000756b  jmp     short loc_180007572
0x18000756d  mov     ebx, 80070057h
0x180007572  mov     eax, cs:dword_180048E90
0x180007578  cmp     eax, 5
0x18000757b  jbe     short loc_1800075A5
0x18000757d  mov     [rbp+arg_8], ebx
0x180007580  mov     eax, [rdi+2Ch]
0x180007583  mov     [rbp+var_38], eax
0x180007586  lea     rax, [rbp+arg_8]
0x18000758a  mov     [rsp+68h+var_40], rax
0x18000758f  lea     rax, [rbp+var_38]
0x180007593  mov     [rsp+68h+var_48], rax
0x180007598  lea     rdx, byte_18003E881
0x18000759f  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800075a4  nop
0x1800075a5  mov     rcx, [rbp+var_30]
0x1800075a9  test    rcx, rcx
0x1800075ac  jz      short loc_1800075BB
0x1800075ae  mov     rax, [rcx]
0x1800075b1  mov     rax, [rax+10h]
0x1800075b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800075ba  nop
0x1800075bb  mov     eax, ebx
0x1800075bd  add     rsp, 68h
0x1800075c1  pop     r15
0x1800075c3  pop     r14
0x1800075c5  pop     r13
0x1800075c7  pop     r12
0x1800075c9  pop     rdi
0x1800075ca  pop     rsi
0x1800075cb  pop     rbx
0x1800075cc  pop     rbp
0x1800075cd  retn
```
