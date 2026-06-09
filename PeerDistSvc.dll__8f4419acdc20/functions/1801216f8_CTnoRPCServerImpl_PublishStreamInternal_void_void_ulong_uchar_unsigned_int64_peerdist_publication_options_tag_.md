# CTnoRPCServerImpl::PublishStreamInternal(void *,void *,ulong,uchar *,unsigned __int64,peerdist_publication_options_tag const *,ulong,uchar *,unsigned __int64 *,void * *)

- ea: `0x1801216f8`
- end: `0x180121dde`
- name: `?PublishStreamInternal@CTnoRPCServerImpl@@IEAAJPEAX0KPEAE_KPEBUpeerdist_publication_options_tag@@K1PEA_KPEAPEAX@Z`
- size: `1766`
- prototype: `__int64 __fastcall(CTnoRPCServerImpl *this, void *, void *, unsigned int, unsigned __int8 *, unsigned __int64, const struct peerdist_publication_options_tag *, unsigned int, unsigned __int8 *, unsigned __int64 *, void **)`
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180121690`
- `0x180143c60`

## callees

- `0x1800024f0`
- `0x180004374`
- `0x180008290`
- `0x18000ecf4`
- `0x180015c28`
- `0x180018170`
- `0x1800191b8`
- `0x18011d8f8`
- `0x1801216f8`
- `0x180125f24`
- `0x180137470`
- `0x180159010`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x18012185a`
- `RPCRT4!RpcImpersonateClient` at `0x18012185a`
- `RPCRT4!RpcRevertToSelf` at `0x1801218ca`
- `RPCRT4!RpcRevertToSelf` at `0x1801218ca`

## string_xrefs

- `0x18012177b`: `PeerDist-Common-Client-Enabled`

## pseudocode

