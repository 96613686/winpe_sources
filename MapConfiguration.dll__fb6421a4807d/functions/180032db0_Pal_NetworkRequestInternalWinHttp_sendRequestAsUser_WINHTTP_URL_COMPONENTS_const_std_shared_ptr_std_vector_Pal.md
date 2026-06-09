# Pal::NetworkRequestInternalWinHttp::sendRequestAsUser(_WINHTTP_URL_COMPONENTS const &,std::shared_ptr<std::vector<Pal::HttpHeader,std::allocator<Pal::HttpHeader>>> const &)

- ea: `0x180032db0`
- end: `0x1800331f2`
- name: `?sendRequestAsUser@NetworkRequestInternalWinHttp@Pal@@MEAAKAEBU_WINHTTP_URL_COMPONENTS@@AEBV?$shared_ptr@V?$vector@VHttpHeader@Pal@@V?$allocator@VHttpHeader@Pal@@@std@@@std@@@std@@@Z`
- size: `1090`
- prototype: `__int64 __fastcall(DWORD_PTR dwContext)`
- caller_count: `1`
- callee_count: `20`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180033200`

## callees

- `0x1800094a0`
- `0x180009988`
- `0x18000ba50`
- `0x18000c2f8`
- `0x18000c354`
- `0x18000c3d0`
- `0x18000c850`
- `0x18000cb24`
- `0x18000d5f0`
- `0x18000fbfc`
- `0x180013da8`
- `0x1800153b4`
- `0x1800153e8`
- `0x18002f430`
- `0x18002fc4c`
- `0x180031f18`
- `0x180031f2c`
- `0x180032008`
- `0x180032300`
- `0x180032db0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032e77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032f83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003318c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032e77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032f83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003318c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180032f23`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180032f23`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180032f76`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180032f76`
- `WINHTTP!WinHttpSetStatusCallback` at `0x1800330ed`
- `WINHTTP!WinHttpSetStatusCallback` at `0x1800330ed`
- `WINHTTP!WinHttpConnect` at `0x180032e62`
- `WINHTTP!WinHttpConnect` at `0x180032e62`
- `WINHTTP!WinHttpOpen` at `0x180032e37`
- `WINHTTP!WinHttpOpen` at `0x180032e37`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x180033052`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x180033052`
- `WINHTTP!WinHttpSetOption` at `0x1800330a3`
- `WINHTTP!WinHttpSetOption` at `0x1800330cc`
- `WINHTTP!WinHttpSetOption` at `0x1800330a3`
- `WINHTTP!WinHttpSetOption` at `0x1800330cc`
- `WINHTTP!WinHttpOpenRequest` at `0x180032ecf`
- `WINHTTP!WinHttpOpenRequest` at `0x180032ecf`
- `WINHTTP!WinHttpSendRequest` at `0x180033182`
- `WINHTTP!WinHttpSendRequest` at `0x180033182`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Pal::NetworkRequestInternalWinHttp::sendRequestAsUser(DWORD_PTR dwContext, __int64 a2, __int64 **a3)
{
  __int64 v6; // rdx
  const WCHAR *v7; // rax
  HINTERNET v8; // rax
  const WCHAR *v9; // rax
  HINTERNET v10; // r10
  HINTERNET v11; // rax
  DWORD LastError; // ebx
  const WCHAR *v13; // rax
  DWORD v14; // r9d
  HINTERNET v15; // r10
  HINTERNET v16; // rbx
  char *v17; // rdi
  HINTERNET *v18; // rsi
  __int64 *v19; // rax
  __int64 v20; // rdx
  __int64 *v21; // r9
  __int64 v22; // r8
  __int64 v23; // rdx
  __int64 *v24; // rax
  __int64 v25; // r15
  __int64 i; // rbx
  __int64 v27; // rax
  const WCHAR *v28; // rax
  DWORD *j; // rbx
  __int64 v30; // rax
  __int64 v31; // rcx
  const WCHAR *v32; // rax
  DWORD v33; // r8d
  DWORD v34; // r9d
  LPVOID v35; // r10
  _WORD v37[2]; // [rsp+40h] [rbp-C0h] BYREF
  int Buffer; // [rsp+44h] [rbp-BCh] BYREF
  __int64 v39; // [rsp+48h] [rbp-B8h] BYREF
  std::_Ref_count_base *v40; // [rsp+50h] [rbp-B0h]
  _DWORD v41[3]; // [rsp+58h] [rbp-A8h] BYREF
  char v42; // [rsp+64h] [rbp-9Ch] BYREF
  _QWORD v43[2]; // [rsp+68h] [rbp-98h] BYREF
  __int64 v44; // [rsp+78h] [rbp-88h] BYREF
  std::_Ref_count_base *v45; // [rsp+80h] [rbp-80h]
  _BYTE v46[16]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v47[40]; // [rsp+A8h] [rbp-58h] BYREF
  int v48; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v49; // [rsp+D8h] [rbp-28h]
  _BYTE v50[544]; // [rsp+E0h] [rbp-20h] BYREF

  std::wstring::wstring((__int64)v47);
  std::wstring::assign(dwContext + 312, *(_QWORD *)(v6 + 24), *(unsigned int *)(v6 + 32));
  std::wstring::assign(v47, *(_QWORD *)(a2 + 72), *(unsigned int *)(a2 + 80));
  v7 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(dwContext + 256);
  v8 = WinHttpOpen(v7, 4u, 0, 0, 0x10000000u);
  *(_QWORD *)(dwContext + 152) = v8;
  if ( !v8
    || (v9 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(dwContext + 312),
        v11 = WinHttpConnect(v10, v9, *(_WORD *)(a2 + 36), 0),
        (*(_QWORD *)(dwContext + 160) = v11) == 0) )
  {
    LastError = GetLastError();
    goto LABEL_30;
  }
  v13 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v47);
  v16 = WinHttpOpenRequest(v15, off_180045450[*(int *)(dwContext + 288)], v13, 0, 0, 0, v14);
  v17 = (char *)operator new(0x18u);
  *(_OWORD *)v17 = 0;
  *((_DWORD *)v17 + 2) = 1;
  *((_DWORD *)v17 + 3) = 1;
  *(_QWORD *)v17 = &std::_Ref_count_obj2<Pal::WinHttpHandle>::`vftable';
  v18 = (HINTERNET *)(v17 + 16);
  *((_QWORD *)v17 + 2) = v16;
  v43[0] = v17 + 16;
  v43[1] = v17;
  EnterCriticalSection((LPCRITICAL_SECTION)(dwContext + 168));
  std::shared_ptr<Pal::Detail::WrlTimerWrapper>::shared_ptr<Pal::Detail::WrlTimerWrapper>(
    &v39,
    (_QWORD *)(dwContext + 208));
  v19 = std::shared_ptr<Pal::Detail::WrlTimerWrapper>::shared_ptr<Pal::Detail::WrlTimerWrapper>(&v44, v43);
  v20 = *v19;
  *v19 = *v21;
  *v21 = v20;
  v22 = v19[1];
  v19[1] = v21[1];
  v21[1] = v22;
  if ( v45 )
    std::_Ref_count_base::_Decref(v45);
  LeaveCriticalSection((LPCRITICAL_SECTION)(dwContext + 168));
  if ( !*v18 )
    goto LABEL_7;
  if ( *a3 )
  {
    Core::InlineVector<Pal::EventHandlerAndId<Core::EventHandler<>>,2>::InlineVector<Pal::EventHandlerAndId<Core::EventHandler<>>,2>(&v48);
    v37[0] = 0;
    Core::InlineVector<unsigned short,256>::ensureSpaceFor(&v48, v49 + 1);
    v23 = ++v49;
    if ( v48 )
      std::vector<unsigned short>::emplace_back<unsigned short>(v50, v37);
    else
      *(_WORD *)Core::InlineVector<unsigned short,32>::getAt(&v48, v23 - 1) = 0;
    v24 = *a3;
    v25 = (*a3)[1];
    for ( i = *v24; i != v25; i += 64 )
    {
      std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(i + 32);
      v27 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(i);
      Core::BasicInlineString<unsigned short,256>::formatInto(&v48, L"%ls: %ls", v27);
      v28 = (const WCHAR *)Core::InlineVector<unsigned short,51>::data(&v48);
      WinHttpAddRequestHeaders(*v18, v28, 0xFFFFFFFF, 0x20000000u);
    }
    Core::InlineVector<unsigned short,51>::~InlineVector<unsigned short,51>(&v48);
  }
  v41[0] = 3;
  v41[1] = 6;
  v41[2] = 5;
  for ( j = v41; j != (DWORD *)&v42; ++j )
  {
    if ( !WinHttpSetOption(*v18, *j, &c_networkTimeout, 4u) )
      goto LABEL_7;
  }
  Buffer = 1;
  if ( !WinHttpSetOption(*v18, 0x76u, &Buffer, 4u)
    || WinHttpSetStatusCallback(*v18, Pal::NetworkRequestInternalWinHttp::winHttpStatusCallback, 0x97E0C00u, 0) == (WINHTTP_STATUS_CALLBACK)-1LL )
  {
LABEL_7:
    LastError = GetLastError();
LABEL_8:
    if ( v40 )
      std::_Ref_count_base::_Decref(v40);
    std::_Ref_count_base::_Decref((std::_Ref_count_base *)v17);
    goto LABEL_30;
  }
  std::wstring::wstring((__int64)v46, (__int64)L"Host: ");
  std::wstring::append(v46, dwContext + 312);
  v30 = std::_WChar_traits<unsigned short>::length(L"\r\n");
  std::wstring::_Append<unsigned short>(v46, v31, v30);
  v32 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v46);
  if ( !WinHttpSendRequest(*v18, v32, v33, v35, v34, v34, dwContext) )
  {
    LastError = GetLastError();
    std::wstring::_Tidy_deallocate(v46);
    goto LABEL_8;
  }
  std::wstring::_Tidy_deallocate(v46);
  if ( v40 )
    std::_Ref_count_base::_Decref(v40);
  std::_Ref_count_base::_Decref((std::_Ref_count_base *)v17);
  LastError = 0;
LABEL_30:
  std::wstring::_Tidy_deallocate(v47);
  return LastError;
}

```

