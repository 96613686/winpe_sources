# BthUsb_ScoReadUrbDone(_DEVICE_EXTENSION *,_SCO_USB_TRANSFER_CTX *)

- ea: `0x1400081b0`
- end: `0x140008515`
- name: `?BthUsb_ScoReadUrbDone@@YAJPEAU_DEVICE_EXTENSION@@PEAU_SCO_USB_TRANSFER_CTX@@@Z`
- size: `869`
- prototype: `__int64 __fastcall(struct _DEVICE_EXTENSION *, struct _SCO_USB_TRANSFER_CTX *)`
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting`

## callees

- `0x14000187c`
- `0x140005be8`
- `0x140006580`
- `0x140006700`
- `0x140006db0`
- `0x140007c5c`
- `0x140007ea0`
- `0x1400081b0`
- `0x140008918`
- `0x14000d85c`
- `0x14000de00`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14000826f`
- `ntoskrnl!KeReleaseSpinLock` at `0x140008309`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400083e8`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000826f`
- `ntoskrnl!KeReleaseSpinLock` at `0x140008309`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400083e8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000824c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400082e9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400083bb`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000824c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400082e9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400083bb`

## string_xrefs

- `0x140008486`: `onecore\drivers\wdm\bluetooth\drivers\bthusb\scousbread.cpp`
- `0x1400084a4`: `onecore\drivers\wdm\bluetooth\drivers\bthusb\scousbread.cpp`

## pseudocode

```c
__int64 __fastcall BthUsb_ScoReadUrbDone(struct _DEVICE_EXTENSION *a1, struct _SCO_USB_TRANSFER_CTX *a2, int a3)
{
  _URB *Urb; // rbp
  _SCO_USB_TRANSFER_CTX *v4; // rbx
  enum _BTH_PIPE_TYPE IndexPipe; // r13d
  unsigned int TransferBufferLength; // r14d
  unsigned int StartFrame; // r12d
  KIRQL v9; // al
  _SCO_USB_TRANSFER_CTX *PartialReadCtx; // rsi
  int v11; // edx
  int v12; // r8d
  _IRP *v13; // rbp
  _SCO_USB_TRANSFER_CTX *v14; // rbp
  KIRQL v15; // al
  int v16; // edx
  unsigned int v17; // r8d
  int v18; // edx
  int v19; // r8d
  KIRQL v20; // al
  int v21; // edx
  int v22; // r8d
  char v24; // [rsp+A0h] [rbp+8h] BYREF
  _IRP *Irp; // [rsp+A8h] [rbp+10h]

  Urb = a2->Urb;
  v4 = a2;
  IndexPipe = a2->IndexPipe;
  v24 = 0;
  TransferBufferLength = Urb->UrbControlTransfer.TransferBufferLength;
  StartFrame = Urb->UrbIsochronousTransfer.StartFrame;
  Irp = a2->Irp;
  LOBYTE(a2) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  WPP_RECORDER_AND_TRACE_SF_LLL(WPP_GLOBAL_Control->AttachedDevice, (_DWORD)a2, a3, WPP_GLOBAL_Control->DeviceExtension);
  v9 = KeAcquireSpinLockRaiseToDpc(&a1->Sco.ReadLock);
  PartialReadCtx = a1->Sco.PartialReadCtx;
  a1->Sco.PartialReadCtx = 0;
  KeReleaseSpinLock(&a1->Sco.ReadLock, v9);
  if ( BthUsb_ScoUrbError(v4, IndexPipe) )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0 || (LOBYTE(v11) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
      LOBYTE(v11) = 0;
    v13 = Irp;
    WPP_RECORDER_AND_TRACE_SF_DDd(WPP_GLOBAL_Control->AttachedDevice, v11, v12, WPP_GLOBAL_Control->DeviceExtension);
  }
  else
  {
    if ( TransferBufferLength )
    {
      v14 = 0;
      v15 = KeAcquireSpinLockRaiseToDpc(&a1->Sco.ReadLock);
      a1->Sco.ReadLastFrame = StartFrame;
      a1->Sco.ReadLastPipeId = 0;
      KeReleaseSpinLock(&a1->Sco.ReadLock, v15);
      if ( PartialReadCtx )
      {
        v17 = PartialReadCtx->Urb->UrbIsochronousTransfer.StartFrame;
        if ( StartFrame == v17 + a1->Sco.UsbAltSetting->READ_FRAMES_X_REQ )
        {
          v14 = PartialReadCtx;
        }
        else
        {
          if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
            || (LOBYTE(v16) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 4u) )
          {
            LOBYTE(v16) = 0;
          }
          WPP_RECORDER_AND_TRACE_SF_dd(
            WPP_GLOBAL_Control->AttachedDevice,
            v16,
            v17,
            WPP_GLOBAL_Control->DeviceExtension,
            4,
            5,
            26,
            (__int64)WPP_bdb2f4b08e1e350eed49ca0df045c47e_Traceguids,
            v17,
            StartFrame);
        }
      }
      a1->Sco.UsbAltSetting->ProcessReadUrb(a1, v14, v4, (unsigned __int8 *)&v24);
      if ( v24 )
      {
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
          || (LOBYTE(v18) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 4u) )
        {
          LOBYTE(v18) = 0;
        }
        WPP_RECORDER_AND_TRACE_SF_q(
          WPP_GLOBAL_Control->AttachedDevice,
          v18,
          v19,
          WPP_GLOBAL_Control->DeviceExtension,
          4,
          5,
          27,
          (__int64)WPP_bdb2f4b08e1e350eed49ca0df045c47e_Traceguids,
          (char)v4);
        v20 = KeAcquireSpinLockRaiseToDpc(&a1->Sco.ReadLock);
        if ( a1->Sco.ReadsEnabled && !a1->Sco.PartialReadCtx )
        {
          a1->Sco.PartialReadCtx = v4;
          v4 = 0;
        }
        KeReleaseSpinLock(&a1->Sco.ReadLock, v20);
      }
    }
    v13 = Irp;
  }
  if ( v13->IoStatus.Status == -1073741810 )
    BthUsb_ScoReadStop(a1);
  else
    BthUsb_ScoReadData(a1, 1u);
  if ( v4 )
    RefObj_ReleaseEx(&v4->RefObj, v4, 962, "onecore\\drivers\\wdm\\bluetooth\\drivers\\bthusb\\scousbread.cpp");
  if ( PartialReadCtx )
    RefObj_ReleaseEx(
      &PartialReadCtx->RefObj,
      PartialReadCtx,
      966,
      "onecore\\drivers\\wdm\\bluetooth\\drivers\\bthusb\\scousbread.cpp");
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0 || (LOBYTE(v21) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 4u) )
    LOBYTE(v21) = 0;
  LOBYTE(v22) = 1;
  WPP_RECORDER_AND_TRACE_SF_L(
    WPP_GLOBAL_Control->AttachedDevice,
    v21,
    v22,
    WPP_GLOBAL_Control->DeviceExtension,
    4,
    5,
    28,
    (__int64)WPP_bdb2f4b08e1e350eed49ca0df045c47e_Traceguids,
    StartFrame);
  return 0;
}

```

