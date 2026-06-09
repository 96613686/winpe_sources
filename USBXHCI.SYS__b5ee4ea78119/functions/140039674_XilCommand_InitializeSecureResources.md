# XilCommand_InitializeSecureResources

- ea: `0x140039674`
- end: `0x140039783`
- name: `XilCommand_InitializeSecureResources`
- size: `271`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14001bac8`

## callees

- `0x14001ad0c`
- `0x14001bb78`
- `0x14001c178`
- `0x140039674`
- `0x140059970`

## string_xrefs

- `0x14003975a`: `onecore\drivers\wdm\usb\usb3\usbxhci\sys\xilcommand.c`
- `0x140039763`: `IOCTL succeeded but CommandAllocateResources failed in VTL-1 failed`

## pseudocode

```c
__int64 __fastcall XilCommand_InitializeSecureResources(__int64 a1)
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
  LODWORD(v10) = 15;
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
          16,
          (__int64)WPP_db21d8d52d393cb96c062fdb7e607301_Traceguids,
          v7);
      }
      return Debug_FreAssertMsg(
               "IOCTL succeeded but CommandAllocateResources failed in VTL-1 failed",
               0,
               "onecore\\drivers\\wdm\\usb\\usb3\\usbxhci\\sys\\xilcommand.c",
               331);
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
               15,
               (__int64)WPP_db21d8d52d393cb96c062fdb7e607301_Traceguids,
               result);
    }
  }
  return result;
}

```

## disassembly

```asm
0x140039674  mov     r11, rsp
0x140039677  push    rbx
0x140039678  sub     rsp, 70h
0x14003967c  mov     rax, cs:__security_cookie
0x140039683  xor     rax, rsp
0x140039686  mov     [rsp+78h+var_18], rax
0x14003968b  xor     eax, eax
0x14003968d  mov     dword ptr [rsp+78h+var_58], 4
0x140039695  mov     [rsp+78h+var_48], eax
0x140039699  lea     r9, [r11-48h]
0x14003969d  mov     rdx, rcx
0x1400396a0  xorps   xmm0, xmm0
0x1400396a3  movups  [rsp+78h+var_40], xmm0
0x1400396a8  mov     r8d, 28h ; '('
0x1400396ae  movups  [rsp+78h+var_30], xmm0
0x1400396b3  mov     [r11-20h], rax
0x1400396b7  mov     rax, [rcx+8]
0x1400396bb  mov     rbx, [rax+8]
0x1400396bf  mov     rax, [rdx+20h]
0x1400396c3  lea     rdx, [r11-40h]
0x1400396c7  mov     rcx, [rbx+70h]
0x1400396cb  mov     [r11-28h], rax
0x1400396cf  mov     dword ptr [rsp+78h+var_20], 0Fh
0x1400396d7  call    SecureChannel_SendRequestSynchronously
0x1400396dc  test    eax, eax
0x1400396de  jns     short loc_140039717
0x1400396e0  lea     rdx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400396e7  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x1400396ee  jz      short loc_14003976F
0x1400396f0  mov     rcx, [rbx+48h]
0x1400396f4  mov     r9d, 0Fh
0x1400396fa  mov     [rsp+78h+var_50], eax
0x1400396fe  mov     dl, 2
0x140039700  lea     rax, WPP_db21d8d52d393cb96c062fdb7e607301_Traceguids
0x140039707  mov     [rsp+78h+var_58], rax
0x14003970c  lea     r8d, [r9-8]
0x140039710  call    WPP_RECORDER_SF_d
0x140039715  jmp     short loc_14003976F
0x140039717  mov     eax, [rsp+78h+var_48]
0x14003971b  test    eax, eax
0x14003971d  jns     short loc_14003976F
0x14003971f  lea     rdx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140039726  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x14003972d  jz      short loc_140039754
0x14003972f  mov     rcx, [rbx+48h]
0x140039733  mov     r9d, 10h
0x140039739  mov     [rsp+78h+var_50], eax
0x14003973d  mov     dl, 2
0x14003973f  lea     rax, WPP_db21d8d52d393cb96c062fdb7e607301_Traceguids
0x140039746  mov     [rsp+78h+var_58], rax
0x14003974b  lea     r8d, [r9-9]
0x14003974f  call    WPP_RECORDER_SF_d
0x140039754  mov     r9d, 14Bh
0x14003975a  lea     r8, aOnecoreDrivers_5; "onecore\\drivers\\wdm\\usb\\usb3\\usbxh"...
0x140039761  xor     edx, edx
0x140039763  lea     rcx, aIoctlSucceeded_5; "IOCTL succeeded but CommandAllocateReso"...
0x14003976a  call    Debug_FreAssertMsg
0x14003976f  mov     rcx, [rsp+78h+var_18]
0x140039774  xor     rcx, rsp; StackCookie
0x140039777  call    __security_check_cookie
0x14003977c  add     rsp, 70h
0x140039780  pop     rbx
0x140039781  retn
```
