# A2dpSidebandAudioWdmDevice::SetSidebandInterfaceState(bool)

- ea: `0x14007e060`
- end: `0x14007e2e8`
- name: `?SetSidebandInterfaceState@A2dpSidebandAudioWdmDevice@@AEAAX_N@Z`
- size: `648`
- prototype: `void __fastcall(A2dpSidebandAudioWdmDevice *__hidden this, bool)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x14007d420`
- `0x14007d440`

## callees

- `0x140006a88`
- `0x14000f6e4`
- `0x140010628`
- `0x14002d890`
- `0x14005a45c`
- `0x14007e060`

## import_xrefs

- `ntoskrnl!IoSetDeviceInterfaceState` at `0x14007e123`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x14007e24c`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x14007e123`
- `ntoskrnl!IoSetDeviceInterfaceState` at `0x14007e24c`

## pseudocode

```c
void __fastcall A2dpSidebandAudioWdmDevice::SetSidebandInterfaceState(
        A2dpSidebandAudioWdmDevice *this,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  char v4; // di
  int v6; // edx
  int v7; // r8d
  char v8; // si
  NTSTATUS v9; // eax
  int v10; // edx
  int v11; // r8d
  char v12; // r15
  char v13; // si
  NTSTATUS v14; // eax
  int v15; // edx
  int v16; // r8d

  v4 = a2;
  if ( !(unsigned int)Feature_55795972__private_IsEnabledDeviceUsageNoInline(this, a2, a3, a4) )
  {
    if ( v4 == *((_BYTE *)this + 499) )
      return;
    v8 = 1;
    LOBYTE(v6) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
    if ( (_BYTE)v6 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v7) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_Dq(
        WPP_GLOBAL_Control->AttachedDevice,
        v6,
        v7,
        WPP_GLOBAL_Control->DeviceExtension,
        4,
        19,
        12,
        (__int64)WPP_eb305fa737073720bb4070d66a1cdc5e_Traceguids,
        v4,
        this);
    }
    *((_BYTE *)this + 499) = v4;
    _mm_mfence();
    v9 = IoSetDeviceInterfaceState((PUNICODE_STRING)((char *)this + 472), v4);
    if ( v9 < 0 )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
      {
        v8 = 0;
      }
      if ( v8 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v10) = v8;
        LOBYTE(v11) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_dq(
          WPP_GLOBAL_Control->AttachedDevice,
          v10,
          v11,
          WPP_GLOBAL_Control->DeviceExtension,
          3,
          19,
          13,
          (__int64)WPP_eb305fa737073720bb4070d66a1cdc5e_Traceguids,
          v9,
          (char)this);
      }
    }
    goto LABEL_36;
  }
  v12 = *((_BYTE *)this + 499);
  *((_BYTE *)this + 499) = v4;
  v13 = 1;
  LOBYTE(v6) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  if ( (_BYTE)v6 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v7) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_llq(
      WPP_GLOBAL_Control->AttachedDevice,
      v6,
      v7,
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      19,
      10,
      (__int64)WPP_eb305fa737073720bb4070d66a1cdc5e_Traceguids,
      v12,
      v4,
      (char)this);
  }
  if ( v12 != v4 )
  {
    v14 = IoSetDeviceInterfaceState((PUNICODE_STRING)((char *)this + 472), v4);
    if ( v14 < 0 )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        v13 = 0;
      }
      if ( v13 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v15) = v13;
        LOBYTE(v16) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_llq(
          WPP_GLOBAL_Control->AttachedDevice,
          v15,
          v16,
          WPP_GLOBAL_Control->DeviceExtension,
          2,
          19,
          11,
          (__int64)WPP_eb305fa737073720bb4070d66a1cdc5e_Traceguids,
          v4,
          v14,
          (char)this);
      }
    }
LABEL_36:
    SidebandAudioWdmDevice::SetSidebandInterfaceState(this, v4);
  }
}

```

## disassembly

