# UsbDevice_DisableCompletion

- ea: `0x14002a734`
- end: `0x14002aa56`
- name: `UsbDevice_DisableCompletion`
- size: `802`
- prototype: ``
- caller_count: `3`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x14002ae80`
- `0x14004de40`
- `0x14004ea70`

## callees

- `0x14000c264`
- `0x1400216b8`
- `0x140024e18`
- `0x140024f24`
- `0x1400296ac`
- `0x140029840`
- `0x14002a734`
- `0x14002aa5c`
- `0x14002aa98`
- `0x14002b19c`
- `0x14002b2c0`
- `0x1400599b0`
- `0x140059d80`

## string_xrefs

- `0x14002a9e7`: `Disable Slot Command failed`

## pseudocode

```c
__int64 __fastcall UsbDevice_DisableCompletion(__int64 a1, __int64 a2, int a3)
{
  __int64 v3; // rdi
  char v6; // cl
  char v7; // bp
  __int64 v8; // r13
  __int64 i; // rbx
  __int64 v10; // rcx
  __int64 v11; // r14
  __int64 XilCoreDeviceSlotData; // rax
  __int64 result; // rax
  __int64 v14; // r8
  __int64 v15; // rcx
  int v16; // edx
  __int64 v17; // rdx
  int v18; // edx
  int v19; // edx

  v3 = *(_QWORD *)(a1 + 48);
  if ( (_DWORD)a2 == 3 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v18 = *(unsigned __int8 *)(v3 + 143);
      LOBYTE(v18) = 4;
      WPP_RECORDER_SF_dq(
        *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
        v18,
        12,
        76,
        (__int64)WPP_38a5a096fcfe3a80d9611fe09a034fab_Traceguids,
        *(_BYTE *)(v3 + 143),
        *(_QWORD *)v3);
    }
    result = UsbDevice_SetDeviceDisabled(v3);
    goto LABEL_24;
  }
  v6 = *(_BYTE *)(a1 + 60);
  if ( v6 != 1 && v6 != 11 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v19 = *(unsigned __int8 *)(a1 + 61);
      LOBYTE(v19) = 2;
      WPP_RECORDER_SF_dqL(*(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL), v19, a3, 78);
    }
    Controller_HwVerifierBreakIfEnabled(
      *(_QWORD *)(v3 + 8),
      *(_QWORD *)v3,
      0,
      0x100000,
      (__int64)"Disable Slot Command failed",
      a1 + 24,
      0);
    result = Controller_ReportFatalError(*(_QWORD *)(v3 + 8), 2, 4120, 0, 0, 0, 0);
LABEL_24:
    v7 = 0;
    v14 = 3221225473LL;
    goto LABEL_16;
  }
  v7 = 1;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v16 = *(unsigned __int8 *)(a1 + 61);
    LOBYTE(v16) = 4;
    WPP_RECORDER_SF_dq(
      *(_QWORD *)(*(_QWORD *)(v3 + 8) + 72LL),
      v16,
      12,
      77,
      (__int64)WPP_38a5a096fcfe3a80d9611fe09a034fab_Traceguids,
      *(_BYTE *)(a1 + 61),
      *(_QWORD *)v3);
  }
  v8 = *(_QWORD *)(*(_QWORD *)(v3 + 8) + 136LL);
  if ( a3 != 2 )
  {
    LOBYTE(a2) = 1;
    Endpoint_Disable(*(_QWORD *)(v3 + 184), a2);
  }
  for ( i = 2; i != 32; ++i )
  {
    v10 = *(_QWORD *)(v3 + 8 * i + 176);
    if ( v10 )
    {
      LOBYTE(a2) = 1;
      Endpoint_Disable(v10, a2);
      *(_QWORD *)(v3 + 8 * i + 176) = 0;
    }
  }
  v11 = *(unsigned __int8 *)(v3 + 143);
  if ( *(_BYTE *)(v8 + 80) )
  {
    XilDeviceSlot_SendClearDeviceContextRequest(v8 + 16, v3);
    result = *(_QWORD *)((-(__int64)(*(_BYTE *)(*(_QWORD *)(v8 + 88) + 80LL) != 0) & 0xFFFFFFFFFFFFFFD0uLL)
                       + *(_QWORD *)(v8 + 88)
                       + 72);
    *(_QWORD *)(result + 8 * v11) = 0;
  }
  else
  {
    XilCoreDeviceSlotData = DeviceSlot_GetXilCoreDeviceSlotData(*(_QWORD *)(v8 + 88));
    result = XilCoreDeviceSlot_ClearDeviceContext(XilCoreDeviceSlotData, v3, (unsigned int)v11);
  }
  *(_WORD *)(v3 + 142) = 0;
  v14 = 0;
  *(_QWORD *)(v3 + 168) = 0;
  if ( a3 == 2 )
  {
    memset((void *)(v3 + 464), 0, 0x60u);
    v15 = *(_QWORD *)(v3 + 8);
    *(_QWORD *)(v3 + 504) = UsbDevice_EnableCompletion;
    *(_QWORD *)(v3 + 512) = v3;
    *(_DWORD *)(v3 + 500) = 9216;
    *(_QWORD *)(v3 + 536) = 0;
    *(_QWORD *)(v3 + 544) = 0;
    *(_QWORD *)(v3 + 552) = 0;
    return Command_SendCommand(*(_QWORD *)(v15 + 144), v3 + 464);
  }
