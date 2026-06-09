# LoadSSUFn(wchar_t const *,wchar_t const *,char *,Windows::AutoGenericHandle<HINSTANCE__ *,0,&Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)> *,__int64 (**)(void),IServicingLoader * *)

- ea: `0x1800451d0`
- end: `0x180045517`
- name: `?LoadSSUFn@@YAJPEB_W0PEADPEAV?$AutoGenericHandle@PEAUHINSTANCE__@@$0A@$1?CloseWithFreeLibrary@Detail@Windows@@YAXPEAU1@@Z@Windows@@PEAP6A_JXZPEAPEAVIServicingLoader@@@Z`
- size: `839`
- prototype: ``
- caller_count: `2`
- callee_count: `16`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180046040`
- `0x180046460`

## callees

- `0x180004a8c`
- `0x18001d694`
- `0x180020440`
- `0x180020dc0`
- `0x180023664`
- `0x18002d2b0`
- `0x18004194c`
- `0x180041998`
- `0x180041a68`
- `0x180042fec`
- `0x180043680`
- `0x180043db8`
- `0x180044d88`
- `0x1800451d0`
- `0x180045914`
- `0x18009e020`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x1800453bd`
- `KERNEL32!LoadLibraryExW` at `0x1800453bd`
- `KERNEL32!GetProcAddress` at `0x180045416`
- `KERNEL32!GetProcAddress` at `0x180045442`
- `KERNEL32!GetProcAddress` at `0x1800454af`
- `KERNEL32!GetProcAddress` at `0x180045416`
- `KERNEL32!GetProcAddress` at `0x180045442`
- `KERNEL32!GetProcAddress` at `0x1800454af`

## string_xrefs

- `0x180045244`: `TurboStack.dll`
- `0x18004537b`: `TurboStack.dll`

## pseudocode

