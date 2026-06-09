# WindowsPerformanceRecorder::CControlManager::RestoreSessionsFromRegistry(ushort const *)

- ea: `0x18005d1bc`
- end: `0x18005d519`
- name: `?RestoreSessionsFromRegistry@CControlManager@WindowsPerformanceRecorder@@AEAAJPEBG@Z`
- size: `861`
- prototype: `__int64 __fastcall(WindowsPerformanceRecorder::CControlManager *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18005f068`

## callees

- `0x180008330`
- `0x18001a92c`
- `0x18001bf98`
- `0x18001c5a0`
- `0x18001c820`
- `0x18001e6e0`
- `0x1800248d8`
- `0x18003175c`
- `0x180040a04`
- `0x180043514`
- `0x18004a5c0`
- `0x18004a824`
- `0x18004a858`
- `0x18005d1bc`
- `0x18005ed4c`
- `0x18008c010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18005d200`
- `OLEAUT32!__imp_SysFreeString` at `0x18005d238`
- `OLEAUT32!__imp_SysFreeString` at `0x18005d2bb`
- `OLEAUT32!__imp_SysFreeString` at `0x18005d318`
- `OLEAUT32!__imp_SysFreeString` at `0x18005d382`
- `OLEAUT32!__imp_SysFreeString` at `0x18005d3a0`
- `OLEAUT32!__imp_SysFreeString` at `0x18005d200`
- `OLEAUT32!__imp_SysFreeString` at `0x18005d238`
- `OLEAUT32!__imp_SysFreeString` at `0x18005d2bb`
- `OLEAUT32!__imp_SysFreeString` at `0x18005d318`
- `OLEAUT32!__imp_SysFreeString` at `0x18005d382`
- `OLEAUT32!__imp_SysFreeString` at `0x18005d3a0`

## string_xrefs

