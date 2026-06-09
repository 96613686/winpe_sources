# WindowsPerformanceRecorder::CControlManager::GetRegistryETWProperties(WindowsPerformanceRecorder::CETWProperties &,bool)

- ea: `0x180031374`
- end: `0x180031753`
- name: `?GetRegistryETWProperties@CControlManager@WindowsPerformanceRecorder@@AEAAJAEAVCETWProperties@2@_N@Z`
- size: `991`
- prototype: `__int64 __fastcall(WindowsPerformanceRecorder::CControlManager *__hidden this, struct WindowsPerformanceRecorder::CETWProperties *, bool)`
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003c270`
- `0x180058800`

## callees

- `0x180008330`
- `0x18000eeb0`
- `0x18001a61c`
- `0x18001a92c`
- `0x18001bf98`
- `0x18001cdd0`
- `0x18001e6e0`
- `0x180031374`
- `0x18003175c`
- `0x180040a04`
- `0x180044210`
- `0x1800483c8`
- `0x18008c010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180031497`
- `OLEAUT32!__imp_SysAllocString` at `0x180031497`
- `OLEAUT32!__imp_SysFreeString` at `0x180031467`
- `OLEAUT32!__imp_SysFreeString` at `0x18003148e`
- `OLEAUT32!__imp_SysFreeString` at `0x1800314fd`
- `OLEAUT32!__imp_SysFreeString` at `0x18003157a`
- `OLEAUT32!__imp_SysFreeString` at `0x18003159f`
- `OLEAUT32!__imp_SysFreeString` at `0x180031467`
- `OLEAUT32!__imp_SysFreeString` at `0x18003148e`
- `OLEAUT32!__imp_SysFreeString` at `0x1800314fd`
- `OLEAUT32!__imp_SysFreeString` at `0x18003157a`
- `OLEAUT32!__imp_SysFreeString` at `0x18003159f`

## string_xrefs

- `0x180031430`: `COMGUARD`
- `0x180031532`: `LoadFromString from registry failed`
- `0x180031445`: `GetRegistryETWProperties`
- `0x180031547`: `GetRegistryETWProperties`

## pseudocode

```c
// Hidden C++ exception states: #wind=12 #try_helpers=1
__int64 __fastcall WindowsPerformanceRecorder::CControlManager::GetRegistryETWProperties(
        BSTR *this,
        struct WindowsPerformanceRecorder::CETWProperties *a2,
        char a3)
{
  unsigned int RunningProfileTraceType; // ebx
  int v7; // eax
  const unsigned __int16 *v8; // rdi
  OLECHAR *v9; // rbx
  signed int RunningProfileStringInRegistry; // edi
  OLECHAR *v12; // r14
  int v13; // edi
  signed int v14; // edi
  __int64 v15; // rcx
  int v16; // ebx
  int v17; // edi
  int v18; // eax
  char *v19; // [rsp+28h] [rbp-50h]
  char *v20; // [rsp+28h] [rbp-50h]
  char v21[8]; // [rsp+30h] [rbp-48h] BYREF
  struct IProfileCollection *v22; // [rsp+38h] [rbp-40h] BYREF
  __int64 v23; // [rsp+40h] [rbp-38h] BYREF
  OLECHAR *v24; // [rsp+48h] [rbp-30h]
  __int64 v25; // [rsp+50h] [rbp-28h]
  OLECHAR *psz; // [rsp+98h] [rbp+20h] BYREF

  v25 = -2;
  *(_QWORD *)v21 = 0;
  RunningProfileTraceType = WindowsPerformanceRecorder::CControlManager::GetRunningProfileTraceType((WindowsPerformanceRecorder::CControlManager *)this);
  if ( RunningProfileTraceType )
  {
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v21);
    return RunningProfileTraceType;
  }
  v7 = *((_DWORD *)this + 142);
  if ( (v7 & 1) != 0 )
    goto LABEL_5;
  if ( (v7 & 8) != 0 )
  {
LABEL_7:
    v8 = L"Boot";
    goto LABEL_8;
  }
  if ( (v7 & 2) == 0 )
  {
    if ( (v7 & 4) == 0 )
    {
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v21);
      return 3310891008LL;
    }
    goto LABEL_7;
  }
LABEL_5:
  v8 = L"Normal";
