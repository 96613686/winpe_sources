# WindowsPerformanceRecorder::CControlManager::Cancel(IProfileCollection *)

- ea: `0x180058800`
- end: `0x180058e4d`
- name: `?Cancel@CControlManager@WindowsPerformanceRecorder@@UEAAJPEAUIProfileCollection@@@Z`
- size: `1613`
- prototype: `int(WindowsPerformanceRecorder::CControlManager *__hidden this, struct IProfileCollection *)`
- caller_count: `0`
- callee_count: `40`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180008330`
- `0x18000aa10`
- `0x180015e2c`
- `0x18001a92c`
- `0x18001bf98`
- `0x18001d190`
- `0x18001e6e0`
- `0x18001ea58`
- `0x180021068`
- `0x180021810`
- `0x1800234f0`
- `0x180024270`
- `0x1800248d8`
- `0x180031374`
- `0x1800328a8`
- `0x1800328f8`
- `0x1800329bc`
- `0x18003567c`
- `0x180036d94`
- `0x1800385d4`
- `0x180039084`
- `0x18003af80`
- `0x180043514`
- `0x18004865c`
- `0x1800490f8`
- `0x18004a758`
- `0x18004b024`
- `0x18004b128`
- `0x18004ece0`
- `0x18004ed10`
- `0x18004f1d0`
- `0x180057734`
- `0x180057b20`
- `0x180058800`
- `0x180058e54`
- `0x18005abe4`
- `0x18005d068`
- `0x1800602d0`
- `0x180071b28`
- `0x18008c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180058bd2`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180058bd2`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180058ccf`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180058ccf`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall WindowsPerformanceRecorder::CControlManager::Cancel(
        WindowsPerformanceRecorder::CControlManager *this,
        struct IProfileCollection *a2)
{
  WindowsPerformanceRecorder::CControlManager *v4; // r15
  int v5; // r14d
  int IsOtherObjectInstanceNameCompatible; // eax
  signed int RunningProfileTraceType; // eax
  __int64 v8; // rbx
  char *v9; // r13
  const unsigned __int16 *v10; // r9
  bool v11; // r8
  char v12; // al
  _QWORD *v13; // rdi
  _QWORD *v14; // r12
  int v15; // eax
  int v16; // eax
  _QWORD *v17; // rdi
  __int64 j; // rax
  bool v19; // si
  WindowsPerformanceRecorder::Status::CSessionInfo *v20; // rax
  __int64 v21; // r12
  WindowsPerformanceRecorder::CControlManager *v22; // rcx
  int v23; // esi
  const unsigned __int16 *v24; // r9
  int v25; // eax
  WindowsPerformanceRecorder::CETWProperties::CEventSession **v26; // rsi
  WindowsPerformanceRecorder::CETWProperties::CEventSession **i; // rdi
  const WCHAR *FileName; // rax
  int Format; // [rsp+20h] [rbp-368h]
  int Formata; // [rsp+20h] [rbp-368h]
  char *v32; // [rsp+28h] [rbp-360h]
  char v33; // [rsp+30h] [rbp-358h]
  char v34; // [rsp+30h] [rbp-358h]
  int v35; // [rsp+34h] [rbp-354h]
  unsigned int v36; // [rsp+38h] [rbp-350h] BYREF
  int v37; // [rsp+3Ch] [rbp-34Ch]
  unsigned __int16 *v38; // [rsp+40h] [rbp-348h] BYREF
  char *v39; // [rsp+48h] [rbp-340h]
  __int64 v40; // [rsp+50h] [rbp-338h]
  WindowsPerformanceRecorder::CControlManager *v41; // [rsp+58h] [rbp-330h]
  void *v42; // [rsp+60h] [rbp-328h] BYREF
  char v43[8]; // [rsp+68h] [rbp-320h] BYREF
  void *v44; // [rsp+70h] [rbp-318h] BYREF
  _DWORD *v45; // [rsp+78h] [rbp-310h]
  __int64 v46; // [rsp+80h] [rbp-308h] BYREF
  char *v47; // [rsp+88h] [rbp-300h]
  WindowsPerformanceRecorder::CControlManager *v48; // [rsp+90h] [rbp-2F8h]
  __int64 v49; // [rsp+98h] [rbp-2F0h] BYREF
  __int64 v50; // [rsp+A0h] [rbp-2E8h]
  __int64 v51; // [rsp+A8h] [rbp-2E0h]
  ATL::CAtlException *v52; // [rsp+B8h] [rbp-2D0h] BYREF
  char v53[8]; // [rsp+C0h] [rbp-2C8h] BYREF
  WindowsPerformanceRecorder::CETWProperties::CEventSession **v54; // [rsp+C8h] [rbp-2C0h]
  WindowsPerformanceRecorder::CETWProperties::CEventSession **v55; // [rsp+D0h] [rbp-2B8h]
  int v56; // [rsp+1C0h] [rbp-1C8h]
  char v57[8]; // [rsp+270h] [rbp-118h] BYREF
  void *Block; // [rsp+278h] [rbp-110h]
  unsigned __int64 v59; // [rsp+2E0h] [rbp-A8h]
  char v60[28]; // [rsp+2E8h] [rbp-A0h] BYREF
  int v61; // [rsp+304h] [rbp-84h]

