# DataStoreReader::LoadMostRecentResultsAndGetState(WinSATData &,__MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002 &,bool)

- ea: `0x180002690`
- end: `0x18000286e`
- name: `?LoadMostRecentResultsAndGetState@DataStoreReader@@SAJAEAUWinSATData@@AEAW4__MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002@@_N@Z`
- size: `478`
- prototype: `__int64 __fastcall(struct WinSATData *, enum __MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002 *, bool)`
- caller_count: `3`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180002254`
- `0x180020500`
- `0x180020dd8`

## callees

- `0x180002690`
- `0x180002880`
- `0x180002f70`
- `0x180003970`
- `0x18000e844`
- `0x18000e938`
- `0x1800100a0`
- `0x180010274`
- `0x18001070c`
- `0x18001115c`
- `0x18002cb0c`
- `0x18002fb50`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180002838`
- `msvcrt!??3@YAXPEAX@Z` at `0x180002838`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000271f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000271f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800026fc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800026fc`
- `USER32!GetSystemMetrics` at `0x1800026eb`
- `USER32!GetSystemMetrics` at `0x1800026eb`
- `KERNEL32!WTSGetActiveConsoleSessionId` at `0x180002739`
- `KERNEL32!WTSGetActiveConsoleSessionId` at `0x180002739`
- `KERNEL32!ProcessIdToSessionId` at `0x18000270f`
- `KERNEL32!ProcessIdToSessionId` at `0x18000270f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DataStoreReader::LoadMostRecentResultsAndGetState(
        struct WinSATData *a1,
        enum __MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002 *a2,
        struct IXMLDOMDocument2 **a3)
{
  __int64 result; // rax
  DWORD CurrentProcessId; // eax
  int v7; // ebx
  __int16 v8; // dx
  __int64 v9; // rcx
  DWORD pSessionId[2]; // [rsp+28h] [rbp-E0h] BYREF
  __int64 v11; // [rsp+30h] [rbp-D8h]
  __int64 v12; // [rsp+38h] [rbp-D0h] BYREF
  void *v13[5]; // [rsp+40h] [rbp-C8h] BYREF
  __int64 v14; // [rsp+68h] [rbp-A0h]
  _BYTE v15[28]; // [rsp+70h] [rbp-98h] BYREF
  int v16; // [rsp+8Ch] [rbp-7Ch]
  __int64 v17; // [rsp+90h] [rbp-78h]
  __int16 v18; // [rsp+98h] [rbp-70h]
  __int16 v19; // [rsp+118h] [rbp+10h]
  __int64 v20; // [rsp+120h] [rbp+18h]
  __int16 v21; // [rsp+128h] [rbp+20h]
  __int16 v22; // [rsp+1A8h] [rbp+A0h]

