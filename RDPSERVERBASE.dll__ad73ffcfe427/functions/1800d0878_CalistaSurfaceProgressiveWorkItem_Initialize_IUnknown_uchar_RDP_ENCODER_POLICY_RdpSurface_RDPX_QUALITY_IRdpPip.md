# CalistaSurfaceProgressiveWorkItem::Initialize(IUnknown *,uchar,_RDP_ENCODER_POLICY_ *,RdpSurface *,_RDPX_QUALITY,IRdpPipeEvents *)

- ea: `0x1800d0878`
- end: `0x1800d0ca3`
- name: `?Initialize@CalistaSurfaceProgressiveWorkItem@@QEAAJPEAUIUnknown@@EPEAU_RDP_ENCODER_POLICY_@@PEAVRdpSurface@@T_RDPX_QUALITY@@PEAVIRdpPipeEvents@@@Z`
- size: `1067`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800b3810`

## callees

- `0x180010d6c`
- `0x180076090`
- `0x180077aa0`
- `0x180079770`
- `0x18007cf90`
- `0x1800d0178`
- `0x1800d0878`
- `0x180158180`
- `0x18019c010`

## import_xrefs

- `RDPBASE!RDPAPI_GetGenericCounter` at `0x1800d0bdf`
- `RDPBASE!RDPAPI_GetGenericCounter` at `0x1800d0c0b`
- `RDPBASE!RDPAPI_GetGenericCounter` at `0x1800d0bdf`
- `RDPBASE!RDPAPI_GetGenericCounter` at `0x1800d0c0b`

## string_xrefs

- `0x1800d0a62`: `failed to create workItem BA`
- `0x1800d08ef`: `pUnkCompressor`
- `0x1800d09a0`: `CaSrfProgWorkItemError_InitializeCreateEncNodePoolFail`
- `0x1800d09f2`: `failed to create pool of encoding nodes`
- `0x1800d0a10`: `CaSrfProgWorkItemError_InitializeCreateBAFail`
- `0x1800d0a83`: `CaSrfProgWorkItemError_InitializeCreateBAFail`
- `0x1800d0b40`: `CaSrfProgWorkItemError_InitializeCreateEncSrfCtxFail`
- `0x1800d0b92`: `CreateEncodingSurfaceContext failed.`
- `0x1800d0c6e`: `Invalid progressive compressor.`

## pseudocode

```c
__int64 __fastcall CalistaSurfaceProgressiveWorkItem::Initialize(
        __int64 a1,
        int (__fastcall ***a2)(_QWORD, GUID *, __int64),
        char a3,
        __int64 a4,
        __int64 a5,
        unsigned __int8 a6,
        __int64 a7)
{
  unsigned int GenericCounter; // ebx
  unsigned int v12; // eax
  int v13; // edx
  const char *v14; // rcx
  signed int Instance; // eax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  signed int v17; // eax
  unsigned int v18; // eax
  int v19; // edx
  signed int v20; // eax
  signed int v21; // eax
  unsigned int v22; // eax
  unsigned int v23; // eax
  int v25; // [rsp+20h] [rbp-48h]

  if ( a2 )
  {
    if ( a5 )
    {
      *(_DWORD *)(a1 + 28) |= 2u;
      Instance = CTSObjectPool<CEncodingNode>::CreateInstance(a1, a2, a1 + 152);
      GenericCounter = Instance;
      if ( Instance < 0 )
      {
        RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
          (RDPGraphicsTraceLogging *)"IID_CalistaSurfaceProgressiveWorkItem",
          "CaSrfProgWorkItemError_InitializeCreateEncNodePoolFail",
          (char *)0xA1,
          Instance,
          v25);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            21,
            (unsigned int)WPP_ddbde35ae9e63e27ac3a8a9cfef3756a_Traceguids,
            CurrentThreadActivityIdPrefix,
            (__int64)"failed to create pool of encoding nodes",
            GenericCounter);
        }
        return GenericCounter;
      }
      v17 = RgnlibBA_CreateInstance(a1 + 120);
      GenericCounter = v17;
      if ( v17 >= 0 )
      {
        v20 = RgnlibBA_CreateInstance(a1 + 128);
        GenericCounter = v20;
        if ( v20 >= 0 )
        {
          if ( !*(_QWORD *)(a5 + 376) )
            *(_DWORD *)(a1 + 184) = *(_DWORD *)(a4 + 12);
          *(_DWORD *)(a1 + 144) = a6;
          if ( (**a2)(a2, &IID_IRdpProgressiveCompressorEx, a1 + 104) < 0 )
          {
            GenericCounter = -2147467259;
            RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
              (RDPGraphicsTraceLogging *)"IID_CalistaSurfaceProgressiveWorkItem",
              "CaSrfProgWorkItemError_InitializeInvalidProgCmp",
              (char *)0xBC,
              0x80004005,
              v25);
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v23 = RdpWppGetCurrentThreadActivityIdPrefix();
              WPP_SF_DsD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                25,
                (unsigned int)WPP_ddbde35ae9e63e27ac3a8a9cfef3756a_Traceguids,
                v23,
                (__int64)"Invalid progressive compressor.",
                5);
            }
          }
          else
          {
            v21 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64))(**(_QWORD **)(a1 + 104) + 24LL))(
                    *(_QWORD *)(a1 + 104),
                    *(_QWORD *)(a5 + 624),
                    *(unsigned int *)(a1 + 184),
                    a1 + 112);
            GenericCounter = v21;
            if ( v21 >= 0 )
            {
              *(_WORD *)(a1 + 64) = *(_WORD *)(a5 + 56);
              *(_BYTE *)(a1 + 96) = a3;
              TCntPtr<IRdpPipeEvents>::operator=(a1 + 88, a7);
              GenericCounter = RDPAPI_GetGenericCounter(
                                 L"RDV::RDP::GraphicsPipeline::WorkItemCodecStart",
                                 0xFFFFFFFFLL,
                                 0xFFFFFFFFLL,
                                 0xFFFFFFFFLL,
                                 4,
                                 a1 + 72);
              if ( (GenericCounter & 0x80000000) == 0 )
              {
                GenericCounter = RDPAPI_GetGenericCounter(
                                   L"RDV::RDP::GraphicsPipeline::WorkItemCodecEnd",
                                   0xFFFFFFFFLL,
                                   0xFFFFFFFFLL,
                                   0xFFFFFFFFLL,
                                   4,
                                   a1 + 80);
                if ( (GenericCounter & 0x80000000) == 0 )
                  return 0;
              }
            }
            else
            {
              RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
                (RDPGraphicsTraceLogging *)"IID_CalistaSurfaceProgressiveWorkItem",
                "CaSrfProgWorkItemError_InitializeCreateEncSrfCtxFail",
                (char *)0xB6,
                v21,
                v25);
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                v22 = RdpWppGetCurrentThreadActivityIdPrefix();
                WPP_SF_DsD(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  24,
                  (unsigned int)WPP_ddbde35ae9e63e27ac3a8a9cfef3756a_Traceguids,
                  v22,
                  (__int64)"CreateEncodingSurfaceContext failed.",
                  GenericCounter);
              }
            }
          }
          return GenericCounter;
        }
        RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
          (RDPGraphicsTraceLogging *)"IID_CalistaSurfaceProgressiveWorkItem",
          "CaSrfProgWorkItemError_InitializeCreateBAFail",
          (char *)0xA9,
          v20,
          v25);
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          return GenericCounter;
        }
        v18 = RdpWppGetCurrentThreadActivityIdPrefix();
        v19 = 23;
      }
      else
      {
        RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
          (RDPGraphicsTraceLogging *)"IID_CalistaSurfaceProgressiveWorkItem",
          "CaSrfProgWorkItemError_InitializeCreateBAFail",
          (char *)0xA5,
          v17,
          v25);
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          return GenericCounter;
        }
        v18 = RdpWppGetCurrentThreadActivityIdPrefix();
        v19 = 22;
      }
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v19,
        (unsigned int)WPP_ddbde35ae9e63e27ac3a8a9cfef3756a_Traceguids,
        v18,
        (__int64)"failed to create workItem BA",
        GenericCounter);
      return GenericCounter;
    }
    GenericCounter = -2147467261;
    RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
      (RDPGraphicsTraceLogging *)"IID_CalistaSurfaceProgressiveWorkItem",
      "CaSrfProgWorkItemError_InitializeNullPtr",
      (char *)0x99,
      0x80004003,
      v25);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v12 = RdpWppGetCurrentThreadActivityIdPrefix();
      v13 = 19;
      v14 = "pSurface";
      goto LABEL_6;
    }
  }
  else
  {
    GenericCounter = -2147467261;
    RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
      (RDPGraphicsTraceLogging *)"IID_CalistaSurfaceProgressiveWorkItem",
      "CaSrfProgWorkItemError_InitializeNullPtr",
      (char *)0x97,
      0x80004003,
      v25);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v12 = RdpWppGetCurrentThreadActivityIdPrefix();
      v13 = 18;
      v14 = "pUnkCompressor";
