# XilCommand_SendAddCommandCRBToRingRequest

- ea: `0x140023678`
- end: `0x140023905`
- name: `XilCommand_SendAddCommandCRBToRingRequest`
- size: `653`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140021a74`

## callees

- `0x14001ac48`
- `0x14001ad0c`
- `0x14001bb78`
- `0x14001c178`
- `0x140023678`
- `0x140046070`
- `0x140059a80`

## import_xrefs

- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x140023751`
- `ntoskrnl!KdRefreshDebuggerNotPresent` at `0x140023751`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400238e9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400238e9`
- `ntoskrnl!ExAllocatePool2` at `0x1400236cc`
- `ntoskrnl!ExAllocatePool2` at `0x1400236cc`

## string_xrefs

- `0x140023734`: `onecore\drivers\wdm\usb\usb3\usbxhci\sys\xilcommand.c`
- `0x1400238d3`: `onecore\drivers\wdm\usb\usb3\usbxhci\sys\xilcommand.c`
- `0x140023728`: `Allocate(sendCommandTrbToRingIn) failed`
- `0x140023887`: `IOCTL succeeded but CommandAddCommandTRBToRing failed in VTL-1 failed`

## pseudocode

```c
__int64 __fastcall XilCommand_SendAddCommandCRBToRingRequest(__int64 a1, __int64 a2)
{
  unsigned int v2; // r10d
  int v3; // r9d
  __int64 v6; // rbp
  unsigned int v7; // eax
  __int64 v8; // r15
  unsigned int v9; // r14d
  __int64 Pool2; // rax
  int v11; // edx
  __int64 v12; // rsi
  unsigned int v13; // edi
  int v14; // edx
  int v15; // r9d
  unsigned int v16; // eax
  int v17; // eax
  __int64 v18; // rcx
  int v19; // eax
  int v20; // edx
  __int64 v21; // r9
  const char *v22; // rcx
  int v24; // [rsp+20h] [rbp-58h]
  int v25; // [rsp+80h] [rbp+8h] BYREF

  v2 = *(_DWORD *)(a2 + 80);
  v3 = -1;
  v25 = 0;
  v6 = *(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL);
  if ( v2 + 72 >= v2 )
    v3 = v2 + 72;
  v7 = 0;
  v8 = *(_QWORD *)(v6 + 112);
  if ( v2 + 72 >= v2 )
    v7 = v3;
  v9 = v7;
  Pool2 = ExAllocatePool2(64, v7, 1229146200);
  v12 = Pool2;
  if ( Pool2 )
  {
    *(_QWORD *)(Pool2 + 24) = *(_QWORD *)(a1 + 32);
    *(_DWORD *)(Pool2 + 32) = 19;
    *(_OWORD *)(Pool2 + 40) = *(_OWORD *)(a2 + 24);
    v16 = *(_DWORD *)(a2 + 80);
    if ( v16 )
    {
      memmove((void *)(v12 + 72), *(const void **)(a2 + 72), v16);
      *(_DWORD *)(v12 + 68) = *(_DWORD *)(a2 + 80);
    }
    *(_DWORD *)(v12 + 64) = *(_DWORD *)(a2 + 84);
    v17 = *(_DWORD *)(a2 + 84);
    if ( v17 == 1 )
    {
      v18 = *(_QWORD *)(*(_QWORD *)(a2 + 88) + 616LL);
    }
    else if ( v17 == 2 )
    {
      v18 = *(_QWORD *)(*(_QWORD *)(a2 + 88) + 1336LL);
    }
    else
    {
      if ( v17 )
      {
        v13 = -1073741811;
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v11) = 2;
          WPP_RECORDER_SF_(*(_QWORD *)(v6 + 72), v11, 7, 20, (__int64)WPP_db21d8d52d393cb96c062fdb7e607301_Traceguids);
        }
        v21 = 570;
        v22 = "Crb->InputContextType is invalid";
        goto LABEL_29;
      }
      v18 = 0;
    }
    *(_QWORD *)(v12 + 56) = v18;
    v19 = SecureChannel_SendRequestSynchronously(v8, v12, v9, &v25, 4);
    v13 = v19;
    if ( v19 < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v20) = 2;
        WPP_RECORDER_SF_d(
          *(_QWORD *)(v6 + 72),
          v20,
          7,
          21,
          (__int64)WPP_db21d8d52d393cb96c062fdb7e607301_Traceguids,
          v19);
      }
      goto LABEL_30;
    }
    v13 = v25;
    if ( v25 >= 0 )
    {
LABEL_30:
      ExFreePoolWithTag((PVOID)v12, 0x49434858u);
      return v13;
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v20) = 2;
      WPP_RECORDER_SF_d(*(_QWORD *)(v6 + 72), v20, 7, 22, (__int64)WPP_db21d8d52d393cb96c062fdb7e607301_Traceguids, v25);
    }
    v21 = 593;
    v22 = "IOCTL succeeded but CommandAddCommandTRBToRing failed in VTL-1 failed";
