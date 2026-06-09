# XilEndpoint_CreateSecureObject

- ea: `0x140047040`
- end: `0x1400471af`
- name: `XilEndpoint_CreateSecureObject`
- size: `367`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140034774`

## callees

- `0x14001ad0c`
- `0x14001bb78`
- `0x14001c178`
- `0x140047040`
- `0x140059970`

## string_xrefs

- `0x1400470b6`: `Unexpected code path hit`
- `0x14004717f`: `IOCTL succeeded but EndpointCreate failed in VTL-1 failed`

## pseudocode

```c
__int64 __fastcall XilEndpoint_CreateSecureObject(_QWORD *a1)
{
  _QWORD *v2; // rax
  __int64 v3; // rsi
  __int64 v4; // rbx
  __int64 v5; // rax
  __int64 v6; // rax
  int v7; // edx
  int v8; // ebx
  __int64 v10; // [rsp+30h] [rbp-19h] BYREF
  __int64 v11; // [rsp+38h] [rbp-11h]
  _OWORD v12[2]; // [rsp+40h] [rbp-9h] BYREF
  __int128 v13; // [rsp+60h] [rbp+17h]
  __int64 v14; // [rsp+70h] [rbp+27h]

  LODWORD(v11) = 0;
  v10 = 0;
  v14 = 0;
  v2 = (_QWORD *)a1[4];
  v13 = 0;
  memset(v12, 0, sizeof(v12));
  v3 = *v2;
  v4 = *(_QWORD *)(*v2 + 112LL);
  LODWORD(v13) = 33;
  v5 = v2[2];
  if ( *(_BYTE *)(v5 + 665) )
  {
    v6 = *(_QWORD *)(v5 + 616);
  }
  else
  {
    Debug_FreAssertMsg(
      "Unexpected code path hit",
      0,
      "onecore\\drivers\\wdm\\usb\\usb3\\usbxhci\\sys\\xilusbdevice.c",
      376);
    v6 = 0;
  }
  *((_QWORD *)&v13 + 1) = v6;
  LODWORD(v14) = *(_DWORD *)(a1[4] + 152LL);
  v8 = SecureChannel_SendRequestSynchronously(v4, v12, 56, &v10, 16);
  if ( v8 >= 0 )
  {
    v8 = v10;
    if ( (int)v10 >= 0 )
    {
      *a1 = v11;
    }
    else
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v7) = 2;
        WPP_RECORDER_SF_d(
          *(_QWORD *)(v3 + 72),
          v7,
          13,
          11,
          (__int64)WPP_0fad196ed6f839af1910845e6c92cab5_Traceguids,
          v10);
      }
      Debug_FreAssertMsg(
        "IOCTL succeeded but EndpointCreate failed in VTL-1 failed",
        0,
        "onecore\\drivers\\wdm\\usb\\usb3\\usbxhci\\sys\\xilendpoint.c",
        255);
    }
  }
  else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v7) = 2;
    WPP_RECORDER_SF_d(*(_QWORD *)(v3 + 72), v7, 13, 10, (__int64)WPP_0fad196ed6f839af1910845e6c92cab5_Traceguids, v8);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140047040  push    rbp