- `0x18005d284`: `COMGUARD`
- `0x18005d358`: `COMGUARD`
- `0x18005d299`: `RestoreSessionsFromRegistry`
- `0x18005d36d`: `RestoreSessionsFromRegistry`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
__int64 __fastcall WindowsPerformanceRecorder::CControlManager::RestoreSessionsFromRegistry(
        WindowsPerformanceRecorder::CControlManager *this,
        const unsigned __int16 *a2)
{
  int RunningProfileTraceType; // ebx
  int v6; // eax
  const unsigned __int16 *v7; // rbx
  signed int RunningProfileStringInRegistry; // ebx
  int v9; // ebx
  OLECHAR *v10; // rbx
  signed int v11; // esi
  int v12; // ebx
  int v13; // r14d
  __int64 *v14; // rbx
  __int64 *v15; // rsi
  const char *v16; // [rsp+28h] [rbp-200h]
  __int64 v17; // [rsp+30h] [rbp-1F8h] BYREF
  struct IProfileCollection *v18; // [rsp+38h] [rbp-1F0h] BYREF
  BSTR bstrString[4]; // [rsp+40h] [rbp-1E8h] BYREF
  char v20[8]; // [rsp+60h] [rbp-1C8h] BYREF
  __int64 *v21; // [rsp+68h] [rbp-1C0h]
  __int64 *v22; // [rsp+70h] [rbp-1B8h]
  int v23; // [rsp+160h] [rbp-C8h]
  __int64 v24; // [rsp+240h] [rbp+18h] BYREF
  void (__fastcall ***v25)(_QWORD, GUID *, __int64 *); // [rsp+248h] [rbp+20h] BYREF

  bstrString[1] = (BSTR)-2LL;
  v25 = 0;
  bstrString[0] = 0;
  RunningProfileTraceType = WindowsPerformanceRecorder::CControlManager::GetRunningProfileTraceType(this);
  if ( RunningProfileTraceType < 0 )
  {
    SysFreeString(0);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v25);
    return (unsigned int)RunningProfileTraceType;
  }
  v6 = *((_DWORD *)this + 142);
  if ( (v6 & 1) != 0 || (v6 & 2) != 0 )
  {
    v7 = L"Normal";
  }
  else
  {
    if ( (v6 & 8) == 0 )
    {
      SysFreeString(0);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v25);
      return 3310891008LL;
    }
    v7 = L"Boot";
  }
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v24);
  RunningProfileStringInRegistry = WindowsPerformanceRecorder::CControlManager::GetRunningProfileStringInRegistry(
                                     this,
                                     v7,
                                     &v24);
  if ( RunningProfileStringInRegistry < 0 )
  {
    WindowsPerformanceRecorder::TraceHR(
      (WindowsPerformanceRecorder *)2,
      "RestoreSessionsFromRegistry",
      (const char *)0x1947,
      RunningProfileStringInRegistry,
      "COMGUARD",
      v16);
    WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&v24);
    SysFreeString(0);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v25);
    return (unsigned int)RunningProfileStringInRegistry;
  }
  ATL::CComBSTR::operator=(bstrString, v24);
  WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&v24);
  v9 = WindowsPerformanceRecorder::CInstanceNameScopedObjectImpl<WindowsPerformanceRecorder::CProfile>::WPRCCreatePeerInstance<CProfile,IProfile>(
         (__int64)this + 216,
         &v25);
  if ( v9 < 0 )
  {
    SysFreeString(bstrString[0]);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v25);
    return (unsigned int)v9;
  }
  v10 = bstrString[0];
  v11 = ((__int64 (__fastcall *)(void (__fastcall ***)(_QWORD, GUID *, __int64 *), BSTR))(*v25)[26])(v25, bstrString[0]);
  if ( v11 < 0 )
  {
    WindowsPerformanceRecorder::TraceHR(
      (WindowsPerformanceRecorder *)2,
      "RestoreSessionsFromRegistry",
      (const char *)0x194E,
      v11,
      "COMGUARD",
      v16);
    SysFreeString(v10);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v25);
    return (unsigned int)v11;
  }
  SysFreeString(v10);
  v18 = 0;
  v12 = WindowsPerformanceRecorder::CInstanceNameScopedObjectImpl<WindowsPerformanceRecorder::CProfile>::WPRCCreatePeerInstance<CProfileCollection,IProfileCollection>(
          (__int64)this + 216,
          (void (__fastcall ****)(_QWORD, GUID *, __int64 *))&v18);
  if ( v12 < 0 )
    goto LABEL_24;
  v13 = (*(__int64 (__fastcall **)(struct IProfileCollection *, _QWORD, __int64))(*(_QWORD *)v18 + 56LL))(
          v18,
          v25,
          0xFFFFFFFFLL);
  WindowsPerformanceRecorder::CETWProperties::CETWProperties((WindowsPerformanceRecorder::CETWProperties *)v20);
  if ( v13 >= 0 )
  {
    v13 = WindowsPerformanceRecorder::CETWProperties::Initialize(
            (WindowsPerformanceRecorder::CETWProperties *)v20,
            v18,
            this,
            (*((_DWORD *)this + 142) & 0x10) != 0);
    if ( v13 >= 0 )
    {
      v14 = v21;
      v15 = v22;
      while ( v14 != v15 )
        WindowsPerformanceRecorder::CControlManager::UpdateEventSession((__int64)this, a2, *v14++, v23, 1);
    }
  }
  v17 = 0;
  v12 = ATL::CComPtrBase<IProfile>::QueryInterface<WindowsPerformanceRecorder::IProfileElement>(&v25, (__int64)&v17);
  if ( v12 < 0 || (v12 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v17 + 32LL))(v17), v12 < 0) )
  {
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v17);
    WindowsPerformanceRecorder::CETWProperties::~CETWProperties((WindowsPerformanceRecorder::CETWProperties *)v20);
LABEL_24:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v18);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v25);
    return (unsigned int)v12;
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v17);
  WindowsPerformanceRecorder::CETWProperties::~CETWProperties((WindowsPerformanceRecorder::CETWProperties *)v20);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v18);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v25);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18005d1bc  mov     rax, rsp
