# XilCommand_SendAbortRingCommandRequest

- ea: `0x14003faa0`
- end: `0x14003fbaf`
- name: `XilCommand_SendAbortRingCommandRequest`
- size: `271`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14003f4b4`

## callees

- `0x14001ad0c`
- `0x14001bb78`
- `0x14001c178`
- `0x14003faa0`
- `0x140059970`

## string_xrefs

- `0x14003fb86`: `onecore\drivers\wdm\usb\usb3\usbxhci\sys\xilcommand.c`
- `0x14003fb8f`: `IOCTL succeeded but CommandAbortRing failed in VTL-1 failed`

## pseudocode

```c
__int64 __fastcall XilCommand_SendAbortRingCommandRequest(__int64 a1)
{
  __int64 v1; // rbx
  __int64 v2; // rax
  __int64 v3; // rcx
  __int64 result; // rax
  _UNKNOWN **v5; // rdx
  _UNKNOWN **v6; // rdx
  int v7; // [rsp+30h] [rbp-48h] BYREF
  __int128 v8; // [rsp+38h] [rbp-40h] BYREF
  __int128 v9; // [rsp+48h] [rbp-30h]
  __int64 v10; // [rsp+58h] [rbp-20h]

  v7 = 0;
  v8 = 0;
  v9 = 0;
  v10 = 0;
  v1 = *(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL);
  v2 = *(_QWORD *)(a1 + 32);
  v3 = *(_QWORD *)(v1 + 112);
  *((_QWORD *)&v9 + 1) = v2;
  LODWORD(v10) = 16;
  result = SecureChannel_SendRequestSynchronously(v3, &v8, 40, &v7, 4);
  if ( (int)result >= 0 )
  {
    result = (unsigned int)v7;
    if ( v7 < 0 )
    {
      v6 = &WPP_RECORDER_INITIALIZED;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v6) = 2;
        WPP_RECORDER_SF_d(
          *(_QWORD *)(v1 + 72),
          (_DWORD)v6,
          7,
          26,
          (__int64)WPP_db21d8d52d393cb96c062fdb7e607301_Traceguids,
          v7);
      }
      return Debug_FreAssertMsg(
               "IOCTL succeeded but CommandAbortRing failed in VTL-1 failed",
               0,
               "onecore\\drivers\\wdm\\usb\\usb3\\usbxhci\\sys\\xilcommand.c",
               791);
    }
  }
  else
  {
    v5 = &WPP_RECORDER_INITIALIZED;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v5) = 2;
      return WPP_RECORDER_SF_d(
               *(_QWORD *)(v1 + 72),
               (_DWORD)v5,
               7,
               25,
               (__int64)WPP_db21d8d52d393cb96c062fdb7e607301_Traceguids,
               result);
    }
  }
  return result;
}

```

## disassembly

```asm
0x14003faa0  mov     r11, rsp
0x14003faa3  push    rbx
0x14003faa4  sub     rsp, 70h
0x14003faa8  mov     rax, cs:__security_cookie
0x14003faaf  xor     rax, rsp
0x14003fab2  mov     [rsp+78h+var_18], rax
0x14003fab7  xor     eax, eax
0x14003fab9  mov     dword ptr [rsp+78h+var_58], 4
0x14003fac1  mov     [rsp+78h+var_48], eax
0x14003fac5  lea     r9, [r11-48h]
0x14003fac9  mov     rdx, rcx
0x14003facc  xorps   xmm0, xmm0
0x14003facf  movups  [rsp+78h+var_40], xmm0
0x14003fad4  mov     r8d, 28h ; '('
0x14003fada  movups  [rsp+78h+var_30], xmm0
0x14003fadf  mov     [r11-20h], rax
0x14003fae3  mov     rax, [rcx+8]
0x14003fae7  mov     rbx, [rax+8]
0x14003faeb  mov     rax, [rdx+20h]
0x14003faef  lea     rdx, [r11-40h]
0x14003faf3  mov     rcx, [rbx+70h]
0x14003faf7  mov     [r11-28h], rax
0x14003fafb  mov     dword ptr [rsp+78h+var_20], 10h
0x14003fb03  call    SecureChannel_SendRequestSynchronously
0x14003fb08  test    eax, eax
0x14003fb0a  jns     short loc_14003FB43
0x14003fb0c  lea     rdx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14003fb13  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x14003fb1a  jz      short loc_14003FB9B
0x14003fb1c  mov     rcx, [rbx+48h]
0x14003fb20  mov     r9d, 19h
0x14003fb26  mov     [rsp+78h+var_50], eax
0x14003fb2a  mov     dl, 2
0x14003fb2c  lea     rax, WPP_db21d8d52d393cb96c062fdb7e607301_Traceguids
0x14003fb33  mov     [rsp+78h+var_58], rax
0x14003fb38  lea     r8d, [r9-12h]
0x14003fb3c  call    WPP_RECORDER_SF_d
0x14003fb41  jmp     short loc_14003FB9B
0x14003fb43  mov     eax, [rsp+78h+var_48]
0x14003fb47  test    eax, eax
0x14003fb49  jns     short loc_14003FB9B
0x14003fb4b  lea     rdx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14003fb52  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x14003fb59  jz      short loc_14003FB80
0x14003fb5b  mov     rcx, [rbx+48h]
0x14003fb5f  mov     r9d, 1Ah
0x14003fb65  mov     [rsp+78h+var_50], eax
0x14003fb69  mov     dl, 2
0x14003fb6b  lea     rax, WPP_db21d8d52d393cb96c062fdb7e607301_Traceguids
0x14003fb72  mov     [rsp+78h+var_58], rax
0x14003fb77  lea     r8d, [r9-13h]
0x14003fb7b  call    WPP_RECORDER_SF_d
0x14003fb80  mov     r9d, 317h
0x14003fb86  lea     r8, aOnecoreDrivers_5; "onecore\\drivers\\wdm\\usb\\usb3\\usbxh"...
0x14003fb8d  xor     edx, edx
0x14003fb8f  lea     rcx, aIoctlSucceeded_1; "IOCTL succeeded but CommandAbortRing fa"...
0x14003fb96  call    Debug_FreAssertMsg
0x14003fb9b  mov     rcx, [rsp+78h+var_18]
0x14003fba0  xor     rcx, rsp; StackCookie
0x14003fba3  call    __security_check_cookie
0x14003fba8  add     rsp, 70h
0x14003fbac  pop     rbx
0x14003fbad  retn
```
