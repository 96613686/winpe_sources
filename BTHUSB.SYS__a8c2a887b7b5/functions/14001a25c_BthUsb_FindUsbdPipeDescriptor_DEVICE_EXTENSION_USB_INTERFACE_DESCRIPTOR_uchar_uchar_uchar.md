# BthUsb_FindUsbdPipeDescriptor(_DEVICE_EXTENSION *,_USB_INTERFACE_DESCRIPTOR *,uchar,uchar,uchar *)

- ea: `0x14001a25c`
- end: `0x14001a4a1`
- name: `?BthUsb_FindUsbdPipeDescriptor@@_Y2PAGE@@APEAU_USB_ENDPOINT_DESCRIPTOR@@PEAU_DEVICE_EXTENSION@@PEAU_USB_INTERFACE_DESCRIPTOR@@EEPEAE@Z`
- size: `581`
- prototype: `struct _USB_ENDPOINT_DESCRIPTOR *__fastcall(struct _DEVICE_EXTENSION *, struct _USB_INTERFACE_DESCRIPTOR *, unsigned __int8, unsigned __int8, unsigned __int8 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x140004b3c`
- `0x14001accc`

## callees

- `0x14000175c`
- `0x14000b960`
- `0x14000ba00`
- `0x14000baec`
- `0x14001a25c`

## pseudocode

```c
struct _USB_INTERFACE_DESCRIPTOR *__fastcall BthUsb_FindUsbdPipeDescriptor(
        struct _DEVICE_EXTENSION *a1,
        struct _USB_INTERFACE_DESCRIPTOR *a2,
        int a3,
        char a4,
        unsigned __int8 *a5)
{
  struct _USB_INTERFACE_DESCRIPTOR *v7; // r14
  struct _USB_INTERFACE_DESCRIPTOR *v8; // rdx
  unsigned int v9; // r8d
  unsigned __int8 *v11; // rsi
  char v12; // bl
  __int64 bLength; // r8
  unsigned int v14; // r11d
  unsigned int bNumEndpoints; // r14d
  unsigned __int8 *p_bInterfaceNumber; // r9
  signed __int64 v17; // rdx
  char v18; // si
  signed __int64 v19; // rdx
  signed __int64 v20; // rdx
  int v21; // [rsp+20h] [rbp-68h]
  int v22; // [rsp+28h] [rbp-60h]
  int v23; // [rsp+30h] [rbp-58h]
  int v24; // [rsp+38h] [rbp-50h]
  char v25; // [rsp+40h] [rbp-48h]
  char v26; // [rsp+40h] [rbp-48h]
  char v27; // [rsp+40h] [rbp-48h]

  v7 = a2;
  *a5 = 0;
  if ( a1->DeviceDescriptor->bcdUSB > 0x200u )
  {
    v11 = &a1->ConfigDescriptor->bLength + a1->ConfigDescriptor->wTotalLength;
    v12 = 1;
    LOBYTE(a2) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
    WPP_RECORDER_AND_TRACE_SF_(
      WPP_GLOBAL_Control->AttachedDevice,
      (_DWORD)a2,
      a3,
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      2,
      56,
      (__int64)WPP_d9e027c83b54391969aefc6614c696e6_Traceguids);
    v14 = 0;
    v8 = (struct _USB_INTERFACE_DESCRIPTOR *)((char *)v7 + v7->bLength);
    bNumEndpoints = v7->bNumEndpoints;
    if ( bNumEndpoints )
    {
      while ( 1 )
      {
        p_bInterfaceNumber = &v8->bInterfaceNumber;
        if ( &v8->bInterfaceNumber < (unsigned __int8 *)v8 || p_bInterfaceNumber > v11 )
          break;
        bLength = v8->bLength;
        if ( (struct _USB_INTERFACE_DESCRIPTOR *)((char *)v8 + bLength) <= v8 || (char *)v8 + bLength > (char *)v11 )
        {
          if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
            v12 = 0;
          v18 = (_BYTE)v11 - (_BYTE)v8;
          v19 = (char *)v8 - (char *)a1->ConfigDescriptor;
          v26 = v19;
          LOBYTE(v19) = v12;
          WPP_RECORDER_AND_TRACE_SF_iDi(
            WPP_GLOBAL_Control->AttachedDevice,
            v19,
            bLength,
            WPP_GLOBAL_Control->DeviceExtension,
            v21,
            v22,
            v23,
            v24,
            v26,
            bLength,
            v18);
          return 0;
        }
        if ( v8->bDescriptorType == 5 )
        {
          if ( (_BYTE)bLength != 7 )
          {
            if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
              v12 = 0;
            v17 = (char *)v8 - (char *)a1->ConfigDescriptor;
            v25 = v17;
            LOBYTE(v17) = v12;
            WPP_RECORDER_AND_TRACE_SF_iDD(
              WPP_GLOBAL_Control->AttachedDevice,
              v17,
              bLength,
              WPP_GLOBAL_Control->DeviceExtension,
              v21,
              v22,
              v23,
              v24,
              v25,
              bLength);
            return 0;
          }
          ++v14;
          if ( (v8->bAlternateSetting & 3) == 1 && (a4 != 0) == *p_bInterfaceNumber >> 7 )
            return v8;
        }
        v8 = (struct _USB_INTERFACE_DESCRIPTOR *)((char *)v8 + bLength);
        if ( v14 >= bNumEndpoints )
          return 0;
      }
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        v12 = 0;
      v20 = (char *)v8 - (char *)a1->ConfigDescriptor;
      v27 = v20;
      LOBYTE(v20) = v12;
      WPP_RECORDER_AND_TRACE_SF_i(
        WPP_GLOBAL_Control->AttachedDevice,
        v20,
        bLength,
        WPP_GLOBAL_Control->DeviceExtension,
        v21,
        v22,
        v23,
        v24,
        v27);
    }
    return 0;
  }
  LOBYTE(a2) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  WPP_RECORDER_AND_TRACE_SF_(
    WPP_GLOBAL_Control->AttachedDevice,
    (_DWORD)a2,
    a3,
    WPP_GLOBAL_Control->DeviceExtension,
    4,
    2,
    55,
    (__int64)WPP_d9e027c83b54391969aefc6614c696e6_Traceguids);
  v8 = v7 + 1;
  v9 = 0;
  if ( !v7->bNumEndpoints )
    return 0;
  while ( (v8->bAlternateSetting & 3) != 1 || (a4 != 0) != v8->bInterfaceNumber >> 7 )
  {
    ++v9;
    v8 = (struct _USB_INTERFACE_DESCRIPTOR *)((char *)v8 + 7);
    if ( v9 >= v7->bNumEndpoints )
      return 0;
  }
  return v8;
}

```