LABEL_6:
      WPP_SF_Ds(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v13,
        (unsigned int)WPP_ddbde35ae9e63e27ac3a8a9cfef3756a_Traceguids,
        v12,
        (__int64)v14);
    }
  }
  return GenericCounter;
}

```

## disassembly

```asm
0x1800d0878  push    rbx
0x1800d087a  push    rbp
0x1800d087b  push    rsi
0x1800d087c  push    rdi
0x1800d087d  push    r14
0x1800d087f  push    r15
0x1800d0881  sub     rsp, 38h
0x1800d0885  mov     rbp, r9
0x1800d0888  mov     r15b, r8b
0x1800d088b  mov     r14, rdx
0x1800d088e  mov     rdi, rcx
0x1800d0891  test    rdx, rdx
0x1800d0894  jnz     loc_1800D091A
0x1800d089a  mov     ebx, 80004003h
0x1800d089f  lea     rdx, aCasrfprogworki_10; "CaSrfProgWorkItemError_InitializeNullPt"...
0x1800d08a6  mov     r9d, ebx; unsigned int
0x1800d08a9  lea     rcx, aIidCalistasurf; "IID_CalistaSurfaceProgressiveWorkItem"
0x1800d08b0  mov     r8d, 97h; char *
0x1800d08b6  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x1800d08bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d08c2  lea     rax, WPP_GLOBAL_Control
0x1800d08c9  cmp     rcx, rax
0x1800d08cc  jz      loc_1800D0C94
0x1800d08d2  test    byte ptr [rcx+1Ch], 8
0x1800d08d6  jz      loc_1800D0C94
0x1800d08dc  cmp     byte ptr [rcx+19h], 2
0x1800d08e0  jb      loc_1800D0C94
0x1800d08e6  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800d08eb  lea     edx, [r14+12h]
0x1800d08ef  lea     rcx, aPunkcompressor; "pUnkCompressor"
0x1800d08f6  mov     [rsp+68h+var_48], rcx
0x1800d08fb  lea     r8, WPP_ddbde35ae9e63e27ac3a8a9cfef3756a_Traceguids
0x1800d0902  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d0909  mov     r9d, eax
0x1800d090c  mov     rcx, [rcx+10h]
0x1800d0910  call    WPP_SF_Ds
0x1800d0915  jmp     loc_1800D0C94
0x1800d091a  mov     rsi, [rsp+68h+arg_20]
0x1800d0922  test    rsi, rsi
0x1800d0925  jnz     short loc_1800D0987
0x1800d0927  mov     ebx, 80004003h
0x1800d092c  lea     rdx, aCasrfprogworki_10; "CaSrfProgWorkItemError_InitializeNullPt"...
0x1800d0933  mov     r9d, ebx; unsigned int
0x1800d0936  lea     rcx, aIidCalistasurf; "IID_CalistaSurfaceProgressiveWorkItem"
0x1800d093d  mov     r8d, 99h; char *
0x1800d0943  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x1800d0948  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d094f  lea     rax, WPP_GLOBAL_Control
0x1800d0956  cmp     rcx, rax
0x1800d0959  jz      loc_1800D0C94
0x1800d095f  test    byte ptr [rcx+1Ch], 8
0x1800d0963  jz      loc_1800D0C94
0x1800d0969  cmp     byte ptr [rcx+19h], 2
0x1800d096d  jb      loc_1800D0C94
0x1800d0973  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800d0978  lea     edx, [rsi+13h]
0x1800d097b  lea     rcx, aPsurface; "pSurface"
0x1800d0982  jmp     loc_1800D08F6
0x1800d0987  or      dword ptr [rcx+1Ch], 2
0x1800d098b  lea     r8, [rcx+98h]
0x1800d0992  call    ?CreateInstance@?$CTSObjectPool@VCEncodingNode@@@@SAJIIPEAPEAV1@H@Z; CTSObjectPool<CEncodingNode>::CreateInstance(uint,uint,CTSObjectPool<CEncodingNode> * *,int)
0x1800d0997  mov     ebx, eax
0x1800d0999  test    eax, eax
0x1800d099b  jns     short loc_1800D09FE
0x1800d099d  mov     r9d, eax; unsigned int
0x1800d09a0  lea     rdx, aCasrfprogworki_7; "CaSrfProgWorkItemError_InitializeCreate"...
0x1800d09a7  mov     r8d, 0A1h; char *
0x1800d09ad  lea     rcx, aIidCalistasurf; "IID_CalistaSurfaceProgressiveWorkItem"
0x1800d09b4  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x1800d09b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d09c0  lea     rax, WPP_GLOBAL_Control
0x1800d09c7  cmp     rcx, rax
0x1800d09ca  jz      loc_1800D0C94
0x1800d09d0  test    byte ptr [rcx+1Ch], 8
0x1800d09d4  jz      loc_1800D0C94
0x1800d09da  cmp     byte ptr [rcx+19h], 2
0x1800d09de  jb      loc_1800D0C94
0x1800d09e4  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800d09e9  mov     edx, 15h
0x1800d09ee  mov     dword ptr [rsp+68h+var_40], ebx
0x1800d09f2  lea     rcx, aFailedToCreate_69; "failed to create pool of encoding nodes"
0x1800d09f9  jmp     loc_1800D0C75
0x1800d09fe  lea     rcx, [rdi+78h]
0x1800d0a02  call    RgnlibBA_CreateInstance
0x1800d0a07  mov     ebx, eax
0x1800d0a09  test    eax, eax
0x1800d0a0b  jns     short loc_1800D0A6E
0x1800d0a0d  mov     r9d, eax; unsigned int
0x1800d0a10  lea     rdx, aCasrfprogworki_23; "CaSrfProgWorkItemError_InitializeCreate"...
0x1800d0a17  mov     r8d, 0A5h; char *
0x1800d0a1d  lea     rcx, aIidCalistasurf; "IID_CalistaSurfaceProgressiveWorkItem"
0x1800d0a24  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x1800d0a29  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d0a30  lea     rax, WPP_GLOBAL_Control
0x1800d0a37  cmp     rcx, rax
0x1800d0a3a  jz      loc_1800D0C94
0x1800d0a40  test    byte ptr [rcx+1Ch], 8
0x1800d0a44  jz      loc_1800D0C94
0x1800d0a4a  cmp     byte ptr [rcx+19h], 2
0x1800d0a4e  jb      loc_1800D0C94
0x1800d0a54  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800d0a59  mov     edx, 16h
0x1800d0a5e  mov     dword ptr [rsp+68h+var_40], ebx
0x1800d0a62  lea     rcx, aFailedToCreate_33; "failed to create workItem BA"
0x1800d0a69  jmp     loc_1800D0C75
0x1800d0a6e  lea     rcx, [rdi+80h]
0x1800d0a75  call    RgnlibBA_CreateInstance
0x1800d0a7a  mov     ebx, eax
0x1800d0a7c  test    eax, eax
0x1800d0a7e  jns     short loc_1800D0AD3
0x1800d0a80  mov     r9d, eax; unsigned int
0x1800d0a83  lea     rdx, aCasrfprogworki_23; "CaSrfProgWorkItemError_InitializeCreate"...
0x1800d0a8a  mov     r8d, 0A9h; char *
0x1800d0a90  lea     rcx, aIidCalistasurf; "IID_CalistaSurfaceProgressiveWorkItem"
0x1800d0a97  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x1800d0a9c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d0aa3  lea     rax, WPP_GLOBAL_Control
0x1800d0aaa  cmp     rcx, rax
0x1800d0aad  jz      loc_1800D0C94
0x1800d0ab3  test    byte ptr [rcx+1Ch], 8
0x1800d0ab7  jz      loc_1800D0C94
0x1800d0abd  cmp     byte ptr [rcx+19h], 2
0x1800d0ac1  jb      loc_1800D0C94
0x1800d0ac7  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800d0acc  mov     edx, 17h
0x1800d0ad1  jmp     short loc_1800D0A5E
0x1800d0ad3  cmp     qword ptr [rsi+178h], 0
0x1800d0adb  jnz     short loc_1800D0AE6
0x1800d0add  mov     eax, [rbp+0Ch]
0x1800d0ae0  mov     [rdi+0B8h], eax
0x1800d0ae6  movzx   eax, [rsp+68h+arg_28]
0x1800d0aee  lea     r8, [rdi+68h]
0x1800d0af2  mov     [rdi+90h], eax
0x1800d0af8  lea     rdx, IID_IRdpProgressiveCompressorEx
0x1800d0aff  mov     rax, [r14]
0x1800d0b02  mov     rcx, r14
0x1800d0b05  mov     rax, [rax]
0x1800d0b08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d0b0d  test    eax, eax
0x1800d0b0f  js      loc_1800D0C1C
0x1800d0b15  mov     rcx, [rdi+68h]
0x1800d0b19  lea     r9, [rdi+70h]
0x1800d0b1d  mov     r8d, [rdi+0B8h]
0x1800d0b24  mov     rdx, [rsi+270h]
0x1800d0b2b  mov     rax, [rcx]
0x1800d0b2e  mov     rax, [rax+18h]
0x1800d0b32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d0b37  mov     ebx, eax
0x1800d0b39  test    eax, eax
0x1800d0b3b  jns     short loc_1800D0B9E
0x1800d0b3d  mov     r9d, eax; unsigned int
0x1800d0b40  lea     rdx, aCasrfprogworki_22; "CaSrfProgWorkItemError_InitializeCreate"...
0x1800d0b47  mov     r8d, 0B6h; char *
0x1800d0b4d  lea     rcx, aIidCalistasurf; "IID_CalistaSurfaceProgressiveWorkItem"
0x1800d0b54  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x1800d0b59  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d0b60  lea     rax, WPP_GLOBAL_Control
0x1800d0b67  cmp     rcx, rax
0x1800d0b6a  jz      loc_1800D0C94
0x1800d0b70  test    byte ptr [rcx+1Ch], 8
0x1800d0b74  jz      loc_1800D0C94
0x1800d0b7a  cmp     byte ptr [rcx+19h], 2
0x1800d0b7e  jb      loc_1800D0C94
0x1800d0b84  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800d0b89  mov     edx, 18h
0x1800d0b8e  mov     dword ptr [rsp+68h+var_40], ebx
0x1800d0b92  lea     rcx, aCreateencoding_3; "CreateEncodingSurfaceContext failed."
0x1800d0b99  jmp     loc_1800D0C75
0x1800d0b9e  movzx   eax, word ptr [rsi+38h]
0x1800d0ba2  lea     rcx, [rdi+58h]
0x1800d0ba6  mov     rdx, [rsp+68h+arg_30]
0x1800d0bae  mov     [rdi+40h], ax
0x1800d0bb2  mov     [rdi+60h], r15b
0x1800d0bb6  call    ??4?$TCntPtr@VIRdpPipeEvents@@@@QEAAPEAVIRdpPipeEvents@@PEAV1@@Z; TCntPtr<IRdpPipeEvents>::operator=(IRdpPipeEvents *)
0x1800d0bbb  or      esi, 0FFFFFFFFh
0x1800d0bbe  lea     rax, [rdi+48h]
0x1800d0bc2  mov     [rsp+68h+var_40], rax
0x1800d0bc7  lea     rcx, aRdvRdpGraphics_3; "RDV::RDP::GraphicsPipeline::WorkItemCod"...
0x1800d0bce  mov     ebp, 4
0x1800d0bd3  mov     r9d, esi
0x1800d0bd6  mov     r8d, esi
0x1800d0bd9  mov     dword ptr [rsp+68h+var_48], ebp
0x1800d0bdd  mov     edx, esi
0x1800d0bdf  call    cs:__imp_RDPAPI_GetGenericCounter
0x1800d0be5  mov     ebx, eax
0x1800d0be7  test    eax, eax
0x1800d0be9  js      loc_1800D0C94
0x1800d0bef  lea     rax, [rdi+50h]
0x1800d0bf3  mov     r9d, esi
0x1800d0bf6  mov     [rsp+68h+var_40], rax
0x1800d0bfb  lea     rcx, aRdvRdpGraphics_41; "RDV::RDP::GraphicsPipeline::WorkItemCod"...
0x1800d0c02  mov     r8d, esi
0x1800d0c05  mov     dword ptr [rsp+68h+var_48], ebp
0x1800d0c09  mov     edx, esi
0x1800d0c0b  call    cs:__imp_RDPAPI_GetGenericCounter
0x1800d0c11  mov     ebx, eax
0x1800d0c13  xor     eax, eax
0x1800d0c15  test    ebx, ebx
0x1800d0c17  cmovns  ebx, eax
0x1800d0c1a  jmp     short loc_1800D0C94
0x1800d0c1c  mov     ebx, 80004005h
0x1800d0c21  lea     rdx, aCasrfprogworki_9; "CaSrfProgWorkItemError_InitializeInvali"...
0x1800d0c28  mov     r9d, ebx; unsigned int
0x1800d0c2b  lea     rcx, aIidCalistasurf; "IID_CalistaSurfaceProgressiveWorkItem"
0x1800d0c32  mov     r8d, 0BCh; char *
0x1800d0c38  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x1800d0c3d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d0c44  lea     rax, WPP_GLOBAL_Control
0x1800d0c4b  cmp     rcx, rax
0x1800d0c4e  jz      short loc_1800D0C94
0x1800d0c50  test    byte ptr [rcx+1Ch], 8
0x1800d0c54  jz      short loc_1800D0C94
0x1800d0c56  cmp     byte ptr [rcx+19h], 2
0x1800d0c5a  jb      short loc_1800D0C94
0x1800d0c5c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800d0c61  mov     edx, 19h
0x1800d0c66  mov     dword ptr [rsp+68h+var_40], 80004005h
0x1800d0c6e  lea     rcx, aInvalidProgres; "Invalid progressive compressor."
0x1800d0c75  mov     [rsp+68h+var_48], rcx
0x1800d0c7a  lea     r8, WPP_ddbde35ae9e63e27ac3a8a9cfef3756a_Traceguids
0x1800d0c81  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d0c88  mov     r9d, eax
0x1800d0c8b  mov     rcx, [rcx+10h]
0x1800d0c8f  call    WPP_SF_DsD
0x1800d0c94  mov     eax, ebx
0x1800d0c96  add     rsp, 38h
0x1800d0c9a  pop     r15
0x1800d0c9c  pop     r14
0x1800d0c9e  pop     rdi
0x1800d0c9f  pop     rsi
0x1800d0ca0  pop     rbp
0x1800d0ca1  pop     rbx
0x1800d0ca2  retn
```
