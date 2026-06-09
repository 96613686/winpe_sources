# XilCommand_AllocateSecureResources

- ea: `0x14003f594`
- end: `0x14003f6d8`
- name: `XilCommand_AllocateSecureResources`
- size: `324`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14003f53c`

## callees

- `0x14001ad0c`
- `0x14001bb78`
- `0x14001c178`
- `0x14003f594`
- `0x140059970`

## string_xrefs

- `0x14003f690`: `onecore\drivers\wdm\usb\usb3\usbxhci\sys\xilcommand.c`
- `0x14003f699`: `IOCTL succeeded but CommandAllocateResources failed in VTL-1 failed`

## pseudocode

```c
__int64 __fastcall XilCommand_AllocateSecureResources(__int64 a1)
{
  __int64 v2; // rax
  __int64 v3; // rsi
  __int64 v4; // rax
  __int64 v5; // rcx
  int v6; // edx
  int v7; // ebx
  __int128 v9; // [rsp+30h] [rbp-19h] BYREF
  __int128 v10; // [rsp+40h] [rbp-9h]
  __int64 v11; // [rsp+50h] [rbp+7h]
  _OWORD v12[2]; // [rsp+58h] [rbp+Fh] BYREF

  memset(v12, 0, 28);
  v11 = 0;
  v2 = *(_QWORD *)(a1 + 8);
  v10 = 0;
  v9 = 0;
  v3 = *(_QWORD *)(v2 + 8);
  v4 = *(_QWORD *)(a1 + 32);
  v5 = *(_QWORD *)(v3 + 112);
  memset(v12, 0, sizeof(v12));
  *((_QWORD *)&v10 + 1) = v4;
  LODWORD(v11) = 13;
  v7 = SecureChannel_SendRequestSynchronously(v5, &v9, 40, v12, 32);
  if ( v7 >= 0 )
  {
    v7 = v12[0];
    if ( SLODWORD(v12[0]) >= 0 )
    {
      *(_OWORD *)(a1 + 40) = *(_OWORD *)((char *)v12 + 8);
      *(_DWORD *)(a1 + 56) = DWORD2(v12[1]);
    }
    else
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v6) = 2;
        WPP_RECORDER_SF_d(
          *(_QWORD *)(v3 + 72),
          v6,
          7,
          14,
          (__int64)WPP_db21d8d52d393cb96c062fdb7e607301_Traceguids,
          v12[0]);
      }
      Debug_FreAssertMsg(
        "IOCTL succeeded but CommandAllocateResources failed in VTL-1 failed",
        0,
        "onecore\\drivers\\wdm\\usb\\usb3\\usbxhci\\sys\\xilcommand.c",
        214);
    }
  }
  else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v6) = 2;
    WPP_RECORDER_SF_d(*(_QWORD *)(v3 + 72), v6, 7, 13, (__int64)WPP_db21d8d52d393cb96c062fdb7e607301_Traceguids, v7);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x14003f594  push    rbp
