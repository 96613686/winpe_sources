# WindowsPerformanceRecorder::CControlManager::DisableSystemBootRecording(WindowsPerformanceRecorder::CETWProperties::CEventSession const &)

- ea: `0x180060d14`
- end: `0x180060f85`
- name: `?DisableSystemBootRecording@CControlManager@WindowsPerformanceRecorder@@AEAAJAEBUCEventSession@CETWProperties@2@@Z`
- size: `625`
- prototype: `__int64 __fastcall(WindowsPerformanceRecorder::CControlManager *__hidden this, const struct WindowsPerformanceRecorder::CETWProperties::CEventSession *)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x18004ac00`
- `0x180060940`

## callees

- `0x180008270`
- `0x18000829c`
- `0x180008330`
- `0x18001c820`
- `0x18001e6b8`
- `0x180034afc`
- `0x180037100`
- `0x180038548`
- `0x18005cacc`
- `0x180060d14`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180060d66`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180060d66`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180060e1a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180060e2a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180060e3a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180060e4a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180060e5a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180060e6a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180060e7a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180060e8a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180060e9a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180060eaa`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180060eba`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180060eca`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180060eda`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180060e1a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180060e2a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180060e3a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180060e4a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180060e5a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180060e6a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180060e7a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180060e8a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180060e9a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180060eaa`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180060eba`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180060eca`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180060eda`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WindowsPerformanceRecorder::CControlManager::DisableSystemBootRecording(
        WindowsPerformanceRecorder::CControlManager *this,
        const struct WindowsPerformanceRecorder::CETWProperties::CEventSession *a2)
{
  const unsigned __int16 *SessionName; // rax
  int v5; // eax
  int v6; // ebx
  unsigned int v7; // eax
  HKEY v8; // rbx
  const unsigned __int16 *v9; // rax
  unsigned int v10; // ebx
  __int64 result; // rax
  ATL::CAtlException *v12; // [rsp+28h] [rbp-30h] BYREF
  HKEY hKey[5]; // [rsp+30h] [rbp-28h] BYREF
  unsigned int v14; // [rsp+70h] [rbp+18h]
  LPCWSTR lpSubKey; // [rsp+78h] [rbp+20h] BYREF

  memset(hKey, 0, 24);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&lpSubKey);
  SessionName = WindowsPerformanceRecorder::CETWProperties::CEventSession::get_SessionName(a2);
  v5 = _o__wcsicmp(SessionName, L"NT Kernel Logger");
  try
  {
    v6 = v5;
    WindowsPerformanceRecorder::CControlManager::GetAutoLoggerKey(this);
    v7 = ATL::CRegKey::Open((ATL::CRegKey *)hKey, HKEY_LOCAL_MACHINE, lpSubKey, 0x2001Fu);
    if ( v6 )
    {
      if ( !v7 )
      {
        v9 = WindowsPerformanceRecorder::CETWProperties::CEventSession::get_SessionName(a2);
        v7 = ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)hKey, v9);
        if ( !v7 )
          goto LABEL_9;
      }
    }
    else if ( !v7 )
    {
      v7 = ATL::CRegKey::SetDWORDValue((ATL::CRegKey *)hKey, L"Start", 0);
      if ( !v7 )
      {
        v8 = hKey[0];
        RegDeleteValueW(hKey[0], L"GUID");
        RegDeleteValueW(v8, L"FileName");
        RegDeleteValueW(v8, L"ClockType");
        RegDeleteValueW(v8, L"LogFileMode");
        RegDeleteValueW(v8, L"BufferSize");
        RegDeleteValueW(v8, L"MinimumBuffers");
        RegDeleteValueW(v8, L"MaximumBuffers");
        RegDeleteValueW(v8, L"MaxFileSize");
        RegDeleteValueW(v8, L"FileMax");
        RegDeleteValueW(v8, L"FileCounter");
        RegDeleteValueW(v8, L"EnableKernelFlags");
        RegDeleteValueW(v8, L"StackWalkingFilter");
        RegDeleteValueW(v8, L"StackCaching");
LABEL_9:
        WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&lpSubKey);
        ATL::CRegKey::Close((ATL::CRegKey *)hKey);
        return 0;
      }
    }
    v10 = ATL::AtlHresultFromWin32(v7);
    WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&lpSubKey);
    ATL::CRegKey::Close((ATL::CRegKey *)hKey);
    result = v10;
  }
  catch ( ATL::CAtlException *v12 )
  {
    v14 = *(_DWORD *)v12;
    WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&lpSubKey);
    ATL::CRegKey::Close((ATL::CRegKey *)hKey);
    return v14;
  }
  return result;
}

