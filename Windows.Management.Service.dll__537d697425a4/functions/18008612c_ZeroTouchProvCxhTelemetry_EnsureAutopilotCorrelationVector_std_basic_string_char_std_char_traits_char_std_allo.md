# ZeroTouchProvCxhTelemetry::EnsureAutopilotCorrelationVector(std::basic_string<char,std::char_traits<char>,std::allocator<char>> &)

- ea: `0x18008612c`
- end: `0x180086490`
- name: `?EnsureAutopilotCorrelationVector@ZeroTouchProvCxhTelemetry@@CAJAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z`
- size: `868`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180086dd0`

## callees

- `0x18000b8f0`
- `0x18000be20`
- `0x18000c504`
- `0x180067e54`
- `0x180077de0`
- `0x180080984`
- `0x180080bac`
- `0x1800835bc`
- `0x1800845c8`
- `0x1800846f4`
- `0x180084d38`
- `0x180084d80`
- `0x180084db8`
- `0x180084ef8`
- `0x18008612c`
- `0x1800876dc`
- `0x180087850`
- `0x180088144`
- `0x180088ad8`
- `0x180089850`
- `0x180089e58`
- `0x18008a454`
- `0x18008a4b0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800863c4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800863c4`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180086327`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180086327`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800861c5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800861c5`

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
0x18008612c  push    rbp
0x18008612e  push    rbx
0x18008612f  push    rsi
0x180086130  push    rdi
0x180086131  push    r14
0x180086133  lea     rbp, [rsp-1E0h]
0x18008613b  sub     rsp, 2E0h
0x180086142  mov     rax, cs:__security_cookie
0x180086149  xor     rax, rsp
0x18008614c  mov     [rbp+200h+var_30], rax
0x180086153  xor     esi, esi
0x180086155  lea     rcx, [rbp+200h+var_250]
0x180086159  call    ??0?$wstring_convert@V?$codecvt_utf8_utf16@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@QEAA@XZ; std::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>(void)
0x18008615e  nop
0x18008615f  mov     ebx, 102h
0x180086164  mov     r8d, ebx; Size
0x180086167  xor     edx, edx; Val
0x180086169  lea     rcx, [rbp+200h+var_140]; void *
0x180086170  call    memset_0
0x180086175  mov     [rsp+300h+var_2B0], ebx
0x180086179  call    ?ZTPIsStateSeparationEnabled@@YA_NXZ; ZTPIsStateSeparationEnabled(void)
0x18008617e  lea     r14, aSoftwareMicros_16; "Software\\Microsoft\\Provisioning\\Auto"...
0x180086185  lea     rbx, SubKey; "OSData\\Software\\Microsoft\\Provisioni"...
0x18008618c  mov     rdx, rbx
0x18008618f  test    al, al
0x180086191  cmovz   rdx, r14; lpSubKey
0x180086195  lea     rax, [rsp+300h+var_2B0]
0x18008619a  mov     [rsp+300h+pcbData], rax; pcbData
0x18008619f  lea     rax, [rbp+200h+var_140]
0x1800861a6  mov     [rsp+300h+pvData], rax; pvData
0x1800861ab  mov     [rsp+300h+pdwType], rsi; int
0x1800861b0  lea     r9d, [rsi+2]; dwFlags
0x1800861b4  lea     r8, ValueName; "AutopilotCorrelationVector"
0x1800861bb  mov     rdi, 0FFFFFFFF80000002h
0x1800861c2  mov     rcx, rdi; hkey
0x1800861c5  call    cs:__imp_RegGetValueW
0x1800861cc  nop     dword ptr [rax+rax+00h]
0x1800861d1  mov     ecx, eax
0x1800861d3  test    eax, eax
0x1800861d5  jnz     short loc_180086223
0x1800861d7  lea     r9, [rbp+200h+var_140]
0x1800861de  cmp     [rbp+200h+var_140], si
0x1800861e5  jz      short loc_1800861F1
0x1800861e7  add     r9, 2
0x1800861eb  cmp     [r9], si
0x1800861ef  jnz     short loc_1800861E7
0x1800861f1  lea     r8, [rbp+200h+var_140]
0x1800861f8  lea     rdx, [rbp+200h+var_278]
0x1800861fc  lea     rcx, [rbp+200h+var_250]
0x180086200  call    ?to_bytes@?$wstring_convert@V?$codecvt_utf8_utf16@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@QEAA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@PEBG0@Z; std::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::to_bytes(ushort const *,ushort const *)
0x180086205  lea     rdx, [rbp+200h+var_278]
0x180086209  lea     rcx, ?autopilot_cv@?1??GetAutopilotCorrelationVector@ZeroTouchProvCxhTelemetry@@SA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ@4V34@A; std::string `ZeroTouchProvCxhTelemetry::GetAutopilotCorrelationVector(void)'::`2'::autopilot_cv
0x180086210  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x180086215  lea     rcx, [rbp+200h+var_278]
0x180086219  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18008621e  jmp     loc_180086465
0x180086223  add     eax, 0FFFFFFFEh
0x180086226  cmp     eax, 1
0x180086229  jbe     short loc_180086244
0x18008622b  test    ecx, ecx
0x18008622d  jle     short loc_180086238
0x18008622f  movzx   ecx, cx
0x180086232  or      ecx, 80070000h; int
0x180086238  lea     rdx, aAutopilotcorre_0; "AutopilotCorrelationVectorCreationFaile"...
0x18008623f  call    ?LogAutopilotCorrelationVectorCreation@ZeroTouchProvCxhTelemetry@@CAXJPEBD@Z; ZeroTouchProvCxhTelemetry::LogAutopilotCorrelationVectorCreation(long,char const *)
0x180086244  xor     edx, edx; Val
0x180086246  mov     r8d, 81h; Size
0x18008624c  lea     rcx, [rbp+200h+var_1D0]; void *
0x180086250  call    memset_0
0x180086255  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18008625c  mov     ecx, 90h; unsigned __int64
0x180086261  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180086266  mov     [rsp+300h+var_2A0], rax
0x18008626b  test    rax, rax
0x18008626e  jz      short loc_18008627A
0x180086270  mov     rcx, rax; this
0x180086273  call    ??0TraceLoggingCorrelationVector@@QEAA@XZ; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(void)
0x180086278  jmp     short loc_18008627D
0x18008627a  mov     rax, rsi
0x18008627d  mov     [rsp+300h+var_2A0], rax
0x180086282  test    rax, rax
0x180086285  jnz     short loc_1800862B7
0x180086287  mov     ebx, 8007000Eh
0x18008628c  mov     edx, 418h; void *
0x180086291  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\moderndeployment\\au"...
0x180086298  mov     r9d, ebx; char *
0x18008629b  mov     rcx, [rbp+208h]; this
0x1800862a2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800862a7  nop
0x1800862a8  lea     rcx, [rsp+300h+var_2A0]
0x1800862ad  call    ??1?$unique_ptr@VTraceLoggingCorrelationVector@@U?$default_delete@VTraceLoggingCorrelationVector@@@std@@@std@@QEAA@XZ; std::unique_ptr<TraceLoggingCorrelationVector>::~unique_ptr<TraceLoggingCorrelationVector>(void)
0x1800862b2  jmp     loc_180086467
0x1800862b7  mov     rdx, rsi
0x1800862ba  lock xadd [rax+88h], rdx; unsigned __int64
0x1800862c3  lea     r8, [rbp+200h+var_1D0]; char *
0x1800862c7  mov     rcx, rax; this
0x1800862ca  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x1800862cf  test    al, al
0x1800862d1  jnz     short loc_1800862DF
0x1800862d3  mov     ebx, 8000FFFFh
0x1800862d8  mov     edx, 419h
0x1800862dd  jmp     short loc_180086291
0x1800862df  mov     [rsp+300h+hKey], rsi
0x1800862e4  xor     edx, edx
0x1800862e6  lea     rcx, [rsp+300h+hKey]
0x1800862eb  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800862f0  call    ?ZTPIsStateSeparationEnabled@@YA_NXZ; ZTPIsStateSeparationEnabled(void)
0x1800862f5  test    al, al
0x1800862f7  cmovz   rbx, r14
0x1800862fb  mov     [rsp+300h+lpdwDisposition], rsi; lpdwDisposition
0x180086300  lea     rax, [rsp+300h+hKey]
0x180086305  mov     [rsp+300h+phkResult], rax; phkResult
0x18008630a  mov     [rsp+300h+pcbData], rsi; lpSecurityAttributes
0x18008630f  mov     dword ptr [rsp+300h+pvData], 2; samDesired
0x180086317  mov     dword ptr [rsp+300h+pdwType], esi; unsigned int
0x18008631b  xor     r9d, r9d; lpClass
0x18008631e  xor     r8d, r8d; Reserved
0x180086321  mov     rdx, rbx; lpSubKey
0x180086324  mov     rcx, rdi; hKey
0x180086327  call    cs:__imp_RegCreateKeyExW
0x18008632e  nop     dword ptr [rax+rax+00h]
0x180086333  test    eax, eax
0x180086335  jz      short loc_180086363
0x180086337  mov     rcx, [rbp+208h]; this
0x18008633e  mov     r9d, eax; char *
0x180086341  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\moderndeployment\\au"...
0x180086348  mov     edx, 41Ch; void *
0x18008634d  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180086352  mov     ebx, eax
0x180086354  lea     rcx, [rsp+300h+hKey]
0x180086359  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18008635e  jmp     loc_1800862A8
0x180086363  lea     rcx, [rbp+200h+var_1D0]
0x180086367  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18008636b  mov     rax, rdi
0x18008636e  inc     rax
0x180086371  cmp     [rcx+rax], sil
0x180086375  jnz     short loc_18008636E
0x180086377  lea     r9, [rbp+200h+var_1D0]
0x18008637b  add     r9, rax
0x18008637e  lea     r8, [rbp+200h+var_1D0]
0x180086382  lea     rdx, [rsp+300h+var_298]
0x180086387  lea     rcx, [rbp+200h+var_250]
0x18008638b  call    ?from_bytes@?$wstring_convert@V?$codecvt_utf8@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@PEBD0@Z; std::wstring_convert<std::codecvt_utf8<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::from_bytes(char const *,char const *)
0x180086390  nop
0x180086391  mov     eax, [rsp+300h+var_288]
0x180086395  lea     ebx, [rax+rax]
0x180086398  mov     [rsp+300h+var_2B0], ebx
0x18008639c  lea     rcx, [rsp+300h+var_298]
0x1800863a1  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800863a6  mov     dword ptr [rsp+300h+pvData], ebx; cbData
0x1800863aa  mov     [rsp+300h+pdwType], rax; unsigned int
0x1800863af  mov     r9d, 1; dwType
0x1800863b5  xor     r8d, r8d; Reserved
0x1800863b8  lea     rdx, ValueName; "AutopilotCorrelationVector"
0x1800863bf  mov     rcx, [rsp+300h+hKey]; hKey
0x1800863c4  call    cs:__imp_RegSetValueExW
0x1800863cb  nop     dword ptr [rax+rax+00h]
0x1800863d0  test    eax, eax
0x1800863d2  jz      short loc_180086400
0x1800863d4  mov     rcx, [rbp+208h]; this
0x1800863db  mov     r9d, eax; char *
0x1800863de  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800863e5  mov     edx, 420h; void *
0x1800863ea  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800863ef  mov     ebx, eax
0x1800863f1  lea     rcx, [rsp+300h+var_298]
0x1800863f6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800863fb  jmp     loc_180086354
0x180086400  lea     rax, [rbp+200h+var_1D0]
0x180086404  inc     rdi
0x180086407  cmp     [rax+rdi], sil
0x18008640b  jnz     short loc_180086404
0x18008640d  mov     r8, rdi
0x180086410  lea     rdx, [rbp+200h+var_1D0]
0x180086414  lea     rcx, ?autopilot_cv@?1??GetAutopilotCorrelationVector@ZeroTouchProvCxhTelemetry@@SA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ@4V34@A; std::string `ZeroTouchProvCxhTelemetry::GetAutopilotCorrelationVector(void)'::`2'::autopilot_cv
0x18008641b  call    ??$_Assign@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@QEBD_K@Z; std::string::_Assign<char>(char const * const,unsigned __int64)
0x180086420  lea     rdx, [rbp+200h+var_1D0]; char *
0x180086424  xor     ecx, ecx; int
0x180086426  call    ?LogAutopilotCorrelationVectorCreation@ZeroTouchProvCxhTelemetry@@CAXJPEBD@Z; ZeroTouchProvCxhTelemetry::LogAutopilotCorrelationVectorCreation(long,char const *)
0x18008642b  lea     rcx, [rsp+300h+var_298]
0x180086430  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180086435  mov     rdx, rax; unsigned __int16 *
0x180086438  lea     rcx, ValueName; "AutopilotCorrelationVector"
0x18008643f  call    ?LogAutopilotCorrelationData@ZeroTouchProvCxhTelemetry@@SAXPEBG0@Z; ZeroTouchProvCxhTelemetry::LogAutopilotCorrelationData(ushort const *,ushort const *)
0x180086444  nop
0x180086445  lea     rcx, [rsp+300h+var_298]
0x18008644a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18008644f  nop
0x180086450  lea     rcx, [rsp+300h+hKey]
0x180086455  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18008645a  nop
0x18008645b  lea     rcx, [rsp+300h+var_2A0]
0x180086460  call    ??1?$unique_ptr@VTraceLoggingCorrelationVector@@U?$default_delete@VTraceLoggingCorrelationVector@@@std@@@std@@QEAA@XZ; std::unique_ptr<TraceLoggingCorrelationVector>::~unique_ptr<TraceLoggingCorrelationVector>(void)
0x180086465  mov     ebx, esi
0x180086467  lea     rcx, [rbp+200h+var_250]
0x18008646b  call    ??1?$wstring_convert@V?$codecvt_utf8@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@UEAA@XZ; std::wstring_convert<std::codecvt_utf8<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::~wstring_convert<std::codecvt_utf8<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>(void)
0x180086470  mov     eax, ebx
0x180086472  mov     rcx, [rbp+200h+var_30]
0x180086479  xor     rcx, rsp; StackCookie
0x18008647c  call    __security_check_cookie
0x180086481  add     rsp, 2E0h
0x180086488  pop     r14
0x18008648a  pop     rdi
0x18008648b  pop     rsi
0x18008648c  pop     rbx
0x18008648d  pop     rbp
0x18008648e  retn
```
