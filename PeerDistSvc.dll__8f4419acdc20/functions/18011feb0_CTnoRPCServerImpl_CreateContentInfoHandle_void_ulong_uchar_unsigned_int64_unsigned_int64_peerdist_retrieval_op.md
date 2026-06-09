# CTnoRPCServerImpl::CreateContentInfoHandle(void *,ulong,uchar *,unsigned __int64,unsigned __int64,peerdist_retrieval_options_tag *,void * *)

- ea: `0x18011feb0`
- end: `0x1801202cb`
- name: `?CreateContentInfoHandle@CTnoRPCServerImpl@@UEAAJPEAXKPEAE_K2PEAUpeerdist_retrieval_options_tag@@PEAPEAX@Z`
- size: `1051`
- prototype: `__int64 __fastcall(CTnoRPCServerImpl *this, RPC_BINDING_HANDLE BindingHandle, unsigned int, unsigned __int8 *, unsigned __int64, unsigned __int64, struct peerdist_retrieval_options_tag *, void **)`
- caller_count: `0`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callees

- `0x1800024f0`
- `0x180008290`
- `0x18000ceac`
- `0x18000e81c`
- `0x18000ecf4`
- `0x180015c28`
- `0x180018170`
- `0x1800191b8`
- `0x18011caa4`
- `0x18011ce4c`
- `0x18011fbc0`
- `0x18011feb0`
- `0x180137470`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x18011ffe4`
- `RPCRT4!RpcImpersonateClient` at `0x18011ffe4`
- `RPCRT4!RpcRevertToSelf` at `0x180120051`
- `RPCRT4!RpcRevertToSelf` at `0x180120051`

## string_xrefs

- `0x18011ff7c`: `PeerDist-Common-Client-Enabled`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CTnoRPCServerImpl::CreateContentInfoHandle(
        RTL_SRWLOCK *this,
        RPC_BINDING_HANDLE BindingHandle,
        unsigned int a3,
        unsigned __int8 *a4,
        unsigned __int64 a5,
        unsigned __int64 a6,
        struct peerdist_retrieval_options_tag *a7,
        void **a8)
{
  struct ITnoContentInfoEncoder *v11; // rbx
  struct peerdist_retrieval_options_tag *v12; // r14
  void **v13; // r15
  int PublisherIdentityForCurrentThread; // edi
  void **v15; // rcx
  CHostedCacheMsgEncoding *v16; // rcx
  __int64 v17; // rdx
  struct ITnoContentInfoEncoder *v18; // rsi
  __int64 v19; // rax
  int v20; // r8d
  struct ITnoContentInfoEncoder *v22; // [rsp+50h] [rbp-68h] BYREF
  void *Block; // [rsp+58h] [rbp-60h] BYREF
  struct ITnoContentInfoEncoder *v24; // [rsp+60h] [rbp-58h] BYREF
  struct ITnoContentInfoEncoder *v25; // [rsp+68h] [rbp-50h] BYREF
  _BYTE v26[16]; // [rsp+70h] [rbp-48h] BYREF
  _BYTE v27[16]; // [rsp+80h] [rbp-38h] BYREF

  v24 = 0;
  v11 = 0;
  v22 = 0;
  Block = 0;
  v12 = a7;
  if ( a7 )
  {
    v13 = a8;
    if ( a8 )
    {
      if ( a4 )
      {
        if ( *(_DWORD *)a7 != 16 )
        {
          if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x8000) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 105) )
          {
            PublisherIdentityForCurrentThread = -2147020834;
            WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 12), 144, WPP_56069f0a00a13e5f2d94d619c5002cd2_Traceguids);
          }
          else
          {
            PublisherIdentityForCurrentThread = -2147020834;
          }
          goto LABEL_49;
        }
        LockSentry<ReadersWriterLock,0>::LockSentry<ReadersWriterLock,0>((__int64)v26, this + 2);
        if ( IsLicenseEnabled(L"PeerDist-Common-Client-Enabled") )
        {
          if ( BindingHandle )
          {
            PublisherIdentityForCurrentThread = RpcImpersonateClient(BindingHandle);
            if ( PublisherIdentityForCurrentThread )
            {
              if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x8000) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 105) )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 12),
                  146,
                  WPP_56069f0a00a13e5f2d94d619c5002cd2_Traceguids,
                  (unsigned int)PublisherIdentityForCurrentThread);
              }
              if ( PublisherIdentityForCurrentThread >= 0 )
                PublisherIdentityForCurrentThread = (unsigned __int16)PublisherIdentityForCurrentThread | 0x80010000;
              goto LABEL_48;
            }
          }
          PublisherIdentityForCurrentThread = GetPublisherIdentityForCurrentThread(v15, (unsigned __int16 **)&Block);
          if ( BindingHandle )
            RpcRevertToSelf();
          if ( !PublisherIdentityForCurrentThread )
          {
            PublisherIdentityForCurrentThread = CTnoRPCServerImpl::CreateContentInfoEncoderForVersion(
                                                  (CTnoRPCServerImpl *)this,
                                                  a3,
                                                  a4,
                                                  (unsigned __int16 *)Block,
                                                  a5,
                                                  a6,
                                                  *((_DWORD *)v12 + 1),
                                                  *((_DWORD *)v12 + 2),
                                                  &v24);
            if ( PublisherIdentityForCurrentThread >= 0 )
            {
              v18 = v24;
              a7 = v24;
              SmartPointer<CRepubJetSessionContext>::AddRef(&a7);
              if ( v18 )
              {
                SmartPointer<CRepubJetSessionContext>::Release(&v22);
                v11 = v18;
                v22 = v18;
                SmartPointer<CRepubJetSessionContext>::AddRef(&v22);
              }
              SmartPointer<CRepubJetSessionContext>::Release(&a7);
              v24 = v11;
              v25 = v11;
              SmartPointer<CRepubJetSessionContext>::AddRef(&v25);
              if ( __eh34_try(-1, 0) )
              {
                __eh34_scope_strut(0);
                v19 = std::_Tree_buy<std::pair<void * const,SmartPointer<ITnoContentInfoEncoder>>>::_Buynode<std::pair<void *,SmartPointer<ITnoContentInfoEncoder>> &>(
                        &this[74],
                        &v24);
                std::_Tree<std::_Tmap_traits<ITnoPublication *,SmartPointer<CPublicationContentId>,std::less<ITnoPublication *>,std::allocator<std::pair<ITnoPublication * const,SmartPointer<CPublicationContentId>>>,0>>::_Insert_nohint<std::pair<ITnoPublication * const,SmartPointer<CPublicationContentId>> &,std::_Tree_node<std::pair<ITnoPublication * const,SmartPointer<CPublicationContentId>>,void *> *>(
                  (_DWORD)this + 592,
                  (int)v27,
                  v20,
                  v19 + 32,
                  v19);
                if ( v27[8] )
                {
                  *v13 = v11;
                  SmartPointer<CRepubJetSessionContext>::Release(&v25);
                }
                else
                {
                  PublisherIdentityForCurrentThread = -2147024122;
                  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
                    && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x8000) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 105) )
                  {
                    WPP_SF_d(
                      *((_QWORD *)WPP_GLOBAL_Control + 12),
                      149,
                      WPP_56069f0a00a13e5f2d94d619c5002cd2_Traceguids,
                      2147943174LL);
                  }
                  SmartPointer<CRepubJetSessionContext>::Release(&v25);
                }
              }
              if ( __eh34_catch(0) )
              {
                if ( __eh34_catch_type(0, &exception `RTTI Type Descriptor', 0) )
                {
                  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
                    && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x8000) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 105) )
                  {
                    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 150, WPP_56069f0a00a13e5f2d94d619c5002cd2_Traceguids);
                  }
                  __eh34_try_continuation(0, &exception `RTTI Type Descriptor', &loc_180120244);
                  LockSentry<ReadersWriterLock,0>::Unlock(v26);
                  PublisherIdentityForCurrentThread = -2147024122;
                  goto LABEL_49;
                }
              }
            }
            else if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
                   && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x8000) != 0
                   && *((_BYTE *)WPP_GLOBAL_Control + 105) )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 12),
                148,
                WPP_56069f0a00a13e5f2d94d619c5002cd2_Traceguids,
                (unsigned int)PublisherIdentityForCurrentThread);
            }
            goto LABEL_48;
          }
          if ( PublisherIdentityForCurrentThread > 0 )
            PublisherIdentityForCurrentThread = (unsigned __int16)PublisherIdentityForCurrentThread | 0x80070000;
          v16 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
            || (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x8000) == 0
            || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
          {
LABEL_48:
            operator delete(Block);
            LockSentry<ReadersWriterLock,0>::Unlock(v26);
LABEL_49:
            SmartPointer<CRepubJetSessionContext>::Release(&v22);
            return (unsigned int)PublisherIdentityForCurrentThread;
          }
          v17 = 147;
        }
        else
        {
          PublisherIdentityForCurrentThread = -2147020832;
          v16 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
            || (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x8000) == 0
            || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
          {
            goto LABEL_48;
          }
          v17 = 145;
        }
        WPP_SF_d(
          *((_QWORD *)v16 + 12),
          v17,
          WPP_56069f0a00a13e5f2d94d619c5002cd2_Traceguids,
          (unsigned int)PublisherIdentityForCurrentThread);
        goto LABEL_48;
      }
    }
  }
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x8000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 143, WPP_56069f0a00a13e5f2d94d619c5002cd2_Traceguids, 2147942487LL);
  }
  SmartPointer<CRepubJetSessionContext>::Release(&v22);
  return 2147942487LL;
}

```

## disassembly

```asm
0x18011feb0  mov     rax, rsp
0x18011feb3  mov     [rax+8], rbx
0x18011feb7  mov     [rax+10h], rsi
0x18011febb  mov     [rax+18h], r8d
0x18011febf  push    rdi
0x18011fec0  push    r12
0x18011fec2  push    r13
0x18011fec4  push    r14
0x18011fec6  push    r15
0x18011fec8  sub     rsp, 90h
0x18011fecf  mov     r12, r9
0x18011fed2  mov     rsi, rdx
0x18011fed5  mov     r13, rcx
0x18011fed8  mov     qword ptr [rax-58h], 0
0x18011fee0  xor     ebx, ebx
0x18011fee2  mov     [rax-68h], rbx
0x18011fee6  mov     [rax-60h], rbx
0x18011feea  mov     r14, [rsp+0B8h+arg_30]
0x18011fef2  test    r14, r14
0x18011fef5  jz      loc_180120261
0x18011fefb  mov     r15, [rsp+0B8h+arg_38]
0x18011ff03  test    r15, r15
0x18011ff06  jz      loc_180120261
0x18011ff0c  test    r9, r9
0x18011ff0f  jz      loc_180120261
0x18011ff15  cmp     dword ptr [r14], 10h
0x18011ff19  jz      short loc_18011FF6D
0x18011ff1b  lea     rax, WPP_GLOBAL_Control
0x18011ff22  mov     rcx, cs:WPP_GLOBAL_Control
0x18011ff29  cmp     rcx, rax
0x18011ff2c  jz      short loc_18011FF63
0x18011ff2e  test    dword ptr [rcx+6Ch], 8000h
0x18011ff35  jz      short loc_18011FF63
0x18011ff37  cmp     byte ptr [rcx+69h], 1
0x18011ff3b  jb      short loc_18011FF63
0x18011ff3d  mov     edx, 90h
0x18011ff42  mov     edi, 80070FDEh
0x18011ff47  mov     dword ptr [rsp+0B8h+var_98], edi
0x18011ff4b  mov     r9d, [r14]
0x18011ff4e  lea     r8, WPP_56069f0a00a13e5f2d94d619c5002cd2_Traceguids
0x18011ff55  mov     rcx, [rcx+60h]
0x18011ff59  call    WPP_SF_Dd
0x18011ff5e  jmp     loc_180120253
0x18011ff63  mov     edi, 80070FDEh
0x18011ff68  jmp     loc_180120253
0x18011ff6d  lea     rdx, [rcx+10h]
0x18011ff71  lea     rcx, [rsp+0B8h+var_48]
0x18011ff76  call    ??0?$LockSentry@VReadersWriterLock@@$0A@@@QEAA@AEAVReadersWriterLock@@@Z; LockSentry<ReadersWriterLock,0>::LockSentry<ReadersWriterLock,0>(ReadersWriterLock &)
0x18011ff7b  nop
0x18011ff7c  lea     rcx, aPeerdistCommon; "PeerDist-Common-Client-Enabled"
0x18011ff83  call    ?IsLicenseEnabled@@YA_NPEBG@Z; IsLicenseEnabled(ushort const *)
0x18011ff88  test    al, al
0x18011ff8a  jnz     short loc_18011FFDC
0x18011ff8c  mov     edi, 80070FE0h
0x18011ff91  lea     rax, WPP_GLOBAL_Control
0x18011ff98  mov     rcx, cs:WPP_GLOBAL_Control
0x18011ff9f  cmp     rcx, rax
0x18011ffa2  jz      loc_18012022D
0x18011ffa8  test    dword ptr [rcx+6Ch], 8000h
0x18011ffaf  jz      loc_18012022D
0x18011ffb5  cmp     byte ptr [rcx+69h], 1
0x18011ffb9  jb      loc_18012022D
0x18011ffbf  mov     edx, 91h
0x18011ffc4  mov     r9d, edi
0x18011ffc7  lea     r8, WPP_56069f0a00a13e5f2d94d619c5002cd2_Traceguids
0x18011ffce  mov     rcx, [rcx+60h]
0x18011ffd2  call    WPP_SF_d
0x18011ffd7  jmp     loc_18012022D
0x18011ffdc  test    rsi, rsi
0x18011ffdf  jz      short loc_180120040
0x18011ffe1  mov     rcx, rsi; BindingHandle
0x18011ffe4  call    cs:__imp_RpcImpersonateClient
0x18011ffea  mov     edi, eax
0x18011ffec  test    eax, eax
0x18011ffee  jz      short loc_180120040
0x18011fff0  lea     rax, WPP_GLOBAL_Control
0x18011fff7  mov     rcx, cs:WPP_GLOBAL_Control
0x18011fffe  cmp     rcx, rax
0x180120001  jz      short loc_18012002A
0x180120003  test    dword ptr [rcx+6Ch], 8000h
0x18012000a  jz      short loc_18012002A
0x18012000c  cmp     byte ptr [rcx+69h], 1
0x180120010  jb      short loc_18012002A
0x180120012  mov     edx, 92h
0x180120017  mov     r9d, edi
0x18012001a  lea     r8, WPP_56069f0a00a13e5f2d94d619c5002cd2_Traceguids
0x180120021  mov     rcx, [rcx+60h]
0x180120025  call    WPP_SF_d
0x18012002a  test    edi, edi
0x18012002c  js      loc_18012022D
0x180120032  movzx   edi, di
0x180120035  or      edi, 80010000h
0x18012003b  jmp     loc_18012022D
0x180120040  lea     rdx, [rsp+0B8h+Block]; unsigned __int16 **
0x180120045  call    ?GetPublisherIdentityForCurrentThread@@YAKPEAPEAXPEAPEAG@Z; GetPublisherIdentityForCurrentThread(void * *,ushort * *)
0x18012004a  mov     edi, eax
0x18012004c  test    rsi, rsi
0x18012004f  jz      short loc_180120057
0x180120051  call    cs:__imp_RpcRevertToSelf
0x180120057  test    edi, edi
0x180120059  jz      short loc_18012009E
0x18012005b  jle     short loc_180120066
0x18012005d  movzx   edi, di
0x180120060  or      edi, 80070000h
0x180120066  lea     rax, WPP_GLOBAL_Control
0x18012006d  mov     rcx, cs:WPP_GLOBAL_Control
0x180120074  cmp     rcx, rax
0x180120077  jz      loc_18012022D
0x18012007d  test    dword ptr [rcx+6Ch], 8000h
0x180120084  jz      loc_18012022D
0x18012008a  cmp     byte ptr [rcx+69h], 1
0x18012008e  jb      loc_18012022D
0x180120094  mov     edx, 93h
0x180120099  jmp     loc_18011FFC4
0x18012009e  lea     rax, [rsp+0B8h+var_58]
0x1801200a3  mov     [rsp+0B8h+var_78], rax; struct ITnoContentInfoEncoder **
0x1801200a8  mov     eax, [r14+8]
0x1801200ac  mov     [rsp+0B8h+var_80], eax; unsigned int
0x1801200b0  mov     eax, [r14+4]
0x1801200b4  mov     [rsp+0B8h+var_88], eax; unsigned int
0x1801200b8  mov     rax, [rsp+0B8h+arg_28]
0x1801200c0  mov     [rsp+0B8h+var_90], rax; unsigned __int64
0x1801200c5  mov     rax, [rsp+0B8h+arg_20]
0x1801200cd  mov     [rsp+0B8h+var_98], rax; unsigned __int64
0x1801200d2  mov     r9, [rsp+0B8h+Block]; unsigned __int16 *
0x1801200d7  mov     r8, r12; unsigned __int8 *
0x1801200da  mov     edx, [rsp+0B8h+arg_10]; unsigned int
0x1801200e1  mov     rcx, r13; this
0x1801200e4  call    ?CreateContentInfoEncoderForVersion@CTnoRPCServerImpl@@IEAAJKPEAEPEAG_K2KKPEAPEAVITnoContentInfoEncoder@@@Z; CTnoRPCServerImpl::CreateContentInfoEncoderForVersion(ulong,uchar *,ushort *,unsigned __int64,unsigned __int64,ulong,ulong,ITnoContentInfoEncoder * *)
0x1801200e9  mov     edi, eax
0x1801200eb  test    eax, eax
0x1801200ed  jns     short loc_18012013A
0x1801200ef  lea     rax, WPP_GLOBAL_Control
0x1801200f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1801200fd  cmp     rcx, rax
0x180120100  jz      loc_18012022D
0x180120106  test    dword ptr [rcx+6Ch], 8000h
0x18012010d  jz      loc_18012022D
0x180120113  cmp     byte ptr [rcx+69h], 1
0x180120117  jb      loc_18012022D
0x18012011d  mov     edx, 94h
0x180120122  mov     r9d, edi
0x180120125  lea     r8, WPP_56069f0a00a13e5f2d94d619c5002cd2_Traceguids
0x18012012c  mov     rcx, [rcx+60h]
0x180120130  call    WPP_SF_d
0x180120135  jmp     loc_18012022D
0x18012013a  mov     rsi, [rsp+0B8h+var_58]
0x18012013f  mov     [rsp+0B8h+arg_30], rsi
0x180120147  lea     rcx, [rsp+0B8h+arg_30]
0x18012014f  call    ?AddRef@?$SmartPointer@VCRepubJetSessionContext@@@@IEAAXXZ; SmartPointer<CRepubJetSessionContext>::AddRef(void)
0x180120154  test    rsi, rsi
0x180120157  jz      short loc_180120175
0x180120159  lea     rcx, [rsp+0B8h+var_68]
0x18012015e  call    ?Release@?$SmartPointer@VCRepubJetSessionContext@@@@IEAAXXZ; SmartPointer<CRepubJetSessionContext>::Release(void)
0x180120163  mov     rbx, rsi
0x180120166  mov     [rsp+0B8h+var_68], rbx
0x18012016b  lea     rcx, [rsp+0B8h+var_68]
0x180120170  call    ?AddRef@?$SmartPointer@VCRepubJetSessionContext@@@@IEAAXXZ; SmartPointer<CRepubJetSessionContext>::AddRef(void)
0x180120175  lea     rcx, [rsp+0B8h+arg_30]
0x18012017d  call    ?Release@?$SmartPointer@VCRepubJetSessionContext@@@@IEAAXXZ; SmartPointer<CRepubJetSessionContext>::Release(void)
0x180120182  nop
0x180120183  mov     [rsp+0B8h+var_58], rbx
0x180120188  mov     [rsp+0B8h+var_50], rbx
0x18012018d  lea     rcx, [rsp+0B8h+var_50]
0x180120192  call    ?AddRef@?$SmartPointer@VCRepubJetSessionContext@@@@IEAAXXZ; SmartPointer<CRepubJetSessionContext>::AddRef(void)
0x180120197  nop
0x180120198  lea     rsi, [r13+250h]
0x18012019f  lea     rdx, [rsp+0B8h+var_58]
0x1801201a4  mov     rcx, rsi
0x1801201a7  call    ??$_Buynode@AEAU?$pair@PEAXV?$SmartPointer@VITnoContentInfoEncoder@@@@@std@@@?$_Tree_buy@U?$pair@QEAXV?$SmartPointer@VITnoContentInfoEncoder@@@@@std@@V?$allocator@U?$pair@QEAXV?$SmartPointer@VITnoContentInfoEncoder@@@@@std@@@2@@std@@QEAAPEAU?$_Tree_node@U?$pair@QEAXV?$SmartPointer@VITnoContentInfoEncoder@@@@@std@@PEAX@1@AEAU?$pair@PEAXV?$SmartPointer@VITnoContentInfoEncoder@@@@@1@@Z; std::_Tree_buy<std::pair<void * const,SmartPointer<ITnoContentInfoEncoder>>>::_Buynode<std::pair<void *,SmartPointer<ITnoContentInfoEncoder>> &>(std::pair<void *,SmartPointer<ITnoContentInfoEncoder>> &)
0x1801201ac  lea     r9, [rax+20h]
0x1801201b0  mov     [rsp+0B8h+var_98], rax
0x1801201b5  lea     rdx, [rsp+0B8h+var_38]
0x1801201bd  mov     rcx, rsi
0x1801201c0  call    ??$_Insert_nohint@AEAU?$pair@QEAVITnoPublication@@V?$SmartPointer@VCPublicationContentId@@@@@std@@PEAU?$_Tree_node@U?$pair@QEAVITnoPublication@@V?$SmartPointer@VCPublicationContentId@@@@@std@@PEAX@2@@?$_Tree@V?$_Tmap_traits@PEAVITnoPublication@@V?$SmartPointer@VCPublicationContentId@@@@U?$less@PEAVITnoPublication@@@std@@V?$allocator@U?$pair@QEAVITnoPublication@@V?$SmartPointer@VCPublicationContentId@@@@@std@@@4@$0A@@std@@@std@@IEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAVITnoPublication@@V?$SmartPointer@VCPublicationContentId@@@@@std@@@std@@@std@@@std@@_N@1@_NAEAU?$pair@QEAVITnoPublication@@V?$SmartPointer@VCPublicationContentId@@@@@1@PEAU?$_Tree_node@U?$pair@QEAVITnoPublication@@V?$SmartPointer@VCPublicationContentId@@@@@std@@PEAX@1@@Z; std::_Tree<std::_Tmap_traits<ITnoPublication *,SmartPointer<CPublicationContentId>,std::less<ITnoPublication *>,std::allocator<std::pair<ITnoPublication * const,SmartPointer<CPublicationContentId>>>,0>>::_Insert_nohint<std::pair<ITnoPublication * const,SmartPointer<CPublicationContentId>> &,std::_Tree_node<std::pair<ITnoPublication * const,SmartPointer<CPublicationContentId>>,void *> *>(bool,std::pair<ITnoPublication * const,SmartPointer<CPublicationContentId>> &,std::_Tree_node<std::pair<ITnoPublication * const,SmartPointer<CPublicationContentId>>,void *> *)
0x1801201c5  cmp     [rsp+0B8h+var_30], 0
0x1801201cd  jnz     short loc_18012021F
0x1801201cf  mov     edi, 80070306h
0x1801201d4  lea     rax, WPP_GLOBAL_Control
0x1801201db  mov     rcx, cs:WPP_GLOBAL_Control
0x1801201e2  cmp     rcx, rax
0x1801201e5  jz      short loc_180120212
0x1801201e7  test    dword ptr [rcx+6Ch], 8000h
0x1801201ee  jz      short loc_180120212
0x1801201f0  cmp     byte ptr [rcx+69h], 1
0x1801201f4  jb      short loc_180120212
0x1801201f6  mov     edx, 95h
0x1801201fb  mov     r9d, 80070306h
0x180120201  lea     r8, WPP_56069f0a00a13e5f2d94d619c5002cd2_Traceguids
0x180120208  mov     rcx, [rcx+60h]
0x18012020c  call    WPP_SF_d
0x180120211  nop
0x180120212  lea     rcx, [rsp+0B8h+var_50]
0x180120217  call    ?Release@?$SmartPointer@VCRepubJetSessionContext@@@@IEAAXXZ; SmartPointer<CRepubJetSessionContext>::Release(void)
0x18012021c  nop
0x18012021d  jmp     short loc_18012022D
0x18012021f  mov     [r15], rbx
0x180120222  lea     rcx, [rsp+0B8h+var_50]
0x180120227  call    ?Release@?$SmartPointer@VCRepubJetSessionContext@@@@IEAAXXZ; SmartPointer<CRepubJetSessionContext>::Release(void)
0x18012022c  nop
0x18012022d  mov     rcx, [rsp+0B8h+Block]; Block
0x180120232  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180120237  nop
0x180120238  lea     rcx, [rsp+0B8h+var_48]
0x18012023d  call    ?Unlock@?$LockSentry@VReadersWriterLock@@$0A@@@QEAAXXZ; LockSentry<ReadersWriterLock,0>::Unlock(void)
0x180120242  jmp     short loc_180120253
0x180120244  lea     rcx, [rsp+0B8h+var_48]
0x180120249  call    ?Unlock@?$LockSentry@VReadersWriterLock@@$0A@@@QEAAXXZ; LockSentry<ReadersWriterLock,0>::Unlock(void)
0x18012024e  mov     edi, 80070306h
0x180120253  lea     rcx, [rsp+0B8h+var_68]
0x180120258  call    ?Release@?$SmartPointer@VCRepubJetSessionContext@@@@IEAAXXZ; SmartPointer<CRepubJetSessionContext>::Release(void)
0x18012025d  mov     eax, edi
0x18012025f  jmp     short loc_1801202AE
0x180120261  lea     rax, WPP_GLOBAL_Control
0x180120268  mov     rcx, cs:WPP_GLOBAL_Control
0x18012026f  cmp     rcx, rax
0x180120272  jz      short loc_18012029F
0x180120274  test    dword ptr [rcx+6Ch], 8000h
0x18012027b  jz      short loc_18012029F
0x18012027d  cmp     byte ptr [rcx+69h], 1
0x180120281  jb      short loc_18012029F
0x180120283  mov     edx, 8Fh
0x180120288  mov     r9d, 80070057h
0x18012028e  lea     r8, WPP_56069f0a00a13e5f2d94d619c5002cd2_Traceguids
0x180120295  mov     rcx, [rcx+60h]
0x180120299  call    WPP_SF_d
0x18012029e  nop
0x18012029f  lea     rcx, [rsp+0B8h+var_68]
0x1801202a4  call    ?Release@?$SmartPointer@VCRepubJetSessionContext@@@@IEAAXXZ; SmartPointer<CRepubJetSessionContext>::Release(void)
0x1801202a9  mov     eax, 80070057h
0x1801202ae  lea     r11, [rsp+0B8h+var_28]
0x1801202b6  mov     rbx, [r11+30h]
0x1801202ba  mov     rsi, [r11+38h]
0x1801202be  mov     rsp, r11
0x1801202c1  pop     r15
0x1801202c3  pop     r14
0x1801202c5  pop     r13
0x1801202c7  pop     r12
0x1801202c9  pop     rdi
0x1801202ca  retn
```