```asm
0x14007e060  push    rbx
0x14007e062  push    rsi
0x14007e063  push    rdi
0x14007e064  push    r12
0x14007e066  push    r14
0x14007e068  push    r15
0x14007e06a  sub     rsp, 68h
0x14007e06e  movzx   edi, dl
0x14007e071  mov     rbx, rcx
0x14007e074  call    Feature_55795972__private_IsEnabledDeviceUsageNoInline
0x14007e079  test    eax, eax
0x14007e07b  jnz     loc_14007E1A7
0x14007e081  mov     al, [rbx+1F3h]
0x14007e087  nop
0x14007e088  cmp     dil, al
0x14007e08b  jz      loc_14007E2D9
0x14007e091  mov     rcx, cs:WPP_GLOBAL_Control
0x14007e098  lea     r14, WPP_GLOBAL_Control
0x14007e09f  mov     sil, 1
0x14007e0a2  cmp     rcx, r14
0x14007e0a5  jz      short loc_14007E0BB
0x14007e0a7  test    dword ptr [rcx+2Ch], 40000h
0x14007e0ae  jz      short loc_14007E0BB
0x14007e0b0  cmp     byte ptr [rcx+29h], 4
0x14007e0b4  jb      short loc_14007E0BB
0x14007e0b6  mov     dl, sil
0x14007e0b9  jmp     short loc_14007E0BD
0x14007e0bb  xor     dl, dl
0x14007e0bd  lea     r12, WPP_RECORDER_INITIALIZED
0x14007e0c4  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14007e0cb  lea     r15, WPP_eb305fa737073720bb4070d66a1cdc5e_Traceguids
0x14007e0d2  setnz   r8b
0x14007e0d6  test    dl, dl
0x14007e0d8  jnz     short loc_14007E0DF
0x14007e0da  test    r8b, r8b
0x14007e0dd  jz      short loc_14007E10E
0x14007e0df  mov     r9, [rcx+40h]
0x14007e0e3  mov     rcx, [rcx+18h]
0x14007e0e7  mov     [rsp+98h+var_50], rbx
0x14007e0ec  mov     [rsp+98h+var_58], edi
0x14007e0f0  mov     [rsp+98h+var_60], r15
0x14007e0f5  mov     [rsp+98h+var_68], 0Ch
0x14007e0fc  mov     [rsp+98h+var_70], 13h
0x14007e104  mov     [rsp+98h+var_78], 4
0x14007e109  call    WPP_RECORDER_AND_TRACE_SF_Dq
0x14007e10e  nop
0x14007e10f  mov     [rbx+1F3h], dil
0x14007e116  mfence
0x14007e119  lea     rcx, [rbx+1D8h]; SymbolicLinkName
0x14007e120  mov     dl, dil; Enable
0x14007e123  call    cs:__imp_IoSetDeviceInterfaceState
0x14007e12a  nop     dword ptr [rax+rax+00h]
0x14007e12f  test    eax, eax
0x14007e131  jns     loc_14007E2CE
0x14007e137  mov     r10, cs:WPP_GLOBAL_Control
0x14007e13e  cmp     r10, r14
0x14007e141  jz      short loc_14007E154
0x14007e143  test    dword ptr [r10+2Ch], 40000h
0x14007e14b  jz      short loc_14007E154
0x14007e14d  cmp     byte ptr [r10+29h], 3
0x14007e152  jnb     short loc_14007E157
0x14007e154  xor     sil, sil
0x14007e157  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14007e15e  setnz   r8b
0x14007e162  test    sil, sil
0x14007e165  jnz     short loc_14007E170
0x14007e167  test    r8b, r8b
0x14007e16a  jz      loc_14007E2CE
0x14007e170  mov     r9, [r10+40h]
0x14007e174  mov     dl, sil
0x14007e177  mov     rcx, [r10+18h]
0x14007e17b  mov     [rsp+98h+var_50], rbx
0x14007e180  mov     [rsp+98h+var_58], eax
0x14007e184  mov     [rsp+98h+var_60], r15
0x14007e189  mov     [rsp+98h+var_68], 0Dh
0x14007e190  mov     [rsp+98h+var_70], 13h
0x14007e198  mov     [rsp+98h+var_78], 3
0x14007e19d  call    WPP_RECORDER_AND_TRACE_SF_dq
0x14007e1a2  jmp     loc_14007E2CE
0x14007e1a7  nop
0x14007e1a8  mov     r15b, dil
0x14007e1ab  xchg    r15b, [rbx+1F3h]
0x14007e1b2  nop
0x14007e1b3  mov     rcx, cs:WPP_GLOBAL_Control
0x14007e1ba  lea     r14, WPP_GLOBAL_Control
0x14007e1c1  mov     sil, 1
0x14007e1c4  cmp     rcx, r14
0x14007e1c7  jz      short loc_14007E1DD
0x14007e1c9  test    dword ptr [rcx+2Ch], 40000h
0x14007e1d0  jz      short loc_14007E1DD
0x14007e1d2  cmp     byte ptr [rcx+29h], 4
0x14007e1d6  jb      short loc_14007E1DD
0x14007e1d8  mov     dl, sil
0x14007e1db  jmp     short loc_14007E1DF
0x14007e1dd  xor     dl, dl
0x14007e1df  lea     r12, WPP_RECORDER_INITIALIZED
0x14007e1e6  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14007e1ed  lea     r10, WPP_eb305fa737073720bb4070d66a1cdc5e_Traceguids
0x14007e1f4  setnz   r8b
0x14007e1f8  test    dl, dl
0x14007e1fa  jnz     short loc_14007E201
0x14007e1fc  test    r8b, r8b
0x14007e1ff  jz      short loc_14007E239
0x14007e201  mov     [rsp+98h+var_48], rbx
0x14007e206  mov     dword ptr [rsp+98h+var_50], edi
0x14007e20a  movzx   r9d, r15b
0x14007e20e  mov     [rsp+98h+var_58], r9d
0x14007e213  mov     r9, [rcx+40h]
0x14007e217  mov     rcx, [rcx+18h]
0x14007e21b  mov     [rsp+98h+var_60], r10
0x14007e220  mov     [rsp+98h+var_68], 0Ah
0x14007e227  mov     [rsp+98h+var_70], 13h
0x14007e22f  mov     [rsp+98h+var_78], 4
0x14007e234  call    WPP_RECORDER_AND_TRACE_SF_llq
0x14007e239  cmp     r15b, dil
0x14007e23c  jz      loc_14007E2D9
0x14007e242  lea     rcx, [rbx+1D8h]; SymbolicLinkName
0x14007e249  mov     dl, dil; Enable
0x14007e24c  call    cs:__imp_IoSetDeviceInterfaceState
0x14007e253  nop     dword ptr [rax+rax+00h]
0x14007e258  test    eax, eax
0x14007e25a  jns     short loc_14007E2CE
0x14007e25c  mov     r10, cs:WPP_GLOBAL_Control
0x14007e263  cmp     r10, r14
0x14007e266  jz      short loc_14007E279
0x14007e268  test    dword ptr [r10+2Ch], 40000h
0x14007e270  jz      short loc_14007E279
0x14007e272  cmp     byte ptr [r10+29h], 2
0x14007e277  jnb     short loc_14007E27C
0x14007e279  xor     sil, sil
0x14007e27c  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14007e283  setnz   r8b
0x14007e287  test    sil, sil
0x14007e28a  jnz     short loc_14007E291
0x14007e28c  test    r8b, r8b
0x14007e28f  jz      short loc_14007E2CE
0x14007e291  mov     r9, [r10+40h]
0x14007e295  mov     dl, sil
0x14007e298  mov     rcx, [r10+18h]
0x14007e29c  mov     [rsp+98h+var_48], rbx
0x14007e2a1  mov     dword ptr [rsp+98h+var_50], eax
0x14007e2a5  lea     rax, WPP_eb305fa737073720bb4070d66a1cdc5e_Traceguids
0x14007e2ac  mov     [rsp+98h+var_58], edi
0x14007e2b0  mov     [rsp+98h+var_60], rax
0x14007e2b5  mov     [rsp+98h+var_68], 0Bh
0x14007e2bc  mov     [rsp+98h+var_70], 13h
0x14007e2c4  mov     [rsp+98h+var_78], 2
0x14007e2c9  call    WPP_RECORDER_AND_TRACE_SF_llq
0x14007e2ce  mov     dl, dil; bool
0x14007e2d1  mov     rcx, rbx; this
0x14007e2d4  call    ?SetSidebandInterfaceState@SidebandAudioWdmDevice@@QEAAX_N@Z; SidebandAudioWdmDevice::SetSidebandInterfaceState(bool)
0x14007e2d9  add     rsp, 68h
0x14007e2dd  pop     r15
0x14007e2df  pop     r14
0x14007e2e1  pop     r12
0x14007e2e3  pop     rdi
0x14007e2e4  pop     rsi
0x14007e2e5  pop     rbx
0x14007e2e6  retn
```
