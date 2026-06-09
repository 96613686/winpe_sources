# Microsoft::Applications::Experimentation::ECS::ECSClient::_UpdateLoggerWithEXPConfig(Microsoft::Applications::Events::ILogger *,std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &)

- ea: `0x1401497cc`
- end: `0x140149b82`
- name: `?_UpdateLoggerWithEXPConfig@ECSClient@ECS@Experimentation@Applications@Microsoft@@AEAAXPEAVILogger@Events@45@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z`
- size: `950`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140147ef0`
- `0x140149b84`

## callees

- `0x14003a0f4`
- `0x14003a5c0`
- `0x14007e14c`
- `0x1400848c8`
- `0x140084a18`
- `0x140084b3c`
- `0x14009cf94`
- `0x14009d4d0`
- `0x1400ff188`
- `0x1401263d4`
- `0x1401497cc`
- `0x140152ad8`
- `0x140166250`

## string_xrefs

- `0x140149aac`: `_UpdateLoggerWithEXPConfig: SetEventExperimentIds eventName=%s, eventConfigIds=%s`
- `0x1401498e4`: `MATSDK.ExpCommonClient`
- `0x140149924`: `MATSDK.ExpCommonClient`
- `0x1401498dd`: `_UpdateLoggerWithEXPConfig: logger(0x%x) added with ETag=%s`
- `0x14014991d`: `_UpdateLoggerWithEXPConfig: logger(0x%x) SetAppExperimentIds configIds=%s`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall Microsoft::Applications::Experimentation::ECS::ECSClient::_UpdateLoggerWithEXPConfig(
        _QWORD *a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v6; // rax
  __m128i si128; // xmm6
  __int64 v8; // rbx
  __int64 v9; // rsi
  unsigned __int64 v10; // r8
  int v11; // eax
  const char *v12; // rax
  const char *v13; // rax
  _QWORD *v14; // rax
  unsigned __int64 v15; // rsi
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // rbx
  _OWORD *v19; // rdx
  __int64 v20; // rax
  const char *v21; // rcx
  const char *v22; // r9
  void *v23; // rax
  _OWORD v25[2]; // [rsp+38h] [rbp-89h] BYREF
  __int128 v26; // [rsp+58h] [rbp-69h] BYREF
  __int128 v27; // [rsp+68h] [rbp-59h]
  __int128 v28; // [rsp+78h] [rbp-49h] BYREF
  __int64 v29; // [rsp+88h] [rbp-39h]
  __int128 v30; // [rsp+90h] [rbp-31h] BYREF
  __int128 Src; // [rsp+A0h] [rbp-21h] BYREF
  __m128i v32; // [rsp+B0h] [rbp-11h]
  _QWORD v33[4]; // [rsp+C0h] [rbp-1h] BYREF

  v6 = *a1;
  Src = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v32 = si128;
  LOBYTE(Src) = 0;
  (*(void (__fastcall **)(_QWORD *, _QWORD *, __int64 *, __int64, __int128 *))(v6 + 184))(
    a1,
    v33,
    qword_1401E6570,
    a3,
    &Src);
  std::string::_Tidy_deallocate(&Src);
  v8 = a1[22] + 32LL;
  if ( a2 && *(_QWORD *)(a3 + 16) )
  {
    v9 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a2 + 8LL))(a2);
    v26 = 0;
    v27 = 0;
    v10 = *(_QWORD *)(v8 + 16);
    if ( *(_QWORD *)(v8 + 24) > 0xFu )
      v8 = *(_QWORD *)v8;
    std::string::_Construct<2,char const *>((__int64)&v26, (_OWORD *)v8, v10);
    (*(void (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v9 + 56LL))(v9, &v26);
    v11 = Microsoft::Applications::Events::PlatformAbstraction::detail::g_logLevel;
    if ( Microsoft::Applications::Events::PlatformAbstraction::detail::g_logLevel >= 4 )
    {
      v12 = (const char *)&v26;
      if ( *((_QWORD *)&v27 + 1) > 0xFu )
        v12 = (const char *)v26;
      Microsoft::Applications::Events::PlatformAbstraction::detail::log(
        4,
        "MATSDK.ExpCommonClient",
        "_UpdateLoggerWithEXPConfig: logger(0x%x) added with ETag=%s",
        a2,
        v12);
      v11 = Microsoft::Applications::Events::PlatformAbstraction::detail::g_logLevel;
    }
    if ( v33[2] )
    {
      if ( v11 >= 4 )
      {
        v13 = (const char *)v33;
        if ( v33[3] > 0xFu )
          v13 = (const char *)v33[0];
        Microsoft::Applications::Events::PlatformAbstraction::detail::log(
          4,
          "MATSDK.ExpCommonClient",
          "_UpdateLoggerWithEXPConfig: logger(0x%x) SetAppExperimentIds configIds=%s",
          a2,
          v13);
      }
      (*(void (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v9 + 48LL))(v9, v33);
    }
    std::string::_Tidy_deallocate(&v26);
  }
  v28 = 0;
  v29 = 0;
  (*(void (__fastcall **)(_QWORD *, __int128 *, __int64 *, __int64))(*a1 + 104LL))(a1, &v28, qword_1401E6350, a3);
  v30 = 0;
  v14 = operator new(0x60u);
  *v14 = v14;
  v14[1] = v14;
  v14[2] = v14;
  *((_WORD *)v14 + 12) = 257;
  *(_QWORD *)&v30 = v14;
  v15 = 0;
  v16 = *((_QWORD *)&v28 + 1);
  v17 = v28;
  if ( (__int64)(*((_QWORD *)&v28 + 1) - v28) >> 5 )
  {
    v18 = 0;
    do
    {
      if ( *(_QWORD *)(v17 + v18 + 16) )
      {
        Src = 0;
        v32 = 0;
        v19 = (_OWORD *)a3;
        if ( *(_QWORD *)(a3 + 24) > 0xFu )
          v19 = *(_OWORD **)a3;
        std::string::_Construct<2,char const *>((__int64)&Src, v19, *(_QWORD *)(a3 + 16));
        std::string::append(&Src);
        std::string::append(&Src);
        v20 = *a1;
        v25[0] = 0;
        v25[1] = si128;
        LOBYTE(v25[0]) = 0;
        (*(void (__fastcall **)(_QWORD *, __int128 *, __int64 *, __int128 *, _OWORD *))(v20 + 184))(
          a1,
          &v26,
          qword_1401E6350,
          &Src,
          v25);
        std::string::_Tidy_deallocate(v25);
        if ( (_QWORD)v27 )
        {
          if ( Microsoft::Applications::Events::PlatformAbstraction::detail::g_logLevel >= 4 )
          {
            v21 = (const char *)&v26;
            if ( *((_QWORD *)&v27 + 1) > 0xFu )
              v21 = (const char *)v26;
            v22 = (const char *)(v18 + v28);
            if ( *(_QWORD *)(v18 + v28 + 24) > 0xFu )
              v22 = *(const char **)v22;
            Microsoft::Applications::Events::PlatformAbstraction::detail::log(
              4,
              "EventsSDK.ECS",
              "_UpdateLoggerWithEXPConfig: SetEventExperimentIds eventName=%s, eventConfigIds=%s",
              v22,
              v21);
          }
          v23 = (void *)std::map<std::string,std::string>::operator[](&v30, v18 + v28);
          std::string::operator=(v23);
        }
        std::string::_Tidy_deallocate(&v26);
        std::string::_Tidy_deallocate(&Src);
        v16 = *((_QWORD *)&v28 + 1);
        v17 = v28;
      }
      ++v15;
      v18 += 32;
    }
    while ( v15 < (v16 - v17) >> 5 );
  }
  if ( *((_QWORD *)&v30 + 1) )
    Microsoft::Applications::Experimentation::ExpCommon::_UpdateLoggerWithEXPConfig(
      v17,
      a2,
      a3,
      a1[22] + 32,
      (__int64)&v30);
  std::_Tree<std::_Tmap_traits<std::string,std::string,std::less<std::string>,std::allocator<std::pair<std::string const,std::string>>,0>>::~_Tree<std::_Tmap_traits<std::string,std::string,std::less<std::string>,std::allocator<std::pair<std::string const,std::string>>,0>>(&v30);
  std::vector<CsProtocol::M365a>::_Tidy(&v28);
  return std::string::_Tidy_deallocate(v33);
}

```