  v11 = -2;
  result = DataStoreReader::LoadMostRecentResultsGetStateGetDoc(a1, a2, a3);
  if ( (int)result >= 0 )
  {
    if ( *a2 == WINSAT_ASSESSMENT_STATE_VALID )
    {
      GetSystemMetrics(4096);
      pSessionId[0] = 0;
      CurrentProcessId = GetCurrentProcessId();
      if ( ProcessIdToSessionId(CurrentProcessId, pSessionId) )
      {
        WTSGetActiveConsoleSessionId();
      }
      else if ( GetLastError() )
      {
        return 2147500037LL;
      }
      memset(v13, 0, 24);
      memset(v15, 0, 24);
      LOBYTE(v12) = 0;
      std::vector<WinsatSystemBoardInfo>::clear(v13);
      v13[3] = (void *)-1LL;
      v13[4] = (void *)-1LL;
      v18 = 0;
      v19 = 0;
      v20 = -1;
      v16 = -1;
      v17 = -1;
      LOBYTE(v14) = 0;
      v21 = 0;
      v22 = 0;
      std::vector<WinsatMemoryInfo>::clear(v15);
      v7 = WinSATCriticalHardwareInfo::PopulateCPUInfo((WinSATCriticalHardwareInfo *)&v12);
      if ( v7 < 0 )
        goto LABEL_11;
      v7 = WinSATCriticalHardwareInfo::PopulateMemoryInfo((WinSATCriticalHardwareInfo *)&v12);
      if ( v7 < 0 )
        goto LABEL_11;
      if ( !(unsigned __int8)WinSATCriticalHardwareInfo::IsPopulated(&v12, 2078) )
      {
        v7 = -2147467259;
LABEL_11:
        WinSATCriticalHardwareInfo::~WinSATCriticalHardwareInfo((WinSATCriticalHardwareInfo *)&v12);
        return (unsigned int)v7;
      }
      if ( (unsigned int)WinSATCriticalHardwareInfo::GetDifferences((__int64)&v12, (__int64)a1, v8) )
        *a2 = WINSAT_ASSESSMENT_STATE_INCOHERENT_WITH_HARDWARE;
      std::vector<WinsatMemoryInfo>::_Tidy(v15);
      if ( v13[0] )
      {
        std::vector<WinsatSystemBoardInfo>::_Destroy(v9, v13[0], v13[1]);
        operator delete(v13[0]);
      }
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180002690  mov     rax, rsp
0x180002693  push    rbp
0x180002694  push    rdi
0x180002695  push    r14
0x180002697  lea     rbp, [rax-0D8h]
0x18000269e  sub     rsp, 1C0h
0x1800026a5  mov     [rsp+1D0h+var_1A8], 0FFFFFFFFFFFFFFFEh
0x1800026ae  mov     [rax+18h], rbx
0x1800026b2  mov     [rax+20h], rsi
0x1800026b6  mov     rax, cs:__security_cookie
0x1800026bd  xor     rax, rsp
0x1800026c0  mov     [rbp+0D0h+var_20], rax
0x1800026c7  mov     rdi, rdx
0x1800026ca  mov     rsi, rcx
0x1800026cd  call    ?LoadMostRecentResultsGetStateGetDoc@DataStoreReader@@KAJAEAUWinSATData@@AEAW4__MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002@@PEAPEAUIXMLDOMDocument2@@@Z; DataStoreReader::LoadMostRecentResultsGetStateGetDoc(WinSATData &,__MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002 &,IXMLDOMDocument2 * *)
0x1800026d2  xor     r14d, r14d
0x1800026d5  test    eax, eax
0x1800026d7  js      loc_180002846
0x1800026dd  cmp     dword ptr [rdi], 1
0x1800026e0  jnz     loc_180002844
0x1800026e6  mov     ecx, 1000h; nIndex
0x1800026eb  call    cs:__imp_GetSystemMetrics
0x1800026f2  nop     dword ptr [rax+rax+00h]
0x1800026f7  mov     [rsp+1D0h+pSessionId], r14d
0x1800026fc  call    cs:__imp_GetCurrentProcessId
0x180002703  nop     dword ptr [rax+rax+00h]
0x180002708  mov     ecx, eax; dwProcessId
0x18000270a  lea     rdx, [rsp+1D0h+pSessionId]; pSessionId
0x18000270f  call    cs:__imp_ProcessIdToSessionId
0x180002716  nop     dword ptr [rax+rax+00h]
0x18000271b  test    eax, eax
0x18000271d  jnz     short loc_180002739
0x18000271f  call    cs:__imp_GetLastError
0x180002726  nop     dword ptr [rax+rax+00h]
0x18000272b  test    eax, eax
0x18000272d  jz      short loc_180002745
0x18000272f  mov     eax, 80004005h
0x180002734  jmp     loc_180002846
0x180002739  call    cs:__imp_WTSGetActiveConsoleSessionId
0x180002740  nop     dword ptr [rax+rax+00h]
0x180002745  mov     qword ptr [rsp+1D0h+var_198], r14
0x18000274a  xorps   xmm0, xmm0
0x18000274d  movdqa  xmmword ptr [rsp+1D0h+var_198+8], xmm0
0x180002753  mov     qword ptr [rsp+1D0h+var_168], r14
0x180002758  xorps   xmm1, xmm1
0x18000275b  movdqa  xmmword ptr [rsp+1D0h+var_168+8], xmm1
0x180002761  mov     byte ptr [rsp+1D0h+var_1A0], r14b
0x180002766  lea     rcx, [rsp+1D0h+var_198]
0x18000276b  call    ?clear@?$vector@UWinsatSystemBoardInfo@@V?$allocator@UWinsatSystemBoardInfo@@@std@@@std@@QEAAXXZ; std::vector<WinsatSystemBoardInfo>::clear(void)
0x180002770  or      ecx, 0FFFFFFFFh
0x180002773  mov     dword ptr [rsp+1D0h+var_180], ecx
0x180002777  mov     dword ptr [rsp+1D0h+var_180+4], ecx
0x18000277b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000277f  mov     [rsp+1D0h+var_178], rax
0x180002784  mov     [rbp+0D0h+var_140], r14w
0x180002789  mov     [rbp+0D0h+var_C0], r14w
0x18000278e  mov     [rbp+0D0h+var_B8], rax
0x180002792  mov     [rbp+0D0h+var_14C], ecx
0x180002795  mov     [rbp+0D0h+var_148], rax
0x180002799  mov     byte ptr [rsp+1D0h+var_170], r14b
0x18000279e  mov     [rbp+0D0h+var_B0], r14w
0x1800027a3  mov     [rbp+0D0h+var_30], r14w
0x1800027ab  lea     rcx, [rsp+1D0h+var_168]
0x1800027b0  call    ?clear@?$vector@UWinsatMemoryInfo@@V?$allocator@UWinsatMemoryInfo@@@std@@@std@@QEAAXXZ; std::vector<WinsatMemoryInfo>::clear(void)
0x1800027b5  lea     rcx, [rsp+1D0h+var_1A0]; this
0x1800027ba  call    ?PopulateCPUInfo@WinSATCriticalHardwareInfo@@AEAAJXZ; WinSATCriticalHardwareInfo::PopulateCPUInfo(void)
0x1800027bf  mov     ebx, eax
0x1800027c1  test    eax, eax
0x1800027c3  js      short loc_1800027ED
0x1800027c5  lea     rcx, [rsp+1D0h+var_1A0]; this
0x1800027ca  call    ?PopulateMemoryInfo@WinSATCriticalHardwareInfo@@AEAAJXZ; WinSATCriticalHardwareInfo::PopulateMemoryInfo(void)
0x1800027cf  mov     ebx, eax
0x1800027d1  test    eax, eax
0x1800027d3  js      short loc_1800027ED
0x1800027d5  mov     edx, 81Eh
0x1800027da  lea     rcx, [rsp+1D0h+var_1A0]
0x1800027df  call    ?IsPopulated@WinSATCriticalHardwareInfo@@QEBA_NW4HardwareID@@@Z; WinSATCriticalHardwareInfo::IsPopulated(HardwareID)
0x1800027e4  test    al, al
0x1800027e6  jnz     short loc_1800027FB
0x1800027e8  mov     ebx, 80004005h
0x1800027ed  lea     rcx, [rsp+1D0h+var_1A0]; this
0x1800027f2  call    ??1WinSATCriticalHardwareInfo@@QEAA@XZ; WinSATCriticalHardwareInfo::~WinSATCriticalHardwareInfo(void)
0x1800027f7  mov     eax, ebx
0x1800027f9  jmp     short loc_180002846
0x1800027fb  mov     r8d, edx
0x1800027fe  mov     rdx, rsi
0x180002801  lea     rcx, [rsp+1D0h+var_1A0]
0x180002806  call    ?GetDifferences@WinSATCriticalHardwareInfo@@QEBA?AW4HardwareID@@AEBU1@W42@@Z; WinSATCriticalHardwareInfo::GetDifferences(WinSATCriticalHardwareInfo const &,HardwareID)
0x18000280b  test    eax, eax
0x18000280d  jz      short loc_180002815
0x18000280f  mov     dword ptr [rdi], 2
0x180002815  lea     rcx, [rsp+1D0h+var_168]
0x18000281a  call    ?_Tidy@?$vector@UWinsatMemoryInfo@@V?$allocator@UWinsatMemoryInfo@@@std@@@std@@IEAAXXZ; std::vector<WinsatMemoryInfo>::_Tidy(void)
0x18000281f  mov     rdx, qword ptr [rsp+1D0h+var_198]
0x180002824  test    rdx, rdx
0x180002827  jz      short loc_180002844
0x180002829  mov     r8, qword ptr [rsp+1D0h+var_198+8]
0x18000282e  call    ?_Destroy@?$vector@UWinsatSystemBoardInfo@@V?$allocator@UWinsatSystemBoardInfo@@@std@@@std@@IEAAXPEAUWinsatSystemBoardInfo@@0@Z; std::vector<WinsatSystemBoardInfo>::_Destroy(WinsatSystemBoardInfo *,WinsatSystemBoardInfo *)
0x180002833  mov     rcx, qword ptr [rsp+1D0h+var_198]
0x180002838  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000283f  nop     dword ptr [rax+rax+00h]
0x180002844  xor     eax, eax
0x180002846  mov     rcx, [rbp+0D0h+var_20]
0x18000284d  xor     rcx, rsp; StackCookie
0x180002850  call    __security_check_cookie
0x180002855  lea     r11, [rsp+1D0h+var_10]
0x18000285d  mov     rbx, [r11+30h]
0x180002861  mov     rsi, [r11+38h]
0x180002865  mov     rsp, r11
0x180002868  pop     r14
0x18000286a  pop     rdi
0x18000286b  pop     rbp
0x18000286c  retn
```
