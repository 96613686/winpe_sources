# CRdpPipeProtocol::InitializeInstance(IRDPCoreVirtualChannel *,IRDPCoreVirtualChannel *,IRDPCoreVirtualChannel *,IRDPCoreVirtualChannel *,IRDPCollection *,IRdpPipeEvents *)

- ea: `0x1800d5550`
- end: `0x1800d5c48`
- name: `?InitializeInstance@CRdpPipeProtocol@@UEAAJPEAUIRDPCoreVirtualChannel@@000PEAUIRDPCollection@@PEAVIRdpPipeEvents@@@Z`
- size: `1784`
- prototype: `__int64 __fastcall(CRdpPipeProtocol *__hidden this, struct IRDPCoreVirtualChannel *, struct IRDPCoreVirtualChannel *, struct IRDPCoreVirtualChannel *, struct IRDPCoreVirtualChannel *, struct IRDPCollection *, struct IRdpPipeEvents *)`
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x18000e4ec`
- `0x180010d6c`
- `0x18002aafc`
- `0x18004f5bc`
- `0x180076090`
- `0x180077aa0`
- `0x180079770`
- `0x18007a404`
- `0x1800d5550`
- `0x1800e0e78`
- `0x180191d58`
- `0x18019c010`

## import_xrefs

- `RDPBASE!?RdpGfxProtocolServerEncoder_CreateInstance@@YAJPEAVIRdpEncoderIO@@PEAPEAVIRdpPipeProtocolEncoderEx@@@Z` at `0x1800d58d5`
- `RDPBASE!?RdpGfxProtocolServerEncoder_CreateInstance@@YAJPEAVIRdpEncoderIO@@PEAPEAVIRdpPipeProtocolEncoderEx@@@Z` at `0x1800d58d5`
- `RDPBASE!?HintCoconet__CreateInstance@@YAJPEAPEAVIRdpPipeCompressHintProvider@@@Z` at `0x1800d581e`
- `RDPBASE!?HintCoconet__CreateInstance@@YAJPEAPEAVIRdpPipeCompressHintProvider@@@Z` at `0x1800d581e`
- `RDPBASE!?CompressRdp8__CreateInstance@@YAJPEAPEAVIRdpPipeCompress@@I@Z` at `0x1800d5764`
- `RDPBASE!?CompressRdp8__CreateInstance@@YAJPEAPEAVIRdpPipeCompress@@I@Z` at `0x1800d5764`
- `RDPBASE!RDPAPI_GetGenericCounter` at `0x1800d5af3`
- `RDPBASE!RDPAPI_GetGenericCounter` at `0x1800d5b24`
- `RDPBASE!RDPAPI_GetGenericCounter` at `0x1800d5b55`
- `RDPBASE!RDPAPI_GetGenericCounter` at `0x1800d5b86`
- `RDPBASE!RDPAPI_GetGenericCounter` at `0x1800d5bb3`
- `RDPBASE!RDPAPI_GetGenericCounter` at `0x1800d5af3`
- `RDPBASE!RDPAPI_GetGenericCounter` at `0x1800d5b24`
- `RDPBASE!RDPAPI_GetGenericCounter` at `0x1800d5b55`
- `RDPBASE!RDPAPI_GetGenericCounter` at `0x1800d5b86`
- `RDPBASE!RDPAPI_GetGenericCounter` at `0x1800d5bb3`
- `OLEAUT32!__imp_VariantInit` at `0x1800d5590`
- `OLEAUT32!__imp_VariantInit` at `0x1800d5590`
- `OLEAUT32!__imp_VariantClear` at `0x1800d5c12`
- `OLEAUT32!__imp_VariantClear` at `0x1800d5c12`

## string_xrefs

- `0x1800d57b0`: `MaxCompressionLevel`
- `0x1800d5689`: `IRdpBaseProtocol::InitializeInstance failed!`
- `0x1800d56bf`: `GfxPipelineTst::BulkCompressor`
- `0x1800d5746`: `QueryInterface failed on test Bulk Compressor`
- `0x1800d579e`: `CompressXXX_CreateInstance failed!`
- `0x1800d5858`: `HintXXX_CreateInstance failed!`
- `0x1800d58ac`: `CompressXXX->Initialize failed!`
- `0x1800d590f`: `RdpGfxProtocolServerEncoder_CreateInstance failed!`
- `0x1800d59a4`: `CTSBufferPool::CreateInstance failed!`
- `0x1800d5a3b`: `RdpGfxProtocolServerDecoder_CreateInstance failed`
- `0x1800d5a8a`: `IRdpPipeProtocolServerDecoder::InitalizeInstance() failed`
- `0x1800d5b12`: `RDV::RDP::GraphicsPipeline::PipelineBulkCompressStart`
- `0x1800d5b43`: `RDV::RDP::GraphicsPipeline::PipelineBulkCompressEnd`
- `0x1800d5ba1`: `RDV::RDP::VirtChan::BufferReady`
- `0x1800d5bdc`: `RDPAPI_GetGenericCounter( RDV::RDP::VirtChan::BufferReady ) failed.  Non-Fatal`

## pseudocode

```c
__int64 __fastcall CRdpPipeProtocol::InitializeInstance(
        CRdpPipeProtocol *this,
        struct IRDPCoreVirtualChannel *a2,
        struct IRDPCoreVirtualChannel *a3,
        struct IRDPCoreVirtualChannel *a4,
        struct IRDPCoreVirtualChannel *a5,
        struct IRDPCollection *a6,
        struct IRdpPipeEvents *a7)
{
  struct IRDPCollection *v11; // r15
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v13; // edx
  const char *v14; // rcx
  int Instance; // ebx
  unsigned int v16; // eax
  int v17; // edx
  const char *v18; // rcx
  __int64 v19; // rax
  unsigned int v20; // eax
  unsigned int v21; // eax
  struct IRdpPipeCompressHintProvider *v22; // rcx
  int v24; // [rsp+30h] [rbp-38h] BYREF
  struct IRdpPipeCompressHintProvider *v25; // [rsp+38h] [rbp-30h] BYREF
  VARIANTARG pvarg; // [rsp+40h] [rbp-28h] BYREF