## disassembly

```asm
0x1400081b0  mov     rax, rsp
0x1400081b3  mov     [rax+18h], rbx
0x1400081b7  push    rbp
0x1400081b8  push    rsi
0x1400081b9  push    rdi
0x1400081ba  push    r12
0x1400081bc  push    r13
0x1400081be  push    r14
0x1400081c0  push    r15
0x1400081c2  sub     rsp, 60h
0x1400081c6  mov     rbp, [rdx+48h]
0x1400081ca  mov     rbx, rdx
0x1400081cd  mov     r13d, [rdx+60h]
0x1400081d1  mov     rdi, rcx
0x1400081d4  mov     byte ptr [rax+8], 0
0x1400081d8  mov     rax, [rdx+40h]
0x1400081dc  mov     r14d, [rbp+24h]
0x1400081e0  mov     r12d, [rbp+80h]
0x1400081e7  mov     [rsp+98h+arg_8], rax
0x1400081ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1400081f6  mov     eax, [rcx+2Ch]
0x1400081f9  test    al, 10h
0x1400081fb  jz      short loc_140008207
0x1400081fd  cmp     byte ptr [rcx+29h], 4
0x140008201  jb      short loc_140008207
0x140008203  mov     dl, 1
0x140008205  jmp     short loc_140008209
0x140008207  xor     dl, dl
0x140008209  mov     eax, [rbx+78h]
0x14000820c  mov     r9, [rcx+40h]
0x140008210  mov     rcx, [rcx+18h]
0x140008214  mov     [rsp+98h+var_48], eax
0x140008218  lea     rax, WPP_bdb2f4b08e1e350eed49ca0df045c47e_Traceguids
0x14000821f  mov     [rsp+98h+var_50], r14d
0x140008224  mov     dword ptr [rsp+98h+var_58], r12d
0x140008229  mov     [rsp+98h+var_60], rax
0x14000822e  mov     [rsp+98h+var_68], 18h
0x140008235  mov     [rsp+98h+var_70], 5
0x14000823d  call    WPP_RECORDER_AND_TRACE_SF_LLL
0x140008242  lea     r15, [rdi+248h]
0x140008249  mov     rcx, r15; SpinLock
0x14000824c  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140008253  nop     dword ptr [rax+rax+00h]
0x140008258  mov     rsi, [rdi+258h]
0x14000825f  mov     rcx, r15; SpinLock
0x140008262  mov     dl, al; NewIrql
0x140008264  mov     qword ptr [rdi+258h], 0
0x14000826f  call    cs:__imp_KeReleaseSpinLock
0x140008276  nop     dword ptr [rax+rax+00h]
0x14000827b  mov     edx, r13d; enum _BTH_PIPE_TYPE
0x14000827e  mov     rcx, rbx; struct _SCO_USB_TRANSFER_CTX *
0x140008281  call    ?BthUsb_ScoUrbError@@YAEPEAU_SCO_USB_TRANSFER_CTX@@W4_BTH_PIPE_TYPE@@@Z; BthUsb_ScoUrbError(_SCO_USB_TRANSFER_CTX *,_BTH_PIPE_TYPE)
0x140008286  xor     r13d, r13d
0x140008289  test    al, al
0x14000828b  jz      short loc_1400082DA
0x14000828d  mov     rcx, cs:WPP_GLOBAL_Control
0x140008294  mov     eax, [rcx+2Ch]
0x140008297  test    al, 10h
0x140008299  jz      short loc_1400082A3
0x14000829b  cmp     byte ptr [rcx+29h], 2
0x14000829f  mov     dl, 1
0x1400082a1  jnb     short loc_1400082A6
0x1400082a3  mov     dl, r13b
0x1400082a6  mov     eax, [rbp+4]
0x1400082a9  mov     r9, [rcx+40h]
0x1400082ad  mov     rbp, [rsp+98h+arg_8]
0x1400082b5  mov     rcx, [rcx+18h]
0x1400082b9  mov     [rsp+98h+var_48], r14d
0x1400082be  mov     [rsp+98h+var_50], eax
0x1400082c2  mov     eax, [rbp+38h]
0x1400082c5  mov     dword ptr [rsp+98h+var_58], eax
0x1400082c9  call    WPP_RECORDER_AND_TRACE_SF_DDd
0x1400082ce  lea     r14, WPP_bdb2f4b08e1e350eed49ca0df045c47e_Traceguids
0x1400082d5  jmp     loc_14000845A
0x1400082da  test    r14d, r14d
0x1400082dd  jz      loc_14000844B
0x1400082e3  mov     rcx, r15; SpinLock
0x1400082e6  mov     rbp, r13
0x1400082e9  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400082f0  nop     dword ptr [rax+rax+00h]
0x1400082f5  mov     rcx, r15; SpinLock
0x1400082f8  mov     [rdi+250h], r12d
0x1400082ff  mov     dl, al; NewIrql
0x140008301  mov     [rdi+254h], r13w
0x140008309  call    cs:__imp_KeReleaseSpinLock
0x140008310  nop     dword ptr [rax+rax+00h]
0x140008315  test    rsi, rsi
0x140008318  jz      short loc_14000833E
0x14000831a  mov     rax, [rsi+48h]
0x14000831e  mov     r8d, [rax+80h]
0x140008325  mov     rax, [rdi+478h]
0x14000832c  mov     eax, [rax+48h]
0x14000832f  add     eax, r8d
0x140008332  cmp     r12d, eax
0x140008335  jnz     loc_1400083F6
0x14000833b  mov     rbp, rsi
0x14000833e  lea     r14, WPP_bdb2f4b08e1e350eed49ca0df045c47e_Traceguids
0x140008345  mov     rax, [rdi+478h]
0x14000834c  lea     r9, [rsp+98h+arg_0]
0x140008354  mov     r8, rbx
0x140008357  mov     rdx, rbp
0x14000835a  mov     rcx, rdi
0x14000835d  mov     rax, [rax+30h]
0x140008361  call    _guard_dispatch_icall
0x140008366  cmp     [rsp+98h+arg_0], r13b
0x14000836e  jz      loc_140008452
0x140008374  mov     rcx, cs:WPP_GLOBAL_Control
0x14000837b  mov     eax, [rcx+2Ch]
0x14000837e  test    al, 10h
0x140008380  jz      short loc_14000838A
0x140008382  cmp     byte ptr [rcx+29h], 4
0x140008386  mov     dl, 1
0x140008388  jnb     short loc_14000838D
0x14000838a  mov     dl, r13b
0x14000838d  mov     r9, [rcx+40h]
0x140008391  mov     rcx, [rcx+18h]
0x140008395  mov     [rsp+98h+var_58], rbx
0x14000839a  mov     [rsp+98h+var_60], r14
0x14000839f  mov     [rsp+98h+var_68], 1Bh
0x1400083a6  mov     [rsp+98h+var_70], 5
0x1400083ae  mov     [rsp+98h+var_78], 4
0x1400083b3  call    WPP_RECORDER_AND_TRACE_SF_q
0x1400083b8  mov     rcx, r15; SpinLock
0x1400083bb  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400083c2  nop     dword ptr [rax+rax+00h]
0x1400083c7  cmp     [rdi+256h], r13b
0x1400083ce  jz      short loc_1400083E3
0x1400083d0  cmp     [rdi+258h], r13
0x1400083d7  jnz     short loc_1400083E3
0x1400083d9  mov     [rdi+258h], rbx
0x1400083e0  mov     rbx, r13
0x1400083e3  mov     dl, al; NewIrql
0x1400083e5  mov     rcx, r15; SpinLock
0x1400083e8  call    cs:__imp_KeReleaseSpinLock
0x1400083ef  nop     dword ptr [rax+rax+00h]
0x1400083f4  jmp     short loc_140008452
0x1400083f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400083fd  mov     eax, [rcx+2Ch]
0x140008400  test    al, 10h
0x140008402  jz      short loc_14000840C
0x140008404  cmp     byte ptr [rcx+29h], 4
0x140008408  mov     dl, 1
0x14000840a  jnb     short loc_14000840F
0x14000840c  mov     dl, r13b
0x14000840f  mov     r9, [rcx+40h]
0x140008413  lea     r14, WPP_bdb2f4b08e1e350eed49ca0df045c47e_Traceguids
0x14000841a  mov     rcx, [rcx+18h]
0x14000841e  mov     [rsp+98h+var_50], r12d
0x140008423  mov     dword ptr [rsp+98h+var_58], r8d
0x140008428  mov     [rsp+98h+var_60], r14
0x14000842d  mov     [rsp+98h+var_68], 1Ah
0x140008434  mov     [rsp+98h+var_70], 5
0x14000843c  mov     [rsp+98h+var_78], 4
0x140008441  call    WPP_RECORDER_AND_TRACE_SF_dd
0x140008446  jmp     loc_140008345
0x14000844b  lea     r14, WPP_bdb2f4b08e1e350eed49ca0df045c47e_Traceguids
0x140008452  mov     rbp, [rsp+98h+arg_8]
0x14000845a  cmp     dword ptr [rbp+30h], 0C000000Eh
0x140008461  mov     rcx, rdi; struct _DEVICE_EXTENSION *
0x140008464  jnz     short loc_14000846D
0x140008466  call    ?BthUsb_ScoReadStop@@YAXPEAU_DEVICE_EXTENSION@@@Z; BthUsb_ScoReadStop(_DEVICE_EXTENSION *)
0x14000846b  jmp     short loc_140008477
0x14000846d  mov     edx, 1; unsigned int
0x140008472  call    ?BthUsb_ScoReadData@@YAJPEAU_DEVICE_EXTENSION@@K@Z; BthUsb_ScoReadData(_DEVICE_EXTENSION *,ulong)
0x140008477  test    rbx, rbx
0x14000847a  jz      short loc_140008495
0x14000847c  lea     rcx, [rbx+8]
0x140008480  mov     r8d, 3C2h
0x140008486  lea     r9, aOnecoreDrivers_1; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x14000848d  mov     rdx, rbx
0x140008490  call    RefObj_ReleaseEx
0x140008495  test    rsi, rsi
0x140008498  jz      short loc_1400084B3
0x14000849a  lea     rcx, [rsi+8]
0x14000849e  mov     r8d, 3C6h
0x1400084a4  lea     r9, aOnecoreDrivers_1; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x1400084ab  mov     rdx, rsi
0x1400084ae  call    RefObj_ReleaseEx
0x1400084b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400084ba  mov     eax, [rcx+2Ch]
0x1400084bd  test    al, 10h
0x1400084bf  jz      short loc_1400084C9
0x1400084c1  cmp     byte ptr [rcx+29h], 4
0x1400084c5  mov     dl, 1
0x1400084c7  jnb     short loc_1400084CC
0x1400084c9  mov     dl, r13b
0x1400084cc  mov     r9, [rcx+40h]
0x1400084d0  mov     r8b, 1
0x1400084d3  mov     rcx, [rcx+18h]
0x1400084d7  mov     dword ptr [rsp+98h+var_58], r12d
0x1400084dc  mov     [rsp+98h+var_60], r14
0x1400084e1  mov     [rsp+98h+var_68], 1Ch
0x1400084e8  mov     [rsp+98h+var_70], 5
0x1400084f0  mov     [rsp+98h+var_78], 4
0x1400084f5  call    WPP_RECORDER_AND_TRACE_SF_L
0x1400084fa  mov     rbx, [rsp+98h+arg_10]
0x140008502  xor     eax, eax
0x140008504  add     rsp, 60h
0x140008508  pop     r15
0x14000850a  pop     r14
0x14000850c  pop     r13
0x14000850e  pop     r12
0x140008510  pop     rdi
0x140008511  pop     rsi
0x140008512  pop     rbp
0x140008513  retn
```
