# InitializeDeviceFriendlyName(WDFDEVICE__ *)

- ea: `0x140028b28`
- end: `0x140028cf3`
- name: `?InitializeDeviceFriendlyName@@YAXPEAUWDFDEVICE__@@@Z`
- size: `459`
- prototype: `void __fastcall(struct WDFDEVICE__ *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140002630`

## callees

- `0x140004810`
- `0x14001ae00`
- `0x140028b28`

## import_xrefs

- `ntoskrnl!IoSetDevicePropertyData` at `0x140028c49`
- `ntoskrnl!IoSetDevicePropertyData` at `0x140028c49`
- `ntoskrnl!ExFreePoolWithTag` at `0x140028cd6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140028cd6`
- `btampm!BtaMpmBuildIndirectStringFromMessageWithSingleUTF8Arg` at `0x140028be6`
- `btampm!BtaMpmBuildIndirectStringFromMessageWithSingleUTF8Arg` at `0x140028be6`

## string_xrefs

- `0x140028bc7`: `@System32\drivers\bthhfenum.sys`

## pseudocode

```c
void __fastcall InitializeDeviceFriendlyName(struct WDFDEVICE__ *a1)
{
  __int64 v2; // rax
  __int64 v3; // rdi
  bool v4; // cf
  unsigned int v5; // ebx
  __int64 v6; // rax
  ULONG v7; // ebx
  PVOID Data; // rdi
  struct _DEVICE_OBJECT *v9; // rax
  char v10; // bl
  NTSTATUS v11; // eax
  int v12; // edx
  int v13; // r8d
  ULONG Size; // [rsp+28h] [rbp-30h]
  PVOID P; // [rsp+68h] [rbp+10h] BYREF
  __int64 v16; // [rsp+70h] [rbp+18h] BYREF

  v2 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, struct WDFDEVICE__ *, __int64 *))(WdfFunctions_01015 + 1616))(
         WdfDriverGlobals,
         a1,
         off_1400220B0);
  v3 = v2;
  if ( (*(_DWORD *)(v2 + 424) & 4) != 0 )
  {
    v4 = *(_DWORD *)(v2 + 416) != 0;
    P = 0;
    v16 = 0;
    v5 = v4 ? 0xFFFFFFFE : 0;
    v6 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, WDFDRIVER))(WdfFunctions_01015 + 944))(
           WdfDriverGlobals,
           WdfDriverGlobals->Driver);
    if ( (int)BtaMpmBuildIndirectStringFromMessageWithSingleUTF8Arg(
                *(_QWORD *)(v6 + 24),
                v5 + 3,
                L"@System32\\drivers\\bthhfenum.sys",
                v3 + 444,
                248,
                1179145282,
                &P,
                &v16) >= 0 )
    {
      v7 = v16 + 2;
      Data = P;
      v9 = (struct _DEVICE_OBJECT *)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, struct WDFDEVICE__ *))(WdfFunctions_01015 + 264))(
                                      WdfDriverGlobals,
                                      a1);
      Size = v7;
      v10 = 1;
      v11 = IoSetDevicePropertyData(v9, &DEVPKEY_Device_FriendlyName, 0, 1u, 0x19u, Size, Data);
      if ( v11 < 0 )
      {
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          v10 = 0;
        }
        if ( v10 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v12) = v10;
          LOBYTE(v13) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          WPP_RECORDER_AND_TRACE_SF_IOCTL_BTHHFP(
            WPP_GLOBAL_Control->AttachedDevice,
            v12,
            v13,
            WPP_GLOBAL_Control->DeviceExtension,
            2,
            4,
            18,
            (__int64)WPP_9739fd3d85a33a980818697074cd9c28_Traceguids,
            v11);
        }
      }
      ExFreePoolWithTag(P, 0x46485442u);
    }
  }
}

```

## disassembly

