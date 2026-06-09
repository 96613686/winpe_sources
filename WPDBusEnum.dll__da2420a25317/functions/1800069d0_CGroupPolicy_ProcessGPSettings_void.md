# CGroupPolicy::ProcessGPSettings(void)

- ea: `0x1800069d0`
- end: `0x180007021`
- name: `?ProcessGPSettings@CGroupPolicy@@IEAAXXZ`
- size: `1617`
- prototype: `void __fastcall(CGroupPolicy *__hidden this)`
- caller_count: `1`
- callee_count: `23`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800069c0`

## callees

- `0x180001730`
- `0x180002a70`
- `0x180002fa0`
- `0x180004050`
- `0x180004f10`
- `0x1800059d0`
- `0x180005bb0`
- `0x1800069d0`
- `0x180007160`
- `0x180007244`
- `0x180007f28`
- `0x180008128`
- `0x180008b44`
- `0x1800097d0`
- `0x18000dfd4`
- `0x18000fc24`
- `0x1800106e0`
- `0x18001396c`
- `0x180013e9c`
- `0x180014334`
- `0x1800143f8`
- `0x180014458`
- `0x1800154fc`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180006e3f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180006e3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006f2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006f2d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006c48`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006c48`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006b53`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006b5e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006b81`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006b8b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006b94`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006e8e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006f0a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006b53`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006b5e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006b81`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006b8b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006b94`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006e8e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006f0a`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180006ff0`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180006ff0`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180006a57`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180006a57`
- `SETUPAPI!CMP_WaitNoPendingInstallEvents` at `0x180006d82`
- `SETUPAPI!CMP_WaitNoPendingInstallEvents` at `0x180006d82`

## string_xrefs

- `0x180006e14`: `Access Code`
- `0x180006fc5`: `HotplugSecurityDescriptor`
- `0x180006fd8`: `HotplugSecureOpen`

## pseudocode