```c
__int64 __fastcall CTnoRPCServerImpl::PublishStreamInternal(
        CTnoRPCServerImpl *this,
        void *a2,
        void *a3,
        unsigned int a4,
        unsigned __int8 *a5,
        unsigned __int64 a6,
        const struct peerdist_publication_options_tag *a7,
        unsigned int a8,
        unsigned __int8 *a9,
        unsigned __int64 *a10,
        void **a11)
{
  unsigned int v11; // r14d
  void **v15; // r13
  void **v17; // rcx
  unsigned int v18; // eax
  signed int PublisherIdentityForCurrentThread; // esi
  int v20; // eax
  CHostedCacheMsgEncoding *v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // rbx
  __int64 v24; // rbx
  __int64 v25; // rbx
  __int64 v26; // rbx
  int v27; // eax
  unsigned int v28; // eax
  int v29; // [rsp+48h] [rbp-C0h]
  void *v30; // [rsp+70h] [rbp-98h] BYREF
  __int64 v31; // [rsp+78h] [rbp-90h] BYREF
  __int64 v32; // [rsp+80h] [rbp-88h] BYREF
  __int64 v33; // [rsp+88h] [rbp-80h] BYREF
  __int64 v34; // [rsp+90h] [rbp-78h] BYREF
  void *Block; // [rsp+98h] [rbp-70h] BYREF
  __int64 v36; // [rsp+A0h] [rbp-68h] BYREF
  __int64 v37; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v38; // [rsp+B0h] [rbp-58h] BYREF
  void *v39; // [rsp+B8h] [rbp-50h]
  Exception *v40; // [rsp+C0h] [rbp-48h] BYREF
  _BYTE v41[64]; // [rsp+C8h] [rbp-40h] BYREF
  int v42; // [rsp+120h] [rbp+18h] BYREF
  int v43; // [rsp+124h] [rbp+1Ch]
  unsigned int v44; // [rsp+128h] [rbp+20h]

  v44 = a4;
  v11 = a4;
  v30 = 0;
  v34 = 0;
  v33 = 0;
  v38 = 0;
  v37 = 0;
  v31 = 0;
  v36 = 0;
  Block = 0;
  if ( a3 )
  {
    v15 = a11;
    if ( a11 )
    {
      if ( !IsLicenseEnabled(L"PeerDist-Common-Client-Enabled") )
      {
        if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x8000) != 0 )
        {
          if ( *((_BYTE *)WPP_GLOBAL_Control + 105) )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 12),
              119,
              WPP_56069f0a00a13e5f2d94d619c5002cd2_Traceguids,
              2147946464LL);
        }
        SmartPointer<CRepubJetSessionContext>::Release(&v36);
        SmartPointer<CRepubJetSessionContext>::Release(&v37);
        SmartPointer<CRepubJetSessionContext>::Release(&v38);
        SmartPointer<CRepubJetSessionContext>::Release(&v33);
        SmartPointer<CRepubJetSessionContext>::Release(&v34);
        return 2147946464LL;
      }
      v32 = 1;
      if ( a7 )
        v32 = (__int64)*a7;
      LockSentry<ReadersWriterLock,0>::LockSentry<ReadersWriterLock,0>(v41, (char *)this + 16);
      if ( a2 )
      {
        v18 = RpcImpersonateClient(a2);
        PublisherIdentityForCurrentThread = v18;
        if ( v18 )
        {
          if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x8000) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 105) )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 120, WPP_56069f0a00a13e5f2d94d619c5002cd2_Traceguids, v18);
          }
          if ( PublisherIdentityForCurrentThread < 0 )
            goto LABEL_51;
          PublisherIdentityForCurrentThread = (unsigned __int16)PublisherIdentityForCurrentThread | 0x80010000;
          goto LABEL_50;
        }
      }
      PublisherIdentityForCurrentThread = GetPublisherIdentityForCurrentThread(v17, (unsigned __int16 **)&Block);
      if ( a2 )
        RpcRevertToSelf();
      if ( PublisherIdentityForCurrentThread )
      {
        if ( PublisherIdentityForCurrentThread > 0 )
          PublisherIdentityForCurrentThread = (unsigned __int16)PublisherIdentityForCurrentThread | 0x80070000;
        if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x8000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 105) )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 12),
            121,
            WPP_56069f0a00a13e5f2d94d619c5002cd2_Traceguids,
            (unsigned int)PublisherIdentityForCurrentThread);
        }
        goto LABEL_50;
      }
      v20 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned __int8 *, _QWORD, unsigned __int64, void *, __int64 *, unsigned int, unsigned __int8 *, _BYTE, void **, __int64 *))(**((_QWORD **)this + 8) + 48LL))(
              *((_QWORD *)this + 8),
              v11,
              a5,
              0,
              a6,
              Block,
              &v32,
              a8,
              a9,
              0,
              &v30,
              &v31);
      PublisherIdentityForCurrentThread = v20;
      if ( v20 < 0 )
      {
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x8000) == 0
          || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
        {
          goto LABEL_51;
        }
        v22 = 122;
        goto LABEL_33;
      }
      v23 = (__int64)v30;
      v39 = v30;
      SmartPointer<CRepubJetSessionContext>::Release(&v34);
      v34 = v23;
      v30 = 0;
      v24 = v31;
      SmartPointer<CRepubJetSessionContext>::Release(&v38);
      v38 = v24;
      v31 = 0;
      if ( (_DWORD)v32 == 1 )
      {
        v43 = HIDWORD(v32);
        v42 = 2;
        LOBYTE(v29) = 0;
        v20 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned __int8 *, _QWORD, unsigned __int64, void *, int *, unsigned int, unsigned __int8 *, int, void **, __int64 *))(**((_QWORD **)this + 8) + 48LL))(
                *((_QWORD *)this + 8),
                v11,
                a5,
                0,
                a6,
                Block,
                &v42,
                a8,
                a9,
                v29,
                &v30,
                &v31);
        PublisherIdentityForCurrentThread = v20;
        if ( v20 == -2147020838 )
        {
          if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x8000) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 123, WPP_56069f0a00a13e5f2d94d619c5002cd2_Traceguids);
          }
          PublisherIdentityForCurrentThread = 0;
        }
        else
        {
          if ( v20 < 0 )
          {
            v21 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
              || (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x8000) == 0
              || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
            {
              goto LABEL_51;
            }
            v22 = 124;
LABEL_33:
            WPP_SF_d(*((_QWORD *)v21 + 12), v22, WPP_56069f0a00a13e5f2d94d619c5002cd2_Traceguids, (unsigned int)v20);
            goto LABEL_51;
          }
          v25 = (__int64)v30;
          SmartPointer<CRepubJetSessionContext>::Release(&v33);
          v33 = v25;
          v30 = 0;
          v26 = v31;
          SmartPointer<CRepubJetSessionContext>::Release(&v37);
          v37 = v26;
          v31 = 0;
        }
      }
      if ( __eh34_try(-1, 0) )
      {
        __eh34_scope_strut(0);
        CPublicationContentId::CreateInstance_PublishStream(
          (int)a3,
          v11,
          (int)a5,
          v32,
          (__int64)Block,
          *((_QWORD *)this + 80),
          (__int64)&v34,
          (__int64)&v33,
          (__int64)&v36);
        CTnoRPCServerImpl::BindThePublicationToClientInstance(this, a3, &v36);
        if ( a10 )
          *a10 = *((_QWORD *)this + 80);
        *v15 = v39;
      }
      if ( __eh34_catch(0) )
      {
        if ( __eh34_catch_type(0, &Exception `RTTI Type Descriptor', &v40) )
        {
          v28 = (*(__int64 (__fastcall **)(Exception *))(*(_QWORD *)v40 + 8LL))(v40);
          v42 = v28;
          if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x8000) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 105) )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 125, WPP_56069f0a00a13e5f2d94d619c5002cd2_Traceguids, v28);
          }
          v11 = v44;
          PublisherIdentityForCurrentThread = v42;
          __eh34_try_continuation(0, &Exception `RTTI Type Descriptor', &loc_180121C41);
          goto LABEL_50;
        }
        if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
        {
          if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x8000) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 105) )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 126, WPP_56069f0a00a13e5f2d94d619c5002cd2_Traceguids);
          }
          v42 = -2147024882;
          PublisherIdentityForCurrentThread = -2147024882;
          v11 = v44;
          __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_180121C5D);
          goto LABEL_51;
        }
        if ( __eh34_catch_type(0, &exception `RTTI Type Descriptor', 0) )
        {
          if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x8000) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 105) )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 127, WPP_56069f0a00a13e5f2d94d619c5002cd2_Traceguids);
          }
          v42 = -2147024122;
          PublisherIdentityForCurrentThread = -2147024122;
          v11 = v44;
          __eh34_try_continuation(0, &exception `RTTI Type Descriptor', &loc_180121C5F);
          goto LABEL_51;
        }
      }
LABEL_50:
      if ( PublisherIdentityForCurrentThread >= 0 )
      {
LABEL_57:
        operator delete(Block);
        LockSentry<ReadersWriterLock,0>::Unlock(v41);
        SmartPointer<CRepubJetSessionContext>::Release(&v36);
        SmartPointer<CRepubJetSessionContext>::Release(&v37);
        SmartPointer<CRepubJetSessionContext>::Release(&v38);
        SmartPointer<CRepubJetSessionContext>::Release(&v33);
        SmartPointer<CRepubJetSessionContext>::Release(&v34);
        return (unsigned int)PublisherIdentityForCurrentThread;
      }
LABEL_51:
      if ( ITnoLoggingMgr::s_spLoggingMgr )
      {
        v27 = (*(__int64 (__fastcall **)(__int64, _QWORD, unsigned __int8 *, _QWORD))(*(_QWORD *)ITnoLoggingMgr::s_spLoggingMgr
                                                                                    + 184LL))(
                ITnoLoggingMgr::s_spLoggingMgr,
                v11,
                a5,
                (unsigned int)PublisherIdentityForCurrentThread);
        if ( v27 < 0
          && WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x8000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 105) )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 12),
            128,
            WPP_56069f0a00a13e5f2d94d619c5002cd2_Traceguids,
            (unsigned int)v27);
        }
      }
      goto LABEL_57;
    }
  }
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x8000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 118, WPP_56069f0a00a13e5f2d94d619c5002cd2_Traceguids, 2147942487LL);
  }
  SmartPointer<CRepubJetSessionContext>::Release(&v36);
  SmartPointer<CRepubJetSessionContext>::Release(&v37);
  SmartPointer<CRepubJetSessionContext>::Release(&v38);
  SmartPointer<CRepubJetSessionContext>::Release(&v33);
  SmartPointer<CRepubJetSessionContext>::Release(&v34);
  return 2147942487LL;
}

```

## disassembly

```asm
0x1801216f8  mov     rax, rsp
0x1801216fb  mov     [rax+8], rbx
0x1801216ff  mov     [rax+20h], r9d
0x180121703  push    rsi
0x180121704  push    r12
0x180121706  push    r13
0x180121708  push    r14
0x18012170a  push    r15
0x18012170c  sub     rsp, 0E0h
0x180121713  mov     r14d, r9d
0x180121716  mov     r12, r8
0x180121719  mov     rbx, rdx
0x18012171c  mov     r15, rcx
0x18012171f  mov     [rsp+108h+var_98], 0
0x180121728  mov     qword ptr [rax-78h], 0
0x180121730  mov     qword ptr [rax-80h], 0
0x180121738  mov     qword ptr [rax-58h], 0
0x180121740  mov     qword ptr [rax-60h], 0
0x180121748  mov     [rsp+108h+var_90], 0
0x180121751  mov     qword ptr [rax-68h], 0
0x180121759  mov     qword ptr [rax-70h], 0
0x180121761  test    r8, r8
0x180121764  jz      loc_180121D3D
0x18012176a  mov     r13, [rsp+108h+arg_50]
0x180121772  test    r13, r13
0x180121775  jz      loc_180121D3D
0x18012177b  lea     rcx, aPeerdistCommon; "PeerDist-Common-Client-Enabled"
0x180121782  call    ?IsLicenseEnabled@@YA_NPEBG@Z; IsLicenseEnabled(ushort const *)
0x180121787  test    al, al
0x180121789  jnz     loc_18012181C
0x18012178f  lea     rbx, WPP_GLOBAL_Control
0x180121796  mov     rcx, cs:WPP_GLOBAL_Control
0x18012179d  cmp     rcx, rbx
0x1801217a0  jz      short loc_1801217CD
0x1801217a2  test    dword ptr [rcx+6Ch], 8000h
0x1801217a9  jz      short loc_1801217CD
0x1801217ab  cmp     byte ptr [rcx+69h], 1
0x1801217af  jb      short loc_1801217CD
0x1801217b1  mov     edx, 77h ; 'w'
0x1801217b6  mov     r9d, 80070FE0h
0x1801217bc  lea     r8, WPP_56069f0a00a13e5f2d94d619c5002cd2_Traceguids
0x1801217c3  mov     rcx, [rcx+60h]
0x1801217c7  call    WPP_SF_d
0x1801217cc  nop
0x1801217cd  lea     rcx, [rsp+108h+var_68]
0x1801217d5  call    ?Release@?$SmartPointer@VCRepubJetSessionContext@@@@IEAAXXZ; SmartPointer<CRepubJetSessionContext>::Release(void)
0x1801217da  nop
0x1801217db  lea     rcx, [rsp+108h+var_60]
0x1801217e3  call    ?Release@?$SmartPointer@VCRepubJetSessionContext@@@@IEAAXXZ; SmartPointer<CRepubJetSessionContext>::Release(void)
0x1801217e8  nop
0x1801217e9  lea     rcx, [rsp+108h+var_58]
0x1801217f1  call    ?Release@?$SmartPointer@VCRepubJetSessionContext@@@@IEAAXXZ; SmartPointer<CRepubJetSessionContext>::Release(void)
0x1801217f6  nop
0x1801217f7  lea     rcx, [rsp+108h+var_80]
0x1801217ff  call    ?Release@?$SmartPointer@VCRepubJetSessionContext@@@@IEAAXXZ; SmartPointer<CRepubJetSessionContext>::Release(void)
0x180121804  nop
0x180121805  lea     rcx, [rsp+108h+var_78]
0x18012180d  call    ?Release@?$SmartPointer@VCRepubJetSessionContext@@@@IEAAXXZ; SmartPointer<CRepubJetSessionContext>::Release(void)
0x180121812  mov     eax, 80070FE0h
0x180121817  jmp     loc_180121DC5
0x18012181c  mov     [rsp+108h+var_88], 1
0x180121828  mov     rax, [rsp+108h+arg_30]
0x180121830  test    rax, rax
0x180121833  jz      short loc_180121840
0x180121835  mov     rax, [rax]
0x180121838  mov     [rsp+108h+var_88], rax
0x180121840  lea     rdx, [r15+10h]
0x180121844  lea     rcx, [rsp+108h+var_40]
0x18012184c  call    ??0?$LockSentry@VReadersWriterLock@@$0A@@@QEAA@AEAVReadersWriterLock@@@Z; LockSentry<ReadersWriterLock,0>::LockSentry<ReadersWriterLock,0>(ReadersWriterLock &)
0x180121851  nop
0x180121852  test    rbx, rbx
0x180121855  jz      short loc_1801218B6
0x180121857  mov     rcx, rbx; BindingHandle
0x18012185a  call    cs:__imp_RpcImpersonateClient
0x180121860  mov     esi, eax
0x180121862  test    eax, eax
0x180121864  jz      short loc_1801218B6
0x180121866  lea     rbx, WPP_GLOBAL_Control
0x18012186d  mov     rcx, cs:WPP_GLOBAL_Control
0x180121874  cmp     rcx, rbx
0x180121877  jz      short loc_1801218A0
0x180121879  test    dword ptr [rcx+6Ch], 8000h
0x180121880  jz      short loc_1801218A0
0x180121882  cmp     byte ptr [rcx+69h], 1
0x180121886  jb      short loc_1801218A0
0x180121888  mov     edx, 78h ; 'x'
0x18012188d  mov     r9d, eax
0x180121890  lea     r8, WPP_56069f0a00a13e5f2d94d619c5002cd2_Traceguids
0x180121897  mov     rcx, [rcx+60h]
0x18012189b  call    WPP_SF_d
0x1801218a0  test    esi, esi
0x1801218a2  js      loc_180121C75
0x1801218a8  movzx   esi, si
0x1801218ab  or      esi, 80010000h
0x1801218b1  jmp     loc_180121C57
0x1801218b6  lea     rdx, [rsp+108h+Block]; unsigned __int16 **
0x1801218be  call    ?GetPublisherIdentityForCurrentThread@@YAKPEAPEAXPEAPEAG@Z; GetPublisherIdentityForCurrentThread(void * *,ushort * *)
0x1801218c3  mov     esi, eax
0x1801218c5  test    rbx, rbx
0x1801218c8  jz      short loc_1801218D0
0x1801218ca  call    cs:__imp_RpcRevertToSelf
0x1801218d0  test    esi, esi
0x1801218d2  jz      short loc_18012192A
0x1801218d4  jle     short loc_1801218DF
0x1801218d6  movzx   esi, si
0x1801218d9  or      esi, 80070000h
0x1801218df  lea     rbx, WPP_GLOBAL_Control
0x1801218e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1801218ed  cmp     rcx, rbx
0x1801218f0  jz      loc_180121C57
0x1801218f6  test    dword ptr [rcx+6Ch], 8000h
0x1801218fd  jz      loc_180121C57
0x180121903  cmp     byte ptr [rcx+69h], 1
0x180121907  jb      loc_180121C57
0x18012190d  mov     edx, 79h ; 'y'
0x180121912  mov     r9d, esi
0x180121915  lea     r8, WPP_56069f0a00a13e5f2d94d619c5002cd2_Traceguids
0x18012191c  mov     rcx, [rcx+60h]
0x180121920  call    WPP_SF_d
0x180121925  jmp     loc_180121C57
0x18012192a  mov     rcx, [r15+40h]
0x18012192e  mov     rax, [rcx]
0x180121931  lea     rdx, [rsp+108h+var_90]
0x180121936  mov     [rsp+108h+var_B0], rdx
0x18012193b  lea     rdx, [rsp+108h+var_98]
0x180121940  mov     [rsp+108h+var_B8], rdx
0x180121945  mov     [rsp+108h+var_C0], 0
0x18012194a  mov     rdx, [rsp+108h+arg_40]
0x180121952  mov     [rsp+108h+var_C8], rdx
0x180121957  mov     edx, [rsp+108h+arg_38]
0x18012195e  mov     dword ptr [rsp+108h+var_D0], edx
0x180121962  lea     rdx, [rsp+108h+var_88]
0x18012196a  mov     [rsp+108h+var_D8], rdx
0x18012196f  mov     rdx, [rsp+108h+Block]
0x180121977  mov     [rsp+108h+var_E0], rdx
0x18012197c  mov     rdx, [rsp+108h+arg_28]
0x180121984  mov     [rsp+108h+var_E8], rdx
0x180121989  xor     r9d, r9d
0x18012198c  mov     r8, [rsp+108h+arg_20]
0x180121994  mov     edx, r14d
0x180121997  mov     rax, [rax+30h]
0x18012199b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801219a0  mov     esi, eax
0x1801219a2  test    eax, eax
0x1801219a4  jns     short loc_1801219F1
0x1801219a6  lea     rbx, WPP_GLOBAL_Control
0x1801219ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1801219b4  cmp     rcx, rbx
0x1801219b7  jz      loc_180121C75
0x1801219bd  test    dword ptr [rcx+6Ch], 8000h
0x1801219c4  jz      loc_180121C75
0x1801219ca  cmp     byte ptr [rcx+69h], 1
0x1801219ce  jb      loc_180121C75
0x1801219d4  mov     edx, 7Ah ; 'z'
0x1801219d9  mov     r9d, eax
0x1801219dc  lea     r8, WPP_56069f0a00a13e5f2d94d619c5002cd2_Traceguids
0x1801219e3  mov     rcx, [rcx+60h]
0x1801219e7  call    WPP_SF_d
0x1801219ec  jmp     loc_180121C75
0x1801219f1  mov     rbx, [rsp+108h+var_98]
0x1801219f6  mov     [rsp+108h+var_50], rbx
0x1801219fe  lea     rcx, [rsp+108h+var_78]
0x180121a06  call    ?Release@?$SmartPointer@VCRepubJetSessionContext@@@@IEAAXXZ; SmartPointer<CRepubJetSessionContext>::Release(void)
0x180121a0b  mov     [rsp+108h+var_78], rbx
0x180121a13  mov     [rsp+108h+var_98], 0
0x180121a1c  mov     rbx, [rsp+108h+var_90]
0x180121a21  lea     rcx, [rsp+108h+var_58]
0x180121a29  call    ?Release@?$SmartPointer@VCRepubJetSessionContext@@@@IEAAXXZ; SmartPointer<CRepubJetSessionContext>::Release(void)
0x180121a2e  mov     [rsp+108h+var_58], rbx
0x180121a36  mov     [rsp+108h+var_90], 0
0x180121a3f  cmp     dword ptr [rsp+108h+var_88], 1
0x180121a47  jnz     loc_180121BA7
0x180121a4d  mov     rax, [rsp+108h+var_88]
0x180121a55  mov     [rsp+108h+arg_10], rax
0x180121a5d  mov     dword ptr [rsp+108h+arg_10], 2
0x180121a68  mov     rcx, [r15+40h]
0x180121a6c  mov     rax, [rcx]
0x180121a6f  lea     rdx, [rsp+108h+var_90]
0x180121a74  mov     [rsp+108h+var_B0], rdx
0x180121a79  lea     rdx, [rsp+108h+var_98]
0x180121a7e  mov     [rsp+108h+var_B8], rdx
0x180121a83  mov     [rsp+108h+var_C0], 0
0x180121a88  mov     rdx, [rsp+108h+arg_40]
0x180121a90  mov     [rsp+108h+var_C8], rdx
0x180121a95  mov     edx, [rsp+108h+arg_38]
0x180121a9c  mov     dword ptr [rsp+108h+var_D0], edx
0x180121aa0  lea     rdx, [rsp+108h+arg_10]
0x180121aa8  mov     [rsp+108h+var_D8], rdx
0x180121aad  mov     rdx, [rsp+108h+Block]
0x180121ab5  mov     [rsp+108h+var_E0], rdx
0x180121aba  mov     rdx, [rsp+108h+arg_28]
0x180121ac2  mov     [rsp+108h+var_E8], rdx
0x180121ac7  xor     r9d, r9d
0x180121aca  mov     r8, [rsp+108h+arg_20]
0x180121ad2  mov     edx, r14d
0x180121ad5  mov     rax, [rax+30h]
0x180121ad9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180121ade  mov     esi, eax
0x180121ae0  cmp     eax, 80070FDAh
0x180121ae5  jnz     short loc_180121B25
0x180121ae7  lea     rbx, WPP_GLOBAL_Control
0x180121aee  mov     rcx, cs:WPP_GLOBAL_Control
0x180121af5  cmp     rcx, rbx
0x180121af8  jz      short loc_180121B1E
0x180121afa  test    dword ptr [rcx+6Ch], 8000h
0x180121b01  jz      short loc_180121B1E
0x180121b03  cmp     byte ptr [rcx+69h], 4
0x180121b07  jb      short loc_180121B1E
0x180121b09  mov     edx, 7Bh ; '{'
0x180121b0e  lea     r8, WPP_56069f0a00a13e5f2d94d619c5002cd2_Traceguids
0x180121b15  mov     rcx, [rcx+60h]
0x180121b19  call    WPP_SF_
0x180121b1e  xor     esi, esi
0x180121b20  jmp     loc_180121BAE
0x180121b25  test    eax, eax
0x180121b27  jns     short loc_180121B61
0x180121b29  lea     rbx, WPP_GLOBAL_Control
0x180121b30  mov     rcx, cs:WPP_GLOBAL_Control
0x180121b37  cmp     rcx, rbx
0x180121b3a  jz      loc_180121C75
0x180121b40  test    dword ptr [rcx+6Ch], 8000h
0x180121b47  jz      loc_180121C75
0x180121b4d  cmp     byte ptr [rcx+69h], 1
0x180121b51  jb      loc_180121C75
0x180121b57  mov     edx, 7Ch ; '|'
0x180121b5c  jmp     loc_1801219D9
0x180121b61  mov     rbx, [rsp+108h+var_98]
0x180121b66  lea     rcx, [rsp+108h+var_80]
0x180121b6e  call    ?Release@?$SmartPointer@VCRepubJetSessionContext@@@@IEAAXXZ; SmartPointer<CRepubJetSessionContext>::Release(void)
0x180121b73  mov     [rsp+108h+var_80], rbx
0x180121b7b  mov     [rsp+108h+var_98], 0
0x180121b84  mov     rbx, [rsp+108h+var_90]
0x180121b89  lea     rcx, [rsp+108h+var_60]
0x180121b91  call    ?Release@?$SmartPointer@VCRepubJetSessionContext@@@@IEAAXXZ; SmartPointer<CRepubJetSessionContext>::Release(void)
0x180121b96  mov     [rsp+108h+var_60], rbx
0x180121b9e  mov     [rsp+108h+var_90], 0
0x180121ba7  lea     rbx, WPP_GLOBAL_Control
0x180121bae  lea     rax, [rsp+108h+var_68]
0x180121bb6  mov     [rsp+108h+var_C8], rax
0x180121bbb  lea     rax, [rsp+108h+var_80]
0x180121bc3  mov     [rsp+108h+var_D0], rax
0x180121bc8  lea     rax, [rsp+108h+var_78]
0x180121bd0  mov     [rsp+108h+var_D8], rax
0x180121bd5  mov     rax, [r15+280h]
0x180121bdc  mov     [rsp+108h+var_E0], rax
0x180121be1  mov     rax, [rsp+108h+Block]
0x180121be9  mov     [rsp+108h+var_E8], rax
0x180121bee  mov     r9d, dword ptr [rsp+108h+var_88]
0x180121bf6  mov     r8, [rsp+108h+arg_20]
0x180121bfe  mov     edx, r14d
0x180121c01  mov     rcx, r12
0x180121c04  call    ?CreateInstance_PublishStream@CPublicationContentId@@SAXPEAXKPEAEKPEAG_KAEAV?$SmartPointer@VITnoPublication@@@@4AEAV?$SmartPointer@VCPublicationContentId@@@@@Z; CPublicationContentId::CreateInstance_PublishStream(void *,ulong,uchar *,ulong,ushort *,unsigned __int64,SmartPointer<ITnoPublication> &,SmartPointer<ITnoPublication> &,SmartPointer<CPublicationContentId> &)
0x180121c09  lea     r8, [rsp+108h+var_68]
0x180121c11  mov     rdx, r12
0x180121c14  mov     rcx, r15
0x180121c17  call    ?BindThePublicationToClientInstance@CTnoRPCServerImpl@@QEAAXPEAXAEAV?$SmartPointer@VCPublicationContentId@@@@@Z; CTnoRPCServerImpl::BindThePublicationToClientInstance(void *,SmartPointer<CPublicationContentId> &)
0x180121c1c  mov     rcx, [rsp+108h+arg_48]
0x180121c24  test    rcx, rcx
0x180121c27  jz      short loc_180121C33
0x180121c29  mov     rax, [r15+280h]
0x180121c30  mov     [rcx], rax
0x180121c33  mov     rax, [rsp+108h+var_50]
0x180121c3b  mov     [r13+0], rax
0x180121c3f  jmp     short loc_180121C57
0x180121c41  lea     rbx, WPP_GLOBAL_Control
0x180121c48  mov     r14d, [rsp+108h+arg_18]
0x180121c50  mov     esi, dword ptr [rsp+108h+arg_10]
0x180121c57  test    esi, esi
0x180121c59  jns     short loc_180121CD5
0x180121c5b  jmp     short loc_180121C75
0x180121c5d  jmp     short $+2
0x180121c5f  mov     esi, dword ptr [rsp+108h+arg_10]
0x180121c66  mov     r14d, [rsp+108h+arg_18]
0x180121c6e  lea     rbx, WPP_GLOBAL_Control
0x180121c75  mov     rcx, cs:?s_spLoggingMgr@ITnoLoggingMgr@@0V?$auto_ptr@VITnoLoggingMgr@@@std@@A; std::auto_ptr<ITnoLoggingMgr> ITnoLoggingMgr::s_spLoggingMgr
0x180121c7c  test    rcx, rcx
0x180121c7f  jz      short loc_180121CD5
0x180121c81  mov     rax, [rcx]
0x180121c84  mov     r9d, esi
0x180121c87  mov     r8, [rsp+108h+arg_20]
0x180121c8f  mov     edx, r14d
0x180121c92  mov     rax, [rax+0B8h]
0x180121c99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180121c9e  test    eax, eax
0x180121ca0  jns     short loc_180121CD5
0x180121ca2  mov     rcx, cs:WPP_GLOBAL_Control
0x180121ca9  cmp     rcx, rbx
0x180121cac  jz      short loc_180121CD5
0x180121cae  test    dword ptr [rcx+6Ch], 8000h
0x180121cb5  jz      short loc_180121CD5
0x180121cb7  cmp     byte ptr [rcx+69h], 1
0x180121cbb  jb      short loc_180121CD5
0x180121cbd  mov     edx, 80h
0x180121cc2  mov     r9d, eax
0x180121cc5  lea     r8, WPP_56069f0a00a13e5f2d94d619c5002cd2_Traceguids
0x180121ccc  mov     rcx, [rcx+60h]
0x180121cd0  call    WPP_SF_d
0x180121cd5  mov     rcx, [rsp+108h+Block]; Block
0x180121cdd  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180121ce2  nop
  ... truncated ...
```
