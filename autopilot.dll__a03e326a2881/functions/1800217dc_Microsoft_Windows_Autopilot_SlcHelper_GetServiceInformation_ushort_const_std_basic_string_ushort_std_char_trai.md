# Microsoft::Windows::Autopilot::SlcHelper::GetServiceInformation(ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x1800217dc`
- end: `0x180021ae7`
- name: `?GetServiceInformation@SlcHelper@Autopilot@Windows@Microsoft@@SAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `779`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18001ad60`

## callees

- `0x1800045b0`
- `0x180009957`
- `0x1800105d4`
- `0x1800105f4`
- `0x180013a40`
- `0x1800174f0`
- `0x180018cd0`
- `0x1800217dc`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180021849`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180021881`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002189f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180021849`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180021881`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002189f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180021811`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180021811`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180021a7f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180021ac3`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180021a7f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180021ac3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021a75`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021ab9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021a75`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021ab9`

## string_xrefs

- `0x18002182a`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\slchelper.cpp`
- `0x180021866`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\slchelper.cpp`
- `0x1800218e7`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\slchelper.cpp`
- `0x180021965`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\slchelper.cpp`
- `0x180021a95`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\slchelper.cpp`
- `0x18002180a`: `slc.dll`
- `0x18002183f`: `SLOpen`
- `0x180021895`: `SLGetServiceInformation`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
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
  _WORD *v14; // rcx
  unsigned __int64 v15; // rdx
  __int64 v16; // rdi
  __int128 *v17; // rdx
  __int64 v18; // r8
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
        v14 = (_WORD *)a2;
      else
        v14 = *(_WORD **)a2;
      *(_QWORD *)(a2 + 16) = 0;
      *v14 = 0;
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
          &v29,
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
        std::wstring::_Tidy_deallocate(a2);
        *(_OWORD *)a2 = v32;
        *(__m128i *)(a2 + 16) = si128;
        si128 = _mm_load_si128((const __m128i *)&_xmm);
        LOWORD(v32) = 0;
      }
      std::wstring::_Tidy_deallocate(&v32);
      std::wstring::_Tidy_deallocate(&v29);
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
0x1800217dc  push    rbp
0x1800217de  push    rbx
0x1800217df  push    rsi
0x1800217e0  push    rdi
0x1800217e1  push    r14
0x1800217e3  push    r15
0x1800217e5  lea     rbp, [rsp-2Fh]
0x1800217ea  sub     rsp, 0D8h
0x1800217f1  mov     rax, cs:__security_cookie
0x1800217f8  xor     rax, rsp
0x1800217fb  mov     [rbp+57h+var_40], rax
0x1800217ff  mov     rsi, rdx
0x180021802  xor     edx, edx; hFile
0x180021804  mov     r8d, 800h; dwFlags
0x18002180a  lea     rcx, LibFileName; "slc.dll"
0x180021811  call    cs:__imp_LoadLibraryExW
0x180021817  mov     rbx, rax
0x18002181a  mov     [rbp+57h+var_B0], rax
0x18002181e  xor     r15d, r15d
0x180021821  test    rax, rax
0x180021824  jnz     short loc_18002183F
0x180021826  mov     rcx, [rbp+5Fh]; this
0x18002182a  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\moderndeployment\\au"...
0x180021831  lea     edx, [rax+27h]; void *
0x180021834  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180021839  nop
0x18002183a  jmp     loc_180021ACB
0x18002183f  lea     rdx, aSlopen; "SLOpen"
0x180021846  mov     rcx, rbx; hModule
0x180021849  call    cs:__imp_GetProcAddress
0x18002184f  mov     rdi, rax
0x180021852  test    rax, rax
0x180021855  jnz     short loc_180021877
0x180021857  lea     edx, [rax+2Ah]; void *
0x18002185a  mov     edi, 80004001h
0x18002185f  mov     rcx, [rbp+5Fh]; this
0x180021863  mov     r9d, edi; char *
0x180021866  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\moderndeployment\\au"...
0x18002186d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021872  jmp     loc_180021AC0
0x180021877  lea     rdx, aSlclose; "SLClose"
0x18002187e  mov     rcx, rbx; hModule
0x180021881  call    cs:__imp_GetProcAddress
0x180021887  mov     [rbp+57h+var_B8], rax
0x18002188b  test    rax, rax
0x18002188e  jnz     short loc_180021895
0x180021890  lea     edx, [rax+2Dh]
0x180021893  jmp     short loc_18002185A
0x180021895  lea     rdx, aSlgetservicein; "SLGetServiceInformation"
0x18002189c  mov     rcx, rbx; hModule
0x18002189f  call    cs:__imp_GetProcAddress
0x1800218a5  mov     r14, rax
0x1800218a8  test    rax, rax
0x1800218ab  jnz     short loc_1800218B2
0x1800218ad  lea     edx, [rax+30h]
0x1800218b0  jmp     short loc_18002185A
0x1800218b2  mov     [rbp+57h+var_C8], r15
0x1800218b6  mov     [rbp+57h+var_C0], r15d
0x1800218ba  mov     [rbp+57h+Src], r15
0x1800218be  lea     rax, [rbp+57h+Src]
0x1800218c2  mov     [rbp+57h+var_A8], rax
0x1800218c6  mov     [rbp+57h+var_A0], 1
0x1800218ca  mov     [rbp+57h+var_BC], r15d
0x1800218ce  lea     rcx, [rbp+57h+var_C8]
0x1800218d2  mov     rax, rdi
0x1800218d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800218da  mov     edi, eax
0x1800218dc  test    eax, eax
0x1800218de  jns     short loc_1800218FD
0x1800218e0  mov     rcx, [rbp+5Fh]; this
0x1800218e4  mov     r9d, eax; char *
0x1800218e7  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800218ee  mov     edx, 39h ; '9'; void *
0x1800218f3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800218f8  jmp     loc_180021AB5
0x1800218fd  lea     rax, [rbp+57h+var_B8]
0x180021901  mov     [rbp+57h+var_98], rax
0x180021905  lea     rax, [rbp+57h+var_C8]
0x180021909  mov     [rbp+57h+var_90], rax
0x18002190d  mov     [rbp+57h+var_88], 1
0x180021911  lea     rax, [rbp+57h+Src]
0x180021915  mov     qword ptr [rsp+100h+var_E0], rax; int
0x18002191a  lea     r9, [rbp+57h+var_BC]
0x18002191e  lea     r8, [rbp+57h+var_C0]
0x180021922  lea     rdx, aBiosproductkey; "BiosProductKey"
0x180021929  mov     rcx, [rbp+57h+var_C8]
0x18002192d  mov     rax, r14
0x180021930  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021935  mov     edi, eax
0x180021937  cmp     eax, 0C004F012h
0x18002193c  jnz     short loc_18002195A
0x18002193e  cmp     qword ptr [rsi+18h], 7
0x180021943  jbe     short loc_18002194A
0x180021945  mov     rcx, [rsi]
0x180021948  jmp     short loc_18002194D
0x18002194a  mov     rcx, rsi
0x18002194d  mov     [rsi+10h], r15
0x180021951  mov     [rcx], r15w
0x180021955  jmp     loc_180021A63
0x18002195a  test    eax, eax
0x18002195c  jns     short loc_18002198A
0x18002195e  mov     rcx, [rbp+5Fh]; this
0x180021962  mov     r9d, eax; char *
0x180021965  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\moderndeployment\\au"...
0x18002196c  mov     edx, 44h ; 'D'; void *
0x180021971  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021976  nop
0x180021977  mov     rcx, [rbp+57h+var_C8]
0x18002197b  mov     rax, [rbp+57h+var_B8]
0x18002197f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021984  nop
0x180021985  jmp     loc_180021AB5
0x18002198a  cmp     [rbp+57h+var_C0], 1
0x18002198e  jnz     loc_180021A89
0x180021994  mov     r9, [rbp+57h+Src]
0x180021998  test    r9, r9
0x18002199b  jz      loc_180021A89
0x1800219a1  xorps   xmm0, xmm0
0x1800219a4  movups  [rbp+57h+var_80], xmm0
0x1800219a8  mov     [rbp+57h+var_70], r15
0x1800219ac  mov     [rbp+57h+var_68], 7
0x1800219b4  mov     word ptr [rbp+57h+var_80], r15w
0x1800219b9  mov     edx, [rbp+57h+var_BC]
0x1800219bc  shr     rdx, 1
0x1800219bf  lea     rcx, [rbp+57h+var_80]; void *
0x1800219c3  cmp     rdx, 7
0x1800219c7  ja      short loc_1800219E4
0x1800219c9  mov     [rbp+57h+var_70], rdx
0x1800219cd  lea     rdi, [rdx+rdx]
0x1800219d1  mov     r8, rdi; Size
0x1800219d4  mov     rdx, r9; Src
0x1800219d7  call    memmove_0
0x1800219dc  mov     word ptr [rbp+rdi+57h+var_80], r15w
0x1800219e2  jmp     short loc_1800219E9
0x1800219e4  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x1800219e9  lea     rdx, [rbp+57h+var_80]
0x1800219ed  cmp     [rbp+57h+var_68], 7
0x1800219f2  cmova   rdx, qword ptr [rbp+57h+var_80]
0x1800219f7  xorps   xmm0, xmm0
0x1800219fa  movups  [rbp+57h+var_60], xmm0
0x1800219fe  xorps   xmm1, xmm1
0x180021a01  movdqu  [rbp+57h+var_50], xmm1
0x180021a06  or      r8, 0FFFFFFFFFFFFFFFFh
0x180021a0a  inc     r8
0x180021a0d  cmp     [rdx+r8*2], r15w
0x180021a12  jnz     short loc_180021A0A
0x180021a14  lea     rcx, [rbp+57h+var_60]
0x180021a18  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180021a1d  lea     rax, [rbp+57h+var_60]
0x180021a21  cmp     rsi, rax
0x180021a24  jz      short loc_180021A4F
0x180021a26  mov     rcx, rsi
0x180021a29  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180021a2e  movups  xmm0, [rbp+57h+var_60]
0x180021a32  movups  xmmword ptr [rsi], xmm0
0x180021a35  movups  xmm1, [rbp+57h+var_50]
0x180021a39  movups  xmmword ptr [rsi+10h], xmm1
0x180021a3d  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x180021a45  movdqu  [rbp+57h+var_50], xmm0
0x180021a4a  mov     word ptr [rbp+57h+var_60], r15w
0x180021a4f  lea     rcx, [rbp+57h+var_60]
0x180021a53  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180021a58  nop
0x180021a59  lea     rcx, [rbp+57h+var_80]
0x180021a5d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180021a62  nop
0x180021a63  mov     rcx, [rbp+57h+var_C8]
0x180021a67  mov     rax, [rbp+57h+var_B8]
0x180021a6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021a70  nop
0x180021a71  mov     rcx, [rbp+57h+Src]; hMem
0x180021a75  call    cs:__imp_LocalFree
0x180021a7b  nop
0x180021a7c  mov     rcx, rbx; hLibModule
0x180021a7f  call    cs:__imp_FreeLibrary
0x180021a85  xor     eax, eax
0x180021a87  jmp     short loc_180021ACB
0x180021a89  mov     rcx, [rbp+5Fh]; this
0x180021a8d  mov     edi, 8000FFFFh
0x180021a92  mov     r9d, edi; char *
0x180021a95  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\moderndeployment\\au"...
0x180021a9c  mov     edx, 52h ; 'R'; void *
0x180021aa1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021aa6  nop
0x180021aa7  mov     rcx, [rbp+57h+var_C8]
0x180021aab  mov     rax, [rbp+57h+var_B8]
0x180021aaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021ab4  nop
0x180021ab5  mov     rcx, [rbp+57h+Src]; hMem
0x180021ab9  call    cs:__imp_LocalFree
0x180021abf  nop
0x180021ac0  mov     rcx, rbx; hLibModule
0x180021ac3  call    cs:__imp_FreeLibrary
0x180021ac9  mov     eax, edi
0x180021acb  mov     rcx, [rbp+57h+var_40]
0x180021acf  xor     rcx, rsp; StackCookie
0x180021ad2  call    __security_check_cookie
0x180021ad7  add     rsp, 0D8h
0x180021ade  pop     r15
0x180021ae0  pop     r14
0x180021ae2  pop     rdi
0x180021ae3  pop     rsi
0x180021ae4  pop     rbx
0x180021ae5  pop     rbp
0x180021ae6  retn
```
