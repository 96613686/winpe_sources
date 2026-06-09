# winreStoreSystemDiskPathInNVRAM

- ea: `0x18003cf28`
- end: `0x18003d7e1`
- name: `winreStoreSystemDiskPathInNVRAM`
- size: `2233`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800193e8`

## callees

- `0x1800059fc`
- `0x180006ed8`
- `0x180036b14`
- `0x180036b28`
- `0x180037e7c`
- `0x18003cf28`
- `0x18005cee2`
- `0x18005cf30`
- `0x18005f010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18003d60d`
- `msvcrt!_wcsicmp` at `0x18003d60d`
- `ntdll!RtlAdjustPrivilege` at `0x18003d542`
- `ntdll!RtlAdjustPrivilege` at `0x18003d64c`
- `ntdll!RtlAdjustPrivilege` at `0x18003d542`
- `ntdll!RtlAdjustPrivilege` at `0x18003d64c`
- `KERNEL32!GetLastError` at `0x18003d4fb`
- `KERNEL32!GetLastError` at `0x18003d586`
- `KERNEL32!GetLastError` at `0x18003d593`
- `KERNEL32!GetLastError` at `0x18003d5cc`
- `KERNEL32!GetLastError` at `0x18003d4fb`
- `KERNEL32!GetLastError` at `0x18003d586`
- `KERNEL32!GetLastError` at `0x18003d593`
- `KERNEL32!GetLastError` at `0x18003d5cc`
- `KERNEL32!GetFirmwareEnvironmentVariableW` at `0x18003d57c`
- `KERNEL32!GetFirmwareEnvironmentVariableW` at `0x18003d57c`
- `KERNEL32!SetFirmwareEnvironmentVariableW` at `0x18003d5c2`
- `KERNEL32!SetFirmwareEnvironmentVariableW` at `0x18003d5c2`
- `RPCRT4!UuidCompare` at `0x18003d5f8`
- `RPCRT4!UuidCompare` at `0x18003d5f8`
- `ole32!CoCreateInstance` at `0x18003d077`
- `ole32!CoCreateInstance` at `0x18003d077`
- `ole32!CoUninitialize` at `0x18003d74e`
- `ole32!CoUninitialize` at `0x18003d74e`
- `ole32!CoTaskMemFree` at `0x18003d36e`
- `ole32!CoTaskMemFree` at `0x18003d381`
- `ole32!CoTaskMemFree` at `0x18003d394`
- `ole32!CoTaskMemFree` at `0x18003d3a7`
- `ole32!CoTaskMemFree` at `0x18003d3ba`
- `ole32!CoTaskMemFree` at `0x18003d3cd`
- `ole32!CoTaskMemFree` at `0x18003d67d`
- `ole32!CoTaskMemFree` at `0x18003d690`
- `ole32!CoTaskMemFree` at `0x18003d6a3`
- `ole32!CoTaskMemFree` at `0x18003d6b6`
- `ole32!CoTaskMemFree` at `0x18003d6c9`
- `ole32!CoTaskMemFree` at `0x18003d6dc`
- `ole32!CoTaskMemFree` at `0x18003d36e`
- `ole32!CoTaskMemFree` at `0x18003d381`
- `ole32!CoTaskMemFree` at `0x18003d394`
- `ole32!CoTaskMemFree` at `0x18003d3a7`
- `ole32!CoTaskMemFree` at `0x18003d3ba`
- `ole32!CoTaskMemFree` at `0x18003d3cd`
- `ole32!CoTaskMemFree` at `0x18003d67d`
- `ole32!CoTaskMemFree` at `0x18003d690`
- `ole32!CoTaskMemFree` at `0x18003d6a3`
- `ole32!CoTaskMemFree` at `0x18003d6b6`
- `ole32!CoTaskMemFree` at `0x18003d6c9`
- `ole32!CoTaskMemFree` at `0x18003d6dc`
- `ole32!CoInitializeEx` at `0x18003d016`
- `ole32!CoInitializeEx` at `0x18003d016`
- `ole32!StringFromGUID2` at `0x18003d4f1`
- `ole32!StringFromGUID2` at `0x18003d4f1`

## string_xrefs

- `0x18003d081`: `CoCreateInstance error hr = 0x%x`
- `0x18003d0b5`: `LoadService error hr = 0x%x`
- `0x18003d0d5`: `WaitForServiceReady error hr = 0x%x`
- `0x18003d31d`: `Location path not found (might be mmc bus)`
- `0x18003d437`: `StringCchCopyW error hr = 0x%x`
- `0x18003d552`: `RtlAdjustPrivilege(SE_SYSTEM_ENVIRONMENT_PRIVILEGE) error = 0x%x`
- `0x18003d659`: `RtlAdjustPrivilege(SE_SYSTEM_ENVIRONMENT_PRIVILEGE) error = 0x%x`
- `0x18003d575`: `PBRDevicePath`
- `0x18003d5bb`: `PBRDevicePath`
- `0x18003d617`: `NVRAM update not necessary`
- `0x18003d62a`: `NVRAM update successful`

## pseudocode

```c
__int64 winreStoreSystemDiskPathInNVRAM()
{
  unsigned int v0; // edi
  unsigned int v1; // eax
  unsigned int v2; // esi
  RPC_STATUS v3; // eax
  const wchar_t *v4; // rdx
  int v5; // ebx
  int v6; // ebx
  DWORD LastError; // eax
  RPC_STATUS v8; // eax
  DWORD v9; // eax
  DWORD v10; // eax
  int v12; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v13[28]; // [rsp+34h] [rbp-CCh] BYREF
  unsigned int v14; // [rsp+50h] [rbp-B0h]
  unsigned int v15; // [rsp+54h] [rbp-ACh]
  unsigned int v16; // [rsp+6Ch] [rbp-94h]
  unsigned int v17; // [rsp+70h] [rbp-90h]
  GUID v18; // [rsp+78h] [rbp-88h]
  LPVOID pv; // [rsp+88h] [rbp-78h]
  LPVOID v20; // [rsp+90h] [rbp-70h]
  LPVOID v21; // [rsp+98h] [rbp-68h]
  LPVOID v22; // [rsp+A0h] [rbp-60h]
  LPVOID v23; // [rsp+A8h] [rbp-58h]
  unsigned __int16 *v24; // [rsp+B0h] [rbp-50h]
  unsigned __int8 OldValue[4]; // [rsp+C0h] [rbp-40h] BYREF
  RPC_STATUS Status; // [rsp+C4h] [rbp-3Ch] BYREF
  __int64 v27; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v28; // [rsp+D0h] [rbp-30h] BYREF
  __int64 (__fastcall ***v29)(_QWORD, GUID *, __int64 *); // [rsp+D8h] [rbp-28h] BYREF
  __int64 v30; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v31; // [rsp+E8h] [rbp-18h] BYREF
  __int64 (__fastcall ***v32)(_QWORD, GUID *, __int64 *); // [rsp+F0h] [rbp-10h] BYREF
  __int64 v33; // [rsp+F8h] [rbp-8h] BYREF
  __int64 (__fastcall ***v34)(_QWORD, GUID *, __int64 *); // [rsp+100h] [rbp+0h] BYREF
  __int64 (__fastcall ***v35)(_QWORD, GUID *, _QWORD); // [rsp+108h] [rbp+8h] BYREF
  __int64 v36; // [rsp+110h] [rbp+10h] BYREF
  __int64 v37; // [rsp+118h] [rbp+18h] BYREF
  LPVOID ppv; // [rsp+120h] [rbp+20h] BYREF
  int v39; // [rsp+128h] [rbp+28h] BYREF
  int v40; // [rsp+12Ch] [rbp+2Ch] BYREF
  _DWORD v41[4]; // [rsp+130h] [rbp+30h] BYREF
  wchar_t pValue[260]; // [rsp+140h] [rbp+40h] BYREF
  GUID rguid; // [rsp+348h] [rbp+248h] BYREF
  wchar_t pBuffer[260]; // [rsp+360h] [rbp+260h] BYREF
  UUID Uuid1; // [rsp+568h] [rbp+468h] BYREF
  OLECHAR sz[264]; // [rsp+580h] [rbp+480h] BYREF

  ATL::CComPtr<IVdsDisk3>::CComPtr<IVdsDisk3>(&ppv);
  ATL::CComPtr<IVdsDisk3>::CComPtr<IVdsDisk3>(&v36);
  ATL::CComPtr<IVdsDisk3>::CComPtr<IVdsDisk3>(&v35);
  ATL::CComPtr<IVdsDisk3>::CComPtr<IVdsDisk3>(&v37);
  v39 = 0;
  ATL::CComPtr<IVdsDisk3>::CComPtr<IVdsDisk3>(&v34);
  ATL::CComPtr<IVdsDisk3>::CComPtr<IVdsDisk3>(&v33);
  ATL::CComPtr<IVdsDisk3>::CComPtr<IVdsDisk3>(&v32);
  v40 = 0;
  ATL::CComPtr<IVdsDisk3>::CComPtr<IVdsDisk3>(&v31);
  ATL::CComPtr<IVdsDisk3>::CComPtr<IVdsDisk3>(&v30);
  ATL::CComPtr<IVdsDisk3>::CComPtr<IVdsDisk3>(&v29);
  v41[0] = 0;
  ATL::CComPtr<IVdsDisk3>::CComPtr<IVdsDisk3>(&v28);
  ATL::CComPtr<IVdsDisk3>::CComPtr<IVdsDisk3>(&v27);
  v12 = 0;
  memset_0(v13, 0, 0x84u);
  Status = 0;
  memset_0(pValue, 0, 0x218u);
  memset_0(pBuffer, 0, 0x218u);
  OldValue[0] = 0;
  v0 = 0;
  v1 = CoInitializeEx(0, 0);
  v2 = v1;
  if ( v1 )
  {
    UnattendLogW(2, L"CoInitialize returned hr=0x%x", v1);
    if ( v2 != 1 && v2 != -2147417850 )
    {
      UnattendLogW(1, L"Not continuing due to CoInitialize error");
      goto LABEL_84;
    }
  }
  v3 = CoCreateInstance(&CLSID_VdsLoader, 0, 4u, &IID_IVdsServiceLoader, &ppv);
  if ( v3 < 0 )
  {
    v4 = L"CoCreateInstance error hr = 0x%x";
LABEL_83:
    UnattendLogW(1, v4, (unsigned int)v3);
    goto LABEL_84;
  }
  v5 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, __int64 *))(*(_QWORD *)ppv + 24LL))(ppv, 0, &v36);
  ATL::CComPtrBase<IVdsServiceLoader>::Release(&ppv);
  if ( v5 < 0 )
  {
    UnattendLogW(1, L"LoadService error hr = 0x%x", (unsigned int)v5);
    goto LABEL_84;
  }
  v3 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v36 + 32LL))(v36);
  if ( v3 < 0 )
  {
    v4 = L"WaitForServiceReady error hr = 0x%x";
    goto LABEL_83;
  }
  v3 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v36 + 48LL))(v36, 1, &v37);
  if ( v3 < 0 )
  {
    v4 = L"QueryProviders error hr = 0x%x";
    goto LABEL_83;
  }
  v6 = 0;
  while ( 1 )
  {
    v3 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 (__fastcall ****)(_QWORD, GUID *, _QWORD), int *))(*(_QWORD *)v37 + 24LL))(
           v37,
           1,
           &v35,
           &v39);
    if ( v3 < 0 )
    {
      v4 = L"pEnum->Next error hr = 0x%x";
      goto LABEL_83;
    }
    if ( v3 == 1 )
      break;
    v3 = (**v35)(v35, &IID_IVdsProvider, &v34);
    if ( v3 < 0 )
    {
      v4 = L"QueryInterface(IID_IVdsProvider) error hr = 0x%x";
      goto LABEL_83;
    }
    v3 = (**v34)(v34, &IID_IVdsSwProvider, &v33);
    if ( v3 < 0 )
    {
      v4 = L"QueryInterface(IID_IVdsSwProvider) error hr = 0x%x";
      goto LABEL_83;
    }
    v3 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v33 + 24LL))(v33, &v31);
    if ( v3 < 0 )
    {
      v4 = L"QueryPacks error hr = 0x%x";
      goto LABEL_83;
    }
