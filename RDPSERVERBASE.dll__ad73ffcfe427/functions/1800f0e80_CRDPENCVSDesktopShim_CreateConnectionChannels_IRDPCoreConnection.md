# CRDPENCVSDesktopShim::CreateConnectionChannels(IRDPCoreConnection *)

- ea: `0x1800f0e80`
- end: `0x1800f1896`
- name: `?CreateConnectionChannels@CRDPENCVSDesktopShim@@UEAAJPEAUIRDPCoreConnection@@@Z`
- size: `2582`
- prototype: `int(CRDPENCVSDesktopShim *__hidden this, struct IRDPCoreConnection *)`
- caller_count: `0`
- callee_count: `19`
- tags: `registry_config, loader_planting`

## callees

- `0x18000cdac`
- `0x18000ce04`
- `0x18000ce34`
- `0x18002aafc`
- `0x18002b14c`
- `0x180076090`
- `0x180079724`
- `0x180079770`
- `0x18007e9e0`
- `0x18007f6b0`
- `0x1800f0b68`
- `0x1800f0d44`
- `0x1800f0e80`
- `0x1800f189c`
- `0x1800f1bf8`
- `0x1800f2480`
- `0x1800f38b0`
- `0x1800f3ecc`
- `0x18019c010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800f1364`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800f1364`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800f1464`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800f1464`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800f1327`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800f1327`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800f1388`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800f1388`
- `ntdll!NtQuerySystemInformation` at `0x1800f13a5`
- `ntdll!NtQuerySystemInformation` at `0x1800f13a5`
- `OLEAUT32!__imp_SysAllocString` at `0x1800f13dc`
- `OLEAUT32!__imp_SysAllocString` at `0x1800f13dc`
- `OLEAUT32!__imp_VariantInit` at `0x1800f13ce`
- `OLEAUT32!__imp_VariantInit` at `0x1800f13ce`
- `OLEAUT32!__imp_VariantClear` at `0x1800f1454`
- `OLEAUT32!__imp_VariantClear` at `0x1800f1454`

## string_xrefs

- `0x1800f11e8`: `Failed to create gfx vc`
- `0x1800f14c0`: `Failed to create GFX plugin`
- `0x1800f15cd`: `Failed to create Input plugin`
- `0x1800f152b`: `Failed to create input vc`
- `0x1800f16a2`: `CreateTouchPlugin failed.`
- `0x1800f1642`: `CreateAudioPlugin failed.`
- `0x1800f175a`: `Creating clipboard plugin failed.`
- `0x1800f0f1f`: `CRDPEncGfxPlugin`

## pseudocode

```c
__int64 __fastcall CRDPENCVSDesktopShim::CreateConnectionChannels(
        CRDPENCVSDesktopShim *this,
        struct IRDPCoreConnection *a2)
{
  struct CRDPMUXElement *v3; // rax
  struct CRDPMUXElement *v4; // r12
  __int64 v5; // rcx
  int GFXPlugin; // ebx
  unsigned int v7; // eax
  int v8; // edx
  const char *v9; // rcx
  int v10; // eax
  char v11; // bl
  unsigned int v12; // eax
  int v13; // eax
  char v14; // bl
  unsigned int v15; // eax
  CRDPENCVSDesktopShim *v16; // rbx
  __int64 v17; // rcx
  CRDPENCVSDesktopShim *v18; // rbx
  struct IRDPCoreConnection *v19; // r8
  CRDPENCVSDesktopShim *v20; // r13
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int16 SystemInformation[2]; // [rsp+30h] [rbp-D0h] BYREF
  int v24; // [rsp+34h] [rbp-CCh] BYREF
  CRDPENCVSDesktopShim *v25; // [rsp+38h] [rbp-C8h]
  struct IRDPCollection *v26; // [rsp+40h] [rbp-C0h] BYREF
  struct IRDPCoreChannelManager *v27; // [rsp+48h] [rbp-B8h] BYREF
  DWORD cbData; // [rsp+50h] [rbp-B0h] BYREF
  DWORD Type; // [rsp+54h] [rbp-ACh] BYREF
  __int64 v30; // [rsp+58h] [rbp-A8h] BYREF
  struct IRDPCoreVirtualChannel *v31; // [rsp+60h] [rbp-A0h] BYREF
  struct IRDPCoreVirtualChannel *v32; // [rsp+68h] [rbp-98h] BYREF
  __int64 v33; // [rsp+70h] [rbp-90h] BYREF
  HKEY hKey; // [rsp+78h] [rbp-88h] BYREF
  struct CRDPMUXElement *v35; // [rsp+80h] [rbp-80h] BYREF
  __int64 v36; // [rsp+88h] [rbp-78h] BYREF
  VARIANTARG pvarg; // [rsp+90h] [rbp-70h] BYREF
  CTSCriticalSection *v38; // [rsp+A8h] [rbp-58h]
  OLECHAR Data[264]; // [rsp+B0h] [rbp-50h] BYREF

