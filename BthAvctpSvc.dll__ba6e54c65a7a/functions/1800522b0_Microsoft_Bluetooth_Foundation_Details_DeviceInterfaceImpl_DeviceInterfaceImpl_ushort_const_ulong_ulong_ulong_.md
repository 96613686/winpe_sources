# Microsoft::Bluetooth::Foundation::Details::DeviceInterfaceImpl::DeviceInterfaceImpl(ushort const *,ulong,ulong,ulong,std::shared_ptr<Microsoft::Bluetooth::Foundation::DeviceInterfaceObserver>,std::shared_ptr<Microsoft::Bluetooth::Foundation::Details::ThreadProcessorProvider>)

- ea: `0x1800522b0`
- end: `0x180052582`
- name: `??0DeviceInterfaceImpl@Details@Foundation@Bluetooth@Microsoft@@QEAA@PEBGKKKV?$shared_ptr@VDeviceInterfaceObserver@Foundation@Bluetooth@Microsoft@@@std@@V?$shared_ptr@VThreadProcessorProvider@Details@Foundation@Bluetooth@Microsoft@@@6@@Z`
- size: `722`
- prototype: `__int64 __fastcall(__int64, LPCWSTR pszDeviceInterface, DWORD dwDesiredAccess, DWORD dwShareMode, DWORD dwFlagsAndAttributes, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180051ba0`

## callees

