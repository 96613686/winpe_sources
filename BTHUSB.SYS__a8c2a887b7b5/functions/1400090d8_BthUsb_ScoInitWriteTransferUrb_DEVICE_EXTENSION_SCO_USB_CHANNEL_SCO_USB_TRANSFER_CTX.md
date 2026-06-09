# BthUsb_ScoInitWriteTransferUrb(_DEVICE_EXTENSION *,_SCO_USB_CHANNEL *,_SCO_USB_TRANSFER_CTX *)

- ea: `0x1400090d8`
- end: `0x140009338`
- name: `?BthUsb_ScoInitWriteTransferUrb@@YAJPEAU_DEVICE_EXTENSION@@PEAU_SCO_USB_CHANNEL@@PEAU_SCO_USB_TRANSFER_CTX@@@Z`
- size: `608`
- prototype: `__int64 __fastcall(struct _DEVICE_EXTENSION *, struct _SCO_USB_CHANNEL *, struct _SCO_USB_TRANSFER_CTX *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1400094f8`

## callees

- `0x1400090d8`
- `0x14000de00`

## pseudocode

```c
__int64 __fastcall BthUsb_ScoInitWriteTransferUrb(
        struct _DEVICE_EXTENSION *a1,
        struct _SCO_USB_CHANNEL *a2,
        struct _SCO_USB_TRANSFER_CTX *a3)
{
  _URB *Urb; // rbx
  unsigned int UrbFrames; // eax
  bool v7; // cc
  unsigned __int16 ConnectionHandle; // ax
  void *CallbackContext; // rcx
  int (__fastcall *Callback)(void *, _BTH_SCO_MP_INDICATION_CODE, _BTH_SCO_MP_INDICATION_PARAMETERS *); // rax
  __int64 result; // rax
  _USBD_ISO_PACKET_DESCRIPTOR *IsoPacket; // r14
  unsigned int v14; // edx
  unsigned int v15; // r12d
  void **v16; // rbx
  char *AuxiliaryBuffer; // rcx
  unsigned int v18; // r9d
  unsigned __int8 *v19; // r8
  void *v20; // rcx
  int (__fastcall *v21)(void *, _BTH_SCO_MP_INDICATION_CODE, _BTH_SCO_MP_INDICATION_PARAMETERS *); // rax
  __int64 v22; // rcx
  char *v23; // rdx
  unsigned __int8 *v24; // r8
  unsigned int v25; // edx
  const unsigned int *v26; // rcx
  unsigned int v27; // ebx
  unsigned int TxFragmentSize; // eax
  unsigned int v29; // edx
  unsigned int v30; // edx
  _BTH_PIPE_TYPE IndexPipe; // [rsp+20h] [rbp-49h]
  void **p_CallbackContext; // [rsp+28h] [rbp-41h]
  __int128 v33; // [rsp+30h] [rbp-39h] BYREF
  __int128 v34; // [rsp+40h] [rbp-29h]
  __int128 v35; // [rsp+50h] [rbp-19h]
  __int64 v36; // [rsp+60h] [rbp-9h]
  char *v37; // [rsp+68h] [rbp-1h]
  unsigned __int8 *v38; // [rsp+70h] [rbp+7h]
  const unsigned int *p_FRAMES_X_HCIPACKET; // [rsp+78h] [rbp+Fh]
  _URB *v40; // [rsp+80h] [rbp+17h]
  unsigned int v41; // [rsp+D0h] [rbp+67h]
  unsigned int v42; // [rsp+E0h] [rbp+77h]
  unsigned __int8 v43; // [rsp+E8h] [rbp+7Fh]

  Urb = a3->Urb;
  IndexPipe = a3->IndexPipe;
  UrbFrames = a3->UrbFrames;
  v7 = a1->Sco.WriteHciPacketsPerReq <= 1;
  v40 = Urb;
  v41 = UrbFrames;
  p_CallbackContext = &a2->CallbackContext;
  if ( v7 )
  {
    p_CallbackContext = &a2->CallbackContext;
  }
  else
  {
    ConnectionHandle = a2->ConnectionHandle;
    CallbackContext = a2->CallbackContext;
    v33 = 0;
    LOWORD(v33) = ConnectionHandle;
    Callback = a2->Callback;
    v34 = 0;
    BYTE8(v33) = 0;
    v35 = 0;
    if ( Callback(CallbackContext, ScoMpIndicationGetSize, (_BTH_SCO_MP_INDICATION_PARAMETERS *)&v33) < 0
      || HIDWORD(v33) < a2->WriteDataSizePerReq )
    {
      return 2147483682LL;
    }
  }
  IsoPacket = Urb->UrbIsochronousTransfer.IsoPacket;
  v14 = 0;
  v15 = 0;
  p_FRAMES_X_HCIPACKET = &a1->Sco.UsbAltSetting->FRAMES_X_HCIPACKET;
  v42 = 0;
  if ( a1->Sco.WriteHciPacketsPerReq )
  {
    v16 = p_CallbackContext;
    do
    {
      AuxiliaryBuffer = (char *)a3->AuxiliaryBuffer;
      v18 = a2->TxPacketSize - 3;
      v36 = 32LL * v14;
      v33 = 0;
      v37 = AuxiliaryBuffer;
      v34 = 0;
      v19 = &a3->TransferBuffer[v15];
      *(_QWORD *)&AuxiliaryBuffer[v36 + 16] = 0;
      v20 = *v16;
      LOWORD(v33) = a2->ConnectionHandle;
      *((_QWORD *)&v33 + 1) = v19 + 3;
      v21 = a2->Callback;
      v38 = v19;
      v43 = v18;
      v35 = 0;
      LODWORD(v34) = v18;
      *((_QWORD *)&v34 + 1) = 0;
      if ( v21(v20, ScoMpIndicationWrite, (_BTH_SCO_MP_INDICATION_PARAMETERS *)&v33) < 0 )
        break;
      v22 = v36;
      v23 = v37;
      v24 = v38;
      *(_QWORD *)&v37[v36 + 16] = *((_QWORD *)&v34 + 1);
      *(_WORD *)v24 = a2->ConnectionHandle;
      v24[2] = v43;
      *(_QWORD *)&v23[v22] = v24;
      *(_DWORD *)&v23[v22 + 8] = a2->TxPacketSize;
      *(_QWORD *)&v23[v22 + 24] = IsoPacket;
      v25 = 0;
      v26 = p_FRAMES_X_HCIPACKET;
      if ( *p_FRAMES_X_HCIPACKET )
      {
        v27 = v41;
        do
        {
          IsoPacket->Offset = v15;
          --v27;
          TxFragmentSize = a2->TxFragmentSize;
          ++v25;
          IsoPacket->Length = TxFragmentSize;
          v15 += TxFragmentSize;
          IsoPacket->Status = 0;
          ++IsoPacket;
        }
        while ( v25 < *v26 );
        v41 = v27;
        v16 = p_CallbackContext;
      }
      v14 = v42 + 1;
      v42 = v14;
    }
    while ( v14 < a1->Sco.WriteHciPacketsPerReq );
    Urb = v40;
  }
  v29 = a3->UrbFrames;
  a3->Chx = a2;
  v30 = v29 - v41;
  if ( !v30 )
    return 2147483682LL;
  Urb->UrbHeader.Function = 10;
  Urb->UrbHeader.Status = 0;
  Urb->UrbHeader.UsbdDeviceHandle = 0;
  Urb->UrbHeader.UsbdFlags = 0;
  Urb->UrbHeader.Length = 12 * v30 + 152;
  Urb->UrbSelectInterface.ConfigurationHandle = a1->Pipes[IndexPipe].PipeHandle;
  Urb->UrbPipeRequest.Reserved = 0;
  Urb->UrbControlTransfer.TransferBufferLength = v15;
  Urb->UrbSelectInterface.Interface.InterfaceHandle = a3->TransferBuffer;
  Urb->UrbSelectConfiguration.Interface.InterfaceHandle = a3->TransferMdl;
  result = 0;
  Urb->UrbControlTransfer.UrbLink = 0;
  Urb->UrbIsochronousTransfer.StartFrame = 0;
  Urb->UrbIsochronousTransfer.NumberOfPackets = v30;
  Urb->UrbIsochronousTransfer.ErrorCount = 0;
  return result;
}

```

