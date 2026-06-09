# WindowsPerformanceRecorder::CControlManager::UpdateNormalOrShutdownRecording(IProfileCollection *,bool)

- ea: `0x18005f068`
- end: `0x18005f3f1`
- name: `?UpdateNormalOrShutdownRecording@CControlManager@WindowsPerformanceRecorder@@AEAAJPEAUIProfileCollection@@_N@Z`
- size: `905`
- prototype: `__int64 __fastcall(WindowsPerformanceRecorder::CControlManager *__hidden this, struct IProfileCollection *, bool)`
- caller_count: `2`
- callee_count: `26`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x18005ec50`
- `0x180062090`

## callees

- `0x180007c40`
- `0x180008330`
- `0x1800192e8`
- `0x18001a92c`
- `0x18001bf98`
- `0x18001ea58`
- `0x1800234f0`
- `0x180024270`
- `0x1800248d8`
- `0x18002c430`
- `0x180036d94`
- `0x180039084`
- `0x18003c270`
- `0x18003c6a4`
- `0x180042638`
- `0x1800483c8`
- `0x1800490f8`
- `0x18004a6ec`
- `0x18004b024`
- `0x18004ed10`
- `0x18005d1bc`
- `0x18005ed4c`
- `0x18005f068`
- `0x18005f6f4`
- `0x180071b28`
- `0x18008c010`

## string_xrefs

- `0x18005f165`: `UpdateNormalOrShutdownRecording`
- `0x18005f39e`: `UpdateNormalOrShutdownRecording`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall WindowsPerformanceRecorder::CControlManager::UpdateNormalOrShutdownRecording(
        WindowsPerformanceRecorder::CControlManager *this,
        struct IProfileCollection *a2,
        unsigned __int8 a3)
{
  int v3; // r12d
  WindowsPerformanceRecorder::CControlManager *v5; // rsi
  __int64 result; // rax
  int v7; // eax
  const unsigned __int16 *v8; // rax
  DWORD v9; // r13d
  __int64 v10; // rbx
  char *v11; // r14
  int v12; // eax
  int updated; // edi
  int v14; // eax
  const unsigned __int16 *v15; // r9
  bool v16; // r8
  __int64 *v17; // r15
  __int64 *v18; // r12
  int v19; // eax
  __int64 InstanceNameScopedData; // rax
  unsigned int v21; // r15d
  __int64 v22; // rcx
  int v23; // [rsp+20h] [rbp-98h]
  int v24; // [rsp+30h] [rbp-88h]
  const unsigned __int16 *v25; // [rsp+38h] [rbp-80h]
  __int64 v26; // [rsp+40h] [rbp-78h]
  unsigned __int16 *v27; // [rsp+48h] [rbp-70h]
  ATL::CAtlException *v28; // [rsp+58h] [rbp-60h] BYREF
  unsigned __int16 *v29[11]; // [rsp+60h] [rbp-58h] BYREF
  WindowsPerformanceRecorder::CETWProperties *v31; // [rsp+C8h] [rbp+10h] BYREF
  unsigned __int8 v32; // [rsp+D0h] [rbp+18h]
  bool v33; // [rsp+D8h] [rbp+20h]

  v32 = a3;
  v3 = a3;
  v5 = this;
  if ( !a2 )
    return 2147500035LL;
  result = WindowsPerformanceRecorder::CControlManager::GetRunningProfileTraceType(this);
  if ( !(_DWORD)result )
  {
    v7 = *((_DWORD *)v5 + 142);
    if ( (v7 & 1) != 0 )
    {
      v33 = 1;
      v8 = L"Normal";
      v9 = v3 ^ 1;
    }
    else
    {
      if ( (v7 & 8) == 0 )
        return 3310891008LL;
      v8 = L"Boot";
      v9 = 0;
      v33 = 0;
    }
    v27 = (unsigned __int16 *)v8;
    v10 = 0;
    v26 = 0;
    v11 = 0;
    v25 = 0;
    v12 = WindowsPerformanceRecorder::CControlManager::ControlProgressHandler_Begin(v5);
    try
    {
      updated = v12;
      v24 = v12;
      if ( v12 >= 0 )
      {
        v31 = (WindowsPerformanceRecorder::CETWProperties *)operator new(0x1A8u);
        v10 = WindowsPerformanceRecorder::CETWProperties::CETWProperties(v31);
        v26 = v10;
        v14 = WindowsPerformanceRecorder::CETWProperties::Initialize(
                (WindowsPerformanceRecorder::CETWProperties *)v10,
                a2,
                v5,
                v3);
        updated = v14;
        if ( v14 >= 0 )
        {
          v11 = *(char **)(v10 + 320);
          v25 = (const unsigned __int16 *)v11;
          WindowsPerformanceRecorder::TelemetryUsage(
            (WindowsPerformanceRecorder *)0x2000,
            (unsigned __int64)"UpdateNormalOrShutdownRecording",
            v11,
            v15);
          if ( (_BYTE)v3 && *(_DWORD *)(v10 + 256) != 2 )
          {
            updated = -984068081;
            v24 = -984068081;
            goto LABEL_24;
          }
          v14 = WindowsPerformanceRecorder::CControlManager::ValidateWithRegistryState(
                  (const unsigned __int16 **)v5,
                  (struct WindowsPerformanceRecorder::CETWProperties *)v10,
                  1);
          updated = v14;
          if ( v14 >= 0 )
          {
            v14 = WindowsPerformanceRecorder::CControlManager::ValidateWithRuntimeState(
                    v5,
                    (struct WindowsPerformanceRecorder::CETWProperties *)v10,
                    1);
            updated = v14;
            if ( v14 >= 0 )
            {
              updated = WindowsPerformanceRecorder::CControlManager::SetProgressHandlerRuntimeState(
                          v5,
                          (struct WindowsPerformanceRecorder::CETWProperties *)v10,
                          v16,
                          1);
              v24 = updated;
              if ( updated >= 0 )
              {
                v17 = *(__int64 **)(v10 + 8);
                v18 = *(__int64 **)(v10 + 16);
                while ( v17 != v18 )
                {
                  updated = WindowsPerformanceRecorder::CControlManager::UpdateEventSession(
                              (__int64)v5,
                              (const unsigned __int16 *)v11,
                              *v17,
                              *(_DWORD *)(v10 + 256),
                              1);
                  v24 = updated;
                  if ( updated < 0 )
                    break;
                  updated = WindowsPerformanceRecorder::CControlManager::ControlProgressHandler_Update(v5, 1);
                  v24 = updated;
                  if ( updated < 0 )
                    break;
                  ++v17;
                }
                LOBYTE(v3) = v32;
              }
              goto LABEL_24;
            }
          }
        }
        v24 = v14;
      }
LABEL_24:
      LOBYTE(v31) = 0;
      if ( updated >= 0 )
      {
        v19 = WindowsPerformanceRecorder::CControlManager::VerifyAllProvidersEnabled(v5, (unsigned __int16 *)v11);
        updated = v19;
        if ( v19 < 0 )
        {
          v24 = v19;
        }
        else
        {
          WindowsPerformanceRecorder::CXmlWriter::CXmlWriter((WindowsPerformanceRecorder::CXmlWriter *)v29);
          InstanceNameScopedData = WindowsPerformanceRecorder::CInstanceNameScopedObjectImpl<WindowsPerformanceRecorder::CProfile>::GetInstanceNameScopedData((char *)v5 + 216);
          updated = WindowsPerformanceRecorder::CETWProperties::TranslateToXML(
                      (WindowsPerformanceRecorder::CETWProperties *)v10,
                      (struct WindowsPerformanceRecorder::CXmlWriter *)v29,
                      (bool)v31,
                      (*((_DWORD *)v5 + 142) & 8) != 0,
                      (struct WindowsPerformanceRecorder::CProfilesCache *)(InstanceNameScopedData + 40));
          if ( updated < 0 )
          {
            v24 = updated;
          }
          else
          {
            updated = WindowsPerformanceRecorder::CControlManager::SaveStateInRegistry(
                        (const BYTE **)v5,
                        (const BYTE *)v29[0],
                        v27,
                        v9,
                        v3,
                        v33);
            v24 = updated;
            v21 = *(_DWORD *)(v10 + 256);
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
              (__int64 *)&v31,
              (char *)v29[0]);
            WindowsPerformanceRecorder::CControlManager::LogProfileXmlEvent(v22, &v31, v21);
            WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&v31);
          }
          std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>::~pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>(v29);
        }
      }
    }
    catch ( std::bad_alloc )
    {
      v24 = -2147024882;
      v11 = (char *)v25;
      v10 = v26;
      updated = -2147024882;
      v5 = this;
    }
    catch ( std::length_error )
    {
      v24 = -2147024882;
      v5 = this;
      updated = -2147024882;
      v10 = v26;
      v11 = (char *)v25;
      goto LABEL_33;
    }
    catch ( ATL::CAtlException *v28 )
    {
      v24 = *(_DWORD *)v28;
      v11 = (char *)v25;
      v10 = v26;
      updated = *(_DWORD *)v28;
      v5 = this;
    }
    if ( updated < 0 )
    {
LABEL_33:
      if ( v10 )
      {
        try
        {
          WindowsPerformanceRecorder::CControlManager::RestoreSessionsFromRegistry(v5, (const unsigned __int16 *)v11);
        }
        catch ( ... )
        {
          WindowsPerformanceRecorder::CControlManager::AddProfileControlWarningInfo(
            this,
            -2147024882,
            &IID_IControlManager,
            v25,
            0);
          WindowsPerformanceRecorder::TraceHR(
            (WindowsPerformanceRecorder *)3,
            "UpdateNormalOrShutdownRecording",
            (const char *)0xC9E,
            0x8007000E,
            "%ws",
            (const char *)v25);
          v5 = this;
          updated = v24;
          v10 = v26;
          v11 = (char *)v25;
        }
        WindowsPerformanceRecorder::CControlManager::SetControlErrorInfo(
          v5,
          (unsigned int)updated,
          1,
          &IID_IControlManager,
          v11);
        WindowsPerformanceRecorder::TelemetryError(
          (WindowsPerformanceRecorder *)0x2000,
          (unsigned __int64)"UpdateNormalOrShutdownRecording",
          v11,
          (const unsigned __int16 *)(unsigned int)updated,
          v23);
      }
    }
    WindowsPerformanceRecorder::CControlManager::ControlProgressHandler_End(v5, updated, 0);
    if ( v10 )
      (**(void (__fastcall ***)(__int64, __int64))v10)(v10, 1);
    return (unsigned int)updated;
  }
  return result;
}

```

