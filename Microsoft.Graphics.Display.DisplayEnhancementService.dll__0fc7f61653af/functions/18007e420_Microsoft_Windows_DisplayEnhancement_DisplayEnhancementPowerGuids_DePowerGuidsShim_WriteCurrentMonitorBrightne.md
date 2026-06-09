# Microsoft::Windows::DisplayEnhancement::DisplayEnhancementPowerGuids::DePowerGuidsShim::WriteCurrentMonitorBrightness(uchar,uchar)

- ea: `0x18007e420`
- end: `0x18007e60c`
- name: `?WriteCurrentMonitorBrightness@DePowerGuidsShim@DisplayEnhancementPowerGuids@DisplayEnhancement@Windows@Microsoft@@AEAAXEE@Z`
- size: `492`
- prototype: `void __fastcall(Microsoft::Windows::DisplayEnhancement::DisplayEnhancementPowerGuids::DePowerGuidsShim *this, char, char)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x18007be8c`

## callees

- `0x180005860`
- `0x180006440`
- `0x180009050`
- `0x180009aa4`
- `0x18000f778`
- `0x18000fb14`
- `0x180013578`
- `0x18001912c`
- `0x1800194e4`
- `0x18001f19c`
- `0x18005f8b0`
- `0x18007dbdc`
- `0x18007e420`
- `0x18007e920`
- `0x18007e940`
- `0x1800ed010`

## import_xrefs

- `api-ms-win-ntuser-sysparams-l1-1-0!DisplayConfigGetDeviceInfo` at `0x18007e4d5`
- `api-ms-win-ntuser-sysparams-l1-1-0!DisplayConfigGetDeviceInfo` at `0x18007e4d5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18007e549`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18007e549`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18007e5b5`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18007e5b5`

## string_xrefs

- `0x18007e4e9`: `onecoreuap\drivers\mobilepc\displayenhancement\service\depowerguidsshim\lib\depowerguidsshim.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Microsoft::Windows::DisplayEnhancement::DisplayEnhancementPowerGuids::DePowerGuidsShim::WriteCurrentMonitorBrightness(
        Microsoft::Windows::DisplayEnhancement::DisplayEnhancementPowerGuids::DePowerGuidsShim *this,
        char a2,
        char a3)
{
  unsigned int DeviceInfo; // eax
  __int64 v7; // rax
  __int64 v8; // rdx
  __int64 v9; // r8
  const WCHAR *v10; // rax
  HANDLE FileW; // rax
  void *v12; // rdx
  unsigned int v13; // r8d
  void *v14; // rdx
  unsigned int v15; // r8d
  const char *v16; // r9
  unsigned int dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  int dwCreationDispositiona; // [rsp+20h] [rbp-E0h]
  _BYTE InBuffer[8]; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE v20; // [rsp+48h] [rbp-B8h] BYREF
  std::_Ref_count_base *v21[2]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v22[32]; // [rsp+60h] [rbp-A0h] BYREF
  LUID v23; // [rsp+80h] [rbp-80h] BYREF
  UINT32 v24; // [rsp+88h] [rbp-78h]
  _BYTE v25[32]; // [rsp+90h] [rbp-70h] BYREF
  DISPLAYCONFIG_DEVICE_INFO_HEADER requestPacket; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v27[144]; // [rsp+C4h] [rbp-3Ch] BYREF
  _BYTE v28[268]; // [rsp+154h] [rbp+54h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  *(_OWORD *)v21 = 0;
  Microsoft::Windows::DisplayEnhancement::Foundation::SharedSRWLockguard::SharedSRWLockguard(
    (Microsoft::Windows::DisplayEnhancement::Foundation::SharedSRWLockguard *)&v20,
    (Microsoft::Windows::DisplayEnhancement::DisplayEnhancementPowerGuids::DePowerGuidsShim *)((char *)this + 264));
  std::shared_ptr<Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementServerSettingsGroup>::operator=(
    v21,
    (char *)this + 272);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v20);
  if ( v21[0] )
  {
    (*(void (__fastcall **)(std::_Ref_count_base *, LUID *))(*(_QWORD *)v21[0] + 64LL))(v21[0], &v23);
    memset_0(v27, 0, 0x190u);
    requestPacket.adapterId = v23;
    requestPacket.id = v24;
    requestPacket.size = 420;
    requestPacket.type = DISPLAYCONFIG_DEVICE_INFO_GET_TARGET_NAME;
    DeviceInfo = DisplayConfigGetDeviceInfo(&requestPacket);
    if ( DeviceInfo )
    {
      wil::details::in1diag3::_Log_Win32(
        retaddr,
        (void *)0x10E,
        (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\depowerguidsshim\\lib\\depowerguidsshim.cpp",
        (const char *)DeviceInfo,
        dwCreationDisposition);
    }
    else
    {
      v7 = std::wstring::wstring(v22, v28);
      Microsoft::Windows::DisplayEnhancement::Foundation::Utils::GetMonitorIoctlDevicePathFromMonitorDevicePath(v25, v7);
      v10 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v25, v8, v9);
      FileW = CreateFileW(v10, 0xC0000000, 0, 0, 3u, 0x800000u, 0);
      v20 = FileW;
      if ( FileW == (HANDLE)-1LL )
      {
        wil::details::in1diag3::_Log_Hr(retaddr, v12, v13, (const char *)0x80004003LL, dwCreationDispositiona);
      }
      else
      {
        InBuffer[0] = a2;
        InBuffer[1] = a3;
        if ( !DeviceIoControl(FileW, 0x234010u, InBuffer, 2u, 0, 0, 0, 0) )
          wil::details::in1diag3::_Log_GetLastError(retaddr, v14, v15, v16);
      }
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v20);
      std::wstring::_Tidy_deallocate(v25);
    }
  }
  if ( v21[1] )
    std::_Ref_count_base::_Decref(v21[1]);
}

