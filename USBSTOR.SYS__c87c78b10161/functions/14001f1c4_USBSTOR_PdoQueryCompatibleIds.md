# USBSTOR_PdoQueryCompatibleIds

- ea: `0x14001f1c4`
- end: `0x14001f2f1`
- name: `USBSTOR_PdoQueryCompatibleIds`
- size: `301`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x140024870`

## callees

- `0x14000e40c`
- `0x1400105e8`
- `0x140010664`
- `0x140013950`
- `0x14001f1c4`
- `0x14001f2f8`
- `0x140024c78`
- `0x140024e34`

## pseudocode

```c
__int64 __fastcall USBSTOR_PdoQueryCompatibleIds(__int64 a1, struct _UNICODE_STRING *a2)
{
  const char *v4; // rax
  unsigned int v5; // ebx
  char pszDest[32]; // [rsp+48h] [rbp-40h] BYREF

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 136, WPP_354602438fa331ce245c005e63ec86c9_Traceguids);
  }
  v4 = (const char *)USBSTOR_PdoDeviceTypeString(a1);
  RtlStringCbPrintfA(pszDest, 0x1Eu, "USBSTOR\\%s", v4);
  USBSTOR_PdoGenericTypeString(a1);
  v5 = USBSTOR_StringArrayToMultiSz(a2);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 137, WPP_354602438fa331ce245c005e63ec86c9_Traceguids);
  }
  return v5;
}

```

## disassembly

```asm
0x14001f1c4  mov     r11, rsp
0x14001f1c7  mov     [r11+18h], rbx
0x14001f1cb  push    rbp
0x14001f1cc  push    rsi
0x14001f1cd  push    rdi
0x14001f1ce  sub     rsp, 70h
0x14001f1d2  mov     rax, cs:__security_cookie
0x14001f1d9  xor     rax, rsp
0x14001f1dc  mov     [rsp+88h+var_20], rax
0x14001f1e1  lea     rax, [r11-40h]
0x14001f1e5  xorps   xmm0, xmm0
0x14001f1e8  mov     [r11-68h], rax
0x14001f1ec  mov     rsi, rdx
0x14001f1ef  lea     rax, aUsbstorRaw; "USBSTOR\\RAW"
0x14001f1f6  mov     rdi, rcx
0x14001f1f9  mov     [r11-60h], rax
0x14001f1fd  movdqu  [rsp+88h+var_58], xmm0
0x14001f203  mov     qword ptr [r11-48h], 0
0x14001f20b  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f212  lea     rbp, WPP_GLOBAL_Control
0x14001f219  cmp     rcx, rbp
0x14001f21c  jz      short loc_14001F240
0x14001f21e  mov     eax, [rcx+2Ch]
0x14001f221  test    al, 1
0x14001f223  jz      short loc_14001F240
0x14001f225  cmp     byte ptr [rcx+29h], 4
0x14001f229  jb      short loc_14001F240
0x14001f22b  mov     rcx, [rcx+18h]
0x14001f22f  lea     r8, WPP_354602438fa331ce245c005e63ec86c9_Traceguids
0x14001f236  mov     edx, 88h
0x14001f23b  call    WPP_SF_
0x14001f240  mov     rbx, [rdi+40h]
0x14001f244  mov     rcx, rdi
0x14001f247  call    USBSTOR_PdoDeviceTypeString
0x14001f24c  mov     r9, rax
0x14001f24f  lea     rcx, [rsp+88h+pszDest]; pszDest
0x14001f254  mov     edx, 1Eh; cbDest
0x14001f259  lea     r8, aUsbstorS; "USBSTOR\\%s"
0x14001f260  call    RtlStringCbPrintfA
0x14001f265  cmp     byte ptr [rbx+46h], 0
0x14001f269  mov     rcx, rdi
0x14001f26c  jz      short loc_14001F286
0x14001f26e  lea     rax, aDisk1667; "Disk1667"
0x14001f275  mov     qword ptr [rsp+88h+var_58], rax
0x14001f27a  call    USBSTOR_PdoGenericTypeString
0x14001f27f  mov     qword ptr [rsp+88h+var_58+8], rax
0x14001f284  jmp     short loc_14001F290
0x14001f286  call    USBSTOR_PdoGenericTypeString
0x14001f28b  mov     qword ptr [rsp+88h+var_58], rax
0x14001f290  lea     rdx, [rsp+88h+var_68]
0x14001f295  mov     rcx, rsi; DestinationString
0x14001f298  call    USBSTOR_StringArrayToMultiSz
0x14001f29d  mov     ebx, eax
0x14001f29f  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f2a6  cmp     rcx, rbp
0x14001f2a9  jz      short loc_14001F2D1
0x14001f2ab  mov     edx, [rcx+2Ch]
0x14001f2ae  test    dl, 1
0x14001f2b1  jz      short loc_14001F2D1
0x14001f2b3  cmp     byte ptr [rcx+29h], 4
0x14001f2b7  jb      short loc_14001F2D1
0x14001f2b9  mov     rcx, [rcx+18h]
0x14001f2bd  lea     r8, WPP_354602438fa331ce245c005e63ec86c9_Traceguids
0x14001f2c4  mov     edx, 89h
0x14001f2c9  mov     r9d, eax
0x14001f2cc  call    WPP_SF_d
0x14001f2d1  mov     eax, ebx
0x14001f2d3  mov     rcx, [rsp+88h+var_20]
0x14001f2d8  xor     rcx, rsp; StackCookie
0x14001f2db  call    __security_check_cookie
0x14001f2e0  mov     rbx, [rsp+88h+arg_10]
0x14001f2e8  add     rsp, 70h
0x14001f2ec  pop     rdi
0x14001f2ed  pop     rsi
0x14001f2ee  pop     rbp
0x14001f2ef  retn
```
