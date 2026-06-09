# NarratorAdminFlowHandler::SetBrailleDisplayDriver(HSTRING__ *,HSTRING__ *)

- ea: `0x14006f494`
- end: `0x14006f732`
- name: `?SetBrailleDisplayDriver@NarratorAdminFlowHandler@@SAJPEAUHSTRING__@@0@Z`
- size: `670`
- prototype: `__int64 __fastcall(HSTRING string, HSTRING)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, service_task, installer_update`

## callers

- `0x140020120`

## callees

- `0x140004e68`
- `0x140005f30`
- `0x14000614e`
- `0x14000d850`
- `0x14002a2c0`
- `0x14002a3e8`
- `0x14006d874`
- `0x14006ef04`
- `0x14006f15c`
- `0x14006f494`
- `0x14007037c`
- `0x1400707f8`
- `0x1400708a8`
- `0x140070b98`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x14006f54a`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x14006f54a`
- `KERNEL32!GetLastError` at `0x14006f66a`
- `KERNEL32!GetLastError` at `0x14006f66a`
- `newdev!DiInstallDevice` at `0x14006f660`
- `newdev!DiInstallDevice` at `0x14006f660`
- `SETUPAPI!SetupDiGetClassDevsW` at `0x14006f4cb`
- `SETUPAPI!SetupDiGetClassDevsW` at `0x14006f4cb`
- `SETUPAPI!SetupDiGetDeviceInstallParamsW` at `0x14006f5b8`
- `SETUPAPI!SetupDiGetDeviceInstallParamsW` at `0x14006f5b8`
- `SETUPAPI!SetupDiSetDeviceInstallParamsW` at `0x14006f5e1`
- `SETUPAPI!SetupDiSetDeviceInstallParamsW` at `0x14006f5e1`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x14006f702`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x14006f702`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14006f4ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14006f541`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14006f4ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14006f541`

## string_xrefs