  v51 = -2;
  v48 = this;
  v46 = 0;
  v4 = (WindowsPerformanceRecorder::CControlManager *)((char *)this - 184);
  v5 = WindowsPerformanceRecorder::CAPIAutoLock::Acquire<WindowsPerformanceRecorder::CControlManager>(
         &v46,
         (char *)this - 184);
  if ( v5 >= 0 )
  {
    (*(void (__fastcall **)(char *))(*((_QWORD *)this - 22) + 24LL))((char *)this - 176);
    WindowsPerformanceRecorder::CEnumControlWarningInfoImpl<WindowsPerformanceRecorder::CControlManager>::ClearControlWarningInfo((char *)this - 80);
    if ( a2 )
    {
      IsOtherObjectInstanceNameCompatible = WindowsPerformanceRecorder::CInstanceNameScopedObjectImpl<WindowsPerformanceRecorder::CProfile>::IsOtherObjectInstanceNameCompatible(
                                              (char *)this + 32,
                                              a2);
      if ( IsOtherObjectInstanceNameCompatible < 0 )
      {
        v5 = IsOtherObjectInstanceNameCompatible;
        goto LABEL_71;
      }
    }
    v41 = v4;
    WindowsPerformanceRecorder::CControlManager::Cancel_::_2_::CPerfEventMacro::CPerfEventMacro(v43);
    RunningProfileTraceType = WindowsPerformanceRecorder::CControlManager::GetRunningProfileTraceType(v4);
    v5 = RunningProfileTraceType;
    v35 = RunningProfileTraceType;
    if ( RunningProfileTraceType < 0 && RunningProfileTraceType != -984076288 )
    {
      WindowsPerformanceRecorder::TraceHR(
        (WindowsPerformanceRecorder *)2,
        (unsigned __int8)"Cancel",
        (const char *)0x3C3,
        RunningProfileTraceType,
        "Failed Cancel",
        v32);
LABEL_70:
      WindowsPerformanceRecorder::CControlManager::Cancel_::_2_::CPerfEventMacro::_CPerfEventMacro(v43);
      goto LABEL_71;
    }
    v45 = (_DWORD *)((char *)this + 384);
    if ( (*((_BYTE *)this + 384) & 8) == 0 && (*((_BYTE *)this + 384) & 2) != 0 )
    {
      WindowsPerformanceRecorder::TraceHR(
        (WindowsPerformanceRecorder *)2,
        (unsigned __int8)"Cancel",
        (const char *)0x3CA,
        0xC5583000,
        "Not allowed to cancel LastShutdown",
        v32);
      WindowsPerformanceRecorder::CControlManager::Cancel_::_2_::CPerfEventMacro::_CPerfEventMacro(v43);
      v5 = -984076288;
      goto LABEL_71;
    }
    WindowsPerformanceRecorder::CControlManager::ControlProgressHandler_Begin(v4);
    try
    {
      v8 = 0;
      v40 = 0;
      v9 = 0;
      v39 = 0;
      if ( v5 >= 0 )
      {
        if ( a2 )
        {
          v47 = (char *)operator new(0x1A8u);
          v8 = WindowsPerformanceRecorder::CETWProperties::CETWProperties((WindowsPerformanceRecorder::CETWProperties *)v47);
          v40 = v8;
          v5 = WindowsPerformanceRecorder::CETWProperties::Initialize(
                 (WindowsPerformanceRecorder::CETWProperties *)v8,
                 a2,
                 v4,
                 (*v45 & 0x10) != 0);
          if ( v5 < 0 )
            goto LABEL_27;
          v9 = *(char **)(v8 + 320);
          v39 = v9;
          WindowsPerformanceRecorder::TelemetryUsage(
            (WindowsPerformanceRecorder *)0x2000,
            (unsigned __int64)"Cancel",
            v9,
            v10);
          WindowsPerformanceRecorder::CControlManager::SetProgressHandlerRuntimeState(
            v4,
            (struct WindowsPerformanceRecorder::CETWProperties *)v8,
            v11,
            1);
          WindowsPerformanceRecorder::CControlManager::SetEventSessionsProviderInfos(v4);
          v12 = 1;
          v33 = 1;
          v13 = *(_QWORD **)(v8 + 8);
          v14 = *(_QWORD **)(v8 + 16);
          while ( v13 != v14 )
          {
            LOBYTE(Format) = v12;
            v15 = WindowsPerformanceRecorder::CControlManager::CancelEventSession(
                    v4,
                    v9,
                    *v13,
                    *(unsigned int *)(v8 + 256),
                    Format);
            if ( v15 < 0 )
            {
              if ( v5 >= 0 )
                v5 = v15;
              v33 = 0;
            }
            WindowsPerformanceRecorder::CControlManager::ControlProgressHandler_Update(v4, 1);
            ++v13;
            v12 = v33;
          }
          v16 = WindowsPerformanceRecorder::CControlManager::RestoreHardwareCounter(
                  v4,
                  (struct WindowsPerformanceRecorder::CETWProperties *)v8);
          if ( v5 < 0 )
            goto LABEL_27;
          v5 = v16;
          v35 = v16;
        }
        if ( v5 >= 0 )
        {
          if ( a2 )
          {
LABEL_52:
            WindowsPerformanceRecorder::CETWProperties::CETWProperties((WindowsPerformanceRecorder::CETWProperties *)v53);
            if ( (int)WindowsPerformanceRecorder::CControlManager::GetRegistryETWProperties(
                        v4,
                        (struct WindowsPerformanceRecorder::CETWProperties *)v53,
                        0) >= 0
              && v56 == 2 )
            {
              v26 = v55;
              for ( i = v54; i != v26; ++i )
              {
                FileName = WindowsPerformanceRecorder::CETWProperties::CEventSession::get_FileName(*i);
                DeleteFileW(FileName);
              }
            }
            WindowsPerformanceRecorder::CETWProperties::~CETWProperties((WindowsPerformanceRecorder::CETWProperties *)v53);
            goto LABEL_74;
          }
LABEL_28:
          v36 = 0;
          v42 = 0;
          v44 = 0;
          v5 = WindowsPerformanceRecorder::QueryAllSessions(&v42, &v44, &v36);
          v35 = v5;
          v17 = v42;
          if ( v5 >= 0 )
          {
            v34 = 0;
            for ( j = 0; ; j = (unsigned int)(v37 + 1) )
            {
              v37 = j;
              if ( (unsigned int)j >= v36 )
                break;
              v50 = j;
              v47 = (char *)(v17[j] + 2 * ((unsigned __int64)*(unsigned int *)(v17[j] + 116LL) >> 1));
              ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                (__int64 *)&v38,
                v47);
              v19 = !Performance::COSVersionInfo::IsWin8AndUp()
                 && WindowsPerformanceRecorder::CSystemCollectorElement::IsLegacySystemCollectorName(v38);
              ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
                &v49,
                (const void **)&v38);
              if ( (unsigned __int8)WindowsPerformanceRecorder::HasWPRInternalInstancePrefix(v20) || v19 )
              {
                v21 = v17[v50];
                WindowsPerformanceRecorder::CETWProperties::CEventSession::CEventSession((WindowsPerformanceRecorder::CETWProperties::CEventSession *)v57);
                if ( !v19
                  || (v59 = *(_QWORD *)(v21 + 8),
                      (int)WindowsPerformanceRecorder::CControlManager::GetRunningSystemGroupMask(
                             v22,
                             v59,
                             (struct _PERFINFO_GROUPMASK *)v60) >= 0)
                  && (v61 & 0x10000000) != 0 )
                {
                  v23 = *(_DWORD *)(v21 + 64) & 1;
                  free(Block);
                  Block = (void *)v21;
                  WindowsPerformanceRecorder::TelemetryUsage(
                    (WindowsPerformanceRecorder *)0x2000,
                    (unsigned __int64)"Cancel",
                    v47,
                    v24);
                  LOBYTE(Format) = 0;
                  v25 = WindowsPerformanceRecorder::CControlManager::CancelEventSession(
                          v4,
                          0,
                          v57,
                          (unsigned int)(v23 + 1),
                          Format);
                  if ( v25 < 0 )
                  {
                    if ( v5 >= 0 )
                      v5 = v25;
                    v35 = v5;
                  }
                  v34 = 1;
                  Block = 0;
                }
                WindowsPerformanceRecorder::CETWProperties::CEventSession::~CEventSession((WindowsPerformanceRecorder::CETWProperties::CEventSession *)v57);
              }
              WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&v38);
            }
            if ( !v34 )
            {
              if ( v5 >= 0 )
                v5 = -984076288;
              v35 = v5;
            }
          }
          operator delete(v44);
          operator delete(v17);
          goto LABEL_52;
        }
      }
