# BthUsb_ScoComputeChannelInfo(_DEVICE_EXTENSION *,_SCO_USB_CHANNEL *,ushort)

- ea: `0x1400047a4`
- end: `0x140004835`
- name: `?BthUsb_ScoComputeChannelInfo@@YAXPEAU_DEVICE_EXTENSION@@PEAU_SCO_USB_CHANNEL@@G@Z`
- size: `145`
- prototype: `void __fastcall(struct _DEVICE_EXTENSION *, struct _SCO_USB_CHANNEL *, unsigned __int16)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400030e0`
- `0x140005858`

## callees

- `0x1400047a4`

## pseudocode

```c
void __fastcall BthUsb_ScoComputeChannelInfo(
        struct _DEVICE_EXTENSION *a1,
        struct _SCO_USB_CHANNEL *a2,
        unsigned __int16 a3)
{
  int v4; // edi
  unsigned int TxBandwidth; // ecx
  unsigned int v6; // r11d
  unsigned int v7; // r10d
  const ScoUsbAltSetting **p_UsbAltSetting; // rbx
  unsigned int v10; // r8d
  unsigned int v11; // ecx
  unsigned int RxBandwidth; // edx

  v4 = a3;
  TxBandwidth = a2->TxBandwidth;
  v6 = 0;
  v7 = 0;
  if ( TxBandwidth )
  {
    p_UsbAltSetting = &a1->Sco.UsbAltSetting;
    v10 = a3 * (TxBandwidth / 0x3E8) + 1;
    v11 = (*p_UsbAltSetting)->FRAMES_X_HCIPACKET * v10;
  }
  else
  {
    v10 = 0;
    v11 = 0;
    p_UsbAltSetting = &a1->Sco.UsbAltSetting;
  }
  RxBandwidth = a2->RxBandwidth;
  if ( RxBandwidth )
  {
    v6 = v4 * (RxBandwidth / 0x3E8) + 1;
    v7 = (*p_UsbAltSetting)->FRAMES_X_HCIPACKET * v6;
  }
  a2->TxPacketSize = v11;
  a2->RxPacketSize = v7;
  a2->TxFragmentSize = v10;
  a2->RxFragmentSize = v6;
}

```

## disassembly

```asm
0x1400047a4  mov     [rsp+arg_0], rbx
0x1400047a9  mov     [rsp+arg_8], rdi
0x1400047ae  mov     rbx, rcx
0x1400047b1  movzx   edi, r8w
0x1400047b5  mov     ecx, [rdx+14h]
0x1400047b8  xor     r11d, r11d
0x1400047bb  xor     r10d, r10d
0x1400047be  mov     r9, rdx
0x1400047c1  test    ecx, ecx
0x1400047c3  jz      short loc_1400047E9
0x1400047c5  mov     eax, 10624DD3h
0x1400047ca  add     rbx, 478h
0x1400047d1  mul     ecx
0x1400047d3  mov     rax, [rbx]
0x1400047d6  shr     edx, 6
0x1400047d9  imul    edx, edi
0x1400047dc  lea     r8d, [rdx+1]
0x1400047e0  mov     ecx, r8d
0x1400047e3  imul    ecx, [rax+0Ch]
0x1400047e7  jmp     short loc_1400047F5
0x1400047e9  xor     r8d, r8d
0x1400047ec  xor     ecx, ecx
0x1400047ee  add     rbx, 478h
0x1400047f5  mov     edx, [r9+18h]
0x1400047f9  test    edx, edx
0x1400047fb  jz      short loc_140004819
0x1400047fd  mov     eax, 10624DD3h
0x140004802  mul     edx
0x140004804  mov     rax, [rbx]
0x140004807  shr     edx, 6
0x14000480a  imul    edx, edi
0x14000480d  lea     r11d, [rdx+1]
0x140004811  mov     r10d, r11d
0x140004814  imul    r10d, [rax+0Ch]
0x140004819  mov     rbx, [rsp+arg_0]
0x14000481e  mov     rdi, [rsp+arg_8]
0x140004823  mov     [r9+1Ch], ecx
0x140004827  mov     [r9+20h], r10d
0x14000482b  mov     [r9+24h], r8d
0x14000482f  mov     [r9+28h], r11d
0x140004833  retn
```
