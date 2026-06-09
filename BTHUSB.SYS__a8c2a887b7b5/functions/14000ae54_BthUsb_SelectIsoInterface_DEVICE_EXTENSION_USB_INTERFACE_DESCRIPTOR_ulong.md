# BthUsb_SelectIsoInterface(_DEVICE_EXTENSION *,_USB_INTERFACE_DESCRIPTOR *,ulong)

- ea: `0x14000ae54`
- end: `0x14000b0b3`
- name: `?BthUsb_SelectIsoInterface@@YAJPEAU_DEVICE_EXTENSION@@PEAU_USB_INTERFACE_DESCRIPTOR@@K@Z`
- size: `607`
- prototype: `__int64 __fastcall(struct _DEVICE_EXTENSION *, struct _USB_INTERFACE_DESCRIPTOR *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x140005600`

## callees

- `0x14000175c`
- `0x1400017d4`
- `0x140002dcc`
- `0x14000ae54`
- `0x14000b400`
- `0x14001b264`
- `0x14001bd90`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14000aede`
- `ntoskrnl!ExAllocatePool2` at `0x14000aede`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b053`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b053`

## pseudocode

```c
__int64 __fastcall BthUsb_SelectIsoInterface(struct _DEVICE_EXTENSION *a1, struct _USB_INTERFACE_DESCRIPTOR *a2)
{
  struct _USB_INTERFACE_DESCRIPTOR *v2; // rbp
  char v4; // di
  unsigned int bNumEndpoints; // ebx
  unsigned __int64 Pool2; // rax
  int v7; // edx
  int v8; // r8d
  unsigned __int64 v9; // r14
  int v10; // edx
  int v11; // r8d
  int v12; // ebx
  __int64 v13; // rdx
  __int64 v14; // rcx
  int v15; // edx
  int v16; // edx
  int v17; // r8d

  v2 = a2;
  v4 = 1;
  LOBYTE(a2) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  WPP_RECORDER_AND_TRACE_SF_qqD(
    WPP_GLOBAL_Control->AttachedDevice,
    (_DWORD)a2,
    (unsigned int)WPP_d9e027c83b54391969aefc6614c696e6_Traceguids,
    WPP_GLOBAL_Control->DeviceExtension);
  bNumEndpoints = v2->bNumEndpoints;
  Pool2 = ExAllocatePool2(64, 24 * bNumEndpoints + 56, 1111642965);
  v9 = Pool2;
  if ( Pool2 )
  {
    *(_WORD *)(Pool2 + 2) = 1;
    *(_WORD *)Pool2 = 24 * bNumEndpoints + 56;
    v13 = 0;
    *(_BYTE *)(Pool2 + 35) = v2->bAlternateSetting;
    *(_BYTE *)(Pool2 + 34) = v2->bInterfaceNumber;
    *(_QWORD *)(Pool2 + 24) = a1->ConfigHandle;
    for ( *(_WORD *)(Pool2 + 32) = 24 * (bNumEndpoints + 1);
          (unsigned int)v13 < bNumEndpoints;
          *(_DWORD *)(Pool2 + 8 * v14 + 72) = 4096 )
    {
      v14 = 3 * v13;
      v13 = (unsigned int)(v13 + 1);
    }
    v12 = USBCallSyncEx(a1->TopOfStack, Pool2, 500, &a1->RemoveLock);
    if ( v12 >= 0 )
    {
      v12 = BthUsb_InitializeIsochPipes(a1, (struct _USBD_INTERFACE_INFORMATION *)(v9 + 32));
      if ( v12 >= 0 )
      {
        v12 = 0;
      }
      else
      {
        LOBYTE(v16) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
        WPP_RECORDER_AND_TRACE_SF_D(
          WPP_GLOBAL_Control->AttachedDevice,
          v16,
          v17,
          WPP_GLOBAL_Control->DeviceExtension,
          2,
          3,
          76,
          (__int64)WPP_d9e027c83b54391969aefc6614c696e6_Traceguids,
          v12);
      }
    }
    else
    {
      LOBYTE(v15) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
      WPP_RECORDER_AND_TRACE_SF_DD(
        WPP_GLOBAL_Control->AttachedDevice,
        v15,
        (_DWORD)WPP_GLOBAL_Control,
        WPP_GLOBAL_Control->DeviceExtension);
    }
    ExFreePoolWithTag((PVOID)v9, 0);
  }
  else
  {
    LOBYTE(v7) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
    WPP_RECORDER_AND_TRACE_SF_(
      WPP_GLOBAL_Control->AttachedDevice,
      v7,
      v8,
      WPP_GLOBAL_Control->DeviceExtension,
      2,
      3,
      74,
      (__int64)WPP_d9e027c83b54391969aefc6614c696e6_Traceguids);
    v12 = -1073741670;
  }
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
    v4 = 0;
  LOBYTE(v10) = v4;
  WPP_RECORDER_AND_TRACE_SF_D(
    WPP_GLOBAL_Control->AttachedDevice,
    v10,
    v11,
    WPP_GLOBAL_Control->DeviceExtension,
    4,
    3,
    77,
    (__int64)WPP_d9e027c83b54391969aefc6614c696e6_Traceguids,
    v12);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x14000ae54  push    rbx
0x14000ae56  push    rbp
0x14000ae57  push    rsi
0x14000ae58  push    rdi
0x14000ae59  push    r14
0x14000ae5b  push    r15
0x14000ae5d  sub     rsp, 68h
0x14000ae61  mov     rbp, rdx
0x14000ae64  mov     rsi, rcx
0x14000ae67  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ae6e  mov     edi, 1
0x14000ae73  mov     eax, [rcx+2Ch]
0x14000ae76  test    al, 4
0x14000ae78  jz      short loc_14000AE85
0x14000ae7a  cmp     byte ptr [rcx+29h], 4
0x14000ae7e  jb      short loc_14000AE85
0x14000ae80  mov     dl, dil
0x14000ae83  jmp     short loc_14000AE87
0x14000ae85  xor     dl, dl
0x14000ae87  mov     r9, [rcx+40h]
0x14000ae8b  lea     r8, WPP_d9e027c83b54391969aefc6614c696e6_Traceguids
0x14000ae92  mov     rcx, [rcx+18h]
0x14000ae96  mov     [rsp+98h+var_48], 1000h
0x14000ae9e  mov     [rsp+98h+var_50], rbp
0x14000aea3  mov     [rsp+98h+var_58], rsi
0x14000aea8  mov     [rsp+98h+var_60], r8
0x14000aead  mov     [rsp+98h+var_68], 48h ; 'H'
0x14000aeb4  mov     [rsp+98h+var_70], 3
0x14000aebc  call    WPP_RECORDER_AND_TRACE_SF_qqD
0x14000aec1  movzx   ebx, byte ptr [rbp+4]
0x14000aec5  mov     ecx, 40h ; '@'
0x14000aeca  mov     r8d, 42425355h
0x14000aed0  lea     eax, [rbx+rbx*2]
0x14000aed3  lea     r15d, ds:38h[rax*8]
0x14000aedb  mov     edx, r15d
0x14000aede  call    cs:__imp_ExAllocatePool2
0x14000aee5  nop     dword ptr [rax+rax+00h]
0x14000aeea  mov     r14, rax
0x14000aeed  test    rax, rax
0x14000aef0  jnz     short loc_14000AF44
0x14000aef2  mov     rcx, cs:WPP_GLOBAL_Control
0x14000aef9  mov     eax, [rcx+2Ch]
0x14000aefc  test    al, 4
0x14000aefe  jz      short loc_14000AF0B
0x14000af00  cmp     byte ptr [rcx+29h], 2
0x14000af04  jb      short loc_14000AF0B
0x14000af06  mov     dl, dil
0x14000af09  jmp     short loc_14000AF0D
0x14000af0b  xor     dl, dl
0x14000af0d  mov     r9, [rcx+40h]
0x14000af11  lea     rsi, WPP_d9e027c83b54391969aefc6614c696e6_Traceguids
0x14000af18  mov     rcx, [rcx+18h]
0x14000af1c  mov     [rsp+98h+var_60], rsi
0x14000af21  mov     [rsp+98h+var_68], 4Ah ; 'J'
0x14000af28  mov     [rsp+98h+var_70], 3
0x14000af30  mov     [rsp+98h+var_78], 2
0x14000af35  call    WPP_RECORDER_AND_TRACE_SF_
0x14000af3a  mov     ebx, 0C000009Ah
0x14000af3f  jmp     loc_14000B05F
0x14000af44  mov     [rax+2], di
0x14000af48  lea     ecx, [rdi+rbx]
0x14000af4b  mov     [rax], r15w
0x14000af4f  xor     edx, edx
0x14000af51  mov     al, [rbp+3]
0x14000af54  mov     [r14+23h], al
0x14000af58  mov     al, [rbp+2]
0x14000af5b  mov     [r14+22h], al
0x14000af5f  mov     rax, [rsi+58h]
0x14000af63  mov     [r14+18h], rax
0x14000af67  movzx   eax, cx
0x14000af6a  add     ax, ax
0x14000af6d  add     cx, ax
0x14000af70  shl     cx, 3
0x14000af74  mov     [r14+20h], cx
0x14000af79  test    ebx, ebx
0x14000af7b  jz      short loc_14000AF90
0x14000af7d  lea     rcx, [rdx+rdx*2]
0x14000af81  add     edx, edi
0x14000af83  mov     dword ptr [r14+rcx*8+48h], 1000h
0x14000af8c  cmp     edx, ebx
0x14000af8e  jb      short loc_14000AF7D
0x14000af90  mov     rcx, [rsi+28h]; Tag
0x14000af94  lea     r9, [rsi+30h]
0x14000af98  mov     r8d, 1F4h
0x14000af9e  mov     rdx, r14
0x14000afa1  call    USBCallSyncEx
0x14000afa6  mov     ebx, eax
0x14000afa8  test    eax, eax
0x14000afaa  jns     short loc_14000AFE5
0x14000afac  mov     r8, cs:WPP_GLOBAL_Control
0x14000afb3  mov     ecx, [r8+2Ch]
0x14000afb7  test    cl, 4
0x14000afba  jz      short loc_14000AFC8
0x14000afbc  cmp     byte ptr [r8+29h], 2
0x14000afc1  jb      short loc_14000AFC8
0x14000afc3  mov     dl, dil
0x14000afc6  jmp     short loc_14000AFCA
0x14000afc8  xor     dl, dl
0x14000afca  mov     eax, [r14+4]
0x14000afce  mov     r9, [r8+40h]
0x14000afd2  mov     rcx, [r8+18h]
0x14000afd6  mov     dword ptr [rsp+98h+var_50], eax
0x14000afda  mov     dword ptr [rsp+98h+var_58], ebx
0x14000afde  call    WPP_RECORDER_AND_TRACE_SF_DD
0x14000afe3  jmp     short loc_14000B047
0x14000afe5  lea     rdx, [r14+20h]; struct _USBD_INTERFACE_INFORMATION *
0x14000afe9  mov     rcx, rsi; struct _DEVICE_EXTENSION *
0x14000afec  call    ?BthUsb_InitializeIsochPipes@@_Y2PAGE@@AJPEAU_DEVICE_EXTENSION@@PEAU_USBD_INTERFACE_INFORMATION@@@Z; BthUsb_InitializeIsochPipes(_DEVICE_EXTENSION *,_USBD_INTERFACE_INFORMATION *)
0x14000aff1  mov     ebx, eax
0x14000aff3  test    eax, eax
0x14000aff5  jns     short loc_14000B045
0x14000aff7  mov     rcx, cs:WPP_GLOBAL_Control
0x14000affe  mov     eax, [rcx+2Ch]
0x14000b001  test    al, 4
0x14000b003  jz      short loc_14000B010
0x14000b005  cmp     byte ptr [rcx+29h], 2
0x14000b009  jb      short loc_14000B010
0x14000b00b  mov     dl, dil
0x14000b00e  jmp     short loc_14000B012
0x14000b010  xor     dl, dl
0x14000b012  mov     r9, [rcx+40h]
0x14000b016  lea     rsi, WPP_d9e027c83b54391969aefc6614c696e6_Traceguids
0x14000b01d  mov     rcx, [rcx+18h]
0x14000b021  mov     dword ptr [rsp+98h+var_58], ebx
0x14000b025  mov     [rsp+98h+var_60], rsi
0x14000b02a  mov     [rsp+98h+var_68], 4Ch ; 'L'
0x14000b031  mov     [rsp+98h+var_70], 3
0x14000b039  mov     [rsp+98h+var_78], 2
0x14000b03e  call    WPP_RECORDER_AND_TRACE_SF_D
0x14000b043  jmp     short loc_14000B04E
0x14000b045  xor     ebx, ebx
0x14000b047  lea     rsi, WPP_d9e027c83b54391969aefc6614c696e6_Traceguids
0x14000b04e  xor     edx, edx; Tag
0x14000b050  mov     rcx, r14; P
0x14000b053  call    cs:__imp_ExFreePoolWithTag
0x14000b05a  nop     dword ptr [rax+rax+00h]
0x14000b05f  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b066  mov     eax, [rcx+2Ch]
0x14000b069  test    al, 4
0x14000b06b  jz      short loc_14000B073
0x14000b06d  cmp     byte ptr [rcx+29h], 4
0x14000b071  jnb     short loc_14000B076
0x14000b073  xor     dil, dil
0x14000b076  mov     r9, [rcx+40h]
0x14000b07a  mov     dl, dil
0x14000b07d  mov     rcx, [rcx+18h]
0x14000b081  mov     dword ptr [rsp+98h+var_58], ebx
0x14000b085  mov     [rsp+98h+var_60], rsi
0x14000b08a  mov     [rsp+98h+var_68], 4Dh ; 'M'
0x14000b091  mov     [rsp+98h+var_70], 3
0x14000b099  mov     [rsp+98h+var_78], 4
0x14000b09e  call    WPP_RECORDER_AND_TRACE_SF_D
0x14000b0a3  mov     eax, ebx
0x14000b0a5  add     rsp, 68h
0x14000b0a9  pop     r15
0x14000b0ab  pop     r14
0x14000b0ad  pop     rdi
0x14000b0ae  pop     rsi
0x14000b0af  pop     rbp
0x14000b0b0  pop     rbx
0x14000b0b1  retn
```
