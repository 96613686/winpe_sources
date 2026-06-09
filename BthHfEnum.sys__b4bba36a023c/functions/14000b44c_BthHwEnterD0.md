# BthHwEnterD0

- ea: `0x14000b44c`
- end: `0x14000b577`
- name: `BthHwEnterD0`
- size: `299`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x140002ab0`
- `0x140003000`
- `0x1400030f0`

## callees

- `0x1400041d0`
- `0x14000b44c`
- `0x14001ae00`
- `0x14002ae68`

## import_xrefs

- `btampm!BtaMpmConnectionRequest` at `0x14000b541`
- `btampm!BtaMpmConnectionRequest` at `0x14000b541`

## pseudocode

```c
__int64 __fastcall BthHwEnterD0(__int64 a1)
{
  int v2; // edx
  int v3; // r8d
  _QWORD *v4; // rbx
  __int64 v5; // rcx

  if ( Bus_IsAutoConnectionDisabled() )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
    {
      LOBYTE(v2) = 0;
    }
    else
    {
      v2 = 1;
    }
    if ( (_BYTE)v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_(
        WPP_GLOBAL_Control->AttachedDevice,
        v2,
        v3,
        WPP_GLOBAL_Control->DeviceExtension,
        4,
        2,
        14,
        (__int64)WPP_a5a394aa8e7a34ed6d5d67bd4b27ab0e_Traceguids);
    }
  }
  else
  {
    v4 = (_QWORD *)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64 *))(WdfFunctions_01015 + 1616))(
                     WdfDriverGlobals,
                     a1,
                     off_1400220B0);
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, _QWORD))(WdfFunctions_01015 + 2504))(
      WdfDriverGlobals,
      v4[41],
      0);
    if ( v4[39] )
    {
      v5 = v4[23];
      if ( v5 )
        BtaMpmConnectionRequest(v5, 1, 1);
    }
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01015 + 2512))(WdfDriverGlobals, v4[41]);
  }
  return 0;
}

```

## disassembly

```asm
0x14000b44c  push    rbx
0x14000b44e  sub     rsp, 40h
0x14000b452  mov     rbx, rcx
0x14000b455  call    Bus_IsAutoConnectionDisabled
0x14000b45a  test    eax, eax
0x14000b45c  jz      short loc_14000B4D8
0x14000b45e  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b465  lea     rax, WPP_GLOBAL_Control
0x14000b46c  cmp     rcx, rax
0x14000b46f  jz      short loc_14000B485
0x14000b471  mov     eax, [rcx+2Ch]
0x14000b474  test    al, 2
0x14000b476  jz      short loc_14000B485
0x14000b478  cmp     byte ptr [rcx+29h], 4
0x14000b47c  jb      short loc_14000B485
0x14000b47e  mov     edx, 1
0x14000b483  jmp     short loc_14000B487
0x14000b485  xor     dl, dl
0x14000b487  lea     rax, WPP_RECORDER_INITIALIZED
0x14000b48e  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000b495  setnz   r8b
0x14000b499  test    dl, dl
0x14000b49b  jnz     short loc_14000B4A6
0x14000b49d  test    r8b, r8b
0x14000b4a0  jz      loc_14000B56E
0x14000b4a6  mov     r9, [rcx+40h]
0x14000b4aa  lea     rax, WPP_a5a394aa8e7a34ed6d5d67bd4b27ab0e_Traceguids
0x14000b4b1  mov     rcx, [rcx+18h]
0x14000b4b5  mov     [rsp+48h+var_10], rax
0x14000b4ba  mov     [rsp+48h+var_18], 0Eh
0x14000b4c1  mov     [rsp+48h+var_20], 2
0x14000b4c9  mov     [rsp+48h+var_28], 4
0x14000b4ce  call    WPP_RECORDER_AND_TRACE_SF_
0x14000b4d3  jmp     loc_14000B56E
0x14000b4d8  mov     rax, cs:WdfFunctions_01015
0x14000b4df  mov     rdx, rbx
0x14000b4e2  mov     r8, cs:off_1400220B0
0x14000b4e9  mov     rcx, cs:WdfDriverGlobals
0x14000b4f0  mov     rax, [rax+650h]
0x14000b4f7  call    _guard_dispatch_icall
0x14000b4fc  mov     rcx, cs:WdfFunctions_01015
0x14000b503  mov     rbx, rax
0x14000b506  xor     r8d, r8d
0x14000b509  mov     rax, [rcx+9C8h]
0x14000b510  mov     rcx, cs:WdfDriverGlobals
0x14000b517  mov     rdx, [rbx+148h]
0x14000b51e  call    _guard_dispatch_icall
0x14000b523  cmp     qword ptr [rbx+138h], 0
0x14000b52b  jz      short loc_14000B54D
0x14000b52d  mov     rcx, [rbx+0B8h]
0x14000b534  test    rcx, rcx
0x14000b537  jz      short loc_14000B54D
0x14000b539  mov     edx, 1
0x14000b53e  mov     r8d, edx
0x14000b541  call    cs:__imp_BtaMpmConnectionRequest
0x14000b548  nop     dword ptr [rax+rax+00h]
0x14000b54d  mov     rax, cs:WdfFunctions_01015
0x14000b554  mov     rdx, [rbx+148h]
0x14000b55b  mov     rcx, cs:WdfDriverGlobals
0x14000b562  mov     rax, [rax+9D0h]
0x14000b569  call    _guard_dispatch_icall
0x14000b56e  xor     eax, eax
0x14000b570  add     rsp, 40h
0x14000b574  pop     rbx
0x14000b575  retn
```
