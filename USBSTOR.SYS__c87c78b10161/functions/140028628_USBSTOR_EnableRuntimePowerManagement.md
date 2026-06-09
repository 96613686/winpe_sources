# USBSTOR_EnableRuntimePowerManagement

- ea: `0x140028628`
- end: `0x140028776`
- name: `USBSTOR_EnableRuntimePowerManagement`
- size: `334`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000b0bc`
- `0x140020d90`

## callees

- `0x140013950`
- `0x140013d40`
- `0x140028628`

## import_xrefs

- `ntoskrnl!PoFxRegisterDevice` at `0x14002871d`
- `ntoskrnl!PoFxRegisterDevice` at `0x14002871d`
- `ntoskrnl!PoFxStartDevicePowerManagement` at `0x140028746`
- `ntoskrnl!PoFxStartDevicePowerManagement` at `0x140028746`
- `ntoskrnl!PoFxSetDeviceIdleTimeout` at `0x140028737`
- `ntoskrnl!PoFxSetDeviceIdleTimeout` at `0x140028737`

## pseudocode

```c
__int64 __fastcall USBSTOR_EnableRuntimePowerManagement(__int64 a1)
{
  _QWORD *v2; // rdi
  __int64 v3; // rcx
  int v4; // ebx
  _QWORD v6[20]; // [rsp+20h] [rbp-69h] BYREF
  _QWORD v7[2]; // [rsp+C0h] [rbp+37h] BYREF
  int v8; // [rsp+D0h] [rbp+47h]
  int v9; // [rsp+D4h] [rbp+4Bh]

  v9 = 0;
  memset(v6, 0, sizeof(v6));
  LODWORD(v6[0]) = 3;
  LODWORD(v6[12]) = 1;
  v6[2] = USBSTOR_FxComponentActiveCallback;
  v2 = (_QWORD *)(a1 + 1968);
  v3 = *(_QWORD *)(a1 + 8);
  v6[3] = USBSTOR_FxComponentIdleCallback;
  v6[1] = 6;
  v6[4] = USBSTOR_FxComponentIdleStateCallback;
  v6[5] = USBSTOR_FxDevicePowerRequiredCallback;
  v6[6] = USBSTOR_FxDevicePowerNotRequiredCallback;
  v6[7] = USBSTOR_FxPowerControlCallback;
  v6[8] = USBSTOR_FxDirectedPowerUpCallback;
  v6[9] = USBSTOR_FxDirectedPowerDownCallback;
  v6[17] = v7;
  v6[11] = a1;
  v7[0] = 0;
  v7[1] = 0;
  v8 = -1;
  v6[16] = 0x100000000LL;
  LODWORD(v6[10]) = 0;
  v4 = PoFxRegisterDevice(v3, v6, a1 + 1968);
  if ( v4 >= 0 )
  {
    PoFxSetDeviceIdleTimeout(*v2, 600000000);
    PoFxStartDevicePowerManagement(*v2);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140028628  mov     [rsp-8+arg_8], rbx
0x14002862d  mov     [rsp-8+arg_10], rdi
0x140028632  push    rbp
0x140028633  lea     rbp, [rsp-57h]
0x140028638  sub     rsp, 0E0h
0x14002863f  mov     rax, cs:__security_cookie
0x140028646  xor     rax, rsp
0x140028649  mov     [rbp+57h+var_8], rax
0x14002864d  mov     rbx, rcx
0x140028650  mov     [rbp+57h+var_C], 0
0x140028657  lea     rcx, [rbp+57h+var_C0]; void *
0x14002865b  xor     edx, edx; Val
0x14002865d  mov     r8d, 0A0h; Size
0x140028663  call    memset
0x140028668  mov     ecx, 1
0x14002866d  mov     [rbp+57h+var_C0], 3
0x140028674  lea     rax, USBSTOR_FxComponentActiveCallback
0x14002867b  mov     [rbp+57h+var_60], ecx
0x14002867e  mov     [rbp+57h+var_B0], rax
0x140028682  lea     rdi, [rbx+7B0h]
0x140028689  lea     rax, USBSTOR_FxComponentIdleCallback
0x140028690  mov     [rbp+57h+var_3C], ecx
0x140028693  mov     rcx, [rbx+8]
0x140028697  lea     rdx, [rbp+57h+var_C0]
0x14002869b  mov     [rbp+57h+var_A8], rax
0x14002869f  mov     r8, rdi
0x1400286a2  lea     rax, USBSTOR_FxComponentIdleStateCallback
0x1400286a9  mov     [rbp+57h+var_B8], 6
0x1400286b1  mov     [rbp+57h+var_A0], rax
0x1400286b5  lea     rax, USBSTOR_FxDevicePowerRequiredCallback
0x1400286bc  mov     [rbp+57h+var_98], rax
0x1400286c0  lea     rax, USBSTOR_FxDevicePowerNotRequiredCallback
0x1400286c7  mov     [rbp+57h+var_90], rax
0x1400286cb  lea     rax, USBSTOR_FxPowerControlCallback
0x1400286d2  mov     [rbp+57h+var_88], rax
0x1400286d6  lea     rax, USBSTOR_FxDirectedPowerUpCallback
0x1400286dd  mov     [rbp+57h+var_80], rax
0x1400286e1  lea     rax, USBSTOR_FxDirectedPowerDownCallback
0x1400286e8  mov     [rbp+57h+var_78], rax
0x1400286ec  lea     rax, [rbp+57h+var_20]
0x1400286f0  mov     [rbp+57h+var_38], rax
0x1400286f4  mov     [rbp+57h+var_68], rbx
0x1400286f8  mov     [rbp+57h+var_20], 0
0x140028700  mov     [rbp+57h+var_18], 0
0x140028708  mov     [rbp+57h+var_10], 0FFFFFFFFh
0x14002870f  mov     [rbp+57h+var_40], 0
0x140028716  mov     [rbp+57h+var_70], 0
0x14002871d  call    cs:__imp_PoFxRegisterDevice
0x140028724  nop     dword ptr [rax+rax+00h]
0x140028729  mov     ebx, eax
0x14002872b  test    eax, eax
0x14002872d  js      short loc_140028752
0x14002872f  mov     rcx, [rdi]
0x140028732  mov     edx, 23C34600h
0x140028737  call    cs:__imp_PoFxSetDeviceIdleTimeout
0x14002873e  nop     dword ptr [rax+rax+00h]
0x140028743  mov     rcx, [rdi]
0x140028746  call    cs:__imp_PoFxStartDevicePowerManagement
0x14002874d  nop     dword ptr [rax+rax+00h]
0x140028752  mov     eax, ebx
0x140028754  mov     rcx, [rbp+57h+var_8]
0x140028758  xor     rcx, rsp; StackCookie
0x14002875b  call    __security_check_cookie
0x140028760  lea     r11, [rsp+0E0h+var_s0]
0x140028768  mov     rbx, [r11+18h]
0x14002876c  mov     rdi, [r11+20h]
0x140028770  mov     rsp, r11
0x140028773  pop     rbp
0x140028774  retn
```