LABEL_20:
    v3 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *), int *))(*(_QWORD *)v31 + 24LL))(
           v31,
           1,
           &v32,
           &v40);
    if ( v3 < 0 )
    {
      v4 = L"pEnumPack->Next error hr = 0x%x";
      goto LABEL_83;
    }
    if ( v3 != 1 )
    {
      v3 = (**v32)(v32, &IID_IVdsPack, &v30);
      if ( v3 < 0 )
      {
        v4 = L"QueryInterface(IID_IVdsPack) error hr = 0x%x";
      }
      else
      {
        v3 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v30 + 48LL))(v30, &v27);
        if ( v3 < 0 )
        {
          v4 = L"QueryDisks error hr = 0x%x";
        }
        else
        {
          while ( 1 )
          {
            v3 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *), _DWORD *))(*(_QWORD *)v27 + 24LL))(
                   v27,
                   1,
                   &v29,
                   v41);
            if ( v3 < 0 )
              break;
            if ( v3 == 1 )
            {
              ATL::CComPtrBase<IVdsServiceLoader>::Release(&v27);
              ATL::CComPtrBase<IVdsServiceLoader>::Release(&v30);
              ATL::CComPtrBase<IVdsServiceLoader>::Release(&v32);
              goto LABEL_20;
            }
            v3 = (**v29)(v29, &IID_IVdsDisk3, &v28);
            if ( v3 < 0 )
            {
              v4 = L"QueryInterface(IID_IVdsDisk3) error hr = 0x%x";
              goto LABEL_83;
            }
            memset_0(&v12, 0, 0x88u);
            v3 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v28 + 24LL))(v28, &v12);
            if ( v3 < 0 )
            {
              v4 = L"GetProperties2(IID_IVdsDisk3) error hr = 0x%x";
              goto LABEL_83;
            }
            UnattendLogW(0, L"Find disk : [%s]", v24);
            UnattendLogW(0, L"       BusType : [%u]", v17);
            UnattendLogW(0, L"       ulFlags : [%u]", v16);
            UnattendLogW(0, L"   dwMediaType : [%u]", v15);
            UnattendLogW(0, L"  dwDeviceType : [%u]", v14);
            if ( (v16 & 0x4000) != 0 && (v16 & 0x80u) != 0 && (v16 & 0x100) != 0 && v15 == 12 && v14 == 7 )
            {
              if ( v6 )
              {
                UnattendLogW(1, L"Multiple system disks found");
                goto LABEL_84;
              }
              UnattendLogW(0, L"System disks found");
              if ( v24 )
              {
                v3 = StringCchCopyW(pValue, 0x104u, v24);
                if ( v3 < 0 )
                {
                  v4 = L"StringCchCopyW error hr = 0x%x";
                  goto LABEL_83;
                }
              }
              else
              {
                UnattendLogW(2, L"Location path not found (might be mmc bus)");
                memset_0(pValue, 0, sizeof(pValue));
              }
              v6 = 1;
              rguid = v18;
            }
            if ( pv )
            {
              CoTaskMemFree(pv);
              pv = 0;
            }
            if ( v20 )
            {
              CoTaskMemFree(v20);
              v20 = 0;
            }
            if ( v21 )
            {
              CoTaskMemFree(v21);
              v21 = 0;
            }
            if ( v22 )
            {
              CoTaskMemFree(v22);
              v22 = 0;
            }
            if ( v23 )
            {
              CoTaskMemFree(v23);
              v23 = 0;
            }
            if ( v24 )
            {
              CoTaskMemFree(v24);
              v24 = 0;
            }
            ATL::CComPtrBase<IVdsServiceLoader>::Release(&v28);
            ATL::CComPtrBase<IVdsServiceLoader>::Release(&v29);
          }
          v4 = L"spEnumDisk->Next error hr = 0x%x";
        }
      }
      goto LABEL_83;
    }
    ATL::CComPtrBase<IVdsServiceLoader>::Release(&v31);
    ATL::CComPtrBase<IVdsServiceLoader>::Release(&v33);
    ATL::CComPtrBase<IVdsServiceLoader>::Release(&v34);
    ATL::CComPtrBase<IVdsServiceLoader>::Release(&v35);
  }
  if ( !v6 )
  {
    UnattendLogW(1, L"No system disk found");
    goto LABEL_84;
  }
  UnattendLogW(0, L"System disk : [%s]", pValue);
  if ( !StringFromGUID2(&rguid, sz, 260) )
  {
    LastError = GetLastError();
    UnattendLogW(2, L"StringFromGUID2 failed error = 0x%0x", LastError);
    sz[0] = 0;
  }
  UnattendLogW(0, L"Disk Guid: [%s]", sz);
  v8 = RtlAdjustPrivilege(0x16u, 1u, 0, OldValue);
  Status = v8;
  if ( v8 < 0 )
    UnattendLogW(1, L"RtlAdjustPrivilege(SE_SYSTEM_ENVIRONMENT_PRIVILEGE) error = 0x%x", (unsigned int)v8);
  if ( GetFirmwareEnvironmentVariableW(L"PBRDevicePath", L"{A9B5F8D2-CB6D-42C2-BC01-B5FFAAE4335E}", pBuffer, 0x218u) )
  {
    if ( !UuidCompare(&Uuid1, &rguid, &Status) && !_wcsicmp(pBuffer, pValue) )
    {
      v0 = 1;
      UnattendLogW(0, L"NVRAM update not necessary");
      goto LABEL_79;
    }
  }
  else if ( GetLastError() != 203 )
  {
    v9 = GetLastError();
    UnattendLogW(0, L"GetFirmwareEnvironmentVariableW() = 0x%x ", v9);
  }
  if ( SetFirmwareEnvironmentVariableW(L"PBRDevicePath", L"{A9B5F8D2-CB6D-42C2-BC01-B5FFAAE4335E}", pValue, 0x218u) )
  {
    UnattendLogW(0, L"NVRAM update successful");
    v0 = 1;
  }
  else
  {
    v10 = GetLastError();
    UnattendLogW(1, L"SetFirmwareEnvironmentVariableW() error = 0x%x", v10);
  }
