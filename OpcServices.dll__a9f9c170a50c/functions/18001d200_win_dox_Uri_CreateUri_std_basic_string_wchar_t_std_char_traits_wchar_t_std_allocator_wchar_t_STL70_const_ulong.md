# win_dox::Uri::CreateUri(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>,_STL70> const &,ulong)

- ea: `0x18001d200`
- end: `0x18001d381`
- name: `?CreateUri@Uri@win_dox@@SA?AV12@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@K@Z`
- size: `385`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `9`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800172f4`
- `0x180018d18`
- `0x180019664`
- `0x18001ad00`
- `0x18005ad78`
- `0x18006b6d0`
- `0x18006bed0`
- `0x18009ae70`
- `0x1800be324`

## callees

- `0x18000d4d8`
- `0x180015a68`
- `0x18001d200`
- `0x1800517a0`
- `0x1800cd38c`
- `0x1800d5fe4`
- `0x180117740`
- `0x18012a010`

## import_xrefs

- `urlmon!CreateUri` at `0x18001d250`
- `urlmon!CreateUri` at `0x18001d250`

## string_xrefs

- `0x18001d325`: `Call to ::CreateUri failed with HResult 0x%X.`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall win_dox::Uri::CreateUri(__int64 a1, __int64 a2, DWORD a3)
{
  const WCHAR *v4; // rcx
  HRESULT Uri; // ebx
  IUri *v6; // rbx
  IUri *v8; // [rsp+40h] [rbp-4F8h] BYREF
  IUri *ppURI[5]; // [rsp+48h] [rbp-4F0h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+70h] [rbp-4C8h] BYREF
  wchar_t v11[512]; // [rsp+110h] [rbp-428h] BYREF

  ppURI[2] = (IUri *)-2LL;
  ppURI[0] = 0;
  v4 = (const WCHAR *)(a2 + 8);
  if ( *(_QWORD *)(a2 + 32) >= 8u )
    v4 = *(const WCHAR **)v4;
  Uri = CreateUri(v4, a3, 0, ppURI);
  if ( Uri < 0 )
  {
    memset_0(v11, 0, sizeof(v11));
    StringCchPrintfW(v11, 0x200u, L"Call to ::CreateUri failed with HResult 0x%X.", (unsigned int)Uri);
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x20Fu,
      Uri,
      (struct win_musl::TStringEllipseBase *)v11);
    throw (SplException::THResultException *)pExceptionObject;
  }
  v8 = 0;
  v6 = ppURI[0];
  if ( ppURI[0] )
    ((void (__fastcall *)(IUri *))ppURI[0]->lpVtbl->AddRef)(ppURI[0]);
  else
    v6 = 0;
  v8 = v6;
  ppURI[3] = (IUri *)&v8;
  win_dox::to_interface<IByteReceiver>::resolve(a1, &v8);
  if ( v8 )
    ((void (__fastcall *)(IUri *))v8->lpVtbl->Release)(v8);
  if ( ppURI[0] )
    ((void (__fastcall *)(IUri *, struct IUriVtbl *))ppURI[0]->lpVtbl->Release)(ppURI[0], ppURI[0]->lpVtbl);
  return a1;
}

```

## disassembly

