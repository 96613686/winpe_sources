# BthUsb_ScoFindInterfaceByFrame(_DEVICE_EXTENSION *,ulong,ulong *)

- ea: `0x140004b3c`
- end: `0x140004dd9`
- name: `?BthUsb_ScoFindInterfaceByFrame@@YAPEAU_USB_INTERFACE_DESCRIPTOR@@PEAU_DEVICE_EXTENSION@@KPEAK@Z`
- size: `669`
- prototype: `struct _USB_INTERFACE_DESCRIPTOR *__fastcall(struct _DEVICE_EXTENSION *, unsigned int, unsigned int *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x1400030e0`
- `0x140005180`

## callees

- `0x1400017d4`
- `0x140004b3c`
- `0x1400064c4`
- `0x140006580`
- `0x14000700c`
- `0x14001a25c`
- `0x14001ac7c`

## pseudocode

```c
struct _USB_INTERFACE_DESCRIPTOR *__fastcall BthUsb_ScoFindInterfaceByFrame(
        struct _DEVICE_EXTENSION *a1,
        unsigned int a2,
        unsigned int *a3)
{
  int v3; // eax
  int v4; // esi
  unsigned int *v5; // rdi
  int v8; // edx
  _USB_INTERFACE_DESCRIPTOR *MaxInterface; // rbx
  bool v10; // al
  LONG InterfaceNumber; // r13d
  LONG v12; // r12d
  unsigned __int8 v13; // r8
  struct _USB_ENDPOINT_DESCRIPTOR *UsbdPipeDescriptor; // r14
  int v15; // edx
  struct _USB_ENDPOINT_DESCRIPTOR *v16; // rcx
  unsigned int wMaxPacketSize; // eax
  PUSB_INTERFACE_DESCRIPTOR InterfaceDescriptor; // rax
  unsigned __int8 v19; // r8
  int v20; // r14d
  unsigned int MaxFrameSize; // ecx
  int v23; // [rsp+20h] [rbp-78h]
  int v24; // [rsp+28h] [rbp-70h]
  int v25; // [rsp+30h] [rbp-68h]
  int v26; // [rsp+38h] [rbp-60h]
  unsigned __int8 v27; // [rsp+A0h] [rbp+8h] BYREF
  void *ConfigDescriptor; // [rsp+B0h] [rbp+18h] BYREF

  v5 = a3;
  if ( a3 )
    *a3 = 0;
  LOBYTE(v3) = 0;
  LOBYTE(v4) = 1;
  while ( 1 )
  {
    v8 = v4 + v3;
    v3 = (char)v3;
    if ( *(_DWORD *)&asc_140010720[4 * (char)v3] == a2 )
      break;
    LOBYTE(v3) = v8;
    if ( (unsigned __int8)v8 >= 6u )
      goto LABEL_6;
  }
  v10 = (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  InterfaceNumber = (char)a1->Sco.InterfaceNumber;
  v12 = (char)v8;
  LOBYTE(v8) = v10;
  WPP_RECORDER_AND_TRACE_SF_qdd(
    WPP_GLOBAL_Control->AttachedDevice,
    v8,
    (unsigned int)WPP_d9e027c83b54391969aefc6614c696e6_Traceguids,
    WPP_GLOBAL_Control->DeviceExtension);
  if ( v5 )
    *v5 = 0;
  ConfigDescriptor = a1->ConfigDescriptor;
  while ( 1 )
  {
    InterfaceDescriptor = BthUsb_GetInterfaceDescriptor(
                            a1,
                            (_USB_CONFIGURATION_DESCRIPTOR **)&ConfigDescriptor,
                            InterfaceNumber,
                            v12);
    MaxInterface = InterfaceDescriptor;
    if ( !InterfaceDescriptor )
    {
      MaxInterface = 0;
      v20 = -1073741198;
      goto LABEL_25;
    }
    if ( InterfaceDescriptor->bNumEndpoints == 2 )
    {
      v27 = 0;
      UsbdPipeDescriptor = BthUsb_FindUsbdPipeDescriptor(a1, InterfaceDescriptor, v19, 1u, &v27);
      if ( UsbdPipeDescriptor )
      {
        if ( !v27 )
        {
          v27 = 0;
          v16 = BthUsb_FindUsbdPipeDescriptor(a1, MaxInterface, v13, 0, &v27);
          if ( v16 )
          {
            if ( !v27 )
            {
              wMaxPacketSize = UsbdPipeDescriptor->wMaxPacketSize;
              if ( (_WORD)wMaxPacketSize == v16->wMaxPacketSize )
                break;
            }
          }
        }
      }
    }
  }
  if ( v5 )
    *v5 = wMaxPacketSize;
  v20 = 0;
LABEL_25:
  LOBYTE(v15) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  WPP_RECORDER_AND_TRACE_SF_D(
    WPP_GLOBAL_Control->AttachedDevice,
    v15,
    (unsigned int)WPP_d9e027c83b54391969aefc6614c696e6_Traceguids,
    WPP_GLOBAL_Control->DeviceExtension,
    4,
    3,
    71,
    (__int64)WPP_d9e027c83b54391969aefc6614c696e6_Traceguids,
    v20);
  if ( v20 < 0 )
  {
LABEL_6:
    MaxInterface = 0;
    goto LABEL_7;
  }
  if ( !MaxInterface )
  {
LABEL_7:
    LOBYTE(v8) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
    LOBYTE(a3) = 1;
    WPP_RECORDER_AND_TRACE_SF_L(
      WPP_GLOBAL_Control->AttachedDevice,
      v8,
      (_DWORD)a3,
      WPP_GLOBAL_Control->DeviceExtension,
      2,
      4,
      12,
      (__int64)WPP_89eaa7be148f36a90e353489c15db76f_Traceguids,
      a2);
    MaxFrameSize = a1->Sco.MaxFrameSize;
    if ( a2 <= MaxFrameSize )
    {
      MaxInterface = a1->Sco.MaxInterface;
      if ( v5 )
        *v5 = MaxFrameSize;
    }
    return MaxInterface;
  }
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
    LOBYTE(v4) = 0;
  LOBYTE(v8) = v4;
  WPP_RECORDER_AND_TRACE_SF_DL(
    WPP_GLOBAL_Control->AttachedDevice,
    v8,
    (_DWORD)a3,
    WPP_GLOBAL_Control->DeviceExtension,
    v23,
    v24,
    v25,
    v26,
    MaxInterface->bAlternateSetting,
    a2);
  return MaxInterface;
}

```

