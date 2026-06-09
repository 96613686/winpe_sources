# WindowsPerformanceRecorder::CControlManager::QueryRunningProfile(bool,ushort * *,ushort * *,IProfileCollection * *)

- ea: `0x18001c8bc`
- end: `0x18001cdbd`
- name: `?QueryRunningProfile@CControlManager@WindowsPerformanceRecorder@@AEAAJ_NPEAPEAG1PEAPEAUIProfileCollection@@@Z`
- size: `1281`
- prototype: `__int64 __usercall@<rax>(WindowsPerformanceRecorder::CControlManager *__hidden this@<rcx>, bool@<dl>, unsigned __int16 **@<r8>, unsigned __int16 **@<r9>, struct IProfileCollection **)`
- caller_count: `6`
- callee_count: `17`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180032450`
- `0x1800326e0`
- `0x180049630`
- `0x180049970`
- `0x180049ca0`
- `0x18005a1f0`

## callees

- `0x180008330`
- `0x18000eeb0`
- `0x18001a92c`
- `0x18001bf98`
- `0x18001c8bc`
- `0x18001cdd0`
- `0x18001e6e0`
- `0x1800248d8`
- `0x18003175c`
- `0x18003c6a4`
- `0x180040a04`
- `0x180043514`
- `0x180044210`
- `0x1800483c8`
- `0x18004a824`
- `0x18004d940`
- `0x18008c010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18001ca65`
- `OLEAUT32!__imp_SysAllocString` at `0x18001ca65`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c98d`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c9b8`
- `OLEAUT32!__imp_SysFreeString` at `0x18001ca27`
- `OLEAUT32!__imp_SysFreeString` at `0x18001ca5c`
- `OLEAUT32!__imp_SysFreeString` at `0x18001cabd`
- `OLEAUT32!__imp_SysFreeString` at `0x18001cb3a`
- `OLEAUT32!__imp_SysFreeString` at `0x18001cb80`
- `OLEAUT32!__imp_SysFreeString` at `0x18001cbbc`
- `OLEAUT32!__imp_SysFreeString` at `0x18001cd6c`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c98d`
- `OLEAUT32!__imp_SysFreeString` at `0x18001c9b8`
- `OLEAUT32!__imp_SysFreeString` at `0x18001ca27`
- `OLEAUT32!__imp_SysFreeString` at `0x18001ca5c`
- `OLEAUT32!__imp_SysFreeString` at `0x18001cabd`
- `OLEAUT32!__imp_SysFreeString` at `0x18001cb3a`
- `OLEAUT32!__imp_SysFreeString` at `0x18001cb80`
- `OLEAUT32!__imp_SysFreeString` at `0x18001cbbc`
- `OLEAUT32!__imp_SysFreeString` at `0x18001cd6c`

## string_xrefs

