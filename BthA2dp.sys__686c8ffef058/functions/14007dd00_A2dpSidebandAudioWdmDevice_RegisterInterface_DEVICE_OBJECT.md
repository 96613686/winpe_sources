# A2dpSidebandAudioWdmDevice::RegisterInterface(_DEVICE_OBJECT *)

- ea: `0x14007dd00`
- end: `0x14007df18`
- name: `?RegisterInterface@A2dpSidebandAudioWdmDevice@@UEAAJPEAU_DEVICE_OBJECT@@@Z`
- size: `536`
- prototype: `__int64 __fastcall(A2dpSidebandAudioWdmDevice *__hidden this, PDEVICE_OBJECT PhysicalDeviceObject)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1400320a8`

## callees

- `0x140003530`
- `0x14000e690`
- `0x14007d8b0`
- `0x14007dc1c`
- `0x14007dd00`

## import_xrefs

- `ntoskrnl!IoRegisterDeviceInterface` at `0x14007de1d`
- `ntoskrnl!IoRegisterDeviceInterface` at `0x14007de1d`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x14007de8a`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x14007de8a`

## pseudocode

```c
__int64 __fastcall A2dpSidebandAudioWdmDevice::RegisterInterface(
        A2dpSidebandAudioWdmDevice *this,
        PDEVICE_OBJECT PhysicalDeviceObject)
{
  struct _DEVICE_OBJECT *v2; // r14
  char v4; // bl
  int v5; // edx
  NTSTATUS v6; // esi
  int v7; // r8d
  PDEVICE_OBJECT v8; // r10
  PVOID DeviceExtension; // r9
  struct _DEVICE_OBJECT *AttachedDevice; // rcx
  NTSTATUS v12; // eax
  __int16 v13; // [rsp+30h] [rbp-68h]
  char v14; // [rsp+40h] [rbp-58h]

  v2 = PhysicalDeviceObject;
  v4 = 1;
  LOBYTE(PhysicalDeviceObject) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0
                              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  if ( (_BYTE)PhysicalDeviceObject || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_q(
      WPP_GLOBAL_Control->AttachedDevice,
      (_DWORD)PhysicalDeviceObject,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      19,
      28,
      (__int64)WPP_eb305fa737073720bb4070d66a1cdc5e_Traceguids,
      (char)this);
  v6 = A2dpSidebandAudioWdmDevice::InitializeInternal(this);
  if ( v6 < 0 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      v4 = 0;
    }
    LOBYTE(v7) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( !v4 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return (unsigned int)v6;
    v14 = v6;
    v13 = 29;
    goto LABEL_17;
  }
  v12 = IoRegisterDeviceInterface(
          v2,
          &GUID_DEVINTERFACE_A2DP_SIDEBAND_AUDIO,
          (PUNICODE_STRING)&ReferenceString,
          (PUNICODE_STRING)((char *)this + 472));
  v6 = 0;
  if ( v12 != 0x40000000 )
    v6 = v12;
  if ( v6 < 0 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      v4 = 0;
    }
    LOBYTE(v7) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( !v4 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return (unsigned int)v6;
    DeviceExtension = WPP_GLOBAL_Control->DeviceExtension;
    AttachedDevice = WPP_GLOBAL_Control->AttachedDevice;
    v14 = v6;
    v13 = 30;
    goto LABEL_18;
  }
  v6 = IoSetDeviceInterfaceState((PUNICODE_STRING)((char *)this + 472), 1u);
  if ( v6 < 0 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      v4 = 0;
    }
    LOBYTE(v7) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( !v4 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return (unsigned int)v6;
    v14 = v6;
    v13 = 31;
LABEL_17:
    DeviceExtension = v8->DeviceExtension;
    AttachedDevice = v8->AttachedDevice;
LABEL_18:
    LOBYTE(v5) = v4;
    WPP_RECORDER_AND_TRACE_SF_d(
      (_DWORD)AttachedDevice,
      v5,
      v7,
      (_DWORD)DeviceExtension,
      2,
      18,
      v13,
      (__int64)WPP_eb305fa737073720bb4070d66a1cdc5e_Traceguids,
      v14);
    return (unsigned int)v6;
  }
  *((_BYTE *)this + 497) = 1;
  _mm_mfence();
  *((_BYTE *)this + 499) = 1;
  _mm_mfence();
  A2dpSidebandAudioWdmDevice::LogA2dpDeviceOwnership(this);
  return 0;
}

```

