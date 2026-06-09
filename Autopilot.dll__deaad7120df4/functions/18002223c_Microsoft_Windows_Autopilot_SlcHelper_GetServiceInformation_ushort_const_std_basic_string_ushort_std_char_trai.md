# Microsoft::Windows::Autopilot::SlcHelper::GetServiceInformation(ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18002223c`
- end: `0x180022578`
- name: `?GetServiceInformation@SlcHelper@Autopilot@Windows@Microsoft@@SAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `828`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18001b3f0`

## callees

- `0x1800045d0`
- `0x1800098e7`
- `0x180010744`
- `0x180010764`
- `0x180013de4`
- `0x180017a20`
- `0x1800192a4`
- `0x18002223c`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800222af`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800222ed`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180022311`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800222af`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800222ed`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180022311`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180022271`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180022271`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800224fd`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002254d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800224fd`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002254d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800224ed`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002253d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800224ed`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002253d`

## string_xrefs

- `0x18002226a`: `slc.dll`
- `0x1800222a5`: `SLOpen`
- `0x180022290`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\slchelper.cpp`
- `0x1800222d2`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\slchelper.cpp`
- `0x18002235f`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\slchelper.cpp`
- `0x1800223dd`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\slchelper.cpp`
- `0x180022519`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\slchelper.cpp`
- `0x180022307`: `SLGetServiceInformation`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Autopilot::SlcHelper::GetServiceInformation(__int64 a1, __int64 a2)
{
  HMODULE Library; // rax
  const char *v4; // r9
  HMODULE v5; // rbx
  FARPROC ProcAddress; // rdi
  __int64 v8; // rdx
  unsigned int v9; // edi
  FARPROC v10; // r14
  int v11; // eax
  int v12; // eax
  __int64 v13; // r8
  char *v14; // rcx
  unsigned __int64 v15; // rdx
  __int64 v16; // rdi
  __int128 *v17; // rdx
  unsigned __int64 v18; // r8
  int v19; // [rsp+20h] [rbp-89h]
  void *Src; // [rsp+30h] [rbp-79h] BYREF
  __int64 v21; // [rsp+38h] [rbp-71h] BYREF
  int v22; // [rsp+40h] [rbp-69h] BYREF
  unsigned int v23; // [rsp+44h] [rbp-65h] BYREF
  _QWORD v24[3]; // [rsp+48h] [rbp-61h] BYREF
  char v25; // [rsp+60h] [rbp-49h]
  _QWORD *v26; // [rsp+68h] [rbp-41h]
  __int64 *v27; // [rsp+70h] [rbp-39h]
  char v28; // [rsp+78h] [rbp-31h]
  __int128 v29; // [rsp+80h] [rbp-29h] BYREF
  unsigned __int64 v30; // [rsp+90h] [rbp-19h]
  unsigned __int64 v31; // [rsp+98h] [rbp-11h]
  __int128 v32; // [rsp+A0h] [rbp-9h] BYREF
  __m128i si128; // [rsp+B0h] [rbp+7h]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  Library = LoadLibraryExW(L"slc.dll", 0, 0x800u);
  v5 = Library;
  v24[1] = Library;
  if ( !Library )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x27,
             (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\slchelper.cpp",
             v4);
  ProcAddress = GetProcAddress(Library, "SLOpen");
  if ( ProcAddress )
  {
    v24[0] = GetProcAddress(v5, "SLClose");
    if ( !v24[0] )
    {
      v8 = 45;
      goto LABEL_5;
    }
    v10 = GetProcAddress(v5, "SLGetServiceInformation");
    if ( !v10 )
    {
      v8 = 48;
      goto LABEL_5;
    }
    v21 = 0;
    v22 = 0;
    Src = 0;
    v24[2] = &Src;
    v25 = 1;
    v23 = 0;
    v11 = ((__int64 (__fastcall *)(__int64 *))ProcAddress)(&v21);
    v9 = v11;
    if ( v11 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x39,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\slchelper.cpp",
        (const char *)(unsigned int)v11,
        v19);
LABEL_33:
      LocalFree(Src);
      goto LABEL_34;
    }
    v26 = v24;
    v27 = &v21;
    v28 = 1;
    v12 = ((__int64 (__fastcall *)(__int64, const wchar_t *, int *, unsigned int *))v10)(
            v21,
            L"BiosProductKey",
            &v22,
            &v23);
    v9 = v12;
    if ( v12 == -1073418222 )
    {
      if ( *(_QWORD *)(a2 + 24) <= 7u )
        v14 = (char *)a2;
      else
        v14 = *(char **)a2;
      *(_QWORD *)(a2 + 16) = 0;
      *(_WORD *)v14 = 0;
    }
    else
    {
      if ( v12 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x44,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\slchelper.cpp",
          (const char *)(unsigned int)v12,
          (int)&Src);
        ((void (__fastcall *)(__int64))v24[0])(v21);
        goto LABEL_33;
      }
      if ( v22 != 1 || !Src )
      {
        v9 = -2147418113;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x52,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\slchelper.cpp",
          (const char *)0x8000FFFFLL,
          (int)&Src);
        ((void (__fastcall *)(__int64))v24[0])(v21);
        goto LABEL_33;
      }
      v29 = 0;
      v30 = 0;
      v31 = 7;
      LOWORD(v29) = 0;
      v15 = (unsigned __int64)v23 >> 1;
      if ( v15 > 7 )
      {
        std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
          (char **)&v29,
          v15,
          v13,
          Src);
      }
      else
      {
        v30 = (unsigned __int64)v23 >> 1;
        v16 = 2 * v15;
        memmove_0(&v29, Src, 2 * v15);
        *(_WORD *)((char *)&v29 + v16) = 0;
      }
      v17 = &v29;
      if ( v31 > 7 )
        v17 = (__int128 *)v29;
      v32 = 0;
      si128 = 0;
      v18 = -1;
      do
        ++v18;
      while ( *((_WORD *)v17 + v18) );
      std::wstring::_Construct<1,unsigned short const *>(&v32, v17, v18);
      if ( (__int128 *)a2 != &v32 )
      {
        std::wstring::_Tidy_deallocate((char **)a2);
        *(_OWORD *)a2 = v32;
        *(__m128i *)(a2 + 16) = si128;
        si128 = _mm_load_si128((const __m128i *)&_xmm);
        LOWORD(v32) = 0;
      }
      std::wstring::_Tidy_deallocate((char **)&v32);
      std::wstring::_Tidy_deallocate((char **)&v29);
    }
    ((void (__fastcall *)(__int64))v24[0])(v21);
    LocalFree(Src);
    FreeLibrary(v5);
    return 0;
  }
  v8 = 42;
