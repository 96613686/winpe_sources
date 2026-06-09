# McpAccessManagerStatics::CheckAccessForUserInternal(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,HSTRING__ *,HSTRING__ *,uint,Windows::Internal::AI::Agents::Mcp::McpResourceRequestInfo *,Windows::Internal::AI::Agents::Mcp::McpAccessStatus *)

- ea: `0x18009b1a0`
- end: `0x18009b4f2`
- name: `?CheckAccessForUserInternal@McpAccessManagerStatics@@QEAAXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUHSTRING__@@1IPEAUMcpResourceRequestInfo@Mcp@Agents@AI@Internal@Windows@@PEAW4McpAccessStatus@6789Windows@@@Z`
- size: `850`
- prototype: ``
- caller_count: `2`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18009b050`
- `0x18009b500`

## callees

- `0x1800094c0`
- `0x180016450`
- `0x18001649c`
- `0x18001c3b4`
- `0x18002392c`
- `0x1800257a4`
- `0x1800259c4`
- `0x18003f4a0`
- `0x180040d7c`
- `0x180043610`
- `0x180099f20`
- `0x18009a110`
- `0x18009b1a0`
- `0x18009e4b0`
- `0x1800b46d8`
- `0x1800b81b0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009b2b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009b2d1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009b357`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009b371`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009b2b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009b2d1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009b357`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009b371`

## string_xrefs

