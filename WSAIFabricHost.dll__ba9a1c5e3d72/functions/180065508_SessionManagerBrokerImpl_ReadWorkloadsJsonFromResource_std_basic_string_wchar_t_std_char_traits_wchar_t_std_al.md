# SessionManagerBrokerImpl::ReadWorkloadsJsonFromResource(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,uint)

- ea: `0x180065508`
- end: `0x1800658db`
- name: `?ReadWorkloadsJsonFromResource@SessionManagerBrokerImpl@@AEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV23@I@Z`
- size: `979`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, unsigned __int16)`
- caller_count: `2`
- callee_count: `14`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180061350`
- `0x1800864da`

## callees

- `0x180004ca0`
- `0x180005120`
- `0x180005140`
- `0x180007cdc`
- `0x180007d44`
- `0x180007f4e`
- `0x180012354`
- `0x1800136b8`
- `0x1800143c0`
- `0x180014428`
- `0x18001899c`
- `0x1800189b8`
- `0x18002940c`
- `0x180065508`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18006580b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18006580b`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x1800655ad`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x1800655ad`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180065597`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180065597`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180065555`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180065555`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x1800655bc`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x1800655bc`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18006577f`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800657ce`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18006577f`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800657ce`
- `api-ms-win-core-libraryloader-l1-2-1!FindResourceW` at `0x18006557b`
- `api-ms-win-core-libraryloader-l1-2-1!FindResourceW` at `0x18006557b`

## string_xrefs

- `0x18006583b`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\sessionmanagerbrokerimpl.cpp`
- `0x18006584d`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\sessionmanagerbrokerimpl.cpp`
- `0x180065865`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\sessionmanagerbrokerimpl.cpp`
- `0x180065877`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\sessionmanagerbrokerimpl.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SessionManagerBrokerImpl::ReadWorkloadsJsonFromResource(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned __int16 a4)
{
  const WCHAR *v5; // rax
  HMODULE Library; // rax
  const char *v8; // r9
  HMODULE v9; // rbx
  HRSRC ResourceW; // rax
  HRSRC v11; // r14
  HGLOBAL Resource; // rax
  const char *v13; // r9
  LPVOID v14; // rdi
  DWORD v15; // eax
  __int64 v16; // r15
  __int64 *v17; // rdi
  size_t v18; // r14
  size_t v19; // rdi
  size_t v20; // r12
  void **v21; // rcx
  void **v22; // r13
  size_t v23; // r8
  int v24; // eax
  __int64 v25; // rdi
  void **v26; // rdx
  unsigned __int64 v27; // rdx
  void *v28; // rcx
  void **v29; // r8
  int v30; // eax
  const char *v31; // r9
  int cchWideChar; // edi
  WCHAR *v33; // rax
  void **v34; // r8
  int lpWideCharStr; // [rsp+20h] [rbp-69h]
  __int64 *Buf2; // [rsp+30h] [rbp-59h]
  void *Buf1[2]; // [rsp+48h] [rbp-41h] BYREF
  int cbMultiByte[4]; // [rsp+58h] [rbp-31h] BYREF
  __int128 v40; // [rsp+68h] [rbp-21h] BYREF
  __int128 v41; // [rsp+78h] [rbp-11h]
  LPWSTR v42[2]; // [rsp+88h] [rbp-1h] BYREF
  __int128 v43; // [rsp+98h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v5 = (const WCHAR *)a3;
  if ( *(_QWORD *)(a3 + 24) > 7u )
    v5 = *(const WCHAR **)a3;
  Library = LoadLibraryExW(v5, 0, 2u);
  v9 = Library;
  if ( !Library )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x598,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\sessionmanagerbrokerimpl.cpp",
      v8);
  ResourceW = FindResourceW(Library, (LPCWSTR)a4, (LPCWSTR)0x3E8);
  v11 = ResourceW;
  if ( !ResourceW )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x59B,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\sessionmanagerbrokerimpl.cpp",
      (const char *)0x80070714LL,
      lpWideCharStr);
  Resource = LoadResource(v9, ResourceW);
  if ( !Resource )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x59E,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\sessionmanagerbrokerimpl.cpp",
      v13);
  v14 = LockResource(Resource);
  v15 = SizeofResource(v9, v11);
  *(_OWORD *)Buf1 = 0;
  memset(cbMultiByte, 0, sizeof(cbMultiByte));
  std::string::_Construct<1,char const *>(Buf1, v14, v15);
  v16 = -1;
  v17 = &qword_1800AFE50;
  if ( dword_1800AFE48 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_1800AFE48);
    if ( dword_1800AFE48 == -1 )
    {
      std::string::_Construct<1,char const *>(&qword_1800AFE50, &qword_1800961B0, 3);
      atexit(SessionManagerBrokerImpl::ReadWorkloadsJsonFromResource_::_2_::_dynamic_atexit_destructor_for__bom_utf8__);
      Init_thread_footer(&dword_1800AFE48);
    }
  }
  v18 = Size;
  if ( (unsigned __int64)qword_1800AFE68 > 0xF )
    v17 = (__int64 *)qword_1800AFE50;
  Buf2 = v17;
  v19 = *(_QWORD *)cbMultiByte;
  v20 = *(_QWORD *)cbMultiByte;
  if ( *(_QWORD *)cbMultiByte >= Size )
    v20 = Size;
  v21 = Buf1;
  v22 = (void **)Buf1[0];
  if ( *(_QWORD *)&cbMultiByte[2] > 0xFu )
    v21 = (void **)Buf1[0];
  v23 = v20;
  if ( Size < v20 )
    v23 = Size;
  v24 = memcmp_0(v21, Buf2, v23);
  if ( !v24 )
  {
    if ( v20 < v18 || v20 > v18 )
      goto LABEL_33;
    v24 = 0;
  }
  if ( !v24 )
  {
    v40 = 0;
    v41 = 0u;
    if ( v19 < v18 )
      std::_String_val<std::_Simple_types<char>>::_Xran();
    v25 = v19 - v18;
    if ( v25 != -1 )
      v16 = v25;
    v26 = Buf1;
    if ( *(_QWORD *)&cbMultiByte[2] > 0xFu )
      v26 = v22;
    std::string::_Construct<1,char const *>(&v40, (char *)v26 + v18, v16);
    if ( *(_QWORD *)&cbMultiByte[2] > 0xFu )
    {
      v27 = *(_QWORD *)&cbMultiByte[2] + 1LL;
      if ( (unsigned __int64)(*(_QWORD *)&cbMultiByte[2] + 1LL) < 0x1000 )
      {
        v28 = Buf1[0];
      }
      else
      {
        v28 = (void *)*((_QWORD *)Buf1[0] - 1);
        if ( (unsigned __int64)((char *)Buf1[0] - (char *)v28 - 8) > 0x1F )
          __fastfail(5u);
        v27 = *(_QWORD *)&cbMultiByte[2] + 40LL;
      }
      operator delete(v28, v27);
    }
    *(_OWORD *)Buf1 = v40;
    *(_OWORD *)cbMultiByte = v41;
    *(_QWORD *)&v41 = 0;
    *((_QWORD *)&v41 + 1) = 15;
    LOBYTE(v40) = 0;
    std::string::~string(&v40);
    v19 = *(_QWORD *)cbMultiByte;
    v22 = (void **)Buf1[0];
  }
