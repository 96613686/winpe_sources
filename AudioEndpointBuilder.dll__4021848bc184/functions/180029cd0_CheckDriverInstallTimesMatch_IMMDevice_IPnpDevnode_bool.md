# CheckDriverInstallTimesMatch(IMMDevice *,IPnpDevnode *,bool *)

- ea: `0x180029cd0`
- end: `0x18002a81b`
- name: `?CheckDriverInstallTimesMatch@@YAJPEAUIMMDevice@@PEAUIPnpDevnode@@PEA_N@Z`
- size: `2891`
- prototype: `__int64 __fastcall(struct IMMDevice *, struct IPnpDevnode *, bool *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180052ffc`

## callees

- `0x180010da8`
- `0x18001f374`
- `0x180029cd0`
- `0x18003e920`
- `0x180068010`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x18002a0fa`
- `ntdll!EtwEventWriteTransfer` at `0x18002a2c2`
- `ntdll!EtwEventWriteTransfer` at `0x18002a483`
- `ntdll!EtwEventWriteTransfer` at `0x18002a783`
- `ntdll!EtwEventWriteTransfer` at `0x18002a0fa`
- `ntdll!EtwEventWriteTransfer` at `0x18002a2c2`
- `ntdll!EtwEventWriteTransfer` at `0x18002a483`
- `ntdll!EtwEventWriteTransfer` at `0x18002a783`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180029d75`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180029d80`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180029d8c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180029d98`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180029e4d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180029e58`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180029e64`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180029e70`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180029f24`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180029f2f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180029f3b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180029f47`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180029fdd`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180029fe8`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180029ff4`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a000`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a105`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a110`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a11c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a128`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a1a5`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a1b0`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a1bc`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a1c8`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a2cf`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a2da`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a2e6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a2f2`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a370`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a37b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a387`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a393`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a490`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a49b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a4a7`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a4b3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a531`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a53c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a548`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a554`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a5b3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a5be`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a5ca`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a5d6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a790`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a79b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a7a7`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a7b3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180029d75`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180029d80`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180029d8c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180029d98`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180029e4d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180029e58`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180029e64`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180029e70`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180029f24`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180029f2f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180029f3b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180029f47`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180029fdd`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180029fe8`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180029ff4`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a000`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a105`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a110`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a11c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a128`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a1a5`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a1b0`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a1bc`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a1c8`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a2cf`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a2da`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a2e6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a2f2`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a370`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a37b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a387`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a393`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a490`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a49b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a4a7`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a4b3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a531`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a53c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a548`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a554`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a5b3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a5be`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a5ca`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a5d6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a790`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a79b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a7a7`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002a7b3`

## string_xrefs

