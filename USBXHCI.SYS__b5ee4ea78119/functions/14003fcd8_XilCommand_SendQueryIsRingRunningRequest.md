# XilCommand_SendQueryIsRingRunningRequest

- ea: `0x14003fcd8`
- end: `0x14003fe03`
- name: `XilCommand_SendQueryIsRingRunningRequest`
- size: `299`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14003fa38`

## callees

- `0x14001ad0c`
- `0x14001bb78`
- `0x14001c178`
- `0x14003fcd8`
- `0x140059970`

## string_xrefs

- `0x14003fdca`: `onecore\drivers\wdm\usb\usb3\usbxhci\sys\xilcommand.c`
- `0x14003fdd3`: `IOCTL succeeded but CommandQueryIsRingRunning failed in VTL-1 failed`

## pseudocode

```c
char __fastcall XilCommand_SendQueryIsRingRunningRequest(__int64 a1, _BYTE *a2, _BYTE *a3)
{
  __int64 v5; // rbx
  __int64 v6; // rax
  __int64 v7; // rcx
  int v8; // eax
  _UNKNOWN **v9; // rdx
  _UNKNOWN **v10; // rdx
  __int64 v12; // [rsp+30h] [rbp-58h] BYREF
  __int128 v13; // [rsp+38h] [rbp-50h] BYREF
  __int128 v14; // [rsp+48h] [rbp-40h]
  __int64 v15; // [rsp+58h] [rbp-30h]

  v12 = 0;
  v13 = 0;
  v14 = 0;
  v15 = 0;
  v5 = *(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL);
  v6 = *(_QWORD *)(a1 + 32);
  v7 = *(_QWORD *)(v5 + 112);
  *((_QWORD *)&v14 + 1) = v6;
  LODWORD(v15) = 18;
  v8 = SecureChannel_SendRequestSynchronously(v7, &v13, 40, &v12, 8);
  if ( v8 >= 0 )
  {
    if ( (int)v12 >= 0 )
    {
      *a2 = BYTE4(v12);
      LOBYTE(v8) = BYTE5(v12);
      *a3 = BYTE5(v12);
    }
    else
    {
      v10 = &WPP_RECORDER_INITIALIZED;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v10) = 2;
        WPP_RECORDER_SF_d(
          *(_QWORD *)(v5 + 72),
          (_DWORD)v10,
          7,
          28,
          (__int64)WPP_db21d8d52d393cb96c062fdb7e607301_Traceguids,
          v12);
      }
      LOBYTE(v8) = Debug_FreAssertMsg(
                     "IOCTL succeeded but CommandQueryIsRingRunning failed in VTL-1 failed",
                     0,
                     "onecore\\drivers\\wdm\\usb\\usb3\\usbxhci\\sys\\xilcommand.c",
                     892);
    }
  }
  else
  {
    v9 = &WPP_RECORDER_INITIALIZED;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v9) = 2;
      LOBYTE(v8) = WPP_RECORDER_SF_d(
                     *(_QWORD *)(v5 + 72),
                     (_DWORD)v9,
                     7,
                     27,
                     (__int64)WPP_db21d8d52d393cb96c062fdb7e607301_Traceguids,
                     v8);
    }
  }
  return v8;
}

```

## disassembly

```asm
0x14003fcd8  mov     r11, rsp
0x14003fcdb  push    rbx
0x14003fcdc  push    rsi
0x14003fcdd  push    rdi
0x14003fcde  sub     rsp, 70h
0x14003fce2  mov     rax, cs:__security_cookie
0x14003fce9  xor     rax, rsp
0x14003fcec  mov     [rsp+88h+var_28], rax
0x14003fcf1  xor     eax, eax
0x14003fcf3  mov     dword ptr [rsp+88h+var_68], 8
0x14003fcfb  mov     [r11-58h], rax
0x14003fcff  mov     r9, rcx
0x14003fd02  xorps   xmm0, xmm0
0x14003fd05  mov     rsi, r8
0x14003fd08  movups  [rsp+88h+var_50], xmm0
0x14003fd0d  mov     rdi, rdx
0x14003fd10  mov     r8d, 28h ; '('
0x14003fd16  movups  [rsp+88h+var_40], xmm0
0x14003fd1b  mov     [r11-30h], rax
0x14003fd1f  lea     rdx, [r11-50h]
0x14003fd23  mov     rax, [rcx+8]
0x14003fd27  mov     rbx, [rax+8]
0x14003fd2b  mov     rax, [r9+20h]
0x14003fd2f  lea     r9, [r11-58h]
0x14003fd33  mov     rcx, [rbx+70h]
0x14003fd37  mov     [r11-38h], rax
0x14003fd3b  mov     dword ptr [rsp+88h+var_30], 12h
0x14003fd43  call    SecureChannel_SendRequestSynchronously
0x14003fd48  test    eax, eax
0x14003fd4a  jns     short loc_14003FD87
0x14003fd4c  lea     rdx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14003fd53  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x14003fd5a  jz      loc_14003FDED
0x14003fd60  mov     rcx, [rbx+48h]
0x14003fd64  mov     r9d, 1Bh
0x14003fd6a  mov     [rsp+88h+var_60], eax
0x14003fd6e  mov     dl, 2
0x14003fd70  lea     rax, WPP_db21d8d52d393cb96c062fdb7e607301_Traceguids
0x14003fd77  mov     [rsp+88h+var_68], rax
0x14003fd7c  lea     r8d, [r9-14h]
0x14003fd80  call    WPP_RECORDER_SF_d
0x14003fd85  jmp     short loc_14003FDED
0x14003fd87  mov     eax, [rsp+88h+var_58]
0x14003fd8b  test    eax, eax
0x14003fd8d  jns     short loc_14003FDE1
0x14003fd8f  lea     rdx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14003fd96  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x14003fd9d  jz      short loc_14003FDC4
0x14003fd9f  mov     rcx, [rbx+48h]
0x14003fda3  mov     r9d, 1Ch
0x14003fda9  mov     [rsp+88h+var_60], eax
0x14003fdad  mov     dl, 2
0x14003fdaf  lea     rax, WPP_db21d8d52d393cb96c062fdb7e607301_Traceguids
0x14003fdb6  mov     [rsp+88h+var_68], rax
0x14003fdbb  lea     r8d, [r9-15h]
0x14003fdbf  call    WPP_RECORDER_SF_d
0x14003fdc4  mov     r9d, 37Ch
0x14003fdca  lea     r8, aOnecoreDrivers_5; "onecore\\drivers\\wdm\\usb\\usb3\\usbxh"...
0x14003fdd1  xor     edx, edx
0x14003fdd3  lea     rcx, aIoctlSucceeded_10; "IOCTL succeeded but CommandQueryIsRingR"...
0x14003fdda  call    Debug_FreAssertMsg
0x14003fddf  jmp     short loc_14003FDED
0x14003fde1  mov     al, [rsp+88h+var_54]
0x14003fde5  mov     [rdi], al
0x14003fde7  mov     al, [rsp+88h+var_53]
0x14003fdeb  mov     [rsi], al
0x14003fded  mov     rcx, [rsp+88h+var_28]
0x14003fdf2  xor     rcx, rsp; StackCookie
0x14003fdf5  call    __security_check_cookie
0x14003fdfa  add     rsp, 70h
0x14003fdfe  pop     rdi
0x14003fdff  pop     rsi
0x14003fe00  pop     rbx
0x14003fe01  retn
```