LABEL_33:
  if ( v19 )
  {
    v29 = Buf1;
    if ( *(_QWORD *)&cbMultiByte[2] > 0xFu )
      v29 = v22;
    v30 = MultiByteToWideChar(0xFDE9u, 0, (LPCCH)v29, v19, 0, 0);
    cchWideChar = v30;
    if ( !v30 )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x5B2,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\sessionmanagerbrokerimpl.cpp",
        v31);
    std::wstring::wstring(v42, v30);
    v33 = (WCHAR *)v42;
    if ( *((_QWORD *)&v43 + 1) > 7u )
      v33 = v42[0];
    v34 = Buf1;
    if ( *(_QWORD *)&cbMultiByte[2] > 0xFu )
      v34 = (void **)Buf1[0];
    MultiByteToWideChar(0xFDE9u, 0, (LPCCH)v34, cbMultiByte[0], v33, cchWideChar);
    *(_OWORD *)a2 = *(_OWORD *)v42;
    *(_OWORD *)(a2 + 16) = v43;
    *(_QWORD *)&v43 = 0;
    *((_QWORD *)&v43 + 1) = 7;
    LOWORD(v42[0]) = 0;
    std::wstring::~wstring(v42);
  }
  else
  {
    *(_OWORD *)a2 = 0;
    *(_QWORD *)(a2 + 16) = 0;
    *(_QWORD *)(a2 + 24) = 7;
    *(_WORD *)a2 = 0;
  }
  std::string::~string(Buf1);
  FreeLibrary(v9);
  return a2;
}