## disassembly

```asm
0x1401497cc  mov     rax, rsp
0x1401497cf  mov     [rax+20h], rbx
0x1401497d3  push    rbp
0x1401497d4  push    rsi
0x1401497d5  push    rdi
0x1401497d6  push    r14
0x1401497d8  push    r15
0x1401497da  lea     rbp, [rax-5Fh]
0x1401497de  sub     rsp, 0F0h
0x1401497e5  movaps  xmmword ptr [rax-38h], xmm6
0x1401497e9  mov     rax, cs:__security_cookie
0x1401497f0  xor     rax, rsp
0x1401497f3  mov     [rbp+57h+var_38], rax
0x1401497f7  mov     rdi, r8
0x1401497fa  mov     r14, rdx
0x1401497fd  mov     r15, rcx
0x140149800  mov     rax, [rcx]
0x140149803  xorps   xmm0, xmm0
0x140149806  movups  [rbp+57h+Src], xmm0
0x14014980a  movdqa  xmm6, cs:__xmm@000000000000000f0000000000000000
0x140149812  movdqu  [rbp+57h+var_68], xmm6
0x140149817  mov     byte ptr [rbp+57h+Src], 0
0x14014981b  lea     rcx, [rbp+57h+Src]
0x14014981f  mov     [rsp+110h+var_F0], rcx
0x140149824  mov     r9, r8
0x140149827  lea     r8, qword_1401E6570
0x14014982e  lea     rdx, [rbp+57h+var_58]
0x140149832  mov     rcx, r15
0x140149835  mov     rax, [rax+0B8h]
0x14014983c  call    cs:__guard_dispatch_icall_fptr
0x140149842  nop
0x140149843  lea     rcx, [rbp+57h+Src]
0x140149847  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x14014984c  mov     rbx, [r15+0B0h]
0x140149853  add     rbx, 20h ; ' '
0x140149857  test    r14, r14
0x14014985a  jz      loc_140149953
0x140149860  cmp     qword ptr [rdi+10h], 0
0x140149865  jz      loc_140149953
0x14014986b  mov     rax, [r14]
0x14014986e  mov     rcx, r14
0x140149871  mov     rax, [rax+8]
0x140149875  call    cs:__guard_dispatch_icall_fptr
0x14014987b  mov     rsi, rax
0x14014987e  xorps   xmm0, xmm0
0x140149881  movups  [rbp+57h+var_C0], xmm0
0x140149885  xorps   xmm1, xmm1
0x140149888  movdqu  [rbp+57h+var_B0], xmm1
0x14014988d  mov     r8, [rbx+10h]
0x140149891  cmp     qword ptr [rbx+18h], 0Fh
0x140149896  jbe     short loc_14014989B
0x140149898  mov     rbx, [rbx]
0x14014989b  mov     rdx, rbx
0x14014989e  lea     rcx, [rbp+57h+var_C0]
0x1401498a2  call    ??$_Construct@$01PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<2,char const *>(char const * const,unsigned __int64)
0x1401498a7  nop
0x1401498a8  mov     rax, [rsi]
0x1401498ab  lea     rdx, [rbp+57h+var_C0]
0x1401498af  mov     rcx, rsi
0x1401498b2  mov     rax, [rax+38h]
0x1401498b6  call    cs:__guard_dispatch_icall_fptr
0x1401498bc  mov     eax, cs:?g_logLevel@detail@PlatformAbstraction@Events@Applications@Microsoft@@3W4LogLevel@2345@A; Microsoft::Applications::Events::PlatformAbstraction::LogLevel Microsoft::Applications::Events::PlatformAbstraction::detail::g_logLevel
0x1401498c2  cmp     eax, 4
0x1401498c5  jl      short loc_1401498FB
0x1401498c7  lea     rax, [rbp+57h+var_C0]
0x1401498cb  cmp     qword ptr [rbp+57h+var_B0+8], 0Fh
0x1401498d0  cmova   rax, qword ptr [rbp+57h+var_C0]
0x1401498d5  mov     [rsp+110h+var_F0], rax
0x1401498da  mov     r9, r14
0x1401498dd  lea     r8, aUpdateloggerwi; "_UpdateLoggerWithEXPConfig: logger(0x%x"...
0x1401498e4  lea     rdx, aMatsdkExpcommo; "MATSDK.ExpCommonClient"
0x1401498eb  mov     ecx, 4
0x1401498f0  call    ?log@detail@PlatformAbstraction@Events@Applications@Microsoft@@YAXW4LogLevel@2345@PEBD1ZZ; Microsoft::Applications::Events::PlatformAbstraction::detail::log(Microsoft::Applications::Events::PlatformAbstraction::LogLevel,char const *,char const *,...)
0x1401498f5  mov     eax, cs:?g_logLevel@detail@PlatformAbstraction@Events@Applications@Microsoft@@3W4LogLevel@2345@A; Microsoft::Applications::Events::PlatformAbstraction::LogLevel Microsoft::Applications::Events::PlatformAbstraction::detail::g_logLevel
0x1401498fb  cmp     [rbp+57h+var_48], 0
0x140149900  jz      short loc_14014994A
0x140149902  cmp     eax, 4
0x140149905  jl      short loc_140149935
0x140149907  lea     rax, [rbp+57h+var_58]
0x14014990b  cmp     [rbp+57h+var_40], 0Fh
0x140149910  cmova   rax, [rbp+57h+var_58]
0x140149915  mov     [rsp+110h+var_F0], rax
0x14014991a  mov     r9, r14
0x14014991d  lea     r8, aUpdateloggerwi_2; "_UpdateLoggerWithEXPConfig: logger(0x%x"...
0x140149924  lea     rdx, aMatsdkExpcommo; "MATSDK.ExpCommonClient"
0x14014992b  mov     ecx, 4
0x140149930  call    ?log@detail@PlatformAbstraction@Events@Applications@Microsoft@@YAXW4LogLevel@2345@PEBD1ZZ; Microsoft::Applications::Events::PlatformAbstraction::detail::log(Microsoft::Applications::Events::PlatformAbstraction::LogLevel,char const *,char const *,...)
0x140149935  mov     rax, [rsi]
0x140149938  lea     rdx, [rbp+57h+var_58]
0x14014993c  mov     rcx, rsi
0x14014993f  mov     rax, [rax+30h]
0x140149943  call    cs:__guard_dispatch_icall_fptr
0x140149949  nop
0x14014994a  lea     rcx, [rbp+57h+var_C0]
0x14014994e  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x140149953  xorps   xmm0, xmm0
0x140149956  xor     eax, eax
0x140149958  movups  [rbp+57h+var_A0], xmm0
0x14014995c  mov     [rbp+57h+var_90], rax
0x140149960  mov     rax, [r15]
0x140149963  mov     r9, rdi
0x140149966  lea     r8, qword_1401E6350
0x14014996d  lea     rdx, [rbp+57h+var_A0]
0x140149971  mov     rcx, r15
0x140149974  mov     rax, [rax+68h]
0x140149978  call    cs:__guard_dispatch_icall_fptr
0x14014997e  nop
0x14014997f  xorps   xmm1, xmm1
0x140149982  movdqu  [rbp+57h+var_88], xmm1
0x140149987  mov     ecx, 60h ; '`'; Size
0x14014998c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140149991  mov     [rax], rax
0x140149994  mov     [rax+8], rax
0x140149998  mov     [rax+10h], rax
0x14014999c  mov     word ptr [rax+18h], 101h
0x1401499a2  mov     qword ptr [rbp+57h+var_88], rax
0x1401499a6  xor     esi, esi
0x1401499a8  mov     rdx, qword ptr [rbp+57h+var_A0+8]
0x1401499ac  mov     rax, rdx
0x1401499af  mov     rcx, qword ptr [rbp+57h+var_A0]
0x1401499b3  sub     rax, rcx
0x1401499b6  sar     rax, 5
0x1401499ba  test    rax, rax
0x1401499bd  jz      loc_140149B16
0x1401499c3  xor     ebx, ebx
0x1401499c5  cmp     qword ptr [rcx+rbx+10h], 0
0x1401499cb  jz      loc_140149AFC
0x1401499d1  xorps   xmm0, xmm0
0x1401499d4  movups  [rbp+57h+Src], xmm0
0x1401499d8  xorps   xmm1, xmm1
0x1401499db  movdqu  [rbp+57h+var_68], xmm1
0x1401499e0  mov     rdx, rdi
0x1401499e3  cmp     qword ptr [rdi+18h], 0Fh
0x1401499e8  jbe     short loc_1401499ED
0x1401499ea  mov     rdx, [rdi]
0x1401499ed  mov     r8, [rdi+10h]
0x1401499f1  lea     rcx, [rbp+57h+Src]
0x1401499f5  call    ??$_Construct@$01PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<2,char const *>(char const * const,unsigned __int64)
0x1401499fa  nop
0x1401499fb  mov     r8d, 1
0x140149a01  lea     rdx, asc_140197944; "/"
0x140149a08  lea     rcx, [rbp+57h+Src]; Src
0x140149a0c  call    ?append@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z; std::string::append(char const * const,unsigned __int64)
0x140149a11  mov     rdx, qword ptr [rbp+57h+var_A0]
0x140149a15  add     rdx, rbx
0x140149a18  mov     r8, [rdx+10h]
0x140149a1c  cmp     qword ptr [rdx+18h], 0Fh
0x140149a21  jbe     short loc_140149A26
0x140149a23  mov     rdx, [rdx]
0x140149a26  lea     rcx, [rbp+57h+Src]; Src
0x140149a2a  call    ?append@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z; std::string::append(char const * const,unsigned __int64)
0x140149a2f  mov     rax, [r15]
0x140149a32  xorps   xmm0, xmm0
0x140149a35  movups  [rsp+110h+var_E8+8], xmm0
0x140149a3a  movdqu  [rbp+57h+var_D0], xmm6
0x140149a3f  mov     byte ptr [rsp+110h+var_E8+8], 0
0x140149a44  lea     rcx, [rsp+110h+var_E8+8]
0x140149a49  mov     [rsp+110h+var_F0], rcx
0x140149a4e  lea     r9, [rbp+57h+Src]
0x140149a52  lea     r8, qword_1401E6350
0x140149a59  lea     rdx, [rbp+57h+var_C0]
0x140149a5d  mov     rcx, r15
0x140149a60  mov     rax, [rax+0B8h]
0x140149a67  call    cs:__guard_dispatch_icall_fptr
0x140149a6d  nop
0x140149a6e  lea     rcx, [rsp+110h+var_E8+8]
0x140149a73  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x140149a78  cmp     qword ptr [rbp+57h+var_B0], 0
0x140149a7d  jz      short loc_140149AE1
0x140149a7f  cmp     cs:?g_logLevel@detail@PlatformAbstraction@Events@Applications@Microsoft@@3W4LogLevel@2345@A, 4; Microsoft::Applications::Events::PlatformAbstraction::LogLevel Microsoft::Applications::Events::PlatformAbstraction::detail::g_logLevel
0x140149a86  jl      short loc_140149AC4
0x140149a88  lea     rcx, [rbp+57h+var_C0]
0x140149a8c  cmp     qword ptr [rbp+57h+var_B0+8], 0Fh
0x140149a91  cmova   rcx, qword ptr [rbp+57h+var_C0]
0x140149a96  mov     r9, qword ptr [rbp+57h+var_A0]
0x140149a9a  add     r9, rbx
0x140149a9d  cmp     qword ptr [r9+18h], 0Fh
0x140149aa2  jbe     short loc_140149AA7
0x140149aa4  mov     r9, [r9]
0x140149aa7  mov     [rsp+110h+var_F0], rcx
0x140149aac  lea     r8, aUpdateloggerwi_1; "_UpdateLoggerWithEXPConfig: SetEventExp"...
0x140149ab3  lea     rdx, ?digits_to_99@?1???$dump_integer@_K$0A@@?$serializer@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@json_abi_v3_11_3@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@X@json_abi_v3_11_3@nlohmann@@@detail@json_abi_v3_11_3@nlohmann@@AEAAX_K@Z@4V?$array@V?$array@D$01@std@@$0GE@@std@@B+0C8h; "EventsSDK.ECS"
0x140149aba  mov     ecx, 4
0x140149abf  call    ?log@detail@PlatformAbstraction@Events@Applications@Microsoft@@YAXW4LogLevel@2345@PEBD1ZZ; Microsoft::Applications::Events::PlatformAbstraction::detail::log(Microsoft::Applications::Events::PlatformAbstraction::LogLevel,char const *,char const *,...)
0x140149ac4  mov     rdx, qword ptr [rbp+57h+var_A0]
0x140149ac8  add     rdx, rbx
0x140149acb  lea     rcx, [rbp+57h+var_88]
0x140149acf  call    ??A?$map@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@2@@std@@QEAAAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@AEBV21@@Z; std::map<std::string,std::string>::operator[](std::string const &)
0x140149ad4  mov     rcx, rax; void *
0x140149ad7  lea     rdx, [rbp+57h+var_C0]
0x140149adb  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@AEBV01@@Z; std::string::operator=(std::string const &)
0x140149ae0  nop
0x140149ae1  lea     rcx, [rbp+57h+var_C0]
0x140149ae5  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x140149aea  nop
0x140149aeb  lea     rcx, [rbp+57h+Src]
0x140149aef  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x140149af4  mov     rdx, qword ptr [rbp+57h+var_A0+8]
0x140149af8  mov     rcx, qword ptr [rbp+57h+var_A0]
0x140149afc  inc     rsi
0x140149aff  add     rbx, 20h ; ' '
0x140149b03  mov     rax, rdx
0x140149b06  sub     rax, rcx
0x140149b09  sar     rax, 5
0x140149b0d  cmp     rsi, rax
0x140149b10  jb      loc_1401499C5
0x140149b16  cmp     qword ptr [rbp+57h+var_88+8], 0
0x140149b1b  jbe     short loc_140149B3D
0x140149b1d  mov     r9, [r15+0B0h]
0x140149b24  add     r9, 20h ; ' '
0x140149b28  lea     rax, [rbp+57h+var_88]
0x140149b2c  mov     [rsp+110h+var_F0], rax
0x140149b31  mov     r8, rdi
0x140149b34  mov     rdx, r14
0x140149b37  call    ?_UpdateLoggerWithEXPConfig@ExpCommon@Experimentation@Applications@Microsoft@@QEAAXPEAVILogger@Events@34@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@1AEBV?$map@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@2@@8@@Z; Microsoft::Applications::Experimentation::ExpCommon::_UpdateLoggerWithEXPConfig(Microsoft::Applications::Events::ILogger *,std::string const &,std::string const &,std::map<std::string,std::string> const &)
0x140149b3c  nop
0x140149b3d  lea     rcx, [rbp+57h+var_88]
0x140149b41  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::string,std::string,std::less<std::string>,std::allocator<std::pair<std::string const,std::string>>,0>>::~_Tree<std::_Tmap_traits<std::string,std::string,std::less<std::string>,std::allocator<std::pair<std::string const,std::string>>,0>>(void)
0x140149b46  nop
0x140149b47  lea     rcx, [rbp+57h+var_A0]
0x140149b4b  call    ?_Tidy@?$vector@UM365a@CsProtocol@@V?$allocator@UM365a@CsProtocol@@@std@@@std@@AEAAXXZ; std::vector<CsProtocol::M365a>::_Tidy(void)
0x140149b50  nop
0x140149b51  lea     rcx, [rbp+57h+var_58]
0x140149b55  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x140149b5a  mov     rcx, [rbp+57h+var_38]
0x140149b5e  xor     rcx, rsp; StackCookie
0x140149b61  call    __security_check_cookie
0x140149b66  lea     r11, [rsp+110h+var_20]
0x140149b6e  mov     rbx, [r11+48h]
0x140149b72  movaps  xmm6, xmmword ptr [r11-10h]
0x140149b77  mov     rsp, r11
0x140149b7a  pop     r15
0x140149b7c  pop     r14
0x140149b7e  pop     rdi
0x140149b7f  pop     rsi
0x140149b80  pop     rbp
0x140149b81  retn
```
