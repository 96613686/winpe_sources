# WindowsPerformanceRecorder::CControlManager::UpdateEventProviders(ushort const *,WindowsPerformanceRecorder::CETWProperties::CEventSession &)

- ea: `0x18002f230`
- end: `0x18002f5bc`
- name: `?UpdateEventProviders@CControlManager@WindowsPerformanceRecorder@@AEAAJPEBGAEAUCEventSession@CETWProperties@2@@Z`
- size: `908`
- prototype: `__int64 __fastcall(WindowsPerformanceRecorder::CControlManager *__hidden this, const unsigned __int16 *, struct WindowsPerformanceRecorder::CETWProperties::CEventSession *)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x18005ed4c`

## callees

- `0x18000829c`
- `0x180009770`
- `0x180009a84`
- `0x180009b40`
- `0x180009b90`
- `0x18000a154`
- `0x18001a8c8`
- `0x18001e6b8`
- `0x18001e6e0`
- `0x18002f230`
- `0x18002f5c4`
- `0x180039de4`
- `0x1800473a4`
- `0x18004ece0`
- `0x18004f1d0`
- `0x18005fae0`
- `0x18008c010`

## import_xrefs

- `api-ms-win-eventing-legacy-l1-1-0!EnableTraceEx` at `0x18002f46e`
- `api-ms-win-eventing-legacy-l1-1-0!EnableTraceEx` at `0x18002f46e`

## string_xrefs