- `0x18009b465`: `onecore\base\devices\cam\winrt\mcp\management\mcpaccessmanagerstatics.cpp`
- `0x18009b480`: `onecore\base\devices\cam\winrt\mcp\management\mcpaccessmanagerstatics.cpp`
- `0x18009b498`: `onecore\base\devices\cam\winrt\mcp\management\mcpaccessmanagerstatics.cpp`
- `0x18009b4b0`: `onecore\base\devices\cam\winrt\mcp\management\mcpaccessmanagerstatics.cpp`
- `0x18009b4c8`: `onecore\base\devices\cam\winrt\mcp\management\mcpaccessmanagerstatics.cpp`
- `0x18009b4e0`: `onecore\base\devices\cam\winrt\mcp\management\mcpaccessmanagerstatics.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall McpAccessManagerStatics::CheckAccessForUserInternal(
        __int64 a1,
        __int64 a2,
        HSTRING a3,
        HSTRING a4,
        unsigned int a5,
        __int64 a6,
        _DWORD *a7)
{
  _DWORD *v9; // r15
  unsigned int v10; // r12d
  char v11; // r14
  PCWSTR StringRawBuffer; // rax
  PCWSTR v13; // rax
  __int64 UserSidStringFromToken; // rsi
  char v15; // bl
  void **v16; // rax
  PCWSTR v17; // rax
  PCWSTR v18; // rax
  int v20; // [rsp+20h] [rbp-E0h]
  _DWORD *v21; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v22; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v23; // [rsp+70h] [rbp-90h]
  HSTRING string; // [rsp+78h] [rbp-88h]
  __int64 v25; // [rsp+80h] [rbp-80h]
  _BYTE v26[32]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v27[40]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v28[32]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v29[32]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v30[32]; // [rsp+110h] [rbp+10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+88h]

  string = a3;
  v25 = a2;
  v9 = a7;
  v21 = a7;
  v10 = 0;
  if ( !a7 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x4F,
      (unsigned int)"onecore\\base\\devices\\cam\\winrt\\mcp\\management\\mcpaccessmanagerstatics.cpp",
      (const char *)0x80004003LL,
      v20);
  if ( !a3 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x50,
      (unsigned int)"onecore\\base\\devices\\cam\\winrt\\mcp\\management\\mcpaccessmanagerstatics.cpp",
      (const char *)0x80070057LL,
      v20);
  if ( !a4 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x51,
      (unsigned int)"onecore\\base\\devices\\cam\\winrt\\mcp\\management\\mcpaccessmanagerstatics.cpp",
      (const char *)0x80070057LL,
      v20);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID61095237>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID61095237>::GetImpl'::`2'::impl)
    && !a5 )
  {
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x55,
      (unsigned int)"onecore\\base\\devices\\cam\\winrt\\mcp\\management\\mcpaccessmanagerstatics.cpp",
      (const char *)0x80070057LL,
      v20);
  }
  *a7 = 4;
  v11 = Windows::Internal::CapabilityAccess::WinRT::CallerValidation::AccessCheckForRPCCaller((Windows::Internal::CapabilityAccess::WinRT::CallerValidation *)4);
  if ( v11 )
  {
    if ( !*(_QWORD *)(a2 + 16) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x61,
        (unsigned int)"onecore\\base\\devices\\cam\\winrt\\mcp\\management\\mcpaccessmanagerstatics.cpp",
        (const char *)0x80070057LL,
        v20);
  }
  else if ( !Windows::Internal::CapabilityAccess::WinRT::CallerValidation::AccessCheckForRPCCaller((Windows::Internal::CapabilityAccess::WinRT::CallerValidation *)8)
         && !Windows::Internal::CapabilityAccess::WinRT::CallerValidation::AccessCheckForRPCCaller((Windows::Internal::CapabilityAccess::WinRT::CallerValidation *)2) )
  {
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x69,
      (unsigned int)"onecore\\base\\devices\\cam\\winrt\\mcp\\management\\mcpaccessmanagerstatics.cpp",
      (const char *)0x80070005LL,
      v20);
  }
  v22 = 0;
  v23 = 0;
  if ( a5 )
  {
    do
    {
      StringRawBuffer = WindowsGetStringRawBuffer(*(HSTRING *)(a6 + 16LL * v10), 0);
      std::wstring::wstring(v28, StringRawBuffer);
      v13 = WindowsGetStringRawBuffer(*(HSTRING *)(a6 + 16LL * v10 + 8), 0);
      std::wstring::wstring(v29, v13);
      std::vector<Windows::Internal::AI::Agents::Mcp::Implementation::InternalMcpResourceRequestInfo>::emplace_back<Windows::Internal::AI::Agents::Mcp::Implementation::InternalMcpResourceRequestInfo &>(
        &v22,
        v28);
      std::pair<std::wstring const,std::wstring>::~pair<std::wstring const,std::wstring>(v28);
      ++v10;
    }
    while ( v10 < a5 );
    v9 = v21;
  }
  if ( v11 )
  {
    UserSidStringFromToken = std::wstring::wstring(v28, a2);
    v15 = 1;
  }
  else
  {
    v16 = Windows::Internal::CapabilityAccess::Private::GetCallerTokenFromComCall((void **)&v21);
    UserSidStringFromToken = Windows::Internal::CapabilityAccess::Private::GetUserSidStringFromToken(v30, v16);
    v15 = 6;
  }
  v17 = WindowsGetStringRawBuffer(a4, 0);
  std::wstring::wstring(v27, v17);
  v18 = WindowsGetStringRawBuffer(string, 0);
  std::wstring::wstring(v26, v18);
  *v9 = Windows::Internal::AI::Agents::Mcp::Implementation::McpAccessManager::AccessCheck(
          1,
          0,
          (unsigned int)v26,
          (unsigned int)v27,
          UserSidStringFromToken,
          0,
          0,
          0,
          (__int64)&v22);
  std::wstring::_Tidy_deallocate(v26);
  std::wstring::_Tidy_deallocate(v27);
  if ( (v15 & 4) != 0 )
  {
    v15 &= ~4u;
    std::wstring::_Tidy_deallocate(v30);
  }
  if ( (v15 & 2) != 0 )
  {
    v15 &= ~2u;
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v21);
  }
  if ( (v15 & 1) != 0 )
    std::wstring::_Tidy_deallocate(v28);
  if ( (_QWORD)v22 )
  {
    std::_Destroy_range<std::allocator<Windows::Internal::AI::Agents::Mcp::Implementation::InternalMcpResourceRequestInfo>>(
      v22,
      *((_QWORD *)&v22 + 1));
    std::_Deallocate<16>(v22, (v23 - v22) & 0xFFFFFFFFFFFFFFC0uLL);
    v22 = 0;
    v23 = 0;
  }
  return std::wstring::_Tidy_deallocate(a2);
}

