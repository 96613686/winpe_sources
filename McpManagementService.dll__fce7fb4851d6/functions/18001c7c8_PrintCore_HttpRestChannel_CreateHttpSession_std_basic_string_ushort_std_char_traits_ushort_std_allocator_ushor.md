# PrintCore::HttpRestChannel::_CreateHttpSession(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,int)

- ea: `0x18001c7c8`
- end: `0x18001c9a1`
- name: `?_CreateHttpSession@HttpRestChannel@PrintCore@@AEAA?AUHttpContext@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@H@Z`
- size: `473`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, int)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x18001d7dc`

## callees

- `0x180003a60`
- `0x18000e164`
- `0x180011c58`
- `0x1800129c4`
- `0x180012bfc`
- `0x180012c30`
- `0x18001c0f4`
- `0x18001c7c8`
- `0x18001c9a8`
- `0x18001d29c`

## import_xrefs

- `WINHTTP!WinHttpOpen` at `0x18001c842`
- `WINHTTP!WinHttpOpen` at `0x18001c842`
- `WINHTTP!WinHttpQueryOption` at `0x18001c8aa`
- `WINHTTP!WinHttpQueryOption` at `0x18001c8aa`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18001c8e3`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18001c8ed`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18001c8e3`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18001c8ed`

## string_xrefs

- `0x18001c8d3`: `PrintCore::HttpRestChannel::_CreateHttpSession`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall PrintCore::HttpRestChannel::_CreateHttpSession(__int64 a1, __int64 a2, __int64 a3, int a4)
{
  const WCHAR *v7; // rax
  __int64 v8; // rax
  void *v9; // rdx
  unsigned int v10; // r8d
  const char *v11; // r9
  __int64 dwFlags; // [rsp+20h] [rbp-99h]
  DWORD dwBufferLength[4]; // [rsp+30h] [rbp-89h] BYREF
  HINTERNET v15[2]; // [rsp+40h] [rbp-79h] BYREF
  __int128 Buffer; // [rsp+50h] [rbp-69h] BYREF
  HGLOBAL hMem; // [rsp+60h] [rbp-59h]
  _BYTE v18[8]; // [rsp+70h] [rbp-49h] BYREF
  std::_Ref_count_base *v19; // [rsp+78h] [rbp-41h]
  __int128 v20; // [rsp+80h] [rbp-39h] BYREF
  __int128 v21; // [rsp+90h] [rbp-29h]
  __int128 v22; // [rsp+A0h] [rbp-19h]
  __int128 v23; // [rsp+B0h] [rbp-9h] BYREF
  __m128i si128; // [rsp+C0h] [rbp+7h]
  __int64 v25; // [rsp+D0h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  v20 = 0;
  v21 = 0;
  v22 = 0;
  v23 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v23) = 0;
  v25 = 0;
  v7 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1 + 72);
  v15[0] = WinHttpOpen(v7, 4u, 0, 0, 0);
  v8 = std::make_shared<PrintCore::HInternetRAII,void *>(v18, v15);
  std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::operator=(
    &v20,
    v8);
  if ( v19 )
    std::_Ref_count_base::_Decref(v19);
  LODWORD(v25) = a4;
  std::wstring::operator=(&v23, a3);
  Buffer = 0;
  hMem = 0;
  dwBufferLength[0] = 24;
  if ( !WinHttpQueryOption(*(HINTERNET *)v20, 0x26u, &Buffer, dwBufferLength) )
    wil::details::in1diag3::_Log_GetLastError(retaddr, v9, v10, v11);
  LODWORD(dwFlags) = v25;
  HttpRestTelemetry::WriteDbgTraceInfo(
    "PrintCore::HttpRestChannel::_CreateHttpSession",
    L"HTTP proxy settings: proxy=%ws, bypass list=%ws, HttpRequestId: %d",
    *((_QWORD *)&Buffer + 1),
    hMem,
    dwFlags);
  GlobalFree(*((HGLOBAL *)&Buffer + 1));
  GlobalFree(hMem);
  *(_OWORD *)a2 = v20;
  v20 = 0;
  *(_OWORD *)(a2 + 16) = v21;
  v21 = 0;
  *(_OWORD *)(a2 + 32) = v22;
  v22 = 0;
  *(_OWORD *)(a2 + 48) = v23;
  *(__m128i *)(a2 + 64) = si128;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v23) = 0;
  *(_DWORD *)(a2 + 80) = v25;
  PrintCore::HttpContext::~HttpContext((PrintCore::HttpContext *)&v20);
  return a2;
}

```

