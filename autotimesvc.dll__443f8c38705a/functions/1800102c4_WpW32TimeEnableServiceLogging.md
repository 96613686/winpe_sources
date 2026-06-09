# WpW32TimeEnableServiceLogging

- ea: `0x1800102c4`
- end: `0x18001050b`
- name: `WpW32TimeEnableServiceLogging`
- size: `583`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `12`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18000d330`

## callees

- `0x180001010`
- `0x1800012f0`
- `0x180002a70`
- `0x18000365c`
- `0x180009194`
- `0x18000dfa8`
- `0x18000e048`
- `0x18000ee3c`
- `0x18000eef0`
- `0x18000fb94`
- `0x18000fcfc`
- `0x1800102c4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800103a5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010404`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800104bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800104e3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800103a5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010404`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800104bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800104e3`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1800103c8`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1800103c8`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x18001035f`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x18001035f`

## string_xrefs

- `0x180010420`: `HKLM\System\ControlSet001\Services\W32Time\Config`
- `0x180010427`: `W32TimeConfig`
- `0x180010380`: `onecore\base\time\autotime\timeservice\wpw32timeclient.cpp`
- `0x1800103df`: `onecore\base\time\autotime\timeservice\wpw32timeclient.cpp`
- `0x18001048b`: `onecore\base\time\autotime\timeservice\wpw32timeclient.cpp`

## pseudocode

```c
__int64 WpW32TimeEnableServiceLogging()
{
  HRESULT v0; // edi
  void *v1; // rcx
  HRESULT v3; // eax
  unsigned int v4; // edi
  void *v5; // rcx
  const unsigned __int16 *v6; // rdx
  unsigned int v7; // r8d
  int v8; // eax
  unsigned int v9; // edi
  void *v10; // rcx
  void *v11; // rcx
  LPVOID pv; // [rsp+20h] [rbp-258h] BYREF
  __int128 v13; // [rsp+28h] [rbp-250h] BYREF
  LPVOID *p_pv; // [rsp+38h] [rbp-240h] BYREF
  PWSTR ppszPath; // [rsp+40h] [rbp-238h] BYREF
  char v16; // [rsp+48h] [rbp-230h]
  WCHAR pszPathOut[264]; // [rsp+50h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  if ( (unsigned int)dword_18001C010 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18001C010, 512) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_18001C010,
      byte_180017911,
      0,
      0);
  memset_0(pszPathOut, 0, 0x20Au);
  pv = 0;
  p_pv = &pv;
  ppszPath = 0;
  v16 = 1;
  v0 = SHGetKnownFolderPath(&rfid, 0x4000u, 0, &ppszPath);
  wil::details::out_param_t<wistd::unique_ptr<unsigned short,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pv);
  if ( v0 >= 0 )
  {
    v3 = PathCchCombine(pszPathOut, 0x105u, (PCWSTR)pv, L"NonEtwLogs\\w32time.log");
    v4 = v3;
    if ( v3 >= 0 )
    {
      v13 = 0;
      RegKey::Create(
        (RegKey *)&v13,
        L"W32TimeConfig",
        L"HKLM\\System\\ControlSet001\\Services\\W32Time\\Config",
        0x20006u);
      RegKey::SetString((RegKey *)&v13, L"FileLogName", pszPathOut);
      RegKey::SetDword((RegKey *)&v13, v6, v7);
      RegKey::SetString((RegKey *)&v13, L"FileLogEntries", L"0-300");
      v8 = CreateAndAclLogFile(pszPathOut);
      v9 = v8;
      if ( v8 >= 0 )
      {
        RegKey::~RegKey((RegKey *)&v13);
        v11 = pv;
        pv = 0;
        if ( v11 )
          CoTaskMemFree(v11);
        return 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x23A,
          (unsigned int)"onecore\\base\\time\\autotime\\timeservice\\wpw32timeclient.cpp",
          (const char *)(unsigned int)v8,
          (int)pv);
        RegKey::~RegKey((RegKey *)&v13);
        v10 = pv;
        pv = 0;
        if ( v10 )
          CoTaskMemFree(v10);
        return v9;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x22A,
        (unsigned int)"onecore\\base\\time\\autotime\\timeservice\\wpw32timeclient.cpp",
        (const char *)(unsigned int)v3,
        (int)pv);
      v5 = pv;
      pv = 0;
      if ( v5 )
        CoTaskMemFree(v5);
      return v4;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x223,
      (unsigned int)"onecore\\base\\time\\autotime\\timeservice\\wpw32timeclient.cpp",
      (const char *)(unsigned int)v0,
      (int)pv);
    v1 = pv;
    pv = 0;
    if ( v1 )
      CoTaskMemFree(v1);
    return (unsigned int)v0;
  }
}

