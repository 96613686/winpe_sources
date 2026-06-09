# WindowsPerformanceRecorder::CControlManager::EnableEventBootRecording(WindowsPerformanceRecorder::CETWProperties::CEventSession &)

- ea: `0x180060f8c`
- end: `0x180061776`
- name: `?EnableEventBootRecording@CControlManager@WindowsPerformanceRecorder@@AEAAJAEAUCEventSession@CETWProperties@2@@Z`
- size: `2026`
- prototype: `__int64 __fastcall(WindowsPerformanceRecorder::CControlManager *__hidden this, struct WindowsPerformanceRecorder::CETWProperties::CEventSession *)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004ac00`

## callees

- `0x180008270`
- `0x18000829c`
- `0x180008330`
- `0x1800102d8`
- `0x1800131a0`
- `0x180015e2c`
- `0x18001c820`
- `0x18001d190`
- `0x18001e6b8`
- `0x180030a54`
- `0x180034afc`
- `0x180037100`
- `0x180039ed8`
- `0x18003a0dc`
- `0x18003c92c`
- `0x18004ece0`
- `0x180060f8c`
- `0x180061f5c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180061226`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18006157b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180061590`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18006165d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180061226`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18006157b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180061590`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18006165d`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180060fff`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180060fff`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
HRESULT __fastcall WindowsPerformanceRecorder::CControlManager::EnableEventBootRecording(
        WindowsPerformanceRecorder::CControlManager *this,
        struct WindowsPerformanceRecorder::CETWProperties::CEventSession *a2)
{
  HRESULT result; // eax
  const unsigned __int16 *SessionName; // rax
  unsigned __int16 *v6; // r9
  unsigned int v7; // eax
  unsigned int v8; // r9d
  const unsigned __int16 *FileName; // r8
  unsigned int v10; // r9d
  unsigned int v11; // r8d
  __int64 v12; // r8
  __int64 v13; // rdx
  const void *v14; // r8
  unsigned int v15; // r9d
  __int64 v16; // rax
  unsigned __int16 *v17; // rcx
  int v18; // r10d
  int v19; // edx
  int v20; // ebx
  int v21; // ebx
  unsigned int v22; // [rsp+28h] [rbp-D0h]
  struct _SECURITY_ATTRIBUTES *v23; // [rsp+30h] [rbp-C8h]
  unsigned int *v24; // [rsp+38h] [rbp-C0h]
  LPCWSTR lpSubKey; // [rsp+70h] [rbp-88h] BYREF
  unsigned __int16 *v26; // [rsp+78h] [rbp-80h] BYREF
  HKEY hKey[3]; // [rsp+80h] [rbp-78h] BYREF
  _DWORD v28[2]; // [rsp+98h] [rbp-60h] BYREF
  __int64 v29; // [rsp+A0h] [rbp-58h]
  ATL::CAtlException *v30; // [rsp+A8h] [rbp-50h] BYREF
  GUID pguid; // [rsp+B0h] [rbp-48h] BYREF

