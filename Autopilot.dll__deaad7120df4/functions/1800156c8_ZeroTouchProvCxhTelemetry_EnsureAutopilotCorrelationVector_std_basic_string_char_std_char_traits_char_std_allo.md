# ZeroTouchProvCxhTelemetry::EnsureAutopilotCorrelationVector(std::basic_string<char,std::char_traits<char>,std::allocator<char>> &)

- ea: `0x1800156c8`
- end: `0x180015ccb`
- name: `?EnsureAutopilotCorrelationVector@ZeroTouchProvCxhTelemetry@@CAJAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z`
- size: `1539`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180015cd4`

## callees

- `0x1800045d0`
- `0x180004638`
- `0x180004a08`
- `0x180004ce0`
- `0x180005356`
- `0x1800053c4`
- `0x1800098db`
- `0x1800098e7`
- `0x180010764`
- `0x180014058`
- `0x180014abc`
- `0x180014c7c`
- `0x1800156c8`
- `0x180015f48`
- `0x1800161c8`
- `0x180016b80`
- `0x1800179b8`
- `0x180017a20`
- `0x1800180b8`
- `0x180018334`
- `0x18002f010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180015989`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180015989`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180015796`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180015796`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015afa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015c3f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015afa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180015c3f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180015abf`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180015abf`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180015b6b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180015b6b`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180015732`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180015a63`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180015732`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180015a63`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 ZeroTouchProvCxhTelemetry::EnsureAutopilotCorrelationVector()
{
  __int64 v0; // rdx
  __int64 v1; // rcx
  char v2; // al
  const WCHAR *v3; // r15
  const WCHAR *v4; // rdx
  LSTATUS ValueW; // eax
  unsigned int v6; // ecx
  _WORD *i; // r9
  TraceLoggingCorrelationVector *v8; // rax
  __int64 v9; // rdx
  __int64 v10; // rcx
  TraceLoggingCorrelationVector *v11; // rbx
  void (__fastcall ***v12)(_QWORD, __int64); // rax
  __int64 v14; // rsi
  size_t v15; // r8
  size_t v16; // rdi
  char v17; // al
  unsigned int v18; // edi
  void (__fastcall ***v19)(_QWORD, __int64); // rax
  __int64 v20; // rax
  char *v21; // rcx
  size_t v22; // rdx
  int v23; // eax
  unsigned int v24; // eax
  __int64 v25; // rax
  const BYTE *v26; // rax
  unsigned int v27; // eax
  __int64 v28; // r8
  void **v29; // rsi
  BYTE **v30; // rdx
  void (__fastcall ***v31)(_QWORD, __int64); // rax
  int pdwType; // [rsp+20h] [rbp-E0h]
  unsigned int pdwTypea; // [rsp+20h] [rbp-E0h]
  unsigned int pdwTypeb; // [rsp+20h] [rbp-E0h]
  DWORD pcbData; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  TraceLoggingCorrelationVector *v37; // [rsp+60h] [rbp-A0h]
  BYTE *lpData[2]; // [rsp+68h] [rbp-98h] BYREF
  int v39; // [rsp+78h] [rbp-88h]
  unsigned __int64 v40; // [rsp+80h] [rbp-80h]
  _QWORD v41[3]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v42; // [rsp+A8h] [rbp-58h]
  char *v43[4]; // [rsp+B0h] [rbp-50h] BYREF
  char *v44[8]; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v45; // [rsp+110h] [rbp+10h] BYREF
  __m128i si128; // [rsp+120h] [rbp+20h]
  char Src[144]; // [rsp+130h] [rbp+30h] BYREF
  _WORD pvData[136]; // [rsp+1C0h] [rbp+C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+328h] [rbp+228h]

  std::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>(v41);
  memset_0(pvData, 0, 0x102u);
  pcbData = 258;
  if ( `ZTPIsStateSeparationEnabled'::`2'::s_HasRun )
  {
    v2 = `ZTPIsStateSeparationEnabled'::`2'::s_Redirection;
  }
  else
  {
    v2 = (unsigned __int8)RtlIsStateSeparationEnabled(v1, v0) != 0;
    `ZTPIsStateSeparationEnabled'::`2'::s_Redirection = v2;
    `ZTPIsStateSeparationEnabled'::`2'::s_HasRun = 1;
  }
  v3 = L"OSData\\Software\\Microsoft\\Provisioning\\AutopilotPolicy";
  v4 = L"OSData\\Software\\Microsoft\\Provisioning\\AutopilotPolicy";
  if ( !v2 )
    v4 = L"Software\\Microsoft\\Provisioning\\AutopilotPolicy";
  ValueW = RegGetValueW(HKEY_LOCAL_MACHINE, v4, L"AutopilotCorrelationVector", 2u, 0, pvData, &pcbData);
  v6 = ValueW;
  if ( !ValueW )
  {
    for ( i = pvData; *i; ++i )
      ;
    std::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::to_bytes(
      v41,
      &v45,
      pvData,
      i);
    std::string::_Tidy_deallocate((char **)&`ZeroTouchProvCxhTelemetry::GetAutopilotCorrelationVector'::`2'::autopilot_cv);
    *(_OWORD *)&`ZeroTouchProvCxhTelemetry::GetAutopilotCorrelationVector'::`2'::autopilot_cv = v45;
    xmmword_180044A68 = (__int128)si128;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOBYTE(v45) = 0;
    std::string::_Tidy_deallocate((char **)&v45);
LABEL_65:
    v41[0] = &std::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::`vftable';
    std::wstring::_Tidy_deallocate(v44);
    std::string::_Tidy_deallocate(v43);
    if ( v42 )
    {
      v31 = (void (__fastcall ***)(_QWORD, __int64))(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
      if ( v31 )
        (**v31)(v31, 1);
    }
    return 0;
  }
  if ( (unsigned int)(ValueW - 2) > 1 )
  {
    if ( ValueW > 0 )
      v6 = (unsigned __int16)ValueW | 0x80070000;
    ZeroTouchProvCxhTelemetry::LogAutopilotCorrelationVectorCreation(v6, "AutopilotCorrelationVectorCreationFailed");
  }
  memset_0(Src, 0, 0x81u);
  v8 = (TraceLoggingCorrelationVector *)operator new(0x90u, (const struct std::nothrow_t *)&std::nothrow);
  v37 = v8;
  if ( v8 )
    v11 = TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(v8);
  else
    v11 = 0;
  v37 = v11;
  if ( !v11 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x418,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\inc\\ZTPLegacyTelemetry.h",
      (const char *)0x8007000ELL,
      pdwType);
    v41[0] = &std::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::`vftable';
    std::wstring::_Tidy_deallocate(v44);
    std::string::_Tidy_deallocate(v43);
    if ( v42 )
    {
      v12 = (void (__fastcall ***)(_QWORD, __int64))(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
      if ( v12 )
        (**v12)(v12, 1);
    }
    return 2147942414LL;
  }
  v14 = _InterlockedExchangeAdd64((volatile signed __int64 *)v11 + 17, 0);
  Src[0] = 0;
  if ( WORD2(v14) )
  {
    v15 = *((unsigned __int8 *)v11 + 130);
    if ( v15 < WORD2(v14) )
    {
      memset_0(Src, 0, v15);
      *(_DWORD *)_o__errno() = 34;
      invalid_parameter_noinfo();
      goto LABEL_31;
    }
    memcpy_0(Src, v11, WORD2(v14));
  }
  v16 = -1;
  if ( v14 < 0 && !(_DWORD)v14 )
  {
    Src[*((unsigned __int8 *)v11 + 129)] = 33;
    Src[*((unsigned __int8 *)v11 + 129) + 1] = 0;
LABEL_28:
    hKey = 0;
    if ( `ZTPIsStateSeparationEnabled'::`2'::s_HasRun )
    {
      v17 = `ZTPIsStateSeparationEnabled'::`2'::s_Redirection;
    }
    else
    {
      v17 = (unsigned __int8)RtlIsStateSeparationEnabled(v10, v9) != 0;
      `ZTPIsStateSeparationEnabled'::`2'::s_Redirection = v17;
      `ZTPIsStateSeparationEnabled'::`2'::s_HasRun = 1;
    }
    if ( !v17 )
      v3 = L"Software\\Microsoft\\Provisioning\\AutopilotPolicy";
    v24 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v3, 0, 0, 0, 2u, 0, &hKey, 0);
    if ( v24 )
    {
      v18 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x41C,
              (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\inc\\ZTPLegacyTelemetry.h",
              (const char *)v24,
              pdwTypea);
    }
    else
    {
      v25 = -1;
      do
        ++v25;
      while ( Src[v25] );
      std::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::from_bytes(
        v41,
        lpData,
        Src,
        &Src[v25]);
      pcbData = 2 * v39;
      v26 = (const BYTE *)lpData;
      if ( v40 > 7 )
        v26 = lpData[0];
      v27 = RegSetValueExW(hKey, L"AutopilotCorrelationVector", 0, 1u, v26, 2 * v39);
      if ( !v27 )
      {
        do
          ++v16;
        while ( Src[v16] );
        if ( v16 > *((_QWORD *)&xmmword_180044A68 + 1) )
        {
          std::string::_Reallocate_for<_lambda_a132b9f505f015b07a26cb4edca31da2_,char const *>(
            &`ZeroTouchProvCxhTelemetry::GetAutopilotCorrelationVector'::`2'::autopilot_cv,
            v16,
            v28,
            Src);
        }
        else
        {
          v29 = &`ZeroTouchProvCxhTelemetry::GetAutopilotCorrelationVector'::`2'::autopilot_cv;
          if ( *((_QWORD *)&xmmword_180044A68 + 1) > 0xFu )
            v29 = (void **)`ZeroTouchProvCxhTelemetry::GetAutopilotCorrelationVector'::`2'::autopilot_cv;
          *(_QWORD *)&xmmword_180044A68 = v16;
          memmove_0(v29, Src, v16);
          *((_BYTE *)v29 + v16) = 0;
        }
        ZeroTouchProvCxhTelemetry::LogAutopilotCorrelationVectorCreation(0, Src);
        v30 = lpData;
        if ( v40 > 7 )
          v30 = (BYTE **)lpData[0];
        ZeroTouchProvCxhTelemetry::LogAutopilotCorrelationData(
          L"AutopilotCorrelationVector",
          (const unsigned __int16 *)v30);
        std::wstring::_Tidy_deallocate((char **)lpData);
        if ( hKey )
          RegCloseKey(hKey);
        operator delete(v11);
        goto LABEL_65;
      }
      v18 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x420,
              (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\inc\\ZTPLegacyTelemetry.h",
              (const char *)v27,
              pdwTypeb);
      std::wstring::_Tidy_deallocate((char **)lpData);
    }
    if ( hKey )
      RegCloseKey(hKey);
    goto LABEL_32;
  }
  v20 = *((unsigned __int8 *)v11 + 129);
  v21 = &Src[v20];
  v22 = *((unsigned __int8 *)v11 + 130) - v20;
  if ( v14 >= 0 )
    v23 = sprintf_s(v21, v22, "%u", (unsigned int)v14);
  else
    v23 = sprintf_s(v21, v22, "%u!", (unsigned int)v14);
  if ( v23 != -1 )
    goto LABEL_28;
LABEL_31:
  v18 = -2147418113;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x419,
    (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\inc\\ZTPLegacyTelemetry.h",
    (const char *)0x8000FFFFLL,
    pdwType);
LABEL_32:
  operator delete(v11);
  v41[0] = &std::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::`vftable';
  std::wstring::_Tidy_deallocate(v44);
  std::string::_Tidy_deallocate(v43);
  if ( v42 )
  {
    v19 = (void (__fastcall ***)(_QWORD, __int64))(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
    if ( v19 )
      (**v19)(v19, 1);
  }
  return v18;
}

```

## disassembly

```asm
0x1800156c8  push    rbp
0x1800156ca  push    rbx
0x1800156cb  push    rsi
0x1800156cc  push    rdi
0x1800156cd  push    r12
0x1800156cf  push    r13
0x1800156d1  push    r14
0x1800156d3  push    r15
0x1800156d5  lea     rbp, [rsp-1E8h]
0x1800156dd  sub     rsp, 2E8h
0x1800156e4  mov     rax, cs:__security_cookie
0x1800156eb  xor     rax, rsp
0x1800156ee  mov     [rbp+220h+var_50], rax
0x1800156f5  xor     r12d, r12d
0x1800156f8  lea     rcx, [rbp+220h+var_290]
0x1800156fc  call    ??0?$wstring_convert@V?$codecvt_utf8_utf16@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@QEAA@XZ; std::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>(void)
0x180015701  nop
0x180015702  mov     ebx, 102h
0x180015707  mov     r8d, ebx; Size
0x18001570a  xor     edx, edx; Val
0x18001570c  lea     rcx, [rbp+220h+var_160]; void *
0x180015713  call    memset_0
0x180015718  mov     [rsp+320h+var_2D0], ebx
0x18001571c  lea     r13d, [r12+1]
0x180015721  cmp     cs:?s_HasRun@?1??ZTPIsStateSeparationEnabled@@YA_NXZ@4_NA, r12b; bool `ZTPIsStateSeparationEnabled(void)'::`2'::s_HasRun
0x180015728  jz      short loc_180015732
0x18001572a  mov     al, cs:?s_Redirection@?1??ZTPIsStateSeparationEnabled@@YA_NXZ@4_NA; bool `ZTPIsStateSeparationEnabled(void)'::`2'::s_Redirection
0x180015730  jmp     short loc_180015750
0x180015732  call    cs:__imp_RtlIsStateSeparationEnabled
0x180015739  nop     dword ptr [rax+rax+00h]
0x18001573e  test    al, al
0x180015740  setnz   al
0x180015743  mov     cs:?s_Redirection@?1??ZTPIsStateSeparationEnabled@@YA_NXZ@4_NA, al; bool `ZTPIsStateSeparationEnabled(void)'::`2'::s_Redirection
0x180015749  mov     cs:?s_HasRun@?1??ZTPIsStateSeparationEnabled@@YA_NXZ@4_NA, r13b; bool `ZTPIsStateSeparationEnabled(void)'::`2'::s_HasRun
0x180015750  lea     rcx, aSoftwareMicros_3; "Software\\Microsoft\\Provisioning\\Auto"...
0x180015757  lea     r15, aOsdataSoftware_1; "OSData\\Software\\Microsoft\\Provisioni"...
0x18001575e  mov     rdx, r15
0x180015761  test    al, al
0x180015763  cmovz   rdx, rcx; lpSubKey
0x180015767  lea     rax, [rsp+320h+var_2D0]
0x18001576c  mov     [rsp+320h+pcbData], rax; pcbData
0x180015771  lea     rax, [rbp+220h+var_160]
0x180015778  mov     [rsp+320h+pvData], rax; pvData
0x18001577d  mov     [rsp+320h+pdwType], r12; int
0x180015782  mov     r9d, 2; dwFlags
0x180015788  lea     r8, aAutopilotcorre; "AutopilotCorrelationVector"
0x18001578f  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180015796  call    cs:__imp_RegGetValueW
0x18001579d  nop     dword ptr [rax+rax+00h]
0x1800157a2  mov     ecx, eax
0x1800157a4  test    eax, eax
0x1800157a6  jnz     short loc_180015818
0x1800157a8  lea     r9, [rbp+220h+var_160]
0x1800157af  cmp     [rbp+220h+var_160], r12w
0x1800157b7  jz      short loc_1800157C3
0x1800157b9  add     r9, 2
0x1800157bd  cmp     [r9], r12w
0x1800157c1  jnz     short loc_1800157B9
0x1800157c3  lea     r8, [rbp+220h+var_160]
0x1800157ca  lea     rdx, [rbp+220h+var_210]
0x1800157ce  lea     rcx, [rbp+220h+var_290]
0x1800157d2  call    ?to_bytes@?$wstring_convert@V?$codecvt_utf8_utf16@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@QEAA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@PEBG0@Z; std::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::to_bytes(ushort const *,ushort const *)
0x1800157d7  lea     rcx, ?autopilot_cv@?1??GetAutopilotCorrelationVector@ZeroTouchProvCxhTelemetry@@SA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ@4V34@A; std::string `ZeroTouchProvCxhTelemetry::GetAutopilotCorrelationVector(void)'::`2'::autopilot_cv
0x1800157de  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800157e3  movups  xmm0, [rbp+220h+var_210]
0x1800157e7  movups  cs:?autopilot_cv@?1??GetAutopilotCorrelationVector@ZeroTouchProvCxhTelemetry@@SA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ@4V34@A, xmm0; std::string `ZeroTouchProvCxhTelemetry::GetAutopilotCorrelationVector(void)'::`2'::autopilot_cv
0x1800157ee  movups  xmm1, [rbp+220h+var_200]
0x1800157f2  movups  cs:xmmword_180044A68, xmm1
0x1800157f9  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x180015801  movdqu  [rbp+220h+var_200], xmm0
0x180015806  mov     byte ptr [rbp+220h+var_210], r12b
0x18001580a  lea     rcx, [rbp+220h+var_210]
0x18001580e  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180015813  jmp     loc_180015C5A
0x180015818  add     eax, 0FFFFFFFEh
0x18001581b  cmp     eax, r13d
0x18001581e  jbe     short loc_180015839
0x180015820  test    ecx, ecx
0x180015822  jle     short loc_18001582D
0x180015824  movzx   ecx, cx
0x180015827  or      ecx, 80070000h; int
0x18001582d  lea     rdx, aAutopilotcorre_0; "AutopilotCorrelationVectorCreationFaile"...
0x180015834  call    ?LogAutopilotCorrelationVectorCreation@ZeroTouchProvCxhTelemetry@@CAXJPEBD@Z; ZeroTouchProvCxhTelemetry::LogAutopilotCorrelationVectorCreation(long,char const *)
0x180015839  xor     edx, edx; Val
0x18001583b  mov     r8d, 81h; Size
0x180015841  lea     rcx, [rbp+220h+Src]; void *
0x180015845  call    memset_0
0x18001584a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180015851  mov     ecx, 90h; unsigned __int64
0x180015856  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001585b  mov     [rsp+320h+var_2C0], rax
0x180015860  test    rax, rax
0x180015863  jz      short loc_180015872
0x180015865  mov     rcx, rax; this
0x180015868  call    ??0TraceLoggingCorrelationVector@@QEAA@XZ; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(void)
0x18001586d  mov     rbx, rax
0x180015870  jmp     short loc_180015875
0x180015872  mov     rbx, r12
0x180015875  mov     [rsp+320h+var_2C0], rbx
0x18001587a  test    rbx, rbx
0x18001587d  jnz     short loc_1800158F2
0x18001587f  mov     rcx, [rbp+228h]; this
0x180015886  mov     ebx, 8007000Eh
0x18001588b  mov     r9d, ebx; char *
0x18001588e  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\moderndeployment\\au"...
0x180015895  mov     edx, 418h; void *
0x18001589a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001589f  nop
0x1800158a0  lea     rax, ??_7?$wstring_convert@V?$codecvt_utf8_utf16@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@6B@; const std::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::`vftable'
0x1800158a7  mov     [rbp+220h+var_290], rax
0x1800158ab  lea     rcx, [rbp+220h+var_250]
0x1800158af  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800158b4  lea     rcx, [rbp+220h+var_270]
0x1800158b8  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800158bd  mov     rcx, [rbp+220h+var_278]
0x1800158c1  test    rcx, rcx
0x1800158c4  jz      short loc_1800158EB
0x1800158c6  mov     rax, [rcx]
0x1800158c9  mov     rax, [rax+10h]
0x1800158cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800158d2  mov     r8, rax
0x1800158d5  test    rax, rax
0x1800158d8  jz      short loc_1800158EB
0x1800158da  mov     rcx, [rax]
0x1800158dd  mov     rax, [rcx]
0x1800158e0  mov     edx, r13d
0x1800158e3  mov     rcx, r8
0x1800158e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800158eb  mov     eax, ebx
0x1800158ed  jmp     loc_180015CA7
0x1800158f2  mov     rsi, r12
0x1800158f5  lock xadd [rbx+88h], rsi
0x1800158fe  test    rsi, rsi
0x180015901  sets    r14b
0x180015905  mov     rax, rsi
0x180015908  shr     rax, 20h
0x18001590c  mov     [rbp+220h+Src], r12b
0x180015910  test    ax, ax
0x180015913  jz      short loc_180015934
0x180015915  movzx   r8d, byte ptr [rbx+82h]; Size
0x18001591d  movzx   ecx, ax
0x180015920  cmp     r8, rcx
0x180015923  jb      short loc_18001597E
0x180015925  mov     r8d, ecx; Size
0x180015928  mov     rdx, rbx; Src
0x18001592b  lea     rcx, [rbp+220h+Src]; void *
0x18001592f  call    memcpy_0
0x180015934  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180015938  test    r14b, r14b
0x18001593b  jz      loc_180015A21
0x180015941  test    esi, esi
0x180015943  jnz     loc_180015A21
0x180015949  movzx   eax, byte ptr [rbx+81h]
0x180015950  mov     [rbp+rax+220h+Src], 21h ; '!'
0x180015955  movzx   eax, byte ptr [rbx+81h]
0x18001595c  mov     [rbp+rax+220h+var_1EF], r12b
0x180015961  mov     [rsp+320h+hKey], r12
0x180015966  cmp     cs:?s_HasRun@?1??ZTPIsStateSeparationEnabled@@YA_NXZ@4_NA, r12b; bool `ZTPIsStateSeparationEnabled(void)'::`2'::s_HasRun
0x18001596d  jz      loc_180015A63
0x180015973  mov     al, cs:?s_Redirection@?1??ZTPIsStateSeparationEnabled@@YA_NXZ@4_NA; bool `ZTPIsStateSeparationEnabled(void)'::`2'::s_Redirection
0x180015979  jmp     loc_180015A81
0x18001597e  xor     edx, edx; Val
0x180015980  lea     rcx, [rbp+220h+Src]; void *
0x180015984  call    memset_0
0x180015989  call    cs:__imp__o__errno
0x180015990  nop     dword ptr [rax+rax+00h]
0x180015995  mov     dword ptr [rax], 22h ; '"'
0x18001599b  call    _invalid_parameter_noinfo
0x1800159a0  mov     rcx, [rbp+228h]; this
0x1800159a7  mov     edi, 8000FFFFh
0x1800159ac  mov     r9d, edi; char *
0x1800159af  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800159b6  mov     edx, 419h; void *
0x1800159bb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800159c0  nop
0x1800159c1  mov     edx, 90h; unsigned __int64
0x1800159c6  mov     rcx, rbx; void *
0x1800159c9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800159ce  nop
0x1800159cf  lea     rax, ??_7?$wstring_convert@V?$codecvt_utf8_utf16@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@6B@; const std::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::`vftable'
0x1800159d6  mov     [rbp+220h+var_290], rax
0x1800159da  lea     rcx, [rbp+220h+var_250]
0x1800159de  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800159e3  lea     rcx, [rbp+220h+var_270]
0x1800159e7  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800159ec  mov     rcx, [rbp+220h+var_278]
0x1800159f0  test    rcx, rcx
0x1800159f3  jz      short loc_180015A1A
0x1800159f5  mov     rax, [rcx]
0x1800159f8  mov     rax, [rax+10h]
0x1800159fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015a01  mov     r8, rax
0x180015a04  test    rax, rax
0x180015a07  jz      short loc_180015A1A
0x180015a09  mov     rcx, [rax]
0x180015a0c  mov     rax, [rcx]
0x180015a0f  mov     edx, r13d
0x180015a12  mov     rcx, r8
0x180015a15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015a1a  mov     eax, edi
0x180015a1c  jmp     loc_180015CA7
0x180015a21  movzx   eax, byte ptr [rbx+81h]
0x180015a28  lea     rcx, [rbp+220h+Src]
0x180015a2c  add     rcx, rax; Buffer
0x180015a2f  movzx   edx, byte ptr [rbx+82h]
0x180015a36  sub     rdx, rax; BufferCount
0x180015a39  mov     r9d, esi
0x180015a3c  test    r14b, r14b
0x180015a3f  jz      short loc_180015A5A
0x180015a41  lea     r8, Format; "%u!"
0x180015a48  call    sprintf_s
0x180015a4d  cmp     eax, edi
0x180015a4f  jz      loc_1800159A0
0x180015a55  jmp     loc_180015961
0x180015a5a  lea     r8, aU_0; "%u"
0x180015a61  jmp     short loc_180015A48
0x180015a63  call    cs:__imp_RtlIsStateSeparationEnabled
0x180015a6a  nop     dword ptr [rax+rax+00h]
0x180015a6f  test    al, al
0x180015a71  setnz   al
0x180015a74  mov     cs:?s_Redirection@?1??ZTPIsStateSeparationEnabled@@YA_NXZ@4_NA, al; bool `ZTPIsStateSeparationEnabled(void)'::`2'::s_Redirection
0x180015a7a  mov     cs:?s_HasRun@?1??ZTPIsStateSeparationEnabled@@YA_NXZ@4_NA, r13b; bool `ZTPIsStateSeparationEnabled(void)'::`2'::s_HasRun
0x180015a81  test    al, al
0x180015a83  lea     rax, aSoftwareMicros_3; "Software\\Microsoft\\Provisioning\\Auto"...
0x180015a8a  cmovz   r15, rax
0x180015a8e  mov     [rsp+320h+lpdwDisposition], r12; lpdwDisposition
0x180015a93  lea     rax, [rsp+320h+hKey]
0x180015a98  mov     [rsp+320h+phkResult], rax; phkResult
0x180015a9d  mov     [rsp+320h+pcbData], r12; lpSecurityAttributes
0x180015aa2  mov     dword ptr [rsp+320h+pvData], 2; samDesired
0x180015aaa  mov     dword ptr [rsp+320h+pdwType], r12d; unsigned int
0x180015aaf  xor     r9d, r9d; lpClass
0x180015ab2  xor     r8d, r8d; Reserved
0x180015ab5  mov     rdx, r15; lpSubKey
0x180015ab8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180015abf  call    cs:__imp_RegCreateKeyExW
0x180015ac6  nop     dword ptr [rax+rax+00h]
0x180015acb  test    eax, eax
0x180015acd  jz      short loc_180015B0B
0x180015acf  mov     rcx, [rbp+228h]; this
0x180015ad6  mov     r9d, eax; char *
0x180015ad9  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\moderndeployment\\au"...
0x180015ae0  mov     edx, 41Ch; void *
0x180015ae5  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180015aea  mov     edi, eax
0x180015aec  mov     rcx, [rsp+320h+hKey]; hKey
0x180015af1  test    rcx, rcx
0x180015af4  jz      loc_1800159C1
0x180015afa  call    cs:__imp_RegCloseKey
0x180015b01  nop     dword ptr [rax+rax+00h]
0x180015b06  jmp     loc_1800159C1
0x180015b0b  lea     rcx, [rbp+220h+Src]
0x180015b0f  mov     rax, rdi
0x180015b12  inc     rax
0x180015b15  cmp     [rcx+rax], r12b
0x180015b19  jnz     short loc_180015B12
0x180015b1b  lea     r9, [rbp+220h+Src]
0x180015b1f  add     r9, rax
0x180015b22  lea     r8, [rbp+220h+Src]
0x180015b26  lea     rdx, [rsp+320h+lpData]
0x180015b2b  lea     rcx, [rbp+220h+var_290]
0x180015b2f  call    ?from_bytes@?$wstring_convert@V?$codecvt_utf8_utf16@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@PEBD0@Z; std::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::from_bytes(char const *,char const *)
0x180015b34  nop
0x180015b35  mov     eax, [rsp+320h+var_2A8]
0x180015b39  lea     ecx, [rax+rax]
0x180015b3c  mov     [rsp+320h+var_2D0], ecx
0x180015b40  lea     rax, [rsp+320h+lpData]
0x180015b45  cmp     [rbp+220h+var_2A0], 7
0x180015b4a  cmova   rax, [rsp+320h+lpData]
0x180015b50  mov     dword ptr [rsp+320h+pvData], ecx; cbData
0x180015b54  mov     [rsp+320h+pdwType], rax; unsigned int
0x180015b59  mov     r9d, r13d; dwType
0x180015b5c  xor     r8d, r8d; Reserved
0x180015b5f  lea     rdx, aAutopilotcorre; "AutopilotCorrelationVector"
0x180015b66  mov     rcx, [rsp+320h+hKey]; hKey
0x180015b6b  call    cs:__imp_RegSetValueExW
0x180015b72  nop     dword ptr [rax+rax+00h]
0x180015b77  test    eax, eax
0x180015b79  jz      short loc_180015BA7
0x180015b7b  mov     rcx, [rbp+228h]; this
0x180015b82  mov     r9d, eax; char *
0x180015b85  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\moderndeployment\\au"...
0x180015b8c  mov     edx, 420h; void *
0x180015b91  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180015b96  mov     edi, eax
0x180015b98  lea     rcx, [rsp+320h+lpData]
0x180015b9d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180015ba2  jmp     loc_180015AEC
0x180015ba7  lea     rax, [rbp+220h+Src]
0x180015bab  inc     rdi
0x180015bae  cmp     [rax+rdi], r12b
0x180015bb2  jnz     short loc_180015BAB
0x180015bb4  mov     rax, qword ptr cs:xmmword_180044A68+8
0x180015bbb  cmp     rdi, rax
0x180015bbe  ja      short loc_180015BEF
0x180015bc0  lea     rsi, ?autopilot_cv@?1??GetAutopilotCorrelationVector@ZeroTouchProvCxhTelemetry@@SA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ@4V34@A; std::string `ZeroTouchProvCxhTelemetry::GetAutopilotCorrelationVector(void)'::`2'::autopilot_cv
0x180015bc7  cmp     rax, 0Fh
0x180015bcb  cmova   rsi, qword ptr cs:?autopilot_cv@?1??GetAutopilotCorrelationVector@ZeroTouchProvCxhTelemetry@@SA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ@4V34@A; std::string `ZeroTouchProvCxhTelemetry::GetAutopilotCorrelationVector(void)'::`2'::autopilot_cv
0x180015bd3  mov     qword ptr cs:xmmword_180044A68, rdi
0x180015bda  mov     r8, rdi; Size
  ... truncated ...
```
