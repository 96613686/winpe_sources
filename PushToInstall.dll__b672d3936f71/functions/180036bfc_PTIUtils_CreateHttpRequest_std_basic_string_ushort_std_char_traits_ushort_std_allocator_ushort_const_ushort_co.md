# PTIUtils::CreateHttpRequest(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,ushort const *)

- ea: `0x180036bfc`
- end: `0x180036ec2`
- name: `?CreateHttpRequest@PTIUtils@@YA?AVHttpRequest@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG@Z`
- size: `710`
- prototype: `char *__fastcall(char *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `20`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180032ac0`
- `0x1800354bc`

## callees

- `0x1800026b0`
- `0x18000dc5b`
- `0x180010b84`
- `0x18002008c`
- `0x18002d5f8`
- `0x18002d674`
- `0x180030a68`
- `0x180030aac`
- `0x180031dd4`
- `0x180034948`
- `0x180034d14`
- `0x180036174`
- `0x180036af4`
- `0x180036b80`
- `0x180036bfc`
- `0x180037b8c`
- `0x1800403c4`
- `0x180042640`
- `0x1800467fc`
- `0x18004f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180036c52`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180036c52`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180036c65`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180036c65`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180036c73`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180036c73`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180036de9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180036de9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180036d5d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180036e0e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180036d5d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180036e0e`

## string_xrefs

- `0x180036e94`: `onecoreuap\enduser\winstore\pushtoinstall\lib\ptiutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
char *__fastcall PTIUtils::CreateHttpRequest(
        char *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  HANDLE CurrentThread; // rax
  WinStoreAuth::AuthenticationInternal *v6; // rcx
  BOOL v7; // eax
  const char *v8; // r9
  void *v9; // rdx
  unsigned int v10; // r8d
  const char *v11; // r9
  void **v12; // rbx
  const void *v13; // rdx
  WinStoreAuth::AuthenticationInternal *v14; // rcx
  HSTRING *v15; // r8
  int DeviceTicketWithBroker; // eax
  int v17; // ebx
  _WORD *v18; // rbx
  PCWSTR StringRawBuffer; // rax
  unsigned __int64 v20; // r8
  __int64 v21; // rax
  HSTRING string; // [rsp+20h] [rbp-49h] BYREF
  int v24; // [rsp+28h] [rbp-41h]
  void **v25; // [rsp+30h] [rbp-39h] BYREF
  void *TokenHandle[3]; // [rsp+38h] [rbp-31h] BYREF
  void *Src[2]; // [rsp+50h] [rbp-19h] BYREF
  __int64 v28; // [rsp+60h] [rbp-9h]
  unsigned __int64 v29; // [rsp+68h] [rbp-1h]
  __int128 v30; // [rsp+70h] [rbp+7h] BYREF
  __int128 v31; // [rsp+80h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  TokenHandle[1] = a1;
  v24 = 0;
  if ( *((_QWORD *)a2 + 3) > 7u )
    a2 = *(const unsigned __int16 **)a2;
  HttpRequest::HttpRequest((HttpRequest *)a1, a2, a3, a4);
  v24 = 1;
  v25 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
  TokenHandle[0] = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 4u, 1, TokenHandle) )
  {
    v7 = SetThreadToken(0, 0);
    v6 = retaddr;
    if ( !v7 )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0xB7,
        (int)"onecoreuap\\enduser\\winstore\\inc\\RAIIhelpers.h",
        v8);
  }
  *(_OWORD *)Src = 0;
  v28 = 0;
  v29 = 7;
  LOWORD(Src[0]) = 0;
  if ( WinStoreAuth::AuthenticationInternal::IsPlatformXbox(v6) )
  {
    v30 = 0;
    *(_QWORD *)&v31 = 0;
    string = 0;
    GatherXToken(&v30, &string);
    if ( !((__int64)(*((_QWORD *)&v30 + 1) - v30) >> 6) )
      wil::details::in1diag3::_Throw_Win32(retaddr, v9, v10, v11, (unsigned int)string);
    if ( v29 < 7 )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(Src);
    }
    else
    {
      v12 = Src;
      if ( v29 > 7 )
        v12 = (void **)Src[0];
      v28 = 7;
      memmove_0(v12, L"XBL3.0 ", 0xEu);
      *((_WORD *)v12 + 7) = 0;
    }
    v13 = (const void *)v30;
    if ( *(_QWORD *)(v30 + 24) > 7u )
      v13 = *(const void **)v30;
    std::wstring::_Append<unsigned short>(Src, v13, *(_QWORD *)(v30 + 16));
    if ( string )
      (*(void (__fastcall **)(HSTRING))(*(_QWORD *)string + 16LL))(string);
    std::vector<StoredTicket>::~vector<StoredTicket>(&v30);
  }
  else
  {
    WindowsDeleteString(0);
    string = 0;
    DeviceTicketWithBroker = WinStoreAuth::AuthenticationInternal::GetDeviceTicketWithBroker(v14, (bool)&string, v15);
    v17 = DeviceTicketWithBroker;
    if ( DeviceTicketWithBroker >= 0 )
      v17 = 0;
    else
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x30E,
        (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
        (const char *)(unsigned int)DeviceTicketWithBroker,
        (int)string);
    if ( v17 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x31,
        (int)"onecoreuap\\enduser\\winstore\\pushtoinstall\\lib\\ptiutils.cpp",
        (const char *)(unsigned int)v17,
        (int)string);
    if ( v29 < 0x10 )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(Src);
    }
    else
    {
      v18 = Src[0];
      v28 = 16;
      memmove_0(Src[0], L"Bearer MSAHW1.0=", 0x20u);
      v18[16] = 0;
    }
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v20 = -1;
    do
      ++v20;
    while ( StringRawBuffer[v20] );
    std::wstring::_Append<unsigned short>(Src, StringRawBuffer, v20);
    WindowsDeleteString(string);
  }
  v30 = 0;
  v31 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v30, L"authorization", 0xDu);
  v21 = std::map<std::wstring,std::wstring>::operator[](a1 + 248, &v30);
  std::wstring::operator=(v21, Src);
  std::wstring::_Tidy_deallocate((char **)&v30);
  std::wstring::_Tidy_deallocate((char **)Src);
  SuspendImpersonationScope::~SuspendImpersonationScope((SuspendImpersonationScope *)&v25);
  return a1;
}

```