  v25 = 0;
  v24 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  v11 = a6;
  if ( !a6 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v13 = 21;
    v14 = "pConnProperties";
LABEL_6:
    WPP_SF_Ds(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v13,
      (unsigned int)&WPP_3bbb71033af43e0060aa7c269e4e67ad_Traceguids,
      CurrentThreadActivityIdPrefix,
      (__int64)v14);
LABEL_7:
    Instance = -2147467261;
    goto LABEL_87;
  }
  if ( !a2 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v13 = 22;
    v14 = "pLegacyChannel";
    goto LABEL_6;
  }
  Instance = (*(__int64 (__fastcall **)(_QWORD, struct IRDPCoreVirtualChannel *, struct IRDPCoreVirtualChannel *, struct IRDPCoreVirtualChannel *, struct IRDPCollection *))(**((_QWORD **)this + 17) + 24LL))(
               *((_QWORD *)this + 17),
               a2,
               a4,
               a5,
               a6);
  if ( Instance < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v16 = RdpWppGetCurrentThreadActivityIdPrefix();
      v17 = 23;
      v18 = "IRdpBaseProtocol::InitializeInstance failed!";
LABEL_18:
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v17,
        (unsigned int)&WPP_3bbb71033af43e0060aa7c269e4e67ad_Traceguids,
        v16,
        (__int64)v18,
        Instance);
      goto LABEL_87;
    }
    goto LABEL_87;
  }
  if ( (*(int (__fastcall **)(struct IRDPCollection *, const wchar_t *, VARIANTARG *))(*(_QWORD *)v11 + 24LL))(
         v11,
         L"GfxPipelineTst::BulkCompressor",
         &pvarg) >= 0
    && pvarg.vt == 13 )
  {
    Instance = (**(__int64 (__fastcall ***)(LONGLONG, GUID *, char *))pvarg.llVal)(
                 pvarg.llVal,
                 &IID_IRdpPipeCompress,
                 (char *)this + 816);
    if ( Instance < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v16 = RdpWppGetCurrentThreadActivityIdPrefix();
        v17 = 24;
        v18 = "QueryInterface failed on test Bulk Compressor";
        goto LABEL_18;
      }
      goto LABEL_87;
    }
  }
  else
  {
    Instance = CompressRdp8__CreateInstance((struct IRdpPipeCompress **)this + 102, 4u);
    if ( Instance < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v16 = RdpWppGetCurrentThreadActivityIdPrefix();
        v17 = 25;
        v18 = "CompressXXX_CreateInstance failed!";
        goto LABEL_18;
      }
      goto LABEL_87;
    }
    v19 = *(_QWORD *)v11;
    LODWORD(a6) = 0;
    if ( (*(int (__fastcall **)(struct IRDPCollection *, const wchar_t *, struct IRDPCollection **))(v19 + 40))(
           v11,
           L"MaxCompressionLevel",
           &a6) >= 0
      && !(_DWORD)a6 )
    {
      *((_DWORD *)this + 957) = 1;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v20 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_3bbb71033af43e0060aa7c269e4e67ad_Traceguids, v20);
      }
    }
    if ( !*((_DWORD *)this + 957) )
    {
      Instance = HintCoconet__CreateInstance(&v25);
      if ( Instance < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v16 = RdpWppGetCurrentThreadActivityIdPrefix();
          v17 = 27;
          v18 = "HintXXX_CreateInstance failed!";
          goto LABEL_18;
        }
        goto LABEL_87;
      }
    }
    Instance = (*(__int64 (__fastcall **)(_QWORD, struct IRdpPipeCompressHintProvider *))(**((_QWORD **)this + 102)
                                                                                        + 24LL))(
                 *((_QWORD *)this + 102),
                 v25);
    if ( Instance < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v16 = RdpWppGetCurrentThreadActivityIdPrefix();
        v17 = 28;
        v18 = "CompressXXX->Initialize failed!";
        goto LABEL_18;
      }
      goto LABEL_87;
    }
  }
  Instance = RdpGfxProtocolServerEncoder_CreateInstance(
               (struct IRdpEncoderIO *)(((unsigned __int64)this + 24) & -(__int64)(this != 0)),
               (struct IRdpPipeProtocolEncoderEx **)this + 23);
  if ( Instance >= 0 )
  {
    if ( (*(int (__fastcall **)(_QWORD, const wchar_t *, int *))(**((_QWORD **)this + 14) + 32LL))(
           *((_QWORD *)this + 14),
           L"GfxPipeline::ForceLyncMCUProfile",
           &v24) >= 0
      && v24 )
    {
      *((_DWORD *)this + 186) = 0x10000;
      *((_DWORD *)this + 184) = 327680;
      *((_DWORD *)this + 185) = 163840;
    }
    Instance = RdpEncodeFIFOBuffer::CreateInstance(*((_DWORD *)this + 186), (struct IRdpFIFOBuffer **)this + 21);
    if ( Instance >= 0 )
    {
      Instance = RdpEncodeFIFOBuffer::CreateInstance(*((_DWORD *)this + 184), (struct IRdpFIFOBuffer **)this + 22);
      if ( Instance >= 0 )
      {
        Instance = RdpGfxProtocolServerDecoder_CreateInstance((struct IRdpPipeProtocolServerDecoder **)this + 20);
        if ( Instance >= 0 )
        {
          Instance = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 20) + 24LL))(*((_QWORD *)this + 20));
          if ( Instance >= 0 )
          {
            a6 = (CRdpPipeProtocol *)((char *)this + 712);
            CTSCriticalSection::Lock((CRdpPipeProtocol *)((char *)this + 712));
            TCntPtr<IRDPCoreVirtualChannel>::operator=((char *)this + 144, a3);
            TCntPtr<IRdpPipeEvents>::operator=((char *)this + 152, a7);
            CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&a6);
            Instance = RDPAPI_GetGenericCounter(
                         L"RDV::RDP::GraphicsPipeline::FrameAckReceived",
                         0xFFFFFFFFLL,
                         0xFFFFFFFFLL,
                         0xFFFFFFFFLL,
                         4,
                         (char *)this + 800);
            if ( Instance >= 0 )
            {
              Instance = RDPAPI_GetGenericCounter(
                           L"RDV::RDP::GraphicsPipeline::PipelineBulkCompressStart",
                           0xFFFFFFFFLL,
                           0xFFFFFFFFLL,
                           0xFFFFFFFFLL,
                           4,
                           (char *)this + 776);
              if ( Instance >= 0 )
              {
                Instance = RDPAPI_GetGenericCounter(
                             L"RDV::RDP::GraphicsPipeline::PipelineBulkCompressEnd",
                             0xFFFFFFFFLL,
                             0xFFFFFFFFLL,
                             0xFFFFFFFFLL,
                             4,
                             (char *)this + 784);
                if ( Instance >= 0 )
                {
                  Instance = RDPAPI_GetGenericCounter(
                               L"RDV::RDP::GraphicsPipeline::PipelineThrottle",
                               0xFFFFFFFFLL,
                               0xFFFFFFFFLL,
                               0xFFFFFFFFLL,
                               4,
                               (char *)this + 808);
                  if ( Instance >= 0 )
                  {
                    Instance = RDPAPI_GetGenericCounter(
                                 L"RDV::RDP::VirtChan::BufferReady",
                                 0xFFFFFFFFLL,
                                 0xFFFFFFFFLL,
                                 0xFFFFFFFFLL,
                                 4,
                                 (char *)this + 792);
                    if ( Instance < 0
                      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                    {
                      v21 = RdpWppGetCurrentThreadActivityIdPrefix();
                      WPP_SF_DsD(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        34,
                        (unsigned int)&WPP_3bbb71033af43e0060aa7c269e4e67ad_Traceguids,
                        v21,
                        (__int64)"RDPAPI_GetGenericCounter( RDV::RDP::VirtChan::BufferReady ) failed.  Non-Fatal",
                        Instance);
                    }
                    *((_DWORD *)this + 24) = 0;
                  }
                }
              }
            }
          }
          else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v16 = RdpWppGetCurrentThreadActivityIdPrefix();
            v17 = 33;
            v18 = "IRdpPipeProtocolServerDecoder::InitalizeInstance() failed";
            goto LABEL_18;
          }
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
               && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
               && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v16 = RdpWppGetCurrentThreadActivityIdPrefix();
          v17 = 32;
          v18 = "RdpGfxProtocolServerDecoder_CreateInstance failed";
          goto LABEL_18;
        }
        goto LABEL_87;
      }
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_87;
      }
      v16 = RdpWppGetCurrentThreadActivityIdPrefix();
      v17 = 31;
    }
    else
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_87;
      }
      v16 = RdpWppGetCurrentThreadActivityIdPrefix();
      v17 = 30;
    }
    v18 = "CTSBufferPool::CreateInstance failed!";
    goto LABEL_18;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v16 = RdpWppGetCurrentThreadActivityIdPrefix();
    v17 = 29;
    v18 = "RdpGfxProtocolServerEncoder_CreateInstance failed!";
    goto LABEL_18;
  }
