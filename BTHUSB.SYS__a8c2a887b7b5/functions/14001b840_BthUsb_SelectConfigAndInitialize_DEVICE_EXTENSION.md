# BthUsb_SelectConfigAndInitialize(_DEVICE_EXTENSION *)

- ea: `0x14001b840`
- end: `0x14001bd88`
- name: `?BthUsb_SelectConfigAndInitialize@@_Y2PAGE@@AJPEAU_DEVICE_EXTENSION@@@Z`
- size: `1352`
- prototype: `__int64 __fastcall(struct _DEVICE_EXTENSION *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting`

## callers

- `0x140018b90`

## callees

- `0x14000175c`
- `0x1400017d4`
- `0x140006db0`
- `0x14001ac7c`
- `0x14001b264`
- `0x14001b310`
- `0x14001b404`
- `0x14001b560`
- `0x14001b840`
- `0x14001bd90`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14001b8c1`
- `ntoskrnl!ExAllocatePool2` at `0x14001b8c1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001bcff`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001bd10`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001bcff`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001bd10`
- `USBD!USBD_CreateConfigurationRequestEx` at `0x14001b969`
- `USBD!USBD_CreateConfigurationRequestEx` at `0x14001b969`

## pseudocode

```c
__int64 __fastcall BthUsb_SelectConfigAndInitialize(struct _DEVICE_EXTENSION *a1, __int64 a2, int a3)
{
  char v4; // di
  bool v5; // dl
  _USB_CONFIGURATION_DESCRIPTOR *ConfigDescriptor; // rsi
  unsigned int bNumInterfaces; // r13d
  int v8; // r8d
  struct _USBD_INTERFACE_LIST_ENTRY *v9; // r14
  char v11; // r15
  unsigned int i; // ebx
  struct _USB_INTERFACE_DESCRIPTOR *InterfaceDescriptor; // rax
  int v14; // r8d
  __int64 v15; // rcx
  PURB ConfigurationRequest; // rax
  int v17; // edx
  int v18; // r8d
  bool v19; // dl
  int v20; // ebx
  int v21; // edx
  int v22; // r8d
  unsigned int v23; // r12d
  struct _USBD_INTERFACE_INFORMATION *v24; // rsi
  int v25; // edx
  int v26; // r8d
  int v27; // r8d
  int v28; // r8d
  int v29; // edx
  int v30; // r8d
  int v31; // [rsp+20h] [rbp-68h]
  int v32; // [rsp+28h] [rbp-60h]
  int v33; // [rsp+30h] [rbp-58h]
  void *v34; // [rsp+90h] [rbp+8h] BYREF
  __int64 Pool2; // [rsp+98h] [rbp+10h]
  PVOID P; // [rsp+A0h] [rbp+18h]

  v4 = 1;
  v5 = (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  WPP_RECORDER_AND_TRACE_SF_(
    WPP_GLOBAL_Control->AttachedDevice,
    v5,
    a3,
    WPP_GLOBAL_Control->DeviceExtension,
    4,
    2,
    33,
    (__int64)WPP_d9e027c83b54391969aefc6614c696e6_Traceguids);
  ConfigDescriptor = a1->ConfigDescriptor;
  bNumInterfaces = ConfigDescriptor->bNumInterfaces;
  Pool2 = ExAllocatePool2(64, 16 * (bNumInterfaces + 1), 1111642965);
  v9 = (struct _USBD_INTERFACE_LIST_ENTRY *)Pool2;
  if ( !Pool2 )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      v4 = 0;
    WPP_RECORDER_AND_TRACE_SF_(
      WPP_GLOBAL_Control->AttachedDevice,
      v4,
      v8,
      WPP_GLOBAL_Control->DeviceExtension,
      2,
      2,
      34,
      (__int64)WPP_d9e027c83b54391969aefc6614c696e6_Traceguids);
    return 3221225626LL;
  }
  v11 = 0;
  v34 = ConfigDescriptor;
  for ( i = 0; i < bNumInterfaces; v9[v15].InterfaceDescriptor = InterfaceDescriptor )
  {
    InterfaceDescriptor = BthUsb_GetInterfaceDescriptor(a1, &v34, -1, 0, v31, v32, v33);
    if ( !InterfaceDescriptor )
    {
      v19 = (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
      WPP_RECORDER_AND_TRACE_SF_(
        WPP_GLOBAL_Control->AttachedDevice,
        v19,
        v14,
        WPP_GLOBAL_Control->DeviceExtension,
        2,
        2,
        35,
        (__int64)WPP_d9e027c83b54391969aefc6614c696e6_Traceguids);
      v20 = -1073741811;
      goto LABEL_64;
    }
    v15 = i++;
  }
  ConfigurationRequest = USBD_CreateConfigurationRequestEx(ConfigDescriptor, v9);
  P = ConfigurationRequest;
  if ( !ConfigurationRequest )
  {
    LOBYTE(v17) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
    WPP_RECORDER_AND_TRACE_SF_D(
      WPP_GLOBAL_Control->AttachedDevice,
      v17,
      v18,
      WPP_GLOBAL_Control->DeviceExtension,
      2,
      2,
      36,
      (__int64)WPP_d9e027c83b54391969aefc6614c696e6_Traceguids,
      0);
    v20 = -1073741670;
    goto LABEL_64;
  }
  v20 = USBCallSyncEx(a1->TopOfStack, (unsigned __int64)ConfigurationRequest, 500, &a1->RemoveLock);
  if ( v20 < 0 )
  {
    LOBYTE(v21) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
    WPP_RECORDER_AND_TRACE_SF_D(
      WPP_GLOBAL_Control->AttachedDevice,
      v21,
      v22,
      WPP_GLOBAL_Control->DeviceExtension,
      2,
      2,
      37,
      (__int64)WPP_d9e027c83b54391969aefc6614c696e6_Traceguids,
      v20);
    goto LABEL_63;
  }
  v23 = 0;
  LOBYTE(v34) = 0;
  a1->ConfigHandle = (void *)*((_QWORD *)P + 4);
  if ( !bNumInterfaces )
    goto LABEL_63;
  while ( 1 )
  {
    v24 = *(struct _USBD_INTERFACE_INFORMATION **)(Pool2 + 16LL * v23 + 8);
    LOBYTE(v21) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
    WPP_RECORDER_AND_TRACE_SF_dd(
      WPP_GLOBAL_Control->AttachedDevice,
      v21,
      v24->InterfaceNumber,
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      2,
      38,
      (__int64)WPP_d9e027c83b54391969aefc6614c696e6_Traceguids,
      v24->InterfaceNumber,
      v24->AlternateSetting);
    LOBYTE(v25) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
    WPP_RECORDER_AND_TRACE_SF_D(
      WPP_GLOBAL_Control->AttachedDevice,
      v25,
      v26,
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      2,
      39,
      (__int64)WPP_d9e027c83b54391969aefc6614c696e6_Traceguids,
      v24->NumberOfPipes);
    if ( !v24->NumberOfPipes )
      goto LABEL_53;
    if ( !v11 && BthUsb_IsNonIsochInterface(v24) )
      break;
    if ( (_BYTE)v34 || !BthUsb_IsIsochInterface(v24) )
      goto LABEL_53;
    v20 = BthUsb_InitializeIsochPipes(a1, v24);
    if ( v20 >= 0 )
    {
      LOBYTE(v34) = 1;
      a1->Sco.OffInterface = *(_USB_INTERFACE_DESCRIPTOR **)(Pool2 + 16LL * v23);
LABEL_54:
      if ( v11 )
        goto LABEL_55;
      goto LABEL_56;
    }
    LOBYTE(v21) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
    WPP_RECORDER_AND_TRACE_SF_D(
      WPP_GLOBAL_Control->AttachedDevice,
      v21,
      v28,
      WPP_GLOBAL_Control->DeviceExtension,
      2,
      2,
      43,
      (__int64)WPP_d9e027c83b54391969aefc6614c696e6_Traceguids,
      v20);
    v20 = 0;
LABEL_56:
    if ( ++v23 >= bNumInterfaces )
    {
LABEL_55:
      v9 = (struct _USBD_INTERFACE_LIST_ENTRY *)Pool2;
      goto LABEL_63;
    }
  }
  v20 = BthUsb_InitializeNonIsochPipes(a1, v24);
  if ( v20 >= 0 )
  {
    v11 = 1;
LABEL_53:
    if ( (_BYTE)v34 )
      goto LABEL_54;
    goto LABEL_56;
  }
  LOBYTE(v21) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
  WPP_RECORDER_AND_TRACE_SF_D(
    WPP_GLOBAL_Control->AttachedDevice,
    v21,
    v27,
    WPP_GLOBAL_Control->DeviceExtension,
    2,
    2,
    42,
    (__int64)WPP_d9e027c83b54391969aefc6614c696e6_Traceguids,
    v20);
  v9 = (struct _USBD_INTERFACE_LIST_ENTRY *)Pool2;
LABEL_63:
  ExFreePoolWithTag(P, 0);
LABEL_64:
  ExFreePoolWithTag(v9, 0);
  if ( v20 >= 0 && !v11 )
    v20 = -1073741823;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
    v4 = 0;
  LOBYTE(v29) = v4;
  WPP_RECORDER_AND_TRACE_SF_D(
    WPP_GLOBAL_Control->AttachedDevice,
    v29,
    v30,
    WPP_GLOBAL_Control->DeviceExtension,
    4,
    2,
    44,
    (__int64)WPP_d9e027c83b54391969aefc6614c696e6_Traceguids,
    v20);
  return (unsigned int)v20;
}

```

