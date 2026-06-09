# WindowsPerformanceRecorder::CControlManager::SaveStateInRegistry(ushort const *,ushort const *,ulong,bool,bool)

- ea: `0x180007c40`
- end: `0x18000826a`
- name: `?SaveStateInRegistry@CControlManager@WindowsPerformanceRecorder@@AEAAJPEBG0K_N1@Z`
- size: `1578`
- prototype: `int(WindowsPerformanceRecorder::CControlManager *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int, bool, bool)`
- caller_count: `3`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180032adc`
- `0x18004ac00`
- `0x18005f068`

## callees

- `0x180007c40`
- `0x180008270`
- `0x18000829c`
- `0x180008330`
- `0x18000a154`
- `0x18000eeb0`
- `0x1800131a0`
- `0x18001a8c8`
- `0x18001c32c`
- `0x180037100`
- `0x180038cd4`
- `0x180039ed8`
- `0x180044210`
- `0x18004ece0`
- `0x18005cacc`
- `0x18008c010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180007dc1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180007eae`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180007dc1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180007eae`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180007f85`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180008053`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180007f85`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180008053`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007ce0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007fd0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007fdf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008079`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008088`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007ce0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007fd0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007fdf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008079`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180008088`

## string_xrefs

- `0x180008049`: `TracePath`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall WindowsPerformanceRecorder::CControlManager::SaveStateInRegistry(
        const BYTE **this,
        const BYTE *a2,
        const unsigned __int16 *a3,
        DWORD a4,
        bool a5,
        bool a6)
{
  const WCHAR *v10; // rax
  __int64 v11; // r8
  LPCWSTR v12; // rbx
  LSTATUS Key; // eax
  __int64 v14; // r8
  HKEY v15; // r14
  char v16; // al
  LSTATUS v17; // eax
  __int64 v18; // r8
  HKEY v19; // rdi
  char v20; // al
  __int64 v21; // rsi
  __int64 v22; // rax
  LSTATUS v23; // eax
  __int64 v24; // r8
  unsigned int v25; // r12d
  __int64 result; // rax
  const BYTE *v27; // rcx
  LSTATUS v28; // eax
  unsigned __int16 *v29; // r9
  unsigned int v30; // esi
  unsigned int v31; // eax
  unsigned int v32; // ebx
  unsigned int v33; // eax
  unsigned int v34; // ebx
  unsigned int v35; // ebx
  unsigned int v36; // ebx
  REGSAM samDesired; // [rsp+28h] [rbp-E0h]
  struct _SECURITY_ATTRIBUTES *lpSecurityAttributes; // [rsp+30h] [rbp-D8h]
  unsigned int *phkResult; // [rsp+38h] [rbp-D0h]
  DWORD dwDisposition[2]; // [rsp+50h] [rbp-B8h] BYREF
  LPCWSTR lpSubKey; // [rsp+58h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v43; // [rsp+68h] [rbp-A0h]
  __int64 v44; // [rsp+70h] [rbp-98h]
  _QWORD v45[4]; // [rsp+78h] [rbp-90h] BYREF
  ATL::CAtlException *v46; // [rsp+98h] [rbp-70h] BYREF
  _QWORD v47[3]; // [rsp+A0h] [rbp-68h] BYREF
  HKEY v48[2]; // [rsp+B8h] [rbp-50h] BYREF

  v45[3] = -2;
  hKey = 0;
  v43 = 0;
  v44 = 0;
  if ( WindowsPerformanceRecorder::CControlManager::GetWPRControlRegistryKey(
         (WindowsPerformanceRecorder::CControlManager *)this,
         (struct ATL::CRegKey *)&hKey,
         0) >= 0 )
  {
    WindowsPerformanceRecorder::CControlManager::SaveEventSession_::_64_::CPerfEventMacro::CPerfEventMacro(&lpSubKey);
    if ( (unsigned int)ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)&hKey, a3) )
    {
      WindowsPerformanceRecorder::CControlManager::SaveStateInRegistry_::_14_::CPerfEventMacro::_CPerfEventMacro(&lpSubKey);
      ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
      goto LABEL_7;
    }
    WindowsPerformanceRecorder::CControlManager::SaveStateInRegistry_::_14_::CPerfEventMacro::_CPerfEventMacro(&lpSubKey);
  }
  if ( hKey )
    RegCloseKey(hKey);
