# CPort::OnIncomingP2PActionFrameReceived(ulong,uchar *)

- ea: `0x1400868e8`
- end: `0x1400870e9`
- name: `?OnIncomingP2PActionFrameReceived@CPort@@QEAAXKPEAE@Z`
- size: `2049`
- prototype: `void __fastcall(CPort *this, unsigned int, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `24`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140026010`

## callees

- `0x140009420`
- `0x14000c778`
- `0x14000c940`
- `0x14000d054`
- `0x14000e3f0`
- `0x140015740`
- `0x14001d1d8`
- `0x14001e2c0`
- `0x14001eed0`
- `0x1400205a4`
- `0x14002a9f8`
- `0x14002c0b4`
- `0x14003895c`
- `0x1400414ac`
- `0x140050660`
- `0x140076138`
- `0x1400868e8`
- `0x14008cad8`
- `0x140097e70`
- `0x1400db13c`
- `0x1400dbac0`
- `0x1400dfd00`
- `0x1400dfd40`
- `0x1400dfe00`

## pseudocode

```c
void __fastcall CPort::OnIncomingP2PActionFrameReceived(CPort *this, unsigned int a2, unsigned __int8 *a3)
{
  bool v3; // bl
  int v7; // edx
  int v8; // r8d
  int v9; // r13d
  unsigned int v10; // edx
  unsigned int v11; // eax
  int v12; // edx
  int v13; // r15d
  _BYTE *v14; // rax
  int v15; // r8d
  _DWORD *v16; // rdi
  __int16 v17; // ax
  void *v18; // rcx
  size_t v19; // rax
  __int16 v20; // ax
  __int16 v21; // ax
  unsigned int v22; // eax
  __int16 v23; // ax
  __int16 v24; // ax
  __int16 v25; // ax
  unsigned int v26; // eax
  CPropertyCache *v27; // rax
  int v28; // edx
  int v29; // r8d
  __int64 v30; // r12
  CBSSEntry *BSSEntryByGroupID; // r14
  CBSSEntry *v32; // rax
  CBSSEntry *v33; // rax
  __int64 v34; // r8
  __int64 v35; // r9
  CBSSEntry *v36; // rbx
  __int64 v37; // rcx
  struct CAdapterPropertyCache *v38; // rax
  __int64 v39; // rax
  unsigned int v40; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v41; // [rsp+54h] [rbp-ACh]
  int v42; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v43; // [rsp+64h] [rbp-9Ch]
  size_t Size; // [rsp+6Ch] [rbp-94h]
  void *Src; // [rsp+78h] [rbp-88h]
  char v46; // [rsp+80h] [rbp-80h]
  int v47; // [rsp+88h] [rbp-78h]
  __int64 v48; // [rsp+90h] [rbp-70h]
  char v49; // [rsp+98h] [rbp-68h]
  int v50; // [rsp+A0h] [rbp-60h] BYREF
  char v51; // [rsp+A4h] [rbp-5Ch]
  _OWORD v52[3]; // [rsp+A8h] [rbp-58h] BYREF
  _QWORD v53[5]; // [rsp+D8h] [rbp-28h] BYREF
  CBSSEntry *v54; // [rsp+100h] [rbp+0h] BYREF

  v42 &= ~1u;
  v3 = 0;
  v43 = 0;
  Size = 0;
  v50 = 0;
  v51 = 0;
  *(_QWORD *)&v52[0] = 0;
  Src = 0;
  strcpy((char *)v52 + 12, "DIRECT-");
  v46 = 0;
  v47 = 0;
  v48 = 0;
  v49 = 0;
  DWORD2(v52[0]) = 7;
  memset((char *)&v52[1] + 4, 0, 24);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      5,
      1,
      287,
      (__int64)WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids);
  }
  v9 = ParseWdiIndicationP2pActionFrameReceivedFromIhv(a2 - 48, a3 + 48, *((_QWORD *)this + 17) + 5384LL, &v42);
  if ( !v9 )
  {
    LODWORD(v52[0]) = HIDWORD(v43);
    LODWORD(v54) = HIDWORD(v43);
    WORD2(v52[0]) = Size;
    WORD2(v54) = Size;
    v11 = 28;
    v12 = 32;
    if ( (_DWORD)v43 == 1 )
    {
      v13 = 1073938453;
    }
    else
    {
      if ( (_DWORD)v43 != 2 )
      {
        switch ( (_DWORD)v43 )
        {
          case 3:
            v11 = 20;
            v13 = 1073938457;
            goto LABEL_26;
          case 4:
            v13 = 1073938459;
            break;
          case 5:
            v13 = 1073938461;
            goto LABEL_26;
          case 6:
            v13 = 1073938463;
            break;
          case 7:
            v13 = 1073938465;
LABEL_26:
            v10 = HIDWORD(Size) + v11;
            v41 = HIDWORD(Size) + v11;
            if ( HIDWORD(Size) + v11 < v11 )
            {
              if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              {
                LOBYTE(v10) = 2;
                WPP_RECORDER_SF_qDddd(
                  WPP_GLOBAL_Control->DeviceExtension,
                  v10,
                  40,
                  290,
                  (__int64)WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids,
                  (char)this,
                  *((_WORD *)this + 74),
                  SBYTE4(Size),
                  -1,
                  1);
              }
              LOBYTE(v9) = 1;
              goto LABEL_72;
            }
            v14 = operator new(v10);
            v16 = v14;
            if ( !v14 )
            {
              if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              {
                LOBYTE(v10) = 2;
                WPP_RECORDER_SF_qD(
                  WPP_GLOBAL_Control->DeviceExtension,
                  v10,
                  v15,
                  291,
                  (__int64)WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids,
                  (char)this,
                  *((_WORD *)this + 74));
              }
              LOBYTE(v9) = -102;
              goto LABEL_72;
            }
            switch ( (_DWORD)v43 )
            {
              case 1:
                *(_DWORD *)v14 = 2097536;
                v14[10] = BYTE2(Size);
                *((_DWORD *)v14 + 1) = HIDWORD(v43);
                v25 = Size;
                v16[6] = 32;
                *((_WORD *)v16 + 4) = v25;
                v26 = HIDWORD(Size);
                v16[7] = HIDWORD(Size);
                memmove(v16 + 8, Src, v26);
                v3 = (int)GetSimpleAttribute((unsigned __int8 *)Src, HIDWORD(Size), 6u, &v50, 5u) >= 0;
                goto LABEL_54;
              case 2:
                *(_DWORD *)v14 = 2097536;
                v14[10] = BYTE2(Size);
                *((_DWORD *)v14 + 1) = HIDWORD(v43);
                v24 = Size;
                v16[6] = 32;
                v18 = v16 + 8;
                *((_WORD *)v16 + 4) = v24;
                v19 = HIDWORD(Size);
                v16[7] = HIDWORD(Size);
                goto LABEL_52;
              case 3:
                *(_DWORD *)v14 = 1311104;
                v14[10] = BYTE2(Size);
                *((_DWORD *)v14 + 1) = HIDWORD(v43);
                v23 = Size;
                v16[3] = 20;
                v18 = v16 + 5;
                *((_WORD *)v16 + 4) = v23;
                v19 = HIDWORD(Size);
                v16[4] = HIDWORD(Size);
                goto LABEL_52;
              case 4:
                *(_DWORD *)v14 = 2621824;
                v40 = 0;
                memset(&v53[2], 0, 22);
                v14[16] = BYTE2(Size);
                *((_DWORD *)v14 + 1) = HIDWORD(v43);
                v21 = Size;
                v16[8] = 40;
                *((_WORD *)v16 + 4) = v21;
                v22 = HIDWORD(Size);
                v16[9] = HIDWORD(Size);
                *(_OWORD *)v53 = 0;
                memmove(v16 + 10, Src, v22);
                if ( (int)GetSimpleAttribute((unsigned __int8 *)Src, HIDWORD(Size), 0x11u, &v50, 5u) >= 0
                  && (int)WFDGetGroupID(Src, HIDWORD(Size), &v40, v53) >= 0
                  && (int)WFDConvertGroupIDFromOTAtoDot11(v53, v40, v52) >= 0
                  && (int)GetSimpleAttribute((unsigned __int8 *)Src, HIDWORD(Size), 7u, &v54, 6u) >= 0 )
                {
                  v3 = 1;
                }
LABEL_54:
                v27 = (CPropertyCache *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(*((_QWORD *)this + 17) + 8LL)
                                                                           + 8LL))(*((_QWORD *)this + 17) + 8LL);
                if ( CPropertyCache::SetPropertyBuffer(v27, 0x32u, a2, a3)
                  && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                {
                  LOBYTE(v28) = 2;
                  WPP_RECORDER_SF_qD(
                    WPP_GLOBAL_Control->DeviceExtension,
                    v28,
                    v29,
                    293,
                    (__int64)WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids,
                    (char)this,
                    *((_WORD *)this + 74));
                }
                if ( !v3 )
                  goto LABEL_70;
                v30 = *((_QWORD *)this + 17);
                BSSEntryByGroupID = CBSSListManager::FindBSSEntryByGroupID(
                                      (CBSSListManager *)(v30 + 1736),
                                      (const struct _DOT11_WFD_GROUP_ID *)v52,
                                      1,
                                      1,
                                      1);
                if ( BSSEntryByGroupID )
                  goto LABEL_66;
                v32 = (CBSSEntry *)operator new(0x3C0u);
                if ( v32 )
                {
                  v33 = CBSSEntry::CBSSEntry(v32, (const unsigned __int8 (*)[6])&v54, 0);
                  v54 = v33;
                  v36 = v33;
                  if ( !v33 )
                    goto LABEL_65;
                  LOBYTE(v35) = 1;
                  *(_OWORD *)((char *)v33 + 824) = v52[0];
                  *(_OWORD *)((char *)v33 + 840) = v52[1];
                  *(_OWORD *)((char *)v33 + 852) = *(_OWORD *)((char *)&v52[1] + 12);
                  if ( (*(unsigned int (__fastcall **)(__int64, CBSSEntry *, __int64, __int64))(*(_QWORD *)(v30 + 1736)
                                                                                              + 8LL))(
                         v30 + 1736,
                         v33,
                         v34,
                         v35) )
                  {
                    wistd::unique_ptr<CBSSEntry,wistd::default_delete<CBSSEntry>>::reset(&v54);
                    v36 = v54;
                  }
                  BSSEntryByGroupID = v36;
                }
                v54 = 0;
LABEL_65:
                wistd::unique_ptr<CBSSEntry,wistd::default_delete<CBSSEntry>>::reset(&v54);
                if ( !BSSEntryByGroupID )
                {
LABEL_70:
                  CAdapter::IndicateStatus(*((CAdapter **)this + 17), *((_DWORD *)this + 36), v13, 0, v16, v41);
LABEL_71:
                  operator delete(v16);
                  goto LABEL_72;
                }
LABEL_66:
                v37 = *((_QWORD *)this + 17) + 8LL;
                LODWORD(v54) = 0;
                v40 = 0;
                v38 = (struct CAdapterPropertyCache *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v37 + 8LL))(v37);
                if ( !(unsigned int)ConvertP2PChannelToBandChannel(
                                      v38,
                                      (struct _WFD_OTA_CHANNEL *)&v50,
                                      (enum _WDI_BAND_ID *)&v40,
                                      (unsigned int *)&v54) )
                {
                  v39 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(*((_QWORD *)this + 17) + 8LL) + 8LL))(*((_QWORD *)this + 17) + 8LL);
                  CBSSEntry::SetChannelAndPhyID(BSSEntryByGroupID, 0, v39, (unsigned int)v54, v40);
                }
                if ( *(_BYTE *)(v30 + 1796) )
                  CBSSEntry::UpdateBackgroundDeviceIndicatedByDriver(
                    BSSEntryByGroupID,
                    *((struct CAdapter **)this + 17));
                goto LABEL_70;
            }
            if ( (_DWORD)v43 != 5 )
            {
              if ( (_DWORD)v43 == 6 )
              {
                *(_DWORD *)v14 = 2621824;
                v14[16] = BYTE2(Size);
                *((_DWORD *)v14 + 1) = HIDWORD(v43);
                v20 = Size;
                v16[8] = 40;
                v18 = v16 + 10;
                *((_WORD *)v16 + 4) = v20;
                v19 = HIDWORD(Size);
                v16[9] = HIDWORD(Size);
                goto LABEL_52;
              }
              if ( (_DWORD)v43 != 7 )
              {
                if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                {
                  LOBYTE(v10) = 2;
                  WPP_RECORDER_SF_qD(
                    WPP_GLOBAL_Control->DeviceExtension,
                    v10,
                    v15,
                    292,
                    (__int64)WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids,
                    (char)this,
                    *((_WORD *)this + 74));
                }
                goto LABEL_71;
              }
            }
            *(_DWORD *)v14 = 1835392;
            v14[16] = BYTE2(Size);
            *((_DWORD *)v14 + 1) = HIDWORD(v43);
            v17 = Size;
            v16[5] = 28;
            v18 = v16 + 7;
            *((_WORD *)v16 + 4) = v17;
            v19 = HIDWORD(Size);
            v16[6] = HIDWORD(Size);
LABEL_52:
            memmove(v18, Src, v19);
            goto LABEL_54;
          default:
            if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              goto LABEL_76;
            LOBYTE(v12) = 2;
            WPP_RECORDER_SF_qD(
              WPP_GLOBAL_Control->DeviceExtension,
              v12,
              40,
              289,
              (__int64)WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids,
              (char)this,
              *((_WORD *)this + 74));
            goto LABEL_72;
        }
        v11 = 40;
        goto LABEL_26;
      }
      v13 = 1073938455;
    }
    v11 = 32;
    goto LABEL_26;
  }
  if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    goto LABEL_76;
  LOBYTE(v7) = 2;
  WPP_RECORDER_SF_qDD(
    WPP_GLOBAL_Control->DeviceExtension,
    v7,
    v8,
    288,
    (__int64)WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids,
    (char)this,
    *((_WORD *)this + 74),
    v9);
LABEL_72:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v10) = 5;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v10,
      1,
      294,
      (__int64)WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids,
      v9);
  }
LABEL_76:
  _WDI_INDICATION_SAE_AUTH_PARAMS_NEEDED_PARAMETERS::~_WDI_INDICATION_SAE_AUTH_PARAMS_NEEDED_PARAMETERS((_WDI_INDICATION_SAE_AUTH_PARAMS_NEEDED_PARAMETERS *)&v42);
}

```

