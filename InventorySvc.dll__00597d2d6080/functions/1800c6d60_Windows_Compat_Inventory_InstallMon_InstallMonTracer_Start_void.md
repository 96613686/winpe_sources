# Windows::Compat::Inventory::InstallMon::InstallMonTracer::Start(void)

- ea: `0x1800c6d60`
- end: `0x1800c6e79`
- name: `?Start@InstallMonTracer@InstallMon@Inventory@Compat@Windows@@UEAAJXZ`
- size: `281`
- prototype: `__int64 __fastcall(Windows::Compat::Inventory::InstallMon::InstallMonTracer *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180010b74`
- `0x1800152d0`
- `0x180031b3c`
- `0x1800c6d60`
- `0x1800c6eac`
- `0x1800d1010`

## string_xrefs

- `0x1800c6e5d`: `InventorySvc successfully called StartInstallMonitoring`
- `0x1800c6db6`: `Windows::Compat::Inventory::InstallMon::InstallMonHost::Start`
- `0x1800c6e64`: `Windows::Compat::Inventory::InstallMon::InstallMonHost::Start`
- `0x1800c6daf`: `Failed starting INSTALLMON monitor [%#x]`
- `0x1800c6df9`: `Failed to initialize InstallMon APIs [%#x]`
- `0x1800c6d82`: `Install Monitoring - Feature_InstallTracingV2 is not enabled.`
- `0x1800c6e30`: `StartInstallMonitoring [%#x]`
- `0x1800c6d8f`: `Windows::Compat::Inventory::InstallMonApi::StartInstallMonitoring`
- `0x1800c6e3f`: `Windows::Compat::Inventory::InstallMonApi::StartInstallMonitoring`

## pseudocode

```c
__int64 __fastcall Windows::Compat::Inventory::InstallMon::InstallMonTracer::Start(
        Windows::Compat::Inventory::InstallMon::InstallMonTracer *this)
{
  unsigned int v2; // ebx
  int v4; // edi
  __int64 v5; // rcx
  const char *v6; // r9
  __int64 v7; // r8
  int v8; // [rsp+20h] [rbp-18h]

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_InstallTracingV2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_InstallTracingV2>::GetImpl'::`2'::impl) )
  {
    v4 = Windows::Compat::Inventory::InstallMonApi::InitializeApis((Windows::Compat::Inventory::InstallMonApi *)&Windows::Compat::Inventory::InstallMonApi::s_InstallMonApis);
    if ( v4 >= 0 )
    {
      if ( qword_1800FF108 && byte_1800FF128 )
        v4 = qword_1800FF108(Windows::Compat::Inventory::InstallMon::InstallMonHost::InstallMonitorCallback);
      v5 = 3;
      v6 = "StartInstallMonitoring [%#x]";
      v7 = 191;
    }
    else
    {
      v5 = 1;
      v6 = "Failed to initialize InstallMon APIs [%#x]";
      v7 = 182;
    }
    v2 = v4;
    v8 = v4;
    AslLogCallPrintf(v5, "Windows::Compat::Inventory::InstallMonApi::StartInstallMonitoring", v7, v6, v8);
    if ( v4 >= 0 )
    {
      AslLogCallPrintf(
        3,
        "Windows::Compat::Inventory::InstallMon::InstallMonHost::Start",
        50,
        "InventorySvc successfully called StartInstallMonitoring");
      goto LABEL_4;
    }
  }
  else
  {
    AslLogCallPrintf(
      3,
      "Windows::Compat::Inventory::InstallMonApi::StartInstallMonitoring",
      173,
      "Install Monitoring - Feature_InstallTracingV2 is not enabled.");
    v2 = -2147467263;
  }
  AslLogCallPrintf(
    1,
    "Windows::Compat::Inventory::InstallMon::InstallMonHost::Start",
    54,
    "Failed starting INSTALLMON monitor [%#x]",
    v2);
LABEL_4:
  Windows::Compat::Inventory::Service::Tracer::LogStart(this, v2);
  return v2;
}

