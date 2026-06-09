# MbxDevice::MbxDevice(WDFDEVICE__ *,_MBB_DEVICE_CONFIG const &,_MBX_PRIVATE_GLOBALS *)

- ea: `0x140009568`
- end: `0x14000968e`
- name: `??0MbxDevice@@AEAA@PEAUWDFDEVICE__@@AEBU_MBB_DEVICE_CONFIG@@PEAU_MBX_PRIVATE_GLOBALS@@@Z`
- size: `294`
- prototype: `MbxDevice *(MbxDevice *__hidden this, struct WDFDEVICE__ *, const struct _MBB_DEVICE_CONFIG *, struct _MBX_PRIVATE_GLOBALS *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14000e900`

## callees

- `0x140048040`
- `0x140048340`

## pseudocode

```c
MbxDevice *__fastcall MbxDevice::MbxDevice(
        MbxDevice *this,
        struct WDFDEVICE__ *a2,
        const struct _MBB_DEVICE_CONFIG *a3,
        struct _MBX_PRIVATE_GLOBALS *a4)
{
  *((_QWORD *)this + 1) = a2;
  *(_QWORD *)this = &MbxDevice::`vftable';
  *((_BYTE *)this + 16) = 1;
  *(_OWORD *)((char *)this + 24) = 0;
  *(_OWORD *)((char *)this + 40) = 0;
  *((_QWORD *)this + 7) = 0;
  memset((char *)this + 64, 0, 0x5D0u);
  *((_DWORD *)this + 388) = 0;
  *((_WORD *)this + 778) = 0;
  *((_BYTE *)this + 1558) = 0;
  *(_OWORD *)((char *)this + 1559) = 0;
  *(_DWORD *)((char *)this + 1575) = 0;
  *((_QWORD *)this + 199) = 0;
  *((_QWORD *)this + 200) = 0;
  *((_BYTE *)this + 1608) = 0;
  *((_QWORD *)this + 202) = 0;
  *((_BYTE *)this + 1640) = 0;
  *((_QWORD *)this + 198) = a4;
  *(_QWORD *)((char *)this + 1644) = 0;
  *((_DWORD *)this + 413) = 0;
  *((_QWORD *)this + 207) = 0;
  *((_QWORD *)this + 208) = 0;
  *(_OWORD *)((char *)this + 1672) = 0;
  *(_OWORD *)((char *)this + 1688) = 0;
  *(_OWORD *)((char *)this + 1704) = 0;
  *((_DWORD *)this + 430) = 0;
  *((_QWORD *)this + 216) = 0;
  *((_QWORD *)this + 217) = 0;
  *((_QWORD *)this + 218) = 0;
  *((_QWORD *)this + 219) = 0;
  *((_QWORD *)this + 220) = 0;
  memmove((char *)this + 24, a3, a3->Size);
  *((_QWORD *)this + 204) = (char *)this + 1624;
  *((_QWORD *)this + 203) = (char *)this + 1624;
  return this;
}

```

## disassembly

```asm
0x140009568  push    rbx
0x14000956a  push    rsi
0x14000956b  push    rdi
0x14000956c  push    r14
0x14000956e  sub     rsp, 28h
0x140009572  mov     [rcx+8], rdx
0x140009576  lea     rax, ??_7MbxDevice@@6B@; const MbxDevice::`vftable'
0x14000957d  mov     [rcx], rax
0x140009580  xorps   xmm0, xmm0
0x140009583  mov     byte ptr [rcx+10h], 1
0x140009587  xor     eax, eax
0x140009589  movups  xmmword ptr [rcx+18h], xmm0
0x14000958d  mov     rsi, r8
0x140009590  mov     r14, rcx
0x140009593  movups  xmmword ptr [rcx+28h], xmm0
0x140009597  mov     [rcx+38h], rax
0x14000959b  xor     edx, edx; Val
0x14000959d  add     rcx, 40h ; '@'; void *
0x1400095a1  mov     r8d, 5D0h; Size
0x1400095a7  mov     rbx, r9
0x1400095aa  call    memset
0x1400095af  xor     ecx, ecx
0x1400095b1  xorps   xmm0, xmm0
0x1400095b4  mov     [r14+610h], ecx
0x1400095bb  xor     eax, eax
0x1400095bd  mov     [r14+614h], cx
0x1400095c5  mov     rdx, rsi; Src
0x1400095c8  mov     [r14+616h], cl
0x1400095cf  movups  xmmword ptr [r14+617h], xmm0
0x1400095d7  mov     [r14+627h], eax
0x1400095de  mov     [r14+638h], rcx
0x1400095e5  mov     [r14+640h], rcx
0x1400095ec  mov     [r14+648h], cl
0x1400095f3  mov     [r14+650h], rcx
0x1400095fa  mov     [r14+668h], cl
0x140009601  mov     [r14+630h], rbx
0x140009608  mov     [r14+66Ch], rax
0x14000960f  mov     [r14+674h], eax
0x140009616  mov     [r14+678h], rcx
0x14000961d  mov     [r14+680h], rcx
0x140009624  movups  xmmword ptr [r14+688h], xmm0
0x14000962c  movups  xmmword ptr [r14+698h], xmm0
0x140009634  movups  xmmword ptr [r14+6A8h], xmm0
0x14000963c  mov     [r14+6B8h], ecx
0x140009643  mov     [r14+6C0h], rcx
0x14000964a  mov     [r14+6C8h], rcx
0x140009651  mov     [r14+6D0h], rcx
0x140009658  mov     [r14+6D8h], rax
0x14000965f  mov     [r14+6E0h], rcx
0x140009666  lea     rcx, [r14+18h]; void *
0x14000966a  mov     r8d, [rsi]; Size
0x14000966d  call    memmove
0x140009672  lea     rax, [r14+658h]
0x140009679  mov     [rax+8], rax
0x14000967d  mov     [rax], rax
0x140009680  mov     rax, r14
0x140009683  add     rsp, 28h
0x140009687  pop     r14
0x140009689  pop     rdi
0x14000968a  pop     rsi
0x14000968b  pop     rbx
0x14000968c  retn
```
