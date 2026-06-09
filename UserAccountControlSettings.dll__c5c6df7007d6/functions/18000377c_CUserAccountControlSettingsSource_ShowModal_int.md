# CUserAccountControlSettingsSource::_ShowModal(int)

- ea: `0x18000377c`
- end: `0x1800039bc`
- name: `?_ShowModal@CUserAccountControlSettingsSource@@AEAAJH@Z`
- size: `576`
- prototype: `__int64 __fastcall(CUserAccountControlSettingsSource *this, int)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800036d0`

## callees

- `0x18000377c`
- `0x180003a18`
- `0x180003efc`
- `0x180005d88`
- `0x18000655c`
- `0x18000a5c4`
- `0x18000a6f4`
- `0x18000b030`
- `0x18000b0a0`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800037d8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800037d8`
- `ole32!OleUninitialize` at `0x180003993`
- `ole32!OleUninitialize` at `0x180003993`
- `ole32!OleInitialize` at `0x1800037ea`
- `ole32!OleInitialize` at `0x1800037ea`
- `USER32!SetForegroundWindow` at `0x18000396a`
- `USER32!SetForegroundWindow` at `0x18000396a`
- `USER32!SetProcessDPIAware` at `0x1800037ad`
- `USER32!SetProcessDPIAware` at `0x1800037ad`
- `DUI70!InitProcessPriv` at `0x180003811`
- `DUI70!InitProcessPriv` at `0x180003811`
- `DUI70!InitThread` at `0x180003826`
- `DUI70!InitThread` at `0x180003826`
- `DUI70!?Create@DUIXmlParser@DirectUI@@SAJPEAPEAV12@P6APEAVValue@2@PEBGPEAX@Z2P6AX11H2@Z2@Z` at `0x1800038b2`
- `DUI70!?Create@DUIXmlParser@DirectUI@@SAJPEAPEAV12@P6APEAVValue@2@PEBGPEAX@Z2P6AX11H2@Z2@Z` at `0x1800038b2`
- `DUI70!?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@0@Z` at `0x1800038d9`
- `DUI70!?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@0@Z` at `0x1800038d9`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x180003914`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x180003914`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x180003928`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x180003928`
- `DUI70!?EndDefer@Element@DirectUI@@QEAAXK@Z` at `0x180003948`
- `DUI70!?EndDefer@Element@DirectUI@@QEAAXK@Z` at `0x180003948`
- `DUI70!?ShowWindow@NativeHWNDHost@DirectUI@@QEAAXH@Z` at `0x180003957`
- `DUI70!?ShowWindow@NativeHWNDHost@DirectUI@@QEAAXH@Z` at `0x180003957`
- `DUI70!?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ` at `0x180003961`
- `DUI70!?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ` at `0x180003961`
- `DUI70!StartMessagePump` at `0x180003970`
- `DUI70!StartMessagePump` at `0x180003970`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x18000397a`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x18000397a`
- `DUI70!UnInitThread` at `0x180003980`
- `DUI70!UnInitThread` at `0x180003980`
- `DUI70!UnInitProcessPriv` at `0x18000398d`
- `DUI70!UnInitProcessPriv` at `0x18000398d`

## pseudocode

```c
__int64 __fastcall CUserAccountControlSettingsSource::_ShowModal(CUserAccountControlSettingsSource *this, int a2)
{
  HRESULT Instance; // edi
  __int64 v4; // r8
  HWND HWND; // rax
  CElevatedCPLPage *v7; // [rsp+30h] [rbp-20h] BYREF
  struct DirectUI::Element *v8; // [rsp+38h] [rbp-18h] BYREF
  struct IOleCommandTarget *ppv; // [rsp+40h] [rbp-10h] BYREF
  ULONG_PTR ulCookie; // [rsp+48h] [rbp-8h] BYREF
  CUserAccountControlSettingsSource *v11; // [rsp+70h] [rbp+20h] BYREF
  struct DirectUI::NativeHWNDHost *v12; // [rsp+80h] [rbp+30h] BYREF
  struct DirectUI::DUIXmlParser *v13; // [rsp+88h] [rbp+38h] BYREF

  v11 = this;
  Instance = CUserAccountControlSettingsSource::s_VerifyHighIL();
  if ( Instance >= 0 )
  {
    ulCookie = 0;
    SHActivateContext(&ulCookie);
    SetProcessDPIAware();
    ppv = 0;
    Instance = CoCreateInstance(&rclsid, 0, 4u, &GUID_b722bccb_4e68_101b_a2bc_00aa00404770, (LPVOID *)&ppv);
    if ( Instance >= 0 )
    {
      Instance = OleInitialize(0);
      if ( Instance >= 0 )
      {
        LOBYTE(v4) = 1;
        Instance = InitProcessPriv(14, &_ImageBase, v4);
        if ( Instance >= 0 )
        {
          Instance = InitThread(2);
          if ( Instance >= 0 )
          {
            Instance = DirectUI::ClassInfo<CNavigateButton,CElementWithSite,DirectUI::StandardCreator<CNavigateButton>>::Register();
            if ( Instance >= 0 )
            {
              Instance = DirectUI::ClassInfo<CFocusIndicator,DirectUI::Element,DirectUI::StandardCreator<CFocusIndicator>>::Register();
              if ( Instance >= 0 )
              {
                Instance = DirectUI::ClassInfo<CElevatedCPLPage,DirectUI::Element,DirectUI::StandardCreator<CElevatedCPLPage>>::Register();
                if ( Instance >= 0 )
                {
                  v12 = 0;
                  v8 = 0;
                  LODWORD(v11) = 0;
                  Instance = CUserAccountControlSettingsSource::s_CreateRootElement(&v12, &v8, (unsigned int *)&v11);
                  if ( Instance >= 0 )
                  {
                    v13 = 0;
                    Instance = DirectUI::DUIXmlParser::Create(&v13, 0, 0, 0, 0);
                    if ( Instance >= 0 )
                    {
                      Instance = DirectUI::DUIXmlParser::SetXMLFromResource(v13, 0xCBu, g_hinst, (HINSTANCE)&_ImageBase);
                      if ( Instance >= 0 )
                      {
                        v7 = 0;
                        Instance = DirectUI::DUIXmlParser::CreateElement(v13, L"main", 0, 0, 0, &v7);
                        if ( Instance >= 0 )
                        {
                          DirectUI::Element::Add(v8, v7);
                          CElevatedCPLPage::LayoutInitialized(v7, a2, v12, ppv);
                          DirectUI::Element::EndDefer(v8, (unsigned int)v11);
                          DirectUI::NativeHWNDHost::ShowWindow(v12, 1);
                          HWND = DirectUI::NativeHWNDHost::GetHWND(v12);
                          SetForegroundWindow(HWND);
                          StartMessagePump();
                        }
                      }
                      DirectUI::DUIXmlParser::Destroy(v13);
                    }
                  }
                }
              }
            }
            UnInitThread();
          }
          UnInitProcessPriv(&_ImageBase);
        }
        OleUninitialize();
      }
      ((void (__fastcall *)(struct IOleCommandTarget *))ppv->lpVtbl->Release)(ppv);
    }
    SHDeactivateContext(ulCookie);
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18000377c  mov     [rsp-18h+arg_0], rcx
0x180003781  push    rbp
0x180003782  push    rsi
0x180003783  push    rdi
0x180003784  mov     rbp, rsp
0x180003787  sub     rsp, 50h
0x18000378b  mov     esi, edx
0x18000378d  call    ?s_VerifyHighIL@CUserAccountControlSettingsSource@@CAJXZ; CUserAccountControlSettingsSource::s_VerifyHighIL(void)
0x180003792  mov     edi, eax
0x180003794  test    eax, eax
0x180003796  js      loc_1800039B2
0x18000379c  lea     rcx, [rbp+ulCookie]
0x1800037a0  mov     [rbp+ulCookie], 0
0x1800037a8  call    SHActivateContext
0x1800037ad  call    cs:__imp_SetProcessDPIAware
0x1800037b3  xor     edx, edx; pUnkOuter
0x1800037b5  mov     [rbp+var_10], 0
0x1800037bd  lea     rax, [rbp+var_10]
0x1800037c1  lea     r9, _GUID_b722bccb_4e68_101b_a2bc_00aa00404770; riid
0x1800037c8  mov     [rsp+50h+ppv], rax; ppv
0x1800037cd  lea     rcx, rclsid; rclsid
0x1800037d4  lea     r8d, [rdx+4]; dwClsContext
0x1800037d8  call    cs:__imp_CoCreateInstance
0x1800037de  mov     edi, eax
0x1800037e0  test    eax, eax
0x1800037e2  js      loc_1800039A9
0x1800037e8  xor     ecx, ecx; pvReserved
0x1800037ea  call    cs:__imp_OleInitialize
0x1800037f0  mov     edi, eax
0x1800037f2  test    eax, eax
0x1800037f4  js      loc_180003999
0x1800037fa  mov     r9b, 1
0x1800037fd  mov     byte ptr [rsp+50h+ppv], 1
0x180003802  mov     r8b, r9b
0x180003805  lea     rdx, __ImageBase
0x18000380c  mov     ecx, 0Eh
0x180003811  call    cs:__imp_InitProcessPriv
0x180003817  mov     edi, eax
0x180003819  test    eax, eax
0x18000381b  js      loc_180003993
0x180003821  mov     ecx, 2
0x180003826  call    cs:__imp_InitThread
0x18000382c  mov     edi, eax
0x18000382e  test    eax, eax
0x180003830  js      loc_180003986
0x180003836  call    ?Register@?$ClassInfo@VCNavigateButton@@VCElementWithSite@@V?$StandardCreator@VCNavigateButton@@@DirectUI@@@DirectUI@@CAJPEAUHINSTANCE__@@PEBGPEBQEBUPropertyInfo@2@I_N@Z; DirectUI::ClassInfo<CNavigateButton,CElementWithSite,DirectUI::StandardCreator<CNavigateButton>>::Register(HINSTANCE__ *,ushort const *,DirectUI::PropertyInfo const * const *,uint,bool)
0x18000383b  mov     edi, eax
0x18000383d  test    eax, eax
0x18000383f  js      loc_180003980
0x180003845  call    ?Register@?$ClassInfo@VCFocusIndicator@@VElement@DirectUI@@V?$StandardCreator@VCFocusIndicator@@@3@@DirectUI@@CAJPEAUHINSTANCE__@@PEBGPEBQEBUPropertyInfo@2@I_N@Z; DirectUI::ClassInfo<CFocusIndicator,DirectUI::Element,DirectUI::StandardCreator<CFocusIndicator>>::Register(HINSTANCE__ *,ushort const *,DirectUI::PropertyInfo const * const *,uint,bool)
0x18000384a  mov     edi, eax
0x18000384c  test    eax, eax
0x18000384e  js      loc_180003980
0x180003854  call    ?Register@?$ClassInfo@VCElevatedCPLPage@@VElement@DirectUI@@V?$StandardCreator@VCElevatedCPLPage@@@3@@DirectUI@@CAJPEAUHINSTANCE__@@PEBGPEBQEBUPropertyInfo@2@I_N@Z; DirectUI::ClassInfo<CElevatedCPLPage,DirectUI::Element,DirectUI::StandardCreator<CElevatedCPLPage>>::Register(HINSTANCE__ *,ushort const *,DirectUI::PropertyInfo const * const *,uint,bool)
0x180003859  mov     edi, eax
0x18000385b  test    eax, eax
0x18000385d  js      loc_180003980
0x180003863  lea     r8, [rbp+arg_0]; unsigned int *
0x180003867  mov     [rbp+arg_10], 0
0x18000386f  lea     rdx, [rbp+var_18]; struct DirectUI::Element **
0x180003873  mov     [rbp+var_18], 0
0x18000387b  lea     rcx, [rbp+arg_10]; struct DirectUI::NativeHWNDHost **
0x18000387f  mov     dword ptr [rbp+arg_0], 0
0x180003886  call    ?s_CreateRootElement@CUserAccountControlSettingsSource@@CAJPEAPEAVNativeHWNDHost@DirectUI@@PEAPEAVElement@3@PEAK@Z; CUserAccountControlSettingsSource::s_CreateRootElement(DirectUI::NativeHWNDHost * *,DirectUI::Element * *,ulong *)
0x18000388b  mov     edi, eax
0x18000388d  test    eax, eax
0x18000388f  js      loc_180003980
0x180003895  xor     r9d, r9d
0x180003898  mov     [rbp+arg_18], 0
0x1800038a0  xor     r8d, r8d
0x1800038a3  mov     [rsp+50h+ppv], 0
0x1800038ac  xor     edx, edx
0x1800038ae  lea     rcx, [rbp+arg_18]
0x1800038b2  call    cs:__imp_?Create@DUIXmlParser@DirectUI@@SAJPEAPEAV12@P6APEAVValue@2@PEBGPEAX@Z2P6AX11H2@Z2@Z; DirectUI::DUIXmlParser::Create(DirectUI::DUIXmlParser * *,DirectUI::Value * (*)(ushort const *,void *),void *,void (*)(ushort const *,ushort const *,int,void *),void *)
0x1800038b8  mov     edi, eax
0x1800038ba  test    eax, eax
0x1800038bc  js      loc_180003980
0x1800038c2  mov     r8, cs:?g_hinst@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hinst
0x1800038c9  lea     r9, __ImageBase
0x1800038d0  mov     rcx, [rbp+arg_18]
0x1800038d4  mov     edx, 0CBh
0x1800038d9  call    cs:__imp_?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@0@Z; DirectUI::DUIXmlParser::SetXMLFromResource(uint,HINSTANCE__ *,HINSTANCE__ *)
0x1800038df  mov     edi, eax
0x1800038e1  test    eax, eax
0x1800038e3  js      loc_180003976
0x1800038e9  mov     rcx, [rbp+arg_18]
0x1800038ed  lea     rax, [rbp+var_20]
0x1800038f1  mov     [rsp+50h+var_28], rax
0x1800038f6  lea     rdx, aMain; "main"
0x1800038fd  xor     r9d, r9d
0x180003900  mov     [rsp+50h+ppv], 0
0x180003909  xor     r8d, r8d
0x18000390c  mov     [rbp+var_20], 0
0x180003914  call    cs:__imp_?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z; DirectUI::DUIXmlParser::CreateElement(ushort const *,DirectUI::Element *,DirectUI::Element *,ulong *,DirectUI::Element * *)
0x18000391a  mov     edi, eax
0x18000391c  test    eax, eax
0x18000391e  js      short loc_180003976
0x180003920  mov     rdx, [rbp+var_20]
0x180003924  mov     rcx, [rbp+var_18]
0x180003928  call    cs:__imp_?Add@Element@DirectUI@@QEAAJPEAV12@@Z; DirectUI::Element::Add(DirectUI::Element *)
0x18000392e  mov     r9, [rbp+var_10]; struct IOleCommandTarget *
0x180003932  mov     edx, esi; int
0x180003934  mov     r8, [rbp+arg_10]; struct DirectUI::NativeHWNDHost *
0x180003938  mov     rcx, [rbp+var_20]; this
0x18000393c  call    ?LayoutInitialized@CElevatedCPLPage@@QEAAJHPEAVNativeHWNDHost@DirectUI@@PEAUIOleCommandTarget@@@Z; CElevatedCPLPage::LayoutInitialized(int,DirectUI::NativeHWNDHost *,IOleCommandTarget *)
0x180003941  mov     edx, dword ptr [rbp+arg_0]
0x180003944  mov     rcx, [rbp+var_18]
0x180003948  call    cs:__imp_?EndDefer@Element@DirectUI@@QEAAXK@Z; DirectUI::Element::EndDefer(ulong)
0x18000394e  mov     rcx, [rbp+arg_10]
0x180003952  mov     edx, 1
0x180003957  call    cs:__imp_?ShowWindow@NativeHWNDHost@DirectUI@@QEAAXH@Z; DirectUI::NativeHWNDHost::ShowWindow(int)
0x18000395d  mov     rcx, [rbp+arg_10]
0x180003961  call    cs:__imp_?GetHWND@NativeHWNDHost@DirectUI@@QEAAPEAUHWND__@@XZ; DirectUI::NativeHWNDHost::GetHWND(void)
0x180003967  mov     rcx, rax; hWnd
0x18000396a  call    cs:__imp_SetForegroundWindow
0x180003970  call    cs:__imp_StartMessagePump
0x180003976  mov     rcx, [rbp+arg_18]
0x18000397a  call    cs:__imp_?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ; DirectUI::DUIXmlParser::Destroy(void)
0x180003980  call    cs:__imp_UnInitThread
0x180003986  lea     rcx, __ImageBase
0x18000398d  call    cs:__imp_UnInitProcessPriv
0x180003993  call    cs:__imp_OleUninitialize
0x180003999  mov     rcx, [rbp+var_10]
0x18000399d  mov     rax, [rcx]
0x1800039a0  mov     rax, [rax+10h]
0x1800039a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039a9  mov     rcx, [rbp+ulCookie]; ulCookie
0x1800039ad  call    SHDeactivateContext
0x1800039b2  mov     eax, edi
0x1800039b4  add     rsp, 50h
0x1800039b8  pop     rdi
0x1800039b9  pop     rsi
0x1800039ba  pop     rbp
0x1800039bb  retn
```
