# WindowsPerformanceRecorder::CControlManager::SaveSystemRundown(ulong &,ushort const *,WindowsPerformanceRecorder::CETWProperties::CEventSession const &,ATL::CHeapPtr<ulong,ATL::CCRTAllocator> &,unsigned __int64,bool)

- ea: `0x1800236b0`
- end: `0x180023b2d`
- name: `?SaveSystemRundown@CControlManager@WindowsPerformanceRecorder@@AEAAJAEAKPEBGAEBUCEventSession@CETWProperties@2@AEAV?$CHeapPtr@KVCCRTAllocator@ATL@@@ATL@@_K_N@Z`
- size: `1149`
- prototype: `__int64 __usercall@<rax>(WindowsPerformanceRecorder::CControlManager *this@<rcx>, __int64, unsigned __int64, bool)`
- caller_count: `1`
- callee_count: `26`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18003a1f0`

## callees

- `0x18000829c`
- `0x180008330`
- `0x180009a84`
- `0x180009b40`
- `0x18000eeb0`
- `0x1800131a0`
- `0x18001c5dc`
- `0x18001d190`
- `0x18001d3d8`
- `0x18001e6b8`
- `0x18001e6e0`
- `0x180021810`
- `0x1800234f0`
- `0x1800236b0`
- `0x180023b34`
- `0x180024074`
- `0x180024270`
- `0x180024598`
- `0x180026460`
- `0x180045cb4`
- `0x18004a758`
- `0x18004ece0`
- `0x18004f904`
- `0x1800581cc`
- `0x180058e54`
- `0x18008c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002370f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002370f`

## string_xrefs

- `0x180023906`: `COMGUARD`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall WindowsPerformanceRecorder::CControlManager::SaveSystemRundown(
        const unsigned __int16 **this,
        unsigned int *a2,
        const unsigned __int16 *a3,
        __int64 a4,
        unsigned int **a5,
        unsigned __int64 a6,
        bool a7)
{
  const unsigned __int16 *SessionName; // r8
  int started; // esi
  const unsigned __int16 *v12; // rax
  char IsLegacySystemCollectorName; // r12
  char *v14; // rbx
  const struct _GUID *v15; // r8
  WindowsPerformanceRecorder::CETWProperties::CEventSession *v16; // rdi
  char *FileName; // rax
  int v18; // esi
  __int64 v19; // rdx
  unsigned int v20; // r8d
  __int64 v21; // rcx
  unsigned int v22; // esi
  __int64 v23; // rax
  unsigned int v24; // edx
  __int64 (__fastcall *v25)(_QWORD, const GUID *, __int64, _QWORD, __int64, _QWORD, int, _OWORD *); // rax
  unsigned int v26; // eax
  unsigned int v27; // edx
  int v28; // r12d
  unsigned int v29; // edx
  int v30; // r12d
  unsigned int v31; // edx
  int Format; // [rsp+20h] [rbp-A1h]
  struct IControlErrorInfo *v34; // [rsp+28h] [rbp-99h]
  struct IControlErrorInfo *v35; // [rsp+28h] [rbp-99h]
  bool v36[8]; // [rsp+30h] [rbp-91h]
  unsigned __int16 *v37; // [rsp+50h] [rbp-71h] BYREF
  char *v38; // [rsp+58h] [rbp-69h] BYREF
  WindowsPerformanceRecorder::CETWProperties::CEventSession *v39; // [rsp+60h] [rbp-61h] BYREF
  unsigned int *v40; // [rsp+68h] [rbp-59h]
  __int64 v41; // [rsp+70h] [rbp-51h]
  _OWORD v42[3]; // [rsp+78h] [rbp-49h] BYREF
  struct WindowsPerformanceRecorder::CWPRControl *v43; // [rsp+A8h] [rbp-19h] BYREF
  int v44; // [rsp+B0h] [rbp-11h]
  int v45; // [rsp+B4h] [rbp-Dh]

  v41 = -2;
  v40 = a2;
  v38 = (char *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  GetCurrentThreadId();
  SessionName = WindowsPerformanceRecorder::CETWProperties::CEventSession::get_SessionName((WindowsPerformanceRecorder::CETWProperties::CEventSession *)a4);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
    &v38,
    L"%ws_Rundown_%x",
    SessionName);
  started = WindowsPerformanceRecorder::AddPrefixToSessionName(&v38);
  if ( started < 0 )
    goto LABEL_39;
  v12 = WindowsPerformanceRecorder::CETWProperties::CEventSession::get_SessionName((WindowsPerformanceRecorder::CETWProperties::CEventSession *)a4);
  IsLegacySystemCollectorName = WindowsPerformanceRecorder::CSystemCollectorElement::IsLegacySystemCollectorName(v12);
  v39 = 0;
  v14 = v38;
  started = WindowsPerformanceRecorder::CETWProperties::CreateSystemRundownSession(
              IsLegacySystemCollectorName,
              (const unsigned __int16 *)v38,
              this[28],
              this[66],
              *a5,
              a6,
              a7,
              &v39);
  v16 = v39;
  if ( started < 0 )
  {
LABEL_36:
    WindowsPerformanceRecorder::CControlManager::AddCollectorControlWarningInfo(
      (WindowsPerformanceRecorder::CControlManager *)this,
      started,
      v15,
      (const unsigned __int16 *)v14,
      a3,
      0);
    WindowsPerformanceRecorder::TraceHR(
      (WindowsPerformanceRecorder *)3,
      (unsigned __int8)"SaveSystemRundown",
      (const char *)0xEB7,
      started,
      "%ws: %ws",
      v14,
      a3);
LABEL_37:
    if ( v16 )
      WindowsPerformanceRecorder::CETWProperties::CEventSession::`scalar deleting destructor'(v16, v24);