```c
__int64 __fastcall LoadSSUFn(__int64 a1, HMODULE a2, const CHAR *a3, HMODULE *a4, FARPROC *a5, _QWORD *a6)
{
  int v8; // eax
  unsigned int LastError; // ebx
  int v10; // eax
  const wchar_t *v11; // rax
  int FilePath; // eax
  __int64 v13; // rdx
  const wchar_t *v14; // rax
  bool v15; // dl
  const WCHAR *v16; // rax
  HMODULE Library; // rax
  const char *v18; // r9
  HMODULE v19; // rbx
  __int64 v20; // rdx
  FARPROC ProcAddress; // rax
  FARPROC v22; // rax
  int v23; // edi
  __int64 v24; // rdx
  FARPROC v25; // rax
  int v27; // [rsp+20h] [rbp-B9h]
  __int128 v28; // [rsp+30h] [rbp-A9h] BYREF
  const wchar_t *v29; // [rsp+40h] [rbp-99h]
  __int128 v30; // [rsp+48h] [rbp-91h] BYREF
  __int64 v31; // [rsp+58h] [rbp-81h]
  _QWORD v32[3]; // [rsp+60h] [rbp-79h] BYREF
  HMODULE hModule; // [rsp+78h] [rbp-61h] BYREF
  __int64 v34; // [rsp+80h] [rbp-59h] BYREF
  __int128 v35; // [rsp+90h] [rbp-49h] BYREF
  __int64 v36; // [rsp+A0h] [rbp-39h]
  __int64 v37; // [rsp+A8h] [rbp-31h]
  __int64 v38; // [rsp+B0h] [rbp-29h]
  __int64 v39; // [rsp+B8h] [rbp-21h]
  __int64 v40; // [rsp+C0h] [rbp-19h]
  __int64 v41; // [rsp+C8h] [rbp-11h]
  char v42; // [rsp+D0h] [rbp-9h]
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+4Fh]

  v34 = a1;
  hModule = a2;
  v31 = 0;
  v35 = 0;
  v36 = 0;
  v37 = 0;
  v38 = 0;
  v39 = 0;
  v40 = 0;
  v41 = 0;
  v42 = 0;
  v30 = 0;
  if ( !a2 )
  {
    v29 = 0;
    v32[0] = 14;
    v32[1] = 14;
    v32[2] = L"Windows";
    v28 = 0;
    v10 = Windows::StringUtil::Rtl::CombineAndNullTerminateWin32Paths<wchar_t const *,_LUNICODE_STRING>(&v34, v32, &v28);
    if ( v10 >= 0 )
    {
      v11 = (const wchar_t *)Windows::StringUtil::c_str<Windows::Auto<_LUNICODE_STRING>>(&v28);
      FilePath = Windows::AutoSsShim::TryLoadFromWindowsPath((Windows::AutoSsShim *)&v35, v11, 0);
      LastError = FilePath;
      if ( FilePath >= 0 )
      {
        v14 = (const wchar_t *)Windows::StringUtil::c_str<Windows::Auto<_LUNICODE_STRING>>(&v28);
        FilePath = Windows::AutoSsShim::Bind((Windows::AutoSsShim *)&v35, v14, 0, 0, 0);
        LastError = FilePath;
        if ( FilePath >= 0 )
        {
          FilePath = Windows::AutoSsShim::Preload((Windows::AutoSsShim *)&v35, v15);
          LastError = FilePath;
          if ( FilePath >= 0 )
          {
            FilePath = Windows::AutoSsShim::GetFilePath(
                         (Windows::AutoSsShim *)&v35,
                         (wchar_t *)L"TurboStack.dll",
                         (struct _LUNICODE_STRING *)&v30);
            LastError = FilePath;
            if ( FilePath >= 0 )
            {
              Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v28);
LABEL_17:
              hModule = 0;
              v16 = (const WCHAR *)Windows::StringUtil::c_str<Windows::Auto<_LUNICODE_STRING>>(&v30);
              Library = LoadLibraryExW(v16, 0, 8u);
              Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::TakeOwnership(
                &hModule,
                Library);
              v19 = hModule;
              if ( hModule )
              {
                if ( g_TestMode )
                {
                  ProcAddress = GetProcAddress(hModule, "SetTestMode");
                  if ( !ProcAddress )
                  {
                    v20 = 143;
                    goto LABEL_19;
                  }
                  ((void (__fastcall *)(__int64))ProcAddress)(1);
                }
                v22 = GetProcAddress(v19, "GetIServicingLoader");
                if ( v22 )
                {
                  v23 = ((__int64 (__fastcall *)(_QWORD *))v22)(a6);
                  if ( v23 >= 0 )
                  {
                    v23 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a6 + 24LL))(*a6);
                    if ( v23 >= 0 )
                    {
                      v25 = GetProcAddress(v19, a3);
                      *a5 = v25;
                      if ( v25 )
                      {
                        hModule = *a4;
                        *a4 = v19;
                        Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&void Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(&hModule);
                        LastError = 0;
                        goto LABEL_34;
                      }
                      v20 = 156;
                      goto LABEL_19;
                    }
                    v24 = 153;
                  }
                  else
                  {
                    v24 = 151;
                  }
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)v24,
                    (unsigned int)"onecore\\base\\cbs\\pbr\\loader\\pbr_loader.cpp",
                    (const char *)(unsigned int)v23,
                    v27);
                  Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&void Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(&hModule);
                  LastError = v23;
                  goto LABEL_34;
                }
                v20 = 149;
              }
              else
              {
                v20 = 138;
              }
LABEL_19:
              LastError = wil::details::in1diag3::Return_GetLastError(
                            retaddr,
                            (void *)v20,
                            (unsigned int)"onecore\\base\\cbs\\pbr\\loader\\pbr_loader.cpp",
                            v18);
              Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&void Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(&hModule);
              goto LABEL_34;
            }
            v13 = 129;
          }
          else
          {
            v13 = 128;
          }
        }
        else
        {
          v13 = 127;
        }
      }
      else
      {
        v13 = 126;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v13,
        (unsigned int)"onecore\\base\\cbs\\pbr\\loader\\pbr_loader.cpp",
        (const char *)(unsigned int)FilePath,
        v27);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_NtStatus(
                    retaddr,
                    (void *)0x7C,
                    (unsigned int)"onecore\\base\\cbs\\pbr\\loader\\pbr_loader.cpp",
                    (const char *)(unsigned int)v10,
                    v27);
    }
    Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v28);
    goto LABEL_34;
  }
  v29 = L"TurboStack.dll";
  *(_QWORD *)&v28 = 28;
  *((_QWORD *)&v28 + 1) = 28;
  v8 = Windows::StringUtil::Rtl::CombineAndNullTerminateWin32Paths<wchar_t const *,_LUNICODE_STRING>(
         &hModule,
         &v28,
         &v30);
  if ( v8 >= 0 )
    goto LABEL_17;
  LastError = wil::details::in1diag3::Return_NtStatus(
                retaddr,
                (void *)0x73,
                (unsigned int)"onecore\\base\\cbs\\pbr\\loader\\pbr_loader.cpp",
                (const char *)(unsigned int)v8,
                v27);
LABEL_34:
  Windows::AutoSsShim::~AutoSsShim((Windows::AutoSsShim *)&v35);
  Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v30);
  return LastError;
}

```

