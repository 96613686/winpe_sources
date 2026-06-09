# XilCommand_Create

- ea: `0x14003f6e0`
- end: `0x14003f73b`
- name: `XilCommand_Create`
- size: `91`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140075b9c`

## callees

- `0x14001bb78`
- `0x14003f6e0`
- `0x14003f744`

## string_xrefs

- `0x14003f715`: `onecore\drivers\wdm\usb\usb3\usbxhci\sys\xilcommand.c`
- `0x14003f71e`: `XilCommand_CreateSecureObject failed`

## pseudocode

```c
__int64 __fastcall XilCommand_Create(__int64 a1)
{
  __int64 v2; // rcx
  char v3; // dl
  int SecureObject; // ebx

  v2 = a1 + 136;
  *(_QWORD *)(v2 + 8) = a1;
  v3 = *(_BYTE *)(*(_QWORD *)(a1 + 8) + 1041LL);
  *(_BYTE *)v2 = v3;
  if ( v3 )
  {
    SecureObject = XilCommand_CreateSecureObject(v2);
    if ( SecureObject < 0 )
      Debug_FreAssertMsg(
        "XilCommand_CreateSecureObject failed",
        0,
        "onecore\\drivers\\wdm\\usb\\usb3\\usbxhci\\sys\\xilcommand.c",
        137);
  }
  else
  {
    *(_QWORD *)(v2 + 32) = a1;
    return 0;
  }
  return (unsigned int)SecureObject;
}

```

## disassembly

```asm
0x14003f6e0  push    rbx
0x14003f6e2  sub     rsp, 20h
0x14003f6e6  mov     r8, rcx
0x14003f6e9  add     rcx, 88h
0x14003f6f0  mov     [rcx+8], r8
0x14003f6f4  mov     rax, [r8+8]
0x14003f6f8  mov     dl, [rax+411h]
0x14003f6fe  mov     [rcx], dl
0x14003f700  test    dl, dl
0x14003f702  jz      short loc_14003F72C
0x14003f704  call    XilCommand_CreateSecureObject
0x14003f709  mov     ebx, eax
0x14003f70b  test    eax, eax
0x14003f70d  jns     short loc_14003F732
0x14003f70f  mov     r9d, 89h
0x14003f715  lea     r8, aOnecoreDrivers_5; "onecore\\drivers\\wdm\\usb\\usb3\\usbxh"...
0x14003f71c  xor     edx, edx
0x14003f71e  lea     rcx, aXilcommandCrea; "XilCommand_CreateSecureObject failed"
0x14003f725  call    Debug_FreAssertMsg
0x14003f72a  jmp     short loc_14003F732
0x14003f72c  mov     [rcx+20h], r8
0x14003f730  xor     ebx, ebx
0x14003f732  mov     eax, ebx
0x14003f734  add     rsp, 20h
0x14003f738  pop     rbx
0x14003f739  retn
```
