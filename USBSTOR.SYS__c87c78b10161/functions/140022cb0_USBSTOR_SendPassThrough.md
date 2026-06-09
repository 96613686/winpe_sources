# USBSTOR_SendPassThrough

- ea: `0x140022cb0`
- end: `0x1400232c4`
- name: `USBSTOR_SendPassThrough`
- size: `1556`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `12`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callers

- `0x1400226d0`

## callees

- `0x14000baf8`
- `0x14000be30`
- `0x14000c030`
- `0x14000cb20`
- `0x14000cb5c`
- `0x14000cc70`
- `0x14000de70`
- `0x1400105e8`
- `0x140010664`
- `0x140013a40`
- `0x140013d40`
- `0x140022cb0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140022ef7`
- `ntoskrnl!ExAllocatePool2` at `0x140022f2b`
- `ntoskrnl!ExAllocatePool2` at `0x140022ffb`
- `ntoskrnl!ExAllocatePool2` at `0x140022ef7`
- `ntoskrnl!ExAllocatePool2` at `0x140022f2b`
- `ntoskrnl!ExAllocatePool2` at `0x140022ffb`
- `ntoskrnl!IofCallDriver` at `0x14002306e`
- `ntoskrnl!IofCallDriver` at `0x14002306e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140023224`
- `ntoskrnl!ExFreePoolWithTag` at `0x140023265`
- `ntoskrnl!ExFreePoolWithTag` at `0x140023224`
- `ntoskrnl!ExFreePoolWithTag` at `0x140023265`
- `ntoskrnl!KeInitializeEvent` at `0x140022d40`
- `ntoskrnl!KeInitializeEvent` at `0x140022d40`
- `ntoskrnl!IofCompleteRequest` at `0x1400230de`
- `ntoskrnl!IofCompleteRequest` at `0x1400230de`
- `ntoskrnl!KeWaitForSingleObject` at `0x140023093`
- `ntoskrnl!KeWaitForSingleObject` at `0x140023093`

## pseudocode

