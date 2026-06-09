# BthUsb_ScoWriteUrbDone(_DEVICE_EXTENSION *,_SCO_USB_TRANSFER_CTX *)

- ea: `0x140009a90`
- end: `0x140009d7c`
- name: `?BthUsb_ScoWriteUrbDone@@YAJPEAU_DEVICE_EXTENSION@@PEAU_SCO_USB_TRANSFER_CTX@@@Z`
- size: `748`
- prototype: `__int64 __fastcall(struct _DEVICE_EXTENSION *, struct _SCO_USB_TRANSFER_CTX *)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1400017d4`
- `0x140005be8`
- `0x140006580`
- `0x140006700`
- `0x1400094f8`
- `0x140009800`
- `0x140009a90`
- `0x14000d85c`
- `0x14000de00`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140009b72`
- `ntoskrnl!KeReleaseSpinLock` at `0x140009b72`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140009b52`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140009b52`

## string_xrefs

- `0x140009cfa`: `onecore\drivers\wdm\bluetooth\drivers\bthusb\scousbwrite.cpp`

## pseudocode

```c
__int64 __fastcall BthUsb_ScoWriteUrbDone(struct _DEVICE_EXTENSION *a1, struct _SCO_USB_TRANSFER_CTX *a2)
{
  _URB *Urb; // rbx
  struct _SCO_USB_TRANSFER_CTX *v3; // rbp
  _SCO_USB_CHANNEL *Chx; // r13
  enum _BTH_PIPE_TYPE IndexPipe; // esi
  _IRP *Irp; // r15
  unsigned int TransferBufferLength; // edi
  unsigned int v9; // ebx
  unsigned __int16 Id; // di
  KIRQL v11; // al
  int Status; // eax
  _IRP *v13; // r13
  unsigned int v14; // edi
  _SCO_USB_CHANNEL *i; // r12
  char *AuxiliaryBuffer; // rsi
  __int64 v17; // rbx
  int v18; // r8d
  int v19; // ecx
  unsigned int FRAMES_X_HCIPACKET; // edx
  __int64 v21; // rax
  int v22; // r9d
  void *CallbackContext; // rcx
  int (__fastcall *Callback)(void *, _BTH_SCO_MP_INDICATION_CODE, _BTH_SCO_MP_INDICATION_PARAMETERS *); // rax
  int v25; // edx
  int v26; // r8d
  unsigned __int16 ConnectionHandle; // [rsp+60h] [rbp-68h] BYREF
  int v29; // [rsp+62h] [rbp-66h]
  __int16 v30; // [rsp+66h] [rbp-62h]
  __int64 v31; // [rsp+68h] [rbp-60h]
  int v32; // [rsp+70h] [rbp-58h]
  int v33; // [rsp+74h] [rbp-54h]
  __int64 v34; // [rsp+78h] [rbp-50h]
  int v35; // [rsp+80h] [rbp-48h]
  int v36; // [rsp+84h] [rbp-44h]
  __int64 v37; // [rsp+88h] [rbp-40h]
  unsigned int StartFrame; // [rsp+D0h] [rbp+8h]
  struct _SCO_USB_CHANNEL *v39; // [rsp+D8h] [rbp+10h]

  Urb = a2->Urb;
  v3 = a2;
  Chx = a2->Chx;
  IndexPipe = a2->IndexPipe;
  Irp = a2->Irp;
  TransferBufferLength = Urb->UrbControlTransfer.TransferBufferLength;
  StartFrame = Urb->UrbIsochronousTransfer.StartFrame;
  v39 = Chx;
  LOBYTE(a2) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  WPP_RECORDER_AND_TRACE_SF_LLL(
    WPP_GLOBAL_Control->AttachedDevice,
    (_DWORD)a2,
    Urb->UrbIsochronousTransfer.StartFrame,
    WPP_GLOBAL_Control->DeviceExtension);
  if ( BthUsb_ScoUrbError(v3, IndexPipe) || !TransferBufferLength )
  {
    if ( Irp->IoStatus.Status >= 0 )
    {
      Status = Urb->UrbHeader.Status;
      Irp->IoStatus.Status = Status;
      if ( Status >= 0 )
        Irp->IoStatus.Status = -1073741823;
    }
  }
  else
  {
    v9 = Urb->UrbIsochronousTransfer.StartFrame;
    Id = Chx->WritePipeObj.Id;
    v11 = KeAcquireSpinLockRaiseToDpc(&a1->Sco.WriteLock);
    a1->Sco.WriteLastFrame = v9;
    a1->Sco.WriteLastPipeId = Id;
    KeReleaseSpinLock(&a1->Sco.WriteLock, v11);
  }
  v13 = v3->Irp;
  v14 = 0;
  for ( i = v3->Chx; v14 < a1->Sco.WriteHciPacketsPerReq; ++v14 )
  {
    AuxiliaryBuffer = (char *)v3->AuxiliaryBuffer;
    v17 = 32LL * v14;
    if ( *(_QWORD *)&AuxiliaryBuffer[v17] )
    {
      v18 = v13->IoStatus.Status;
      if ( v18 >= 0 )
      {
        v19 = 0;
        FRAMES_X_HCIPACKET = a1->Sco.UsbAltSetting->FRAMES_X_HCIPACKET;
        v21 = *(_QWORD *)&AuxiliaryBuffer[v17 + 24];
        if ( FRAMES_X_HCIPACKET )
        {
          while ( 1 )
          {
            v22 = *(_DWORD *)(v21 + 8);
            if ( v22 < 0 )
              break;
            v21 += 12;
            if ( ++v19 >= FRAMES_X_HCIPACKET )
              goto LABEL_23;
          }
          LOBYTE(FRAMES_X_HCIPACKET) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
                                    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
          WPP_RECORDER_AND_TRACE_SF_D(
            WPP_GLOBAL_Control->AttachedDevice,
            FRAMES_X_HCIPACKET,
            v18,
            WPP_GLOBAL_Control->DeviceExtension,
            2,
            4,
            30,
            (__int64)WPP_89eaa7be148f36a90e353489c15db76f_Traceguids,
            v22);
          v18 = -1073741823;
        }
      }
LABEL_23:
      CallbackContext = i->CallbackContext;
      v30 = 0;
      v33 = 0;
      v36 = 0;
      ConnectionHandle = i->ConnectionHandle;
      v31 = *(_QWORD *)&AuxiliaryBuffer[v17 + 16];
      v34 = *(_QWORD *)&AuxiliaryBuffer[v17];
      v35 = *(_DWORD *)&AuxiliaryBuffer[v17 + 8];
      Callback = i->Callback;
      v32 = v18;
      v29 = 0;
      v37 = 0;
      Callback(CallbackContext, ScoMpIndicationWriteComplete, (_BTH_SCO_MP_INDICATION_PARAMETERS *)&ConnectionHandle);
    }
  }
  if ( Irp->IoStatus.Status == -1073741810 )
    BthUsb_ScoWriteStop(a1);
  else
    BthUsb_ScoWriteData(a1, v39, 0);
  RefObj_ReleaseEx(&v3->RefObj, v3, 1045, "onecore\\drivers\\wdm\\bluetooth\\drivers\\bthusb\\scousbwrite.cpp");
  LOBYTE(v25) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  LOBYTE(v26) = 1;
  WPP_RECORDER_AND_TRACE_SF_L(
    WPP_GLOBAL_Control->AttachedDevice,
    v25,
    v26,
    WPP_GLOBAL_Control->DeviceExtension,
    4,
    5,
    27,
    (__int64)WPP_5fbab361c58e305795b7101c701f7776_Traceguids,
    StartFrame);
  return 0;
}

