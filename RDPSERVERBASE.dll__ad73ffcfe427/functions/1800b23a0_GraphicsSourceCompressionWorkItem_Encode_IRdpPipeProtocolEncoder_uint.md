# GraphicsSourceCompressionWorkItem::Encode(IRdpPipeProtocolEncoder *,uint)

- ea: `0x1800b23a0`
- end: `0x1800b28cd`
- name: `?Encode@GraphicsSourceCompressionWorkItem@@UEAAJPEAVIRdpPipeProtocolEncoder@@I@Z`
- size: `1325`
- prototype: `int(GraphicsSourceCompressionWorkItem *__hidden this, struct IRdpPipeProtocolEncoder *, unsigned int)`
- caller_count: `0`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180022d10`
- `0x180076090`
- `0x180077aa0`
- `0x180079770`
- `0x18007a404`
- `0x1800b20dc`
- `0x1800b23a0`
- `0x1800b5774`
- `0x180158180`
- `0x18019c010`

## string_xrefs

- `0x1800b2422`: `pProtocolEncoder`
- `0x1800b23dc`: `GraphicsSourceCompressionWorkItemError_EncodeNullPointer`
- `0x1800b23e6`: `CODEC_GUID_GRAPHICSCOMPRESSION`
- `0x1800b2471`: `CODEC_GUID_GRAPHICSCOMPRESSION`
- `0x1800b2844`: `GraphicsSourceCompressionWorkItemError_EncodeSetupCompressionRectDataFail`
- `0x1800b287b`: `Failed to initialize compression region`
- `0x1800b2801`: `GraphicsSourceCompressionWorkItemError_EncodeCreateSurfaceCompressionContextFail`
- `0x1800b2838`: `Failed to initialize the compression region`
- `0x1800b2788`: `GraphicsSourceCompressionWorkItemError_EncodeStartWireToSurface1Fail`
- `0x1800b2745`: `GraphicsSourceCompressionWorkItemError_EncodeCompressSurfaceBitsFail`
- `0x1800b277c`: `GFX source compression failure`
- `0x1800b262e`: `GraphicsSourceCompressionWorkItemError_EncodeCommitWireToSurface1Fail`
- `0x1800b2671`: `CommitWireToSurface failed!`
- `0x1800b2694`: `GraphicsSourceCompressionWorkItemError_EncodeCancelWireToSurface1Fail`

## pseudocode

```c
__int64 __fastcall GraphicsSourceCompressionWorkItem::Encode(
        struct IRDPPerfCounterGeneric **this,
        struct IRdpPipeProtocolEncoder *a2,
        unsigned int a3)
{
  unsigned int v4; // edi
  unsigned int CurrentThreadActivityIdPrefix; // eax
  unsigned __int16 *v6; // rsi
  signed int v7; // eax
  struct IRDPPerfCounterGeneric *v8; // rax
  struct IRDPPerfCounterGeneric *v9; // rcx
  signed int v10; // eax
  unsigned int v11; // eax
  signed int v12; // eax
  signed int v13; // eax
  unsigned int v14; // eax
  struct IRDPPerfCounterGeneric *v15; // rcx
  unsigned int v16; // eax
  int v17; // edx
  const char *v18; // rcx
  unsigned int v19; // eax
  int v20; // edx
  const char *v21; // rcx
  int v23; // [rsp+20h] [rbp-58h]
  int v24[2]; // [rsp+40h] [rbp-38h] BYREF
  struct IRDPPerfCounterGeneric **v25; // [rsp+48h] [rbp-30h]
  int v26; // [rsp+50h] [rbp-28h] BYREF
  int v27; // [rsp+54h] [rbp-24h]
  int v28; // [rsp+58h] [rbp-20h]
  int v29; // [rsp+5Ch] [rbp-1Ch]
  unsigned int v32; // [rsp+D8h] [rbp+60h]

  *(_QWORD *)v24 = 0;
  if ( !a2 )
  {
    v4 = -2147467261;
    RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
      (RDPGraphicsTraceLogging *)"CODEC_GUID_GRAPHICSCOMPRESSION",
      "GraphicsSourceCompressionWorkItemError_EncodeNullPointer",
      (char *)0x2A6,
      0x80004003,
      v23);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Ds(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        52,
        (unsigned int)WPP_e87abb6865a7333453d6f9536d50f3e7_Traceguids,
        CurrentThreadActivityIdPrefix,
        (__int64)"pProtocolEncoder");
    }
    v6 = (unsigned __int16 *)(this + 3);
    goto LABEL_42;
  }
  v6 = (unsigned __int16 *)(this + 3);
  v4 = 0;
  PerfCounterSetRdpFrameAckMarker(this[151], a3, *((unsigned __int16 *)this + 12), 0);
