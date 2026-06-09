# WindowsPerformanceRecorder::CControlManager::EnableSystemBootRecording(WindowsPerformanceRecorder::CETWProperties::CEventSession &)

- ea: `0x18003415c`
- end: `0x180034af4`
- name: `?EnableSystemBootRecording@CControlManager@WindowsPerformanceRecorder@@AEAAJAEAUCEventSession@CETWProperties@2@@Z`
- size: `2456`
- prototype: `__int64 __fastcall(WindowsPerformanceRecorder::CControlManager *__hidden this, struct WindowsPerformanceRecorder::CETWProperties::CEventSession *)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004ac00`

## callees

- `0x180008270`
- `0x18000829c`
- `0x180008330`
- `0x18000eeb0`
- `0x1800102d8`
- `0x1800131a0`
- `0x180015e2c`
- `0x18001c820`
- `0x18001d190`
- `0x18001e6b8`
- `0x180030a54`
- `0x18003415c`
- `0x180034afc`
- `0x180037100`
- `0x18003a0dc`
- `0x18003c92c`
- `0x18004ece0`
- `0x180061f5c`
- `0x18008c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800341c3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800341e3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800341c3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800341e3`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180034292`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180034292`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800344c3`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18003482f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180034844`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800348b4`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800344c3`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18003482f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180034844`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800348b4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180034475`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180034544`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800345a4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180034604`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180034664`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800346c4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180034475`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180034544`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800345a4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180034604`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180034664`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800346c4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800346ee`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800346ee`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180034314`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180034314`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall WindowsPerformanceRecorder::CControlManager::EnableSystemBootRecording(
        WindowsPerformanceRecorder::CControlManager *this,
        struct WindowsPerformanceRecorder::CETWProperties::CEventSession *a2)
{
  WindowsPerformanceRecorder::CControlManager *v3; // rsi
  const unsigned __int16 *SessionName; // rax
  int v5; // r12d
  const unsigned __int16 *v6; // rax
  int v7; // r13d
  __int64 v8; // rax
  const unsigned __int16 *v9; // rax
  LPCWSTR v10; // rbx
  LSTATUS Key; // eax
  HKEY v12; // rcx
  HRESULT Guid; // edi
  __int64 result; // rax
  unsigned int v15; // r9d
  unsigned int v16; // eax
  unsigned int v17; // ebx
  const unsigned __int16 *FileName; // rax
  unsigned int v19; // r9d
  LSTATUS v20; // eax
  unsigned int v21; // edi
  unsigned int v22; // r8d
  __int64 v23; // r8
  __int64 v24; // rdx
  const void *v25; // rbx
  unsigned int v26; // edi
  __int64 v27; // r9
  unsigned __int16 *v28; // rcx
  int v29; // r8d
  unsigned int v30; // ebx
  int v31; // ebx
  DWORD dwOptions[2]; // [rsp+20h] [rbp-E8h]
  __int64 samDesired; // [rsp+28h] [rbp-E0h]
  LPSECURITY_ATTRIBUTES lpSecurityAttributes; // [rsp+30h] [rbp-D8h]
  PHKEY phkResult; // [rsp+38h] [rbp-D0h]
  LPDWORD lpdwDisposition; // [rsp+40h] [rbp-C8h]
  LPCWSTR lpSubKey; // [rsp+70h] [rbp-98h] BYREF
  DWORD dwDisposition[2]; // [rsp+78h] [rbp-90h] BYREF
  HKEY hKey[3]; // [rsp+80h] [rbp-88h] BYREF
  WindowsPerformanceRecorder::CControlManager *v40; // [rsp+98h] [rbp-70h]
  __int64 v41; // [rsp+A0h] [rbp-68h]
  DWORD *v42; // [rsp+A8h] [rbp-60h] BYREF
  HKEY v43[2]; // [rsp+B0h] [rbp-58h] BYREF
  __int128 v44; // [rsp+C0h] [rbp-48h]

  v41 = -2;
  v3 = this;
  v40 = this;
  memset(hKey, 0, sizeof(hKey));
  SessionName = WindowsPerformanceRecorder::CETWProperties::CEventSession::get_SessionName(a2);
  v5 = _o__wcsicmp(SessionName, L"NT Kernel Logger");
  v6 = WindowsPerformanceRecorder::CETWProperties::CEventSession::get_SessionName(a2);
  v7 = _o__wcsicmp(v6, L"Circular Kernel Context Logger");
  v8 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr);
  try
  {
    lpSubKey = (LPCWSTR)(v8 + 24);
    WindowsPerformanceRecorder::CControlManager::GetAutoLoggerKey(v3);
    if ( v5 )
    {
      ATL::CSimpleStringT<unsigned short,0>::Append(&lpSubKey, L"\\");
      v9 = WindowsPerformanceRecorder::CETWProperties::CEventSession::get_SessionName(a2);
      ATL::CSimpleStringT<unsigned short,0>::Append(&lpSubKey, v9);
    }
    dwDisposition[0] = 0;
    v43[0] = 0;
    v10 = lpSubKey;
    Key = RegCreateKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0, 0, 0x2001Fu, 0, v43, dwDisposition);
    if ( Key )
      goto LABEL_51;
    Key = ATL::CRegKey::Close((ATL::CRegKey *)hKey);
    v12 = v43[0];
    hKey[0] = v43[0];
    if ( Key )
      goto LABEL_51;
    if ( v5 )
    {
      *(_OWORD *)v43 = 0;
      if ( v7 )
      {
        Guid = CoCreateGuid((GUID *)v43);
        if ( Guid < 0 )
        {
          WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&lpSubKey);
          ATL::CRegKey::Close((ATL::CRegKey *)hKey);
          return (unsigned int)Guid;
        }
      }
      else
      {
        v43[0] = (HKEY)0x42A4ED1F54DEA73ALL;
        v43[1] = (HKEY)0x74F156D0633E71AFLL;
      }
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(dwDisposition);
      LODWORD(lpdwDisposition) = BYTE3(v43[1]);
      LODWORD(phkResult) = BYTE2(v43[1]);
      LODWORD(lpSecurityAttributes) = BYTE1(v43[1]);
      LODWORD(samDesired) = LOBYTE(v43[1]);
      dwOptions[0] = HIWORD(v43[0]);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
        dwDisposition,
        L"{%08x-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x}",
        LODWORD(v43[0]),
        WORD2(v43[0]),
        *(_QWORD *)dwOptions,
        samDesired,
        lpSecurityAttributes,
        phkResult,
        lpdwDisposition,
        BYTE4(v43[1]),
        BYTE5(v43[1]),
        BYTE6(v43[1]),
        HIBYTE(v43[1]));
      v16 = ATL::CRegKey::SetStringValue((ATL::CRegKey *)hKey, L"GUID", *(const unsigned __int16 **)dwDisposition, v15);
      if ( v16 )
      {
        v17 = ATL::AtlHresultFromWin32(v16);
        WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)dwDisposition);
        WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&lpSubKey);
        ATL::CRegKey::Close((ATL::CRegKey *)hKey);
        return v17;
      }
      WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)dwDisposition);
      v12 = hKey[0];
      v3 = v40;
    }
    dwDisposition[0] = 1;
    Key = RegSetValueExW(v12, L"Start", 0, 4u, (const BYTE *)dwDisposition, 4u);
    if ( Key )
      goto LABEL_51;
    if ( (*(_DWORD *)(*((_QWORD *)a2 + 1) + 64LL) & 0x400) != 0 )
    {
      RegDeleteValueW(hKey[0], L"FileName");
    }
    else
    {
      FileName = WindowsPerformanceRecorder::CETWProperties::CEventSession::get_FileName(a2);
      Key = ATL::CRegKey::SetStringValue((ATL::CRegKey *)hKey, L"FileName", FileName, v19);
      if ( Key )
        goto LABEL_51;
    }
    dwDisposition[0] = *(_DWORD *)(*((_QWORD *)a2 + 1) + 40LL);
    Key = RegSetValueExW(hKey[0], L"ClockType", 0, 4u, (const BYTE *)dwDisposition, 4u);
    if ( !Key )
    {
      dwDisposition[0] = *(_DWORD *)(*((_QWORD *)a2 + 1) + 64LL);
      Key = RegSetValueExW(hKey[0], L"LogFileMode", 0, 4u, (const BYTE *)dwDisposition, 4u);
      if ( !Key )
      {
        dwDisposition[0] = *(_DWORD *)(*((_QWORD *)a2 + 1) + 48LL);
        Key = RegSetValueExW(hKey[0], L"BufferSize", 0, 4u, (const BYTE *)dwDisposition, 4u);
        if ( !Key )
        {
          dwDisposition[0] = *(_DWORD *)(*((_QWORD *)a2 + 1) + 52LL);
          Key = RegSetValueExW(hKey[0], L"MinimumBuffers", 0, 4u, (const BYTE *)dwDisposition, 4u);
          if ( !Key )
          {
            dwDisposition[0] = *(_DWORD *)(*((_QWORD *)a2 + 1) + 56LL);
            v20 = RegSetValueExW(hKey[0], L"MaximumBuffers", 0, 4u, (const BYTE *)dwDisposition, 4u);
            if ( v20 )
            {
              v21 = ATL::AtlHresultFromWin32(v20);
              ATL::CStringData::Release((ATL::CStringData *)(v10 - 12));
              if ( hKey[0] )
              {
                RegCloseKey(hKey[0]);
                hKey[0] = 0;
              }
              return v21;
            }
            Key = ATL::CRegKey::SetDWORDValue(
                    (ATL::CRegKey *)hKey,
                    L"MaxFileSize",
                    *(_DWORD *)(*((_QWORD *)a2 + 1) + 60LL));
            if ( !Key )
            {
              Key = ATL::CRegKey::SetDWORDValue(
                      (ATL::CRegKey *)hKey,
                      L"FlushTimer",
                      *(_DWORD *)(*((_QWORD *)a2 + 1) + 68LL));
              if ( !Key )
              {
                Key = ATL::CRegKey::SetDWORDValue(
                        (ATL::CRegKey *)hKey,
                        L"FlushThreshold",
                        *(_DWORD *)(*((_QWORD *)a2 + 1) + 76LL));
                if ( !Key )
                {
                  v22 = *((_DWORD *)a2 + 50);
                  if ( v22 )
                  {
                    Key = ATL::CRegKey::SetDWORDValue((ATL::CRegKey *)hKey, L"FileMax", v22);
                    if ( Key )
                      goto LABEL_51;
                  }
                  else
                  {
                    RegDeleteValueW(hKey[0], L"FileMax");
                    RegDeleteValueW(hKey[0], L"FileCounter");
                  }
                  if ( *((_DWORD *)a2 + 46) && *((_DWORD *)a2 + 47) && Performance::COSVersionInfo::IsWin8AndUp() )
                  {
                    HIDWORD(v43[0]) = *((_DWORD *)a2 + 46);
                    LODWORD(v43[0]) = *((_DWORD *)a2 + 47);
                    ATL::CRegKey::SetBinaryValue((ATL::CRegKey *)hKey, L"StackCaching", v43, 8u);
                  }
                  else
                  {
                    RegDeleteValueW(hKey[0], L"StackCaching");
                  }
                  v23 = *((_QWORD *)a2 + 2);
                  if ( !v23
                    || (Key = ATL::CRegKey::SetQWORDValue((ATL::CRegKey *)hKey, L"V2Options", *(_QWORD *)(v23 + 136))) == 0 )
                  {
                    v24 = *((_QWORD *)a2 + 1);
                    if ( !*(_DWORD *)(v24 + 72) )
                      goto LABEL_64;
                    *(_OWORD *)v43 = 0;
                    v44 = 0;
                    v25 = 0;
                    v26 = 0;
                    v27 = *(unsigned __int16 *)(v24 + 72);
                    v28 = (unsigned __int16 *)(v27 + v24 + 4);
                    v29 = 0;
                    if ( *(_WORD *)(v27 + v24 + 2) )
                    {
                      do
                      {
                        if ( v28[1] == 1 )
                        {
                          *(_OWORD *)v43 = *(_OWORD *)(v28 + 2);
                          v44 = *(_OWORD *)(v28 + 10);
                        }
                        else if ( v28[1] == 3 )
                        {
                          v25 = v28 + 2;
                          v26 = 4 * *v28 - 4;
                        }
                        v28 += 2 * *v28;
                        ++v29;
                      }
                      while ( v29 < *(unsigned __int16 *)(v27 + v24 + 2) );
                    }
                    Key = ATL::CRegKey::SetBinaryValue((ATL::CRegKey *)hKey, L"EnableKernelFlags", v43, 0x20u);
                    if ( !Key
                      && (!v25
                       || !v26
                       || (Key = ATL::CRegKey::SetBinaryValue((ATL::CRegKey *)hKey, L"StackWalkingFilter", v25, v26)) == 0) )
                    {
LABEL_64:
                      if ( v5
                        && v7
                        && (v31 = WindowsPerformanceRecorder::CControlManager::EnableEventProviderBootRecording(
                                    v3,
                                    a2,
                                    (const struct ATL::CRegKey *)hKey),
                            v31 < 0) )
                      {
                        WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&lpSubKey);
                        ATL::CRegKey::Close((ATL::CRegKey *)hKey);
                        return (unsigned int)v31;
                      }
                      else
                      {
                        WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&lpSubKey);
                        ATL::CRegKey::Close((ATL::CRegKey *)hKey);
                        return 0;
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
LABEL_51:
    v30 = ATL::AtlHresultFromWin32(Key);
    WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&lpSubKey);
    ATL::CRegKey::Close((ATL::CRegKey *)hKey);
    result = v30;
  }
  catch ( ATL::CAtlException *v42 )
  {
    dwDisposition[0] = *v42;
    ATL::CRegKey::Close((ATL::CRegKey *)hKey);
    return dwDisposition[0];
  }
  return result;
}

```