LABEL_39:
    WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&v38);
    return (unsigned int)started;
  }
  FileName = (char *)WindowsPerformanceRecorder::CETWProperties::CEventSession::get_FileName(v39);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (__int64 *)&v37,
    FileName);
  if ( this[69] == this[70] )
  {
    std::vector<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>::_Emplace_reallocate<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const &>(
      this + 68,
      this[69],
      &v37);
  }
  else
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      this[69],
      (const void **)&v37);
    this[69] += 4;
  }
  *(_DWORD *)(*((_QWORD *)v16 + 1) + 48LL) = *(_DWORD *)(*(_QWORD *)(a4 + 8) + 48LL);
  v18 = *(unsigned __int16 *)(a4 + 204);
  v20 = (int)((double (*)(void))o_ceil_0)();
  if ( (_WORD)v18 )
  {
    v21 = *((_QWORD *)v16 + 1);
    v19 = (unsigned int)(v18 << 10) % *(_DWORD *)(v21 + 48);
    v22 = (unsigned int)(v18 << 10) / *(_DWORD *)(v21 + 48);
    if ( v22 >= v20 )
      v22 = v20;
  }
  else
  {
    v22 = v20;
  }
  *(_DWORD *)(*((_QWORD *)v16 + 1) + 52LL) = v22;
  *(_DWORD *)(*((_QWORD *)v16 + 1) + 56LL) = (int)o_ceil_0(*(unsigned int *)(*(_QWORD *)(a4 + 8) + 56LL), v19);
  *(_DWORD *)v36 = v22;
  LODWORD(v34) = *(unsigned __int16 *)(a4 + 204);
  WindowsPerformanceRecorder::TraceHR(
    (WindowsPerformanceRecorder *)4,
    (unsigned __int8)"SaveSystemRundown",
    (const char *)0xE6E,
    0,
    "User defined MinimumRundownSpace = %u, MinimumBuffers = %u",
    (const char *)v34,
    *(_QWORD *)v36);
  if ( a7 )
  {
    v23 = *((_QWORD *)v16 + 2);
    if ( v23 )
      *(_DWORD *)(v23 + 136) |= 2u;
  }
  started = WindowsPerformanceRecorder::CControlManager::StartEventSession((__int64)this, a3, (__int64)v16, 2);
  if ( started == (unsigned int)ATL::AtlHresultFromWin32(0x4C7u) )
  {
    LOBYTE(Format) = 1;
    WindowsPerformanceRecorder::CControlManager::CancelEventSession(this, a3, v16, 2, Format);
  }
  if ( started < 0 )
  {
    WindowsPerformanceRecorder::TraceHR(
      (WindowsPerformanceRecorder *)2,
      (unsigned __int8)"SaveSystemRundown",
      (const char *)0xE7D,
      started,
      "COMGUARD",
      (const char *)v35);
    WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&v37);
    goto LABEL_37;
  }
  if ( !IsLegacySystemCollectorName )
  {
    v43 = 0;
    if ( (int)WindowsPerformanceRecorder::CWPRControl::GetInstance(&v43) < 0
      || (v25 = (__int64 (__fastcall *)(_QWORD, const GUID *, __int64, _QWORD, __int64, _QWORD, int, _OWORD *))Performance::DelayLoad::CDelayLoadedImport<void * (*)(void *,unsigned short const *,unsigned long),Performance::DelayLoad::CFakeSRWLock>::operator void * (*)(void *,unsigned short const *,unsigned long)((char *)v43 + 32)) == 0 )
    {
      WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&v37);
      if ( v16 )
        WindowsPerformanceRecorder::CETWProperties::CEventSession::`scalar deleting destructor'(v16, v27);
      started = -2147418113;
      goto LABEL_39;
    }
    v45 = -2147483646;
    v43 = (struct WindowsPerformanceRecorder::CWPRControl *)(a4 + 112);
    v44 = 8;
    memset(v42, 0, 32);
    LODWORD(v42[0]) = 1;
    v42[2] = (unsigned __int64)&v43;
    v26 = v25(*((_QWORD *)v16 + 14), &SystemTraceControlGuid, 2, 0, 2, 0, -1, v42);
    if ( v26 )
      started = ATL::AtlHresultFromWin32(v26);
  }
  v28 = WindowsPerformanceRecorder::CControlManager::StopEventSession(
          (WindowsPerformanceRecorder::CControlManager *)this,
          v40,
          a3,
          v16);
  if ( v28 < 0
    || (v28 = WindowsPerformanceRecorder::CControlManager::AdjustControlProgressHandler(
                (WindowsPerformanceRecorder::CControlManager *)this,
                a3,
                (const unsigned __int16 *)v14,
                v37),
        v28 < 0) )
  {
    WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&v37);
    if ( v16 )
      WindowsPerformanceRecorder::CETWProperties::CEventSession::`scalar deleting destructor'(v16, v29);
    started = v28;
    goto LABEL_39;
  }
  v30 = WindowsPerformanceRecorder::CControlManager::ControlProgressHandler_Update(
          (WindowsPerformanceRecorder::CControlManager *)this,
          0);
  if ( v30 >= 0 )
  {
    WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&v37);
    if ( started >= 0 )
      goto LABEL_37;
    goto LABEL_36;
  }
  ATL::CStringData::Release((ATL::CStringData *)(v37 - 12));
  if ( v16 )
    WindowsPerformanceRecorder::CETWProperties::CEventSession::`scalar deleting destructor'(v16, v31);
  ATL::CStringData::Release((ATL::CStringData *)(v14 - 24));
  return (unsigned int)v30;
}

```

