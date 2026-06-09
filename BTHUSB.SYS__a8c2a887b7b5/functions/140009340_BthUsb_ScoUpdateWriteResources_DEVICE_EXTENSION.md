# BthUsb_ScoUpdateWriteResources(_DEVICE_EXTENSION *)

- ea: `0x140009340`
- end: `0x140009442`
- name: `?BthUsb_ScoUpdateWriteResources@@YAXPEAU_DEVICE_EXTENSION@@@Z`
- size: `258`
- prototype: `void __fastcall(struct _DEVICE_EXTENSION *)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callers

- `0x1400030e0`
- `0x140005180`

## callees

- `0x14000509c`
- `0x140009340`

## pseudocode

```c
void __fastcall BthUsb_ScoUpdateWriteResources(struct _DEVICE_EXTENSION *a1)
{
  int NumChannels; // r8d
  __int64 v2; // rdi
  unsigned __int16 v4; // bp
  const ScoUsbAltSetting **p_UsbAltSetting; // rsi
  unsigned int v6; // eax
  const ScoUsbAltSetting *UsbAltSetting; // rcx
  __int64 v8; // rcx

  NumChannels = a1->Sco.NumChannels;
  v2 = 0;
  v4 = 0;
  if ( NumChannels == 1 || (unsigned int)(NumChannels - 2) < 2 )
  {
    p_UsbAltSetting = &a1->Sco.UsbAltSetting;
    UsbAltSetting = a1->Sco.UsbAltSetting;
    a1->Sco.WriteFramesPerReq = UsbAltSetting->FRAMES_X_HCIPACKET;
    a1->Sco.WriteHciPacketsPerReq = 1;
    v6 = UsbAltSetting->MAX_PENDING_WRITE_REQS_SPAN / (UsbAltSetting->WRITE_USEC_X_HCIPACKET * NumChannels);
  }
  else
  {
    *(_QWORD *)&a1->Sco.WriteFramesPerReq = 0;
    p_UsbAltSetting = &a1->Sco.UsbAltSetting;
    v6 = 0;
  }
  a1->Sco.WriteMaxPendingReq = v6;
  do
  {
    v8 = v2;
    if ( a1->Sco.Channel[v2].ConnectionHandle != 0xFFFF )
    {
      a1->Sco.Channel[v8].WriteDataSizePerReq = a1->Sco.WriteHciPacketsPerReq * (a1->Sco.Channel[v8].TxPacketSize - 3);
      BthUsb_ScoPipeObjInit(
        (struct _DEVICE_EXTENSION *)(v8 * 152),
        &a1->Sco.Channel[v8].WritePipeObj,
        WRITE_SCO_PIPE,
        v4++,
        (int (*)(struct _DEVICE_EXTENSION *, struct _SCO_USB_TRANSFER_CTX *))BthUsb_ScoWriteUrbSend,
        (int (*)(struct _DEVICE_EXTENSION *, struct _SCO_USB_TRANSFER_CTX *))BthUsb_ScoWriteUrbDone,
        (unsigned int (*)(struct _DEVICE_EXTENSION *, struct _SCO_USB_TRANSFER_CTX *, unsigned __int16, unsigned int))BthUsb_ScoWriteAlignFrame,
        (unsigned int (*)(struct _DEVICE_EXTENSION *, struct _SCO_USB_TRANSFER_CTX *, unsigned __int16, unsigned int))(*p_UsbAltSetting)->WriteGetNextFrame);
    }
    ++v2;
  }
  while ( v2 != 3 );
}

