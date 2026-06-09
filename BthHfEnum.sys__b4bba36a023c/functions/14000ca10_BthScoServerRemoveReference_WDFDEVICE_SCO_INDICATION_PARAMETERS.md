# BthScoServerRemoveReference(WDFDEVICE__ *,_SCO_INDICATION_PARAMETERS *)

- ea: `0x14000ca10`
- end: `0x14000cafd`
- name: `?BthScoServerRemoveReference@@YAXPEAUWDFDEVICE__@@PEAU_SCO_INDICATION_PARAMETERS@@@Z`
- size: `237`
- prototype: `void __fastcall(struct WDFDEVICE__ *, struct _SCO_INDICATION_PARAMETERS *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140011b70`

## callees

- `0x1400041d0`
- `0x14000ca10`
- `0x14001ae00`

## pseudocode

```c
void __fastcall BthScoServerRemoveReference(struct WDFDEVICE__ *a1, struct _SCO_INDICATION_PARAMETERS *a2)
{
  int v3; // edx
  __int64 v4; // rbx
  int v5; // r8d

  v4 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, struct WDFDEVICE__ *, __int64 *))(WdfFunctions_01015 + 1616))(
         WdfDriverGlobals,
         a1,
         off_1400220B0);
  LOBYTE(v3) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  if ( (_BYTE)v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v5) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_(
      WPP_GLOBAL_Control->AttachedDevice,
      v3,
      v5,
      WPP_GLOBAL_Control->DeviceExtension,
      4,
      5,
      128,
      (__int64)WPP_351f2ada31f4311c39bc4c7cedb75b25_Traceguids);
  }
  _InterlockedDecrement((volatile signed __int32 *)(v4 + 168));
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, struct WDFDEVICE__ *, __int64, __int64, const char *))(WdfFunctions_01015 + 1648))(
    WdfDriverGlobals,
    a1,
    1179145282,
    3704,
    "onecoreuap\\drivers\\wdm\\audio\\drivers\\bluetooth\\bthhfenum\\bthscoserver.cpp");
}

```

## disassembly

```asm
0x14000ca10  mov     [rsp+arg_0], rbx
0x14000ca15  push    rdi
0x14000ca16  sub     rsp, 40h
0x14000ca1a  mov     rax, cs:WdfFunctions_01015
0x14000ca21  mov     rdi, rcx
0x14000ca24  mov     r8, cs:off_1400220B0
0x14000ca2b  mov     rdx, rcx
0x14000ca2e  mov     rcx, cs:WdfDriverGlobals
0x14000ca35  mov     rax, [rax+650h]
0x14000ca3c  call    _guard_dispatch_icall
0x14000ca41  mov     rbx, rax
0x14000ca44  mov     r10, cs:WPP_GLOBAL_Control
0x14000ca4b  lea     rax, WPP_GLOBAL_Control
0x14000ca52  cmp     r10, rax
0x14000ca55  jz      short loc_14000CA6B
0x14000ca57  mov     ecx, [r10+2Ch]
0x14000ca5b  test    cl, 10h
0x14000ca5e  jz      short loc_14000CA6B
0x14000ca60  cmp     byte ptr [r10+29h], 4
0x14000ca65  jb      short loc_14000CA6B
0x14000ca67  mov     dl, 1
0x14000ca69  jmp     short loc_14000CA6D
0x14000ca6b  xor     dl, dl
0x14000ca6d  lea     rax, WPP_RECORDER_INITIALIZED
0x14000ca74  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000ca7b  setnz   r8b
0x14000ca7f  test    dl, dl
0x14000ca81  jnz     short loc_14000CA88
0x14000ca83  test    r8b, r8b
0x14000ca86  jz      short loc_14000CAB5
0x14000ca88  mov     r9, [r10+40h]
0x14000ca8c  lea     rax, WPP_351f2ada31f4311c39bc4c7cedb75b25_Traceguids
0x14000ca93  mov     rcx, [r10+18h]
0x14000ca97  mov     [rsp+48h+var_10], rax
0x14000ca9c  mov     [rsp+48h+var_18], 80h
0x14000caa3  mov     [rsp+48h+var_20], 5
0x14000caab  mov     byte ptr [rsp+48h+var_28], 4
0x14000cab0  call    WPP_RECORDER_AND_TRACE_SF_
0x14000cab5  lock dec dword ptr [rbx+0A8h]
0x14000cabc  lea     rcx, aOnecoreuapDriv; "onecoreuap\\drivers\\wdm\\audio\\driver"...
0x14000cac3  mov     rax, cs:WdfFunctions_01015
0x14000caca  mov     r9d, 0E78h
0x14000cad0  mov     [rsp+48h+var_28], rcx
0x14000cad5  mov     r8d, 46485442h
0x14000cadb  mov     rcx, cs:WdfDriverGlobals
0x14000cae2  mov     rdx, rdi
0x14000cae5  mov     rax, [rax+670h]
0x14000caec  call    _guard_dispatch_icall
0x14000caf1  mov     rbx, [rsp+48h+arg_0]
0x14000caf6  add     rsp, 40h
0x14000cafa  pop     rdi
0x14000cafb  retn
```