0x14003f596  push    rbx
0x14003f597  push    rsi
0x14003f598  push    rdi
0x14003f599  lea     rbp, [rsp-3Fh]
0x14003f59e  sub     rsp, 88h
0x14003f5a5  mov     rax, cs:__security_cookie
0x14003f5ac  xor     rax, rsp
0x14003f5af  mov     [rbp+57h+var_28], rax
0x14003f5b3  xorps   xmm0, xmm0
0x14003f5b6  mov     dword ptr [rsp+0A0h+var_80], 20h ; ' '
0x14003f5be  movups  [rbp+57h+var_48], xmm0
0x14003f5c2  xor     eax, eax
0x14003f5c4  mov     rdi, rcx
0x14003f5c7  mov     [rbp+57h+var_50], rax
0x14003f5cb  lea     r9, [rbp+57h+var_48]
0x14003f5cf  mov     rax, [rcx+8]
0x14003f5d3  lea     rdx, [rbp+57h+var_70]
0x14003f5d7  movups  [rbp+57h+var_48+0Ch], xmm0
0x14003f5db  mov     r8d, 28h ; '('
0x14003f5e1  movups  [rbp+57h+var_60], xmm0
0x14003f5e5  movups  [rbp+57h+var_70], xmm0
0x14003f5e9  mov     rsi, [rax+8]
0x14003f5ed  mov     rax, [rdi+20h]
0x14003f5f1  mov     rcx, [rsi+70h]
0x14003f5f5  movups  [rbp+57h+var_48], xmm0
0x14003f5f9  mov     qword ptr [rbp+57h+var_60+8], rax
0x14003f5fd  movups  [rbp+57h+var_38], xmm0
0x14003f601  mov     dword ptr [rbp+57h+var_50], 0Dh
0x14003f608  call    SecureChannel_SendRequestSynchronously
0x14003f60d  mov     ebx, eax
0x14003f60f  test    eax, eax
0x14003f611  jns     short loc_14003F64E
0x14003f613  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14003f61a  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003f621  jz      loc_14003F6BD
0x14003f627  mov     rcx, [rsi+48h]
0x14003f62b  lea     rax, WPP_db21d8d52d393cb96c062fdb7e607301_Traceguids
0x14003f632  mov     r9d, 0Dh
0x14003f638  mov     [rsp+0A0h+var_78], ebx
0x14003f63c  mov     dl, 2
0x14003f63e  mov     [rsp+0A0h+var_80], rax
0x14003f643  lea     r8d, [r9-6]
0x14003f647  call    WPP_RECORDER_SF_d
0x14003f64c  jmp     short loc_14003F6BD
0x14003f64e  mov     ebx, dword ptr [rbp+57h+var_48]
0x14003f651  test    ebx, ebx
0x14003f653  jns     short loc_14003F6A7
0x14003f655  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14003f65c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003f663  jz      short loc_14003F68A
0x14003f665  mov     rcx, [rsi+48h]
0x14003f669  lea     rax, WPP_db21d8d52d393cb96c062fdb7e607301_Traceguids
0x14003f670  mov     r9d, 0Eh
0x14003f676  mov     [rsp+0A0h+var_78], ebx
0x14003f67a  mov     dl, 2
0x14003f67c  mov     [rsp+0A0h+var_80], rax
0x14003f681  lea     r8d, [r9-7]
0x14003f685  call    WPP_RECORDER_SF_d
0x14003f68a  mov     r9d, 0D6h
0x14003f690  lea     r8, aOnecoreDrivers_5; "onecore\\drivers\\wdm\\usb\\usb3\\usbxh"...
0x14003f697  xor     edx, edx
0x14003f699  lea     rcx, aIoctlSucceeded_5; "IOCTL succeeded but CommandAllocateReso"...
0x14003f6a0  call    Debug_FreAssertMsg
0x14003f6a5  jmp     short loc_14003F6BD
0x14003f6a7  mov     rax, qword ptr [rbp+57h+var_48+8]
0x14003f6ab  mov     [rdi+28h], rax
0x14003f6af  mov     rax, qword ptr [rbp+57h+var_38]
0x14003f6b3  mov     [rdi+30h], rax
0x14003f6b7  mov     eax, dword ptr [rbp+57h+var_38+8]
0x14003f6ba  mov     [rdi+38h], eax
0x14003f6bd  mov     eax, ebx
0x14003f6bf  mov     rcx, [rbp+57h+var_28]
0x14003f6c3  xor     rcx, rsp; StackCookie
0x14003f6c6  call    __security_check_cookie
0x14003f6cb  add     rsp, 88h
0x14003f6d2  pop     rdi
0x14003f6d3  pop     rsi
0x14003f6d4  pop     rbx
0x14003f6d5  pop     rbp
0x14003f6d6  retn
```