- `0x18001c9fe`: `COMGUARD`
- `0x18001cb00`: `LoadFromString from registry failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=9 #try_helpers=1
__int64 __fastcall WindowsPerformanceRecorder::CControlManager::QueryRunningProfile(
        BSTR *this,
        char a2,
        unsigned __int16 **a3,
        unsigned __int16 **a4,
        struct IProfileCollection **a5)
{
  OLECHAR *v10; // rbx
  unsigned int RunningProfileTraceType; // edi
  int v12; // ecx
  const unsigned __int16 *v13; // rdx
  signed int RunningProfileStringInRegistry; // edi
  OLECHAR *v15; // r14
  int v16; // edi
  signed int v17; // edi
  __int64 v18; // rcx
  int v19; // ebx
  struct IProfileCollection *v20; // rcx
  int v21; // edi
  int v22; // eax
  char *v23; // [rsp+28h] [rbp-210h]
  char *v24; // [rsp+28h] [rbp-210h]
  char v25[8]; // [rsp+30h] [rbp-208h] BYREF
  struct IProfileCollection *v26; // [rsp+38h] [rbp-200h] BYREF
  _QWORD v27[4]; // [rsp+40h] [rbp-1F8h] BYREF
  _BYTE v28[432]; // [rsp+60h] [rbp-1D8h] BYREF
  OLECHAR *psz; // [rsp+250h] [rbp+18h] BYREF

  v27[1] = -2;
  if ( !a3 )
    return 2147500035LL;
  *a3 = 0;
  *(_QWORD *)v25 = 0;
  psz = (OLECHAR *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  v10 = 0;
  v27[0] = 0;
  RunningProfileTraceType = WindowsPerformanceRecorder::CControlManager::GetRunningProfileTraceType((WindowsPerformanceRecorder::CControlManager *)this);
  if ( RunningProfileTraceType )
  {
    SysFreeString(0);
    WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&psz);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v25);
    return RunningProfileTraceType;
  }
  v12 = *((_DWORD *)this + 142);
  if ( (v12 & 1) != 0 )
    goto LABEL_15;
  if ( (v12 & 2) == 0 )
  {
    if ( (v12 & 8) != 0 )
      goto LABEL_13;
    if ( (v12 & 4) == 0 )
      goto LABEL_14;
  }
  if ( (v12 & 8) == 0 )
  {
    if ( (v12 & 2) != 0 )
    {
      a2 = 0;
LABEL_15:
      v13 = L"Normal";
      goto LABEL_16;
    }
    if ( (v12 & 4) == 0 || a2 )
    {
LABEL_14:
      SysFreeString(0);
      WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&psz);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v25);
      return 3310891008LL;
    }
  }
LABEL_13:
  v13 = L"Boot";
LABEL_16:
  RunningProfileStringInRegistry = WindowsPerformanceRecorder::CControlManager::GetRunningProfileStringInRegistry(
                                     this,
                                     v13,
                                     &psz);
  if ( RunningProfileStringInRegistry < 0 )
  {
    WindowsPerformanceRecorder::TraceHR(
      (WindowsPerformanceRecorder *)2,
      "QueryRunningProfile",
      (const char *)0x1568,
      RunningProfileStringInRegistry,
      "COMGUARD",
      v23);
    SysFreeString(0);
    WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&psz);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v25);
    return (unsigned int)RunningProfileStringInRegistry;
  }
  v15 = psz;
  if ( psz )
  {
    SysFreeString(0);
    v10 = SysAllocString(v15);
    v27[0] = v10;
    if ( !v10 )
      ATL::AtlThrowImpl(-2147024882);
  }
  v16 = WPRCCreateInstanceUnderInstanceName(
          this[28],
          &GUID_d66d26bf_6098_4b78_9d94_7bc219612ae4,
          0,
          1,
          (__int64)&GUID_71e0563a_bcbc_4784_933a_735a2ef4fb8a,
          (void (__fastcall ****)(_QWORD, GUID *, __int64 *))v25);
  if ( v16 < 0 )
    goto LABEL_22;
  v17 = (*(__int64 (__fastcall **)(_QWORD, OLECHAR *))(**(_QWORD **)v25 + 208LL))(*(_QWORD *)v25, v10);
  if ( v17 < 0 )
  {
    WindowsPerformanceRecorder::TraceHR(
      (WindowsPerformanceRecorder *)2,
      "QueryRunningProfile",
      (const char *)0x1573,
      v17,
      "LoadFromString from registry failed",
      v24);
    WindowsPerformanceRecorder::CControlManager::LogProfileXmlEvent(v18, &psz, 0);
    SysFreeString(v10);
    WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&psz);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v25);
    return (unsigned int)v17;
  }
  v16 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 **))(**(_QWORD **)v25 + 128LL))(*(_QWORD *)v25, a3);
  if ( v16 < 0 )
  {
LABEL_22:
    SysFreeString(v10);
    WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&psz);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v25);
    return (unsigned int)v16;
  }
  if ( a4 )
    *a4 = ATL::CComBSTR::Copy((ATL::CComBSTR *)v27);
  SysFreeString(v10);
  ATL::CStringData::Release((ATL::CStringData *)(v15 - 12));
  v26 = 0;
  v19 = WPRCCreateInstanceUnderInstanceName(
          this[28],
          &GUID_b98b53f3_83ba_4837_8946_e886be8d4003,
          0,
          1,
          (__int64)&GUID_bb5ed25c_a7a8_4cef_bffd_2d9c64cb457a,
          (void (__fastcall ****)(_QWORD, GUID *, __int64 *))&v26);
  if ( v19 < 0 )
  {
    if ( v26 )
      (*(void (__fastcall **)(struct IProfileCollection *, _QWORD))(*(_QWORD *)v26 + 16LL))(v26, *(_QWORD *)v26);
    if ( *(_QWORD *)v25 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v25 + 16LL))(*(_QWORD *)v25);
    return (unsigned int)v19;
  }
  v19 = (*(__int64 (__fastcall **)(struct IProfileCollection *, _QWORD, __int64))(*(_QWORD *)v26 + 56LL))(
          v26,
          *(_QWORD *)v25,
          0xFFFFFFFFLL);
  if ( v19 >= 0 )
  {
    if ( !a2 )
      goto LABEL_39;
    WindowsPerformanceRecorder::CETWProperties::CETWProperties((WindowsPerformanceRecorder::CETWProperties *)v28);
    v19 = WindowsPerformanceRecorder::CETWProperties::Initialize(
            (WindowsPerformanceRecorder::CETWProperties *)v28,
            v26,
            (struct WindowsPerformanceRecorder::CControlManager *)this,
            ((_DWORD)this[71] & 0x10) != 0);
    if ( v19 >= 0 )
      v19 = WindowsPerformanceRecorder::CControlManager::ValidateWithRuntimeState(
              (WindowsPerformanceRecorder::CControlManager *)this,
              (struct WindowsPerformanceRecorder::CETWProperties *)v28,
              0);
    WindowsPerformanceRecorder::CETWProperties::~CETWProperties((WindowsPerformanceRecorder::CETWProperties *)v28);
    if ( v19 >= 0 )
    {
LABEL_39:
      if ( a5 )
      {
        v20 = v26;
        *a5 = v26;
        (*(void (__fastcall **)(struct IProfileCollection *))(*(_QWORD *)v20 + 8LL))(v20);
LABEL_46:
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v26);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v25);
        return (unsigned int)v19;
      }
    }
  }
  psz = 0;
  v21 = ATL::CComPtrBase<IProfile>::QueryInterface<WindowsPerformanceRecorder::IProfileElement>(v25, (__int64)&psz);
  if ( v21 >= 0 )
  {
    v22 = (*(__int64 (__fastcall **)(OLECHAR *))(*(_QWORD *)psz + 32LL))(psz);
    if ( v22 >= 0 )
    {
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&psz);
      goto LABEL_46;
    }
    v21 = v22;
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&psz);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v26);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v25);
  return (unsigned int)v21;
}

```