LABEL_7:
  v10 = (const WCHAR *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  lpSubKey = v10;
  try
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
      &lpSubKey,
      L"%ws\\%ws");
    hKey = 0;
    v43 = 0;
    v44 = 0;
    v47[0] = &off_18008EB00;
    if ( (Microsoft_Windows_Performance_Recorder_ControlEnableBits & 1) != 0 )
      McGenEventWrite_EventWriteTransfer(
        &WindowsPerformanceRecorderControlProvider_Context,
        Perf_ExternalCall_Begin,
        v11,
        1,
        v48);
    dwDisposition[0] = 0;
    v48[0] = 0;
    v12 = lpSubKey;
    Key = RegCreateKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0, 0, 0x2001Fu, 0, v48, dwDisposition);
    if ( Key || (Key = ATL::CRegKey::Close((ATL::CRegKey *)&hKey), v15 = v48[0], hKey = v48[0], Key) )
    {
      v36 = ATL::AtlHresultFromWin32(Key);
      WindowsPerformanceRecorder::CControlManager::SaveStateInRegistry_::_14_::CPerfEventMacro::_CPerfEventMacro(v47);
      ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
      WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&lpSubKey);
      result = v36;
    }
    else
    {
      v16 = Microsoft_Windows_Performance_Recorder_ControlEnableBits;
      if ( (Microsoft_Windows_Performance_Recorder_ControlEnableBits & 1) != 0 )
      {
        McGenEventWrite_EventWriteTransfer(&WindowsPerformanceRecorderControlProvider_Context, L"e", v14, 1, v47);
        v16 = Microsoft_Windows_Performance_Recorder_ControlEnableBits;
      }
      memset(v45, 0, 24);
      v47[0] = &off_18008EB00;
      if ( (v16 & 1) != 0 )
        McGenEventWrite_EventWriteTransfer(
          &WindowsPerformanceRecorderControlProvider_Context,
          Perf_ExternalCall_Begin,
          v14,
          1,
          v48);
      dwDisposition[0] = 0;
      v48[0] = 0;
      v17 = RegCreateKeyExW(v15, a3, 0, 0, a4, 0x2001Fu, 0, v48, dwDisposition);
      if ( v17 || (v17 = ATL::CRegKey::Close((ATL::CRegKey *)v45), v19 = v48[0], v45[0] = v48[0], v17) )
      {
        v35 = ATL::AtlHresultFromWin32(v17);
        WindowsPerformanceRecorder::CControlManager::SaveStateInRegistry_::_14_::CPerfEventMacro::_CPerfEventMacro(v47);
        ATL::CRegKey::Close((ATL::CRegKey *)v45);
        ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
        WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&lpSubKey);
        result = v35;
      }
      else
      {
        v20 = Microsoft_Windows_Performance_Recorder_ControlEnableBits;
        if ( (Microsoft_Windows_Performance_Recorder_ControlEnableBits & 1) != 0 )
        {
          McGenEventWrite_EventWriteTransfer(&WindowsPerformanceRecorderControlProvider_Context, L"e", v18, 1, v47);
          v20 = Microsoft_Windows_Performance_Recorder_ControlEnableBits;
        }
        *(_QWORD *)dwDisposition = &off_18008EB00;
        if ( (v20 & 1) != 0 )
          McGenEventWrite_EventWriteTransfer(
            &WindowsPerformanceRecorderControlProvider_Context,
            Perf_ExternalCall_Begin,
            v18,
            1,
            v47);
        if ( !a2 )
          ATL::AtlThrowImpl(-2147467259);
        v21 = -1;
        v22 = -1;
        do
          ++v22;
        while ( *(_WORD *)&a2[2 * v22] );
        v23 = RegSetValueExW(v19, L"RunningProfile", 0, 1u, a2, 2 * v22 + 2);
        if ( v23 )
        {
          v25 = ATL::AtlHresultFromWin32(v23);
          if ( (Microsoft_Windows_Performance_Recorder_ControlEnableBits & 1) != 0 )
            McGenEventWrite_EventWriteTransfer(&WindowsPerformanceRecorderControlProvider_Context, L"e", v24, 1, v47);
          if ( v19 )
            RegCloseKey(v19);
          if ( v15 )
            RegCloseKey(v15);
          if ( _InterlockedDecrement((volatile signed __int32 *)v12 - 2) <= 0 )
            (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v12 - 3) + 8LL))(*((_QWORD *)v12 - 3));
          result = v25;
        }
        else
        {
          v27 = this[66];
          if ( !v27 )
            ATL::AtlThrowImpl(-2147467259);
          do
            ++v21;
          while ( *(_WORD *)&v27[2 * v21] );
          v28 = RegSetValueExW(v19, L"TracePath", 0, 1u, v27, 2 * v21 + 2);
          if ( v28 )
          {
            v30 = ATL::AtlHresultFromWin32(v28);
            WindowsPerformanceRecorder::CControlManager::SaveStateInRegistry_::_14_::CPerfEventMacro::_CPerfEventMacro(dwDisposition);
            if ( v19 )
              RegCloseKey(v19);
            if ( v15 )
              RegCloseKey(v15);
            ATL::CStringData::Release((ATL::CStringData *)(v12 - 12));
            result = v30;
          }
          else
          {
            if ( a5 )
            {
              v31 = ATL::CRegKey::SetDWORDValue(
                      (ATL::CRegKey *)v45,
                      L"Shutdown",
                      (unsigned int)(*((_BYTE *)this + 572) != 0) + 1);
              if ( v31 )
              {
                v32 = ATL::AtlHresultFromWin32(v31);
                WindowsPerformanceRecorder::CControlManager::SaveStateInRegistry_::_14_::CPerfEventMacro::_CPerfEventMacro(dwDisposition);
                ATL::CRegKey::Close((ATL::CRegKey *)v45);
                ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
                WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&lpSubKey);
                return v32;
              }
            }
            if ( a6 )
            {
              memset(v47, 0, sizeof(v47));
              v33 = ATL::CRegKey::Create(
                      (ATL::CRegKey *)v47,
                      v19,
                      L"SystemRunning",
                      v29,
                      1u,
                      samDesired,
                      lpSecurityAttributes,
                      phkResult);
              if ( v33 )
              {
                v34 = ATL::AtlHresultFromWin32(v33);
                ATL::CRegKey::Close((ATL::CRegKey *)v47);
                WindowsPerformanceRecorder::CControlManager::SaveStateInRegistry_::_14_::CPerfEventMacro::_CPerfEventMacro(dwDisposition);
                ATL::CRegKey::Close((ATL::CRegKey *)v45);
                ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
                WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&lpSubKey);
                return v34;
              }
              ATL::CRegKey::Close((ATL::CRegKey *)v47);
            }
            WindowsPerformanceRecorder::CControlManager::SaveStateInRegistry_::_14_::CPerfEventMacro::_CPerfEventMacro(dwDisposition);
            ATL::CRegKey::Close((ATL::CRegKey *)v45);
            ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
            WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&lpSubKey);
            result = 0;
          }
        }
      }
    }
  }
  catch ( ATL::CAtlException *v46 )
  {
    return *(unsigned int *)v46;
  }
  return result;
}

