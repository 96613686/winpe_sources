# XilCommand_SendAdvanceDequeuePointerRequest

- ea: `0x14003fbb8`
- end: `0x14003fccf`
- name: `XilCommand_SendAdvanceDequeuePointerRequest`
- size: `279`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14003f514`

## callees

- `0x14001ad0c`
- `0x14001bb78`
- `0x14001c178`
- `0x14003fbb8`
- `0x140059970`

## string_xrefs

- `0x14003fca6`: `onecore\drivers\wdm\usb\usb3\usbxhci\sys\xilcommand.c`
- `0x14003fcaf`: `IOCTL succeeded but CommandAdvanceDequeuePointer failed in VTL-1 failed`

## pseudocode

```c
__int64 __fastcall XilCommand_SendAdvanceDequeuePointerRequest(__int64 a1, int a2)
{
  __int64 v2; // rax
  __int64 v3; // rbx
  __int64 v4; // rax
  __int64 v5; // rcx
  __int64 result; // rax
  _UNKNOWN **v7; // rdx
  _UNKNOWN **v8; // rdx
  int v9; // [rsp+30h] [rbp-48h] BYREF
  __int128 v10; // [rsp+38h] [rbp-40h] BYREF
  __int128 v11; // [rsp+48h] [rbp-30h]
  __int128 v12; // [rsp+58h] [rbp-20h]

  v2 = *(_QWORD *)(a1 + 8);
  v9 = 0;
  v12 = 0;
  v11 = 0;
  v10 = 0;
  v3 = *(_QWORD *)(v2 + 8);
  v4 = *(_QWORD *)(a1 + 32);
  v5 = *(_QWORD *)(v3 + 112);
  DWORD2(v12) = a2;
  *((_QWORD *)&v11 + 1) = v4;
  LODWORD(v12) = 17;
  result = SecureChannel_SendRequestSynchronously(v5, &v10, 48, &v9, 4);
  if ( (int)result >= 0 )
  {
    result = (unsigned int)v9;
    if ( v9 < 0 )
    {
      v8 = &WPP_RECORDER_INITIALIZED;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v8) = 2;
        WPP_RECORDER_SF_d(
          *(_QWORD *)(v3 + 72),
          (_DWORD)v8,
          7,
          24,
          (__int64)WPP_db21d8d52d393cb96c062fdb7e607301_Traceguids,
          v9);
      }
      return Debug_FreAssertMsg(
               "IOCTL succeeded but CommandAdvanceDequeuePointer failed in VTL-1 failed",
               0,
               "onecore\\drivers\\wdm\\usb\\usb3\\usbxhci\\sys\\xilcommand.c",
               695);
    }
  }
  else
  {
    v7 = &WPP_RECORDER_INITIALIZED;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v7) = 2;
      return WPP_RECORDER_SF_d(
               *(_QWORD *)(v3 + 72),
               (_DWORD)v7,
               7,
               23,
               (__int64)WPP_db21d8d52d393cb96c062fdb7e607301_Traceguids,
               result);
    }
  }
  return result;
}

```

## disassembly

```asm
0x14003fbb8  push    rbx
0x14003fbba  sub     rsp, 70h
0x14003fbbe  mov     rax, cs:__security_cookie
0x14003fbc5  xor     rax, rsp
0x14003fbc8  mov     [rsp+78h+var_10], rax
0x14003fbcd  mov     rax, [rcx+8]
0x14003fbd1  lea     r9, [rsp+78h+var_48]
0x14003fbd6  xorps   xmm0, xmm0
0x14003fbd9  mov     [rsp+78h+var_48], 0
0x14003fbe1  movups  [rsp+78h+var_20], xmm0
0x14003fbe6  mov     r8, rcx
0x14003fbe9  mov     dword ptr [rsp+78h+var_58], 4
0x14003fbf1  movups  [rsp+78h+var_30], xmm0
0x14003fbf6  movups  [rsp+78h+var_40], xmm0
0x14003fbfb  mov     rbx, [rax+8]
0x14003fbff  mov     rax, [r8+20h]
0x14003fc03  mov     r8d, 30h ; '0'
0x14003fc09  mov     rcx, [rbx+70h]
0x14003fc0d  mov     dword ptr [rsp+78h+var_20+8], edx
0x14003fc11  lea     rdx, [rsp+78h+var_40]
0x14003fc16  mov     qword ptr [rsp+78h+var_30+8], rax
0x14003fc1b  mov     dword ptr [rsp+78h+var_20], 11h
0x14003fc23  call    SecureChannel_SendRequestSynchronously
0x14003fc28  test    eax, eax
0x14003fc2a  jns     short loc_14003FC63
0x14003fc2c  lea     rdx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14003fc33  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x14003fc3a  jz      short loc_14003FCBB
0x14003fc3c  mov     rcx, [rbx+48h]
0x14003fc40  mov     r9d, 17h
0x14003fc46  mov     [rsp+78h+var_50], eax
0x14003fc4a  mov     dl, 2
0x14003fc4c  lea     rax, WPP_db21d8d52d393cb96c062fdb7e607301_Traceguids
0x14003fc53  mov     [rsp+78h+var_58], rax
0x14003fc58  lea     r8d, [r9-10h]
0x14003fc5c  call    WPP_RECORDER_SF_d
0x14003fc61  jmp     short loc_14003FCBB
0x14003fc63  mov     eax, [rsp+78h+var_48]
0x14003fc67  test    eax, eax
0x14003fc69  jns     short loc_14003FCBB
0x14003fc6b  lea     rdx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14003fc72  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x14003fc79  jz      short loc_14003FCA0
0x14003fc7b  mov     rcx, [rbx+48h]
0x14003fc7f  mov     r9d, 18h
0x14003fc85  mov     [rsp+78h+var_50], eax
0x14003fc89  mov     dl, 2
0x14003fc8b  lea     rax, WPP_db21d8d52d393cb96c062fdb7e607301_Traceguids
0x14003fc92  mov     [rsp+78h+var_58], rax
0x14003fc97  lea     r8d, [r9-11h]
0x14003fc9b  call    WPP_RECORDER_SF_d
0x14003fca0  mov     r9d, 2B7h
0x14003fca6  lea     r8, aOnecoreDrivers_5; "onecore\\drivers\\wdm\\usb\\usb3\\usbxh"...
0x14003fcad  xor     edx, edx
0x14003fcaf  lea     rcx, aIoctlSucceeded_9; "IOCTL succeeded but CommandAdvanceDeque"...
0x14003fcb6  call    Debug_FreAssertMsg
0x14003fcbb  mov     rcx, [rsp+78h+var_10]
0x14003fcc0  xor     rcx, rsp; StackCookie
0x14003fcc3  call    __security_check_cookie
0x14003fcc8  add     rsp, 70h
0x14003fccc  pop     rbx
0x14003fccd  retn
```