LABEL_27:
      WindowsPerformanceRecorder::TraceHR(
        (WindowsPerformanceRecorder *)3,
        (unsigned __int8)"Cancel",
        (const char *)0x407,
        v5,
        "Fall back cancel",
        v32);
      goto LABEL_28;
    }
    catch ( std::bad_alloc )
    {
      v35 = -2147024882;
      v5 = -2147024882;
      v8 = v40;
      v9 = v39;
      v4 = v41;
    }
    catch ( std::length_error )
    {
      v35 = -2147024882;
      v5 = -2147024882;
      v8 = v40;
      v9 = v39;
      v4 = v41;
    }
    catch ( ATL::CAtlException *v52 )
    {
      v35 = *(_DWORD *)v52;
      v5 = *(_DWORD *)v52;
      v8 = v40;
      v9 = v39;
      v4 = v41;
    }
LABEL_74:
    try
    {
      if ( (*v45 & 1) != 0 )
      {
        WindowsPerformanceRecorder::CControlManager::ClearStateInRegistry(v4, L"Normal");
      }
      else if ( (*v45 & 8) != 0 )
      {
        WindowsPerformanceRecorder::CControlManager::ClearStateInRegistry(v4, L"Boot");
      }
    }
    catch ( ... )
    {
      v9 = v39;
      v4 = v41;
      WindowsPerformanceRecorder::CControlManager::AddProfileControlWarningInfo(
        v41,
        -2147024882,
        &IID_IControlManager,
        (const unsigned __int16 *)v39,
        0);
      WindowsPerformanceRecorder::TraceHR(
        (WindowsPerformanceRecorder *)3,
        (unsigned __int8)"Cancel",
        (const char *)0x489,
        0x8007000E,
        "%ws",
        v9);
      v5 = v35;
      if ( v35 >= 0 )
        v5 = -2147024882;
      v8 = v40;
LABEL_67:
      WindowsPerformanceRecorder::CControlManager::SetControlErrorInfo(
        v4,
        (unsigned int)v5,
        1,
        &IID_IControlManager,
        v9);
      WindowsPerformanceRecorder::TelemetryError(
        (WindowsPerformanceRecorder *)0x2000,
        (unsigned __int64)"Cancel",
        v9,
        (const unsigned __int16 *)(unsigned int)v5,
        Formata);
LABEL_68:
      WindowsPerformanceRecorder::CControlManager::ControlProgressHandler_End(v4, v5, 0);
      if ( v8 )
        (**(void (__fastcall ***)(__int64, __int64))v8)(v8, 1);
      goto LABEL_70;
    }
    if ( v5 >= 0 )
      goto LABEL_68;
    goto LABEL_67;
  }