LABEL_5:
  v9 = -2147467263;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\slchelper.cpp",
    (const char *)0x80004001LL,
    v19);
LABEL_34:
  FreeLibrary(v5);
  return v9;
}

```

## disassembly

```asm
0x18002223c  push    rbp
0x18002223e  push    rbx
0x18002223f  push    rsi
0x180022240  push    rdi
0x180022241  push    r14
0x180022243  push    r15
0x180022245  lea     rbp, [rsp-2Fh]
0x18002224a  sub     rsp, 0D8h
0x180022251  mov     rax, cs:__security_cookie
0x180022258  xor     rax, rsp
0x18002225b  mov     [rbp+57h+var_40], rax
0x18002225f  mov     rsi, rdx
0x180022262  xor     edx, edx; hFile
0x180022264  mov     r8d, 800h; dwFlags
0x18002226a  lea     rcx, LibFileName; "slc.dll"
0x180022271  call    cs:__imp_LoadLibraryExW
0x180022278  nop     dword ptr [rax+rax+00h]
0x18002227d  mov     rbx, rax
0x180022280  mov     [rbp+57h+var_B0], rax
0x180022284  xor     r15d, r15d
0x180022287  test    rax, rax
0x18002228a  jnz     short loc_1800222A5
0x18002228c  mov     rcx, [rbp+5Fh]; this
0x180022290  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\moderndeployment\\au"...
0x180022297  lea     edx, [rax+27h]; void *
0x18002229a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002229f  nop
0x1800222a0  jmp     loc_18002255B
0x1800222a5  lea     rdx, aSlopen; "SLOpen"
0x1800222ac  mov     rcx, rbx; hModule
0x1800222af  call    cs:__imp_GetProcAddress
0x1800222b6  nop     dword ptr [rax+rax+00h]
0x1800222bb  mov     rdi, rax
0x1800222be  test    rax, rax
0x1800222c1  jnz     short loc_1800222E3
0x1800222c3  lea     edx, [rax+2Ah]; void *
0x1800222c6  mov     edi, 80004001h
0x1800222cb  mov     rcx, [rbp+5Fh]; this
0x1800222cf  mov     r9d, edi; char *
0x1800222d2  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800222d9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800222de  jmp     loc_18002254A
0x1800222e3  lea     rdx, aSlclose; "SLClose"
0x1800222ea  mov     rcx, rbx; hModule
0x1800222ed  call    cs:__imp_GetProcAddress
0x1800222f4  nop     dword ptr [rax+rax+00h]
0x1800222f9  mov     [rbp+57h+var_B8], rax
0x1800222fd  test    rax, rax
0x180022300  jnz     short loc_180022307
0x180022302  lea     edx, [rax+2Dh]
0x180022305  jmp     short loc_1800222C6
0x180022307  lea     rdx, aSlgetservicein; "SLGetServiceInformation"
0x18002230e  mov     rcx, rbx; hModule
0x180022311  call    cs:__imp_GetProcAddress
0x180022318  nop     dword ptr [rax+rax+00h]
0x18002231d  mov     r14, rax
0x180022320  test    rax, rax
0x180022323  jnz     short loc_18002232A
0x180022325  lea     edx, [rax+30h]
0x180022328  jmp     short loc_1800222C6
0x18002232a  mov     [rbp+57h+var_C8], r15
0x18002232e  mov     [rbp+57h+var_C0], r15d
0x180022332  mov     [rbp+57h+Src], r15
0x180022336  lea     rax, [rbp+57h+Src]
0x18002233a  mov     [rbp+57h+var_A8], rax
0x18002233e  mov     [rbp+57h+var_A0], 1
0x180022342  mov     [rbp+57h+var_BC], r15d
0x180022346  lea     rcx, [rbp+57h+var_C8]
0x18002234a  mov     rax, rdi
0x18002234d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022352  mov     edi, eax
0x180022354  test    eax, eax
0x180022356  jns     short loc_180022375
0x180022358  mov     rcx, [rbp+5Fh]; this
0x18002235c  mov     r9d, eax; char *
0x18002235f  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\moderndeployment\\au"...
0x180022366  mov     edx, 39h ; '9'; void *
0x18002236b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022370  jmp     loc_180022539
0x180022375  lea     rax, [rbp+57h+var_B8]
0x180022379  mov     [rbp+57h+var_98], rax
0x18002237d  lea     rax, [rbp+57h+var_C8]
0x180022381  mov     [rbp+57h+var_90], rax
0x180022385  mov     [rbp+57h+var_88], 1
0x180022389  lea     rax, [rbp+57h+Src]
0x18002238d  mov     qword ptr [rsp+100h+var_E0], rax; int
0x180022392  lea     r9, [rbp+57h+var_BC]
0x180022396  lea     r8, [rbp+57h+var_C0]
0x18002239a  lea     rdx, aBiosproductkey; "BiosProductKey"
0x1800223a1  mov     rcx, [rbp+57h+var_C8]
0x1800223a5  mov     rax, r14
0x1800223a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800223ad  mov     edi, eax
0x1800223af  cmp     eax, 0C004F012h
0x1800223b4  jnz     short loc_1800223D2
0x1800223b6  cmp     qword ptr [rsi+18h], 7
0x1800223bb  jbe     short loc_1800223C2
0x1800223bd  mov     rcx, [rsi]
0x1800223c0  jmp     short loc_1800223C5
0x1800223c2  mov     rcx, rsi
0x1800223c5  mov     [rsi+10h], r15
0x1800223c9  mov     [rcx], r15w
0x1800223cd  jmp     loc_1800224DB
0x1800223d2  test    eax, eax
0x1800223d4  jns     short loc_180022402
0x1800223d6  mov     rcx, [rbp+5Fh]; this
0x1800223da  mov     r9d, eax; char *
0x1800223dd  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800223e4  mov     edx, 44h ; 'D'; void *
0x1800223e9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800223ee  nop
0x1800223ef  mov     rcx, [rbp+57h+var_C8]
0x1800223f3  mov     rax, [rbp+57h+var_B8]
0x1800223f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800223fc  nop
0x1800223fd  jmp     loc_180022539
0x180022402  cmp     [rbp+57h+var_C0], 1
0x180022406  jnz     loc_18002250D
0x18002240c  mov     r9, [rbp+57h+Src]
0x180022410  test    r9, r9
0x180022413  jz      loc_18002250D
0x180022419  xorps   xmm0, xmm0
0x18002241c  movups  [rbp+57h+var_80], xmm0
0x180022420  mov     [rbp+57h+var_70], r15
0x180022424  mov     [rbp+57h+var_68], 7
0x18002242c  mov     word ptr [rbp+57h+var_80], r15w
0x180022431  mov     edx, [rbp+57h+var_BC]
0x180022434  shr     rdx, 1
0x180022437  lea     rcx, [rbp+57h+var_80]; void *
0x18002243b  cmp     rdx, 7
0x18002243f  ja      short loc_18002245C
0x180022441  mov     [rbp+57h+var_70], rdx
0x180022445  lea     rdi, [rdx+rdx]
0x180022449  mov     r8, rdi; Size
0x18002244c  mov     rdx, r9; Src
0x18002244f  call    memmove_0
0x180022454  mov     word ptr [rbp+rdi+57h+var_80], r15w
0x18002245a  jmp     short loc_180022461
0x18002245c  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180022461  lea     rdx, [rbp+57h+var_80]
0x180022465  cmp     [rbp+57h+var_68], 7
0x18002246a  cmova   rdx, qword ptr [rbp+57h+var_80]
0x18002246f  xorps   xmm0, xmm0
0x180022472  movups  [rbp+57h+var_60], xmm0
0x180022476  xorps   xmm1, xmm1
0x180022479  movdqu  [rbp+57h+var_50], xmm1
0x18002247e  or      r8, 0FFFFFFFFFFFFFFFFh
0x180022482  inc     r8
0x180022485  cmp     [rdx+r8*2], r15w
0x18002248a  jnz     short loc_180022482
0x18002248c  lea     rcx, [rbp+57h+var_60]
0x180022490  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180022495  lea     rax, [rbp+57h+var_60]
0x180022499  cmp     rsi, rax
0x18002249c  jz      short loc_1800224C7
0x18002249e  mov     rcx, rsi
0x1800224a1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800224a6  movups  xmm0, [rbp+57h+var_60]
0x1800224aa  movups  xmmword ptr [rsi], xmm0
0x1800224ad  movups  xmm1, [rbp+57h+var_50]
0x1800224b1  movups  xmmword ptr [rsi+10h], xmm1
0x1800224b5  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x1800224bd  movdqu  [rbp+57h+var_50], xmm0
0x1800224c2  mov     word ptr [rbp+57h+var_60], r15w
0x1800224c7  lea     rcx, [rbp+57h+var_60]
0x1800224cb  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800224d0  nop
0x1800224d1  lea     rcx, [rbp+57h+var_80]
0x1800224d5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800224da  nop
0x1800224db  mov     rcx, [rbp+57h+var_C8]
0x1800224df  mov     rax, [rbp+57h+var_B8]
0x1800224e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800224e8  nop
0x1800224e9  mov     rcx, [rbp+57h+Src]; hMem
0x1800224ed  call    cs:__imp_LocalFree
0x1800224f4  nop     dword ptr [rax+rax+00h]
0x1800224f9  nop
0x1800224fa  mov     rcx, rbx; hLibModule
0x1800224fd  call    cs:__imp_FreeLibrary
0x180022504  nop     dword ptr [rax+rax+00h]
0x180022509  xor     eax, eax
0x18002250b  jmp     short loc_18002255B
0x18002250d  mov     rcx, [rbp+5Fh]; this
0x180022511  mov     edi, 8000FFFFh
0x180022516  mov     r9d, edi; char *
0x180022519  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\moderndeployment\\au"...
0x180022520  mov     edx, 52h ; 'R'; void *
0x180022525  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002252a  nop
0x18002252b  mov     rcx, [rbp+57h+var_C8]
0x18002252f  mov     rax, [rbp+57h+var_B8]
0x180022533  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022538  nop
0x180022539  mov     rcx, [rbp+57h+Src]; hMem
0x18002253d  call    cs:__imp_LocalFree
0x180022544  nop     dword ptr [rax+rax+00h]
0x180022549  nop
0x18002254a  mov     rcx, rbx; hLibModule
0x18002254d  call    cs:__imp_FreeLibrary
0x180022554  nop     dword ptr [rax+rax+00h]
0x180022559  mov     eax, edi
0x18002255b  mov     rcx, [rbp+57h+var_40]
0x18002255f  xor     rcx, rsp; StackCookie
0x180022562  call    __security_check_cookie
0x180022567  add     rsp, 0D8h
0x18002256e  pop     r15
0x180022570  pop     r14
0x180022572  pop     rdi
0x180022573  pop     rsi
0x180022574  pop     rbx
0x180022575  pop     rbp
0x180022576  retn
```
