# ZeroTouchProvCxhTelemetry::EnsureAutopilotCorrelationVector(std::basic_string<char,std::char_traits<char>,std::allocator<char>> &)

- ea: `0x18008548c`
- end: `0x1800857dd`
- name: `?EnsureAutopilotCorrelationVector@ZeroTouchProvCxhTelemetry@@CAJAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z`
- size: `849`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800860c4`

## callees

- `0x18000b820`
- `0x18000bd50`
- `0x18000c414`
- `0x180067a54`
- `0x18007755c`
- `0x18007ff90`
- `0x18008019c`
- `0x180082a40`
- `0x180083a0c`
- `0x180083b94`
- `0x1800841c4`
- `0x180084208`
- `0x180084238`
- `0x180084370`
- `0x18008548c`
- `0x180086968`
- `0x180086ad4`
- `0x1800873a4`
- `0x180087cc8`
- `0x1800889a0`
- `0x180088fa4`
- `0x180089614`
- `0x180089668`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180085718`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180085718`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180085681`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180085681`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180085525`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180085525`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 ZeroTouchProvCxhTelemetry::EnsureAutopilotCorrelationVector()
{
  bool v0; // al
  const WCHAR *v1; // rbx
  const WCHAR *v2; // rdx
  LSTATUS ValueW; // eax
  unsigned int v4; // ecx
  _WORD *i; // r9
  TraceLoggingCorrelationVector *v6; // rax
  volatile signed __int64 *v7; // rax
  unsigned int v8; // ebx
  __int64 v9; // rdx
  unsigned int v10; // eax
  __int64 v11; // rdi
  __int64 v12; // rax
  DWORD v13; // ebx
  const BYTE *v14; // rax
  unsigned int v15; // eax
  const unsigned __int16 *v16; // rax
  int pdwType; // [rsp+20h] [rbp-E0h]
  unsigned int pdwTypea; // [rsp+20h] [rbp-E0h]
  unsigned int pdwTypeb; // [rsp+20h] [rbp-E0h]
  DWORD pcbData; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  void *v23; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v24[16]; // [rsp+68h] [rbp-98h] BYREF
  int v25; // [rsp+78h] [rbp-88h]
  _BYTE v26[40]; // [rsp+88h] [rbp-78h] BYREF
  char v27[128]; // [rsp+B0h] [rbp-50h] BYREF
  char v28[144]; // [rsp+130h] [rbp+30h] BYREF
  _WORD pvData[136]; // [rsp+1C0h] [rbp+C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+308h] [rbp+208h]

  std::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>(v27);
  memset_0(pvData, 0, 0x102u);
  pcbData = 258;
  v0 = ZTPIsStateSeparationEnabled();
  v1 = L"OSData\\Software\\Microsoft\\Provisioning\\AutopilotPolicy";
  v2 = L"OSData\\Software\\Microsoft\\Provisioning\\AutopilotPolicy";
  if ( !v0 )
    v2 = L"Software\\Microsoft\\Provisioning\\AutopilotPolicy";
  ValueW = RegGetValueW(HKEY_LOCAL_MACHINE, v2, L"AutopilotCorrelationVector", 2u, 0, pvData, &pcbData);
  v4 = ValueW;
  if ( !ValueW )
  {
    for ( i = pvData; *i; ++i )
      ;
    std::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::to_bytes(
      v27,
      v26,
      pvData,
      i);
    std::string::operator=(`ZeroTouchProvCxhTelemetry::GetAutopilotCorrelationVector'::`2'::autopilot_cv, v26);
    std::string::_Tidy_deallocate(v26);
    goto LABEL_31;
  }
  if ( (unsigned int)(ValueW - 2) > 1 )
  {
    if ( ValueW > 0 )
      v4 = (unsigned __int16)ValueW | 0x80070000;
    ZeroTouchProvCxhTelemetry::LogAutopilotCorrelationVectorCreation(v4, "AutopilotCorrelationVectorCreationFailed");
  }
  memset_0(v28, 0, 0x81u);
  v6 = (TraceLoggingCorrelationVector *)operator new(0x90u, (const struct std::nothrow_t *)&std::nothrow);
  v23 = v6;
  if ( v6 )
    v7 = (volatile signed __int64 *)TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(v6);
  else
    v7 = 0;
  v23 = (void *)v7;
  if ( !v7 )
  {
    v8 = -2147024882;
    v9 = 1048;
LABEL_16:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\inc\\ZTPLegacyTelemetry.h",
      (const char *)v8,
      pdwType);
    goto LABEL_17;
  }
  if ( !TraceLoggingCorrelationVector::ToStringImpl(
          (TraceLoggingCorrelationVector *)v7,
          _InterlockedExchangeAdd64(v7 + 17, 0),
          v28) )
  {
    v8 = -2147418113;
    v9 = 1049;
    goto LABEL_16;
  }
  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  if ( !ZTPIsStateSeparationEnabled() )
    v1 = L"Software\\Microsoft\\Provisioning\\AutopilotPolicy";
  v10 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v1, 0, 0, 0, 2u, 0, &hKey, 0);
  if ( v10 )
  {
    v8 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x41C,
           (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\inc\\ZTPLegacyTelemetry.h",
           (const char *)v10,
           pdwTypea);
  }
  else
  {
    v11 = -1;
    v12 = -1;
    do
      ++v12;
    while ( v28[v12] );
    std::wstring_convert<std::codecvt_utf8<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::from_bytes(
      v27,
      v24,
      v28,
      &v28[v12]);
    v13 = 2 * v25;
    pcbData = 2 * v25;
    v14 = (const BYTE *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v24);
    v15 = RegSetValueExW(hKey, L"AutopilotCorrelationVector", 0, 1u, v14, v13);
    if ( !v15 )
    {
      do
        ++v11;
      while ( v28[v11] );
      std::string::_Assign<char>(
        `ZeroTouchProvCxhTelemetry::GetAutopilotCorrelationVector'::`2'::autopilot_cv,
        v28,
        v11);
      ZeroTouchProvCxhTelemetry::LogAutopilotCorrelationVectorCreation(0, v28);
      v16 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v24);
      ZeroTouchProvCxhTelemetry::LogAutopilotCorrelationData(L"AutopilotCorrelationVector", v16);
      std::wstring::_Tidy_deallocate(v24);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      std::unique_ptr<TraceLoggingCorrelationVector>::~unique_ptr<TraceLoggingCorrelationVector>(&v23);
LABEL_31:
      v8 = 0;
      goto LABEL_32;
    }
    v8 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x420,
           (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\inc\\ZTPLegacyTelemetry.h",
           (const char *)v15,
           pdwTypeb);
    std::wstring::_Tidy_deallocate(v24);
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
LABEL_17:
  std::unique_ptr<TraceLoggingCorrelationVector>::~unique_ptr<TraceLoggingCorrelationVector>(&v23);