  v29 = -2;
  pguid = 0;
  if ( *(_DWORD *)a2 == 3 )
  {
    pguid.Data1 = 573137579;
    *(_DWORD *)&pguid.Data2 = 1267229056;
    *(_DWORD *)pguid.Data4 = 1798579624;
    *(_DWORD *)&pguid.Data4[4] = 1252192885;
  }
  else
  {
    result = CoCreateGuid(&pguid);
    if ( result < 0 )
      return result;
  }
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v26);
  LODWORD(v24) = pguid.Data4[2];
  LODWORD(v23) = pguid.Data4[1];
  v22 = pguid.Data4[0];
  try
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
      &v26,
      L"{%08x-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x}");
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&lpSubKey);
    WindowsPerformanceRecorder::CControlManager::GetAutoLoggerKey(this);
    ATL::CSimpleStringT<unsigned short,0>::Append(&lpSubKey, L"\\");
    SessionName = WindowsPerformanceRecorder::CETWProperties::CEventSession::get_SessionName(a2);
    ATL::CSimpleStringT<unsigned short,0>::Append(&lpSubKey, SessionName);
    memset(hKey, 0, sizeof(hKey));
    v7 = ATL::CRegKey::Create((ATL::CRegKey *)hKey, HKEY_LOCAL_MACHINE, lpSubKey, v6, 0, v22, v23, v24);
    if ( v7 )
      goto LABEL_38;
    v7 = ATL::CRegKey::SetDWORDValue((ATL::CRegKey *)hKey, L"Start", 1u);
    if ( v7 )
      goto LABEL_38;
    v7 = ATL::CRegKey::SetStringValue((ATL::CRegKey *)hKey, L"GUID", v26, v8);
    if ( v7 )
      goto LABEL_38;
    if ( (*(_DWORD *)(*((_QWORD *)a2 + 1) + 64LL) & 0x400) != 0 )
    {
      RegDeleteValueW(hKey[0], L"FileName");
    }
    else
    {
      FileName = WindowsPerformanceRecorder::CETWProperties::CEventSession::get_FileName(a2);
      v7 = ATL::CRegKey::SetStringValue((ATL::CRegKey *)hKey, L"FileName", FileName, v10);
      if ( v7 )
      {
LABEL_38:
        v20 = ATL::AtlHresultFromWin32(v7);
        ATL::CRegKey::Close((ATL::CRegKey *)hKey);
        WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&lpSubKey);
        WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&v26);
        return v20;
      }
    }
    v7 = ATL::CRegKey::SetDWORDValue((ATL::CRegKey *)hKey, L"ClockType", *(_DWORD *)(*((_QWORD *)a2 + 1) + 40LL));
    if ( v7 )
      goto LABEL_38;
    v7 = ATL::CRegKey::SetDWORDValue((ATL::CRegKey *)hKey, L"LogFileMode", *(_DWORD *)(*((_QWORD *)a2 + 1) + 64LL));
    if ( v7 )
      goto LABEL_38;
    v7 = ATL::CRegKey::SetDWORDValue((ATL::CRegKey *)hKey, L"BufferSize", *(_DWORD *)(*((_QWORD *)a2 + 1) + 48LL));
    if ( v7 )
      goto LABEL_38;
    v7 = ATL::CRegKey::SetDWORDValue((ATL::CRegKey *)hKey, L"MinimumBuffers", *(_DWORD *)(*((_QWORD *)a2 + 1) + 52LL));
    if ( v7 )
      goto LABEL_38;
    v7 = ATL::CRegKey::SetDWORDValue((ATL::CRegKey *)hKey, L"MaximumBuffers", *(_DWORD *)(*((_QWORD *)a2 + 1) + 56LL));
    if ( v7 )
      goto LABEL_38;
    v7 = ATL::CRegKey::SetDWORDValue((ATL::CRegKey *)hKey, L"MaxFileSize", *(_DWORD *)(*((_QWORD *)a2 + 1) + 60LL));
    if ( v7 )
      goto LABEL_38;
    v7 = ATL::CRegKey::SetDWORDValue((ATL::CRegKey *)hKey, L"FlushTimer", *(_DWORD *)(*((_QWORD *)a2 + 1) + 68LL));
    if ( v7 )
      goto LABEL_38;
    v7 = ATL::CRegKey::SetDWORDValue((ATL::CRegKey *)hKey, L"FlushThreshold", *(_DWORD *)(*((_QWORD *)a2 + 1) + 76LL));
    if ( v7 )
      goto LABEL_38;
    v11 = *((_DWORD *)a2 + 50);
    if ( v11 )
    {
      v7 = ATL::CRegKey::SetDWORDValue((ATL::CRegKey *)hKey, L"FileMax", v11);
      if ( v7 )
        goto LABEL_38;
    }
    else
    {
      RegDeleteValueW(hKey[0], L"FileMax");
      RegDeleteValueW(hKey[0], L"FileCounter");
    }
    v12 = *((_QWORD *)a2 + 2);
    if ( v12 )
    {
      v7 = ATL::CRegKey::SetQWORDValue((ATL::CRegKey *)hKey, L"V2Options", *(_QWORD *)(v12 + 136));
      if ( v7 )
        goto LABEL_38;
    }
    if ( *((_DWORD *)a2 + 46) && *((_DWORD *)a2 + 47) && Performance::COSVersionInfo::IsWin8AndUp() )
    {
      v28[1] = *((_DWORD *)a2 + 46);
      v28[0] = *((_DWORD *)a2 + 47);
      ATL::CRegKey::SetBinaryValue((ATL::CRegKey *)hKey, L"StackCaching", v28, 8u);
    }
    else
    {
      RegDeleteValueW(hKey[0], L"StackCaching");
    }
    v13 = *((_QWORD *)a2 + 1);
    if ( *(_DWORD *)(v13 + 72) )
    {
      v14 = 0;
      v15 = 0;
      v16 = *(unsigned __int16 *)(v13 + 72);
      v17 = (unsigned __int16 *)(v16 + v13 + 4);
      v18 = *(unsigned __int16 *)(v16 + v13 + 2);
      v19 = 0;
      if ( v18 )
      {
        do
        {
          if ( v17[1] == 3 )
          {
            v14 = v17 + 2;
            v15 = 4 * *v17 - 4;
          }
          v17 += 2 * *v17;
          ++v19;
        }
        while ( v19 < v18 );
        if ( v14 )
        {
          if ( v15 )
          {
            v7 = ATL::CRegKey::SetBinaryValue((ATL::CRegKey *)hKey, L"StackWalkingFilter", v14, v15);
            if ( v7 )
              goto LABEL_38;
          }
        }
      }
    }
    v21 = WindowsPerformanceRecorder::CControlManager::EnableEventProviderBootRecording(
            this,
            a2,
            (const struct ATL::CRegKey *)hKey);
    ATL::CRegKey::Close((ATL::CRegKey *)hKey);
    WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&lpSubKey);
    WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&v26);
    if ( v21 >= 0 )
      result = 0;
    else
      result = v21;
  }
  catch ( ATL::CAtlException *v30 )
  {
    return *(_DWORD *)v30;
  }
  return result;
}

