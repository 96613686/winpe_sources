# Controller_WdfEvtDeviceReleaseHardware

- ea: `0x14007ada0`
- end: `0x14007af84`
- name: `Controller_WdfEvtDeviceReleaseHardware`
- size: `484`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x140031928`
- `0x140035738`
- `0x140046a40`
- `0x140049ec8`
- `0x1400599b0`
- `0x1400760a8`
- `0x14007ada0`
- `0x14007d5cc`
- `0x14007f584`

## import_xrefs

- `ntoskrnl!MmUnmapIoSpace` at `0x14007af0a`
- `ntoskrnl!MmUnmapIoSpace` at `0x14007af0a`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_UnregisterComponent` at `0x14007ae9c`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_UnregisterComponent` at `0x14007ae9c`

## pseudocode

```c
__int64 __fastcall Controller_WdfEvtDeviceReleaseHardware(__int64 a1)
{
  char v1; // bl
  int v2; // edx
  __int64 v3; // rdi
  __int64 v4; // rbx

  v1 = a1;
  v3 = *(_QWORD *)((*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01033 + 1616))(
                     WdfDriverGlobals,
                     a1,
                     off_14006C2C0)
                 + 8);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v2) = 4;
    WPP_RECORDER_SF_q(*(_QWORD *)(v3 + 72), v2, 4, 53, (__int64)WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids, v1);
  }
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01033 + 3056))(
    WdfDriverGlobals,
    *(_QWORD *)(v3 + 768));
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01033 + 3056))(
    WdfDriverGlobals,
    *(_QWORD *)(v3 + 1280));
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01033 + 3056))(
    WdfDriverGlobals,
    *(_QWORD *)(v3 + 1008));
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01033 + 3056))(
    WdfDriverGlobals,
    *(_QWORD *)(v3 + 1160));
  if ( *(_QWORD *)(v3 + 1296) )
  {
    SleepstudyHelper_UnregisterComponent();
    *(_QWORD *)(v3 + 1296) = 0;
  }
  RootHub_ReleaseHardware(*(_QWORD *)(v3 + 152));
  Command_ReleaseHardware(*(_QWORD *)(v3 + 144));
  XilDeviceSlot_ReleaseHardware(*(_QWORD *)(v3 + 136));
  Interrupter_ReleaseHardware(*(_QWORD *)(v3 + 128));
  v4 = *(_QWORD *)(v3 + 88);
  if ( *(_QWORD *)(v4 + 24) )
  {
    if ( (unsigned __int8)Controller_IsSecureDevice(*(_QWORD *)(v4 + 8)) )
      Register_UnmapSecureMmio(v4);
    MmUnmapIoSpace(*(PVOID *)(v4 + 24), *(unsigned int *)(v4 + 20));
    *(_BYTE *)(v4 + 16) = 0;
    *(_QWORD *)(v4 + 24) = 0;
    *(_QWORD *)(v4 + 32) = 0;
    *(_QWORD *)(v4 + 40) = 0;
    *(_QWORD *)(v4 + 48) = 0;
    *(_QWORD *)(v4 + 56) = 0;
    *(_QWORD *)(v4 + 64) = 0;
    *(_QWORD *)(v4 + 72) = 0;
  }
  if ( !*(_BYTE *)(v3 + 16) )
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01033 + 1664))(
      WdfDriverGlobals,
      *(_QWORD *)(v3 + 8));
  return 0;
}