LABEL_8:
  v9 = 0;
  v24 = 0;
  psz = (OLECHAR *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  if ( a3 )
    WindowsPerformanceRecorder::CControlManager::SetTemporaryTraceDirectoryToCurrentTracingDirectory(
      (WindowsPerformanceRecorder::CControlManager *)this,
      *((_DWORD *)this + 142));
  RunningProfileStringInRegistry = WindowsPerformanceRecorder::CControlManager::GetRunningProfileStringInRegistry(
                                     this,
                                     v8,
                                     &psz);
  if ( RunningProfileStringInRegistry < 0 )
  {
    WindowsPerformanceRecorder::TraceHR(
      (WindowsPerformanceRecorder *)2,
      "GetRegistryETWProperties",
      (const char *)0x16F3,
      RunningProfileStringInRegistry,
      "COMGUARD",
      v19);
    WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&psz);
    SysFreeString(0);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v21);
    return (unsigned int)RunningProfileStringInRegistry;
  }
  v12 = psz;
  if ( psz )
  {
    SysFreeString(0);
    v9 = SysAllocString(v12);
    v24 = v9;
    if ( !v9 )
      ATL::AtlThrowImpl(-2147024882);
  }
  v13 = WPRCCreateInstanceUnderInstanceName(
          this[28],
          &GUID_d66d26bf_6098_4b78_9d94_7bc219612ae4,
          0,
          1,
          (__int64)&GUID_71e0563a_bcbc_4784_933a_735a2ef4fb8a,
          (void (__fastcall ****)(_QWORD, GUID *, __int64 *))v21);
  if ( v13 < 0 )
  {
    WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&psz);
    SysFreeString(v9);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v21);
    return (unsigned int)v13;
  }
  v14 = (*(__int64 (__fastcall **)(_QWORD, OLECHAR *))(**(_QWORD **)v21 + 208LL))(*(_QWORD *)v21, v9);
  if ( v14 < 0 )
  {
    WindowsPerformanceRecorder::TraceHR(
      (WindowsPerformanceRecorder *)2,
      "GetRegistryETWProperties",
      (const char *)0x16FD,
      v14,
      "LoadFromString from registry failed",
      v20);
    WindowsPerformanceRecorder::CControlManager::LogProfileXmlEvent(v15, &psz, 0);
    WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&psz);
    SysFreeString(v9);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v21);
    return (unsigned int)v14;
  }
  ATL::CStringData::Release((ATL::CStringData *)(v12 - 12));
  SysFreeString(v9);
  v22 = 0;
  v16 = WPRCCreateInstanceUnderInstanceName(
          this[28],
          &GUID_b98b53f3_83ba_4837_8946_e886be8d4003,
          0,
          1,
          (__int64)&GUID_bb5ed25c_a7a8_4cef_bffd_2d9c64cb457a,
          (void (__fastcall ****)(_QWORD, GUID *, __int64 *))&v22);
  if ( v16 < 0 )
  {
    if ( v22 )
      (*(void (__fastcall **)(struct IProfileCollection *, _QWORD))(*(_QWORD *)v22 + 16LL))(v22, *(_QWORD *)v22);
    if ( *(_QWORD *)v21 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v21 + 16LL))(*(_QWORD *)v21);
    return (unsigned int)v16;
  }
  v17 = (*(__int64 (__fastcall **)(struct IProfileCollection *, _QWORD, __int64))(*(_QWORD *)v22 + 56LL))(
          v22,
          *(_QWORD *)v21,
          0xFFFFFFFFLL);
  if ( v17 >= 0 )
    v17 = WindowsPerformanceRecorder::CETWProperties::Initialize(
            a2,
            v22,
            (struct WindowsPerformanceRecorder::CControlManager *)this,
            ((_DWORD)this[71] & 0x10) != 0);
  v23 = 0;
  v16 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))v21)(
          *(_QWORD *)v21,
          &GUID_23eb05b7_c03b_4abd_ab86_7be3e0e57e66,
          &v23);
  if ( v16 < 0 )
  {
LABEL_30:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v23);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v22);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v21);
    return (unsigned int)v16;
  }
  v18 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v23 + 32LL))(v23);
  if ( v18 < 0 )
  {
    v16 = v18;
    goto LABEL_30;
  }
  if ( v23 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
  if ( v22 )
    (*(void (__fastcall **)(struct IProfileCollection *))(*(_QWORD *)v22 + 16LL))(v22);
  if ( *(_QWORD *)v21 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v21 + 16LL))(*(_QWORD *)v21);
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x180031374  mov     rax, rsp
0x180031377  push    rdi
0x180031378  push    r14
0x18003137a  push    r15
0x18003137c  sub     rsp, 60h
0x180031380  mov     qword ptr [rax-28h], 0FFFFFFFFFFFFFFFEh
0x180031388  mov     [rax+8], rbx
0x18003138c  mov     [rax+10h], rsi
0x180031390  mov     r14b, r8b
0x180031393  mov     r15, rdx
0x180031396  mov     rsi, rcx
0x180031399  mov     qword ptr [rax-48h], 0
0x1800313a1  call    ?GetRunningProfileTraceType@CControlManager@WindowsPerformanceRecorder@@AEAAJXZ; WindowsPerformanceRecorder::CControlManager::GetRunningProfileTraceType(void)
0x1800313a6  mov     ebx, eax
0x1800313a8  test    eax, eax
0x1800313aa  jnz     loc_18003171E
0x1800313b0  mov     eax, [rsi+238h]
0x1800313b6  test    al, 1
0x1800313b8  jnz     short loc_1800313C2
0x1800313ba  test    al, 8
0x1800313bc  jnz     short loc_1800313D3
0x1800313be  test    al, 2
0x1800313c0  jz      short loc_1800313CB
0x1800313c2  lea     rdi, ?sc_wchWPRNormalRegistryKey@CControlManager@WindowsPerformanceRecorder@@0QBGB; "Normal"
0x1800313c9  jmp     short loc_1800313DA
0x1800313cb  test    al, 4
0x1800313cd  jz      loc_18003170D
0x1800313d3  lea     rdi, ?sc_wchWPRBootRegistryKey@CControlManager@WindowsPerformanceRecorder@@0QBGB; "Boot"
0x1800313da  xor     ebx, ebx
0x1800313dc  mov     [rsp+78h+var_30], rbx
0x1800313e1  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1800313e8  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1800313ef  mov     rax, [rax+18h]
0x1800313f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800313f8  add     rax, 18h
0x1800313fc  mov     [rsp+78h+psz], rax
0x180031404  test    r14b, r14b
0x180031407  jz      short loc_180031417
0x180031409  mov     edx, [rsi+238h]
0x18003140f  mov     rcx, rsi
0x180031412  call    ?SetTemporaryTraceDirectoryToCurrentTracingDirectory@CControlManager@WindowsPerformanceRecorder@@AEAAXUCTraceType@IControlInfo@Status@2@@Z; WindowsPerformanceRecorder::CControlManager::SetTemporaryTraceDirectoryToCurrentTracingDirectory(WindowsPerformanceRecorder::Status::IControlInfo::CTraceType)
0x180031417  lea     r8, [rsp+78h+psz]
0x18003141f  mov     rdx, rdi
0x180031422  mov     rcx, rsi
0x180031425  call    ?GetRunningProfileStringInRegistry@CControlManager@WindowsPerformanceRecorder@@AEBAJPEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WindowsPerformanceRecorder::CControlManager::GetRunningProfileStringInRegistry(ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x18003142a  mov     edi, eax
0x18003142c  test    eax, eax
0x18003142e  jns     short loc_18003147F
0x180031430  lea     rax, aComguard; "COMGUARD"
0x180031437  mov     [rsp+78h+Format], rax; Format
0x18003143c  mov     r9d, edi; unsigned int
0x18003143f  mov     r8d, 16F3h; char *
0x180031445  lea     rdx, aGetregistryetw; "GetRegistryETWProperties"
0x18003144c  mov     ecx, 2; this
0x180031451  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x180031456  nop
0x180031457  lea     rcx, [rsp+78h+psz]; this
0x18003145f  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x180031464  nop
0x180031465  xor     ecx, ecx; bstrString
0x180031467  call    cs:__imp_SysFreeString
0x18003146d  nop
0x18003146e  lea     rcx, [rsp+78h+var_48]
0x180031473  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180031478  mov     eax, edi
0x18003147a  jmp     loc_18003173D
0x18003147f  mov     r14, [rsp+78h+psz]
0x180031487  test    r14, r14
0x18003148a  jz      short loc_1800314B4
0x18003148c  xor     ecx, ecx; bstrString
0x18003148e  call    cs:__imp_SysFreeString
0x180031494  mov     rcx, r14; psz
0x180031497  call    cs:__imp_SysAllocString
0x18003149d  mov     rbx, rax
0x1800314a0  mov     [rsp+78h+var_30], rax
0x1800314a5  test    rax, rax
0x1800314a8  jnz     short loc_1800314B4
0x1800314aa  mov     ecx, 8007000Eh; int
0x1800314af  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800314b4  lea     rax, [rsp+78h+var_48]
0x1800314b9  mov     [rsp+78h+var_50], rax; char *
0x1800314be  lea     rax, _GUID_71e0563a_bcbc_4784_933a_735a2ef4fb8a
0x1800314c5  mov     [rsp+78h+Format], rax; __int64
0x1800314ca  mov     r9d, 1
0x1800314d0  xor     r8d, r8d
0x1800314d3  lea     rdx, _GUID_d66d26bf_6098_4b78_9d94_7bc219612ae4
0x1800314da  mov     rcx, [rsi+0E0h]; pbstr
0x1800314e1  call    WPRCCreateInstanceUnderInstanceName
0x1800314e6  mov     edi, eax
0x1800314e8  test    eax, eax
0x1800314ea  jns     short loc_180031515
0x1800314ec  lea     rcx, [rsp+78h+psz]; this
0x1800314f4  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x1800314f9  nop
0x1800314fa  mov     rcx, rbx; bstrString
0x1800314fd  call    cs:__imp_SysFreeString
0x180031503  nop
0x180031504  lea     rcx, [rsp+78h+var_48]
0x180031509  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003150e  mov     eax, edi
0x180031510  jmp     loc_18003173D
0x180031515  mov     rcx, qword ptr [rsp+78h+var_48]
0x18003151a  mov     rax, [rcx]
0x18003151d  mov     rdx, rbx
0x180031520  mov     rax, [rax+0D0h]
0x180031527  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003152c  mov     edi, eax
0x18003152e  test    eax, eax
0x180031530  jns     short loc_180031592
0x180031532  lea     rax, aLoadfromstring; "LoadFromString from registry failed"
0x180031539  mov     [rsp+78h+Format], rax; Format
0x18003153e  mov     r9d, edi; unsigned int
0x180031541  mov     r8d, 16FDh; char *
0x180031547  lea     rdx, aGetregistryetw; "GetRegistryETWProperties"
0x18003154e  mov     ecx, 2; this
0x180031553  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x180031558  xor     r8d, r8d
0x18003155b  lea     rdx, [rsp+78h+psz]
0x180031563  call    ?LogProfileXmlEvent@CControlManager@WindowsPerformanceRecorder@@AEAAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@W4__MIDL_IProfile_0001@@@Z; WindowsPerformanceRecorder::CControlManager::LogProfileXmlEvent(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,__MIDL_IProfile_0001)
0x180031568  nop
0x180031569  lea     rcx, [rsp+78h+psz]; this
0x180031571  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x180031576  nop
0x180031577  mov     rcx, rbx; bstrString
0x18003157a  call    cs:__imp_SysFreeString
0x180031580  nop
0x180031581  lea     rcx, [rsp+78h+var_48]
0x180031586  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003158b  mov     eax, edi
0x18003158d  jmp     loc_18003173D
0x180031592  lea     rcx, [r14-18h]; this
0x180031596  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18003159b  nop
0x18003159c  mov     rcx, rbx; bstrString
0x18003159f  call    cs:__imp_SysFreeString
0x1800315a5  nop
0x1800315a6  mov     [rsp+78h+var_40], 0
0x1800315af  lea     rax, [rsp+78h+var_40]
0x1800315b4  mov     [rsp+78h+var_50], rax; __int64
0x1800315b9  lea     rax, _GUID_bb5ed25c_a7a8_4cef_bffd_2d9c64cb457a
0x1800315c0  mov     [rsp+78h+Format], rax; __int64
0x1800315c5  mov     r9d, 1
0x1800315cb  xor     r8d, r8d
0x1800315ce  lea     rdx, _GUID_b98b53f3_83ba_4837_8946_e886be8d4003
0x1800315d5  mov     rcx, [rsi+0E0h]; pbstr
0x1800315dc  call    WPRCCreateInstanceUnderInstanceName
0x1800315e1  mov     ebx, eax
0x1800315e3  test    eax, eax
0x1800315e5  jns     short loc_18003161C
0x1800315e7  mov     rcx, [rsp+78h+var_40]
0x1800315ec  test    rcx, rcx
0x1800315ef  jz      short loc_1800315FE
0x1800315f1  mov     rdx, [rcx]
0x1800315f4  mov     rax, [rdx+10h]
0x1800315f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800315fd  nop
0x1800315fe  mov     rcx, qword ptr [rsp+78h+var_48]
0x180031603  test    rcx, rcx
0x180031606  jz      short loc_180031615
0x180031608  mov     rax, [rcx]
0x18003160b  mov     rax, [rax+10h]
0x18003160f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031614  nop
0x180031615  mov     eax, ebx
0x180031617  jmp     loc_18003173D
0x18003161c  mov     rcx, [rsp+78h+var_40]
0x180031621  mov     rax, [rcx]
0x180031624  or      r8d, 0FFFFFFFFh
0x180031628  mov     rdx, qword ptr [rsp+78h+var_48]
0x18003162d  mov     rax, [rax+38h]
0x180031631  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031636  mov     edi, eax
0x180031638  test    eax, eax
0x18003163a  js      short loc_18003165D
0x18003163c  mov     r9d, [rsi+238h]
0x180031643  shr     r9d, 4
0x180031647  and     r9b, 1; bool
0x18003164b  mov     r8, rsi; struct WindowsPerformanceRecorder::CControlManager *
0x18003164e  mov     rdx, [rsp+78h+var_40]; struct IProfileCollection *
0x180031653  mov     rcx, r15; this
0x180031656  call    ?Initialize@CETWProperties@WindowsPerformanceRecorder@@QEAAJPEAUIProfileCollection@@PEAVCControlManager@2@_N@Z; WindowsPerformanceRecorder::CETWProperties::Initialize(IProfileCollection *,WindowsPerformanceRecorder::CControlManager *,bool)
0x18003165b  mov     edi, eax
0x18003165d  mov     [rsp+78h+var_38], 0
0x180031666  mov     rcx, qword ptr [rsp+78h+var_48]
0x18003166b  mov     rax, [rcx]
0x18003166e  lea     r8, [rsp+78h+var_38]
0x180031673  lea     rdx, _GUID_23eb05b7_c03b_4abd_ab86_7be3e0e57e66
0x18003167a  mov     rax, [rax]
0x18003167d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031682  mov     ebx, eax
0x180031684  test    eax, eax
0x180031686  js      short loc_18003169F
0x180031688  mov     rcx, [rsp+78h+var_38]
0x18003168d  mov     rax, [rcx]
0x180031690  mov     rax, [rax+20h]
0x180031694  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031699  test    eax, eax
0x18003169b  jns     short loc_1800316C4
0x18003169d  mov     ebx, eax
0x18003169f  lea     rcx, [rsp+78h+var_38]
0x1800316a4  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800316a9  nop
0x1800316aa  lea     rcx, [rsp+78h+var_40]
0x1800316af  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800316b4  nop
0x1800316b5  lea     rcx, [rsp+78h+var_48]
0x1800316ba  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800316bf  jmp     loc_180031615
0x1800316c4  mov     rcx, [rsp+78h+var_38]
0x1800316c9  test    rcx, rcx
0x1800316cc  jz      short loc_1800316DB
0x1800316ce  mov     rax, [rcx]
0x1800316d1  mov     rax, [rax+10h]
0x1800316d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800316da  nop
0x1800316db  mov     rcx, [rsp+78h+var_40]
0x1800316e0  test    rcx, rcx
0x1800316e3  jz      short loc_1800316F2
0x1800316e5  mov     rax, [rcx]
0x1800316e8  mov     rax, [rax+10h]
0x1800316ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800316f1  nop
0x1800316f2  mov     rcx, qword ptr [rsp+78h+var_48]
0x1800316f7  test    rcx, rcx
0x1800316fa  jz      short loc_180031709
0x1800316fc  mov     rax, [rcx]
0x1800316ff  mov     rax, [rax+10h]
0x180031703  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031708  nop
0x180031709  mov     eax, edi
0x18003170b  jmp     short loc_18003173D
0x18003170d  lea     rcx, [rsp+78h+var_48]
0x180031712  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180031717  mov     eax, 0C5583000h
0x18003171c  jmp     short loc_18003173D
0x18003171e  lea     rcx, [rsp+78h+var_48]
0x180031723  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180031728  mov     eax, ebx
0x18003172a  jmp     short loc_18003173D
0x18003172c  lea     rcx, [rsp+78h+var_48]
0x180031731  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180031736  mov     eax, dword ptr [rsp+78h+psz]
0x18003173d  lea     r11, [rsp+78h+var_18]
0x180031742  mov     rbx, [r11+20h]
0x180031746  mov     rsi, [r11+28h]
0x18003174a  mov     rsp, r11
0x18003174d  pop     r15
0x18003174f  pop     r14
0x180031751  pop     rdi
0x180031752  retn
```