```

## disassembly

```asm
0x180007c40  mov     rax, rsp
0x180007c43  push    rbx
0x180007c44  push    rsi
0x180007c45  push    rdi
0x180007c46  push    r12
0x180007c48  push    r13
0x180007c4a  push    r14
0x180007c4c  push    r15
0x180007c4e  sub     rsp, 0D0h
0x180007c55  mov     qword ptr [rax-78h], 0FFFFFFFFFFFFFFFEh
0x180007c5d  mov     rax, cs:__security_cookie
0x180007c64  xor     rax, rsp
0x180007c67  mov     [rsp+108h+var_40], rax
0x180007c6f  mov     esi, r9d
0x180007c72  mov     rdi, r8
0x180007c75  mov     r12, rdx
0x180007c78  mov     r13, rcx
0x180007c7b  xor     r14d, r14d
0x180007c7e  mov     [rsp+108h+hKey], r14
0x180007c83  mov     [rsp+108h+var_A0], r14
0x180007c88  mov     [rsp+108h+var_98], r14
0x180007c8d  xor     r8d, r8d; unsigned __int16 *
0x180007c90  lea     rdx, [rsp+108h+hKey]; struct ATL::CRegKey *
0x180007c95  call    ?GetWPRControlRegistryKey@CControlManager@WindowsPerformanceRecorder@@AEBAJAEAVCRegKey@ATL@@PEBG@Z; WindowsPerformanceRecorder::CControlManager::GetWPRControlRegistryKey(ATL::CRegKey &,ushort const *)
0x180007c9a  test    eax, eax
0x180007c9c  js      short loc_180007CD6
0x180007c9e  lea     rcx, [rsp+108h+lpSubKey]
0x180007ca3  call    _WindowsPerformanceRecorder__CControlManager__SaveEventSession____64___CPerfEventMacro__CPerfEventMacro
0x180007ca8  mov     rdx, rdi; unsigned __int16 *
0x180007cab  lea     rcx, [rsp+108h+hKey]; this
0x180007cb0  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x180007cb5  lea     rcx, [rsp+108h+lpSubKey]
0x180007cba  test    eax, eax
0x180007cbc  jz      short loc_180007CD0
0x180007cbe  call    _WindowsPerformanceRecorder__CControlManager__SaveStateInRegistry____14___CPerfEventMacro___CPerfEventMacro
0x180007cc3  nop
0x180007cc4  lea     rcx, [rsp+108h+hKey]; this
0x180007cc9  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180007cce  jmp     short loc_180007CE7
0x180007cd0  call    _WindowsPerformanceRecorder__CControlManager__SaveStateInRegistry____14___CPerfEventMacro___CPerfEventMacro
0x180007cd5  nop
0x180007cd6  mov     rcx, [rsp+108h+hKey]; hKey
0x180007cdb  test    rcx, rcx
0x180007cde  jz      short loc_180007CE7
0x180007ce0  call    cs:__imp_RegCloseKey
0x180007ce6  nop
0x180007ce7  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180007cee  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180007cf5  mov     rax, [rax+18h]
0x180007cf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007cfe  add     rax, 18h
0x180007d02  mov     [rsp+108h+lpSubKey], rax
0x180007d07  mov     r9, [r13+0E0h]
0x180007d0e  lea     r8, ?sc_wchWPRControlRegistryKey@CControlManager@WindowsPerformanceRecorder@@0QBGB; "Software\\Microsoft\\Windows Performanc"...
0x180007d15  lea     rdx, aWsWs_5; "%ws\\%ws"
0x180007d1c  lea     rcx, [rsp+108h+lpSubKey]
0x180007d21  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x180007d26  mov     [rsp+108h+hKey], r14
0x180007d2b  mov     [rsp+108h+var_A0], r14
0x180007d30  mov     [rsp+108h+var_98], r14
0x180007d35  lea     rax, off_18008EB00
0x180007d3c  mov     [rsp+108h+var_68], rax
0x180007d44  lea     r15, WindowsPerformanceRecorderControlProvider_Context
0x180007d4b  test    byte ptr cs:Microsoft_Windows_Performance_Recorder_ControlEnableBits, 1
0x180007d52  jz      short loc_180007D76
0x180007d54  lea     rax, [rsp+108h+var_50]
0x180007d5c  mov     qword ptr [rsp+108h+dwOptions], rax
0x180007d61  mov     r9d, 1
0x180007d67  lea     rdx, Perf_ExternalCall_Begin
0x180007d6e  mov     rcx, r15
0x180007d71  call    McGenEventWrite_EventWriteTransfer
0x180007d76  mov     [rsp+108h+dwDisposition], r14d
0x180007d7b  mov     [rsp+108h+var_50], r14
0x180007d83  lea     rax, [rsp+108h+dwDisposition]
0x180007d88  mov     [rsp+108h+lpdwDisposition], rax; lpdwDisposition
0x180007d8d  lea     rax, [rsp+108h+var_50]
0x180007d95  mov     [rsp+108h+phkResult], rax; phkResult
0x180007d9a  mov     [rsp+108h+lpSecurityAttributes], r14; lpSecurityAttributes
0x180007d9f  mov     [rsp+108h+samDesired], 2001Fh; samDesired
0x180007da7  mov     [rsp+108h+dwOptions], r14d; dwOptions
0x180007dac  xor     r9d, r9d; lpClass
0x180007daf  xor     r8d, r8d; Reserved
0x180007db2  mov     rbx, [rsp+108h+lpSubKey]
0x180007db7  mov     rdx, rbx; lpSubKey
0x180007dba  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180007dc1  call    cs:__imp_RegCreateKeyExW
0x180007dc7  test    eax, eax
0x180007dc9  jnz     loc_180008212
0x180007dcf  lea     rcx, [rsp+108h+hKey]; this
0x180007dd4  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180007dd9  mov     r14, [rsp+108h+var_50]
0x180007de1  mov     [rsp+108h+hKey], r14
0x180007de6  xor     edx, edx
0x180007de8  test    eax, eax
0x180007dea  jnz     loc_180008212
0x180007df0  mov     eax, cs:Microsoft_Windows_Performance_Recorder_ControlEnableBits
0x180007df6  test    al, 1
0x180007df8  jz      short loc_180007E22
0x180007dfa  lea     rax, [rsp+108h+var_68]
0x180007e02  mov     qword ptr [rsp+108h+dwOptions], rax
0x180007e07  lea     r9d, [rdx+1]
0x180007e0b  lea     rdx, Perf_ExternalCall_End; "e"
0x180007e12  mov     rcx, r15
0x180007e15  call    McGenEventWrite_EventWriteTransfer
0x180007e1a  mov     eax, cs:Microsoft_Windows_Performance_Recorder_ControlEnableBits
0x180007e20  xor     edx, edx
0x180007e22  mov     [rsp+108h+var_90], rdx
0x180007e27  mov     [rsp+108h+var_88], rdx
0x180007e2f  mov     [rsp+108h+var_80], rdx
0x180007e37  lea     rcx, off_18008EB00
0x180007e3e  mov     [rsp+108h+var_68], rcx
0x180007e46  test    al, 1
0x180007e48  jz      short loc_180007E6E
0x180007e4a  lea     rax, [rsp+108h+var_50]
0x180007e52  mov     qword ptr [rsp+108h+dwOptions], rax
0x180007e57  mov     r9d, 1
0x180007e5d  lea     rdx, Perf_ExternalCall_Begin
0x180007e64  mov     rcx, r15
0x180007e67  call    McGenEventWrite_EventWriteTransfer
0x180007e6c  xor     edx, edx
0x180007e6e  mov     [rsp+108h+dwDisposition], edx
0x180007e72  mov     [rsp+108h+var_50], rdx
0x180007e7a  lea     rax, [rsp+108h+dwDisposition]
0x180007e7f  mov     [rsp+108h+lpdwDisposition], rax; lpdwDisposition
0x180007e84  lea     rax, [rsp+108h+var_50]
0x180007e8c  mov     [rsp+108h+phkResult], rax; unsigned int *
0x180007e91  mov     [rsp+108h+lpSecurityAttributes], rdx; struct _SECURITY_ATTRIBUTES *
0x180007e96  mov     [rsp+108h+samDesired], 2001Fh; samDesired
0x180007e9e  mov     [rsp+108h+dwOptions], esi; dwOptions
0x180007ea2  xor     r9d, r9d; lpClass
0x180007ea5  xor     r8d, r8d; Reserved
0x180007ea8  mov     rdx, rdi; lpSubKey
0x180007eab  mov     rcx, r14; hKey
0x180007eae  call    cs:__imp_RegCreateKeyExW
0x180007eb4  test    eax, eax
0x180007eb6  jnz     loc_1800081D7
0x180007ebc  lea     rcx, [rsp+108h+var_90]; this
0x180007ec1  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180007ec6  mov     rdi, [rsp+108h+var_50]
0x180007ece  mov     [rsp+108h+var_90], rdi
0x180007ed3  test    eax, eax
0x180007ed5  jnz     loc_1800081D7
0x180007edb  mov     eax, cs:Microsoft_Windows_Performance_Recorder_ControlEnableBits
0x180007ee1  test    al, 1
0x180007ee3  jz      short loc_180007F0D
0x180007ee5  lea     rax, [rsp+108h+var_68]
0x180007eed  mov     qword ptr [rsp+108h+dwOptions], rax
0x180007ef2  mov     r9d, 1
0x180007ef8  lea     rdx, Perf_ExternalCall_End; "e"
0x180007eff  mov     rcx, r15
0x180007f02  call    McGenEventWrite_EventWriteTransfer
0x180007f07  mov     eax, cs:Microsoft_Windows_Performance_Recorder_ControlEnableBits
0x180007f0d  lea     rcx, off_18008EB00
0x180007f14  mov     qword ptr [rsp+108h+dwDisposition], rcx
0x180007f19  test    al, 1
0x180007f1b  jz      short loc_180007F40
0x180007f1d  lea     rax, [rsp+108h+var_68]
0x180007f25  mov     qword ptr [rsp+108h+dwOptions], rax
0x180007f2a  mov     r9d, 1
0x180007f30  lea     rdx, Perf_ExternalCall_Begin
0x180007f37  mov     rcx, r15
0x180007f3a  call    McGenEventWrite_EventWriteTransfer
0x180007f3f  nop
0x180007f40  test    r12, r12
0x180007f43  jnz     short loc_180007F4F
0x180007f45  mov     ecx, 80004005h; int
0x180007f4a  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180007f4f  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180007f53  mov     rax, rsi
0x180007f56  xor     ecx, ecx
0x180007f58  inc     rax
0x180007f5b  cmp     [r12+rax*2], cx
0x180007f60  jnz     short loc_180007F58
0x180007f62  lea     eax, ds:2[rax*2]
0x180007f69  mov     [rsp+108h+samDesired], eax; cbData
0x180007f6d  mov     qword ptr [rsp+108h+dwOptions], r12; lpData
0x180007f72  mov     r9d, 1; dwType
0x180007f78  xor     r8d, r8d; Reserved
0x180007f7b  lea     rdx, ?sc_wchWPRRunningProfileRegistryKey@CControlManager@WindowsPerformanceRecorder@@0QBGB; "RunningProfile"
0x180007f82  mov     rcx, rdi; hKey
0x180007f85  call    cs:__imp_RegSetValueExW
0x180007f8b  xor     r12d, r12d
0x180007f8e  test    eax, eax
0x180007f90  jz      short loc_18000800E
0x180007f92  mov     ecx, eax; unsigned int
0x180007f94  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x180007f99  mov     r12d, eax
0x180007f9c  test    byte ptr cs:Microsoft_Windows_Performance_Recorder_ControlEnableBits, 1
0x180007fa3  jz      short loc_180007FC8
0x180007fa5  lea     rax, [rsp+108h+var_68]
0x180007fad  mov     qword ptr [rsp+108h+dwOptions], rax
0x180007fb2  mov     r9d, 1
0x180007fb8  lea     rdx, Perf_ExternalCall_End; "e"
0x180007fbf  mov     rcx, r15
0x180007fc2  call    McGenEventWrite_EventWriteTransfer
0x180007fc7  nop
0x180007fc8  test    rdi, rdi
0x180007fcb  jz      short loc_180007FD7
0x180007fcd  mov     rcx, rdi; hKey
0x180007fd0  call    cs:__imp_RegCloseKey
0x180007fd6  nop
0x180007fd7  test    r14, r14
0x180007fda  jz      short loc_180007FE6
0x180007fdc  mov     rcx, r14; hKey
0x180007fdf  call    cs:__imp_RegCloseKey
0x180007fe5  nop
0x180007fe6  lea     rdx, [rbx-18h]
0x180007fea  mov     eax, esi
0x180007fec  lock xadd [rdx+10h], eax
0x180007ff1  add     eax, esi
0x180007ff3  test    eax, eax
0x180007ff5  jg      short loc_180008006
0x180007ff7  mov     rcx, [rdx]
0x180007ffa  mov     rax, [rcx]
0x180007ffd  mov     rax, [rax+8]
0x180008001  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008006  mov     eax, r12d
0x180008009  jmp     loc_180008246
0x18000800e  mov     rcx, [r13+210h]
0x180008015  test    rcx, rcx
0x180008018  jnz     short loc_180008024
0x18000801a  mov     ecx, 80004005h; int
0x18000801f  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180008024  inc     rsi
0x180008027  cmp     [rcx+rsi*2], r12w
0x18000802c  jnz     short loc_180008024
0x18000802e  lea     eax, ds:2[rsi*2]
0x180008035  mov     [rsp+108h+samDesired], eax; unsigned int
0x180008039  mov     qword ptr [rsp+108h+dwOptions], rcx; lpData
0x18000803e  mov     esi, 1
0x180008043  mov     r9d, esi; dwType
0x180008046  xor     r8d, r8d; Reserved
0x180008049  lea     rdx, ?sc_wchWPRTracePath@CControlManager@WindowsPerformanceRecorder@@0QBGB; "TracePath"
0x180008050  mov     rcx, rdi; hKey
0x180008053  call    cs:__imp_RegSetValueExW
0x180008059  test    eax, eax
0x18000805b  jz      short loc_18000809F
0x18000805d  mov     ecx, eax; unsigned int
0x18000805f  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x180008064  mov     esi, eax
0x180008066  lea     rcx, [rsp+108h+dwDisposition]
0x18000806b  call    _WindowsPerformanceRecorder__CControlManager__SaveStateInRegistry____14___CPerfEventMacro___CPerfEventMacro
0x180008070  nop
0x180008071  test    rdi, rdi
0x180008074  jz      short loc_180008080
0x180008076  mov     rcx, rdi; hKey
0x180008079  call    cs:__imp_RegCloseKey
0x18000807f  nop
0x180008080  test    r14, r14
0x180008083  jz      short loc_18000808F
0x180008085  mov     rcx, r14; hKey
0x180008088  call    cs:__imp_RegCloseKey
0x18000808e  nop
0x18000808f  lea     rcx, [rbx-18h]; this
0x180008093  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180008098  mov     eax, esi
0x18000809a  jmp     loc_180008246
0x18000809f  cmp     [rsp+108h+arg_20], r12b
0x1800080a7  jz      short loc_18000810B
0x1800080a9  mov     al, [r13+23Ch]
0x1800080b0  neg     al
0x1800080b2  sbb     r8d, r8d
0x1800080b5  neg     r8d
0x1800080b8  add     r8d, esi; unsigned int
0x1800080bb  lea     rdx, ?sc_wchShutdownFileNameTag@CControlManager@WindowsPerformanceRecorder@@0QBGB; "Shutdown"
0x1800080c2  lea     rcx, [rsp+108h+var_90]; this
0x1800080c7  call    ?SetDWORDValue@CRegKey@ATL@@QEAAJPEBGK@Z; ATL::CRegKey::SetDWORDValue(ushort const *,ulong)
0x1800080cc  test    eax, eax
0x1800080ce  jz      short loc_18000810B
0x1800080d0  mov     ecx, eax; unsigned int
0x1800080d2  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x1800080d7  mov     ebx, eax
0x1800080d9  lea     rcx, [rsp+108h+dwDisposition]
0x1800080de  call    _WindowsPerformanceRecorder__CControlManager__SaveStateInRegistry____14___CPerfEventMacro___CPerfEventMacro
0x1800080e3  nop
0x1800080e4  lea     rcx, [rsp+108h+var_90]; this
0x1800080e9  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800080ee  nop
0x1800080ef  lea     rcx, [rsp+108h+hKey]; this
0x1800080f4  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800080f9  nop
0x1800080fa  lea     rcx, [rsp+108h+lpSubKey]; this
0x1800080ff  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x180008104  mov     eax, ebx
0x180008106  jmp     loc_180008246
0x18000810b  cmp     [rsp+108h+arg_28], r12b
0x180008113  jz      loc_1800081A7
0x180008119  mov     [rsp+108h+var_68], r12
0x180008121  mov     [rsp+108h+var_60], r12
0x180008129  mov     [rsp+108h+var_58], r12
0x180008131  mov     [rsp+108h+dwOptions], esi; unsigned int
0x180008135  lea     r8, ?sc_wchWPRSystemRunningRegistryKey@CControlManager@WindowsPerformanceRecorder@@0QBGB; "SystemRunning"
0x18000813c  mov     rdx, rdi; hKey
0x18000813f  lea     rcx, [rsp+108h+var_68]; this
0x180008147  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x18000814c  test    eax, eax
0x18000814e  jz      short loc_180008199
0x180008150  mov     ecx, eax; unsigned int
0x180008152  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x180008157  mov     ebx, eax
  ... truncated ...
```