## disassembly

```asm
0x14007dd00  push    rbx
0x14007dd02  push    rbp
0x14007dd03  push    rsi
0x14007dd04  push    rdi
0x14007dd05  push    r12
0x14007dd07  push    r13
0x14007dd09  push    r14
0x14007dd0b  push    r15
0x14007dd0d  sub     rsp, 58h
0x14007dd11  mov     r14, rdx
0x14007dd14  mov     rdi, rcx
0x14007dd17  mov     rcx, cs:WPP_GLOBAL_Control
0x14007dd1e  lea     r15, WPP_GLOBAL_Control
0x14007dd25  mov     bl, 1
0x14007dd27  cmp     rcx, r15
0x14007dd2a  jz      short loc_14007DD3F
0x14007dd2c  test    dword ptr [rcx+2Ch], 40000h
0x14007dd33  jz      short loc_14007DD3F
0x14007dd35  cmp     byte ptr [rcx+29h], 4
0x14007dd39  jb      short loc_14007DD3F
0x14007dd3b  mov     dl, bl
0x14007dd3d  jmp     short loc_14007DD41
0x14007dd3f  xor     dl, dl
0x14007dd41  lea     r12, WPP_RECORDER_INITIALIZED
0x14007dd48  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14007dd4f  lea     r13, WPP_eb305fa737073720bb4070d66a1cdc5e_Traceguids
0x14007dd56  setnz   r8b
0x14007dd5a  test    dl, dl
0x14007dd5c  jnz     short loc_14007DD63
0x14007dd5e  test    r8b, r8b
0x14007dd61  jz      short loc_14007DD8E
0x14007dd63  mov     r9, [rcx+40h]
0x14007dd67  mov     rcx, [rcx+18h]
0x14007dd6b  mov     qword ptr [rsp+98h+var_58], rdi
0x14007dd70  mov     [rsp+98h+var_60], r13
0x14007dd75  mov     [rsp+98h+var_68], 1Ch
0x14007dd7c  mov     [rsp+98h+var_70], 13h
0x14007dd84  mov     [rsp+98h+var_78], 4
0x14007dd89  call    WPP_RECORDER_AND_TRACE_SF_q
0x14007dd8e  mov     rcx, rdi; this
0x14007dd91  call    ?InitializeInternal@A2dpSidebandAudioWdmDevice@@AEAAJXZ; A2dpSidebandAudioWdmDevice::InitializeInternal(void)
0x14007dd96  mov     esi, eax
0x14007dd98  test    eax, eax
0x14007dd9a  jns     short loc_14007DE02
0x14007dd9c  mov     r10, cs:WPP_GLOBAL_Control
0x14007dda3  cmp     r10, r15
0x14007dda6  jz      short loc_14007DDB9
0x14007dda8  test    dword ptr [r10+2Ch], 20000h
0x14007ddb0  jz      short loc_14007DDB9
0x14007ddb2  cmp     byte ptr [r10+29h], 2
0x14007ddb7  jnb     short loc_14007DDBB
0x14007ddb9  xor     bl, bl
0x14007ddbb  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14007ddc2  setnz   r8b
0x14007ddc6  test    bl, bl
0x14007ddc8  jnz     short loc_14007DDCF
0x14007ddca  test    r8b, r8b
0x14007ddcd  jz      short loc_14007DDFB
0x14007ddcf  mov     dword ptr [rsp+98h+var_58], esi
0x14007ddd3  mov     [rsp+98h+var_60], r13
0x14007ddd8  mov     [rsp+98h+var_68], 1Dh
0x14007dddf  mov     r9, [r10+40h]
0x14007dde3  mov     rcx, [r10+18h]
0x14007dde7  mov     [rsp+98h+var_70], 12h
0x14007ddef  mov     dl, bl
0x14007ddf1  mov     [rsp+98h+var_78], 2
0x14007ddf6  call    WPP_RECORDER_AND_TRACE_SF_d
0x14007ddfb  mov     eax, esi
0x14007ddfd  jmp     loc_14007DF06
0x14007de02  lea     rbp, [rdi+1D8h]
0x14007de09  mov     rcx, r14; PhysicalDeviceObject
0x14007de0c  mov     r9, rbp; SymbolicLinkName
0x14007de0f  lea     r8, ReferenceString; ReferenceString
0x14007de16  lea     rdx, GUID_DEVINTERFACE_A2DP_SIDEBAND_AUDIO; InterfaceClassGuid
0x14007de1d  call    cs:__imp_IoRegisterDeviceInterface
0x14007de24  nop     dword ptr [rax+rax+00h]
0x14007de29  xor     esi, esi
0x14007de2b  cmp     eax, 40000000h
0x14007de30  cmovnz  esi, eax
0x14007de33  test    esi, esi
0x14007de35  jns     short loc_14007DE85
0x14007de37  mov     rcx, cs:WPP_GLOBAL_Control
0x14007de3e  cmp     rcx, r15
0x14007de41  jz      short loc_14007DE52
0x14007de43  test    dword ptr [rcx+2Ch], 20000h
0x14007de4a  jz      short loc_14007DE52
0x14007de4c  cmp     byte ptr [rcx+29h], 2
0x14007de50  jnb     short loc_14007DE54
0x14007de52  xor     bl, bl
0x14007de54  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14007de5b  setnz   r8b
0x14007de5f  test    bl, bl
0x14007de61  jnz     short loc_14007DE68
0x14007de63  test    r8b, r8b
0x14007de66  jz      short loc_14007DDFB
0x14007de68  mov     r9, [rcx+40h]
0x14007de6c  mov     rcx, [rcx+18h]
0x14007de70  mov     dword ptr [rsp+98h+var_58], esi
0x14007de74  mov     [rsp+98h+var_60], r13
0x14007de79  mov     [rsp+98h+var_68], 1Eh
0x14007de80  jmp     loc_14007DDE7
0x14007de85  mov     dl, bl; Enable
0x14007de87  mov     rcx, rbp; SymbolicLinkName
0x14007de8a  call    cs:__imp_IoSetDeviceInterfaceState
0x14007de91  nop     dword ptr [rax+rax+00h]
0x14007de96  mov     esi, eax
0x14007de98  test    eax, eax
0x14007de9a  jns     short loc_14007DEE8
0x14007de9c  mov     r10, cs:WPP_GLOBAL_Control
0x14007dea3  cmp     r10, r15
0x14007dea6  jz      short loc_14007DEB9
0x14007dea8  test    dword ptr [r10+2Ch], 20000h
0x14007deb0  jz      short loc_14007DEB9
0x14007deb2  cmp     byte ptr [r10+29h], 2
0x14007deb7  jnb     short loc_14007DEBB
0x14007deb9  xor     bl, bl
0x14007debb  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14007dec2  setnz   r8b
0x14007dec6  test    bl, bl
0x14007dec8  jnz     short loc_14007DED3
0x14007deca  test    r8b, r8b
0x14007decd  jz      loc_14007DDFB
0x14007ded3  mov     dword ptr [rsp+98h+var_58], esi
0x14007ded7  mov     [rsp+98h+var_60], r13
0x14007dedc  mov     [rsp+98h+var_68], 1Fh
0x14007dee3  jmp     loc_14007DDDF
0x14007dee8  nop
0x14007dee9  mov     [rdi+1F1h], bl
0x14007deef  mfence
0x14007def2  nop
0x14007def3  mov     [rdi+1F3h], bl
0x14007def9  mfence
0x14007defc  mov     rcx, rdi; this
0x14007deff  call    ?LogA2dpDeviceOwnership@A2dpSidebandAudioWdmDevice@@AEAAXXZ; A2dpSidebandAudioWdmDevice::LogA2dpDeviceOwnership(void)
0x14007df04  xor     eax, eax
0x14007df06  add     rsp, 58h
0x14007df0a  pop     r15
0x14007df0c  pop     r14
0x14007df0e  pop     r13
0x14007df10  pop     r12
0x14007df12  pop     rdi
0x14007df13  pop     rsi
0x14007df14  pop     rbp
0x14007df15  pop     rbx
0x14007df16  retn
```