```c
__int64 __fastcall USBSTOR_SendPassThrough(struct _DEVICE_OBJECT *a1, IRP *a2, char a3)
{
  _QWORD *DeviceExtension; // rax
  __int64 v7; // rax
  int Status; // ebx
  __int64 v9; // r8
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r10
  unsigned __int8 v11; // r13
  __int64 v12; // rsi
  unsigned int v13; // ebx
  unsigned __int64 Length; // rdx
  char v15; // r15
  __int64 v16; // r9
  char *v17; // rcx
  KPROCESSOR_MODE RequestorMode; // al
  IO_STATUS_BLOCK *p_IoStatus; // rsi
  IRP *v20; // r15
  _WORD *Pool2; // r14
  unsigned __int8 v22; // r8
  int v23; // ecx
  int v24; // eax
  __int64 v25; // rax
  void *v26; // rsi
  __int64 v27; // rdx
  struct _IO_STACK_LOCATION *v28; // rax
  unsigned __int64 Options; // rcx
  unsigned int v31; // [rsp+58h] [rbp-49h]
  __int64 v32; // [rsp+58h] [rbp-49h]
  unsigned int v33; // [rsp+60h] [rbp-41h]
  __int128 v34; // [rsp+68h] [rbp-39h] BYREF
  __int128 v35; // [rsp+78h] [rbp-29h]
  __int128 Src; // [rsp+88h] [rbp-19h] BYREF
  __int64 v37; // [rsp+98h] [rbp-9h]
  struct _KEVENT Event; // [rsp+A0h] [rbp-1h] BYREF
  PDEVICE_OBJECT DeviceObject; // [rsp+B8h] [rbp+17h]

  DeviceObject = a1;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 47, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
  }
  DeviceExtension = a1->DeviceExtension;
  memset(&Event, 0, sizeof(Event));
  v7 = *(_QWORD *)(DeviceExtension[2] + 64LL);
  v33 = *(_DWORD *)(v7 + 1820);
  v31 = *(_DWORD *)(v7 + 1816);
  KeInitializeEvent(&Event, NotificationEvent, 0);
  v34 = 0;
  v37 = 0;
  v35 = 0;
  Src = 0;
  Status = PortPassThroughNormalize(&v34, a2);
  if ( Status < 0 )
    goto LABEL_30;
  if ( BYTE6(v34) > 0x10u )
    goto LABEL_29;
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  v11 = BYTE7(v34);
  v12 = *((_QWORD *)&v35 + 1);
  v13 = HIDWORD(v34);
  Length = CurrentStackLocation->Parameters.Read.Length;
  if ( BYTE7(v34) )
  {
    v9 = (unsigned int)Src + BYTE7(v34);
    if ( (unsigned int)v9 < (unsigned int)Src
      || (unsigned __int16)v34 > (unsigned int)Src
      || !a3
      && HIDWORD(v34)
      && ((unsigned __int64)(unsigned int)Src >= *((_QWORD *)&v35 + 1)
       || (unsigned __int64)(unsigned int)v9 > *((_QWORD *)&v35 + 1)) )
    {
      goto LABEL_29;
    }
    if ( (unsigned int)Src > (unsigned int)Length || (unsigned int)v9 > (unsigned int)Length )
      goto LABEL_29;
  }
  v15 = BYTE8(v34);
  if ( a3 )
  {
    if ( !*((_QWORD *)&v35 + 1) && HIDWORD(v34) )
      goto LABEL_29;
  }
  else
  {
    if ( (unsigned __int64)(unsigned __int16)v34 > *((_QWORD *)&v35 + 1) && HIDWORD(v34) )
      goto LABEL_29;
    if ( BYTE8(v34) == 1 )
      goto LABEL_56;
    if ( HIDWORD(v34) )
    {
      Options = CurrentStackLocation->Parameters.Create.Options;
      if ( *((_QWORD *)&v35 + 1) > Options || *((_QWORD *)&v35 + 1) + (unsigned __int64)HIDWORD(v34) > Options )
        goto LABEL_29;
    }
    if ( BYTE8(v34) )
    {
LABEL_56:
      if ( HIDWORD(v34)
        && (*((_QWORD *)&v35 + 1) > Length || *((_QWORD *)&v35 + 1) + (unsigned __int64)HIDWORD(v34) > Length) )
      {
        goto LABEL_29;
      }
    }
  }
  if ( (unsigned int)(v35 - 1) > 0x1A5DF )
    goto LABEL_29;
  if ( BYTE4(Src) == 24 || (unsigned __int8)(BYTE4(Src) - 57) <= 1u )
  {
    Status = -1073741808;
    goto LABEL_30;
  }
  PortpPassThroughZeroUnusedBuffers(a2, Length, v9, (unsigned __int16)v34);
  if ( v13 )
  {
    LODWORD(v17) = v12;
    if ( !a3 )
      v17 = (char *)a2->AssociatedIrp.MasterIrp + v12;
  }
  else
  {
    LODWORD(v17) = 0;
  }
  if ( (a1->AlignmentRequirement & (unsigned int)v17) != 0 )
    goto LABEL_29;
  if ( !v13 )
  {
    v12 = 0;
    if ( !a3 )
      goto LABEL_25;
    goto LABEL_32;
  }
  if ( (unsigned int)((v13 + 4095LL + (unsigned __int64)((unsigned __int16)v17 & 0xFFF)) >> 12) > v33 || v13 > v31 )
  {
LABEL_29:
    Status = -1073741811;
    goto LABEL_30;
  }
  if ( !a3 )
  {
    v12 += (__int64)a2->AssociatedIrp.MasterIrp;
LABEL_25:
    RequestorMode = 0;
    goto LABEL_33;
  }
LABEL_32:
  RequestorMode = a2->RequestorMode;
LABEL_33:
  LOBYTE(v16) = v15 != 0;
  v20 = (IRP *)PortPassThroughBuildIrpEx(a1, v12, v13, v16, RequestorMode, a2);
  if ( !v20 )
  {
    Status = -1073741670;
    goto LABEL_64;
  }
  Pool2 = (_WORD *)ExAllocatePool2(64, 88, 1766878288);
  if ( !Pool2 )
  {
LABEL_63:
    Status = -1073741670;
    PortPassThroughFreeIrpEx(v20);
LABEL_64:
    p_IoStatus = &a2->IoStatus;
    a2->IoStatus.Status = -1073741670;
    PortpSyncCompletion(a2, &Event);
    goto LABEL_46;
  }
  v32 = 0;
  if ( v11 )
  {
    v32 = ExAllocatePool2(72, v11, 1766878288);
    if ( !v32 )
    {
      ExFreePoolWithTag(Pool2, 0x69506C50u);
      goto LABEL_63;
    }
  }
  memset(Pool2, 0, 0x58u);
  v22 = BYTE6(v34);
  *(_WORD *)((char *)Pool2 + 5) = *(_WORD *)((char *)&v34 + 3);
  *((_BYTE *)Pool2 + 7) = BYTE5(v34);
  *Pool2 = 88;
  *((_BYTE *)Pool2 + 10) = v22;
  *((_BYTE *)Pool2 + 11) = v11;
  if ( v13 )
  {
    if ( BYTE8(v34) )
    {
      if ( BYTE8(v34) == 1 )
        v23 = 64;
      else
        v23 = 192;
    }
    else
    {
      v23 = 128;
    }
  }
  else
  {
    v23 = 0;
  }
  *((_QWORD *)Pool2 + 4) = v32;
  *((_DWORD *)Pool2 + 4) = v13;
  if ( !v32 )
    v23 |= 0x20u;
  *((_QWORD *)Pool2 + 3) = v12;
  v24 = v35;
  *((_DWORD *)Pool2 + 3) = v23 | 0x100;
  *((_DWORD *)Pool2 + 5) = v24;
  memmove(Pool2 + 36, (char *)&Src + 4, v22);
  v20->Tail.Overlay.CurrentStackLocation[-1].Parameters.WMI.ProviderId = (ULONG_PTR)Pool2;
  *((_QWORD *)Pool2 + 6) = v20;
  v25 = ExAllocatePool2(64, 48, 1766878288);
  v26 = (void *)v25;
  if ( v25 )
  {
    *(_QWORD *)(v25 + 24) = Pool2;
    *(_QWORD *)(v25 + 8) = v20;
    v27 = v25;
    *(_BYTE *)v25 = a3;
    *(_QWORD *)(v25 + 16) = a2;
    *(_QWORD *)(v25 + 32) = PortpSyncCompletion;
    *(_QWORD *)(v25 + 40) = &Event;
    v28 = v20->Tail.Overlay.CurrentStackLocation;
    v28[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)PortpAsyncCompletion;
    v28[-1].Context = v26;
    v28[-1].Control = -32;
    Status = PortpEnableCancel(a2, v27);
    if ( Status == 259 )
    {
      IofCallDriver(DeviceObject, v20);
      p_IoStatus = &a2->IoStatus;
      KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
      Status = a2->IoStatus.Status;
      goto LABEL_46;
    }
  }
  else
  {
    Status = -1073741670;
  }
  PortPassThroughFreeIrpEx(v20);
  PortPassThroughFreeSrb(Pool2);
  if ( v26 )
    ExFreePoolWithTag(v26, 0x69506C50u);
LABEL_30:
  p_IoStatus = &a2->IoStatus;
  a2->IoStatus.Status = Status;
  PortpSyncCompletion(a2, &Event);
LABEL_46:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 49, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
  }
  p_IoStatus->Status = Status;
  IofCompleteRequest(a2, 0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 50, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
  }
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x140022cb0  mov     rax, rsp
0x140022cb3  push    rbp
0x140022cb4  push    rbx
0x140022cb5  lea     rbp, [rax-5Fh]
0x140022cb9  sub     rsp, 0E8h
0x140022cc0  mov     [rax+20h], rsi
0x140022cc4  mov     [rax-18h], rdi
0x140022cc8  mov     rdi, rdx
0x140022ccb  mov     [rax-20h], r12
0x140022ccf  movzx   r12d, r8b
0x140022cd3  mov     [rax-30h], r14
0x140022cd7  mov     r14, rcx
0x140022cda  mov     [rbp+57h+DeviceObject], rcx
0x140022cde  mov     rcx, cs:WPP_GLOBAL_Control
0x140022ce5  lea     rax, WPP_GLOBAL_Control
0x140022cec  cmp     rcx, rax
0x140022cef  jz      short loc_140022CFC
0x140022cf1  mov     eax, [rcx+2Ch]
0x140022cf4  test    al, 10h
0x140022cf6  jnz     loc_1400231C3
0x140022cfc  mov     rax, [r14+40h]
0x140022d00  xorps   xmm0, xmm0
0x140022d03  mov     [rsp+0F0h+var_20], r13
0x140022d0b  xor     r8d, r8d; State
0x140022d0e  xor     edx, edx; Type
0x140022d10  mov     [rsp+0F0h+var_30], r15
0x140022d18  movups  xmmword ptr [rbp+57h+Event.Header], xmm0
0x140022d1c  mov     rcx, [rax+10h]
0x140022d20  mov     rax, [rcx+40h]
0x140022d24  mov     ecx, [rax+718h]
0x140022d2a  mov     eax, [rax+71Ch]
0x140022d30  mov     [rbp+57h+var_98], eax
0x140022d33  xor     eax, eax
0x140022d35  mov     dword ptr [rbp+57h+var_A0], ecx
0x140022d38  lea     rcx, [rbp+57h+Event]; Event
0x140022d3c  mov     [rbp+57h+Event.Header.WaitListHead.Blink], rax
0x140022d40  call    cs:__imp_KeInitializeEvent
0x140022d47  nop     dword ptr [rax+rax+00h]
0x140022d4c  xorps   xmm0, xmm0
0x140022d4f  lea     rcx, [rbp+57h+var_90]
0x140022d53  xor     eax, eax
0x140022d55  mov     rdx, rdi
0x140022d58  movups  [rbp+57h+var_90], xmm0
0x140022d5c  mov     [rbp+57h+var_60], rax
0x140022d60  movups  [rbp+57h+var_80], xmm0
0x140022d64  movups  [rbp+57h+Src], xmm0
0x140022d68  call    PortPassThroughNormalize
0x140022d6d  mov     ebx, eax
0x140022d6f  test    eax, eax
0x140022d71  js      loc_140022E8F
0x140022d77  cmp     byte ptr [rbp+57h+var_90+6], 10h
0x140022d7b  ja      loc_140022E8A
0x140022d81  mov     r10, [rdi+0B8h]
0x140022d88  mov     r13, qword ptr [rbp+57h+var_90+7]
0x140022d8c  mov     rsi, qword ptr [rbp+57h+var_80+8]
0x140022d90  mov     rbx, qword ptr [rbp+57h+var_90+0Ch]
0x140022d94  mov     edx, [r10+8]
0x140022d98  movzx   r9d, word ptr [rbp+57h+var_90]
0x140022d9d  test    r13b, r13b
0x140022da0  jz      short loc_140022DD8
0x140022da2  mov     ecx, dword ptr [rbp+57h+Src]
0x140022da5  movzx   r8d, r13b
0x140022da9  add     r8d, ecx
0x140022dac  cmp     r8d, ecx
0x140022daf  jb      loc_140022E8A
0x140022db5  cmp     r9d, ecx
0x140022db8  ja      loc_140022E8A
0x140022dbe  test    r12b, r12b
0x140022dc1  jz      loc_140022E71
0x140022dc7  cmp     ecx, edx
0x140022dc9  ja      loc_140022E8A
0x140022dcf  cmp     r8d, edx
0x140022dd2  ja      loc_140022E8A
0x140022dd8  mov     r15, qword ptr [rbp+57h+var_90+8]
0x140022ddc  test    r12b, r12b
0x140022ddf  jz      loc_140023130
0x140022de5  test    rsi, rsi
0x140022de8  jz      loc_14002317E
0x140022dee  mov     rax, qword ptr [rbp+57h+var_80]
0x140022df2  dec     eax
0x140022df4  cmp     eax, 1A5DFh
0x140022df9  ja      loc_140022E8A
0x140022dff  movzx   eax, byte ptr [rbp+57h+Src+4]
0x140022e03  cmp     al, 18h
0x140022e05  jz      loc_14002318B
0x140022e0b  sub     al, 39h ; '9'
0x140022e0d  cmp     al, 1
0x140022e0f  jbe     loc_14002318B
0x140022e15  mov     rcx, rdi
0x140022e18  call    PortpPassThroughZeroUnusedBuffers
0x140022e1d  test    ebx, ebx
0x140022e1f  jz      loc_140023177
0x140022e25  mov     rcx, rsi
0x140022e28  test    r12b, r12b
0x140022e2b  jz      loc_14002316E
0x140022e31  mov     eax, [r14+98h]
0x140022e38  test    rcx, rax
0x140022e3b  jnz     short loc_140022E8A
0x140022e3d  test    ebx, ebx
0x140022e3f  jz      short loc_140022EB2
0x140022e41  and     ecx, 0FFFh
0x140022e47  mov     eax, ebx
0x140022e49  add     rax, 0FFFh
0x140022e4f  add     rcx, rax
0x140022e52  shr     rcx, 0Ch
0x140022e56  cmp     ecx, [rbp+57h+var_98]
0x140022e59  ja      short loc_140022E8A
0x140022e5b  cmp     ebx, dword ptr [rbp+57h+var_A0]
0x140022e5e  ja      short loc_140022E8A
0x140022e60  test    ebx, ebx
0x140022e62  jz      short loc_140022EB2
0x140022e64  test    r12b, r12b
0x140022e67  jnz     short loc_140022EB9
0x140022e69  add     rsi, [rdi+18h]
0x140022e6d  xor     al, al
0x140022e6f  jmp     short loc_140022EBD
0x140022e71  test    ebx, ebx
0x140022e73  jz      loc_140022DC7
0x140022e79  cmp     rcx, rsi
0x140022e7c  jnb     short loc_140022E8A
0x140022e7e  mov     eax, r8d
0x140022e81  cmp     rax, rsi
0x140022e84  jbe     loc_140022DC7
0x140022e8a  mov     ebx, 0C000000Dh
0x140022e8f  lea     rsi, [rdi+30h]
0x140022e93  mov     rcx, rdi
0x140022e96  lea     rdx, [rbp+57h+Event]
0x140022e9a  mov     [rsi], ebx
0x140022e9c  call    PortpSyncCompletion
0x140022ea1  cmp     ebx, 103h
0x140022ea7  jnz     loc_1400230A1
0x140022ead  jmp     loc_14002307E
0x140022eb2  xor     esi, esi
0x140022eb4  test    r12b, r12b
0x140022eb7  jz      short loc_140022E6D
0x140022eb9  movzx   eax, byte ptr [rdi+40h]
0x140022ebd  test    r15b, r15b
0x140022ec0  mov     [rsp+28h], rdi
0x140022ec5  mov     r8d, ebx
0x140022ec8  mov     byte ptr [rsp+0F0h+Timeout], al
0x140022ecc  setnz   r9b
0x140022ed0  mov     rdx, rsi
0x140022ed3  mov     rcx, r14
0x140022ed6  call    PortPassThroughBuildIrpEx
0x140022edb  mov     r15, rax
0x140022ede  test    rax, rax
0x140022ee1  jz      loc_140023215
0x140022ee7  mov     edx, 58h ; 'X'
0x140022eec  mov     ecx, 40h ; '@'
0x140022ef1  mov     r8d, 69506C50h
0x140022ef7  call    cs:__imp_ExAllocatePool2
0x140022efe  nop     dword ptr [rax+rax+00h]
0x140022f03  mov     r14, rax
0x140022f06  test    rax, rax
0x140022f09  jz      loc_140023195
0x140022f0f  mov     [rbp+57h+var_A0], 0
0x140022f17  test    r13b, r13b
0x140022f1a  jz      short loc_140022F44
0x140022f1c  movzx   edx, r13b
0x140022f20  mov     ecx, 48h ; 'H'
0x140022f25  mov     r8d, 69506C50h
0x140022f2b  call    cs:__imp_ExAllocatePool2
0x140022f32  nop     dword ptr [rax+rax+00h]
0x140022f37  mov     [rbp+57h+var_A0], rax
0x140022f3b  test    rax, rax
0x140022f3e  jz      loc_14002321C
0x140022f44  xor     edx, edx; Val
0x140022f46  mov     r8d, 58h ; 'X'; Size
0x140022f4c  mov     rcx, r14; void *
0x140022f4f  call    memset
0x140022f54  movzx   eax, byte ptr [rbp+57h+var_90+3]
0x140022f58  mov     r8, qword ptr [rbp+57h+var_90+6]
0x140022f5c  mov     [r14+5], al
0x140022f60  movzx   eax, byte ptr [rbp+57h+var_90+4]
0x140022f64  mov     [r14+6], al
0x140022f68  movzx   eax, byte ptr [rbp+57h+var_90+5]
0x140022f6c  mov     [r14+7], al
0x140022f70  mov     word ptr [r14], 58h ; 'X'
0x140022f76  mov     [r14+0Ah], r8b
0x140022f7a  mov     [r14+0Bh], r13b
0x140022f7e  test    ebx, ebx
0x140022f80  jz      loc_140023167
0x140022f86  movzx   ecx, byte ptr [rbp+57h+var_90+8]
0x140022f8a  test    ecx, ecx
0x140022f8c  jz      loc_140023126
0x140022f92  cmp     ecx, 1
0x140022f95  jnz     loc_140023235
0x140022f9b  mov     ecx, 40h ; '@'
0x140022fa0  mov     rdx, [rbp+57h+var_A0]
0x140022fa4  mov     eax, ecx
0x140022fa6  or      eax, 20h
0x140022fa9  mov     [r14+20h], rdx
0x140022fad  test    rdx, rdx
0x140022fb0  movzx   r8d, r8b; Size
0x140022fb4  lea     rdx, [rbp+57h+Src+4]; Src
0x140022fb8  mov     [r14+10h], ebx
0x140022fbc  cmovz   ecx, eax
0x140022fbf  mov     [r14+18h], rsi
0x140022fc3  mov     rax, qword ptr [rbp+57h+var_80]
0x140022fc7  bts     ecx, 8
0x140022fcb  mov     [r14+0Ch], ecx
0x140022fcf  lea     rcx, [r14+48h]; void *
0x140022fd3  mov     [r14+14h], eax
0x140022fd7  call    memmove
0x140022fdc  mov     rax, [r15+0B8h]
0x140022fe3  mov     edx, 30h ; '0'
0x140022fe8  mov     ecx, 40h ; '@'
0x140022fed  mov     r8d, 69506C50h
0x140022ff3  mov     [rax-40h], r14
0x140022ff7  mov     [r14+30h], r15
0x140022ffb  call    cs:__imp_ExAllocatePool2
0x140023002  nop     dword ptr [rax+rax+00h]
0x140023007  mov     rsi, rax
0x14002300a  test    rax, rax
0x14002300d  jz      loc_14002323F
0x140023013  mov     [rax+18h], r14
0x140023017  lea     rcx, PortpAsyncCompletion
0x14002301e  mov     [rax+8], r15
0x140023022  mov     rdx, rsi
0x140023025  mov     [rax], r12b
0x140023028  mov     [rax+10h], rdi
0x14002302c  lea     rax, PortpSyncCompletion
0x140023033  mov     [rsi+20h], rax
0x140023037  lea     rax, [rbp+57h+Event]
0x14002303b  mov     [rsi+28h], rax
0x14002303f  mov     rax, [r15+0B8h]
0x140023046  mov     [rax-10h], rcx
0x14002304a  mov     rcx, rdi
0x14002304d  mov     [rax-8], rsi
0x140023051  mov     byte ptr [rax-45h], 0E0h
0x140023055  call    PortpEnableCancel
0x14002305a  mov     ebx, eax
0x14002305c  cmp     eax, 103h
0x140023061  jnz     loc_140023244
0x140023067  mov     rcx, [rbp+57h+DeviceObject]; DeviceObject
0x14002306b  mov     rdx, r15; Irp
0x14002306e  call    cs:__imp_IofCallDriver
0x140023075  nop     dword ptr [rax+rax+00h]
0x14002307a  lea     rsi, [rdi+30h]
0x14002307e  xor     r9d, r9d; Alertable
0x140023081  mov     [rsp+0F0h+Timeout], 0; Timeout
0x14002308a  xor     r8d, r8d; WaitMode
0x14002308d  lea     rcx, [rbp+57h+Event]; Object
0x140023091  xor     edx, edx; WaitReason
0x140023093  call    cs:__imp_KeWaitForSingleObject
0x14002309a  nop     dword ptr [rax+rax+00h]
0x14002309f  mov     ebx, [rsi]
0x1400230a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400230a8  lea     r14, WPP_GLOBAL_Control
0x1400230af  mov     r15, [rsp+0F0h+var_30]
0x1400230b7  mov     r13, [rsp+0F0h+var_20]
0x1400230bf  mov     r12, [rsp+0F0h+var_18]
0x1400230c7  cmp     rcx, r14
0x1400230ca  jz      short loc_1400230D7
0x1400230cc  mov     eax, [rcx+2Ch]
0x1400230cf  test    al, 1
0x1400230d1  jnz     loc_140023276
0x1400230d7  xor     edx, edx; PriorityBoost
0x1400230d9  mov     [rsi], ebx
0x1400230db  mov     rcx, rdi; Irp
0x1400230de  call    cs:__imp_IofCompleteRequest
0x1400230e5  nop     dword ptr [rax+rax+00h]
0x1400230ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1400230f1  mov     rdi, [rsp+0E0h]
0x1400230f9  cmp     rcx, r14
0x1400230fc  mov     r14, [rsp+0F0h+var_28]
0x140023104  mov     rsi, [rsp+0F0h+arg_18]
0x14002310c  jz      short loc_140023119
0x14002310e  mov     eax, [rcx+2Ch]
0x140023111  test    al, 10h
0x140023113  jnz     loc_14002329D
0x140023119  mov     eax, ebx
0x14002311b  add     rsp, 0E8h
0x140023122  pop     rbx
0x140023123  pop     rbp
0x140023124  retn
0x140023126  mov     ecx, 80h
0x14002312b  jmp     loc_140022FA0
0x140023130  cmp     r9, rsi
0x140023133  ja      loc_1400231E7
0x140023139  cmp     r15b, 1
0x14002313d  jnz     loc_1400231F4
0x140023143  test    ebx, ebx
0x140023145  jz      loc_140022DEE
0x14002314b  cmp     rsi, rdx
0x14002314e  ja      loc_140022E8A
0x140023154  mov     eax, ebx
0x140023156  add     rax, rsi
0x140023159  cmp     rax, rdx
0x14002315c  jbe     loc_140022DEE
0x140023162  jmp     loc_140022E8A
0x140023167  xor     ecx, ecx
0x140023169  jmp     loc_140022FA0
0x14002316e  add     rcx, [rdi+18h]
0x140023172  jmp     loc_140022E31
0x140023177  xor     ecx, ecx
0x140023179  jmp     loc_140022E31
0x14002317e  test    ebx, ebx
0x140023180  jz      loc_140022DEE
0x140023186  jmp     loc_140022E8A
  ... truncated ...
```