## disassembly

```asm
0x14001a25c  push    rbx
0x14001a25e  push    rbp
0x14001a25f  push    rsi
0x14001a260  push    r14
0x14001a262  push    r15
0x14001a264  sub     rsp, 60h
0x14001a268  mov     rax, [rsp+88h+arg_20]
0x14001a270  mov     rbp, rcx
0x14001a273  mov     r15b, r9b
0x14001a276  mov     r14, rdx
0x14001a279  mov     byte ptr [rax], 0
0x14001a27c  mov     rax, [rcx+60h]
0x14001a280  mov     ecx, 200h
0x14001a285  cmp     cx, [rax+2]
0x14001a289  jb      loc_14001A322
0x14001a28f  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a296  mov     ebx, 1
0x14001a29b  mov     eax, [rcx+2Ch]
0x14001a29e  test    al, 2
0x14001a2a0  jz      short loc_14001A2AC
0x14001a2a2  cmp     byte ptr [rcx+29h], 4
0x14001a2a6  jb      short loc_14001A2AC
0x14001a2a8  mov     dl, bl
0x14001a2aa  jmp     short loc_14001A2AE
0x14001a2ac  xor     dl, dl
0x14001a2ae  mov     r9, [rcx+40h]
0x14001a2b2  lea     rax, WPP_d9e027c83b54391969aefc6614c696e6_Traceguids
0x14001a2b9  mov     rcx, [rcx+18h]
0x14001a2bd  mov     [rsp+88h+var_50], rax
0x14001a2c2  mov     [rsp+88h+var_58], 37h ; '7'
0x14001a2c9  mov     [rsp+88h+var_60], 2
0x14001a2d1  mov     [rsp+88h+var_68], 4
0x14001a2d6  call    WPP_RECORDER_AND_TRACE_SF_
0x14001a2db  movzx   r9d, byte ptr [r14+4]
0x14001a2e0  lea     rdx, [r14+9]
0x14001a2e4  xor     r8d, r8d
0x14001a2e7  test    r9d, r9d
0x14001a2ea  jz      loc_14001A492
0x14001a2f0  mov     al, [rdx+3]
0x14001a2f3  and     al, 3
0x14001a2f5  cmp     al, bl
0x14001a2f7  jnz     short loc_14001A309
0x14001a2f9  mov     cl, [rdx+2]
0x14001a2fc  shr     cl, 7
0x14001a2ff  test    r15b, r15b
0x14001a302  setnz   al
0x14001a305  cmp     al, cl
0x14001a307  jz      short loc_14001A31A
0x14001a309  add     r8d, ebx
0x14001a30c  add     rdx, 7
0x14001a310  cmp     r8d, r9d
0x14001a313  jb      short loc_14001A2F0
0x14001a315  jmp     loc_14001A492
0x14001a31a  mov     rax, rdx
0x14001a31d  jmp     loc_14001A494
0x14001a322  mov     rax, [rbp+68h]
0x14001a326  movzx   esi, word ptr [rax+2]
0x14001a32a  add     rsi, rax
0x14001a32d  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a334  mov     ebx, 1
0x14001a339  mov     eax, [rcx+2Ch]
0x14001a33c  test    al, 2
0x14001a33e  jz      short loc_14001A34A
0x14001a340  cmp     byte ptr [rcx+29h], 4
0x14001a344  jb      short loc_14001A34A
0x14001a346  mov     dl, bl
0x14001a348  jmp     short loc_14001A34C
0x14001a34a  xor     dl, dl
0x14001a34c  mov     r9, [rcx+40h]
0x14001a350  lea     rax, WPP_d9e027c83b54391969aefc6614c696e6_Traceguids
0x14001a357  mov     rcx, [rcx+18h]
0x14001a35b  mov     [rsp+88h+var_50], rax
0x14001a360  mov     [rsp+88h+var_58], 38h ; '8'
0x14001a367  mov     [rsp+88h+var_60], 2
0x14001a36f  mov     [rsp+88h+var_68], 4
0x14001a374  call    WPP_RECORDER_AND_TRACE_SF_
0x14001a379  movzx   edx, byte ptr [r14]
0x14001a37d  xor     r11d, r11d
0x14001a380  add     rdx, r14
0x14001a383  movzx   r14d, byte ptr [r14+4]
0x14001a388  test    r14d, r14d
0x14001a38b  jz      loc_14001A492
0x14001a391  lea     r9, [rdx+2]
0x14001a395  cmp     r9, rdx
0x14001a398  jb      loc_14001A464
0x14001a39e  cmp     r9, rsi
0x14001a3a1  ja      loc_14001A464
0x14001a3a7  movzx   r8d, byte ptr [rdx]
0x14001a3ab  lea     r10, [r8+rdx]
0x14001a3af  cmp     r10, rdx
0x14001a3b2  jbe     short loc_14001A427
0x14001a3b4  cmp     r10, rsi
0x14001a3b7  ja      short loc_14001A427
0x14001a3b9  cmp     byte ptr [rdx+1], 5
0x14001a3bd  jnz     short loc_14001A3E5
0x14001a3bf  cmp     r8b, 7
0x14001a3c3  jnz     short loc_14001A3F2
0x14001a3c5  mov     al, [rdx+3]
0x14001a3c8  add     r11d, ebx
0x14001a3cb  and     al, 3
0x14001a3cd  cmp     al, bl
0x14001a3cf  jnz     short loc_14001A3E5
0x14001a3d1  mov     al, [r9]
0x14001a3d4  test    r15b, r15b
0x14001a3d7  setnz   cl
0x14001a3da  shr     al, 7
0x14001a3dd  cmp     cl, al
0x14001a3df  jz      loc_14001A31A
0x14001a3e5  mov     rdx, r10
0x14001a3e8  cmp     r11d, r14d
0x14001a3eb  jb      short loc_14001A391
0x14001a3ed  jmp     loc_14001A492
0x14001a3f2  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a3f9  mov     eax, [rcx+2Ch]
0x14001a3fc  test    al, 2
0x14001a3fe  jz      short loc_14001A406
0x14001a400  cmp     byte ptr [rcx+29h], 2
0x14001a404  jnb     short loc_14001A408
0x14001a406  xor     bl, bl
0x14001a408  sub     rdx, [rbp+68h]
0x14001a40c  mov     r9, [rcx+40h]
0x14001a410  mov     rcx, [rcx+18h]
0x14001a414  mov     [rsp+88h+var_40], r8d
0x14001a419  mov     [rsp+88h+var_48], rdx
0x14001a41e  mov     dl, bl
0x14001a420  call    WPP_RECORDER_AND_TRACE_SF_iDD
0x14001a425  jmp     short loc_14001A492
0x14001a427  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a42e  mov     eax, [rcx+2Ch]
0x14001a431  test    al, 2
0x14001a433  jz      short loc_14001A43B
0x14001a435  cmp     byte ptr [rcx+29h], 2
0x14001a439  jnb     short loc_14001A43D
0x14001a43b  xor     bl, bl
0x14001a43d  mov     r9, [rcx+40h]
0x14001a441  sub     rsi, rdx
0x14001a444  sub     rdx, [rbp+68h]
0x14001a448  mov     rcx, [rcx+18h]
0x14001a44c  mov     [rsp+88h+var_38], rsi
0x14001a451  mov     [rsp+88h+var_40], r8d
0x14001a456  mov     [rsp+88h+var_48], rdx
0x14001a45b  mov     dl, bl
0x14001a45d  call    WPP_RECORDER_AND_TRACE_SF_iDi
0x14001a462  jmp     short loc_14001A492
0x14001a464  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a46b  mov     eax, [rcx+2Ch]
0x14001a46e  test    al, 2
0x14001a470  jz      short loc_14001A478
0x14001a472  cmp     byte ptr [rcx+29h], 2
0x14001a476  jnb     short loc_14001A47A
0x14001a478  xor     bl, bl
0x14001a47a  sub     rdx, [rbp+68h]
0x14001a47e  mov     r9, [rcx+40h]
0x14001a482  mov     rcx, [rcx+18h]
0x14001a486  mov     [rsp+88h+var_48], rdx
0x14001a48b  mov     dl, bl
0x14001a48d  call    WPP_RECORDER_AND_TRACE_SF_i
0x14001a492  xor     eax, eax
0x14001a494  add     rsp, 60h
0x14001a498  pop     r15
0x14001a49a  pop     r14
0x14001a49c  pop     rsi
0x14001a49d  pop     rbp
0x14001a49e  pop     rbx
0x14001a49f  retn
```