- `0x14006f6a3`: `pcshell\shell\systemsettings\adminflows\accessibility\narratoradminflowhandler.cpp`
- `0x14006f6cd`: `pcshell\shell\systemsettings\adminflows\accessibility\narratoradminflowhandler.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall NarratorAdminFlowHandler::SetBrailleDisplayDriver(HSTRING string, HSTRING a2)
{
  PCWSTR StringRawBuffer; // rdx
  PCWSTR v5; // rax
  const void *DriverInfo; // rax
  bool IsRunning; // bl
  signed int LastError; // eax
  unsigned __int64 v9; // r9
  DWORD Flags; // [rsp+20h] [rbp-F48h]
  WINBOOL NeedReboot; // [rsp+30h] [rbp-F38h] BYREF
  HDEVINFO DeviceInfoSet; // [rsp+38h] [rbp-F30h] BYREF
  SC_HANDLE v14[3]; // [rsp+40h] [rbp-F28h] BYREF
  char v15; // [rsp+58h] [rbp-F10h]
  _BYTE v16[32]; // [rsp+60h] [rbp-F08h] BYREF
  int v17; // [rsp+80h] [rbp-EE8h] BYREF
  struct _SP_DEVINFO_DATA DeviceInfoData; // [rsp+6A0h] [rbp-8C8h] BYREF
  _BYTE v19[32]; // [rsp+6C0h] [rbp-8A8h] BYREF
  _SP_DEVINSTALL_PARAMS_W DeviceInstallParams; // [rsp+6E0h] [rbp-888h] BYREF
  _SP_DRVINFO_DATA_V2_A DriverInfoData; // [rsp+930h] [rbp-638h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F68h] [rbp+0h]

  DeviceInfoSet = SetupDiGetClassDevsW(&GUID_DEVCLASS_USB, 0, 0, 6u);
  v14[2] = (SC_HANDLE)&DeviceInfoSet;
  v15 = 1;
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  std::wstring::wstring((__int64)v19, (__int64)StringRawBuffer);
  DeviceInfoData = *(struct _SP_DEVINFO_DATA *)anonymous_namespace_::GetDeviceData(v16, &DeviceInfoSet, v19);
  std::wstring::_Tidy_deallocate(v19);
  v5 = WindowsGetStringRawBuffer(a2, 0);
  _o__wtoi(v5);
  DriverInfo = (const void *)anonymous_namespace_::GetDriverInfo((int)&v17);
  memcpy_0(&DriverInfoData, DriverInfo, 0x620u);
  memset_0(&DeviceInstallParams.Flags, 0, 0x244u);
  DeviceInstallParams.cbSize = 584;
  if ( SetupDiGetDeviceInstallParamsW(DeviceInfoSet, &DeviceInfoData, &DeviceInstallParams) )
  {
    DeviceInstallParams.FlagsEx |= 1u;
    SetupDiSetDeviceInstallParamsW(DeviceInfoSet, &DeviceInfoData, &DeviceInstallParams);
  }
  std::wstring::wstring((__int64)v19, (__int64)L"brlapi");
  ServiceHandler::ServiceHandler(v14, (__int64)v19);
  std::wstring::_Tidy_deallocate(v19);
  IsRunning = BrlApiService::IsRunning((BrlApiService *)v14);
  if ( IsRunning )
    ServiceHandler::Stop(v14);
  NeedReboot = 0;
  if ( !DiInstallDevice(0, DeviceInfoSet, &DeviceInfoData, &DriverInfoData, 0, &NeedReboot) )
  {
    LastError = GetLastError();
    v9 = (unsigned int)LastError;
    if ( (LastError & 0xE0000000) == 0xE0000000 )
    {
      v9 = (unsigned __int16)LastError | 0x800F0000;
    }
    else if ( LastError > 0 )
    {
      v9 = (unsigned __int16)LastError | 0x80070000;
    }
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x153,
      (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\accessibility\\narratoradminflowhandler.cpp",
      (const char *)v9,
      Flags);
  }
  if ( NeedReboot )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x156,
      (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\accessibility\\narratoradminflowhandler.cpp",
      (const char *)0x80070BC2LL,
      Flags);
  if ( IsRunning )
    BrlApiService::Restart((BrlApiService *)v14);
  ServiceHandler::~ServiceHandler((ServiceHandler *)v14);
  if ( DeviceInfoSet )
    SetupDiDestroyDeviceInfoList(DeviceInfoSet);
  return 0;
}

```

## disassembly

