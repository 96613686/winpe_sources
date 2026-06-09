# RtlEtwTrace::Start(wchar_t const *,_GUID const &,wchar_t const *,std::vector<RtlEtwTrace::ProviderTuple,std::allocator<RtlEtwTrace::ProviderTuple>> const &)

- ea: `0x1800260a4`
- end: `0x18002641f`
- name: `?Start@RtlEtwTrace@@QEAAXPEB_WAEBU_GUID@@0AEBV?$vector@UProviderTuple@RtlEtwTrace@@V?$allocator@UProviderTuple@RtlEtwTrace@@@std@@@std@@@Z`
- size: `891`
- prototype: `void __fastcall(__int64, __int64, __int64, __int64, __int64 *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x18000717c`

## callees

- `0x1800027c0`
- `0x180002bcc`
- `0x1800032d8`
- `0x1800032e4`
- `0x1800061d0`
- `0x1800078d0`
- `0x180008854`
- `0x180008c78`
- `0x18000d954`
- `0x18000d9b4`
- `0x18002498c`
- `0x180025a78`
- `0x180025ad4`
- `0x180025db4`
- `0x180025e84`
- `0x1800260a4`
- `0x180026428`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002620a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002620a`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800261d1`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800261d1`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800261b1`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800261b1`
- `api-ms-win-eventing-legacy-l1-1-0!EnableTrace` at `0x18002633f`
- `api-ms-win-eventing-legacy-l1-1-0!EnableTrace` at `0x18002633f`
- `api-ms-win-eventing-controller-l1-1-0!StartTraceW` at `0x1800262b9`
- `api-ms-win-eventing-controller-l1-1-0!StartTraceW` at `0x1800262b9`

## string_xrefs

- `0x18002619c`: `LogPath`
- `0x1800261a3`: `SYSTEM\CurrentControlSet\Services\NetSetupSvc\Parameters`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall RtlEtwTrace::Start(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 *a5)
{
  RtlEtwTrace *v5; // r15
  ULONG64 *v6; // rsi
  _DWORD *v7; // r12
  int v8; // edi
  int v9; // ebx
  LSTATUS ValueW; // eax
  const WCHAR *v11; // rcx
  DWORD v12; // eax
  DWORD v13; // ebx
  signed int LastError; // eax
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // rdx
  __int64 LogFileName; // rax
  __int64 v19; // rdx
  __int64 v20; // r8
  const wchar_t *v21; // rax
  ULONG started; // ebx
  __int64 v23; // rbx
  __int64 v24; // r14
  ULONG v25; // edi
  _BYTE v26[32]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE pExceptionObject[208]; // [rsp+60h] [rbp-A0h] BYREF
  DWORD pcbData; // [rsp+130h] [rbp+30h] BYREF
  _DWORD *v29; // [rsp+138h] [rbp+38h] BYREF
  _BYTE pvData[528]; // [rsp+140h] [rbp+40h] BYREF

  v5 = g_NetSetupTrace;
  v6 = (ULONG64 *)((char *)g_NetSetupTrace + 16);
  if ( !*((_QWORD *)g_NetSetupTrace + 2) )
  {
    v7 = operator new(0x1078u);
    v29 = v7;
    v8 = *((_DWORD *)v5 + 2);
    v9 = *(_DWORD *)v5;
    memset_0(v7, 0, 0x1078u);
    *v7 = 4216;
    v7[11] = 0x20000;
    v7[10] = 2;
    *(_OWORD *)(v7 + 6) = xmmword_180037048;
    v7[16] = v9 | 0x10000000;
    v7[15] = v8;
    v7[29] = 120;
    v7[28] = 2168;
    v29 = v7;
    memset_0(pvData, 0, 0x208u);
    pcbData = 520;
    ValueW = RegGetValueW(
               HKEY_LOCAL_MACHINE,
               L"SYSTEM\\CurrentControlSet\\Services\\NetSetupSvc\\Parameters",
               L"LogPath",
               2u,
               0,
               pvData,
               &pcbData);
    v11 = (const WCHAR *)pvData;
    if ( ValueW )
      v11 = L"%windir%\\Logs\\NetSetup\\";
    v12 = ExpandEnvironmentStringsW(v11, (LPWSTR)v7 + 1084, 0x3FFu);
    v13 = v12;
    if ( !v12 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_4a7bb80c34923429700e535c78fe3875_Traceguids);
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      HResultException::HResultException((HResultException *)pExceptionObject, LastError);
      throw (HResultException *)pExceptionObject;
    }
    if ( v12 >= 0x400 || 1024 - (unsigned __int64)v12 < 0xD )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_4a7bb80c34923429700e535c78fe3875_Traceguids);
      HResultException::HResultException((HResultException *)pExceptionObject, -2147024735);
      throw (HResultException *)pExceptionObject;
    }
    MakeSureDirectoryPathExists((PCSTR)v7 + 2168);
    BackupLogFiles(v16, v15, *((_DWORD *)v5 + 1), *((_DWORD *)v5 + 3) << 20, (__int64)(v7 + 542));
    LogFileName = MakeLogFileName(v26, v17, 0);
    v21 = (const wchar_t *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(LogFileName, v19, v20);
    StringCchCopyW((wchar_t *)v7 + v13 + 1083, 0xEu, v21);
    std::wstring::_Tidy_deallocate(v26);
    started = StartTraceW(v6, L"NetCfgTrace", (PEVENT_TRACE_PROPERTIES)v7);
    if ( started )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          16,
          (unsigned int)WPP_4a7bb80c34923429700e535c78fe3875_Traceguids,
          (unsigned int)L"NetCfgTrace",
          started);
      Win32Exception::Win32Exception((Win32Exception *)pExceptionObject, started);
      throw (Win32Exception *)pExceptionObject;
    }
    v23 = *a5;
    v24 = a5[1];
    while ( v23 != v24 )
    {
      v25 = EnableTrace(1u, *(_DWORD *)(v23 + 16), *(_DWORD *)(v23 + 20), (LPCGUID)v23, *v6);
      if ( v25 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          WPP_SF__guid_D(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            17,
            WPP_4a7bb80c34923429700e535c78fe3875_Traceguids,
            v23,
            v25);
        Win32Exception::Win32Exception((Win32Exception *)pExceptionObject, v25);
        throw (Win32Exception *)pExceptionObject;
      }
      v23 += 24;
    }
    std::unique_ptr<FULL_TRACE_PROPERTIES>::~unique_ptr<FULL_TRACE_PROPERTIES>(&v29);
  }
}

```