- `0x18002f279`: `COMGUARD`
- `0x18002f51c`: `COMGUARD`
- `0x18002f28e`: `UpdateEventProviders`
- `0x18002f4df`: `UpdateEventProviders`
- `0x18002f531`: `UpdateEventProviders`
- `0x18002f582`: `UpdateEventProviders`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall WindowsPerformanceRecorder::CControlManager::UpdateEventProviders(
        WindowsPerformanceRecorder::CControlManager *this,
        const unsigned __int16 *a2,
        TRACEHANDLE *a3)
{
  signed int v6; // eax
  unsigned int v7; // ebx
  unsigned int v8; // edi
  __int64 (__fastcall *v10)(TRACEHANDLE, __int64, __int64, __int64, _QWORD, _QWORD, int); // r14
  void *v11; // rcx
  __int64 v12; // r8
  __int64 v13; // rbx
  signed int FilterParamsForEventProvider; // eax
  __int64 v15; // r8
  __int64 v16; // r9
  ULONG v17; // edi
  __int64 v18; // r8
  const struct _GUID *v19; // r8
  const struct _GUID *v20; // r8
  __int64 v21; // rax
  const unsigned __int16 *Level; // [rsp+28h] [rbp-E0h]
  const char *MatchAnyKeyword; // [rsp+30h] [rbp-D8h]
  const char *MatchAnyKeyworda; // [rsp+30h] [rbp-D8h]
  const char *MatchAnyKeywordb; // [rsp+30h] [rbp-D8h]
  const char *MatchAnyKeywordc; // [rsp+30h] [rbp-D8h]
  struct IControlErrorInfo *EnableProperty; // [rsp+40h] [rbp-C8h]
  void *Block[6]; // [rsp+58h] [rbp-B0h] BYREF
  int v29; // [rsp+88h] [rbp-80h]
  __int64 v30; // [rsp+90h] [rbp-78h]
  __int64 (__fastcall **v31)(void *); // [rsp+98h] [rbp-70h]
  _BYTE v32[8]; // [rsp+A0h] [rbp-68h] BYREF
  _OWORD v33[3]; // [rsp+A8h] [rbp-60h] BYREF
  _BYTE v34[16]; // [rsp+D8h] [rbp-30h] BYREF
  _BYTE v35[16]; // [rsp+E8h] [rbp-20h] BYREF
  _BYTE v36[16]; // [rsp+F8h] [rbp-10h] BYREF

  v30 = -2;
  v6 = WindowsPerformanceRecorder::CControlManager::DisableRunningProviders(
         this,
         a2,
         (struct WindowsPerformanceRecorder::CETWProperties::CEventSession *)a3);
  v7 = v6;
  v8 = 0;
  if ( v6 >= 0 )
  {
    v10 = 0;
    Block[0] = 0;
    if ( (int)WindowsPerformanceRecorder::CWPRControl::GetInstance((struct WindowsPerformanceRecorder::CWPRControl **)Block) >= 0 )
      v10 = (__int64 (__fastcall *)(TRACEHANDLE, __int64, __int64, __int64, _QWORD, _QWORD, int))Performance::DelayLoad::CDelayLoadedImport<void * (*)(void *,unsigned short const *,unsigned long),Performance::DelayLoad::CFakeSRWLock>::operator void * (*)(void *,unsigned short const *,unsigned long)((char *)Block[0] + 32);
    v13 = a3[3];
    while ( v13 != a3[4] )
    {
      if ( v10 )
      {
        memset(v33, 0, sizeof(v33));
        memset(Block, 0, sizeof(Block));
        v29 = 10;
        FilterParamsForEventProvider = WindowsPerformanceRecorder::CControlManager::GetFilterParamsForEventProvider(
                                         v11,
                                         v13,
                                         (__int64)v33,
                                         Block,
                                         (__int64)&Block[1],
                                         0);
        v8 = FilterParamsForEventProvider;
        if ( FilterParamsForEventProvider < 0 )
        {
          WindowsPerformanceRecorder::TraceHR(
            (WindowsPerformanceRecorder *)2,
            (unsigned __int8)"UpdateEventProviders",
            (const char *)0xD39,
            FilterParamsForEventProvider,
            "COMGUARD",
            MatchAnyKeyworda);
          ATL::CAtlList<ATL::CAutoVectorPtr<unsigned char>,ATL::CAutoVectorPtrElementTraits<unsigned char>>::RemoveAll(&Block[1]);
          operator delete(Block[0]);
          return v8;
        }
        v31 = &off_18008EB00;
        if ( (Microsoft_Windows_Performance_Recorder_ControlEnableBits & 1) != 0 )
          McGenEventWrite_EventWriteTransfer(
            &WindowsPerformanceRecorderControlProvider_Context,
            Perf_ExternalCall_Begin,
            v15,
            1,
            v34);
        EnableProperty = (struct IControlErrorInfo *)v33;
        LOBYTE(v16) = *(_BYTE *)(v13 + 248);
        v17 = v10(a3[14], v13, 1, v16, *(_QWORD *)(v13 + 16), 0, *(_BYTE *)(v13 + 252) != 0 ? 0x7530 : 0);
        if ( (Microsoft_Windows_Performance_Recorder_ControlEnableBits & 1) != 0 )
          McGenEventWrite_EventWriteTransfer(&WindowsPerformanceRecorderControlProvider_Context, L"e", v18, 1, v35);
        ATL::CAtlList<ATL::CAutoVectorPtr<unsigned char>,ATL::CAutoVectorPtrElementTraits<unsigned char>>::RemoveAll(&Block[1]);
        operator delete(Block[0]);
      }
      else
      {
        Block[0] = &off_18008EB00;
        if ( (Microsoft_Windows_Performance_Recorder_ControlEnableBits & 1) != 0 )
          McGenEventWrite_EventWriteTransfer(
            &WindowsPerformanceRecorderControlProvider_Context,
            Perf_ExternalCall_Begin,
            v12,
            1,
            v36);
        v17 = EnableTraceEx(
                (LPCGUID)v13,
                0,
                a3[14],
                1u,
                *(_BYTE *)(v13 + 248),
                *(_QWORD *)(v13 + 16),
                0,
                *(_DWORD *)(v13 + 232),
                0);
        WindowsPerformanceRecorder::CControlManager::SaveStateInRegistry_::_14_::CPerfEventMacro::_CPerfEventMacro(Block);
      }
      LOBYTE(v11) = 0;
      if ( v17 )
      {
        v8 = ATL::AtlHresultFromWin32(v17);
        if ( *(_BYTE *)(v13 + 252) )
        {
          WindowsPerformanceRecorder::CControlManager::SetProviderControlErrorInfo(
            this,
            v8,
            v19,
            (const struct _GUID *)v13);
          LODWORD(MatchAnyKeywordb) = *(_DWORD *)v13;
          WindowsPerformanceRecorder::TraceHR(
            (WindowsPerformanceRecorder *)2,
            (unsigned __int8)"UpdateEventProviders",
            (const char *)0xD54,
            v8,
            "Provider:(0x%x...)",
            MatchAnyKeywordb);
          return v8;
        }
        Level = WindowsPerformanceRecorder::CETWProperties::CEventSession::get_SessionName((WindowsPerformanceRecorder::CETWProperties::CEventSession *)a3);
        WindowsPerformanceRecorder::CControlManager::AddProviderControlWarningInfo(
          this,
          v8,
          v20,
          (const struct _GUID *)v13,
          Level,
          a2,
          0,
          EnableProperty);
        LODWORD(MatchAnyKeywordc) = *(_DWORD *)v13;
        WindowsPerformanceRecorder::TraceHR(
          (WindowsPerformanceRecorder *)3,
          (unsigned __int8)"UpdateEventProviders",
          (const char *)0xD5A,
          v8,
          "Provider:(0x%x...)",
          MatchAnyKeywordc);
        v13 = *(_QWORD *)std::vector<WindowsPerformanceRecorder::CETWProperties::CEventProvider>::erase(
                           a3 + 3,
                           v32,
                           v13);
        LOBYTE(v11) = 1;
      }
      v21 = v13;
      v13 += 264;
      v8 = 0;
      if ( (_BYTE)v11 )
        v13 = v21;
    }
    return v8;
  }
  else
  {
    WindowsPerformanceRecorder::TraceHR(
      (WindowsPerformanceRecorder *)2,
      (unsigned __int8)"UpdateEventProviders",
      (const char *)0xD22,
      v6,
      "COMGUARD",
      MatchAnyKeyword);
    return v7;
  }
}