  v25 = this;
  v24 = 0;
  v30 = 0;
  v33 = 0;
  v32 = 0;
  v31 = 0;
  v36 = 0;
  v27 = 0;
  v26 = 0;
  v35 = 0;
  v38 = (CRDPENCVSDesktopShim *)((char *)this + 88);
  CTSCriticalSection::Lock((CRDPENCVSDesktopShim *)((char *)this + 88));
  v3 = (struct CRDPMUXElement *)operator new(0x78u);
  v4 = v3;
  if ( !v3 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        47,
        WPP_ddf958eafb1132b6757b61040ed68a97_Traceguids,
        CurrentThreadActivityIdPrefix,
        -2147024882);
    }
    GFXPlugin = -2147024882;
    goto LABEL_121;
  }
  *((_DWORD *)v3 + 6) = -607474739;
  *((_DWORD *)v3 + 7) = 1;
  *((_QWORD *)v3 + 2) = "CRDPEncGfxPlugin";
  *(_QWORD *)v3 = &CTSUnknown::`vftable'{for `INonDelegatingUnknown'};
  *((_QWORD *)v3 + 1) = &CTSUnknown::`vftable'{for `CTSObject'};
  *((_DWORD *)v3 + 10) = 0;
  *(_QWORD *)v3 = &CTSAsyncResultImpl::`vftable'{for `INonDelegatingUnknown'};
  *((_QWORD *)v3 + 1) = &CRDPMUXElement::`vftable'{for `CTSObject'};
  *((_QWORD *)v3 + 4) = v3;
  *((_QWORD *)v3 + 6) = 0;
  *((_QWORD *)v3 + 7) = 0;
  *((_QWORD *)v3 + 8) = 0;
  *((_QWORD *)v3 + 9) = 0;
  *((_QWORD *)v3 + 10) = 0;
  *((_QWORD *)v3 + 11) = 0;
  *((_QWORD *)v3 + 12) = 0;
  *((_QWORD *)v3 + 13) = 0;
  *((_QWORD *)v3 + 14) = 0;
  TCntPtr<CFakeGfxProvider>::SafeRelease(&v35);
  v5 = *((_QWORD *)v4 + 4);
  v35 = v4;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 8LL))(v5);
  if ( a2 != *((struct IRDPCoreConnection **)v4 + 11) )
  {
    TCntPtr<IRdpVCMgr>::SafeRelease((char *)v4 + 88);
    *((_QWORD *)v4 + 11) = a2;
    TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef((char *)v4 + 88);
  }
  GFXPlugin = (*(__int64 (__fastcall **)(struct IRDPCoreConnection *, struct IRDPCollection **))(*(_QWORD *)a2 + 80LL))(
                a2,
                &v26);
  if ( GFXPlugin < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v7 = RdpWppGetCurrentThreadActivityIdPrefix();
      v8 = 49;
      v9 = "Failed to get IRDPCOllection from Connection object";
LABEL_9:
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v8,
        (unsigned int)WPP_ddf958eafb1132b6757b61040ed68a97_Traceguids,
        v7,
        (__int64)v9,
        GFXPlugin);
      goto LABEL_121;
    }
    goto LABEL_121;
  }
  GFXPlugin = (*(__int64 (__fastcall **)(struct IRDPCoreConnection *, __int64 *))(*(_QWORD *)a2 + 64LL))(a2, &v30);
  if ( GFXPlugin < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v7 = RdpWppGetCurrentThreadActivityIdPrefix();
      v8 = 50;
      v9 = "Failed to get_ChannelManager";
      goto LABEL_9;
    }
    goto LABEL_121;
  }
  v10 = (*(__int64 (__fastcall **)(struct IRDPCollection *, const wchar_t *, int *))(*(_QWORD *)v26 + 32LL))(
          v26,
          L"EnableFakeVCMgr",
          &v24);
  v11 = v10;
  if ( v10 < 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v12 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      51,
      (unsigned int)WPP_ddf958eafb1132b6757b61040ed68a97_Traceguids,
      v12,
      (__int64)"Failed to get enable Fake VC Mgr property",
      v11);
  }
  if ( v24 )
  {
    GFXPlugin = (*(__int64 (__fastcall **)(struct IRDPCoreConnection *, __int64 *))(*(_QWORD *)a2 + 72LL))(a2, &v33);
    if ( GFXPlugin < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v7 = RdpWppGetCurrentThreadActivityIdPrefix();
        v8 = 52;
        v9 = "Failed to get Fake VC Mgr";
        goto LABEL_9;
      }
      goto LABEL_121;
    }
    GFXPlugin = (*(__int64 (__fastcall **)(__int64, const char *, _QWORD, struct IRDPCoreVirtualChannel **))(*(_QWORD *)v33 + 24LL))(
                  v33,
                  "rdpgrfx",
                  0,
                  &v32);
    if ( GFXPlugin < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_121;
      }
      v7 = RdpWppGetCurrentThreadActivityIdPrefix();
      v8 = 53;
      goto LABEL_31;
    }
  }
  else
  {
    GFXPlugin = (*(__int64 (__fastcall **)(__int64, const char *, _QWORD, struct IRDPCoreVirtualChannel **))(*(_QWORD *)v30 + 24LL))(
                  v30,
                  "rdpgrfx",
                  0,
                  &v32);
    if ( GFXPlugin < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_121;
      }
      v7 = RdpWppGetCurrentThreadActivityIdPrefix();
      v8 = 54;
LABEL_31:
      v9 = "Failed to create gfx vc";
      goto LABEL_9;
    }
  }
  GFXPlugin = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v30)(v30, &IID_IRdpVCMgr, &v36);
  if ( GFXPlugin < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v7 = RdpWppGetCurrentThreadActivityIdPrefix();
      v8 = 55;
      v9 = "Failed to QI IRdpVCMgr interface";
      goto LABEL_9;
    }
    goto LABEL_121;
  }
  GFXPlugin = (*(__int64 (__fastcall **)(__int64, struct IRDPCoreChannelManager **))(*(_QWORD *)v36 + 32LL))(v36, &v27);
  if ( GFXPlugin < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v7 = RdpWppGetCurrentThreadActivityIdPrefix();
      v8 = 56;
      v9 = "Failed to get DVC manager";
      goto LABEL_9;
    }
    goto LABEL_121;
  }
  cbData = 0;
  Type = 0;
  hKey = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"System\\CurrentControlSet\\Control\\Terminal Server\\WinStations",
          0,
          0x20019u,
          &hKey) )
  {
    cbData = 520;
    if ( !RegQueryValueExW(hKey, L"RecordCollabGFXData", 0, &Type, (LPBYTE)Data, &cbData) && Type == 1 )
    {
      if ( v26 )
      {
        if ( IsDebuggerPresent()
          || (SystemInformation[0] = 0,
              NtQuerySystemInformation(SystemKernelDebuggerInformation, SystemInformation, 2u, 0) >= 0)
          && LOBYTE(SystemInformation[0]) )
        {
          memset(&pvarg, 0, sizeof(pvarg));
          VariantInit(&pvarg);
          pvarg.vt = 8;
          pvarg.llVal = (LONGLONG)SysAllocString(Data);
          v13 = (*(__int64 (__fastcall **)(struct IRDPCollection *, const wchar_t *, VARIANTARG *))(*(_QWORD *)v26 + 56LL))(
                  v26,
                  L"RecordingEnabled",
                  &pvarg);
          v14 = v13;
          if ( v13 < 0
            && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v15 = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_DsD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              57,
              (unsigned int)WPP_ddf958eafb1132b6757b61040ed68a97_Traceguids,
              v15,
              (__int64)"Failed to set enable recording propery",
              v14);
          }
          VariantClear(&pvarg);
        }
      }
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  GFXPlugin = CRDPENCVSDesktopShim::CreateGFXPlugin((CRDPENCVSDesktopShim *)((char *)v25 - 16), v32, v27, v26, v4);
  if ( GFXPlugin < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v7 = RdpWppGetCurrentThreadActivityIdPrefix();
      v8 = 58;
      v9 = "Failed to create GFX plugin";
      goto LABEL_9;
    }
    goto LABEL_121;
  }
  if ( v24 )
  {
    GFXPlugin = (*(__int64 (__fastcall **)(__int64, const char *, _QWORD, struct IRDPCoreVirtualChannel **))(*(_QWORD *)v33 + 24LL))(
                  v33,
                  "rdpinpt",
                  0,
                  &v31);
    if ( GFXPlugin < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_121;
      }
      v7 = RdpWppGetCurrentThreadActivityIdPrefix();
      v8 = 59;
      goto LABEL_73;
    }
  }
  else
  {
    GFXPlugin = (*(__int64 (__fastcall **)(__int64, const char *, _QWORD, struct IRDPCoreVirtualChannel **))(*(_QWORD *)v30 + 24LL))(
                  v30,
                  "rdpinpt",
                  0,
                  &v31);
    if ( GFXPlugin < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_121;
      }
      v7 = RdpWppGetCurrentThreadActivityIdPrefix();
      v8 = 60;
LABEL_73:
      v9 = "Failed to create input vc";
      goto LABEL_9;
    }
  }
  GFXPlugin = CRDPENCVSDesktopShim::CreateInputPlugin((CRDPENCVSDesktopShim *)((char *)v25 - 16), v31, v26, v4);
  if ( GFXPlugin >= 0 )
  {
    v16 = v25;
    v17 = *((_QWORD *)v25 + 24);
    if ( v17 && (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v17 + 40LL))(v17) )
    {
      GFXPlugin = CRDPENCVSDesktopShim::CreateAudioPlugin((CRDPENCVSDesktopShim *)((char *)v16 - 16), v27, a2, v4);
      if ( GFXPlugin < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v7 = RdpWppGetCurrentThreadActivityIdPrefix();
          v8 = 62;
          v9 = "CreateAudioPlugin failed.";
          goto LABEL_9;
        }
        goto LABEL_121;
      }
      v16 = v25;
    }
    if ( !*((_QWORD *)v16 + 25)
      || (GFXPlugin = CRDPENCVSDesktopShim::CreateTouchPlugin((CRDPENCVSDesktopShim *)((char *)v16 - 16), v27, v4),
          GFXPlugin >= 0) )
    {
      v18 = v25;
      if ( (unsigned int)CRDPENCVSDesktopShim::IsClipboardRedirectionEnabled((CRDPENCVSDesktopShim *)((char *)v25 - 16)) )
      {
        GFXPlugin = CRDPENCVSDesktopShim::InitializeClipboardRedirection((CRDPENCVSDesktopShim *)((char *)v18 - 16));
        if ( GFXPlugin < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v7 = RdpWppGetCurrentThreadActivityIdPrefix();
            v8 = 64;
            v9 = "Initializing clipboard redirection failed.";
            goto LABEL_9;
          }
          goto LABEL_121;
        }
        v19 = a2;
        v20 = v25;
        GFXPlugin = CRDPENCVSDesktopShim::CreateClipboardPlugin(
                      (CRDPENCVSDesktopShim *)((char *)v25 - 16),
                      v27,
                      v19,
                      v4);
        if ( GFXPlugin < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v7 = RdpWppGetCurrentThreadActivityIdPrefix();
            v8 = 65;
            v9 = "Creating clipboard plugin failed.";
            goto LABEL_9;
          }
          goto LABEL_121;
        }
      }
      else
      {
        v20 = v18;
      }
      GFXPlugin = (*(__int64 (__fastcall **)(__int64, struct CRDPMUXElement *))(*((_QWORD *)v20 + 14) + 8LL))(
                    (__int64)v20 + 112,
                    v4);
      if ( GFXPlugin >= 0 )
      {
        ++*((_DWORD *)v20 + 63);
        goto LABEL_121;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v7 = RdpWppGetCurrentThreadActivityIdPrefix();
        v8 = 66;
        v9 = "Failed to add elemnent to the array";
        goto LABEL_9;
      }
      goto LABEL_121;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v7 = RdpWppGetCurrentThreadActivityIdPrefix();
      v8 = 63;
      v9 = "CreateTouchPlugin failed.";
      goto LABEL_9;
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v7 = RdpWppGetCurrentThreadActivityIdPrefix();
    v8 = 61;
    v9 = "Failed to create Input plugin";
    goto LABEL_9;
  }