## disassembly

```asm
0x14001b840  mov     [rsp+arg_18], rbx
0x14001b845  push    rbp
0x14001b846  push    rsi
0x14001b847  push    rdi
0x14001b848  push    r12
0x14001b84a  push    r13
0x14001b84c  push    r14
0x14001b84e  push    r15
0x14001b850  sub     rsp, 50h
0x14001b854  mov     rbp, rcx
0x14001b857  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b85e  mov     edi, 1
0x14001b863  mov     eax, [rcx+2Ch]
0x14001b866  lea     r12d, [rdi+1]
0x14001b86a  test    r12b, al
0x14001b86d  jz      short loc_14001B87A
0x14001b86f  cmp     byte ptr [rcx+29h], 4
0x14001b873  jb      short loc_14001B87A
0x14001b875  mov     dl, dil
0x14001b878  jmp     short loc_14001B87C
0x14001b87a  xor     dl, dl
0x14001b87c  mov     r9, [rcx+40h]
0x14001b880  lea     rbx, WPP_d9e027c83b54391969aefc6614c696e6_Traceguids
0x14001b887  mov     rcx, [rcx+18h]
0x14001b88b  mov     [rsp+88h+var_50], rbx
0x14001b890  mov     word ptr [rsp+88h+var_58], 21h ; '!'; int
0x14001b897  mov     [rsp+88h+var_60], r12d; int
0x14001b89c  mov     byte ptr [rsp+88h+var_68], 4; int
0x14001b8a1  call    WPP_RECORDER_AND_TRACE_SF_
0x14001b8a6  mov     rsi, [rbp+68h]
0x14001b8aa  mov     ecx, 40h ; '@'
0x14001b8af  mov     r8d, 42425355h
0x14001b8b5  movzx   r13d, byte ptr [rsi+4]
0x14001b8ba  lea     edx, [r13+1]
0x14001b8be  shl     edx, 4
0x14001b8c1  call    cs:__imp_ExAllocatePool2
0x14001b8c8  nop     dword ptr [rax+rax+00h]
0x14001b8cd  mov     [rsp+88h+arg_8], rax
0x14001b8d5  mov     r14, rax
0x14001b8d8  test    rax, rax
0x14001b8db  jnz     short loc_14001B925
0x14001b8dd  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b8e4  mov     eax, [rcx+2Ch]
0x14001b8e7  test    r12b, al
0x14001b8ea  jz      short loc_14001B8F2
0x14001b8ec  cmp     [rcx+29h], r12b
0x14001b8f0  jnb     short loc_14001B8F5
0x14001b8f2  xor     dil, dil
0x14001b8f5  mov     r9, [rcx+40h]
0x14001b8f9  mov     dl, dil
0x14001b8fc  mov     rcx, [rcx+18h]
0x14001b900  mov     [rsp+88h+var_50], rbx
0x14001b905  mov     word ptr [rsp+88h+var_58], 22h ; '"'
0x14001b90c  mov     [rsp+88h+var_60], r12d
0x14001b911  mov     byte ptr [rsp+88h+var_68], r12b
0x14001b916  call    WPP_RECORDER_AND_TRACE_SF_
0x14001b91b  mov     eax, 0C000009Ah
0x14001b920  jmp     loc_14001BD6F
0x14001b925  xor     r15b, r15b
0x14001b928  mov     [rsp+88h+arg_0], rsi
0x14001b930  xor     ebx, ebx
0x14001b932  test    r13d, r13d
0x14001b935  jz      short loc_14001B963
0x14001b937  xor     r9d, r9d; int
0x14001b93a  lea     rdx, [rsp+88h+arg_0]; void **
0x14001b942  or      r8d, 0FFFFFFFFh; int
0x14001b946  mov     rcx, rbp; struct _DEVICE_EXTENSION *
0x14001b949  call    ?BthUsb_GetInterfaceDescriptor@@_Y2PAGE@@APEAU_USB_INTERFACE_DESCRIPTOR@@PEAU_DEVICE_EXTENSION@@PEAPEAXJJJJJ@Z; BthUsb_GetInterfaceDescriptor(_DEVICE_EXTENSION *,void * *,long,long,long,long,long)
0x14001b94e  test    rax, rax
0x14001b951  jz      short loc_14001B9A0
0x14001b953  mov     ecx, ebx
0x14001b955  add     ebx, edi
0x14001b957  add     rcx, rcx
0x14001b95a  mov     [r14+rcx*8], rax
0x14001b95e  cmp     ebx, r13d
0x14001b961  jb      short loc_14001B937
0x14001b963  mov     rdx, r14; InterfaceList
0x14001b966  mov     rcx, rsi; ConfigurationDescriptor
0x14001b969  call    cs:__imp_USBD_CreateConfigurationRequestEx
0x14001b970  nop     dword ptr [rax+rax+00h]
0x14001b975  mov     [rsp+88h+P], rax
0x14001b97d  test    rax, rax
0x14001b980  jnz     loc_14001BA2E
0x14001b986  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b98d  mov     eax, [rcx+2Ch]
0x14001b990  test    r12b, al
0x14001b993  jz      short loc_14001B9F0
0x14001b995  cmp     [rcx+29h], r12b
0x14001b999  jb      short loc_14001B9F0
0x14001b99b  mov     dl, dil
0x14001b99e  jmp     short loc_14001B9F2
0x14001b9a0  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b9a7  mov     eax, [rcx+2Ch]
0x14001b9aa  test    r12b, al
0x14001b9ad  jz      short loc_14001B9BA
0x14001b9af  cmp     [rcx+29h], r12b
0x14001b9b3  jb      short loc_14001B9BA
0x14001b9b5  mov     dl, dil
0x14001b9b8  jmp     short loc_14001B9BC
0x14001b9ba  xor     dl, dl
0x14001b9bc  mov     r9, [rcx+40h]
0x14001b9c0  lea     rsi, WPP_d9e027c83b54391969aefc6614c696e6_Traceguids
0x14001b9c7  mov     rcx, [rcx+18h]
0x14001b9cb  mov     [rsp+88h+var_50], rsi
0x14001b9d0  mov     word ptr [rsp+88h+var_58], 23h ; '#'
0x14001b9d7  mov     [rsp+88h+var_60], r12d
0x14001b9dc  mov     byte ptr [rsp+88h+var_68], r12b
0x14001b9e1  call    WPP_RECORDER_AND_TRACE_SF_
0x14001b9e6  mov     ebx, 0C000000Dh
0x14001b9eb  jmp     loc_14001BD0B
0x14001b9f0  xor     dl, dl
0x14001b9f2  mov     r9, [rcx+40h]
0x14001b9f6  lea     rsi, WPP_d9e027c83b54391969aefc6614c696e6_Traceguids
0x14001b9fd  mov     rcx, [rcx+18h]
0x14001ba01  mov     [rsp+88h+var_48], 0
0x14001ba09  mov     [rsp+88h+var_50], rsi
0x14001ba0e  mov     word ptr [rsp+88h+var_58], 24h ; '$'
0x14001ba15  mov     [rsp+88h+var_60], r12d
0x14001ba1a  mov     byte ptr [rsp+88h+var_68], r12b
0x14001ba1f  call    WPP_RECORDER_AND_TRACE_SF_D
0x14001ba24  mov     ebx, 0C000009Ah
0x14001ba29  jmp     loc_14001BD0B
0x14001ba2e  mov     rcx, [rbp+28h]; Tag
0x14001ba32  lea     r9, [rbp+30h]
0x14001ba36  mov     r8d, 1F4h
0x14001ba3c  mov     rdx, rax
0x14001ba3f  call    USBCallSyncEx
0x14001ba44  mov     ebx, eax
0x14001ba46  test    eax, eax
0x14001ba48  jns     short loc_14001BA99
0x14001ba4a  mov     rax, cs:WPP_GLOBAL_Control
0x14001ba51  mov     ecx, [rax+2Ch]
0x14001ba54  test    r12b, cl
0x14001ba57  jz      short loc_14001BA64
0x14001ba59  cmp     [rax+29h], r12b
0x14001ba5d  jb      short loc_14001BA64
0x14001ba5f  mov     dl, dil
0x14001ba62  jmp     short loc_14001BA66
0x14001ba64  xor     dl, dl
0x14001ba66  mov     r9, [rax+40h]
0x14001ba6a  lea     rsi, WPP_d9e027c83b54391969aefc6614c696e6_Traceguids
0x14001ba71  mov     rcx, [rax+18h]
0x14001ba75  mov     [rsp+88h+var_48], ebx
0x14001ba79  mov     [rsp+88h+var_50], rsi
0x14001ba7e  mov     word ptr [rsp+88h+var_58], 25h ; '%'
0x14001ba85  mov     [rsp+88h+var_60], r12d
0x14001ba8a  mov     byte ptr [rsp+88h+var_68], r12b
0x14001ba8f  call    WPP_RECORDER_AND_TRACE_SF_D
0x14001ba94  jmp     loc_14001BCF5
0x14001ba99  mov     rax, [rsp+88h+P]
0x14001baa1  xor     r12d, r12d
0x14001baa4  mov     byte ptr [rsp+88h+arg_0], r15b
0x14001baac  mov     rax, [rax+20h]
0x14001bab0  mov     [rbp+58h], rax
0x14001bab4  test    r13d, r13d
0x14001bab7  jz      loc_14001BCE8
0x14001babd  mov     rax, [rsp+88h+arg_8]
0x14001bac5  mov     r14d, r12d
0x14001bac8  add     r14, r14
0x14001bacb  mov     rsi, [rax+r14*8+8]
0x14001bad0  mov     rcx, cs:WPP_GLOBAL_Control
0x14001bad7  mov     eax, [rcx+2Ch]
0x14001bada  test    al, 2
0x14001badc  jz      short loc_14001BAE9
0x14001bade  cmp     byte ptr [rcx+29h], 4
0x14001bae2  jb      short loc_14001BAE9
0x14001bae4  mov     dl, dil
0x14001bae7  jmp     short loc_14001BAEB
0x14001bae9  xor     dl, dl
0x14001baeb  movzx   eax, byte ptr [rsi+3]
0x14001baef  movzx   r8d, byte ptr [rsi+2]
0x14001baf4  mov     r9, [rcx+40h]
0x14001baf8  mov     rcx, [rcx+18h]
0x14001bafc  mov     [rsp+88h+var_40], eax
0x14001bb00  lea     rax, WPP_d9e027c83b54391969aefc6614c696e6_Traceguids
0x14001bb07  mov     [rsp+88h+var_48], r8d
0x14001bb0c  mov     [rsp+88h+var_50], rax
0x14001bb11  mov     word ptr [rsp+88h+var_58], 26h ; '&'
0x14001bb18  mov     [rsp+88h+var_60], 2
0x14001bb20  mov     byte ptr [rsp+88h+var_68], 4
0x14001bb25  call    WPP_RECORDER_AND_TRACE_SF_dd
0x14001bb2a  mov     rcx, cs:WPP_GLOBAL_Control
0x14001bb31  mov     eax, [rcx+2Ch]
0x14001bb34  test    al, 2
0x14001bb36  jz      short loc_14001BB43
0x14001bb38  cmp     byte ptr [rcx+29h], 4
0x14001bb3c  jb      short loc_14001BB43
0x14001bb3e  mov     dl, dil
0x14001bb41  jmp     short loc_14001BB45
0x14001bb43  xor     dl, dl
0x14001bb45  mov     eax, [rsi+10h]
0x14001bb48  mov     r9, [rcx+40h]
0x14001bb4c  mov     rcx, [rcx+18h]
0x14001bb50  mov     [rsp+88h+var_48], eax
0x14001bb54  lea     rax, WPP_d9e027c83b54391969aefc6614c696e6_Traceguids
0x14001bb5b  mov     [rsp+88h+var_50], rax
0x14001bb60  mov     word ptr [rsp+88h+var_58], 27h ; '''
0x14001bb67  mov     [rsp+88h+var_60], 2
0x14001bb6f  mov     byte ptr [rsp+88h+var_68], 4
0x14001bb74  call    WPP_RECORDER_AND_TRACE_SF_D
0x14001bb79  cmp     dword ptr [rsi+10h], 0
0x14001bb7d  jz      loc_14001BC51
0x14001bb83  test    r15b, r15b
0x14001bb86  jnz     short loc_14001BBB1
0x14001bb88  mov     rcx, rsi; struct _USBD_INTERFACE_INFORMATION *
0x14001bb8b  call    ?BthUsb_IsNonIsochInterface@@_Y2PAGE@@AEPEAU_USBD_INTERFACE_INFORMATION@@@Z; BthUsb_IsNonIsochInterface(_USBD_INTERFACE_INFORMATION *)
0x14001bb90  test    al, al
0x14001bb92  jz      short loc_14001BBB1
0x14001bb94  mov     rdx, rsi; struct _USBD_INTERFACE_INFORMATION *
0x14001bb97  mov     rcx, rbp; struct _DEVICE_EXTENSION *
0x14001bb9a  call    ?BthUsb_InitializeNonIsochPipes@@_Y2PAGE@@AJPEAU_DEVICE_EXTENSION@@PEAU_USBD_INTERFACE_INFORMATION@@@Z; BthUsb_InitializeNonIsochPipes(_DEVICE_EXTENSION *,_USBD_INTERFACE_INFORMATION *)
0x14001bb9f  mov     ebx, eax
0x14001bba1  test    eax, eax
0x14001bba3  js      loc_14001BC86
0x14001bba9  mov     r15b, dil
0x14001bbac  jmp     loc_14001BC51
0x14001bbb1  cmp     byte ptr [rsp+88h+arg_0], 0
0x14001bbb9  jnz     loc_14001BC49
0x14001bbbf  mov     rcx, rsi; struct _USBD_INTERFACE_INFORMATION *
0x14001bbc2  call    ?BthUsb_IsIsochInterface@@_Y2PAGE@@AEPEAU_USBD_INTERFACE_INFORMATION@@@Z; BthUsb_IsIsochInterface(_USBD_INTERFACE_INFORMATION *)
0x14001bbc7  test    al, al
0x14001bbc9  jz      short loc_14001BC49
0x14001bbcb  mov     rdx, rsi; struct _USBD_INTERFACE_INFORMATION *
0x14001bbce  mov     rcx, rbp; struct _DEVICE_EXTENSION *
0x14001bbd1  call    ?BthUsb_InitializeIsochPipes@@_Y2PAGE@@AJPEAU_DEVICE_EXTENSION@@PEAU_USBD_INTERFACE_INFORMATION@@@Z; BthUsb_InitializeIsochPipes(_DEVICE_EXTENSION *,_USBD_INTERFACE_INFORMATION *)
0x14001bbd6  mov     ebx, eax
0x14001bbd8  test    eax, eax
0x14001bbda  js      short loc_14001BBF9
0x14001bbdc  mov     rax, [rsp+88h+arg_8]
0x14001bbe4  mov     byte ptr [rsp+88h+arg_0], dil
0x14001bbec  mov     rax, [rax+r14*8]
0x14001bbf0  mov     [rbp+280h], rax
0x14001bbf7  jmp     short loc_14001BC5B
0x14001bbf9  mov     rcx, cs:WPP_GLOBAL_Control
0x14001bc00  mov     eax, [rcx+2Ch]
0x14001bc03  test    al, 2
0x14001bc05  jz      short loc_14001BC12
0x14001bc07  cmp     byte ptr [rcx+29h], 2
0x14001bc0b  jb      short loc_14001BC12
0x14001bc0d  mov     dl, dil
0x14001bc10  jmp     short loc_14001BC14
0x14001bc12  xor     dl, dl
0x14001bc14  mov     r9, [rcx+40h]
0x14001bc18  lea     rsi, WPP_d9e027c83b54391969aefc6614c696e6_Traceguids
0x14001bc1f  mov     rcx, [rcx+18h]
0x14001bc23  mov     [rsp+88h+var_48], ebx
0x14001bc27  mov     [rsp+88h+var_50], rsi
0x14001bc2c  mov     word ptr [rsp+88h+var_58], 2Bh ; '+'
0x14001bc33  mov     [rsp+88h+var_60], 2
0x14001bc3b  mov     byte ptr [rsp+88h+var_68], 2
0x14001bc40  call    WPP_RECORDER_AND_TRACE_SF_D
0x14001bc45  xor     ebx, ebx
0x14001bc47  jmp     short loc_14001BC78
0x14001bc49  test    ebx, ebx
0x14001bc4b  js      loc_14001BCE0
0x14001bc51  cmp     byte ptr [rsp+88h+arg_0], 0
0x14001bc59  jz      short loc_14001BC71
0x14001bc5b  lea     rsi, WPP_d9e027c83b54391969aefc6614c696e6_Traceguids
0x14001bc62  test    r15b, r15b
0x14001bc65  jz      short loc_14001BC78
0x14001bc67  mov     r14, [rsp+88h+arg_8]
0x14001bc6f  jmp     short loc_14001BCEF
0x14001bc71  lea     rsi, WPP_d9e027c83b54391969aefc6614c696e6_Traceguids
0x14001bc78  add     r12d, edi
0x14001bc7b  cmp     r12d, r13d
0x14001bc7e  jb      loc_14001BABD
0x14001bc84  jmp     short loc_14001BC67
0x14001bc86  mov     rcx, cs:WPP_GLOBAL_Control
0x14001bc8d  mov     r12d, 2
0x14001bc93  mov     eax, [rcx+2Ch]
0x14001bc96  test    r12b, al
0x14001bc99  jz      short loc_14001BCA6
0x14001bc9b  cmp     [rcx+29h], r12b
0x14001bc9f  jb      short loc_14001BCA6
0x14001bca1  mov     dl, dil
0x14001bca4  jmp     short loc_14001BCA8
0x14001bca6  xor     dl, dl
0x14001bca8  mov     r9, [rcx+40h]
0x14001bcac  lea     rsi, WPP_d9e027c83b54391969aefc6614c696e6_Traceguids
0x14001bcb3  mov     rcx, [rcx+18h]
0x14001bcb7  mov     [rsp+88h+var_48], ebx
0x14001bcbb  mov     [rsp+88h+var_50], rsi
0x14001bcc0  mov     word ptr [rsp+88h+var_58], 2Ah ; '*'
0x14001bcc7  mov     [rsp+88h+var_60], r12d
0x14001bccc  mov     byte ptr [rsp+88h+var_68], r12b
0x14001bcd1  call    WPP_RECORDER_AND_TRACE_SF_D
0x14001bcd6  mov     r14, [rsp+88h+arg_8]
0x14001bcde  jmp     short loc_14001BCF5
0x14001bce0  mov     r14, [rsp+88h+arg_8]
0x14001bce8  lea     rsi, WPP_d9e027c83b54391969aefc6614c696e6_Traceguids
0x14001bcef  mov     r12d, 2
0x14001bcf5  mov     rcx, [rsp+88h+P]; P
0x14001bcfd  xor     edx, edx; Tag
0x14001bcff  call    cs:__imp_ExFreePoolWithTag
0x14001bd06  nop     dword ptr [rax+rax+00h]
0x14001bd0b  xor     edx, edx; Tag
0x14001bd0d  mov     rcx, r14; P
0x14001bd10  call    cs:__imp_ExFreePoolWithTag
0x14001bd17  nop     dword ptr [rax+rax+00h]
0x14001bd1c  test    ebx, ebx
  ... truncated ...
```
