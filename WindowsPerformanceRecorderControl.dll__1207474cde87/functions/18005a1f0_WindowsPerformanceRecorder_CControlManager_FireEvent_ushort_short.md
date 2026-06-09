# WindowsPerformanceRecorder::CControlManager::FireEvent(ushort *,short)

- ea: `0x18005a1f0`
- end: `0x18005a570`
- name: `?FireEvent@CControlManager@WindowsPerformanceRecorder@@UEAAJPEAGF@Z`
- size: `896`
- prototype: `__int64 __fastcall(WindowsPerformanceRecorder::CControlManager *__hidden this, unsigned __int16 *, __int16)`
- caller_count: `0`
- callee_count: `14`
- tags: `broker_com_uri`

## callees

- `0x180008330`
- `0x18001a92c`
- `0x18001c8bc`
- `0x18001d1bc`
- `0x18001e6e0`
- `0x1800234f0`
- `0x1800248d8`
- `0x180039be8`
- `0x180040a04`
- `0x18004ed10`
- `0x18005a1f0`
- `0x18005b044`
- `0x1800600a0`
- `0x18008c010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18005a28b`
- `OLEAUT32!__imp_SysFreeString` at `0x18005a2b9`
- `OLEAUT32!__imp_SysFreeString` at `0x18005a28b`
- `OLEAUT32!__imp_SysFreeString` at `0x18005a2b9`

## string_xrefs