```

## disassembly

```asm
0x18002f230  mov     rax, rsp
0x18002f233  push    rbp
0x18002f234  push    rsi
0x18002f235  push    rdi
0x18002f236  push    r12
0x18002f238  push    r13
0x18002f23a  push    r14
0x18002f23c  push    r15
0x18002f23e  lea     rbp, [rax-48h]
0x18002f242  sub     rsp, 110h
0x18002f249  mov     [rbp+40h+var_B8], 0FFFFFFFFFFFFFFFEh
0x18002f251  mov     [rax+20h], rbx
0x18002f255  mov     rax, cs:__security_cookie
0x18002f25c  xor     rax, rsp
0x18002f25f  mov     [rbp+40h+var_40], rax
0x18002f263  mov     rsi, r8
0x18002f266  mov     r13, rdx
0x18002f269  mov     r15, rcx
0x18002f26c  call    ?DisableRunningProviders@CControlManager@WindowsPerformanceRecorder@@AEAAJPEBGAEAUCEventSession@CETWProperties@2@@Z; WindowsPerformanceRecorder::CControlManager::DisableRunningProviders(ushort const *,WindowsPerformanceRecorder::CETWProperties::CEventSession &)
0x18002f271  mov     ebx, eax
0x18002f273  xor     edi, edi
0x18002f275  test    eax, eax
0x18002f277  jns     short loc_18002F2A4
0x18002f279  lea     rcx, aComguard; "COMGUARD"
0x18002f280  mov     qword ptr [rsp+140h+Level], rcx; Format
0x18002f285  mov     r9d, eax; unsigned int
0x18002f288  mov     r8d, 0D22h; char *
0x18002f28e  lea     rdx, aUpdateeventpro; "UpdateEventProviders"
0x18002f295  lea     ecx, [rdi+2]; this
0x18002f298  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x18002f29d  mov     eax, ebx
0x18002f29f  jmp     loc_18002F595
0x18002f2a4  mov     r14, rdi
0x18002f2a7  mov     [rsp+140h+Block], rdi
0x18002f2ac  lea     rcx, [rsp+140h+Block]; struct WindowsPerformanceRecorder::CWPRControl **
0x18002f2b1  call    ?GetInstance@CWPRControl@WindowsPerformanceRecorder@@SAJPEAPEAV12@@Z; WindowsPerformanceRecorder::CWPRControl::GetInstance(WindowsPerformanceRecorder::CWPRControl * *)
0x18002f2b6  test    eax, eax
0x18002f2b8  js      short loc_18002F2CB
0x18002f2ba  mov     rcx, [rsp+140h+Block]
0x18002f2bf  add     rcx, 20h ; ' '
0x18002f2c3  call    ??B?$CDelayLoadedImport@P6APEAXPEAXPEBGK@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6APEAXPEAXPEBGK@ZXZ; Performance::DelayLoad::CDelayLoadedImport<void * (*)(void *,ushort const *,ulong),Performance::DelayLoad::CFakeSRWLock>::operator void * (*)(void *,ushort const *,ulong)(void)
0x18002f2c8  mov     r14, rax
0x18002f2cb  mov     rbx, [rsi+18h]
0x18002f2cf  cmp     rbx, [rsi+20h]
0x18002f2d3  jz      loc_18002F593
0x18002f2d9  test    r14, r14
0x18002f2dc  jz      loc_18002F401
0x18002f2e2  xorps   xmm0, xmm0
0x18002f2e5  movups  [rbp+40h+var_A0], xmm0
0x18002f2e9  movups  [rbp+40h+var_90], xmm0
0x18002f2ed  movups  [rbp+40h+var_80], xmm0
0x18002f2f1  mov     [rsp+140h+Block], rdi
0x18002f2f6  movdqu  xmmword ptr [rsp+140h+Block+8], xmm0
0x18002f2fc  mov     qword ptr [rsp+140h+var_D8], rdi
0x18002f301  xorps   xmm1, xmm1
0x18002f304  movdqu  xmmword ptr [rsp+140h+var_D8+8], xmm1
0x18002f30a  mov     [rbp+40h+var_C0], 0Ah
0x18002f311  mov     [rsp+140h+MatchAnyKeyword], rdi; char *
0x18002f316  lea     rax, [rsp+140h+Block+8]
0x18002f31b  mov     qword ptr [rsp+140h+Level], rax
0x18002f320  lea     r9, [rsp+140h+Block]
0x18002f325  lea     r8, [rbp+40h+var_A0]
0x18002f329  mov     rdx, rbx
0x18002f32c  call    ?GetFilterParamsForEventProvider@CControlManager@WindowsPerformanceRecorder@@AEAAJAEBUCEventProvider@CETWProperties@2@AEAU_ENABLE_TRACE_PARAMETERS@@AEAV?$CAutoVectorPtr@U_EVENT_FILTER_DESCRIPTOR@@@ATL@@AEAV?$CAutoVectorPtrList@E@12@PEAK@Z; WindowsPerformanceRecorder::CControlManager::GetFilterParamsForEventProvider(WindowsPerformanceRecorder::CETWProperties::CEventProvider const &,_ENABLE_TRACE_PARAMETERS &,ATL::CAutoVectorPtr<_EVENT_FILTER_DESCRIPTOR> &,WindowsPerformanceRecorder::CControlManager::CAutoVectorPtrList<uchar> &,ulong *)
0x18002f331  mov     edi, eax
0x18002f333  test    eax, eax
0x18002f335  js      loc_18002F51C
0x18002f33b  lea     rax, off_18008EB00
0x18002f342  mov     [rbp+40h+var_B0], rax
0x18002f346  mov     edi, 1
0x18002f34b  test    byte ptr cs:Microsoft_Windows_Performance_Recorder_ControlEnableBits, dil
0x18002f352  jz      short loc_18002F374
0x18002f354  lea     rax, [rbp+40h+var_70]
0x18002f358  mov     qword ptr [rsp+140h+Level], rax
0x18002f35d  mov     r9d, edi
0x18002f360  lea     rdx, Perf_ExternalCall_Begin
0x18002f367  lea     rcx, WindowsPerformanceRecorderControlProvider_Context
0x18002f36e  call    McGenEventWrite_EventWriteTransfer
0x18002f373  nop
0x18002f374  mov     al, [rbx+0FCh]
0x18002f37a  neg     al
0x18002f37c  sbb     ecx, ecx
0x18002f37e  and     ecx, 7530h
0x18002f384  lea     rax, [rbp+40h+var_A0]
0x18002f388  mov     qword ptr [rsp+140h+EnableProperty], rax
0x18002f38d  mov     dword ptr [rsp+140h+MatchAllKeyword], ecx
0x18002f391  mov     [rsp+140h+MatchAnyKeyword], 0
0x18002f39a  mov     rax, [rbx+10h]
0x18002f39e  mov     qword ptr [rsp+140h+Level], rax
0x18002f3a3  mov     r9b, [rbx+0F8h]
0x18002f3aa  mov     r8d, edi
0x18002f3ad  mov     rdx, rbx
0x18002f3b0  mov     rcx, [rsi+70h]
0x18002f3b4  mov     rax, r14
0x18002f3b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f3bc  mov     edi, eax
0x18002f3be  test    byte ptr cs:Microsoft_Windows_Performance_Recorder_ControlEnableBits, 1
0x18002f3c5  jz      short loc_18002F3EA
0x18002f3c7  lea     rax, [rbp+40h+var_60]
0x18002f3cb  mov     qword ptr [rsp+140h+Level], rax
0x18002f3d0  mov     r9d, 1
0x18002f3d6  lea     rdx, Perf_ExternalCall_End; "e"
0x18002f3dd  lea     rcx, WindowsPerformanceRecorderControlProvider_Context
0x18002f3e4  call    McGenEventWrite_EventWriteTransfer
0x18002f3e9  nop
0x18002f3ea  lea     rcx, [rsp+140h+Block+8]
0x18002f3ef  call    ?RemoveAll@?$CAtlList@V?$CAutoVectorPtr@E@ATL@@V?$CAutoVectorPtrElementTraits@E@2@@ATL@@QEAAXXZ; ATL::CAtlList<ATL::CAutoVectorPtr<uchar>,ATL::CAutoVectorPtrElementTraits<uchar>>::RemoveAll(void)
0x18002f3f4  nop
0x18002f3f5  mov     rcx, [rsp+140h+Block]; Block
0x18002f3fa  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002f3ff  jmp     short loc_18002F480
0x18002f401  lea     rax, off_18008EB00
0x18002f408  mov     [rsp+140h+Block], rax
0x18002f40d  test    byte ptr cs:Microsoft_Windows_Performance_Recorder_ControlEnableBits, 1
0x18002f414  jz      short loc_18002F438
0x18002f416  lea     rax, [rbp+40h+var_50]
0x18002f41a  mov     qword ptr [rsp+140h+Level], rax
0x18002f41f  mov     r9d, 1
0x18002f425  lea     rdx, Perf_ExternalCall_Begin
0x18002f42c  lea     rcx, WindowsPerformanceRecorderControlProvider_Context
0x18002f433  call    McGenEventWrite_EventWriteTransfer
0x18002f438  mov     [rsp+40h], rdi; EnableFilterDesc
0x18002f43d  mov     eax, [rbx+0E8h]
0x18002f443  mov     [rsp+140h+EnableProperty], eax; struct IControlErrorInfo *
0x18002f447  mov     [rsp+140h+MatchAllKeyword], rdi; MatchAllKeyword
0x18002f44c  mov     rax, [rbx+10h]
0x18002f450  mov     [rsp+140h+MatchAnyKeyword], rax; MatchAnyKeyword
0x18002f455  mov     al, [rbx+0F8h]
0x18002f45b  mov     [rsp+140h+Level], al; Level
0x18002f45f  mov     r9d, 1; IsEnabled
0x18002f465  mov     r8, [rsi+70h]; TraceHandle
0x18002f469  xor     edx, edx; SourceId
0x18002f46b  mov     rcx, rbx; ProviderId
0x18002f46e  call    cs:__imp_EnableTraceEx
0x18002f474  mov     edi, eax
0x18002f476  lea     rcx, [rsp+140h+Block]
0x18002f47b  call    _WindowsPerformanceRecorder__CControlManager__SaveStateInRegistry____14___CPerfEventMacro___CPerfEventMacro
0x18002f480  xor     cl, cl
0x18002f482  test    edi, edi
0x18002f484  jz      short loc_18002F505
0x18002f486  mov     ecx, edi; unsigned int
0x18002f488  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x18002f48d  mov     edi, eax
0x18002f48f  cmp     byte ptr [rbx+0FCh], 0
0x18002f496  jnz     loc_18002F55A
0x18002f49c  mov     rcx, rsi; this
0x18002f49f  call    ?get_SessionName@CEventSession@CETWProperties@WindowsPerformanceRecorder@@QEBAPEBGXZ; WindowsPerformanceRecorder::CETWProperties::CEventSession::get_SessionName(void)
0x18002f4a4  mov     [rsp+140h+MatchAllKeyword], 0; unsigned __int16 *
0x18002f4ad  mov     [rsp+140h+MatchAnyKeyword], r13; unsigned __int16 *
0x18002f4b2  mov     qword ptr [rsp+140h+Level], rax; unsigned __int16 *
0x18002f4b7  mov     r9, rbx; struct _GUID *
0x18002f4ba  mov     edx, edi; int
0x18002f4bc  mov     rcx, r15; this
0x18002f4bf  call    ?AddProviderControlWarningInfo@CControlManager@WindowsPerformanceRecorder@@QEAAXJAEBU_GUID@@PEBU3@PEBG22PEAUIControlErrorInfo@@@Z; WindowsPerformanceRecorder::CControlManager::AddProviderControlWarningInfo(long,_GUID const &,_GUID const *,ushort const *,ushort const *,ushort const *,IControlErrorInfo *)
0x18002f4c4  mov     eax, [rbx]
0x18002f4c6  mov     dword ptr [rsp+140h+MatchAnyKeyword], eax; char *
0x18002f4ca  lea     rax, aProvider0xX; "Provider:(0x%x...)"
0x18002f4d1  mov     qword ptr [rsp+140h+Level], rax; Format
0x18002f4d6  mov     r9d, edi; unsigned int
0x18002f4d9  mov     r8d, 0D5Ah; char *
0x18002f4df  lea     rdx, aUpdateeventpro; "UpdateEventProviders"
0x18002f4e6  mov     ecx, 3; this
0x18002f4eb  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x18002f4f0  mov     r8, rbx
0x18002f4f3  lea     rdx, [rbp+40h+var_A8]
0x18002f4f7  lea     rcx, [rsi+18h]
0x18002f4fb  call    ?erase@?$vector@UCEventProvider@CETWProperties@WindowsPerformanceRecorder@@V?$allocator@UCEventProvider@CETWProperties@WindowsPerformanceRecorder@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UCEventProvider@CETWProperties@WindowsPerformanceRecorder@@@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@UCEventProvider@CETWProperties@WindowsPerformanceRecorder@@@std@@@std@@@2@@Z; std::vector<WindowsPerformanceRecorder::CETWProperties::CEventProvider>::erase(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<WindowsPerformanceRecorder::CETWProperties::CEventProvider>>>)
0x18002f500  mov     rbx, [rax]
0x18002f503  mov     cl, 1
0x18002f505  mov     rax, rbx
0x18002f508  add     rbx, 108h
0x18002f50f  xor     edi, edi
0x18002f511  test    cl, cl
0x18002f513  cmovnz  rbx, rax
0x18002f517  jmp     loc_18002F2CF
0x18002f51c  lea     rcx, aComguard; "COMGUARD"
0x18002f523  mov     qword ptr [rsp+140h+Level], rcx; Format
0x18002f528  mov     r9d, edi; unsigned int
0x18002f52b  mov     r8d, 0D39h; char *
0x18002f531  lea     rdx, aUpdateeventpro; "UpdateEventProviders"
0x18002f538  mov     ecx, 2; this
0x18002f53d  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x18002f542  nop
0x18002f543  lea     rcx, [rsp+140h+Block+8]
0x18002f548  call    ?RemoveAll@?$CAtlList@V?$CAutoVectorPtr@E@ATL@@V?$CAutoVectorPtrElementTraits@E@2@@ATL@@QEAAXXZ; ATL::CAtlList<ATL::CAutoVectorPtr<uchar>,ATL::CAutoVectorPtrElementTraits<uchar>>::RemoveAll(void)
0x18002f54d  nop
0x18002f54e  mov     rcx, [rsp+140h+Block]; Block
0x18002f553  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002f558  jmp     short loc_18002F593
0x18002f55a  mov     r9, rbx; struct _GUID *
0x18002f55d  mov     edx, edi; int
0x18002f55f  mov     rcx, r15; this
0x18002f562  call    ?SetProviderControlErrorInfo@CControlManager@WindowsPerformanceRecorder@@QEAAXJAEBU_GUID@@PEBU3@@Z; WindowsPerformanceRecorder::CControlManager::SetProviderControlErrorInfo(long,_GUID const &,_GUID const *)
0x18002f567  mov     eax, [rbx]
0x18002f569  mov     dword ptr [rsp+140h+MatchAnyKeyword], eax; char *
0x18002f56d  lea     rax, aProvider0xX; "Provider:(0x%x...)"
0x18002f574  mov     qword ptr [rsp+140h+Level], rax; Format
0x18002f579  mov     r9d, edi; unsigned int
0x18002f57c  mov     r8d, 0D54h; char *
0x18002f582  lea     rdx, aUpdateeventpro; "UpdateEventProviders"
0x18002f589  mov     ecx, 2; this
0x18002f58e  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x18002f593  mov     eax, edi
0x18002f595  mov     rcx, [rbp+40h+var_40]
0x18002f599  xor     rcx, rsp; StackCookie
0x18002f59c  call    __security_check_cookie
0x18002f5a1  mov     rbx, [rsp+140h+arg_18]
0x18002f5a9  add     rsp, 110h
0x18002f5b0  pop     r15
0x18002f5b2  pop     r14
0x18002f5b4  pop     r13
0x18002f5b6  pop     r12
0x18002f5b8  pop     rdi
0x18002f5b9  pop     rsi
0x18002f5ba  pop     rbp
0x18002f5bb  retn
```