```

## disassembly

```asm
0x180060d14  mov     rax, rsp
0x180060d17  push    rdi
0x180060d18  sub     rsp, 50h
0x180060d1c  mov     qword ptr [rax-38h], 0FFFFFFFFFFFFFFFEh
0x180060d24  mov     [rax+8], rbx
0x180060d28  mov     [rax+10h], rsi
0x180060d2c  mov     rdi, rdx
0x180060d2f  mov     rsi, rcx
0x180060d32  mov     qword ptr [rax-28h], 0
0x180060d3a  mov     qword ptr [rax-20h], 0
0x180060d42  mov     qword ptr [rax-18h], 0
0x180060d4a  lea     rcx, [rax+20h]; void *
0x180060d4e  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180060d53  nop
0x180060d54  mov     rcx, rdi; this
0x180060d57  call    ?get_SessionName@CEventSession@CETWProperties@WindowsPerformanceRecorder@@QEBAPEBGXZ; WindowsPerformanceRecorder::CETWProperties::CEventSession::get_SessionName(void)
0x180060d5c  mov     rcx, rax
0x180060d5f  lea     rdx, aNtKernelLogger; "NT Kernel Logger"
0x180060d66  call    cs:__imp__o__wcsicmp
0x180060d6c  mov     ebx, eax
0x180060d6e  test    eax, eax
0x180060d70  setz    r8b
0x180060d74  lea     rdx, [rsp+58h+lpSubKey]
0x180060d79  mov     rcx, rsi; this
0x180060d7c  call    ?GetAutoLoggerKey@CControlManager@WindowsPerformanceRecorder@@AEBAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@_N@Z; WindowsPerformanceRecorder::CControlManager::GetAutoLoggerKey(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,bool)
0x180060d81  mov     r9d, 2001Fh; unsigned int
0x180060d87  mov     r8, [rsp+58h+lpSubKey]; lpSubKey
0x180060d8c  mov     rdx, 0FFFFFFFF80000002h; hKey
0x180060d93  lea     rcx, [rsp+58h+hKey]; this
0x180060d98  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180060d9d  test    ebx, ebx
0x180060d9f  jnz     loc_180060EE2
0x180060da5  test    eax, eax
0x180060da7  jz      short loc_180060DCE
0x180060da9  mov     ecx, eax; unsigned int
0x180060dab  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x180060db0  mov     ebx, eax
0x180060db2  lea     rcx, [rsp+58h+lpSubKey]; this
0x180060db7  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x180060dbc  nop
0x180060dbd  lea     rcx, [rsp+58h+hKey]; this
0x180060dc2  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180060dc7  mov     eax, ebx
0x180060dc9  jmp     loc_180060F75
0x180060dce  xor     r8d, r8d; unsigned int
0x180060dd1  lea     rdx, aStart; "Start"
0x180060dd8  lea     rcx, [rsp+58h+hKey]; this
0x180060ddd  call    ?SetDWORDValue@CRegKey@ATL@@QEAAJPEBGK@Z; ATL::CRegKey::SetDWORDValue(ushort const *,ulong)
0x180060de2  test    eax, eax
0x180060de4  jz      short loc_180060E0B
0x180060de6  mov     ecx, eax; unsigned int
0x180060de8  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x180060ded  mov     ebx, eax
0x180060def  lea     rcx, [rsp+58h+lpSubKey]; this
0x180060df4  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x180060df9  nop
0x180060dfa  lea     rcx, [rsp+58h+hKey]; this
0x180060dff  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180060e04  mov     eax, ebx
0x180060e06  jmp     loc_180060F75
0x180060e0b  lea     rdx, aGuid; "GUID"
0x180060e12  mov     rbx, [rsp+58h+hKey]
0x180060e17  mov     rcx, rbx; hKey
0x180060e1a  call    cs:__imp_RegDeleteValueW
0x180060e20  lea     rdx, aFilename_0; "FileName"
0x180060e27  mov     rcx, rbx; hKey
0x180060e2a  call    cs:__imp_RegDeleteValueW
0x180060e30  lea     rdx, aClocktype; "ClockType"
0x180060e37  mov     rcx, rbx; hKey
0x180060e3a  call    cs:__imp_RegDeleteValueW
0x180060e40  lea     rdx, aLogfilemode; "LogFileMode"
0x180060e47  mov     rcx, rbx; hKey
0x180060e4a  call    cs:__imp_RegDeleteValueW
0x180060e50  lea     rdx, aBuffersize_0; "BufferSize"
0x180060e57  mov     rcx, rbx; hKey
0x180060e5a  call    cs:__imp_RegDeleteValueW
0x180060e60  lea     rdx, aMinimumbuffers; "MinimumBuffers"
0x180060e67  mov     rcx, rbx; hKey
0x180060e6a  call    cs:__imp_RegDeleteValueW
0x180060e70  lea     rdx, aMaximumbuffers; "MaximumBuffers"
0x180060e77  mov     rcx, rbx; hKey
0x180060e7a  call    cs:__imp_RegDeleteValueW
0x180060e80  lea     rdx, aMaxfilesize; "MaxFileSize"
0x180060e87  mov     rcx, rbx; hKey
0x180060e8a  call    cs:__imp_RegDeleteValueW
0x180060e90  lea     rdx, aFilemax; "FileMax"
0x180060e97  mov     rcx, rbx; hKey
0x180060e9a  call    cs:__imp_RegDeleteValueW
0x180060ea0  lea     rdx, aFilecounter; "FileCounter"
0x180060ea7  mov     rcx, rbx; hKey
0x180060eaa  call    cs:__imp_RegDeleteValueW
0x180060eb0  lea     rdx, aEnablekernelfl; "EnableKernelFlags"
0x180060eb7  mov     rcx, rbx; hKey
0x180060eba  call    cs:__imp_RegDeleteValueW
0x180060ec0  lea     rdx, aStackwalkingfi; "StackWalkingFilter"
0x180060ec7  mov     rcx, rbx; hKey
0x180060eca  call    cs:__imp_RegDeleteValueW
0x180060ed0  lea     rdx, aStackcaching; "StackCaching"
0x180060ed7  mov     rcx, rbx; hKey
0x180060eda  call    cs:__imp_RegDeleteValueW
0x180060ee0  jmp     short loc_180060F43
0x180060ee2  test    eax, eax
0x180060ee4  jz      short loc_180060F08
0x180060ee6  mov     ecx, eax; unsigned int
0x180060ee8  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x180060eed  mov     ebx, eax
0x180060eef  lea     rcx, [rsp+58h+lpSubKey]; this
0x180060ef4  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x180060ef9  nop
0x180060efa  lea     rcx, [rsp+58h+hKey]; this
0x180060eff  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180060f04  mov     eax, ebx
0x180060f06  jmp     short loc_180060F75
0x180060f08  mov     rcx, rdi; this
0x180060f0b  call    ?get_SessionName@CEventSession@CETWProperties@WindowsPerformanceRecorder@@QEBAPEBGXZ; WindowsPerformanceRecorder::CETWProperties::CEventSession::get_SessionName(void)
0x180060f10  mov     rdx, rax; unsigned __int16 *
0x180060f13  lea     rcx, [rsp+58h+hKey]; this
0x180060f18  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x180060f1d  test    eax, eax
0x180060f1f  jz      short loc_180060F43
0x180060f21  mov     ecx, eax; unsigned int
0x180060f23  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x180060f28  mov     ebx, eax
0x180060f2a  lea     rcx, [rsp+58h+lpSubKey]; this
0x180060f2f  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x180060f34  nop
0x180060f35  lea     rcx, [rsp+58h+hKey]; this
0x180060f3a  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180060f3f  mov     eax, ebx
0x180060f41  jmp     short loc_180060F75
0x180060f43  lea     rcx, [rsp+58h+lpSubKey]; this
0x180060f48  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x180060f4d  nop
0x180060f4e  lea     rcx, [rsp+58h+hKey]; this
0x180060f53  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180060f58  xor     eax, eax
0x180060f5a  jmp     short loc_180060F75
0x180060f5c  lea     rcx, [rsp+58h+lpSubKey]; this
0x180060f61  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x180060f66  nop
0x180060f67  lea     rcx, [rsp+58h+hKey]; this
0x180060f6c  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180060f71  mov     eax, [rsp+58h+arg_10]
0x180060f75  mov     rbx, [rsp+58h+arg_0]
0x180060f7a  mov     rsi, [rsp+58h+arg_8]
0x180060f7f  add     rsp, 50h
0x180060f83  pop     rdi
0x180060f84  retn
```
