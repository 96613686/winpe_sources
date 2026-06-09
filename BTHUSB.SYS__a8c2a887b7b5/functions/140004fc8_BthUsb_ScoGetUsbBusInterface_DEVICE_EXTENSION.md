# BthUsb_ScoGetUsbBusInterface(_DEVICE_EXTENSION *)

- ea: `0x140004fc8`
- end: `0x140005093`
- name: `?BthUsb_ScoGetUsbBusInterface@@YAJPEAU_DEVICE_EXTENSION@@@Z`
- size: `203`
- prototype: `__int64 __fastcall(struct _DEVICE_EXTENSION *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1400030e0`

## callees

- `0x14000175c`
- `0x140004fc8`
- `0x14000ac54`
- `0x14000e1c0`

## pseudocode

```c
__int64 __fastcall BthUsb_ScoGetUsbBusInterface(struct _DEVICE_EXTENSION *a1)
{
  int v2; // edx
  int UsbBusInterface; // ebx
  __int128 v4; // xmm1
  __int128 v5; // xmm0
  __int128 v6; // xmm1
  _OWORD v8[4]; // [rsp+40h] [rbp-48h] BYREF

  memset(v8, 0, sizeof(v8));
  UsbBusInterface = BthUsb_GetUsbBusInterface(a1, v8, 0x40u, 0);
  if ( UsbBusInterface >= 0 )
  {
    LOBYTE(v2) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
    WPP_RECORDER_AND_TRACE_SF_(
      WPP_GLOBAL_Control->AttachedDevice,
      v2,
      (_DWORD)WPP_GLOBAL_Control,
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      4,
      31,
      (__int64)WPP_89eaa7be148f36a90e353489c15db76f_Traceguids);
    v4 = v8[1];
    *(_OWORD *)&a1->Sco.UsbBusInterface.Size = v8[0];
    v5 = v8[2];
    *(_OWORD *)&a1->Sco.UsbBusInterface.InterfaceReference = v4;
    v6 = v8[3];
    *(_OWORD *)&a1->Sco.UsbBusInterface.GetUSBDIVersion = v5;
    *(_OWORD *)&a1->Sco.UsbBusInterface.SubmitIsoOutUrb = v6;
  }
  return (unsigned int)UsbBusInterface;
}

```

## disassembly

```asm
0x140004fc8  mov     [rsp+arg_0], rbx
0x140004fcd  push    rdi
0x140004fce  sub     rsp, 80h
0x140004fd5  mov     rdi, rcx
0x140004fd8  mov     ebx, 40h ; '@'
0x140004fdd  mov     r8d, ebx; Size
0x140004fe0  lea     rcx, [rsp+88h+var_48]; void *
0x140004fe5  xor     edx, edx; Val
0x140004fe7  call    memset
0x140004fec  xor     r9d, r9d; unsigned __int16
0x140004fef  lea     rdx, [rsp+88h+var_48]; void *
0x140004ff4  mov     r8d, ebx; unsigned __int16
0x140004ff7  mov     rcx, rdi; struct _DEVICE_EXTENSION *
0x140004ffa  call    ?BthUsb_GetUsbBusInterface@@YAJPEAU_DEVICE_EXTENSION@@PEAXGG@Z; BthUsb_GetUsbBusInterface(_DEVICE_EXTENSION *,void *,ushort,ushort)
0x140004fff  mov     ebx, eax
0x140005001  test    eax, eax
0x140005003  js      short loc_14000507F
0x140005005  mov     r8, cs:WPP_GLOBAL_Control
0x14000500c  mov     ecx, [r8+2Ch]
0x140005010  test    cl, 8
0x140005013  jz      short loc_140005020
0x140005015  cmp     byte ptr [r8+29h], 4
0x14000501a  jb      short loc_140005020
0x14000501c  mov     dl, 1
0x14000501e  jmp     short loc_140005022
0x140005020  xor     dl, dl
0x140005022  mov     r9, [r8+40h]
0x140005026  lea     rax, WPP_89eaa7be148f36a90e353489c15db76f_Traceguids
0x14000502d  mov     rcx, [r8+18h]
0x140005031  mov     [rsp+88h+var_50], rax
0x140005036  mov     [rsp+88h+var_58], 1Fh
0x14000503d  mov     [rsp+88h+var_60], 4
0x140005045  mov     [rsp+88h+var_68], 4
0x14000504a  call    WPP_RECORDER_AND_TRACE_SF_
0x14000504f  movaps  xmm0, [rsp+88h+var_48]
0x140005054  movaps  xmm1, [rsp+88h+var_38]
0x140005059  movups  xmmword ptr [rdi+0F0h], xmm0
0x140005060  movaps  xmm0, [rsp+88h+var_28]
0x140005065  movups  xmmword ptr [rdi+100h], xmm1
0x14000506c  movaps  xmm1, [rsp+88h+var_18]
0x140005071  movups  xmmword ptr [rdi+110h], xmm0
0x140005078  movups  xmmword ptr [rdi+120h], xmm1
0x14000507f  mov     eax, ebx
0x140005081  mov     rbx, [rsp+88h+arg_0]
0x140005089  add     rsp, 80h
0x140005090  pop     rdi
0x140005091  retn
```
