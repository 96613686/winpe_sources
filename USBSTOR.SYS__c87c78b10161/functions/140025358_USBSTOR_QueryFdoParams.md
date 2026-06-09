# USBSTOR_QueryFdoParams

- ea: `0x140025358`
- end: `0x140025628`
- name: `USBSTOR_QueryFdoParams`
- size: `720`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1400250c0`

## callees

- `0x1400105e8`
- `0x140010664`
- `0x140013950`
- `0x140013d40`
- `0x140025358`

## import_xrefs

- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x14002549c`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x14002549c`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002550a`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002550a`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x1400253fa`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x1400254e6`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x1400253fa`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x1400254e6`
- `ntoskrnl!ZwQueryValueKey` at `0x14002553c`
- `ntoskrnl!ZwQueryValueKey` at `0x14002553c`
- `ntoskrnl!ZwClose` at `0x1400254ad`
- `ntoskrnl!ZwClose` at `0x140025569`
- `ntoskrnl!ZwClose` at `0x1400254ad`
- `ntoskrnl!ZwClose` at `0x140025569`

## pseudocode

```c
NTSTATUS __fastcall USBSTOR_QueryFdoParams(__int64 a1)
{
  __int64 v2; // rbx
  unsigned int v3; // eax
  struct _DEVICE_OBJECT *v4; // rcx
  NTSTATUS result; // eax
  char v6; // al
  unsigned int v7; // [rsp+30h] [rbp-D0h] BYREF
  int v8; // [rsp+34h] [rbp-CCh] BYREF
  void *DeviceRegKey; // [rsp+38h] [rbp-C8h] BYREF
  ULONG ResultLength; // [rsp+40h] [rbp-C0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v12[22]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE KeyValueInformation[24]; // [rsp+110h] [rbp+10h] BYREF

  v7 = 0;
  DestinationString = 0;
  v8 = 0;
  DeviceRegKey = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 8u)
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_354602438fa331ce245c005e63ec86c9_Traceguids);
  }
  v2 = *(_QWORD *)(a1 + 64);
  v7 = 0;
  v8 = 0;
  if ( IoOpenDeviceRegistryKey(*(PDEVICE_OBJECT *)(v2 + 16), 2u, 0x1F0000u, &DeviceRegKey) >= 0 )
  {
    memset(v12, 0, 0xA8u);
    LODWORD(v12[6]) = 4;
    LODWORD(v12[4]) = 67108868;
    LODWORD(v12[1]) = 288;
    v12[2] = L"DriverFlags";
    LODWORD(v12[8]) = 288;
    v12[3] = &v7;
    v12[5] = &v7;
    v12[9] = L"NonRemovable";
    v12[10] = &v8;
    LODWORD(v12[11]) = 67108868;
    v12[12] = &v8;
    LODWORD(v12[13]) = 4;
    RtlQueryRegistryValuesEx(0x40000000, DeviceRegKey, v12);
    ZwClose(DeviceRegKey);
  }
  v3 = v7;
  if ( v7 >= 4 )
  {
    v3 = 0;
    v7 = 0;
  }
  v4 = *(struct _DEVICE_OBJECT **)(v2 + 16);
  *(_DWORD *)(v2 + 120) = v3;
  *(_DWORD *)(v2 + 124) = v8;
  result = IoOpenDeviceRegistryKey(v4, 1u, 0x20019u, &DeviceRegKey);
  if ( result >= 0 )
  {
    ResultLength = 0;
    RtlInitUnicodeString(&DestinationString, L"EnableSelectiveSuspend");
    if ( ZwQueryValueKey(
           DeviceRegKey,
           &DestinationString,
           KeyValuePartialInformation,
           KeyValueInformation,
           0x14u,
           &ResultLength) >= 0
      && ResultLength )
    {
      v6 = KeyValueInformation[12] != 0;
    }
    else
    {
      v6 = -1;
    }
    *(_BYTE *)(v2 + 2041) = v6;
    result = ZwClose(DeviceRegKey);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 8u) && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      result = WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_354602438fa331ce245c005e63ec86c9_Traceguids);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      if ( _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 8u)
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        result = WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_354602438fa331ce245c005e63ec86c9_Traceguids);
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 8u)
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      {
        return WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_354602438fa331ce245c005e63ec86c9_Traceguids);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x140025358  push    rbp