## disassembly

```asm
0x18001c8bc  mov     rax, rsp
0x18001c8bf  push    rdi
0x18001c8c0  push    r12
0x18001c8c2  push    r13
0x18001c8c4  push    r14
0x18001c8c6  push    r15
0x18001c8c8  sub     rsp, 210h
0x18001c8cf  mov     [rsp+238h+var_1F0], 0FFFFFFFFFFFFFFFEh
0x18001c8d8  mov     [rax+8], rbx
0x18001c8dc  mov     [rax+10h], rsi
0x18001c8e0  mov     r13, r9
0x18001c8e3  mov     r15, r8
0x18001c8e6  mov     r12b, dl
0x18001c8e9  mov     rsi, rcx
0x18001c8ec  test    r8, r8
0x18001c8ef  jnz     short loc_18001C8FB
0x18001c8f1  mov     eax, 80004003h
0x18001c8f6  jmp     loc_18001CDA0
0x18001c8fb  mov     qword ptr [r8], 0
0x18001c902  mov     qword ptr [rsp+238h+var_208], 0
0x18001c90b  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18001c912  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18001c919  mov     rax, [rax+18h]
0x18001c91d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c922  add     rax, 18h
0x18001c926  mov     [rsp+238h+psz], rax
0x18001c92e  xor     ebx, ebx
0x18001c930  mov     [rsp+238h+var_1F8], rbx
0x18001c935  mov     rcx, rsi; this
0x18001c938  call    ?GetRunningProfileTraceType@CControlManager@WindowsPerformanceRecorder@@AEAAJXZ; WindowsPerformanceRecorder::CControlManager::GetRunningProfileTraceType(void)
0x18001c93d  mov     edi, eax
0x18001c93f  test    eax, eax
0x18001c941  jnz     loc_18001CD6A
0x18001c947  mov     ecx, [rsi+238h]
0x18001c94d  test    cl, 1
0x18001c950  jnz     loc_18001C9E1
0x18001c956  mov     edx, ecx
0x18001c958  mov     eax, ecx
0x18001c95a  and     eax, 8
0x18001c95d  and     edx, 2
0x18001c960  jnz     short loc_18001C96B
0x18001c962  test    eax, eax
0x18001c964  jnz     short loc_18001C982
0x18001c966  test    cl, 4
0x18001c969  jz      short loc_18001C9B6
0x18001c96b  test    eax, eax
0x18001c96d  jnz     short loc_18001C982
0x18001c96f  test    edx, edx
0x18001c971  jz      short loc_18001C978
0x18001c973  xor     r12b, r12b
0x18001c976  jmp     short loc_18001C9E1
0x18001c978  test    cl, 4
0x18001c97b  jz      short loc_18001C98B
0x18001c97d  test    r12b, r12b
0x18001c980  jnz     short loc_18001C98B
0x18001c982  lea     rdx, ?sc_wchWPRBootRegistryKey@CControlManager@WindowsPerformanceRecorder@@0QBGB; "Boot"
0x18001c989  jmp     short loc_18001C9E8
0x18001c98b  xor     ecx, ecx; bstrString
0x18001c98d  call    cs:__imp_SysFreeString
0x18001c993  nop
0x18001c994  lea     rcx, [rsp+238h+psz]; this
0x18001c99c  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x18001c9a1  nop
0x18001c9a2  lea     rcx, [rsp+238h+var_208]
0x18001c9a7  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001c9ac  mov     eax, 0C5583000h
0x18001c9b1  jmp     loc_18001CDA0
0x18001c9b6  xor     ecx, ecx; bstrString
0x18001c9b8  call    cs:__imp_SysFreeString
0x18001c9be  nop
0x18001c9bf  lea     rcx, [rsp+238h+psz]; this
0x18001c9c7  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x18001c9cc  nop
0x18001c9cd  lea     rcx, [rsp+238h+var_208]
0x18001c9d2  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001c9d7  mov     eax, 0C5583000h
0x18001c9dc  jmp     loc_18001CDA0
0x18001c9e1  lea     rdx, ?sc_wchWPRNormalRegistryKey@CControlManager@WindowsPerformanceRecorder@@0QBGB; "Normal"
0x18001c9e8  lea     r8, [rsp+238h+psz]
0x18001c9f0  mov     rcx, rsi
0x18001c9f3  call    ?GetRunningProfileStringInRegistry@CControlManager@WindowsPerformanceRecorder@@AEBAJPEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WindowsPerformanceRecorder::CControlManager::GetRunningProfileStringInRegistry(ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x18001c9f8  mov     edi, eax
0x18001c9fa  test    eax, eax
0x18001c9fc  jns     short loc_18001CA4D
0x18001c9fe  lea     rax, aComguard; "COMGUARD"
0x18001ca05  mov     [rsp+238h+Format], rax; Format
0x18001ca0a  mov     r9d, edi; unsigned int
0x18001ca0d  mov     r8d, 1568h; char *
0x18001ca13  lea     rdx, aQueryrunningpr; "QueryRunningProfile"
0x18001ca1a  mov     ecx, 2; this
0x18001ca1f  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x18001ca24  nop
0x18001ca25  xor     ecx, ecx; bstrString
0x18001ca27  call    cs:__imp_SysFreeString
0x18001ca2d  nop
0x18001ca2e  lea     rcx, [rsp+238h+psz]; this
0x18001ca36  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x18001ca3b  nop
0x18001ca3c  lea     rcx, [rsp+238h+var_208]
0x18001ca41  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001ca46  mov     eax, edi
0x18001ca48  jmp     loc_18001CDA0
0x18001ca4d  mov     r14, [rsp+238h+psz]
0x18001ca55  test    r14, r14
0x18001ca58  jz      short loc_18001CA82
0x18001ca5a  xor     ecx, ecx; bstrString
0x18001ca5c  call    cs:__imp_SysFreeString
0x18001ca62  mov     rcx, r14; psz
0x18001ca65  call    cs:__imp_SysAllocString
0x18001ca6b  mov     rbx, rax
0x18001ca6e  mov     [rsp+238h+var_1F8], rax
0x18001ca73  test    rax, rax
0x18001ca76  jnz     short loc_18001CA82
0x18001ca78  mov     ecx, 8007000Eh; int
0x18001ca7d  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001ca82  lea     rax, [rsp+238h+var_208]
0x18001ca87  mov     [rsp+238h+var_210], rax; char *
0x18001ca8c  lea     rax, _GUID_71e0563a_bcbc_4784_933a_735a2ef4fb8a
0x18001ca93  mov     [rsp+238h+Format], rax; __int64
0x18001ca98  mov     r9d, 1
0x18001ca9e  xor     r8d, r8d
0x18001caa1  lea     rdx, _GUID_d66d26bf_6098_4b78_9d94_7bc219612ae4
0x18001caa8  mov     rcx, [rsi+0E0h]; pbstr
0x18001caaf  call    WPRCCreateInstanceUnderInstanceName
0x18001cab4  mov     edi, eax
0x18001cab6  test    eax, eax
0x18001cab8  jns     short loc_18001CAE3
0x18001caba  mov     rcx, rbx; bstrString
0x18001cabd  call    cs:__imp_SysFreeString
0x18001cac3  nop
0x18001cac4  lea     rcx, [rsp+238h+psz]; this
0x18001cacc  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x18001cad1  nop
0x18001cad2  lea     rcx, [rsp+238h+var_208]
0x18001cad7  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001cadc  mov     eax, edi
0x18001cade  jmp     loc_18001CDA0
0x18001cae3  mov     rcx, qword ptr [rsp+238h+var_208]
0x18001cae8  mov     rax, [rcx]
0x18001caeb  mov     rdx, rbx
0x18001caee  mov     rax, [rax+0D0h]
0x18001caf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cafa  mov     edi, eax
0x18001cafc  test    eax, eax
0x18001cafe  jns     short loc_18001CB60
0x18001cb00  lea     rax, aLoadfromstring; "LoadFromString from registry failed"
0x18001cb07  mov     [rsp+238h+Format], rax; Format
0x18001cb0c  mov     r9d, edi; unsigned int
0x18001cb0f  mov     r8d, 1573h; char *
0x18001cb15  lea     rdx, aQueryrunningpr; "QueryRunningProfile"
0x18001cb1c  mov     ecx, 2; this
0x18001cb21  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x18001cb26  xor     r8d, r8d
0x18001cb29  lea     rdx, [rsp+238h+psz]
0x18001cb31  call    ?LogProfileXmlEvent@CControlManager@WindowsPerformanceRecorder@@AEAAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@W4__MIDL_IProfile_0001@@@Z; WindowsPerformanceRecorder::CControlManager::LogProfileXmlEvent(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,__MIDL_IProfile_0001)
0x18001cb36  nop
0x18001cb37  mov     rcx, rbx; bstrString
0x18001cb3a  call    cs:__imp_SysFreeString
0x18001cb40  nop
0x18001cb41  lea     rcx, [rsp+238h+psz]; this
0x18001cb49  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x18001cb4e  nop
0x18001cb4f  lea     rcx, [rsp+238h+var_208]
0x18001cb54  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001cb59  mov     eax, edi
0x18001cb5b  jmp     loc_18001CDA0
0x18001cb60  mov     rcx, qword ptr [rsp+238h+var_208]
0x18001cb65  mov     rax, [rcx]
0x18001cb68  mov     rdx, r15
0x18001cb6b  mov     rax, [rax+80h]
0x18001cb72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cb77  mov     edi, eax
0x18001cb79  test    eax, eax
0x18001cb7b  jns     short loc_18001CBA6
0x18001cb7d  mov     rcx, rbx; bstrString
0x18001cb80  call    cs:__imp_SysFreeString
0x18001cb86  nop
0x18001cb87  lea     rcx, [rsp+238h+psz]; this
0x18001cb8f  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x18001cb94  nop
0x18001cb95  lea     rcx, [rsp+238h+var_208]
0x18001cb9a  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001cb9f  mov     eax, edi
0x18001cba1  jmp     loc_18001CDA0
0x18001cba6  test    r13, r13
0x18001cba9  jz      short loc_18001CBB9
0x18001cbab  lea     rcx, [rsp+238h+var_1F8]; this
0x18001cbb0  call    ?Copy@CComBSTR@ATL@@QEBAPEAGXZ; ATL::CComBSTR::Copy(void)
0x18001cbb5  mov     [r13+0], rax
0x18001cbb9  mov     rcx, rbx; bstrString
0x18001cbbc  call    cs:__imp_SysFreeString
0x18001cbc2  nop
0x18001cbc3  lea     rcx, [r14-18h]; this
0x18001cbc7  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001cbcc  nop
0x18001cbcd  mov     [rsp+238h+var_200], 0
0x18001cbd6  lea     rax, [rsp+238h+var_200]
0x18001cbdb  mov     [rsp+238h+var_210], rax; __int64
0x18001cbe0  lea     rax, _GUID_bb5ed25c_a7a8_4cef_bffd_2d9c64cb457a
0x18001cbe7  mov     [rsp+238h+Format], rax; __int64
0x18001cbec  mov     r9d, 1
0x18001cbf2  xor     r8d, r8d
0x18001cbf5  lea     rdx, _GUID_b98b53f3_83ba_4837_8946_e886be8d4003
0x18001cbfc  mov     rcx, [rsi+0E0h]; pbstr
0x18001cc03  call    WPRCCreateInstanceUnderInstanceName
0x18001cc08  mov     ebx, eax
0x18001cc0a  test    eax, eax
0x18001cc0c  jns     short loc_18001CC43
0x18001cc0e  mov     rcx, [rsp+238h+var_200]
0x18001cc13  test    rcx, rcx
0x18001cc16  jz      short loc_18001CC25
0x18001cc18  mov     rdx, [rcx]
0x18001cc1b  mov     rax, [rdx+10h]
0x18001cc1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cc24  nop
0x18001cc25  mov     rcx, qword ptr [rsp+238h+var_208]
0x18001cc2a  test    rcx, rcx
0x18001cc2d  jz      short loc_18001CC3C
0x18001cc2f  mov     rax, [rcx]
0x18001cc32  mov     rax, [rax+10h]
0x18001cc36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cc3b  nop
0x18001cc3c  mov     eax, ebx
0x18001cc3e  jmp     loc_18001CDA0
0x18001cc43  mov     rcx, [rsp+238h+var_200]
0x18001cc48  mov     rax, [rcx]
0x18001cc4b  or      r8d, 0FFFFFFFFh
0x18001cc4f  mov     rdx, qword ptr [rsp+238h+var_208]
0x18001cc54  mov     rax, [rax+38h]
0x18001cc58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cc5d  mov     ebx, eax
0x18001cc5f  test    eax, eax
0x18001cc61  js      short loc_18001CCDD
0x18001cc63  test    r12b, r12b
0x18001cc66  jz      short loc_18001CCBA
0x18001cc68  lea     rcx, [rsp+238h+var_1D8]; this
0x18001cc6d  call    ??0CETWProperties@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::CETWProperties::CETWProperties(void)
0x18001cc72  nop
0x18001cc73  mov     r9d, [rsi+238h]
0x18001cc7a  shr     r9d, 4
0x18001cc7e  and     r9b, 1; bool
0x18001cc82  mov     r8, rsi; struct WindowsPerformanceRecorder::CControlManager *
0x18001cc85  mov     rdx, [rsp+238h+var_200]; struct IProfileCollection *
0x18001cc8a  lea     rcx, [rsp+238h+var_1D8]; this
0x18001cc8f  call    ?Initialize@CETWProperties@WindowsPerformanceRecorder@@QEAAJPEAUIProfileCollection@@PEAVCControlManager@2@_N@Z; WindowsPerformanceRecorder::CETWProperties::Initialize(IProfileCollection *,WindowsPerformanceRecorder::CControlManager *,bool)
0x18001cc94  mov     ebx, eax
0x18001cc96  test    eax, eax
0x18001cc98  js      short loc_18001CCAC
0x18001cc9a  xor     r8d, r8d; bool
0x18001cc9d  lea     rdx, [rsp+238h+var_1D8]; struct WindowsPerformanceRecorder::CETWProperties *
0x18001cca2  mov     rcx, rsi; this
0x18001cca5  call    ?ValidateWithRuntimeState@CControlManager@WindowsPerformanceRecorder@@AEAAJAEAVCETWProperties@2@_N@Z; WindowsPerformanceRecorder::CControlManager::ValidateWithRuntimeState(WindowsPerformanceRecorder::CETWProperties &,bool)
0x18001ccaa  mov     ebx, eax
0x18001ccac  lea     rcx, [rsp+238h+var_1D8]; this
0x18001ccb1  call    ??1CETWProperties@WindowsPerformanceRecorder@@UEAA@XZ; WindowsPerformanceRecorder::CETWProperties::~CETWProperties(void)
0x18001ccb6  test    ebx, ebx
0x18001ccb8  js      short loc_18001CCDD
0x18001ccba  mov     rax, [rsp+238h+arg_20]
0x18001ccc2  test    rax, rax
0x18001ccc5  jz      short loc_18001CCDD
0x18001ccc7  mov     rcx, [rsp+238h+var_200]
0x18001cccc  mov     [rax], rcx
0x18001cccf  mov     rax, [rcx]
0x18001ccd2  mov     rax, [rax+8]
0x18001ccd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ccdb  jmp     short loc_18001CD50
0x18001ccdd  mov     [rsp+238h+psz], 0
0x18001cce9  lea     rdx, [rsp+238h+psz]
0x18001ccf1  lea     rcx, [rsp+238h+var_208]
0x18001ccf6  call    ??$QueryInterface@UIProfileElement@WindowsPerformanceRecorder@@@?$CComPtrBase@UIProfile@@@ATL@@QEBAJPEAPEAUIProfileElement@WindowsPerformanceRecorder@@@Z; ATL::CComPtrBase<IProfile>::QueryInterface<WindowsPerformanceRecorder::IProfileElement>(WindowsPerformanceRecorder::IProfileElement * *)
0x18001ccfb  mov     edi, eax
0x18001ccfd  test    eax, eax
0x18001ccff  js      short loc_18001CD1B
0x18001cd01  mov     rcx, [rsp+238h+psz]
0x18001cd09  mov     rax, [rcx]
0x18001cd0c  mov     rax, [rax+20h]
0x18001cd10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cd15  test    eax, eax
0x18001cd17  jns     short loc_18001CD42
0x18001cd19  mov     edi, eax
0x18001cd1b  lea     rcx, [rsp+238h+psz]
0x18001cd23  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001cd28  nop
0x18001cd29  lea     rcx, [rsp+238h+var_200]
0x18001cd2e  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001cd33  nop
0x18001cd34  lea     rcx, [rsp+238h+var_208]
0x18001cd39  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001cd3e  mov     eax, edi
0x18001cd40  jmp     short loc_18001CDA0
0x18001cd42  lea     rcx, [rsp+238h+psz]
0x18001cd4a  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001cd4f  nop
0x18001cd50  lea     rcx, [rsp+238h+var_200]
0x18001cd55  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001cd5a  nop
0x18001cd5b  lea     rcx, [rsp+238h+var_208]
0x18001cd60  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001cd65  jmp     loc_18001CC3C
0x18001cd6a  xor     ecx, ecx; bstrString
  ... truncated ...
```