- `0x18005a25f`: `COMGUARD`
- `0x18005a303`: `COMGUARD`
- `0x18005a3f4`: `COMGUARD`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall WindowsPerformanceRecorder::CControlManager::FireEvent(
        WindowsPerformanceRecorder::CControlManager *this,
        char *a2,
        unsigned __int16 a3)
{
  WindowsPerformanceRecorder::CControlManager *v4; // r12
  signed int v5; // eax
  unsigned int v6; // ebx
  __int64 result; // rax
  __int64 v8; // rbx
  signed int v9; // eax
  int v10; // esi
  char v11; // al
  const struct WindowsPerformanceRecorder::CETWProperties::CEventSession **v12; // r14
  const struct WindowsPerformanceRecorder::CETWProperties::CEventSession **v13; // r13
  __int64 v14; // rcx
  signed int v15; // eax
  const struct WindowsPerformanceRecorder::CETWProperties::CEventSession **v16; // rsi
  const struct WindowsPerformanceRecorder::CETWProperties::CEventSession **v17; // r13
  const struct WindowsPerformanceRecorder::CETWProperties::CEventSession *v18; // r14
  WindowsPerformanceRecorder::CControlManager *v19; // rcx
  int v20; // r15d
  const char *v21; // [rsp+28h] [rbp-50h]
  BSTR bstrString[2]; // [rsp+30h] [rbp-48h] BYREF
  WindowsPerformanceRecorder::CETWProperties *v23; // [rsp+40h] [rbp-38h]
  DWORD *v24; // [rsp+48h] [rbp-30h] BYREF
  unsigned __int16 *v25; // [rsp+80h] [rbp+8h] BYREF
  unsigned __int16 v26; // [rsp+90h] [rbp+18h]
  struct IProfileCollection *v27; // [rsp+98h] [rbp+20h] BYREF

  v26 = a3;
  bstrString[1] = (BSTR)-2LL;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (__int64 *)&v25,
    a2);
  try
  {
    v27 = 0;
    bstrString[0] = 0;
    v4 = (WindowsPerformanceRecorder::CControlManager *)((char *)this - 200);
    v5 = WindowsPerformanceRecorder::CControlManager::QueryRunningProfile(
           (WindowsPerformanceRecorder::CControlManager *)((char *)this - 200),
           0,
           bstrString,
           0,
           &v27);
    v6 = v5;
    if ( v5 >= 0 )
    {
      SysFreeString(bstrString[0]);
      bstrString[0] = 0;
      v23 = (WindowsPerformanceRecorder::CETWProperties *)operator new(0x1A8u);
      v8 = WindowsPerformanceRecorder::CETWProperties::CETWProperties(v23);
      bstrString[0] = (BSTR)v8;
      v9 = WindowsPerformanceRecorder::CETWProperties::Initialize(
             (WindowsPerformanceRecorder::CETWProperties *)v8,
             v27,
             (WindowsPerformanceRecorder::CControlManager *)((char *)this - 200),
             0);
      v10 = v9;
      if ( v9 >= 0 )
      {
        v11 = 0;
        v12 = *(const struct WindowsPerformanceRecorder::CETWProperties::CEventSession ***)(v8 + 8);
        v13 = *(const struct WindowsPerformanceRecorder::CETWProperties::CEventSession ***)(v8 + 16);
        while ( v12 != v13 )
        {
          if ( *(_DWORD *)*v12 == 1 )
          {
            v10 = WindowsPerformanceRecorder::CControlManager::SetRunningEventTraceProperties(
                    (WindowsPerformanceRecorder::CControlManager *)((char *)this - 200),
                    *v12);
            if ( v10 < 0 )
            {
              if ( v8 )
                (**(void (__fastcall ***)(__int64, __int64))v8)(v8, 1);
              goto LABEL_18;
            }
            v15 = WindowsPerformanceRecorder::CControlManager::LogLegacyMark(
                    v14,
                    *(_QWORD *)(*((_QWORD *)this + 24) + 8LL),
                    &v25,
                    v26);
            v10 = v15;
            if ( v15 < 0 )
            {
              WindowsPerformanceRecorder::TraceHR(
                (WindowsPerformanceRecorder *)2,
                "FireEvent",
                (const char *)0x677,
                v15,
                "COMGUARD",
                v21);
              if ( v8 )
                (**(void (__fastcall ***)(__int64, __int64))v8)(v8, 1);
              goto LABEL_18;
            }
            v11 = 1;
          }
          ++v12;
        }
        if ( !v11 )
        {
          v16 = *(const struct WindowsPerformanceRecorder::CETWProperties::CEventSession ***)(v8 + 8);
          v17 = *(const struct WindowsPerformanceRecorder::CETWProperties::CEventSession ***)(v8 + 16);
          while ( v16 != v17 )
          {
            v18 = *v16;
            if ( *(_DWORD *)*v16 != 1 )
            {
              v20 = WindowsPerformanceRecorder::CControlManager::SetRunningEventTraceProperties(v4, *v16);
              if ( v20 < 0 )
              {
                if ( v8 )
                  (**(void (__fastcall ***)(__int64, __int64))v8)(v8, 1);
                ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v27);
                WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&v25);
                return (unsigned int)v20;
              }
              if ( WindowsPerformanceRecorder::CControlManager::LogMark(v19, *((_QWORD *)v18 + 14), v25) >= 0 )
                break;
            }
            ++v16;
          }
        }
        if ( (Microsoft_Windows_Performance_Recorder_ContextEnableBits & 1) != 0 )
          McTemplateU0zz_EventWriteTransfer(
            &WindowsPerformanceRecorderContextProvider_Context,
            InformationCapture_FireEvent,
            v25,
            L"Trace Marker");
        if ( v8 )
          (**(void (__fastcall ***)(__int64, __int64))v8)(v8, 1);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v27);
        WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&v25);
        result = 0;
      }
      else
      {
        WindowsPerformanceRecorder::TraceHR(
          (WindowsPerformanceRecorder *)2,
          "FireEvent",
          (const char *)0x66A,
          v9,
          "COMGUARD",
          v21);
        if ( v8 )
          (**(void (__fastcall ***)(__int64, __int64))v8)(v8, 1);
LABEL_18:
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v27);
        WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&v25);
        result = (unsigned int)v10;
      }
    }
    else
    {
      WindowsPerformanceRecorder::TraceHR(
        (WindowsPerformanceRecorder *)2,
        "FireEvent",
        (const char *)0x664,
        v5,
        "COMGUARD",
        v21);
      SysFreeString(bstrString[0]);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v27);
      WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&v25);
      result = v6;
    }
  }
  catch ( ATL::CAtlException *v24 )
  {
    SetLastError(*v24);
    WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&v25);
    return 2147500037LL;
  }
  return result;
}