```asm
0x18001d200  push    rbx
0x18001d202  push    rsi
0x18001d203  push    rdi
0x18001d204  sub     rsp, 520h
0x18001d20b  mov     [rsp+538h+var_4E0], 0FFFFFFFFFFFFFFFEh
0x18001d214  mov     rax, cs:__security_cookie
0x18001d21b  xor     rax, rsp
0x18001d21e  mov     [rsp+538h+var_28], rax
0x18001d226  mov     eax, r8d
0x18001d229  mov     rdi, rcx
0x18001d22c  mov     [rsp+538h+ppURI], rcx
0x18001d231  xor     esi, esi
0x18001d233  mov     [rsp+538h+ppURI], rsi
0x18001d238  lea     rcx, [rdx+8]
0x18001d23c  cmp     qword ptr [rdx+20h], 8
0x18001d241  jb      short loc_18001D246
0x18001d243  mov     rcx, [rcx]; pwzURI
0x18001d246  lea     r9, [rsp+538h+ppURI]; ppURI
0x18001d24b  xor     r8d, r8d; dwReserved
0x18001d24e  mov     edx, eax; dwFlags
0x18001d250  call    cs:__imp_CreateUri
0x18001d256  mov     ebx, eax
0x18001d258  test    eax, eax
0x18001d25a  js      loc_18001D30D
0x18001d260  mov     rcx, rsi
0x18001d263  mov     [rsp+538h+var_4F8], rcx
0x18001d268  mov     rbx, [rsp+538h+ppURI]
0x18001d26d  test    rbx, rbx
0x18001d270  jnz     short loc_18001D2E3
0x18001d272  mov     rbx, rsi
0x18001d275  mov     [rsp+538h+var_4F8], rbx
0x18001d27a  test    rcx, rcx
0x18001d27d  jnz     short loc_18001D2FC
0x18001d27f  lea     rax, [rsp+538h+var_4F8]
0x18001d284  mov     [rsp+538h+var_4D8], rax
0x18001d289  lea     rdx, [rsp+538h+var_4F8]
0x18001d28e  mov     rcx, rdi
0x18001d291  call    ?resolve@?$to_interface@UIByteReceiver@@@win_dox@@SA?AV?$scope@PEAUIByteReceiver@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@AEBV34@@Z; win_dox::to_interface<IByteReceiver>::resolve(win_scope::scope<IByteReceiver *,win_scope::const_policies<win_scope::com_policies>> const &)
0x18001d296  nop
0x18001d297  mov     rcx, [rsp+538h+var_4F8]
0x18001d29c  test    rcx, rcx
0x18001d29f  jz      short loc_18001D2AE
0x18001d2a1  mov     rax, [rcx]
0x18001d2a4  mov     rax, [rax+10h]
0x18001d2a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d2ad  nop
0x18001d2ae  mov     rcx, [rsp+538h+ppURI]
0x18001d2b3  test    rcx, rcx
0x18001d2b6  jz      short loc_18001D2C5
0x18001d2b8  mov     rdx, [rcx]
0x18001d2bb  mov     rax, [rdx+10h]
0x18001d2bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d2c4  nop
0x18001d2c5  mov     rax, rdi
0x18001d2c8  mov     rcx, [rsp+538h+var_28]
0x18001d2d0  xor     rcx, rsp; StackCookie
0x18001d2d3  call    __security_check_cookie
0x18001d2d8  add     rsp, 520h
0x18001d2df  pop     rdi
0x18001d2e0  pop     rsi
0x18001d2e1  pop     rbx
0x18001d2e2  retn
0x18001d2e3  mov     rax, [rbx]
0x18001d2e6  mov     rcx, rbx
0x18001d2e9  mov     rax, [rax+8]
0x18001d2ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d2f2  mov     rcx, [rsp+538h+var_4F8]
0x18001d2f7  jmp     loc_18001D275
0x18001d2fc  mov     rax, [rcx]
0x18001d2ff  mov     rax, [rax+10h]
0x18001d303  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d308  jmp     loc_18001D27F
0x18001d30d  xor     edx, edx; Val
0x18001d30f  mov     r8d, 400h; Size
0x18001d315  lea     rcx, [rsp+538h+var_428]; void *
0x18001d31d  call    memset_0
0x18001d322  mov     r9d, ebx
0x18001d325  lea     r8, aCallToCreateur; "Call to ::CreateUri failed with HResult"...
0x18001d32c  mov     edx, 200h; unsigned __int64
0x18001d331  lea     rcx, [rsp+538h+var_428]; wchar_t *
0x18001d339  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18001d33e  lea     rax, [rsp+538h+var_428]
0x18001d346  mov     [rsp+538h+var_508], rax; struct win_musl::TStringEllipseBase *
0x18001d34b  mov     [rsp+538h+var_510], ebx; unsigned int
0x18001d34f  mov     [rsp+538h+var_518], 20Fh; unsigned int
0x18001d357  lea     r9, word_18013A0B6
0x18001d35e  lea     r8, aNoFilename; "(no filename)"
0x18001d365  lea     rcx, [rsp+538h+pExceptionObject]; this
0x18001d36a  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18001d36f  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18001d376  lea     rcx, [rsp+538h+pExceptionObject]; pExceptionObject
0x18001d37b  call    _CxxThrowException_0
```