LABEL_8:
  if ( (*(unsigned int (__fastcall **)(struct IRDPPerfCounterGeneric *))(*(_QWORD *)this[2] + 176LL))(this[2]) )
  {
    v7 = GraphicsSourceCompressionWorkItem::SetupCompressionRectData((GraphicsSourceCompressionWorkItem *)(this - 6));
    v4 = v7;
    if ( v7 < 0 )
    {
      RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
        (RDPGraphicsTraceLogging *)"CODEC_GUID_GRAPHICSCOMPRESSION",
        "GraphicsSourceCompressionWorkItemError_EncodeSetupCompressionRectDataFail",
        (char *)0x2B1,
        v7,
        v23);
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_42;
      }
      v19 = RdpWppGetCurrentThreadActivityIdPrefix();
      v20 = 53;
      v21 = "Failed to initialize compression region";
    }
    else
    {
      v8 = this[142];
      this[140] = 0;
      *((_DWORD *)this + 278) = 0;
      this[138] = 0;
      v9 = this[4];
      this[5] = v8;
      *((_DWORD *)this + 274) = 1;
      v10 = (*(__int64 (__fastcall **)(struct IRDPPerfCounterGeneric *))(*(_QWORD *)v9 + 96LL))(v9);
      v4 = v10;
      if ( v10 >= 0 )
      {
        while ( 1 )
        {
          v11 = *((_DWORD *)this + 282);
          if ( v11 >= *((_DWORD *)this + 12) )
          {
            (*(void (__fastcall **)(struct IRDPPerfCounterGeneric *, char *))(*(_QWORD *)this[4] + 104LL))(
              this[4],
              (char *)this + 40);
            goto LABEL_8;
          }
          v25 = &this[2 * v11 + 9];
          v26 = *(_DWORD *)v25;
          v27 = *((_DWORD *)v25 + 1);
          v28 = *((_DWORD *)v25 + 2);
          v29 = *((_DWORD *)v25 + 3);
          GraphicsSourceCompressionWorkItem::AlignRect(
            (GraphicsSourceCompressionWorkItem *)(this - 6),
            (struct RdpRect *)&v26,
            0);
          v32 = (v29 - v27) * ((int)((32 * (v28 - v26) + 63) & 0xFFFFFFC0) / 8);
          v12 = (*(__int64 (__fastcall **)(struct IRdpPipeProtocolEncoder *, _QWORD, _QWORD, int *))(*(_QWORD *)a2 + 40LL))(
                  a2,
                  *((unsigned __int16 *)this[148] + 28),
                  v32 + 0x2000,
                  v24);
          v4 = v12;
          if ( v12 < 0 )
            break;
          v23 = v24[0];
          v13 = (*(__int64 (__fastcall **)(struct IRDPPerfCounterGeneric *, char *, _QWORD, _QWORD))(*(_QWORD *)this[4] + 112LL))(
                  this[4],
                  (char *)this + 40,
                  *((unsigned int *)this + 282),
                  v32 + 0x2000);
          v4 = v13;
          if ( v13 < 0 )
          {
            RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
              (RDPGraphicsTraceLogging *)"CODEC_GUID_GRAPHICSCOMPRESSION",
              "GraphicsSourceCompressionWorkItemError_EncodeCompressSurfaceBitsFail",
              (char *)0x2E3,
              v13,
              v23);
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v16 = RdpWppGetCurrentThreadActivityIdPrefix();
              v17 = 56;
              v18 = "GFX source compression failure";
LABEL_31:
              WPP_SF_DsD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                v17,
                (unsigned int)WPP_e87abb6865a7333453d6f9536d50f3e7_Traceguids,
                v16,
                (__int64)v18,
                v4);
              goto LABEL_32;
            }
            goto LABEL_32;
          }
          if ( (*(int (__fastcall **)(struct IRdpPipeProtocolEncoder *))(*(_QWORD *)a2 + 72LL))(a2) < 0 )
          {
            RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
              (RDPGraphicsTraceLogging *)"CODEC_GUID_GRAPHICSCOMPRESSION",
              "GraphicsSourceCompressionWorkItemError_EncodeCancelWireToSurface1Fail",
              (char *)0x2F7,
              0,
              v23);
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
            {
              v14 = RdpWppGetCurrentThreadActivityIdPrefix();
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, WPP_e87abb6865a7333453d6f9536d50f3e7_Traceguids, v14);
            }
          }
          (*(void (__fastcall **)(struct IRDPPerfCounterGeneric *, struct IRDPPerfCounterGeneric **))(*(_QWORD *)this[2] + 80LL))(
            this[2],
            v25);
          v15 = this[149];
          if ( v15 )
            (*(void (__fastcall **)(struct IRDPPerfCounterGeneric *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v15 + 264LL))(
              v15,
              *v6,
              v32,
              0);
          ++*((_DWORD *)this + 282);
        }
        RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
          (RDPGraphicsTraceLogging *)"CODEC_GUID_GRAPHICSCOMPRESSION",
          "GraphicsSourceCompressionWorkItemError_EncodeStartWireToSurface1Fail",
          (char *)0x2DA,
          v12,
          v23);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v16 = RdpWppGetCurrentThreadActivityIdPrefix();
          v17 = 55;
          v18 = "StartWireToSurface1 failed!";
          goto LABEL_31;
        }
