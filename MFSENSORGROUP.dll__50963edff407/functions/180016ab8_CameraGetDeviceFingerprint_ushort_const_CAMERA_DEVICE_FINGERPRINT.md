# CameraGetDeviceFingerprint(ushort const *,CAMERA_DEVICE_FINGERPRINT *)

- ea: `0x180016ab8`
- end: `0x180017042`
- name: `?CameraGetDeviceFingerprint@@YAJPEBGPEAUCAMERA_DEVICE_FINGERPRINT@@@Z`
- size: `1418`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct CAMERA_DEVICE_FINGERPRINT *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800169ac`

## callees

- `0x180016ab8`
- `0x18001764c`
- `0x180044f30`
- `0x1800458dc`
- `0x180045900`
- `0x180077010`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x180016fac`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x180016ff0`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x180016fac`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x180016ff0`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180016e61`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180016e61`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180016e7d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180016e7d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180016f55`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180016f55`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x180016f33`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x180016f47`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x180016f33`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x180016f47`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x180016c11`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x180016c93`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x180016c11`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x180016c93`
- `api-ms-win-devices-query-l1-1-0!DevFindProperty` at `0x180016c3c`
- `api-ms-win-devices-query-l1-1-0!DevFindProperty` at `0x180016cc8`
- `api-ms-win-devices-query-l1-1-0!DevFindProperty` at `0x180016ced`
- `api-ms-win-devices-query-l1-1-0!DevFindProperty` at `0x180016d30`
- `api-ms-win-devices-query-l1-1-0!DevFindProperty` at `0x180016d5c`
- `api-ms-win-devices-query-l1-1-0!DevFindProperty` at `0x180016d99`
- `api-ms-win-devices-query-l1-1-0!DevFindProperty` at `0x180016dbe`
- `api-ms-win-devices-query-l1-1-0!DevFindProperty` at `0x180016e08`
- `api-ms-win-devices-query-l1-1-0!DevFindProperty` at `0x180016e2d`
- `api-ms-win-devices-query-l1-1-0!DevFindProperty` at `0x180016c3c`
- `api-ms-win-devices-query-l1-1-0!DevFindProperty` at `0x180016cc8`
- `api-ms-win-devices-query-l1-1-0!DevFindProperty` at `0x180016ced`
- `api-ms-win-devices-query-l1-1-0!DevFindProperty` at `0x180016d30`
- `api-ms-win-devices-query-l1-1-0!DevFindProperty` at `0x180016d5c`
- `api-ms-win-devices-query-l1-1-0!DevFindProperty` at `0x180016d99`
- `api-ms-win-devices-query-l1-1-0!DevFindProperty` at `0x180016dbe`
- `api-ms-win-devices-query-l1-1-0!DevFindProperty` at `0x180016e08`
- `api-ms-win-devices-query-l1-1-0!DevFindProperty` at `0x180016e2d`

## string_xrefs

- `0x180016e54`: `mfsensorgroup.dll`
- `0x180016f12`: `CameraDeviceMftClsid`
- `0x180016e73`: `MFGetSensorDeviceRegistryProperty`
- `0x180016ec5`: `CameraPostProcessingPluginCLSID`

## pseudocode

```c
__int64 __fastcall CameraGetDeviceFingerprint(const unsigned __int16 *a1, struct CAMERA_DEVICE_FINGERPRINT *a2)
{
  HMODULE v4; // rbx
  int ObjectProperties; // esi
  __int64 Property; // rax
  __int64 v7; // rbx
  unsigned int v8; // r14d
  __int64 v9; // rax
  __int64 v10; // rbx
  unsigned int v11; // r14d
  __int64 v12; // rax
  __int64 v13; // rbx
  unsigned int v14; // r14d
  __int64 v15; // rax
  __int64 v16; // rbx
  unsigned int v17; // r14d
  __int64 v18; // rax
  _DWORD *v19; // rcx
  HMODULE Library; // rax
  FARPROC ProcAddress; // r14
  int v23; // eax
  int v24; // eax
  __int64 v25; // rcx
  unsigned int v26; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v27; // [rsp+44h] [rbp-BCh] BYREF
  unsigned int v28; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v29; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v30; // [rsp+58h] [rbp-A8h] BYREF
  DEVPROPKEY v31; // [rsp+60h] [rbp-A0h] BYREF
  int v32; // [rsp+74h] [rbp-8Ch]
  __int64 v33; // [rsp+78h] [rbp-88h]
  DEVPROPKEY v34; // [rsp+80h] [rbp-80h]
  int v35; // [rsp+94h] [rbp-6Ch]
  __int64 v36; // [rsp+98h] [rbp-68h]
  DEVPROPKEY v37; // [rsp+A0h] [rbp-60h]
  int v38; // [rsp+B4h] [rbp-4Ch]
  __int64 v39; // [rsp+B8h] [rbp-48h]
  DEVPROPKEY v40; // [rsp+C0h] [rbp-40h]
  int v41; // [rsp+D4h] [rbp-2Ch]
  __int64 v42; // [rsp+D8h] [rbp-28h]
  DEVPROPKEY v43; // [rsp+E0h] [rbp-20h]
  int v44; // [rsp+F4h] [rbp-Ch]
  __int64 v45; // [rsp+F8h] [rbp-8h]
  wchar_t Source[40]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v47[528]; // [rsp+150h] [rbp+50h] BYREF

  v26 = 0;
  v29 = 0;
  v28 = 0;
  v30 = 0;
  memset_0(Source, 0, 0x4Eu);
  v27 = 0;
  memset_0(v47, 0, 0x208u);
  v31 = DEVPKEY_Device_InLocalMachineContainer;
  v34 = DEVPKEY_Device_PhysicalDeviceLocation;
  v37 = DEVPKEY_Device_DriverVersion;
  v40 = DEVPKEY_Device_DriverDate;
  v32 = 0;
  v33 = 0;
  v35 = 0;
  v36 = 0;
  v38 = 0;
  v39 = 0;
  v41 = 0;
  v42 = 0;
  v43 = DEVPKEY_Device_InstanceId;
  v44 = 0;
  v45 = 0;
  if ( a1 && a2 )
  {
    v4 = 0;
    memset_0(a2, 0, 0x108u);
    ObjectProperties = DevGetObjectProperties(1, a1, 0, 5, &v31, &v26, &v29);
    if ( ObjectProperties >= 0 )
    {
      Property = DevFindProperty(&DEVPKEY_Device_InstanceId, 0, 0, v26, v29);
      if ( !Property
        || *(_DWORD *)(Property + 32) != 18
        || (o_wcsncpy_s_0(v47, 260, *(_QWORD *)(Property + 40), -1),
            ObjectProperties = DevGetObjectProperties(3, v47, 0, 5, &v31, &v28, &v30),
            ObjectProperties >= 0) )
      {
        v7 = v30;
        v8 = v28;
        v9 = DevFindProperty(&DEVPKEY_Device_InLocalMachineContainer, 0, 0, v26, v29);
        if ( v9 && *(_DWORD *)(v9 + 32) == 17
          || (v9 = DevFindProperty(&DEVPKEY_Device_InLocalMachineContainer, 0, 0, v8, v7)) != 0
          && *(_DWORD *)(v9 + 32) == 17 )
        {
          *((_BYTE *)a2 + 72) = **(_BYTE **)(v9 + 40) == 0xFF;
        }
        v10 = v30;
        v11 = v28;
        v12 = DevFindProperty(&DEVPKEY_Device_PhysicalDeviceLocation, 0, 0, v26, v29);
        if ( v12 && *(_DWORD *)(v12 + 32) == 4099
          || (v12 = DevFindProperty(&DEVPKEY_Device_PhysicalDeviceLocation, 0, 0, v11, v10)) != 0
          && *(_DWORD *)(v12 + 32) == 4099 )
        {
          v25 = *(_QWORD *)(v12 + 40);
          if ( v25 )
          {
            *((_DWORD *)a2 + 19) = (*(_DWORD *)(v25 + 8) >> 3) & 7;
            *((_DWORD *)a2 + 20) = (*(_DWORD *)(v25 + 12) >> 19) & 0xF;
          }
        }
        v13 = v30;
        v14 = v28;
        v15 = DevFindProperty(&DEVPKEY_Device_DriverVersion, 0, 0, v26, v29);
        if ( v15 && *(_DWORD *)(v15 + 32) == 18
          || (v15 = DevFindProperty(&DEVPKEY_Device_DriverVersion, 0, 0, v14, v13)) != 0 && *(_DWORD *)(v15 + 32) == 18 )
        {
          o_wcsncpy_s_0(a2, 32, *(_QWORD *)(v15 + 40), -1);
        }
        v16 = v30;
        v17 = v28;
        v18 = DevFindProperty(&DEVPKEY_Device_DriverDate, 0, 0, v26, v29);
        if ( v18 && *(_DWORD *)(v18 + 32) == 16
          || (v18 = DevFindProperty(&DEVPKEY_Device_DriverDate, 0, 0, v17, v16)) != 0 && *(_DWORD *)(v18 + 32) == 16 )
        {
          v19 = *(_DWORD **)(v18 + 40);
          if ( v19 )
          {
            *((_DWORD *)a2 + 16) = *v19;
            *((_DWORD *)a2 + 17) = v19[1];
          }
        }
        Library = LoadLibraryExW(L"mfsensorgroup.dll", 0, 0x800u);
        v4 = Library;
        if ( Library )
        {
          ProcAddress = GetProcAddress(Library, "MFGetSensorDeviceRegistryProperty");
          if ( ProcAddress )
          {
            v27 = 0;
            memset_0(Source, 0, 0x4Eu);
            if ( ((int (__fastcall *)(const unsigned __int16 *, const WCHAR *, __int64, wchar_t *, int, unsigned int *))ProcAddress)(
                   a1,
                   L"CameraPostProcessingPluginCLSID",
                   1,
                   Source,
                   78,
                   &v27) >= 0
              && v27 > 2 )
            {
              o_wcsncpy_s_0((char *)a2 + 84, 39, Source, -1);
              v24 = wcsnlen(Source, 0x27u);
              CameraGenerateDWORD64Hash((PUCHAR)Source, 2 * v24, (unsigned __int64 *)a2 + 21);
            }
            v27 = 0;
            memset_0(Source, 0, 0x4Eu);
            if ( ((int (__fastcall *)(const unsigned __int16 *, const WCHAR *, __int64, wchar_t *, int, unsigned int *))ProcAddress)(
                   a1,
                   L"CameraDeviceMftClsid",
                   1,
                   Source,
                   78,
                   &v27) >= 0
              && v27 > 2 )
            {
              o_wcsncpy_s_0((char *)a2 + 176, 39, Source, -1);
              v23 = wcsnlen(Source, 0x27u);
              CameraGenerateDWORD64Hash((PUCHAR)Source, 2 * v23, (unsigned __int64 *)a2 + 32);
            }
          }
        }
      }
    }
    if ( v29 )
      DevFreeObjectProperties(v26);
    if ( v30 )
      DevFreeObjectProperties(v28);
    if ( v4 )
      FreeLibrary(v4);
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)ObjectProperties;
}

