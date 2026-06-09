# CPolicyChannelNode::Add(IConfigManager2URI *,ConfigDataType,tagVARIANT,ICSPNode * *,ulong *)

- ea: `0x18000bcc0`
- end: `0x18000bf3e`
- name: `?Add@CPolicyChannelNode@@UEAAJPEAUIConfigManager2URI@@W4ConfigDataType@@UtagVARIANT@@PEAPEAUICSPNode@@PEAK@Z`
- size: `638`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int128 *, struct ICSPNode **, unsigned int *)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000108c`
- `0x18000bcc0`
- `0x18000bf50`
- `0x18000cb9c`
- `0x180014640`
- `0x180014aac`
- `0x180037010`

## pseudocode

```c
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
            v9 = CCSPNodeImpl::Add(a1, a2, a3, (__int64)&v22, a5, a6);
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
  if ( (unsigned int)dword_180048E90 > 5 )
  {
    v19 = v9;
    LODWORD(v20) = *(_DWORD *)(a1 + 44);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (__int64)v10,
      (__int64)&byte_18003F117,
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
0x18000bcc0  mov     [rsp-40h+arg_10], r8d
0x18000bcc5  push    rbp
0x18000bcc6  push    rbx
0x18000bcc7  push    rsi
0x18000bcc8  push    rdi
0x18000bcc9  push    r12
0x18000bccb  push    r13
0x18000bccd  push    r14
0x18000bccf  push    r15
0x18000bcd1  mov     rbp, rsp
0x18000bcd4  sub     rsp, 78h
0x18000bcd8  mov     r12, r9
0x18000bcdb  mov     r15, rdx
0x18000bcde  mov     rdi, rcx
0x18000bce1  xor     r13d, r13d
0x18000bce4  mov     ebx, r13d
0x18000bce7  mov     [rbp+var_38], r13
0x18000bceb  call    ?PoliciesKeyExist@CPolicyChannelNode@@CA_NXZ; CPolicyChannelNode::PoliciesKeyExist(void)
0x18000bcf0  test    al, al
0x18000bcf2  jz      loc_18000BEDE
0x18000bcf8  test    r15, r15
0x18000bcfb  jz      loc_18000BED9
0x18000bd01  mov     rsi, [rbp+arg_20]
0x18000bd05  test    rsi, rsi
0x18000bd08  jz      loc_18000BED9
0x18000bd0e  mov     r14, [rbp+arg_28]
0x18000bd12  test    r14, r14
0x18000bd15  jz      loc_18000BED9
0x18000bd1b  mov     [rsi], r13
0x18000bd1e  mov     [r14], r13d
0x18000bd21  mov     rbx, [rdi+18h]
0x18000bd25  mov     rax, [rbx]
0x18000bd28  mov     r13, [rax+0A8h]
0x18000bd2f  mov     rcx, [rbp+var_38]
0x18000bd33  test    rcx, rcx
0x18000bd36  jz      short loc_18000BD4D
0x18000bd38  mov     [rbp+var_38], 0
0x18000bd40  mov     rax, [rcx]
0x18000bd43  mov     rax, [rax+10h]
0x18000bd47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd4c  nop
0x18000bd4d  lea     rax, [rbp+var_38]
0x18000bd51  mov     [rsp+78h+var_58], rax
0x18000bd56  xor     r9d, r9d
0x18000bd59  xor     r8d, r8d
0x18000bd5c  mov     rdx, r15
0x18000bd5f  mov     rcx, rbx
0x18000bd62  mov     rax, r13
0x18000bd65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd6a  mov     ebx, eax
0x18000bd6c  xor     r13d, r13d
0x18000bd6f  test    eax, eax
0x18000bd71  js      loc_18000BEDE
0x18000bd77  mov     rax, [rdi+10h]
0x18000bd7b  mov     rcx, [rax+20h]; struct CspNodeMapBase *
0x18000bd7f  test    rcx, rcx
0x18000bd82  jz      loc_18000BED2
0x18000bd88  mov     rdx, [rbp+var_38]; struct IConfigManager2URI *
0x18000bd8c  call    ?CspGetNodeMapEntryForURI@@YAPEBUCSP_NODEMAP_ENTRY@@PEBVCspNodeMapBase@@PEAUIConfigManager2URI@@@Z; CspGetNodeMapEntryForURI(CspNodeMapBase const *,IConfigManager2URI *)
0x18000bd91  test    rax, rax
0x18000bd94  jz      loc_18000BED2
0x18000bd9a  mov     edx, [rdi+2Ch]
0x18000bd9d  sub     edx, 21h ; '!'
0x18000bda0  jz      loc_18000BE71
0x18000bda6  cmp     edx, 1
0x18000bda9  jz      short loc_18000BDE4
0x18000bdab  movups  xmm0, xmmword ptr [r12]
0x18000bdb0  movaps  [rbp+var_28], xmm0
0x18000bdb4  movsd   xmm1, qword ptr [r12+10h]
0x18000bdbb  movsd   [rbp+var_18], xmm1
0x18000bdc0  mov     [rsp+78h+var_50], r14
0x18000bdc5  mov     [rsp+78h+var_58], rsi
0x18000bdca  lea     r9, [rbp+var_28]
0x18000bdce  mov     r8d, [rbp+arg_10]
0x18000bdd2  mov     rdx, r15
0x18000bdd5  mov     rcx, rdi
0x18000bdd8  call    ?Add@CCSPNodeImpl@@UEAAJPEAUIConfigManager2URI@@W4ConfigDataType@@UtagVARIANT@@PEAPEAUICSPNode@@PEAK@Z; CCSPNodeImpl::Add(IConfigManager2URI *,ConfigDataType,tagVARIANT,ICSPNode * *,ulong *)
0x18000bddd  mov     ebx, eax
0x18000bddf  jmp     loc_18000BEDE
0x18000bde4  mov     [rbp+var_40], r13
0x18000bde8  mov     [rbp+var_48], r13d
0x18000bdec  lea     rcx, [rbp+var_48]
0x18000bdf0  mov     [rsp+78h+var_50], rcx; unsigned int *
0x18000bdf5  lea     rcx, [rbp+var_40]
0x18000bdf9  mov     [rsp+78h+var_58], rcx; struct ICSPNode **
0x18000bdfe  mov     r9d, 1; int
0x18000be04  mov     r8, rax; struct CSP_NODE_DATA *
0x18000be07  mov     rdx, [rbp+var_38]; struct IConfigManager2URI *
0x18000be0b  mov     rcx, [rdi+10h]; struct CConfigServiceProvider2Impl *
0x18000be0f  call    ?CreateNodeInstance@CPolicyChannelNode@@SAJPEAVCConfigServiceProvider2Impl@@PEAUIConfigManager2URI@@PEBUCSP_NODE_DATA@@HPEAPEAUICSPNode@@PEAK@Z; CPolicyChannelNode::CreateNodeInstance(CConfigServiceProvider2Impl *,IConfigManager2URI *,CSP_NODE_DATA const *,int,ICSPNode * *,ulong *)
0x18000be14  mov     ebx, eax
0x18000be16  test    eax, eax
0x18000be18  jns     short loc_18000BE39
0x18000be1a  mov     rcx, [rbp+var_40]
0x18000be1e  test    rcx, rcx
0x18000be21  jz      short loc_18000BE34
0x18000be23  mov     [rbp+var_40], r13
0x18000be27  mov     rax, [rcx]
0x18000be2a  mov     rax, [rax+10h]
0x18000be2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be33  nop
0x18000be34  jmp     loc_18000BEDE
0x18000be39  mov     rcx, [rbp+var_40]
0x18000be3d  movups  xmm0, xmmword ptr [r12]
0x18000be42  movaps  [rbp+var_28], xmm0
0x18000be46  movsd   xmm1, qword ptr [r12+10h]
0x18000be4d  movsd   [rbp+var_18], xmm1
0x18000be52  mov     rax, [rcx]
0x18000be55  lea     rdx, [rbp+var_28]
0x18000be59  mov     rax, [rax+58h]
0x18000be5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be62  mov     rax, [rbp+var_40]
0x18000be66  mov     [rsi], rax
0x18000be69  mov     eax, [rbp+var_48]
0x18000be6c  mov     [r14], eax
0x18000be6f  jmp     short loc_18000BEDE
0x18000be71  mov     [rbp+var_40], r13
0x18000be75  mov     [rbp+var_48], r13d
0x18000be79  lea     rcx, [rbp+var_48]
0x18000be7d  mov     [rsp+78h+var_50], rcx; unsigned int *
0x18000be82  lea     rcx, [rbp+var_40]
0x18000be86  mov     [rsp+78h+var_58], rcx; struct ICSPNode **
0x18000be8b  mov     r9d, 1; int
0x18000be91  mov     r8, rax; struct CSP_NODE_DATA *
0x18000be94  mov     rdx, [rbp+var_38]; struct IConfigManager2URI *
0x18000be98  mov     rcx, [rdi+10h]; struct CConfigServiceProvider2Impl *
0x18000be9c  call    ?CreateNodeInstance@CPolicyChannelNode@@SAJPEAVCConfigServiceProvider2Impl@@PEAUIConfigManager2URI@@PEBUCSP_NODE_DATA@@HPEAPEAUICSPNode@@PEAK@Z; CPolicyChannelNode::CreateNodeInstance(CConfigServiceProvider2Impl *,IConfigManager2URI *,CSP_NODE_DATA const *,int,ICSPNode * *,ulong *)
0x18000bea1  mov     ebx, eax
0x18000bea3  test    eax, eax
0x18000bea5  jns     short loc_18000BEC3
0x18000bea7  mov     rcx, [rbp+var_40]
0x18000beab  test    rcx, rcx
0x18000beae  jz      short loc_18000BEC1
0x18000beb0  mov     [rbp+var_40], r13
0x18000beb4  mov     rax, [rcx]
0x18000beb7  mov     rax, [rax+10h]
0x18000bebb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bec0  nop
0x18000bec1  jmp     short loc_18000BEDE
0x18000bec3  mov     rax, [rbp+var_40]
0x18000bec7  mov     [rsi], rax
0x18000beca  mov     eax, [rbp+var_48]
0x18000becd  mov     [r14], eax
0x18000bed0  jmp     short loc_18000BEDE
0x18000bed2  mov     ebx, 86000002h
0x18000bed7  jmp     short loc_18000BEDE
0x18000bed9  mov     ebx, 80070057h
0x18000bede  mov     eax, cs:dword_180048E90
0x18000bee4  cmp     eax, 5
0x18000bee7  jbe     short loc_18000BF11
0x18000bee9  mov     [rbp+var_48], ebx
0x18000beec  mov     eax, [rdi+2Ch]
0x18000beef  mov     dword ptr [rbp+var_40], eax
0x18000bef2  lea     rax, [rbp+var_48]
0x18000bef6  mov     [rsp+78h+var_50], rax
0x18000befb  lea     rax, [rbp+var_40]
0x18000beff  mov     [rsp+78h+var_58], rax
0x18000bf04  lea     rdx, byte_18003F117
0x18000bf0b  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000bf10  nop
0x18000bf11  mov     rcx, [rbp+var_38]
0x18000bf15  test    rcx, rcx
0x18000bf18  jz      short loc_18000BF2B
0x18000bf1a  mov     [rbp+var_38], r13
0x18000bf1e  mov     rax, [rcx]
0x18000bf21  mov     rax, [rax+10h]
0x18000bf25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf2a  nop
0x18000bf2b  mov     eax, ebx
0x18000bf2d  add     rsp, 78h
0x18000bf31  pop     r15
0x18000bf33  pop     r14
0x18000bf35  pop     r13
0x18000bf37  pop     r12
0x18000bf39  pop     rdi
0x18000bf3a  pop     rsi
0x18000bf3b  pop     rbx
0x18000bf3c  pop     rbp
0x18000bf3d  retn
```
