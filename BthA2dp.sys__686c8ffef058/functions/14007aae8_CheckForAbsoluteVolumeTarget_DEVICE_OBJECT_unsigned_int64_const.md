# CheckForAbsoluteVolumeTarget(_DEVICE_OBJECT *,unsigned __int64 const &)

- ea: `0x14007aae8`
- end: `0x14007ae5f`
- name: `?CheckForAbsoluteVolumeTarget@@YAJPEAU_DEVICE_OBJECT@@AEB_K@Z`
- size: `887`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, const unsigned __int64 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x140079014`

## callees

- `0x14000e690`
- `0x14000f570`
- `0x1400126ac`
- `0x1400349ec`
- `0x140034a9c`
- `0x14005c7d0`
- `0x1400784bc`
- `0x14007aae8`

## import_xrefs

- `btampm!BtaMpmGetRemoteDeviceProfileVersionAndAttribute` at `0x14007ab45`
- `btampm!BtaMpmGetRemoteDeviceProfileVersionAndAttribute` at `0x14007ab45`

## string_xrefs

- `0x14007acbd`: `\Registry\Machine\SYSTEM\CurrentControlSet\Control\Bluetooth\Audio\AVRCP\CT`

## pseudocode

```c
__int64 __fastcall CheckForAbsoluteVolumeTarget(struct _DEVICE_OBJECT *a1, const unsigned __int64 *a2)
{
  int v2; // edx
  int RemoteDeviceProfileVersionAndAttribute; // ebx
  int v4; // r8d
  _WORD v6[4]; // [rsp+50h] [rbp-B0h] BYREF

  v6[0] = 0;
  v6[2] = 0;
  RemoteDeviceProfileVersionAndAttribute = BtaMpmGetRemoteDeviceProfileVersionAndAttribute(
                                             a1,
                                             a2,
                                             &AVRemoteControlTargetServiceClass_UUID,
                                             &AVRemoteControlServiceClass_UUID);
  if ( RemoteDeviceProfileVersionAndAttribute >= 0 )
  {
    LOBYTE(v2) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
    if ( (_BYTE)v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v4) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_HH(
        WPP_GLOBAL_Control->AttachedDevice,
        v2,
        v4,
        WPP_GLOBAL_Control->DeviceExtension,
        785,
        (unsigned int)v6,
        15);
    }
    return 3221226021LL;
  }
  else
  {
    LOBYTE(v2) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
    if ( (_BYTE)v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v4) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        v2,
        v4,
        WPP_GLOBAL_Control->DeviceExtension,
        4,
        5,
        14,
        (__int64)WPP_4800887547dd3d4e33fad0eec8a4812f_Traceguids,
        RemoteDeviceProfileVersionAndAttribute);
    }
    return (unsigned int)RemoteDeviceProfileVersionAndAttribute;
  }
}