```

## disassembly

```asm
0x180016ab8  mov     [rsp-8+arg_10], rbx
0x180016abd  push    rbp
0x180016abe  push    rsi
0x180016abf  push    rdi
0x180016ac0  push    r12
0x180016ac2  push    r13
0x180016ac4  push    r14
0x180016ac6  push    r15
0x180016ac8  lea     rbp, [rsp-270h]
0x180016ad0  sub     rsp, 370h
0x180016ad7  mov     rax, cs:__security_cookie
0x180016ade  xor     rax, rsp
0x180016ae1  mov     [rbp+2A0h+var_40], rax
0x180016ae8  xor     r12d, r12d
0x180016aeb  mov     rdi, rdx
0x180016aee  mov     r15, rcx
0x180016af1  mov     [rsp+3A0h+var_360], r12d
0x180016af6  xor     edx, edx; Val
0x180016af8  mov     [rsp+3A0h+var_350], r12
0x180016afd  lea     rcx, [rbp+2A0h+Source]; void *
0x180016b01  mov     [rsp+3A0h+var_358], r12d
0x180016b06  lea     r8d, [r12+4Eh]; Size
0x180016b0b  mov     [rsp+3A0h+var_348], r12
0x180016b10  call    memset_0
0x180016b15  xor     edx, edx; Val
0x180016b17  mov     [rsp+3A0h+var_35C], r12d
0x180016b1c  mov     r8d, 208h; Size
0x180016b22  lea     rcx, [rbp+2A0h+var_250]; void *
0x180016b26  call    memset_0
0x180016b2b  mov     eax, cs:DEVPKEY_Device_InLocalMachineContainer.pid
0x180016b31  mov     [rsp+3A0h+var_330], eax
0x180016b35  mov     eax, cs:DEVPKEY_Device_PhysicalDeviceLocation.pid
0x180016b3b  mov     [rbp+2A0h+var_310], eax
0x180016b3e  mov     eax, cs:DEVPKEY_Device_DriverVersion.pid
0x180016b44  mov     [rbp+2A0h+var_2F0], eax
0x180016b47  mov     eax, cs:DEVPKEY_Device_DriverDate.pid
0x180016b4d  mov     [rbp+2A0h+var_2D0], eax
0x180016b50  mov     eax, cs:DEVPKEY_Device_InstanceId.pid
0x180016b56  mov     [rsp+3A0h+var_32C], r12d
0x180016b5b  mov     [rsp+3A0h+var_328], r12
0x180016b60  mov     [rbp+2A0h+var_30C], r12d
0x180016b64  mov     [rbp+2A0h+var_308], r12
0x180016b68  mov     [rbp+2A0h+var_2EC], r12d
0x180016b6c  mov     [rbp+2A0h+var_2E8], r12
0x180016b70  mov     [rbp+2A0h+var_2CC], r12d
0x180016b74  mov     [rbp+2A0h+var_2C8], r12
0x180016b78  mov     [rbp+2A0h+var_2B0], eax
0x180016b7b  mov     [rbp+2A0h+var_2AC], r12d
0x180016b7f  mov     [rbp+2A0h+var_2A8], r12
0x180016b83  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_InLocalMachineContainer.fmtid.Data1
0x180016b8a  movaps  [rsp+3A0h+var_340], xmm0
0x180016b8f  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_PhysicalDeviceLocation.fmtid.Data1
0x180016b96  movaps  [rbp+2A0h+var_320], xmm0
0x180016b9a  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_DriverVersion.fmtid.Data1
0x180016ba1  movaps  [rbp+2A0h+var_300], xmm0
0x180016ba5  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_DriverDate.fmtid.Data1
0x180016bac  movaps  [rbp+2A0h+var_2E0], xmm0
0x180016bb0  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_InstanceId.fmtid.Data1
0x180016bb7  movaps  [rbp+2A0h+var_2C0], xmm0
0x180016bbb  test    r15, r15
0x180016bbe  jz      loc_180017038
0x180016bc4  test    rdi, rdi
0x180016bc7  jz      loc_180017038
0x180016bcd  xor     edx, edx; Val
0x180016bcf  mov     r8d, 108h; Size
0x180016bd5  mov     rcx, rdi; void *
0x180016bd8  mov     ebx, r12d
0x180016bdb  call    memset_0
0x180016be0  lea     rax, [rsp+3A0h+var_350]
0x180016be5  xor     r8d, r8d
0x180016be8  mov     [rsp+3A0h+var_370], rax
0x180016bed  lea     r14d, [r12+5]
0x180016bf2  lea     rax, [rsp+3A0h+var_360]
0x180016bf7  mov     r9d, r14d
0x180016bfa  mov     [rsp+3A0h+var_378], rax
0x180016bff  lea     ecx, [r12+1]
0x180016c04  lea     rax, [rsp+3A0h+var_340]
0x180016c09  mov     rdx, r15
0x180016c0c  mov     [rsp+3A0h+var_380], rax
0x180016c11  call    cs:__imp_DevGetObjectProperties
0x180016c17  mov     esi, eax
0x180016c19  test    eax, eax
0x180016c1b  js      loc_180016F25
0x180016c21  mov     rcx, [rsp+3A0h+var_350]
0x180016c26  xor     r8d, r8d
0x180016c29  mov     r9d, [rsp+3A0h+var_360]
0x180016c2e  xor     edx, edx
0x180016c30  mov     [rsp+3A0h+var_380], rcx
0x180016c35  lea     rcx, DEVPKEY_Device_InstanceId
0x180016c3c  call    cs:__imp_DevFindProperty
0x180016c42  or      r13, 0FFFFFFFFFFFFFFFFh
0x180016c46  test    rax, rax
0x180016c49  jz      short loc_180016CA3
0x180016c4b  cmp     dword ptr [rax+20h], 12h
0x180016c4f  jnz     short loc_180016CA3
0x180016c51  mov     r8, [rax+28h]
0x180016c55  lea     rcx, [rbp+2A0h+var_250]
0x180016c59  mov     r9, r13
0x180016c5c  mov     edx, 104h
0x180016c61  call    _o_wcsncpy_s_0
0x180016c66  lea     rax, [rsp+3A0h+var_348]
0x180016c6b  mov     r9d, r14d
0x180016c6e  mov     [rsp+3A0h+var_370], rax
0x180016c73  lea     rdx, [rbp+2A0h+var_250]
0x180016c77  lea     rax, [rsp+3A0h+var_358]
0x180016c7c  xor     r8d, r8d
0x180016c7f  mov     [rsp+3A0h+var_378], rax
0x180016c84  lea     ecx, [r12+3]
0x180016c89  lea     rax, [rsp+3A0h+var_340]
0x180016c8e  mov     [rsp+3A0h+var_380], rax
0x180016c93  call    cs:__imp_DevGetObjectProperties
0x180016c99  mov     esi, eax
0x180016c9b  test    eax, eax
0x180016c9d  js      loc_180016F25
0x180016ca3  mov     rax, [rsp+3A0h+var_350]
0x180016ca8  lea     rcx, DEVPKEY_Device_InLocalMachineContainer
0x180016caf  mov     r9d, [rsp+3A0h+var_360]
0x180016cb4  xor     r8d, r8d
0x180016cb7  mov     rbx, [rsp+3A0h+var_348]
0x180016cbc  xor     edx, edx
0x180016cbe  mov     r14d, [rsp+3A0h+var_358]
0x180016cc3  mov     [rsp+3A0h+var_380], rax
0x180016cc8  call    cs:__imp_DevFindProperty
0x180016cce  test    rax, rax
0x180016cd1  jz      short loc_180016CD9
0x180016cd3  cmp     dword ptr [rax+20h], 11h
0x180016cd7  jz      short loc_180016CFE
0x180016cd9  mov     r9d, r14d
0x180016cdc  mov     [rsp+3A0h+var_380], rbx
0x180016ce1  xor     r8d, r8d
0x180016ce4  lea     rcx, DEVPKEY_Device_InLocalMachineContainer
0x180016ceb  xor     edx, edx
0x180016ced  call    cs:__imp_DevFindProperty
0x180016cf3  test    rax, rax
0x180016cf6  jz      short loc_180016D0B
0x180016cf8  cmp     dword ptr [rax+20h], 11h
0x180016cfc  jnz     short loc_180016D0B
0x180016cfe  mov     rax, [rax+28h]
0x180016d02  cmp     [rax], r13b
0x180016d05  setz    al
0x180016d08  mov     [rdi+48h], al
0x180016d0b  mov     rax, [rsp+3A0h+var_350]
0x180016d10  lea     rcx, DEVPKEY_Device_PhysicalDeviceLocation
0x180016d17  mov     r9d, [rsp+3A0h+var_360]
0x180016d1c  xor     r8d, r8d
0x180016d1f  mov     rbx, [rsp+3A0h+var_348]
0x180016d24  xor     edx, edx
0x180016d26  mov     r14d, [rsp+3A0h+var_358]
0x180016d2b  mov     [rsp+3A0h+var_380], rax
0x180016d30  call    cs:__imp_DevFindProperty
0x180016d36  test    rax, rax
0x180016d39  jz      short loc_180016D48
0x180016d3b  cmp     dword ptr [rax+20h], 1003h
0x180016d42  jz      loc_18001700E
0x180016d48  mov     r9d, r14d
0x180016d4b  mov     [rsp+3A0h+var_380], rbx
0x180016d50  xor     r8d, r8d
0x180016d53  lea     rcx, DEVPKEY_Device_PhysicalDeviceLocation
0x180016d5a  xor     edx, edx
0x180016d5c  call    cs:__imp_DevFindProperty
0x180016d62  test    rax, rax
0x180016d65  jz      short loc_180016D74
0x180016d67  cmp     dword ptr [rax+20h], 1003h
0x180016d6e  jz      loc_18001700E
0x180016d74  mov     rax, [rsp+3A0h+var_350]
0x180016d79  lea     rcx, DEVPKEY_Device_DriverVersion
0x180016d80  mov     r9d, [rsp+3A0h+var_360]
0x180016d85  xor     r8d, r8d
0x180016d88  mov     rbx, [rsp+3A0h+var_348]
0x180016d8d  xor     edx, edx
0x180016d8f  mov     r14d, [rsp+3A0h+var_358]
0x180016d94  mov     [rsp+3A0h+var_380], rax
0x180016d99  call    cs:__imp_DevFindProperty
0x180016d9f  test    rax, rax
0x180016da2  jz      short loc_180016DAA
0x180016da4  cmp     dword ptr [rax+20h], 12h
0x180016da8  jz      short loc_180016DCF
0x180016daa  mov     r9d, r14d
0x180016dad  mov     [rsp+3A0h+var_380], rbx
0x180016db2  xor     r8d, r8d
0x180016db5  lea     rcx, DEVPKEY_Device_DriverVersion
0x180016dbc  xor     edx, edx
0x180016dbe  call    cs:__imp_DevFindProperty
0x180016dc4  test    rax, rax
0x180016dc7  jz      short loc_180016DE3
0x180016dc9  cmp     dword ptr [rax+20h], 12h
0x180016dcd  jnz     short loc_180016DE3
0x180016dcf  mov     r8, [rax+28h]
0x180016dd3  mov     r9, r13
0x180016dd6  mov     edx, 20h ; ' '
0x180016ddb  mov     rcx, rdi
0x180016dde  call    _o_wcsncpy_s_0
0x180016de3  mov     rax, [rsp+3A0h+var_350]
0x180016de8  lea     rcx, DEVPKEY_Device_DriverDate
0x180016def  mov     r9d, [rsp+3A0h+var_360]
0x180016df4  xor     r8d, r8d
0x180016df7  mov     rbx, [rsp+3A0h+var_348]
0x180016dfc  xor     edx, edx
0x180016dfe  mov     r14d, [rsp+3A0h+var_358]
0x180016e03  mov     [rsp+3A0h+var_380], rax
0x180016e08  call    cs:__imp_DevFindProperty
0x180016e0e  test    rax, rax
0x180016e11  jz      short loc_180016E19
0x180016e13  cmp     dword ptr [rax+20h], 10h
0x180016e17  jz      short loc_180016E3E
0x180016e19  mov     r9d, r14d
0x180016e1c  mov     [rsp+3A0h+var_380], rbx
0x180016e21  xor     r8d, r8d
0x180016e24  lea     rcx, DEVPKEY_Device_DriverDate
0x180016e2b  xor     edx, edx
0x180016e2d  call    cs:__imp_DevFindProperty
0x180016e33  test    rax, rax
0x180016e36  jz      short loc_180016E52
0x180016e38  cmp     dword ptr [rax+20h], 10h
0x180016e3c  jnz     short loc_180016E52
0x180016e3e  mov     rcx, [rax+28h]
0x180016e42  test    rcx, rcx
0x180016e45  jz      short loc_180016E52
0x180016e47  mov     eax, [rcx]
0x180016e49  mov     [rdi+40h], eax
0x180016e4c  mov     eax, [rcx+4]
0x180016e4f  mov     [rdi+44h], eax
0x180016e52  xor     edx, edx; hFile
0x180016e54  lea     rcx, LibFileName; "mfsensorgroup.dll"
0x180016e5b  mov     r8d, 800h; dwFlags
0x180016e61  call    cs:__imp_LoadLibraryExW
0x180016e67  mov     rbx, rax
0x180016e6a  test    rax, rax
0x180016e6d  jz      loc_180016F25
0x180016e73  lea     rdx, aMfgetsensordev_1; "MFGetSensorDeviceRegistryProperty"
0x180016e7a  mov     rcx, rax; hModule
0x180016e7d  call    cs:__imp_GetProcAddress
0x180016e83  mov     r14, rax
0x180016e86  test    rax, rax
0x180016e89  jz      loc_180016F25
0x180016e8f  mov     r13d, 4Eh ; 'N'
0x180016e95  mov     [rsp+3A0h+var_35C], r12d
0x180016e9a  mov     r8d, r13d; Size
0x180016e9d  lea     rcx, [rbp+2A0h+Source]; void *
0x180016ea1  xor     edx, edx; Val
0x180016ea3  call    memset_0
0x180016ea8  lea     rax, [rsp+3A0h+var_35C]
0x180016ead  mov     rcx, r15
0x180016eb0  mov     [rsp+3A0h+var_378], rax
0x180016eb5  lea     r9, [rbp+2A0h+Source]
0x180016eb9  mov     rax, r14
0x180016ebc  mov     dword ptr [rsp+3A0h+var_380], r13d
0x180016ec1  lea     r8d, [r13-4Dh]
0x180016ec5  lea     rdx, aCamerapostproc; "CameraPostProcessingPluginCLSID"
0x180016ecc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016ed1  mov     r13d, 27h ; '''
0x180016ed7  test    eax, eax
0x180016ed9  jns     loc_180016FCA
0x180016edf  xor     edx, edx; Val
0x180016ee1  mov     [rsp+3A0h+var_35C], r12d
0x180016ee6  lea     rcx, [rbp+2A0h+Source]; void *
0x180016eea  lea     r8d, [rdx+4Eh]; Size
0x180016eee  call    memset_0
0x180016ef3  lea     rax, [rsp+3A0h+var_35C]
0x180016ef8  mov     r8d, 1
0x180016efe  mov     [rsp+3A0h+var_378], rax
0x180016f03  lea     r9, [rbp+2A0h+Source]
0x180016f07  mov     rax, r14
0x180016f0a  mov     dword ptr [rsp+3A0h+var_380], 4Eh ; 'N'
0x180016f12  lea     rdx, aCameradevicemf_0; "CameraDeviceMftClsid"
0x180016f19  mov     rcx, r15
0x180016f1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016f21  test    eax, eax
0x180016f23  jns     short loc_180016F87
0x180016f25  mov     rdx, [rsp+3A0h+var_350]
0x180016f2a  test    rdx, rdx
0x180016f2d  jz      short loc_180016F39
0x180016f2f  mov     ecx, [rsp+3A0h+var_360]
0x180016f33  call    cs:__imp_DevFreeObjectProperties
0x180016f39  mov     rdx, [rsp+3A0h+var_348]
0x180016f3e  test    rdx, rdx
0x180016f41  jz      short loc_180016F4D
0x180016f43  mov     ecx, [rsp+3A0h+var_358]
0x180016f47  call    cs:__imp_DevFreeObjectProperties
0x180016f4d  test    rbx, rbx
0x180016f50  jz      short loc_180016F5B
0x180016f52  mov     rcx, rbx; hLibModule
0x180016f55  call    cs:__imp_FreeLibrary
0x180016f5b  mov     eax, esi
0x180016f5d  mov     rcx, [rbp+2A0h+var_40]
0x180016f64  xor     rcx, rsp; StackCookie
0x180016f67  call    __security_check_cookie
0x180016f6c  mov     rbx, [rsp+3A0h+arg_10]
0x180016f74  add     rsp, 370h
0x180016f7b  pop     r15
0x180016f7d  pop     r14
0x180016f7f  pop     r13
0x180016f81  pop     r12
0x180016f83  pop     rdi
0x180016f84  pop     rsi
0x180016f85  pop     rbp
0x180016f86  retn
0x180016f87  cmp     [rsp+3A0h+var_35C], 2
0x180016f8c  jbe     short loc_180016F25
0x180016f8e  lea     rcx, [rdi+0B0h]
  ... truncated ...
```