## disassembly

```asm
0x18001c7c8  push    rbp
0x18001c7ca  push    rbx
0x18001c7cb  push    rsi
0x18001c7cc  push    rdi
0x18001c7cd  lea     rbp, [rsp-3Fh]
0x18001c7d2  sub     rsp, 0F8h
0x18001c7d9  mov     rax, cs:__security_cookie
0x18001c7e0  xor     rax, rsp
0x18001c7e3  mov     [rbp+57h+var_30], rax
0x18001c7e7  mov     esi, r9d
0x18001c7ea  mov     rdi, r8
0x18001c7ed  mov     rbx, rdx
0x18001c7f0  mov     [rbp+57h+var_D0], rdx
0x18001c7f4  xorps   xmm0, xmm0
0x18001c7f7  xorps   xmm1, xmm1
0x18001c7fa  movdqa  [rbp+57h+var_90], xmm1
0x18001c7ff  movdqa  [rbp+57h+var_80], xmm1
0x18001c804  movdqa  [rbp+57h+var_70], xmm1
0x18001c809  movups  [rbp+57h+var_60], xmm0
0x18001c80d  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18001c815  movdqa  [rbp+57h+var_50], xmm1
0x18001c81a  xor     eax, eax
0x18001c81c  mov     word ptr [rbp+57h+var_60], ax
0x18001c820  mov     [rbp+57h+var_40], rax
0x18001c824  add     rcx, 48h ; 'H'
0x18001c828  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001c82d  mov     [rsp+110h+dwFlags], 0; dwFlags
0x18001c835  xor     r9d, r9d; pszProxyBypassW
0x18001c838  xor     r8d, r8d; pszProxyW
0x18001c83b  lea     edx, [r9+4]; dwAccessType
0x18001c83f  mov     rcx, rax; pszAgentW
0x18001c842  call    cs:__imp_WinHttpOpen
0x18001c848  mov     [rbp+57h+var_D0], rax
0x18001c84c  lea     rdx, [rbp+57h+var_D0]
0x18001c850  lea     rcx, [rbp+57h+var_A0]
0x18001c854  call    ??$make_shared@VHInternetRAII@PrintCore@@PEAX@std@@YA?AV?$shared_ptr@VHInternetRAII@PrintCore@@@0@$$QEAPEAX@Z; std::make_shared<PrintCore::HInternetRAII,void *>(void * &&)
0x18001c859  mov     rdx, rax
0x18001c85c  lea     rcx, [rbp+57h+var_90]
0x18001c860  call    ??4?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::operator=(std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>> &&)
0x18001c865  mov     rcx, [rbp+57h+var_98]; this
0x18001c869  test    rcx, rcx
0x18001c86c  jz      short loc_18001C873
0x18001c86e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001c873  mov     dword ptr [rbp+57h+var_40], esi
0x18001c876  mov     rdx, rdi
0x18001c879  lea     rcx, [rbp+57h+var_60]
0x18001c87d  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18001c882  xorps   xmm0, xmm0
0x18001c885  xor     eax, eax
0x18001c887  movups  [rbp+57h+Buffer], xmm0
0x18001c88b  mov     [rbp+57h+hMem], rax
0x18001c88f  mov     [rsp+110h+dwBufferLength], 18h
0x18001c897  lea     r9, [rsp+110h+dwBufferLength]; lpdwBufferLength
0x18001c89c  lea     r8, [rbp+57h+Buffer]; lpBuffer
0x18001c8a0  lea     edx, [rax+26h]; dwOption
0x18001c8a3  mov     rcx, qword ptr [rbp+57h+var_90]
0x18001c8a7  mov     rcx, [rcx]; hInternet
0x18001c8aa  call    cs:__imp_WinHttpQueryOption
0x18001c8b0  mov     rcx, [rbp+5Fh]; this
0x18001c8b4  test    eax, eax
0x18001c8b6  jnz     short loc_18001C8BD
0x18001c8b8  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18001c8bd  mov     eax, dword ptr [rbp+57h+var_40]
0x18001c8c0  mov     [rsp+110h+dwFlags], eax
0x18001c8c4  mov     r9, [rbp+57h+hMem]
0x18001c8c8  mov     r8, qword ptr [rbp+57h+Buffer+8]
0x18001c8cc  lea     rdx, aHttpProxySetti; "HTTP proxy settings: proxy=%ws, bypass "...
0x18001c8d3  lea     rcx, aPrintcoreHttpr_4; "PrintCore::HttpRestChannel::_CreateHttp"...
0x18001c8da  call    ?WriteDbgTraceInfo@HttpRestTelemetry@@SAXPEBDPEBGZZ; HttpRestTelemetry::WriteDbgTraceInfo(char const *,ushort const *,...)
0x18001c8df  mov     rcx, qword ptr [rbp+57h+Buffer+8]; hMem
0x18001c8e3  call    cs:__imp_GlobalFree
0x18001c8e9  mov     rcx, [rbp+57h+hMem]; hMem
0x18001c8ed  call    cs:__imp_GlobalFree
0x18001c8f3  mov     rax, qword ptr [rbp+57h+var_90]
0x18001c8f7  mov     [rbx], rax
0x18001c8fa  mov     rax, qword ptr [rbp+57h+var_90+8]
0x18001c8fe  mov     [rbx+8], rax
0x18001c902  xorps   xmm0, xmm0
0x18001c905  movdqa  [rbp+57h+var_90], xmm0
0x18001c90a  mov     rax, qword ptr [rbp+57h+var_80]
0x18001c90e  mov     [rbx+10h], rax
0x18001c912  mov     rax, qword ptr [rbp+57h+var_80+8]
0x18001c916  mov     [rbx+18h], rax
0x18001c91a  movdqa  [rbp+57h+var_80], xmm0
0x18001c91f  mov     rax, qword ptr [rbp+57h+var_70]
0x18001c923  mov     [rbx+20h], rax
0x18001c927  mov     rax, qword ptr [rbp+57h+var_70+8]
0x18001c92b  mov     [rbx+28h], rax
0x18001c92f  movdqa  [rbp+57h+var_70], xmm0
0x18001c934  movzx   eax, word ptr [rbp+57h+var_60]
0x18001c938  mov     [rbx+30h], ax
0x18001c93c  movsd   xmm0, qword ptr [rbp+57h+var_60+2]
0x18001c941  movsd   qword ptr [rbx+32h], xmm0
0x18001c946  mov     eax, dword ptr [rbp+57h+var_60+0Ah]
0x18001c949  mov     [rbx+3Ah], eax
0x18001c94c  movzx   eax, word ptr [rbp+57h+var_60+0Eh]
0x18001c950  mov     [rbx+3Eh], ax
0x18001c954  mov     rcx, qword ptr [rbp+57h+var_50]
0x18001c958  mov     [rbx+40h], rcx
0x18001c95c  mov     rcx, qword ptr [rbp+57h+var_50+8]
0x18001c960  mov     [rbx+48h], rcx
0x18001c964  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x18001c96c  movdqa  [rbp+57h+var_50], xmm0
0x18001c971  xor     ecx, ecx
0x18001c973  mov     word ptr [rbp+57h+var_60], cx
0x18001c977  mov     ecx, dword ptr [rbp+57h+var_40]
0x18001c97a  mov     [rbx+50h], ecx
0x18001c97d  lea     rcx, [rbp+57h+var_90]; this
0x18001c981  call    ??1HttpContext@PrintCore@@QEAA@XZ; PrintCore::HttpContext::~HttpContext(void)
0x18001c986  mov     rax, rbx
0x18001c989  mov     rcx, [rbp+57h+var_30]
0x18001c98d  xor     rcx, rsp; StackCookie
0x18001c990  call    __security_check_cookie
0x18001c995  add     rsp, 0F8h
0x18001c99c  pop     rdi
0x18001c99d  pop     rsi
0x18001c99e  pop     rbx
0x18001c99f  pop     rbp
0x18001c9a0  retn
```