LABEL_79:
  if ( !OldValue[0] )
  {
    v3 = RtlAdjustPrivilege(0x16u, 0, 0, OldValue);
    Status = v3;
    if ( v3 < 0 )
    {
      v4 = L"RtlAdjustPrivilege(SE_SYSTEM_ENVIRONMENT_PRIVILEGE) error = 0x%x";
      goto LABEL_83;
    }
  }
LABEL_84:
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
  if ( v20 )
  {
    CoTaskMemFree(v20);
    v20 = 0;
  }
  if ( v21 )
  {
    CoTaskMemFree(v21);
    v21 = 0;
  }
  if ( v22 )
  {
    CoTaskMemFree(v22);
    v22 = 0;
  }
  if ( v23 )
  {
    CoTaskMemFree(v23);
    v23 = 0;
  }
  if ( v24 )
  {
    CoTaskMemFree(v24);
    v24 = 0;
  }
  ATL::CComPtrBase<IVdsServiceLoader>::Release(&v28);
  ATL::CComPtrBase<IVdsServiceLoader>::Release(&v29);
  ATL::CComPtrBase<IVdsServiceLoader>::Release(&v27);
  ATL::CComPtrBase<IVdsServiceLoader>::Release(&v30);
  ATL::CComPtrBase<IVdsServiceLoader>::Release(&v32);
  ATL::CComPtrBase<IVdsServiceLoader>::Release(&v31);
  ATL::CComPtrBase<IVdsServiceLoader>::Release(&v33);
  ATL::CComPtrBase<IVdsServiceLoader>::Release(&v34);
  ATL::CComPtrBase<IVdsServiceLoader>::Release(&v35);
  ATL::CComPtrBase<IVdsServiceLoader>::Release(&v37);
  ATL::CComPtrBase<IVdsServiceLoader>::Release(&v36);
  if ( v2 <= 1 )
    CoUninitialize();
  ATL::CComPtr<IVdsAdvancedDisk2>::~CComPtr<IVdsAdvancedDisk2>();
  ATL::CComPtr<IVdsAdvancedDisk2>::~CComPtr<IVdsAdvancedDisk2>();
  ATL::CComPtr<IVdsAdvancedDisk2>::~CComPtr<IVdsAdvancedDisk2>();
  ATL::CComPtr<IVdsAdvancedDisk2>::~CComPtr<IVdsAdvancedDisk2>();
  ATL::CComPtr<IVdsAdvancedDisk2>::~CComPtr<IVdsAdvancedDisk2>();
  ATL::CComPtr<IVdsAdvancedDisk2>::~CComPtr<IVdsAdvancedDisk2>();
  ATL::CComPtr<IVdsAdvancedDisk2>::~CComPtr<IVdsAdvancedDisk2>();
  ATL::CComPtr<IVdsAdvancedDisk2>::~CComPtr<IVdsAdvancedDisk2>();
  ATL::CComPtr<IVdsAdvancedDisk2>::~CComPtr<IVdsAdvancedDisk2>();
  ATL::CComPtr<IVdsAdvancedDisk2>::~CComPtr<IVdsAdvancedDisk2>();
  ATL::CComPtr<IVdsAdvancedDisk2>::~CComPtr<IVdsAdvancedDisk2>();
  ATL::CComPtr<IVdsAdvancedDisk2>::~CComPtr<IVdsAdvancedDisk2>();
  return v0;
}