LABEL_87:
  VariantClear(&pvarg);
  v22 = v25;
  if ( v25 )
  {
    v25 = 0;
    (*(void (__fastcall **)(struct IRdpPipeCompressHintProvider *))(*(_QWORD *)v22 + 16LL))(v22);
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x1800d5550  push    rbp
0x1800d5552  push    rbx
0x1800d5553  push    rsi
0x1800d5554  push    rdi
0x1800d5555  push    r12
0x1800d5557  push    r13
0x1800d5559  push    r14
0x1800d555b  push    r15
0x1800d555d  mov     rbp, rsp
0x1800d5560  sub     rsp, 68h
0x1800d5564  mov     rdi, rcx
0x1800d5567  mov     [rbp+var_30], 0
0x1800d556f  xorps   xmm0, xmm0
0x1800d5572  mov     [rbp+var_38], 0
0x1800d5579  xor     eax, eax
0x1800d557b  lea     rcx, [rbp+pvarg]; pvarg
0x1800d557f  movups  xmmword ptr [rbp+pvarg], xmm0
0x1800d5583  mov     qword ptr [rbp+pvarg+10h], rax
0x1800d5587  mov     rsi, r9
0x1800d558a  mov     r13, r8
0x1800d558d  mov     rbx, rdx
0x1800d5590  call    cs:__imp_VariantInit
0x1800d5596  mov     r15, [rbp+arg_28]
0x1800d559a  test    r15, r15
0x1800d559d  jnz     short loc_1800D55F7
0x1800d559f  mov     rax, cs:WPP_GLOBAL_Control
0x1800d55a6  lea     rsi, WPP_GLOBAL_Control
0x1800d55ad  cmp     rax, rsi
0x1800d55b0  jz      short loc_1800D55ED
0x1800d55b2  test    byte ptr [rax+1Ch], 8
0x1800d55b6  jz      short loc_1800D55ED
0x1800d55b8  cmp     byte ptr [rax+19h], 2
0x1800d55bc  jb      short loc_1800D55ED
0x1800d55be  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800d55c3  lea     edx, [r15+15h]
0x1800d55c7  lea     rcx, aPconnpropertie; "pConnProperties"
0x1800d55ce  mov     [rsp+68h+var_48], rcx
0x1800d55d3  lea     r8, WPP_3bbb71033af43e0060aa7c269e4e67ad_Traceguids
0x1800d55da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d55e1  mov     r9d, eax
0x1800d55e4  mov     rcx, [rcx+10h]
0x1800d55e8  call    WPP_SF_Ds
0x1800d55ed  mov     ebx, 80004003h
0x1800d55f2  jmp     loc_1800D5C0E
0x1800d55f7  test    rbx, rbx
0x1800d55fa  jnz     short loc_1800D562C
0x1800d55fc  mov     rax, cs:WPP_GLOBAL_Control
0x1800d5603  lea     rsi, WPP_GLOBAL_Control
0x1800d560a  cmp     rax, rsi
0x1800d560d  jz      short loc_1800D55ED
0x1800d560f  test    byte ptr [rax+1Ch], 8
0x1800d5613  jz      short loc_1800D55ED
0x1800d5615  cmp     byte ptr [rax+19h], 2
0x1800d5619  jb      short loc_1800D55ED
0x1800d561b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800d5620  lea     edx, [rbx+16h]
0x1800d5623  lea     rcx, aPlegacychannel; "pLegacyChannel"
0x1800d562a  jmp     short loc_1800D55CE
0x1800d562c  mov     rcx, [rdi+88h]
0x1800d5633  mov     r8, rsi
0x1800d5636  mov     r9, [rbp+arg_20]
0x1800d563a  mov     rdx, rbx
0x1800d563d  mov     [rsp+68h+var_48], r15
0x1800d5642  mov     rax, [rcx]
0x1800d5645  mov     rax, [rax+18h]
0x1800d5649  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d564e  mov     ebx, eax
0x1800d5650  test    eax, eax
0x1800d5652  jns     short loc_1800D56B8
0x1800d5654  mov     rax, cs:WPP_GLOBAL_Control
0x1800d565b  lea     rsi, WPP_GLOBAL_Control
0x1800d5662  cmp     rax, rsi
0x1800d5665  jz      loc_1800D5C0E
0x1800d566b  test    byte ptr [rax+1Ch], 8
0x1800d566f  jz      loc_1800D5C0E
0x1800d5675  cmp     byte ptr [rax+19h], 2
0x1800d5679  jb      loc_1800D5C0E
0x1800d567f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800d5684  mov     edx, 17h
0x1800d5689  lea     rcx, aIrdpbaseprotoc; "IRdpBaseProtocol::InitializeInstance fa"...
0x1800d5690  lea     r8, WPP_3bbb71033af43e0060aa7c269e4e67ad_Traceguids
0x1800d5697  mov     dword ptr [rsp+68h+var_40], ebx
0x1800d569b  mov     r9d, eax
0x1800d569e  mov     [rsp+68h+var_48], rcx
0x1800d56a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d56aa  mov     rcx, [rcx+10h]
0x1800d56ae  call    WPP_SF_DsD
0x1800d56b3  jmp     loc_1800D5C0E
0x1800d56b8  mov     rax, [r15]
0x1800d56bb  lea     r8, [rbp+pvarg]
0x1800d56bf  lea     rdx, aGfxpipelinetst_1; "GfxPipelineTst::BulkCompressor"
0x1800d56c6  mov     rcx, r15
0x1800d56c9  mov     rax, [rax+18h]
0x1800d56cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d56d2  lea     rsi, WPP_GLOBAL_Control
0x1800d56d9  mov     r12d, 4
0x1800d56df  lea     r14, WPP_3bbb71033af43e0060aa7c269e4e67ad_Traceguids
0x1800d56e6  test    eax, eax
0x1800d56e8  js      short loc_1800D5755
0x1800d56ea  cmp     word ptr [rbp+pvarg], 0Dh
0x1800d56ef  jnz     short loc_1800D5755
0x1800d56f1  mov     rcx, qword ptr [rbp+pvarg+8]
0x1800d56f5  lea     r8, [rdi+330h]
0x1800d56fc  lea     rdx, IID_IRdpPipeCompress
0x1800d5703  mov     rax, [rcx]
0x1800d5706  mov     rax, [rax]
0x1800d5709  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d570e  mov     ebx, eax
0x1800d5710  test    eax, eax
0x1800d5712  jns     loc_1800D58BE
0x1800d5718  mov     rax, cs:WPP_GLOBAL_Control
0x1800d571f  cmp     rax, rsi
0x1800d5722  jz      loc_1800D5C0E
0x1800d5728  test    byte ptr [rax+1Ch], 8
0x1800d572c  jz      loc_1800D5C0E
0x1800d5732  cmp     byte ptr [rax+19h], 2
0x1800d5736  jb      loc_1800D5C0E
0x1800d573c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800d5741  lea     edx, [r12+14h]
0x1800d5746  lea     rcx, aQueryinterface_5; "QueryInterface failed on test Bulk Comp"...
0x1800d574d  mov     r8, r14
0x1800d5750  jmp     loc_1800D5697
0x1800d5755  lea     r12, [rdi+330h]
0x1800d575c  mov     edx, 4
0x1800d5761  mov     rcx, r12
0x1800d5764  call    cs:__imp_?CompressRdp8__CreateInstance@@YAJPEAPEAVIRdpPipeCompress@@I@Z; CompressRdp8__CreateInstance(IRdpPipeCompress * *,uint)
0x1800d576a  mov     ebx, eax
0x1800d576c  test    eax, eax
0x1800d576e  jns     short loc_1800D57A7
0x1800d5770  mov     rax, cs:WPP_GLOBAL_Control
0x1800d5777  cmp     rax, rsi
0x1800d577a  jz      loc_1800D5C0E
0x1800d5780  test    byte ptr [rax+1Ch], 8
0x1800d5784  jz      loc_1800D5C0E
0x1800d578a  cmp     byte ptr [rax+19h], 2
0x1800d578e  jb      loc_1800D5C0E
0x1800d5794  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800d5799  mov     edx, 19h
0x1800d579e  lea     rcx, aCompressxxxCre; "CompressXXX_CreateInstance failed!"
0x1800d57a5  jmp     short loc_1800D574D
0x1800d57a7  mov     rax, [r15]
0x1800d57aa  lea     r8, [rbp+arg_28]
0x1800d57ae  xor     ebx, ebx
0x1800d57b0  lea     rdx, aMaxcompression_0; "MaxCompressionLevel"
0x1800d57b7  mov     rcx, r15
0x1800d57ba  mov     dword ptr [rbp+arg_28], ebx
0x1800d57bd  mov     rax, [rax+28h]
0x1800d57c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d57c6  test    eax, eax
0x1800d57c8  js      short loc_1800D5812
0x1800d57ca  cmp     dword ptr [rbp+arg_28], ebx
0x1800d57cd  jnz     short loc_1800D5812
0x1800d57cf  mov     dword ptr [rdi+0EF4h], 1
0x1800d57d9  mov     rax, cs:WPP_GLOBAL_Control
0x1800d57e0  cmp     rax, rsi
0x1800d57e3  jz      short loc_1800D5812
0x1800d57e5  test    dword ptr [rax+1Ch], 100h
0x1800d57ec  jz      short loc_1800D5812
0x1800d57ee  cmp     byte ptr [rax+19h], 4
0x1800d57f2  jb      short loc_1800D5812
0x1800d57f4  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800d57f9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d5800  lea     edx, [rbx+1Ah]
0x1800d5803  mov     r9d, eax
0x1800d5806  mov     r8, r14
0x1800d5809  mov     rcx, [rcx+10h]
0x1800d580d  call    WPP_SF_d
0x1800d5812  cmp     [rdi+0EF4h], ebx
0x1800d5818  jnz     short loc_1800D5864
0x1800d581a  lea     rcx, [rbp+var_30]
0x1800d581e  call    cs:__imp_?HintCoconet__CreateInstance@@YAJPEAPEAVIRdpPipeCompressHintProvider@@@Z; HintCoconet__CreateInstance(IRdpPipeCompressHintProvider * *)
0x1800d5824  mov     ebx, eax
0x1800d5826  test    eax, eax
0x1800d5828  jns     short loc_1800D5864
0x1800d582a  mov     rax, cs:WPP_GLOBAL_Control
0x1800d5831  cmp     rax, rsi
0x1800d5834  jz      loc_1800D5C0E
0x1800d583a  test    byte ptr [rax+1Ch], 8
0x1800d583e  jz      loc_1800D5C0E
0x1800d5844  cmp     byte ptr [rax+19h], 2
0x1800d5848  jb      loc_1800D5C0E
0x1800d584e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800d5853  mov     edx, 1Bh
0x1800d5858  lea     rcx, aHintxxxCreatei; "HintXXX_CreateInstance failed!"
0x1800d585f  jmp     loc_1800D574D
0x1800d5864  mov     rcx, [r12]
0x1800d5868  mov     rdx, [rbp+var_30]
0x1800d586c  mov     rax, [rcx]
0x1800d586f  mov     rax, [rax+18h]
0x1800d5873  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d5878  mov     ebx, eax
0x1800d587a  test    eax, eax
0x1800d587c  jns     short loc_1800D58B8
0x1800d587e  mov     rax, cs:WPP_GLOBAL_Control
0x1800d5885  cmp     rax, rsi
0x1800d5888  jz      loc_1800D5C0E
0x1800d588e  test    byte ptr [rax+1Ch], 8
0x1800d5892  jz      loc_1800D5C0E
0x1800d5898  cmp     byte ptr [rax+19h], 2
0x1800d589c  jb      loc_1800D5C0E
0x1800d58a2  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800d58a7  mov     edx, 1Ch
0x1800d58ac  lea     rcx, aCompressxxxIni; "CompressXXX->Initialize failed!"
0x1800d58b3  jmp     loc_1800D574D
0x1800d58b8  mov     r12d, 4
0x1800d58be  lea     r8, [rdi+18h]
0x1800d58c2  mov     rax, rdi
0x1800d58c5  neg     rax
0x1800d58c8  lea     rdx, [rdi+0B8h]
0x1800d58cf  sbb     rcx, rcx
0x1800d58d2  and     rcx, r8
0x1800d58d5  call    cs:__imp_?RdpGfxProtocolServerEncoder_CreateInstance@@YAJPEAVIRdpEncoderIO@@PEAPEAVIRdpPipeProtocolEncoderEx@@@Z; RdpGfxProtocolServerEncoder_CreateInstance(IRdpEncoderIO *,IRdpPipeProtocolEncoderEx * *)
0x1800d58db  mov     ebx, eax
0x1800d58dd  test    eax, eax
0x1800d58df  jns     short loc_1800D591B
0x1800d58e1  mov     rax, cs:WPP_GLOBAL_Control
0x1800d58e8  cmp     rax, rsi
0x1800d58eb  jz      loc_1800D5C0E
0x1800d58f1  test    byte ptr [rax+1Ch], 8
0x1800d58f5  jz      loc_1800D5C0E
0x1800d58fb  cmp     byte ptr [rax+19h], 2
0x1800d58ff  jb      loc_1800D5C0E
0x1800d5905  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800d590a  mov     edx, 1Dh
0x1800d590f  lea     rcx, aRdpgfxprotocol; "RdpGfxProtocolServerEncoder_CreateInsta"...
0x1800d5916  jmp     loc_1800D574D
0x1800d591b  mov     rcx, [rdi+70h]
0x1800d591f  lea     r8, [rbp+var_38]
0x1800d5923  lea     rdx, aGfxpipelineFor_1; "GfxPipeline::ForceLyncMCUProfile"
0x1800d592a  mov     rax, [rcx]
0x1800d592d  mov     rax, [rax+20h]
0x1800d5931  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d5936  test    eax, eax
0x1800d5938  js      short loc_1800D595E
0x1800d593a  cmp     [rbp+var_38], 0
0x1800d593e  jz      short loc_1800D595E
0x1800d5940  mov     dword ptr [rdi+2E8h], 10000h
0x1800d594a  mov     dword ptr [rdi+2E0h], 50000h
0x1800d5954  mov     dword ptr [rdi+2E4h], 28000h
0x1800d595e  mov     ecx, [rdi+2E8h]; unsigned int
0x1800d5964  lea     rdx, [rdi+0A8h]; struct IRdpFIFOBuffer **
0x1800d596b  call    ?CreateInstance@RdpEncodeFIFOBuffer@@SAJKPEAPEAVIRdpFIFOBuffer@@@Z; RdpEncodeFIFOBuffer::CreateInstance(ulong,IRdpFIFOBuffer * *)
0x1800d5970  mov     ebx, eax
0x1800d5972  test    eax, eax
0x1800d5974  jns     short loc_1800D59B0
0x1800d5976  mov     rax, cs:WPP_GLOBAL_Control
0x1800d597d  cmp     rax, rsi
0x1800d5980  jz      loc_1800D5C0E
0x1800d5986  test    byte ptr [rax+1Ch], 8
0x1800d598a  jz      loc_1800D5C0E
0x1800d5990  cmp     byte ptr [rax+19h], 2
0x1800d5994  jb      loc_1800D5C0E
0x1800d599a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800d599f  mov     edx, 1Eh
0x1800d59a4  lea     rcx, aCtsbufferpoolC; "CTSBufferPool::CreateInstance failed!"
0x1800d59ab  jmp     loc_1800D574D
0x1800d59b0  mov     ecx, [rdi+2E0h]; unsigned int
0x1800d59b6  lea     rdx, [rdi+0B0h]; struct IRdpFIFOBuffer **
0x1800d59bd  call    ?CreateInstance@RdpEncodeFIFOBuffer@@SAJKPEAPEAVIRdpFIFOBuffer@@@Z; RdpEncodeFIFOBuffer::CreateInstance(ulong,IRdpFIFOBuffer * *)
0x1800d59c2  mov     ebx, eax
0x1800d59c4  test    eax, eax
0x1800d59c6  jns     short loc_1800D59F8
0x1800d59c8  mov     rax, cs:WPP_GLOBAL_Control
0x1800d59cf  cmp     rax, rsi
0x1800d59d2  jz      loc_1800D5C0E
0x1800d59d8  test    byte ptr [rax+1Ch], 8
0x1800d59dc  jz      loc_1800D5C0E
0x1800d59e2  cmp     byte ptr [rax+19h], 2
0x1800d59e6  jb      loc_1800D5C0E
0x1800d59ec  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800d59f1  mov     edx, 1Fh
0x1800d59f6  jmp     short loc_1800D59A4
0x1800d59f8  lea     r15, [rdi+0A0h]
0x1800d59ff  mov     rcx, r15; struct IRdpPipeProtocolServerDecoder **
0x1800d5a02  call    ?RdpGfxProtocolServerDecoder_CreateInstance@@YAJPEAPEAVIRdpPipeProtocolServerDecoder@@@Z; RdpGfxProtocolServerDecoder_CreateInstance(IRdpPipeProtocolServerDecoder * *)
0x1800d5a07  mov     ebx, eax
0x1800d5a09  test    eax, eax
0x1800d5a0b  jns     short loc_1800D5A47
0x1800d5a0d  mov     rax, cs:WPP_GLOBAL_Control
0x1800d5a14  cmp     rax, rsi
0x1800d5a17  jz      loc_1800D5C0E
0x1800d5a1d  test    byte ptr [rax+1Ch], 8
0x1800d5a21  jz      loc_1800D5C0E
0x1800d5a27  cmp     byte ptr [rax+19h], 2
0x1800d5a2b  jb      loc_1800D5C0E
0x1800d5a31  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800d5a36  mov     edx, 20h ; ' '
0x1800d5a3b  lea     rcx, aRdpgfxprotocol_0; "RdpGfxProtocolServerDecoder_CreateInsta"...
0x1800d5a42  jmp     loc_1800D574D
0x1800d5a47  mov     rcx, [r15]
0x1800d5a4a  mov     rax, [rcx]
0x1800d5a4d  mov     rax, [rax+18h]
0x1800d5a51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d5a56  mov     ebx, eax
0x1800d5a58  test    eax, eax
0x1800d5a5a  jns     short loc_1800D5A96
0x1800d5a5c  mov     rax, cs:WPP_GLOBAL_Control
0x1800d5a63  cmp     rax, rsi
0x1800d5a66  jz      loc_1800D5C0E
0x1800d5a6c  test    byte ptr [rax+1Ch], 8
  ... truncated ...
```
