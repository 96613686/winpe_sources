# uus::DllForwarder::_Init(ushort const *,ushort const *)

- ea: `0x18000aa84`
- end: `0x18000ae4e`
- name: `?_Init@DllForwarder@uus@@AEAAXPEBG0@Z`
- size: `970`
- prototype: `void __fastcall(uus::DllForwarder *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180009f58`

## callees

- `0x180002200`
- `0x18000260c`
- `0x180006aec`
- `0x180006cfc`
- `0x180007940`
- `0x180007b54`
- `0x18000865c`
- `0x180008f20`
- `0x180009168`
- `0x180009208`
- `0x180009fc8`
- `0x18000a168`
- `0x18000aa84`
- `0x18000b210`
- `0x18000b258`
- `0x18000bda0`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000adc3`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000adc3`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000ade3`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000ade3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000adeb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000adeb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000add8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000add8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ad44`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ad44`

## string_xrefs

- `0x18000ae27`: `onecore\enduser\windowsupdate\undocked\stubdlls\UndockedDllForwarder.hpp`
- `0x18000ab72`: `WaasMedicSvcImpl.dll`
- `0x18000aca6`: `WaasMedicSvcImpl.dll`
- `0x18000ae3c`: `onecore\internal\sdk\inc\wil\opensource/wil/win32_helpers.h`

## pseudocode

```c
void __fastcall uus::DllForwarder::_Init(
        uus::DllForwarder *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  int v3; // ebx
  const unsigned __int16 *v4; // rdx
  __int64 v5; // rax
  void (__fastcall ***v6)(_QWORD, __int64); // rcx
  __int64 v7; // rcx
  const wchar_t *v8; // rax
  __int64 v9; // rdi
  __int64 v10; // r8
  __int64 v11; // r8
  void **v12; // r9
  void **v13; // rsi
  __int64 v14; // rbx
  __int64 v15; // rbx
  __int64 v16; // rcx
  __int64 v17; // rax
  const WCHAR *v18; // rbx
  HMODULE Library; // rdi
  const char *v20; // r9
  HMODULE v21; // rsi
  DWORD LastError; // ebx
  int v23[2]; // [rsp+20h] [rbp-E0h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v25; // [rsp+30h] [rbp-D0h] BYREF
  void *Src[2]; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v27; // [rsp+48h] [rbp-B8h]
  __int128 v28; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v29; // [rsp+68h] [rbp-98h]
  __int64 v30; // [rsp+70h] [rbp-90h]
  __int128 v31; // [rsp+78h] [rbp-88h] BYREF
  __int64 v32; // [rsp+88h] [rbp-78h]
  __int64 v33; // [rsp+90h] [rbp-70h]
  unsigned __int16 *v34[2]; // [rsp+98h] [rbp-68h] BYREF
  __int128 v35; // [rsp+A8h] [rbp-58h]
  _BYTE v36[32]; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v37[8]; // [rsp+D8h] [rbp-28h] BYREF
  _QWORD v38[13]; // [rsp+E0h] [rbp-20h] BYREF
  _QWORD *v39; // [rsp+148h] [rbp+48h]
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+88h]

  *(_OWORD *)Src = 0;
  *(_QWORD *)&v27 = 0;
  *((_QWORD *)&v27 + 1) = 7;
  LOWORD(Src[0]) = 0;
  LODWORD(pv) = 2;
  *(_QWORD *)v23 = 0;
  v25 = 0;
  v38[0] = &wistd::__function::__func<_lambda_843902387d8c5b5ae08b6cfe18992148_,long (unsigned short *,unsigned __int64,unsigned __int64 *)>::`vftable';
  v38[1] = &v25;
  v38[2] = v23;
  v39 = v38;
  v3 = wil::AdaptFixedSizeToAllocatedResult<std::wstring,128>(Src, v37, a3);
  if ( v39 )
    (*(void (__fastcall **)(_QWORD *))(*v39 + 24LL))(v39);
  if ( v3 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x276,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/win32_helpers.h",
      (const char *)(unsigned int)v3,
      v23[0]);
  *(_OWORD *)v34 = *(_OWORD *)Src;
  v35 = v27;
  *(_QWORD *)&v27 = 0;
  *((_QWORD *)&v27 + 1) = 7;
  LOWORD(Src[0]) = 0;
  std::wstring::~wstring(Src);
  v4 = (const unsigned __int16 *)v34;
  if ( *((_QWORD *)&v35 + 1) > 7u )
    v4 = v34[0];
  uus::UndockedStubDllTelemetry::InitForwardingDll(L"WaasMedic.Engine", v4, L"WaasMedicSvcImpl.dll");
  *(_QWORD *)v23 = operator new(0x10u);
  v5 = uus::Session::Session(*(uus::Session **)v23, L"WaasMedic.Engine");
  v6 = (void (__fastcall ***)(_QWORD, __int64))qword_180013098;
  qword_180013098 = v5;
  if ( v6 )
  {
    (**v6)(v6, 1);
    v5 = qword_180013098;
  }
  v7 = *(_QWORD *)(v5 + 8);
  if ( v7 )
    v8 = (const wchar_t *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v7 + 32LL))(v7);
  else
    v8 = L"0.0.0.0";
  *(_OWORD *)Src = 0;
  v27 = 0u;
  v9 = -1;
  v10 = -1;
  do
    ++v10;
  while ( v8[v10] );
  std::wstring::_Construct<1,unsigned short const *>(Src, v8);
  v12 = Src;
  if ( *((_QWORD *)&v27 + 1) > 7u )
    v12 = (void **)Src[0];
  if ( (unsigned __int64)v27 > qword_1800130E0 )
  {
    std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
      &qword_1800130C8,
      v27,
      v11,
      v12);
  }
  else
  {
    v13 = &qword_1800130C8;
    if ( (unsigned __int64)qword_1800130E0 > 7 )
      v13 = (void **)qword_1800130C8;
    qword_1800130D8 = v27;
    v14 = 2 * v27;
    memmove_0(v13, v12, 2 * v27);
    *(_WORD *)((char *)v13 + v14) = 0;
  }
  std::wstring::~wstring(Src);
  v15 = qword_180013098;
  v31 = 0;
  v32 = 0;
  v33 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v31, L"WaasMedicSvcImpl.dll");
  v16 = *(_QWORD *)(v15 + 8);
  if ( v16 )
  {
    v17 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v16 + 40LL))(v16, 1);
    do
      ++v9;
    while ( *(_WORD *)(v17 + 2 * v9) );
    *(_OWORD *)Src = 0;
    v27 = 0u;
    std::wstring::_Construct<1,unsigned short const *>(Src, v17);
  }
  else
  {
    wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(&pv);
    do
      ++v9;
    while ( *((_WORD *)pv + v9) );
    v28 = 0;
    v29 = 0;
    v30 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v28, pv);
    if ( pv )
      CoTaskMemFree(pv);
    uus::Utility::GetGuestOrNativeArchFolder(Src, &v28);
    std::wstring::~wstring(&v28);
  }
  std::filesystem::operator/(v36, (struct std::filesystem::path *)Src, (std::filesystem *)&v31);
  std::wstring::~wstring(Src);
  std::wstring::~wstring(&v31);
  v18 = (const WCHAR *)&lpLibFileName;
  std::wstring::operator=(&lpLibFileName, v36);
  std::wstring::~wstring(v36);
  if ( (unsigned __int64)qword_1800130C0 > 7 )
    v18 = lpLibFileName;
  Library = LoadLibraryExW(v18, 0, 0);
  v21 = hLibModule;
  if ( hLibModule )
  {
    LastError = GetLastError();
    FreeLibrary(v21);
    SetLastError(LastError);
  }
  hLibModule = Library;
  if ( !Library )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x37,
      (unsigned int)"onecore\\enduser\\windowsupdate\\undocked\\stubdlls\\UndockedDllForwarder.hpp",
      v20);
  std::wstring::~wstring(v34);
}

```