0x140047042  push    rbx
0x140047043  push    rsi
0x140047044  push    rdi
0x140047045  lea     rbp, [rsp-3Fh]
0x14004704a  sub     rsp, 88h
0x140047051  mov     rax, cs:__security_cookie
0x140047058  xor     rax, rsp
0x14004705b  mov     [rbp+57h+var_28], rax
0x14004705f  xor     eax, eax
0x140047061  xorps   xmm0, xmm0
0x140047064  mov     qword ptr [rbp+57h+var_6C], rax
0x140047068  mov     rdi, rcx
0x14004706b  mov     [rbp-19h], rax
0x14004706f  mov     [rbp+57h+var_30], rax
0x140047073  mov     rax, [rcx+20h]
0x140047077  movups  [rbp+57h+var_40], xmm0
0x14004707b  movups  [rbp+57h+var_60], xmm0
0x14004707f  movups  [rbp+57h+var_50], xmm0
0x140047083  mov     rsi, [rax]
0x140047086  mov     rbx, [rsi+70h]
0x14004708a  mov     dword ptr [rbp+57h+var_40], 21h ; '!'
0x140047091  mov     rax, [rax+10h]
0x140047095  cmp     byte ptr [rax+299h], 0
0x14004709c  jz      short loc_1400470A7
0x14004709e  mov     rax, [rax+268h]
0x1400470a5  jmp     short loc_1400470C4
0x1400470a7  mov     r9d, 178h
0x1400470ad  lea     r8, aOnecoreDrivers_10; "onecore\\drivers\\wdm\\usb\\usb3\\usbxh"...
0x1400470b4  xor     edx, edx
0x1400470b6  lea     rcx, aUnexpectedCode; "Unexpected code path hit"
0x1400470bd  call    Debug_FreAssertMsg
0x1400470c2  xor     eax, eax
0x1400470c4  mov     qword ptr [rbp+57h+var_40+8], rax
0x1400470c8  lea     r9, [rbp+57h+var_70]
0x1400470cc  mov     rax, [rdi+20h]
0x1400470d0  mov     r8d, 38h ; '8'
0x1400470d6  mov     rcx, rbx
0x1400470d9  mov     dword ptr [rsp+0A0h+var_80], 10h
0x1400470e1  mov     edx, [rax+98h]
0x1400470e7  mov     dword ptr [rbp+57h+var_30], edx
0x1400470ea  lea     rdx, [rbp+57h+var_60]
0x1400470ee  call    SecureChannel_SendRequestSynchronously
0x1400470f3  mov     ebx, eax
0x1400470f5  test    eax, eax
0x1400470f7  jns     short loc_140047134
0x1400470f9  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140047100  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140047107  jz      loc_140047194
0x14004710d  mov     rcx, [rsi+48h]
0x140047111  lea     rax, WPP_0fad196ed6f839af1910845e6c92cab5_Traceguids
0x140047118  mov     r9d, 0Ah
0x14004711e  mov     [rsp+0A0h+var_78], ebx
0x140047122  mov     dl, 2
0x140047124  mov     [rsp+0A0h+var_80], rax
0x140047129  lea     r8d, [r9+3]
0x14004712d  call    WPP_RECORDER_SF_d
0x140047132  jmp     short loc_140047194
0x140047134  mov     ebx, [rbp+57h+var_70]
0x140047137  test    ebx, ebx
0x140047139  jns     short loc_14004718D
0x14004713b  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140047142  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140047149  jz      short loc_140047170
0x14004714b  mov     rcx, [rsi+48h]
0x14004714f  lea     rax, WPP_0fad196ed6f839af1910845e6c92cab5_Traceguids
0x140047156  mov     r9d, 0Bh
0x14004715c  mov     [rsp+0A0h+var_78], ebx
0x140047160  mov     dl, 2
0x140047162  mov     [rsp+0A0h+var_80], rax
0x140047167  lea     r8d, [r9+2]
0x14004716b  call    WPP_RECORDER_SF_d
0x140047170  mov     r9d, 0FFh
0x140047176  lea     r8, aOnecoreDrivers_18; "onecore\\drivers\\wdm\\usb\\usb3\\usbxh"...
0x14004717d  xor     edx, edx
0x14004717f  lea     rcx, aIoctlSucceeded; "IOCTL succeeded but EndpointCreate fail"...
0x140047186  call    Debug_FreAssertMsg
0x14004718b  jmp     short loc_140047194
0x14004718d  mov     rax, qword ptr [rbp+57h+var_6C+4]
0x140047191  mov     [rdi], rax
0x140047194  mov     eax, ebx
0x140047196  mov     rcx, [rbp+57h+var_28]
0x14004719a  xor     rcx, rsp; StackCookie
0x14004719d  call    __security_check_cookie
0x1400471a2  add     rsp, 88h
0x1400471a9  pop     rdi
0x1400471aa  pop     rsi
0x1400471ab  pop     rbx
0x1400471ac  pop     rbp
0x1400471ad  retn
```