```c
void __fastcall CGroupPolicy::ProcessGPSettings(CGroupPolicy *this)
{
  HRESULT v2; // eax
  void *v3; // rdi
  int v4; // edx
  CGroupPolicy *v5; // rcx
  HLOCAL *v6; // rdi
  HLOCAL *v7; // rbx
  _DWORD *v8; // r15
  __int64 **v9; // r14
  __int64 i; // rbx
  int v11; // edx
  int v12; // eax
  HLOCAL v13; // r14
  char *v14; // rax
  __int128 v15; // xmm0
  int v16; // ecx
  _QWORD *v17; // rax
  _QWORD *v18; // rbx
  _QWORD *v19; // rax
  int v20; // eax
  CGroupPolicy *v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // rdx
  DWORD v24; // edi
  unsigned int v25; // eax
  __int64 v26; // rdx
  int v27; // ebx
  DWORD LastError; // eax
  unsigned int v29; // eax
  __int64 v30; // rdx
  CPnPNotification *v31; // rcx
  int v32; // r12d
  __int64 *j; // rbx
  __int64 v34; // rdx
  __int64 v35; // rcx
  int v36; // [rsp+40h] [rbp-C0h] BYREF
  HLOCAL v37; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v38; // [rsp+50h] [rbp-B0h] BYREF
  HLOCAL v39; // [rsp+58h] [rbp-A8h] BYREF
  HLOCAL hMem; // [rsp+60h] [rbp-A0h] BYREF
  HRESULT v41; // [rsp+68h] [rbp-98h]
  HLOCAL Buf1[2]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR Buffer[128]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR Message[128]; // [rsp+180h] [rbp+80h] BYREF

  Buf1[0] = 0;
  hMem = 0;
  v38 = 0;
  if ( WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_bf352b66c2b13fdf6580719fc101b8b6_Traceguids);
  }
  v2 = CoInitializeEx(0, 0);
  v41 = v2;
  if ( v2 == -2147417850 )
  {
    if ( WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_bf352b66c2b13fdf6580719fc101b8b6_Traceguids, 2147549446LL);
    while ( 1 )
    {
LABEL_12:
      v36 = 0;
      v3 = 0;
      CGroupPolicy::UpdateMdmPolicy(this);
      v4 = *((_DWORD *)this + 8);
      LODWORD(v39) = 0;
      LODWORD(v37) = 0;
      if ( (unsigned int)WPDLibCheckGivenDeviceGUID(0, v4, (struct _ACL **)Buf1, &hMem, &v38, &v39, (DWORD *)&v37) )
      {
        GPDebugPrintX(8, "Deny_All not set for all. Will query other %d GUIDs\n", 6);
        for ( i = 0; i != 6; ++i )
        {
          WPDLibPropagateDenyExecuteDeviceGUID(&GP_WellKnown_GUIDS.Data1 + 4 * i);
          v11 = *((_DWORD *)this + 8);
          LODWORD(v39) = 0;
          LODWORD(v37) = 0;
          v12 = WPDLibCheckGivenDeviceGUID(
                  (__int64)(&GP_WellKnown_GUIDS + i),
                  v11,
                  (struct _ACL **)Buf1,
                  &hMem,
                  &v38,
                  &v39,
                  (DWORD *)&v37);
          if ( v12 || (v13 = hMem) == 0 )
          {
            GPDebugPrintX(8, "Policy for other GUID is not enabled, status:  %d\n", v12);
          }
          else
          {
            GPDebugPrintX(8, "Query for other GUID succeeded\n");
            v14 = (char *)LocalAlloc(0x40u, 0x40u);
            if ( v14 )
            {
              v15 = *((_OWORD *)&GP_WellKnown_GUIDS + i);
              *((HLOCAL *)v14 + 1) = Buf1[0];
              *((_DWORD *)v14 + 6) = v38;
              *((_DWORD *)v14 + 13) = (_DWORD)v39;
              v16 = (int)v37;
              *(_QWORD *)v14 = v3;
              v3 = v14;
              *((_DWORD *)v14 + 14) = v16;
              *(_OWORD *)(v14 + 28) = v15;
              *((_QWORD *)v14 + 2) = v13;
              *((_DWORD *)v14 + 12) = 1;
              *((_DWORD *)v14 + 15) = 0;
            }
          }
        }
        v17 = WPDLibEnumerateCustomKeys(*((_DWORD *)this + 8));
        v18 = v17;
        if ( v3 )
        {
          v19 = (_QWORD *)WPDLibRemoveDuplicateEntries(v17, v3);
          v3 = v19;
          if ( v18 )
          {
            while ( v19 )
            {
              if ( !*v19 )
              {
                *v19 = v18;
                break;
              }
              v19 = (_QWORD *)*v19;
            }
          }
          if ( !v3 )
            v3 = v18;
          v37 = v3;
          GPDebugPrintX(8, "Well known GUID List %p\n", v3);
        }
        else
        {
          if ( v17 )
            v3 = v17;
          v37 = v3;
        }
        v9 = (__int64 **)((char *)this + 8);
        WPDLibCheckIfGPDisabled(*((_QWORD *)this + 1), v3, (char *)this + 16);
        WPDLibUpdateSecurityDescriptorList((char *)this + 8, &v37, (char *)this + 16);
        v8 = (_DWORD *)((char *)this + 24);
        v20 = *((_DWORD *)this + 6);
        *((_DWORD *)this + 7) = v20;
        *((_DWORD *)this + 6) = 1;
        if ( (v20 & 0xFFFFFFFD) == 0 )
        {
          GPDebugPrintX(8, "Deny_All for all devices is being reset\n");
          CGroupPolicy::DisableAllAccessToAllDevices(v21, 0, 0, 0, &v36);
          CMP_WaitNoPendingInstallEvents(0xFFFFFFFF);
        }
        if ( *v9 )
        {
          GPDebugPrintX(8, "Have devices to process\n");
          CGroupPolicy::ProcessGPForDevices(this, &v36);
        }
      }
      else
      {
        GPDebugPrintX(8, "Deny_All set for all devices\n");
        CGroupPolicy::DisableAllAccessToAllDevices(v5, (struct _ACL *)Buf1[0], hMem, v38, &v36);
        LocalFree(hMem);
        LocalFree(Buf1[0]);
        v6 = (HLOCAL *)*((_QWORD *)this + 1);
        *((_DWORD *)this + 7) = *((_DWORD *)this + 6);
        *((_DWORD *)this + 6) = 2;
        while ( v6 )
        {
          v7 = v6;
          v6 = (HLOCAL *)*v6;
          LocalFree(v7[1]);
          LocalFree(v7[2]);
          LocalFree(v7);
        }
        *((_QWORD *)this + 1) = 0;
        v8 = (_DWORD *)((char *)this + 24);
        v9 = (__int64 **)((char *)this + 8);
      }
      CGroupPolicy::PersistEnabledDenyGP(this);
      if ( !v36 )
        goto LABEL_55;
      if ( WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_bf352b66c2b13fdf6580719fc101b8b6_Traceguids);
      }
      GPDebugPrintX(2, "Policy enforcement requires system reboot\n");
      AccessCode = 3;
      WPDLibSetRegistryValue(
        0,
        v22,
        L"SYSTEM\\CurrentControlSet\\Control\\Storage\\Test",
        L"Access Code",
        4u,
        (BYTE *)&AccessCode,
        4u);
      if ( LoadStringW(g_hInstance, 0x66u, Buffer, 128) )
      {
        v39 = 0;
        v36 = 0;
        if ( !(unsigned int)WPDLibGetRegistryValue(
                              0,
                              v23,
                              L"SOFTWARE\\Policies\\Microsoft\\Windows\\RemovableStorageDevices",
                              L"RebootTimeinSeconds",
                              4,
                              &v39,
                              &v37) )
        {
          v24 = *(_DWORD *)v39;
          LocalFree(v39);
          goto LABEL_49;
        }
        if ( !(unsigned int)WPDLibGetUserRebootTime((unsigned int *)&v36) )
        {
          v24 = v36;
LABEL_49:
          v25 = StringCchPrintfW(Message, 0x80u, Buffer, v24);
          if ( v25 )
          {
            GPDebugPrintX(2, "Failed (%d) to format reboot message\n", v25);
          }
          else
          {
            v37 = 0;
            WPDLibGetRegistryValue(
              0,
              v26,
              L"SYSTEM\\CurrentControlSet\\Control\\Storage\\FeatureFlags",
              L"EnableRebootOnFailure",
              4,
              &v37,
              &v36);
            if ( v37 )
            {
              v27 = *(_DWORD *)v37;
              LocalFree(v37);
              if ( v27 )
                WPDLibRequestSystemReboot(Message, v24);
            }
          }
        }
      }
      else
      {
        LastError = GetLastError();
        GPDebugPrintX(2, "Failed (%d) to load reboot message\n", LastError);
      }
LABEL_55:
      v29 = Service_Release();
      v31 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_bf352b66c2b13fdf6580719fc101b8b6_Traceguids, v29);
      }
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)this, 0xFFFFFFFF) == 1 )
      {
        v32 = v41;
        if ( *v8 == 1 )
        {
          for ( j = *v9; j; j = (__int64 *)*j )
          {
            *(_OWORD *)Buf1 = *(_OWORD *)((char *)j + 28);
            if ( !memcmp_0(Buf1, &GUID_DEVINTERFACE_VOLUME, 0x10u) )
              goto LABEL_65;
          }
          WPDLibDeleteRegistryValue(
            (__int64)v31,
            v30,
            L"SYSTEM\\CurrentControlSet\\Control\\Storage",
            L"HotplugSecurityDescriptor");
          WPDLibDeleteRegistryValue(v35, v34, L"SYSTEM\\CurrentControlSet\\Control\\Storage", L"HotplugSecureOpen");
        }
LABEL_65:
        if ( v32 >= 0 )
          CoUninitialize();
        return;
      }
    }
  }
  if ( v2 > -1 )
    goto LABEL_12;
  if ( WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_bf352b66c2b13fdf6580719fc101b8b6_Traceguids, (unsigned int)v2);
}

```

