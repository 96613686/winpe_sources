# BthUsbAltSetting6_ScoProcessReadUrb(_DEVICE_EXTENSION *,_SCO_USB_TRANSFER_CTX *,_SCO_USB_TRANSFER_CTX *,uchar *)

- ea: `0x140007410`
- end: `0x1400076b2`
- name: `?BthUsbAltSetting6_ScoProcessReadUrb@@YAXPEAU_DEVICE_EXTENSION@@PEAU_SCO_USB_TRANSFER_CTX@@1PEAE@Z`
- size: `674`
- prototype: `void __fastcall(struct _DEVICE_EXTENSION *, struct _SCO_USB_TRANSFER_CTX *, struct _SCO_USB_TRANSFER_CTX *, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140007410`
- `0x1400089f8`
- `0x140008b20`
- `0x140008c4c`
- `0x14000de00`

## pseudocode

```c
void __fastcall BthUsbAltSetting6_ScoProcessReadUrb(
        struct _DEVICE_EXTENSION *a1,
        struct _SCO_USB_TRANSFER_CTX *a2,
        struct _SCO_USB_TRANSFER_CTX *a3,
        unsigned __int8 *a4)
{
  struct _SCO_USB_TRANSFER_CTX *v4; // rsi
  _URB *Urb; // rdi
  unsigned int NumberOfPackets; // edx
  __int64 v8; // rbx
  int Status; // r10d
  int v10; // r11d
  bool v11; // al
  _OWORD *AuxiliaryBuffer; // r8
  unsigned __int8 *TransferBuffer; // rax
  __int64 Offset; // rcx
  char *v15; // r8
  int v16; // edx
  _SCO_USB_CHANNEL *v17; // rcx
  int v18; // eax
  int (__fastcall *Callback)(void *, _BTH_SCO_MP_INDICATION_CODE, _BTH_SCO_MP_INDICATION_PARAMETERS *); // rax
  void *CallbackContext; // rcx
  bool v21; // r10
  int v22; // [rsp+20h] [rbp-B8h]
  int v23; // [rsp+28h] [rbp-B0h]
  int v24; // [rsp+30h] [rbp-A8h]
  int v25; // [rsp+38h] [rbp-A0h]
  char v26; // [rsp+48h] [rbp-90h]
  char v27; // [rsp+48h] [rbp-90h]
  char v28; // [rsp+48h] [rbp-90h]
  _QWORD v29[2]; // [rsp+70h] [rbp-68h] BYREF
  __int128 v30; // [rsp+80h] [rbp-58h]
  __int128 v31; // [rsp+90h] [rbp-48h]

  *a4 = 0;
  v4 = a3;
  Urb = a3->Urb;
  NumberOfPackets = Urb->UrbIsochronousTransfer.NumberOfPackets;
  if ( NumberOfPackets )
  {
    v8 = 0;
    do
    {
      Status = Urb->UrbIsochronousTransfer.IsoPacket[v8].Status;
      v10 = v8 + Urb->UrbIsochronousTransfer.StartFrame;
      if ( Status >= 0 )
      {
        LODWORD(a3) = Urb->UrbIsochronousTransfer.IsoPacket[v8].Length;
        if ( (_DWORD)a3 )
        {
          if ( (_DWORD)a3 == 63 )
          {
            AuxiliaryBuffer = v4->AuxiliaryBuffer;
            if ( AuxiliaryBuffer && v4->AuxBufferLen >= 0x3F )
            {
              TransferBuffer = v4->TransferBuffer;
              Offset = Urb->UrbIsochronousTransfer.IsoPacket[v8].Offset;
              *AuxiliaryBuffer = *(_OWORD *)&TransferBuffer[Offset];
              AuxiliaryBuffer[1] = *(_OWORD *)&TransferBuffer[Offset + 16];
              AuxiliaryBuffer[2] = *(_OWORD *)&TransferBuffer[Offset + 32];
              *(_OWORD *)((char *)AuxiliaryBuffer + 47) = *(_OWORD *)&TransferBuffer[Offset + 47];
              v15 = (char *)v4->AuxiliaryBuffer;
              v16 = 0;
              while ( 1 )
              {
                v17 = &a1->Sco.Channel[(unsigned __int16)v16];
                if ( v17->ConnectionHandle == (*(_WORD *)v15 & 0xFFF) )
                  break;
                LOWORD(v16) = v16 + 1;
                if ( (unsigned __int16)v16 >= 3u )
                  goto LABEL_24;
              }
              if ( v17 )
              {
                v29[0] = v17->ConnectionHandle;
                v29[1] = v15 + 3;
                v18 = (unsigned __int8)v15[2];
                v30 = 0;
                LODWORD(v30) = v18;
                Callback = v17->Callback;
                CallbackContext = v17->CallbackContext;
                v31 = 0;
                *((_QWORD *)&v30 + 1) = 0;
                Callback(CallbackContext, ScoMpIndicationRead, (_BTH_SCO_MP_INDICATION_PARAMETERS *)v29);
                goto LABEL_35;
              }
LABEL_24:
              LOBYTE(v16) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
              WPP_RECORDER_AND_TRACE_SF_LLLLD(
                WPP_GLOBAL_Control->AttachedDevice,
                v16,
                (_DWORD)v15,
                WPP_GLOBAL_Control->DeviceExtension,
                v22,
                v23,
                40,
                v25,
                v8,
                Urb->UrbIsochronousTransfer.NumberOfPackets,
                v10,
                Urb->UrbIsochronousTransfer.IsoPacket[v8].Length,
                *v15);
            }
            else
            {
              v21 = (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
              v28 = NumberOfPackets;
              LOBYTE(NumberOfPackets) = v21;
              WPP_RECORDER_AND_TRACE_SF_LLLLqL(
                WPP_GLOBAL_Control->AttachedDevice,
                NumberOfPackets,
                (_DWORD)AuxiliaryBuffer,
                WPP_GLOBAL_Control->DeviceExtension,
                v22,
                v23,
                v24,
                v25,
                v8,
                v28,
                v10,
                63,
                (char)AuxiliaryBuffer,
                v4->AuxBufferLen);
            }
          }
          else
          {
            v11 = (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
            v27 = NumberOfPackets;
            LOBYTE(NumberOfPackets) = v11;
            WPP_RECORDER_AND_TRACE_SF_LLLLL(
              WPP_GLOBAL_Control->AttachedDevice,
              NumberOfPackets,
              (_DWORD)a3,
              WPP_GLOBAL_Control->DeviceExtension,
              v22,
              v23,
              v24,
              v25,
              v8,
              v27,
              v10,
              (char)a3);
          }
        }
      }
      else
      {
        LOBYTE(a3) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
        v26 = NumberOfPackets;
        LOBYTE(NumberOfPackets) = (_BYTE)a3;
        WPP_RECORDER_AND_TRACE_SF_LLLLD(
          WPP_GLOBAL_Control->AttachedDevice,
          NumberOfPackets,
          (_DWORD)a3,
          WPP_GLOBAL_Control->DeviceExtension,
          v22,
          v23,
          37,
          v25,
          v8,
          v26,
          v10,
          Urb->UrbIsochronousTransfer.IsoPacket[v8].Length,
          Status);
      }
LABEL_35:
      NumberOfPackets = Urb->UrbIsochronousTransfer.NumberOfPackets;
      v8 = (unsigned int)(v8 + 1);
    }
    while ( (unsigned int)v8 < NumberOfPackets );
  }
}

```