LABEL_32:
        (*(void (__fastcall **)(struct IRDPPerfCounterGeneric *, char *))(*(_QWORD *)this[4] + 104LL))(
          this[4],
          (char *)this + 40);
        goto LABEL_42;
      }
      RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
        (RDPGraphicsTraceLogging *)"CODEC_GUID_GRAPHICSCOMPRESSION",
        "GraphicsSourceCompressionWorkItemError_EncodeCreateSurfaceCompressionContextFail",
        (char *)0x2C0,
        v10,
        v23);
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_42;
      }
      v19 = RdpWppGetCurrentThreadActivityIdPrefix();
      v20 = 54;
      v21 = "Failed to initialize the compression region";
    }
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v20,
      (unsigned int)WPP_e87abb6865a7333453d6f9536d50f3e7_Traceguids,
      v19,
      (__int64)v21,
      v4);
  }
LABEL_42:
  PerfCounterSetRdpFrameAckMarker(this[152], a3, *v6, 1u);
  return v4;
}

```

## disassembly

```asm
0x1800b23a0  mov     [rsp-40h+arg_10], r8d
0x1800b23a5  mov     [rsp-40h+arg_8], rdx
0x1800b23aa  push    rbp
0x1800b23ab  push    rbx
0x1800b23ac  push    rsi
0x1800b23ad  push    rdi
0x1800b23ae  push    r12
0x1800b23b0  push    r13
0x1800b23b2  push    r14
0x1800b23b4  push    r15
0x1800b23b6  mov     rbp, rsp
0x1800b23b9  sub     rsp, 78h
0x1800b23bd  mov     qword ptr [rbp+var_38], 0
0x1800b23c5  mov     r10d, r8d
0x1800b23c8  mov     [rbp+arg_0], 0
0x1800b23cf  mov     rbx, rcx
0x1800b23d2  test    rdx, rdx
0x1800b23d5  jnz     short loc_1800B2455
0x1800b23d7  mov     edi, 80004003h
0x1800b23dc  lea     rdx, aGraphicssource_6; "GraphicsSourceCompressionWorkItemError_"...
0x1800b23e3  mov     r9d, edi; unsigned int
0x1800b23e6  lea     rcx, aCodecGuidGraph; "CODEC_GUID_GRAPHICSCOMPRESSION"
0x1800b23ed  mov     r8d, 2A6h; char *
0x1800b23f3  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x1800b23f8  mov     rax, cs:WPP_GLOBAL_Control
0x1800b23ff  lea     r12, WPP_GLOBAL_Control
0x1800b2406  cmp     rax, r12
0x1800b2409  jz      short loc_1800B244C
0x1800b240b  mov     r14d, 8
0x1800b2411  test    [rax+1Ch], r14b
0x1800b2415  jz      short loc_1800B244C
0x1800b2417  cmp     byte ptr [rax+19h], 2
0x1800b241b  jb      short loc_1800B244C
0x1800b241d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800b2422  lea     rcx, aPprotocolencod; "pProtocolEncoder"
0x1800b2429  mov     r9d, eax
0x1800b242c  mov     qword ptr [rsp+78h+var_58], rcx
0x1800b2431  lea     edx, [r14+2Ch]
0x1800b2435  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b243c  lea     r8, WPP_e87abb6865a7333453d6f9536d50f3e7_Traceguids
0x1800b2443  mov     rcx, [rcx+10h]
0x1800b2447  call    WPP_SF_Ds
0x1800b244c  lea     rsi, [rbx+18h]
0x1800b2450  jmp     loc_1800B28A1
0x1800b2455  lea     rsi, [rcx+18h]
0x1800b2459  xor     edi, edi
0x1800b245b  movzx   r8d, word ptr [rsi]; unsigned int
0x1800b245f  xor     r9d, r9d; unsigned int
0x1800b2462  mov     rcx, [rcx+4B8h]; struct IRDPPerfCounterGeneric *
0x1800b2469  mov     edx, r10d; unsigned int
0x1800b246c  call    ?PerfCounterSetRdpFrameAckMarker@@YAJPEAUIRDPPerfCounterGeneric@@III@Z; PerfCounterSetRdpFrameAckMarker(IRDPPerfCounterGeneric *,uint,uint,uint)
0x1800b2471  lea     r15, aCodecGuidGraph; "CODEC_GUID_GRAPHICSCOMPRESSION"
0x1800b2478  lea     r12, WPP_GLOBAL_Control
0x1800b247f  lea     r14d, [rdi+8]
0x1800b2483  lea     r13, WPP_e87abb6865a7333453d6f9536d50f3e7_Traceguids
0x1800b248a  mov     rcx, [rbx+10h]
0x1800b248e  mov     rax, [rcx]
0x1800b2491  mov     rax, [rax+0B0h]
0x1800b2498  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b249d  test    eax, eax
0x1800b249f  jz      loc_1800B28A1
0x1800b24a5  lea     rcx, [rbx-30h]; this
0x1800b24a9  call    ?SetupCompressionRectData@GraphicsSourceCompressionWorkItem@@AEAAJXZ; GraphicsSourceCompressionWorkItem::SetupCompressionRectData(void)
0x1800b24ae  xor     ecx, ecx
0x1800b24b0  mov     edi, eax
0x1800b24b2  test    eax, eax
0x1800b24b4  js      loc_1800B2841
0x1800b24ba  mov     rax, [rbx+470h]
0x1800b24c1  lea     rdx, [rbx+28h]
0x1800b24c5  mov     [rbx+460h], rcx
0x1800b24cc  mov     [rbx+458h], ecx
0x1800b24d2  mov     [rbx+450h], rcx
0x1800b24d9  mov     rcx, [rbx+20h]
0x1800b24dd  mov     [rdx], rax
0x1800b24e0  mov     dword ptr [rbx+448h], 1
0x1800b24ea  mov     rax, [rcx]
0x1800b24ed  mov     rax, [rax+60h]
0x1800b24f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b24f6  mov     edi, eax
0x1800b24f8  test    eax, eax
0x1800b24fa  js      loc_1800B27FE
0x1800b2500  mov     eax, [rbx+468h]
0x1800b2506  cmp     eax, [rbx+30h]
0x1800b2509  jnb     loc_1800B2729
0x1800b250f  mov     ecx, eax
0x1800b2511  lea     rdx, [rbp+var_28]; struct RdpRect *
0x1800b2515  shl     rcx, 4
0x1800b2519  xor     r8d, r8d; int
0x1800b251c  add     rcx, 48h ; 'H'
0x1800b2520  add     rcx, rbx
0x1800b2523  mov     [rbp+var_30], rcx
0x1800b2527  mov     eax, [rcx]
0x1800b2529  mov     [rbp+var_28], eax
0x1800b252c  mov     eax, [rcx+4]
0x1800b252f  mov     [rbp+var_24], eax
0x1800b2532  mov     eax, [rcx+8]
0x1800b2535  mov     [rbp+var_20], eax
0x1800b2538  mov     eax, [rcx+0Ch]
0x1800b253b  lea     rcx, [rbx-30h]; this
0x1800b253f  mov     [rbp+var_1C], eax
0x1800b2542  call    ?AlignRect@GraphicsSourceCompressionWorkItem@@AEAAXPEAURdpRect@@H@Z; GraphicsSourceCompressionWorkItem::AlignRect(RdpRect *,int)
0x1800b2547  mov     eax, [rbp+var_20]
0x1800b254a  lea     r9, [rbp+var_38]
0x1800b254e  sub     eax, [rbp+var_28]
0x1800b2551  shl     eax, 5
0x1800b2554  add     eax, 3Fh ; '?'
0x1800b2557  and     eax, 0FFFFFFC0h
0x1800b255a  cdq
0x1800b255b  idiv    r14d
0x1800b255e  mov     rdx, [rbx+4A0h]
0x1800b2565  mov     ecx, eax
0x1800b2567  mov     eax, [rbp+var_1C]
0x1800b256a  sub     eax, [rbp+var_24]
0x1800b256d  imul    ecx, eax
0x1800b2570  movzx   edx, word ptr [rdx+38h]
0x1800b2574  mov     [rbp+arg_18], ecx
0x1800b2577  lea     r8d, [rcx+2000h]
0x1800b257e  mov     rcx, [rbp+arg_8]
0x1800b2582  mov     rax, [rcx]
0x1800b2585  mov     rax, [rax+28h]
0x1800b2589  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b258e  mov     edi, eax
0x1800b2590  test    eax, eax
0x1800b2592  js      loc_1800B2785
0x1800b2598  mov     rdx, qword ptr [rbp+var_38]
0x1800b259c  lea     r8, [rbp+arg_0]
0x1800b25a0  mov     rcx, [rbx+20h]
0x1800b25a4  mov     r9d, [rbp+arg_18]
0x1800b25a8  mov     [rsp+78h+var_50], r8
0x1800b25ad  add     r9d, 2000h
0x1800b25b4  mov     r8d, [rbx+468h]
0x1800b25bb  mov     rax, [rcx]
0x1800b25be  mov     qword ptr [rsp+78h+var_58], rdx; int
0x1800b25c3  lea     rdx, [rbx+28h]
0x1800b25c7  mov     rax, [rax+70h]
0x1800b25cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b25d0  mov     edi, eax
0x1800b25d2  test    eax, eax
0x1800b25d4  js      loc_1800B2742
0x1800b25da  mov     edx, [rbp+arg_0]
0x1800b25dd  test    edx, edx
0x1800b25df  jz      loc_1800B267D
0x1800b25e5  mov     rcx, [rbp+var_30]
0x1800b25e9  lea     r9, [rbp+var_18]
0x1800b25ed  movzx   r8d, word ptr [rsi]
0x1800b25f1  mov     [rsp+78h+var_58], edx; int
0x1800b25f5  mov     edx, 20h ; ' '
0x1800b25fa  mov     eax, [rcx]
0x1800b25fc  mov     [rbp+var_18], eax
0x1800b25ff  mov     eax, [rcx+4]
0x1800b2602  mov     [rbp+var_14], eax
0x1800b2605  mov     eax, [rcx+8]
0x1800b2608  mov     [rbp+var_10], eax
0x1800b260b  mov     eax, [rcx+0Ch]
0x1800b260e  mov     rcx, [rbp+arg_8]
0x1800b2612  mov     [rbp+var_C], eax
0x1800b2615  mov     rax, [rcx]
0x1800b2618  mov     rax, [rax+30h]
0x1800b261c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b2621  mov     edi, eax
0x1800b2623  test    eax, eax
0x1800b2625  jns     loc_1800B26E4
0x1800b262b  mov     r9d, eax; unsigned int
0x1800b262e  lea     rdx, aGraphicssource; "GraphicsSourceCompressionWorkItemError_"...
0x1800b2635  mov     r8d, 2F0h; char *
0x1800b263b  mov     rcx, r15; this
0x1800b263e  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x1800b2643  mov     rax, cs:WPP_GLOBAL_Control
0x1800b264a  cmp     rax, r12
0x1800b264d  jz      loc_1800B27E5
0x1800b2653  test    [rax+1Ch], r14b
0x1800b2657  jz      loc_1800B27E5
0x1800b265d  cmp     byte ptr [rax+19h], 2
0x1800b2661  jb      loc_1800B27E5
0x1800b2667  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800b266c  mov     edx, 39h ; '9'
0x1800b2671  lea     rcx, aCommitwiretosu_0; "CommitWireToSurface failed!"
0x1800b2678  jmp     loc_1800B27C6
0x1800b267d  mov     rcx, [rbp+arg_8]
0x1800b2681  mov     rax, [rcx]
0x1800b2684  mov     rax, [rax+48h]
0x1800b2688  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b268d  test    eax, eax
0x1800b268f  jns     short loc_1800B26E4
0x1800b2691  xor     r9d, r9d; unsigned int
0x1800b2694  lea     rdx, aGraphicssource_3; "GraphicsSourceCompressionWorkItemError_"...
0x1800b269b  mov     r8d, 2F7h; char *
0x1800b26a1  mov     rcx, r15; this
0x1800b26a4  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x1800b26a9  mov     rax, cs:WPP_GLOBAL_Control
0x1800b26b0  cmp     rax, r12
0x1800b26b3  jz      short loc_1800B26E4
0x1800b26b5  test    dword ptr [rax+1Ch], 100h
0x1800b26bc  jz      short loc_1800B26E4
0x1800b26be  cmp     byte ptr [rax+19h], 3
0x1800b26c2  jb      short loc_1800B26E4
0x1800b26c4  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800b26c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b26d0  mov     edx, 3Ah ; ':'
0x1800b26d5  mov     r9d, eax
0x1800b26d8  mov     r8, r13
0x1800b26db  mov     rcx, [rcx+10h]
0x1800b26df  call    WPP_SF_d
0x1800b26e4  mov     rcx, [rbx+10h]
0x1800b26e8  mov     rdx, [rbp+var_30]
0x1800b26ec  mov     rax, [rcx]
0x1800b26ef  mov     rax, [rax+50h]
0x1800b26f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b26f8  mov     rcx, [rbx+4A8h]
0x1800b26ff  test    rcx, rcx
0x1800b2702  jz      short loc_1800B271E
0x1800b2704  mov     rax, [rcx]
0x1800b2707  movzx   edx, word ptr [rsi]
0x1800b270a  mov     r9d, [rbp+arg_0]
0x1800b270e  mov     r8d, [rbp+arg_18]
0x1800b2712  mov     rax, [rax+108h]
0x1800b2719  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b271e  inc     dword ptr [rbx+468h]
0x1800b2724  jmp     loc_1800B2500
0x1800b2729  mov     rcx, [rbx+20h]
0x1800b272d  lea     rdx, [rbx+28h]
0x1800b2731  mov     rax, [rcx]
0x1800b2734  mov     rax, [rax+68h]
0x1800b2738  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b273d  jmp     loc_1800B248A
0x1800b2742  mov     r9d, edi; unsigned int
0x1800b2745  lea     rdx, aGraphicssource_1; "GraphicsSourceCompressionWorkItemError_"...
0x1800b274c  mov     r8d, 2E3h; char *
0x1800b2752  mov     rcx, r15; this
0x1800b2755  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x1800b275a  mov     rax, cs:WPP_GLOBAL_Control
0x1800b2761  cmp     rax, r12
0x1800b2764  jz      short loc_1800B27E5
0x1800b2766  test    [rax+1Ch], r14b
0x1800b276a  jz      short loc_1800B27E5
0x1800b276c  cmp     byte ptr [rax+19h], 2
0x1800b2770  jb      short loc_1800B27E5
0x1800b2772  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800b2777  mov     edx, 38h ; '8'
0x1800b277c  lea     rcx, aGfxSourceCompr; "GFX source compression failure"
0x1800b2783  jmp     short loc_1800B27C6
0x1800b2785  mov     r9d, edi; unsigned int
0x1800b2788  lea     rdx, aGraphicssource_4; "GraphicsSourceCompressionWorkItemError_"...
0x1800b278f  mov     r8d, 2DAh; char *
0x1800b2795  mov     rcx, r15; this
0x1800b2798  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x1800b279d  mov     rax, cs:WPP_GLOBAL_Control
0x1800b27a4  cmp     rax, r12
0x1800b27a7  jz      short loc_1800B27E5
0x1800b27a9  test    [rax+1Ch], r14b
0x1800b27ad  jz      short loc_1800B27E5
0x1800b27af  cmp     byte ptr [rax+19h], 2
0x1800b27b3  jb      short loc_1800B27E5
0x1800b27b5  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800b27ba  mov     edx, 37h ; '7'
0x1800b27bf  lea     rcx, aStartwiretosur; "StartWireToSurface1 failed!"
0x1800b27c6  mov     dword ptr [rsp+78h+var_50], edi
0x1800b27ca  mov     r9d, eax
0x1800b27cd  mov     qword ptr [rsp+78h+var_58], rcx
0x1800b27d2  mov     r8, r13
0x1800b27d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b27dc  mov     rcx, [rcx+10h]
0x1800b27e0  call    WPP_SF_DsD
0x1800b27e5  mov     rcx, [rbx+20h]
0x1800b27e9  lea     rdx, [rbx+28h]
0x1800b27ed  mov     rax, [rcx]
0x1800b27f0  mov     rax, [rax+68h]
0x1800b27f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b27f9  jmp     loc_1800B28A1
0x1800b27fe  mov     r9d, edi; unsigned int
0x1800b2801  lea     rdx, aGraphicssource_0; "GraphicsSourceCompressionWorkItemError_"...
0x1800b2808  mov     r8d, 2C0h; char *
0x1800b280e  mov     rcx, r15; this
0x1800b2811  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x1800b2816  mov     rax, cs:WPP_GLOBAL_Control
0x1800b281d  cmp     rax, r12
0x1800b2820  jz      short loc_1800B28A1
0x1800b2822  test    [rax+1Ch], r14b
0x1800b2826  jz      short loc_1800B28A1
0x1800b2828  cmp     byte ptr [rax+19h], 2
0x1800b282c  jb      short loc_1800B28A1
0x1800b282e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800b2833  mov     edx, 36h ; '6'
0x1800b2838  lea     rcx, aFailedToInitia_31; "Failed to initialize the compression re"...
0x1800b283f  jmp     short loc_1800B2882
0x1800b2841  mov     r9d, edi; unsigned int
0x1800b2844  lea     rdx, aGraphicssource_2; "GraphicsSourceCompressionWorkItemError_"...
0x1800b284b  mov     r8d, 2B1h; char *
0x1800b2851  mov     rcx, r15; this
0x1800b2854  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x1800b2859  mov     rax, cs:WPP_GLOBAL_Control
0x1800b2860  cmp     rax, r12
0x1800b2863  jz      short loc_1800B28A1
0x1800b2865  test    [rax+1Ch], r14b
0x1800b2869  jz      short loc_1800B28A1
0x1800b286b  cmp     byte ptr [rax+19h], 2
0x1800b286f  jb      short loc_1800B28A1
0x1800b2871  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800b2876  mov     edx, 35h ; '5'
0x1800b287b  lea     rcx, aFailedToInitia_41; "Failed to initialize compression region"
  ... truncated ...
```