```asm
0x14006f494  mov     [rsp+arg_10], rbx
0x14006f499  push    rdi
0x14006f49a  sub     rsp, 0F60h
0x14006f4a1  mov     rax, cs:__security_cookie
0x14006f4a8  xor     rax, rsp
0x14006f4ab  mov     [rsp+0F68h+var_18], rax
0x14006f4b3  mov     rdi, rdx
0x14006f4b6  mov     rbx, rcx
0x14006f4b9  mov     r9d, 6; Flags
0x14006f4bf  xor     r8d, r8d; hwndParent
0x14006f4c2  xor     edx, edx; Enumerator
0x14006f4c4  lea     rcx, GUID_DEVCLASS_USB; ClassGuid
0x14006f4cb  call    cs:__imp_SetupDiGetClassDevsW
0x14006f4d1  mov     [rsp+0F68h+DeviceInfoSet], rax
0x14006f4d6  lea     rax, [rsp+0F68h+DeviceInfoSet]
0x14006f4db  mov     [rsp+0F68h+var_F18], rax
0x14006f4e0  mov     [rsp+0F68h+var_F10], 1
0x14006f4e5  xor     edx, edx; length
0x14006f4e7  mov     rcx, rbx; string
0x14006f4ea  call    cs:__imp_WindowsGetStringRawBuffer
0x14006f4f0  mov     rdx, rax
0x14006f4f3  lea     rcx, [rsp+0F68h+var_8A8]
0x14006f4fb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x14006f500  nop
0x14006f501  lea     r8, [rsp+0F68h+var_8A8]
0x14006f509  lea     rdx, [rsp+0F68h+DeviceInfoSet]
0x14006f50e  lea     rcx, [rsp+0F68h+var_F08]
0x14006f513  call    _anonymous_namespace___GetDeviceData
0x14006f518  movups  xmm0, xmmword ptr [rax]
0x14006f51b  movups  xmmword ptr [rsp+0F68h+DeviceInfoData.cbSize], xmm0
0x14006f523  movups  xmm1, xmmword ptr [rax+10h]
0x14006f527  movups  xmmword ptr [rsp+0F68h+DeviceInfoData.ClassGuid.Data4+4], xmm1
0x14006f52f  lea     rcx, [rsp+0F68h+var_8A8]
0x14006f537  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14006f53c  xor     edx, edx; length
0x14006f53e  mov     rcx, rdi; string
0x14006f541  call    cs:__imp_WindowsGetStringRawBuffer
0x14006f547  mov     rcx, rax
0x14006f54a  call    cs:__imp__o__wtoi
0x14006f550  mov     r9d, eax
0x14006f553  lea     r8, [rsp+0F68h+DeviceInfoData]
0x14006f55b  lea     rdx, [rsp+0F68h+DeviceInfoSet]
0x14006f560  lea     rcx, [rsp+0F68h+var_EE8]; int
0x14006f568  call    _anonymous_namespace___GetDriverInfo
0x14006f56d  lea     rcx, [rsp+0F68h+DriverInfoData]; void *
0x14006f575  mov     rdx, rax; Src
0x14006f578  mov     r8d, 620h; Size
0x14006f57e  call    memcpy_0
0x14006f583  xor     edx, edx; Val
0x14006f585  mov     r8d, 244h; Size
0x14006f58b  lea     rcx, [rsp+0F68h+DeviceInstallParams.Flags]; void *
0x14006f593  call    memset_0
0x14006f598  mov     [rsp+0F68h+DeviceInstallParams.cbSize], 248h
0x14006f5a3  lea     r8, [rsp+0F68h+DeviceInstallParams]; DeviceInstallParams
0x14006f5ab  lea     rdx, [rsp+0F68h+DeviceInfoData]; DeviceInfoData
0x14006f5b3  mov     rcx, [rsp+0F68h+DeviceInfoSet]; DeviceInfoSet
0x14006f5b8  call    cs:__imp_SetupDiGetDeviceInstallParamsW
0x14006f5be  xor     edi, edi
0x14006f5c0  test    eax, eax
0x14006f5c2  jz      short loc_14006F5E7
0x14006f5c4  or      [rsp+0F68h+DeviceInstallParams.FlagsEx], 1
0x14006f5cc  lea     r8, [rsp+0F68h+DeviceInstallParams]; DeviceInstallParams
0x14006f5d4  lea     rdx, [rsp+0F68h+DeviceInfoData]; DeviceInfoData
0x14006f5dc  mov     rcx, [rsp+0F68h+DeviceInfoSet]; DeviceInfoSet
0x14006f5e1  call    cs:__imp_SetupDiSetDeviceInstallParamsW
0x14006f5e7  lea     rdx, aBrlapi; "brlapi"
0x14006f5ee  lea     rcx, [rsp+0F68h+var_8A8]
0x14006f5f6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x14006f5fb  nop
0x14006f5fc  lea     rdx, [rsp+0F68h+var_8A8]
0x14006f604  lea     rcx, [rsp+0F68h+var_F28]
0x14006f609  call    ??0ServiceHandler@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ServiceHandler::ServiceHandler(std::wstring const &)
0x14006f60e  nop
0x14006f60f  lea     rcx, [rsp+0F68h+var_8A8]
0x14006f617  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14006f61c  nop
0x14006f61d  lea     rcx, [rsp+0F68h+var_F28]; this
0x14006f622  call    ?IsRunning@BrlApiService@@QEBA_NXZ; BrlApiService::IsRunning(void)
0x14006f627  mov     bl, al
0x14006f629  test    al, al
0x14006f62b  jz      short loc_14006F637
0x14006f62d  lea     rcx, [rsp+0F68h+var_F28]; this
0x14006f632  call    ?Stop@ServiceHandler@@QEBAXXZ; ServiceHandler::Stop(void)
0x14006f637  mov     [rsp+0F68h+var_F38], edi
0x14006f63b  lea     rax, [rsp+0F68h+var_F38]
0x14006f640  mov     [rsp+0F68h+NeedReboot], rax; NeedReboot
0x14006f645  mov     [rsp+0F68h+Flags], edi; int
0x14006f649  lea     r9, [rsp+0F68h+DriverInfoData]; DriverInfoData
0x14006f651  lea     r8, [rsp+0F68h+DeviceInfoData]; DeviceInfoData
0x14006f659  mov     rdx, [rsp+0F68h+DeviceInfoSet]; DeviceInfoSet
0x14006f65e  xor     ecx, ecx; hwndParent
0x14006f660  call    cs:__imp_DiInstallDevice
0x14006f666  test    eax, eax
0x14006f668  jnz     short loc_14006F6B4
0x14006f66a  call    cs:__imp_GetLastError
0x14006f670  mov     r9d, eax
0x14006f673  mov     ecx, 0E0000000h
0x14006f678  and     eax, ecx
0x14006f67a  cmp     eax, ecx
0x14006f67c  jnz     short loc_14006F68B
0x14006f67e  movzx   r9d, r9w
0x14006f682  or      r9d, 800F0000h
0x14006f689  jmp     short loc_14006F69B
0x14006f68b  test    r9d, r9d
0x14006f68e  jle     short loc_14006F69B
0x14006f690  movzx   r9d, r9w
0x14006f694  or      r9d, 80070000h; char *
0x14006f69b  mov     rcx, [rsp+0F68h]; this
0x14006f6a3  lea     r8, aPcshellShellSy_31; "pcshell\\shell\\systemsettings\\adminfl"...
0x14006f6aa  mov     edx, 153h; void *
0x14006f6af  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14006f6b4  cmp     [rsp+0F68h+var_F38], edi
0x14006f6b8  setnz   al
0x14006f6bb  mov     rcx, [rsp+0F68h]; this
0x14006f6c3  test    al, al
0x14006f6c5  jz      short loc_14006F6DE
0x14006f6c7  mov     r9d, 80070BC2h; char *
0x14006f6cd  lea     r8, aPcshellShellSy_31; "pcshell\\shell\\systemsettings\\adminfl"...
0x14006f6d4  mov     edx, 156h; void *
0x14006f6d9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14006f6de  test    bl, bl
0x14006f6e0  jz      short loc_14006F6ED
0x14006f6e2  lea     rcx, [rsp+0F68h+var_F28]; this
0x14006f6e7  call    ?Restart@BrlApiService@@QEBAXXZ; BrlApiService::Restart(void)
0x14006f6ec  nop
0x14006f6ed  lea     rcx, [rsp+0F68h+var_F28]; this
0x14006f6f2  call    ??1ServiceHandler@@QEAA@XZ; ServiceHandler::~ServiceHandler(void)
0x14006f6f7  nop
0x14006f6f8  mov     rcx, [rsp+0F68h+DeviceInfoSet]; DeviceInfoSet
0x14006f6fd  test    rcx, rcx
0x14006f700  jz      short loc_14006F708
0x14006f702  call    cs:__imp_SetupDiDestroyDeviceInfoList
0x14006f708  xor     eax, eax
0x14006f70a  jmp     short loc_14006F710
0x14006f70c  mov     eax, [rsp+0F68h+var_F38]
0x14006f710  mov     rcx, [rsp+0F68h+var_18]
0x14006f718  xor     rcx, rsp; StackCookie
0x14006f71b  call    __security_check_cookie
0x14006f720  mov     rbx, [rsp+0F68h+arg_10]
0x14006f728  add     rsp, 0F60h
0x14006f72f  pop     rdi
0x14006f730  retn
```