```

## disassembly

```asm
0x14007aae8  mov     [rsp-8+arg_10], rbx
0x14007aaed  mov     [rsp-8+arg_18], rdi
0x14007aaf2  push    rbp
0x14007aaf3  lea     rbp, [rsp-20h]
0x14007aaf8  sub     rsp, 120h
0x14007aaff  mov     rax, cs:__security_cookie
0x14007ab06  xor     rax, rsp
0x14007ab09  mov     [rbp+20h+var_10], rax
0x14007ab0d  xor     eax, eax
0x14007ab0f  lea     r9, AVRemoteControlServiceClass_UUID
0x14007ab16  mov     [rsp+120h+var_D0], ax
0x14007ab1b  lea     r8, AVRemoteControlTargetServiceClass_UUID
0x14007ab22  mov     [rsp+120h+var_CC], ax
0x14007ab27  mov     rdi, rdx
0x14007ab2a  lea     rax, [rsp+120h+var_CC]
0x14007ab2f  mov     [rsp+120h+var_F0], rax
0x14007ab34  lea     rax, [rsp+120h+var_D0]
0x14007ab39  mov     [rsp+120h+var_F8], rax
0x14007ab3e  mov     [rsp+120h+var_100], 311h
0x14007ab45  call    cs:__imp_BtaMpmGetRemoteDeviceProfileVersionAndAttribute
0x14007ab4c  nop     dword ptr [rax+rax+00h]
0x14007ab51  mov     ebx, eax
0x14007ab53  test    eax, eax
0x14007ab55  jns     short loc_14007ABD3
0x14007ab57  mov     r10, cs:WPP_GLOBAL_Control
0x14007ab5e  lea     rcx, WPP_GLOBAL_Control
0x14007ab65  cmp     r10, rcx
0x14007ab68  jz      short loc_14007AB7E
0x14007ab6a  mov     ecx, [r10+2Ch]
0x14007ab6e  test    cl, 10h
0x14007ab71  jz      short loc_14007AB7E
0x14007ab73  cmp     byte ptr [r10+29h], 4
0x14007ab78  jb      short loc_14007AB7E
0x14007ab7a  mov     dl, 1
0x14007ab7c  jmp     short loc_14007AB80
0x14007ab7e  xor     dl, dl
0x14007ab80  lea     rax, WPP_RECORDER_INITIALIZED
0x14007ab87  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14007ab8e  setnz   r8b
0x14007ab92  test    dl, dl
0x14007ab94  jnz     short loc_14007AB9B
0x14007ab96  test    r8b, r8b
0x14007ab99  jz      short loc_14007ABCC
0x14007ab9b  mov     r9, [r10+40h]
0x14007ab9f  lea     rax, WPP_4800887547dd3d4e33fad0eec8a4812f_Traceguids
0x14007aba6  mov     rcx, [r10+18h]
0x14007abaa  mov     [rsp+120h+var_E0], ebx
0x14007abae  mov     [rsp+120h+var_E8], rax
0x14007abb3  mov     word ptr [rsp+120h+var_F0], 0Eh
0x14007abba  mov     dword ptr [rsp+120h+var_F8], 5
0x14007abc2  mov     byte ptr [rsp+120h+var_100], 4
0x14007abc7  call    WPP_RECORDER_AND_TRACE_SF_d
0x14007abcc  mov     eax, ebx
0x14007abce  jmp     loc_14007AE3D
0x14007abd3  movzx   r9d, [rsp+120h+var_D0]
0x14007abd9  mov     r11d, 104h
0x14007abdf  cmp     r9w, r11w
0x14007abe3  jnb     short loc_14007AC52
0x14007abe5  mov     r10, cs:WPP_GLOBAL_Control
0x14007abec  lea     rcx, WPP_GLOBAL_Control
0x14007abf3  cmp     r10, rcx
0x14007abf6  jz      short loc_14007AC0B
0x14007abf8  mov     eax, [r10+2Ch]
0x14007abfc  test    al, 10h
0x14007abfe  jz      short loc_14007AC0B
0x14007ac00  cmp     byte ptr [r10+29h], 4
0x14007ac05  jb      short loc_14007AC0B
0x14007ac07  mov     dl, 1
0x14007ac09  jmp     short loc_14007AC0D
0x14007ac0b  xor     dl, dl
0x14007ac0d  lea     rax, WPP_RECORDER_INITIALIZED
0x14007ac14  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14007ac1b  setnz   r8b
0x14007ac1f  test    dl, dl
0x14007ac21  jnz     short loc_14007AC28
0x14007ac23  test    r8b, r8b
0x14007ac26  jz      short loc_14007AC48
0x14007ac28  mov     rcx, [r10+18h]
0x14007ac2c  mov     [rsp+120h+var_D8], r11w
0x14007ac32  mov     word ptr [rsp+120h+var_E0], r9w
0x14007ac38  mov     r9, [r10+40h]
0x14007ac3c  mov     word ptr [rsp+120h+var_F0], 0Fh
0x14007ac43  call    WPP_RECORDER_AND_TRACE_SF_HH
0x14007ac48  mov     eax, 0C0000225h
0x14007ac4d  jmp     loc_14007AE3D
0x14007ac52  movzx   r9d, [rsp+120h+var_CC]
0x14007ac58  test    r9b, 2
0x14007ac5c  jnz     short loc_14007ACBD
0x14007ac5e  mov     r10, cs:WPP_GLOBAL_Control
0x14007ac65  lea     rcx, WPP_GLOBAL_Control
0x14007ac6c  cmp     r10, rcx
0x14007ac6f  jz      short loc_14007AC84
0x14007ac71  mov     eax, [r10+2Ch]
0x14007ac75  test    al, 10h
0x14007ac77  jz      short loc_14007AC84
0x14007ac79  cmp     byte ptr [r10+29h], 4
0x14007ac7e  jb      short loc_14007AC84
0x14007ac80  mov     dl, 1
0x14007ac82  jmp     short loc_14007AC86
0x14007ac84  xor     dl, dl
0x14007ac86  lea     rax, WPP_RECORDER_INITIALIZED
0x14007ac8d  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14007ac94  setnz   r8b
0x14007ac98  test    dl, dl
0x14007ac9a  jnz     short loc_14007ACA5
0x14007ac9c  test    r8b, r8b
0x14007ac9f  jz      loc_14007AE34
0x14007aca5  mov     rcx, [r10+18h]
0x14007aca9  mov     word ptr [rsp+120h+var_E0], r9w
0x14007acaf  mov     r9, [r10+40h]
0x14007acb3  call    WPP_RECORDER_AND_TRACE_SF_H
0x14007acb8  jmp     loc_14007AE34
0x14007acbd  movaps  xmm0, xmmword ptr cs:aRegistryMachin; "\\Registry\\Machine\\SYSTEM\\CurrentCon"...
0x14007acc4  lea     rdx, aDisableabsolut; "DisableAbsoluteVolume"
0x14007accb  movaps  xmm1, xmmword ptr cs:aRegistryMachin+10h; "y\\Machine\\SYSTEM\\CurrentControlSet\\"...
0x14007acd2  lea     rcx, [rsp+120h+var_C8]
0x14007acd7  mov     rax, qword ptr cs:aRegistryMachin+90h; "\\CT"
0x14007acde  xor     r8d, r8d
0x14007ace1  movups  [rsp+120h+var_B0], xmm0
0x14007ace6  mov     [rbp+20h+var_20], rax
0x14007acea  lea     rax, [rsp+120h+var_B0]
0x14007acef  movaps  xmm0, xmmword ptr cs:aRegistryMachin+20h; "e\\SYSTEM\\CurrentControlSet\\Control\\"...
0x14007acf6  movups  [rbp+20h+var_90], xmm0
0x14007acfa  mov     [rsp+120h+var_C8], 980096h
0x14007ad03  movaps  xmm0, xmmword ptr cs:aRegistryMachin+40h; "ControlSet\\Control\\Bluetooth\\Audio\\"...
0x14007ad0a  movups  [rbp+20h+var_A0], xmm1
0x14007ad0e  mov     [rsp+120h+var_C0], rax
0x14007ad13  movaps  xmm1, xmmword ptr cs:aRegistryMachin+30h; "\\CurrentControlSet\\Control\\Bluetooth"...
0x14007ad1a  movups  [rbp+20h+var_70], xmm0
0x14007ad1e  movaps  xmm0, xmmword ptr cs:aRegistryMachin+60h; "ol\\Bluetooth\\Audio\\AVRCP\\CT"
0x14007ad25  movups  [rbp+20h+var_80], xmm1
0x14007ad29  movaps  xmm1, xmmword ptr cs:aRegistryMachin+50h; "et\\Control\\Bluetooth\\Audio\\AVRCP\\C"...
0x14007ad30  movups  [rbp+20h+var_50], xmm0
0x14007ad34  movaps  xmm0, xmmword ptr cs:aRegistryMachin+80h; "io\\AVRCP\\CT"
0x14007ad3b  movups  [rbp+20h+var_60], xmm1
0x14007ad3f  movaps  xmm1, xmmword ptr cs:aRegistryMachin+70h; "ooth\\Audio\\AVRCP\\CT"
0x14007ad46  movups  [rbp+20h+var_30], xmm0
0x14007ad4a  movups  [rbp+20h+var_40], xmm1
0x14007ad4e  call    QueryRegistryDWord
0x14007ad53  test    eax, eax
0x14007ad55  jz      short loc_14007ADB3
0x14007ad57  mov     r10, cs:WPP_GLOBAL_Control
0x14007ad5e  lea     rcx, WPP_GLOBAL_Control
0x14007ad65  cmp     r10, rcx
0x14007ad68  jz      short loc_14007AD7D
0x14007ad6a  mov     eax, [r10+2Ch]
0x14007ad6e  test    al, 10h
0x14007ad70  jz      short loc_14007AD7D
0x14007ad72  cmp     byte ptr [r10+29h], 4
0x14007ad77  jb      short loc_14007AD7D
0x14007ad79  mov     dl, 1
0x14007ad7b  jmp     short loc_14007AD7F
0x14007ad7d  xor     dl, dl
0x14007ad7f  lea     rax, WPP_RECORDER_INITIALIZED
0x14007ad86  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14007ad8d  setnz   r8b
0x14007ad91  test    dl, dl
0x14007ad93  jnz     short loc_14007AD9E
0x14007ad95  test    r8b, r8b
0x14007ad98  jz      loc_14007AE34
0x14007ad9e  lea     rax, WPP_4800887547dd3d4e33fad0eec8a4812f_Traceguids
0x14007ada5  mov     [rsp+120h+var_E8], rax
0x14007adaa  mov     word ptr [rsp+120h+var_F0], 11h
0x14007adb1  jmp     short loc_14007AE1A
0x14007adb3  mov     rcx, [rdi]
0x14007adb6  xor     r8d, r8d
0x14007adb9  lea     edx, [r8+8]
0x14007adbd  call    BthQueryDeviceCompatFlags
0x14007adc2  mov     dl, 1
0x14007adc4  test    dl, al
0x14007adc6  jz      short loc_14007AE3B
0x14007adc8  mov     r10, cs:WPP_GLOBAL_Control
0x14007adcf  lea     rcx, WPP_GLOBAL_Control
0x14007add6  cmp     r10, rcx
0x14007add9  jz      short loc_14007ADEA
0x14007addb  mov     eax, [r10+2Ch]
0x14007addf  test    al, 10h
0x14007ade1  jz      short loc_14007ADEA
0x14007ade3  cmp     byte ptr [r10+29h], 4
0x14007ade8  jnb     short loc_14007ADEC
0x14007adea  xor     dl, dl
0x14007adec  lea     rax, WPP_RECORDER_INITIALIZED
0x14007adf3  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14007adfa  setnz   r8b
0x14007adfe  test    dl, dl
0x14007ae00  jnz     short loc_14007AE07
0x14007ae02  test    r8b, r8b
0x14007ae05  jz      short loc_14007AE34
0x14007ae07  lea     rax, WPP_4800887547dd3d4e33fad0eec8a4812f_Traceguids
0x14007ae0e  mov     [rsp+120h+var_E8], rax
0x14007ae13  mov     word ptr [rsp+120h+var_F0], 12h
0x14007ae1a  mov     r9, [r10+40h]
0x14007ae1e  mov     rcx, [r10+18h]
0x14007ae22  mov     dword ptr [rsp+120h+var_F8], 5
0x14007ae2a  mov     byte ptr [rsp+120h+var_100], 4
0x14007ae2f  call    WPP_RECORDER_AND_TRACE_SF_
0x14007ae34  mov     eax, 0C00000BBh
0x14007ae39  jmp     short loc_14007AE3D
0x14007ae3b  xor     eax, eax
0x14007ae3d  mov     rcx, [rbp+20h+var_10]
0x14007ae41  xor     rcx, rsp; StackCookie
0x14007ae44  call    __security_check_cookie
0x14007ae49  lea     r11, [rsp+120h+var_s0]
0x14007ae51  mov     rbx, [r11+20h]
0x14007ae55  mov     rdi, [r11+28h]
0x14007ae59  mov     rsp, r11
0x14007ae5c  pop     rbp
0x14007ae5d  retn
```
