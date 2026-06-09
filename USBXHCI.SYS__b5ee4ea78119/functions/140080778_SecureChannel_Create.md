# SecureChannel_Create

- ea: `0x140080778`
- end: `0x1400809b1`
- name: `SecureChannel_Create`
- size: `569`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14007a250`

## callees

- `0x14001ad0c`
- `0x140031928`
- `0x140044cd8`
- `0x140044fb4`
- `0x1400599b0`
- `0x140080778`

## import_xrefs

- `HAL!KeQueryPerformanceCounter` at `0x14008094c`
- `HAL!KeQueryPerformanceCounter` at `0x14008094c`

## pseudocode

```c
__int64 __fastcall SecureChannel_Create(union _LARGE_INTEGER a1, __int64 a2, union _LARGE_INTEGER **a3)
{
  __int64 v4; // rdx
  int v7; // edx
  int v8; // ebx
  int v9; // ecx
  int v10; // r8d
  int v11; // r9d
  int v12; // edx
  int v13; // edx
  __int128 v15; // [rsp+30h] [rbp-40h] BYREF
  __int128 v16; // [rsp+40h] [rbp-30h]
  __int128 v17; // [rsp+50h] [rbp-20h]
  __int64 *v18; // [rsp+60h] [rbp-10h]
  union _LARGE_INTEGER *v19; // [rsp+90h] [rbp+20h] BYREF
  __int64 v20; // [rsp+A8h] [rbp+38h] BYREF

  LODWORD(v18) = 0;
  v4 = *(_QWORD *)(a1.QuadPart + 88);
  v19 = 0;
  v20 = 0;
  v15 = 0;
  v16 = 0;
  v17 = 0;
  v8 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01033 + 3584))(
         WdfDriverGlobals,
         v4,
         &v20);
  if ( v8 >= 0 )
  {
    v15 = 0;
    v18 = 0;
    v16 = 0;
    v17 = 0;
    if ( WdfClientVersionHigherThanFramework )
    {
      if ( (unsigned int)WdfStructureCount <= 0x26 )
        LODWORD(v15) = -1;
      else
        LODWORD(v15) = *(_DWORD *)(WdfStructures + 304);
    }
    else
    {
      LODWORD(v15) = 56;
    }
    *((_QWORD *)&v16 + 1) = 0x100000001LL;
    v18 = off_14006C158;
    v8 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int128 *, union _LARGE_INTEGER **))(WdfFunctions_01033 + 1624))(
           WdfDriverGlobals,
           v20,
           &v15,
           &v19);
    if ( v8 >= 0 )
    {
      v19->QuadPart = v20;
      v19[1] = a1;
      KeQueryPerformanceCounter(v19 + 2);
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v13) = 4;
        WPP_RECORDER_SF_q(
          *(_QWORD *)(a1.QuadPart + 16),
          v13,
          19,
          12,
          (__int64)WPP_1c685d3d62dd34c321aa434cf17c39a3_Traceguids,
          v20);
      }
      *a3 = v19;
    }
    else
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v12) = 2;
        WPP_RECORDER_SF_d(
          *(_QWORD *)(a1.QuadPart + 16),
          v12,
          19,
          11,
          (__int64)WPP_1c685d3d62dd34c321aa434cf17c39a3_Traceguids,
          v8);
      }
      if ( (unsigned int)Feature_XhciCompanionEtw__private_IsEnabledDeviceUsageNoInline()
        && (BYTE1(WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc) & 0x40) != 0 )
      {
        v11 = 34;
        goto LABEL_8;
      }
    }
  }
  else
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v7) = 2;
      WPP_RECORDER_SF_d(
        *(_QWORD *)(a1.QuadPart + 16),
        v7,
        19,
        10,
        (__int64)WPP_1c685d3d62dd34c321aa434cf17c39a3_Traceguids,
        v8);
    }
    if ( (unsigned int)Feature_XhciCompanionEtw__private_IsEnabledDeviceUsageNoInline()
      && v8 != -1073741772
      && (BYTE1(WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc) & 0x40) != 0 )
    {
      v11 = 33;
LABEL_8:
      McTemplateK0qzq_EtwWriteTransfer(
        v9,
        (unsigned int)USBXHCI_ETW_EVENT_SECURE_CONTROLLER_SECURE_CHANNEL_CREATE_FAILED,
        v10,
        v11,
        a2,
        v8);
    }
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140080778  mov     [rsp-18h+arg_8], rbx
0x14008077d  mov     [rsp-18h+arg_10], rsi
0x140080782  push    rbp
0x140080783  push    rdi
0x140080784  push    r14
0x140080786  mov     rbp, rsp
0x140080789  sub     rsp, 70h
0x14008078d  xor     eax, eax
0x14008078f  xorps   xmm0, xmm0
0x140080792  mov     dword ptr [rbp+var_10], eax
0x140080795  mov     rsi, rdx
0x140080798  mov     rdx, [rcx+58h]
0x14008079c  mov     r14, r8
0x14008079f  mov     [rbp+arg_0], rax
0x1400807a3  lea     r8, [rbp+arg_18]
0x1400807a7  mov     [rbp+arg_18], rax
0x1400807ab  mov     rdi, rcx
0x1400807ae  mov     rax, cs:WdfFunctions_01033
0x1400807b5  mov     rcx, cs:WdfDriverGlobals
0x1400807bc  movups  [rbp+var_40], xmm0
0x1400807c0  movups  [rbp+var_30], xmm0
0x1400807c4  movups  [rbp+var_20], xmm0
0x1400807c8  mov     rax, [rax+0E00h]
0x1400807cf  call    _guard_dispatch_icall
0x1400807d4  mov     ebx, eax
0x1400807d6  test    eax, eax
0x1400807d8  jns     short loc_140080855
0x1400807da  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400807e1  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400807e8  jz      short loc_14008080F
0x1400807ea  mov     rcx, [rdi+10h]
0x1400807ee  lea     rax, WPP_1c685d3d62dd34c321aa434cf17c39a3_Traceguids
0x1400807f5  mov     r9d, 0Ah
0x1400807fb  mov     dword ptr [rsp+70h+var_48], ebx
0x1400807ff  mov     dl, 2
0x140080801  mov     [rsp+70h+var_50], rax
0x140080806  lea     r8d, [r9+9]
0x14008080a  call    WPP_RECORDER_SF_d
0x14008080f  call    Feature_XhciCompanionEtw__private_IsEnabledDeviceUsageNoInline
0x140080814  test    eax, eax
0x140080816  jz      loc_140080999
0x14008081c  cmp     ebx, 0C0000034h
0x140080822  jz      loc_140080999
0x140080828  test    byte ptr cs:WPP_MAIN_CB.Queue+41h, 40h
0x14008082f  jz      loc_140080999
0x140080835  mov     r9d, 21h ; '!'
0x14008083b  mov     dword ptr [rsp+70h+var_48], ebx
0x14008083f  lea     rdx, USBXHCI_ETW_EVENT_SECURE_CONTROLLER_SECURE_CHANNEL_CREATE_FAILED
0x140080846  mov     [rsp+70h+var_50], rsi
0x14008084b  call    McTemplateK0qzq_EtwWriteTransfer
0x140080850  jmp     loc_140080999
0x140080855  xorps   xmm0, xmm0
0x140080858  xor     eax, eax
0x14008085a  cmp     cs:WdfClientVersionHigherThanFramework, al
0x140080860  movups  [rbp+var_40], xmm0
0x140080864  mov     [rbp+var_10], rax
0x140080868  movups  [rbp+var_30], xmm0
0x14008086c  movups  [rbp+var_20], xmm0
0x140080870  jz      short loc_140080896
0x140080872  cmp     cs:WdfStructureCount, 26h ; '&'
0x140080879  jbe     short loc_14008088D
0x14008087b  mov     rax, cs:WdfStructures
0x140080882  mov     ecx, [rax+130h]
0x140080888  mov     dword ptr [rbp+var_40], ecx
0x14008088b  jmp     short loc_14008089D
0x14008088d  mov     dword ptr [rbp+var_40], 0FFFFFFFFh
0x140080894  jmp     short loc_14008089D
0x140080896  mov     dword ptr [rbp+var_40], 38h ; '8'
0x14008089d  mov     rdx, [rbp+arg_18]
0x1400808a1  lea     r9, [rbp+arg_0]
0x1400808a5  mov     rcx, cs:WdfDriverGlobals
0x1400808ac  lea     r8, [rbp+var_40]
0x1400808b0  mov     eax, 1
0x1400808b5  mov     dword ptr [rbp+var_30+8], eax
0x1400808b8  mov     dword ptr [rbp+var_30+0Ch], eax
0x1400808bb  mov     rax, cs:off_14006C158
0x1400808c2  mov     [rbp+var_10], rax
0x1400808c6  mov     rax, cs:WdfFunctions_01033
0x1400808cd  mov     rax, [rax+658h]
0x1400808d4  call    _guard_dispatch_icall
0x1400808d9  mov     ebx, eax
0x1400808db  test    eax, eax
0x1400808dd  jns     short loc_140080931
0x1400808df  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400808e6  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400808ed  jz      short loc_140080914
0x1400808ef  mov     rcx, [rdi+10h]
0x1400808f3  lea     rax, WPP_1c685d3d62dd34c321aa434cf17c39a3_Traceguids
0x1400808fa  mov     r9d, 0Bh
0x140080900  mov     dword ptr [rsp+70h+var_48], ebx
0x140080904  mov     dl, 2
0x140080906  mov     [rsp+70h+var_50], rax
0x14008090b  lea     r8d, [r9+8]
0x14008090f  call    WPP_RECORDER_SF_d
0x140080914  call    Feature_XhciCompanionEtw__private_IsEnabledDeviceUsageNoInline
0x140080919  test    eax, eax
0x14008091b  jz      short loc_140080999
0x14008091d  test    byte ptr cs:WPP_MAIN_CB.Queue+41h, 40h
0x140080924  jz      short loc_140080999
0x140080926  mov     r9d, 22h ; '"'
0x14008092c  jmp     loc_14008083B
0x140080931  mov     rcx, [rbp+arg_0]
0x140080935  mov     rax, [rbp+arg_18]
0x140080939  mov     [rcx], rax
0x14008093c  mov     rax, [rbp+arg_0]
0x140080940  mov     [rax+8], rdi
0x140080944  mov     rcx, [rbp+arg_0]
0x140080948  add     rcx, 10h; PerformanceFrequency
0x14008094c  call    cs:__imp_KeQueryPerformanceCounter
0x140080953  nop     dword ptr [rax+rax+00h]
0x140080958  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14008095f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140080966  jz      short loc_140080992
0x140080968  mov     rax, [rbp+arg_18]
0x14008096c  mov     r9d, 0Ch
0x140080972  mov     rcx, [rdi+10h]
0x140080976  mov     dl, 4
0x140080978  mov     [rsp+70h+var_48], rax
0x14008097d  lea     rax, WPP_1c685d3d62dd34c321aa434cf17c39a3_Traceguids
0x140080984  mov     [rsp+70h+var_50], rax
0x140080989  lea     r8d, [r9+7]
0x14008098d  call    WPP_RECORDER_SF_q
0x140080992  mov     rax, [rbp+arg_0]
0x140080996  mov     [r14], rax
0x140080999  lea     r11, [rsp+70h+var_s0]
0x14008099e  mov     eax, ebx
0x1400809a0  mov     rbx, [r11+28h]
0x1400809a4  mov     rsi, [r11+30h]
0x1400809a8  mov     rsp, r11
0x1400809ab  pop     r14
0x1400809ad  pop     rdi
0x1400809ae  pop     rbp
0x1400809af  retn
```