## disassembly

```asm
0x1800451d0  push    rbp
0x1800451d2  push    rbx
0x1800451d3  push    rsi
0x1800451d4  push    rdi
0x1800451d5  push    r12
0x1800451d7  push    r14
0x1800451d9  push    r15
0x1800451db  lea     rbp, [rsp-17h]
0x1800451e0  sub     rsp, 0F0h
0x1800451e7  mov     rax, cs:__security_cookie
0x1800451ee  xor     rax, rsp
0x1800451f1  mov     [rbp+47h+var_40], rax
0x1800451f5  mov     r12, [rbp+47h+arg_20]
0x1800451f9  xor     eax, eax
0x1800451fb  mov     r14, [rbp+47h+arg_28]
0x1800451ff  xorps   xmm0, xmm0
0x180045202  mov     [rbp+47h+var_A0], rcx
0x180045206  mov     rsi, r9
0x180045209  mov     [rbp+47h+hModule], rdx
0x18004520d  mov     r15, r8
0x180045210  mov     [rsp+120h+var_C8], rax
0x180045215  movdqa  [rbp+47h+var_90], xmm0
0x18004521a  mov     [rbp+47h+var_80], rax
0x18004521e  mov     [rbp+47h+var_78], rax
0x180045222  mov     [rbp+47h+var_70], rax
0x180045226  mov     [rbp+47h+var_68], rax
0x18004522a  mov     [rbp+47h+var_60], rax
0x18004522e  mov     [rbp+47h+var_58], rax
0x180045232  mov     [rbp+47h+var_50], al
0x180045235  movups  [rsp+120h+var_D8], xmm0
0x18004523a  test    rdx, rdx
0x18004523d  jz      short loc_180045294
0x18004523f  mov     eax, 1Ch
0x180045244  lea     rdx, aTurbostackDll; "TurboStack.dll"
0x18004524b  mov     [rsp+120h+var_E0], rdx
0x180045250  lea     r8, [rsp+120h+var_D8]
0x180045255  lea     rdx, [rsp+120h+var_F0]
0x18004525a  mov     qword ptr [rsp+120h+var_F0], rax
0x18004525f  lea     rcx, [rbp+47h+hModule]
0x180045263  mov     qword ptr [rsp+120h+var_F0+8], rax
0x180045268  call    ??$CombineAndNullTerminateWin32Paths@PEB_WU_LUNICODE_STRING@@@Rtl@StringUtil@Windows@@YAJAEBQEB_WAEBU_LUNICODE_STRING@@PEAV?$Auto@U_LUNICODE_STRING@@@2@@Z; Windows::StringUtil::Rtl::CombineAndNullTerminateWin32Paths<wchar_t const *,_LUNICODE_STRING>(wchar_t const * const &,_LUNICODE_STRING const &,Windows::Auto<_LUNICODE_STRING> *)
0x18004526d  test    eax, eax
0x18004526f  jns     loc_1800453A2
0x180045275  mov     rcx, [rbp+4Fh]; this
0x180045279  lea     r8, aOnecoreBaseCbs_7; "onecore\\base\\cbs\\pbr\\loader\\pbr_lo"...
0x180045280  mov     r9d, eax; char *
0x180045283  mov     edx, 73h ; 's'; void *
0x180045288  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18004528d  mov     ebx, eax
0x18004528f  jmp     loc_1800454E3
0x180045294  mov     [rsp+120h+var_E0], rax
0x180045299  lea     r8, [rsp+120h+var_F0]
0x18004529e  mov     eax, 0Eh
0x1800452a3  lea     rdx, [rbp+47h+var_C0]
0x1800452a7  mov     [rbp+47h+var_C0], rax
0x1800452ab  lea     rcx, [rbp+47h+var_A0]
0x1800452af  mov     [rbp+47h+var_B8], rax
0x1800452b3  lea     rax, aWindows; "Windows"
0x1800452ba  mov     [rbp+47h+var_B0], rax
0x1800452be  movups  [rsp+120h+var_F0], xmm0
0x1800452c3  call    ??$CombineAndNullTerminateWin32Paths@PEB_WU_LUNICODE_STRING@@@Rtl@StringUtil@Windows@@YAJAEBQEB_WAEBU_LUNICODE_STRING@@PEAV?$Auto@U_LUNICODE_STRING@@@2@@Z; Windows::StringUtil::Rtl::CombineAndNullTerminateWin32Paths<wchar_t const *,_LUNICODE_STRING>(wchar_t const * const &,_LUNICODE_STRING const &,Windows::Auto<_LUNICODE_STRING> *)
0x1800452c8  test    eax, eax
0x1800452ca  jns     short loc_1800452F5
0x1800452cc  mov     rcx, [rbp+4Fh]; this
0x1800452d0  lea     r8, aOnecoreBaseCbs_7; "onecore\\base\\cbs\\pbr\\loader\\pbr_lo"...
0x1800452d7  mov     r9d, eax; char *
0x1800452da  mov     edx, 7Ch ; '|'; void *
0x1800452df  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800452e4  mov     ebx, eax
0x1800452e6  lea     rcx, [rsp+120h+var_F0]
0x1800452eb  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x1800452f0  jmp     loc_1800454E3
0x1800452f5  lea     rcx, [rsp+120h+var_F0]
0x1800452fa  call    ??$c_str@V?$Auto@U_LUNICODE_STRING@@@Windows@@@StringUtil@Windows@@YA?A_PAEBV?$Auto@U_LUNICODE_STRING@@@1@@Z
0x1800452ff  mov     rdx, rax; wchar_t *
0x180045302  lea     rcx, [rbp+47h+var_90]; this
0x180045306  xor     r8d, r8d; wchar_t *
0x180045309  call    ?TryLoadFromWindowsPath@AutoSsShim@Windows@@QEAAJQEB_W0@Z; Windows::AutoSsShim::TryLoadFromWindowsPath(wchar_t const * const,wchar_t const * const)
0x18004530e  mov     ebx, eax
0x180045310  test    eax, eax
0x180045312  jns     short loc_18004532E
0x180045314  mov     edx, 7Eh ; '~'; void *
0x180045319  mov     rcx, [rbp+4Fh]; this
0x18004531d  lea     r8, aOnecoreBaseCbs_7; "onecore\\base\\cbs\\pbr\\loader\\pbr_lo"...
0x180045324  mov     r9d, eax; char *
0x180045327  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004532c  jmp     short loc_1800452E6
0x18004532e  lea     rcx, [rsp+120h+var_F0]
0x180045333  call    ??$c_str@V?$Auto@U_LUNICODE_STRING@@@Windows@@@StringUtil@Windows@@YA?A_PAEBV?$Auto@U_LUNICODE_STRING@@@1@@Z
0x180045338  mov     rdx, rax; wchar_t *
0x18004533b  mov     qword ptr [rsp+120h+var_100], 0; int
0x180045344  xor     r9d, r9d; wchar_t *
0x180045347  lea     rcx, [rbp+47h+var_90]; this
0x18004534b  xor     r8d, r8d; bool
0x18004534e  call    ?Bind@AutoSsShim@Windows@@QEAAJQEB_W_N0PEB_K@Z; Windows::AutoSsShim::Bind(wchar_t const * const,bool,wchar_t const * const,unsigned __int64 const *)
0x180045353  mov     ebx, eax
0x180045355  test    eax, eax
0x180045357  jns     short loc_180045360
0x180045359  mov     edx, 7Fh
0x18004535e  jmp     short loc_180045319
0x180045360  lea     rcx, [rbp+47h+var_90]; this
0x180045364  call    ?Preload@AutoSsShim@Windows@@QEAAJ_N@Z; Windows::AutoSsShim::Preload(bool)
0x180045369  mov     ebx, eax
0x18004536b  test    eax, eax
0x18004536d  jns     short loc_180045376
0x18004536f  mov     edx, 80h
0x180045374  jmp     short loc_180045319
0x180045376  lea     r8, [rsp+120h+var_D8]; struct _LUNICODE_STRING *
0x18004537b  lea     rdx, aTurbostackDll; "TurboStack.dll"
0x180045382  lea     rcx, [rbp+47h+var_90]; this
0x180045386  call    ?GetFilePath@AutoSsShim@Windows@@QEAAJQEB_WPEAV?$Auto@U_LUNICODE_STRING@@@2@@Z; Windows::AutoSsShim::GetFilePath(wchar_t const * const,Windows::Auto<_LUNICODE_STRING> *)
0x18004538b  mov     ebx, eax
0x18004538d  test    eax, eax
0x18004538f  jns     short loc_180045398
0x180045391  mov     edx, 81h
0x180045396  jmp     short loc_180045319
0x180045398  lea     rcx, [rsp+120h+var_F0]
0x18004539d  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x1800453a2  lea     rcx, [rsp+120h+var_D8]
0x1800453a7  mov     [rbp+47h+hModule], 0
0x1800453af  call    ??$c_str@V?$Auto@U_LUNICODE_STRING@@@Windows@@@StringUtil@Windows@@YA?A_PAEBV?$Auto@U_LUNICODE_STRING@@@1@@Z
0x1800453b4  xor     edx, edx; hFile
0x1800453b6  mov     rcx, rax; lpLibFileName
0x1800453b9  lea     r8d, [rdx+8]; dwFlags
0x1800453bd  call    cs:__imp_LoadLibraryExW
0x1800453c4  nop     dword ptr [rax+rax+00h]
0x1800453c9  mov     rdx, rax
0x1800453cc  lea     rcx, [rbp+47h+hModule]
0x1800453d0  call    ?TakeOwnership@?$AutoGenericHandleBase@PEA_W$0A@V?$AutoNewArrayPtr@_W@Windows@@@Windows@@QEAAXPEA_W@Z; Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::TakeOwnership(wchar_t *)
0x1800453d5  mov     rbx, [rbp+47h+hModule]
0x1800453d9  test    rbx, rbx
0x1800453dc  jnz     short loc_180045403
0x1800453de  mov     edx, 8Ah; void *
0x1800453e3  mov     rcx, [rbp+4Fh]; this
0x1800453e7  lea     r8, aOnecoreBaseCbs_7; "onecore\\base\\cbs\\pbr\\loader\\pbr_lo"...
0x1800453ee  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800453f3  lea     rcx, [rbp+47h+hModule]
0x1800453f7  mov     ebx, eax
0x1800453f9  call    ?Close@?$AutoGenericHandleBase@PEAUHINSTANCE__@@$0A@V?$AutoGenericHandle@PEAUHINSTANCE__@@$0A@$1?CloseWithFreeLibrary@Detail@Windows@@YAXPEAU1@@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(void)
0x1800453fe  jmp     loc_1800454E3
0x180045403  cmp     cs:?g_TestMode@@3_NA, 0; bool g_TestMode
0x18004540a  jz      short loc_180045438
0x18004540c  lea     rdx, aSettestmode; "SetTestMode"
0x180045413  mov     rcx, rbx; hModule
0x180045416  call    cs:__imp_GetProcAddress
0x18004541d  nop     dword ptr [rax+rax+00h]
0x180045422  test    rax, rax
0x180045425  jnz     short loc_18004542E
0x180045427  mov     edx, 8Fh
0x18004542c  jmp     short loc_1800453E3
0x18004542e  mov     ecx, 1
0x180045433  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045438  lea     rdx, aGetiservicingl; "GetIServicingLoader"
0x18004543f  mov     rcx, rbx; hModule
0x180045442  call    cs:__imp_GetProcAddress
0x180045449  nop     dword ptr [rax+rax+00h]
0x18004544e  test    rax, rax
0x180045451  jnz     short loc_18004545A
0x180045453  mov     edx, 95h
0x180045458  jmp     short loc_1800453E3
0x18004545a  mov     rcx, r14
0x18004545d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045462  mov     edi, eax
0x180045464  test    eax, eax
0x180045466  jns     short loc_18004548D
0x180045468  mov     edx, 97h; void *
0x18004546d  mov     rcx, [rbp+4Fh]; this
0x180045471  lea     r8, aOnecoreBaseCbs_7; "onecore\\base\\cbs\\pbr\\loader\\pbr_lo"...
0x180045478  mov     r9d, edi; char *
0x18004547b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180045480  lea     rcx, [rbp+47h+hModule]
0x180045484  call    ?Close@?$AutoGenericHandleBase@PEAUHINSTANCE__@@$0A@V?$AutoGenericHandle@PEAUHINSTANCE__@@$0A@$1?CloseWithFreeLibrary@Detail@Windows@@YAXPEAU1@@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(void)
0x180045489  mov     ebx, edi
0x18004548b  jmp     short loc_1800454E3
0x18004548d  mov     rcx, [r14]
0x180045490  mov     rax, [rcx]
0x180045493  mov     rax, [rax+18h]
0x180045497  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004549c  mov     edi, eax
0x18004549e  test    eax, eax
0x1800454a0  jns     short loc_1800454A9
0x1800454a2  mov     edx, 99h
0x1800454a7  jmp     short loc_18004546D
0x1800454a9  mov     rdx, r15; lpProcName
0x1800454ac  mov     rcx, rbx; hModule
0x1800454af  call    cs:__imp_GetProcAddress
0x1800454b6  nop     dword ptr [rax+rax+00h]
0x1800454bb  mov     [r12], rax
0x1800454bf  test    rax, rax
0x1800454c2  jnz     short loc_1800454CE
0x1800454c4  mov     edx, 9Ch
0x1800454c9  jmp     loc_1800453E3
0x1800454ce  mov     rax, [rsi]
0x1800454d1  lea     rcx, [rbp+47h+hModule]
0x1800454d5  mov     [rbp+47h+hModule], rax
0x1800454d9  mov     [rsi], rbx
0x1800454dc  call    ?Close@?$AutoGenericHandleBase@PEAUHINSTANCE__@@$0A@V?$AutoGenericHandle@PEAUHINSTANCE__@@$0A@$1?CloseWithFreeLibrary@Detail@Windows@@YAXPEAU1@@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(void)
0x1800454e1  xor     ebx, ebx
0x1800454e3  lea     rcx, [rbp+47h+var_90]; this
0x1800454e7  call    ??1AutoSsShim@Windows@@QEAA@XZ; Windows::AutoSsShim::~AutoSsShim(void)
0x1800454ec  lea     rcx, [rsp+120h+var_D8]
0x1800454f1  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x1800454f6  mov     eax, ebx
0x1800454f8  mov     rcx, [rbp+47h+var_40]
0x1800454fc  xor     rcx, rsp; StackCookie
0x1800454ff  call    __security_check_cookie
0x180045504  add     rsp, 0F0h
0x18004550b  pop     r15
0x18004550d  pop     r14
0x18004550f  pop     r12
0x180045511  pop     rdi
0x180045512  pop     rsi
0x180045513  pop     rbx
0x180045514  pop     rbp
0x180045515  retn
```