```

## disassembly

```asm
0x180065508  mov     [rsp-8+arg_0], rbx
0x18006550d  push    rbp
0x18006550e  push    rsi
0x18006550f  push    rdi
0x180065510  push    r12
0x180065512  push    r13
0x180065514  push    r14
0x180065516  push    r15
0x180065518  lea     rbp, [rsp-27h]
0x18006551d  sub     rsp, 0B0h
0x180065524  mov     rax, cs:__security_cookie
0x18006552b  xor     rax, rsp
0x18006552e  mov     [rbp+57h+var_38], rax
0x180065532  mov     edi, r9d
0x180065535  mov     rax, r8
0x180065538  mov     rsi, rdx
0x18006553b  mov     [rbp+57h+Buf2], rdx
0x18006553f  xor     r15d, r15d
0x180065542  cmp     qword ptr [r8+18h], 7
0x180065547  jbe     short loc_18006554C
0x180065549  mov     rax, [r8]
0x18006554c  xor     edx, edx; hFile
0x18006554e  lea     r8d, [rdx+2]; dwFlags
0x180065552  mov     rcx, rax; lpLibFileName
0x180065555  call    cs:__imp_LoadLibraryExW
0x18006555b  mov     rbx, rax
0x18006555e  mov     [rbp+57h+var_A0], rax
0x180065562  mov     rcx, [rbp+5Fh]; this
0x180065566  test    rax, rax
0x180065569  jz      loc_18006584D
0x18006556f  movzx   edx, di; lpName
0x180065572  mov     r8d, 3E8h; lpType
0x180065578  mov     rcx, rax; hModule
0x18006557b  call    cs:__imp_FindResourceW
0x180065581  mov     r14, rax
0x180065584  mov     rcx, [rbp+5Fh]; this
0x180065588  test    rax, rax
0x18006558b  jz      loc_18006585F
0x180065591  mov     rdx, rax; hResInfo
0x180065594  mov     rcx, rbx; hModule
0x180065597  call    cs:__imp_LoadResource
0x18006559d  mov     rcx, [rbp+5Fh]; this
0x1800655a1  test    rax, rax
0x1800655a4  jz      loc_180065877
0x1800655aa  mov     rcx, rax; hResData
0x1800655ad  call    cs:__imp_LockResource
0x1800655b3  mov     rdi, rax
0x1800655b6  mov     rdx, r14; hResInfo
0x1800655b9  mov     rcx, rbx; hModule
0x1800655bc  call    cs:__imp_SizeofResource
0x1800655c2  xorps   xmm0, xmm0
0x1800655c5  movups  xmmword ptr [rbp+57h+Buf1], xmm0
0x1800655c9  mov     qword ptr [rbp+57h+cbMultiByte], r15
0x1800655cd  mov     qword ptr [rbp+57h+cbMultiByte+8], r15
0x1800655d1  mov     r8d, eax
0x1800655d4  mov     rdx, rdi
0x1800655d7  lea     rcx, [rbp+57h+Buf1]
0x1800655db  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800655e0  nop
0x1800655e1  mov     ecx, cs:_tls_index
0x1800655e7  mov     rax, gs:58h
0x1800655f0  mov     edx, 4
0x1800655f5  mov     rax, [rax+rcx*8]
0x1800655f9  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800655fd  lea     rdi, qword_1800AFE50
0x180065604  mov     eax, [rdx+rax]
0x180065607  cmp     cs:dword_1800AFE48, eax
0x18006560d  jg      loc_180065889
0x180065613  mov     r14, cs:Size
0x18006561a  cmp     cs:qword_1800AFE68, 0Fh
0x180065622  cmova   rdi, cs:qword_1800AFE50
0x18006562a  mov     [rbp+57h+Buf2], rdi
0x18006562e  mov     rdi, qword ptr [rbp+57h+cbMultiByte]
0x180065632  mov     r12, rdi
0x180065635  cmp     rdi, r14
0x180065638  cmovnb  r12, r14
0x18006563c  lea     rcx, [rbp+57h+Buf1]
0x180065640  mov     r13, [rbp+57h+Buf1]
0x180065644  cmp     qword ptr [rbp+57h+cbMultiByte+8], 0Fh
0x180065649  cmova   rcx, r13; Buf1
0x18006564d  mov     r8, r12
0x180065650  cmp     r14, r12
0x180065653  cmovb   r8, r14; Size
0x180065657  mov     rdx, [rbp+57h+Buf2]; Buf2
0x18006565b  call    memcmp_0
0x180065660  test    eax, eax
0x180065662  jz      short loc_180065669
0x180065664  xor     r12d, r12d
0x180065667  jmp     short loc_18006567E
0x180065669  cmp     r12, r14
0x18006566c  jb      loc_180065737
0x180065672  ja      loc_180065737
0x180065678  xor     r12d, r12d
0x18006567b  mov     eax, r12d
0x18006567e  test    eax, eax
0x180065680  jnz     loc_18006573A
0x180065686  xorps   xmm0, xmm0
0x180065689  movups  [rbp+57h+var_78], xmm0
0x18006568d  mov     qword ptr [rbp+57h+var_68], r12
0x180065691  mov     qword ptr [rbp+57h+var_68+8], r12
0x180065695  cmp     rdi, r14
0x180065698  jb      loc_1800658D5
0x18006569e  sub     rdi, r14
0x1800656a1  cmp     rdi, r15
0x1800656a4  cmovb   r15, rdi
0x1800656a8  lea     rdx, [rbp+57h+Buf1]
0x1800656ac  cmp     qword ptr [rbp+57h+cbMultiByte+8], 0Fh
0x1800656b1  cmova   rdx, r13
0x1800656b5  add     rdx, r14
0x1800656b8  mov     r8, r15
0x1800656bb  lea     rcx, [rbp+57h+var_78]
0x1800656bf  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800656c4  mov     rdx, qword ptr [rbp+57h+cbMultiByte+8]
0x1800656c8  cmp     rdx, 0Fh
0x1800656cc  jbe     short loc_180065704
0x1800656ce  mov     rax, [rbp+57h+Buf1]
0x1800656d2  inc     rdx; unsigned __int64
0x1800656d5  cmp     rdx, 1000h
0x1800656dc  jb      short loc_1800656FC
0x1800656de  mov     rcx, [rax-8]
0x1800656e2  sub     rax, rcx
0x1800656e5  sub     rax, 8
0x1800656e9  cmp     rax, 1Fh
0x1800656ed  ja      short loc_1800656F5
0x1800656ef  add     rdx, 27h ; '''
0x1800656f3  jmp     short loc_1800656FF
0x1800656f5  mov     ecx, 5
0x1800656fa  int     29h; Win8: RtlFailFast(ecx)
0x1800656fc  mov     rcx, rax; void *
0x1800656ff  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180065704  movups  xmm0, [rbp+57h+var_78]
0x180065708  movups  xmmword ptr [rbp+57h+Buf1], xmm0
0x18006570c  movups  xmm1, [rbp+57h+var_68]
0x180065710  movups  xmmword ptr [rbp+57h+cbMultiByte], xmm1
0x180065714  mov     qword ptr [rbp+57h+var_68], r12
0x180065718  mov     qword ptr [rbp+57h+var_68+8], 0Fh
0x180065720  mov     byte ptr [rbp+57h+var_78], r12b
0x180065724  lea     rcx, [rbp+57h+var_78]
0x180065728  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18006572d  mov     rdi, qword ptr [rbp+57h+cbMultiByte]
0x180065731  mov     r13, [rbp+57h+Buf1]
0x180065735  jmp     short loc_18006573A
0x180065737  xor     r12d, r12d
0x18006573a  test    rdi, rdi
0x18006573d  jnz     short loc_18006575A
0x18006573f  xorps   xmm0, xmm0
0x180065742  movups  xmmword ptr [rsi], xmm0
0x180065745  mov     [rsi+10h], r12
0x180065749  mov     qword ptr [rsi+18h], 7
0x180065751  mov     [rsi], r12w
0x180065755  jmp     loc_1800657FE
0x18006575a  lea     r8, [rbp+57h+Buf1]
0x18006575e  cmp     qword ptr [rbp+57h+cbMultiByte+8], 0Fh
0x180065763  cmova   r8, r13; lpMultiByteStr
0x180065767  mov     [rsp+0E0h+cchWideChar], r12d; cchWideChar
0x18006576c  mov     [rsp+0E0h+lpWideCharStr], r12; lpWideCharStr
0x180065771  mov     r9d, edi; cbMultiByte
0x180065774  xor     edx, edx; dwFlags
0x180065776  mov     r14d, 0FDE9h
0x18006577c  mov     ecx, r14d; CodePage
0x18006577f  call    cs:__imp_MultiByteToWideChar
0x180065785  movsxd  rdi, eax
0x180065788  mov     rcx, [rbp+5Fh]; this
0x18006578c  test    eax, eax
0x18006578e  jz      loc_18006583B
0x180065794  mov     rdx, rdi
0x180065797  lea     rcx, [rbp+57h+var_58]
0x18006579b  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@_K_W@Z; std::wstring::wstring(unsigned __int64,wchar_t)
0x1800657a0  lea     rax, [rbp+57h+var_58]
0x1800657a4  cmp     [rbp+57h+var_40], 7
0x1800657a9  cmova   rax, [rbp+57h+var_58]
0x1800657ae  lea     r8, [rbp+57h+Buf1]
0x1800657b2  cmp     qword ptr [rbp+57h+cbMultiByte+8], 0Fh
0x1800657b7  cmova   r8, [rbp+57h+Buf1]; lpMultiByteStr
0x1800657bc  mov     [rsp+0E0h+cchWideChar], edi; cchWideChar
0x1800657c0  mov     [rsp+0E0h+lpWideCharStr], rax; lpWideCharStr
0x1800657c5  mov     r9d, [rbp+57h+cbMultiByte]; cbMultiByte
0x1800657c9  xor     edx, edx; dwFlags
0x1800657cb  mov     ecx, r14d; CodePage
0x1800657ce  call    cs:__imp_MultiByteToWideChar
0x1800657d4  movups  xmm0, xmmword ptr [rbp+57h+var_58]
0x1800657d8  movups  xmmword ptr [rsi], xmm0
0x1800657db  movups  xmm1, xmmword ptr [rbp+0Fh]
0x1800657df  movups  xmmword ptr [rsi+10h], xmm1
0x1800657e3  mov     [rbp+57h+var_48], r12
0x1800657e7  mov     [rbp+57h+var_40], 7
0x1800657ef  mov     word ptr [rbp+57h+var_58], r12w
0x1800657f4  lea     rcx, [rbp+57h+var_58]
0x1800657f8  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800657fd  nop
0x1800657fe  lea     rcx, [rbp+57h+Buf1]
0x180065802  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180065807  nop
0x180065808  mov     rcx, rbx; hLibModule
0x18006580b  call    cs:__imp_FreeLibrary
0x180065811  mov     rax, rsi
0x180065814  mov     rcx, [rbp+57h+var_38]
0x180065818  xor     rcx, rsp; StackCookie
0x18006581b  call    __security_check_cookie
0x180065820  mov     rbx, [rsp+0E0h+arg_0]
0x180065828  add     rsp, 0B0h
0x18006582f  pop     r15
0x180065831  pop     r14
0x180065833  pop     r13
0x180065835  pop     r12
0x180065837  pop     rdi
0x180065838  pop     rsi
0x180065839  pop     rbp
0x18006583a  retn
0x18006583b  lea     r8, aOnecoreuapBase_11; "onecoreuap\\base\\appmodel\\search\\com"...
0x180065842  mov     edx, 5B2h; void *
0x180065847  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18006584d  lea     r8, aOnecoreuapBase_11; "onecoreuap\\base\\appmodel\\search\\com"...
0x180065854  mov     edx, 598h; void *
0x180065859  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18006585f  mov     r9d, 80070714h; char *
0x180065865  lea     r8, aOnecoreuapBase_11; "onecoreuap\\base\\appmodel\\search\\com"...
0x18006586c  mov     edx, 59Bh; void *
0x180065871  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180065877  lea     r8, aOnecoreuapBase_11; "onecoreuap\\base\\appmodel\\search\\com"...
0x18006587e  mov     edx, 59Eh; void *
0x180065883  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180065889  lea     rcx, dword_1800AFE48
0x180065890  call    _Init_thread_header
0x180065895  cmp     cs:dword_1800AFE48, r15d
0x18006589c  jnz     loc_180065613
0x1800658a2  mov     r8d, 3
0x1800658a8  lea     rdx, qword_1800961B0
0x1800658af  mov     rcx, rdi
0x1800658b2  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800658b7  lea     rcx, _SessionManagerBrokerImpl__ReadWorkloadsJsonFromResource____2____dynamic_atexit_destructor_for__bom_utf8__; void (__cdecl *)()
0x1800658be  call    atexit
0x1800658c3  nop
0x1800658c4  lea     rcx, dword_1800AFE48
0x1800658cb  call    _Init_thread_footer
0x1800658d0  jmp     loc_180065613
0x1800658d5  call    ?_Xran@?$_String_val@U?$_Simple_types@D@std@@@std@@SAXXZ; std::_String_val<std::_Simple_types<char>>::_Xran(void)
```
