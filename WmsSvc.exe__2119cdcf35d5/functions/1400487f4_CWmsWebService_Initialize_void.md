# CWmsWebService::Initialize(void)

- ea: `0x1400487f4`
- end: `0x140048a74`
- name: `?Initialize@CWmsWebService@@AEAAJXZ`
- size: `640`
- prototype: `__int64 __fastcall(CWmsWebService *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x14004c234`

## callees

- `0x1400487f4`
- `0x14004ac94`
- `0x14005bc30`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x140076784`

## import_xrefs

- `ADVAPI32!RegGetValueW` at `0x140048854`
- `ADVAPI32!RegGetValueW` at `0x140048854`
- `KERNEL32!CreateThread` at `0x140048a12`
- `KERNEL32!CreateThread` at `0x140048a12`
- `KERNEL32!CreateEventW` at `0x14004892a`
- `KERNEL32!CreateEventW` at `0x1400489b0`
- `KERNEL32!CreateEventW` at `0x14004892a`
- `KERNEL32!CreateEventW` at `0x1400489b0`
- `KERNEL32!GetLastError` at `0x14004893c`
- `KERNEL32!GetLastError` at `0x1400489c2`
- `KERNEL32!GetLastError` at `0x140048a24`
- `KERNEL32!GetLastError` at `0x14004893c`
- `KERNEL32!GetLastError` at `0x1400489c2`
- `KERNEL32!GetLastError` at `0x140048a24`
- `KERNEL32!IsDebuggerPresent` at `0x1400488b0`
- `KERNEL32!IsDebuggerPresent` at `0x1400488b0`

## string_xrefs

- `0x140048898`: `termsrv\wms\src\devices\wmssvc\wmswebservice.cpp`
- `0x140048881`: `CWmsWebService::Initialize`
- `0x140048953`: `m_hWebServiceReadyEvent != 0`
- `0x140048a3b`: `m_hThreadCertExpiry != 0`
- `0x140048a55`: `CWmsWebService::InitializeDisk Protection is active, not starting certificate expiry thread.\n`

## pseudocode

```c
__int64 __fastcall CWmsWebService::Initialize(CWmsWebService *this)
{
  LSTATUS ValueW; // eax
  signed int started; // ebx
  const unsigned __int16 *v4; // r12
  unsigned int v5; // r15d
  HANDLE EventW; // rax
  signed int LastError; // eax
  HANDLE v8; // rax
  signed int v9; // eax
  HANDLE Thread; // rax
  signed int v11; // eax
  __int64 v13; // [rsp+30h] [rbp-38h]
  int v14; // [rsp+78h] [rbp+10h] BYREF
  int v15; // [rsp+80h] [rbp+18h] BYREF
  DWORD v16; // [rsp+88h] [rbp+20h] BYREF

  v14 = 0;
  v15 = 0;
  v16 = 4;
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"SOFTWARE\\Microsoft\\Windows MultiPoint Server\\Remote Management",
             L"SslCertificateTimeUnitsMinutes",
             0x10u,
             0,
             &v14,
             &v16);
  started = ValueW;
  if ( (ValueW & 0xFFFFFFFD) != 0 )
  {
    if ( ValueW > 0 )
      started = (unsigned __int16)ValueW | 0x80070000;
    v4 = L"(lr == 0L) || (lr == 2L)";
    v5 = 389;
LABEL_5:
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
      v5,
      L"CWmsWebService::Initialize",
      L"CBRAEx",
      v4,
      started);
    if ( IsDebuggerPresent() )
    {
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
        v5,
        L"CWmsWebService::Initialize",
        L"CBRAEx",
        v4,
        started);
    }
    else
    {
      LODWORD(v13) = started;
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmswebservice.cpp",
        v5,
        L"CWmsWebService::Initialize",
        L"CBRAEx",
        v4,
        v13);
    }
    return (unsigned int)started;
  }
  *((_DWORD *)this + 86) = v14 != 0;
  EventW = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)this + 40) = EventW;
  if ( !EventW )
  {
    LastError = GetLastError();
    started = LastError;
    if ( LastError > 0 )
      started = (unsigned __int16)LastError | 0x80070000;
    v4 = L"m_hWebServiceReadyEvent != 0";
    v5 = 395;
    if ( started >= 0 )
      started = -2147467259;
    goto LABEL_5;
  }
  started = CWmsWebService::StartWebService(this);
  if ( started >= 0 )
  {
    started = IsDiskProtectionActive(&v15);
    if ( started >= 0 )
    {
      if ( v15 )
      {
        DEBUGMSG(L"CWmsWebService::InitializeDisk Protection is active, not starting certificate expiry thread.\n");
        return (unsigned int)started;
      }
      v8 = CreateEventW(0, 1, 0, 0);
      *((_QWORD *)this + 39) = v8;
      if ( v8 )
      {
        Thread = CreateThread(0, 0, CWmsWebService::s_ThreadProcCertExpiry, this, 0, 0);
        *((_QWORD *)this + 38) = Thread;
        if ( Thread )
          return (unsigned int)started;
        v11 = GetLastError();
        started = v11;
        if ( v11 > 0 )
          started = (unsigned __int16)v11 | 0x80070000;
        v4 = L"m_hThreadCertExpiry != 0";
        v5 = 414;
        if ( started >= 0 )
          started = -2147467259;
      }
      else
      {
        v9 = GetLastError();
        started = v9;
        if ( v9 > 0 )
          started = (unsigned __int16)v9 | 0x80070000;
        v4 = L"m_hKillEventCertExpiry != 0";
        v5 = 411;
        if ( started >= 0 )
          started = -2147467259;
      }
      goto LABEL_5;
    }
  }
  return (unsigned int)started;
}

