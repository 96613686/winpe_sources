# CPolicyChannelNode::Add(IConfigManager2URI *,ConfigDataType,tagVARIANT,ICSPNode * *,ulong *)

- ea: `0x18000c210`
- end: `0x18000c48f`
- name: `?Add@CPolicyChannelNode@@UEAAJPEAUIConfigManager2URI@@W4ConfigDataType@@UtagVARIANT@@PEAPEAUICSPNode@@PEAK@Z`
- size: `639`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180001090`
- `0x18000c210`
- `0x18000c4a0`
- `0x18000d194`
- `0x180015100`
- `0x180015590`
- `0x180039010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CPolicyChannelNode::Add(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        __int128 *a4,
        struct ICSPNode **a5,
        unsigned int *a6)
{
  signed int v9; // ebx
  struct ICSPNode *v10; // rcx
  __int64 v11; // r8
  __int64 v12; // r9
  __int64 v13; // rbx
  __int64 (__fastcall *v14)(__int64, __int64, _QWORD, _QWORD, struct IConfigManager2URI **); // r13
  struct IConfigManager2URI *v15; // rcx
  const struct CSP_NODE_DATA *NodeMapEntryForURI; // rax
  struct IConfigManager2URI *v17; // rcx
  unsigned int v19; // [rsp+30h] [rbp-48h] BYREF
  struct ICSPNode *v20; // [rsp+38h] [rbp-40h] BYREF
  struct IConfigManager2URI *v21; // [rsp+40h] [rbp-38h] BYREF
  __int128 v22; // [rsp+50h] [rbp-28h] BYREF
  __int64 v23; // [rsp+60h] [rbp-18h]

  v9 = 0;
  v21 = 0;
  if ( CPolicyChannelNode::PoliciesKeyExist() )
  {
    if ( a2 && a5 && a6 )
    {
      *a5 = 0;
      *a6 = 0;
      v13 = *(_QWORD *)(a1 + 24);
      v14 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD, struct IConfigManager2URI **))(*(_QWORD *)v13 + 168LL);
      v15 = v21;
      if ( v21 )
      {
        v21 = 0;
        (*(void (__fastcall **)(struct IConfigManager2URI *))(*(_QWORD *)v15 + 16LL))(v15);
      }
      v9 = v14(v13, a2, 0, 0, &v21);
      if ( v9 >= 0 )
      {
        v10 = *(struct ICSPNode **)(*(_QWORD *)(a1 + 16) + 32LL);
        if ( v10 && (NodeMapEntryForURI = CspGetNodeMapEntryForURI(v10, v21)) != 0 )
        {
          if ( *(_DWORD *)(a1 + 44) == 33 )
          {
            v20 = 0;
            v19 = 0;
            v9 = CPolicyChannelNode::CreateNodeInstance(
                   *(struct CConfigServiceProvider2Impl **)(a1 + 16),
                   v21,
                   NodeMapEntryForURI,
                   1,
                   &v20,
                   &v19);
            if ( v9 >= 0 )
            {
              *a5 = v20;
              *a6 = v19;
            }
            else
            {
              v10 = v20;
              if ( v20 )
              {
                v20 = 0;
                (*(void (__fastcall **)(struct ICSPNode *))(*(_QWORD *)v10 + 16LL))(v10);
              }
            }
          }
          else if ( *(_DWORD *)(a1 + 44) == 34 )
          {
            v20 = 0;
            v19 = 0;
            v9 = CPolicyChannelNode::CreateNodeInstance(
                   *(struct CConfigServiceProvider2Impl **)(a1 + 16),
                   v21,
                   NodeMapEntryForURI,
                   1,
                   &v20,
                   &v19);
            if ( v9 >= 0 )
            {
              v22 = *a4;
              v23 = *((_QWORD *)a4 + 2);
              (*(void (__fastcall **)(struct ICSPNode *, __int128 *))(*(_QWORD *)v20 + 88LL))(v20, &v22);
              *a5 = v20;
              *a6 = v19;
            }
            else
            {
              v10 = v20;
              if ( v20 )
              {
                v20 = 0;
                (*(void (__fastcall **)(struct ICSPNode *))(*(_QWORD *)v10 + 16LL))(v10);
              }
            }
          }
          else
          {
            v22 = *a4;
            v23 = *((_QWORD *)a4 + 2);
            v9 = CCSPNodeImpl::Add(a1, a2, a3, &v22, a5, a6);
          }
        }
        else
        {
          v9 = -2046820350;
        }
      }
    }
    else
    {
      v9 = -2147024809;
    }
  }
  if ( (unsigned int)dword_18004AE90 > 5 )
  {
    v19 = v9;
    LODWORD(v20) = *(_DWORD *)(a1 + 44);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (__int64)v10,
      (unsigned __int8 *)byte_180041117,
      v11,
      v12,
      (__int64)&v20,
      (__int64)&v19);
  }
  v17 = v21;
  if ( v21 )
  {
    v21 = 0;
    (*(void (__fastcall **)(struct IConfigManager2URI *))(*(_QWORD *)v17 + 16LL))(v17);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000c210  mov     [rsp-40h+arg_10], r8d
0x18000c215  push    rbp
0x18000c216  push    rbx
0x18000c217  push    rsi
0x18000c218  push    rdi
0x18000c219  push    r12
0x18000c21b  push    r13
0x18000c21d  push    r14
0x18000c21f  push    r15
0x18000c221  mov     rbp, rsp
0x18000c224  sub     rsp, 78h
0x18000c228  mov     r12, r9
0x18000c22b  mov     r15, rdx
0x18000c22e  mov     rdi, rcx
0x18000c231  xor     r13d, r13d
0x18000c234  mov     ebx, r13d
0x18000c237  mov     [rbp+var_38], r13
0x18000c23b  call    ?PoliciesKeyExist@CPolicyChannelNode@@CA_NXZ; CPolicyChannelNode::PoliciesKeyExist(void)
0x18000c240  test    al, al
0x18000c242  jz      loc_18000C42E
0x18000c248  test    r15, r15
0x18000c24b  jz      loc_18000C429
0x18000c251  mov     rsi, [rbp+arg_20]
0x18000c255  test    rsi, rsi
0x18000c258  jz      loc_18000C429
0x18000c25e  mov     r14, [rbp+arg_28]
0x18000c262  test    r14, r14
0x18000c265  jz      loc_18000C429
0x18000c26b  mov     [rsi], r13
0x18000c26e  mov     [r14], r13d
0x18000c271  mov     rbx, [rdi+18h]
0x18000c275  mov     rax, [rbx]
0x18000c278  mov     r13, [rax+0A8h]
0x18000c27f  mov     rcx, [rbp+var_38]
0x18000c283  test    rcx, rcx
0x18000c286  jz      short loc_18000C29D
0x18000c288  mov     [rbp+var_38], 0
0x18000c290  mov     rax, [rcx]
0x18000c293  mov     rax, [rax+10h]
0x18000c297  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c29c  nop
0x18000c29d  lea     rax, [rbp+var_38]
0x18000c2a1  mov     [rsp+78h+var_58], rax
0x18000c2a6  xor     r9d, r9d
0x18000c2a9  xor     r8d, r8d
0x18000c2ac  mov     rdx, r15
0x18000c2af  mov     rcx, rbx
0x18000c2b2  mov     rax, r13
0x18000c2b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c2ba  mov     ebx, eax
0x18000c2bc  xor     r13d, r13d
0x18000c2bf  test    eax, eax
0x18000c2c1  js      loc_18000C42E
0x18000c2c7  mov     rax, [rdi+10h]
0x18000c2cb  mov     rcx, [rax+20h]; struct CspNodeMapBase *
0x18000c2cf  test    rcx, rcx
0x18000c2d2  jz      loc_18000C422
0x18000c2d8  mov     rdx, [rbp+var_38]; struct IConfigManager2URI *
0x18000c2dc  call    ?CspGetNodeMapEntryForURI@@YAPEBUCSP_NODEMAP_ENTRY@@PEBVCspNodeMapBase@@PEAUIConfigManager2URI@@@Z; CspGetNodeMapEntryForURI(CspNodeMapBase const *,IConfigManager2URI *)
0x18000c2e1  test    rax, rax
0x18000c2e4  jz      loc_18000C422
0x18000c2ea  mov     edx, [rdi+2Ch]
0x18000c2ed  sub     edx, 21h ; '!'
0x18000c2f0  jz      loc_18000C3C1
0x18000c2f6  cmp     edx, 1
0x18000c2f9  jz      short loc_18000C334
0x18000c2fb  movups  xmm0, xmmword ptr [r12]
0x18000c300  movaps  [rbp+var_28], xmm0
0x18000c304  movsd   xmm1, qword ptr [r12+10h]
0x18000c30b  movsd   [rbp+var_18], xmm1
0x18000c310  mov     [rsp+78h+var_50], r14
0x18000c315  mov     [rsp+78h+var_58], rsi
0x18000c31a  lea     r9, [rbp+var_28]
0x18000c31e  mov     r8d, [rbp+arg_10]
0x18000c322  mov     rdx, r15
0x18000c325  mov     rcx, rdi
0x18000c328  call    ?Add@CCSPNodeImpl@@UEAAJPEAUIConfigManager2URI@@W4ConfigDataType@@UtagVARIANT@@PEAPEAUICSPNode@@PEAK@Z; CCSPNodeImpl::Add(IConfigManager2URI *,ConfigDataType,tagVARIANT,ICSPNode * *,ulong *)
0x18000c32d  mov     ebx, eax
0x18000c32f  jmp     loc_18000C42E
0x18000c334  mov     [rbp+var_40], r13
0x18000c338  mov     [rbp+var_48], r13d
0x18000c33c  lea     rcx, [rbp+var_48]
0x18000c340  mov     [rsp+78h+var_50], rcx; unsigned int *
0x18000c345  lea     rcx, [rbp+var_40]
0x18000c349  mov     [rsp+78h+var_58], rcx; struct ICSPNode **
0x18000c34e  mov     r9d, 1; int
0x18000c354  mov     r8, rax; struct CSP_NODE_DATA *
0x18000c357  mov     rdx, [rbp+var_38]; struct IConfigManager2URI *
0x18000c35b  mov     rcx, [rdi+10h]; struct CConfigServiceProvider2Impl *
0x18000c35f  call    ?CreateNodeInstance@CPolicyChannelNode@@SAJPEAVCConfigServiceProvider2Impl@@PEAUIConfigManager2URI@@PEBUCSP_NODE_DATA@@HPEAPEAUICSPNode@@PEAK@Z; CPolicyChannelNode::CreateNodeInstance(CConfigServiceProvider2Impl *,IConfigManager2URI *,CSP_NODE_DATA const *,int,ICSPNode * *,ulong *)
0x18000c364  mov     ebx, eax
0x18000c366  test    eax, eax
0x18000c368  jns     short loc_18000C389
0x18000c36a  mov     rcx, [rbp+var_40]
0x18000c36e  test    rcx, rcx
0x18000c371  jz      short loc_18000C384
0x18000c373  mov     [rbp+var_40], r13
0x18000c377  mov     rax, [rcx]
0x18000c37a  mov     rax, [rax+10h]
0x18000c37e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c383  nop
0x18000c384  jmp     loc_18000C42E
0x18000c389  mov     rcx, [rbp+var_40]
0x18000c38d  movups  xmm0, xmmword ptr [r12]
0x18000c392  movaps  [rbp+var_28], xmm0
0x18000c396  movsd   xmm1, qword ptr [r12+10h]
0x18000c39d  movsd   [rbp+var_18], xmm1
0x18000c3a2  mov     rax, [rcx]
0x18000c3a5  lea     rdx, [rbp+var_28]
0x18000c3a9  mov     rax, [rax+58h]
0x18000c3ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c3b2  mov     rax, [rbp+var_40]
0x18000c3b6  mov     [rsi], rax
0x18000c3b9  mov     eax, [rbp+var_48]
0x18000c3bc  mov     [r14], eax
0x18000c3bf  jmp     short loc_18000C42E
0x18000c3c1  mov     [rbp+var_40], r13
0x18000c3c5  mov     [rbp+var_48], r13d
0x18000c3c9  lea     rcx, [rbp+var_48]
0x18000c3cd  mov     [rsp+78h+var_50], rcx; unsigned int *
0x18000c3d2  lea     rcx, [rbp+var_40]
0x18000c3d6  mov     [rsp+78h+var_58], rcx; struct ICSPNode **
0x18000c3db  mov     r9d, 1; int
0x18000c3e1  mov     r8, rax; struct CSP_NODE_DATA *
0x18000c3e4  mov     rdx, [rbp+var_38]; struct IConfigManager2URI *
0x18000c3e8  mov     rcx, [rdi+10h]; struct CConfigServiceProvider2Impl *
0x18000c3ec  call    ?CreateNodeInstance@CPolicyChannelNode@@SAJPEAVCConfigServiceProvider2Impl@@PEAUIConfigManager2URI@@PEBUCSP_NODE_DATA@@HPEAPEAUICSPNode@@PEAK@Z; CPolicyChannelNode::CreateNodeInstance(CConfigServiceProvider2Impl *,IConfigManager2URI *,CSP_NODE_DATA const *,int,ICSPNode * *,ulong *)
0x18000c3f1  mov     ebx, eax
0x18000c3f3  test    eax, eax
0x18000c3f5  jns     short loc_18000C413
0x18000c3f7  mov     rcx, [rbp+var_40]
0x18000c3fb  test    rcx, rcx
0x18000c3fe  jz      short loc_18000C411
0x18000c400  mov     [rbp+var_40], r13
0x18000c404  mov     rax, [rcx]
0x18000c407  mov     rax, [rax+10h]
0x18000c40b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c410  nop
0x18000c411  jmp     short loc_18000C42E
0x18000c413  mov     rax, [rbp+var_40]
0x18000c417  mov     [rsi], rax
0x18000c41a  mov     eax, [rbp+var_48]
0x18000c41d  mov     [r14], eax
0x18000c420  jmp     short loc_18000C42E
0x18000c422  mov     ebx, 86000002h
0x18000c427  jmp     short loc_18000C42E
0x18000c429  mov     ebx, 80070057h
0x18000c42e  mov     eax, cs:dword_18004AE90
0x18000c434  cmp     eax, 5
0x18000c437  jbe     short loc_18000C461
0x18000c439  mov     [rbp+var_48], ebx
0x18000c43c  mov     eax, [rdi+2Ch]
0x18000c43f  mov     dword ptr [rbp+var_40], eax
0x18000c442  lea     rax, [rbp+var_48]
0x18000c446  mov     [rsp+78h+var_50], rax
0x18000c44b  lea     rax, [rbp+var_40]
0x18000c44f  mov     [rsp+78h+var_58], rax
0x18000c454  lea     rdx, byte_180041117
0x18000c45b  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000c460  nop
0x18000c461  mov     rcx, [rbp+var_38]
0x18000c465  test    rcx, rcx
0x18000c468  jz      short loc_18000C47B
0x18000c46a  mov     [rbp+var_38], r13
0x18000c46e  mov     rax, [rcx]
0x18000c471  mov     rax, [rax+10h]
0x18000c475  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c47a  nop
0x18000c47b  mov     eax, ebx
0x18000c47d  add     rsp, 78h
0x18000c481  pop     r15
0x18000c483  pop     r14
0x18000c485  pop     r13
0x18000c487  pop     r12
0x18000c489  pop     rdi
0x18000c48a  pop     rsi
0x18000c48b  pop     rbx
0x18000c48c  pop     rbp
0x18000c48d  retn
```
