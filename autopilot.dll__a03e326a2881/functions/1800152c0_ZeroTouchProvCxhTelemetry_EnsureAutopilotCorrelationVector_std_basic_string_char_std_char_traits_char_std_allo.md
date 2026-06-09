# ZeroTouchProvCxhTelemetry::EnsureAutopilotCorrelationVector(std::basic_string<char,std::char_traits<char>,std::allocator<char>> &)

- ea: `0x1800152c0`
- end: `0x180015892`
- name: `?EnsureAutopilotCorrelationVector@ZeroTouchProvCxhTelemetry@@CAJAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z`
- size: `1490`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180015898`

## callees

- `0x1800045b0`
- `0x180004618`
- `0x1800049f4`
- `0x180004cc0`
- `0x180005306`
- `0x180005374`
- `0x18000994b`
- `0x180009957`
- `0x1800105f4`
- `0x180013cac`
- `0x180014704`
- `0x180014898`
- `0x1800152c0`
- `0x180015af0`
- `0x180015d4c`
- `0x1800166dc`
- `0x180017488`
- `0x1800174f0`
- `0x180017b84`
- `0x180017df8`
- `0x18002e010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180015575`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180015575`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180015388`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180015388`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800156d4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001580d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800156d4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001580d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001569f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001569f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001573f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001573f`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18001532a`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180015649`
- `ntdll!RtlIsStateSeparationEnabled` at `0x18001532a`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180015649`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
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
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // r8
  unsigned int v21; // edi
  void (__fastcall ***v22)(_QWORD, __int64); // rax
  __int64 v23; // rax
  char *v24; // rcx
  size_t v25; // rdx
  int v26; // eax
  unsigned int v27; // eax
  __int64 v28; // rax
  const BYTE *v29; // rax
  unsigned int v30; // eax
  __int64 v31; // r8
  void **v32; // rsi
  BYTE **v33; // rdx
  void (__fastcall ***v34)(_QWORD, __int64); // rax
  int pdwType; // [rsp+20h] [rbp-E0h]
  unsigned int pdwTypea; // [rsp+20h] [rbp-E0h]
  unsigned int pdwTypeb; // [rsp+20h] [rbp-E0h]
  DWORD pcbData; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  TraceLoggingCorrelationVector *v40; // [rsp+60h] [rbp-A0h]
  BYTE *lpData[2]; // [rsp+68h] [rbp-98h] BYREF
  int v42; // [rsp+78h] [rbp-88h]
  unsigned __int64 v43; // [rsp+80h] [rbp-80h]
  _QWORD v44[3]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v45; // [rsp+A8h] [rbp-58h]
  _BYTE v46[32]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v47[64]; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v48; // [rsp+110h] [rbp+10h] BYREF
  __m128i si128; // [rsp+120h] [rbp+20h]
  char Src[144]; // [rsp+130h] [rbp+30h] BYREF
  _WORD pvData[136]; // [rsp+1C0h] [rbp+C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+328h] [rbp+228h]

  std::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>(v44);
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
      v44,
      &v48,
      pvData,
      i);
    std::string::_Tidy_deallocate(&`ZeroTouchProvCxhTelemetry::GetAutopilotCorrelationVector'::`2'::autopilot_cv);
    *(_OWORD *)&`ZeroTouchProvCxhTelemetry::GetAutopilotCorrelationVector'::`2'::autopilot_cv = v48;
    xmmword_180043A68 = (__int128)si128;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOBYTE(v48) = 0;
    std::string::_Tidy_deallocate(&v48);
LABEL_65:
    v44[0] = &std::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::`vftable';
    std::wstring::_Tidy_deallocate(v47);
    std::string::_Tidy_deallocate(v46);
    if ( v45 )
    {
      v34 = (void (__fastcall ***)(_QWORD, __int64))(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
      if ( v34 )
        (**v34)(v34, 1);
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
  v40 = v8;
  if ( v8 )
    v11 = TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(v8);
  else
    v11 = 0;
  v40 = v11;
  if ( !v11 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x418,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\inc\\ZTPLegacyTelemetry.h",
      (const char *)0x8007000ELL,
      pdwType);
    v44[0] = &std::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::`vftable';
    std::wstring::_Tidy_deallocate(v47);
    std::string::_Tidy_deallocate(v46);
    if ( v45 )
    {
      v12 = (void (__fastcall ***)(_QWORD, __int64))(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
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
      *(_DWORD *)_o__errno(v19, v18, v20) = 34;
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
    v27 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v3, 0, 0, 0, 2u, 0, &hKey, 0);
    if ( v27 )
    {
      v21 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x41C,
              (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\inc\\ZTPLegacyTelemetry.h",
              (const char *)v27,
              pdwTypea);
    }
    else
    {
      v28 = -1;
      do
        ++v28;
      while ( Src[v28] );
      std::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::from_bytes(
        v44,
        lpData,
        Src,
        &Src[v28]);
      pcbData = 2 * v42;
      v29 = (const BYTE *)lpData;
      if ( v43 > 7 )
        v29 = lpData[0];
      v30 = RegSetValueExW(hKey, L"AutopilotCorrelationVector", 0, 1u, v29, 2 * v42);
      if ( !v30 )
      {
        do
          ++v16;
        while ( Src[v16] );
        if ( v16 > *((_QWORD *)&xmmword_180043A68 + 1) )
        {
          std::string::_Reallocate_for<_lambda_a132b9f505f015b07a26cb4edca31da2_,char const *>(
            &`ZeroTouchProvCxhTelemetry::GetAutopilotCorrelationVector'::`2'::autopilot_cv,
            v16,
            v31,
            Src);
        }
        else
        {
          v32 = &`ZeroTouchProvCxhTelemetry::GetAutopilotCorrelationVector'::`2'::autopilot_cv;
          if ( *((_QWORD *)&xmmword_180043A68 + 1) > 0xFu )
            v32 = (void **)`ZeroTouchProvCxhTelemetry::GetAutopilotCorrelationVector'::`2'::autopilot_cv;
          *(_QWORD *)&xmmword_180043A68 = v16;
          memmove_0(v32, Src, v16);
          *((_BYTE *)v32 + v16) = 0;
        }
        ZeroTouchProvCxhTelemetry::LogAutopilotCorrelationVectorCreation(0, Src);
        v33 = lpData;
        if ( v43 > 7 )
          v33 = (BYTE **)lpData[0];
        ZeroTouchProvCxhTelemetry::LogAutopilotCorrelationData(
          L"AutopilotCorrelationVector",
          (const unsigned __int16 *)v33);
        std::wstring::_Tidy_deallocate(lpData);
        if ( hKey )
          RegCloseKey(hKey);
        operator delete(v11);
        goto LABEL_65;
      }
      v21 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x420,
              (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\inc\\ZTPLegacyTelemetry.h",
              (const char *)v30,
              pdwTypeb);
      std::wstring::_Tidy_deallocate(lpData);
    }
    if ( hKey )
      RegCloseKey(hKey);
    goto LABEL_32;
  }
  v23 = *((unsigned __int8 *)v11 + 129);
  v24 = &Src[v23];
  v25 = *((unsigned __int8 *)v11 + 130) - v23;
  if ( v14 >= 0 )
    v26 = sprintf_s(v24, v25, "%u", (unsigned int)v14);
  else
    v26 = sprintf_s(v24, v25, "%u!", (unsigned int)v14);
  if ( v26 != -1 )
    goto LABEL_28;
LABEL_31:
  v21 = -2147418113;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x419,
    (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\inc\\ZTPLegacyTelemetry.h",
    (const char *)0x8000FFFFLL,
    pdwType);
LABEL_32:
  operator delete(v11);
  v44[0] = &std::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::`vftable';
  std::wstring::_Tidy_deallocate(v47);
  std::string::_Tidy_deallocate(v46);
  if ( v45 )
  {
    v22 = (void (__fastcall ***)(_QWORD, __int64))(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
    if ( v22 )
      (**v22)(v22, 1);
  }
  return v21;
}

```

## disassembly

```asm
0x1800152c0  push    rbp
0x1800152c2  push    rbx
0x1800152c3  push    rsi
0x1800152c4  push    rdi
0x1800152c5  push    r12
0x1800152c7  push    r13
0x1800152c9  push    r14
0x1800152cb  push    r15
0x1800152cd  lea     rbp, [rsp-1E8h]
0x1800152d5  sub     rsp, 2E8h
0x1800152dc  mov     rax, cs:__security_cookie
0x1800152e3  xor     rax, rsp
0x1800152e6  mov     [rbp+220h+var_50], rax
0x1800152ed  xor     r12d, r12d
0x1800152f0  lea     rcx, [rbp+220h+var_290]
0x1800152f4  call    ??0?$wstring_convert@V?$codecvt_utf8_utf16@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@QEAA@XZ; std::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>(void)
0x1800152f9  nop
0x1800152fa  mov     ebx, 102h
0x1800152ff  mov     r8d, ebx; Size
0x180015302  xor     edx, edx; Val
0x180015304  lea     rcx, [rbp+220h+var_160]; void *
0x18001530b  call    memset_0
0x180015310  mov     [rsp+320h+var_2D0], ebx
0x180015314  lea     r13d, [r12+1]
0x180015319  cmp     cs:?s_HasRun@?1??ZTPIsStateSeparationEnabled@@YA_NXZ@4_NA, r12b; bool `ZTPIsStateSeparationEnabled(void)'::`2'::s_HasRun
0x180015320  jz      short loc_18001532A
0x180015322  mov     al, cs:?s_Redirection@?1??ZTPIsStateSeparationEnabled@@YA_NXZ@4_NA; bool `ZTPIsStateSeparationEnabled(void)'::`2'::s_Redirection
0x180015328  jmp     short loc_180015342
0x18001532a  call    cs:__imp_RtlIsStateSeparationEnabled
0x180015330  test    al, al
0x180015332  setnz   al
0x180015335  mov     cs:?s_Redirection@?1??ZTPIsStateSeparationEnabled@@YA_NXZ@4_NA, al; bool `ZTPIsStateSeparationEnabled(void)'::`2'::s_Redirection
0x18001533b  mov     cs:?s_HasRun@?1??ZTPIsStateSeparationEnabled@@YA_NXZ@4_NA, r13b; bool `ZTPIsStateSeparationEnabled(void)'::`2'::s_HasRun
0x180015342  lea     rcx, aSoftwareMicros_3; "Software\\Microsoft\\Provisioning\\Auto"...
0x180015349  lea     r15, aOsdataSoftware_1; "OSData\\Software\\Microsoft\\Provisioni"...
0x180015350  mov     rdx, r15
0x180015353  test    al, al
0x180015355  cmovz   rdx, rcx; lpSubKey
0x180015359  lea     rax, [rsp+320h+var_2D0]
0x18001535e  mov     [rsp+320h+pcbData], rax; pcbData
0x180015363  lea     rax, [rbp+220h+var_160]
0x18001536a  mov     [rsp+320h+pvData], rax; pvData
0x18001536f  mov     [rsp+320h+pdwType], r12; int
0x180015374  mov     r9d, 2; dwFlags
0x18001537a  lea     r8, aAutopilotcorre; "AutopilotCorrelationVector"
0x180015381  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180015388  call    cs:__imp_RegGetValueW
0x18001538e  mov     ecx, eax
0x180015390  test    eax, eax
0x180015392  jnz     short loc_180015404
0x180015394  lea     r9, [rbp+220h+var_160]
0x18001539b  cmp     [rbp+220h+var_160], r12w
0x1800153a3  jz      short loc_1800153AF
0x1800153a5  add     r9, 2
0x1800153a9  cmp     [r9], r12w
0x1800153ad  jnz     short loc_1800153A5
0x1800153af  lea     r8, [rbp+220h+var_160]
0x1800153b6  lea     rdx, [rbp+220h+var_210]
0x1800153ba  lea     rcx, [rbp+220h+var_290]
0x1800153be  call    ?to_bytes@?$wstring_convert@V?$codecvt_utf8_utf16@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@QEAA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@PEBG0@Z; std::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::to_bytes(ushort const *,ushort const *)
0x1800153c3  lea     rcx, ?autopilot_cv@?1??GetAutopilotCorrelationVector@ZeroTouchProvCxhTelemetry@@SA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ@4V34@A; std::string `ZeroTouchProvCxhTelemetry::GetAutopilotCorrelationVector(void)'::`2'::autopilot_cv
0x1800153ca  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800153cf  movups  xmm0, [rbp+220h+var_210]
0x1800153d3  movups  cs:?autopilot_cv@?1??GetAutopilotCorrelationVector@ZeroTouchProvCxhTelemetry@@SA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ@4V34@A, xmm0; std::string `ZeroTouchProvCxhTelemetry::GetAutopilotCorrelationVector(void)'::`2'::autopilot_cv
0x1800153da  movups  xmm1, [rbp+220h+var_200]
0x1800153de  movups  cs:xmmword_180043A68, xmm1
0x1800153e5  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x1800153ed  movdqu  [rbp+220h+var_200], xmm0
0x1800153f2  mov     byte ptr [rbp+220h+var_210], r12b
0x1800153f6  lea     rcx, [rbp+220h+var_210]
0x1800153fa  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800153ff  jmp     loc_180015822
0x180015404  add     eax, 0FFFFFFFEh
0x180015407  cmp     eax, r13d
0x18001540a  jbe     short loc_180015425
0x18001540c  test    ecx, ecx
0x18001540e  jle     short loc_180015419
0x180015410  movzx   ecx, cx
0x180015413  or      ecx, 80070000h; int
0x180015419  lea     rdx, aAutopilotcorre_0; "AutopilotCorrelationVectorCreationFaile"...
0x180015420  call    ?LogAutopilotCorrelationVectorCreation@ZeroTouchProvCxhTelemetry@@CAXJPEBD@Z; ZeroTouchProvCxhTelemetry::LogAutopilotCorrelationVectorCreation(long,char const *)
0x180015425  xor     edx, edx; Val
0x180015427  mov     r8d, 81h; Size
0x18001542d  lea     rcx, [rbp+220h+Src]; void *
0x180015431  call    memset_0
0x180015436  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001543d  mov     ecx, 90h; unsigned __int64
0x180015442  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180015447  mov     [rsp+320h+var_2C0], rax
0x18001544c  test    rax, rax
0x18001544f  jz      short loc_18001545E
0x180015451  mov     rcx, rax; this
0x180015454  call    ??0TraceLoggingCorrelationVector@@QEAA@XZ; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(void)
0x180015459  mov     rbx, rax
0x18001545c  jmp     short loc_180015461
0x18001545e  mov     rbx, r12
0x180015461  mov     [rsp+320h+var_2C0], rbx
0x180015466  test    rbx, rbx
0x180015469  jnz     short loc_1800154DE
0x18001546b  mov     rcx, [rbp+228h]; this
0x180015472  mov     ebx, 8007000Eh
0x180015477  mov     r9d, ebx; char *
0x18001547a  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\moderndeployment\\au"...
0x180015481  mov     edx, 418h; void *
0x180015486  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001548b  nop
0x18001548c  lea     rax, ??_7?$wstring_convert@V?$codecvt_utf8_utf16@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@6B@; const std::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::`vftable'
0x180015493  mov     [rbp+220h+var_290], rax
0x180015497  lea     rcx, [rbp+220h+var_250]
0x18001549b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800154a0  lea     rcx, [rbp+220h+var_270]
0x1800154a4  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800154a9  mov     rcx, [rbp+220h+var_278]
0x1800154ad  test    rcx, rcx
0x1800154b0  jz      short loc_1800154D7
0x1800154b2  mov     rax, [rcx]
0x1800154b5  mov     rax, [rax+10h]
0x1800154b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800154be  mov     r8, rax
0x1800154c1  test    rax, rax
0x1800154c4  jz      short loc_1800154D7
0x1800154c6  mov     rcx, [rax]
0x1800154c9  mov     rax, [rcx]
0x1800154cc  mov     edx, r13d
0x1800154cf  mov     rcx, r8
0x1800154d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800154d7  mov     eax, ebx
0x1800154d9  jmp     loc_18001586F
0x1800154de  mov     rsi, r12
0x1800154e1  lock xadd [rbx+88h], rsi
0x1800154ea  test    rsi, rsi
0x1800154ed  sets    r14b
0x1800154f1  mov     rax, rsi
0x1800154f4  shr     rax, 20h
0x1800154f8  mov     [rbp+220h+Src], r12b
0x1800154fc  test    ax, ax
0x1800154ff  jz      short loc_180015520
0x180015501  movzx   r8d, byte ptr [rbx+82h]; Size
0x180015509  movzx   ecx, ax
0x18001550c  cmp     r8, rcx
0x18001550f  jb      short loc_18001556A
0x180015511  mov     r8d, ecx; Size
0x180015514  mov     rdx, rbx; Src
0x180015517  lea     rcx, [rbp+220h+Src]; void *
0x18001551b  call    memcpy_0
0x180015520  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180015524  test    r14b, r14b
0x180015527  jz      loc_180015607
0x18001552d  test    esi, esi
0x18001552f  jnz     loc_180015607
0x180015535  movzx   eax, byte ptr [rbx+81h]
0x18001553c  mov     [rbp+rax+220h+Src], 21h ; '!'
0x180015541  movzx   eax, byte ptr [rbx+81h]
0x180015548  mov     [rbp+rax+220h+var_1EF], r12b
0x18001554d  mov     [rsp+320h+hKey], r12
0x180015552  cmp     cs:?s_HasRun@?1??ZTPIsStateSeparationEnabled@@YA_NXZ@4_NA, r12b; bool `ZTPIsStateSeparationEnabled(void)'::`2'::s_HasRun
0x180015559  jz      loc_180015649
0x18001555f  mov     al, cs:?s_Redirection@?1??ZTPIsStateSeparationEnabled@@YA_NXZ@4_NA; bool `ZTPIsStateSeparationEnabled(void)'::`2'::s_Redirection
0x180015565  jmp     loc_180015661
0x18001556a  xor     edx, edx; Val
0x18001556c  lea     rcx, [rbp+220h+Src]; void *
0x180015570  call    memset_0
0x180015575  call    cs:__imp__o__errno
0x18001557b  mov     dword ptr [rax], 22h ; '"'
0x180015581  call    _invalid_parameter_noinfo
0x180015586  mov     rcx, [rbp+228h]; this
0x18001558d  mov     edi, 8000FFFFh
0x180015592  mov     r9d, edi; char *
0x180015595  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001559c  mov     edx, 419h; void *
0x1800155a1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800155a6  nop
0x1800155a7  mov     edx, 90h
0x1800155ac  mov     rcx, rbx; Block
0x1800155af  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800155b4  nop
0x1800155b5  lea     rax, ??_7?$wstring_convert@V?$codecvt_utf8_utf16@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@6B@; const std::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::`vftable'
0x1800155bc  mov     [rbp+220h+var_290], rax
0x1800155c0  lea     rcx, [rbp+220h+var_250]
0x1800155c4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800155c9  lea     rcx, [rbp+220h+var_270]
0x1800155cd  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800155d2  mov     rcx, [rbp+220h+var_278]
0x1800155d6  test    rcx, rcx
0x1800155d9  jz      short loc_180015600
0x1800155db  mov     rax, [rcx]
0x1800155de  mov     rax, [rax+10h]
0x1800155e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800155e7  mov     r8, rax
0x1800155ea  test    rax, rax
0x1800155ed  jz      short loc_180015600
0x1800155ef  mov     rcx, [rax]
0x1800155f2  mov     rax, [rcx]
0x1800155f5  mov     edx, r13d
0x1800155f8  mov     rcx, r8
0x1800155fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015600  mov     eax, edi
0x180015602  jmp     loc_18001586F
0x180015607  movzx   eax, byte ptr [rbx+81h]
0x18001560e  lea     rcx, [rbp+220h+Src]
0x180015612  add     rcx, rax; Buffer
0x180015615  movzx   edx, byte ptr [rbx+82h]
0x18001561c  sub     rdx, rax; BufferCount
0x18001561f  mov     r9d, esi
0x180015622  test    r14b, r14b
0x180015625  jz      short loc_180015640
0x180015627  lea     r8, Format; "%u!"
0x18001562e  call    sprintf_s
0x180015633  cmp     eax, edi
0x180015635  jz      loc_180015586
0x18001563b  jmp     loc_18001554D
0x180015640  lea     r8, aU_0; "%u"
0x180015647  jmp     short loc_18001562E
0x180015649  call    cs:__imp_RtlIsStateSeparationEnabled
0x18001564f  test    al, al
0x180015651  setnz   al
0x180015654  mov     cs:?s_Redirection@?1??ZTPIsStateSeparationEnabled@@YA_NXZ@4_NA, al; bool `ZTPIsStateSeparationEnabled(void)'::`2'::s_Redirection
0x18001565a  mov     cs:?s_HasRun@?1??ZTPIsStateSeparationEnabled@@YA_NXZ@4_NA, r13b; bool `ZTPIsStateSeparationEnabled(void)'::`2'::s_HasRun
0x180015661  test    al, al
0x180015663  lea     rax, aSoftwareMicros_3; "Software\\Microsoft\\Provisioning\\Auto"...
0x18001566a  cmovz   r15, rax
0x18001566e  mov     [rsp+320h+lpdwDisposition], r12; lpdwDisposition
0x180015673  lea     rax, [rsp+320h+hKey]
0x180015678  mov     [rsp+320h+phkResult], rax; phkResult
0x18001567d  mov     [rsp+320h+pcbData], r12; lpSecurityAttributes
0x180015682  mov     dword ptr [rsp+320h+pvData], 2; samDesired
0x18001568a  mov     dword ptr [rsp+320h+pdwType], r12d; unsigned int
0x18001568f  xor     r9d, r9d; lpClass
0x180015692  xor     r8d, r8d; Reserved
0x180015695  mov     rdx, r15; lpSubKey
0x180015698  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001569f  call    cs:__imp_RegCreateKeyExW
0x1800156a5  test    eax, eax
0x1800156a7  jz      short loc_1800156DF
0x1800156a9  mov     rcx, [rbp+228h]; this
0x1800156b0  mov     r9d, eax; char *
0x1800156b3  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800156ba  mov     edx, 41Ch; void *
0x1800156bf  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800156c4  mov     edi, eax
0x1800156c6  mov     rcx, [rsp+320h+hKey]; hKey
0x1800156cb  test    rcx, rcx
0x1800156ce  jz      loc_1800155A7
0x1800156d4  call    cs:__imp_RegCloseKey
0x1800156da  jmp     loc_1800155A7
0x1800156df  lea     rcx, [rbp+220h+Src]
0x1800156e3  mov     rax, rdi
0x1800156e6  inc     rax
0x1800156e9  cmp     [rcx+rax], r12b
0x1800156ed  jnz     short loc_1800156E6
0x1800156ef  lea     r9, [rbp+220h+Src]
0x1800156f3  add     r9, rax
0x1800156f6  lea     r8, [rbp+220h+Src]
0x1800156fa  lea     rdx, [rsp+320h+lpData]
0x1800156ff  lea     rcx, [rbp+220h+var_290]
0x180015703  call    ?from_bytes@?$wstring_convert@V?$codecvt_utf8_utf16@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@PEBD0@Z; std::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::from_bytes(char const *,char const *)
0x180015708  nop
0x180015709  mov     eax, [rsp+320h+var_2A8]
0x18001570d  lea     ecx, [rax+rax]
0x180015710  mov     [rsp+320h+var_2D0], ecx
0x180015714  lea     rax, [rsp+320h+lpData]
0x180015719  cmp     [rbp+220h+var_2A0], 7
0x18001571e  cmova   rax, [rsp+320h+lpData]
0x180015724  mov     dword ptr [rsp+320h+pvData], ecx; cbData
0x180015728  mov     [rsp+320h+pdwType], rax; unsigned int
0x18001572d  mov     r9d, r13d; dwType
0x180015730  xor     r8d, r8d; Reserved
0x180015733  lea     rdx, aAutopilotcorre; "AutopilotCorrelationVector"
0x18001573a  mov     rcx, [rsp+320h+hKey]; hKey
0x18001573f  call    cs:__imp_RegSetValueExW
0x180015745  test    eax, eax
0x180015747  jz      short loc_180015775
0x180015749  mov     rcx, [rbp+228h]; this
0x180015750  mov     r9d, eax; char *
0x180015753  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001575a  mov     edx, 420h; void *
0x18001575f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180015764  mov     edi, eax
0x180015766  lea     rcx, [rsp+320h+lpData]
0x18001576b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180015770  jmp     loc_1800156C6
0x180015775  lea     rax, [rbp+220h+Src]
0x180015779  inc     rdi
0x18001577c  cmp     [rax+rdi], r12b
0x180015780  jnz     short loc_180015779
0x180015782  mov     rax, qword ptr cs:xmmword_180043A68+8
0x180015789  cmp     rdi, rax
0x18001578c  ja      short loc_1800157BD
0x18001578e  lea     rsi, ?autopilot_cv@?1??GetAutopilotCorrelationVector@ZeroTouchProvCxhTelemetry@@SA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ@4V34@A; std::string `ZeroTouchProvCxhTelemetry::GetAutopilotCorrelationVector(void)'::`2'::autopilot_cv
0x180015795  cmp     rax, 0Fh
0x180015799  cmova   rsi, qword ptr cs:?autopilot_cv@?1??GetAutopilotCorrelationVector@ZeroTouchProvCxhTelemetry@@SA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ@4V34@A; std::string `ZeroTouchProvCxhTelemetry::GetAutopilotCorrelationVector(void)'::`2'::autopilot_cv
0x1800157a1  mov     qword ptr cs:xmmword_180043A68, rdi
0x1800157a8  mov     r8, rdi; Size
0x1800157ab  lea     rdx, [rbp+220h+Src]; Src
0x1800157af  mov     rcx, rsi; void *
0x1800157b2  call    memmove_0
0x1800157b7  mov     [rsi+rdi], r12b
0x1800157bb  jmp     short loc_1800157D0
0x1800157bd  lea     r9, [rbp+220h+Src]
0x1800157c1  mov     rdx, rdi
  ... truncated ...
```