```

## disassembly

```asm
0x180060f8c  mov     r11, rsp
0x180060f8f  push    rsi
0x180060f90  push    rdi
0x180060f91  push    r12
0x180060f93  push    r13
0x180060f95  push    r15
0x180060f97  sub     rsp, 0D0h
0x180060f9e  mov     qword ptr [r11-58h], 0FFFFFFFFFFFFFFFEh
0x180060fa6  mov     [r11+18h], rbx
0x180060faa  mov     rax, cs:__security_cookie
0x180060fb1  xor     rax, rsp
0x180060fb4  mov     [rsp+0F8h+var_38], rax
0x180060fbc  mov     r15, rdx
0x180060fbf  mov     r12, rcx
0x180060fc2  xorps   xmm0, xmm0
0x180060fc5  movups  xmmword ptr [r11-48h], xmm0
0x180060fca  mov     r13d, 3
0x180060fd0  cmp     [rdx], r13d
0x180060fd3  jnz     short loc_180060FF7
0x180060fd5  mov     dword ptr [r11-48h], 222962ABh
0x180060fdd  mov     dword ptr [r11-44h], 4B886180h
0x180060fe5  mov     dword ptr [r11-40h], 6B3425A8h
0x180060fed  mov     dword ptr [r11-3Ch], 4AA2F275h
0x180060ff5  jmp     short loc_18006100D
0x180060ff7  lea     rcx, [rsp+0F8h+pguid]; pguid
0x180060fff  call    cs:__imp_CoCreateGuid
0x180061005  test    eax, eax
0x180061007  js      loc_18006174D
0x18006100d  lea     rcx, [rsp+0F8h+var_80]; void *
0x180061012  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180061017  nop
0x180061018  movzx   eax, [rsp+0F8h+pguid.Data4+7]
0x180061020  movzx   ecx, [rsp+0F8h+pguid.Data4+6]
0x180061028  movzx   edx, [rsp+0F8h+pguid.Data4+5]
0x180061030  movzx   r8d, [rsp+0F8h+pguid.Data4+4]
0x180061039  movzx   r10d, [rsp+0F8h+pguid.Data4+3]
0x180061042  movzx   r11d, [rsp+0F8h+pguid.Data4+2]
0x18006104b  movzx   ebx, [rsp+0F8h+pguid.Data4+1]
0x180061053  movzx   edi, [rsp+0F8h+pguid.Data4]
0x18006105b  movzx   esi, [rsp+0F8h+pguid.Data3]
0x180061063  movzx   r9d, [rsp+0F8h+pguid.Data2]
0x18006106c  mov     [rsp+0F8h+var_98], eax
0x180061070  mov     [rsp+0F8h+var_A0], ecx
0x180061074  mov     [rsp+0F8h+var_A8], edx
0x180061078  mov     [rsp+0F8h+var_B0], r8d
0x18006107d  mov     [rsp+0F8h+var_B8], r10d
0x180061082  mov     dword ptr [rsp+0F8h+var_C0], r11d; unsigned int *
0x180061087  mov     dword ptr [rsp+0F8h+var_C8], ebx; struct _SECURITY_ATTRIBUTES *
0x18006108b  mov     [rsp+0F8h+var_D0], edi; unsigned int
0x18006108f  mov     [rsp+0F8h+var_D8], esi
0x180061093  mov     r8d, [rsp+0F8h+pguid.Data1]
0x18006109b  lea     rdx, a08x04x04x02x02; "{%08x-%04x-%04x-%02x%02x-%02x%02x%02x%0"...
0x1800610a2  lea     rcx, [rsp+0F8h+var_80]
0x1800610a7  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x1800610ac  lea     rcx, [rsp+0F8h+lpSubKey]; void *
0x1800610b1  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800610b6  nop
0x1800610b7  xor     r8d, r8d
0x1800610ba  lea     rdx, [rsp+0F8h+lpSubKey]
0x1800610bf  mov     rcx, r12; this
0x1800610c2  call    ?GetAutoLoggerKey@CControlManager@WindowsPerformanceRecorder@@AEBAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@_N@Z; WindowsPerformanceRecorder::CControlManager::GetAutoLoggerKey(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,bool)
0x1800610c7  lea     rdx, SubBlock; "\\"
0x1800610ce  lea     rcx, [rsp+0F8h+lpSubKey]
0x1800610d3  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *)
0x1800610d8  mov     rcx, r15; this
0x1800610db  call    ?get_SessionName@CEventSession@CETWProperties@WindowsPerformanceRecorder@@QEBAPEBGXZ; WindowsPerformanceRecorder::CETWProperties::CEventSession::get_SessionName(void)
0x1800610e0  mov     rdx, rax
0x1800610e3  lea     rcx, [rsp+0F8h+lpSubKey]
0x1800610e8  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *)
0x1800610ed  mov     [rsp+0F8h+hKey], 0
0x1800610f9  mov     [rsp+0F8h+var_70], 0
0x180061105  mov     [rsp+0F8h+var_68], 0
0x180061111  mov     [rsp+0F8h+var_D8], 0; unsigned int
0x180061119  mov     r8, [rsp+0F8h+lpSubKey]; lpSubKey
0x18006111e  mov     rdx, 0FFFFFFFF80000002h; hKey
0x180061125  lea     rcx, [rsp+0F8h+hKey]; this
0x18006112d  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x180061132  test    eax, eax
0x180061134  jz      short loc_180061169
0x180061136  mov     ecx, eax; unsigned int
0x180061138  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x18006113d  mov     ebx, eax
0x18006113f  lea     rcx, [rsp+0F8h+hKey]; this
0x180061147  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18006114c  nop
0x18006114d  lea     rcx, [rsp+0F8h+lpSubKey]; this
0x180061152  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x180061157  nop
0x180061158  lea     rcx, [rsp+0F8h+var_80]; this
0x18006115d  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x180061162  mov     eax, ebx
0x180061164  jmp     loc_18006174D
0x180061169  mov     r8d, 1; unsigned int
0x18006116f  lea     rdx, aStart; "Start"
0x180061176  lea     rcx, [rsp+0F8h+hKey]; this
0x18006117e  call    ?SetDWORDValue@CRegKey@ATL@@QEAAJPEBGK@Z; ATL::CRegKey::SetDWORDValue(ushort const *,ulong)
0x180061183  test    eax, eax
0x180061185  jz      short loc_1800611BA
0x180061187  mov     ecx, eax; unsigned int
0x180061189  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x18006118e  mov     ebx, eax
0x180061190  lea     rcx, [rsp+0F8h+hKey]; this
0x180061198  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18006119d  nop
0x18006119e  lea     rcx, [rsp+0F8h+lpSubKey]; this
0x1800611a3  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x1800611a8  nop
0x1800611a9  lea     rcx, [rsp+0F8h+var_80]; this
0x1800611ae  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x1800611b3  mov     eax, ebx
0x1800611b5  jmp     loc_18006174D
0x1800611ba  mov     r8, [rsp+0F8h+var_80]; unsigned __int16 *
0x1800611bf  lea     rdx, aGuid; "GUID"
0x1800611c6  lea     rcx, [rsp+0F8h+hKey]; this
0x1800611ce  call    ?SetStringValue@CRegKey@ATL@@QEAAJPEBG0K@Z; ATL::CRegKey::SetStringValue(ushort const *,ushort const *,ulong)
0x1800611d3  test    eax, eax
0x1800611d5  jz      short loc_18006120A
0x1800611d7  mov     ecx, eax; unsigned int
0x1800611d9  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x1800611de  mov     ebx, eax
0x1800611e0  lea     rcx, [rsp+0F8h+hKey]; this
0x1800611e8  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800611ed  nop
0x1800611ee  lea     rcx, [rsp+0F8h+lpSubKey]; this
0x1800611f3  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x1800611f8  nop
0x1800611f9  lea     rcx, [rsp+0F8h+var_80]; this
0x1800611fe  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x180061203  mov     eax, ebx
0x180061205  jmp     loc_18006174D
0x18006120a  mov     rax, [r15+8]
0x18006120e  test    dword ptr [rax+40h], 400h
0x180061215  jz      short loc_18006122E
0x180061217  lea     rdx, aFilename_0; "FileName"
0x18006121e  mov     rcx, [rsp+0F8h+hKey]; hKey
0x180061226  call    cs:__imp_RegDeleteValueW
0x18006122c  jmp     short loc_180061284
0x18006122e  mov     rcx, r15; this
0x180061231  call    ?get_FileName@CEventSession@CETWProperties@WindowsPerformanceRecorder@@QEBAPEBGXZ; WindowsPerformanceRecorder::CETWProperties::CEventSession::get_FileName(void)
0x180061236  mov     r8, rax; unsigned __int16 *
0x180061239  lea     rdx, aFilename_0; "FileName"
0x180061240  lea     rcx, [rsp+0F8h+hKey]; this
0x180061248  call    ?SetStringValue@CRegKey@ATL@@QEAAJPEBG0K@Z; ATL::CRegKey::SetStringValue(ushort const *,ushort const *,ulong)
0x18006124d  test    eax, eax
0x18006124f  jz      short loc_180061284
0x180061251  mov     ecx, eax; unsigned int
0x180061253  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x180061258  mov     ebx, eax
0x18006125a  lea     rcx, [rsp+0F8h+hKey]; this
0x180061262  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180061267  nop
0x180061268  lea     rcx, [rsp+0F8h+lpSubKey]; this
0x18006126d  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x180061272  nop
0x180061273  lea     rcx, [rsp+0F8h+var_80]; this
0x180061278  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x18006127d  mov     eax, ebx
0x18006127f  jmp     loc_18006174D
0x180061284  mov     r8, [r15+8]
0x180061288  mov     r8d, [r8+28h]; unsigned int
0x18006128c  lea     rdx, aClocktype; "ClockType"
0x180061293  lea     rcx, [rsp+0F8h+hKey]; this
0x18006129b  call    ?SetDWORDValue@CRegKey@ATL@@QEAAJPEBGK@Z; ATL::CRegKey::SetDWORDValue(ushort const *,ulong)
0x1800612a0  test    eax, eax
0x1800612a2  jz      short loc_1800612D7
0x1800612a4  mov     ecx, eax; unsigned int
0x1800612a6  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x1800612ab  mov     ebx, eax
0x1800612ad  lea     rcx, [rsp+0F8h+hKey]; this
0x1800612b5  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800612ba  nop
0x1800612bb  lea     rcx, [rsp+0F8h+lpSubKey]; this
0x1800612c0  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x1800612c5  nop
0x1800612c6  lea     rcx, [rsp+0F8h+var_80]; this
0x1800612cb  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x1800612d0  mov     eax, ebx
0x1800612d2  jmp     loc_18006174D
0x1800612d7  mov     r8, [r15+8]
0x1800612db  mov     r8d, [r8+40h]; unsigned int
0x1800612df  lea     rdx, aLogfilemode; "LogFileMode"
0x1800612e6  lea     rcx, [rsp+0F8h+hKey]; this
0x1800612ee  call    ?SetDWORDValue@CRegKey@ATL@@QEAAJPEBGK@Z; ATL::CRegKey::SetDWORDValue(ushort const *,ulong)
0x1800612f3  test    eax, eax
0x1800612f5  jz      short loc_18006132A
0x1800612f7  mov     ecx, eax; unsigned int
0x1800612f9  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x1800612fe  mov     ebx, eax
0x180061300  lea     rcx, [rsp+0F8h+hKey]; this
0x180061308  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18006130d  nop
0x18006130e  lea     rcx, [rsp+0F8h+lpSubKey]; this
0x180061313  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x180061318  nop
0x180061319  lea     rcx, [rsp+0F8h+var_80]; this
0x18006131e  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x180061323  mov     eax, ebx
0x180061325  jmp     loc_18006174D
0x18006132a  mov     r8, [r15+8]
0x18006132e  mov     r8d, [r8+30h]; unsigned int
0x180061332  lea     rdx, aBuffersize_0; "BufferSize"
0x180061339  lea     rcx, [rsp+0F8h+hKey]; this
0x180061341  call    ?SetDWORDValue@CRegKey@ATL@@QEAAJPEBGK@Z; ATL::CRegKey::SetDWORDValue(ushort const *,ulong)
0x180061346  test    eax, eax
0x180061348  jz      short loc_18006137D
0x18006134a  mov     ecx, eax; unsigned int
0x18006134c  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x180061351  mov     ebx, eax
0x180061353  lea     rcx, [rsp+0F8h+hKey]; this
0x18006135b  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180061360  nop
0x180061361  lea     rcx, [rsp+0F8h+lpSubKey]; this
0x180061366  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x18006136b  nop
0x18006136c  lea     rcx, [rsp+0F8h+var_80]; this
0x180061371  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x180061376  mov     eax, ebx
0x180061378  jmp     loc_18006174D
0x18006137d  mov     r8, [r15+8]
0x180061381  mov     r8d, [r8+34h]; unsigned int
0x180061385  lea     rdx, aMinimumbuffers; "MinimumBuffers"
0x18006138c  lea     rcx, [rsp+0F8h+hKey]; this
0x180061394  call    ?SetDWORDValue@CRegKey@ATL@@QEAAJPEBGK@Z; ATL::CRegKey::SetDWORDValue(ushort const *,ulong)
0x180061399  test    eax, eax
0x18006139b  jz      short loc_1800613D0
0x18006139d  mov     ecx, eax; unsigned int
0x18006139f  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x1800613a4  mov     ebx, eax
0x1800613a6  lea     rcx, [rsp+0F8h+hKey]; this
0x1800613ae  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800613b3  nop
0x1800613b4  lea     rcx, [rsp+0F8h+lpSubKey]; this
0x1800613b9  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x1800613be  nop
0x1800613bf  lea     rcx, [rsp+0F8h+var_80]; this
0x1800613c4  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x1800613c9  mov     eax, ebx
0x1800613cb  jmp     loc_18006174D
0x1800613d0  mov     r8, [r15+8]
0x1800613d4  mov     r8d, [r8+38h]; unsigned int
0x1800613d8  lea     rdx, aMaximumbuffers; "MaximumBuffers"
0x1800613df  lea     rcx, [rsp+0F8h+hKey]; this
0x1800613e7  call    ?SetDWORDValue@CRegKey@ATL@@QEAAJPEBGK@Z; ATL::CRegKey::SetDWORDValue(ushort const *,ulong)
0x1800613ec  test    eax, eax
0x1800613ee  jz      short loc_180061423
0x1800613f0  mov     ecx, eax; unsigned int
0x1800613f2  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x1800613f7  mov     ebx, eax
0x1800613f9  lea     rcx, [rsp+0F8h+hKey]; this
0x180061401  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180061406  nop
0x180061407  lea     rcx, [rsp+0F8h+lpSubKey]; this
0x18006140c  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x180061411  nop
0x180061412  lea     rcx, [rsp+0F8h+var_80]; this
0x180061417  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x18006141c  mov     eax, ebx
0x18006141e  jmp     loc_18006174D
0x180061423  mov     r8, [r15+8]
0x180061427  mov     r8d, [r8+3Ch]; unsigned int
0x18006142b  lea     rdx, aMaxfilesize; "MaxFileSize"
0x180061432  lea     rcx, [rsp+0F8h+hKey]; this
0x18006143a  call    ?SetDWORDValue@CRegKey@ATL@@QEAAJPEBGK@Z; ATL::CRegKey::SetDWORDValue(ushort const *,ulong)
0x18006143f  test    eax, eax
0x180061441  jz      short loc_180061476
0x180061443  mov     ecx, eax; unsigned int
0x180061445  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x18006144a  mov     ebx, eax
0x18006144c  lea     rcx, [rsp+0F8h+hKey]; this
0x180061454  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180061459  nop
0x18006145a  lea     rcx, [rsp+0F8h+lpSubKey]; this
0x18006145f  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x180061464  nop
0x180061465  lea     rcx, [rsp+0F8h+var_80]; this
0x18006146a  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x18006146f  mov     eax, ebx
0x180061471  jmp     loc_18006174D
0x180061476  mov     r8, [r15+8]
0x18006147a  mov     r8d, [r8+44h]; unsigned int
0x18006147e  lea     rdx, aFlushtimer; "FlushTimer"
0x180061485  lea     rcx, [rsp+0F8h+hKey]; this
0x18006148d  call    ?SetDWORDValue@CRegKey@ATL@@QEAAJPEBGK@Z; ATL::CRegKey::SetDWORDValue(ushort const *,ulong)
0x180061492  test    eax, eax
0x180061494  jz      short loc_1800614C9
0x180061496  mov     ecx, eax; unsigned int
0x180061498  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x18006149d  mov     ebx, eax
0x18006149f  lea     rcx, [rsp+0F8h+hKey]; this
0x1800614a7  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800614ac  nop
0x1800614ad  lea     rcx, [rsp+0F8h+lpSubKey]; this
0x1800614b2  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x1800614b7  nop
0x1800614b8  lea     rcx, [rsp+0F8h+var_80]; this
0x1800614bd  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x1800614c2  mov     eax, ebx
0x1800614c4  jmp     loc_18006174D
0x1800614c9  mov     r8, [r15+8]
0x1800614cd  mov     r8d, [r8+4Ch]; unsigned int
  ... truncated ...
```