```

## disassembly

```asm
0x1800102c4  push    rdi
0x1800102c6  sub     rsp, 270h
0x1800102cd  mov     rax, cs:__security_cookie
0x1800102d4  xor     rax, rsp
0x1800102d7  mov     [rsp+278h+var_18], rax
0x1800102df  mov     eax, cs:dword_18001C010
0x1800102e5  cmp     eax, 4
0x1800102e8  jbe     short loc_180010318
0x1800102ea  mov     edx, 200h
0x1800102ef  lea     rcx, dword_18001C010
0x1800102f6  call    _tlgKeywordOn
0x1800102fb  test    al, al
0x1800102fd  jz      short loc_180010318
0x1800102ff  xor     r9d, r9d
0x180010302  xor     r8d, r8d
0x180010305  lea     rdx, byte_180017911
0x18001030c  lea     rcx, dword_18001C010
0x180010313  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180010318  xor     edx, edx; Val
0x18001031a  mov     r8d, 20Ah; Size
0x180010320  lea     rcx, [rsp+278h+pszPathOut]; void *
0x180010325  call    memset_0
0x18001032a  mov     [rsp+278h+pv], 0; int
0x180010333  lea     rax, [rsp+278h+pv]
0x180010338  mov     [rsp+278h+var_240], rax
0x18001033d  mov     [rsp+278h+ppszPath], 0
0x180010346  mov     [rsp+278h+var_230], 1
0x18001034b  lea     r9, [rsp+278h+ppszPath]; ppszPath
0x180010350  xor     r8d, r8d; hToken
0x180010353  mov     edx, 4000h; dwFlags
0x180010358  lea     rcx, rfid; rfid
0x18001035f  call    cs:__imp_SHGetKnownFolderPath
0x180010365  mov     edi, eax
0x180010367  lea     rcx, [rsp+278h+var_240]
0x18001036c  call    ??1?$out_param_t@V?$unique_ptr@GU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<ushort,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x180010371  test    edi, edi
0x180010373  jns     short loc_1800103B2
0x180010375  mov     rcx, [rsp+278h]; this
0x18001037d  mov     r9d, edi; char *
0x180010380  lea     r8, aOnecoreBaseTim_2; "onecore\\base\\time\\autotime\\timeserv"...
0x180010387  mov     edx, 223h; void *
0x18001038c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010391  nop
0x180010392  mov     rcx, [rsp+278h+pv]; pv
0x180010397  mov     [rsp+278h+pv], 0
0x1800103a0  test    rcx, rcx
0x1800103a3  jz      short loc_1800103AB
0x1800103a5  call    cs:__imp_CoTaskMemFree
0x1800103ab  mov     eax, edi
0x1800103ad  jmp     loc_1800104F1
0x1800103b2  lea     r9, pszMore; "NonEtwLogs\\w32time.log"
0x1800103b9  mov     r8, [rsp+278h+pv]; pszPathIn
0x1800103be  mov     edx, 105h; cchPathOut
0x1800103c3  lea     rcx, [rsp+278h+pszPathOut]; pszPathOut
0x1800103c8  call    cs:__imp_PathCchCombine
0x1800103ce  mov     edi, eax
0x1800103d0  test    eax, eax
0x1800103d2  jns     short loc_180010411
0x1800103d4  mov     rcx, [rsp+278h]; this
0x1800103dc  mov     r9d, eax; char *
0x1800103df  lea     r8, aOnecoreBaseTim_2; "onecore\\base\\time\\autotime\\timeserv"...
0x1800103e6  mov     edx, 22Ah; void *
0x1800103eb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800103f0  nop
0x1800103f1  mov     rcx, [rsp+278h+pv]; pv
0x1800103f6  mov     [rsp+278h+pv], 0
0x1800103ff  test    rcx, rcx
0x180010402  jz      short loc_18001040A
0x180010404  call    cs:__imp_CoTaskMemFree
0x18001040a  mov     eax, edi
0x18001040c  jmp     loc_1800104F1
0x180010411  xorps   xmm0, xmm0
0x180010414  movdqu  [rsp+278h+var_250], xmm0
0x18001041a  mov     r9d, 20006h; unsigned int
0x180010420  lea     r8, aHklmSystemCont; "HKLM\\System\\ControlSet001\\Services\\"...
0x180010427  lea     rdx, aW32timeconfig; "W32TimeConfig"
0x18001042e  lea     rcx, [rsp+278h+var_250]; this
0x180010433  call    ?Create@RegKey@@QEAAXPEBG0K@Z; RegKey::Create(ushort const *,ushort const *,ulong)
0x180010438  lea     r8, [rsp+278h+pszPathOut]; unsigned __int16 *
0x18001043d  lea     rdx, aFilelogname; "FileLogName"
0x180010444  lea     rcx, [rsp+278h+var_250]; this
0x180010449  call    ?SetString@RegKey@@QEBAXPEBG0@Z; RegKey::SetString(ushort const *,ushort const *)
0x18001044e  lea     rcx, [rsp+278h+var_250]; this
0x180010453  call    ?SetDword@RegKey@@QEBAXPEBGK@Z; RegKey::SetDword(ushort const *,ulong)
0x180010458  lea     r8, a0300; "0-300"
0x18001045f  lea     rdx, aFilelogentries; "FileLogEntries"
0x180010466  lea     rcx, [rsp+278h+var_250]; this
0x18001046b  call    ?SetString@RegKey@@QEBAXPEBG0@Z; RegKey::SetString(ushort const *,ushort const *)
0x180010470  lea     rcx, [rsp+278h+pszPathOut]; pObjectName
0x180010475  call    CreateAndAclLogFile
0x18001047a  mov     edi, eax
0x18001047c  test    eax, eax
0x18001047e  jns     short loc_1800104C5
0x180010480  mov     rcx, [rsp+278h]; this
0x180010488  mov     r9d, eax; char *
0x18001048b  lea     r8, aOnecoreBaseTim_2; "onecore\\base\\time\\autotime\\timeserv"...
0x180010492  mov     edx, 23Ah; void *
0x180010497  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001049c  nop
0x18001049d  lea     rcx, [rsp+278h+var_250]; this
0x1800104a2  call    ??1RegKey@@QEAA@XZ; RegKey::~RegKey(void)
0x1800104a7  nop
0x1800104a8  mov     rcx, [rsp+278h+pv]; pv
0x1800104ad  mov     [rsp+278h+pv], 0
0x1800104b6  test    rcx, rcx
0x1800104b9  jz      short loc_1800104C1
0x1800104bb  call    cs:__imp_CoTaskMemFree
0x1800104c1  mov     eax, edi
0x1800104c3  jmp     short loc_1800104F1
0x1800104c5  lea     rcx, [rsp+278h+var_250]; this
0x1800104ca  call    ??1RegKey@@QEAA@XZ; RegKey::~RegKey(void)
0x1800104cf  nop
0x1800104d0  mov     rcx, [rsp+278h+pv]; pv
0x1800104d5  mov     [rsp+278h+pv], 0
0x1800104de  test    rcx, rcx
0x1800104e1  jz      short loc_1800104E9
0x1800104e3  call    cs:__imp_CoTaskMemFree
0x1800104e9  xor     eax, eax
0x1800104eb  jmp     short loc_1800104F1
0x1800104ed  mov     eax, dword ptr [rsp+278h+pv]
0x1800104f1  mov     rcx, [rsp+278h+var_18]
0x1800104f9  xor     rcx, rsp; StackCookie
0x1800104fc  call    __security_check_cookie
0x180010501  add     rsp, 270h
0x180010508  pop     rdi
0x180010509  retn
```