0x14002535a  push    rbx
0x14002535b  push    r14
0x14002535d  push    r15
0x14002535f  lea     rbp, [rsp-38h]
0x140025364  sub     rsp, 138h
0x14002536b  mov     rax, cs:__security_cookie
0x140025372  xor     rax, rsp
0x140025375  mov     [rbp+50h+var_28], rax
0x140025379  xorps   xmm0, xmm0
0x14002537c  mov     [rsp+150h+var_120], 0
0x140025384  movups  xmmword ptr [rsp+150h+DestinationString.Length], xmm0
0x140025389  mov     rbx, rcx
0x14002538c  mov     [rsp+150h+var_11C], 0
0x140025394  mov     [rsp+150h+DeviceRegKey], 0
0x14002539d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400253a4  lea     r15, WPP_GLOBAL_Control
0x1400253ab  cmp     rcx, r15
0x1400253ae  jz      short loc_1400253D2
0x1400253b0  bt      dword ptr [rcx+2Ch], 8
0x1400253b5  jnb     short loc_1400253D2
0x1400253b7  cmp     byte ptr [rcx+29h], 4
0x1400253bb  jb      short loc_1400253D2
0x1400253bd  mov     rcx, [rcx+18h]
0x1400253c1  lea     r8, WPP_354602438fa331ce245c005e63ec86c9_Traceguids
0x1400253c8  mov     edx, 11h
0x1400253cd  call    WPP_SF_
0x1400253d2  mov     rbx, [rbx+40h]
0x1400253d6  lea     r9, [rsp+150h+DeviceRegKey]; DeviceRegKey
0x1400253db  mov     [rsp+150h+var_120], 0
0x1400253e3  mov     edx, 2; DevInstKeyType
0x1400253e8  mov     [rsp+150h+var_11C], 0
0x1400253f0  mov     r8d, 1F0000h; DesiredAccess
0x1400253f6  mov     rcx, [rbx+10h]; DeviceObject
0x1400253fa  call    cs:__imp_IoOpenDeviceRegistryKey
0x140025401  nop     dword ptr [rax+rax+00h]
0x140025406  test    eax, eax
0x140025408  js      loc_1400254B9
0x14002540e  xor     edx, edx; Val
0x140025410  lea     rcx, [rsp+150h+var_F0]; void *
0x140025415  mov     r8d, 0A8h; Size
0x14002541b  call    memset
0x140025420  mov     ecx, 4000004h
0x140025425  mov     [rbp+50h+var_C0], 4
0x14002542c  mov     edx, 120h
0x140025431  mov     [rbp+50h+var_D0], ecx
0x140025434  lea     rax, aDriverflags; "DriverFlags"
0x14002543b  mov     [rsp+150h+var_E8], edx
0x14002543f  mov     [rsp+150h+var_E0], rax
0x140025444  lea     r8, [rsp+150h+var_F0]
0x140025449  lea     rax, [rsp+150h+var_120]
0x14002544e  mov     [rbp+50h+var_B0], edx
0x140025451  mov     rdx, [rsp+150h+DeviceRegKey]
0x140025456  xor     r9d, r9d
0x140025459  mov     [rsp+150h+var_D8], rax
0x14002545e  lea     rax, [rsp+150h+var_120]
0x140025463  mov     [rbp+50h+var_C8], rax
0x140025467  lea     rax, ValueName; "NonRemovable"
0x14002546e  mov     [rbp+50h+var_A8], rax
0x140025472  lea     rax, [rsp+150h+var_11C]
0x140025477  mov     [rbp+50h+var_A0], rax
0x14002547b  lea     rax, [rsp+150h+var_11C]
0x140025480  mov     [rbp+50h+var_98], ecx
0x140025483  mov     ecx, 40000000h
0x140025488  mov     [rbp+50h+var_90], rax
0x14002548c  mov     [rbp+50h+var_88], 4
0x140025493  mov     qword ptr [rsp+150h+Length], 0
0x14002549c  call    cs:__imp_RtlQueryRegistryValuesEx
0x1400254a3  nop     dword ptr [rax+rax+00h]
0x1400254a8  mov     rcx, [rsp+150h+DeviceRegKey]; Handle
0x1400254ad  call    cs:__imp_ZwClose
0x1400254b4  nop     dword ptr [rax+rax+00h]
0x1400254b9  mov     eax, [rsp+150h+var_120]
0x1400254bd  cmp     eax, 4
0x1400254c0  jb      short loc_1400254C8
0x1400254c2  xor     eax, eax
0x1400254c4  mov     [rsp+150h+var_120], eax
0x1400254c8  mov     rcx, [rbx+10h]; DeviceObject
0x1400254cc  lea     r9, [rsp+150h+DeviceRegKey]; DeviceRegKey
0x1400254d1  mov     [rbx+78h], eax
0x1400254d4  mov     edx, 1; DevInstKeyType
0x1400254d9  mov     eax, [rsp+150h+var_11C]
0x1400254dd  mov     r8d, 20019h; DesiredAccess
0x1400254e3  mov     [rbx+7Ch], eax
0x1400254e6  call    cs:__imp_IoOpenDeviceRegistryKey
0x1400254ed  nop     dword ptr [rax+rax+00h]
0x1400254f2  test    eax, eax
0x1400254f4  js      short loc_140025575
0x1400254f6  lea     rdx, aEnableselectiv; "EnableSelectiveSuspend"
0x1400254fd  mov     [rsp+150h+var_110], 0
0x140025505  lea     rcx, [rsp+150h+DestinationString]; DestinationString
0x14002550a  call    cs:__imp_RtlInitUnicodeString
0x140025511  nop     dword ptr [rax+rax+00h]
0x140025516  mov     rcx, [rsp+150h+DeviceRegKey]; KeyHandle
0x14002551b  lea     rax, [rsp+150h+var_110]
0x140025520  mov     [rsp+150h+ResultLength], rax; ResultLength
0x140025525  lea     r9, [rbp+50h+KeyValueInformation]; KeyValueInformation
0x140025529  mov     r8d, 2; KeyValueInformationClass
0x14002552f  mov     [rsp+150h+Length], 14h; Length
0x140025537  lea     rdx, [rsp+150h+DestinationString]; ValueName
0x14002553c  call    cs:__imp_ZwQueryValueKey
0x140025543  nop     dword ptr [rax+rax+00h]
0x140025548  test    eax, eax
0x14002554a  js      short loc_14002555C
0x14002554c  cmp     [rsp+150h+var_110], 0
0x140025551  jbe     short loc_14002555C
0x140025553  cmp     [rbp+50h+var_34], 0
0x140025557  setnz   al
0x14002555a  jmp     short loc_14002555E
0x14002555c  mov     al, 0FFh
0x14002555e  mov     [rbx+7F9h], al
0x140025564  mov     rcx, [rsp+150h+DeviceRegKey]; Handle
0x140025569  call    cs:__imp_ZwClose
0x140025570  nop     dword ptr [rax+rax+00h]
0x140025575  mov     rcx, cs:WPP_GLOBAL_Control
0x14002557c  cmp     rcx, r15
0x14002557f  jz      loc_14002560D
0x140025585  bt      dword ptr [rcx+2Ch], 8
0x14002558a  jnb     short loc_1400255AC
0x14002558c  cmp     byte ptr [rcx+29h], 4
0x140025590  jb      short loc_1400255AC
0x140025592  mov     r9d, [rsp+150h+var_120]
0x140025597  lea     r8, WPP_354602438fa331ce245c005e63ec86c9_Traceguids
0x14002559e  mov     rcx, [rcx+18h]
0x1400255a2  mov     edx, 12h
0x1400255a7  call    WPP_SF_d
0x1400255ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1400255b3  cmp     rcx, r15
0x1400255b6  jz      short loc_14002560D
0x1400255b8  bt      dword ptr [rcx+2Ch], 8
0x1400255bd  jnb     short loc_1400255DF
0x1400255bf  cmp     byte ptr [rcx+29h], 4
0x1400255c3  jb      short loc_1400255DF
0x1400255c5  mov     r9d, [rsp+150h+var_11C]
0x1400255ca  lea     r8, WPP_354602438fa331ce245c005e63ec86c9_Traceguids
0x1400255d1  mov     rcx, [rcx+18h]
0x1400255d5  mov     edx, 13h
0x1400255da  call    WPP_SF_d
0x1400255df  mov     rcx, cs:WPP_GLOBAL_Control
0x1400255e6  cmp     rcx, r15
0x1400255e9  jz      short loc_14002560D
0x1400255eb  bt      dword ptr [rcx+2Ch], 8
0x1400255f0  jnb     short loc_14002560D
0x1400255f2  cmp     byte ptr [rcx+29h], 5
0x1400255f6  jb      short loc_14002560D
0x1400255f8  mov     rcx, [rcx+18h]
0x1400255fc  lea     r8, WPP_354602438fa331ce245c005e63ec86c9_Traceguids
0x140025603  mov     edx, 14h
0x140025608  call    WPP_SF_
0x14002560d  mov     rcx, [rbp+50h+var_28]
0x140025611  xor     rcx, rsp; StackCookie
0x140025614  call    __security_check_cookie
0x140025619  add     rsp, 138h
0x140025620  pop     r15
0x140025622  pop     r14
0x140025624  pop     rbx
0x140025625  pop     rbp
0x140025626  retn
```