```

## disassembly

```asm
0x18007e420  mov     [rsp-8+arg_18], rbx
0x18007e425  push    rbp
0x18007e426  push    rsi
0x18007e427  push    rdi
0x18007e428  lea     rbp, [rsp-170h]
0x18007e430  sub     rsp, 270h
0x18007e437  mov     rax, cs:__security_cookie
0x18007e43e  xor     rax, rsp
0x18007e441  mov     [rbp+180h+var_20], rax
0x18007e448  mov     sil, r8b
0x18007e44b  mov     dil, dl
0x18007e44e  mov     rbx, rcx
0x18007e451  xorps   xmm0, xmm0
0x18007e454  movdqu  xmmword ptr [rsp+280h+var_230], xmm0
0x18007e45a  lea     rdx, [rcx+108h]; struct wil::srwlock *
0x18007e461  lea     rcx, [rsp+280h+var_238]; this
0x18007e466  call    ??0SharedSRWLockguard@Foundation@DisplayEnhancement@Windows@Microsoft@@QEAA@AEAVsrwlock@wil@@@Z; Microsoft::Windows::DisplayEnhancement::Foundation::SharedSRWLockguard::SharedSRWLockguard(wil::srwlock &)
0x18007e46b  lea     rdx, [rbx+110h]
0x18007e472  lea     rcx, [rsp+280h+var_230]
0x18007e477  call    ??4?$shared_ptr@VDeManagementServerSettingsGroup@DeManagementRpcServer@DisplayEnhancement@Windows@Microsoft@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementServerSettingsGroup>::operator=(std::shared_ptr<Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementServerSettingsGroup> const &)
0x18007e47c  lea     rcx, [rsp+280h+var_238]
0x18007e481  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18007e486  mov     rcx, [rsp+280h+var_230]
0x18007e48b  test    rcx, rcx
0x18007e48e  jz      loc_18007E5DB
0x18007e494  mov     rax, [rcx]
0x18007e497  lea     rdx, [rbp+180h+var_200]
0x18007e49b  mov     rax, [rax+40h]
0x18007e49f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007e4a4  xor     edx, edx; Val
0x18007e4a6  mov     r8d, 190h; Size
0x18007e4ac  lea     rcx, [rbp+180h+var_1BC]; void *
0x18007e4b0  call    memset_0
0x18007e4b5  mov     rax, [rbp+180h+var_200]
0x18007e4b9  mov     qword ptr [rbp+180h+requestPacket.adapterId.LowPart], rax
0x18007e4bd  mov     eax, [rbp+180h+var_1F8]
0x18007e4c0  mov     [rbp+180h+requestPacket.id], eax
0x18007e4c3  mov     [rbp+180h+requestPacket.size], 1A4h
0x18007e4ca  mov     [rbp+180h+requestPacket.type], 2
0x18007e4d1  lea     rcx, [rbp+180h+requestPacket]; requestPacket
0x18007e4d5  call    cs:__imp_DisplayConfigGetDeviceInfo
0x18007e4db  mov     rcx, [rbp+188h]; this
0x18007e4e2  test    eax, eax
0x18007e4e4  jz      short loc_18007E4FF
0x18007e4e6  mov     r9d, eax; char *
0x18007e4e9  lea     r8, aOnecoreuapDriv_41; "onecoreuap\\drivers\\mobilepc\\displaye"...
0x18007e4f0  mov     edx, 10Eh; void *
0x18007e4f5  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x18007e4fa  jmp     loc_18007E5DB
0x18007e4ff  lea     rdx, [rbp+180h+var_12C]
0x18007e503  lea     rcx, [rsp+280h+var_220]
0x18007e508  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18007e50d  mov     rdx, rax
0x18007e510  lea     rcx, [rbp+180h+var_1F0]
0x18007e514  call    ?GetMonitorIoctlDevicePathFromMonitorDevicePath@Utils@Foundation@DisplayEnhancement@Windows@Microsoft@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V67@@Z; Microsoft::Windows::DisplayEnhancement::Foundation::Utils::GetMonitorIoctlDevicePathFromMonitorDevicePath(std::wstring)
0x18007e519  lea     rcx, [rbp+180h+var_1F0]
0x18007e51d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007e522  mov     rcx, rax; lpFileName
0x18007e525  mov     [rsp+280h+hTemplateFile], 0; hTemplateFile
0x18007e52e  mov     [rsp+280h+dwFlagsAndAttributes], 800000h; dwFlagsAndAttributes
0x18007e536  mov     [rsp+280h+dwCreationDisposition], 3; int
0x18007e53e  xor     r9d, r9d; lpSecurityAttributes
0x18007e541  xor     r8d, r8d; dwShareMode
0x18007e544  mov     edx, 0C0000000h; dwDesiredAccess
0x18007e549  call    cs:__imp_CreateFileW
0x18007e54f  mov     [rsp+280h+var_238], rax
0x18007e554  mov     rcx, [rbp+188h]; this
0x18007e55b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18007e55f  jnz     short loc_18007E56E
0x18007e561  mov     r9d, 80004003h; char *
0x18007e567  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18007e56c  jmp     short loc_18007E5C7
0x18007e56e  mov     [rsp+280h+InBuffer], dil
0x18007e573  mov     [rsp+280h+var_23F], sil
0x18007e578  mov     rbx, [rbp+188h]
0x18007e57f  mov     [rsp+280h+lpOverlapped], 0; lpOverlapped
0x18007e588  mov     [rsp+280h+hTemplateFile], 0; lpBytesReturned
0x18007e591  mov     [rsp+280h+dwFlagsAndAttributes], 0; nOutBufferSize
0x18007e599  mov     qword ptr [rsp+280h+dwCreationDisposition], 0; lpOutBuffer
0x18007e5a2  mov     r9d, 2; nInBufferSize
0x18007e5a8  lea     r8, [rsp+280h+InBuffer]; lpInBuffer
0x18007e5ad  mov     edx, 234010h; dwIoControlCode
0x18007e5b2  mov     rcx, rax; hDevice
0x18007e5b5  call    cs:__imp_DeviceIoControl
0x18007e5bb  test    eax, eax
0x18007e5bd  jnz     short loc_18007E5C7
0x18007e5bf  mov     rcx, rbx; this
0x18007e5c2  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18007e5c7  lea     rcx, [rsp+280h+var_238]
0x18007e5cc  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18007e5d1  lea     rcx, [rbp+180h+var_1F0]
0x18007e5d5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007e5da  nop
0x18007e5db  mov     rcx, [rsp+280h+var_230+8]; this
0x18007e5e0  test    rcx, rcx
0x18007e5e3  jz      short loc_18007E5EA
0x18007e5e5  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18007e5ea  mov     rcx, [rbp+180h+var_20]
0x18007e5f1  xor     rcx, rsp; StackCookie
0x18007e5f4  call    __security_check_cookie
0x18007e5f9  mov     rbx, [rsp+280h+arg_18]
0x18007e601  add     rsp, 270h
0x18007e608  pop     rdi
0x18007e609  pop     rsi
0x18007e60a  pop     rbp
0x18007e60b  retn
```