- `0x18000dca8`
- `0x18000de78`
- `0x18000e0e0`
- `0x180012130`
- `0x1800151f4`
- `0x180019c68`
- `0x18002eb08`
- `0x180044e84`
- `0x1800522b0`
- `0x180055498`
- `0x18005f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18005230f`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18005230f`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_PropertyW` at `0x18005245c`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_PropertyW` at `0x18005245c`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x180052469`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x180052469`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800524b6`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800524b6`

## pseudocode

```c
__int64 __fastcall Microsoft::Bluetooth::Foundation::Details::DeviceInterfaceImpl::DeviceInterfaceImpl(
        __int64 a1,
        LPCWSTR pszDeviceInterface,
        DWORD dwDesiredAccess,
        DWORD dwShareMode,
        DWORD dwFlagsAndAttributes,
        _QWORD *a6,
        _QWORD *a7)
{
  __int64 v11; // rdi
  __int64 v12; // rax
  char v13; // dl
  char v14; // r8
  __int64 v15; // rax
  __int64 v16; // r10
  CONFIGRET Device_Interface_PropertyW; // eax
  DWORD v18; // eax
  const WCHAR *v19; // rax
  HANDLE FileW; // rax
  const char *v21; // r9
  __int64 *v22; // rax
  __int64 v23; // rcx
  __int64 v24; // rdx
  std::_Ref_count_base *v25; // rcx
  std::_Ref_count_base *v26; // rcx
  std::_Ref_count_base *v27; // rcx
  unsigned int PropertyBufferSize; // [rsp+20h] [rbp-98h]
  ULONG v30; // [rsp+50h] [rbp-68h] BYREF
  DEVPROPTYPE PropertyType; // [rsp+54h] [rbp-64h] BYREF
  _BYTE v32[8]; // [rsp+58h] [rbp-60h] BYREF
  std::_Ref_count_base *v33; // [rsp+60h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  *(_QWORD *)(a1 + 8) = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)a1 = &Microsoft::Bluetooth::Foundation::Details::DeviceInterfaceImpl::`vftable';
  *(_QWORD *)(a1 + 24) = 0;
  *(_QWORD *)(a1 + 32) = 0;
  v11 = a1 + 40;
  std::wstring::wstring(a1 + 40, (__int64)pszDeviceInterface);
  *(_DWORD *)(a1 + 88) = dwFlagsAndAttributes;
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)(a1 + 96), 0, 0);
  *(_QWORD *)(a1 + 136) = -1;
  *(_QWORD *)(a1 + 144) = 0;
  *(_QWORD *)(a1 + 152) = 0;
  if ( a6[1] )
  {
    *(_QWORD *)(a1 + 144) = *a6;
    v12 = a6[1];
    *(_QWORD *)(a1 + 152) = v12;
    _InterlockedIncrement((volatile signed __int32 *)(v12 + 12));
  }
  *(_QWORD *)(a1 + 160) = 0;
  *(_QWORD *)(a1 + 168) = 0;
  *(_QWORD *)(a1 + 176) = 0;
  *(_QWORD *)(a1 + 184) = 0;
  std::_Tree<std::_Tmap_traits<_GUID,std::shared_ptr<Microsoft::Bluetooth::Foundation::Details::DeviceInterfaceImpl::PendingIoSubmission>,std::less<_GUID>,std::allocator<std::pair<_GUID const,std::shared_ptr<Microsoft::Bluetooth::Foundation::Details::DeviceInterfaceImpl::PendingIoSubmission>>>,0>>::_Alloc_sentinel_and_proxy();
  *(_QWORD *)(a1 + 192) = 0;
  *(_QWORD *)(a1 + 200) = 0;
  *(_QWORD *)(a1 + 208) = 0;
  std::list<std::unique_ptr<Microsoft::Bluetooth::Foundation::Details::DeviceInterfaceImpl::DEVICE_HANDLE_NOTIFICATION_CONTEXT>>::_Alloc_sentinel_and_proxy();
  *(_QWORD *)(a1 + 216) = 0;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
    || (v13 = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u) )
  {
    v13 = 0;
  }
  if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    || (v14 = 1, !*((_WORD *)WPP_GLOBAL_Control + 24)) )
  {
    v14 = 0;
  }
  if ( v13 || v14 )
  {
    v15 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v11);
    WPP_RECORDER_AND_TRACE_SF_Sq(
      *(_QWORD *)(v16 + 16),
      5,
      2,
      10,
      &WPP_e62633feb1923f1d4e65c173e11b2cbc_Traceguids,
      v15,
      a1);
  }
  PropertyType = 0;
  v30 = 16;
  Device_Interface_PropertyW = CM_Get_Device_Interface_PropertyW(
                                 pszDeviceInterface,
                                 &DEVPKEY_DeviceInterface_ClassGuid,
                                 &PropertyType,
                                 (PBYTE)(a1 + 72),
                                 &v30,
                                 0);
  v18 = CM_MapCrToWin32Err(Device_Interface_PropertyW, 0x507u);
  if ( v18 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x47,
      (unsigned int)"onecore\\drivers\\bluetooth\\foundation\\lib\\deviceinterface.cpp",
      (const char *)v18,
      PropertyBufferSize);
  v19 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v11);
  FileW = CreateFileW(v19, dwDesiredAccess, dwShareMode, 0, 3u, dwFlagsAndAttributes, 0);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    a1 + 136,
    FileW);
  if ( (unsigned __int64)(*(_QWORD *)(a1 + 136) - 1LL) > 0xFFFFFFFFFFFFFFFDuLL )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x51,
      (unsigned int)"onecore\\drivers\\bluetooth\\foundation\\lib\\deviceinterface.cpp",
      v21);
  v22 = (__int64 *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *, __int64))(*(_QWORD *)*a7 + 16LL))(*a7, v32, 1869180788);
  v23 = *v22;
  v24 = v22[1];
  *v22 = 0;
  v22[1] = 0;
  *(_QWORD *)(a1 + 160) = v23;
  v25 = *(std::_Ref_count_base **)(a1 + 168);
  *(_QWORD *)(a1 + 168) = v24;
  if ( v25 )
    std::_Ref_count_base::_Decref(v25);
  if ( v33 )
    std::_Ref_count_base::_Decref(v33);
  v26 = (std::_Ref_count_base *)a6[1];
  if ( v26 )
    std::_Ref_count_base::_Decref(v26);
  v27 = (std::_Ref_count_base *)a7[1];
  if ( v27 )
    std::_Ref_count_base::_Decref(v27);
  return a1;
}