## disassembly

```asm
0x1400868e8  mov     [rsp-8+arg_18], rbx
0x1400868ed  push    rbp
0x1400868ee  push    rsi
0x1400868ef  push    rdi
0x1400868f0  push    r12
0x1400868f2  push    r13
0x1400868f4  push    r14
0x1400868f6  push    r15
0x1400868f8  lea     rbp, [rsp-10h]
0x1400868fd  sub     rsp, 110h
0x140086904  mov     rax, cs:__security_cookie
0x14008690b  xor     rax, rsp
0x14008690e  mov     [rbp+40h+var_38], rax
0x140086912  and     [rsp+140h+var_E0], 0FFFFFFFEh
0x140086917  xor     eax, eax
0x140086919  xor     ebx, ebx
0x14008691b  mov     [rsp+140h+var_DC], rax
0x140086920  mov     [rsp+140h+Size], rax
0x140086925  xorps   xmm0, xmm0
0x140086928  mov     [rbp+40h+var_A0], eax
0x14008692b  mov     r12, r8
0x14008692e  mov     [rbp+40h+var_9C], al
0x140086931  mov     r14d, edx
0x140086934  mov     qword ptr [rbp+40h+var_98], rax
0x140086938  mov     rsi, rcx
0x14008693b  mov     rax, 2D544345524944h
0x140086945  mov     [rsp+140h+Src], rbx
0x14008694a  mov     qword ptr [rbp+40h+var_98+0Ch], rax
0x14008694e  xor     eax, eax
0x140086950  mov     [rbp+40h+var_74], rax
0x140086954  mov     [rbp+40h+var_C0], bl
0x140086957  mov     [rbp+40h+var_B8], ebx
0x14008695a  mov     [rbp+40h+var_B0], rbx
0x14008695e  mov     [rbp+40h+var_A8], bl
0x140086961  mov     dword ptr [rbp+40h+var_98+8], 7
0x140086968  movups  [rbp+40h+var_84], xmm0
0x14008696c  lea     rax, WPP_RECORDER_INITIALIZED
0x140086973  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14008697a  lea     edx, [rbx+5]
0x14008697d  lea     r15, WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids
0x140086984  lea     edi, [rbx+1]
0x140086987  jz      short loc_1400869B2
0x140086989  mov     rcx, cs:WPP_GLOBAL_Control
0x140086990  cmp     [rcx+29h], dl
0x140086993  jnb     short loc_14008699B
0x140086995  cmp     [rcx+48h], bx
0x140086999  jz      short loc_1400869B2
0x14008699b  mov     rcx, [rcx+40h]
0x14008699f  mov     r9d, 11Fh
0x1400869a5  mov     r8d, edi
0x1400869a8  mov     [rsp+140h+var_120], r15
0x1400869ad  call    WPP_RECORDER_SF_
0x1400869b2  mov     r8, [rsi+88h]
0x1400869b9  lea     rdx, [r12+30h]
0x1400869be  add     r8, 1508h
0x1400869c5  lea     ecx, [r14-30h]
0x1400869c9  lea     r9, [rsp+140h+var_E0]
0x1400869ce  call    ParseWdiIndicationP2pActionFrameReceivedFromIhv
0x1400869d3  mov     r13d, eax
0x1400869d6  test    eax, eax
0x1400869d8  jz      short loc_140086A25
0x1400869da  lea     rax, WPP_RECORDER_INITIALIZED
0x1400869e1  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400869e8  jz      loc_1400870B7
0x1400869ee  movzx   ecx, word ptr [rsi+94h]
0x1400869f5  mov     r9d, 120h
0x1400869fb  mov     [rsp+140h+var_108], r13d
0x140086a00  mov     dl, 2
0x140086a02  mov     [rsp+140h+var_110], ecx
0x140086a06  mov     rcx, cs:WPP_GLOBAL_Control
0x140086a0d  mov     qword ptr [rsp+140h+var_118], rsi
0x140086a12  mov     [rsp+140h+var_120], r15
0x140086a17  mov     rcx, [rcx+40h]
0x140086a1b  call    WPP_RECORDER_SF_qDD
0x140086a20  jmp     loc_140087072
0x140086a25  movzx   eax, word ptr [rsp+140h+Size]
0x140086a2a  mov     ecx, dword ptr [rsp+140h+var_DC+4]
0x140086a2e  mov     dword ptr [rbp+40h+var_98], ecx
0x140086a31  mov     dword ptr [rbp+40h+var_40], ecx
0x140086a34  mov     ecx, dword ptr [rsp+140h+var_DC]
0x140086a38  mov     word ptr [rbp+40h+var_98+4], ax
0x140086a3c  mov     word ptr [rbp+40h+var_40+4], ax
0x140086a40  mov     eax, 1Ch
0x140086a45  lea     edx, [rax+4]
0x140086a48  lea     r8d, [rax+0Ch]
0x140086a4c  sub     ecx, edi
0x140086a4e  jz      loc_140086AEE
0x140086a54  sub     ecx, edi
0x140086a56  jz      loc_140086AE6
0x140086a5c  sub     ecx, edi
0x140086a5e  jz      short loc_140086AD9
0x140086a60  sub     ecx, edi
0x140086a62  jz      short loc_140086ACE
0x140086a64  sub     ecx, edi
0x140086a66  jz      short loc_140086AC6
0x140086a68  sub     ecx, edi
0x140086a6a  jz      short loc_140086ABE
0x140086a6c  cmp     ecx, edi
0x140086a6e  jz      short loc_140086AB6
0x140086a70  lea     rax, WPP_RECORDER_INITIALIZED
0x140086a77  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140086a7e  jz      loc_1400870B7
0x140086a84  mov     rcx, cs:WPP_GLOBAL_Control
0x140086a8b  mov     r9d, 121h
0x140086a91  movzx   eax, word ptr [rsi+94h]
0x140086a98  mov     dl, 2
0x140086a9a  mov     [rsp+140h+var_110], eax
0x140086a9e  mov     qword ptr [rsp+140h+var_118], rsi
0x140086aa3  mov     rcx, [rcx+40h]
0x140086aa7  mov     [rsp+140h+var_120], r15
0x140086aac  call    WPP_RECORDER_SF_qD
0x140086ab1  jmp     loc_140087072
0x140086ab6  mov     r15d, 40030021h
0x140086abc  jmp     short loc_140086AF6
0x140086abe  mov     r15d, 4003001Fh
0x140086ac4  jmp     short loc_140086AD4
0x140086ac6  mov     r15d, 4003001Dh
0x140086acc  jmp     short loc_140086AF6
0x140086ace  mov     r15d, 4003001Bh
0x140086ad4  mov     eax, r8d
0x140086ad7  jmp     short loc_140086AF6
0x140086ad9  mov     eax, 14h
0x140086ade  mov     r15d, 40030019h
0x140086ae4  jmp     short loc_140086AF6
0x140086ae6  mov     r15d, 40030017h
0x140086aec  jmp     short loc_140086AF4
0x140086aee  mov     r15d, 40030015h
0x140086af4  mov     eax, edx
0x140086af6  mov     ecx, dword ptr [rsp+140h+Size+4]
0x140086afa  lea     edx, [rcx+rax]
0x140086afd  mov     [rsp+140h+var_EC], edx
0x140086b01  cmp     edx, eax
0x140086b03  jnb     short loc_140086B68
0x140086b05  lea     rax, WPP_RECORDER_INITIALIZED
0x140086b0c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140086b13  lea     r15, WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids
0x140086b1a  jz      short loc_140086B5D
0x140086b1c  movzx   eax, word ptr [rsi+94h]
0x140086b23  mov     r9d, 122h
0x140086b29  mov     [rsp+140h+var_F8], 0C0000001h
0x140086b31  mov     dl, 2
0x140086b33  mov     [rsp+140h+var_100], 0FFFFFFFFh
0x140086b3b  mov     [rsp+140h+var_108], ecx
0x140086b3f  mov     rcx, cs:WPP_GLOBAL_Control
0x140086b46  mov     [rsp+140h+var_110], eax
0x140086b4a  mov     qword ptr [rsp+140h+var_118], rsi
0x140086b4f  mov     [rsp+140h+var_120], r15
0x140086b54  mov     rcx, [rcx+40h]
0x140086b58  call    WPP_RECORDER_SF_qDddd
0x140086b5d  mov     r13d, 0C0000001h
0x140086b63  jmp     loc_140087072
0x140086b68  mov     ecx, edx; unsigned __int64
0x140086b6a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140086b6f  mov     rdi, rax
0x140086b72  test    rax, rax
0x140086b75  jnz     short loc_140086BC6
0x140086b77  lea     rax, WPP_RECORDER_INITIALIZED
0x140086b7e  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140086b85  lea     r15, WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids
0x140086b8c  jz      short loc_140086BBB
0x140086b8e  mov     rcx, cs:WPP_GLOBAL_Control
0x140086b95  mov     r9d, 123h
0x140086b9b  movzx   eax, word ptr [rsi+94h]
0x140086ba2  mov     dl, 2
0x140086ba4  mov     [rsp+140h+var_110], eax
0x140086ba8  mov     qword ptr [rsp+140h+var_118], rsi
0x140086bad  mov     rcx, [rcx+40h]
0x140086bb1  mov     [rsp+140h+var_120], r15
0x140086bb6  call    WPP_RECORDER_SF_qD
0x140086bbb  mov     r13d, 0C000009Ah
0x140086bc1  jmp     loc_14008706D
0x140086bc6  mov     ecx, dword ptr [rsp+140h+var_DC]
0x140086bca  sub     ecx, 1
0x140086bcd  jz      loc_140086E00
0x140086bd3  sub     ecx, 1
0x140086bd6  jz      loc_140086DC1
0x140086bdc  sub     ecx, 1
0x140086bdf  jz      loc_140086D8F
0x140086be5  sub     ecx, 1
0x140086be8  jz      loc_140086CB8
0x140086bee  sub     ecx, 1
0x140086bf1  jz      short loc_140086C4E
0x140086bf3  sub     ecx, 1
0x140086bf6  jz      loc_140086C83
0x140086bfc  cmp     ecx, 1
0x140086bff  jz      short loc_140086C4E
0x140086c01  lea     rax, WPP_RECORDER_INITIALIZED
0x140086c08  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140086c0f  lea     r15, WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids
0x140086c16  jz      loc_140087063
0x140086c1c  mov     rcx, cs:WPP_GLOBAL_Control
0x140086c23  mov     r9d, 124h
0x140086c29  movzx   eax, word ptr [rsi+94h]
0x140086c30  mov     dl, 2
0x140086c32  mov     [rsp+140h+var_110], eax
0x140086c36  mov     qword ptr [rsp+140h+var_118], rsi
0x140086c3b  mov     rcx, [rcx+40h]
0x140086c3f  mov     [rsp+140h+var_120], r15
0x140086c44  call    WPP_RECORDER_SF_qD
0x140086c49  jmp     loc_140087063
0x140086c4e  mov     dword ptr [rax], 1C0180h
0x140086c54  mov     ecx, 1Ch
0x140086c59  mov     al, byte ptr [rsp+140h+Size+2]
0x140086c5d  mov     [rdi+10h], al
0x140086c60  mov     eax, dword ptr [rsp+140h+var_DC+4]
0x140086c64  mov     [rdi+4], eax
0x140086c67  movzx   eax, word ptr [rsp+140h+Size]
0x140086c6c  mov     [rdi+14h], ecx
0x140086c6f  lea     rcx, [rdi+1Ch]
0x140086c73  mov     [rdi+8], ax
0x140086c77  mov     eax, dword ptr [rsp+140h+Size+4]
0x140086c7b  mov     [rdi+18h], eax
0x140086c7e  jmp     loc_140086DF1
0x140086c83  mov     dword ptr [rax], 280180h
0x140086c89  mov     ecx, 28h ; '('
0x140086c8e  mov     al, byte ptr [rsp+140h+Size+2]
0x140086c92  mov     [rdi+10h], al
0x140086c95  mov     eax, dword ptr [rsp+140h+var_DC+4]
0x140086c99  mov     [rdi+4], eax
0x140086c9c  movzx   eax, word ptr [rsp+140h+Size]
0x140086ca1  mov     [rdi+20h], ecx
0x140086ca4  lea     rcx, [rdi+28h]
0x140086ca8  mov     [rdi+8], ax
0x140086cac  mov     eax, dword ptr [rsp+140h+Size+4]
0x140086cb0  mov     [rdi+24h], eax
0x140086cb3  jmp     loc_140086DF1
0x140086cb8  xor     eax, eax
0x140086cba  mov     dword ptr [rdi], 280180h
0x140086cc0  mov     [rsp+140h+var_F0], eax
0x140086cc4  xorps   xmm0, xmm0
0x140086cc7  movups  xmmword ptr [rbp+40h+var_58], xmm0
0x140086ccb  mov     qword ptr [rbp+40h+var_58+0Eh], rax
0x140086ccf  lea     ecx, [rax+28h]
0x140086cd2  mov     al, byte ptr [rsp+140h+Size+2]
0x140086cd6  mov     [rdi+10h], al
0x140086cd9  mov     eax, dword ptr [rsp+140h+var_DC+4]
0x140086cdd  mov     [rdi+4], eax
0x140086ce0  movzx   eax, word ptr [rsp+140h+Size]
0x140086ce5  mov     [rdi+20h], ecx
0x140086ce8  lea     rcx, [rdi+28h]; void *
0x140086cec  mov     [rdi+8], ax
0x140086cf0  mov     eax, dword ptr [rsp+140h+Size+4]
0x140086cf4  mov     [rdi+24h], eax
0x140086cf7  mov     r8d, eax; Size
0x140086cfa  mov     rdx, [rsp+140h+Src]; Src
0x140086cff  movups  [rbp+40h+var_68], xmm0
0x140086d03  call    memmove
0x140086d08  mov     edx, dword ptr [rsp+140h+Size+4]; unsigned int
0x140086d0c  lea     r9, [rbp+40h+var_A0]; void *
0x140086d10  mov     rcx, [rsp+140h+Src]; unsigned __int8 *
0x140086d15  mov     r8b, 11h; unsigned __int8
0x140086d18  mov     word ptr [rsp+140h+var_120], 5; unsigned __int16
0x140086d1f  call    ?GetSimpleAttribute@@YAJPEAEKEPEAXG@Z; GetSimpleAttribute(uchar *,ulong,uchar,void *,ushort)
0x140086d24  test    eax, eax
0x140086d26  js      loc_140086E69
0x140086d2c  mov     edx, dword ptr [rsp+140h+Size+4]
0x140086d30  lea     r9, [rbp+40h+var_68]
0x140086d34  mov     rcx, [rsp+140h+Src]
0x140086d39  lea     r8, [rsp+140h+var_F0]
0x140086d3e  call    WFDGetGroupID
0x140086d43  test    eax, eax
0x140086d45  js      loc_140086E69
0x140086d4b  mov     edx, [rsp+140h+var_F0]
0x140086d4f  lea     r8, [rbp+40h+var_98]
0x140086d53  lea     rcx, [rbp+40h+var_68]
0x140086d57  call    WFDConvertGroupIDFromOTAtoDot11
0x140086d5c  test    eax, eax
0x140086d5e  js      loc_140086E69
0x140086d64  mov     edx, dword ptr [rsp+140h+Size+4]; unsigned int
0x140086d68  lea     r9, [rbp+40h+var_40]; void *
0x140086d6c  mov     rcx, [rsp+140h+Src]; unsigned __int8 *
0x140086d71  mov     r8b, 7; unsigned __int8
0x140086d74  mov     word ptr [rsp+140h+var_120], 6; unsigned __int16
0x140086d7b  call    ?GetSimpleAttribute@@YAJPEAEKEPEAXG@Z; GetSimpleAttribute(uchar *,ulong,uchar,void *,ushort)
0x140086d80  test    eax, eax
0x140086d82  js      loc_140086E69
0x140086d88  mov     bl, 1
0x140086d8a  jmp     loc_140086E69
0x140086d8f  mov     dword ptr [rax], 140180h
0x140086d95  mov     ecx, 14h
0x140086d9a  mov     al, byte ptr [rsp+140h+Size+2]
0x140086d9e  mov     [rdi+0Ah], al
0x140086da1  mov     eax, dword ptr [rsp+140h+var_DC+4]
0x140086da5  mov     [rdi+4], eax
0x140086da8  movzx   eax, word ptr [rsp+140h+Size]
0x140086dad  mov     [rdi+0Ch], ecx
0x140086db0  lea     rcx, [rdi+14h]
0x140086db4  mov     [rdi+8], ax
0x140086db8  mov     eax, dword ptr [rsp+140h+Size+4]
0x140086dbc  mov     [rdi+10h], eax
0x140086dbf  jmp     short loc_140086DF1
0x140086dc1  mov     dword ptr [rax], 200180h
0x140086dc7  mov     ecx, 20h ; ' '
0x140086dcc  mov     al, byte ptr [rsp+140h+Size+2]
0x140086dd0  mov     [rdi+0Ah], al
0x140086dd3  mov     eax, dword ptr [rsp+140h+var_DC+4]
0x140086dd7  mov     [rdi+4], eax
0x140086dda  movzx   eax, word ptr [rsp+140h+Size]
0x140086ddf  mov     [rdi+18h], ecx
0x140086de2  lea     rcx, [rdi+20h]; void *
  ... truncated ...
```