LABEL_121:
  CTSCriticalSection::UnLock(v38);
  TCntPtr<CFakeGfxProvider>::SafeRelease(&v35);
  TCntPtr<IRdpVCMgr>::SafeRelease(&v26);
  TCntPtr<IRdpVCMgr>::SafeRelease(&v27);
  TCntPtr<IRdpVCMgr>::SafeRelease(&v36);
  TCntPtr<IRdpVCMgr>::SafeRelease(&v31);
  TCntPtr<IRdpVCMgr>::SafeRelease(&v32);
  TCntPtr<IRdpVCMgr>::SafeRelease(&v33);
  TCntPtr<IRdpVCMgr>::SafeRelease(&v30);
  return (unsigned int)GFXPlugin;
}

```

## disassembly

```asm
0x1800f0e80  mov     [rsp-8+arg_10], rbx
0x1800f0e85  push    rbp
0x1800f0e86  push    rsi
0x1800f0e87  push    rdi
0x1800f0e88  push    r12
0x1800f0e8a  push    r13
0x1800f0e8c  push    r14
0x1800f0e8e  push    r15
0x1800f0e90  lea     rbp, [rsp-1D0h]
0x1800f0e98  sub     rsp, 2D0h
0x1800f0e9f  mov     rax, cs:__security_cookie
0x1800f0ea6  xor     rax, rsp
0x1800f0ea9  mov     [rbp+200h+var_40], rax
0x1800f0eb0  xor     edi, edi
0x1800f0eb2  mov     [rsp+300h+var_2C8], rcx
0x1800f0eb7  mov     rax, rcx
0x1800f0eba  mov     [rsp+300h+var_2CC], edi
0x1800f0ebe  add     rax, 58h ; 'X'
0x1800f0ec2  mov     [rsp+300h+var_2A8], rdi
0x1800f0ec7  mov     rcx, rax; this
0x1800f0eca  mov     [rsp+300h+var_290], rdi
0x1800f0ecf  mov     r13, rdx
0x1800f0ed2  mov     [rsp+300h+var_298], rdi
0x1800f0ed7  mov     [rsp+300h+var_2A0], rdi
0x1800f0edc  mov     [rbp+200h+var_278], rdi
0x1800f0ee0  mov     [rsp+300h+var_2B8], rdi
0x1800f0ee5  mov     [rsp+300h+var_2C0], rdi
0x1800f0eea  mov     [rbp+200h+var_280], rdi
0x1800f0eee  mov     [rbp+200h+var_258], rax
0x1800f0ef2  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x1800f0ef7  lea     ecx, [rdi+78h]; Size
0x1800f0efa  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800f0eff  mov     r12, rax
0x1800f0f02  test    rax, rax
0x1800f0f05  jz      loc_1800F17BD
0x1800f0f0b  mov     dword ptr [rax+18h], 0DBCAABCDh
0x1800f0f12  lea     rcx, [rbp+200h+var_280]
0x1800f0f16  mov     dword ptr [r12+1Ch], 1
0x1800f0f1f  lea     rax, aCrdpencgfxplug; "CRDPEncGfxPlugin"
0x1800f0f26  mov     [r12+10h], rax
0x1800f0f2b  lea     rax, ??_7CTSUnknown@@6BINonDelegatingUnknown@@@; const CTSUnknown::`vftable'{for `INonDelegatingUnknown'}
0x1800f0f32  mov     [r12], rax
0x1800f0f36  lea     rax, ??_7CTSUnknown@@6BCTSObject@@@; const CTSUnknown::`vftable'{for `CTSObject'}
0x1800f0f3d  mov     [r12+8], rax
0x1800f0f42  lea     rax, ??_7CTSAsyncResultImpl@@6BINonDelegatingUnknown@@@; const CTSAsyncResultImpl::`vftable'{for `INonDelegatingUnknown'}
0x1800f0f49  mov     [r12+28h], edi
0x1800f0f4e  mov     [r12], rax
0x1800f0f52  lea     rax, ??_7CRDPMUXElement@@6BCTSObject@@@; const CRDPMUXElement::`vftable'{for `CTSObject'}
0x1800f0f59  mov     [r12+8], rax
0x1800f0f5e  mov     [r12+20h], r12
0x1800f0f63  mov     [r12+30h], rdi
0x1800f0f68  mov     [r12+38h], rdi
0x1800f0f6d  mov     [r12+40h], rdi
0x1800f0f72  mov     [r12+48h], rdi
0x1800f0f77  mov     [r12+50h], rdi
0x1800f0f7c  mov     [r12+58h], rdi
0x1800f0f81  mov     [r12+60h], rdi
0x1800f0f86  mov     [r12+68h], rdi
0x1800f0f8b  mov     [r12+70h], rdi
0x1800f0f90  call    ?SafeRelease@?$TCntPtr@VCFakeGfxProvider@@@@AEAAXXZ; TCntPtr<CFakeGfxProvider>::SafeRelease(void)
0x1800f0f95  mov     rcx, [r12+20h]
0x1800f0f9a  mov     [rbp+200h+var_280], r12
0x1800f0f9e  mov     rax, [rcx]
0x1800f0fa1  mov     rax, [rax+8]
0x1800f0fa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f0faa  lea     rbx, [r12+58h]
0x1800f0faf  cmp     r13, [rbx]
0x1800f0fb2  jz      short loc_1800F0FC7
0x1800f0fb4  mov     rcx, rbx
0x1800f0fb7  call    ?SafeRelease@?$TCntPtr@UIRdpVCMgr@@@@AEAAXXZ; TCntPtr<IRdpVCMgr>::SafeRelease(void)
0x1800f0fbc  mov     rcx, rbx
0x1800f0fbf  mov     [rbx], r13
0x1800f0fc2  call    ?SafeAddRef@?$TCntPtr@UIRDPWDUMX_StackEx@@@@AEAAXXZ; TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(void)
0x1800f0fc7  mov     rax, [r13+0]
0x1800f0fcb  lea     rdx, [rsp+300h+var_2C0]
0x1800f0fd0  mov     rcx, r13
0x1800f0fd3  mov     rax, [rax+50h]
0x1800f0fd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f0fdc  mov     ebx, eax
0x1800f0fde  test    eax, eax
0x1800f0fe0  jns     short loc_1800F104C
0x1800f0fe2  mov     rax, cs:WPP_GLOBAL_Control
0x1800f0fe9  lea     r14, WPP_GLOBAL_Control
0x1800f0ff0  cmp     rax, r14
0x1800f0ff3  jz      loc_1800F1813
0x1800f0ff9  mov     esi, 8
0x1800f0ffe  test    [rax+1Ch], sil
0x1800f1002  jz      loc_1800F1813
0x1800f1008  lea     edi, [rsi-6]
0x1800f100b  cmp     [rax+19h], dil
0x1800f100f  jb      loc_1800F1813
0x1800f1015  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800f101a  lea     edx, [rsi+29h]
0x1800f101d  lea     rcx, aFailedToGetIrd; "Failed to get IRDPCOllection from Conne"...
0x1800f1024  lea     r8, WPP_ddf958eafb1132b6757b61040ed68a97_Traceguids
0x1800f102b  mov     dword ptr [rsp+300h+lpcbData], ebx
0x1800f102f  mov     r9d, eax
0x1800f1032  mov     [rsp+300h+phkResult], rcx
0x1800f1037  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f103e  mov     rcx, [rcx+10h]
0x1800f1042  call    WPP_SF_DsD
0x1800f1047  jmp     loc_1800F1813
0x1800f104c  mov     rax, [r13+0]
0x1800f1050  lea     rdx, [rsp+300h+var_2A8]
0x1800f1055  mov     rcx, r13
0x1800f1058  mov     rax, [rax+40h]
0x1800f105c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f1061  mov     ebx, eax
0x1800f1063  test    eax, eax
0x1800f1065  jns     short loc_1800F10AE
0x1800f1067  mov     rax, cs:WPP_GLOBAL_Control
0x1800f106e  lea     r14, WPP_GLOBAL_Control
0x1800f1075  cmp     rax, r14
0x1800f1078  jz      loc_1800F1813
0x1800f107e  mov     esi, 8
0x1800f1083  test    [rax+1Ch], sil
0x1800f1087  jz      loc_1800F1813
0x1800f108d  lea     edi, [rsi-6]
0x1800f1090  cmp     [rax+19h], dil
0x1800f1094  jb      loc_1800F1813
0x1800f109a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800f109f  lea     edx, [rsi+2Ah]
0x1800f10a2  lea     rcx, aFailedToGetCha; "Failed to get_ChannelManager"
0x1800f10a9  jmp     loc_1800F1024
0x1800f10ae  mov     rcx, [rsp+300h+var_2C0]
0x1800f10b3  lea     r8, [rsp+300h+var_2CC]
0x1800f10b8  lea     rdx, aEnablefakevcmg; "EnableFakeVCMgr"
0x1800f10bf  mov     rax, [rcx]
0x1800f10c2  mov     rax, [rax+20h]
0x1800f10c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f10cb  lea     r15, WPP_ddf958eafb1132b6757b61040ed68a97_Traceguids
0x1800f10d2  mov     edi, 2
0x1800f10d7  lea     r14, WPP_GLOBAL_Control
0x1800f10de  mov     ebx, eax
0x1800f10e0  lea     esi, [rdi+6]
0x1800f10e3  test    eax, eax
0x1800f10e5  jns     short loc_1800F112D
0x1800f10e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f10ee  cmp     rcx, r14
0x1800f10f1  jz      short loc_1800F112D
0x1800f10f3  test    [rcx+1Ch], sil
0x1800f10f7  jz      short loc_1800F112D
0x1800f10f9  cmp     [rcx+19h], dil
0x1800f10fd  jb      short loc_1800F112D
0x1800f10ff  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800f1104  lea     rcx, aFailedToGetEna_0; "Failed to get enable Fake VC Mgr proper"...
0x1800f110b  mov     dword ptr [rsp+300h+lpcbData], ebx
0x1800f110f  mov     [rsp+300h+phkResult], rcx
0x1800f1114  lea     edx, [rdi+31h]
0x1800f1117  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f111e  mov     r9d, eax
0x1800f1121  mov     r8, r15
0x1800f1124  mov     rcx, [rcx+10h]
0x1800f1128  call    WPP_SF_DsD
0x1800f112d  cmp     [rsp+300h+var_2CC], 0
0x1800f1132  jz      loc_1800F11F1
0x1800f1138  mov     rax, [r13+0]
0x1800f113c  lea     rdx, [rsp+300h+var_290]
0x1800f1141  mov     rcx, r13
0x1800f1144  mov     rax, [rax+48h]
0x1800f1148  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f114d  mov     ebx, eax
0x1800f114f  test    eax, eax
0x1800f1151  jns     short loc_1800F1190
0x1800f1153  mov     rax, cs:WPP_GLOBAL_Control
0x1800f115a  cmp     rax, r14
0x1800f115d  jz      loc_1800F1813
0x1800f1163  test    [rax+1Ch], sil
0x1800f1167  jz      loc_1800F1813
0x1800f116d  cmp     [rax+19h], dil
0x1800f1171  jb      loc_1800F1813
0x1800f1177  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800f117c  mov     edx, 34h ; '4'
0x1800f1181  lea     rcx, aFailedToGetFak; "Failed to get Fake VC Mgr"
0x1800f1188  mov     r8, r15
0x1800f118b  jmp     loc_1800F102B
0x1800f1190  mov     rcx, [rsp+300h+var_290]
0x1800f1195  lea     r9, [rsp+300h+var_298]
0x1800f119a  xor     r8d, r8d
0x1800f119d  lea     rdx, aRdpgrfx_0; "rdpgrfx"
0x1800f11a4  mov     rax, [rcx]
0x1800f11a7  mov     rax, [rax+18h]
0x1800f11ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f11b0  mov     ebx, eax
0x1800f11b2  test    eax, eax
0x1800f11b4  jns     loc_1800F1247
0x1800f11ba  mov     rax, cs:WPP_GLOBAL_Control
0x1800f11c1  cmp     rax, r14
0x1800f11c4  jz      loc_1800F1813
0x1800f11ca  test    [rax+1Ch], sil
0x1800f11ce  jz      loc_1800F1813
0x1800f11d4  cmp     [rax+19h], dil
0x1800f11d8  jb      loc_1800F1813
0x1800f11de  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800f11e3  mov     edx, 35h ; '5'
0x1800f11e8  lea     rcx, aFailedToCreate_86; "Failed to create gfx vc"
0x1800f11ef  jmp     short loc_1800F1188
0x1800f11f1  mov     rcx, [rsp+300h+var_2A8]
0x1800f11f6  lea     r9, [rsp+300h+var_298]
0x1800f11fb  xor     r8d, r8d
0x1800f11fe  lea     rdx, aRdpgrfx_0; "rdpgrfx"
0x1800f1205  mov     rax, [rcx]
0x1800f1208  mov     rax, [rax+18h]
0x1800f120c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f1211  mov     ebx, eax
0x1800f1213  test    eax, eax
0x1800f1215  jns     short loc_1800F1247
0x1800f1217  mov     rax, cs:WPP_GLOBAL_Control
0x1800f121e  cmp     rax, r14
0x1800f1221  jz      loc_1800F1813
0x1800f1227  test    [rax+1Ch], sil
0x1800f122b  jz      loc_1800F1813
0x1800f1231  cmp     [rax+19h], dil
0x1800f1235  jb      loc_1800F1813
0x1800f123b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800f1240  mov     edx, 36h ; '6'
0x1800f1245  jmp     short loc_1800F11E8
0x1800f1247  mov     rcx, [rsp+300h+var_2A8]
0x1800f124c  lea     r8, [rbp+200h+var_278]
0x1800f1250  lea     rdx, IID_IRdpVCMgr
0x1800f1257  mov     rax, [rcx]
0x1800f125a  mov     rax, [rax]
0x1800f125d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f1262  mov     ebx, eax
0x1800f1264  test    eax, eax
0x1800f1266  jns     short loc_1800F12A2
0x1800f1268  mov     rax, cs:WPP_GLOBAL_Control
0x1800f126f  cmp     rax, r14
0x1800f1272  jz      loc_1800F1813
0x1800f1278  test    [rax+1Ch], sil
0x1800f127c  jz      loc_1800F1813
0x1800f1282  cmp     [rax+19h], dil
0x1800f1286  jb      loc_1800F1813
0x1800f128c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800f1291  mov     edx, 37h ; '7'
0x1800f1296  lea     rcx, aFailedToQiIrdp; "Failed to QI IRdpVCMgr interface"
0x1800f129d  jmp     loc_1800F1188
0x1800f12a2  mov     rcx, [rbp+200h+var_278]
0x1800f12a6  lea     rdx, [rsp+300h+var_2B8]
0x1800f12ab  mov     rax, [rcx]
0x1800f12ae  mov     rax, [rax+20h]
0x1800f12b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f12b7  mov     ebx, eax
0x1800f12b9  test    eax, eax
0x1800f12bb  jns     short loc_1800F12F7
0x1800f12bd  mov     rax, cs:WPP_GLOBAL_Control
0x1800f12c4  cmp     rax, r14
0x1800f12c7  jz      loc_1800F1813
0x1800f12cd  test    [rax+1Ch], sil
0x1800f12d1  jz      loc_1800F1813
0x1800f12d7  cmp     [rax+19h], dil
0x1800f12db  jb      loc_1800F1813
0x1800f12e1  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800f12e6  mov     edx, 38h ; '8'
0x1800f12eb  lea     rcx, aFailedToGetDvc; "Failed to get DVC manager"
0x1800f12f2  jmp     loc_1800F1188
0x1800f12f7  xor     ebx, ebx
0x1800f12f9  lea     rax, [rsp+300h+hKey]
0x1800f12fe  mov     r9d, 20019h; samDesired
0x1800f1304  mov     [rsp+300h+cbData], ebx
0x1800f1308  xor     r8d, r8d; ulOptions
0x1800f130b  mov     [rsp+300h+Type], ebx
0x1800f130f  lea     rdx, aSystemCurrentc_0; "System\\CurrentControlSet\\Control\\Ter"...
0x1800f1316  mov     [rsp+300h+hKey], rbx
0x1800f131b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800f1322  mov     [rsp+300h+phkResult], rax; phkResult
0x1800f1327  call    cs:__imp_RegOpenKeyExW
0x1800f132d  test    eax, eax
0x1800f132f  jnz     loc_1800F145A
0x1800f1335  mov     rcx, [rsp+300h+hKey]; hKey
0x1800f133a  lea     rax, [rsp+300h+cbData]
0x1800f133f  mov     [rsp+300h+lpcbData], rax; lpcbData
0x1800f1344  lea     r9, [rsp+300h+Type]; lpType
0x1800f1349  lea     rax, [rbp+200h+Data]
0x1800f134d  mov     [rsp+300h+cbData], 208h
0x1800f1355  xor     r8d, r8d; lpReserved
0x1800f1358  mov     [rsp+300h+phkResult], rax; lpData
0x1800f135d  lea     rdx, aRecordcollabgf; "RecordCollabGFXData"
0x1800f1364  call    cs:__imp_RegQueryValueExW
0x1800f136a  test    eax, eax
0x1800f136c  jnz     loc_1800F145A
0x1800f1372  cmp     [rsp+300h+Type], 1
0x1800f1377  jnz     loc_1800F145A
0x1800f137d  cmp     [rsp+300h+var_2C0], rbx
0x1800f1382  jz      loc_1800F145A
0x1800f1388  call    cs:__imp_IsDebuggerPresent
0x1800f138e  test    eax, eax
0x1800f1390  jnz     short loc_1800F13BD
0x1800f1392  xor     r9d, r9d; ReturnLength
0x1800f1395  mov     [rsp+300h+SystemInformation], bx
0x1800f139a  mov     r8d, edi; SystemInformationLength
0x1800f139d  lea     rdx, [rsp+300h+SystemInformation]; SystemInformation
0x1800f13a2  lea     ecx, [rbx+23h]; SystemInformationClass
0x1800f13a5  call    cs:__imp_NtQuerySystemInformation
0x1800f13ab  test    eax, eax
0x1800f13ad  js      loc_1800F145A
0x1800f13b3  cmp     byte ptr [rsp+300h+SystemInformation], bl
0x1800f13b7  jz      loc_1800F145A
0x1800f13bd  xorps   xmm0, xmm0
0x1800f13c0  lea     rcx, [rbp+200h+pvarg]; pvarg
  ... truncated ...
```