```

## disassembly

```asm
0x1400487f4  mov     r11, rsp
0x1400487f7  mov     [r11+8], rbx
0x1400487fb  push    rbp
0x1400487fc  push    rsi
0x1400487fd  push    rdi
0x1400487fe  push    r12
0x140048800  push    r15
0x140048802  sub     rsp, 40h
0x140048806  lea     rax, [r11+20h]
0x14004880a  mov     [rsp+68h+arg_8], 0
0x140048812  mov     [r11-38h], rax
0x140048816  lea     r8, aSslcertificate_3; "SslCertificateTimeUnitsMinutes"
0x14004881d  lea     rax, [r11+10h]
0x140048821  mov     dword ptr [r11+18h], 0
0x140048829  mov     rdi, rcx
0x14004882c  mov     [r11-40h], rax
0x140048830  mov     r9d, 10h; dwFlags
0x140048836  mov     qword ptr [r11-48h], 0
0x14004883e  lea     rdx, aSoftwareMicros_25; "SOFTWARE\\Microsoft\\Windows MultiPoint"...
0x140048845  mov     dword ptr [r11+20h], 4
0x14004884d  mov     rcx, 0FFFFFFFF80000002h; hkey
0x140048854  call    cs:__imp_RegGetValueW
0x14004885a  mov     ebx, eax
0x14004885c  test    eax, 0FFFFFFFDh
0x140048861  jz      loc_140048911
0x140048867  test    eax, eax
0x140048869  jle     short loc_140048874
0x14004886b  movzx   ebx, ax
0x14004886e  or      ebx, 80070000h
0x140048874  lea     r12, aLr0lLr2l; "(lr == 0L) || (lr == 2L)"
0x14004887b  mov     r15d, 185h
0x140048881  lea     rsi, aCwmswebservice_38; "CWmsWebService::Initialize"
0x140048888  mov     dword ptr [rsp+68h+lpThreadId], ebx; int
0x14004888c  lea     rbp, aCbraex; "CBRAEx"
0x140048893  mov     qword ptr [rsp+68h+dwCreationFlags], r12; unsigned __int16 *
0x140048898  lea     rdi, aTermsrvWmsSrcD_25; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x14004889f  mov     r8, rsi; unsigned __int16 *
0x1400488a2  mov     r9, rbp; unsigned __int16 *
0x1400488a5  mov     rcx, rdi; unsigned __int16 *
0x1400488a8  mov     edx, r15d; unsigned int
0x1400488ab  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x1400488b0  call    cs:__imp_IsDebuggerPresent
0x1400488b6  test    eax, eax
0x1400488b8  jz      short loc_1400488E9
0x1400488ba  mov     [rsp+68h+var_30], ebx
0x1400488be  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x1400488c5  mov     [rsp+68h+var_38], r12
0x1400488ca  mov     r9d, r15d
0x1400488cd  mov     [rsp+68h+lpThreadId], rbp
0x1400488d2  mov     r8, rdi
0x1400488d5  mov     ecx, 2; unsigned __int8
0x1400488da  mov     qword ptr [rsp+68h+dwCreationFlags], rsi
0x1400488df  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x1400488e4  jmp     loc_140048A61
0x1400488e9  mov     dword ptr [rsp+68h+var_38], ebx
0x1400488ed  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x1400488f4  mov     [rsp+68h+lpThreadId], r12
0x1400488f9  mov     r9, rsi
0x1400488fc  mov     r8d, r15d
0x1400488ff  mov     qword ptr [rsp+68h+dwCreationFlags], rbp
0x140048904  mov     rdx, rdi
0x140048907  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14004890c  jmp     loc_140048A61
0x140048911  xor     eax, eax
0x140048913  cmp     [rsp+68h+arg_8], eax
0x140048917  setnz   al
0x14004891a  xor     r9d, r9d; lpName
0x14004891d  xor     r8d, r8d; bInitialState
0x140048920  mov     [rdi+158h], eax
0x140048926  xor     edx, edx; bManualReset
0x140048928  xor     ecx, ecx; lpEventAttributes
0x14004892a  call    cs:__imp_CreateEventW
0x140048930  mov     [rdi+140h], rax
0x140048937  test    rax, rax
0x14004893a  jnz     short loc_14004896D
0x14004893c  call    cs:__imp_GetLastError
0x140048942  mov     ebx, eax
0x140048944  test    eax, eax
0x140048946  jle     short loc_140048951
0x140048948  movzx   ebx, ax
0x14004894b  or      ebx, 80070000h
0x140048951  test    ebx, ebx
0x140048953  lea     r12, aMHwebservicere; "m_hWebServiceReadyEvent != 0"
0x14004895a  mov     eax, 80004005h
0x14004895f  mov     r15d, 18Bh
0x140048965  cmovns  ebx, eax
0x140048968  jmp     loc_140048881
0x14004896d  mov     rcx, rdi; this
0x140048970  call    ?StartWebService@CWmsWebService@@AEAAJXZ; CWmsWebService::StartWebService(void)
0x140048975  mov     ebx, eax
0x140048977  test    eax, eax
0x140048979  js      loc_140048A61
0x14004897f  lea     rcx, [rsp+68h+arg_10]; int *
0x140048987  call    ?IsDiskProtectionActive@@YAJPEAH@Z; IsDiskProtectionActive(int *)
0x14004898c  mov     ebx, eax
0x14004898e  test    eax, eax
0x140048990  js      loc_140048A61
0x140048996  cmp     [rsp+68h+arg_10], 0
0x14004899e  jnz     loc_140048A55
0x1400489a4  xor     r9d, r9d; lpName
0x1400489a7  xor     r8d, r8d; bInitialState
0x1400489aa  xor     ecx, ecx; lpEventAttributes
0x1400489ac  lea     edx, [r9+1]; bManualReset
0x1400489b0  call    cs:__imp_CreateEventW
0x1400489b6  mov     [rdi+138h], rax
0x1400489bd  test    rax, rax
0x1400489c0  jnz     short loc_1400489F3
0x1400489c2  call    cs:__imp_GetLastError
0x1400489c8  mov     ebx, eax
0x1400489ca  test    eax, eax
0x1400489cc  jle     short loc_1400489D7
0x1400489ce  movzx   ebx, ax
0x1400489d1  or      ebx, 80070000h
0x1400489d7  test    ebx, ebx
0x1400489d9  lea     r12, aMHkilleventcer; "m_hKillEventCertExpiry != 0"
0x1400489e0  mov     eax, 80004005h
0x1400489e5  mov     r15d, 19Bh
0x1400489eb  cmovns  ebx, eax
0x1400489ee  jmp     loc_140048881
0x1400489f3  mov     [rsp+68h+lpThreadId], 0; lpThreadId
0x1400489fc  lea     r8, ?s_ThreadProcCertExpiry@CWmsWebService@@CAKPEAX@Z; lpStartAddress
0x140048a03  mov     r9, rdi; lpParameter
0x140048a06  mov     [rsp+68h+dwCreationFlags], 0; dwCreationFlags
0x140048a0e  xor     edx, edx; dwStackSize
0x140048a10  xor     ecx, ecx; lpThreadAttributes
0x140048a12  call    cs:__imp_CreateThread
0x140048a18  mov     [rdi+130h], rax
0x140048a1f  test    rax, rax
0x140048a22  jnz     short loc_140048A61
0x140048a24  call    cs:__imp_GetLastError
0x140048a2a  mov     ebx, eax
0x140048a2c  test    eax, eax
0x140048a2e  jle     short loc_140048A39
0x140048a30  movzx   ebx, ax
0x140048a33  or      ebx, 80070000h
0x140048a39  test    ebx, ebx
0x140048a3b  lea     r12, aMHthreadcertex; "m_hThreadCertExpiry != 0"
0x140048a42  mov     eax, 80004005h
0x140048a47  mov     r15d, 19Eh
0x140048a4d  cmovns  ebx, eax
0x140048a50  jmp     loc_140048881
0x140048a55  lea     rcx, aCwmswebservice_60; "CWmsWebService::InitializeDisk Protecti"...
0x140048a5c  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140048a61  mov     eax, ebx
0x140048a63  mov     rbx, [rsp+68h+arg_0]
0x140048a68  add     rsp, 40h
0x140048a6c  pop     r15
0x140048a6e  pop     r12
0x140048a70  pop     rdi
0x140048a71  pop     rsi
0x140048a72  pop     rbp
0x140048a73  retn
```
