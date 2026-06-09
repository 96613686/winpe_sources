# WxDevice::DeviceResumePowerIdleDetection(void)

- ea: `0x1400cc380`
- end: `0x1400cc40e`
- name: `?DeviceResumePowerIdleDetection@WxDevice@@QEAAXXZ`
- size: `142`
- prototype: `void __fastcall(WxDevice *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1400557ac`

## callees

- `0x14000d054`
- `0x1400cc380`
- `0x1400dfd40`

## string_xrefs

- `0x1400cc399`: `onecoreuap\net\wlan\sys\wificx\extension\src\wxdevice.cpp`

## pseudocode

```c
void __fastcall WxDevice::DeviceResumePowerIdleDetection(WxDevice *this)
{
  int v2; // edx

  if ( *((_BYTE *)this + 5512) )
  {
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, __int64, __int64, const char *))(WdfFunctions_01031 + 3512))(
      WdfDriverGlobals,
      *((_QWORD *)this + 1),
      1230010455,
      887,
      "onecoreuap\\net\\wlan\\sys\\wificx\\extension\\src\\wxdevice.cpp");
    *((_BYTE *)this + 5512) = 0;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v2) = 4;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v2,
        1,
        66,
        (__int64)WPP_270fc2b2b10437060e298a6bcfb11c73_Traceguids);
    }
  }
}

```

## disassembly

```asm
0x1400cc380  push    rbx
0x1400cc382  sub     rsp, 30h
0x1400cc386  cmp     byte ptr [rcx+1588h], 0
0x1400cc38d  mov     rbx, rcx
0x1400cc390  jz      short loc_1400CC407
0x1400cc392  mov     rax, cs:WdfFunctions_01031
0x1400cc399  lea     rcx, aOnecoreuapNetW; "onecoreuap\\net\\wlan\\sys\\wificx\\ext"...
0x1400cc3a0  mov     rdx, [rbx+8]
0x1400cc3a4  mov     r9d, 377h
0x1400cc3aa  mov     [rsp+38h+var_18], rcx
0x1400cc3af  mov     r8d, 49507857h
0x1400cc3b5  mov     rcx, cs:WdfDriverGlobals
0x1400cc3bc  mov     rax, [rax+0DB8h]
0x1400cc3c3  call    _guard_dispatch_icall
0x1400cc3c8  mov     byte ptr [rbx+1588h], 0
0x1400cc3cf  lea     rax, WPP_RECORDER_INITIALIZED
0x1400cc3d6  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400cc3dd  jz      short loc_1400CC407
0x1400cc3df  mov     rcx, cs:WPP_GLOBAL_Control
0x1400cc3e6  lea     rax, WPP_270fc2b2b10437060e298a6bcfb11c73_Traceguids
0x1400cc3ed  mov     r9d, 42h ; 'B'
0x1400cc3f3  mov     [rsp+38h+var_18], rax
0x1400cc3f8  mov     dl, 4
0x1400cc3fa  mov     rcx, [rcx+40h]
0x1400cc3fe  lea     r8d, [r9-41h]
0x1400cc402  call    WPP_RECORDER_SF_
0x1400cc407  add     rsp, 30h
0x1400cc40b  pop     rbx
0x1400cc40c  retn
```