LABEL_16:
  if ( a3 == 1 )
    v14 = 3221225473LL;
  if ( v7 )
  {
    v17 = *(_QWORD *)(v3 + 432);
    *(_QWORD *)(v3 + 432) = 0;
    return (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64))(WdfFunctions_01033 + 2104))(
             WdfDriverGlobals,
             v17,
             v14);
  }
  return result;
}

```

## disassembly

```asm
0x14002a734  push    rbx
0x14002a736  push    rbp
0x14002a737  push    rdi
0x14002a738  push    r12
0x14002a73a  push    r13
0x14002a73c  push    r14
0x14002a73e  push    r15
0x14002a740  sub     rsp, 40h
0x14002a744  mov     rdi, [rcx+30h]
0x14002a748  mov     r15d, r8d
0x14002a74b  mov     rbx, rcx
0x14002a74e  mov     r12d, 0C0000001h
0x14002a754  cmp     edx, 3
0x14002a757  jz      loc_14002A945
0x14002a75d  movzx   ecx, byte ptr [rcx+3Ch]
0x14002a761  cmp     cl, 1
0x14002a764  jnz     loc_14002AA34
0x14002a76a  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14002a771  mov     bpl, 1
0x14002a774  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002a77b  jnz     loc_14002A8A6
0x14002a781  mov     rax, [rdi+8]
0x14002a785  mov     r13, [rax+88h]
0x14002a78c  cmp     r15d, 2
0x14002a790  jz      short loc_14002A7A1
0x14002a792  mov     rcx, [rdi+0B8h]
0x14002a799  mov     dl, bpl
0x14002a79c  call    Endpoint_Disable
0x14002a7a1  mov     ebx, 2
0x14002a7a6  mov     rcx, [rdi+rbx*8+0B0h]
0x14002a7ae  test    rcx, rcx
0x14002a7b1  jnz     loc_14002A8E0
0x14002a7b7  inc     rbx
0x14002a7ba  cmp     rbx, 20h ; ' '
0x14002a7be  jnz     short loc_14002A7A6
0x14002a7c0  cmp     byte ptr [r13+50h], 0
0x14002a7c5  movzx   r14d, byte ptr [rdi+8Fh]
0x14002a7cd  jnz     loc_14002A878
0x14002a7d3  mov     rcx, [r13+58h]
0x14002a7d7  call    DeviceSlot_GetXilCoreDeviceSlotData
0x14002a7dc  mov     rcx, rax
0x14002a7df  mov     r8d, r14d
0x14002a7e2  mov     rdx, rdi
0x14002a7e5  call    XilCoreDeviceSlot_ClearDeviceContext
0x14002a7ea  mov     word ptr [rdi+8Eh], 0
0x14002a7f3  xor     r8d, r8d
0x14002a7f6  mov     qword ptr [rdi+0A8h], 0
0x14002a801  cmp     r15d, 2
0x14002a805  jnz     loc_14002A8F9
0x14002a80b  lea     rbx, [rdi+1D0h]
0x14002a812  xor     edx, edx; Val
0x14002a814  mov     rcx, rbx; void *
0x14002a817  lea     r8d, [r15+5Eh]; Size
0x14002a81b  call    memset
0x14002a820  mov     rcx, [rdi+8]
0x14002a824  lea     rax, UsbDevice_EnableCompletion
0x14002a82b  mov     [rdi+1F8h], rax
0x14002a832  mov     rdx, rbx
0x14002a835  mov     [rdi+200h], rdi
0x14002a83c  mov     dword ptr [rdi+1F4h], 2400h
0x14002a846  mov     qword ptr [rdi+218h], 0
0x14002a851  mov     qword ptr [rdi+220h], 0
0x14002a85c  mov     qword ptr [rdi+228h], 0
0x14002a867  mov     rcx, [rcx+90h]
0x14002a86e  call    Command_SendCommand
0x14002a873  jmp     loc_14002A906
0x14002a878  mov     rdx, rdi
0x14002a87b  lea     rcx, [r13+10h]
0x14002a87f  call    XilDeviceSlot_SendClearDeviceContextRequest
0x14002a884  mov     rdx, [r13+58h]
0x14002a888  mov     al, [rdx+50h]
0x14002a88b  neg     al
0x14002a88d  sbb     rax, rax
0x14002a890  and     rax, 0FFFFFFFFFFFFFFD0h
0x14002a894  mov     rax, [rax+rdx+48h]
0x14002a899  mov     qword ptr [rax+r14*8], 0
0x14002a8a1  jmp     loc_14002A7EA
0x14002a8a6  mov     rax, [rdi]
0x14002a8a9  mov     r9d, 4Dh ; 'M'
0x14002a8af  movzx   edx, byte ptr [rbx+3Dh]
0x14002a8b3  mov     rcx, [rdi+8]
0x14002a8b7  mov     [rsp+78h+var_48], rax
0x14002a8bc  lea     rax, WPP_38a5a096fcfe3a80d9611fe09a034fab_Traceguids
0x14002a8c3  mov     dword ptr [rsp+78h+var_50], edx
0x14002a8c7  lea     r8d, [r9-41h]
0x14002a8cb  mov     dl, 4
0x14002a8cd  mov     [rsp+78h+var_58], rax
0x14002a8d2  mov     rcx, [rcx+48h]
0x14002a8d6  call    WPP_RECORDER_SF_dq
0x14002a8db  jmp     loc_14002A781
0x14002a8e0  mov     dl, bpl
0x14002a8e3  call    Endpoint_Disable
0x14002a8e8  mov     qword ptr [rdi+rbx*8+0B0h], 0
0x14002a8f4  jmp     loc_14002A7B7
0x14002a8f9  cmp     r15d, 1
0x14002a8fd  cmovz   r8d, r12d
0x14002a901  test    bpl, bpl
0x14002a904  jnz     short loc_14002A917
0x14002a906  add     rsp, 40h
0x14002a90a  pop     r15
0x14002a90c  pop     r14
0x14002a90e  pop     r13
0x14002a910  pop     r12
0x14002a912  pop     rdi
0x14002a913  pop     rbp
0x14002a914  pop     rbx
0x14002a915  retn
0x14002a917  mov     rdx, [rdi+1B0h]
0x14002a91e  mov     qword ptr [rdi+1B0h], 0
0x14002a929  mov     rax, cs:WdfFunctions_01033
0x14002a930  mov     rcx, cs:WdfDriverGlobals
0x14002a937  mov     rax, [rax+838h]
0x14002a93e  call    _guard_dispatch_icall
0x14002a943  jmp     short loc_14002A906
0x14002a945  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14002a94c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002a953  jz      short loc_14002A98D
0x14002a955  mov     rax, [rdi]
0x14002a958  mov     r9d, 4Ch ; 'L'
0x14002a95e  movzx   edx, byte ptr [rdi+8Fh]
0x14002a965  mov     rcx, [rdi+8]
0x14002a969  mov     [rsp+78h+var_48], rax
0x14002a96e  lea     rax, WPP_38a5a096fcfe3a80d9611fe09a034fab_Traceguids
0x14002a975  mov     dword ptr [rsp+78h+var_50], edx
0x14002a979  lea     r8d, [r9-40h]
0x14002a97d  mov     dl, 4
0x14002a97f  mov     [rsp+78h+var_58], rax
0x14002a984  mov     rcx, [rcx+48h]
0x14002a988  call    WPP_RECORDER_SF_dq
0x14002a98d  mov     rcx, rdi
0x14002a990  call    UsbDevice_SetDeviceDisabled
0x14002a995  jmp     loc_14002AA29
0x14002a99a  movzx   edx, byte ptr [rbx+3Dh]
0x14002a99e  mov     eax, ecx
0x14002a9a0  mov     rcx, [rdi+8]
0x14002a9a4  mov     r9d, 4Eh ; 'N'
0x14002a9aa  mov     [rsp+78h+var_40], eax
0x14002a9ae  mov     rax, [rdi]
0x14002a9b1  mov     [rsp+78h+var_48], rax
0x14002a9b6  mov     rcx, [rcx+48h]
0x14002a9ba  mov     dword ptr [rsp+78h+var_50], edx
0x14002a9be  mov     dl, 2
0x14002a9c0  call    WPP_RECORDER_SF_dqL
0x14002a9c5  mov     rdx, [rdi]
0x14002a9c8  lea     rax, [rbx+18h]
0x14002a9cc  mov     rcx, [rdi+8]
0x14002a9d0  mov     r9d, 100000h
0x14002a9d6  mov     [rsp+78h+var_48], 0
0x14002a9df  xor     r8d, r8d
0x14002a9e2  mov     [rsp+78h+var_50], rax
0x14002a9e7  lea     rax, aDisableSlotCom; "Disable Slot Command failed"
0x14002a9ee  mov     [rsp+78h+var_58], rax
0x14002a9f3  call    Controller_HwVerifierBreakIfEnabled
0x14002a9f8  mov     rcx, [rdi+8]
0x14002a9fc  xor     r9d, r9d
0x14002a9ff  mov     [rsp+78h+var_48], 0
0x14002aa08  mov     r8d, 1018h
0x14002aa0e  mov     [rsp+78h+var_50], 0
0x14002aa17  mov     [rsp+78h+var_58], 0
0x14002aa20  lea     edx, [r9+2]
0x14002aa24  call    Controller_ReportFatalError
0x14002aa29  xor     bpl, bpl
0x14002aa2c  mov     r8d, r12d
0x14002aa2f  jmp     loc_14002A8F9
0x14002aa34  cmp     cl, 0Bh
0x14002aa37  jz      loc_14002A76A
0x14002aa3d  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14002aa44  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002aa4b  jz      loc_14002A9C5
0x14002aa51  jmp     loc_14002A99A
```