```

## disassembly

```asm
0x140009a90  mov     [rsp+arg_10], rbx
0x140009a95  push    rbp
0x140009a96  push    rsi
0x140009a97  push    rdi
0x140009a98  push    r12
0x140009a9a  push    r13
0x140009a9c  push    r14
0x140009a9e  push    r15
0x140009aa0  sub     rsp, 90h
0x140009aa7  mov     rbx, [rdx+48h]
0x140009aab  mov     rbp, rdx
0x140009aae  mov     r13, [rdx+90h]
0x140009ab5  mov     r14, rcx
0x140009ab8  mov     esi, [rdx+60h]
0x140009abb  mov     r15, [rdx+40h]
0x140009abf  mov     r8d, [rbx+80h]
0x140009ac6  mov     edi, [rbx+24h]
0x140009ac9  mov     [rsp+0C8h+arg_0], r8d
0x140009ad1  mov     [rsp+0C8h+arg_8], r13
0x140009ad9  mov     rcx, cs:WPP_GLOBAL_Control
0x140009ae0  mov     eax, [rcx+2Ch]
0x140009ae3  test    al, 10h
0x140009ae5  jz      short loc_140009AF1
0x140009ae7  cmp     byte ptr [rcx+29h], 4
0x140009aeb  jb      short loc_140009AF1
0x140009aed  mov     dl, 1
0x140009aef  jmp     short loc_140009AF3
0x140009af1  xor     dl, dl
0x140009af3  mov     eax, [rbp+78h]
0x140009af6  mov     r9, [rcx+40h]
0x140009afa  mov     rcx, [rcx+18h]
0x140009afe  mov     [rsp+0C8h+var_78], eax
0x140009b02  lea     rax, WPP_5fbab361c58e305795b7101c701f7776_Traceguids
0x140009b09  mov     [rsp+0C8h+var_80], edi
0x140009b0d  mov     [rsp+0C8h+var_88], r8d
0x140009b12  mov     [rsp+0C8h+var_90], rax
0x140009b17  mov     [rsp+0C8h+var_98], 1Ah
0x140009b1e  mov     [rsp+0C8h+var_A0], 5
0x140009b26  call    WPP_RECORDER_AND_TRACE_SF_LLL
0x140009b2b  mov     edx, esi; enum _BTH_PIPE_TYPE
0x140009b2d  mov     rcx, rbp; struct _SCO_USB_TRANSFER_CTX *
0x140009b30  call    ?BthUsb_ScoUrbError@@YAEPEAU_SCO_USB_TRANSFER_CTX@@W4_BTH_PIPE_TYPE@@@Z; BthUsb_ScoUrbError(_SCO_USB_TRANSFER_CTX *,_BTH_PIPE_TYPE)
0x140009b35  test    al, al
0x140009b37  jnz     short loc_140009B80
0x140009b39  test    edi, edi
0x140009b3b  jz      short loc_140009B80
0x140009b3d  mov     ebx, [rbx+80h]
0x140009b43  lea     rsi, [r14+260h]
0x140009b4a  movzx   edi, word ptr [r13+64h]
0x140009b4f  mov     rcx, rsi; SpinLock
0x140009b52  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140009b59  nop     dword ptr [rax+rax+00h]
0x140009b5e  mov     rcx, rsi; SpinLock
0x140009b61  mov     [r14+268h], ebx
0x140009b68  mov     dl, al; NewIrql
0x140009b6a  mov     [r14+26Ch], di
0x140009b72  call    cs:__imp_KeReleaseSpinLock
0x140009b79  nop     dword ptr [rax+rax+00h]
0x140009b7e  jmp     short loc_140009B9A
0x140009b80  cmp     dword ptr [r15+30h], 0
0x140009b85  jl      short loc_140009B9A
0x140009b87  mov     eax, [rbx+4]
0x140009b8a  mov     [r15+30h], eax
0x140009b8e  test    eax, eax
0x140009b90  js      short loc_140009B9A
0x140009b92  mov     dword ptr [r15+30h], 0C0000001h
0x140009b9a  mov     r13, [rbp+40h]
0x140009b9e  xor     edi, edi
0x140009ba0  mov     r12, [rbp+90h]
0x140009ba7  cmp     [r14+274h], edi
0x140009bae  jbe     loc_140009CCC
0x140009bb4  mov     rsi, [rbp+80h]
0x140009bbb  mov     ebx, edi
0x140009bbd  shl     rbx, 5
0x140009bc1  cmp     qword ptr [rbx+rsi], 0
0x140009bc6  jz      loc_140009CBD
0x140009bcc  mov     r8d, [r13+30h]
0x140009bd0  test    r8d, r8d
0x140009bd3  js      short loc_140009C51
0x140009bd5  mov     rax, [r14+478h]
0x140009bdc  xor     ecx, ecx
0x140009bde  mov     edx, [rax+0Ch]
0x140009be1  mov     rax, [rbx+rsi+18h]
0x140009be6  test    edx, edx
0x140009be8  jz      short loc_140009C51
0x140009bea  mov     r9d, [rax+8]
0x140009bee  test    r9d, r9d
0x140009bf1  js      short loc_140009BFF
0x140009bf3  add     rax, 0Ch
0x140009bf7  inc     ecx
0x140009bf9  cmp     ecx, edx
0x140009bfb  jb      short loc_140009BEA
0x140009bfd  jmp     short loc_140009C51
0x140009bff  mov     rcx, cs:WPP_GLOBAL_Control
0x140009c06  mov     eax, [rcx+2Ch]
0x140009c09  test    al, 8
0x140009c0b  jz      short loc_140009C17
0x140009c0d  cmp     byte ptr [rcx+29h], 2
0x140009c11  jb      short loc_140009C17
0x140009c13  mov     dl, 1
0x140009c15  jmp     short loc_140009C19
0x140009c17  xor     dl, dl
0x140009c19  mov     [rsp+0C8h+var_88], r9d
0x140009c1e  lea     rax, WPP_89eaa7be148f36a90e353489c15db76f_Traceguids
0x140009c25  mov     r9, [rcx+40h]
0x140009c29  mov     rcx, [rcx+18h]
0x140009c2d  mov     [rsp+0C8h+var_90], rax
0x140009c32  mov     [rsp+0C8h+var_98], 1Eh
0x140009c39  mov     [rsp+0C8h+var_A0], 4
0x140009c41  mov     [rsp+0C8h+var_A8], 2
0x140009c46  call    WPP_RECORDER_AND_TRACE_SF_D
0x140009c4b  mov     r8d, 0C0000001h
0x140009c51  mov     rcx, [r12+38h]
0x140009c56  xor     eax, eax
0x140009c58  mov     [rsp+0C8h+var_62], ax
0x140009c5d  mov     edx, 3
0x140009c62  mov     [rsp+0C8h+var_54], eax
0x140009c66  mov     [rsp+0C8h+var_44], eax
0x140009c6d  movzx   eax, word ptr [r12]
0x140009c72  mov     [rsp+0C8h+var_68], ax
0x140009c77  mov     rax, [rbx+rsi+10h]
0x140009c7c  mov     [rsp+0C8h+var_60], rax
0x140009c81  mov     rax, [rbx+rsi]
0x140009c85  mov     [rsp+0C8h+var_50], rax
0x140009c8a  mov     eax, [rbx+rsi+8]
0x140009c8e  mov     [rsp+0C8h+var_48], eax
0x140009c95  mov     rax, [r12+30h]
0x140009c9a  mov     [rsp+0C8h+var_58], r8d
0x140009c9f  lea     r8, [rsp+0C8h+var_68]
0x140009ca4  mov     [rsp+0C8h+var_66], 0
0x140009cac  mov     [rsp+0C8h+var_40], 0
0x140009cb8  call    _guard_dispatch_icall
0x140009cbd  inc     edi
0x140009cbf  cmp     edi, [r14+274h]
0x140009cc6  jb      loc_140009BB4
0x140009ccc  cmp     dword ptr [r15+30h], 0C000000Eh
0x140009cd4  mov     rcx, r14; struct _DEVICE_EXTENSION *
0x140009cd7  jnz     short loc_140009CE0
0x140009cd9  call    ?BthUsb_ScoWriteStop@@YAXPEAU_DEVICE_EXTENSION@@@Z; BthUsb_ScoWriteStop(_DEVICE_EXTENSION *)
0x140009cde  jmp     short loc_140009CF0
0x140009ce0  mov     rdx, [rsp+0C8h+arg_8]; struct _SCO_USB_CHANNEL *
0x140009ce8  xor     r8d, r8d; unsigned __int8
0x140009ceb  call    ?BthUsb_ScoWriteData@@YAJPEAU_DEVICE_EXTENSION@@PEAU_SCO_USB_CHANNEL@@E@Z; BthUsb_ScoWriteData(_DEVICE_EXTENSION *,_SCO_USB_CHANNEL *,uchar)
0x140009cf0  lea     rcx, [rbp+8]
0x140009cf4  mov     r8d, 415h
0x140009cfa  lea     r9, aOnecoreDrivers_0; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x140009d01  mov     rdx, rbp
0x140009d04  call    RefObj_ReleaseEx
0x140009d09  mov     rcx, cs:WPP_GLOBAL_Control
0x140009d10  mov     eax, [rcx+2Ch]
0x140009d13  test    al, 10h
0x140009d15  jz      short loc_140009D21
0x140009d17  cmp     byte ptr [rcx+29h], 4
0x140009d1b  jb      short loc_140009D21
0x140009d1d  mov     dl, 1
0x140009d1f  jmp     short loc_140009D23
0x140009d21  xor     dl, dl
0x140009d23  mov     eax, [rsp+0C8h+arg_0]
0x140009d2a  mov     r8b, 1
0x140009d2d  mov     r9, [rcx+40h]
0x140009d31  mov     rcx, [rcx+18h]
0x140009d35  mov     [rsp+0C8h+var_88], eax
0x140009d39  lea     rax, WPP_5fbab361c58e305795b7101c701f7776_Traceguids
0x140009d40  mov     [rsp+0C8h+var_90], rax
0x140009d45  mov     [rsp+0C8h+var_98], 1Bh
0x140009d4c  mov     [rsp+0C8h+var_A0], 5
0x140009d54  mov     [rsp+0C8h+var_A8], 4
0x140009d59  call    WPP_RECORDER_AND_TRACE_SF_L
0x140009d5e  mov     rbx, [rsp+0C8h+arg_10]
0x140009d66  xor     eax, eax
0x140009d68  add     rsp, 90h
0x140009d6f  pop     r15
0x140009d71  pop     r14
0x140009d73  pop     r13
0x140009d75  pop     r12
0x140009d77  pop     rdi
0x140009d78  pop     rsi
0x140009d79  pop     rbp
0x140009d7a  retn
```