## disassembly

```asm
0x180036bfc  push    rbp
0x180036bfe  push    rbx
0x180036bff  push    rsi
0x180036c00  push    rdi
0x180036c01  push    r14
0x180036c03  lea     rbp, [rsp-37h]
0x180036c08  sub     rsp, 0A0h
0x180036c0f  mov     rax, cs:__security_cookie
0x180036c16  xor     rax, rsp
0x180036c19  mov     [rbp+57h+var_30], rax
0x180036c1d  mov     rdi, rcx
0x180036c20  mov     [rbp+57h+var_80], rcx
0x180036c24  xor     esi, esi
0x180036c26  mov     [rbp+57h+var_98], esi
0x180036c29  lea     r14d, [rsi+7]
0x180036c2d  cmp     [rdx+18h], r14
0x180036c31  jbe     short loc_180036C36
0x180036c33  mov     rdx, [rdx]; unsigned __int16 *
0x180036c36  call    ??0HttpRequest@@QEAA@PEBG00@Z; HttpRequest::HttpRequest(ushort const *,ushort const *,ushort const *)
0x180036c3b  mov     ebx, 1
0x180036c40  mov     [rbp+57h+var_98], ebx
0x180036c43  lea     rax, ??_7?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable'
0x180036c4a  mov     [rbp+57h+var_90], rax
0x180036c4e  mov     [rbp+57h+TokenHandle], rsi
0x180036c52  call    cs:__imp_GetCurrentThread
0x180036c58  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x180036c5c  mov     r8d, ebx; OpenAsSelf
0x180036c5f  lea     edx, [rbx+3]; DesiredAccess
0x180036c62  mov     rcx, rax; ThreadHandle
0x180036c65  call    cs:__imp_OpenThreadToken
0x180036c6b  test    eax, eax
0x180036c6d  jz      short loc_180036C85
0x180036c6f  xor     edx, edx; Token
0x180036c71  xor     ecx, ecx; Thread
0x180036c73  call    cs:__imp_SetThreadToken
0x180036c79  mov     rcx, [rbp+5Fh]; this
0x180036c7d  test    eax, eax
0x180036c7f  jz      loc_180036EA6
0x180036c85  xorps   xmm0, xmm0
0x180036c88  movups  xmmword ptr [rbp+57h+Src], xmm0
0x180036c8c  mov     [rbp+57h+var_60], rsi
0x180036c90  mov     [rbp+57h+var_58], r14
0x180036c94  mov     word ptr [rbp+57h+Src], si
0x180036c98  call    ?IsPlatformXbox@AuthenticationInternal@WinStoreAuth@@YA_NXZ; WinStoreAuth::AuthenticationInternal::IsPlatformXbox(void)
0x180036c9d  test    al, al
0x180036c9f  jz      loc_180036D57
0x180036ca5  xorps   xmm0, xmm0
0x180036ca8  movdqu  [rbp+57h+var_50], xmm0
0x180036cad  mov     qword ptr [rbp+57h+var_40], rsi
0x180036cb1  mov     [rbp+57h+string], rsi
0x180036cb5  lea     rdx, [rbp+57h+string]
0x180036cb9  lea     rcx, [rbp+57h+var_50]
0x180036cbd  call    ?GatherXToken@@YAXAEAV?$vector@UStoredTicket@@V?$allocator@UStoredTicket@@@std@@@std@@AEAV?$ComPtr@U?$IVector@PEAUIInspectable@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Z; GatherXToken(std::vector<StoredTicket> &,Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<IInspectable *>> &)
0x180036cc2  mov     rax, qword ptr [rbp+57h+var_50+8]
0x180036cc6  sub     rax, qword ptr [rbp+57h+var_50]
0x180036cca  sar     rax, 6
0x180036cce  test    rax, rax
0x180036cd1  jz      loc_180036EB8
0x180036cd7  cmp     [rbp+57h+var_58], r14
0x180036cdb  jb      short loc_180036D05
0x180036cdd  lea     rbx, [rbp+57h+Src]
0x180036ce1  cmova   rbx, [rbp+57h+Src]
0x180036ce6  mov     [rbp+57h+var_60], r14
0x180036cea  mov     r8d, 0Eh; Size
0x180036cf0  lea     rdx, aXbl30; "XBL3.0 "
0x180036cf7  mov     rcx, rbx; void *
0x180036cfa  call    memmove_0
0x180036cff  mov     [rbx+0Eh], si
0x180036d03  jmp     short loc_180036D18
0x180036d05  lea     r9, aXbl30; "XBL3.0 "
0x180036d0c  mov     rdx, r14
0x180036d0f  lea     rcx, [rbp+57h+Src]
0x180036d13  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180036d18  mov     rdx, qword ptr [rbp+57h+var_50]
0x180036d1c  mov     r8, [rdx+10h]
0x180036d20  cmp     [rdx+18h], r14
0x180036d24  jbe     short loc_180036D29
0x180036d26  mov     rdx, [rdx]
0x180036d29  lea     rcx, [rbp+57h+Src]; Src
0x180036d2d  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180036d32  nop
0x180036d33  mov     rcx, [rbp+57h+string]
0x180036d37  test    rcx, rcx
0x180036d3a  jz      short loc_180036D49
0x180036d3c  mov     rax, [rcx]
0x180036d3f  mov     rax, [rax+10h]
0x180036d43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036d48  nop
0x180036d49  lea     rcx, [rbp+57h+var_50]
0x180036d4d  call    ??1?$vector@UStoredTicket@@V?$allocator@UStoredTicket@@@std@@@std@@QEAA@XZ; std::vector<StoredTicket>::~vector<StoredTicket>(void)
0x180036d52  jmp     loc_180036E14
0x180036d57  mov     [rbp+57h+string], rsi
0x180036d5b  xor     ecx, ecx; string
0x180036d5d  call    cs:__imp_WindowsDeleteString
0x180036d63  mov     [rbp+57h+string], rsi
0x180036d67  lea     rdx, [rbp+57h+string]; bool
0x180036d6b  call    ?GetDeviceTicketWithBroker@AuthenticationInternal@WinStoreAuth@@YAJ_NPEAPEAUHSTRING__@@@Z; WinStoreAuth::AuthenticationInternal::GetDeviceTicketWithBroker(bool,HSTRING__ * *)
0x180036d70  mov     ebx, eax
0x180036d72  test    eax, eax
0x180036d74  jns     short loc_180036D90
0x180036d76  mov     rcx, [rbp+5Fh]; this
0x180036d7a  mov     r9d, eax; char *
0x180036d7d  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x180036d84  mov     edx, 30Eh; void *
0x180036d89  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180036d8e  jmp     short loc_180036D92
0x180036d90  mov     ebx, esi
0x180036d92  mov     rcx, [rbp+5Fh]; this
0x180036d96  test    ebx, ebx
0x180036d98  js      loc_180036E91
0x180036d9e  mov     edx, 10h
0x180036da3  cmp     [rbp+57h+var_58], rdx
0x180036da7  jb      short loc_180036DD3
0x180036da9  lea     rbx, [rbp+57h+Src]
0x180036dad  cmp     [rbp+57h+var_58], r14
0x180036db1  cmova   rbx, [rbp+57h+Src]
0x180036db6  mov     [rbp+57h+var_60], rdx
0x180036dba  lea     r8d, [rdx+10h]; Size
0x180036dbe  lea     rdx, aBearerMsahw10; "Bearer MSAHW1.0="
0x180036dc5  mov     rcx, rbx; void *
0x180036dc8  call    memmove_0
0x180036dcd  mov     [rbx+20h], si
0x180036dd1  jmp     short loc_180036DE3
0x180036dd3  lea     r9, aBearerMsahw10; "Bearer MSAHW1.0="
0x180036dda  lea     rcx, [rbp+57h+Src]
0x180036dde  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180036de3  xor     edx, edx; length
0x180036de5  mov     rcx, [rbp+57h+string]; string
0x180036de9  call    cs:__imp_WindowsGetStringRawBuffer
0x180036def  or      r8, 0FFFFFFFFFFFFFFFFh
0x180036df3  inc     r8
0x180036df6  cmp     [rax+r8*2], si
0x180036dfb  jnz     short loc_180036DF3
0x180036dfd  mov     rdx, rax
0x180036e00  lea     rcx, [rbp+57h+Src]; Src
0x180036e04  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180036e09  nop
0x180036e0a  mov     rcx, [rbp+57h+string]; string
0x180036e0e  call    cs:__imp_WindowsDeleteString
0x180036e14  xorps   xmm0, xmm0
0x180036e17  movups  [rbp+57h+var_50], xmm0
0x180036e1b  xorps   xmm1, xmm1
0x180036e1e  movdqu  [rbp+57h+var_40], xmm1
0x180036e23  mov     r8d, 0Dh
0x180036e29  lea     rdx, aAuthorization; "authorization"
0x180036e30  lea     rcx, [rbp+57h+var_50]
0x180036e34  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180036e39  nop
0x180036e3a  lea     rcx, [rdi+0F8h]
0x180036e41  lea     rdx, [rbp+57h+var_50]
0x180036e45  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::map<std::wstring,std::wstring>::operator[](std::wstring &&)
0x180036e4a  mov     rcx, rax
0x180036e4d  lea     rdx, [rbp+57h+Src]
0x180036e51  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180036e56  nop
0x180036e57  lea     rcx, [rbp+57h+var_50]
0x180036e5b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180036e60  nop
0x180036e61  lea     rcx, [rbp+57h+Src]
0x180036e65  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180036e6a  nop
0x180036e6b  lea     rcx, [rbp+57h+var_90]; this
0x180036e6f  call    ??1SuspendImpersonationScope@@QEAA@XZ; SuspendImpersonationScope::~SuspendImpersonationScope(void)
0x180036e74  mov     rax, rdi
0x180036e77  mov     rcx, [rbp+57h+var_30]
0x180036e7b  xor     rcx, rsp; StackCookie
0x180036e7e  call    __security_check_cookie
0x180036e83  add     rsp, 0A0h
0x180036e8a  pop     r14
0x180036e8c  pop     rdi
0x180036e8d  pop     rsi
0x180036e8e  pop     rbx
0x180036e8f  pop     rbp
0x180036e90  retn
0x180036e91  mov     r9d, ebx; char *
0x180036e94  lea     r8, aOnecoreuapEndu_10; "onecoreuap\\enduser\\winstore\\pushtoin"...
0x180036e9b  mov     edx, 31h ; '1'; void *
0x180036ea0  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180036ea6  lea     r8, aOnecoreuapEndu_3; "onecoreuap\\enduser\\winstore\\inc\\RAI"...
0x180036ead  mov     edx, 0B7h; void *
0x180036eb2  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180036eb8  mov     rcx, [rbp+5Fh]; this
0x180036ebc  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
```
