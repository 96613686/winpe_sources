# USBDevice::_GetDevInstFromPath(ushort const *)

- ea: `0x1800306d8`
- end: `0x1800307e6`
- name: `?_GetDevInstFromPath@USBDevice@@AEAAKPEBG@Z`
- size: `270`
- prototype: `__int64 __fastcall(USBDevice *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18003010c`

## callees

- `0x180002d40`
- `0x180003a0c`
- `0x18000f760`
- `0x1800306d8`

## import_xrefs

- `SETUPAPI!CM_Locate_DevNodeW` at `0x18003076b`
- `SETUPAPI!CM_Locate_DevNodeW` at `0x18003076b`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_PropertyW` at `0x180030749`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Device_Interface_PropertyW` at `0x180030749`

## string_xrefs

- `0x1800307a2`: `USBDevice::_DevicePathToCmDeviceId`
- `0x180030784`: `USBDevice::_GetDevInstFromPath`
- `0x1800307b8`: `USBDevice::_GetDevInstFromPath`

## pseudocode

```c
__int64 __fastcall USBDevice::_GetDevInstFromPath(USBDevice *this, const unsigned __int16 *a2)
{
  CONFIGRET Device_Interface_PropertyW; // eax
  CONFIGRET v4; // eax
  DEVPROPTYPE PropertyType; // [rsp+30h] [rbp-D0h] BYREF
  DEVNODE pdnDevInst; // [rsp+34h] [rbp-CCh] BYREF
  ULONG PropertyBufferSize; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR PropertyBuffer[200]; // [rsp+40h] [rbp-C0h] BYREF

  memset_0(PropertyBuffer, 0, sizeof(PropertyBuffer));
  PropertyType = 0;
  PropertyBufferSize = 400;
  Device_Interface_PropertyW = CM_Get_Device_Interface_PropertyW(
                                 a2,
                                 &DEVPKEY_Device_InstanceId,
                                 &PropertyType,
                                 (PBYTE)PropertyBuffer,
                                 &PropertyBufferSize,
                                 0);
  if ( Device_Interface_PropertyW || PropertyType != 18 )
  {
    PrintScanBrokerTelemetry::WriteDbgTraceInfo(
      "USBDevice::_DevicePathToCmDeviceId",
      L"CM_Get_Device_Interface_Property failed 0x%x",
      Device_Interface_PropertyW);
    PrintScanBrokerTelemetry::WriteDbgTraceInfo("USBDevice::_GetDevInstFromPath", L"Failed to get DeviceId for %ws", a2);
  }
  else
  {
    pdnDevInst = 0;
    v4 = CM_Locate_DevNodeW(&pdnDevInst, PropertyBuffer, 0);
    if ( !v4 )
      return pdnDevInst;
    PrintScanBrokerTelemetry::WriteDbgTraceInfo(
      "USBDevice::_GetDevInstFromPath",
      L"CM_Locate_DevNode(%ws) failed 0x%x",
      PropertyBuffer,
      v4);
  }
  return 0;
}

```

## disassembly

```asm
0x1800306d8  mov     [rsp-8+arg_0], rbx
0x1800306dd  push    rbp
0x1800306de  lea     rbp, [rsp-0E0h]
0x1800306e6  sub     rsp, 1E0h
0x1800306ed  mov     rax, cs:__security_cookie
0x1800306f4  xor     rax, rsp
0x1800306f7  mov     [rbp+0E0h+var_10], rax
0x1800306fe  mov     rbx, rdx
0x180030701  lea     rcx, [rsp+1E0h+PropertyBuffer]; void *
0x180030706  xor     edx, edx; Val
0x180030708  mov     r8d, 190h; Size
0x18003070e  call    memset_0
0x180030713  lea     rax, [rsp+1E0h+var_1A8]
0x180030718  mov     [rsp+1E0h+ulFlags], 0; ulFlags
0x180030720  lea     r9, [rsp+1E0h+PropertyBuffer]; PropertyBuffer
0x180030725  mov     [rsp+1E0h+PropertyBufferSize], rax; PropertyBufferSize
0x18003072a  lea     r8, [rsp+1E0h+PropertyType]; PropertyType
0x18003072f  mov     [rsp+1E0h+PropertyType], 0
0x180030737  lea     rdx, DEVPKEY_Device_InstanceId; PropertyKey
0x18003073e  mov     [rsp+1E0h+var_1A8], 190h
0x180030746  mov     rcx, rbx; pszDeviceInterface
0x180030749  call    cs:__imp_CM_Get_Device_Interface_PropertyW
0x18003074f  test    eax, eax
0x180030751  jnz     short loc_180030798
0x180030753  cmp     [rsp+1E0h+PropertyType], 12h
0x180030758  jnz     short loc_180030798
0x18003075a  xor     r8d, r8d; ulFlags
0x18003075d  mov     [rsp+1E0h+pdnDevInst], eax
0x180030761  lea     rdx, [rsp+1E0h+PropertyBuffer]; pDeviceID
0x180030766  lea     rcx, [rsp+1E0h+pdnDevInst]; pdnDevInst
0x18003076b  call    cs:__imp_CM_Locate_DevNodeW
0x180030771  test    eax, eax
0x180030773  jz      short loc_180030792
0x180030775  mov     r9d, eax
0x180030778  lea     r8, [rsp+1E0h+PropertyBuffer]
0x18003077d  lea     rdx, aCmLocateDevnod; "CM_Locate_DevNode(%ws) failed 0x%x"
0x180030784  lea     rcx, aUsbdeviceGetde; "USBDevice::_GetDevInstFromPath"
0x18003078b  call    ?WriteDbgTraceInfo@PrintScanBrokerTelemetry@@SAXPEADPEAGZZ; PrintScanBrokerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180030790  jmp     short loc_1800307C4
0x180030792  mov     eax, [rsp+1E0h+pdnDevInst]
0x180030796  jmp     short loc_1800307C6
0x180030798  mov     r8d, eax
0x18003079b  lea     rdx, aCmGetDeviceInt; "CM_Get_Device_Interface_Property failed"...
0x1800307a2  lea     rcx, aUsbdeviceDevic; "USBDevice::_DevicePathToCmDeviceId"
0x1800307a9  call    ?WriteDbgTraceInfo@PrintScanBrokerTelemetry@@SAXPEADPEAGZZ; PrintScanBrokerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800307ae  mov     r8, rbx
0x1800307b1  lea     rdx, aFailedToGetDev; "Failed to get DeviceId for %ws"
0x1800307b8  lea     rcx, aUsbdeviceGetde; "USBDevice::_GetDevInstFromPath"
0x1800307bf  call    ?WriteDbgTraceInfo@PrintScanBrokerTelemetry@@SAXPEADPEAGZZ; PrintScanBrokerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800307c4  xor     eax, eax
0x1800307c6  mov     rcx, [rbp+0E0h+var_10]
0x1800307cd  xor     rcx, rsp; StackCookie
0x1800307d0  call    __security_check_cookie
0x1800307d5  mov     rbx, [rsp+1E0h+arg_0]
0x1800307dd  add     rsp, 1E0h
0x1800307e4  pop     rbp
0x1800307e5  retn
```