- `0x180029d5f`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x180029e37`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x180029f0e`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x180029fc7`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x18002a18f`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x18002a35a`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x18002a51b`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
__int64 __fastcall CheckDriverInstallTimesMatch(struct IMMDevice *a1, struct IPnpDevnode *a2, bool *a3)
{
  int v5; // eax
  unsigned int v6; // ebx
  HRESULT (__stdcall *OpenPropertyStore)(IMMDevice *, DWORD, IPropertyStore **); // rbx
  __int64 v9; // rcx
  int v10; // eax
  unsigned int v11; // ebx
  __int64 v12; // rbx
  __int64 (__fastcall *v13)(__int64, _QWORD, __int64 *); // rsi
  __int64 v14; // rcx
  int v15; // eax
  unsigned int v16; // ebx
  int v17; // eax
  unsigned int v18; // ebx
  const struct _tlgProvider_t *v19; // rax
  int v20; // eax
  unsigned int v21; // ebx
  const struct _tlgProvider_t *v22; // rax
  int v23; // eax
  unsigned int v24; // ebx
  const struct _tlgProvider_t *v25; // rax
  int v26; // eax
  unsigned int v27; // ebx
  const struct _tlgProvider_t *v28; // rax
  const struct _tlgProvider_t *v29; // r10
  __int64 *v30; // rdx
  const struct _tlgProvider_t *v31; // rax
  int v32; // [rsp+20h] [rbp-E0h]
  __int64 v33; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v34; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v35; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v36; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v37; // [rsp+58h] [rbp-A8h]
  PROPVARIANT v38[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v39; // [rsp+70h] [rbp-90h]
  PROPVARIANT v40[2]; // [rsp+78h] [rbp-88h] BYREF
  __int64 v41; // [rsp+88h] [rbp-78h]
  PROPVARIANT pvar[2]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v43; // [rsp+A0h] [rbp-60h]
  PROPVARIANT v44[2]; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v45; // [rsp+B8h] [rbp-48h]
  PROPVARIANT v46; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v47; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v48; // [rsp+D0h] [rbp-30h]
  char *v49; // [rsp+D8h] [rbp-28h]
  int v50; // [rsp+E0h] [rbp-20h]
  int v51; // [rsp+E4h] [rbp-1Ch]
  unsigned __int16 *v52; // [rsp+F0h] [rbp-10h]
  int v53; // [rsp+F8h] [rbp-8h]
  int v54; // [rsp+FCh] [rbp-4h]
  void *v55; // [rsp+100h] [rbp+0h]
  int v56; // [rsp+108h] [rbp+8h]
  int v57; // [rsp+10Ch] [rbp+Ch]
  __int64 *v58; // [rsp+110h] [rbp+10h]
  __int64 v59; // [rsp+118h] [rbp+18h]
  PROPVARIANT *v60; // [rsp+120h] [rbp+20h]
  __int64 v61; // [rsp+128h] [rbp+28h]
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+68h]

  v34 = 0;
  v33 = 0;
  *(_OWORD *)v40 = 0;
  v41 = 0;
  *(_OWORD *)v38 = 0;
  v39 = 0;
  *(_OWORD *)v44 = 0;
  v45 = 0;
  *(_OWORD *)pvar = 0;
  v43 = 0;
  v35 = 0;
  v5 = (**(__int64 (__fastcall ***)(struct IPnpDevnode *, GUID *, __int64 *))a2)(
         a2,
         &GUID_d666063f_1587_4e43_81f1_b948e807363f,
         &v35);
  v6 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAD7,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
      (const char *)(unsigned int)v5,
      v32);
    PropVariantClear(pvar);
    PropVariantClear(v44);
    PropVariantClear(v38);
    PropVariantClear(v40);
    if ( v35 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
    return v6;
  }
  *a3 = 1;
  OpenPropertyStore = a1->lpVtbl->OpenPropertyStore;
  v9 = v34;
  v34 = 0;
  if ( v9 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  v10 = ((__int64 (__fastcall *)(struct IMMDevice *, __int64, __int64 *))OpenPropertyStore)(a1, 2, &v34);
  v11 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xADF,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
      (const char *)(unsigned int)v10,
      v32);
    PropVariantClear(pvar);
    PropVariantClear(v44);
    PropVariantClear(v38);
    PropVariantClear(v40);
    if ( v35 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
    if ( v33 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
    if ( v34 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
    return v11;
  }
  v12 = v35;
  v13 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v35 + 32LL);
  v14 = v33;
  v33 = 0;
  if ( v14 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  v15 = v13(v12, 0, &v33);
  v16 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAE1,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
      (const char *)(unsigned int)v15,
      v32);
    PropVariantClear(pvar);
    PropVariantClear(v44);
    PropVariantClear(v38);
    PropVariantClear(v40);
    if ( v35 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
    if ( v33 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
    if ( v34 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
    return v16;
  }
  v17 = (*(__int64 (__fastcall **)(__int64, const DEVPROPKEY *, PROPVARIANT *))(*(_QWORD *)v33 + 40LL))(
          v33,
          &DEVPKEY_Device_IsRebootRequired,
          pvar);
  v18 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAE5,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
      (const char *)(unsigned int)v17,
      v32);
    PropVariantClear(pvar);
    PropVariantClear(v44);
    PropVariantClear(v38);
    PropVariantClear(v40);
    if ( v35 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
    if ( v33 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
    if ( v34 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
    return v18;
  }
  if ( LOWORD(pvar[0]) == 11 && LOWORD(pvar[1]) )
  {
    v19 = AudioEndpointBuilderTelemetryProvider::Provider();
    if ( *(_DWORD *)v19 > 4u )
    {
      v36 = 0x40B000000LL;
      v37 = 0;
      v47 = *((_QWORD *)v19 + 1);
      v48 = *(unsigned __int16 *)v47 | 0x200000000LL;
      v49 = byte_1800769BD;
      v50 = 90;
      v51 = 1;
      EtwEventWriteTransfer(*((_QWORD *)v19 + 4), &v36, 0, 0);
    }
    PropVariantClear(pvar);
    PropVariantClear(v44);
    PropVariantClear(v38);
    PropVariantClear(v40);
    if ( v35 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
    if ( v33 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
LABEL_101:
    if ( v34 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
    return 0;
  }
  v20 = (*(__int64 (__fastcall **)(__int64, const DEVPROPKEY *, PROPVARIANT *))(*(_QWORD *)v34 + 40LL))(
          v34,
          &DEVPKEY_Device_IsRebootRequired,
          v44);
  v21 = v20;
  if ( v20 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAF1,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
      (const char *)(unsigned int)v20,
      v32);
    PropVariantClear(pvar);
    PropVariantClear(v44);
    PropVariantClear(v38);
    PropVariantClear(v40);
    if ( v35 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
    if ( v33 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
    if ( v34 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
    return v21;
  }
  if ( LOWORD(v44[0]) == 11 && LOWORD(v44[1]) )
  {
    v22 = AudioEndpointBuilderTelemetryProvider::Provider();
    if ( *(_DWORD *)v22 > 4u )
    {
      v36 = 0x40B000000LL;
      v37 = 0;
      v47 = *((_QWORD *)v22 + 1);
      v48 = *(unsigned __int16 *)v47 | 0x200000000LL;
      v49 = (char *)&dword_18007695C;
      v50 = 85;
      v51 = 1;
      EtwEventWriteTransfer(*((_QWORD *)v22 + 4), &v36, 0, 0);
    }
    *a3 = 0;
    PropVariantClear(pvar);
    PropVariantClear(v44);
    PropVariantClear(v38);
    PropVariantClear(v40);
    if ( v35 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
    if ( v33 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
    goto LABEL_101;
  }
  v23 = (*(__int64 (__fastcall **)(__int64, const DEVPROPKEY *, PROPVARIANT *))(*(_QWORD *)v34 + 40LL))(
          v34,
          &DEVPKEY_Device_InstallDate,
          v40);
  v24 = v23;
  if ( v23 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAFE,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
      (const char *)(unsigned int)v23,
      v32);
    PropVariantClear(pvar);
    PropVariantClear(v44);
    PropVariantClear(v38);
    PropVariantClear(v40);
    if ( v35 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
    if ( v33 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
    if ( v34 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
    return v24;
  }
  if ( LOWORD(v40[0]) != 64 )
  {
    v25 = AudioEndpointBuilderTelemetryProvider::Provider();
    if ( *(_DWORD *)v25 > 4u )
    {
      v36 = 0x40B000000LL;
      v37 = 0;
      v47 = *((_QWORD *)v25 + 1);
      v48 = *(unsigned __int16 *)v47 | 0x200000000LL;
      v49 = &byte_1800768FF;
      v50 = 81;
      v51 = 1;
      EtwEventWriteTransfer(*((_QWORD *)v25 + 4), &v36, 0, 0);
    }
    *a3 = 0;
    PropVariantClear(pvar);
    PropVariantClear(v44);
    PropVariantClear(v38);
    PropVariantClear(v40);
    if ( v35 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
    if ( v33 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
    goto LABEL_101;
  }
  v26 = (*(__int64 (__fastcall **)(__int64, const DEVPROPKEY *, PROPVARIANT *))(*(_QWORD *)v33 + 40LL))(
          v33,
          &DEVPKEY_Device_InstallDate,
          v38);
  v27 = v26;
  if ( v26 >= 0 )
  {
    if ( LOWORD(v38[0]) != 64 )
    {
      PropVariantClear(pvar);
      PropVariantClear(v44);
      PropVariantClear(v38);
      PropVariantClear(v40);
      if ( v35 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
      if ( v33 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
      goto LABEL_101;
    }
    if ( v40[1] )
    {
      if ( v40[1] == v38[1] )
      {
LABEL_97:
        PropVariantClear(pvar);
        PropVariantClear(v44);
        PropVariantClear(v38);
        PropVariantClear(v40);
        if ( v35 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
        if ( v33 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
        goto LABEL_101;
      }
      v31 = AudioEndpointBuilderTelemetryProvider::Provider();
      v29 = v31;
      if ( *(_DWORD *)v31 > 4u )
      {
        v46 = v38[1];
        v36 = (__int64)v40[1];
        v60 = &v46;
        v61 = 8;
        v58 = &v36;
        v59 = 8;
        v47 = 0x40B000000LL;
        v48 = 0;
        v52 = (unsigned __int16 *)*((_QWORD *)v31 + 1);
        v53 = *v52;
        v54 = 2;
        v55 = &unk_1800767F0;
        v56 = 148;
        v57 = 1;
        v30 = &v47;
        goto LABEL_95;
      }
    }
    else
    {
      v28 = AudioEndpointBuilderTelemetryProvider::Provider();
      v29 = v28;
      if ( *(_DWORD *)v28 > 4u )
      {
        v36 = 0x40B000000LL;
        v37 = 0;
        v47 = *((_QWORD *)v28 + 1);
        v48 = *(unsigned __int16 *)v47 | 0x200000000LL;
        v49 = (char *)qword_180076890;
        v50 = 99;
        v51 = 1;
        v30 = &v36;
LABEL_95:
        EtwEventWriteTransfer(*((_QWORD *)v29 + 4), v30, 0, 0);
      }
    }
    *a3 = 0;
    goto LABEL_97;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xB0B,
    (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
    (const char *)(unsigned int)v26,
    v32);
  PropVariantClear(pvar);
  PropVariantClear(v44);
  PropVariantClear(v38);
  PropVariantClear(v40);
  if ( v35 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
  if ( v33 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
  if ( v34 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
  return v27;
}

```

## disassembly

```asm
0x180029cd0  push    rbp
0x180029cd2  push    rbx
0x180029cd3  push    rsi
0x180029cd4  push    rdi
0x180029cd5  push    r14
0x180029cd7  lea     rbp, [rsp-40h]
0x180029cdc  sub     rsp, 140h
0x180029ce3  mov     rax, cs:__security_cookie
0x180029cea  xor     rax, rsp
0x180029ced  mov     [rbp+60h+var_30], rax
0x180029cf1  mov     rdi, r8
0x180029cf4  mov     r9, rdx
0x180029cf7  mov     rsi, rcx
0x180029cfa  xor     r14d, r14d
0x180029cfd  mov     [rsp+160h+var_120], r14
0x180029d02  mov     [rsp+160h+var_128], r14
0x180029d07  xorps   xmm0, xmm0
0x180029d0a  xor     eax, eax
0x180029d0c  movups  xmmword ptr [rsp+160h+var_E8], xmm0
0x180029d11  mov     [rbp+60h+var_D8], rax
0x180029d15  movups  xmmword ptr [rsp+160h+var_100], xmm0
0x180029d1a  mov     [rsp+160h+var_F0], rax
0x180029d1f  movups  xmmword ptr [rbp+60h+var_B8], xmm0
0x180029d23  mov     [rbp+60h+var_A8], rax
0x180029d27  movups  xmmword ptr [rbp+60h+pvar], xmm0
0x180029d2b  mov     [rbp+60h+var_C0], rax
0x180029d2f  mov     [rsp+160h+var_118], r14
0x180029d34  mov     rax, [rdx]
0x180029d37  lea     r8, [rsp+160h+var_118]
0x180029d3c  lea     rdx, _GUID_d666063f_1587_4e43_81f1_b948e807363f
0x180029d43  mov     rcx, r9
0x180029d46  mov     rax, [rax]
0x180029d49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029d4e  mov     ebx, eax
0x180029d50  test    eax, eax
0x180029d52  jns     loc_180029DEB
0x180029d58  mov     rcx, [rbp+68h]; this
0x180029d5c  mov     r9d, eax; char *
0x180029d5f  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x180029d66  mov     edx, 0AD7h; void *
0x180029d6b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029d70  nop
0x180029d71  lea     rcx, [rbp+60h+pvar]; pvar
0x180029d75  call    cs:__imp_PropVariantClear
0x180029d7b  nop
0x180029d7c  lea     rcx, [rbp+60h+var_B8]; pvar
0x180029d80  call    cs:__imp_PropVariantClear
0x180029d86  nop
0x180029d87  lea     rcx, [rsp+160h+var_100]; pvar
0x180029d8c  call    cs:__imp_PropVariantClear
0x180029d92  nop
0x180029d93  lea     rcx, [rsp+160h+var_E8]; pvar
0x180029d98  call    cs:__imp_PropVariantClear
0x180029d9e  nop
0x180029d9f  mov     rcx, [rsp+160h+var_118]
0x180029da4  test    rcx, rcx
0x180029da7  jz      short loc_180029DB6
0x180029da9  mov     rax, [rcx]
0x180029dac  mov     rax, [rax+10h]
0x180029db0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029db5  nop
0x180029db6  mov     rcx, [rsp+160h+var_128]
0x180029dbb  test    rcx, rcx
0x180029dbe  jz      short loc_180029DCD
0x180029dc0  mov     rax, [rcx]
0x180029dc3  mov     rax, [rax+10h]
0x180029dc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029dcc  nop
0x180029dcd  mov     rcx, [rsp+160h+var_120]
0x180029dd2  test    rcx, rcx
0x180029dd5  jz      short loc_180029DE4
0x180029dd7  mov     rax, [rcx]
0x180029dda  mov     rax, [rax+10h]
0x180029dde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029de3  nop
0x180029de4  mov     eax, ebx
0x180029de6  jmp     loc_18002A801
0x180029deb  mov     byte ptr [rdi], 1
0x180029dee  mov     rax, [rsi]
0x180029df1  mov     rbx, [rax+20h]
0x180029df5  mov     rcx, [rsp+160h+var_120]
0x180029dfa  mov     [rsp+160h+var_120], r14
0x180029dff  test    rcx, rcx
0x180029e02  jz      short loc_180029E11
0x180029e04  mov     rdx, [rcx]
0x180029e07  mov     rax, [rdx+10h]
0x180029e0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029e10  nop
0x180029e11  lea     r8, [rsp+160h+var_120]
0x180029e16  mov     edx, 2
0x180029e1b  mov     rcx, rsi
0x180029e1e  mov     rax, rbx
0x180029e21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029e26  mov     ebx, eax
0x180029e28  test    eax, eax
0x180029e2a  jns     loc_180029EC3
0x180029e30  mov     rcx, [rbp+68h]; this
0x180029e34  mov     r9d, eax; char *
0x180029e37  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x180029e3e  mov     edx, 0ADFh; void *
0x180029e43  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029e48  nop
0x180029e49  lea     rcx, [rbp+60h+pvar]; pvar
0x180029e4d  call    cs:__imp_PropVariantClear
0x180029e53  nop
0x180029e54  lea     rcx, [rbp+60h+var_B8]; pvar
0x180029e58  call    cs:__imp_PropVariantClear
0x180029e5e  nop
0x180029e5f  lea     rcx, [rsp+160h+var_100]; pvar
0x180029e64  call    cs:__imp_PropVariantClear
0x180029e6a  nop
0x180029e6b  lea     rcx, [rsp+160h+var_E8]; pvar
0x180029e70  call    cs:__imp_PropVariantClear
0x180029e76  nop
0x180029e77  mov     rcx, [rsp+160h+var_118]
0x180029e7c  test    rcx, rcx
0x180029e7f  jz      short loc_180029E8E
0x180029e81  mov     rax, [rcx]
0x180029e84  mov     rax, [rax+10h]
0x180029e88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029e8d  nop
0x180029e8e  mov     rcx, [rsp+160h+var_128]
0x180029e93  test    rcx, rcx
0x180029e96  jz      short loc_180029EA5
0x180029e98  mov     rax, [rcx]
0x180029e9b  mov     rax, [rax+10h]
0x180029e9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029ea4  nop
0x180029ea5  mov     rcx, [rsp+160h+var_120]
0x180029eaa  test    rcx, rcx
0x180029ead  jz      short loc_180029EBC
0x180029eaf  mov     rax, [rcx]
0x180029eb2  mov     rax, [rax+10h]
0x180029eb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029ebb  nop
0x180029ebc  mov     eax, ebx
0x180029ebe  jmp     loc_18002A801
0x180029ec3  mov     rbx, [rsp+160h+var_118]
0x180029ec8  mov     rax, [rbx]
0x180029ecb  mov     rsi, [rax+20h]
0x180029ecf  mov     rcx, [rsp+160h+var_128]
0x180029ed4  mov     [rsp+160h+var_128], r14
0x180029ed9  test    rcx, rcx
0x180029edc  jz      short loc_180029EEB
0x180029ede  mov     rdx, [rcx]
0x180029ee1  mov     rax, [rdx+10h]
0x180029ee5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029eea  nop
0x180029eeb  lea     r8, [rsp+160h+var_128]
0x180029ef0  xor     edx, edx
0x180029ef2  mov     rcx, rbx
0x180029ef5  mov     rax, rsi
0x180029ef8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029efd  mov     ebx, eax
0x180029eff  test    eax, eax
0x180029f01  jns     loc_180029F9A
0x180029f07  mov     rcx, [rbp+68h]; this
0x180029f0b  mov     r9d, eax; char *
0x180029f0e  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x180029f15  mov     edx, 0AE1h; void *
0x180029f1a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029f1f  nop
0x180029f20  lea     rcx, [rbp+60h+pvar]; pvar
0x180029f24  call    cs:__imp_PropVariantClear
0x180029f2a  nop
0x180029f2b  lea     rcx, [rbp+60h+var_B8]; pvar
0x180029f2f  call    cs:__imp_PropVariantClear
0x180029f35  nop
0x180029f36  lea     rcx, [rsp+160h+var_100]; pvar
0x180029f3b  call    cs:__imp_PropVariantClear
0x180029f41  nop
0x180029f42  lea     rcx, [rsp+160h+var_E8]; pvar
0x180029f47  call    cs:__imp_PropVariantClear
0x180029f4d  nop
0x180029f4e  mov     rcx, [rsp+160h+var_118]
0x180029f53  test    rcx, rcx
0x180029f56  jz      short loc_180029F65
0x180029f58  mov     rax, [rcx]
0x180029f5b  mov     rax, [rax+10h]
0x180029f5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029f64  nop
0x180029f65  mov     rcx, [rsp+160h+var_128]
0x180029f6a  test    rcx, rcx
0x180029f6d  jz      short loc_180029F7C
0x180029f6f  mov     rax, [rcx]
0x180029f72  mov     rax, [rax+10h]
0x180029f76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029f7b  nop
0x180029f7c  mov     rcx, [rsp+160h+var_120]
0x180029f81  test    rcx, rcx
0x180029f84  jz      short loc_180029F93
0x180029f86  mov     rax, [rcx]
0x180029f89  mov     rax, [rax+10h]
0x180029f8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029f92  nop
0x180029f93  mov     eax, ebx
0x180029f95  jmp     loc_18002A801
0x180029f9a  mov     rcx, [rsp+160h+var_128]
0x180029f9f  mov     rax, [rcx]
0x180029fa2  lea     r8, [rbp+60h+pvar]
0x180029fa6  lea     rdx, DEVPKEY_Device_IsRebootRequired
0x180029fad  mov     rax, [rax+28h]
0x180029fb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029fb6  mov     ebx, eax
0x180029fb8  test    eax, eax
0x180029fba  jns     loc_18002A053
0x180029fc0  mov     rcx, [rbp+68h]; this
0x180029fc4  mov     r9d, eax; char *
0x180029fc7  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x180029fce  mov     edx, 0AE5h; void *
0x180029fd3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029fd8  nop
0x180029fd9  lea     rcx, [rbp+60h+pvar]; pvar
0x180029fdd  call    cs:__imp_PropVariantClear
0x180029fe3  nop
0x180029fe4  lea     rcx, [rbp+60h+var_B8]; pvar
0x180029fe8  call    cs:__imp_PropVariantClear
0x180029fee  nop
0x180029fef  lea     rcx, [rsp+160h+var_100]; pvar
0x180029ff4  call    cs:__imp_PropVariantClear
0x180029ffa  nop
0x180029ffb  lea     rcx, [rsp+160h+var_E8]; pvar
0x18002a000  call    cs:__imp_PropVariantClear
0x18002a006  nop
0x18002a007  mov     rcx, [rsp+160h+var_118]
0x18002a00c  test    rcx, rcx
0x18002a00f  jz      short loc_18002A01E
0x18002a011  mov     rax, [rcx]
0x18002a014  mov     rax, [rax+10h]
0x18002a018  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a01d  nop
0x18002a01e  mov     rcx, [rsp+160h+var_128]
0x18002a023  test    rcx, rcx
0x18002a026  jz      short loc_18002A035
0x18002a028  mov     rax, [rcx]
0x18002a02b  mov     rax, [rax+10h]
0x18002a02f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a034  nop
0x18002a035  mov     rcx, [rsp+160h+var_120]
0x18002a03a  test    rcx, rcx
0x18002a03d  jz      short loc_18002A04C
0x18002a03f  mov     rax, [rcx]
0x18002a042  mov     rax, [rax+10h]
0x18002a046  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a04b  nop
0x18002a04c  mov     eax, ebx
0x18002a04e  jmp     loc_18002A801
0x18002a053  cmp     word ptr [rbp+60h+pvar], 0Bh
0x18002a058  jnz     loc_18002A162
0x18002a05e  cmp     word ptr [rbp+60h+pvar+8], 0
0x18002a063  jz      loc_18002A162
0x18002a069  call    ?Provider@AudioEndpointBuilderTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; AudioEndpointBuilderTelemetryProvider::Provider(void)
0x18002a06e  mov     r10, rax
0x18002a071  mov     ecx, [rax]
0x18002a073  cmp     ecx, 4
0x18002a076  jbe     loc_18002A101
0x18002a07c  mov     dword ptr [rsp+160h+var_110], 0B000000h
0x18002a084  movzx   ecx, cs:word_1800769B3
0x18002a08b  mov     dword ptr [rsp+160h+var_110+4], ecx
0x18002a08f  mov     [rsp+160h+var_108], r14
0x18002a094  mov     rcx, [rax+8]
0x18002a098  mov     [rbp+60h+var_98], rcx
0x18002a09c  movzx   eax, word ptr [rcx]
0x18002a09f  mov     dword ptr [rbp+60h+var_90], eax
0x18002a0a2  mov     dword ptr [rbp+60h+var_90+4], 2
0x18002a0a9  lea     rax, byte_1800769BD
0x18002a0b0  mov     [rbp+60h+var_88], rax
0x18002a0b4  mov     [rbp+60h+var_80], 5Ah ; 'Z'
0x18002a0bb  mov     [rbp+60h+var_7C], 1
0x18002a0c2  lea     rax, _TraceLoggingMetadataEnd
0x18002a0c9  lea     rcx, _TraceLoggingMetadata
0x18002a0d0  sub     eax, ecx
0x18002a0d2  mov     [rsp+160h+var_130], eax
0x18002a0d6  mov     eax, [rsp+160h+var_130]
0x18002a0da  lea     rax, [rbp+60h+var_98]
0x18002a0de  mov     [rsp+160h+var_138], rax
0x18002a0e3  mov     [rsp+160h+var_140], 2
0x18002a0eb  xor     r9d, r9d
0x18002a0ee  xor     r8d, r8d
0x18002a0f1  lea     rdx, [rsp+160h+var_110]
0x18002a0f6  mov     rcx, [r10+20h]
0x18002a0fa  call    cs:__imp_EtwEventWriteTransfer
0x18002a100  nop
0x18002a101  lea     rcx, [rbp+60h+pvar]; pvar
0x18002a105  call    cs:__imp_PropVariantClear
0x18002a10b  nop
0x18002a10c  lea     rcx, [rbp+60h+var_B8]; pvar
0x18002a110  call    cs:__imp_PropVariantClear
0x18002a116  nop
0x18002a117  lea     rcx, [rsp+160h+var_100]; pvar
0x18002a11c  call    cs:__imp_PropVariantClear
0x18002a122  nop
0x18002a123  lea     rcx, [rsp+160h+var_E8]; pvar
0x18002a128  call    cs:__imp_PropVariantClear
0x18002a12e  nop
0x18002a12f  mov     rcx, [rsp+160h+var_118]
0x18002a134  test    rcx, rcx
0x18002a137  jz      short loc_18002A146
0x18002a139  mov     rax, [rcx]
0x18002a13c  mov     rax, [rax+10h]
  ... truncated ...
```