0x18005d1bf  push    rdi
0x18005d1c0  push    r14
0x18005d1c2  push    r15
0x18005d1c4  sub     rsp, 210h
0x18005d1cb  mov     [rsp+228h+var_1E0], 0FFFFFFFFFFFFFFFEh
0x18005d1d4  mov     [rax+8], rbx
0x18005d1d8  mov     [rax+10h], rsi
0x18005d1dc  mov     r15, rdx
0x18005d1df  mov     rdi, rcx
0x18005d1e2  mov     qword ptr [rax+20h], 0
0x18005d1ea  mov     [rsp+228h+bstrString], 0
0x18005d1f3  call    ?GetRunningProfileTraceType@CControlManager@WindowsPerformanceRecorder@@AEAAJXZ; WindowsPerformanceRecorder::CControlManager::GetRunningProfileTraceType(void)
0x18005d1f8  mov     ebx, eax
0x18005d1fa  test    eax, eax
0x18005d1fc  jns     short loc_18005D21B
0x18005d1fe  xor     ecx, ecx; bstrString
0x18005d200  call    cs:__imp_SysFreeString
0x18005d206  nop
0x18005d207  lea     rcx, [rsp+228h+arg_18]
0x18005d20f  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18005d214  mov     eax, ebx
0x18005d216  jmp     loc_18005D500
0x18005d21b  mov     eax, [rdi+238h]
0x18005d221  test    al, 1
0x18005d223  jnz     short loc_18005D256
0x18005d225  test    al, 2
0x18005d227  jnz     short loc_18005D256
0x18005d229  test    al, 8
0x18005d22b  jz      short loc_18005D236
0x18005d22d  lea     rbx, ?sc_wchWPRBootRegistryKey@CControlManager@WindowsPerformanceRecorder@@0QBGB; "Boot"
0x18005d234  jmp     short loc_18005D25D
0x18005d236  xor     ecx, ecx; bstrString
0x18005d238  call    cs:__imp_SysFreeString
0x18005d23e  nop
0x18005d23f  lea     rcx, [rsp+228h+arg_18]
0x18005d247  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18005d24c  mov     eax, 0C5583000h
0x18005d251  jmp     loc_18005D500
0x18005d256  lea     rbx, ?sc_wchWPRNormalRegistryKey@CControlManager@WindowsPerformanceRecorder@@0QBGB; "Normal"
0x18005d25d  lea     rcx, [rsp+228h+arg_10]; void *
0x18005d265  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18005d26a  nop
0x18005d26b  lea     r8, [rsp+228h+arg_10]
0x18005d273  mov     rdx, rbx
0x18005d276  mov     rcx, rdi
0x18005d279  call    ?GetRunningProfileStringInRegistry@CControlManager@WindowsPerformanceRecorder@@AEBAJPEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WindowsPerformanceRecorder::CControlManager::GetRunningProfileStringInRegistry(ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x18005d27e  mov     ebx, eax
0x18005d280  test    eax, eax
0x18005d282  jns     short loc_18005D2D6
0x18005d284  lea     rax, aComguard; "COMGUARD"
0x18005d28b  mov     [rsp+228h+Format], rax; Format
0x18005d290  mov     r9d, ebx; unsigned int
0x18005d293  mov     r8d, 1947h; char *
0x18005d299  lea     rdx, aRestoresession; "RestoreSessionsFromRegistry"
0x18005d2a0  mov     ecx, 2; this
0x18005d2a5  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x18005d2aa  nop
0x18005d2ab  lea     rcx, [rsp+228h+arg_10]; this
0x18005d2b3  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x18005d2b8  nop
0x18005d2b9  xor     ecx, ecx; bstrString
0x18005d2bb  call    cs:__imp_SysFreeString
0x18005d2c1  nop
0x18005d2c2  lea     rcx, [rsp+228h+arg_18]
0x18005d2ca  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18005d2cf  mov     eax, ebx
0x18005d2d1  jmp     loc_18005D500
0x18005d2d6  mov     rdx, [rsp+228h+arg_10]
0x18005d2de  lea     rcx, [rsp+228h+bstrString]
0x18005d2e3  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x18005d2e8  nop
0x18005d2e9  lea     rcx, [rsp+228h+arg_10]; this
0x18005d2f1  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x18005d2f6  lea     r14, [rdi+0D8h]
0x18005d2fd  lea     rdx, [rsp+228h+arg_18]
0x18005d305  mov     rcx, r14
0x18005d308  call    ??$WPRCCreatePeerInstance@VCProfile@@UIProfile@@@?$CInstanceNameScopedObjectImpl@VCProfile@WindowsPerformanceRecorder@@@WindowsPerformanceRecorder@@IEAAJAEAV?$CComPtr@UIProfile@@@ATL@@@Z; WindowsPerformanceRecorder::CInstanceNameScopedObjectImpl<WindowsPerformanceRecorder::CProfile>::WPRCCreatePeerInstance<CProfile,IProfile>(ATL::CComPtr<IProfile> &)
0x18005d30d  mov     ebx, eax
0x18005d30f  test    eax, eax
0x18005d311  jns     short loc_18005D333
0x18005d313  mov     rcx, [rsp+228h+bstrString]; bstrString
0x18005d318  call    cs:__imp_SysFreeString
0x18005d31e  nop
0x18005d31f  lea     rcx, [rsp+228h+arg_18]
0x18005d327  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18005d32c  mov     eax, ebx
0x18005d32e  jmp     loc_18005D500
0x18005d333  mov     rcx, [rsp+228h+arg_18]
0x18005d33b  mov     rax, [rcx]
0x18005d33e  mov     rbx, [rsp+228h+bstrString]
0x18005d343  mov     rdx, rbx
0x18005d346  mov     rax, [rax+0D0h]
0x18005d34d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d352  mov     esi, eax
0x18005d354  test    eax, eax
0x18005d356  jns     short loc_18005D39D
0x18005d358  lea     rax, aComguard; "COMGUARD"
0x18005d35f  mov     [rsp+228h+Format], rax; Format
0x18005d364  mov     r9d, esi; unsigned int
0x18005d367  mov     r8d, 194Eh; char *
0x18005d36d  lea     rdx, aRestoresession; "RestoreSessionsFromRegistry"
0x18005d374  mov     ecx, 2; this
0x18005d379  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x18005d37e  nop
0x18005d37f  mov     rcx, rbx; bstrString
0x18005d382  call    cs:__imp_SysFreeString
0x18005d388  nop
0x18005d389  lea     rcx, [rsp+228h+arg_18]
0x18005d391  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18005d396  mov     eax, esi
0x18005d398  jmp     loc_18005D500
0x18005d39d  mov     rcx, rbx; bstrString
0x18005d3a0  call    cs:__imp_SysFreeString
0x18005d3a6  nop
0x18005d3a7  mov     [rsp+228h+var_1F0], 0
0x18005d3b0  lea     rdx, [rsp+228h+var_1F0]
0x18005d3b5  mov     rcx, r14
0x18005d3b8  call    ??$WPRCCreatePeerInstance@VCProfileCollection@@UIProfileCollection@@@?$CInstanceNameScopedObjectImpl@VCProfile@WindowsPerformanceRecorder@@@WindowsPerformanceRecorder@@IEAAJAEAV?$CComPtr@UIProfileCollection@@@ATL@@@Z; WindowsPerformanceRecorder::CInstanceNameScopedObjectImpl<WindowsPerformanceRecorder::CProfile>::WPRCCreatePeerInstance<CProfileCollection,IProfileCollection>(ATL::CComPtr<IProfileCollection> &)
0x18005d3bd  mov     ebx, eax
0x18005d3bf  test    eax, eax
0x18005d3c1  js      loc_18005D49D
0x18005d3c7  mov     rcx, [rsp+228h+var_1F0]
0x18005d3cc  mov     rax, [rcx]
0x18005d3cf  or      r8d, 0FFFFFFFFh
0x18005d3d3  mov     rdx, [rsp+228h+arg_18]
0x18005d3db  mov     rax, [rax+38h]
0x18005d3df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d3e4  mov     r14d, eax
0x18005d3e7  lea     rcx, [rsp+228h+var_1C8]; this
0x18005d3ec  call    ??0CETWProperties@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::CETWProperties::CETWProperties(void)
0x18005d3f1  nop
0x18005d3f2  test    r14d, r14d
0x18005d3f5  js      short loc_18005D44F
0x18005d3f7  mov     r9d, [rdi+238h]
0x18005d3fe  shr     r9d, 4
0x18005d402  and     r9b, 1; bool
0x18005d406  mov     r8, rdi; struct WindowsPerformanceRecorder::CControlManager *
0x18005d409  mov     rdx, [rsp+228h+var_1F0]; struct IProfileCollection *
0x18005d40e  lea     rcx, [rsp+228h+var_1C8]; this
0x18005d413  call    ?Initialize@CETWProperties@WindowsPerformanceRecorder@@QEAAJPEAUIProfileCollection@@PEAVCControlManager@2@_N@Z; WindowsPerformanceRecorder::CETWProperties::Initialize(IProfileCollection *,WindowsPerformanceRecorder::CControlManager *,bool)
0x18005d418  mov     r14d, eax
0x18005d41b  test    eax, eax
0x18005d41d  js      short loc_18005D44F
0x18005d41f  mov     rbx, [rsp+228h+var_1C0]
0x18005d424  mov     rsi, [rsp+228h+var_1B8]
0x18005d429  jmp     short loc_18005D44A
0x18005d42b  mov     byte ptr [rsp+228h+Format], 1
0x18005d430  mov     r9d, [rsp+228h+var_C8]
0x18005d438  mov     r8, [rbx]
0x18005d43b  mov     rdx, r15
0x18005d43e  mov     rcx, rdi
0x18005d441  call    ?UpdateEventSession@CControlManager@WindowsPerformanceRecorder@@AEAAJPEBGAEAUCEventSession@CETWProperties@2@W4__MIDL_IProfile_0001@@_N@Z; WindowsPerformanceRecorder::CControlManager::UpdateEventSession(ushort const *,WindowsPerformanceRecorder::CETWProperties::CEventSession &,__MIDL_IProfile_0001,bool)
0x18005d446  add     rbx, 8
0x18005d44a  cmp     rbx, rsi
0x18005d44d  jnz     short loc_18005D42B
0x18005d44f  mov     [rsp+228h+var_1F8], 0
0x18005d458  lea     rdx, [rsp+228h+var_1F8]
0x18005d45d  lea     rcx, [rsp+228h+arg_18]
0x18005d465  call    ??$QueryInterface@UIProfileElement@WindowsPerformanceRecorder@@@?$CComPtrBase@UIProfile@@@ATL@@QEBAJPEAPEAUIProfileElement@WindowsPerformanceRecorder@@@Z; ATL::CComPtrBase<IProfile>::QueryInterface<WindowsPerformanceRecorder::IProfileElement>(WindowsPerformanceRecorder::IProfileElement * *)
0x18005d46a  mov     ebx, eax
0x18005d46c  test    eax, eax
0x18005d46e  js      short loc_18005D487
0x18005d470  mov     rcx, [rsp+228h+var_1F8]
0x18005d475  mov     rax, [rcx]
0x18005d478  mov     rax, [rax+20h]
0x18005d47c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d481  mov     ebx, eax
0x18005d483  test    eax, eax
0x18005d485  jns     short loc_18005D4B9
0x18005d487  lea     rcx, [rsp+228h+var_1F8]
0x18005d48c  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18005d491  nop
0x18005d492  lea     rcx, [rsp+228h+var_1C8]; this
0x18005d497  call    ??1CETWProperties@WindowsPerformanceRecorder@@UEAA@XZ; WindowsPerformanceRecorder::CETWProperties::~CETWProperties(void)
0x18005d49c  nop
0x18005d49d  lea     rcx, [rsp+228h+var_1F0]
0x18005d4a2  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18005d4a7  nop
0x18005d4a8  lea     rcx, [rsp+228h+arg_18]
0x18005d4b0  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18005d4b5  mov     eax, ebx
0x18005d4b7  jmp     short loc_18005D500
0x18005d4b9  lea     rcx, [rsp+228h+var_1F8]
0x18005d4be  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18005d4c3  nop
0x18005d4c4  lea     rcx, [rsp+228h+var_1C8]; this
0x18005d4c9  call    ??1CETWProperties@WindowsPerformanceRecorder@@UEAA@XZ; WindowsPerformanceRecorder::CETWProperties::~CETWProperties(void)
0x18005d4ce  nop
0x18005d4cf  lea     rcx, [rsp+228h+var_1F0]
0x18005d4d4  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18005d4d9  nop
0x18005d4da  lea     rcx, [rsp+228h+arg_18]
0x18005d4e2  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18005d4e7  mov     eax, r14d
0x18005d4ea  jmp     short loc_18005D500
0x18005d4ec  lea     rcx, [rsp+228h+arg_18]
0x18005d4f4  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18005d4f9  mov     eax, dword ptr [rsp+228h+arg_10]
0x18005d500  lea     r11, [rsp+228h+var_18]
0x18005d508  mov     rbx, [r11+20h]
0x18005d50c  mov     rsi, [r11+28h]
0x18005d510  mov     rsp, r11
0x18005d513  pop     r15
0x18005d515  pop     r14
0x18005d517  pop     rdi
0x18005d518  retn
```