```

## disassembly

```asm
0x140009340  push    rbx
0x140009342  push    rbp
0x140009343  push    rsi
0x140009344  push    rdi
0x140009345  push    r14
0x140009347  sub     rsp, 40h
0x14000934b  movzx   r8d, word ptr [rcx+2ACh]
0x140009353  xor     edi, edi
0x140009355  mov     rbx, rcx
0x140009358  mov     ebp, edi
0x14000935a  mov     ecx, r8d
0x14000935d  lea     r14d, [rdi+1]
0x140009361  sub     ecx, r14d
0x140009364  jz      short loc_140009382
0x140009366  sub     ecx, r14d
0x140009369  jz      short loc_140009382
0x14000936b  cmp     ecx, r14d
0x14000936e  jz      short loc_140009382
0x140009370  mov     [rbx+270h], rdi
0x140009377  lea     rsi, [rbx+478h]
0x14000937e  mov     eax, edi
0x140009380  jmp     short loc_1400093A8
0x140009382  lea     rsi, [rbx+478h]
0x140009389  xor     edx, edx
0x14000938b  mov     rcx, [rsi]
0x14000938e  mov     eax, [rcx+0Ch]
0x140009391  mov     [rbx+270h], eax
0x140009397  mov     [rbx+274h], r14d
0x14000939e  imul    r8d, [rcx+8]
0x1400093a3  mov     eax, [rcx]
0x1400093a5  div     r8d
0x1400093a8  mov     [rbx+278h], eax
0x1400093ae  imul    rcx, rdi, 98h; struct _DEVICE_EXTENSION *
0x1400093b5  mov     eax, 0FFFFh
0x1400093ba  cmp     ax, [rcx+rbx+2B0h]
0x1400093c2  jz      short loc_140009429
0x1400093c4  mov     eax, [rcx+rbx+2CCh]
0x1400093cb  lea     rdx, [rbx+2F0h]
0x1400093d2  sub     eax, 3
0x1400093d5  add     rdx, rcx; struct _SCO_USB_PIPE_OBJ *
0x1400093d8  imul    eax, [rbx+274h]
0x1400093df  movzx   r9d, bp; unsigned __int16
0x1400093e3  mov     r8d, 4; enum _BTH_PIPE_TYPE
0x1400093e9  mov     [rcx+rbx+340h], eax
0x1400093f0  mov     rax, [rsi]
0x1400093f3  mov     rax, [rax+18h]
0x1400093f7  mov     [rsp+68h+var_30], rax; unsigned int (*)(struct _DEVICE_EXTENSION *, struct _SCO_USB_TRANSFER_CTX *, unsigned __int16, unsigned int)
0x1400093fc  lea     rax, ?BthUsb_ScoWriteAlignFrame@@YAKPEAU_DEVICE_EXTENSION@@PEAU_SCO_USB_TRANSFER_CTX@@GK@Z; BthUsb_ScoWriteAlignFrame(_DEVICE_EXTENSION *,_SCO_USB_TRANSFER_CTX *,ushort,ulong)
0x140009403  mov     [rsp+68h+var_38], rax; unsigned int (*)(struct _DEVICE_EXTENSION *, struct _SCO_USB_TRANSFER_CTX *, unsigned __int16, unsigned int)
0x140009408  lea     rax, ?BthUsb_ScoWriteUrbDone@@YAJPEAU_DEVICE_EXTENSION@@PEAU_SCO_USB_TRANSFER_CTX@@@Z; BthUsb_ScoWriteUrbDone(_DEVICE_EXTENSION *,_SCO_USB_TRANSFER_CTX *)
0x14000940f  mov     [rsp+68h+var_40], rax; int (*)(struct _DEVICE_EXTENSION *, struct _SCO_USB_TRANSFER_CTX *)
0x140009414  lea     rax, ?BthUsb_ScoWriteUrbSend@@YAJPEAU_DEVICE_EXTENSION@@PEAU_SCO_USB_TRANSFER_CTX@@@Z; BthUsb_ScoWriteUrbSend(_DEVICE_EXTENSION *,_SCO_USB_TRANSFER_CTX *)
0x14000941b  mov     [rsp+68h+var_48], rax; int (*)(struct _DEVICE_EXTENSION *, struct _SCO_USB_TRANSFER_CTX *)
0x140009420  call    ?BthUsb_ScoPipeObjInit@@YAXPEAU_DEVICE_EXTENSION@@PEAU_SCO_USB_PIPE_OBJ@@W4_BTH_PIPE_TYPE@@GP6AJ0PEAU_SCO_USB_TRANSFER_CTX@@@Z4P6AK03GK@Z5@Z; BthUsb_ScoPipeObjInit(_DEVICE_EXTENSION *,_SCO_USB_PIPE_OBJ *,_BTH_PIPE_TYPE,ushort,long (*)(_DEVICE_EXTENSION *,_SCO_USB_TRANSFER_CTX *),long (*)(_DEVICE_EXTENSION *,_SCO_USB_TRANSFER_CTX *),ulong (*)(_DEVICE_EXTENSION *,_SCO_USB_TRANSFER_CTX *,ushort,ulong),ulong (*)(_DEVICE_EXTENSION *,_SCO_USB_TRANSFER_CTX *,ushort,ulong))
0x140009425  add     bp, r14w
0x140009429  add     rdi, r14
0x14000942c  cmp     rdi, 3
0x140009430  jnz     loc_1400093AE
0x140009436  add     rsp, 40h
0x14000943a  pop     r14
0x14000943c  pop     rdi
0x14000943d  pop     rsi
0x14000943e  pop     rbp
0x14000943f  pop     rbx
0x140009440  retn
```