```asm
0x140028b28  mov     [rsp+arg_0], rbx
0x140028b2d  mov     [rsp+arg_18], rsi
0x140028b32  push    rdi
0x140028b33  sub     rsp, 50h
0x140028b37  mov     rax, cs:WdfFunctions_01015
0x140028b3e  mov     rsi, rcx
0x140028b41  mov     r8, cs:off_1400220B0
0x140028b48  mov     rdx, rcx
0x140028b4b  mov     rcx, cs:WdfDriverGlobals
0x140028b52  mov     rax, [rax+650h]
0x140028b59  call    _guard_dispatch_icall
0x140028b5e  mov     rdi, rax
0x140028b61  mov     edx, [rax+1A8h]
0x140028b67  test    dl, 4
0x140028b6a  jz      loc_140028CE2
0x140028b70  mov     ecx, [rax+1A0h]
0x140028b76  mov     rax, cs:WdfFunctions_01015
0x140028b7d  neg     ecx
0x140028b7f  mov     rcx, cs:WdfDriverGlobals
0x140028b86  mov     [rsp+58h+P], 0
0x140028b8f  sbb     ebx, ebx
0x140028b91  mov     [rsp+58h+arg_10], 0
0x140028b9a  and     ebx, 0FFFFFFFEh
0x140028b9d  mov     rax, [rax+3B0h]
0x140028ba4  mov     rdx, [rcx]
0x140028ba7  call    _guard_dispatch_icall
0x140028bac  lea     rcx, [rsp+58h+arg_10]
0x140028bb1  mov     [rsp+58h+var_20], rcx
0x140028bb6  lea     r9, [rdi+1BCh]
0x140028bbd  lea     rcx, [rsp+58h+P]
0x140028bc2  mov     [rsp+58h+Data], rcx
0x140028bc7  lea     r8, aSystem32Driver; "@System32\\drivers\\bthhfenum.sys"
0x140028bce  mov     rcx, [rax+18h]
0x140028bd2  lea     edx, [rbx+3]
0x140028bd5  mov     [rsp+58h+Size], 46485442h
0x140028bdd  mov     qword ptr [rsp+58h+Type], 0F8h
0x140028be6  call    cs:__imp_BtaMpmBuildIndirectStringFromMessageWithSingleUTF8Arg
0x140028bed  nop     dword ptr [rax+rax+00h]
0x140028bf2  test    eax, eax
0x140028bf4  js      loc_140028CE2
0x140028bfa  mov     rax, cs:WdfFunctions_01015
0x140028c01  mov     rdx, rsi
0x140028c04  mov     ebx, dword ptr [rsp+58h+arg_10]
0x140028c08  mov     rcx, cs:WdfDriverGlobals
0x140028c0f  add     ebx, 2
0x140028c12  mov     rdi, [rsp+58h+P]
0x140028c17  mov     rax, [rax+108h]
0x140028c1e  call    _guard_dispatch_icall
0x140028c23  mov     [rsp+58h+Data], rdi; Data
0x140028c28  lea     rdx, DEVPKEY_Device_FriendlyName; PropertyKey
0x140028c2f  mov     [rsp+58h+Size], ebx; Size
0x140028c33  xor     r8d, r8d; Lcid
0x140028c36  mov     ebx, 1
0x140028c3b  mov     [rsp+58h+Type], 19h; Type
0x140028c43  mov     r9d, ebx; Flags
0x140028c46  mov     rcx, rax; Pdo
0x140028c49  call    cs:__imp_IoSetDevicePropertyData
0x140028c50  nop     dword ptr [rax+rax+00h]
0x140028c55  test    eax, eax
0x140028c57  jns     short loc_140028CCC
0x140028c59  mov     r10, cs:WPP_GLOBAL_Control
0x140028c60  lea     rcx, WPP_GLOBAL_Control
0x140028c67  cmp     r10, rcx
0x140028c6a  jz      short loc_140028C7C
0x140028c6c  mov     ecx, [r10+2Ch]
0x140028c70  test    cl, 8
0x140028c73  jz      short loc_140028C7C
0x140028c75  cmp     byte ptr [r10+29h], 2
0x140028c7a  jnb     short loc_140028C7E
0x140028c7c  xor     bl, bl
0x140028c7e  lea     rcx, WPP_RECORDER_INITIALIZED
0x140028c85  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140028c8c  setnz   r8b
0x140028c90  test    bl, bl
0x140028c92  jnz     short loc_140028C99
0x140028c94  test    r8b, r8b
0x140028c97  jz      short loc_140028CCC
0x140028c99  mov     r9, [r10+40h]
0x140028c9d  mov     dl, bl
0x140028c9f  mov     rcx, [r10+18h]
0x140028ca3  mov     [rsp+58h+var_18], eax
0x140028ca7  lea     rax, WPP_9739fd3d85a33a980818697074cd9c28_Traceguids
0x140028cae  mov     [rsp+58h+var_20], rax
0x140028cb3  mov     word ptr [rsp+58h+Data], 12h
0x140028cba  mov     [rsp+58h+Size], 4
0x140028cc2  mov     byte ptr [rsp+58h+Type], 2
0x140028cc7  call    WPP_RECORDER_AND_TRACE_SF_IOCTL_BTHHFP
0x140028ccc  mov     rcx, [rsp+58h+P]; P
0x140028cd1  mov     edx, 46485442h; Tag
0x140028cd6  call    cs:__imp_ExFreePoolWithTag
0x140028cdd  nop     dword ptr [rax+rax+00h]
0x140028ce2  mov     rbx, [rsp+58h+arg_0]
0x140028ce7  mov     rsi, [rsp+58h+arg_18]
0x140028cec  add     rsp, 50h
0x140028cf0  pop     rdi
0x140028cf1  retn
```
