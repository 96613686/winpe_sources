# BthUsb_GetMaxIsoInterface(_DEVICE_EXTENSION *,uchar,_USB_INTERFACE_DESCRIPTOR * *,ulong *,_USB_INTERFACE_DESCRIPTOR * *,ulong *)

- ea: `0x14001accc`
- end: `0x14001b25e`
- name: `?BthUsb_GetMaxIsoInterface@@YAJPEAU_DEVICE_EXTENSION@@EPEAPEAU_USB_INTERFACE_DESCRIPTOR@@PEAK12@Z`
- size: `1426`
- prototype: `__int64 __usercall@<rax>(struct _DEVICE_EXTENSION *@<rcx>, unsigned __int8@<dl>, struct _USB_INTERFACE_DESCRIPTOR **@<r8>, unsigned int *@<r9>, struct _USB_INTERFACE_DESCRIPTOR **, unsigned int *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x14001743c`

## callees

- `0x1400010b8`
- `0x14000175c`
- `0x140001da0`
- `0x14000b14c`
- `0x14000b338`
- `0x14000b4c0`
- `0x14000b5c0`
- `0x14000d484`
- `0x14000ddc0`
- `0x14001a25c`
- `0x14001ac7c`
- `0x14001accc`

## pseudocode

```c
__int64 __fastcall BthUsb_GetMaxIsoInterface(
        struct _DEVICE_EXTENSION *a1,
        __int16 a2,
        struct _USB_INTERFACE_DESCRIPTOR **a3,
        unsigned int *a4,
        struct _USB_INTERFACE_DESCRIPTOR **a5,
        unsigned int *a6)
{
  unsigned __int16 v6; // r12
  int v7; // r15d
  struct _DEVICE_EXTENSION *v8; // rdi
  unsigned __int16 v9; // r13
  int v10; // ebx
  char v11; // r14
  unsigned int *v12; // rax
  PUSB_INTERFACE_DESCRIPTOR InterfaceDescriptor; // rax
  unsigned __int8 v14; // r8
  _BYTE *v15; // rbx
  PUSB_INTERFACE_DESCRIPTOR v16; // rsi
  char *v17; // rdi
  struct _DEVICE_EXTENSION *v18; // r13
  struct _DEVICE_EXTENSION *v19; // r15
  unsigned __int8 v20; // r8
  struct _USB_ENDPOINT_DESCRIPTOR *UsbdPipeDescriptor; // r13
  struct _USB_ENDPOINT_DESCRIPTOR *v22; // rax
  USHORT wMaxPacketSize; // dx
  int v24; // r8d
  int v25; // eax
  unsigned __int64 v26; // rdx
  _BYTE *v27; // rdi
  char v28; // al
  char *v29; // rcx
  char *v30; // rdx
  int v31; // edx
  char bAlternateSetting; // r9
  unsigned __int8 v33; // r15
  unsigned __int8 v34; // r12
  bool v35; // r11
  USHORT v36; // ax
  int v37; // edx
  struct _USB_INTERFACE_DESCRIPTOR **v38; // rsi
  unsigned int *v39; // rax
  char v40; // r9
  struct _USB_INTERFACE_DESCRIPTOR **v41; // rcx
  int v42; // r8d
  unsigned int *v43; // rdx
  int v44; // eax
  struct _USB_INTERFACE_DESCRIPTOR *v45; // rcx
  int v46; // r9d
  int v47; // edx
  int v48; // edx
  int v50; // [rsp+20h] [rbp-E0h]
  int v51; // [rsp+20h] [rbp-E0h]
  int v52; // [rsp+28h] [rbp-D8h]
  int v53; // [rsp+28h] [rbp-D8h]
  int v54; // [rsp+30h] [rbp-D0h]
  int v55; // [rsp+38h] [rbp-C8h]
  char v56; // [rsp+48h] [rbp-B8h]
  unsigned __int8 v57; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int8 v58[7]; // [rsp+61h] [rbp-9Fh] BYREF
  unsigned __int8 v59; // [rsp+68h] [rbp-98h] BYREF
  struct _DEVICE_EXTENSION *v60; // [rsp+70h] [rbp-90h]
  int v61; // [rsp+78h] [rbp-88h]
  _BYTE v62[11]; // [rsp+80h] [rbp-80h] BYREF
  USHORT v63; // [rsp+90h] [rbp-70h] BYREF
  int v64; // [rsp+94h] [rbp-6Ch]
  void *v65[2]; // [rsp+98h] [rbp-68h] BYREF
  __int64 v66; // [rsp+A8h] [rbp-58h]
  struct _USB_INTERFACE_DESCRIPTOR **v67; // [rsp+B0h] [rbp-50h]
  int v68; // [rsp+B8h] [rbp-48h]
  unsigned int *v69; // [rsp+C0h] [rbp-40h]
  void *ConfigDescriptor; // [rsp+C8h] [rbp-38h] BYREF
  struct _USB_INTERFACE_DESCRIPTOR *v71; // [rsp+D0h] [rbp-30h]
  struct _USB_INTERFACE_DESCRIPTOR *v72; // [rsp+D8h] [rbp-28h]
  unsigned int *v73; // [rsp+E0h] [rbp-20h]
  __int64 v74; // [rsp+E8h] [rbp-18h] BYREF
  struct _USB_INTERFACE_DESCRIPTOR **v75; // [rsp+F0h] [rbp-10h]
  struct _EVENT_DATA_DESCRIPTOR v76; // [rsp+100h] [rbp+0h] BYREF
  __int64 *v77; // [rsp+120h] [rbp+20h]
  __int64 v78; // [rsp+128h] [rbp+28h]
  struct _DEVICE_EXTENSION *v79; // [rsp+130h] [rbp+30h]
  __int64 v80; // [rsp+138h] [rbp+38h]
  unsigned __int8 *v81; // [rsp+140h] [rbp+40h]
  __int64 v82; // [rsp+148h] [rbp+48h]
  USHORT *v83; // [rsp+150h] [rbp+50h]
  __int64 v84; // [rsp+158h] [rbp+58h]
  unsigned __int8 *v85; // [rsp+160h] [rbp+60h]
  __int64 v86; // [rsp+168h] [rbp+68h]
  unsigned __int8 *v87; // [rsp+170h] [rbp+70h]
  __int64 v88; // [rsp+178h] [rbp+78h]

  v6 = 0;
  v7 = -1073741823;
  v69 = a4;
  v8 = a1;
  v67 = a3;
  v9 = 0;
  v10 = (unsigned __int8)a2;
  v61 = 0;
  v60 = a1;
  v75 = a5;
  v73 = a6;
  *(_DWORD *)&v58[3] = -1073741823;
  v64 = 0;
  v71 = 0;
  v72 = 0;
  v11 = 1;
  LOBYTE(a2) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  WPP_RECORDER_AND_TRACE_SF_(
    WPP_GLOBAL_Control->AttachedDevice,
    a2,
    (unsigned int)WPP_d9e027c83b54391969aefc6614c696e6_Traceguids,
    WPP_GLOBAL_Control->DeviceExtension,
    4,
    3,
    66,
    (__int64)WPP_d9e027c83b54391969aefc6614c696e6_Traceguids);
  *(__m128i *)v65 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  *v67 = 0;
  *v69 = 0;
  v12 = v73;
  *a5 = 0;
  v66 = -1;
  *v12 = 0;
  utl::vector<USB_ALT_SETTING,utl::allocator<USB_ALT_SETTING>>::_SetCapacity(v65, 8);
  ConfigDescriptor = v8->ConfigDescriptor;
  v68 = v10;
  InterfaceDescriptor = BthUsb_GetInterfaceDescriptor(v8, (_USB_CONFIGURATION_DESCRIPTOR **)&ConfigDescriptor, v10, -1);
  v15 = v65[0];
  v16 = InterfaceDescriptor;
  if ( !InterfaceDescriptor )
  {
    v38 = v67;
    goto LABEL_50;
  }
  v17 = (char *)v65[1];
  v18 = v60;
  do
  {
    if ( v16->bNumEndpoints != 2 )
      goto LABEL_41;
    v19 = v60;
    v58[0] = 0;
    UsbdPipeDescriptor = BthUsb_FindUsbdPipeDescriptor(v60, v16, v14, 1u, v58);
    if ( !UsbdPipeDescriptor
      || (v57 = 0, (v22 = BthUsb_FindUsbdPipeDescriptor(v19, v16, v20, 0, &v57)) == 0)
      || (wMaxPacketSize = UsbdPipeDescriptor->wMaxPacketSize, v24 = v22->wMaxPacketSize, wMaxPacketSize != (_WORD)v24)
      || wMaxPacketSize < 9u )
    {
      v18 = v60;
      goto LABEL_41;
    }
    v62[0] = v16->bAlternateSetting;
    *(_WORD *)&v62[1] = *(_WORD *)&v22->bEndpointAddress;
    v62[5] = v22->bInterval;
    *(_WORD *)&v62[6] = *(_WORD *)&UsbdPipeDescriptor->bEndpointAddress;
    v62[10] = UsbdPipeDescriptor->bInterval;
    *(_WORD *)&v62[3] = v24;
    *(_WORD *)&v62[8] = wMaxPacketSize;
    if ( v17 != (char *)v66 )
    {
      v25 = *(_DWORD *)&v62[7];
      *(_QWORD *)v17 = *(_QWORD *)v62;
      *(_DWORD *)(v17 + 7) = v25;
      v17 += 11;
LABEL_14:
      v65[1] = v17;
      goto LABEL_23;
    }
    v26 = 7 * ((unsigned __int64)(0x2E8BA2E8BA2E8BA3LL * (v66 - (_QWORD)v15)) >> 2) + 8;
    if ( v26 > 0xBA2E8BA2E8BA2E8LL )
      v26 = 0xBA2E8BA2E8BA2E8LL;
    if ( 0x2E8BA2E8BA2E8BA3LL * (v66 - (__int64)v15) < v26 )
    {
      v27 = (_BYTE *)(v62 - v15);
      v28 = utl::vector<USB_ALT_SETTING,utl::allocator<USB_ALT_SETTING>>::_SetCapacity(v65, v26);
      v15 = v65[0];
      if ( v28 )
      {
        v29 = (char *)v65[1];
        v30 = v62;
        if ( v27 < (_BYTE *)((char *)v65[1] - (char *)v65[0]) )
          v30 = &v27[(unsigned __int64)v65[0]];
        v17 = (char *)v65[1] + 11;
        *(_QWORD *)v65[1] = *(_QWORD *)v30;
        *(_DWORD *)(v29 + 7) = *(_DWORD *)(v30 + 7);
        goto LABEL_14;
      }
      v17 = (char *)v65[1];
    }
LABEL_23:
    v31 = UsbdPipeDescriptor->wMaxPacketSize;
    if ( (unsigned __int16)v31 > (unsigned __int16)v61 )
    {
      LOWORD(v61) = UsbdPipeDescriptor->wMaxPacketSize;
      v72 = v16;
    }
    bAlternateSetting = v16->bAlternateSetting;
    v33 = v57;
    v34 = v58[0];
    if ( (unsigned __int8)bAlternateSetting > 6u || v58[0] || v57 )
    {
      v35 = (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u;
      v56 = v31;
      LOBYTE(v31) = v35;
      WPP_RECORDER_AND_TRACE_SF_DDll(
        WPP_GLOBAL_Control->AttachedDevice,
        v31,
        v24,
        WPP_GLOBAL_Control->DeviceExtension,
        v50,
        v52,
        v54,
        v55,
        bAlternateSetting,
        v56,
        v58[0],
        v57);
      if ( (unsigned int)dword_140013000 > 3
        && (qword_140013010 & 0x400000000000LL) != 0
        && (qword_140013018 & 0x400000000000LL) == qword_140013018 )
      {
        v36 = UsbdPipeDescriptor->wMaxPacketSize;
        v18 = v60;
        v63 = v36;
        v59 = v16->bAlternateSetting;
        v87 = v58;
        v85 = &v57;
        v83 = &v63;
        v81 = &v59;
        v77 = &v74;
        v58[0] = v33;
        v57 = v34;
        v74 = 33556480;
        v88 = 1;
        v86 = 1;
        v84 = 2;
        v82 = 1;
        v79 = v60;
        v80 = 16;
        v78 = 8;
        tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_140013000, (unsigned __int8 *)byte_1400110D5, 0, 0, 8u, &v76);
      }
      else
      {
        v18 = v60;
      }
      v6 = v64;
    }
    else
    {
      v6 = v64;
      v18 = v60;
      if ( (unsigned __int16)v31 > (unsigned __int16)v64 )
      {
        v6 = v31;
        v71 = v16;
        v7 = 0;
        v64 = (unsigned __int16)v31;
        *(_DWORD *)&v58[3] = 0;
        goto LABEL_42;
      }
    }
LABEL_41:
    v7 = *(_DWORD *)&v58[3];
LABEL_42:
    v16 = BthUsb_GetInterfaceDescriptor(v18, (_USB_CONFIGURATION_DESCRIPTOR **)&ConfigDescriptor, v68, -1);
  }
  while ( v16 );
  v38 = v67;
  if ( v7 >= 0 )
  {
    v39 = v69;
    v40 = (char)v71;
    *v67 = v71;
    *v39 = v6;
    LOBYTE(v37) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
    WPP_RECORDER_AND_TRACE_SF_qd(
      WPP_GLOBAL_Control->AttachedDevice,
      v37,
      (unsigned int)WPP_d9e027c83b54391969aefc6614c696e6_Traceguids,
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      3,
      68,
      (__int64)WPP_d9e027c83b54391969aefc6614c696e6_Traceguids,
      v40,
      v6);
  }
  v9 = v61;
  LODWORD(v8) = (_DWORD)v60;
LABEL_50:
  v41 = v75;
  v42 = -1;
  v43 = v73;
  *v75 = v72;
  v44 = v9;
  *v43 = v9;
  v45 = *v41;
  if ( v45 )
  {
    v46 = v45->bAlternateSetting;
  }
  else
  {
    v46 = -1;
    v44 = -1;
  }
  if ( *v38 )
  {
    v47 = (*v38)->bAlternateSetting;
    v42 = *v69;
  }
  else
  {
    v47 = -1;
  }
  LogMaxIsoInterface((_DWORD)v8, v47, v42, v46, v44, (__int64)v65);
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
    v11 = 0;
  LOBYTE(v48) = v11;
  WPP_RECORDER_AND_TRACE_SF_Dd(
    WPP_GLOBAL_Control->AttachedDevice,
    v48,
    v6,
    WPP_GLOBAL_Control->DeviceExtension,
    v51,
    v53,
    v54,
    v55,
    v7,
    v6);
  if ( v15 != (_BYTE *)-1LL )
    operator delete(v15);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x14001accc  push    rbp
0x14001acce  push    rbx
0x14001accf  push    rsi
0x14001acd0  push    rdi
0x14001acd1  push    r12
0x14001acd3  push    r13
0x14001acd5  push    r14
0x14001acd7  push    r15
0x14001acd9  lea     rbp, [rsp-98h]
0x14001ace1  sub     rsp, 198h
0x14001ace8  mov     rax, cs:__security_cookie
0x14001acef  xor     rax, rsp
0x14001acf2  mov     [rbp+0D0h+var_50], rax
0x14001acf9  mov     rsi, [rbp+0D0h+arg_20]
0x14001ad00  xor     r12d, r12d
0x14001ad03  mov     rax, [rbp+0D0h+arg_28]
0x14001ad0a  mov     r15d, 0C0000001h
0x14001ad10  mov     [rbp+0D0h+var_110], r9
0x14001ad14  mov     rdi, rcx
0x14001ad17  xor     r9d, r9d
0x14001ad1a  mov     [rbp+0D0h+var_120], r8
0x14001ad1e  xor     r13d, r13d
0x14001ad21  movzx   ebx, dl
0x14001ad24  mov     [rsp+1D0h+var_158], r13d
0x14001ad29  mov     [rsp+1D0h+var_160], rcx
0x14001ad2e  mov     [rbp+0D0h+var_E0], rsi
0x14001ad32  mov     [rbp+0D0h+var_F0], rax
0x14001ad36  mov     dword ptr [rsp+1D0h+var_16F+3], r15d
0x14001ad3b  mov     [rbp+0D0h+var_13C], r12d
0x14001ad3f  mov     [rbp+0D0h+var_100], r9
0x14001ad43  mov     [rbp+0D0h+var_F8], r9
0x14001ad47  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ad4e  lea     r14d, [r12+1]
0x14001ad53  mov     eax, [rcx+2Ch]
0x14001ad56  test    al, 4
0x14001ad58  jz      short loc_14001AD65
0x14001ad5a  cmp     byte ptr [rcx+29h], 4
0x14001ad5e  jb      short loc_14001AD65
0x14001ad60  mov     dl, r14b
0x14001ad63  jmp     short loc_14001AD67
0x14001ad65  xor     dl, dl
0x14001ad67  mov     r9, [rcx+40h]
0x14001ad6b  lea     r8, WPP_d9e027c83b54391969aefc6614c696e6_Traceguids
0x14001ad72  mov     rcx, [rcx+18h]
0x14001ad76  mov     [rsp+1D0h+var_198], r8
0x14001ad7b  mov     word ptr [rsp+1D0h+var_1A0], 42h ; 'B'; int
0x14001ad82  mov     [rsp+1D0h+var_1A8], 3; int
0x14001ad8a  mov     byte ptr [rsp+1D0h+var_1B0], 4; int
0x14001ad8f  call    WPP_RECORDER_AND_TRACE_SF_
0x14001ad94  mov     rax, [rbp+0D0h+var_120]
0x14001ad98  xor     ecx, ecx
0x14001ad9a  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x14001ada2  movdqu  xmmword ptr [rbp+0D0h+var_138], xmm0
0x14001ada7  mov     [rax], rcx
0x14001adaa  lea     edx, [rcx+8]
0x14001adad  mov     rax, [rbp+0D0h+var_110]
0x14001adb1  mov     [rax], ecx
0x14001adb3  mov     rax, [rbp+0D0h+var_F0]
0x14001adb7  mov     [rsi], rcx
0x14001adba  or      rsi, 0FFFFFFFFFFFFFFFFh
0x14001adbe  mov     [rbp+0D0h+var_128], rsi
0x14001adc2  mov     [rax], ecx
0x14001adc4  lea     rcx, [rbp+0D0h+var_138]
0x14001adc8  call    ?_SetCapacity@?$vector@UUSB_ALT_SETTING@@V?$allocator@UUSB_ALT_SETTING@@@utl@@@utl@@AEAA_N_K@Z; utl::vector<USB_ALT_SETTING,utl::allocator<USB_ALT_SETTING>>::_SetCapacity(unsigned __int64)
0x14001adcd  mov     rax, [rdi+68h]
0x14001add1  lea     rdx, [rbp+0D0h+var_108]; void **
0x14001add5  mov     r9d, esi; int
0x14001add8  mov     [rbp+0D0h+var_108], rax
0x14001addc  mov     r8d, ebx; int
0x14001addf  mov     [rbp+0D0h+var_118], ebx
0x14001ade2  mov     rcx, rdi; struct _DEVICE_EXTENSION *
0x14001ade5  call    ?BthUsb_GetInterfaceDescriptor@@_Y2PAGE@@APEAU_USB_INTERFACE_DESCRIPTOR@@PEAU_DEVICE_EXTENSION@@PEAPEAXJJJJJ@Z; BthUsb_GetInterfaceDescriptor(_DEVICE_EXTENSION *,void * *,long,long,long,long,long)
0x14001adea  mov     rbx, [rbp+0D0h+var_138]
0x14001adee  mov     rsi, rax
0x14001adf1  test    rax, rax
0x14001adf4  jz      loc_14001B1BA
0x14001adfa  mov     rdi, [rbp+0D0h+var_138+8]
0x14001adfe  mov     r13, [rsp+1D0h+var_160]
0x14001ae03  cmp     byte ptr [rsi+4], 2
0x14001ae07  jnz     loc_14001B0F6
0x14001ae0d  mov     r15, [rsp+1D0h+var_160]
0x14001ae12  lea     rax, [rsp+1D0h+var_16F]
0x14001ae17  mov     rcx, r15; struct _DEVICE_EXTENSION *
0x14001ae1a  mov     [rsp+1D0h+var_16F], 0
0x14001ae1f  mov     r9b, r14b; unsigned __int8
0x14001ae22  mov     [rsp+1D0h+var_1B0], rax; int
0x14001ae27  mov     rdx, rsi; struct _USB_INTERFACE_DESCRIPTOR *
0x14001ae2a  call    ?BthUsb_FindUsbdPipeDescriptor@@_Y2PAGE@@APEAU_USB_ENDPOINT_DESCRIPTOR@@PEAU_DEVICE_EXTENSION@@PEAU_USB_INTERFACE_DESCRIPTOR@@EEPEAE@Z; BthUsb_FindUsbdPipeDescriptor(_DEVICE_EXTENSION *,_USB_INTERFACE_DESCRIPTOR *,uchar,uchar,uchar *)
0x14001ae2f  mov     r13, rax
0x14001ae32  test    rax, rax
0x14001ae35  jz      loc_14001B0F1
0x14001ae3b  lea     rax, [rsp+1D0h+var_170]
0x14001ae40  mov     [rsp+1D0h+var_170], 0
0x14001ae45  xor     r9d, r9d; unsigned __int8
0x14001ae48  mov     [rsp+1D0h+var_1B0], rax; unsigned __int8 *
0x14001ae4d  mov     rdx, rsi; struct _USB_INTERFACE_DESCRIPTOR *
0x14001ae50  mov     rcx, r15; struct _DEVICE_EXTENSION *
0x14001ae53  call    ?BthUsb_FindUsbdPipeDescriptor@@_Y2PAGE@@APEAU_USB_ENDPOINT_DESCRIPTOR@@PEAU_DEVICE_EXTENSION@@PEAU_USB_INTERFACE_DESCRIPTOR@@EEPEAE@Z; BthUsb_FindUsbdPipeDescriptor(_DEVICE_EXTENSION *,_USB_INTERFACE_DESCRIPTOR *,uchar,uchar,uchar *)
0x14001ae58  mov     rcx, rax
0x14001ae5b  test    rax, rax
0x14001ae5e  jz      loc_14001B0F1
0x14001ae64  movzx   edx, word ptr [r13+4]
0x14001ae69  movzx   r8d, word ptr [rax+4]
0x14001ae6e  cmp     dx, r8w
0x14001ae72  jnz     loc_14001B0F1
0x14001ae78  cmp     dx, 9
0x14001ae7c  jb      loc_14001B0F1
0x14001ae82  mov     al, [rsi+3]
0x14001ae85  mov     byte ptr [rbp+0D0h+var_150], al
0x14001ae88  mov     al, [rcx+2]
0x14001ae8b  mov     byte ptr [rbp+0D0h+var_150+1], al
0x14001ae8e  mov     al, [rcx+3]
0x14001ae91  mov     byte ptr [rbp+0D0h+var_150+2], al
0x14001ae94  mov     al, [rcx+6]
0x14001ae97  mov     byte ptr [rbp+0D0h+var_150+5], al
0x14001ae9a  mov     al, [r13+2]
0x14001ae9e  mov     byte ptr [rbp+0D0h+var_150+6], al
0x14001aea1  mov     al, [r13+3]
0x14001aea5  mov     byte ptr [rbp+0D0h+var_150+7], al
0x14001aea8  mov     al, [r13+6]
0x14001aeac  mov     [rbp+0D0h+var_146], al
0x14001aeaf  mov     word ptr [rbp+0D0h+var_150+3], r8w
0x14001aeb4  mov     [rbp+0D0h+var_148], dx
0x14001aeb8  cmp     rdi, [rbp+0D0h+var_128]
0x14001aebc  jz      short loc_14001AEDA
0x14001aebe  movsd   xmm0, [rbp+0D0h+var_150]
0x14001aec3  mov     eax, dword ptr [rbp+0D0h+var_150+7]
0x14001aec6  movsd   qword ptr [rdi], xmm0
0x14001aeca  mov     [rdi+7], eax
0x14001aecd  add     rdi, 0Bh
0x14001aed1  mov     [rbp+0D0h+var_138+8], rdi
0x14001aed5  jmp     loc_14001AF5E
0x14001aeda  mov     rcx, [rbp+0D0h+var_128]
0x14001aede  mov     rax, 2E8BA2E8BA2E8BA3h
0x14001aee8  sub     rcx, rbx
0x14001aeeb  imul    rcx, rax
0x14001aeef  mov     rax, rcx
0x14001aef2  shr     rax, 2
0x14001aef6  imul    rdx, rax, 7
0x14001aefa  mov     rax, 0BA2E8BA2E8BA2E8h
0x14001af04  add     rdx, 8
0x14001af08  cmp     rdx, rax
0x14001af0b  cmova   rdx, rax
0x14001af0f  cmp     rcx, rdx
0x14001af12  jnb     short loc_14001AF5E
0x14001af14  lea     rdi, [rbp+0D0h+var_150]
0x14001af18  lea     rcx, [rbp+0D0h+var_138]
0x14001af1c  sub     rdi, rbx
0x14001af1f  call    ?_SetCapacity@?$vector@UUSB_ALT_SETTING@@V?$allocator@UUSB_ALT_SETTING@@@utl@@@utl@@AEAA_N_K@Z; utl::vector<USB_ALT_SETTING,utl::allocator<USB_ALT_SETTING>>::_SetCapacity(unsigned __int64)
0x14001af24  mov     rbx, [rbp+0D0h+var_138]
0x14001af28  test    al, al
0x14001af2a  jz      short loc_14001AF5A
0x14001af2c  mov     rcx, [rbp+0D0h+var_138+8]
0x14001af30  lea     rdx, [rbp+0D0h+var_150]
0x14001af34  mov     rax, rcx
0x14001af37  sub     rax, rbx
0x14001af3a  cmp     rdi, rax
0x14001af3d  jnb     short loc_14001AF43
0x14001af3f  lea     rdx, [rdi+rbx]
0x14001af43  movsd   xmm0, qword ptr [rdx]
0x14001af47  lea     rdi, [rcx+0Bh]
0x14001af4b  movsd   qword ptr [rcx], xmm0
0x14001af4f  mov     eax, [rdx+7]
0x14001af52  mov     [rcx+7], eax
0x14001af55  jmp     loc_14001AED1
0x14001af5a  mov     rdi, [rbp+0D0h+var_138+8]
0x14001af5e  movzx   edx, word ptr [r13+4]
0x14001af63  cmp     dx, word ptr [rsp+1D0h+var_158]
0x14001af68  jbe     short loc_14001AF73
0x14001af6a  mov     word ptr [rsp+1D0h+var_158], dx
0x14001af6f  mov     [rbp+0D0h+var_F8], rsi
0x14001af73  movzx   r9d, byte ptr [rsi+3]
0x14001af78  movzx   r15d, [rsp+1D0h+var_170]
0x14001af7e  movzx   r12d, [rsp+1D0h+var_16F]
0x14001af84  cmp     r9b, 6
0x14001af88  ja      short loc_14001AFC0
0x14001af8a  test    r12b, r12b
0x14001af8d  jnz     short loc_14001AFC0
0x14001af8f  test    r15b, r15b
0x14001af92  jnz     short loc_14001AFC0
0x14001af94  mov     r12d, [rbp+0D0h+var_13C]
0x14001af98  mov     r13, [rsp+1D0h+var_160]
0x14001af9d  cmp     dx, r12w
0x14001afa1  jbe     loc_14001B0F6
0x14001afa7  movzx   r12d, dx
0x14001afab  mov     [rbp+0D0h+var_100], rsi
0x14001afaf  xor     r15d, r15d
0x14001afb2  mov     [rbp+0D0h+var_13C], r12d
0x14001afb6  mov     dword ptr [rsp+1D0h+var_16F+3], r15d
0x14001afbb  jmp     loc_14001B0FB
0x14001afc0  mov     r10, cs:WPP_GLOBAL_Control
0x14001afc7  mov     eax, [r10+2Ch]
0x14001afcb  test    al, 4
0x14001afcd  jz      short loc_14001AFDB
0x14001afcf  cmp     byte ptr [r10+29h], 3
0x14001afd4  jb      short loc_14001AFDB
0x14001afd6  mov     r11b, r14b
0x14001afd9  jmp     short loc_14001AFDE
0x14001afdb  xor     r11b, r11b
0x14001afde  mov     rcx, [r10+18h]
0x14001afe2  mov     [rsp+1D0h+var_178], r15d
0x14001afe7  mov     [rsp+1D0h+var_180], r12d
0x14001afec  mov     dword ptr [rsp+1D0h+var_188], edx
0x14001aff0  mov     dl, r11b
0x14001aff3  mov     dword ptr [rsp+1D0h+var_190], r9d
0x14001aff8  mov     r9, [r10+40h]
0x14001affc  call    WPP_RECORDER_AND_TRACE_SF_DDll
0x14001b001  mov     eax, cs:dword_140013000
0x14001b007  cmp     eax, 3
0x14001b00a  jbe     loc_14001B0E6
0x14001b010  mov     rcx, cs:qword_140013018
0x14001b017  mov     rdx, 400000000000h
0x14001b021  mov     rax, cs:qword_140013010
0x14001b028  test    rdx, rax
0x14001b02b  jz      loc_14001B0E6
0x14001b031  mov     rax, rcx
0x14001b034  and     rax, rdx
0x14001b037  cmp     rax, rcx
0x14001b03a  jnz     loc_14001B0E6
0x14001b040  movzx   eax, word ptr [r13+4]
0x14001b045  lea     rdx, byte_1400110D5
0x14001b04c  mov     r13, [rsp+1D0h+var_160]
0x14001b051  lea     rcx, dword_140013000
0x14001b058  mov     [rbp+0D0h+var_140], ax
0x14001b05c  xor     r9d, r9d
0x14001b05f  mov     al, [rsi+3]
0x14001b062  xor     r8d, r8d
0x14001b065  mov     [rsp+1D0h+var_168], al
0x14001b069  lea     rax, [rsp+1D0h+var_16F]
0x14001b06e  mov     [rbp+0D0h+var_60], rax
0x14001b072  lea     rax, [rsp+1D0h+var_170]
0x14001b077  mov     [rbp+0D0h+var_70], rax
0x14001b07b  lea     rax, [rbp+0D0h+var_140]
0x14001b07f  mov     [rbp+0D0h+var_80], rax
0x14001b083  lea     rax, [rsp+1D0h+var_168]
0x14001b088  mov     [rbp+0D0h+var_90], rax
0x14001b08c  lea     rax, [rbp+0D0h+var_E8]
0x14001b090  mov     [rbp+0D0h+var_B0], rax
0x14001b094  lea     rax, [rbp+0D0h+var_D0]
0x14001b098  mov     qword ptr [rsp+1D0h+var_1A8], rax
0x14001b09d  mov     dword ptr [rsp+1D0h+var_1B0], 8
0x14001b0a5  mov     [rsp+1D0h+var_16F], r15b
0x14001b0aa  mov     [rsp+1D0h+var_170], r12b
0x14001b0af  mov     [rbp+0D0h+var_E8], 2000800h
0x14001b0b7  mov     [rbp+0D0h+var_58], r14
0x14001b0bb  mov     [rbp+0D0h+var_68], r14
0x14001b0bf  mov     [rbp+0D0h+var_78], 2
0x14001b0c7  mov     [rbp+0D0h+var_88], r14
0x14001b0cb  mov     [rbp+0D0h+var_A0], r13
0x14001b0cf  mov     [rbp+0D0h+var_98], 10h
0x14001b0d7  mov     [rbp+0D0h+var_A8], 8
0x14001b0df  call    _tlgWriteTransfer_EtwWriteTransfer
0x14001b0e4  jmp     short loc_14001B0EB
0x14001b0e6  mov     r13, [rsp+1D0h+var_160]
0x14001b0eb  mov     r12d, [rbp+0D0h+var_13C]
0x14001b0ef  jmp     short loc_14001B0F6
0x14001b0f1  mov     r13, [rsp+1D0h+var_160]
0x14001b0f6  mov     r15d, dword ptr [rsp+1D0h+var_16F+3]
0x14001b0fb  mov     r8d, [rbp+0D0h+var_118]; int
0x14001b0ff  lea     rdx, [rbp+0D0h+var_108]; void **
0x14001b103  or      r9d, 0FFFFFFFFh; int
0x14001b107  mov     rcx, r13; struct _DEVICE_EXTENSION *
0x14001b10a  call    ?BthUsb_GetInterfaceDescriptor@@_Y2PAGE@@APEAU_USB_INTERFACE_DESCRIPTOR@@PEAU_DEVICE_EXTENSION@@PEAPEAXJJJJJ@Z; BthUsb_GetInterfaceDescriptor(_DEVICE_EXTENSION *,void * *,long,long,long,long,long)
0x14001b10f  mov     rsi, rax
0x14001b112  test    rax, rax
0x14001b115  jnz     loc_14001AE03
0x14001b11b  mov     rsi, [rbp+0D0h+var_120]
0x14001b11f  test    r15d, r15d
0x14001b122  js      short loc_14001B188
0x14001b124  mov     rax, [rbp+0D0h+var_110]
0x14001b128  mov     r9, [rbp+0D0h+var_100]
0x14001b12c  movzx   r8d, r12w
0x14001b130  mov     [rsi], r9
0x14001b133  mov     [rax], r8d
0x14001b136  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b13d  mov     eax, [rcx+2Ch]
0x14001b140  test    al, 4
0x14001b142  jz      short loc_14001B14F
0x14001b144  cmp     byte ptr [rcx+29h], 4
0x14001b148  jb      short loc_14001B14F
0x14001b14a  mov     dl, r14b
0x14001b14d  jmp     short loc_14001B151
0x14001b14f  xor     dl, dl
0x14001b151  mov     dword ptr [rsp+1D0h+var_188], r8d
0x14001b156  lea     r8, WPP_d9e027c83b54391969aefc6614c696e6_Traceguids
0x14001b15d  mov     [rsp+1D0h+var_190], r9
0x14001b162  mov     r9, [rcx+40h]
0x14001b166  mov     rcx, [rcx+18h]
0x14001b16a  mov     [rsp+1D0h+var_198], r8
0x14001b16f  mov     word ptr [rsp+1D0h+var_1A0], 44h ; 'D'
0x14001b176  mov     [rsp+1D0h+var_1A8], 3
0x14001b17e  mov     byte ptr [rsp+1D0h+var_1B0], 4
0x14001b183  call    WPP_RECORDER_AND_TRACE_SF_qd
0x14001b188  mov     r13d, [rsp+1D0h+var_158]
0x14001b18d  mov     rdi, [rsp+1D0h+var_160]
0x14001b192  mov     rcx, [rbp+0D0h+var_E0]
0x14001b196  or      r8d, 0FFFFFFFFh
0x14001b19a  mov     rax, [rbp+0D0h+var_F8]
0x14001b19e  mov     rdx, [rbp+0D0h+var_F0]
0x14001b1a2  mov     [rcx], rax
  ... truncated ...
```
