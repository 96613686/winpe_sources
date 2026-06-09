# BthEnumGetConnectionCountKey

- ea: `0x14001dba4`
- end: `0x14001dce6`
- name: `BthEnumGetConnectionCountKey`
- size: `322`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x140019058`

## callees

- `0x1400013e8`
- `0x140007d00`
- `0x14001dba4`

## import_xrefs

- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x14001dbdd`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x14001dbdd`
- `ntoskrnl!ZwClose` at `0x14001dc83`
- `ntoskrnl!ZwClose` at `0x14001dc83`
- `ntoskrnl!ZwQueryValueKey` at `0x14001dc66`
- `ntoskrnl!ZwQueryValueKey` at `0x14001dc66`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001dc37`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001dc37`

## pseudocode

```c
__int64 __fastcall BthEnumGetConnectionCountKey(__int64 a1)
{
  struct _DEVICE_OBJECT *v1; // rcx
  unsigned int v2; // ebx
  NTSTATUS v3; // eax
  int v4; // edx
  int v6; // edx
  PULONG ResultLength; // [rsp+28h] [rbp-48h]
  __int64 v8; // [rsp+30h] [rbp-40h] BYREF
  void *DeviceRegKey; // [rsp+38h] [rbp-38h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-30h] BYREF
  _BYTE KeyValueInformation[4]; // [rsp+50h] [rbp-20h] BYREF
  int v12; // [rsp+54h] [rbp-1Ch]
  unsigned int v13; // [rsp+5Ch] [rbp-14h]

  v1 = *(struct _DEVICE_OBJECT **)(a1 + 16);
  v2 = 0;
  DestinationString = 0;
  DeviceRegKey = 0;
  LODWORD(v8) = 0;
  v3 = IoOpenDeviceRegistryKey(v1, 1u, 1u, &DeviceRegKey);
  if ( v3 >= 0 )
  {
    RtlInitUnicodeString(&DestinationString, L"ConnectionCount");
    if ( ZwQueryValueKey(
           DeviceRegKey,
           &DestinationString,
           KeyValuePartialInformation,
           KeyValueInformation,
           0x14u,
           (PULONG)&v8) >= 0
      && v12 == 4 )
    {
      v2 = v13;
    }
    ZwClose(DeviceRegKey);
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LODWORD(ResultLength) = v2;
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        v6,
        3,
        12,
        (__int64)WPP_f24dc5fc8d98372b7b5478949da3430c_Traceguids,
        ResultLength,
        v8);
    }
    return v2;
  }
  else
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        v4,
        3,
        11,
        (__int64)WPP_f24dc5fc8d98372b7b5478949da3430c_Traceguids,
        v3,
        v8);
    return 0;
  }
}

```

## disassembly

```asm
0x14001dba4  mov     [rsp-8+arg_8], rbx
0x14001dba9  push    rbp
0x14001dbaa  mov     rbp, rsp
0x14001dbad  sub     rsp, 70h
0x14001dbb1  mov     rax, cs:__security_cookie
0x14001dbb8  xor     rax, rsp
0x14001dbbb  mov     [rbp+var_8], rax
0x14001dbbf  mov     rcx, [rcx+10h]; DeviceObject
0x14001dbc3  lea     r9, [rbp+DeviceRegKey]; DeviceRegKey
0x14001dbc7  xor     ebx, ebx
0x14001dbc9  xorps   xmm0, xmm0
0x14001dbcc  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14001dbd0  mov     [rbp+DeviceRegKey], rbx
0x14001dbd4  mov     dword ptr [rbp+var_40], ebx
0x14001dbd7  lea     edx, [rbx+1]; DevInstKeyType
0x14001dbda  mov     r8d, edx; DesiredAccess
0x14001dbdd  call    cs:__imp_IoOpenDeviceRegistryKey
0x14001dbe4  nop     dword ptr [rax+rax+00h]
0x14001dbe9  test    eax, eax
0x14001dbeb  jns     short loc_14001DC2C
0x14001dbed  lea     rcx, WPP_RECORDER_INITIALIZED
0x14001dbf4  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14001dbfb  jz      short loc_14001DC25
0x14001dbfd  mov     rcx, cs:WPP_GLOBAL_Control
0x14001dc04  lea     r9d, [rbx+0Bh]
0x14001dc08  mov     dword ptr [rsp+70h+ResultLength], eax
0x14001dc0c  lea     r8d, [rbx+3]
0x14001dc10  lea     rax, WPP_f24dc5fc8d98372b7b5478949da3430c_Traceguids
0x14001dc17  mov     qword ptr [rsp+70h+Length], rax
0x14001dc1c  mov     rcx, [rcx+40h]
0x14001dc20  call    WPP_RECORDER_SF_d
0x14001dc25  xor     eax, eax
0x14001dc27  jmp     loc_14001DCCB
0x14001dc2c  lea     rdx, aConnectioncoun; "ConnectionCount"
0x14001dc33  lea     rcx, [rbp+DestinationString]; DestinationString
0x14001dc37  call    cs:__imp_RtlInitUnicodeString
0x14001dc3e  nop     dword ptr [rax+rax+00h]
0x14001dc43  mov     rcx, [rbp+DeviceRegKey]; KeyHandle
0x14001dc47  lea     rax, [rbp+var_40]
0x14001dc4b  mov     [rsp+70h+ResultLength], rax; ResultLength
0x14001dc50  lea     r9, [rbp+KeyValueInformation]; KeyValueInformation
0x14001dc54  mov     r8d, 2; KeyValueInformationClass
0x14001dc5a  mov     [rsp+70h+Length], 14h; Length
0x14001dc62  lea     rdx, [rbp+DestinationString]; ValueName
0x14001dc66  call    cs:__imp_ZwQueryValueKey
0x14001dc6d  nop     dword ptr [rax+rax+00h]
0x14001dc72  test    eax, eax
0x14001dc74  js      short loc_14001DC7F
0x14001dc76  cmp     [rbp+var_1C], 4
0x14001dc7a  jnz     short loc_14001DC7F
0x14001dc7c  mov     ebx, [rbp+var_14]
0x14001dc7f  mov     rcx, [rbp+DeviceRegKey]; Handle
0x14001dc83  call    cs:__imp_ZwClose
0x14001dc8a  nop     dword ptr [rax+rax+00h]
0x14001dc8f  lea     rcx, WPP_RECORDER_INITIALIZED
0x14001dc96  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14001dc9d  jz      short loc_14001DCC9
0x14001dc9f  mov     rcx, cs:WPP_GLOBAL_Control
0x14001dca6  lea     rax, WPP_f24dc5fc8d98372b7b5478949da3430c_Traceguids
0x14001dcad  mov     r9d, 0Ch
0x14001dcb3  mov     dword ptr [rsp+70h+ResultLength], ebx
0x14001dcb7  mov     qword ptr [rsp+70h+Length], rax
0x14001dcbc  mov     rcx, [rcx+40h]
0x14001dcc0  lea     r8d, [r9-9]
0x14001dcc4  call    WPP_RECORDER_SF_d
0x14001dcc9  mov     eax, ebx
0x14001dccb  mov     rcx, [rbp+var_8]
0x14001dccf  xor     rcx, rsp; StackCookie
0x14001dcd2  call    __security_check_cookie
0x14001dcd7  mov     rbx, [rsp+70h+arg_8]
0x14001dcdf  add     rsp, 70h
0x14001dce3  pop     rbp
0x14001dce4  retn
```
