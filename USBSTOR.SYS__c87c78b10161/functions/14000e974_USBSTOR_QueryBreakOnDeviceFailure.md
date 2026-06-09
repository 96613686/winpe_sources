# USBSTOR_QueryBreakOnDeviceFailure

- ea: `0x14000e974`
- end: `0x14000ea8c`
- name: `USBSTOR_QueryBreakOnDeviceFailure`
- size: `280`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14002890c`

## callees

- `0x14000e974`
- `0x140010664`
- `0x140013990`
- `0x140013d40`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14000ea0b`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000ea0b`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000ea1c`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14000ea1c`
- `ntoskrnl!RtlQueryRegistryValues` at `0x14000ea40`

## string_xrefs

- `0x14000e9d6`: `RtlQueryRegistryValuesEx`

## pseudocode

```c
__int64 USBSTOR_QueryBreakOnDeviceFailure()
{
  __int64 (__fastcall *SystemRoutineAddress)(__int64, const wchar_t *, _QWORD *); // rax
  __int64 result; // rax
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-88h] BYREF
  _QWORD v3[15]; // [rsp+40h] [rbp-78h] BYREF

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_aacf58c1c3d036691363e31f780ca4b7_Traceguids);
  }
  memset(v3, 0, 0x70u);
  LODWORD(v3[1]) = 32;
  v3[2] = L"BreakOnUnexpectedDeviceFailure";
  LODWORD(v3[4]) = 4;
  v3[3] = &USBSTOR_DriverGlobals;
  v3[5] = &USBSTOR_DriverGlobals;
  LODWORD(v3[6]) = 4;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"RtlQueryRegistryValuesEx");
  SystemRoutineAddress = (__int64 (__fastcall *)(__int64, const wchar_t *, _QWORD *))MmGetSystemRoutineAddress(&DestinationString);
  if ( !SystemRoutineAddress )
    SystemRoutineAddress = (__int64 (__fastcall *)(__int64, const wchar_t *, _QWORD *))RtlQueryRegistryValues;
  result = SystemRoutineAddress(2, L"USBSTOR", v3);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    result = HIDWORD(WPP_GLOBAL_Control->Timer);
    if ( (result & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      return WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_aacf58c1c3d036691363e31f780ca4b7_Traceguids);
  }
  return result;
}

```

## disassembly

```asm
0x14000e974  push    rdi
0x14000e976  sub     rsp, 0B0h
0x14000e97d  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e984  lea     rdi, WPP_GLOBAL_Control
0x14000e98b  cmp     rcx, rdi
0x14000e98e  jz      short loc_14000E9B2
0x14000e990  mov     eax, [rcx+2Ch]
0x14000e993  test    al, 1
0x14000e995  jz      short loc_14000E9B2
0x14000e997  cmp     byte ptr [rcx+29h], 4
0x14000e99b  jb      short loc_14000E9B2
0x14000e99d  mov     rcx, [rcx+18h]
0x14000e9a1  lea     r8, WPP_aacf58c1c3d036691363e31f780ca4b7_Traceguids
0x14000e9a8  mov     edx, 0Ch
0x14000e9ad  call    WPP_SF_
0x14000e9b2  xor     edx, edx; Val
0x14000e9b4  lea     rcx, [rsp+0B8h+var_78]; void *
0x14000e9b9  lea     r8d, [rdx+70h]; Size
0x14000e9bd  call    memset
0x14000e9c2  lea     rax, aBreakonunexpec; "BreakOnUnexpectedDeviceFailure"
0x14000e9c9  mov     [rsp+0B8h+var_70], 20h ; ' '
0x14000e9d1  mov     [rsp+0B8h+var_68], rax
0x14000e9d6  lea     rdx, aRtlqueryregist; "RtlQueryRegistryValuesEx"
0x14000e9dd  lea     rax, USBSTOR_DriverGlobals
0x14000e9e4  mov     [rsp+0B8h+var_58], 4
0x14000e9ec  xorps   xmm0, xmm0
0x14000e9ef  mov     [rsp+0B8h+var_60], rax
0x14000e9f4  lea     rcx, [rsp+0B8h+DestinationString]; DestinationString
0x14000e9f9  mov     [rsp+0B8h+var_50], rax
0x14000e9fe  mov     [rsp+0B8h+var_48], 4
0x14000ea06  movups  xmmword ptr [rsp+0B8h+DestinationString.Length], xmm0
0x14000ea0b  call    cs:__imp_RtlInitUnicodeString
0x14000ea12  nop     dword ptr [rax+rax+00h]
0x14000ea17  lea     rcx, [rsp+0B8h+DestinationString]; SystemRoutineName
0x14000ea1c  call    cs:__imp_MmGetSystemRoutineAddress
0x14000ea23  nop     dword ptr [rax+rax+00h]
0x14000ea28  lea     r8, [rsp+0B8h+var_78]
0x14000ea2d  mov     [rsp+0B8h+var_98], 0
0x14000ea36  test    rax, rax
0x14000ea39  lea     rdx, aUsbstor; "USBSTOR"
0x14000ea40  cmovz   rax, cs:__imp_RtlQueryRegistryValues
0x14000ea48  xor     r9d, r9d
0x14000ea4b  lea     ecx, [r9+2]
0x14000ea4f  call    _guard_dispatch_icall
0x14000ea54  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ea5b  cmp     rcx, rdi
0x14000ea5e  jz      short loc_14000EA82
0x14000ea60  mov     eax, [rcx+2Ch]
0x14000ea63  test    al, 1
0x14000ea65  jz      short loc_14000EA82
0x14000ea67  cmp     byte ptr [rcx+29h], 4
0x14000ea6b  jb      short loc_14000EA82
0x14000ea6d  mov     rcx, [rcx+18h]
0x14000ea71  lea     r8, WPP_aacf58c1c3d036691363e31f780ca4b7_Traceguids
0x14000ea78  mov     edx, 0Dh
0x14000ea7d  call    WPP_SF_
0x14000ea82  add     rsp, 0B0h
0x14000ea89  pop     rdi
0x14000ea8a  retn
```