## disassembly

```asm
0x18003415c  mov     r11, rsp
0x18003415f  push    rdi
0x180034160  push    r12
0x180034162  push    r13
0x180034164  push    r14
0x180034166  push    r15
0x180034168  sub     rsp, 0E0h
0x18003416f  mov     qword ptr [r11-68h], 0FFFFFFFFFFFFFFFEh
0x180034177  mov     [r11+18h], rbx
0x18003417b  mov     [r11+20h], rsi
0x18003417f  mov     rax, cs:__security_cookie
0x180034186  xor     rax, rsp
0x180034189  mov     [rsp+108h+var_38], rax
0x180034191  mov     r15, rdx
0x180034194  mov     rsi, rcx
0x180034197  mov     [rsp+108h+var_70], rcx
0x18003419f  xor     r14d, r14d
0x1800341a2  mov     [r11-88h], r14
0x1800341a9  mov     [r11-80h], r14
0x1800341ad  mov     [r11-78h], r14
0x1800341b1  mov     rcx, rdx; this
0x1800341b4  call    ?get_SessionName@CEventSession@CETWProperties@WindowsPerformanceRecorder@@QEBAPEBGXZ; WindowsPerformanceRecorder::CETWProperties::CEventSession::get_SessionName(void)
0x1800341b9  mov     rcx, rax
0x1800341bc  lea     rdx, aNtKernelLogger; "NT Kernel Logger"
0x1800341c3  call    cs:__imp__o__wcsicmp
0x1800341c9  mov     r12d, eax
0x1800341cc  test    eax, eax
0x1800341ce  setz    bl
0x1800341d1  mov     rcx, r15; this
0x1800341d4  call    ?get_SessionName@CEventSession@CETWProperties@WindowsPerformanceRecorder@@QEBAPEBGXZ; WindowsPerformanceRecorder::CETWProperties::CEventSession::get_SessionName(void)
0x1800341d9  mov     rcx, rax
0x1800341dc  lea     rdx, aCircularKernel; "Circular Kernel Context Logger"
0x1800341e3  call    cs:__imp__o__wcsicmp
0x1800341e9  mov     r13d, eax
0x1800341ec  mov     rcx, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1800341f3  mov     rax, [rcx+18h]
0x1800341f7  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1800341fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034203  add     rax, 18h
0x180034207  mov     [rsp+108h+lpSubKey], rax
0x18003420c  mov     r8b, bl
0x18003420f  lea     rdx, [rsp+108h+lpSubKey]
0x180034214  mov     rcx, rsi; this
0x180034217  call    ?GetAutoLoggerKey@CControlManager@WindowsPerformanceRecorder@@AEBAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@_N@Z; WindowsPerformanceRecorder::CControlManager::GetAutoLoggerKey(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,bool)
0x18003421c  test    r12d, r12d
0x18003421f  jz      short loc_180034247
0x180034221  lea     rdx, SubBlock; "\\"
0x180034228  lea     rcx, [rsp+108h+lpSubKey]
0x18003422d  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *)
0x180034232  mov     rcx, r15; this
0x180034235  call    ?get_SessionName@CEventSession@CETWProperties@WindowsPerformanceRecorder@@QEBAPEBGXZ; WindowsPerformanceRecorder::CETWProperties::CEventSession::get_SessionName(void)
0x18003423a  mov     rdx, rax
0x18003423d  lea     rcx, [rsp+108h+lpSubKey]
0x180034242  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *)
0x180034247  mov     [rsp+108h+dwDisposition], r14d
0x18003424c  mov     [rsp+108h+var_58], r14
0x180034254  lea     rax, [rsp+108h+dwDisposition]
0x180034259  mov     [rsp+108h+lpdwDisposition], rax; lpdwDisposition
0x18003425e  lea     rax, [rsp+108h+var_58]
0x180034266  mov     [rsp+108h+phkResult], rax; phkResult
0x18003426b  mov     [rsp+108h+lpSecurityAttributes], r14; lpSecurityAttributes
0x180034270  mov     dword ptr [rsp+108h+samDesired], 2001Fh; samDesired
0x180034278  mov     [rsp+108h+dwOptions], r14d; dwOptions
0x18003427d  xor     r9d, r9d; lpClass
0x180034280  xor     r8d, r8d; Reserved
0x180034283  mov     rbx, [rsp+108h+lpSubKey]
0x180034288  mov     rdx, rbx; lpSubKey
0x18003428b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180034292  call    cs:__imp_RegCreateKeyExW
0x180034298  test    eax, eax
0x18003429a  jnz     loc_180034A91
0x1800342a0  lea     rcx, [rsp+108h+hKey]; this
0x1800342a8  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800342ad  mov     rcx, [rsp+108h+var_58]
0x1800342b5  mov     [rsp+108h+hKey], rcx
0x1800342bd  test    eax, eax
0x1800342bf  jnz     loc_180034A91
0x1800342c5  test    r12d, r12d
0x1800342c8  jz      loc_18003444D
0x1800342ce  xorps   xmm0, xmm0
0x1800342d1  movups  xmmword ptr [rsp+108h+var_58], xmm0
0x1800342d9  test    r13d, r13d
0x1800342dc  jnz     short loc_18003430C
0x1800342de  mov     dword ptr [rsp+108h+var_58], 54DEA73Ah
0x1800342e9  mov     dword ptr [rsp+108h+var_58+4], 42A4ED1Fh
0x1800342f4  mov     dword ptr [rsp+108h+var_58+8], 633E71AFh
0x1800342ff  mov     dword ptr [rsp+108h+var_58+0Ch], 74F156D0h
0x18003430a  jmp     short loc_18003433F
0x18003430c  lea     rcx, [rsp+108h+var_58]; pguid
0x180034314  call    cs:__imp_CoCreateGuid
0x18003431a  mov     edi, eax
0x18003431c  test    eax, eax
0x18003431e  jns     short loc_18003433F
0x180034320  lea     rcx, [rsp+108h+lpSubKey]; this
0x180034325  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x18003432a  nop
0x18003432b  lea     rcx, [rsp+108h+hKey]; this
0x180034333  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180034338  mov     eax, edi
0x18003433a  jmp     loc_180034AC7
0x18003433f  lea     rcx, [rsp+108h+dwDisposition]; void *
0x180034344  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180034349  nop
0x18003434a  movzx   eax, byte ptr [rsp+108h+var_58+0Fh]
0x180034352  movzx   ecx, byte ptr [rsp+108h+var_58+0Eh]
0x18003435a  movzx   edx, byte ptr [rsp+108h+var_58+0Dh]
0x180034362  movzx   r8d, byte ptr [rsp+108h+var_58+0Ch]
0x18003436b  movzx   r10d, byte ptr [rsp+108h+var_58+0Bh]
0x180034374  movzx   r11d, byte ptr [rsp+108h+var_58+0Ah]
0x18003437d  movzx   edi, byte ptr [rsp+108h+var_58+9]
0x180034385  movzx   esi, byte ptr [rsp+108h+var_58+8]
0x18003438d  movzx   r14d, word ptr [rsp+108h+var_58+6]
0x180034396  movzx   r9d, word ptr [rsp+108h+var_58+4]
0x18003439f  mov     [rsp+108h+var_A8], eax
0x1800343a3  mov     [rsp+108h+var_B0], ecx
0x1800343a7  mov     [rsp+108h+var_B8], edx
0x1800343ab  mov     [rsp+108h+var_C0], r8d
0x1800343b0  mov     dword ptr [rsp+108h+lpdwDisposition], r10d
0x1800343b5  mov     dword ptr [rsp+108h+phkResult], r11d
0x1800343ba  mov     dword ptr [rsp+108h+lpSecurityAttributes], edi
0x1800343be  mov     dword ptr [rsp+108h+samDesired], esi
0x1800343c2  mov     [rsp+108h+dwOptions], r14d
0x1800343c7  mov     r8d, dword ptr [rsp+108h+var_58]
0x1800343cf  lea     rdx, a08x04x04x02x02; "{%08x-%04x-%04x-%02x%02x-%02x%02x%02x%0"...
0x1800343d6  lea     rcx, [rsp+108h+dwDisposition]
0x1800343db  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x1800343e0  mov     r8, qword ptr [rsp+108h+dwDisposition]; unsigned __int16 *
0x1800343e5  lea     rdx, aGuid; "GUID"
0x1800343ec  lea     rcx, [rsp+108h+hKey]; this
0x1800343f4  call    ?SetStringValue@CRegKey@ATL@@QEAAJPEBG0K@Z; ATL::CRegKey::SetStringValue(ushort const *,ushort const *,ulong)
0x1800343f9  xor     r14d, r14d
0x1800343fc  test    eax, eax
0x1800343fe  jz      short loc_180034433
0x180034400  mov     ecx, eax; unsigned int
0x180034402  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x180034407  mov     ebx, eax
0x180034409  lea     rcx, [rsp+108h+dwDisposition]; this
0x18003440e  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x180034413  nop
0x180034414  lea     rcx, [rsp+108h+lpSubKey]; this
0x180034419  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x18003441e  nop
0x18003441f  lea     rcx, [rsp+108h+hKey]; this
0x180034427  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18003442c  mov     eax, ebx
0x18003442e  jmp     loc_180034AC7
0x180034433  lea     rcx, [rsp+108h+dwDisposition]; this
0x180034438  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x18003443d  mov     rcx, [rsp+108h+hKey]; hKey
0x180034445  mov     rsi, [rsp+108h+var_70]
0x18003444d  mov     [rsp+108h+dwDisposition], 1
0x180034455  mov     edi, 4
0x18003445a  mov     dword ptr [rsp+108h+samDesired], edi; cbData
0x18003445e  lea     rax, [rsp+108h+dwDisposition]
0x180034463  mov     qword ptr [rsp+108h+dwOptions], rax; lpData
0x180034468  mov     r9d, edi; dwType
0x18003446b  xor     r8d, r8d; Reserved
0x18003446e  lea     rdx, aStart; "Start"
0x180034475  call    cs:__imp_RegSetValueExW
0x18003447b  test    eax, eax
0x18003447d  jz      short loc_1800344A7
0x18003447f  mov     ecx, eax; unsigned int
0x180034481  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x180034486  mov     ebx, eax
0x180034488  lea     rcx, [rsp+108h+lpSubKey]; this
0x18003448d  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x180034492  nop
0x180034493  lea     rcx, [rsp+108h+hKey]; this
0x18003449b  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800344a0  mov     eax, ebx
0x1800344a2  jmp     loc_180034AC7
0x1800344a7  mov     rax, [r15+8]
0x1800344ab  test    dword ptr [rax+40h], 400h
0x1800344b2  jz      short loc_1800344CB
0x1800344b4  lea     rdx, aFilename_0; "FileName"
0x1800344bb  mov     rcx, [rsp+108h+hKey]; hKey
0x1800344c3  call    cs:__imp_RegDeleteValueW
0x1800344c9  jmp     short loc_180034516
0x1800344cb  mov     rcx, r15; this
0x1800344ce  call    ?get_FileName@CEventSession@CETWProperties@WindowsPerformanceRecorder@@QEBAPEBGXZ; WindowsPerformanceRecorder::CETWProperties::CEventSession::get_FileName(void)
0x1800344d3  mov     r8, rax; unsigned __int16 *
0x1800344d6  lea     rdx, aFilename_0; "FileName"
0x1800344dd  lea     rcx, [rsp+108h+hKey]; this
0x1800344e5  call    ?SetStringValue@CRegKey@ATL@@QEAAJPEBG0K@Z; ATL::CRegKey::SetStringValue(ushort const *,ushort const *,ulong)
0x1800344ea  test    eax, eax
0x1800344ec  jz      short loc_180034516
0x1800344ee  mov     ecx, eax; unsigned int
0x1800344f0  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x1800344f5  mov     ebx, eax
0x1800344f7  lea     rcx, [rsp+108h+lpSubKey]; this
0x1800344fc  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x180034501  nop
0x180034502  lea     rcx, [rsp+108h+hKey]; this
0x18003450a  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18003450f  mov     eax, ebx
0x180034511  jmp     loc_180034AC7
0x180034516  mov     rax, [r15+8]
0x18003451a  mov     ecx, [rax+28h]
0x18003451d  mov     [rsp+108h+dwDisposition], ecx
0x180034521  mov     dword ptr [rsp+108h+samDesired], edi; cbData
0x180034525  lea     rax, [rsp+108h+dwDisposition]
0x18003452a  mov     qword ptr [rsp+108h+dwOptions], rax; lpData
0x18003452f  mov     r9d, edi; dwType
0x180034532  xor     r8d, r8d; Reserved
0x180034535  lea     rdx, aClocktype; "ClockType"
0x18003453c  mov     rcx, [rsp+108h+hKey]; hKey
0x180034544  call    cs:__imp_RegSetValueExW
0x18003454a  test    eax, eax
0x18003454c  jz      short loc_180034576
0x18003454e  mov     ecx, eax; unsigned int
0x180034550  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x180034555  mov     ebx, eax
0x180034557  lea     rcx, [rsp+108h+lpSubKey]; this
0x18003455c  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x180034561  nop
0x180034562  lea     rcx, [rsp+108h+hKey]; this
0x18003456a  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18003456f  mov     eax, ebx
0x180034571  jmp     loc_180034AC7
0x180034576  mov     rax, [r15+8]
0x18003457a  mov     ecx, [rax+40h]
0x18003457d  mov     [rsp+108h+dwDisposition], ecx
0x180034581  mov     dword ptr [rsp+108h+samDesired], edi; cbData
0x180034585  lea     rax, [rsp+108h+dwDisposition]
0x18003458a  mov     qword ptr [rsp+108h+dwOptions], rax; lpData
0x18003458f  mov     r9d, edi; dwType
0x180034592  xor     r8d, r8d; Reserved
0x180034595  lea     rdx, aLogfilemode; "LogFileMode"
0x18003459c  mov     rcx, [rsp+108h+hKey]; hKey
0x1800345a4  call    cs:__imp_RegSetValueExW
0x1800345aa  test    eax, eax
0x1800345ac  jz      short loc_1800345D6
0x1800345ae  mov     ecx, eax; unsigned int
0x1800345b0  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x1800345b5  mov     ebx, eax
0x1800345b7  lea     rcx, [rsp+108h+lpSubKey]; this
0x1800345bc  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x1800345c1  nop
0x1800345c2  lea     rcx, [rsp+108h+hKey]; this
0x1800345ca  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800345cf  mov     eax, ebx
0x1800345d1  jmp     loc_180034AC7
0x1800345d6  mov     rax, [r15+8]
0x1800345da  mov     ecx, [rax+30h]
0x1800345dd  mov     [rsp+108h+dwDisposition], ecx
0x1800345e1  mov     dword ptr [rsp+108h+samDesired], edi; cbData
0x1800345e5  lea     rax, [rsp+108h+dwDisposition]
0x1800345ea  mov     qword ptr [rsp+108h+dwOptions], rax; lpData
0x1800345ef  mov     r9d, edi; dwType
0x1800345f2  xor     r8d, r8d; Reserved
0x1800345f5  lea     rdx, aBuffersize_0; "BufferSize"
0x1800345fc  mov     rcx, [rsp+108h+hKey]; hKey
0x180034604  call    cs:__imp_RegSetValueExW
0x18003460a  test    eax, eax
0x18003460c  jz      short loc_180034636
0x18003460e  mov     ecx, eax; unsigned int
0x180034610  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x180034615  mov     ebx, eax
0x180034617  lea     rcx, [rsp+108h+lpSubKey]; this
0x18003461c  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x180034621  nop
0x180034622  lea     rcx, [rsp+108h+hKey]; this
0x18003462a  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18003462f  mov     eax, ebx
0x180034631  jmp     loc_180034AC7
0x180034636  mov     rax, [r15+8]
0x18003463a  mov     ecx, [rax+34h]
0x18003463d  mov     [rsp+108h+dwDisposition], ecx
0x180034641  mov     dword ptr [rsp+108h+samDesired], edi; cbData
0x180034645  lea     rax, [rsp+108h+dwDisposition]
0x18003464a  mov     qword ptr [rsp+108h+dwOptions], rax; lpData
0x18003464f  mov     r9d, edi; dwType
0x180034652  xor     r8d, r8d; Reserved
0x180034655  lea     rdx, aMinimumbuffers; "MinimumBuffers"
0x18003465c  mov     rcx, [rsp+108h+hKey]; hKey
0x180034664  call    cs:__imp_RegSetValueExW
0x18003466a  test    eax, eax
0x18003466c  jz      short loc_180034696
0x18003466e  mov     ecx, eax; unsigned int
0x180034670  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x180034675  mov     ebx, eax
0x180034677  lea     rcx, [rsp+108h+lpSubKey]; this
0x18003467c  call    ??1CSessionInfo@Status@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo(void)
0x180034681  nop
0x180034682  lea     rcx, [rsp+108h+hKey]; this
0x18003468a  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18003468f  mov     eax, ebx
0x180034691  jmp     loc_180034AC7
0x180034696  mov     rax, [r15+8]
0x18003469a  mov     ecx, [rax+38h]
0x18003469d  mov     [rsp+108h+dwDisposition], ecx
0x1800346a1  mov     dword ptr [rsp+108h+samDesired], edi; cbData
0x1800346a5  lea     rax, [rsp+108h+dwDisposition]
0x1800346aa  mov     qword ptr [rsp+108h+dwOptions], rax; lpData
0x1800346af  mov     r9d, edi; dwType
0x1800346b2  xor     r8d, r8d; Reserved
0x1800346b5  lea     rdx, aMaximumbuffers; "MaximumBuffers"
0x1800346bc  mov     rcx, [rsp+108h+hKey]; hKey
0x1800346c4  call    cs:__imp_RegSetValueExW
0x1800346ca  test    eax, eax
  ... truncated ...
```