## disassembly

```asm
0x1800069d0  mov     [rsp-8+arg_8], rbx
0x1800069d5  mov     [rsp-8+arg_10], rsi
0x1800069da  push    rbp
0x1800069db  push    rdi
0x1800069dc  push    r12
0x1800069de  push    r14
0x1800069e0  push    r15
0x1800069e2  lea     rbp, [rsp-190h]
0x1800069ea  sub     rsp, 290h
0x1800069f1  mov     rax, cs:__security_cookie
0x1800069f8  xor     rax, rsp
0x1800069fb  mov     [rbp+1B0h+var_30], rax
0x180006a02  mov     rsi, rcx
0x180006a05  mov     [rsp+2B0h+Buf1], 0
0x180006a0e  mov     [rsp+2B0h+hMem], 0
0x180006a17  mov     [rsp+2B0h+var_260], 0
0x180006a1f  mov     rcx, cs:WPP_GLOBAL_Control
0x180006a26  lea     rbx, WPP_GLOBAL_Control
0x180006a2d  lea     rdi, WPP_bf352b66c2b13fdf6580719fc101b8b6_Traceguids
0x180006a34  cmp     rcx, rbx
0x180006a37  jz      short loc_180006A53
0x180006a39  test    dword ptr [rcx+1Ch], 400h
0x180006a40  jz      short loc_180006A53
0x180006a42  mov     rcx, [rcx+10h]
0x180006a46  mov     edx, 0Eh
0x180006a4b  mov     r8, rdi
0x180006a4e  call    WPP_SF_
0x180006a53  xor     edx, edx; dwCoInit
0x180006a55  xor     ecx, ecx; pvReserved
0x180006a57  call    cs:__imp_CoInitializeEx
0x180006a5d  mov     [rsp+2B0h+var_248], eax
0x180006a61  cmp     eax, 80010106h
0x180006a66  jz      short loc_180006AA0
0x180006a68  cmp     eax, 0FFFFFFFFh
0x180006a6b  jg      short loc_180006AC6
0x180006a6d  mov     rcx, cs:WPP_GLOBAL_Control
0x180006a74  cmp     rcx, rbx
0x180006a77  jz      loc_180006FF6
0x180006a7d  test    byte ptr [rcx+1Ch], 2
0x180006a81  jz      loc_180006FF6
0x180006a87  mov     rcx, [rcx+10h]
0x180006a8b  mov     edx, 10h
0x180006a90  mov     r9d, eax
0x180006a93  mov     r8, rdi
0x180006a96  call    WPP_SF_d
0x180006a9b  jmp     loc_180006FF6
0x180006aa0  mov     rcx, cs:WPP_GLOBAL_Control
0x180006aa7  cmp     rcx, rbx
0x180006aaa  jz      short loc_180006AC6
0x180006aac  test    byte ptr [rcx+1Ch], 4
0x180006ab0  jz      short loc_180006AC6
0x180006ab2  mov     rcx, [rcx+10h]
0x180006ab6  mov     edx, 0Fh
0x180006abb  mov     r9d, eax
0x180006abe  mov     r8, rdi
0x180006ac1  call    WPP_SF_d
0x180006ac6  lea     r12, WPP_GLOBAL_Control
0x180006acd  mov     rcx, rsi; this
0x180006ad0  mov     [rsp+2B0h+var_270], 0
0x180006ad8  xor     edi, edi
0x180006ada  call    ?UpdateMdmPolicy@CGroupPolicy@@IEAAXXZ; CGroupPolicy::UpdateMdmPolicy(void)
0x180006adf  mov     edx, [rsi+20h]
0x180006ae2  lea     rax, [rsp+2B0h+var_268]
0x180006ae7  mov     [rsp+2B0h+var_280], rax
0x180006aec  lea     r9, [rsp+2B0h+hMem]
0x180006af1  lea     rax, [rsp+2B0h+var_258]
0x180006af6  mov     dword ptr [rsp+2B0h+var_258], edi
0x180006afa  mov     [rsp+2B0h+var_288], rax
0x180006aff  lea     r8, [rsp+2B0h+Buf1]
0x180006b04  lea     rax, [rsp+2B0h+var_260]
0x180006b09  mov     dword ptr [rsp+2B0h+var_268], edi
0x180006b0d  xor     ecx, ecx
0x180006b0f  mov     [rsp+2B0h+var_290], rax
0x180006b14  call    WPDLibCheckGivenDeviceGUID
0x180006b19  lea     ecx, [rdi+8]; unsigned int
0x180006b1c  test    eax, eax
0x180006b1e  jnz     loc_180006BB2
0x180006b24  lea     rdx, aDenyAllSetForA; "Deny_All set for all devices\n"
0x180006b2b  call    ?GPDebugPrintX@@YAXKPEADZZ; GPDebugPrintX(ulong,char *,...)
0x180006b30  mov     r9d, [rsp+2B0h+var_260]; unsigned int
0x180006b35  lea     rax, [rsp+2B0h+var_270]
0x180006b3a  mov     r8, [rsp+2B0h+hMem]; void *
0x180006b3f  mov     rdx, [rsp+2B0h+Buf1]; struct _ACL *
0x180006b44  mov     [rsp+2B0h+var_290], rax; int *
0x180006b49  call    ?DisableAllAccessToAllDevices@CGroupPolicy@@IEAAXPEAU_ACL@@PEAXKPEAH@Z; CGroupPolicy::DisableAllAccessToAllDevices(_ACL *,void *,ulong,int *)
0x180006b4e  mov     rcx, [rsp+2B0h+hMem]; hMem
0x180006b53  call    cs:__imp_LocalFree
0x180006b59  mov     rcx, [rsp+2B0h+Buf1]; hMem
0x180006b5e  call    cs:__imp_LocalFree
0x180006b64  mov     eax, [rsi+18h]
0x180006b67  mov     rdi, [rsi+8]
0x180006b6b  mov     [rsi+1Ch], eax
0x180006b6e  mov     dword ptr [rsi+18h], 2
0x180006b75  jmp     short loc_180006B9A
0x180006b77  mov     rbx, rdi
0x180006b7a  mov     rdi, [rdi]
0x180006b7d  mov     rcx, [rbx+8]; hMem
0x180006b81  call    cs:__imp_LocalFree
0x180006b87  mov     rcx, [rbx+10h]; hMem
0x180006b8b  call    cs:__imp_LocalFree
0x180006b91  mov     rcx, rbx; hMem
0x180006b94  call    cs:__imp_LocalFree
0x180006b9a  test    rdi, rdi
0x180006b9d  jnz     short loc_180006B77
0x180006b9f  mov     [rsi+8], rdi
0x180006ba3  lea     r15, [rsi+18h]
0x180006ba7  lea     r14, [rsi+8]
0x180006bab  xor     ebx, ebx
0x180006bad  jmp     loc_180006DAB
0x180006bb2  mov     r8d, 6
0x180006bb8  lea     rdx, aDenyAllNotSetF; "Deny_All not set for all. Will query ot"...
0x180006bbf  call    ?GPDebugPrintX@@YAXKPEADZZ; GPDebugPrintX(ulong,char *,...)
0x180006bc4  xor     ebx, ebx
0x180006bc6  lea     rcx, ?GP_WellKnown_GUIDS@@3PAU_GUID@@A; _GUID near * GP_WellKnown_GUIDS
0x180006bcd  mov     r15, rbx
0x180006bd0  shl     r15, 4
0x180006bd4  add     r15, rcx
0x180006bd7  mov     rcx, r15
0x180006bda  call    WPDLibPropagateDenyExecuteDeviceGUID
0x180006bdf  mov     edx, [rsi+20h]
0x180006be2  lea     rax, [rsp+2B0h+var_268]
0x180006be7  mov     [rsp+2B0h+var_280], rax
0x180006bec  lea     r9, [rsp+2B0h+hMem]
0x180006bf1  lea     rax, [rsp+2B0h+var_258]
0x180006bf6  mov     dword ptr [rsp+2B0h+var_258], 0
0x180006bfe  mov     [rsp+2B0h+var_288], rax
0x180006c03  lea     r8, [rsp+2B0h+Buf1]
0x180006c08  lea     rax, [rsp+2B0h+var_260]
0x180006c0d  mov     dword ptr [rsp+2B0h+var_268], 0
0x180006c15  mov     rcx, r15
0x180006c18  mov     [rsp+2B0h+var_290], rax
0x180006c1d  call    WPDLibCheckGivenDeviceGUID
0x180006c22  test    eax, eax
0x180006c24  jnz     short loc_180006C94
0x180006c26  mov     r14, [rsp+2B0h+hMem]
0x180006c2b  test    r14, r14
0x180006c2e  jz      short loc_180006C94
0x180006c30  lea     rdx, aQueryForOtherG; "Query for other GUID succeeded\n"
0x180006c37  lea     ecx, [rax+8]; unsigned int
0x180006c3a  call    ?GPDebugPrintX@@YAXKPEADZZ; GPDebugPrintX(ulong,char *,...)
0x180006c3f  mov     eax, 40h ; '@'
0x180006c44  mov     edx, eax; uBytes
0x180006c46  mov     ecx, eax; uFlags
0x180006c48  call    cs:__imp_LocalAlloc
0x180006c4e  test    rax, rax
0x180006c51  jz      short loc_180006CA8
0x180006c53  movups  xmm0, xmmword ptr [r15]
0x180006c57  mov     rcx, [rsp+2B0h+Buf1]
0x180006c5c  mov     [rax+8], rcx
0x180006c60  mov     ecx, [rsp+2B0h+var_260]
0x180006c64  mov     [rax+18h], ecx
0x180006c67  mov     ecx, dword ptr [rsp+2B0h+var_258]
0x180006c6b  mov     [rax+34h], ecx
0x180006c6e  mov     ecx, dword ptr [rsp+2B0h+var_268]
0x180006c72  mov     [rax], rdi
0x180006c75  mov     rdi, rax
0x180006c78  mov     [rax+38h], ecx
0x180006c7b  movdqu  xmmword ptr [rax+1Ch], xmm0
0x180006c80  mov     [rax+10h], r14
0x180006c84  mov     dword ptr [rax+30h], 1
0x180006c8b  mov     dword ptr [rax+3Ch], 0
0x180006c92  jmp     short loc_180006CA8
0x180006c94  mov     r8d, eax
0x180006c97  lea     rdx, aPolicyForOther; "Policy for other GUID is not enabled, s"...
0x180006c9e  mov     ecx, 8; unsigned int
0x180006ca3  call    ?GPDebugPrintX@@YAXKPEADZZ; GPDebugPrintX(ulong,char *,...)
0x180006ca8  inc     rbx
0x180006cab  cmp     rbx, 6
0x180006caf  jnz     loc_180006BC6
0x180006cb5  mov     ecx, [rsi+20h]
0x180006cb8  call    WPDLibEnumerateCustomKeys
0x180006cbd  mov     rbx, rax
0x180006cc0  test    rdi, rdi
0x180006cc3  jz      short loc_180006D0F
0x180006cc5  mov     rdx, rdi
0x180006cc8  mov     rcx, rax
0x180006ccb  call    WPDLibRemoveDuplicateEntries
0x180006cd0  mov     rdi, rax
0x180006cd3  test    rbx, rbx
0x180006cd6  jz      short loc_180006CED
0x180006cd8  test    rax, rax
0x180006cdb  jz      short loc_180006CED
0x180006cdd  mov     rcx, [rax]
0x180006ce0  test    rcx, rcx
0x180006ce3  jz      short loc_180006CEA
0x180006ce5  mov     rax, rcx
0x180006ce8  jmp     short loc_180006CD8
0x180006cea  mov     [rax], rbx
0x180006ced  test    rdi, rdi
0x180006cf0  lea     rdx, aWellKnownGuidL; "Well known GUID List %p\n"
0x180006cf7  mov     ecx, 8; unsigned int
0x180006cfc  cmovz   rdi, rbx
0x180006d00  mov     r8, rdi
0x180006d03  mov     [rsp+2B0h+var_268], rdi
0x180006d08  call    ?GPDebugPrintX@@YAXKPEADZZ; GPDebugPrintX(ulong,char *,...)
0x180006d0d  jmp     short loc_180006D1B
0x180006d0f  test    rbx, rbx
0x180006d12  cmovnz  rdi, rbx
0x180006d16  mov     [rsp+2B0h+var_268], rdi
0x180006d1b  lea     r14, [rsi+8]
0x180006d1f  mov     rdx, rdi
0x180006d22  mov     rcx, [r14]
0x180006d25  lea     r8, [rsi+10h]
0x180006d29  call    WPDLibCheckIfGPDisabled
0x180006d2e  lea     r8, [rsi+10h]
0x180006d32  mov     rcx, r14
0x180006d35  lea     rdx, [rsp+2B0h+var_268]
0x180006d3a  call    WPDLibUpdateSecurityDescriptorList
0x180006d3f  lea     r15, [rsi+18h]
0x180006d43  mov     eax, [r15]
0x180006d46  mov     [rsi+1Ch], eax
0x180006d49  mov     dword ptr [r15], 1
0x180006d50  test    eax, 0FFFFFFFDh
0x180006d55  jnz     short loc_180006D88
0x180006d57  lea     rdx, aDenyAllForAllD; "Deny_All for all devices is being reset"...
0x180006d5e  mov     ecx, 8; unsigned int
0x180006d63  call    ?GPDebugPrintX@@YAXKPEADZZ; GPDebugPrintX(ulong,char *,...)
0x180006d68  lea     rax, [rsp+2B0h+var_270]
0x180006d6d  xor     r9d, r9d; unsigned int
0x180006d70  xor     r8d, r8d; void *
0x180006d73  mov     [rsp+2B0h+var_290], rax; int *
0x180006d78  xor     edx, edx; struct _ACL *
0x180006d7a  call    ?DisableAllAccessToAllDevices@CGroupPolicy@@IEAAXPEAU_ACL@@PEAXKPEAH@Z; CGroupPolicy::DisableAllAccessToAllDevices(_ACL *,void *,ulong,int *)
0x180006d7f  or      ecx, 0FFFFFFFFh; dwTimeout
0x180006d82  call    cs:__imp_CMP_WaitNoPendingInstallEvents
0x180006d88  xor     ebx, ebx
0x180006d8a  cmp     [r14], rbx
0x180006d8d  jz      short loc_180006DAB
0x180006d8f  lea     rdx, aHaveDevicesToP; "Have devices to process\n"
0x180006d96  lea     ecx, [rbx+8]; unsigned int
0x180006d99  call    ?GPDebugPrintX@@YAXKPEADZZ; GPDebugPrintX(ulong,char *,...)
0x180006d9e  lea     rdx, [rsp+2B0h+var_270]; int *
0x180006da3  mov     rcx, rsi; this
0x180006da6  call    ?ProcessGPForDevices@CGroupPolicy@@IEAAXPEAH@Z; CGroupPolicy::ProcessGPForDevices(int *)
0x180006dab  mov     rcx, rsi; this
0x180006dae  call    ?PersistEnabledDenyGP@CGroupPolicy@@IEAAXXZ; CGroupPolicy::PersistEnabledDenyGP(void)
0x180006db3  cmp     [rsp+2B0h+var_270], ebx
0x180006db7  jz      loc_180006F47
0x180006dbd  mov     rcx, cs:WPP_GLOBAL_Control
0x180006dc4  cmp     rcx, r12
0x180006dc7  jz      short loc_180006DE4
0x180006dc9  test    byte ptr [rcx+1Ch], 2
0x180006dcd  jz      short loc_180006DE4
0x180006dcf  mov     rcx, [rcx+10h]
0x180006dd3  lea     r8, WPP_bf352b66c2b13fdf6580719fc101b8b6_Traceguids
0x180006dda  mov     edx, 11h
0x180006ddf  call    WPP_SF_
0x180006de4  lea     rdx, aPolicyEnforcem; "Policy enforcement requires system rebo"...
0x180006deb  mov     ecx, 2; unsigned int
0x180006df0  call    ?GPDebugPrintX@@YAXKPEADZZ; GPDebugPrintX(ulong,char *,...)
0x180006df5  mov     edi, 4
0x180006dfa  mov     cs:?AccessCode@@3KA, 3; ulong AccessCode
0x180006e04  lea     rax, ?AccessCode@@3KA; ulong AccessCode
0x180006e0b  mov     dword ptr [rsp+2B0h+var_280], edi
0x180006e0f  mov     [rsp+2B0h+var_288], rax
0x180006e14  lea     r9, aAccessCode; "Access Code"
0x180006e1b  lea     r8, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Control\\Sto"...
0x180006e22  mov     dword ptr [rsp+2B0h+var_290], edi
0x180006e26  xor     ecx, ecx
0x180006e28  call    WPDLibSetRegistryValue
0x180006e2d  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x180006e34  lea     r9d, [rdi+7Ch]; cchBufferMax
0x180006e38  lea     r8, [rbp+1B0h+Buffer]; lpBuffer
0x180006e3c  lea     edx, [rdi+62h]; uID
0x180006e3f  call    cs:__imp_LoadStringW
0x180006e45  test    eax, eax
0x180006e47  jz      loc_180006F2D
0x180006e4d  lea     rax, [rsp+2B0h+var_268]
0x180006e52  mov     [rsp+2B0h+var_258], rbx
0x180006e57  mov     [rsp+2B0h+var_280], rax
0x180006e5c  lea     r9, aReboottimeinse_0; "RebootTimeinSeconds"
0x180006e63  lea     rax, [rsp+2B0h+var_258]
0x180006e68  mov     [rsp+2B0h+var_270], ebx
0x180006e6c  mov     [rsp+2B0h+var_288], rax
0x180006e71  lea     r8, aSoftwarePolici_0; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x180006e78  xor     ecx, ecx
0x180006e7a  mov     dword ptr [rsp+2B0h+var_290], edi
0x180006e7e  call    WPDLibGetRegistryValue
0x180006e83  test    eax, eax
0x180006e85  jnz     short loc_180006E96
0x180006e87  mov     rcx, [rsp+2B0h+var_258]; hMem
0x180006e8c  mov     edi, [rcx]
0x180006e8e  call    cs:__imp_LocalFree
0x180006e94  jmp     short loc_180006EAC
0x180006e96  lea     rcx, [rsp+2B0h+var_270]
0x180006e9b  call    WPDLibGetUserRebootTime
0x180006ea0  test    eax, eax
0x180006ea2  jnz     loc_180006F47
0x180006ea8  mov     edi, [rsp+2B0h+var_270]
0x180006eac  mov     r9d, edi
0x180006eaf  lea     r8, [rbp+1B0h+Buffer]; unsigned __int16 *
0x180006eb3  mov     edx, 80h; unsigned __int64
0x180006eb8  lea     rcx, [rbp+1B0h+Message]; unsigned __int16 *
0x180006ebf  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180006ec4  test    eax, eax
0x180006ec6  jnz     short loc_180006F24
0x180006ec8  lea     rax, [rsp+2B0h+var_270]
0x180006ecd  mov     [rsp+2B0h+var_268], rbx
0x180006ed2  mov     [rsp+2B0h+var_280], rax
0x180006ed7  lea     r9, aEnablerebooton; "EnableRebootOnFailure"
  ... truncated ...
```