```

## disassembly

```asm
0x1800c6d60  mov     [rsp+arg_0], rbx
0x1800c6d65  mov     [rsp+arg_8], rsi
0x1800c6d6a  push    rdi
0x1800c6d6b  sub     rsp, 30h
0x1800c6d6f  mov     rsi, rcx
0x1800c6d72  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_InstallTracingV2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_InstallTracingV2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_InstallTracingV2> `wil::Feature<__WilFeatureTraits_Feature_InstallTracingV2>::GetImpl(void)'::`2'::impl
0x1800c6d79  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_InstallTracingV2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_InstallTracingV2>::__private_IsEnabled(void)
0x1800c6d7e  test    al, al
0x1800c6d80  jnz     short loc_1800C6DE2
0x1800c6d82  lea     r9, aInstallMonitor; "Install Monitoring - Feature_InstallTra"...
0x1800c6d89  mov     r8d, 0ADh
0x1800c6d8f  lea     rdx, aWindowsCompatI_1; "Windows::Compat::Inventory::InstallMonA"...
0x1800c6d96  mov     ecx, 3
0x1800c6d9b  call    AslLogCallPrintf
0x1800c6da0  mov     ebx, 80004001h
0x1800c6da5  mov     r8d, 36h ; '6'
0x1800c6dab  mov     [rsp+38h+var_18], ebx
0x1800c6daf  lea     r9, aFailedStarting; "Failed starting INSTALLMON monitor [%#x"...
0x1800c6db6  lea     rdx, aWindowsCompatI_53; "Windows::Compat::Inventory::InstallMon:"...
0x1800c6dbd  lea     ecx, [r8-35h]
0x1800c6dc1  call    AslLogCallPrintf
0x1800c6dc6  mov     edx, ebx; int
0x1800c6dc8  mov     rcx, rsi; this
0x1800c6dcb  call    ?LogStart@Tracer@Service@Inventory@Compat@Windows@@IEAAJJ@Z; Windows::Compat::Inventory::Service::Tracer::LogStart(long)
0x1800c6dd0  mov     rsi, [rsp+38h+arg_8]
0x1800c6dd5  mov     eax, ebx
0x1800c6dd7  mov     rbx, [rsp+38h+arg_0]
0x1800c6ddc  add     rsp, 30h
0x1800c6de0  pop     rdi
0x1800c6de1  retn
0x1800c6de2  lea     rcx, ?s_InstallMonApis@InstallMonApi@Inventory@Compat@Windows@@0V1234@A; this
0x1800c6de9  call    ?InitializeApis@InstallMonApi@Inventory@Compat@Windows@@QEAAJXZ; Windows::Compat::Inventory::InstallMonApi::InitializeApis(void)
0x1800c6dee  mov     edi, eax
0x1800c6df0  test    eax, eax
0x1800c6df2  jns     short loc_1800C6E08
0x1800c6df4  mov     ecx, 1
0x1800c6df9  lea     r9, aFailedToInitia_0; "Failed to initialize InstallMon APIs [%"...
0x1800c6e00  mov     r8d, 0B6h
0x1800c6e06  jmp     short loc_1800C6E3D
0x1800c6e08  mov     rax, cs:qword_1800FF108
0x1800c6e0f  test    rax, rax
0x1800c6e12  jz      short loc_1800C6E2B
0x1800c6e14  cmp     cs:byte_1800FF128, 0
0x1800c6e1b  jz      short loc_1800C6E2B
0x1800c6e1d  lea     rcx, ?InstallMonitorCallback@InstallMonHost@InstallMon@Inventory@Compat@Windows@@SAXPEAU_INSTALLMON_INSTALLER@@@Z; Windows::Compat::Inventory::InstallMon::InstallMonHost::InstallMonitorCallback(_INSTALLMON_INSTALLER *)
0x1800c6e24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c6e29  mov     edi, eax
0x1800c6e2b  mov     ecx, 3
0x1800c6e30  lea     r9, aStartinstallmo_0; "StartInstallMonitoring [%#x]"
0x1800c6e37  mov     r8d, 0BFh
0x1800c6e3d  mov     ebx, edi
0x1800c6e3f  lea     rdx, aWindowsCompatI_1; "Windows::Compat::Inventory::InstallMonA"...
0x1800c6e46  mov     [rsp+38h+var_18], ebx
0x1800c6e4a  call    AslLogCallPrintf
0x1800c6e4f  test    edi, edi
0x1800c6e51  js      loc_1800C6DA5
0x1800c6e57  mov     r8d, 32h ; '2'
0x1800c6e5d  lea     r9, aInventorysvcSu; "InventorySvc successfully called StartI"...
0x1800c6e64  lea     rdx, aWindowsCompatI_53; "Windows::Compat::Inventory::InstallMon:"...
0x1800c6e6b  lea     ecx, [r8-2Fh]
0x1800c6e6f  call    AslLogCallPrintf
0x1800c6e74  jmp     loc_1800C6DC6
```
