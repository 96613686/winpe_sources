# BthEnumUpdateProfileConnectionCountKey

- ea: `0x14001dcec`
- end: `0x14001de0b`
- name: `BthEnumUpdateProfileConnectionCountKey`
- size: `287`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x140019058`
- `0x14001a868`

## callees

- `0x1400013e8`
- `0x14000295c`
- `0x14001dcec`

## import_xrefs

- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x14001dd23`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x14001dd23`
- `ntoskrnl!ZwSetValueKey` at `0x14001ddb3`
- `ntoskrnl!ZwSetValueKey` at `0x14001ddb3`
- `ntoskrnl!ZwClose` at `0x14001ddc5`
- `ntoskrnl!ZwClose` at `0x14001ddc5`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001dd7f`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001dd7f`

## pseudocode

```c
__int64 __fastcall BthEnumUpdateProfileConnectionCountKey(__int64 a1)
{
  struct _DEVICE_OBJECT *v2; // rcx
  NTSTATUS v3; // eax
  int v4; // edx
  char v6; // bl
  int v7; // edx
  int v8; // r8d
  int v9; // r9d
  int Data; // [rsp+20h] [rbp-30h]
  ULONG DataSize; // [rsp+28h] [rbp-28h]
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-10h] BYREF
  unsigned int v13; // [rsp+60h] [rbp+10h] BYREF
  void *DeviceRegKey; // [rsp+68h] [rbp+18h] BYREF

  DeviceRegKey = 0;
  v13 = 0;
  v2 = *(struct _DEVICE_OBJECT **)(a1 + 16);
  DestinationString = 0;
  v3 = IoOpenDeviceRegistryKey(v2, 1u, 3u, &DeviceRegKey);
  if ( v3 >= 0 )
  {
    RtlInitUnicodeString(&DestinationString, L"ConnectionCount");
    v13 = *(_DWORD *)(a1 + 2924);
    v6 = ZwSetValueKey(DeviceRegKey, &DestinationString, 0, 4u, &v13, 4u);
    ZwClose(DeviceRegKey);
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_dd(WPP_GLOBAL_Control->DeviceExtension, v7, v8, v9, Data, v13, v6);
    return v13;
  }
  else
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      DataSize = v3;
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        v4,
        3,
        13,
        (__int64)WPP_f24dc5fc8d98372b7b5478949da3430c_Traceguids,
        DataSize);
    }
    return 0;
  }
}

```

## disassembly

```asm
0x14001dcec  mov     [rsp-8+arg_10], rbx
0x14001dcf1  push    rbp
0x14001dcf2  mov     rbp, rsp
0x14001dcf5  sub     rsp, 50h
0x14001dcf9  mov     edx, 1; DevInstKeyType
0x14001dcfe  mov     [rbp+DeviceRegKey], 0
0x14001dd06  mov     rbx, rcx
0x14001dd09  mov     [rbp+arg_0], 0
0x14001dd10  mov     rcx, [rcx+10h]; DeviceObject
0x14001dd14  lea     r9, [rbp+DeviceRegKey]; DeviceRegKey
0x14001dd18  xorps   xmm0, xmm0
0x14001dd1b  lea     r8d, [rdx+2]; DesiredAccess
0x14001dd1f  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14001dd23  call    cs:__imp_IoOpenDeviceRegistryKey
0x14001dd2a  nop     dword ptr [rax+rax+00h]
0x14001dd2f  test    eax, eax
0x14001dd31  jns     short loc_14001DD74
0x14001dd33  lea     rcx, WPP_RECORDER_INITIALIZED
0x14001dd3a  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14001dd41  jz      short loc_14001DD6D
0x14001dd43  mov     rcx, cs:WPP_GLOBAL_Control
0x14001dd4a  mov     r9d, 0Dh
0x14001dd50  mov     [rsp+50h+DataSize], eax
0x14001dd54  lea     rax, WPP_f24dc5fc8d98372b7b5478949da3430c_Traceguids
0x14001dd5b  mov     [rsp+50h+Data], rax
0x14001dd60  mov     rcx, [rcx+40h]
0x14001dd64  lea     r8d, [r9-0Ah]
0x14001dd68  call    WPP_RECORDER_SF_d
0x14001dd6d  xor     eax, eax
0x14001dd6f  jmp     loc_14001DDFF
0x14001dd74  lea     rdx, aConnectioncoun; "ConnectionCount"
0x14001dd7b  lea     rcx, [rbp+DestinationString]; DestinationString
0x14001dd7f  call    cs:__imp_RtlInitUnicodeString
0x14001dd86  nop     dword ptr [rax+rax+00h]
0x14001dd8b  mov     eax, [rbx+0B6Ch]
0x14001dd91  lea     rdx, [rbp+DestinationString]; ValueName
0x14001dd95  mov     rcx, [rbp+DeviceRegKey]; KeyHandle
0x14001dd99  mov     r9d, 4; Type
0x14001dd9f  mov     [rbp+arg_0], eax
0x14001dda2  xor     r8d, r8d; TitleIndex
0x14001dda5  lea     rax, [rbp+arg_0]
0x14001dda9  mov     [rsp+50h+DataSize], r9d; DataSize
0x14001ddae  mov     [rsp+50h+Data], rax; Data
0x14001ddb3  call    cs:__imp_ZwSetValueKey
0x14001ddba  nop     dword ptr [rax+rax+00h]
0x14001ddbf  mov     rcx, [rbp+DeviceRegKey]; Handle
0x14001ddc3  mov     ebx, eax
0x14001ddc5  call    cs:__imp_ZwClose
0x14001ddcc  nop     dword ptr [rax+rax+00h]
0x14001ddd1  lea     rcx, WPP_RECORDER_INITIALIZED
0x14001ddd8  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14001dddf  jz      short loc_14001DDFC
0x14001dde1  mov     rcx, cs:WPP_GLOBAL_Control
0x14001dde8  mov     eax, [rbp+arg_0]
0x14001ddeb  mov     [rsp+50h+var_20], ebx
0x14001ddef  mov     [rsp+50h+DataSize], eax
0x14001ddf3  mov     rcx, [rcx+40h]
0x14001ddf7  call    WPP_RECORDER_SF_dd
0x14001ddfc  mov     eax, [rbp+arg_0]
0x14001ddff  mov     rbx, [rsp+50h+arg_10]
0x14001de04  add     rsp, 50h
0x14001de08  pop     rbp
0x14001de09  retn
```
