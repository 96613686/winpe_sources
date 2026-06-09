# WxDevice::DeviceStopPowerIdleDetection(bool)

- ea: `0x1400cc414`
- end: `0x1400cc503`
- name: `?DeviceStopPowerIdleDetection@WxDevice@@QEAAJ_N@Z`
- size: `239`
- prototype: `__int64 __fastcall(WxDevice *__hidden this, bool)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1400557ac`

## callees

- `0x140024428`
- `0x140024a20`
- `0x1400cc414`
- `0x1400dfd40`

## string_xrefs

- `0x1400cc442`: `onecoreuap\net\wlan\sys\wificx\extension\src\wxdevice.cpp`

## pseudocode

```c
__int64 __fastcall WxDevice::DeviceStopPowerIdleDetection(WxDevice *this, __int64 a2, int a3)
{
  int v4; // edx
  int v5; // edi

  if ( *((_BYTE *)this + 5512) )
  {
    v5 = 255;
  }
  else
  {
    v5 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, _QWORD, __int64, int, const char *))(WdfFunctions_01031 + 3504))(
           WdfDriverGlobals,
           *((_QWORD *)this + 1),
           0,
           1230010455,
           861,
           "onecoreuap\\net\\wlan\\sys\\wificx\\extension\\src\\wxdevice.cpp");
    if ( v5 < 0 )
    {
      *((_BYTE *)this + 5512) = 0;
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return (unsigned int)v5;
      LOBYTE(v4) = 2;
      WPP_RECORDER_SF_q(
        WPP_GLOBAL_Control->DeviceExtension,
        v4,
        a3,
        64,
        (__int64)WPP_270fc2b2b10437060e298a6bcfb11c73_Traceguids,
        *((_QWORD *)this + 1));
    }
    else
    {
      *((_BYTE *)this + 5512) = 1;
    }
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_Ld(
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      a3,
      65,
      (__int64)WPP_270fc2b2b10437060e298a6bcfb11c73_Traceguids,
      *((_BYTE *)this + 5512),
      v5);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1400cc414  push    rbx
0x1400cc416  push    rbp
0x1400cc417  push    rsi
0x1400cc418  push    rdi
0x1400cc419  sub     rsp, 48h
0x1400cc41d  cmp     byte ptr [rcx+1588h], 0
0x1400cc424  lea     rsi, WPP_RECORDER_INITIALIZED
0x1400cc42b  mov     rbx, rcx
0x1400cc42e  lea     rbp, WPP_270fc2b2b10437060e298a6bcfb11c73_Traceguids
0x1400cc435  jnz     loc_1400CC4BD
0x1400cc43b  mov     rax, cs:WdfFunctions_01031
0x1400cc442  lea     rcx, aOnecoreuapNetW; "onecoreuap\\net\\wlan\\sys\\wificx\\ext"...
0x1400cc449  mov     rdx, [rbx+8]
0x1400cc44d  mov     r9d, 49507857h
0x1400cc453  mov     [rsp+68h+var_40], rcx
0x1400cc458  xor     r8d, r8d
0x1400cc45b  mov     rcx, cs:WdfDriverGlobals
0x1400cc462  mov     rax, [rax+0DB0h]
0x1400cc469  mov     dword ptr [rsp+68h+var_48], 35Dh
0x1400cc471  call    _guard_dispatch_icall
0x1400cc476  mov     edi, eax
0x1400cc478  test    eax, eax
0x1400cc47a  js      short loc_1400CC485
0x1400cc47c  mov     byte ptr [rbx+1588h], 1
0x1400cc483  jmp     short loc_1400CC4C2
0x1400cc485  mov     byte ptr [rbx+1588h], 0
0x1400cc48c  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400cc493  jz      short loc_1400CC4F7
0x1400cc495  mov     rcx, cs:WPP_GLOBAL_Control
0x1400cc49c  mov     r9d, 40h ; '@'
0x1400cc4a2  mov     rax, [rbx+8]
0x1400cc4a6  mov     dl, 2
0x1400cc4a8  mov     [rsp+68h+var_40], rax
0x1400cc4ad  mov     [rsp+68h+var_48], rbp
0x1400cc4b2  mov     rcx, [rcx+40h]
0x1400cc4b6  call    WPP_RECORDER_SF_q
0x1400cc4bb  jmp     short loc_1400CC4C2
0x1400cc4bd  mov     edi, 0FFh
0x1400cc4c2  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400cc4c9  jz      short loc_1400CC4F7
0x1400cc4cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400cc4d2  mov     r9d, 41h ; 'A'
0x1400cc4d8  movzx   eax, byte ptr [rbx+1588h]
0x1400cc4df  mov     dl, 4
0x1400cc4e1  mov     [rsp+68h+var_38], edi
0x1400cc4e5  mov     dword ptr [rsp+68h+var_40], eax
0x1400cc4e9  mov     rcx, [rcx+40h]
0x1400cc4ed  mov     [rsp+68h+var_48], rbp
0x1400cc4f2  call    WPP_RECORDER_SF_Ld
0x1400cc4f7  mov     eax, edi
0x1400cc4f9  add     rsp, 48h
0x1400cc4fd  pop     rdi
0x1400cc4fe  pop     rsi
0x1400cc4ff  pop     rbp
0x1400cc500  pop     rbx
0x1400cc501  retn
```