LABEL_71:
  WindowsPerformanceRecorder::CAPIAutoLock::~CAPIAutoLock((WindowsPerformanceRecorder::CAPIAutoLock *)&v46);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180058800  mov     r11, rsp
0x180058803  push    rdi
0x180058804  push    r12
0x180058806  push    r13
0x180058808  push    r14
0x18005880a  push    r15
0x18005880c  sub     rsp, 360h
0x180058813  mov     qword ptr [r11-2E0h], 0FFFFFFFFFFFFFFFEh
0x18005881e  mov     [r11+18h], rbx
0x180058822  mov     [r11+20h], rsi
0x180058826  mov     rax, cs:__security_cookie
0x18005882d  xor     rax, rsp
0x180058830  mov     [rsp+388h+var_38], rax
0x180058838  mov     rsi, rdx
0x18005883b  mov     rbx, rcx
0x18005883e  mov     [rsp+388h+var_2F8], rcx
0x180058846  mov     qword ptr [r11-308h], 0
0x180058851  lea     r15, [rcx-0B8h]
0x180058858  mov     rdx, r15
0x18005885b  lea     rcx, [r11-308h]
0x180058862  call    ??$Acquire@VCControlManager@WindowsPerformanceRecorder@@@CAPIAutoLock@WindowsPerformanceRecorder@@QEAAJPEAVCControlManager@1@@Z; WindowsPerformanceRecorder::CAPIAutoLock::Acquire<WindowsPerformanceRecorder::CControlManager>(WindowsPerformanceRecorder::CControlManager *)
0x180058867  mov     r14d, eax
0x18005886a  test    eax, eax
0x18005886c  js      loc_180058E10
0x180058872  lea     rcx, [rbx-0B0h]
0x180058879  mov     rax, [rcx]
0x18005887c  mov     rax, [rax+18h]
0x180058880  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058885  lea     rcx, [rbx-50h]
0x180058889  call    ?ClearControlWarningInfo@?$CEnumControlWarningInfoImpl@VCControlManager@WindowsPerformanceRecorder@@@WindowsPerformanceRecorder@@IEAAXXZ; WindowsPerformanceRecorder::CEnumControlWarningInfoImpl<WindowsPerformanceRecorder::CControlManager>::ClearControlWarningInfo(void)
0x18005888e  test    rsi, rsi
0x180058891  jz      short loc_1800588AB
0x180058893  lea     rcx, [rbx+20h]
0x180058897  mov     rdx, rsi
0x18005889a  call    ?IsOtherObjectInstanceNameCompatible@?$CInstanceNameScopedObjectImpl@VCProfile@WindowsPerformanceRecorder@@@WindowsPerformanceRecorder@@IEAAJPEAUIUnknown@@@Z; WindowsPerformanceRecorder::CInstanceNameScopedObjectImpl<WindowsPerformanceRecorder::CProfile>::IsOtherObjectInstanceNameCompatible(IUnknown *)
0x18005889f  test    eax, eax
0x1800588a1  jns     short loc_1800588AB
0x1800588a3  mov     r14d, eax
0x1800588a6  jmp     loc_180058E10
0x1800588ab  mov     [rsp+388h+var_330], r15
0x1800588b0  lea     rcx, [rsp+388h+var_320]
0x1800588b5  call    _WindowsPerformanceRecorder__CControlManager__Cancel____2___CPerfEventMacro__CPerfEventMacro
0x1800588ba  nop
0x1800588bb  mov     rcx, r15; this
0x1800588be  call    ?GetRunningProfileTraceType@CControlManager@WindowsPerformanceRecorder@@AEAAJXZ; WindowsPerformanceRecorder::CControlManager::GetRunningProfileTraceType(void)
0x1800588c3  mov     r14d, eax
0x1800588c6  mov     [rsp+388h+var_354], eax
0x1800588ca  test    eax, eax
0x1800588cc  jns     short loc_180058900
0x1800588ce  cmp     eax, 0C5583000h
0x1800588d3  jz      short loc_180058900
0x1800588d5  lea     rax, aFailedCancel; "Failed Cancel"
0x1800588dc  mov     [rsp+388h+Format], rax; Format
0x1800588e1  mov     r9d, r14d; unsigned int
0x1800588e4  mov     r8d, 3C3h; char *
0x1800588ea  lea     rdx, aCancel; "Cancel"
0x1800588f1  mov     ecx, 2; this
0x1800588f6  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x1800588fb  jmp     loc_180058E05
0x180058900  lea     rax, [rbx+180h]
0x180058907  mov     [rsp+388h+var_310], rax
0x18005890c  test    byte ptr [rax], 8
0x18005890f  jnz     short loc_180058954
0x180058911  test    byte ptr [rax], 2
0x180058914  jz      short loc_180058954
0x180058916  lea     rax, aNotAllowedToCa; "Not allowed to cancel LastShutdown"
0x18005891d  mov     [rsp+388h+Format], rax; Format
0x180058922  mov     esi, 0C5583000h
0x180058927  mov     r9d, esi; unsigned int
0x18005892a  mov     r8d, 3CAh; char *
0x180058930  lea     rdx, aCancel; "Cancel"
0x180058937  mov     ecx, 2; this
0x18005893c  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x180058941  nop
0x180058942  lea     rcx, [rsp+388h+var_320]
0x180058947  call    _WindowsPerformanceRecorder__CControlManager__Cancel____2___CPerfEventMacro___CPerfEventMacro
0x18005894c  mov     r14d, esi
0x18005894f  jmp     loc_180058E10
0x180058954  mov     rcx, r15; this
0x180058957  call    ?ControlProgressHandler_Begin@CControlManager@WindowsPerformanceRecorder@@AEAAJXZ; WindowsPerformanceRecorder::CControlManager::ControlProgressHandler_Begin(void)
0x18005895c  xor     ebx, ebx
0x18005895e  mov     [rsp+388h+var_338], rbx
0x180058963  xor     r13d, r13d
0x180058966  mov     [rsp+388h+var_340], r13
0x18005896b  test    r14d, r14d
0x18005896e  js      loc_180058A76
0x180058974  test    rsi, rsi
0x180058977  jz      loc_180058A66
0x18005897d  mov     ecx, 1A8h; Size
0x180058982  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180058987  mov     [rsp+388h+var_300], rax
0x18005898f  mov     rcx, rax; this
0x180058992  call    ??0CETWProperties@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::CETWProperties::CETWProperties(void)
0x180058997  mov     rbx, rax
0x18005899a  mov     [rsp+388h+var_338], rax
0x18005899f  mov     rax, [rsp+388h+var_310]
0x1800589a4  mov     r9d, [rax]
0x1800589a7  shr     r9d, 4
0x1800589ab  and     r9b, 1; bool
0x1800589af  mov     r8, r15; struct WindowsPerformanceRecorder::CControlManager *
0x1800589b2  mov     rdx, rsi; struct IProfileCollection *
0x1800589b5  mov     rcx, rbx; this
0x1800589b8  call    ?Initialize@CETWProperties@WindowsPerformanceRecorder@@QEAAJPEAUIProfileCollection@@PEAVCControlManager@2@_N@Z; WindowsPerformanceRecorder::CETWProperties::Initialize(IProfileCollection *,WindowsPerformanceRecorder::CControlManager *,bool)
0x1800589bd  mov     r14d, eax
0x1800589c0  test    eax, eax
0x1800589c2  js      loc_180058A76
0x1800589c8  mov     r13, [rbx+140h]
0x1800589cf  mov     [rsp+388h+var_340], r13
0x1800589d4  mov     r8, r13; char *
0x1800589d7  lea     rdx, aCancel; "Cancel"
0x1800589de  mov     ecx, 2000h; this
0x1800589e3  call    ?TelemetryUsage@WindowsPerformanceRecorder@@YAX_KPEBDPEBG@Z; WindowsPerformanceRecorder::TelemetryUsage(unsigned __int64,char const *,ushort const *)
0x1800589e8  mov     r9b, 1; bool
0x1800589eb  mov     rdx, rbx; struct WindowsPerformanceRecorder::CETWProperties *
0x1800589ee  mov     rcx, r15; this
0x1800589f1  call    ?SetProgressHandlerRuntimeState@CControlManager@WindowsPerformanceRecorder@@AEAAJAEAVCETWProperties@2@_N1@Z; WindowsPerformanceRecorder::CControlManager::SetProgressHandlerRuntimeState(WindowsPerformanceRecorder::CETWProperties &,bool,bool)
0x1800589f6  lea     rdx, [rbx+8]
0x1800589fa  mov     rcx, r15; this
0x1800589fd  call    ?SetEventSessionsProviderInfos@CControlManager@WindowsPerformanceRecorder@@AEAAJAEAV?$vector@PEAUCEventSession@CETWProperties@WindowsPerformanceRecorder@@V?$allocator@PEAUCEventSession@CETWProperties@WindowsPerformanceRecorder@@@std@@@std@@@Z; WindowsPerformanceRecorder::CControlManager::SetEventSessionsProviderInfos(std::vector<WindowsPerformanceRecorder::CETWProperties::CEventSession *> &)
0x180058a02  mov     al, 1
0x180058a04  mov     [rsp+388h+var_358], al
0x180058a08  mov     rdi, [rbx+8]
0x180058a0c  mov     r12, [rbx+10h]
0x180058a10  mov     rcx, r15; this
0x180058a13  cmp     rdi, r12
0x180058a16  jz      short loc_180058A52
0x180058a18  mov     byte ptr [rsp+388h+Format], al
0x180058a1c  mov     r9d, [rbx+100h]
0x180058a23  mov     r8, [rdi]
0x180058a26  mov     rdx, r13
0x180058a29  call    ?CancelEventSession@CControlManager@WindowsPerformanceRecorder@@AEAAJPEBGAEAUCEventSession@CETWProperties@2@W4__MIDL_IProfile_0001@@_N@Z; WindowsPerformanceRecorder::CControlManager::CancelEventSession(ushort const *,WindowsPerformanceRecorder::CETWProperties::CEventSession &,__MIDL_IProfile_0001,bool)
0x180058a2e  test    eax, eax
0x180058a30  jns     short loc_180058A3E
0x180058a32  test    r14d, r14d
0x180058a35  cmovns  r14d, eax
0x180058a39  mov     [rsp+388h+var_358], 0
0x180058a3e  mov     dl, 1; bool
0x180058a40  mov     rcx, r15; this
0x180058a43  call    ?ControlProgressHandler_Update@CControlManager@WindowsPerformanceRecorder@@QEAAJ_N@Z; WindowsPerformanceRecorder::CControlManager::ControlProgressHandler_Update(bool)
0x180058a48  add     rdi, 8
0x180058a4c  mov     al, [rsp+388h+var_358]
0x180058a50  jmp     short loc_180058A10
0x180058a52  mov     rdx, rbx; struct WindowsPerformanceRecorder::CETWProperties *
0x180058a55  call    ?RestoreHardwareCounter@CControlManager@WindowsPerformanceRecorder@@AEAAJAEAVCETWProperties@2@@Z; WindowsPerformanceRecorder::CControlManager::RestoreHardwareCounter(WindowsPerformanceRecorder::CETWProperties &)
0x180058a5a  test    r14d, r14d
0x180058a5d  js      short loc_180058A76
0x180058a5f  mov     r14d, eax
0x180058a62  mov     [rsp+388h+var_354], eax
0x180058a66  test    r14d, r14d
0x180058a69  js      short loc_180058A76
0x180058a6b  test    rsi, rsi
0x180058a6e  jnz     loc_180058C83
0x180058a74  jmp     short loc_180058A9C
0x180058a76  lea     rax, aFallBackCancel; "Fall back cancel"
0x180058a7d  mov     [rsp+388h+Format], rax; Format
0x180058a82  mov     r9d, r14d; unsigned int
0x180058a85  mov     r8d, 407h; char *
0x180058a8b  lea     rdx, aCancel; "Cancel"
0x180058a92  mov     ecx, 3; this
0x180058a97  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x180058a9c  mov     [rsp+388h+var_350], 0
0x180058aa4  mov     [rsp+388h+var_328], 0
0x180058aad  mov     [rsp+388h+var_318], 0
0x180058ab6  lea     r8, [rsp+388h+var_350]
0x180058abb  lea     rdx, [rsp+388h+var_318]
0x180058ac0  lea     rcx, [rsp+388h+var_328]
0x180058ac5  call    ?QueryAllSessions@WindowsPerformanceRecorder@@YAJAEAV?$CAutoVectorPtr@PEAU_EVENT_TRACE_PROPERTIES@@@ATL@@AEAV?$CAutoVectorPtr@E@3@AEAK@Z; WindowsPerformanceRecorder::QueryAllSessions(ATL::CAutoVectorPtr<_EVENT_TRACE_PROPERTIES *> &,ATL::CAutoVectorPtr<uchar> &,ulong &)
0x180058aca  mov     r14d, eax
0x180058acd  mov     [rsp+388h+var_354], eax
0x180058ad1  mov     rdi, [rsp+388h+var_328]
0x180058ad6  test    eax, eax
0x180058ad8  js      loc_180058C70
0x180058ade  mov     [rsp+388h+var_358], 0
0x180058ae3  xor     eax, eax
0x180058ae5  mov     [rsp+388h+var_34C], eax
0x180058ae9  cmp     eax, [rsp+388h+var_350]
0x180058aed  jnb     loc_180058C58
0x180058af3  mov     [rsp+388h+var_2E8], rax
0x180058afb  mov     rcx, [rdi+rax*8]
0x180058aff  mov     eax, [rcx+74h]
0x180058b02  shr     rax, 1
0x180058b05  lea     rax, [rcx+rax*2]
0x180058b09  mov     [rsp+388h+var_300], rax
0x180058b11  mov     rdx, rax
0x180058b14  lea     rcx, [rsp+388h+var_348]
0x180058b19  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180058b1e  nop
0x180058b1f  call    ?IsWin8AndUp@COSVersionInfo@Performance@@SA_NXZ; Performance::COSVersionInfo::IsWin8AndUp(void)
0x180058b24  test    al, al
0x180058b26  jnz     short loc_180058B3B
0x180058b28  mov     rcx, [rsp+388h+var_348]; unsigned __int16 *
0x180058b2d  call    ?IsLegacySystemCollectorName@CSystemCollectorElement@WindowsPerformanceRecorder@@SA_NPEBG@Z; WindowsPerformanceRecorder::CSystemCollectorElement::IsLegacySystemCollectorName(ushort const *)
0x180058b32  test    al, al
0x180058b34  jz      short loc_180058B3B
0x180058b36  mov     sil, 1
0x180058b39  jmp     short loc_180058B3E
0x180058b3b  xor     sil, sil
0x180058b3e  mov     rax, [rsp+388h+var_2F8]
0x180058b46  mov     r12, [rax+28h]
0x180058b4a  lea     rdx, [rsp+388h+var_348]; void *
0x180058b4f  lea     rcx, [rsp+388h+var_2F0]; void *
0x180058b57  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180058b5c  mov     rdx, r12
0x180058b5f  mov     rcx, rax; this
0x180058b62  call    ?HasWPRInternalInstancePrefix@WindowsPerformanceRecorder@@YA_NV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBG@Z; WindowsPerformanceRecorder::HasWPRInternalInstancePrefix(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ushort const *)
0x180058b67  test    al, al
0x180058b69  jnz     short loc_180058B74
0x180058b6b  test    sil, sil
0x180058b6e  jz      loc_180058C43
0x180058b74  mov     r12, [rsp+388h+var_2E8]
0x180058b7c  mov     r12, [rdi+r12*8]
0x180058b80  lea     rcx, [rsp+388h+var_118]; this
0x180058b88  call    ??0CEventSession@CETWProperties@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::CETWProperties::CEventSession::CEventSession(void)
0x180058b8d  nop
0x180058b8e  test    sil, sil
0x180058b91  jz      short loc_180058BC2
0x180058b93  mov     rdx, [r12+8]; unsigned __int64
0x180058b98  mov     [rsp+388h+var_A8], rdx
0x180058ba0  lea     r8, [rsp+388h+var_A0]; struct _PERFINFO_GROUPMASK *
0x180058ba8  call    ?GetRunningSystemGroupMask@CControlManager@WindowsPerformanceRecorder@@AEAAJ_KAEAU_PERFINFO_GROUPMASK@@@Z; WindowsPerformanceRecorder::CControlManager::GetRunningSystemGroupMask(unsigned __int64,_PERFINFO_GROUPMASK &)
0x180058bad  test    eax, eax
0x180058baf  js      loc_180058C35
0x180058bb5  test    [rsp+388h+var_84], 10000000h
0x180058bc0  jz      short loc_180058C35
0x180058bc2  mov     esi, [r12+40h]
0x180058bc7  and     esi, 1
0x180058bca  mov     rcx, [rsp+388h+Block]; Block
0x180058bd2  call    cs:__imp_free
0x180058bd8  mov     [rsp+388h+Block], r12
0x180058be0  mov     r8, [rsp+388h+var_300]; char *
0x180058be8  lea     rdx, aCancel; "Cancel"
0x180058bef  mov     ecx, 2000h; this
0x180058bf4  call    ?TelemetryUsage@WindowsPerformanceRecorder@@YAX_KPEBDPEBG@Z; WindowsPerformanceRecorder::TelemetryUsage(unsigned __int64,char const *,ushort const *)
0x180058bf9  mov     byte ptr [rsp+388h+Format], 0
0x180058bfe  lea     r9d, [rsi+1]
0x180058c02  lea     r8, [rsp+388h+var_118]
0x180058c0a  xor     edx, edx
0x180058c0c  mov     rcx, r15
0x180058c0f  call    ?CancelEventSession@CControlManager@WindowsPerformanceRecorder@@AEAAJPEBGAEAUCEventSession@CETWProperties@2@W4__MIDL_IProfile_0001@@_N@Z; WindowsPerformanceRecorder::CControlManager::CancelEventSession(ushort const *,WindowsPerformanceRecorder::CETWProperties::CEventSession &,__MIDL_IProfile_0001,bool)
0x180058c14  test    eax, eax
0x180058c16  jns     short loc_180058C24
0x180058c18  test    r14d, r14d
0x180058c1b  cmovns  r14d, eax
0x180058c1f  mov     [rsp+388h+var_354], r14d
0x180058c24  mov     [rsp+388h+var_358], 1
0x180058c29  mov     [rsp+388h+Block], 0
0x180058c35  lea     rcx, [rsp+388h+var_118]; this
0x180058c3d  call    ??1CEventSession@CETWProperties@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::CETWProperties::CEventSession::~CEventSession(void)
0x180058c42  nop
0x180058c43  lea     rcx, [rsp+388h+var_348]; this
0x180058c48  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x180058c4d  mov     eax, [rsp+388h+var_34C]
0x180058c51  inc     eax
0x180058c53  jmp     loc_180058AE5
0x180058c58  cmp     [rsp+388h+var_358], 0
0x180058c5d  jnz     short loc_180058C70
0x180058c5f  mov     esi, 0C5583000h
0x180058c64  test    r14d, r14d
0x180058c67  cmovns  r14d, esi
0x180058c6b  mov     [rsp+388h+var_354], r14d
0x180058c70  mov     rcx, [rsp+388h+var_318]; Block
0x180058c75  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180058c7a  nop
0x180058c7b  mov     rcx, rdi; Block
0x180058c7e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180058c83  lea     rcx, [rsp+388h+var_2C8]; this
0x180058c8b  call    ??0CETWProperties@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::CETWProperties::CETWProperties(void)
0x180058c90  nop
0x180058c91  xor     r8d, r8d; bool
0x180058c94  lea     rdx, [rsp+388h+var_2C8]; struct WindowsPerformanceRecorder::CETWProperties *
0x180058c9c  mov     rcx, r15; this
0x180058c9f  call    ?GetRegistryETWProperties@CControlManager@WindowsPerformanceRecorder@@AEAAJAEAVCETWProperties@2@_N@Z; WindowsPerformanceRecorder::CControlManager::GetRegistryETWProperties(WindowsPerformanceRecorder::CETWProperties &,bool)
0x180058ca4  test    eax, eax
0x180058ca6  js      short loc_180058CDE
0x180058ca8  cmp     [rsp+388h+var_1C8], 2
0x180058cb0  jnz     short loc_180058CDE
0x180058cb2  mov     rsi, [rsp+388h+var_2B8]
0x180058cba  mov     rdi, [rsp+388h+var_2C0]
0x180058cc2  jmp     short loc_180058CD9
0x180058cc4  mov     rcx, [rdi]; this
0x180058cc7  call    ?get_FileName@CEventSession@CETWProperties@WindowsPerformanceRecorder@@QEBAPEBGXZ; WindowsPerformanceRecorder::CETWProperties::CEventSession::get_FileName(void)
0x180058ccc  mov     rcx, rax; lpFileName
0x180058ccf  call    cs:__imp_DeleteFileW
0x180058cd5  add     rdi, 8
0x180058cd9  cmp     rdi, rsi
0x180058cdc  jnz     short loc_180058CC4
0x180058cde  lea     rcx, [rsp+388h+var_2C8]; this
0x180058ce6  call    ??1CETWProperties@WindowsPerformanceRecorder@@UEAA@XZ; WindowsPerformanceRecorder::CETWProperties::~CETWProperties(void)
0x180058ceb  nop
0x180058cec  jmp     short loc_180058D02
0x180058cee  mov     r14d, [rsp+388h+var_354]
0x180058cf3  mov     rbx, [rsp+388h+var_338]
0x180058cf8  mov     r13, [rsp+388h+var_340]
0x180058cfd  mov     r15, [rsp+388h+var_330]
0x180058d02  mov     rax, [rsp+388h+var_310]
0x180058d07  mov     ecx, [rax]
0x180058d09  test    cl, 1
0x180058d0c  jz      short loc_180058D21
0x180058d0e  lea     rdx, ?sc_wchWPRNormalRegistryKey@CControlManager@WindowsPerformanceRecorder@@0QBGB; "Normal"
0x180058d15  mov     rcx, r15; this
  ... truncated ...
```
