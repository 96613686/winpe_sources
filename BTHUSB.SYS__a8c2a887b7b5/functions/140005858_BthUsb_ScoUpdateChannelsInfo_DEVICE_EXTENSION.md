# BthUsb_ScoUpdateChannelsInfo(_DEVICE_EXTENSION *)

- ea: `0x140005858`
- end: `0x1400058b4`
- name: `?BthUsb_ScoUpdateChannelsInfo@@YAXPEAU_DEVICE_EXTENSION@@@Z`
- size: `92`
- prototype: `void __fastcall(struct _DEVICE_EXTENSION *)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400030e0`
- `0x140005180`

## callees

- `0x1400047a4`
- `0x140005858`

## pseudocode

```c
void __fastcall BthUsb_ScoUpdateChannelsInfo(struct _DEVICE_EXTENSION *a1)
{
  unsigned __int16 NumChannels; // si
  __int64 i; // rbx
  struct _SCO_USB_CHANNEL *v4; // rdx

  NumChannels = a1->Sco.NumChannels;
  for ( i = 0; i != 3; ++i )
  {
    v4 = &a1->Sco.Channel[i];
    if ( v4->ConnectionHandle != 0xFFFF )
      BthUsb_ScoComputeChannelInfo(a1, v4, NumChannels);
  }
}

```

## disassembly

```asm
0x140005858  mov     [rsp+arg_0], rbx
0x14000585d  mov     [rsp+arg_8], rsi
0x140005862  push    rdi
0x140005863  sub     rsp, 20h
0x140005867  movzx   esi, word ptr [rcx+2ACh]
0x14000586e  mov     rdi, rcx
0x140005871  xor     ebx, ebx
0x140005873  imul    rdx, rbx, 98h
0x14000587a  mov     eax, 0FFFFh
0x14000587f  add     rdx, 2B0h
0x140005886  add     rdx, rdi; struct _SCO_USB_CHANNEL *
0x140005889  cmp     ax, [rdx]
0x14000588c  jz      short loc_14000589A
0x14000588e  movzx   r8d, si; unsigned __int16
0x140005892  mov     rcx, rdi; struct _DEVICE_EXTENSION *
0x140005895  call    ?BthUsb_ScoComputeChannelInfo@@YAXPEAU_DEVICE_EXTENSION@@PEAU_SCO_USB_CHANNEL@@G@Z; BthUsb_ScoComputeChannelInfo(_DEVICE_EXTENSION *,_SCO_USB_CHANNEL *,ushort)
0x14000589a  inc     rbx
0x14000589d  cmp     rbx, 3
0x1400058a1  jnz     short loc_140005873
0x1400058a3  mov     rbx, [rsp+28h+arg_0]
0x1400058a8  mov     rsi, [rsp+28h+arg_8]
0x1400058ad  add     rsp, 20h
0x1400058b1  pop     rdi
0x1400058b2  retn
```