## disassembly

```asm
0x1400090d8  mov     [rsp-8+arg_8], rbx
0x1400090dd  push    rbp
0x1400090de  push    rsi
0x1400090df  push    rdi
0x1400090e0  push    r12
0x1400090e2  push    r13
0x1400090e4  push    r14
0x1400090e6  push    r15
0x1400090e8  lea     rbp, [rsp-27h]
0x1400090ed  sub     rsp, 90h
0x1400090f4  mov     eax, [r8+60h]
0x1400090f8  mov     r15, rcx
0x1400090fb  mov     rbx, [r8+48h]
0x1400090ff  lea     rcx, [rdx+38h]
0x140009103  xor     r10d, r10d
0x140009106  mov     [rbp+57h+var_A0], eax
0x140009109  mov     eax, [r8+50h]
0x14000910d  mov     rsi, r8
0x140009110  cmp     dword ptr [r15+274h], 1
0x140009118  mov     rdi, rdx
0x14000911b  mov     [rbp+57h+var_40], rbx
0x14000911f  mov     [rbp+57h+arg_0], eax
0x140009122  mov     [rbp+57h+var_98], rcx
0x140009126  jbe     short loc_140009172
0x140009128  movzx   eax, word ptr [rdx]
0x14000912b  lea     r8, [rbp+57h+var_90]
0x14000912f  mov     rcx, [rcx]
0x140009132  xorps   xmm0, xmm0
0x140009135  movups  [rbp+57h+var_90], xmm0
0x140009139  mov     word ptr [rbp+57h+var_90], ax
0x14000913d  mov     rax, [rdx+30h]
0x140009141  lea     edx, [r10+1]
0x140009145  movups  [rbp+57h+var_80], xmm0
0x140009149  mov     byte ptr [rbp+57h+var_90+8], r10b
0x14000914d  movups  [rbp+57h+var_70], xmm0
0x140009151  call    _guard_dispatch_icall
0x140009156  xor     r10d, r10d
0x140009159  test    eax, eax
0x14000915b  js      short loc_140009168
0x14000915d  mov     eax, dword ptr [rbp+57h+var_90+0Ch]
0x140009160  cmp     eax, [rdi+90h]
0x140009166  jnb     short loc_140009176
0x140009168  mov     eax, 80000022h
0x14000916d  jmp     loc_14000931C
0x140009172  mov     [rbp+57h+var_98], rcx
0x140009176  mov     rax, [r15+478h]
0x14000917d  lea     r14, [rbx+8Ch]
0x140009184  add     rax, 0Ch
0x140009188  mov     edx, r10d
0x14000918b  mov     r12d, r10d
0x14000918e  mov     [rbp+57h+var_48], rax
0x140009192  mov     [rbp+57h+arg_10], edx
0x140009195  cmp     [r15+274h], r10d
0x14000919c  jbe     loc_140009298
0x1400091a2  mov     rbx, [rbp+57h+var_98]
0x1400091a6  mov     rcx, [rsi+80h]
0x1400091ad  xorps   xmm0, xmm0
0x1400091b0  mov     r9d, [rdi+1Ch]
0x1400091b4  mov     eax, edx
0x1400091b6  add     r9d, 0FFFFFFFDh
0x1400091ba  shl     rax, 5
0x1400091be  mov     edx, 2
0x1400091c3  mov     [rbp+57h+var_60], rax
0x1400091c7  movups  [rbp+57h+var_90], xmm0
0x1400091cb  mov     [rbp+57h+var_58], rcx
0x1400091cf  movups  [rbp+57h+var_80], xmm0
0x1400091d3  mov     r8d, r12d
0x1400091d6  add     r8, [rsi+68h]
0x1400091da  mov     [rax+rcx+10h], r10
0x1400091df  movzx   eax, word ptr [rdi]
0x1400091e2  mov     rcx, [rbx]
0x1400091e5  mov     word ptr [rbp+57h+var_90], ax
0x1400091e9  lea     rax, [r8+3]
0x1400091ed  mov     qword ptr [rbp+57h+var_90+8], rax
0x1400091f1  mov     rax, [rdi+30h]
0x1400091f5  mov     [rbp+57h+var_50], r8
0x1400091f9  lea     r8, [rbp+57h+var_90]
0x1400091fd  mov     [rbp+57h+arg_18], r9d
0x140009201  movups  [rbp+57h+var_70], xmm0
0x140009205  mov     dword ptr [rbp+57h+var_80], r9d
0x140009209  mov     qword ptr [rbp+57h+var_80+8], r10
0x14000920d  call    _guard_dispatch_icall
0x140009212  xor     r10d, r10d
0x140009215  test    eax, eax
0x140009217  js      short loc_140009294
0x140009219  mov     rcx, [rbp+57h+var_60]
0x14000921d  mov     rdx, [rbp+57h+var_58]
0x140009221  mov     rax, qword ptr [rbp+57h+var_80+8]
0x140009225  mov     r8, [rbp+57h+var_50]
0x140009229  mov     [rcx+rdx+10h], rax
0x14000922e  movzx   eax, word ptr [rdi]
0x140009231  mov     [r8], ax
0x140009235  mov     eax, [rbp+57h+arg_18]
0x140009238  mov     [r8+2], al
0x14000923c  mov     [rcx+rdx], r8
0x140009240  mov     eax, [rdi+1Ch]
0x140009243  mov     [rcx+rdx+8], eax
0x140009247  mov     [rcx+rdx+18h], r14
0x14000924c  mov     edx, r10d
0x14000924f  mov     rcx, [rbp+57h+var_48]
0x140009253  cmp     [rcx], r10d
0x140009256  jbe     short loc_14000927F
0x140009258  mov     ebx, [rbp+57h+arg_0]
0x14000925b  mov     [r14], r12d
0x14000925e  dec     ebx
0x140009260  mov     eax, [rdi+24h]
0x140009263  inc     edx
0x140009265  mov     [r14+4], eax
0x140009269  add     r12d, eax
0x14000926c  mov     [r14+8], r10d
0x140009270  add     r14, 0Ch
0x140009274  cmp     edx, [rcx]
0x140009276  jb      short loc_14000925B
0x140009278  mov     [rbp+57h+arg_0], ebx
0x14000927b  mov     rbx, [rbp+57h+var_98]
0x14000927f  mov     edx, [rbp+57h+arg_10]
0x140009282  inc     edx
0x140009284  mov     [rbp+57h+arg_10], edx
0x140009287  cmp     edx, [r15+274h]
0x14000928e  jb      loc_1400091A6
0x140009294  mov     rbx, [rbp+57h+var_40]
0x140009298  mov     edx, [rsi+50h]
0x14000929b  mov     [rsi+90h], rdi
0x1400092a2  sub     edx, [rbp+57h+arg_0]
0x1400092a5  jz      loc_140009168
0x1400092ab  movzx   eax, dx
0x1400092ae  mov     word ptr [rbx+2], 0Ah
0x1400092b4  add     ax, ax
0x1400092b7  mov     [rbx+4], r10d
0x1400092bb  mov     [rbx+8], r10
0x1400092bf  mov     [rbx+10h], r10d
0x1400092c3  lea     ecx, [rax+rdx]
0x1400092c6  mov     eax, 98h
0x1400092cb  shl     cx, 2
0x1400092cf  add     cx, ax
0x1400092d2  movsxd  rax, [rbp+57h+var_A0]
0x1400092d6  add     rax, 5
0x1400092da  mov     [rbx], cx
0x1400092dd  lea     rax, [rax+rax*2]
0x1400092e1  mov     rcx, [r15+rax*8]
0x1400092e5  mov     [rbx+18h], rcx
0x1400092e9  mov     [rbx+20h], r10d
0x1400092ed  mov     [rbx+24h], r12d
0x1400092f1  mov     rax, [rsi+68h]
0x1400092f5  mov     [rbx+28h], rax
0x1400092f9  mov     rax, [rsi+70h]
0x1400092fd  mov     [rbx+30h], rax
0x140009301  mov     eax, r10d
0x140009304  mov     [rbx+38h], r10
0x140009308  mov     [rbx+80h], r10d
0x14000930f  mov     [rbx+84h], edx
0x140009315  mov     [rbx+88h], r10d
0x14000931c  mov     rbx, [rsp+0C0h+arg_8]
0x140009324  add     rsp, 90h
0x14000932b  pop     r15
0x14000932d  pop     r14
0x14000932f  pop     r13
0x140009331  pop     r12
0x140009333  pop     rdi
0x140009334  pop     rsi
0x140009335  pop     rbp
0x140009336  retn
```