## disassembly

```asm
0x140004b3c  mov     [rsp+arg_8], rbx
0x140004b41  push    rbp
0x140004b42  push    rsi
0x140004b43  push    rdi
0x140004b44  push    r12
0x140004b46  push    r13
0x140004b48  push    r14
0x140004b4a  push    r15
0x140004b4c  sub     rsp, 60h
0x140004b50  mov     rdi, r8
0x140004b53  mov     r15d, edx
0x140004b56  mov     rbp, rcx
0x140004b59  test    r8, r8
0x140004b5c  jz      short loc_140004B65
0x140004b5e  mov     dword ptr [r8], 0
0x140004b65  xor     al, al
0x140004b67  mov     sil, 1
0x140004b6a  lea     edx, [rsi+rax]
0x140004b6d  movsx   rax, al
0x140004b71  lea     rcx, asc_140010720; "\t"
0x140004b78  cmp     [rcx+rax*4], r15d
0x140004b7c  jz      short loc_140004BAB
0x140004b7e  mov     al, dl
0x140004b80  cmp     dl, 6
0x140004b83  jb      short loc_140004B6A
0x140004b85  xor     ebx, ebx
0x140004b87  mov     rcx, cs:WPP_GLOBAL_Control
0x140004b8e  mov     eax, [rcx+2Ch]
0x140004b91  test    al, 8
0x140004b93  jz      loc_140004D6D
0x140004b99  cmp     byte ptr [rcx+29h], 2
0x140004b9d  jb      loc_140004D6D
0x140004ba3  mov     dl, sil
0x140004ba6  jmp     loc_140004D6F
0x140004bab  movsx   r8d, byte ptr [rbp+27Ch]
0x140004bb3  mov     rcx, cs:WPP_GLOBAL_Control
0x140004bba  mov     eax, [rcx+2Ch]
0x140004bbd  test    al, 4
0x140004bbf  jz      short loc_140004BCC
0x140004bc1  cmp     byte ptr [rcx+29h], 4
0x140004bc5  jb      short loc_140004BCC
0x140004bc7  mov     al, sil
0x140004bca  jmp     short loc_140004BCE
0x140004bcc  xor     al, al
0x140004bce  mov     r9, [rcx+40h]
0x140004bd2  mov     r13d, r8d
0x140004bd5  mov     rcx, [rcx+18h]
0x140004bd9  movsx   r12d, dl
0x140004bdd  mov     dl, al
0x140004bdf  mov     [rsp+98h+var_48], r12d
0x140004be4  mov     [rsp+98h+var_50], r8d
0x140004be9  lea     r8, WPP_d9e027c83b54391969aefc6614c696e6_Traceguids
0x140004bf0  mov     [rsp+98h+var_58], rbp
0x140004bf5  mov     [rsp+98h+var_60], r8
0x140004bfa  mov     [rsp+98h+var_68], 46h ; 'F'
0x140004c01  mov     [rsp+98h+var_70], 3
0x140004c09  call    WPP_RECORDER_AND_TRACE_SF_qdd
0x140004c0e  test    rdi, rdi
0x140004c11  jz      short loc_140004C19
0x140004c13  mov     dword ptr [rdi], 0
0x140004c19  mov     rax, [rbp+68h]
0x140004c1d  mov     [rsp+98h+arg_10], rax
0x140004c25  jmp     short loc_140004CA2
0x140004c27  cmp     byte ptr [rbx+4], 2
0x140004c2b  jnz     short loc_140004CA2
0x140004c2d  lea     rax, [rsp+98h+arg_0]
0x140004c35  mov     [rsp+98h+arg_0], 0
0x140004c3d  mov     r9b, sil; unsigned __int8
0x140004c40  mov     [rsp+98h+var_78], rax; unsigned __int8 *
0x140004c45  mov     rdx, rbx; struct _USB_INTERFACE_DESCRIPTOR *
0x140004c48  mov     rcx, rbp; struct _DEVICE_EXTENSION *
0x140004c4b  call    ?BthUsb_FindUsbdPipeDescriptor@@_Y2PAGE@@APEAU_USB_ENDPOINT_DESCRIPTOR@@PEAU_DEVICE_EXTENSION@@PEAU_USB_INTERFACE_DESCRIPTOR@@EEPEAE@Z; BthUsb_FindUsbdPipeDescriptor(_DEVICE_EXTENSION *,_USB_INTERFACE_DESCRIPTOR *,uchar,uchar,uchar *)
0x140004c50  mov     r14, rax
0x140004c53  test    rax, rax
0x140004c56  jz      short loc_140004CA2
0x140004c58  cmp     [rsp+98h+arg_0], 0
0x140004c60  jnz     short loc_140004CA2
0x140004c62  lea     rax, [rsp+98h+arg_0]
0x140004c6a  mov     [rsp+98h+arg_0], 0
0x140004c72  xor     r9d, r9d; unsigned __int8
0x140004c75  mov     [rsp+98h+var_78], rax; int
0x140004c7a  mov     rdx, rbx; struct _USB_INTERFACE_DESCRIPTOR *
0x140004c7d  mov     rcx, rbp; struct _DEVICE_EXTENSION *
0x140004c80  call    ?BthUsb_FindUsbdPipeDescriptor@@_Y2PAGE@@APEAU_USB_ENDPOINT_DESCRIPTOR@@PEAU_DEVICE_EXTENSION@@PEAU_USB_INTERFACE_DESCRIPTOR@@EEPEAE@Z; BthUsb_FindUsbdPipeDescriptor(_DEVICE_EXTENSION *,_USB_INTERFACE_DESCRIPTOR *,uchar,uchar,uchar *)
0x140004c85  mov     rcx, rax
0x140004c88  test    rax, rax
0x140004c8b  jz      short loc_140004CA2
0x140004c8d  cmp     [rsp+98h+arg_0], 0
0x140004c95  jnz     short loc_140004CA2
0x140004c97  movzx   eax, word ptr [r14+4]
0x140004c9c  cmp     ax, [rcx+4]
0x140004ca0  jz      short loc_140004CE5
0x140004ca2  mov     r9d, r12d; int
0x140004ca5  lea     rdx, [rsp+98h+arg_10]; void **
0x140004cad  mov     r8d, r13d; int
0x140004cb0  mov     rcx, rbp; struct _DEVICE_EXTENSION *
0x140004cb3  call    ?BthUsb_GetInterfaceDescriptor@@_Y2PAGE@@APEAU_USB_INTERFACE_DESCRIPTOR@@PEAU_DEVICE_EXTENSION@@PEAPEAXJJJJJ@Z; BthUsb_GetInterfaceDescriptor(_DEVICE_EXTENSION *,void * *,long,long,long,long,long)
0x140004cb8  mov     rbx, rax
0x140004cbb  test    rax, rax
0x140004cbe  jnz     loc_140004C27
0x140004cc4  xor     ebx, ebx
0x140004cc6  mov     r14d, 0C0000272h
0x140004ccc  mov     rcx, cs:WPP_GLOBAL_Control
0x140004cd3  mov     eax, [rcx+2Ch]
0x140004cd6  test    al, 4
0x140004cd8  jz      short loc_140004CF1
0x140004cda  cmp     byte ptr [rcx+29h], 4
0x140004cde  jb      short loc_140004CF1
0x140004ce0  mov     dl, sil
0x140004ce3  jmp     short loc_140004CF3
0x140004ce5  test    rdi, rdi
0x140004ce8  jz      short loc_140004CEC
0x140004cea  mov     [rdi], eax
0x140004cec  xor     r14d, r14d
0x140004cef  jmp     short loc_140004CCC
0x140004cf1  xor     dl, dl
0x140004cf3  mov     r9, [rcx+40h]
0x140004cf7  lea     r8, WPP_d9e027c83b54391969aefc6614c696e6_Traceguids
0x140004cfe  mov     rcx, [rcx+18h]
0x140004d02  mov     dword ptr [rsp+98h+var_58], r14d
0x140004d07  mov     [rsp+98h+var_60], r8
0x140004d0c  mov     [rsp+98h+var_68], 47h ; 'G'
0x140004d13  mov     [rsp+98h+var_70], 3
0x140004d1b  mov     byte ptr [rsp+98h+var_78], 4
0x140004d20  call    WPP_RECORDER_AND_TRACE_SF_D
0x140004d25  test    r14d, r14d
0x140004d28  js      loc_140004B85
0x140004d2e  test    rbx, rbx
0x140004d31  jz      loc_140004B87
0x140004d37  mov     rcx, cs:WPP_GLOBAL_Control
0x140004d3e  mov     eax, [rcx+2Ch]
0x140004d41  test    al, 8
0x140004d43  jz      short loc_140004D4B
0x140004d45  cmp     byte ptr [rcx+29h], 4
0x140004d49  jnb     short loc_140004D4E
0x140004d4b  xor     sil, sil
0x140004d4e  movzx   eax, byte ptr [rbx+3]
0x140004d52  mov     dl, sil
0x140004d55  mov     r9, [rcx+40h]
0x140004d59  mov     rcx, [rcx+18h]
0x140004d5d  mov     [rsp+98h+var_50], r15d
0x140004d62  mov     dword ptr [rsp+98h+var_58], eax
0x140004d66  call    WPP_RECORDER_AND_TRACE_SF_DL
0x140004d6b  jmp     short loc_140004DBD
0x140004d6d  xor     dl, dl
0x140004d6f  mov     r9, [rcx+40h]
0x140004d73  lea     rax, WPP_89eaa7be148f36a90e353489c15db76f_Traceguids
0x140004d7a  mov     rcx, [rcx+18h]
0x140004d7e  mov     r8b, sil
0x140004d81  mov     dword ptr [rsp+98h+var_58], r15d
0x140004d86  mov     [rsp+98h+var_60], rax
0x140004d8b  mov     [rsp+98h+var_68], 0Ch
0x140004d92  mov     [rsp+98h+var_70], 4
0x140004d9a  mov     byte ptr [rsp+98h+var_78], 2
0x140004d9f  call    WPP_RECORDER_AND_TRACE_SF_L
0x140004da4  mov     ecx, [rbp+2A0h]
0x140004daa  cmp     r15d, ecx
0x140004dad  ja      short loc_140004DBD
0x140004daf  mov     rbx, [rbp+288h]
0x140004db6  test    rdi, rdi
0x140004db9  jz      short loc_140004DBD
0x140004dbb  mov     [rdi], ecx
0x140004dbd  mov     rax, rbx
0x140004dc0  mov     rbx, [rsp+98h+arg_8]
0x140004dc8  add     rsp, 60h
0x140004dcc  pop     r15
0x140004dce  pop     r14
0x140004dd0  pop     r13
0x140004dd2  pop     r12
0x140004dd4  pop     rdi
0x140004dd5  pop     rsi
0x140004dd6  pop     rbp
0x140004dd7  retn
```
