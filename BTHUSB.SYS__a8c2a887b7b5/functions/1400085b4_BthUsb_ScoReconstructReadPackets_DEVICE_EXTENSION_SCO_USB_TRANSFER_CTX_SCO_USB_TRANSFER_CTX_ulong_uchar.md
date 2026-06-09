# BthUsb_ScoReconstructReadPackets(_DEVICE_EXTENSION *,_SCO_USB_TRANSFER_CTX *,_SCO_USB_TRANSFER_CTX *,ulong *,uchar *)

- ea: `0x1400085b4`
- end: `0x140008912`
- name: `?BthUsb_ScoReconstructReadPackets@@YAPEAU_SCO_DATA_PACKET@@PEAU_DEVICE_EXTENSION@@PEAU_SCO_USB_TRANSFER_CTX@@1PEAKPEAE@Z`
- size: `862`
- prototype: `struct _SCO_DATA_PACKET *__fastcall(struct _DEVICE_EXTENSION *, __int64, struct _SCO_USB_TRANSFER_CTX *, unsigned int *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x140007b10`

## callees

- `0x14000175c`
- `0x140007980`
- `0x1400085b4`
- `0x14000ddc0`
- `0x14000dec0`

## pseudocode

```c
struct _SCO_DATA_PACKET *__fastcall BthUsb_ScoReconstructReadPackets(
        struct _DEVICE_EXTENSION *a1,
        __int64 a2,
        struct _SCO_USB_TRANSFER_CTX *a3,
        unsigned int *a4,
        unsigned __int8 *a5)
{
  unsigned int v5; // ebx
  void *v6; // rdi
  const ScoUsbAltSetting *UsbAltSetting; // rax
  struct _SCO_USB_TRANSFER_CTX *v9; // r10
  struct _DEVICE_EXTENSION *v10; // r11
  char v11; // r14
  unsigned int FRAMES_X_HCIPACKET; // r13d
  unsigned int v13; // ecx
  unsigned int v14; // eax
  _URB *v15; // r11
  unsigned int v16; // r9d
  unsigned int v17; // r15d
  unsigned __int8 *v18; // r12
  __int64 v19; // r8
  unsigned __int8 *v20; // rcx
  _URB *Urb; // r8
  __int64 UrbFrameIndex; // rcx
  __int64 v23; // rcx
  int v24; // edx
  int v25; // r8d
  char *AuxiliaryBuffer; // rax
  unsigned int v27; // r15d
  unsigned int AuxBufferLen; // r12d
  __int64 v29; // r13
  __int64 *v30; // rdx
  unsigned __int8 v31; // al
  unsigned int v33; // [rsp+40h] [rbp-61h]
  unsigned int *v34; // [rsp+48h] [rbp-59h]
  char *v36; // [rsp+58h] [rbp-49h]
  _URB *v37; // [rsp+60h] [rbp-41h]
  void *v38; // [rsp+70h] [rbp-31h] BYREF
  _OWORD Src[2]; // [rsp+78h] [rbp-29h] BYREF
  __int64 v40; // [rsp+98h] [rbp-9h]

  v5 = 0;
  v34 = a4;
  *a4 = 0;
  v6 = 0;
  v40 = 0;
  UsbAltSetting = a1->Sco.UsbAltSetting;
  v9 = (struct _SCO_USB_TRANSFER_CTX *)a2;
  v10 = a1;
  v38 = 0;
  v11 = 1;
  memset(Src, 0, sizeof(Src));
  FRAMES_X_HCIPACKET = UsbAltSetting->FRAMES_X_HCIPACKET;
  v33 = FRAMES_X_HCIPACKET;
  if ( a2 )
  {
    v13 = *(_DWORD *)(a2 + 88);
    v14 = *(_DWORD *)(a2 + 80);
    if ( v14 > v13 && v14 - v13 < FRAMES_X_HCIPACKET )
    {
      v15 = *(_URB **)(a2 + 72);
      *a4 = v15->UrbIsochronousTransfer.StartFrame + v13;
      v16 = *(_DWORD *)(a2 + 88);
      v17 = *(_DWORD *)(a2 + 80);
      if ( v16 < v17 )
      {
        v18 = *(unsigned __int8 **)(a2 + 104);
        do
        {
          LODWORD(a2) = v16;
          v19 = v5++;
          v19 *= 2;
          *((_DWORD *)Src + 2 * v19) = v15->UrbIsochronousTransfer.IsoPacket[v16].Length;
          v20 = &v18[v15->UrbIsochronousTransfer.IsoPacket[v16++].Offset];
          *(&v38 + v19) = v20;
          v9->UrbFrameIndex = v16;
        }
        while ( v16 < v17 );
      }
      v10 = a1;
      a4 = v34;
    }
  }
  Urb = a3->Urb;
  v37 = Urb;
  while ( 1 )
  {
    UrbFrameIndex = a3->UrbFrameIndex;
    if ( (unsigned int)UrbFrameIndex >= a3->UrbFrames )
      break;
    a2 = 3 * UrbFrameIndex;
    if ( Urb->UrbIsochronousTransfer.IsoPacket[UrbFrameIndex].Status >= 0 )
    {
      if ( !v5 )
        *a4 = Urb->UrbIsochronousTransfer.StartFrame + UrbFrameIndex;
      v23 = v5;
      LODWORD(Src[v23]) = *(&Urb->UrbIsochronousTransfer.IsoPacket[0].Length + a2);
      *(&v38 + v23 * 2) = &a3->TransferBuffer[*(&Urb->UrbIsochronousTransfer.IsoPacket[0].Offset + a2)];
      if ( v5 + 1 < FRAMES_X_HCIPACKET )
      {
        ++v5;
      }
      else if ( BthUsb_ScoIsPacketInFrames(v10, (struct _SCO_HCIPACKET_FRAME *)&v38) )
      {
        AuxiliaryBuffer = (char *)a3->AuxiliaryBuffer;
        v27 = 0;
        AuxBufferLen = a3->AuxBufferLen;
        v36 = AuxiliaryBuffer;
        if ( FRAMES_X_HCIPACKET )
        {
          while ( 1 )
          {
            v29 = LODWORD(Src[v27]);
            if ( (unsigned int)v29 > AuxBufferLen )
              break;
            memmove(AuxiliaryBuffer, *(&v38 + 2 * v27), (unsigned int)v29);
            AuxBufferLen -= v29;
            AuxiliaryBuffer = &v36[v29];
            ++v27;
            FRAMES_X_HCIPACKET = v33;
            v36 = AuxiliaryBuffer;
            if ( v27 >= v33 )
              goto LABEL_24;
          }
          if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
            v11 = 0;
          v30 = WPP_bdb2f4b08e1e350eed49ca0df045c47e_Traceguids;
          LOBYTE(v30) = v11;
          WPP_RECORDER_AND_TRACE_SF_(
            WPP_GLOBAL_Control->AttachedDevice,
            (_DWORD)v30,
            v25,
            WPP_GLOBAL_Control->DeviceExtension,
            2,
            5,
            30,
            (__int64)WPP_bdb2f4b08e1e350eed49ca0df045c47e_Traceguids);
LABEL_36:
          v31 = 0;
          goto LABEL_44;
        }
LABEL_24:
        v6 = a3->AuxiliaryBuffer;
        v5 = 0;
        LOBYTE(v24) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
        WPP_RECORDER_AND_TRACE_SF_(
          WPP_GLOBAL_Control->AttachedDevice,
          v24,
          v25,
          WPP_GLOBAL_Control->DeviceExtension,
          4,
          5,
          31,
          (__int64)WPP_bdb2f4b08e1e350eed49ca0df045c47e_Traceguids);
        Urb = v37;
      }
      else
      {
        LOBYTE(v24) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
        WPP_RECORDER_AND_TRACE_SF_(
          WPP_GLOBAL_Control->AttachedDevice,
          v24,
          v25,
          WPP_GLOBAL_Control->DeviceExtension,
          4,
          5,
          29,
          (__int64)WPP_bdb2f4b08e1e350eed49ca0df045c47e_Traceguids);
        memmove(&v38, (char *)Src + 8, 0x20u);
        Urb = v37;
      }
    }
    else
    {
      v5 = 0;
    }
    ++a3->UrbFrameIndex;
    if ( v6 )
      goto LABEL_36;
    a4 = v34;
    v10 = a1;
  }
  v31 = 0;
  if ( v5 )
  {
    LOBYTE(a2) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
    WPP_RECORDER_AND_TRACE_SF_(
      WPP_GLOBAL_Control->AttachedDevice,
      a2,
      (_DWORD)Urb,
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      5,
      32,
      (__int64)WPP_bdb2f4b08e1e350eed49ca0df045c47e_Traceguids);
    a3->UrbFrameIndex = a3->UrbFrames - v5;
    v31 = 1;
  }
LABEL_44:
  *a5 = v31;
  return (struct _SCO_DATA_PACKET *)v6;
}

```

