# MFIsWindowsStudioEffectAvailable

- ea: `0x180057f50`
- end: `0x1800580d0`
- name: `MFIsWindowsStudioEffectAvailable`
- size: `384`
- prototype: `__int64 __fastcall(LPCWSTR pszDeviceInterface)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180008f9c`
- `0x18001b39c`
- `0x18001b3d8`
- `0x180028d5c`
- `0x180028e5c`
- `0x18002c008`
- `0x18003c55c`
- `0x18003d064`
- `0x180057f50`

## import_xrefs

- `api-ms-win-devices-config-l1-1-1!CM_Open_Device_Interface_KeyW` at `0x180058054`
- `api-ms-win-devices-config-l1-1-1!CM_Open_Device_Interface_KeyW` at `0x180058054`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_PropertyW` at `0x180058018`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_PropertyW` at `0x180058018`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180058096`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180058096`

## pseudocode

```c
_BOOL8 __fastcall MFIsWindowsStudioEffectAvailable(LPCWSTR pszDeviceInterface, _DWORD *a2)
{
  BOOL v2; // ebx
  DWORD pcbData; // [rsp+40h] [rbp-28h] BYREF
  struct IFSConfiguration *v7; // [rsp+48h] [rbp-20h] BYREF
  HKEY phkDeviceInterface[3]; // [rsp+50h] [rbp-18h] BYREF
  BYTE PropertyBuffer; // [rsp+90h] [rbp+28h] BYREF
  DEVPROPTYPE PropertyType; // [rsp+98h] [rbp+30h] BYREF
  int pvData; // [rsp+A0h] [rbp+38h] BYREF
  ULONG PropertyBufferSize; // [rsp+A8h] [rbp+40h] BYREF

  v7 = 0;
  v2 = 1;
  PropertyBufferSize = 1;
  PropertyType = 0;
  PropertyBuffer = 0;
  phkDeviceInterface[0] = 0;
  if ( a2 )
    *a2 = 0;
  if ( !pszDeviceInterface )
    goto LABEL_16;
  wil::com_ptr_t<Windows::Internal::System::IRelativePanelDirectionTracker,wil::err_returncode_policy>::reset(&v7);
  if ( (int)FSLoadAllAppsDeviceConfiguration(pszDeviceInterface, &v7) < 0 )
    goto LABEL_20;
  if ( (MFGetAttributeUINT64(v7, MF_FRAMESERVER_MANAGED_CAMERA_MODE) & 3) != 0 )
  {
    if ( a2 )
      *a2 = 1;
    goto LABEL_16;
  }
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_39449421>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_39449421>::GetImpl'::`2'::impl)
    || !(unsigned int)MFGetAttributeUINT32(v7, MF_DEVSOURCE_ATTRIBUTE_ENABLE_MS_CAMERA_EFFECTS, 0) )
  {
LABEL_20:
    if ( CM_Get_Device_Interface_PropertyW(
           pszDeviceInterface,
           &DEVPKEY_DeviceInterface_IsWindowsCameraEffectAvailable,
           &PropertyType,
           &PropertyBuffer,
           &PropertyBufferSize,
           0)
      || PropertyType == 17 && PropertyBuffer == 0xFF )
    {
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        phkDeviceInterface,
        0);
      if ( !CM_Open_Device_Interface_KeyW(pszDeviceInterface, 0x20019u, 1u, phkDeviceInterface, 0) )
      {
        pvData = 0;
        pcbData = 4;
        if ( !RegGetValueW(phkDeviceInterface[0], 0, L"FSMEnableMsEffects", 0x10u, 0, &pvData, &pcbData) )
        {
          v2 = pvData != 0;
          goto LABEL_17;
        }
      }
    }
LABEL_16:
    v2 = 0;
  }
LABEL_17:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(phkDeviceInterface);
  wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&v7);
  return v2;
}