```

## disassembly

```asm
0x18009b1a0  push    rbp
0x18009b1a2  push    rbx
0x18009b1a3  push    rsi
0x18009b1a4  push    rdi
0x18009b1a5  push    r12
0x18009b1a7  push    r13
0x18009b1a9  push    r14
0x18009b1ab  push    r15
0x18009b1ad  lea     rbp, [rsp-48h]
0x18009b1b2  sub     rsp, 148h
0x18009b1b9  mov     rax, cs:__security_cookie
0x18009b1c0  xor     rax, rsp
0x18009b1c3  mov     [rbp+80h+var_50], rax
0x18009b1c7  mov     r13, r9
0x18009b1ca  mov     rax, r8
0x18009b1cd  mov     [rsp+180h+string], rax
0x18009b1d2  mov     rdi, rdx
0x18009b1d5  mov     [rbp+80h+var_100], rdx
0x18009b1d9  mov     r15, [rbp+80h+arg_30]
0x18009b1e0  mov     [rsp+180h+var_128], r15
0x18009b1e5  xor     r12d, r12d
0x18009b1e8  mov     [rsp+180h+var_130], r12d
0x18009b1ed  mov     rcx, [rbp+88h]; this
0x18009b1f4  test    r15, r15
0x18009b1f7  jz      loc_18009B492
0x18009b1fd  mov     rcx, [rbp+88h]; this
0x18009b204  test    rax, rax
0x18009b207  jz      loc_18009B4AA
0x18009b20d  mov     rcx, [rbp+88h]; this
0x18009b214  test    r9, r9
0x18009b217  jz      loc_18009B4C2
0x18009b21d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID61095237@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID61095237@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID61095237> `wil::Feature<__WilFeatureTraits_Feature_ID61095237>::GetImpl(void)'::`2'::impl
0x18009b224  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ID61095237@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID61095237>::__private_IsEnabled(void)
0x18009b229  mov     esi, [rbp+80h+arg_20]
0x18009b22f  test    al, al
0x18009b231  jz      short loc_18009B242
0x18009b233  mov     rcx, [rbp+88h]; this
0x18009b23a  test    esi, esi
0x18009b23c  jz      loc_18009B4DA
0x18009b242  mov     eax, 4
0x18009b247  mov     [r15], eax
0x18009b24a  mov     ecx, eax; this
0x18009b24c  call    ?AccessCheckForRPCCaller@CallerValidation@WinRT@CapabilityAccess@Internal@Windows@@YA_NI@Z; Windows::Internal::CapabilityAccess::WinRT::CallerValidation::AccessCheckForRPCCaller(uint)
0x18009b251  mov     r14b, al
0x18009b254  test    al, al
0x18009b256  jz      short loc_18009B26B
0x18009b258  mov     rcx, [rbp+88h]; this
0x18009b25f  cmp     [rdi+10h], r12
0x18009b263  jz      loc_18009B47A
0x18009b269  jmp     short loc_18009B292
0x18009b26b  mov     ecx, 8; this
0x18009b270  call    ?AccessCheckForRPCCaller@CallerValidation@WinRT@CapabilityAccess@Internal@Windows@@YA_NI@Z; Windows::Internal::CapabilityAccess::WinRT::CallerValidation::AccessCheckForRPCCaller(uint)
0x18009b275  test    al, al
0x18009b277  jnz     short loc_18009B292
0x18009b279  mov     rbx, [rbp+88h]
0x18009b280  mov     ecx, 2; this
0x18009b285  call    ?AccessCheckForRPCCaller@CallerValidation@WinRT@CapabilityAccess@Internal@Windows@@YA_NI@Z; Windows::Internal::CapabilityAccess::WinRT::CallerValidation::AccessCheckForRPCCaller(uint)
0x18009b28a  test    al, al
0x18009b28c  jz      loc_18009B45F
0x18009b292  xorps   xmm0, xmm0
0x18009b295  movdqu  [rsp+180h+var_120], xmm0
0x18009b29b  mov     [rsp+180h+var_110], r12
0x18009b2a0  test    esi, esi
0x18009b2a2  jz      short loc_18009B309
0x18009b2a4  mov     r15, [rbp+80h+arg_28]
0x18009b2ab  mov     ebx, r12d
0x18009b2ae  add     rbx, rbx
0x18009b2b1  xor     edx, edx; length
0x18009b2b3  mov     rcx, [r15+rbx*8]; string
0x18009b2b7  call    cs:__imp_WindowsGetStringRawBuffer
0x18009b2bd  mov     rdx, rax
0x18009b2c0  lea     rcx, [rbp+80h+var_B0]
0x18009b2c4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18009b2c9  nop
0x18009b2ca  xor     edx, edx; length
0x18009b2cc  mov     rcx, [r15+rbx*8+8]; string
0x18009b2d1  call    cs:__imp_WindowsGetStringRawBuffer
0x18009b2d7  mov     rdx, rax
0x18009b2da  lea     rcx, [rbp+80h+var_90]
0x18009b2de  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18009b2e3  nop
0x18009b2e4  lea     rdx, [rbp+80h+var_B0]
0x18009b2e8  lea     rcx, [rsp+180h+var_120]
0x18009b2ed  call    ??$emplace_back@AEAUInternalMcpResourceRequestInfo@Implementation@Mcp@Agents@AI@Internal@Windows@@@?$vector@UInternalMcpResourceRequestInfo@Implementation@Mcp@Agents@AI@Internal@Windows@@V?$allocator@UInternalMcpResourceRequestInfo@Implementation@Mcp@Agents@AI@Internal@Windows@@@std@@@std@@QEAAAEAUInternalMcpResourceRequestInfo@Implementation@Mcp@Agents@AI@Internal@Windows@@AEAU2345678@@Z; std::vector<Windows::Internal::AI::Agents::Mcp::Implementation::InternalMcpResourceRequestInfo>::emplace_back<Windows::Internal::AI::Agents::Mcp::Implementation::InternalMcpResourceRequestInfo &>(Windows::Internal::AI::Agents::Mcp::Implementation::InternalMcpResourceRequestInfo &)
0x18009b2f2  nop
0x18009b2f3  lea     rcx, [rbp+80h+var_B0]
0x18009b2f7  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@QEAA@XZ; std::pair<std::wstring const,std::wstring>::~pair<std::wstring const,std::wstring>(void)
0x18009b2fc  inc     r12d
0x18009b2ff  cmp     r12d, esi
0x18009b302  jb      short loc_18009B2AB
0x18009b304  mov     r15, [rsp+180h+var_128]
0x18009b309  xor     r12d, r12d
0x18009b30c  test    r14b, r14b
0x18009b30f  jz      short loc_18009B327
0x18009b311  mov     rdx, rdi
0x18009b314  lea     rcx, [rbp+80h+var_B0]
0x18009b318  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18009b31d  mov     rsi, rax
0x18009b320  lea     ebx, [r12+1]
0x18009b325  jmp     short loc_18009B34E
0x18009b327  lea     rcx, [rsp+180h+var_128]
0x18009b32c  call    ?GetCallerTokenFromComCall@Private@CapabilityAccess@Internal@Windows@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@XZ; Windows::Internal::CapabilityAccess::Private::GetCallerTokenFromComCall(void)
0x18009b331  nop
0x18009b332  mov     [rsp+180h+var_130], 2
0x18009b33a  mov     rdx, rax
0x18009b33d  lea     rcx, [rbp+80h+var_70]
0x18009b341  call    ?GetUserSidStringFromToken@Private@CapabilityAccess@Internal@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Z; Windows::Internal::CapabilityAccess::Private::GetUserSidStringFromToken(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> const &)
0x18009b346  mov     rsi, rax
0x18009b349  mov     ebx, 6
0x18009b34e  mov     [rsp+180h+var_130], ebx
0x18009b352  xor     edx, edx; length
0x18009b354  mov     rcx, r13; string
0x18009b357  call    cs:__imp_WindowsGetStringRawBuffer
0x18009b35d  mov     rdx, rax
0x18009b360  lea     rcx, [rbp+80h+var_D8]
0x18009b364  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18009b369  nop
0x18009b36a  xor     edx, edx; length
0x18009b36c  mov     rcx, [rsp+180h+string]; string
0x18009b371  call    cs:__imp_WindowsGetStringRawBuffer
0x18009b377  mov     rdx, rax
0x18009b37a  lea     rcx, [rbp+80h+var_F8]
0x18009b37e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18009b383  nop
0x18009b384  lea     rax, [rsp+180h+var_120]
0x18009b389  mov     [rsp+180h+var_140], rax
0x18009b38e  mov     [rsp+180h+var_148], r12
0x18009b393  mov     [rsp+180h+var_150], r12
0x18009b398  mov     [rsp+180h+var_158], r12
0x18009b39d  mov     [rsp+180h+var_160], rsi
0x18009b3a2  lea     r9, [rbp+80h+var_D8]
0x18009b3a6  lea     r8, [rbp+80h+var_F8]
0x18009b3aa  xor     edx, edx
0x18009b3ac  lea     ecx, [rdx+1]
0x18009b3af  call    ?AccessCheck@McpAccessManager@Implementation@Mcp@Agents@AI@Internal@Windows@@SA?AW4McpAccessStatus@34567@I_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@11PEAUIRandomAccessStream@Streams@Storage@7@2PEAUHSTRING__@@AEBV?$vector@UInternalMcpResourceRequestInfo@Implementation@Mcp@Agents@AI@Internal@Windows@@V?$allocator@UInternalMcpResourceRequestInfo@Implementation@Mcp@Agents@AI@Internal@Windows@@@std@@@std@@@Z; Windows::Internal::AI::Agents::Mcp::Implementation::McpAccessManager::AccessCheck(uint,unsigned __int64,std::wstring const &,std::wstring const &,std::wstring const &,Windows::Storage::Streams::IRandomAccessStream *,Windows::Storage::Streams::IRandomAccessStream *,HSTRING__ *,std::vector<Windows::Internal::AI::Agents::Mcp::Implementation::InternalMcpResourceRequestInfo> const &)
0x18009b3b4  mov     [r15], eax
0x18009b3b7  lea     rcx, [rbp+80h+var_F8]
0x18009b3bb  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18009b3c0  nop
0x18009b3c1  lea     rcx, [rbp+80h+var_D8]
0x18009b3c5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18009b3ca  nop
0x18009b3cb  test    bl, 4
0x18009b3ce  jz      short loc_18009B3DD
0x18009b3d0  and     ebx, 0FFFFFFFBh
0x18009b3d3  lea     rcx, [rbp+80h+var_70]
0x18009b3d7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18009b3dc  nop
0x18009b3dd  test    bl, 2
0x18009b3e0  jz      short loc_18009B3F0
0x18009b3e2  and     ebx, 0FFFFFFFDh
0x18009b3e5  lea     rcx, [rsp+180h+var_128]
0x18009b3ea  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18009b3ef  nop
0x18009b3f0  test    bl, 1
0x18009b3f3  jz      short loc_18009B3FF
0x18009b3f5  lea     rcx, [rbp+80h+var_B0]
0x18009b3f9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18009b3fe  nop
0x18009b3ff  mov     rcx, qword ptr [rsp+180h+var_120]
0x18009b404  test    rcx, rcx
0x18009b407  jz      short loc_18009B437
0x18009b409  mov     rdx, qword ptr [rsp+180h+var_120+8]
0x18009b40e  call    ??$_Destroy_range@V?$allocator@UInternalMcpResourceRequestInfo@Implementation@Mcp@Agents@AI@Internal@Windows@@@std@@@std@@YAXPEAUInternalMcpResourceRequestInfo@Implementation@Mcp@Agents@AI@Internal@Windows@@QEAU1234567@AEAV?$allocator@UInternalMcpResourceRequestInfo@Implementation@Mcp@Agents@AI@Internal@Windows@@@0@@Z; std::_Destroy_range<std::allocator<Windows::Internal::AI::Agents::Mcp::Implementation::InternalMcpResourceRequestInfo>>(Windows::Internal::AI::Agents::Mcp::Implementation::InternalMcpResourceRequestInfo *,Windows::Internal::AI::Agents::Mcp::Implementation::InternalMcpResourceRequestInfo * const,std::allocator<Windows::Internal::AI::Agents::Mcp::Implementation::InternalMcpResourceRequestInfo> &)
0x18009b413  mov     rcx, qword ptr [rsp+180h+var_120]
0x18009b418  mov     rdx, [rsp+180h+var_110]
0x18009b41d  sub     rdx, rcx
0x18009b420  and     rdx, 0FFFFFFFFFFFFFFC0h
0x18009b424  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18009b429  xorps   xmm0, xmm0
0x18009b42c  movdqu  [rsp+180h+var_120], xmm0
0x18009b432  mov     [rsp+180h+var_110], r12
0x18009b437  mov     rcx, rdi
0x18009b43a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18009b43f  mov     rcx, [rbp+80h+var_50]
0x18009b443  xor     rcx, rsp; StackCookie
0x18009b446  call    __security_check_cookie
0x18009b44b  add     rsp, 148h
0x18009b452  pop     r15
0x18009b454  pop     r14
0x18009b456  pop     r13
0x18009b458  pop     r12
0x18009b45a  pop     rdi
0x18009b45b  pop     rsi
0x18009b45c  pop     rbx
0x18009b45d  pop     rbp
0x18009b45e  retn
0x18009b45f  mov     r9d, 80070005h; char *
0x18009b465  lea     r8, aOnecoreBaseDev_20; "onecore\\base\\devices\\cam\\winrt\\mcp"...
0x18009b46c  mov     edx, 69h ; 'i'; void *
0x18009b471  mov     rcx, rbx; this
0x18009b474  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18009b47a  mov     r9d, 80070057h; char *
0x18009b480  lea     r8, aOnecoreBaseDev_20; "onecore\\base\\devices\\cam\\winrt\\mcp"...
0x18009b487  mov     edx, 61h ; 'a'; void *
0x18009b48c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18009b492  mov     r9d, 80004003h; char *
0x18009b498  lea     r8, aOnecoreBaseDev_20; "onecore\\base\\devices\\cam\\winrt\\mcp"...
0x18009b49f  mov     edx, 4Fh ; 'O'; void *
0x18009b4a4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18009b4aa  mov     r9d, 80070057h; char *
0x18009b4b0  lea     r8, aOnecoreBaseDev_20; "onecore\\base\\devices\\cam\\winrt\\mcp"...
0x18009b4b7  mov     edx, 50h ; 'P'; void *
0x18009b4bc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18009b4c2  mov     r9d, 80070057h; char *
0x18009b4c8  lea     r8, aOnecoreBaseDev_20; "onecore\\base\\devices\\cam\\winrt\\mcp"...
0x18009b4cf  mov     edx, 51h ; 'Q'; void *
0x18009b4d4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18009b4da  mov     r9d, 80070057h; char *
0x18009b4e0  lea     r8, aOnecoreBaseDev_20; "onecore\\base\\devices\\cam\\winrt\\mcp"...
0x18009b4e7  mov     edx, 55h ; 'U'; void *
0x18009b4ec  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