LABEL_29:
    Debug_FreAssertMsg(v22, 0, "onecore\\drivers\\wdm\\usb\\usb3\\usbxhci\\sys\\xilcommand.c", v21);
    goto LABEL_30;
  }
  v13 = -1073741670;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v11) = 2;
    WPP_RECORDER_SF_(*(_QWORD *)(v6 + 72), v11, 7, 19, (__int64)WPP_db21d8d52d393cb96c062fdb7e607301_Traceguids);
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_sds(
        WPP_GLOBAL_Control->DeviceExtension,
        v14,
        (unsigned int)"onecore\\drivers\\wdm\\usb\\usb3\\usbxhci\\sys\\xilcommand.c",
        v15,
        v24,
        (__int64)"onecore\\drivers\\wdm\\usb\\usb3\\usbxhci\\sys\\xilcommand.c",
        6,
        (__int64)"Allocate(sendCommandTrbToRingIn) failed");
  }
  if ( !KdRefreshDebuggerNotPresent() )
    __debugbreak();
  return v13;
}

```

## disassembly

```asm
0x140023678  mov     rax, rsp
0x14002367b  push    rbx
0x14002367c  push    rbp
0x14002367d  push    rsi
0x14002367e  push    rdi
0x14002367f  push    r14
0x140023681  push    r15
0x140023683  sub     rsp, 48h
0x140023687  mov     r10d, [rdx+50h]
0x14002368b  or      r9d, 0FFFFFFFFh
0x14002368f  mov     dword ptr [rax+8], 0
0x140023696  mov     rbx, rdx
0x140023699  mov     rax, [rcx+8]
0x14002369d  mov     rdi, rcx
0x1400236a0  mov     ecx, 40h ; '@'
0x1400236a5  lea     r8d, [r10+48h]
0x1400236a9  cmp     r8d, r10d
0x1400236ac  mov     rbp, [rax+8]
0x1400236b0  cmovnb  r9d, r8d
0x1400236b4  xor     eax, eax
0x1400236b6  cmp     r8d, r10d
0x1400236b9  mov     r8d, 49434858h
0x1400236bf  mov     r15, [rbp+70h]
0x1400236c3  cmovnb  eax, r9d
0x1400236c7  mov     edx, eax
0x1400236c9  mov     r14d, eax
0x1400236cc  call    cs:__imp_ExAllocatePool2
0x1400236d3  nop     dword ptr [rax+rax+00h]
0x1400236d8  mov     rsi, rax
0x1400236db  test    rax, rax
0x1400236de  jnz     loc_14002376B
0x1400236e4  mov     edi, 0C000009Ah
0x1400236e9  lea     rbx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400236f0  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x1400236f7  jz      short loc_140023751
0x1400236f9  mov     rcx, [rbp+48h]
0x1400236fd  lea     r9d, [rax+13h]
0x140023701  lea     rax, WPP_db21d8d52d393cb96c062fdb7e607301_Traceguids
0x140023708  mov     dl, 2
0x14002370a  lea     r8d, [rsi+7]
0x14002370e  mov     [rsp+78h+var_58], rax
0x140023713  call    WPP_RECORDER_SF_
0x140023718  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x14002371f  jz      short loc_140023751
0x140023721  mov     rcx, cs:WPP_GLOBAL_Control
0x140023728  lea     rax, aAllocateSendco; "Allocate(sendCommandTrbToRingIn) failed"
0x14002372f  mov     [rsp+78h+var_40], rax
0x140023734  lea     r8, aOnecoreDrivers_5; "onecore\\drivers\\wdm\\usb\\usb3\\usbxh"...
0x14002373b  mov     [rsp+78h+var_48], 206h
0x140023743  mov     [rsp+78h+var_50], r8
0x140023748  mov     rcx, [rcx+40h]
0x14002374c  call    WPP_RECORDER_SF_sds
0x140023751  call    cs:__imp_KdRefreshDebuggerNotPresent
0x140023758  nop     dword ptr [rax+rax+00h]
0x14002375d  test    al, al
0x14002375f  jnz     loc_1400238F5
0x140023765  int     3; Trap to Debugger
0x140023766  jmp     loc_1400238F5
0x14002376b  mov     rax, [rdi+20h]
0x14002376f  mov     [rsi+18h], rax
0x140023773  mov     dword ptr [rsi+20h], 13h
0x14002377a  movups  xmm0, xmmword ptr [rbx+18h]
0x14002377e  movdqu  xmmword ptr [rsi+28h], xmm0
0x140023783  mov     eax, [rbx+50h]
0x140023786  test    eax, eax
0x140023788  jz      short loc_1400237A0
0x14002378a  mov     rdx, [rbx+48h]; Src
0x14002378e  lea     rcx, [rsi+48h]; void *
0x140023792  mov     r8d, eax; Size
0x140023795  call    memmove
0x14002379a  mov     eax, [rbx+50h]
0x14002379d  mov     [rsi+44h], eax
0x1400237a0  mov     eax, [rbx+54h]
0x1400237a3  mov     [rsi+40h], eax
0x1400237a6  mov     eax, [rbx+54h]
0x1400237a9  cmp     eax, 1
0x1400237ac  jnz     short loc_1400237BB
0x1400237ae  mov     rax, [rbx+58h]
0x1400237b2  mov     rcx, [rax+268h]
0x1400237b9  jmp     short loc_1400237D7
0x1400237bb  cmp     eax, 2
0x1400237be  jnz     short loc_1400237CD
0x1400237c0  mov     rax, [rbx+58h]
0x1400237c4  mov     rcx, [rax+538h]
0x1400237cb  jmp     short loc_1400237D7
0x1400237cd  test    eax, eax
0x1400237cf  jnz     loc_140023890
0x1400237d5  xor     ecx, ecx
0x1400237d7  mov     [rsi+38h], rcx
0x1400237db  lea     r9, [rsp+78h+arg_0]
0x1400237e3  mov     rcx, r15
0x1400237e6  mov     dword ptr [rsp+78h+var_58], 4
0x1400237ee  mov     r8d, r14d
0x1400237f1  mov     rdx, rsi
0x1400237f4  call    SecureChannel_SendRequestSynchronously
0x1400237f9  mov     edi, eax
0x1400237fb  test    eax, eax
0x1400237fd  jns     short loc_14002383D
0x1400237ff  lea     rbx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140023806  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x14002380d  jz      loc_1400238E1
0x140023813  mov     rcx, [rbp+48h]
0x140023817  mov     r9d, 15h
0x14002381d  mov     dword ptr [rsp+78h+var_50], eax
0x140023821  mov     dl, 2
0x140023823  lea     rax, WPP_db21d8d52d393cb96c062fdb7e607301_Traceguids
0x14002382a  mov     [rsp+78h+var_58], rax
0x14002382f  lea     r8d, [r9-0Eh]
0x140023833  call    WPP_RECORDER_SF_d
0x140023838  jmp     loc_1400238E1
0x14002383d  mov     edi, [rsp+78h+arg_0]
0x140023844  test    edi, edi
0x140023846  jns     loc_1400238E1
0x14002384c  lea     rbx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140023853  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x14002385a  jz      short loc_140023881
0x14002385c  mov     rcx, [rbp+48h]
0x140023860  lea     rax, WPP_db21d8d52d393cb96c062fdb7e607301_Traceguids
0x140023867  mov     r9d, 16h
0x14002386d  mov     dword ptr [rsp+78h+var_50], edi
0x140023871  mov     dl, 2
0x140023873  mov     [rsp+78h+var_58], rax
0x140023878  lea     r8d, [r9-0Fh]
0x14002387c  call    WPP_RECORDER_SF_d
0x140023881  mov     r9d, 251h
0x140023887  lea     rcx, aIoctlSucceeded_4; "IOCTL succeeded but CommandAddCommandTR"...
0x14002388e  jmp     short loc_1400238D3
0x140023890  mov     edi, 0C000000Dh
0x140023895  lea     rbx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14002389c  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x1400238a3  jz      short loc_1400238C6
0x1400238a5  mov     rcx, [rbp+48h]
0x1400238a9  lea     rax, WPP_db21d8d52d393cb96c062fdb7e607301_Traceguids
0x1400238b0  mov     r9d, 14h
0x1400238b6  mov     [rsp+78h+var_58], rax
0x1400238bb  mov     dl, 2
0x1400238bd  lea     r8d, [r9-0Dh]
0x1400238c1  call    WPP_RECORDER_SF_
0x1400238c6  mov     r9d, 23Ah
0x1400238cc  lea     rcx, aCrbInputcontex; "Crb->InputContextType is invalid"
0x1400238d3  lea     r8, aOnecoreDrivers_5; "onecore\\drivers\\wdm\\usb\\usb3\\usbxh"...
0x1400238da  xor     edx, edx
0x1400238dc  call    Debug_FreAssertMsg
0x1400238e1  mov     edx, 49434858h; Tag
0x1400238e6  mov     rcx, rsi; P
0x1400238e9  call    cs:__imp_ExFreePoolWithTag
0x1400238f0  nop     dword ptr [rax+rax+00h]
0x1400238f5  mov     eax, edi
0x1400238f7  add     rsp, 48h
0x1400238fb  pop     r15
0x1400238fd  pop     r14
0x1400238ff  pop     rdi
0x140023900  pop     rsi
0x140023901  pop     rbp
0x140023902  pop     rbx
0x140023903  retn
```
