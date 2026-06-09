# DdcProtectionStateHelper::GetNetworkProtectionValues(Windows::Data::Json::IJsonObject *)

- ea: `0x18001f2e0`
- end: `0x18001f68d`
- name: `?GetNetworkProtectionValues@DdcProtectionStateHelper@@CAJPEAUIJsonObject@Json@Data@Windows@@@Z`
- size: `941`
- prototype: `__int64 __fastcall(struct Windows::Data::Json::IJsonObject *, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180020068`

## callees

- `0x1800024c0`
- `0x180004060`
- `0x1800050b8`
- `0x18000fc64`
- `0x18000fd48`
- `0x18001d2b8`
- `0x18001f2e0`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001f4cb`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001f4cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f418`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f42d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f601`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f616`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f62b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f418`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f42d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f601`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f616`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f62b`

## string_xrefs

- `0x18001f4ac`: `Windows.Data.Json.JsonValue`
- `0x18001f4e4`: `CHR(GetActivationFactory(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValueStatics.GetAddressOf()))`
- `0x18001f5c6`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcprotectionstatehelper.cpp`
- `0x18001f5b2`: `CHR(pJsonValueStatics->CreateStringValue(HStringReference(ppwszStatus[i]).Get(), pJsonValue.ReleaseAndGetAddressOf()))`
- `0x18001f593`: `CHR(pProtectionState->SetNamedValue(HStringReference(ppwszJsonFields[i]).Get(), pJsonValue.Get()))`

## pseudocode

```c
__int64 __fastcall DdcProtectionStateHelper::GetNetworkProtectionValues(
        struct Windows::Data::Json::IJsonObject *a1,
        int a2)
{
  int ActivationFactory; // ebx
  int v4; // edx
  int v5; // ecx
  IUnknown *v6; // rbx
  int v7; // r14d
  LPVOID v8; // rdx
  unsigned int v9; // r12d
  __int64 v10; // rdi
  void *v11; // rcx
  int v12; // eax
  const wchar_t *v13; // rax
  int v14; // edx
  int v15; // ecx
  int i; // r14d
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, PVOID, __int64 *); // rbx
  char v19; // r8
  HSTRING_HEADER *v20; // rax
  int v21; // edx
  int v22; // ecx
  char v23; // r8
  __int64 (__fastcall *v24)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64); // rdi
  __int64 v25; // rbx
  HSTRING_HEADER *v26; // rax
  int v27; // edx
  int v28; // ecx
  LPVOID v29; // rdx
  unsigned int v30; // edi
  void *v31; // rcx
  __int64 v32; // rcx
  LPVOID pv; // [rsp+30h] [rbp-59h] BYREF
  int v35; // [rsp+38h] [rbp-51h] BYREF
  __int64 v36; // [rsp+40h] [rbp-49h] BYREF
  __int64 v37; // [rsp+48h] [rbp-41h] BYREF
  IUnknown *v38; // [rsp+50h] [rbp-39h] BYREF
  _DWORD v39[4]; // [rsp+58h] [rbp-31h]
  _QWORD v40[3]; // [rsp+68h] [rbp-21h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+80h] [rbp-9h] BYREF
  __int64 v42; // [rsp+98h] [rbp+Fh]
  _QWORD v43[3]; // [rsp+A0h] [rbp+17h] BYREF

  v38 = 0;
  v35 = 0;
  pv = 0;
  v37 = 0;
  v36 = 0;
  if ( a1 )
  {
    v39[0] = 1;
    v39[1] = 2;
    v39[2] = 4;
    v43[0] = L"Unknown";
    v43[1] = L"Unknown";
    v43[2] = L"Unknown";
    v40[0] = L"NetworkProtectionDomainNetwork";
    v40[1] = L"NetworkProtectionPrivateNetwork";
    v40[2] = L"NetworkProtectionPublicNetwork";
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
    if ( (int)CreateInstanceWithCloak<INetworkProtectionShield>(v5, v4, &v38) < 0
      || (v6 = v38, ((int (__fastcall *)(IUnknown *, int *))v38->lpVtbl[2].AddRef)(v38, &v35) < 0) )
    {
LABEL_23:
      v42 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &hstringHeader,
        L"Windows.Data.Json.JsonValue",
        0x1Cu,
        0x1Bu);
      ActivationFactory = RoGetActivationFactory(v42, &GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c, &v37);
      if ( ActivationFactory >= 0 )
      {
        for ( i = 0; (unsigned __int64)i < 3; ++i )
        {
          v17 = v37;
          v18 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *))(*(_QWORD *)v37 + 80LL);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v36);
          v20 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                  &hstringHeader,
                  (const WCHAR **)&v43[i],
                  v19);
          ActivationFactory = v18(v17, v20[1].Reserved.Reserved1, &v36);
          if ( ActivationFactory < 0 )
          {
            if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
              McTemplateU0dsqs_EventWriteTransfer(
                v22,
                v21,
                ActivationFactory,
                (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcprotectionstatehelper.cpp",
                244,
                "CHR(pJsonValueStatics->CreateStringValue(HStringReference(ppwszStatus[i]).Get(), pJsonValue.ReleaseAndGetAddressOf()))");
            goto LABEL_35;
          }
          v24 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, PVOID, __int64))(*(_QWORD *)a1 + 56LL);
          v25 = v36;
          v26 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                  &hstringHeader,
                  (const WCHAR **)&v40[i],
                  v23);
          ActivationFactory = v24(a1, v26[1].Reserved.Reserved1, v25);
          if ( ActivationFactory < 0 )
          {
            if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
              McTemplateU0dsqs_EventWriteTransfer(
                v28,
                v27,
                ActivationFactory,
                (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcprotectionstatehelper.cpp",
                245,
                "CHR(pProtectionState->SetNamedValue(HStringReference(ppwszJsonFields[i]).Get(), pJsonValue.Get()))");
            goto LABEL_35;
          }
        }
      }
      else if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      {
        McTemplateU0dsqs_EventWriteTransfer(
          v15,
          v14,
          ActivationFactory,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcprotectionstatehelper.cpp",
          241,
          "CHR(GetActivationFactory(HStringReference(RuntimeClass_Windows_Data_Json_JsonValue).Get(), pJsonValueStatics.GetAddressOf()))");
      }
      goto LABEL_35;
    }
    v7 = 0;
    v8 = pv;
    while ( 1 )
    {
      v9 = v39[v7];
      if ( (v9 & v35) != 0 )
      {
        if ( v8 && *((_DWORD *)v8 + 10) && *((_QWORD *)v8 + 6) )
        {
          v10 = 0;
          do
          {
            v11 = *(void **)(*((_QWORD *)v8 + 6) + 24 * v10 + 8);
            if ( v11 )
            {
              CoTaskMemFree(v11);
              v8 = pv;
            }
            v10 = (unsigned int)(v10 + 1);
          }
          while ( (unsigned int)v10 < *((_DWORD *)v8 + 10) );
          CoTaskMemFree(*((LPVOID *)v8 + 6));
          *((_QWORD *)pv + 6) = 0;
          *((_DWORD *)pv + 10) = 0;
        }
        v12 = ((__int64 (__fastcall *)(IUnknown *, _QWORD, LPVOID *))v6->lpVtbl[5].QueryInterface)(v6, v9, &pv);
        v8 = pv;
        if ( v12 < 0 )
          goto LABEL_22;
        v13 = L"On";
        if ( !*(_DWORD *)pv )
          v13 = L"Off";
      }
      else
      {
        v13 = L"NotSupported";
      }
      v43[v7] = v13;
LABEL_22:
      if ( (unsigned int)++v7 >= 3 )
        goto LABEL_23;
    }
  }
  ActivationFactory = -2147024809;
  if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
    goto LABEL_44;
  McTemplateU0dsqs_EventWriteTransfer(
    0,
    a2,
    -2147024809,
    (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcprotectionstatehelper.cpp",
    192,
    "CPR(pProtectionState)");
LABEL_35:
  v29 = pv;
  if ( pv )
  {
    if ( *((_DWORD *)pv + 10) && *((_QWORD *)pv + 6) )
    {
      v30 = 0;
      do
      {
        v31 = *(void **)(*((_QWORD *)v29 + 6) + 24LL * v30 + 8);
        if ( v31 )
        {
          CoTaskMemFree(v31);
          v29 = pv;
        }
        ++v30;
      }
      while ( v30 < *((_DWORD *)v29 + 10) );
      CoTaskMemFree(*((LPVOID *)v29 + 6));
      *((_QWORD *)pv + 6) = 0;
      v29 = pv;
    }
    CoTaskMemFree(v29);
    pv = 0;
  }
LABEL_44:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v36);
  v32 = v37;
  if ( v37 )
  {
    v37 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x18001f2e0  mov     [rsp-8+arg_8], rbx
0x18001f2e5  mov     [rsp-8+arg_10], rdi
0x18001f2ea  push    rbp
0x18001f2eb  push    r12
0x18001f2ed  push    r13
0x18001f2ef  push    r14
0x18001f2f1  push    r15
0x18001f2f3  lea     rbp, [rsp-37h]
0x18001f2f8  sub     rsp, 0C0h
0x18001f2ff  mov     rax, cs:__security_cookie
0x18001f306  xor     rax, rsp
0x18001f309  mov     [rbp+57h+var_28], rax
0x18001f30d  mov     r13, rcx
0x18001f310  xor     r12d, r12d
0x18001f313  mov     [rbp+57h+var_90], r12
0x18001f317  mov     [rbp+57h+var_A8], r12d
0x18001f31b  mov     [rbp+57h+pv], r12
0x18001f31f  mov     [rbp+57h+var_98], r12
0x18001f323  mov     [rbp+57h+var_A0], r12
0x18001f327  test    rcx, rcx
0x18001f32a  jnz     short loc_18001F357
0x18001f32c  mov     ebx, 80070057h
0x18001f331  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001f338  jz      loc_18001F635
0x18001f33e  lea     rax, aCprPprotection; "CPR(pProtectionState)"
0x18001f345  mov     [rsp+0E0h+var_B8], rax
0x18001f34a  mov     [rsp+0E0h+var_C0], 3C0h
0x18001f352  jmp     loc_18001F5C6
0x18001f357  mov     [rbp+57h+var_88], 1
0x18001f35e  mov     [rbp+57h+var_84], 2
0x18001f365  mov     [rbp+57h+var_80], 4
0x18001f36c  lea     rax, aUnknown; "Unknown"
0x18001f373  mov     [rbp+57h+var_40], rax
0x18001f377  mov     [rbp+57h+var_38], rax
0x18001f37b  mov     [rbp+57h+var_30], rax
0x18001f37f  lea     rax, aNetworkprotect_0; "NetworkProtectionDomainNetwork"
0x18001f386  mov     [rbp+57h+var_78], rax
0x18001f38a  lea     rax, aNetworkprotect; "NetworkProtectionPrivateNetwork"
0x18001f391  mov     [rbp+57h+var_70], rax
0x18001f395  lea     rax, aNetworkprotect_2; "NetworkProtectionPublicNetwork"
0x18001f39c  mov     [rbp+57h+var_68], rax
0x18001f3a0  lea     rcx, [rbp+57h+var_90]
0x18001f3a4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001f3a9  lea     r8, [rbp+57h+var_90]
0x18001f3ad  call    ??$CreateInstanceWithCloak@UINetworkProtectionShield@@@@YAJAEBU_GUID@@0PEAPEAUINetworkProtectionShield@@@Z; CreateInstanceWithCloak<INetworkProtectionShield>(_GUID const &,_GUID const &,INetworkProtectionShield * *)
0x18001f3b2  test    eax, eax
0x18001f3b4  js      loc_18001F49E
0x18001f3ba  mov     rbx, [rbp+57h+var_90]
0x18001f3be  mov     rax, [rbx]
0x18001f3c1  lea     rdx, [rbp+57h+var_A8]
0x18001f3c5  mov     rcx, rbx
0x18001f3c8  mov     rax, [rax+38h]
0x18001f3cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f3d1  test    eax, eax
0x18001f3d3  js      loc_18001F49E
0x18001f3d9  mov     r14d, r12d
0x18001f3dc  mov     rdx, [rbp+57h+pv]
0x18001f3e0  movsxd  r15, r14d
0x18001f3e3  mov     r12d, [rbp+r15*4+57h+var_88]
0x18001f3e8  test    [rbp+57h+var_A8], r12d
0x18001f3ec  jz      loc_18001F482
0x18001f3f2  test    rdx, rdx
0x18001f3f5  jz      short loc_18001F44A
0x18001f3f7  cmp     dword ptr [rdx+28h], 0
0x18001f3fb  jbe     short loc_18001F44A
0x18001f3fd  cmp     qword ptr [rdx+30h], 0
0x18001f402  jz      short loc_18001F44A
0x18001f404  xor     edi, edi
0x18001f406  lea     rcx, [rdi+rdi*2]
0x18001f40a  mov     rax, [rdx+30h]
0x18001f40e  mov     rcx, [rax+rcx*8+8]; pv
0x18001f413  test    rcx, rcx
0x18001f416  jz      short loc_18001F422
0x18001f418  call    cs:__imp_CoTaskMemFree
0x18001f41e  mov     rdx, [rbp+57h+pv]
0x18001f422  inc     edi
0x18001f424  cmp     edi, [rdx+28h]
0x18001f427  jb      short loc_18001F406
0x18001f429  mov     rcx, [rdx+30h]; pv
0x18001f42d  call    cs:__imp_CoTaskMemFree
0x18001f433  mov     rax, [rbp+57h+pv]
0x18001f437  mov     qword ptr [rax+30h], 0
0x18001f43f  mov     rax, [rbp+57h+pv]
0x18001f443  mov     dword ptr [rax+28h], 0
0x18001f44a  mov     rax, [rbx]
0x18001f44d  lea     r8, [rbp+57h+pv]
0x18001f451  mov     edx, r12d
0x18001f454  mov     rcx, rbx
0x18001f457  mov     rax, [rax+78h]
0x18001f45b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f460  xor     r12d, r12d
0x18001f463  mov     rdx, [rbp+57h+pv]
0x18001f467  test    eax, eax
0x18001f469  js      short loc_18001F491
0x18001f46b  lea     rcx, aOff; "Off"
0x18001f472  lea     rax, aOn; "On"
0x18001f479  cmp     [rdx], r12d
0x18001f47c  cmovz   rax, rcx
0x18001f480  jmp     short loc_18001F48C
0x18001f482  lea     rax, aNotsupported; "NotSupported"
0x18001f489  xor     r12d, r12d
0x18001f48c  mov     [rbp+r15*8+57h+var_40], rax
0x18001f491  inc     r14d
0x18001f494  cmp     r14d, 3
0x18001f498  jb      loc_18001F3E0
0x18001f49e  mov     [rbp+57h+var_48], r12
0x18001f4a2  mov     r9d, 1Bh; unsigned int
0x18001f4a8  lea     r8d, [r9+1]; unsigned int
0x18001f4ac  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonValue@@3QBGB; "Windows.Data.Json.JsonValue"
0x18001f4b3  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18001f4b7  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18001f4bc  lea     r8, [rbp+57h+var_98]
0x18001f4c0  lea     rdx, _GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c
0x18001f4c7  mov     rcx, [rbp+57h+var_48]
0x18001f4cb  call    cs:__imp_RoGetActivationFactory
0x18001f4d1  mov     ebx, eax
0x18001f4d3  test    eax, eax
0x18001f4d5  jns     short loc_18001F4FD
0x18001f4d7  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001f4de  jz      loc_18001F5D5
0x18001f4e4  lea     rax, aChrGetactivati_1; "CHR(GetActivationFactory(HStringReferen"...
0x18001f4eb  mov     [rsp+0E0h+var_B8], rax
0x18001f4f0  mov     [rsp+0E0h+var_C0], 3F1h
0x18001f4f8  jmp     loc_18001F5C6
0x18001f4fd  mov     r14d, r12d
0x18001f500  movsxd  r15, r14d
0x18001f503  cmp     r15, 3
0x18001f507  jnb     loc_18001F5D5
0x18001f50d  mov     rdi, [rbp+57h+var_98]
0x18001f511  mov     rax, [rdi]
0x18001f514  mov     rbx, [rax+50h]
0x18001f518  lea     rcx, [rbp+57h+var_A0]
0x18001f51c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001f521  lea     rdx, [rbp+57h+var_40]
0x18001f525  lea     rdx, [rdx+r15*8]
0x18001f529  lea     rcx, [rbp+57h+hstringHeader]
0x18001f52d  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18001f532  nop
0x18001f533  lea     r8, [rbp+57h+var_A0]
0x18001f537  mov     rdx, [rax+18h]
0x18001f53b  mov     rcx, rdi
0x18001f53e  mov     rax, rbx
0x18001f541  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f546  mov     ebx, eax
0x18001f548  test    eax, eax
0x18001f54a  js      short loc_18001F5A9
0x18001f54c  mov     rax, [r13+0]
0x18001f550  mov     rdi, [rax+38h]
0x18001f554  mov     rbx, [rbp+57h+var_A0]
0x18001f558  lea     rdx, [rbp+57h+var_78]
0x18001f55c  lea     rdx, [rdx+r15*8]
0x18001f560  lea     rcx, [rbp+57h+hstringHeader]
0x18001f564  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18001f569  nop
0x18001f56a  mov     r8, rbx
0x18001f56d  mov     rdx, [rax+18h]
0x18001f571  mov     rcx, r13
0x18001f574  mov     rax, rdi
0x18001f577  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f57c  mov     ebx, eax
0x18001f57e  test    eax, eax
0x18001f580  js      short loc_18001F58A
0x18001f582  inc     r14d
0x18001f585  jmp     loc_18001F500
0x18001f58a  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001f591  jz      short loc_18001F5D5
0x18001f593  lea     rax, aChrPprotection_4; "CHR(pProtectionState->SetNamedValue(HSt"...
0x18001f59a  mov     [rsp+0E0h+var_B8], rax
0x18001f59f  mov     [rsp+0E0h+var_C0], 3F5h
0x18001f5a7  jmp     short loc_18001F5C6
0x18001f5a9  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001f5b0  jz      short loc_18001F5D5
0x18001f5b2  lea     rax, aChrPjsonvalues_12; "CHR(pJsonValueStatics->CreateStringValu"...
0x18001f5b9  mov     [rsp+0E0h+var_B8], rax
0x18001f5be  mov     [rsp+0E0h+var_C0], 3F4h
0x18001f5c6  lea     r9, aOnecoreuapShel_1; "onecoreuap\\shell\\devicedirectory\\dev"...
0x18001f5cd  mov     r8d, ebx
0x18001f5d0  call    McTemplateU0dsqs_EventWriteTransfer
0x18001f5d5  mov     rdx, [rbp+57h+pv]
0x18001f5d9  test    rdx, rdx
0x18001f5dc  jz      short loc_18001F635
0x18001f5de  cmp     [rdx+28h], r12d
0x18001f5e2  jbe     short loc_18001F628
0x18001f5e4  cmp     [rdx+30h], r12
0x18001f5e8  jz      short loc_18001F628
0x18001f5ea  mov     edi, r12d
0x18001f5ed  mov     eax, edi
0x18001f5ef  lea     rcx, [rax+rax*2]
0x18001f5f3  mov     rax, [rdx+30h]
0x18001f5f7  mov     rcx, [rax+rcx*8+8]; pv
0x18001f5fc  test    rcx, rcx
0x18001f5ff  jz      short loc_18001F60B
0x18001f601  call    cs:__imp_CoTaskMemFree
0x18001f607  mov     rdx, [rbp+57h+pv]
0x18001f60b  inc     edi
0x18001f60d  cmp     edi, [rdx+28h]
0x18001f610  jb      short loc_18001F5ED
0x18001f612  mov     rcx, [rdx+30h]; pv
0x18001f616  call    cs:__imp_CoTaskMemFree
0x18001f61c  mov     rax, [rbp+57h+pv]
0x18001f620  mov     [rax+30h], r12
0x18001f624  mov     rdx, [rbp+57h+pv]
0x18001f628  mov     rcx, rdx; pv
0x18001f62b  call    cs:__imp_CoTaskMemFree
0x18001f631  mov     [rbp+57h+pv], r12
0x18001f635  lea     rcx, [rbp+57h+var_A0]
0x18001f639  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001f63e  nop
0x18001f63f  mov     rcx, [rbp+57h+var_98]
0x18001f643  test    rcx, rcx
0x18001f646  jz      short loc_18001F659
0x18001f648  mov     [rbp+57h+var_98], r12
0x18001f64c  mov     rax, [rcx]
0x18001f64f  mov     rax, [rax+10h]
0x18001f653  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f658  nop
0x18001f659  lea     rcx, [rbp+57h+var_90]
0x18001f65d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001f662  mov     eax, ebx
0x18001f664  mov     rcx, [rbp+57h+var_28]
0x18001f668  xor     rcx, rsp; StackCookie
0x18001f66b  call    __security_check_cookie
0x18001f670  lea     r11, [rsp+0E0h+var_20]
0x18001f678  mov     rbx, [r11+38h]
0x18001f67c  mov     rdi, [r11+40h]
0x18001f680  mov     rsp, r11
0x18001f683  pop     r15
0x18001f685  pop     r14
0x18001f687  pop     r13
0x18001f689  pop     r12
0x18001f68b  pop     rbp
0x18001f68c  retn
```