```

## disassembly

```asm
0x14007ada0  mov     [rsp+arg_0], rbx
0x14007ada5  push    rdi
0x14007ada6  sub     rsp, 30h
0x14007adaa  mov     rax, cs:WdfFunctions_01033
0x14007adb1  mov     rbx, rcx
0x14007adb4  mov     r8, cs:off_14006C2C0
0x14007adbb  mov     rdx, rcx
0x14007adbe  mov     rcx, cs:WdfDriverGlobals
0x14007adc5  mov     rax, [rax+650h]
0x14007adcc  call    _guard_dispatch_icall
0x14007add1  mov     rdi, [rax+8]
0x14007add5  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14007addc  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14007ade3  jz      short loc_14007AE0C
0x14007ade5  mov     rcx, [rdi+48h]
0x14007ade9  lea     rax, WPP_fc7190ad091936951f4a59c8b46d7948_Traceguids
0x14007adf0  mov     r9d, 35h ; '5'
0x14007adf6  mov     [rsp+38h+var_10], rbx
0x14007adfb  mov     [rsp+38h+var_18], rax
0x14007ae00  lea     r8d, [r9-31h]
0x14007ae04  mov     dl, r8b
0x14007ae07  call    WPP_RECORDER_SF_q
0x14007ae0c  mov     rax, cs:WdfFunctions_01033
0x14007ae13  mov     rdx, [rdi+300h]
0x14007ae1a  mov     rcx, cs:WdfDriverGlobals
0x14007ae21  mov     rax, [rax+0BF0h]
0x14007ae28  call    _guard_dispatch_icall
0x14007ae2d  mov     rax, cs:WdfFunctions_01033
0x14007ae34  mov     rdx, [rdi+500h]
0x14007ae3b  mov     rcx, cs:WdfDriverGlobals
0x14007ae42  mov     rax, [rax+0BF0h]
0x14007ae49  call    _guard_dispatch_icall
0x14007ae4e  mov     rax, cs:WdfFunctions_01033
0x14007ae55  mov     rdx, [rdi+3F0h]
0x14007ae5c  mov     rcx, cs:WdfDriverGlobals
0x14007ae63  mov     rax, [rax+0BF0h]
0x14007ae6a  call    _guard_dispatch_icall
0x14007ae6f  mov     rax, cs:WdfFunctions_01033
0x14007ae76  mov     rdx, [rdi+488h]
0x14007ae7d  mov     rcx, cs:WdfDriverGlobals
0x14007ae84  mov     rax, [rax+0BF0h]
0x14007ae8b  call    _guard_dispatch_icall
0x14007ae90  mov     rcx, [rdi+510h]
0x14007ae97  test    rcx, rcx
0x14007ae9a  jz      short loc_14007AEB3
0x14007ae9c  call    cs:__imp_SleepstudyHelper_UnregisterComponent
0x14007aea3  nop     dword ptr [rax+rax+00h]
0x14007aea8  mov     qword ptr [rdi+510h], 0
0x14007aeb3  mov     rcx, [rdi+98h]
0x14007aeba  call    RootHub_ReleaseHardware
0x14007aebf  mov     rcx, [rdi+90h]
0x14007aec6  call    Command_ReleaseHardware
0x14007aecb  mov     rcx, [rdi+88h]
0x14007aed2  call    XilDeviceSlot_ReleaseHardware
0x14007aed7  mov     rcx, [rdi+80h]
0x14007aede  call    Interrupter_ReleaseHardware
0x14007aee3  mov     rbx, [rdi+58h]
0x14007aee7  cmp     qword ptr [rbx+18h], 0
0x14007aeec  jz      short loc_14007AF52
0x14007aeee  mov     rcx, [rbx+8]
0x14007aef2  call    Controller_IsSecureDevice
0x14007aef7  test    al, al
0x14007aef9  jz      short loc_14007AF03
0x14007aefb  mov     rcx, rbx
0x14007aefe  call    Register_UnmapSecureMmio
0x14007af03  mov     edx, [rbx+14h]; NumberOfBytes
0x14007af06  mov     rcx, [rbx+18h]; BaseAddress
0x14007af0a  call    cs:__imp_MmUnmapIoSpace
0x14007af11  nop     dword ptr [rax+rax+00h]
0x14007af16  mov     byte ptr [rbx+10h], 0
0x14007af1a  mov     qword ptr [rbx+18h], 0
0x14007af22  mov     qword ptr [rbx+20h], 0
0x14007af2a  mov     qword ptr [rbx+28h], 0
0x14007af32  mov     qword ptr [rbx+30h], 0
0x14007af3a  mov     qword ptr [rbx+38h], 0
0x14007af42  mov     qword ptr [rbx+40h], 0
0x14007af4a  mov     qword ptr [rbx+48h], 0
0x14007af52  cmp     byte ptr [rdi+10h], 0
0x14007af56  jnz     short loc_14007AF76
0x14007af58  mov     rax, cs:WdfFunctions_01033
0x14007af5f  mov     rdx, [rdi+8]
0x14007af63  mov     rcx, cs:WdfDriverGlobals
0x14007af6a  mov     rax, [rax+680h]
0x14007af71  call    _guard_dispatch_icall
0x14007af76  mov     rbx, [rsp+38h+arg_0]
0x14007af7b  xor     eax, eax
0x14007af7d  add     rsp, 30h
0x14007af81  pop     rdi
0x14007af82  retn
```
