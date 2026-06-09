# XilCommand_CreateSecureObject

- ea: `0x14003f744`
- end: `0x14003f875`
- name: `XilCommand_CreateSecureObject`
- size: `305`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14003f6e0`

## callees

- `0x14001ad0c`
- `0x14001bb78`
- `0x14001c178`
- `0x14003f744`
- `0x140059970`

## string_xrefs

- `0x14003f83b`: `onecore\drivers\wdm\usb\usb3\usbxhci\sys\xilcommand.c`
- `0x14003f844`: `IOCTL succeeded but CommandCreate failed in VTL-1 failed`

## pseudocode

```c
__int64 __fastcall XilCommand_CreateSecureObject(__int64 a1)
{
  __int64 v1; // rax
  _QWORD *v3; // rdi
  __int64 v4; // rcx
  int v5; // edx
  int v6; // ebx
  __int64 v8; // [rsp+30h] [rbp-19h] BYREF
  __int64 v9; // [rsp+38h] [rbp-11h]
  _OWORD v10[2]; // [rsp+40h] [rbp-9h] BYREF
  __int128 v11; // [rsp+60h] [rbp+17h]

  LODWORD(v9) = 0;
  v8 = 0;
  v1 = *(_QWORD *)(a1 + 8);
  v11 = 0;
  memset(v10, 0, sizeof(v10));
  v3 = *(_QWORD **)(v1 + 8);
  v4 = v3[14];
  LODWORD(v11) = 12;
  *((_QWORD *)&v11 + 1) = v3[133];
  v6 = SecureChannel_SendRequestSynchronously(v4, v10, 48, &v8, 16);
  if ( v6 >= 0 )
  {
    v6 = v8;
    if ( (int)v8 >= 0 )
    {
      *(_QWORD *)(a1 + 32) = v9;
    }
    else
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v5) = 2;
        WPP_RECORDER_SF_d(v3[9], v5, 7, 11, (__int64)WPP_db21d8d52d393cb96c062fdb7e607301_Traceguids, v8);
      }
      Debug_FreAssertMsg(
        "IOCTL succeeded but CommandCreate failed in VTL-1 failed",
        0,
        "onecore\\drivers\\wdm\\usb\\usb3\\usbxhci\\sys\\xilcommand.c",
        92);
    }
  }
  else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v5) = 2;
    WPP_RECORDER_SF_d(v3[9], v5, 7, 10, (__int64)WPP_db21d8d52d393cb96c062fdb7e607301_Traceguids, v6);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x14003f744  push    rbp
0x14003f746  push    rbx
0x14003f747  push    rsi
0x14003f748  push    rdi
0x14003f749  lea     rbp, [rsp-3Fh]
0x14003f74e  sub     rsp, 88h
0x14003f755  mov     rax, cs:__security_cookie
0x14003f75c  xor     rax, rsp
0x14003f75f  mov     [rbp+57h+var_30], rax
0x14003f763  xor     eax, eax
0x14003f765  mov     dword ptr [rsp+0A0h+var_80], 10h
0x14003f76d  mov     [rbp+57h+var_70+4], rax
0x14003f771  lea     r9, [rbp+57h+var_70]
0x14003f775  mov     [rbp+57h+var_70], rax
0x14003f779  lea     rdx, [rbp+57h+var_60]
0x14003f77d  mov     rax, [rcx+8]
0x14003f781  xorps   xmm0, xmm0
0x14003f784  movups  [rbp+57h+var_40], xmm0
0x14003f788  mov     rsi, rcx
0x14003f78b  mov     r8d, 30h ; '0'
0x14003f791  movups  [rbp+57h+var_60], xmm0
0x14003f795  movups  [rbp+57h+var_50], xmm0
0x14003f799  mov     rdi, [rax+8]
0x14003f79d  mov     rcx, [rdi+70h]
0x14003f7a1  mov     dword ptr [rbp+57h+var_40], 0Ch
0x14003f7a8  mov     rax, [rdi+428h]
0x14003f7af  mov     qword ptr [rbp+57h+var_40+8], rax
0x14003f7b3  call    SecureChannel_SendRequestSynchronously
0x14003f7b8  mov     ebx, eax
0x14003f7ba  test    eax, eax
0x14003f7bc  jns     short loc_14003F7F9
0x14003f7be  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14003f7c5  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003f7cc  jz      loc_14003F85A
0x14003f7d2  mov     rcx, [rdi+48h]
0x14003f7d6  lea     rax, WPP_db21d8d52d393cb96c062fdb7e607301_Traceguids
0x14003f7dd  mov     r9d, 0Ah
0x14003f7e3  mov     [rsp+0A0h+var_78], ebx
0x14003f7e7  mov     dl, 2
0x14003f7e9  mov     [rsp+0A0h+var_80], rax
0x14003f7ee  lea     r8d, [r9-3]
0x14003f7f2  call    WPP_RECORDER_SF_d
0x14003f7f7  jmp     short loc_14003F85A
0x14003f7f9  mov     ebx, dword ptr [rbp+57h+var_70]
0x14003f7fc  test    ebx, ebx
0x14003f7fe  jns     short loc_14003F852
0x14003f800  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14003f807  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003f80e  jz      short loc_14003F835
0x14003f810  mov     rcx, [rdi+48h]
0x14003f814  lea     rax, WPP_db21d8d52d393cb96c062fdb7e607301_Traceguids
0x14003f81b  mov     r9d, 0Bh
0x14003f821  mov     [rsp+0A0h+var_78], ebx
0x14003f825  mov     dl, 2
0x14003f827  mov     [rsp+0A0h+var_80], rax
0x14003f82c  lea     r8d, [r9-4]
0x14003f830  call    WPP_RECORDER_SF_d
0x14003f835  mov     r9d, 5Ch ; '\'
0x14003f83b  lea     r8, aOnecoreDrivers_5; "onecore\\drivers\\wdm\\usb\\usb3\\usbxh"...
0x14003f842  xor     edx, edx
0x14003f844  lea     rcx, aIoctlSucceeded_14; "IOCTL succeeded but CommandCreate faile"...
0x14003f84b  call    Debug_FreAssertMsg
0x14003f850  jmp     short loc_14003F85A
0x14003f852  mov     rax, [rbp+57h+var_68]
0x14003f856  mov     [rsi+20h], rax
0x14003f85a  mov     eax, ebx
0x14003f85c  mov     rcx, [rbp+57h+var_30]
0x14003f860  xor     rcx, rsp; StackCookie
0x14003f863  call    __security_check_cookie
0x14003f868  add     rsp, 88h
0x14003f86f  pop     rdi
0x14003f870  pop     rsi
0x14003f871  pop     rbx
0x14003f872  pop     rbp
0x14003f873  retn
```
