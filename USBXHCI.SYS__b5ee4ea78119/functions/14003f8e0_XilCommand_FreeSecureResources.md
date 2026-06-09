# XilCommand_FreeSecureResources

- ea: `0x14003f8e0`
- end: `0x14003f9ef`
- name: `XilCommand_FreeSecureResources`
- size: `271`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14003f87c`

## callees

- `0x14001ad0c`
- `0x14001bb78`
- `0x14001c178`
- `0x14003f8e0`
- `0x140059970`

## string_xrefs

- `0x14003f9c6`: `onecore\drivers\wdm\usb\usb3\usbxhci\sys\xilcommand.c`
- `0x14003f9cf`: `IOCTL succeeded but CommandFreeResources failed in VTL-1 failed`

## pseudocode

```c
__int64 __fastcall XilCommand_FreeSecureResources(__int64 a1)
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
  LODWORD(v10) = 14;
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
          18,
          (__int64)WPP_db21d8d52d393cb96c062fdb7e607301_Traceguids,
          v7);
      }
      return Debug_FreAssertMsg(
               "IOCTL succeeded but CommandFreeResources failed in VTL-1 failed",
               0,
               "onecore\\drivers\\wdm\\usb\\usb3\\usbxhci\\sys\\xilcommand.c",
               430);
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
               17,
               (__int64)WPP_db21d8d52d393cb96c062fdb7e607301_Traceguids,
               result);
    }
  }
  return result;
}

```

## disassembly

```asm
0x14003f8e0  mov     r11, rsp
0x14003f8e3  push    rbx
0x14003f8e4  sub     rsp, 70h
0x14003f8e8  mov     rax, cs:__security_cookie
0x14003f8ef  xor     rax, rsp
0x14003f8f2  mov     [rsp+78h+var_18], rax
0x14003f8f7  xor     eax, eax
0x14003f8f9  mov     dword ptr [rsp+78h+var_58], 4
0x14003f901  mov     [rsp+78h+var_48], eax
0x14003f905  lea     r9, [r11-48h]
0x14003f909  mov     rdx, rcx
0x14003f90c  xorps   xmm0, xmm0
0x14003f90f  movups  [rsp+78h+var_40], xmm0
0x14003f914  mov     r8d, 28h ; '('
0x14003f91a  movups  [rsp+78h+var_30], xmm0
0x14003f91f  mov     [r11-20h], rax
0x14003f923  mov     rax, [rcx+8]
0x14003f927  mov     rbx, [rax+8]
0x14003f92b  mov     rax, [rdx+20h]
0x14003f92f  lea     rdx, [r11-40h]
0x14003f933  mov     rcx, [rbx+70h]
0x14003f937  mov     [r11-28h], rax
0x14003f93b  mov     dword ptr [rsp+78h+var_20], 0Eh
0x14003f943  call    SecureChannel_SendRequestSynchronously
0x14003f948  test    eax, eax
0x14003f94a  jns     short loc_14003F983
0x14003f94c  lea     rdx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14003f953  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x14003f95a  jz      short loc_14003F9DB
0x14003f95c  mov     rcx, [rbx+48h]
0x14003f960  mov     r9d, 11h
0x14003f966  mov     [rsp+78h+var_50], eax
0x14003f96a  mov     dl, 2
0x14003f96c  lea     rax, WPP_db21d8d52d393cb96c062fdb7e607301_Traceguids
0x14003f973  mov     [rsp+78h+var_58], rax
0x14003f978  lea     r8d, [r9-0Ah]
0x14003f97c  call    WPP_RECORDER_SF_d
0x14003f981  jmp     short loc_14003F9DB
0x14003f983  mov     eax, [rsp+78h+var_48]
0x14003f987  test    eax, eax
0x14003f989  jns     short loc_14003F9DB
0x14003f98b  lea     rdx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14003f992  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x14003f999  jz      short loc_14003F9C0
0x14003f99b  mov     rcx, [rbx+48h]
0x14003f99f  mov     r9d, 12h
0x14003f9a5  mov     [rsp+78h+var_50], eax
0x14003f9a9  mov     dl, 2
0x14003f9ab  lea     rax, WPP_db21d8d52d393cb96c062fdb7e607301_Traceguids
0x14003f9b2  mov     [rsp+78h+var_58], rax
0x14003f9b7  lea     r8d, [r9-0Bh]
0x14003f9bb  call    WPP_RECORDER_SF_d
0x14003f9c0  mov     r9d, 1AEh
0x14003f9c6  lea     r8, aOnecoreDrivers_5; "onecore\\drivers\\wdm\\usb\\usb3\\usbxh"...
0x14003f9cd  xor     edx, edx
0x14003f9cf  lea     rcx, aIoctlSucceeded_3; "IOCTL succeeded but CommandFreeResource"...
0x14003f9d6  call    Debug_FreAssertMsg
0x14003f9db  mov     rcx, [rsp+78h+var_18]
0x14003f9e0  xor     rcx, rsp; StackCookie
0x14003f9e3  call    __security_check_cookie
0x14003f9e8  add     rsp, 70h
0x14003f9ec  pop     rbx
0x14003f9ed  retn
```