LABEL_32:
  std::wstring_convert<std::codecvt_utf8<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::~wstring_convert<std::codecvt_utf8<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>(v27);
  return v8;
}

```

## disassembly

```asm
0x18008548c  push    rbp
0x18008548e  push    rbx
0x18008548f  push    rsi
0x180085490  push    rdi
0x180085491  push    r14
0x180085493  lea     rbp, [rsp-1E0h]
0x18008549b  sub     rsp, 2E0h
0x1800854a2  mov     rax, cs:__security_cookie
0x1800854a9  xor     rax, rsp
0x1800854ac  mov     [rbp+200h+var_30], rax
0x1800854b3  xor     esi, esi
0x1800854b5  lea     rcx, [rbp+200h+var_250]
0x1800854b9  call    ??0?$wstring_convert@V?$codecvt_utf8_utf16@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@QEAA@XZ; std::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>(void)
0x1800854be  nop
0x1800854bf  mov     ebx, 102h
0x1800854c4  mov     r8d, ebx; Size
0x1800854c7  xor     edx, edx; Val
0x1800854c9  lea     rcx, [rbp+200h+var_140]; void *
0x1800854d0  call    memset_0
0x1800854d5  mov     [rsp+300h+var_2B0], ebx
0x1800854d9  call    ?ZTPIsStateSeparationEnabled@@YA_NXZ; ZTPIsStateSeparationEnabled(void)
0x1800854de  lea     r14, aSoftwareMicros_16; "Software\\Microsoft\\Provisioning\\Auto"...
0x1800854e5  lea     rbx, SubKey; "OSData\\Software\\Microsoft\\Provisioni"...
0x1800854ec  mov     rdx, rbx
0x1800854ef  test    al, al
0x1800854f1  cmovz   rdx, r14; lpSubKey
0x1800854f5  lea     rax, [rsp+300h+var_2B0]
0x1800854fa  mov     [rsp+300h+pcbData], rax; pcbData
0x1800854ff  lea     rax, [rbp+200h+var_140]
0x180085506  mov     [rsp+300h+pvData], rax; pvData
0x18008550b  mov     [rsp+300h+pdwType], rsi; int
0x180085510  lea     r9d, [rsi+2]; dwFlags
0x180085514  lea     r8, ValueName; "AutopilotCorrelationVector"
0x18008551b  mov     rdi, 0FFFFFFFF80000002h
0x180085522  mov     rcx, rdi; hkey
0x180085525  call    cs:__imp_RegGetValueW
0x18008552b  mov     ecx, eax
0x18008552d  test    eax, eax
0x18008552f  jnz     short loc_18008557D
0x180085531  lea     r9, [rbp+200h+var_140]
0x180085538  cmp     [rbp+200h+var_140], si
0x18008553f  jz      short loc_18008554B
0x180085541  add     r9, 2
0x180085545  cmp     [r9], si
0x180085549  jnz     short loc_180085541
0x18008554b  lea     r8, [rbp+200h+var_140]
0x180085552  lea     rdx, [rbp+200h+var_278]
0x180085556  lea     rcx, [rbp+200h+var_250]
0x18008555a  call    ?to_bytes@?$wstring_convert@V?$codecvt_utf8_utf16@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@QEAA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@PEBG0@Z; std::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::to_bytes(ushort const *,ushort const *)
0x18008555f  lea     rdx, [rbp+200h+var_278]
0x180085563  lea     rcx, ?autopilot_cv@?1??GetAutopilotCorrelationVector@ZeroTouchProvCxhTelemetry@@SA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ@4V34@A; std::string `ZeroTouchProvCxhTelemetry::GetAutopilotCorrelationVector(void)'::`2'::autopilot_cv
0x18008556a  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x18008556f  lea     rcx, [rbp+200h+var_278]
0x180085573  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180085578  jmp     loc_1800857B3
0x18008557d  add     eax, 0FFFFFFFEh
0x180085580  cmp     eax, 1
0x180085583  jbe     short loc_18008559E
0x180085585  test    ecx, ecx
0x180085587  jle     short loc_180085592
0x180085589  movzx   ecx, cx
0x18008558c  or      ecx, 80070000h; int
0x180085592  lea     rdx, aAutopilotcorre_0; "AutopilotCorrelationVectorCreationFaile"...
0x180085599  call    ?LogAutopilotCorrelationVectorCreation@ZeroTouchProvCxhTelemetry@@CAXJPEBD@Z; ZeroTouchProvCxhTelemetry::LogAutopilotCorrelationVectorCreation(long,char const *)
0x18008559e  xor     edx, edx; Val
0x1800855a0  mov     r8d, 81h; Size
0x1800855a6  lea     rcx, [rbp+200h+var_1D0]; void *
0x1800855aa  call    memset_0
0x1800855af  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800855b6  mov     ecx, 90h; unsigned __int64
0x1800855bb  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800855c0  mov     [rsp+300h+var_2A0], rax
0x1800855c5  test    rax, rax
0x1800855c8  jz      short loc_1800855D4
0x1800855ca  mov     rcx, rax; this
0x1800855cd  call    ??0TraceLoggingCorrelationVector@@QEAA@XZ; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(void)
0x1800855d2  jmp     short loc_1800855D7
0x1800855d4  mov     rax, rsi
0x1800855d7  mov     [rsp+300h+var_2A0], rax
0x1800855dc  test    rax, rax
0x1800855df  jnz     short loc_180085611
0x1800855e1  mov     ebx, 8007000Eh
0x1800855e6  mov     edx, 418h; void *
0x1800855eb  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800855f2  mov     r9d, ebx; char *
0x1800855f5  mov     rcx, [rbp+208h]; this
0x1800855fc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180085601  nop
0x180085602  lea     rcx, [rsp+300h+var_2A0]
0x180085607  call    ??1?$unique_ptr@VTraceLoggingCorrelationVector@@U?$default_delete@VTraceLoggingCorrelationVector@@@std@@@std@@QEAA@XZ; std::unique_ptr<TraceLoggingCorrelationVector>::~unique_ptr<TraceLoggingCorrelationVector>(void)
0x18008560c  jmp     loc_1800857B5
0x180085611  mov     rdx, rsi
0x180085614  lock xadd [rax+88h], rdx; unsigned __int64
0x18008561d  lea     r8, [rbp+200h+var_1D0]; char *
0x180085621  mov     rcx, rax; this
0x180085624  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x180085629  test    al, al
0x18008562b  jnz     short loc_180085639
0x18008562d  mov     ebx, 8000FFFFh
0x180085632  mov     edx, 419h
0x180085637  jmp     short loc_1800855EB
0x180085639  mov     [rsp+300h+hKey], rsi
0x18008563e  xor     edx, edx
0x180085640  lea     rcx, [rsp+300h+hKey]
0x180085645  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18008564a  call    ?ZTPIsStateSeparationEnabled@@YA_NXZ; ZTPIsStateSeparationEnabled(void)
0x18008564f  test    al, al
0x180085651  cmovz   rbx, r14
0x180085655  mov     [rsp+300h+lpdwDisposition], rsi; lpdwDisposition
0x18008565a  lea     rax, [rsp+300h+hKey]
0x18008565f  mov     [rsp+300h+phkResult], rax; phkResult
0x180085664  mov     [rsp+300h+pcbData], rsi; lpSecurityAttributes
0x180085669  mov     dword ptr [rsp+300h+pvData], 2; samDesired
0x180085671  mov     dword ptr [rsp+300h+pdwType], esi; unsigned int
0x180085675  xor     r9d, r9d; lpClass
0x180085678  xor     r8d, r8d; Reserved
0x18008567b  mov     rdx, rbx; lpSubKey
0x18008567e  mov     rcx, rdi; hKey
0x180085681  call    cs:__imp_RegCreateKeyExW
0x180085687  test    eax, eax
0x180085689  jz      short loc_1800856B7
0x18008568b  mov     rcx, [rbp+208h]; this
0x180085692  mov     r9d, eax; char *
0x180085695  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\moderndeployment\\au"...
0x18008569c  mov     edx, 41Ch; void *
0x1800856a1  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800856a6  mov     ebx, eax
0x1800856a8  lea     rcx, [rsp+300h+hKey]
0x1800856ad  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800856b2  jmp     loc_180085602
0x1800856b7  lea     rcx, [rbp+200h+var_1D0]
0x1800856bb  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800856bf  mov     rax, rdi
0x1800856c2  inc     rax
0x1800856c5  cmp     [rcx+rax], sil
0x1800856c9  jnz     short loc_1800856C2
0x1800856cb  lea     r9, [rbp+200h+var_1D0]
0x1800856cf  add     r9, rax
0x1800856d2  lea     r8, [rbp+200h+var_1D0]
0x1800856d6  lea     rdx, [rsp+300h+var_298]
0x1800856db  lea     rcx, [rbp+200h+var_250]
0x1800856df  call    ?from_bytes@?$wstring_convert@V?$codecvt_utf8@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@PEBD0@Z; std::wstring_convert<std::codecvt_utf8<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::from_bytes(char const *,char const *)
0x1800856e4  nop
0x1800856e5  mov     eax, [rsp+300h+var_288]
0x1800856e9  lea     ebx, [rax+rax]
0x1800856ec  mov     [rsp+300h+var_2B0], ebx
0x1800856f0  lea     rcx, [rsp+300h+var_298]
0x1800856f5  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800856fa  mov     dword ptr [rsp+300h+pvData], ebx; cbData
0x1800856fe  mov     [rsp+300h+pdwType], rax; unsigned int
0x180085703  mov     r9d, 1; dwType
0x180085709  xor     r8d, r8d; Reserved
0x18008570c  lea     rdx, ValueName; "AutopilotCorrelationVector"
0x180085713  mov     rcx, [rsp+300h+hKey]; hKey
0x180085718  call    cs:__imp_RegSetValueExW
0x18008571e  test    eax, eax
0x180085720  jz      short loc_18008574E
0x180085722  mov     rcx, [rbp+208h]; this
0x180085729  mov     r9d, eax; char *
0x18008572c  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\moderndeployment\\au"...
0x180085733  mov     edx, 420h; void *
0x180085738  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18008573d  mov     ebx, eax
0x18008573f  lea     rcx, [rsp+300h+var_298]
0x180085744  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180085749  jmp     loc_1800856A8
0x18008574e  lea     rax, [rbp+200h+var_1D0]
0x180085752  inc     rdi
0x180085755  cmp     [rax+rdi], sil
0x180085759  jnz     short loc_180085752
0x18008575b  mov     r8, rdi
0x18008575e  lea     rdx, [rbp+200h+var_1D0]
0x180085762  lea     rcx, ?autopilot_cv@?1??GetAutopilotCorrelationVector@ZeroTouchProvCxhTelemetry@@SA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ@4V34@A; std::string `ZeroTouchProvCxhTelemetry::GetAutopilotCorrelationVector(void)'::`2'::autopilot_cv
0x180085769  call    ??$_Assign@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@QEBD_K@Z; std::string::_Assign<char>(char const * const,unsigned __int64)
0x18008576e  lea     rdx, [rbp+200h+var_1D0]; char *
0x180085772  xor     ecx, ecx; int
0x180085774  call    ?LogAutopilotCorrelationVectorCreation@ZeroTouchProvCxhTelemetry@@CAXJPEBD@Z; ZeroTouchProvCxhTelemetry::LogAutopilotCorrelationVectorCreation(long,char const *)
0x180085779  lea     rcx, [rsp+300h+var_298]
0x18008577e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180085783  mov     rdx, rax; unsigned __int16 *
0x180085786  lea     rcx, ValueName; "AutopilotCorrelationVector"
0x18008578d  call    ?LogAutopilotCorrelationData@ZeroTouchProvCxhTelemetry@@SAXPEBG0@Z; ZeroTouchProvCxhTelemetry::LogAutopilotCorrelationData(ushort const *,ushort const *)
0x180085792  nop
0x180085793  lea     rcx, [rsp+300h+var_298]
0x180085798  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18008579d  nop
0x18008579e  lea     rcx, [rsp+300h+hKey]
0x1800857a3  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800857a8  nop
0x1800857a9  lea     rcx, [rsp+300h+var_2A0]
0x1800857ae  call    ??1?$unique_ptr@VTraceLoggingCorrelationVector@@U?$default_delete@VTraceLoggingCorrelationVector@@@std@@@std@@QEAA@XZ; std::unique_ptr<TraceLoggingCorrelationVector>::~unique_ptr<TraceLoggingCorrelationVector>(void)
0x1800857b3  mov     ebx, esi
0x1800857b5  lea     rcx, [rbp+200h+var_250]
0x1800857b9  call    ??1?$wstring_convert@V?$codecvt_utf8@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@UEAA@XZ; std::wstring_convert<std::codecvt_utf8<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::~wstring_convert<std::codecvt_utf8<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>(void)
0x1800857be  mov     eax, ebx
0x1800857c0  mov     rcx, [rbp+200h+var_30]
0x1800857c7  xor     rcx, rsp; StackCookie
0x1800857ca  call    __security_check_cookie
0x1800857cf  add     rsp, 2E0h
0x1800857d6  pop     r14
0x1800857d8  pop     rdi
0x1800857d9  pop     rsi
0x1800857da  pop     rbx
0x1800857db  pop     rbp
0x1800857dc  retn
```