```

## disassembly

```asm
0x18005a1f0  mov     rax, rsp
0x18005a1f3  mov     [rax+18h], r8w
0x18005a1f8  push    rsi
0x18005a1f9  push    r12
0x18005a1fb  push    r13
0x18005a1fd  push    r14
0x18005a1ff  push    r15
0x18005a201  sub     rsp, 50h
0x18005a205  mov     qword ptr [rax-40h], 0FFFFFFFFFFFFFFFEh
0x18005a20d  mov     [rax+10h], rbx
0x18005a211  mov     r15, rcx
0x18005a214  lea     rcx, [rax+8]
0x18005a218  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18005a21d  nop
0x18005a21e  mov     [rsp+78h+arg_18], 0
0x18005a22a  mov     [rsp+78h+bstrString], 0
0x18005a233  lea     r12, [r15-0C8h]
0x18005a23a  lea     rax, [rsp+78h+arg_18]
0x18005a242  mov     [rsp+78h+Format], rax; struct IProfileCollection **
0x18005a247  xor     r9d, r9d; unsigned __int16 **
0x18005a24a  lea     r8, [rsp+78h+bstrString]; unsigned __int16 **
0x18005a24f  xor     edx, edx; bool
0x18005a251  mov     rcx, r12; this
0x18005a254  call    ?QueryRunningProfile@CControlManager@WindowsPerformanceRecorder@@AEAAJ_NPEAPEAG1PEAPEAUIProfileCollection@@@Z; WindowsPerformanceRecorder::CControlManager::QueryRunningProfile(bool,ushort * *,ushort * *,IProfileCollection * *)
0x18005a259  mov     ebx, eax
0x18005a25b  test    eax, eax
0x18005a25d  jns     short loc_18005A2B4
0x18005a25f  lea     rcx, aComguard; "COMGUARD"
0x18005a266  mov     [rsp+78h+Format], rcx; Format
0x18005a26b  mov     r9d, eax; unsigned int
0x18005a26e  mov     r8d, 664h; char *
0x18005a274  lea     rdx, aFireevent; "FireEvent"
0x18005a27b  mov     ecx, 2; this
0x18005a280  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x18005a285  nop
0x18005a286  mov     rcx, [rsp+78h+bstrString]; bstrString
0x18005a28b  call    cs:__imp_SysFreeString
0x18005a291  nop
0x18005a292  lea     rcx, [rsp+78h+arg_18]
0x18005a29a  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18005a29f  nop
0x18005a2a0  lea     rcx, [rsp+78h+arg_0]; this
0x18005a2a8  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x18005a2ad  mov     eax, ebx
0x18005a2af  jmp     loc_18005A55A
0x18005a2b4  mov     rcx, [rsp+78h+bstrString]; bstrString
0x18005a2b9  call    cs:__imp_SysFreeString
0x18005a2bf  mov     [rsp+78h+bstrString], 0
0x18005a2c8  mov     ecx, 1A8h; Size
0x18005a2cd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005a2d2  mov     [rsp+78h+var_38], rax
0x18005a2d7  mov     rcx, rax; this
0x18005a2da  call    ??0CETWProperties@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::CETWProperties::CETWProperties(void)
0x18005a2df  mov     rbx, rax
0x18005a2e2  mov     [rsp+78h+bstrString], rax
0x18005a2e7  xor     r9d, r9d; bool
0x18005a2ea  mov     r8, r12; struct WindowsPerformanceRecorder::CControlManager *
0x18005a2ed  mov     rdx, [rsp+78h+arg_18]; struct IProfileCollection *
0x18005a2f5  mov     rcx, rax; this
0x18005a2f8  call    ?Initialize@CETWProperties@WindowsPerformanceRecorder@@QEAAJPEAUIProfileCollection@@PEAVCControlManager@2@_N@Z; WindowsPerformanceRecorder::CETWProperties::Initialize(IProfileCollection *,WindowsPerformanceRecorder::CControlManager *,bool)
0x18005a2fd  mov     esi, eax
0x18005a2ff  test    eax, eax
0x18005a301  jns     short loc_18005A365
0x18005a303  lea     rcx, aComguard; "COMGUARD"
0x18005a30a  mov     [rsp+78h+Format], rcx; Format
0x18005a30f  mov     r9d, eax; unsigned int
0x18005a312  mov     r8d, 66Ah; char *
0x18005a318  lea     rdx, aFireevent; "FireEvent"
0x18005a31f  mov     ecx, 2; this
0x18005a324  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x18005a329  nop
0x18005a32a  test    rbx, rbx
0x18005a32d  jz      short loc_18005A343
0x18005a32f  mov     rax, [rbx]
0x18005a332  mov     edx, 1
0x18005a337  mov     rcx, rbx
0x18005a33a  mov     rax, [rax]
0x18005a33d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a342  nop
0x18005a343  lea     rcx, [rsp+78h+arg_18]
0x18005a34b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18005a350  nop
0x18005a351  lea     rcx, [rsp+78h+arg_0]; this
0x18005a359  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x18005a35e  mov     eax, esi
0x18005a360  jmp     loc_18005A55A
0x18005a365  xor     al, al
0x18005a367  mov     r14, [rbx+8]
0x18005a36b  mov     r13, [rbx+10h]
0x18005a36f  cmp     r14, r13
0x18005a372  jz      loc_18005A461
0x18005a378  mov     rdx, [r14]; struct WindowsPerformanceRecorder::CETWProperties::CEventSession *
0x18005a37b  cmp     dword ptr [rdx], 1
0x18005a37e  jnz     loc_18005A458
0x18005a384  mov     rcx, r12; this
0x18005a387  call    ?SetRunningEventTraceProperties@CControlManager@WindowsPerformanceRecorder@@AEAAJAEBUCEventSession@CETWProperties@2@@Z; WindowsPerformanceRecorder::CControlManager::SetRunningEventTraceProperties(WindowsPerformanceRecorder::CETWProperties::CEventSession const &)
0x18005a38c  mov     esi, eax
0x18005a38e  test    eax, eax
0x18005a390  jns     short loc_18005A3CD
0x18005a392  test    rbx, rbx
0x18005a395  jz      short loc_18005A3AB
0x18005a397  mov     rcx, [rbx]
0x18005a39a  mov     rax, [rcx]
0x18005a39d  mov     edx, 1
0x18005a3a2  mov     rcx, rbx
0x18005a3a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a3aa  nop
0x18005a3ab  lea     rcx, [rsp+78h+arg_18]
0x18005a3b3  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18005a3b8  nop
0x18005a3b9  lea     rcx, [rsp+78h+arg_0]; this
0x18005a3c1  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x18005a3c6  mov     eax, esi
0x18005a3c8  jmp     loc_18005A55A
0x18005a3cd  mov     rdx, [r15+0C0h]
0x18005a3d4  movzx   r9d, [rsp+78h+arg_10]
0x18005a3dd  lea     r8, [rsp+78h+arg_0]
0x18005a3e5  mov     rdx, [rdx+8]
0x18005a3e9  call    ?LogLegacyMark@CControlManager@WindowsPerformanceRecorder@@AEAAJ_KAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@F@Z; WindowsPerformanceRecorder::CControlManager::LogLegacyMark(unsigned __int64,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,short)
0x18005a3ee  mov     esi, eax
0x18005a3f0  test    eax, eax
0x18005a3f2  jns     short loc_18005A456
0x18005a3f4  lea     rcx, aComguard; "COMGUARD"
0x18005a3fb  mov     [rsp+78h+Format], rcx; Format
0x18005a400  mov     r9d, eax; unsigned int
0x18005a403  mov     r8d, 677h; char *
0x18005a409  lea     rdx, aFireevent; "FireEvent"
0x18005a410  mov     ecx, 2; this
0x18005a415  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x18005a41a  nop
0x18005a41b  test    rbx, rbx
0x18005a41e  jz      short loc_18005A434
0x18005a420  mov     rax, [rbx]
0x18005a423  mov     edx, 1
0x18005a428  mov     rcx, rbx
0x18005a42b  mov     rax, [rax]
0x18005a42e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a433  nop
0x18005a434  lea     rcx, [rsp+78h+arg_18]
0x18005a43c  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18005a441  nop
0x18005a442  lea     rcx, [rsp+78h+arg_0]; this
0x18005a44a  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x18005a44f  mov     eax, esi
0x18005a451  jmp     loc_18005A55A
0x18005a456  mov     al, 1
0x18005a458  add     r14, 8
0x18005a45c  jmp     loc_18005A36F
0x18005a461  test    al, al
0x18005a463  jnz     short loc_18005A4E4
0x18005a465  mov     rsi, [rbx+8]
0x18005a469  mov     r13, [rbx+10h]
0x18005a46d  cmp     rsi, r13
0x18005a470  jz      short loc_18005A4E4
0x18005a472  mov     r14, [rsi]
0x18005a475  cmp     dword ptr [r14], 1
0x18005a479  jz      short loc_18005A4DE
0x18005a47b  mov     rdx, r14; struct WindowsPerformanceRecorder::CETWProperties::CEventSession *
0x18005a47e  mov     rcx, r12; this
0x18005a481  call    ?SetRunningEventTraceProperties@CControlManager@WindowsPerformanceRecorder@@AEAAJAEBUCEventSession@CETWProperties@2@@Z; WindowsPerformanceRecorder::CControlManager::SetRunningEventTraceProperties(WindowsPerformanceRecorder::CETWProperties::CEventSession const &)
0x18005a486  mov     r15d, eax
0x18005a489  test    eax, eax
0x18005a48b  jns     short loc_18005A4C9
0x18005a48d  test    rbx, rbx
0x18005a490  jz      short loc_18005A4A6
0x18005a492  mov     rcx, [rbx]
0x18005a495  mov     rax, [rcx]
0x18005a498  mov     edx, 1
0x18005a49d  mov     rcx, rbx
0x18005a4a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a4a5  nop
0x18005a4a6  lea     rcx, [rsp+78h+arg_18]
0x18005a4ae  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18005a4b3  nop
0x18005a4b4  lea     rcx, [rsp+78h+arg_0]; this
0x18005a4bc  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x18005a4c1  mov     eax, r15d
0x18005a4c4  jmp     loc_18005A55A
0x18005a4c9  mov     r8, [rsp+78h+arg_0]; unsigned __int16 *
0x18005a4d1  mov     rdx, [r14+70h]; unsigned __int64
0x18005a4d5  call    ?LogMark@CControlManager@WindowsPerformanceRecorder@@AEAAJ_KPEBG@Z; WindowsPerformanceRecorder::CControlManager::LogMark(unsigned __int64,ushort const *)
0x18005a4da  test    eax, eax
0x18005a4dc  jns     short loc_18005A4E4
0x18005a4de  add     rsi, 8
0x18005a4e2  jmp     short loc_18005A46D
0x18005a4e4  test    cs:Microsoft_Windows_Performance_Recorder_ContextEnableBits, 1
0x18005a4eb  jz      short loc_18005A510
0x18005a4ed  lea     r9, aTraceMarker; "Trace Marker"
0x18005a4f4  mov     r8, [rsp+78h+arg_0]
0x18005a4fc  lea     rdx, InformationCapture_FireEvent
0x18005a503  lea     rcx, WindowsPerformanceRecorderContextProvider_Context
0x18005a50a  call    McTemplateU0zz_EventWriteTransfer
0x18005a50f  nop
0x18005a510  test    rbx, rbx
0x18005a513  jz      short loc_18005A529
0x18005a515  mov     rax, [rbx]
0x18005a518  mov     edx, 1
0x18005a51d  mov     rcx, rbx
0x18005a520  mov     rax, [rax]
0x18005a523  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a528  nop
0x18005a529  lea     rcx, [rsp+78h+arg_18]
0x18005a531  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18005a536  nop
0x18005a537  lea     rcx, [rsp+78h+arg_0]; this
0x18005a53f  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x18005a544  xor     eax, eax
0x18005a546  jmp     short loc_18005A55A
0x18005a548  lea     rcx, [rsp+78h+arg_0]; this
0x18005a550  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x18005a555  mov     eax, 80004005h
0x18005a55a  mov     rbx, [rsp+78h+arg_8]
0x18005a562  add     rsp, 50h
0x18005a566  pop     r15
0x18005a568  pop     r14
0x18005a56a  pop     r13
0x18005a56c  pop     r12
0x18005a56e  pop     rsi
0x18005a56f  retn
```