## disassembly

```asm
0x18005f068  mov     [rsp+arg_10], r8b
0x18005f06d  mov     [rsp+arg_0], rcx
0x18005f072  push    rbx
0x18005f073  push    rsi
0x18005f074  push    rdi
0x18005f075  push    r12
0x18005f077  push    r13
0x18005f079  push    r14
0x18005f07b  push    r15
0x18005f07d  sub     rsp, 80h
0x18005f084  mov     [rsp+0B8h+var_68], 0FFFFFFFFFFFFFFFEh
0x18005f08d  movzx   r12d, r8b
0x18005f091  mov     r15, rdx
0x18005f094  mov     rsi, rcx
0x18005f097  test    rdx, rdx
0x18005f09a  jnz     short loc_18005F0A6
0x18005f09c  mov     eax, 80004003h
0x18005f0a1  jmp     loc_18005F3DE
0x18005f0a6  call    ?GetRunningProfileTraceType@CControlManager@WindowsPerformanceRecorder@@AEAAJXZ; WindowsPerformanceRecorder::CControlManager::GetRunningProfileTraceType(void)
0x18005f0ab  test    eax, eax
0x18005f0ad  jnz     loc_18005F3DE
0x18005f0b3  mov     eax, [rsi+238h]
0x18005f0b9  test    al, 1
0x18005f0bb  jz      short loc_18005F0D5
0x18005f0bd  mov     [rsp+0B8h+arg_18], 1
0x18005f0c5  lea     rax, ?sc_wchWPRNormalRegistryKey@CControlManager@WindowsPerformanceRecorder@@0QBGB; "Normal"
0x18005f0cc  mov     r13d, r12d
0x18005f0cf  xor     r13d, 1
0x18005f0d3  jmp     short loc_18005F0EF
0x18005f0d5  test    al, 8
0x18005f0d7  jz      loc_18005F3D9
0x18005f0dd  lea     rax, ?sc_wchWPRBootRegistryKey@CControlManager@WindowsPerformanceRecorder@@0QBGB; "Boot"
0x18005f0e4  xor     r13d, r13d
0x18005f0e7  mov     [rsp+0B8h+arg_18], r13b
0x18005f0ef  mov     [rsp+0B8h+var_70], rax
0x18005f0f4  xor     ebx, ebx
0x18005f0f6  mov     [rsp+0B8h+var_78], rbx
0x18005f0fb  xor     r14d, r14d
0x18005f0fe  mov     [rsp+0B8h+var_80], r14
0x18005f103  mov     rcx, rsi; this
0x18005f106  call    ?ControlProgressHandler_Begin@CControlManager@WindowsPerformanceRecorder@@AEAAJXZ; WindowsPerformanceRecorder::CControlManager::ControlProgressHandler_Begin(void)
0x18005f10b  mov     edi, eax
0x18005f10d  mov     [rsp+0B8h+var_88], eax
0x18005f111  test    eax, eax
0x18005f113  js      loc_18005F22B
0x18005f119  mov     ecx, 1A8h; Size
0x18005f11e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005f123  mov     [rsp+0B8h+arg_8], rax
0x18005f12b  mov     rcx, rax; this
0x18005f12e  call    ??0CETWProperties@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::CETWProperties::CETWProperties(void)
0x18005f133  mov     rbx, rax
0x18005f136  mov     [rsp+0B8h+var_78], rax
0x18005f13b  mov     r9b, r12b; bool
0x18005f13e  mov     r8, rsi; struct WindowsPerformanceRecorder::CControlManager *
0x18005f141  mov     rdx, r15; struct IProfileCollection *
0x18005f144  mov     rcx, rax; this
0x18005f147  call    ?Initialize@CETWProperties@WindowsPerformanceRecorder@@QEAAJPEAUIProfileCollection@@PEAVCControlManager@2@_N@Z; WindowsPerformanceRecorder::CETWProperties::Initialize(IProfileCollection *,WindowsPerformanceRecorder::CControlManager *,bool)
0x18005f14c  mov     edi, eax
0x18005f14e  test    eax, eax
0x18005f150  js      loc_18005F21D
0x18005f156  mov     r14, [rbx+140h]
0x18005f15d  mov     [rsp+0B8h+var_80], r14
0x18005f162  mov     r8, r14; char *
0x18005f165  lea     rdx, aUpdatenormalor; "UpdateNormalOrShutdownRecording"
0x18005f16c  mov     ecx, 2000h; this
0x18005f171  call    ?TelemetryUsage@WindowsPerformanceRecorder@@YAX_KPEBDPEBG@Z; WindowsPerformanceRecorder::TelemetryUsage(unsigned __int64,char const *,ushort const *)
0x18005f176  test    r12b, r12b
0x18005f179  jz      short loc_18005F192
0x18005f17b  cmp     dword ptr [rbx+100h], 2
0x18005f182  jz      short loc_18005F192
0x18005f184  mov     edi, 0C558500Fh
0x18005f189  mov     [rsp+0B8h+var_88], edi
0x18005f18d  jmp     loc_18005F22B
0x18005f192  mov     r8b, 1; bool
0x18005f195  mov     rdx, rbx; struct WindowsPerformanceRecorder::CETWProperties *
0x18005f198  mov     rcx, rsi; this
0x18005f19b  call    ?ValidateWithRegistryState@CControlManager@WindowsPerformanceRecorder@@AEAAJAEAVCETWProperties@2@_N@Z; WindowsPerformanceRecorder::CControlManager::ValidateWithRegistryState(WindowsPerformanceRecorder::CETWProperties &,bool)
0x18005f1a0  mov     edi, eax
0x18005f1a2  test    eax, eax
0x18005f1a4  js      short loc_18005F21D
0x18005f1a6  mov     r8b, 1; bool
0x18005f1a9  mov     rdx, rbx; struct WindowsPerformanceRecorder::CETWProperties *
0x18005f1ac  mov     rcx, rsi; this
0x18005f1af  call    ?ValidateWithRuntimeState@CControlManager@WindowsPerformanceRecorder@@AEAAJAEAVCETWProperties@2@_N@Z; WindowsPerformanceRecorder::CControlManager::ValidateWithRuntimeState(WindowsPerformanceRecorder::CETWProperties &,bool)
0x18005f1b4  mov     edi, eax
0x18005f1b6  test    eax, eax
0x18005f1b8  js      short loc_18005F21D
0x18005f1ba  mov     r9b, 1; bool
0x18005f1bd  mov     rdx, rbx; struct WindowsPerformanceRecorder::CETWProperties *
0x18005f1c0  mov     rcx, rsi; this
0x18005f1c3  call    ?SetProgressHandlerRuntimeState@CControlManager@WindowsPerformanceRecorder@@AEAAJAEAVCETWProperties@2@_N1@Z; WindowsPerformanceRecorder::CControlManager::SetProgressHandlerRuntimeState(WindowsPerformanceRecorder::CETWProperties &,bool,bool)
0x18005f1c8  mov     edi, eax
0x18005f1ca  mov     [rsp+0B8h+var_88], eax
0x18005f1ce  test    eax, eax
0x18005f1d0  js      short loc_18005F22B
0x18005f1d2  mov     r15, [rbx+8]
0x18005f1d6  mov     r12, [rbx+10h]
0x18005f1da  cmp     r15, r12
0x18005f1dd  jz      short loc_18005F223
0x18005f1df  mov     byte ptr [rsp+0B8h+var_98], 1
0x18005f1e4  mov     r9d, [rbx+100h]
0x18005f1eb  mov     r8, [r15]
0x18005f1ee  mov     rdx, r14
0x18005f1f1  mov     rcx, rsi
0x18005f1f4  call    ?UpdateEventSession@CControlManager@WindowsPerformanceRecorder@@AEAAJPEBGAEAUCEventSession@CETWProperties@2@W4__MIDL_IProfile_0001@@_N@Z; WindowsPerformanceRecorder::CControlManager::UpdateEventSession(ushort const *,WindowsPerformanceRecorder::CETWProperties::CEventSession &,__MIDL_IProfile_0001,bool)
0x18005f1f9  mov     edi, eax
0x18005f1fb  mov     [rsp+0B8h+var_88], eax
0x18005f1ff  test    eax, eax
0x18005f201  js      short loc_18005F223
0x18005f203  mov     dl, 1; bool
0x18005f205  mov     rcx, rsi; this
0x18005f208  call    ?ControlProgressHandler_Update@CControlManager@WindowsPerformanceRecorder@@QEAAJ_N@Z; WindowsPerformanceRecorder::CControlManager::ControlProgressHandler_Update(bool)
0x18005f20d  mov     edi, eax
0x18005f20f  mov     [rsp+0B8h+var_88], eax
0x18005f213  test    eax, eax
0x18005f215  js      short loc_18005F223
0x18005f217  add     r15, 8
0x18005f21b  jmp     short loc_18005F1DA
0x18005f21d  mov     [rsp+0B8h+var_88], eax
0x18005f221  jmp     short loc_18005F22B
0x18005f223  mov     r12b, [rsp+0B8h+arg_10]
0x18005f22b  mov     byte ptr [rsp+0B8h+arg_8], 0
0x18005f233  test    edi, edi
0x18005f235  js      loc_18005F31F
0x18005f23b  lea     r8, [rbx+8]
0x18005f23f  lea     r9, [rsp+0B8h+arg_8]
0x18005f247  mov     rdx, r14; unsigned __int16 *
0x18005f24a  mov     rcx, rsi; this
0x18005f24d  call    ?VerifyAllProvidersEnabled@CControlManager@WindowsPerformanceRecorder@@AEAAJPEBGAEAV?$vector@PEAUCEventSession@CETWProperties@WindowsPerformanceRecorder@@V?$allocator@PEAUCEventSession@CETWProperties@WindowsPerformanceRecorder@@@std@@@std@@AEA_N@Z; WindowsPerformanceRecorder::CControlManager::VerifyAllProvidersEnabled(ushort const *,std::vector<WindowsPerformanceRecorder::CETWProperties::CEventSession *> &,bool &)
0x18005f252  mov     edi, eax
0x18005f254  test    eax, eax
0x18005f256  js      loc_18005F31B
0x18005f25c  lea     rcx, [rsp+0B8h+var_58]; this
0x18005f261  call    ??0CXmlWriter@WindowsPerformanceRecorder@@QEAA@I@Z; WindowsPerformanceRecorder::CXmlWriter::CXmlWriter(uint)
0x18005f266  nop
0x18005f267  lea     rcx, [rsi+0D8h]
0x18005f26e  call    ?GetInstanceNameScopedData@?$CInstanceNameScopedObjectImpl@VCProfile@WindowsPerformanceRecorder@@@WindowsPerformanceRecorder@@IEAAPEAUCInstanceNameScopedData@2@XZ; WindowsPerformanceRecorder::CInstanceNameScopedObjectImpl<WindowsPerformanceRecorder::CProfile>::GetInstanceNameScopedData(void)
0x18005f273  add     rax, 28h ; '('
0x18005f277  mov     r9d, [rsi+238h]
0x18005f27e  shr     r9d, 3
0x18005f282  and     r9b, 1; bool
0x18005f286  mov     [rsp+0B8h+var_98], rax; struct WindowsPerformanceRecorder::CProfilesCache *
0x18005f28b  mov     r8b, byte ptr [rsp+0B8h+arg_8]; bool
0x18005f293  lea     rdx, [rsp+0B8h+var_58]; struct WindowsPerformanceRecorder::CXmlWriter *
0x18005f298  mov     rcx, rbx; this
0x18005f29b  call    ?TranslateToXML@CETWProperties@WindowsPerformanceRecorder@@QEBAJAEAVCXmlWriter@2@_N1AEAVCProfilesCache@2@@Z; WindowsPerformanceRecorder::CETWProperties::TranslateToXML(WindowsPerformanceRecorder::CXmlWriter &,bool,bool,WindowsPerformanceRecorder::CProfilesCache &)
0x18005f2a0  mov     edi, eax
0x18005f2a2  test    eax, eax
0x18005f2a4  js      short loc_18005F30B
0x18005f2a6  mov     al, [rsp+0B8h+arg_18]
0x18005f2ad  mov     [rsp+0B8h+var_90], al; bool
0x18005f2b1  mov     byte ptr [rsp+0B8h+var_98], r12b; bool
0x18005f2b6  mov     r9d, r13d; unsigned int
0x18005f2b9  mov     r8, [rsp+0B8h+var_70]; unsigned __int16 *
0x18005f2be  mov     rdx, [rsp+0B8h+var_58]; unsigned __int16 *
0x18005f2c3  mov     rcx, rsi; this
0x18005f2c6  call    ?SaveStateInRegistry@CControlManager@WindowsPerformanceRecorder@@AEAAJPEBG0K_N1@Z; WindowsPerformanceRecorder::CControlManager::SaveStateInRegistry(ushort const *,ushort const *,ulong,bool,bool)
0x18005f2cb  mov     edi, eax
0x18005f2cd  mov     [rsp+0B8h+var_88], eax
0x18005f2d1  mov     r15d, [rbx+100h]
0x18005f2d8  mov     rdx, [rsp+0B8h+var_58]
0x18005f2dd  lea     rcx, [rsp+0B8h+arg_8]
0x18005f2e5  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18005f2ea  nop
0x18005f2eb  mov     r8d, r15d
0x18005f2ee  lea     rdx, [rsp+0B8h+arg_8]
0x18005f2f6  call    ?LogProfileXmlEvent@CControlManager@WindowsPerformanceRecorder@@AEAAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@W4__MIDL_IProfile_0001@@@Z; WindowsPerformanceRecorder::CControlManager::LogProfileXmlEvent(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,__MIDL_IProfile_0001)
0x18005f2fb  nop
0x18005f2fc  lea     rcx, [rsp+0B8h+arg_8]; this
0x18005f304  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x18005f309  jmp     short loc_18005F30F
0x18005f30b  mov     [rsp+0B8h+var_88], edi
0x18005f30f  lea     rcx, [rsp+0B8h+var_58]
0x18005f314  call    ??1?$pair@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@QEAA@XZ; std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>::~pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>(void)
0x18005f319  jmp     short loc_18005F31F
0x18005f31b  mov     [rsp+0B8h+var_88], eax
0x18005f31f  jmp     short loc_18005F337
0x18005f321  mov     r14, [rsp+0B8h+var_80]
0x18005f326  mov     rbx, [rsp+0B8h+var_78]
0x18005f32b  mov     edi, [rsp+0B8h+var_88]
0x18005f32f  mov     rsi, [rsp+0B8h+arg_0]
0x18005f337  test    edi, edi
0x18005f339  jns     short loc_18005F3AF
0x18005f33b  test    rbx, rbx
0x18005f33e  jz      short loc_18005F3AF
0x18005f340  mov     rdx, r14; unsigned __int16 *
0x18005f343  mov     rcx, rsi; this
0x18005f346  call    ?RestoreSessionsFromRegistry@CControlManager@WindowsPerformanceRecorder@@AEAAJPEBG@Z; WindowsPerformanceRecorder::CControlManager::RestoreSessionsFromRegistry(ushort const *)
0x18005f34b  nop
0x18005f34c  jmp     short loc_18005F37C
0x18005f34e  mov     rsi, [rsp+0B8h+arg_0]
0x18005f356  mov     edi, [rsp+0B8h+var_88]
0x18005f35a  mov     rbx, [rsp+0B8h+var_78]
0x18005f35f  mov     r14, [rsp+0B8h+var_80]
0x18005f364  jmp     short loc_18005F33B
0x18005f366  mov     rsi, [rsp+0B8h+arg_0]
0x18005f36e  mov     edi, [rsp+0B8h+var_88]
0x18005f372  mov     rbx, [rsp+0B8h+var_78]
0x18005f377  mov     r14, [rsp+0B8h+var_80]
0x18005f37c  mov     [rsp+0B8h+var_98], r14; int
0x18005f381  lea     r9, IID_IControlManager
0x18005f388  mov     r8d, 1
0x18005f38e  mov     edx, edi
0x18005f390  mov     rcx, rsi
0x18005f393  call    ?SetControlErrorInfo@CControlManager@WindowsPerformanceRecorder@@QEAAXJW4__MIDL_IControlErrorInfo_0001@@AEBU_GUID@@PEBG@Z; WindowsPerformanceRecorder::CControlManager::SetControlErrorInfo(long,__MIDL_IControlErrorInfo_0001,_GUID const &,ushort const *)
0x18005f398  mov     r9d, edi; unsigned __int16 *
0x18005f39b  mov     r8, r14; char *
0x18005f39e  lea     rdx, aUpdatenormalor; "UpdateNormalOrShutdownRecording"
0x18005f3a5  mov     ecx, 2000h; this
0x18005f3aa  call    ?TelemetryError@WindowsPerformanceRecorder@@YAX_KPEBDPEBGJ@Z; WindowsPerformanceRecorder::TelemetryError(unsigned __int64,char const *,ushort const *,long)
0x18005f3af  xor     r8d, r8d; unsigned int
0x18005f3b2  mov     edx, edi; int
0x18005f3b4  mov     rcx, rsi; this
0x18005f3b7  call    ?ControlProgressHandler_End@CControlManager@WindowsPerformanceRecorder@@AEAAXJK@Z; WindowsPerformanceRecorder::CControlManager::ControlProgressHandler_End(long,ulong)
0x18005f3bc  nop
0x18005f3bd  test    rbx, rbx
0x18005f3c0  jz      short loc_18005F3D5
0x18005f3c2  mov     rax, [rbx]
0x18005f3c5  mov     edx, 1
0x18005f3ca  mov     rcx, rbx
0x18005f3cd  mov     rax, [rax]
0x18005f3d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f3d5  mov     eax, edi
0x18005f3d7  jmp     short loc_18005F3DE
0x18005f3d9  mov     eax, 0C5583000h
0x18005f3de  add     rsp, 80h
0x18005f3e5  pop     r15
0x18005f3e7  pop     r14
0x18005f3e9  pop     r13
0x18005f3eb  pop     r12
0x18005f3ed  pop     rdi
0x18005f3ee  pop     rsi
0x18005f3ef  pop     rbx
0x18005f3f0  retn
```