## disassembly

```asm
0x1800260a4  push    rbp
0x1800260a6  push    rbx
0x1800260a7  push    rsi
0x1800260a8  push    rdi
0x1800260a9  push    r12
0x1800260ab  push    r13
0x1800260ad  push    r14
0x1800260af  push    r15
0x1800260b1  lea     rbp, [rsp-268h]
0x1800260b9  sub     rsp, 368h
0x1800260c0  mov     rax, cs:__security_cookie
0x1800260c7  xor     rax, rsp
0x1800260ca  mov     [rbp+2A0h+var_50], rax
0x1800260d1  mov     r14, [rbp+2A0h+arg_20]
0x1800260d8  mov     r15, cs:?g_NetSetupTrace@@3PEAVRtlEtwTrace@@EA; RtlEtwTrace * g_NetSetupTrace
0x1800260df  lea     rsi, [r15+10h]
0x1800260e3  cmp     qword ptr [rsi], 0
0x1800260e7  jnz     loc_1800263AD
0x1800260ed  mov     r13d, 1078h
0x1800260f3  mov     ecx, r13d; Size
0x1800260f6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800260fb  mov     r12, rax
0x1800260fe  mov     [rbp+2A0h+var_268], rax
0x180026102  mov     edi, [r15+8]
0x180026106  mov     ebx, [r15]
0x180026109  mov     r8d, r13d; Size
0x18002610c  xor     edx, edx; Val
0x18002610e  mov     rcx, rax; void *
0x180026111  call    memset_0
0x180026116  mov     [r12], r13d
0x18002611a  mov     dword ptr [r12+2Ch], 20000h
0x180026123  mov     r13d, 2
0x180026129  mov     [r12+28h], r13d
0x18002612e  movups  xmm0, cs:xmmword_180037048
0x180026135  movdqu  xmmword ptr [r12+18h], xmm0
0x18002613c  bts     ebx, 1Ch
0x180026140  mov     [r12+40h], ebx
0x180026145  mov     [r12+3Ch], edi
0x18002614a  mov     dword ptr [r12+74h], 78h ; 'x'
0x180026153  mov     dword ptr [r12+70h], 878h
0x18002615c  mov     [rbp+2A0h+var_268], r12
0x180026160  mov     ebx, 208h
0x180026165  mov     r8d, ebx; Size
0x180026168  xor     edx, edx; Val
0x18002616a  lea     rcx, [rbp+2A0h+var_260]; void *
0x18002616e  call    memset_0
0x180026173  mov     [rbp+2A0h+var_270], ebx
0x180026176  lea     rdi, [r12+878h]
0x18002617e  lea     rax, [rbp+2A0h+var_270]
0x180026182  mov     [rsp+3A0h+pcbData], rax; pcbData
0x180026187  lea     rax, [rbp+2A0h+var_260]
0x18002618b  mov     [rsp+3A0h+pvData], rax; pvData
0x180026190  mov     [rsp+3A0h+pdwType], 0; pdwType
0x180026199  mov     r9d, r13d; dwFlags
0x18002619c  lea     r8, Value; "LogPath"
0x1800261a3  lea     rdx, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Services\\Ne"...
0x1800261aa  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1800261b1  call    cs:__imp_RegGetValueW
0x1800261b7  lea     rdx, Src; "%windir%\\Logs\\NetSetup\\"
0x1800261be  lea     rcx, [rbp+2A0h+var_260]
0x1800261c2  test    eax, eax
0x1800261c4  cmovnz  rcx, rdx; lpSrc
0x1800261c8  mov     r8d, 3FFh; nSize
0x1800261ce  mov     rdx, rdi; lpDst
0x1800261d1  call    cs:__imp_ExpandEnvironmentStringsW
0x1800261d7  mov     ebx, eax
0x1800261d9  test    eax, eax
0x1800261db  jnz     short loc_18002623A
0x1800261dd  lea     rax, WPP_GLOBAL_Control
0x1800261e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800261eb  cmp     rcx, rax
0x1800261ee  jz      short loc_18002620A
0x1800261f0  cmp     [rcx+19h], r13b
0x1800261f4  jb      short loc_18002620A
0x1800261f6  lea     edx, [r13+0Ch]
0x1800261fa  lea     r8, WPP_4a7bb80c34923429700e535c78fe3875_Traceguids
0x180026201  mov     rcx, [rcx+10h]
0x180026205  call    WPP_SF_
0x18002620a  call    cs:__imp_GetLastError
0x180026210  test    eax, eax
0x180026212  jle     short loc_18002621C
0x180026214  movzx   eax, ax
0x180026217  or      eax, 80070000h
0x18002621c  mov     edx, eax; int
0x18002621e  lea     rcx, [rsp+3A0h+pExceptionObject]; this
0x180026223  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x180026228  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x18002622f  lea     rcx, [rsp+3A0h+pExceptionObject]; pExceptionObject
0x180026234  call    _CxxThrowException_0
0x18002623a  mov     ecx, 400h
0x18002623f  cmp     ebx, ecx
0x180026241  jnb     loc_1800263D0
0x180026247  sub     rcx, rbx
0x18002624a  cmp     rcx, 0Dh
0x18002624e  jb      loc_1800263D0
0x180026254  mov     rcx, rdi; DirPath
0x180026257  call    MakeSureDirectoryPathExists
0x18002625c  mov     r9d, [r15+0Ch]
0x180026260  shl     r9d, 14h
0x180026264  mov     [rsp+3A0h+pdwType], rdi
0x180026269  mov     r8d, [r15+4]
0x18002626d  call    BackupLogFiles
0x180026272  xor     r8d, r8d
0x180026275  lea     rcx, [rsp+3A0h+var_360]
0x18002627a  call    MakeLogFileName
0x18002627f  mov     rcx, rax
0x180026282  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180026287  lea     edx, [rbx-1]
0x18002628a  lea     rdx, [rdx+43Ch]
0x180026291  lea     rcx, [r12+rdx*2]; wchar_t *
0x180026295  mov     r8, rax; wchar_t *
0x180026298  mov     edx, 0Eh; unsigned __int64
0x18002629d  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800262a2  lea     rcx, [rsp+3A0h+var_360]
0x1800262a7  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800262ac  mov     r8, r12; Properties
0x1800262af  lea     rdx, InstanceName; "NetCfgTrace"
0x1800262b6  mov     rcx, rsi; TraceHandle
0x1800262b9  call    cs:__imp_StartTraceW
0x1800262bf  mov     ebx, eax
0x1800262c1  test    eax, eax
0x1800262c3  jz      short loc_18002631C
0x1800262c5  lea     rax, WPP_GLOBAL_Control
0x1800262cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800262d3  cmp     rcx, rax
0x1800262d6  jz      short loc_1800262FE
0x1800262d8  cmp     [rcx+19h], r13b
0x1800262dc  jb      short loc_1800262FE
0x1800262de  mov     edx, 10h
0x1800262e3  mov     dword ptr [rsp+3A0h+pdwType], ebx
0x1800262e7  lea     r9, InstanceName; "NetCfgTrace"
0x1800262ee  lea     r8, WPP_4a7bb80c34923429700e535c78fe3875_Traceguids
0x1800262f5  mov     rcx, [rcx+10h]
0x1800262f9  call    WPP_SF_Sd
0x1800262fe  mov     edx, ebx; int
0x180026300  lea     rcx, [rsp+3A0h+pExceptionObject]; this
0x180026305  call    ??0Win32Exception@@QEAA@J@Z; Win32Exception::Win32Exception(long)
0x18002630a  lea     rdx, _TI4?AVWin32Exception@@; pThrowInfo
0x180026311  lea     rcx, [rsp+3A0h+pExceptionObject]; pExceptionObject
0x180026316  call    _CxxThrowException_0
0x18002631c  mov     rbx, [r14]
0x18002631f  mov     r14, [r14+8]
0x180026323  cmp     rbx, r14
0x180026326  jz      short loc_1800263A4
0x180026328  mov     rax, [rsi]
0x18002632b  mov     [rsp+3A0h+pdwType], rax; TraceHandle
0x180026330  mov     r9, rbx; ControlGuid
0x180026333  mov     r8d, [rbx+14h]; EnableLevel
0x180026337  mov     edx, [rbx+10h]; EnableFlag
0x18002633a  mov     ecx, 1; Enable
0x18002633f  call    cs:__imp_EnableTrace
0x180026345  mov     edi, eax
0x180026347  test    eax, eax
0x180026349  jnz     short loc_180026351
0x18002634b  add     rbx, 18h
0x18002634f  jmp     short loc_180026323
0x180026351  lea     rax, WPP_GLOBAL_Control
0x180026358  mov     rcx, cs:WPP_GLOBAL_Control
0x18002635f  cmp     rcx, rax
0x180026362  jz      short loc_180026386
0x180026364  cmp     [rcx+19h], r13b
0x180026368  jb      short loc_180026386
0x18002636a  mov     edx, 11h
0x18002636f  mov     dword ptr [rsp+3A0h+pdwType], edi
0x180026373  mov     r9, rbx
0x180026376  lea     r8, WPP_4a7bb80c34923429700e535c78fe3875_Traceguids
0x18002637d  mov     rcx, [rcx+10h]
0x180026381  call    WPP_SF__guid_D
0x180026386  mov     edx, edi; int
0x180026388  lea     rcx, [rsp+3A0h+pExceptionObject]; this
0x18002638d  call    ??0Win32Exception@@QEAA@J@Z; Win32Exception::Win32Exception(long)
0x180026392  lea     rdx, _TI4?AVWin32Exception@@; pThrowInfo
0x180026399  lea     rcx, [rsp+3A0h+pExceptionObject]; pExceptionObject
0x18002639e  call    _CxxThrowException_0
0x1800263a4  lea     rcx, [rbp+2A0h+var_268]
0x1800263a8  call    ??1?$unique_ptr@UFULL_TRACE_PROPERTIES@@U?$default_delete@UFULL_TRACE_PROPERTIES@@@std@@@std@@QEAA@XZ; std::unique_ptr<FULL_TRACE_PROPERTIES>::~unique_ptr<FULL_TRACE_PROPERTIES>(void)
0x1800263ad  mov     rcx, [rbp+2A0h+var_50]
0x1800263b4  xor     rcx, rsp; StackCookie
0x1800263b7  call    __security_check_cookie
0x1800263bc  add     rsp, 368h
0x1800263c3  pop     r15
0x1800263c5  pop     r14
0x1800263c7  pop     r13
0x1800263c9  pop     r12
0x1800263cb  pop     rdi
0x1800263cc  pop     rsi
0x1800263cd  pop     rbx
0x1800263ce  pop     rbp
0x1800263cf  retn
0x1800263d0  lea     rax, WPP_GLOBAL_Control
0x1800263d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800263de  cmp     rcx, rax
0x1800263e1  jz      short loc_1800263FE
0x1800263e3  cmp     [rcx+19h], r13b
0x1800263e7  jb      short loc_1800263FE
0x1800263e9  mov     edx, 0Fh
0x1800263ee  lea     r8, WPP_4a7bb80c34923429700e535c78fe3875_Traceguids
0x1800263f5  mov     rcx, [rcx+10h]
0x1800263f9  call    WPP_SF_
0x1800263fe  mov     edx, 800700A1h; int
0x180026403  lea     rcx, [rsp+3A0h+pExceptionObject]; this
0x180026408  call    ??0HResultException@@QEAA@J@Z; HResultException::HResultException(long)
0x18002640d  lea     rdx, _TI3?AVHResultException@@; pThrowInfo
0x180026414  lea     rcx, [rsp+3A0h+pExceptionObject]; pExceptionObject
0x180026419  call    _CxxThrowException_0
```