```

## disassembly

```asm
0x1800522b0  mov     [rsp+arg_0], rcx
0x1800522b5  push    rbx
0x1800522b6  push    rbp
0x1800522b7  push    rsi
0x1800522b8  push    rdi
0x1800522b9  push    r12
0x1800522bb  push    r13
0x1800522bd  push    r14
0x1800522bf  push    r15
0x1800522c1  sub     rsp, 78h
0x1800522c5  mov     r12d, r9d
0x1800522c8  mov     r13d, r8d
0x1800522cb  mov     rbp, rdx
0x1800522ce  mov     rbx, rcx
0x1800522d1  xor     esi, esi
0x1800522d3  mov     [rcx+8], rsi
0x1800522d7  mov     [rcx+10h], rsi
0x1800522db  lea     rax, ??_7DeviceInterfaceImpl@Details@Foundation@Bluetooth@Microsoft@@6B@; const Microsoft::Bluetooth::Foundation::Details::DeviceInterfaceImpl::`vftable'
0x1800522e2  mov     [rcx], rax
0x1800522e5  mov     [rcx+18h], rsi
0x1800522e9  mov     [rcx+20h], rsi
0x1800522ed  lea     rdi, [rcx+28h]
0x1800522f1  mov     rcx, rdi
0x1800522f4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800522f9  nop
0x1800522fa  mov     r15d, [rsp+0B8h+dwFlagsAndAttributes]
0x180052302  mov     [rbx+58h], r15d
0x180052306  lea     rcx, [rbx+60h]; lpCriticalSection
0x18005230a  xor     r8d, r8d; Flags
0x18005230d  xor     edx, edx; dwSpinCount
0x18005230f  call    cs:__imp_InitializeCriticalSectionEx
0x180052315  nop
0x180052316  lea     r14, [rbx+88h]
0x18005231d  mov     qword ptr [r14], 0FFFFFFFFFFFFFFFFh
0x180052324  mov     [rbx+90h], rsi
0x18005232b  mov     [rbx+98h], rsi
0x180052332  mov     rsi, [rsp+0B8h+arg_28]
0x18005233a  xor     edx, edx
0x18005233c  cmp     [rsi+8], rdx
0x180052340  jz      short loc_18005235B
0x180052342  mov     rax, [rsi]
0x180052345  mov     [rbx+90h], rax
0x18005234c  mov     rax, [rsi+8]
0x180052350  mov     [rbx+98h], rax
0x180052357  lock inc dword ptr [rax+0Ch]
0x18005235b  mov     [rbx+0A0h], rdx
0x180052362  mov     [rbx+0A8h], rdx
0x180052369  lea     rcx, [rbx+0B0h]
0x180052370  mov     [rcx], rdx
0x180052373  mov     [rcx+8], rdx
0x180052377  call    ?_Alloc_sentinel_and_proxy@?$_Tree@V?$_Tmap_traits@U_GUID@@V?$shared_ptr@UPendingIoSubmission@DeviceInterfaceImpl@Details@Foundation@Bluetooth@Microsoft@@@std@@U?$less@U_GUID@@@3@V?$allocator@U?$pair@$$CBU_GUID@@V?$shared_ptr@UPendingIoSubmission@DeviceInterfaceImpl@Details@Foundation@Bluetooth@Microsoft@@@std@@@std@@@3@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tmap_traits<_GUID,std::shared_ptr<Microsoft::Bluetooth::Foundation::Details::DeviceInterfaceImpl::PendingIoSubmission>,std::less<_GUID>,std::allocator<std::pair<_GUID const,std::shared_ptr<Microsoft::Bluetooth::Foundation::Details::DeviceInterfaceImpl::PendingIoSubmission>>>,0>>::_Alloc_sentinel_and_proxy(void)
0x18005237c  nop
0x18005237d  xor     eax, eax
0x18005237f  mov     [rbx+0C0h], rax
0x180052386  lea     rcx, [rbx+0C8h]
0x18005238d  mov     [rcx], rax
0x180052390  mov     [rcx+8], rax
0x180052394  call    ?_Alloc_sentinel_and_proxy@?$list@V?$unique_ptr@UDEVICE_HANDLE_NOTIFICATION_CONTEXT@DeviceInterfaceImpl@Details@Foundation@Bluetooth@Microsoft@@U?$default_delete@UDEVICE_HANDLE_NOTIFICATION_CONTEXT@DeviceInterfaceImpl@Details@Foundation@Bluetooth@Microsoft@@@std@@@std@@V?$allocator@V?$unique_ptr@UDEVICE_HANDLE_NOTIFICATION_CONTEXT@DeviceInterfaceImpl@Details@Foundation@Bluetooth@Microsoft@@U?$default_delete@UDEVICE_HANDLE_NOTIFICATION_CONTEXT@DeviceInterfaceImpl@Details@Foundation@Bluetooth@Microsoft@@@std@@@std@@@2@@std@@AEAAXXZ; std::list<std::unique_ptr<Microsoft::Bluetooth::Foundation::Details::DeviceInterfaceImpl::DEVICE_HANDLE_NOTIFICATION_CONTEXT>>::_Alloc_sentinel_and_proxy(void)
0x180052399  nop
0x18005239a  xor     ecx, ecx
0x18005239c  mov     [rbx+0D8h], rcx
0x1800523a3  lea     rax, WPP_GLOBAL_Control
0x1800523aa  mov     r10, cs:WPP_GLOBAL_Control
0x1800523b1  cmp     r10, rax
0x1800523b4  jz      short loc_1800523C6
0x1800523b6  test    byte ptr [r10+1Ch], 2
0x1800523bb  jz      short loc_1800523C6
0x1800523bd  cmp     byte ptr [r10+19h], 5
0x1800523c2  mov     dl, 1
0x1800523c4  jnb     short loc_1800523C8
0x1800523c6  mov     dl, cl
0x1800523c8  lea     rax, WPP_RECORDER_INITIALIZED
0x1800523cf  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1800523d6  jz      short loc_1800523E2
0x1800523d8  cmp     [r10+30h], cx
0x1800523dd  mov     r8b, 1
0x1800523e0  jnz     short loc_1800523E5
0x1800523e2  mov     r8b, cl
0x1800523e5  test    dl, dl
0x1800523e7  jnz     short loc_1800523EE
0x1800523e9  test    r8b, r8b
0x1800523ec  jz      short loc_18005242F
0x1800523ee  mov     rcx, rdi
0x1800523f1  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800523f6  mov     qword ptr [rsp+0B8h+var_70], rbx; char
0x1800523fb  mov     [rsp+0B8h+var_78], rax; __int64
0x180052400  lea     rax, WPP_e62633feb1923f1d4e65c173e11b2cbc_Traceguids
0x180052407  mov     [rsp+0B8h+MessageGuid], rax; MessageGuid
0x18005240c  mov     word ptr [rsp+0B8h+hTemplateFile], 0Ah; __int16
0x180052413  mov     [rsp+0B8h+ulFlags], 2; int
0x18005241b  mov     byte ptr [rsp+0B8h+PropertyBufferSize], 5; char
0x180052420  mov     r9, [r10+28h]
0x180052424  mov     rcx, [r10+10h]; LoggerHandle
0x180052428  call    WPP_RECORDER_AND_TRACE_SF_Sq
0x18005242d  xor     ecx, ecx
0x18005242f  mov     [rsp+0B8h+PropertyType], ecx
0x180052433  mov     [rsp+0B8h+var_68], 10h
0x18005243b  lea     r9, [rbx+48h]; PropertyBuffer
0x18005243f  mov     [rsp+0B8h+ulFlags], ecx; ulFlags
0x180052443  lea     rax, [rsp+0B8h+var_68]
0x180052448  mov     [rsp+0B8h+PropertyBufferSize], rax; unsigned int
0x18005244d  lea     r8, [rsp+0B8h+PropertyType]; PropertyType
0x180052452  lea     rdx, DEVPKEY_DeviceInterface_ClassGuid; PropertyKey
0x180052459  mov     rcx, rbp; pszDeviceInterface
0x18005245c  call    cs:__imp_CM_Get_Device_Interface_PropertyW
0x180052462  mov     ecx, eax; CmReturnCode
0x180052464  mov     edx, 507h; DefaultErr
0x180052469  call    cs:__imp_CM_MapCrToWin32Err
0x18005246f  mov     rcx, [rsp+0B8h]; this
0x180052477  xor     ebp, ebp
0x180052479  test    eax, eax
0x18005247b  jz      short loc_180052490
0x18005247d  mov     r9d, eax; char *
0x180052480  lea     r8, aOnecoreDrivers_16; "onecore\\drivers\\bluetooth\\foundation"...
0x180052487  lea     edx, [rbp+47h]; void *
0x18005248a  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180052490  mov     rcx, rdi
0x180052493  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180052498  mov     [rsp+0B8h+hTemplateFile], rbp; hTemplateFile
0x18005249d  mov     [rsp+0B8h+ulFlags], r15d; dwFlagsAndAttributes
0x1800524a2  mov     dword ptr [rsp+0B8h+PropertyBufferSize], 3; dwCreationDisposition
0x1800524aa  xor     r9d, r9d; lpSecurityAttributes
0x1800524ad  mov     r8d, r12d; dwShareMode
0x1800524b0  mov     edx, r13d; dwDesiredAccess
0x1800524b3  mov     rcx, rax; lpFileName
0x1800524b6  call    cs:__imp_CreateFileW
0x1800524bc  mov     rdx, rax
0x1800524bf  mov     rcx, r14
0x1800524c2  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800524c7  mov     rax, [r14]
0x1800524ca  dec     rax
0x1800524cd  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800524d1  setbe   al
0x1800524d4  mov     rcx, [rsp+0B8h]; this
0x1800524dc  test    al, al
0x1800524de  jnz     short loc_1800524F2
0x1800524e0  lea     r8, aOnecoreDrivers_16; "onecore\\drivers\\bluetooth\\foundation"...
0x1800524e7  mov     edx, 51h ; 'Q'; void *
0x1800524ec  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800524f2  mov     rdi, [rsp+0B8h+arg_30]
0x1800524fa  mov     rcx, [rdi]
0x1800524fd  mov     rax, [rcx]
0x180052500  mov     r8d, 6F696F74h
0x180052506  lea     rdx, [rsp+0B8h+var_60]
0x18005250b  mov     rax, [rax+10h]
0x18005250f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052514  mov     rcx, [rax]
0x180052517  mov     rdx, [rax+8]
0x18005251b  mov     [rax], rbp
0x18005251e  mov     [rax+8], rbp
0x180052522  mov     [rbx+0A0h], rcx
0x180052529  mov     rcx, [rbx+0A8h]; this
0x180052530  mov     [rbx+0A8h], rdx
0x180052537  test    rcx, rcx
0x18005253a  jz      short loc_180052541
0x18005253c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180052541  mov     rcx, [rsp+0B8h+var_58]; this
0x180052546  test    rcx, rcx
0x180052549  jz      short loc_180052551
0x18005254b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180052550  nop
0x180052551  mov     rcx, [rsi+8]; this
0x180052555  test    rcx, rcx
0x180052558  jz      short loc_180052560
0x18005255a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18005255f  nop
0x180052560  mov     rcx, [rdi+8]; this
0x180052564  test    rcx, rcx
0x180052567  jz      short loc_18005256E
0x180052569  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18005256e  mov     rax, rbx
0x180052571  add     rsp, 78h
0x180052575  pop     r15
0x180052577  pop     r14
0x180052579  pop     r13
0x18005257b  pop     r12
0x18005257d  pop     rdi
0x18005257e  pop     rsi
0x18005257f  pop     rbp
0x180052580  pop     rbx
0x180052581  retn
```