## disassembly

```asm
0x140007410  push    rbx
0x140007412  push    rbp
0x140007413  push    rsi
0x140007414  push    rdi
0x140007415  push    r14
0x140007417  push    r15
0x140007419  sub     rsp, 0A8h
0x140007420  mov     byte ptr [r9], 0
0x140007424  mov     rsi, r8
0x140007427  mov     rdi, [r8+48h]
0x14000742b  mov     rbp, rcx
0x14000742e  mov     edx, [rdi+84h]
0x140007434  test    edx, edx
0x140007436  jz      loc_1400076A1
0x14000743c  xor     ebx, ebx
0x14000743e  lea     r15d, [rbx+1]
0x140007442  mov     r11d, [rdi+80h]
0x140007449  lea     r9, [rbx+rbx*2]
0x14000744d  mov     r10d, [rdi+r9*4+94h]
0x140007455  add     r11d, ebx
0x140007458  test    r10d, r10d
0x14000745b  jns     short loc_1400074B3
0x14000745d  mov     rcx, cs:WPP_GLOBAL_Control
0x140007464  mov     eax, [rcx+2Ch]
0x140007467  test    al, 8
0x140007469  jz      short loc_140007476
0x14000746b  cmp     byte ptr [rcx+29h], 2
0x14000746f  jb      short loc_140007476
0x140007471  mov     r8b, r15b
0x140007474  jmp     short loc_140007479
0x140007476  xor     r8b, r8b
0x140007479  mov     eax, [rdi+r9*4+90h]
0x140007481  mov     dword ptr [rsp+0D8h+var_78], r10d
0x140007486  mov     [rsp+0D8h+var_80], eax
0x14000748a  mov     [rsp+0D8h+var_88], r11d
0x14000748f  mov     dword ptr [rsp+0D8h+var_90], edx
0x140007493  mov     dl, r8b
0x140007496  mov     [rsp+0D8h+var_98], ebx
0x14000749a  mov     [rsp+0D8h+var_A8], 25h ; '%'
0x1400074a1  mov     r9, [rcx+40h]
0x1400074a5  mov     rcx, [rcx+18h]
0x1400074a9  call    WPP_RECORDER_AND_TRACE_SF_LLLLD
0x1400074ae  jmp     loc_140007690
0x1400074b3  mov     r8d, [rdi+r9*4+90h]
0x1400074bb  test    r8d, r8d
0x1400074be  jz      loc_140007690
0x1400074c4  cmp     r8d, 3Fh ; '?'
0x1400074c8  jz      short loc_14000750B
0x1400074ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1400074d1  mov     eax, [rcx+2Ch]
0x1400074d4  test    al, 8
0x1400074d6  jz      short loc_1400074E3
0x1400074d8  cmp     byte ptr [rcx+29h], 2
0x1400074dc  jb      short loc_1400074E3
0x1400074de  mov     al, r15b
0x1400074e1  jmp     short loc_1400074E5
0x1400074e3  xor     al, al
0x1400074e5  mov     r9, [rcx+40h]
0x1400074e9  mov     rcx, [rcx+18h]
0x1400074ed  mov     [rsp+0D8h+var_80], r8d
0x1400074f2  mov     [rsp+0D8h+var_88], r11d
0x1400074f7  mov     dword ptr [rsp+0D8h+var_90], edx
0x1400074fb  mov     dl, al
0x1400074fd  mov     [rsp+0D8h+var_98], ebx
0x140007501  call    WPP_RECORDER_AND_TRACE_SF_LLLLL
0x140007506  jmp     loc_140007690
0x14000750b  mov     r8, [rsi+80h]
0x140007512  test    r8, r8
0x140007515  jz      loc_140007640
0x14000751b  cmp     dword ptr [rsi+88h], 3Fh ; '?'
0x140007522  jb      loc_140007640
0x140007528  mov     rax, [rsi+68h]
0x14000752c  mov     ecx, [rdi+r9*4+8Ch]
0x140007534  movups  xmm0, xmmword ptr [rax+rcx]
0x140007538  movups  xmmword ptr [r8], xmm0
0x14000753c  movups  xmm1, xmmword ptr [rax+rcx+10h]
0x140007541  movups  xmmword ptr [r8+10h], xmm1
0x140007546  movups  xmm0, xmmword ptr [rax+rcx+20h]
0x14000754b  movups  xmmword ptr [r8+20h], xmm0
0x140007550  movups  xmm1, xmmword ptr [rax+rcx+2Fh]
0x140007555  mov     eax, 0FFFh
0x14000755a  movups  xmmword ptr [r8+2Fh], xmm1
0x14000755f  mov     r8, [rsi+80h]
0x140007566  movzx   r10d, word ptr [r8]
0x14000756a  and     r10w, ax
0x14000756e  xor     edx, edx
0x140007570  movzx   eax, dx
0x140007573  imul    rcx, rax, 98h
0x14000757a  add     rcx, 2B0h
0x140007581  add     rcx, rbp
0x140007584  cmp     [rcx], r10w
0x140007588  jz      short loc_140007596
0x14000758a  add     dx, r15w
0x14000758e  cmp     dx, 3
0x140007592  jb      short loc_140007570
0x140007594  jmp     short loc_14000759B
0x140007596  test    rcx, rcx
0x140007599  jnz     short loc_1400075E9
0x14000759b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400075a2  mov     eax, [rcx+2Ch]
0x1400075a5  test    al, 8
0x1400075a7  jz      short loc_1400075B4
0x1400075a9  cmp     byte ptr [rcx+29h], 2
0x1400075ad  jb      short loc_1400075B4
0x1400075af  mov     dl, r15b
0x1400075b2  jmp     short loc_1400075B6
0x1400075b4  xor     dl, dl
0x1400075b6  movzx   eax, r10w
0x1400075ba  mov     dword ptr [rsp+0D8h+var_78], eax
0x1400075be  mov     eax, [rdi+r9*4+90h]
0x1400075c6  mov     [rsp+0D8h+var_80], eax
0x1400075ca  mov     eax, [rdi+84h]
0x1400075d0  mov     [rsp+0D8h+var_88], r11d
0x1400075d5  mov     dword ptr [rsp+0D8h+var_90], eax
0x1400075d9  mov     [rsp+0D8h+var_98], ebx
0x1400075dd  mov     [rsp+0D8h+var_A8], 28h ; '('
0x1400075e4  jmp     loc_1400074A1
0x1400075e9  movzx   eax, word ptr [rcx]
0x1400075ec  xorps   xmm0, xmm0
0x1400075ef  movups  [rsp+0D8h+var_68], xmm0
0x1400075f4  mov     word ptr [rsp+0D8h+var_68], ax
0x1400075f9  xor     edx, edx
0x1400075fb  lea     rax, [r8+3]
0x1400075ff  mov     qword ptr [rsp+0D8h+var_68+8], rax
0x140007604  movzx   eax, byte ptr [r8+2]
0x140007609  lea     r8, [rsp+0D8h+var_68]
0x14000760e  movups  [rsp+0D8h+var_58], xmm0
0x140007616  mov     dword ptr [rsp+0D8h+var_58], eax
0x14000761d  mov     rax, [rcx+30h]
0x140007621  mov     rcx, [rcx+38h]
0x140007625  movups  [rsp+0D8h+var_48], xmm0
0x14000762d  mov     qword ptr [rsp+0D8h+var_58+8], 0
0x140007639  call    _guard_dispatch_icall
0x14000763e  jmp     short loc_140007690
0x140007640  mov     rcx, cs:WPP_GLOBAL_Control
0x140007647  mov     eax, [rcx+2Ch]
0x14000764a  test    al, 8
0x14000764c  jz      short loc_140007659
0x14000764e  cmp     byte ptr [rcx+29h], 2
0x140007652  jb      short loc_140007659
0x140007654  mov     r10b, r15b
0x140007657  jmp     short loc_14000765C
0x140007659  xor     r10b, r10b
0x14000765c  mov     eax, [rsi+88h]
0x140007662  mov     r9, [rcx+40h]
0x140007666  mov     rcx, [rcx+18h]
0x14000766a  mov     [rsp+0D8h+var_70], eax
0x14000766e  mov     [rsp+0D8h+var_78], r8
0x140007673  mov     [rsp+0D8h+var_80], 3Fh ; '?'
0x14000767b  mov     [rsp+0D8h+var_88], r11d
0x140007680  mov     dword ptr [rsp+0D8h+var_90], edx
0x140007684  mov     dl, r10b
0x140007687  mov     [rsp+0D8h+var_98], ebx
0x14000768b  call    WPP_RECORDER_AND_TRACE_SF_LLLLqL
0x140007690  mov     edx, [rdi+84h]
0x140007696  add     ebx, r15d
0x140007699  cmp     ebx, edx
0x14000769b  jb      loc_140007442
0x1400076a1  add     rsp, 0A8h
0x1400076a8  pop     r15
0x1400076aa  pop     r14
0x1400076ac  pop     rdi
0x1400076ad  pop     rsi
0x1400076ae  pop     rbp
0x1400076af  pop     rbx
0x1400076b0  retn
```