## disassembly

```asm
0x18000aa84  push    rbp
0x18000aa86  push    rbx
0x18000aa87  push    rsi
0x18000aa88  push    rdi
0x18000aa89  push    r14
0x18000aa8b  lea     rbp, [rsp-60h]
0x18000aa90  sub     rsp, 160h
0x18000aa97  mov     rax, cs:__security_cookie
0x18000aa9e  xor     rax, rsp
0x18000aaa1  mov     [rbp+80h+var_30], rax
0x18000aaa5  xor     r14d, r14d
0x18000aaa8  mov     dword ptr [rsp+180h+pv], r14d
0x18000aaad  xorps   xmm0, xmm0
0x18000aab0  movups  xmmword ptr [rsp+180h+Src], xmm0
0x18000aab5  mov     qword ptr [rsp+180h+var_138], r14
0x18000aaba  mov     qword ptr [rsp+180h+var_138+8], 7
0x18000aac3  mov     word ptr [rsp+180h+Src], r14w
0x18000aac9  mov     dword ptr [rsp+180h+pv], 2
0x18000aad1  mov     qword ptr [rsp+180h+var_160], r14; int
0x18000aad6  mov     [rsp+180h+var_150], r14
0x18000aadb  lea     rax, ??_7?$__func@V_lambda_843902387d8c5b5ae08b6cfe18992148_@@$$A6AJPEAG_KPEA_K@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_843902387d8c5b5ae08b6cfe18992148_,long (ushort *,unsigned __int64,unsigned __int64 *)>::`vftable'
0x18000aae2  mov     [rbp+80h+var_A0], rax
0x18000aae6  lea     rax, [rsp+180h+var_150]
0x18000aaeb  mov     [rbp+80h+var_98], rax
0x18000aaef  lea     rax, [rsp+180h+var_160]
0x18000aaf4  mov     [rbp+80h+var_90], rax
0x18000aaf8  lea     rax, [rbp+80h+var_A0]
0x18000aafc  mov     [rbp+80h+var_38], rax
0x18000ab00  lea     rdx, [rbp+80h+var_A8]
0x18000ab04  lea     rcx, [rsp+180h+Src]
0x18000ab09  call    ??$AdaptFixedSizeToAllocatedResult@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$0IA@@wil@@YAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@@Z; wil::AdaptFixedSizeToAllocatedResult<std::wstring,128>(std::wstring &,wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)> const &)
0x18000ab0e  mov     ebx, eax
0x18000ab10  mov     rcx, [rbp+80h+var_38]
0x18000ab14  test    rcx, rcx
0x18000ab17  jz      short loc_18000AB25
0x18000ab19  mov     rdx, [rcx]
0x18000ab1c  mov     rax, [rdx+18h]
0x18000ab20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ab25  mov     rcx, [rbp+88h]; this
0x18000ab2c  test    ebx, ebx
0x18000ab2e  js      loc_18000AE39
0x18000ab34  movups  xmm0, xmmword ptr [rsp+180h+Src]
0x18000ab39  movups  xmmword ptr [rbp+80h+var_E8], xmm0
0x18000ab3d  movups  xmm1, [rsp+180h+var_138]
0x18000ab42  movups  [rbp+80h+var_D8], xmm1
0x18000ab46  mov     qword ptr [rsp+180h+var_138], r14
0x18000ab4b  mov     qword ptr [rsp+180h+var_138+8], 7
0x18000ab54  mov     word ptr [rsp+180h+Src], r14w
0x18000ab5a  lea     rcx, [rsp+180h+Src]
0x18000ab5f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000ab64  lea     rdx, [rbp+80h+var_E8]
0x18000ab68  cmp     qword ptr [rbp+80h+var_D8+8], 7
0x18000ab6d  cmova   rdx, [rbp+80h+var_E8]; unsigned __int16 *
0x18000ab72  lea     r8, aWaasmedicsvcim; "WaasMedicSvcImpl.dll"
0x18000ab79  lea     rcx, aWaasmedicEngin; "WaasMedic.Engine"
0x18000ab80  call    ?InitForwardingDll@UndockedStubDllTelemetry@uus@@SAXPEBG00@Z; uus::UndockedStubDllTelemetry::InitForwardingDll(ushort const *,ushort const *,ushort const *)
0x18000ab85  mov     ecx, 10h; Size
0x18000ab8a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000ab8f  mov     qword ptr [rsp+180h+var_160], rax
0x18000ab94  lea     rdx, aWaasmedicEngin; "WaasMedic.Engine"
0x18000ab9b  mov     rcx, rax; this
0x18000ab9e  call    ??0Session@uus@@QEAA@PEBG@Z; uus::Session::Session(ushort const *)
0x18000aba3  nop
0x18000aba4  mov     rcx, cs:qword_180013098
0x18000abab  mov     cs:qword_180013098, rax
0x18000abb2  test    rcx, rcx
0x18000abb5  jz      short loc_18000ABCE
0x18000abb7  mov     rax, [rcx]
0x18000abba  mov     edx, 1
0x18000abbf  mov     rax, [rax]
0x18000abc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000abc7  mov     rax, cs:qword_180013098
0x18000abce  mov     rcx, [rax+8]
0x18000abd2  test    rcx, rcx
0x18000abd5  jz      short loc_18000ABE5
0x18000abd7  mov     rax, [rcx]
0x18000abda  mov     rax, [rax+20h]
0x18000abde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000abe3  jmp     short loc_18000ABEC
0x18000abe5  lea     rax, a0000; "0.0.0.0"
0x18000abec  xorps   xmm0, xmm0
0x18000abef  movups  xmmword ptr [rsp+180h+Src], xmm0
0x18000abf4  mov     qword ptr [rsp+180h+var_138], r14
0x18000abf9  mov     qword ptr [rsp+180h+var_138+8], r14
0x18000abfe  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000ac02  mov     r8, rdi
0x18000ac05  inc     r8
0x18000ac08  cmp     [rax+r8*2], r14w
0x18000ac0d  jnz     short loc_18000AC05
0x18000ac0f  mov     rdx, rax
0x18000ac12  lea     rcx, [rsp+180h+Src]
0x18000ac17  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000ac1c  nop
0x18000ac1d  mov     rdx, qword ptr [rsp+180h+var_138]
0x18000ac22  lea     r9, [rsp+180h+Src]
0x18000ac27  cmp     qword ptr [rsp+180h+var_138+8], 7
0x18000ac2d  cmova   r9, [rsp+180h+Src]
0x18000ac33  mov     rax, cs:qword_1800130E0
0x18000ac3a  cmp     rdx, rax
0x18000ac3d  ja      short loc_18000AC72
0x18000ac3f  lea     rsi, qword_1800130C8
0x18000ac46  cmp     rax, 7
0x18000ac4a  cmova   rsi, cs:qword_1800130C8
0x18000ac52  mov     cs:qword_1800130D8, rdx
0x18000ac59  lea     rbx, [rdx+rdx]
0x18000ac5d  mov     r8, rbx; Size
0x18000ac60  mov     rdx, r9; Src
0x18000ac63  mov     rcx, rsi; void *
0x18000ac66  call    memmove_0
0x18000ac6b  mov     [rbx+rsi], r14w
0x18000ac70  jmp     short loc_18000AC7F
0x18000ac72  lea     rcx, qword_1800130C8
0x18000ac79  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18000ac7e  nop
0x18000ac7f  lea     rcx, [rsp+180h+Src]
0x18000ac84  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000ac89  mov     rbx, cs:qword_180013098
0x18000ac90  xorps   xmm0, xmm0
0x18000ac93  movups  [rsp+180h+var_108], xmm0
0x18000ac98  mov     [rbp+80h+var_F8], r14
0x18000ac9c  mov     [rbp+80h+var_F0], r14
0x18000aca0  mov     r8d, 14h
0x18000aca6  lea     rdx, aWaasmedicsvcim; "WaasMedicSvcImpl.dll"
0x18000acad  lea     rcx, [rsp+180h+var_108]
0x18000acb2  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000acb7  nop
0x18000acb8  mov     rcx, [rbx+8]
0x18000acbc  test    rcx, rcx
0x18000acbf  jz      short loc_18000AD00
0x18000acc1  mov     rax, [rcx]
0x18000acc4  mov     edx, 1
0x18000acc9  mov     rax, [rax+28h]
0x18000accd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000acd2  inc     rdi
0x18000acd5  cmp     [rax+rdi*2], r14w
0x18000acda  jnz     short loc_18000ACD2
0x18000acdc  xorps   xmm0, xmm0
0x18000acdf  movups  xmmword ptr [rsp+180h+Src], xmm0
0x18000ace4  mov     qword ptr [rsp+180h+var_138], r14
0x18000ace9  mov     qword ptr [rsp+180h+var_138+8], r14
0x18000acee  mov     r8, rdi
0x18000acf1  mov     rdx, rax
0x18000acf4  lea     rcx, [rsp+180h+Src]
0x18000acf9  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000acfe  jmp     short loc_18000AD66
0x18000ad00  lea     rcx, [rsp+180h+pv]
0x18000ad05  call    ??$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG@Z; wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(ushort const *)
0x18000ad0a  nop
0x18000ad0b  mov     rdx, [rsp+180h+pv]
0x18000ad10  inc     rdi
0x18000ad13  cmp     [rdx+rdi*2], r14w
0x18000ad18  jnz     short loc_18000AD10
0x18000ad1a  xorps   xmm0, xmm0
0x18000ad1d  movups  [rsp+180h+var_128], xmm0
0x18000ad22  mov     [rsp+180h+var_118], r14
0x18000ad27  mov     [rsp+180h+var_110], r14
0x18000ad2c  mov     r8, rdi
0x18000ad2f  lea     rcx, [rsp+180h+var_128]
0x18000ad34  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000ad39  nop
0x18000ad3a  mov     rcx, [rsp+180h+pv]; pv
0x18000ad3f  test    rcx, rcx
0x18000ad42  jz      short loc_18000AD4B
0x18000ad44  call    cs:__imp_CoTaskMemFree
0x18000ad4a  nop
0x18000ad4b  lea     rdx, [rsp+180h+var_128]
0x18000ad50  lea     rcx, [rsp+180h+Src]
0x18000ad55  call    ?GetGuestOrNativeArchFolder@Utility@uus@@SA?AVpath@filesystem@std@@AEBV345@@Z; uus::Utility::GetGuestOrNativeArchFolder(std::filesystem::path const &)
0x18000ad5a  nop
0x18000ad5b  lea     rcx, [rsp+180h+var_128]
0x18000ad60  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000ad65  nop
0x18000ad66  lea     r8, [rsp+180h+var_108]; this
0x18000ad6b  lea     rdx, [rsp+180h+Src]; struct std::filesystem::path *
0x18000ad70  lea     rcx, [rbp+80h+var_C8]; Src
0x18000ad74  call    ??Kfilesystem@std@@YA?AVpath@01@AEBV201@0@Z; std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)
0x18000ad79  nop
0x18000ad7a  lea     rcx, [rsp+180h+Src]
0x18000ad7f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000ad84  nop
0x18000ad85  lea     rcx, [rsp+180h+var_108]
0x18000ad8a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000ad8f  lea     rdx, [rbp+80h+var_C8]
0x18000ad93  lea     rbx, lpLibFileName
0x18000ad9a  mov     rcx, rbx
0x18000ad9d  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18000ada2  lea     rcx, [rbp+80h+var_C8]
0x18000ada6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000adab  cmp     cs:qword_1800130C0, 7
0x18000adb3  cmova   rbx, cs:lpLibFileName
0x18000adbb  xor     r8d, r8d; dwFlags
0x18000adbe  xor     edx, edx; hFile
0x18000adc0  mov     rcx, rbx; lpLibFileName
0x18000adc3  call    cs:__imp_LoadLibraryExW
0x18000adc9  mov     rdi, rax
0x18000adcc  mov     rsi, cs:hLibModule
0x18000add3  test    rsi, rsi
0x18000add6  jz      short loc_18000ADF1
0x18000add8  call    cs:__imp_GetLastError
0x18000adde  mov     ebx, eax
0x18000ade0  mov     rcx, rsi; hLibModule
0x18000ade3  call    cs:__imp_FreeLibrary
0x18000ade9  mov     ecx, ebx; dwErrCode
0x18000adeb  call    cs:__imp_SetLastError
0x18000adf1  mov     cs:hLibModule, rdi
0x18000adf8  mov     rcx, [rbp+88h]; this
0x18000adff  test    rdi, rdi
0x18000ae02  jz      short loc_18000AE27
0x18000ae04  lea     rcx, [rbp+80h+var_E8]
0x18000ae08  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000ae0d  mov     rcx, [rbp+80h+var_30]
0x18000ae11  xor     rcx, rsp; StackCookie
0x18000ae14  call    __security_check_cookie
0x18000ae19  add     rsp, 160h
0x18000ae20  pop     r14
0x18000ae22  pop     rdi
0x18000ae23  pop     rsi
0x18000ae24  pop     rbx
0x18000ae25  pop     rbp
0x18000ae26  retn
0x18000ae27  lea     r8, aOnecoreEnduser_0; "onecore\\enduser\\windowsupdate\\undock"...
0x18000ae2e  mov     edx, 37h ; '7'; void *
0x18000ae33  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18000ae39  mov     r9d, ebx; char *
0x18000ae3c  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000ae43  mov     edx, 276h; void *
0x18000ae48  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