## disassembly

```asm
0x1800236b0  push    rbp
0x1800236b2  push    rbx
0x1800236b3  push    rsi
0x1800236b4  push    rdi
0x1800236b5  push    r12
0x1800236b7  push    r13
0x1800236b9  push    r14
0x1800236bb  push    r15
0x1800236bd  lea     rbp, [rsp-7]
0x1800236c2  sub     rsp, 0C8h
0x1800236c9  mov     [rbp+3Fh+var_90], 0FFFFFFFFFFFFFFFEh
0x1800236d1  mov     rax, cs:__security_cookie
0x1800236d8  xor     rax, rsp
0x1800236db  mov     [rbp+3Fh+var_48], rax
0x1800236df  mov     r13, r9
0x1800236e2  mov     r15, r8
0x1800236e5  mov     [rbp+3Fh+var_98], rdx
0x1800236e9  mov     r14, rcx
0x1800236ec  mov     rbx, [rbp+3Fh+arg_20]
0x1800236f0  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1800236f7  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1800236fe  mov     rax, [rax+18h]
0x180023702  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023707  add     rax, 18h
0x18002370b  mov     [rbp+3Fh+var_A8], rax
0x18002370f  call    cs:__imp_GetCurrentThreadId
0x180023715  mov     r9d, eax
0x180023718  mov     rcx, r13; this
0x18002371b  call    ?get_SessionName@CEventSession@CETWProperties@WindowsPerformanceRecorder@@QEBAPEBGXZ; WindowsPerformanceRecorder::CETWProperties::CEventSession::get_SessionName(void)
0x180023720  mov     r8, rax
0x180023723  lea     rdx, aWsRundownX; "%ws_Rundown_%x"
0x18002372a  lea     rcx, [rbp+3Fh+var_A8]
0x18002372e  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x180023733  mov     rdx, [r14+0E0h]
0x18002373a  lea     rcx, [rbp+3Fh+var_A8]; void *
0x18002373e  call    ?AddPrefixToSessionName@WindowsPerformanceRecorder@@YAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBG@Z; WindowsPerformanceRecorder::AddPrefixToSessionName(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ushort const *)
0x180023743  mov     esi, eax
0x180023745  xor     edi, edi
0x180023747  test    eax, eax
0x180023749  js      loc_180023B02
0x18002374f  mov     rcx, r13; this
0x180023752  call    ?get_SessionName@CEventSession@CETWProperties@WindowsPerformanceRecorder@@QEBAPEBGXZ; WindowsPerformanceRecorder::CETWProperties::CEventSession::get_SessionName(void)
0x180023757  mov     rcx, rax; unsigned __int16 *
0x18002375a  call    ?IsLegacySystemCollectorName@CSystemCollectorElement@WindowsPerformanceRecorder@@SA_NPEBG@Z; WindowsPerformanceRecorder::CSystemCollectorElement::IsLegacySystemCollectorName(ushort const *)
0x18002375f  mov     r12b, al
0x180023762  mov     [rbp+3Fh+var_A0], rdi
0x180023766  lea     rax, [rbp+3Fh+var_A0]
0x18002376a  mov     [rsp+100h+var_C8], rax; struct WindowsPerformanceRecorder::CETWProperties::CEventSession **
0x18002376f  mov     al, [rbp+3Fh+arg_30]
0x180023772  mov     [rsp+100h+var_D0], al; bool
0x180023776  mov     rcx, [rbp+3Fh+arg_28]
0x18002377a  mov     [rsp+100h+var_D8], rcx; unsigned __int64
0x18002377f  mov     rcx, [rbx]
0x180023782  mov     [rsp+100h+Format], rcx; unsigned int *
0x180023787  mov     r9, [r14+210h]; unsigned __int16 *
0x18002378e  mov     r8, [r14+0E0h]; unsigned __int16 *
0x180023795  mov     rbx, [rbp+3Fh+var_A8]
0x180023799  mov     rdx, rbx; unsigned __int16 *
0x18002379c  mov     cl, r12b; bool
0x18002379f  call    ?CreateSystemRundownSession@CETWProperties@WindowsPerformanceRecorder@@SAJ_NPEBG11PEAK_K0PEAPEAUCEventSession@12@@Z; WindowsPerformanceRecorder::CETWProperties::CreateSystemRundownSession(bool,ushort const *,ushort const *,ushort const *,ulong *,unsigned __int64,bool,WindowsPerformanceRecorder::CETWProperties::CEventSession * *)
0x1800237a4  mov     esi, eax
0x1800237a6  mov     rdi, [rbp+3Fh+var_A0]
0x1800237aa  test    eax, eax
0x1800237ac  js      loc_180023AA9
0x1800237b2  mov     rcx, rdi; this
0x1800237b5  call    ?get_FileName@CEventSession@CETWProperties@WindowsPerformanceRecorder@@QEBAPEBGXZ; WindowsPerformanceRecorder::CETWProperties::CEventSession::get_FileName(void)
0x1800237ba  mov     rdx, rax
0x1800237bd  lea     rcx, [rbp+3Fh+var_B0]
0x1800237c1  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1800237c6  nop
0x1800237c7  lea     rsi, [r14+220h]
0x1800237ce  mov     rax, [rsi+8]
0x1800237d2  cmp     rax, [rsi+10h]
0x1800237d6  jz      short loc_1800237EB
0x1800237d8  lea     rdx, [rbp+3Fh+var_B0]; void *
0x1800237dc  mov     rcx, rax; void *
0x1800237df  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x1800237e4  add     qword ptr [rsi+8], 8
0x1800237e9  jmp     short loc_1800237FA
0x1800237eb  lea     r8, [rbp+3Fh+var_B0]
0x1800237ef  mov     rdx, rax
0x1800237f2  mov     rcx, rsi
0x1800237f5  call    ??$_Emplace_reallocate@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@?$vector@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$allocator@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@@std@@AEAAPEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAV23@AEBV23@@Z; std::vector<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>::_Emplace_reallocate<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> * const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x1800237fa  mov     rax, [r13+8]
0x1800237fe  mov     rcx, [rdi+8]
0x180023802  mov     eax, [rax+30h]
0x180023805  mov     [rcx+30h], eax
0x180023808  movzx   esi, word ptr [r13+0CCh]
0x180023810  mov     rax, [r13+8]
0x180023814  mov     ecx, [rax+34h]
0x180023817  xorps   xmm0, xmm0
0x18002381a  cvtsi2sd xmm0, rcx
0x18002381f  mulsd   xmm0, cs:__real@3fd0000000000000
0x180023827  call    _o_ceil_0
0x18002382c  cvttsd2si r8, xmm0
0x180023831  test    si, si
0x180023834  jz      short loc_18002384F
0x180023836  mov     eax, esi
0x180023838  shl     eax, 0Ah
0x18002383b  mov     rcx, [rdi+8]
0x18002383f  xor     edx, edx
0x180023841  div     dword ptr [rcx+30h]
0x180023844  mov     esi, eax
0x180023846  cmp     eax, r8d
0x180023849  cmovnb  esi, r8d
0x18002384d  jmp     short loc_180023852
0x18002384f  mov     esi, r8d
0x180023852  mov     rax, [rdi+8]
0x180023856  mov     [rax+34h], esi
0x180023859  mov     rax, [r13+8]
0x18002385d  mov     ecx, [rax+38h]
0x180023860  xorps   xmm0, xmm0
0x180023863  cvtsi2sd xmm0, rcx
0x180023868  call    _o_ceil_0
0x18002386d  cvttsd2si rcx, xmm0
0x180023872  mov     rax, [rdi+8]
0x180023876  mov     [rax+38h], ecx
0x180023879  movzx   eax, word ptr [r13+0CCh]
0x180023881  mov     dword ptr [rsp+100h+var_D0], esi
0x180023885  mov     dword ptr [rsp+100h+var_D8], eax; char *
0x180023889  lea     rax, aUserDefinedMin; "User defined MinimumRundownSpace = %u, "...
0x180023890  mov     [rsp+100h+Format], rax; Format
0x180023895  xor     r9d, r9d; unsigned int
0x180023898  mov     r8d, 0E6Eh; char *
0x18002389e  lea     rdx, aSavesystemrund; "SaveSystemRundown"
0x1800238a5  lea     ecx, [r9+4]; this
0x1800238a9  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x1800238ae  xor     ecx, ecx
0x1800238b0  cmp     [rbp+3Fh+arg_30], cl
0x1800238b3  jz      short loc_1800238C5
0x1800238b5  mov     rax, [rdi+10h]
0x1800238b9  test    rax, rax
0x1800238bc  jz      short loc_1800238C5
0x1800238be  or      dword ptr [rax+88h], 2
0x1800238c5  mov     r9d, 2
0x1800238cb  mov     r8, rdi
0x1800238ce  mov     rdx, r15
0x1800238d1  mov     rcx, r14
0x1800238d4  call    ?StartEventSession@CControlManager@WindowsPerformanceRecorder@@AEAAJPEBGAEAUCEventSession@CETWProperties@2@W4__MIDL_IProfile_0001@@@Z; WindowsPerformanceRecorder::CControlManager::StartEventSession(ushort const *,WindowsPerformanceRecorder::CETWProperties::CEventSession &,__MIDL_IProfile_0001)
0x1800238d9  mov     esi, eax
0x1800238db  mov     ecx, 4C7h; unsigned int
0x1800238e0  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x1800238e5  cmp     esi, eax
0x1800238e7  jnz     short loc_180023902
0x1800238e9  mov     byte ptr [rsp+100h+Format], 1
0x1800238ee  mov     r9d, 2
0x1800238f4  mov     r8, rdi
0x1800238f7  mov     rdx, r15
0x1800238fa  mov     rcx, r14
0x1800238fd  call    ?CancelEventSession@CControlManager@WindowsPerformanceRecorder@@AEAAJPEBGAEAUCEventSession@CETWProperties@2@W4__MIDL_IProfile_0001@@_N@Z; WindowsPerformanceRecorder::CControlManager::CancelEventSession(ushort const *,WindowsPerformanceRecorder::CETWProperties::CEventSession &,__MIDL_IProfile_0001,bool)
0x180023902  test    esi, esi
0x180023904  jns     short loc_18002393B
0x180023906  lea     rax, aComguard; "COMGUARD"
0x18002390d  mov     [rsp+100h+Format], rax; Format
0x180023912  mov     r9d, esi; unsigned int
0x180023915  mov     r8d, 0E7Dh; char *
0x18002391b  lea     rdx, aSavesystemrund; "SaveSystemRundown"
0x180023922  mov     ecx, 2; this
0x180023927  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x18002392c  nop
0x18002392d  lea     rcx, [rbp+3Fh+var_B0]; this
0x180023931  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x180023936  jmp     loc_180023AF4
0x18002393b  test    r12b, r12b
0x18002393e  jnz     loc_180023A0B
0x180023944  xor     r12d, r12d
0x180023947  mov     [rbp+3Fh+var_58], r12
0x18002394b  lea     rcx, [rbp+3Fh+var_58]; struct WindowsPerformanceRecorder::CWPRControl **
0x18002394f  call    ?GetInstance@CWPRControl@WindowsPerformanceRecorder@@SAJPEAPEAV12@@Z; WindowsPerformanceRecorder::CWPRControl::GetInstance(WindowsPerformanceRecorder::CWPRControl * *)
0x180023954  test    eax, eax
0x180023956  js      loc_1800239EA
0x18002395c  mov     rcx, [rbp+3Fh+var_58]
0x180023960  add     rcx, 20h ; ' '
0x180023964  call    ??B?$CDelayLoadedImport@P6APEAXPEAXPEBGK@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6APEAXPEAXPEBGK@ZXZ; Performance::DelayLoad::CDelayLoadedImport<void * (*)(void *,ushort const *,ulong),Performance::DelayLoad::CFakeSRWLock>::operator void * (*)(void *,ushort const *,ulong)(void)
0x180023969  test    rax, rax
0x18002396c  jz      short loc_1800239EA
0x18002396e  mov     [rbp+3Fh+var_4C], 80000002h
0x180023975  lea     rcx, [r13+70h]
0x180023979  mov     [rbp+3Fh+var_58], rcx
0x18002397d  mov     [rbp+3Fh+var_50], 8
0x180023984  xorps   xmm0, xmm0
0x180023987  movups  [rbp+3Fh+var_88], xmm0
0x18002398b  movups  [rbp+3Fh+var_78], xmm0
0x18002398f  movups  [rbp+3Fh+var_68], xmm0
0x180023993  mov     dword ptr [rbp+3Fh+var_88], 1
0x18002399a  lea     rcx, [rbp+3Fh+var_58]
0x18002399e  mov     qword ptr [rbp+3Fh+var_68], rcx
0x1800239a2  lea     rcx, [rbp+3Fh+var_88]
0x1800239a6  mov     [rsp+100h+var_C8], rcx
0x1800239ab  mov     dword ptr [rsp+100h+var_D0], 0FFFFFFFFh
0x1800239b3  xor     r13d, r13d
0x1800239b6  mov     [rsp+100h+var_D8], r13
0x1800239bb  lea     ecx, [r12+2]
0x1800239c0  mov     [rsp+100h+Format], rcx
0x1800239c5  xor     r9d, r9d
0x1800239c8  mov     r8d, ecx
0x1800239cb  lea     rdx, SystemTraceControlGuid
0x1800239d2  mov     rcx, [rdi+70h]
0x1800239d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800239db  test    eax, eax
0x1800239dd  jz      short loc_180023A0E
0x1800239df  mov     ecx, eax; unsigned int
0x1800239e1  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x1800239e6  mov     esi, eax
0x1800239e8  jmp     short loc_180023A0E
0x1800239ea  lea     rcx, [rbp+3Fh+var_B0]; this
0x1800239ee  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x1800239f3  nop
0x1800239f4  test    rdi, rdi
0x1800239f7  jz      short loc_180023A01
0x1800239f9  mov     rcx, rdi; this
0x1800239fc  call    ??_GCEventSession@CETWProperties@WindowsPerformanceRecorder@@QEAAPEAXI@Z; WindowsPerformanceRecorder::CETWProperties::CEventSession::`scalar deleting destructor'(uint)
0x180023a01  mov     esi, 8000FFFFh
0x180023a06  jmp     loc_180023B02
0x180023a0b  xor     r13d, r13d
0x180023a0e  mov     r9, rdi; struct WindowsPerformanceRecorder::CETWProperties::CEventSession *
0x180023a11  mov     r8, r15; unsigned __int16 *
0x180023a14  mov     rdx, [rbp+3Fh+var_98]; unsigned int *
0x180023a18  mov     rcx, r14; this
0x180023a1b  call    ?StopEventSession@CControlManager@WindowsPerformanceRecorder@@AEAAJAEAKPEBGAEAUCEventSession@CETWProperties@2@@Z; WindowsPerformanceRecorder::CControlManager::StopEventSession(ulong &,ushort const *,WindowsPerformanceRecorder::CETWProperties::CEventSession &)
0x180023a20  mov     r12d, eax
0x180023a23  test    eax, eax
0x180023a25  jns     short loc_180023A46
0x180023a27  lea     rcx, [rbp+3Fh+var_B0]; this
0x180023a2b  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x180023a30  nop
0x180023a31  test    rdi, rdi
0x180023a34  jz      short loc_180023A3E
0x180023a36  mov     rcx, rdi; this
0x180023a39  call    ??_GCEventSession@CETWProperties@WindowsPerformanceRecorder@@QEAAPEAXI@Z; WindowsPerformanceRecorder::CETWProperties::CEventSession::`scalar deleting destructor'(uint)
0x180023a3e  mov     esi, r12d
0x180023a41  jmp     loc_180023B02
0x180023a46  mov     r9, [rbp+3Fh+var_B0]; unsigned __int16 *
0x180023a4a  mov     r8, rbx; unsigned __int16 *
0x180023a4d  mov     rdx, r15; unsigned __int16 *
0x180023a50  mov     rcx, r14; this
0x180023a53  call    ?AdjustControlProgressHandler@CControlManager@WindowsPerformanceRecorder@@AEAAJPEBG00@Z; WindowsPerformanceRecorder::CControlManager::AdjustControlProgressHandler(ushort const *,ushort const *,ushort const *)
0x180023a58  mov     r12d, eax
0x180023a5b  test    eax, eax
0x180023a5d  js      short loc_180023A27
0x180023a5f  xor     edx, edx; bool
0x180023a61  mov     rcx, r14; this
0x180023a64  call    ?ControlProgressHandler_Update@CControlManager@WindowsPerformanceRecorder@@QEAAJ_N@Z; WindowsPerformanceRecorder::CControlManager::ControlProgressHandler_Update(bool)
0x180023a69  mov     r12d, eax
0x180023a6c  test    eax, eax
0x180023a6e  jns     short loc_180023A9A
0x180023a70  mov     rcx, [rbp+3Fh+var_B0]
0x180023a74  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180023a78  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180023a7d  nop
0x180023a7e  test    rdi, rdi
0x180023a81  jz      short loc_180023A8C
0x180023a83  mov     rcx, rdi; this
0x180023a86  call    ??_GCEventSession@CETWProperties@WindowsPerformanceRecorder@@QEAAPEAXI@Z; WindowsPerformanceRecorder::CETWProperties::CEventSession::`scalar deleting destructor'(uint)
0x180023a8b  nop
0x180023a8c  lea     rcx, [rbx-18h]; this
0x180023a90  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180023a95  mov     eax, r12d
0x180023a98  jmp     short loc_180023B0D
0x180023a9a  lea     rcx, [rbp+3Fh+var_B0]; this
0x180023a9e  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x180023aa3  test    esi, esi
0x180023aa5  js      short loc_180023AAC
0x180023aa7  jmp     short loc_180023AF4
0x180023aa9  xor     r13d, r13d
0x180023aac  mov     [rsp+100h+var_D8], r13; struct IControlErrorInfo *
0x180023ab1  mov     [rsp+100h+Format], r15; unsigned __int16 *
0x180023ab6  mov     r9, rbx; unsigned __int16 *
0x180023ab9  mov     edx, esi; int
0x180023abb  mov     rcx, r14; this
0x180023abe  call    ?AddCollectorControlWarningInfo@CControlManager@WindowsPerformanceRecorder@@QEAAXJAEBU_GUID@@PEBG1PEAUIControlErrorInfo@@@Z; WindowsPerformanceRecorder::CControlManager::AddCollectorControlWarningInfo(long,_GUID const &,ushort const *,ushort const *,IControlErrorInfo *)
0x180023ac3  mov     qword ptr [rsp+100h+var_D0], r15
0x180023ac8  mov     [rsp+100h+var_D8], rbx; char *
0x180023acd  lea     rax, aWsWs_4; "%ws: %ws"
0x180023ad4  mov     [rsp+100h+Format], rax; Format
0x180023ad9  mov     r9d, esi; unsigned int
0x180023adc  mov     r8d, 0EB7h; char *
0x180023ae2  lea     rdx, aSavesystemrund; "SaveSystemRundown"
0x180023ae9  mov     ecx, 3; this
0x180023aee  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x180023af3  nop
0x180023af4  test    rdi, rdi
0x180023af7  jz      short loc_180023B02
0x180023af9  mov     rcx, rdi; this
0x180023afc  call    ??_GCEventSession@CETWProperties@WindowsPerformanceRecorder@@QEAAPEAXI@Z; WindowsPerformanceRecorder::CETWProperties::CEventSession::`scalar deleting destructor'(uint)
0x180023b01  nop
0x180023b02  lea     rcx, [rbp+3Fh+var_A8]; this
0x180023b06  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x180023b0b  mov     eax, esi
0x180023b0d  mov     rcx, [rbp+3Fh+var_48]
0x180023b11  xor     rcx, rsp; StackCookie
0x180023b14  call    __security_check_cookie
0x180023b19  add     rsp, 0C8h
0x180023b20  pop     r15
0x180023b22  pop     r14
0x180023b24  pop     r13
0x180023b26  pop     r12
0x180023b28  pop     rdi
0x180023b29  pop     rsi
0x180023b2a  pop     rbx
  ... truncated ...
```