```

## disassembly

```asm
0x180057f50  push    rbp
0x180057f52  push    rbx
0x180057f53  push    rsi
0x180057f54  push    rdi
0x180057f55  mov     rbp, rsp
0x180057f58  sub     rsp, 68h
0x180057f5c  mov     [rbp+var_20], 0
0x180057f64  mov     ebx, 1
0x180057f69  mov     [rbp+arg_18], ebx
0x180057f6c  mov     rdi, rdx
0x180057f6f  mov     [rbp+PropertyType], 0
0x180057f76  mov     rsi, rcx
0x180057f79  mov     [rbp+PropertyBuffer], 0
0x180057f7d  mov     [rbp+phkDeviceInterface], 0
0x180057f85  test    rdx, rdx
0x180057f88  jz      short loc_180057F90
0x180057f8a  mov     dword ptr [rdx], 0
0x180057f90  test    rsi, rsi
0x180057f93  jz      loc_1800580B1
0x180057f99  lea     rcx, [rbp+var_20]
0x180057f9d  call    ?reset@?$com_ptr_t@UIRelativePanelDirectionTracker@System@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<Windows::Internal::System::IRelativePanelDirectionTracker,wil::err_returncode_policy>::reset(void)
0x180057fa2  lea     rdx, [rbp+var_20]; struct IFSConfiguration **
0x180057fa6  mov     rcx, rsi; pszDeviceInterface
0x180057fa9  call    FSLoadAllAppsDeviceConfiguration
0x180057fae  test    eax, eax
0x180057fb0  js      short loc_180057FF5
0x180057fb2  mov     rcx, [rbp+var_20]
0x180057fb6  lea     rdx, MF_FRAMESERVER_MANAGED_CAMERA_MODE
0x180057fbd  call    MFGetAttributeUINT64
0x180057fc2  test    al, 3
0x180057fc4  jnz     loc_1800580AA
0x180057fca  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_39449421@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_39449421@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_39449421> `wil::Feature<__WilFeatureTraits_Feature_39449421>::GetImpl(void)'::`2'::impl
0x180057fd1  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_39449421@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_39449421>::__private_IsEnabled(void)
0x180057fd6  test    al, al
0x180057fd8  jz      short loc_180057FF5
0x180057fda  mov     rcx, [rbp+var_20]
0x180057fde  lea     rdx, MF_DEVSOURCE_ATTRIBUTE_ENABLE_MS_CAMERA_EFFECTS
0x180057fe5  xor     r8d, r8d
0x180057fe8  call    MFGetAttributeUINT32
0x180057fed  test    eax, eax
0x180057fef  jnz     loc_1800580B3
0x180057ff5  lea     rax, [rbp+arg_18]
0x180057ff9  mov     [rsp+68h+ulFlags], 0; ulFlags
0x180058001  lea     r9, [rbp+PropertyBuffer]; PropertyBuffer
0x180058005  mov     [rsp+68h+PropertyBufferSize], rax; PropertyBufferSize
0x18005800a  lea     r8, [rbp+PropertyType]; PropertyType
0x18005800e  mov     rcx, rsi; pszDeviceInterface
0x180058011  lea     rdx, DEVPKEY_DeviceInterface_IsWindowsCameraEffectAvailable; PropertyKey
0x180058018  call    cs:__imp_CM_Get_Device_Interface_PropertyW
0x18005801e  test    eax, eax
0x180058020  jnz     short loc_180058032
0x180058022  cmp     [rbp+PropertyType], 11h
0x180058026  jnz     loc_1800580B1
0x18005802c  cmp     [rbp+PropertyBuffer], 0FFh
0x180058030  jnz     short loc_1800580B1
0x180058032  xor     edx, edx
0x180058034  lea     rcx, [rbp+phkDeviceInterface]
0x180058038  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18005803d  lea     r9, [rbp+phkDeviceInterface]; phkDeviceInterface
0x180058041  mov     dword ptr [rsp+68h+PropertyBufferSize], 0; ulFlags
0x180058049  mov     r8d, ebx; Disposition
0x18005804c  mov     edx, 20019h; samDesired
0x180058051  mov     rcx, rsi; pszDeviceInterface
0x180058054  call    cs:__imp_CM_Open_Device_Interface_KeyW
0x18005805a  test    eax, eax
0x18005805c  jnz     short loc_1800580B1
0x18005805e  mov     rcx, [rbp+phkDeviceInterface]; hkey
0x180058062  lea     r8, aFsmenablemseff; "FSMEnableMsEffects"
0x180058069  mov     [rbp+pvData], eax
0x18005806c  mov     r9d, 10h; dwFlags
0x180058072  lea     rax, [rbp+var_28]
0x180058076  mov     [rbp+var_28], 4
0x18005807d  mov     [rsp+68h+pcbData], rax; pcbData
0x180058082  xor     edx, edx; lpSubKey
0x180058084  lea     rax, [rbp+pvData]
0x180058088  mov     qword ptr [rsp+68h+ulFlags], rax; pvData
0x18005808d  mov     [rsp+68h+PropertyBufferSize], 0; pdwType
0x180058096  call    cs:__imp_RegGetValueW
0x18005809c  test    eax, eax
0x18005809e  jnz     short loc_1800580B1
0x1800580a0  xor     ebx, ebx
0x1800580a2  cmp     [rbp+pvData], ebx
0x1800580a5  setnz   bl
0x1800580a8  jmp     short loc_1800580B3
0x1800580aa  test    rdi, rdi
0x1800580ad  jz      short loc_1800580B1
0x1800580af  mov     [rdi], ebx
0x1800580b1  xor     ebx, ebx
0x1800580b3  lea     rcx, [rbp+phkDeviceInterface]
0x1800580b7  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800580bc  lea     rcx, [rbp+var_20]
0x1800580c0  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x1800580c5  mov     eax, ebx
0x1800580c7  add     rsp, 68h
0x1800580cb  pop     rdi
0x1800580cc  pop     rsi
0x1800580cd  pop     rbx
0x1800580ce  pop     rbp
0x1800580cf  retn
```