## disassembly

```asm
0x1400085b4  push    rbp
0x1400085b6  push    rbx
0x1400085b7  push    rsi
0x1400085b8  push    rdi
0x1400085b9  push    r12
0x1400085bb  push    r13
0x1400085bd  push    r14
0x1400085bf  push    r15
0x1400085c1  lea     rbp, [rsp-17h]
0x1400085c6  sub     rsp, 0B8h
0x1400085cd  mov     rax, cs:__security_cookie
0x1400085d4  xor     rax, rsp
0x1400085d7  mov     [rbp+4Fh+var_50], rax
0x1400085db  mov     rax, [rbp+4Fh+arg_20]
0x1400085df  xor     ebx, ebx
0x1400085e1  mov     [rbp+4Fh+var_88], rax
0x1400085e5  xorps   xmm0, xmm0
0x1400085e8  xor     eax, eax
0x1400085ea  mov     [rbp+4Fh+var_A8], r9
0x1400085ee  mov     [r9], eax
0x1400085f1  xor     edi, edi
0x1400085f3  mov     [rbp+4Fh+var_58], rax
0x1400085f7  mov     rsi, r8
0x1400085fa  mov     rax, [rcx+478h]
0x140008601  mov     r10, rdx
0x140008604  mov     [rbp+4Fh+var_A0], rcx
0x140008608  mov     r11, rcx
0x14000860b  mov     [rbp+4Fh+var_80], rbx
0x14000860f  lea     r14d, [rbx+1]
0x140008613  movups  [rbp+4Fh+Src], xmm0
0x140008617  mov     r13d, [rax+0Ch]
0x14000861b  mov     [rbp+4Fh+var_B0], r13d
0x14000861f  movups  [rbp+4Fh+var_68], xmm0
0x140008623  test    rdx, rdx
0x140008626  jz      short loc_14000869D
0x140008628  mov     ecx, [rdx+58h]
0x14000862b  mov     eax, [rdx+50h]
0x14000862e  cmp     eax, ecx
0x140008630  jbe     short loc_14000869D
0x140008632  sub     eax, ecx
0x140008634  cmp     eax, r13d
0x140008637  jnb     short loc_14000869D
0x140008639  mov     r11, [rdx+48h]
0x14000863d  add     ecx, [r11+80h]
0x140008644  mov     [r9], ecx
0x140008647  mov     r9d, [rdx+58h]
0x14000864b  mov     r15d, [rdx+50h]
0x14000864f  cmp     r9d, r15d
0x140008652  jnb     short loc_140008695
0x140008654  mov     r12, [rdx+68h]
0x140008658  mov     edx, r9d
0x14000865b  mov     r8d, ebx
0x14000865e  add     ebx, r14d
0x140008661  add     r8, r8
0x140008664  lea     rax, [rdx+rdx*2]
0x140008668  mov     ecx, [r11+rax*4+90h]
0x140008670  lea     rax, [rdx+rdx*2]
0x140008674  mov     dword ptr [rbp+r8*8+4Fh+Src], ecx
0x140008679  mov     ecx, [r11+rax*4+8Ch]
0x140008681  add     rcx, r12
0x140008684  inc     r9d
0x140008687  mov     [rbp+r8*8+4Fh+var_80], rcx
0x14000868c  mov     [r10+58h], r9d
0x140008690  cmp     r9d, r15d
0x140008693  jb      short loc_140008658
0x140008695  mov     r11, [rbp+4Fh+var_A0]
0x140008699  mov     r9, [rbp+4Fh+var_A8]
0x14000869d  mov     r8, [rsi+48h]
0x1400086a1  lea     r15, WPP_bdb2f4b08e1e350eed49ca0df045c47e_Traceguids
0x1400086a8  mov     [rbp+4Fh+var_90], r8
0x1400086ac  mov     r12d, 20h ; ' '
0x1400086b2  mov     ecx, [rsi+58h]
0x1400086b5  cmp     ecx, [rsi+50h]
0x1400086b8  jnb     loc_140008892
0x1400086be  lea     rdx, [rcx+rcx*2]
0x1400086c2  cmp     dword ptr [r8+rdx*4+94h], 0
0x1400086cb  jge     short loc_1400086D4
0x1400086cd  xor     ebx, ebx
0x1400086cf  jmp     loc_140008831
0x1400086d4  test    ebx, ebx
0x1400086d6  jnz     short loc_1400086E2
0x1400086d8  add     ecx, [r8+80h]
0x1400086df  mov     [r9], ecx
0x1400086e2  mov     eax, [r8+rdx*4+90h]
0x1400086ea  mov     ecx, ebx
0x1400086ec  add     rcx, rcx
0x1400086ef  mov     dword ptr [rbp+rcx*8+4Fh+Src], eax
0x1400086f3  mov     eax, [r8+rdx*4+8Ch]
0x1400086fb  add     rax, [rsi+68h]
0x1400086ff  mov     [rbp+rcx*8+4Fh+var_80], rax
0x140008704  lea     eax, [rbx+1]
0x140008707  cmp     eax, r13d
0x14000870a  jb      loc_14000882F
0x140008710  lea     rdx, [rbp+4Fh+var_80]; struct _SCO_HCIPACKET_FRAME *
0x140008714  mov     rcx, r11; struct _DEVICE_EXTENSION *
0x140008717  call    ?BthUsb_ScoIsPacketInFrames@@YAEPEAU_DEVICE_EXTENSION@@PEAU_SCO_HCIPACKET_FRAME@@@Z; BthUsb_ScoIsPacketInFrames(_DEVICE_EXTENSION *,_SCO_HCIPACKET_FRAME *)
0x14000871c  test    al, al
0x14000871e  jnz     short loc_14000877A
0x140008720  mov     rcx, cs:WPP_GLOBAL_Control
0x140008727  mov     eax, [rcx+2Ch]
0x14000872a  test    al, 10h
0x14000872c  jz      short loc_140008739
0x14000872e  cmp     byte ptr [rcx+29h], 4
0x140008732  jb      short loc_140008739
0x140008734  mov     dl, r14b
0x140008737  jmp     short loc_14000873B
0x140008739  xor     dl, dl
0x14000873b  mov     r9, [rcx+40h]
0x14000873f  mov     rcx, [rcx+18h]
0x140008743  mov     [rsp+0F0h+var_B8], r15
0x140008748  mov     [rsp+0F0h+var_C0], 1Dh
0x14000874f  mov     [rsp+0F0h+var_C8], 5
0x140008757  mov     [rsp+0F0h+var_D0], 4
0x14000875c  call    WPP_RECORDER_AND_TRACE_SF_
0x140008761  mov     r8, r12; Size
0x140008764  lea     rdx, [rbp+4Fh+Src+8]; Src
0x140008768  lea     rcx, [rbp+4Fh+var_80]; void *
0x14000876c  call    memmove
0x140008771  mov     r8, [rbp+4Fh+var_90]
0x140008775  jmp     loc_140008831
0x14000877a  mov     rax, [rsi+80h]
0x140008781  xor     r15d, r15d
0x140008784  mov     r12d, [rsi+88h]
0x14000878b  mov     [rbp+4Fh+var_98], rax
0x14000878f  test    r13d, r13d
0x140008792  jz      short loc_1400087D2
0x140008794  mov     edx, r15d
0x140008797  add     rdx, rdx
0x14000879a  mov     r13d, dword ptr [rbp+rdx*8+4Fh+Src]
0x14000879f  cmp     r13d, r12d
0x1400087a2  ja      loc_140008847
0x1400087a8  mov     rdx, [rbp+rdx*8+4Fh+var_80]; Src
0x1400087ad  mov     r8d, r13d; Size
0x1400087b0  mov     rcx, rax; void *
0x1400087b3  call    memmove
0x1400087b8  mov     rax, [rbp+4Fh+var_98]
0x1400087bc  sub     r12d, r13d
0x1400087bf  add     rax, r13
0x1400087c2  add     r15d, r14d
0x1400087c5  mov     r13d, [rbp+4Fh+var_B0]
0x1400087c9  mov     [rbp+4Fh+var_98], rax
0x1400087cd  cmp     r15d, r13d
0x1400087d0  jb      short loc_140008794
0x1400087d2  mov     rdi, [rsi+80h]
0x1400087d9  xor     ebx, ebx
0x1400087db  mov     rcx, cs:WPP_GLOBAL_Control
0x1400087e2  mov     eax, [rcx+2Ch]
0x1400087e5  test    al, 10h
0x1400087e7  jz      short loc_1400087F4
0x1400087e9  cmp     byte ptr [rcx+29h], 4
0x1400087ed  jb      short loc_1400087F4
0x1400087ef  mov     dl, r14b
0x1400087f2  jmp     short loc_1400087F6
0x1400087f4  xor     dl, dl
0x1400087f6  mov     r9, [rcx+40h]
0x1400087fa  lea     r15, WPP_bdb2f4b08e1e350eed49ca0df045c47e_Traceguids
0x140008801  mov     rcx, [rcx+18h]
0x140008805  mov     [rsp+0F0h+var_B8], r15
0x14000880a  mov     [rsp+0F0h+var_C0], 1Fh
0x140008811  mov     [rsp+0F0h+var_C8], 5
0x140008819  mov     [rsp+0F0h+var_D0], 4
0x14000881e  call    WPP_RECORDER_AND_TRACE_SF_
0x140008823  mov     r8, [rbp+4Fh+var_90]
0x140008827  mov     r12d, 20h ; ' '
0x14000882d  jmp     short loc_140008831
0x14000882f  mov     ebx, eax
0x140008831  add     [rsi+58h], r14d
0x140008835  test    rdi, rdi
0x140008838  jnz     short loc_14000888E
0x14000883a  mov     r9, [rbp+4Fh+var_A8]
0x14000883e  mov     r11, [rbp+4Fh+var_A0]
0x140008842  jmp     loc_1400086B2
0x140008847  mov     rcx, cs:WPP_GLOBAL_Control
0x14000884e  mov     eax, [rcx+2Ch]
0x140008851  test    al, 10h
0x140008853  jz      short loc_14000885B
0x140008855  cmp     byte ptr [rcx+29h], 2
0x140008859  jnb     short loc_14000885E
0x14000885b  xor     r14b, r14b
0x14000885e  mov     r9, [rcx+40h]
0x140008862  lea     rdx, WPP_bdb2f4b08e1e350eed49ca0df045c47e_Traceguids
0x140008869  mov     rcx, [rcx+18h]
0x14000886d  mov     [rsp+0F0h+var_B8], rdx
0x140008872  mov     dl, r14b
0x140008875  mov     [rsp+0F0h+var_C0], 1Eh
0x14000887c  mov     [rsp+0F0h+var_C8], 5
0x140008884  mov     [rsp+0F0h+var_D0], 2
0x140008889  call    WPP_RECORDER_AND_TRACE_SF_
0x14000888e  xor     al, al
0x140008890  jmp     short loc_1400088E8
0x140008892  xor     al, al
0x140008894  test    rdi, rdi
0x140008897  jnz     short loc_1400088E8
0x140008899  test    ebx, ebx
0x14000889b  jz      short loc_1400088E8
0x14000889d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400088a4  mov     eax, [rcx+2Ch]
0x1400088a7  test    al, 10h
0x1400088a9  jz      short loc_1400088B6
0x1400088ab  cmp     byte ptr [rcx+29h], 4
0x1400088af  jb      short loc_1400088B6
0x1400088b1  mov     dl, r14b
0x1400088b4  jmp     short loc_1400088B8
0x1400088b6  xor     dl, dl
0x1400088b8  mov     r9, [rcx+40h]
0x1400088bc  mov     rcx, [rcx+18h]
0x1400088c0  mov     [rsp+0F0h+var_B8], r15
0x1400088c5  mov     [rsp+0F0h+var_C0], r12w
0x1400088cb  mov     [rsp+0F0h+var_C8], 5
0x1400088d3  mov     [rsp+0F0h+var_D0], 4
0x1400088d8  call    WPP_RECORDER_AND_TRACE_SF_
0x1400088dd  mov     eax, [rsi+50h]
0x1400088e0  sub     eax, ebx
0x1400088e2  mov     [rsi+58h], eax
0x1400088e5  mov     al, r14b
0x1400088e8  mov     rcx, [rbp+4Fh+var_88]
0x1400088ec  mov     [rcx], al
0x1400088ee  mov     rax, rdi
0x1400088f1  mov     rcx, [rbp+4Fh+var_50]
0x1400088f5  xor     rcx, rsp; StackCookie
0x1400088f8  call    __security_check_cookie
0x1400088fd  add     rsp, 0B8h
0x140008904  pop     r15
0x140008906  pop     r14
0x140008908  pop     r13
0x14000890a  pop     r12
0x14000890c  pop     rdi
0x14000890d  pop     rsi
0x14000890e  pop     rbx
0x14000890f  pop     rbp
0x140008910  retn
```