## disassembly

```asm
0x180032db0  push    rbp
0x180032db2  push    rbx
0x180032db3  push    rsi
0x180032db4  push    rdi
0x180032db5  push    r12
0x180032db7  push    r14
0x180032db9  push    r15
0x180032dbb  lea     rbp, [rsp-210h]
0x180032dc3  sub     rsp, 310h
0x180032dca  mov     rax, cs:__security_cookie
0x180032dd1  xor     rax, rsp
0x180032dd4  mov     [rbp+240h+var_40], rax
0x180032ddb  mov     r15, r8
0x180032dde  mov     rbx, rdx
0x180032de1  mov     r14, rcx
0x180032de4  lea     rcx, [rbp+240h+var_298]
0x180032de8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180032ded  nop
0x180032dee  lea     r12, [r14+138h]
0x180032df5  mov     r8d, [rdx+20h]
0x180032df9  mov     rdx, [rdx+18h]
0x180032dfd  mov     rcx, r12
0x180032e00  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG_K@Z; std::wstring::assign(ushort const * const,unsigned __int64)
0x180032e05  mov     r8d, [rbx+50h]
0x180032e09  mov     rdx, [rbx+48h]
0x180032e0d  lea     rcx, [rbp+240h+var_298]
0x180032e11  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG_K@Z; std::wstring::assign(ushort const * const,unsigned __int64)
0x180032e16  lea     rcx, [r14+100h]
0x180032e1d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180032e22  mov     [rsp+340h+dwFlags], 10000000h; dwFlags
0x180032e2a  xor     r9d, r9d; pszProxyBypassW
0x180032e2d  xor     r8d, r8d; pszProxyW
0x180032e30  lea     edx, [r9+4]; dwAccessType
0x180032e34  mov     rcx, rax; pszAgentW
0x180032e37  call    cs:__imp_WinHttpOpen
0x180032e3d  mov     r10, rax
0x180032e40  mov     [r14+98h], rax
0x180032e47  test    rax, rax
0x180032e4a  jz      short loc_180032E77
0x180032e4c  mov     rcx, r12
0x180032e4f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180032e54  xor     r9d, r9d; dwReserved
0x180032e57  movzx   r8d, word ptr [rbx+24h]; nServerPort
0x180032e5c  mov     rdx, rax; pswzServerName
0x180032e5f  mov     rcx, r10; hSession
0x180032e62  call    cs:__imp_WinHttpConnect
0x180032e68  mov     r10, rax
0x180032e6b  mov     [r14+0A0h], rax
0x180032e72  test    rax, rax
0x180032e75  jnz     short loc_180032E84
0x180032e77  call    cs:__imp_GetLastError
0x180032e7d  mov     ebx, eax
0x180032e7f  jmp     loc_1800331C6
0x180032e84  xor     eax, eax
0x180032e86  mov     r9d, 800000h
0x180032e8c  cmp     dword ptr [rbx+14h], 2
0x180032e90  cmovnz  r9d, eax
0x180032e94  lea     rcx, [rbp+240h+var_298]
0x180032e98  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180032e9d  mov     r8, rax; pwszObjectName
0x180032ea0  movsxd  rdx, dword ptr [r14+120h]
0x180032ea7  lea     rax, off_180045450; "GET"
0x180032eae  mov     [rsp+340h+var_310], r9d; dwFlags
0x180032eb3  mov     [rsp+340h+ppwszAcceptTypes], 0; ppwszAcceptTypes
0x180032ebc  mov     qword ptr [rsp+340h+dwFlags], 0; pwszReferrer
0x180032ec5  xor     r9d, r9d; pwszVersion
0x180032ec8  mov     rdx, [rax+rdx*8]; pwszVerb
0x180032ecc  mov     rcx, r10; hConnect
0x180032ecf  call    cs:__imp_WinHttpOpenRequest
0x180032ed5  mov     rbx, rax
0x180032ed8  mov     ecx, 18h; Size
0x180032edd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180032ee2  mov     rdi, rax
0x180032ee5  mov     [rsp+340h+var_2D8], rax
0x180032eea  xorps   xmm0, xmm0
0x180032eed  movups  xmmword ptr [rax], xmm0
0x180032ef0  mov     dword ptr [rax+8], 1
0x180032ef7  mov     dword ptr [rax+0Ch], 1
0x180032efe  lea     rax, ??_7?$_Ref_count_obj2@VWinHttpHandle@Pal@@@std@@6B@; const std::_Ref_count_obj2<Pal::WinHttpHandle>::`vftable'
0x180032f05  mov     [rdi], rax
0x180032f08  lea     rsi, [rdi+10h]
0x180032f0c  mov     [rsi], rbx
0x180032f0f  mov     [rsp+340h+var_2D8], rsi
0x180032f14  mov     [rsp+340h+var_2D0], rdi
0x180032f19  lea     rbx, [r14+0A8h]
0x180032f20  mov     rcx, rbx; lpCriticalSection
0x180032f23  call    cs:__imp_EnterCriticalSection
0x180032f29  lea     r9, [rbx+28h]
0x180032f2d  mov     rdx, r9
0x180032f30  lea     rcx, [rsp+340h+var_2F8]
0x180032f35  call    ??0?$shared_ptr@VWrlTimerWrapper@Detail@Pal@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Pal::Detail::WrlTimerWrapper>::shared_ptr<Pal::Detail::WrlTimerWrapper>(std::shared_ptr<Pal::Detail::WrlTimerWrapper> const &)
0x180032f3a  lea     rdx, [rsp+340h+var_2D8]
0x180032f3f  lea     rcx, [rsp+340h+var_2C8]
0x180032f44  call    ??0?$shared_ptr@VWrlTimerWrapper@Detail@Pal@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Pal::Detail::WrlTimerWrapper>::shared_ptr<Pal::Detail::WrlTimerWrapper>(std::shared_ptr<Pal::Detail::WrlTimerWrapper> const &)
0x180032f49  mov     rdx, [rax]
0x180032f4c  mov     rcx, [r9]
0x180032f4f  mov     [rax], rcx
0x180032f52  mov     [r9], rdx
0x180032f55  mov     r8, [rax+8]
0x180032f59  mov     rdx, [r9+8]
0x180032f5d  mov     [rax+8], rdx
0x180032f61  mov     [r9+8], r8
0x180032f65  mov     rcx, [rbp+240h+var_2C0]; this
0x180032f69  test    rcx, rcx
0x180032f6c  jz      short loc_180032F73
0x180032f6e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180032f73  mov     rcx, rbx; lpCriticalSection
0x180032f76  call    cs:__imp_LeaveCriticalSection
0x180032f7c  nop
0x180032f7d  cmp     qword ptr [rsi], 0
0x180032f81  jnz     short loc_180032FA8
0x180032f83  call    cs:__imp_GetLastError
0x180032f89  mov     ebx, eax
0x180032f8b  mov     rcx, [rsp+340h+var_2F0]; this
0x180032f90  test    rcx, rcx
0x180032f93  jz      short loc_180032F9B
0x180032f95  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180032f9a  nop
0x180032f9b  mov     rcx, rdi; this
0x180032f9e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180032fa3  jmp     loc_1800331C6
0x180032fa8  cmp     qword ptr [r15], 0
0x180032fac  jz      loc_18003306A
0x180032fb2  lea     rcx, [rbp+240h+var_270]
0x180032fb6  call    ??0?$InlineVector@V?$EventHandlerAndId@V?$EventHandler@$$V@Core@@@Pal@@$01@Core@@QEAA@XZ; Core::InlineVector<Pal::EventHandlerAndId<Core::EventHandler<>>,2>::InlineVector<Pal::EventHandlerAndId<Core::EventHandler<>>,2>(void)
0x180032fbb  nop
0x180032fbc  xor     eax, eax
0x180032fbe  mov     [rsp+340h+var_300], ax
0x180032fc3  mov     rdx, [rbp+240h+var_268]
0x180032fc7  inc     rdx
0x180032fca  lea     rcx, [rbp+240h+var_270]
0x180032fce  call    ?ensureSpaceFor@?$InlineVector@G$0BAA@@Core@@AEAAX_K@Z; Core::InlineVector<ushort,256>::ensureSpaceFor(unsigned __int64)
0x180032fd3  mov     rdx, [rbp+240h+var_268]
0x180032fd7  inc     rdx
0x180032fda  mov     [rbp+240h+var_268], rdx
0x180032fde  cmp     [rbp+240h+var_270], 0
0x180032fe2  jnz     short loc_180032FF7
0x180032fe4  dec     rdx
0x180032fe7  lea     rcx, [rbp+240h+var_270]
0x180032feb  call    ?getAt@?$InlineVector@G$0CA@@Core@@AEAAPEAG_K@Z; Core::InlineVector<ushort,32>::getAt(unsigned __int64)
0x180032ff0  xor     ecx, ecx
0x180032ff2  mov     [rax], cx
0x180032ff5  jmp     short loc_180033006
0x180032ff7  lea     rdx, [rsp+340h+var_300]
0x180032ffc  lea     rcx, [rbp+240h+var_260]
0x180033000  call    ??$emplace_back@G@?$vector@GV?$allocator@G@std@@@std@@QEAAAEAG$$QEAG@Z; std::vector<ushort>::emplace_back<ushort>(ushort &&)
0x180033005  nop
0x180033006  mov     rax, [r15]
0x180033009  mov     r15, [rax+8]
0x18003300d  mov     rbx, [rax]
0x180033010  jmp     short loc_18003305C
0x180033012  lea     rcx, [rbx+20h]
0x180033016  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003301b  mov     r9, rax
0x18003301e  mov     rcx, rbx
0x180033021  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180033026  mov     r8, rax
0x180033029  lea     rdx, aLsLs; "%ls: %ls"
0x180033030  lea     rcx, [rbp+240h+var_270]
0x180033034  call    ?formatInto@?$BasicInlineString@G$0BAA@@Core@@QEAAXPEBGZZ; Core::BasicInlineString<ushort,256>::formatInto(ushort const *,...)
0x180033039  lea     rcx, [rbp+240h+var_270]
0x18003303d  call    ?data@?$InlineVector@G$0DD@@Core@@QEAAPEAGXZ; Core::InlineVector<ushort,51>::data(void)
0x180033042  mov     rdx, rax; lpszHeaders
0x180033045  mov     r9d, 20000000h; dwModifiers
0x18003304b  or      r8d, 0FFFFFFFFh; dwHeadersLength
0x18003304f  mov     rcx, [rsi]; hRequest
0x180033052  call    cs:__imp_WinHttpAddRequestHeaders
0x180033058  add     rbx, 40h ; '@'
0x18003305c  cmp     rbx, r15
0x18003305f  jnz     short loc_180033012
0x180033061  lea     rcx, [rbp+240h+var_270]
0x180033065  call    ??1?$InlineVector@G$0DD@@Core@@QEAA@XZ; Core::InlineVector<ushort,51>::~InlineVector<ushort,51>(void)
0x18003306a  mov     [rsp+340h+var_2E8], 3
0x180033072  mov     [rsp+340h+var_2E4], 6
0x18003307a  mov     [rsp+340h+var_2E0], 5
0x180033082  lea     rbx, [rsp+340h+var_2E8]
0x180033087  lea     rax, [rsp+340h+var_2DC]
0x18003308c  mov     r9d, 4; dwBufferLength
0x180033092  cmp     rbx, rax
0x180033095  jz      short loc_1800330B7
0x180033097  lea     r8, ?c_networkTimeout@@3KA; lpBuffer
0x18003309e  mov     edx, [rbx]; dwOption
0x1800330a0  mov     rcx, [rsi]; hInternet
0x1800330a3  call    cs:__imp_WinHttpSetOption
0x1800330a9  test    eax, eax
0x1800330ab  jz      loc_180032F83
0x1800330b1  add     rbx, 4
0x1800330b5  jmp     short loc_180033087
0x1800330b7  mov     [rsp+340h+Buffer], 1
0x1800330bf  lea     r8, [rsp+340h+Buffer]; lpBuffer
0x1800330c4  mov     edx, 76h ; 'v'; dwOption
0x1800330c9  mov     rcx, [rsi]; hInternet
0x1800330cc  call    cs:__imp_WinHttpSetOption
0x1800330d2  test    eax, eax
0x1800330d4  jz      loc_180032F83
0x1800330da  xor     r9d, r9d; dwReserved
0x1800330dd  mov     r8d, 97E0C00h; dwNotificationFlags
0x1800330e3  lea     rdx, ?winHttpStatusCallback@NetworkRequestInternalWinHttp@Pal@@CAXPEAX_KK0K@Z; lpfnInternetCallback
0x1800330ea  mov     rcx, [rsi]; hInternet
0x1800330ed  call    cs:__imp_WinHttpSetStatusCallback
0x1800330f3  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800330f7  jz      loc_180032F83
0x1800330fd  lea     rdx, aHost; "Host: "
0x180033104  lea     rcx, [rbp+240h+var_2B8]
0x180033108  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003310d  nop
0x18003310e  mov     rdx, r12
0x180033111  lea     rcx, [rbp+240h+var_2B8]
0x180033115  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18003311a  lea     rcx, asc_180068D14; "\r\n"
0x180033121  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180033126  mov     r8, rax
0x180033129  mov     rdx, rcx
0x18003312c  lea     rcx, [rbp+240h+var_2B8]
0x180033130  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180033135  xor     r10d, r10d
0x180033138  xor     r9d, r9d
0x18003313b  mov     rdx, [r14+128h]
0x180033142  test    rdx, rdx
0x180033145  jz      short loc_180033159
0x180033147  mov     rax, [rdx+8]
0x18003314b  cmp     rax, [rdx]
0x18003314e  jz      short loc_180033159
0x180033150  mov     r10, [rdx]
0x180033153  mov     r9d, eax
0x180033156  sub     r9d, r10d
0x180033159  mov     r8d, [rbp+240h+var_2A8]
0x18003315d  add     r8d, 0FFFFFFFEh
0x180033161  lea     rcx, [rbp+240h+var_2B8]
0x180033165  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003316a  mov     rdx, rax; lpszHeaders
0x18003316d  mov     qword ptr [rsp+340h+var_310], r14; dwContext
0x180033172  mov     dword ptr [rsp+340h+ppwszAcceptTypes], r9d; dwTotalLength
0x180033177  mov     [rsp+340h+dwFlags], r9d; dwOptionalLength
0x18003317c  mov     r9, r10; lpOptional
0x18003317f  mov     rcx, [rsi]; hRequest
0x180033182  call    cs:__imp_WinHttpSendRequest
0x180033188  test    eax, eax
0x18003318a  jnz     short loc_1800331A2
0x18003318c  call    cs:__imp_GetLastError
0x180033192  mov     ebx, eax
0x180033194  lea     rcx, [rbp+240h+var_2B8]
0x180033198  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003319d  jmp     loc_180032F8B
0x1800331a2  lea     rcx, [rbp+240h+var_2B8]
0x1800331a6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800331ab  nop
0x1800331ac  mov     rcx, [rsp+340h+var_2F0]; this
0x1800331b1  test    rcx, rcx
0x1800331b4  jz      short loc_1800331BC
0x1800331b6  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800331bb  nop
0x1800331bc  mov     rcx, rdi; this
0x1800331bf  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800331c4  xor     ebx, ebx
0x1800331c6  lea     rcx, [rbp+240h+var_298]
0x1800331ca  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800331cf  mov     eax, ebx
0x1800331d1  mov     rcx, [rbp+240h+var_40]
0x1800331d8  xor     rcx, rsp; StackCookie
0x1800331db  call    __security_check_cookie
0x1800331e0  add     rsp, 310h
0x1800331e7  pop     r15
0x1800331e9  pop     r14
0x1800331eb  pop     r12
0x1800331ed  pop     rdi
0x1800331ee  pop     rsi
0x1800331ef  pop     rbx
0x1800331f0  pop     rbp
0x1800331f1  retn
```
