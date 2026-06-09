# USBDevice::_OpenDeviceInterfaceKey(ushort const *)

- ea: `0x1800307ec`
- end: `0x18003093a`
- name: `?_OpenDeviceInterfaceKey@USBDevice@@CA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEBG@Z`
- size: `334`
- prototype: `HKEY *__fastcall(HKEY *, const WCHAR *)`
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180030038`
- `0x180030430`

## callees

- `0x180002d40`
- `0x18001cf80`
- `0x18002b28c`
- `0x1800307ec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800308d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800308d4`
- `SETUPAPI!SetupDiCreateDeviceInfoList` at `0x18003081d`
- `SETUPAPI!SetupDiCreateDeviceInfoList` at `0x18003081d`
- `SETUPAPI!SetupDiOpenDeviceInterfaceW` at `0x18003087f`
- `SETUPAPI!SetupDiOpenDeviceInterfaceW` at `0x18003087f`
- `SETUPAPI!SetupDiOpenDeviceInterfaceRegKey` at `0x18003089a`
- `SETUPAPI!SetupDiOpenDeviceInterfaceRegKey` at `0x18003089a`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x1800308f3`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x1800308f3`

## string_xrefs

- `0x180030842`: `onecoreuap\printscan\print\printscanbroker\class\usbdevice.cpp`
- `0x1800308be`: `onecoreuap\printscan\print\printscanbroker\class\usbdevice.cpp`
- `0x180030928`: `onecoreuap\printscan\print\printscanbroker\class\usbdevice.cpp`
- `0x180030832`: `SetupDiCreateDeviceInfoList failed`
- `0x180030921`: `SetupDiOpenDeviceInterface failed`
- `0x1800308ae`: `SetupDiOpenDeviceInterfaceRegKey failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
HKEY *__fastcall USBDevice::_OpenDeviceInterfaceKey(HKEY *a1, const WCHAR *a2)
{
  HKEY v4; // rbx
  DWORD LastError; // eax
  char *v7; // [rsp+20h] [rbp-60h]
  const char *v8; // [rsp+28h] [rbp-58h]
  const char *v9; // [rsp+28h] [rbp-58h]
  HDEVINFO DeviceInfoSet[3]; // [rsp+30h] [rbp-50h] BYREF
  char v11; // [rsp+48h] [rbp-38h]
  _SP_DEVICE_INTERFACE_DATA DeviceInterfaceData; // [rsp+50h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+8h]

  DeviceInfoSet[0] = SetupDiCreateDeviceInfoList(0, 0);
  wil::details::in1diag3::Throw_GetLastErrorIfMsg(
    retaddr,
    (void *)0xBB,
    (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\usbdevice.cpp",
    (const char *)(DeviceInfoSet[0] == (HDEVINFO)-1LL),
    (bool)"SetupDiCreateDeviceInfoList failed",
    v8);
  DeviceInfoSet[2] = DeviceInfoSet;
  v11 = 1;
  memset(&DeviceInterfaceData, 0, sizeof(DeviceInterfaceData));
  DeviceInterfaceData.cbSize = 32;
  if ( SetupDiOpenDeviceInterfaceW(DeviceInfoSet[0], a2, 0, &DeviceInterfaceData) )
  {
    v4 = SetupDiOpenDeviceInterfaceRegKey(DeviceInfoSet[0], &DeviceInterfaceData, 0, 0xF003Fu);
    wil::details::in1diag3::Throw_GetLastErrorIfMsg(
      retaddr,
      (void *)0xC6,
      (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\usbdevice.cpp",
      (const char *)((HKEY)((char *)v4 + 1) == 0),
      (bool)"SetupDiOpenDeviceInterfaceRegKey failed",
      v9);
    *a1 = v4;
  }
  else
  {
    LastError = GetLastError();
    if ( LastError != 1168 && LastError != -536870363 )
      wil::details::in1diag3::Throw_GetLastErrorMsg(
        retaddr,
        (void *)0xD1,
        (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\usbdevice.cpp",
        "SetupDiOpenDeviceInterface failed",
        v7);
    *a1 = 0;
  }
  SetupDiDestroyDeviceInfoList(DeviceInfoSet[0]);
  return a1;
}

```

## disassembly

```asm
0x1800307ec  mov     [rsp-8+arg_10], rbx
0x1800307f1  mov     [rsp-8+arg_18], rdi
0x1800307f6  push    rbp
0x1800307f7  mov     rbp, rsp
0x1800307fa  sub     rsp, 80h
0x180030801  mov     rax, cs:__security_cookie
0x180030808  xor     rax, rsp
0x18003080b  mov     [rbp+var_10], rax
0x18003080f  mov     rbx, rdx
0x180030812  mov     rdi, rcx
0x180030815  mov     [rbp+DeviceInfoSet], rcx
0x180030819  xor     edx, edx; hwndParent
0x18003081b  xor     ecx, ecx; ClassGuid
0x18003081d  call    cs:__imp_SetupDiCreateDeviceInfoList
0x180030823  mov     [rbp+DeviceInfoSet], rax
0x180030827  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003082b  setz    al
0x18003082e  mov     rcx, [rbp+8]; this
0x180030832  lea     rdx, aSetupdicreated; "SetupDiCreateDeviceInfoList failed"
0x180030839  mov     [rsp+80h+var_60], rdx; char *
0x18003083e  movzx   r9d, al; char *
0x180030842  lea     r8, aOnecoreuapPrin_1; "onecoreuap\\printscan\\print\\printscan"...
0x180030849  mov     edx, 0BBh; void *
0x18003084e  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x180030853  lea     rax, [rbp+DeviceInfoSet]
0x180030857  mov     [rbp+var_40], rax
0x18003085b  mov     [rbp+var_38], 1
0x18003085f  xorps   xmm0, xmm0
0x180030862  movups  xmmword ptr [rbp+DeviceInterfaceData.cbSize], xmm0
0x180030866  movups  xmmword ptr [rbp+DeviceInterfaceData.InterfaceClassGuid.Data4+4], xmm0
0x18003086a  mov     [rbp+DeviceInterfaceData.cbSize], 20h ; ' '
0x180030871  lea     r9, [rbp+DeviceInterfaceData]; DeviceInterfaceData
0x180030875  xor     r8d, r8d; OpenFlags
0x180030878  mov     rdx, rbx; DevicePath
0x18003087b  mov     rcx, [rbp+DeviceInfoSet]; DeviceInfoSet
0x18003087f  call    cs:__imp_SetupDiOpenDeviceInterfaceW
0x180030885  test    eax, eax
0x180030887  jz      short loc_1800308D4
0x180030889  mov     r9d, 0F003Fh; samDesired
0x18003088f  xor     r8d, r8d; Reserved
0x180030892  lea     rdx, [rbp+DeviceInterfaceData]; DeviceInterfaceData
0x180030896  mov     rcx, [rbp+DeviceInfoSet]; DeviceInfoSet
0x18003089a  call    cs:__imp_SetupDiOpenDeviceInterfaceRegKey
0x1800308a0  mov     rbx, rax
0x1800308a3  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800308a7  setz    dl
0x1800308aa  mov     rcx, [rbp+8]; this
0x1800308ae  lea     rax, aSetupdiopendev_0; "SetupDiOpenDeviceInterfaceRegKey failed"
0x1800308b5  mov     [rsp+80h+var_60], rax; bool
0x1800308ba  movzx   r9d, dl; char *
0x1800308be  lea     r8, aOnecoreuapPrin_1; "onecoreuap\\printscan\\print\\printscan"...
0x1800308c5  mov     edx, 0C6h; void *
0x1800308ca  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x1800308cf  mov     [rdi], rbx
0x1800308d2  jmp     short loc_1800308EF
0x1800308d4  call    cs:__imp_GetLastError
0x1800308da  cmp     eax, 490h
0x1800308df  jz      short loc_1800308E8
0x1800308e1  cmp     eax, 0E0000225h
0x1800308e6  jnz     short loc_18003091D
0x1800308e8  mov     qword ptr [rdi], 0
0x1800308ef  mov     rcx, [rbp+DeviceInfoSet]; DeviceInfoSet
0x1800308f3  call    cs:__imp_SetupDiDestroyDeviceInfoList
0x1800308f9  mov     rax, rdi
0x1800308fc  mov     rcx, [rbp+var_10]
0x180030900  xor     rcx, rsp; StackCookie
0x180030903  call    __security_check_cookie
0x180030908  lea     r11, [rsp+80h+var_s0]
0x180030910  mov     rbx, [r11+20h]
0x180030914  mov     rdi, [r11+28h]
0x180030918  mov     rsp, r11
0x18003091b  pop     rbp
0x18003091c  retn
0x18003091d  mov     rcx, [rbp+8]; this
0x180030921  lea     r9, aSetupdiopendev; "SetupDiOpenDeviceInterface failed"
0x180030928  lea     r8, aOnecoreuapPrin_1; "onecoreuap\\printscan\\print\\printscan"...
0x18003092f  mov     edx, 0D1h; void *
0x180030934  call    ?Throw_GetLastErrorMsg@in1diag3@details@wil@@YAXPEAXIPEBD1ZZ; wil::details::in1diag3::Throw_GetLastErrorMsg(void *,uint,char const *,char const *,...)
```