```

## disassembly

```asm
0x18003cf28  push    rbp
0x18003cf2a  push    rbx
0x18003cf2b  push    rsi
0x18003cf2c  push    rdi
0x18003cf2d  push    r14
0x18003cf2f  push    r15
0x18003cf31  lea     rbp, [rsp-6A8h]
0x18003cf39  sub     rsp, 7A8h
0x18003cf40  mov     rax, cs:__security_cookie
0x18003cf47  xor     rax, rsp
0x18003cf4a  mov     [rbp+6D0h+var_40], rax
0x18003cf51  lea     rcx, [rbp+6D0h+var_6B0]
0x18003cf55  call    ??0?$CComPtr@UIVdsDisk3@@@ATL@@QEAA@XZ; ATL::CComPtr<IVdsDisk3>::CComPtr<IVdsDisk3>(void)
0x18003cf5a  lea     rcx, [rbp+6D0h+var_6C0]
0x18003cf5e  call    ??0?$CComPtr@UIVdsDisk3@@@ATL@@QEAA@XZ; ATL::CComPtr<IVdsDisk3>::CComPtr<IVdsDisk3>(void)
0x18003cf63  lea     rcx, [rbp+6D0h+var_6C8]
0x18003cf67  call    ??0?$CComPtr@UIVdsDisk3@@@ATL@@QEAA@XZ; ATL::CComPtr<IVdsDisk3>::CComPtr<IVdsDisk3>(void)
0x18003cf6c  lea     rcx, [rbp+6D0h+var_6B8]
0x18003cf70  call    ??0?$CComPtr@UIVdsDisk3@@@ATL@@QEAA@XZ; ATL::CComPtr<IVdsDisk3>::CComPtr<IVdsDisk3>(void)
0x18003cf75  xor     r14d, r14d
0x18003cf78  lea     rcx, [rbp+6D0h+var_6D0]
0x18003cf7c  mov     [rbp+6D0h+var_6A8], r14d
0x18003cf80  call    ??0?$CComPtr@UIVdsDisk3@@@ATL@@QEAA@XZ; ATL::CComPtr<IVdsDisk3>::CComPtr<IVdsDisk3>(void)
0x18003cf85  lea     rcx, [rbp+6D0h+var_6D8]
0x18003cf89  call    ??0?$CComPtr@UIVdsDisk3@@@ATL@@QEAA@XZ; ATL::CComPtr<IVdsDisk3>::CComPtr<IVdsDisk3>(void)
0x18003cf8e  lea     rcx, [rbp+6D0h+var_6E0]
0x18003cf92  call    ??0?$CComPtr@UIVdsDisk3@@@ATL@@QEAA@XZ; ATL::CComPtr<IVdsDisk3>::CComPtr<IVdsDisk3>(void)
0x18003cf97  lea     rcx, [rbp+6D0h+var_6E8]
0x18003cf9b  mov     [rbp+6D0h+var_6A4], r14d
0x18003cf9f  call    ??0?$CComPtr@UIVdsDisk3@@@ATL@@QEAA@XZ; ATL::CComPtr<IVdsDisk3>::CComPtr<IVdsDisk3>(void)
0x18003cfa4  lea     rcx, [rbp+6D0h+var_6F0]
0x18003cfa8  call    ??0?$CComPtr@UIVdsDisk3@@@ATL@@QEAA@XZ; ATL::CComPtr<IVdsDisk3>::CComPtr<IVdsDisk3>(void)
0x18003cfad  lea     rcx, [rbp+6D0h+var_6F8]
0x18003cfb1  call    ??0?$CComPtr@UIVdsDisk3@@@ATL@@QEAA@XZ; ATL::CComPtr<IVdsDisk3>::CComPtr<IVdsDisk3>(void)
0x18003cfb6  lea     rcx, [rbp+6D0h+var_700]
0x18003cfba  mov     [rbp+6D0h+var_6A0], r14d
0x18003cfbe  call    ??0?$CComPtr@UIVdsDisk3@@@ATL@@QEAA@XZ; ATL::CComPtr<IVdsDisk3>::CComPtr<IVdsDisk3>(void)
0x18003cfc3  lea     rcx, [rbp+6D0h+var_708]
0x18003cfc7  call    ??0?$CComPtr@UIVdsDisk3@@@ATL@@QEAA@XZ; ATL::CComPtr<IVdsDisk3>::CComPtr<IVdsDisk3>(void)
0x18003cfcc  xor     edx, edx; Val
0x18003cfce  mov     [rsp+7D0h+var_7A0], r14d
0x18003cfd3  mov     r8d, 84h; Size
0x18003cfd9  lea     rcx, [rsp+7D0h+var_79C]; void *
0x18003cfde  call    memset_0
0x18003cfe3  mov     ebx, 218h
0x18003cfe8  mov     [rbp+6D0h+Status], r14d
0x18003cfec  mov     r8d, ebx; Size
0x18003cfef  lea     rcx, [rbp+6D0h+pValue]; void *
0x18003cff3  xor     edx, edx; Val
0x18003cff5  call    memset_0
0x18003cffa  mov     r8d, ebx; Size
0x18003cffd  lea     rcx, [rbp+6D0h+pBuffer]; void *
0x18003d004  xor     edx, edx; Val
0x18003d006  call    memset_0
0x18003d00b  xor     edx, edx; dwCoInit
0x18003d00d  mov     [rbp+6D0h+OldValue], r14b
0x18003d011  xor     ecx, ecx; pvReserved
0x18003d013  mov     edi, r14d
0x18003d016  call    cs:__imp_CoInitializeEx
0x18003d01c  lea     r15d, [r14+1]
0x18003d020  mov     esi, eax
0x18003d022  test    eax, eax
0x18003d024  jz      short loc_18003D05A
0x18003d026  mov     r8d, eax
0x18003d029  lea     rdx, aCoinitializeRe; "CoInitialize returned hr=0x%x"
0x18003d030  lea     ecx, [r14+2]
0x18003d034  call    UnattendLogW
0x18003d039  cmp     esi, r15d
0x18003d03c  jz      short loc_18003D05A
0x18003d03e  cmp     esi, 80010106h
0x18003d044  jz      short loc_18003D05A
0x18003d046  lea     rdx, aNotContinuingD; "Not continuing due to CoInitialize erro"...
0x18003d04d  mov     ecx, r15d
0x18003d050  call    UnattendLogW
0x18003d055  jmp     loc_18003D674
0x18003d05a  xor     edx, edx; pUnkOuter
0x18003d05c  lea     rax, [rbp+6D0h+var_6B0]
0x18003d060  lea     r9, IID_IVdsServiceLoader; riid
0x18003d067  mov     [rsp+7D0h+ppv], rax; ppv
0x18003d06c  lea     rcx, CLSID_VdsLoader; rclsid
0x18003d073  lea     r8d, [rdx+4]; dwClsContext
0x18003d077  call    cs:__imp_CoCreateInstance
0x18003d07d  test    eax, eax
0x18003d07f  jns     short loc_18003D08D
0x18003d081  lea     rdx, aCocreateinstan_0; "CoCreateInstance error hr = 0x%x"
0x18003d088  jmp     loc_18003D669
0x18003d08d  mov     rcx, [rbp+6D0h+var_6B0]
0x18003d091  lea     r8, [rbp+6D0h+var_6C0]
0x18003d095  xor     edx, edx
0x18003d097  mov     rax, [rcx]
0x18003d09a  mov     rax, [rax+18h]
0x18003d09e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d0a3  lea     rcx, [rbp+6D0h+var_6B0]
0x18003d0a7  mov     ebx, eax
0x18003d0a9  call    ?Release@?$CComPtrBase@UIVdsServiceLoader@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IVdsServiceLoader>::Release(void)
0x18003d0ae  test    ebx, ebx
0x18003d0b0  jns     short loc_18003D0C1
0x18003d0b2  mov     r8d, ebx
0x18003d0b5  lea     rdx, aLoadserviceErr; "LoadService error hr = 0x%x"
0x18003d0bc  jmp     loc_18003D66C
0x18003d0c1  mov     rcx, [rbp+6D0h+var_6C0]
0x18003d0c5  mov     rax, [rcx]
0x18003d0c8  mov     rax, [rax+20h]
0x18003d0cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d0d1  test    eax, eax
0x18003d0d3  jns     short loc_18003D0E1
0x18003d0d5  lea     rdx, aWaitforservice; "WaitForServiceReady error hr = 0x%x"
0x18003d0dc  jmp     loc_18003D669
0x18003d0e1  mov     rcx, [rbp+6D0h+var_6C0]
0x18003d0e5  lea     r8, [rbp+6D0h+var_6B8]
0x18003d0e9  mov     edx, r15d
0x18003d0ec  mov     rax, [rcx]
0x18003d0ef  mov     rax, [rax+30h]
0x18003d0f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d0f8  test    eax, eax
0x18003d0fa  jns     short loc_18003D108
0x18003d0fc  lea     rdx, aQueryproviders; "QueryProviders error hr = 0x%x"
0x18003d103  jmp     loc_18003D669
0x18003d108  mov     ebx, r14d
0x18003d10b  mov     rcx, [rbp+6D0h+var_6B8]
0x18003d10f  lea     r9, [rbp+6D0h+var_6A8]
0x18003d113  lea     r8, [rbp+6D0h+var_6C8]
0x18003d117  mov     edx, r15d
0x18003d11a  mov     rax, [rcx]
0x18003d11d  mov     rax, [rax+18h]
0x18003d121  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d126  test    eax, eax
0x18003d128  js      loc_18003D662
0x18003d12e  cmp     eax, r15d
0x18003d131  jz      loc_18003D4BB
0x18003d137  mov     rcx, [rbp+6D0h+var_6C8]
0x18003d13b  lea     r8, [rbp+6D0h+var_6D0]
0x18003d13f  lea     rdx, IID_IVdsProvider
0x18003d146  mov     rax, [rcx]
0x18003d149  mov     rax, [rax]
0x18003d14c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d151  test    eax, eax
0x18003d153  js      loc_18003D4AF
0x18003d159  mov     rcx, [rbp+6D0h+var_6D0]
0x18003d15d  lea     r8, [rbp+6D0h+var_6D8]
0x18003d161  lea     rdx, IID_IVdsSwProvider
0x18003d168  mov     rax, [rcx]
0x18003d16b  mov     rax, [rax]
0x18003d16e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d173  test    eax, eax
0x18003d175  js      loc_18003D4A3
0x18003d17b  mov     rcx, [rbp+6D0h+var_6D8]
0x18003d17f  lea     rdx, [rbp+6D0h+var_6E8]
0x18003d183  mov     rax, [rcx]
0x18003d186  mov     rax, [rax+18h]
0x18003d18a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d18f  test    eax, eax
0x18003d191  js      loc_18003D497
0x18003d197  mov     rcx, [rbp+6D0h+var_6E8]
0x18003d19b  lea     r9, [rbp+6D0h+var_6A4]
0x18003d19f  lea     r8, [rbp+6D0h+var_6E0]
0x18003d1a3  mov     edx, r15d
0x18003d1a6  mov     rax, [rcx]
0x18003d1a9  mov     rax, [rax+18h]
0x18003d1ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d1b2  test    eax, eax
0x18003d1b4  js      loc_18003D48B
0x18003d1ba  cmp     eax, r15d
0x18003d1bd  jz      loc_18003D40E
0x18003d1c3  mov     rcx, [rbp+6D0h+var_6E0]
0x18003d1c7  lea     r8, [rbp+6D0h+var_6F0]
0x18003d1cb  lea     rdx, IID_IVdsPack
0x18003d1d2  mov     rax, [rcx]
0x18003d1d5  mov     rax, [rax]
0x18003d1d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d1dd  test    eax, eax
0x18003d1df  js      loc_18003D47F
0x18003d1e5  mov     rcx, [rbp+6D0h+var_6F0]
0x18003d1e9  lea     rdx, [rbp+6D0h+var_708]
0x18003d1ed  mov     rax, [rcx]
0x18003d1f0  mov     rax, [rax+30h]
0x18003d1f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d1f9  test    eax, eax
0x18003d1fb  js      loc_18003D473
0x18003d201  mov     rcx, [rbp+6D0h+var_708]
0x18003d205  lea     r9, [rbp+6D0h+var_6A0]
0x18003d209  lea     r8, [rbp+6D0h+var_6F8]
0x18003d20d  mov     edx, r15d
0x18003d210  mov     rax, [rcx]
0x18003d213  mov     rax, [rax+18h]
0x18003d217  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d21c  test    eax, eax
0x18003d21e  js      loc_18003D467
0x18003d224  cmp     eax, r15d
0x18003d227  jz      loc_18003D3EE
0x18003d22d  mov     rcx, [rbp+6D0h+var_6F8]
0x18003d231  lea     r8, [rbp+6D0h+var_700]
0x18003d235  lea     rdx, IID_IVdsDisk3
0x18003d23c  mov     rax, [rcx]
0x18003d23f  mov     rax, [rax]
0x18003d242  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d247  test    eax, eax
0x18003d249  js      loc_18003D45B
0x18003d24f  xor     edx, edx; Val
0x18003d251  lea     rcx, [rsp+7D0h+var_7A0]; void *
0x18003d256  mov     r8d, 88h; Size
0x18003d25c  call    memset_0
0x18003d261  mov     rcx, [rbp+6D0h+var_700]
0x18003d265  lea     rdx, [rsp+7D0h+var_7A0]
0x18003d26a  mov     rax, [rcx]
0x18003d26d  mov     rax, [rax+18h]
0x18003d271  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d276  test    eax, eax
0x18003d278  js      loc_18003D44F
0x18003d27e  mov     r8, [rbp+6D0h+var_720]
0x18003d282  lea     rdx, aFindDiskS; "Find disk : [%s]"
0x18003d289  xor     ecx, ecx
0x18003d28b  call    UnattendLogW
0x18003d290  mov     r8d, [rsp+7D0h+var_760]
0x18003d295  lea     rdx, aBustypeU; "       BusType : [%u]"
0x18003d29c  xor     ecx, ecx
0x18003d29e  call    UnattendLogW
0x18003d2a3  mov     r8d, [rsp+7D0h+var_764]
0x18003d2a8  lea     rdx, aUlflagsU; "       ulFlags : [%u]"
0x18003d2af  xor     ecx, ecx
0x18003d2b1  call    UnattendLogW
0x18003d2b6  mov     r8d, [rsp+7D0h+var_77C]
0x18003d2bb  lea     rdx, aDwmediatypeU; "   dwMediaType : [%u]"
0x18003d2c2  xor     ecx, ecx
0x18003d2c4  call    UnattendLogW
0x18003d2c9  mov     r8d, [rsp+7D0h+var_780]
0x18003d2ce  lea     rdx, aDwdevicetypeU; "  dwDeviceType : [%u]"
0x18003d2d5  xor     ecx, ecx
0x18003d2d7  call    UnattendLogW
0x18003d2dc  mov     eax, [rsp+7D0h+var_764]
0x18003d2e0  bt      eax, 0Eh
0x18003d2e4  jnb     short loc_18003D365
0x18003d2e6  test    al, al
0x18003d2e8  jns     short loc_18003D365
0x18003d2ea  bt      eax, 8
0x18003d2ee  jnb     short loc_18003D365
0x18003d2f0  cmp     [rsp+7D0h+var_77C], 0Ch
0x18003d2f5  jnz     short loc_18003D365
0x18003d2f7  cmp     [rsp+7D0h+var_780], 7
0x18003d2fc  jnz     short loc_18003D365
0x18003d2fe  test    ebx, ebx
0x18003d300  jnz     loc_18003D443
0x18003d306  lea     rdx, aSystemDisksFou; "System disks found"
0x18003d30d  xor     ecx, ecx
0x18003d30f  call    UnattendLogW
0x18003d314  mov     r8, [rbp+6D0h+var_720]; unsigned __int16 *
0x18003d318  test    r8, r8
0x18003d31b  jnz     short loc_18003D33F
0x18003d31d  lea     rdx, aLocationPathNo; "Location path not found (might be mmc b"...
0x18003d324  lea     ecx, [rbx+2]
0x18003d327  call    UnattendLogW
0x18003d32c  xor     edx, edx; Val
0x18003d32e  lea     rcx, [rbp+6D0h+pValue]; void *
0x18003d332  mov     r8d, 208h; Size
0x18003d338  call    memset_0
0x18003d33d  jmp     short loc_18003D355
0x18003d33f  mov     edx, 104h; unsigned __int64
0x18003d344  lea     rcx, [rbp+6D0h+pValue]; unsigned __int16 *
0x18003d348  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003d34d  test    eax, eax
0x18003d34f  js      loc_18003D437
0x18003d355  movups  xmm0, [rsp+7D0h+var_758]
0x18003d35a  mov     ebx, r15d
0x18003d35d  movdqu  xmmword ptr [rbp+6D0h+rguid.Data1], xmm0
0x18003d365  mov     rcx, [rbp+6D0h+pv]; pv
0x18003d369  test    rcx, rcx
0x18003d36c  jz      short loc_18003D378
0x18003d36e  call    cs:__imp_CoTaskMemFree
0x18003d374  mov     [rbp+6D0h+pv], r14
0x18003d378  mov     rcx, [rbp+6D0h+var_740]; pv
0x18003d37c  test    rcx, rcx
0x18003d37f  jz      short loc_18003D38B
0x18003d381  call    cs:__imp_CoTaskMemFree
0x18003d387  mov     [rbp+6D0h+var_740], r14
0x18003d38b  mov     rcx, [rbp+6D0h+var_738]; pv
0x18003d38f  test    rcx, rcx
0x18003d392  jz      short loc_18003D39E
0x18003d394  call    cs:__imp_CoTaskMemFree
0x18003d39a  mov     [rbp+6D0h+var_738], r14
0x18003d39e  mov     rcx, [rbp+6D0h+var_730]; pv
0x18003d3a2  test    rcx, rcx
0x18003d3a5  jz      short loc_18003D3B1
0x18003d3a7  call    cs:__imp_CoTaskMemFree
0x18003d3ad  mov     [rbp+6D0h+var_730], r14
0x18003d3b1  mov     rcx, [rbp+6D0h+var_728]; pv
0x18003d3b5  test    rcx, rcx
0x18003d3b8  jz      short loc_18003D3C4
0x18003d3ba  call    cs:__imp_CoTaskMemFree
0x18003d3c0  mov     [rbp+6D0h+var_728], r14
0x18003d3c4  mov     rcx, [rbp+6D0h+var_720]; pv
0x18003d3c8  test    rcx, rcx
0x18003d3cb  jz      short loc_18003D3D7
0x18003d3cd  call    cs:__imp_CoTaskMemFree
0x18003d3d3  mov     [rbp+6D0h+var_720], r14
0x18003d3d7  lea     rcx, [rbp+6D0h+var_700]
0x18003d3db  call    ?Release@?$CComPtrBase@UIVdsServiceLoader@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IVdsServiceLoader>::Release(void)
0x18003d3e0  lea     rcx, [rbp+6D0h+var_6F8]
0x18003d3e4  call    ?Release@?$CComPtrBase@UIVdsServiceLoader@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IVdsServiceLoader>::Release(void)
0x18003d3e9  jmp     loc_18003D201
0x18003d3ee  lea     rcx, [rbp+6D0h+var_708]
  ... truncated ...
```
