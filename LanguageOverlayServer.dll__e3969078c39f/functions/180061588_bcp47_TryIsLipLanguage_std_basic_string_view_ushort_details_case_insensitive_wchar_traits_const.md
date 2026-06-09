# bcp47::TryIsLipLanguage(std::basic_string_view<ushort,details::case_insensitive_wchar_traits> const &)

- ea: `0x180061588`
- end: `0x180061825`
- name: `?TryIsLipLanguage@bcp47@@YA?AU?$pair@_N_N@std@@AEBV?$basic_string_view@GUcase_insensitive_wchar_traits@details@@@3@@Z`
- size: `669`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180061d38`
- `0x18006253c`

## callees

- `0x180003a00`
- `0x1800040a0`
- `0x180011318`
- `0x180012a98`
- `0x180050dd4`
- `0x180061588`
- `0x180062d1c`
- `0x18006a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcslwr_s` at `0x180061733`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr_s` at `0x180061733`
- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x1800616e5`
- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x1800616e5`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18006174c`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18006174c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180061655`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180061655`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180061770`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180061770`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180061766`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180061766`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800615cf`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800615cf`

## string_xrefs

- `0x1800615c8`: `slc.dll`
- `0x1800617b1`: `onecore\base\languageoverlay\common\bcp47utils.cpp`
- `0x1800617c5`: `onecore\base\languageoverlay\common\bcp47utils.cpp`
- `0x1800617dc`: `onecore\base\languageoverlay\common\bcp47utils.cpp`
- `0x1800617f3`: `onecore\base\languageoverlay\common\bcp47utils.cpp`
- `0x18006180a`: `onecore\base\languageoverlay\common\bcp47utils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
bool *__fastcall bcp47::TryIsLipLanguage(bool *a1, __int64 *a2)
{
  HMODULE LibraryW; // rax
  HMODULE v5; // rbx
  __int64 v6; // rax
  __int64 v7; // rdx
  const char *v8; // r9
  bool *result; // rax
  FARPROC ProcAddress; // rax
  const char *v11; // r9
  int v12; // eax
  wchar_t *v13; // r14
  __int64 v14; // rdx
  wil::details::in1diag3 *v15; // rcx
  unsigned __int64 v16; // r15
  unsigned __int64 v17; // r15
  __int64 v18; // rdx
  int v19; // [rsp+20h] [rbp-198h]
  int v20; // [rsp+30h] [rbp-188h] BYREF
  int v21; // [rsp+34h] [rbp-184h] BYREF
  wchar_t *String; // [rsp+38h] [rbp-180h] BYREF
  wchar_t *v23; // [rsp+40h] [rbp-178h]
  bool *v24; // [rsp+48h] [rbp-170h]
  _QWORD v25[3]; // [rsp+58h] [rbp-160h] BYREF
  int v26[6]; // [rsp+70h] [rbp-148h] BYREF
  _BYTE v27[40]; // [rsp+88h] [rbp-130h] BYREF
  wchar_t SubStr[104]; // [rsp+B0h] [rbp-108h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+0h]

  v24 = a1;
  v20 = 0;
  v21 = 0;
  String = 0;
  LibraryW = LoadLibraryW(L"slc.dll");
  try
  {
    v5 = LibraryW;
    v25[2] = LibraryW;
    v23 = 0;
    if ( LibraryW )
    {
      ProcAddress = GetProcAddress(LibraryW, "SLGetWindowsInformation");
      if ( !ProcAddress )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0xC1,
          (unsigned int)"onecore\\base\\languageoverlay\\common\\bcp47utils.cpp",
          v11);
      v12 = ((__int64 (__fastcall *)(const wchar_t *, int *, int *, wchar_t **))ProcAddress)(
              L"Kernel-MUI-Language-SKU",
              &v20,
              &v21,
              &String);
      if ( v12 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xC7,
          (unsigned int)"onecore\\base\\languageoverlay\\common\\bcp47utils.cpp",
          (const char *)(unsigned int)v12,
          v19);
      v13 = String;
      v23 = String;
      if ( v20 != 1 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xCA,
          (unsigned int)"onecore\\base\\languageoverlay\\common\\bcp47utils.cpp",
          (const char *)0x8000FFFFLL,
          v19);
      v14 = a2[1];
      v15 = retaddr;
      if ( (unsigned __int64)(v14 + 1) > 0x64 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xCC,
          (unsigned int)"onecore\\base\\languageoverlay\\common\\bcp47utils.cpp",
          (const char *)0xD0000023LL,
          v19);
      v16 = 0;
      if ( v14 )
      {
        do
        {
          SubStr[v16] = _o_towlower(*(unsigned __int16 *)(*a2 + 2 * v16));
          ++v16;
        }
        while ( v16 < a2[1] );
      }
      v17 = v16;
      if ( v17 >= 100 )
        _report_rangecheckfailure(v15);
      SubStr[v17] = 0;
      v18 = -1;
      do
        ++v18;
      while ( v13[v18] );
      if ( _wcslwr_s(v13, v18 + 1) )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xD8,
          (unsigned int)"onecore\\base\\languageoverlay\\common\\bcp47utils.cpp",
          (const char *)0x8000FFFFLL,
          v19);
      *a1 = wcsstr(v13, SubStr) == 0;
      a1[1] = 1;
      if ( v13 )
        LocalFree(v13);
      FreeLibrary(v5);
      result = a1;
    }
    else
    {
      v6 = *a2;
      v25[0] = *a2;
      v7 = -1;
      do
        ++v7;
      while ( *(_WORD *)(v6 + 2 * v7) );
      v25[1] = v7;
      LanguageDetails::CreateInstanceForLanguage(v26, v25);
      if ( v27[32] )
      {
        *a1 = (v26[0] & 4) != 0;
        a1[1] = 1;
        std::vector<std::pair<std::basic_string_view<unsigned short,details::case_insensitive_wchar_traits>,std::basic_string_view<unsigned short,details::case_insensitive_wchar_traits>>>::~vector<std::pair<std::basic_string_view<unsigned short,details::case_insensitive_wchar_traits>,std::basic_string_view<unsigned short,details::case_insensitive_wchar_traits>>>(v27);
      }
      else
      {
        *(_WORD *)a1 = 0;
      }
      result = a1;
    }
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0xDD,
      (unsigned int)"onecore\\base\\languageoverlay\\common\\bcp47utils.cpp",
      v8);
    result = v24;
    *v24 = 0;
    result[1] = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180061588  mov     [rsp+arg_10], rbx
0x18006158d  push    rsi
0x18006158e  push    rdi
0x18006158f  push    r12
0x180061591  push    r14
0x180061593  push    r15
0x180061595  sub     rsp, 190h
0x18006159c  mov     rax, cs:__security_cookie
0x1800615a3  xor     rax, rsp
0x1800615a6  mov     [rsp+1B8h+var_38], rax
0x1800615ae  mov     r12, rdx
0x1800615b1  mov     rsi, rcx
0x1800615b4  mov     [rsp+1B8h+var_170], rcx
0x1800615b9  xor     edi, edi
0x1800615bb  mov     [rsp+1B8h+var_188], edi
0x1800615bf  mov     [rsp+1B8h+var_184], edi
0x1800615c3  mov     [rsp+1B8h+String], rdi
0x1800615c8  lea     rcx, aSlcDll; "slc.dll"
0x1800615cf  call    cs:__imp_LoadLibraryW
0x1800615d5  mov     rbx, rax
0x1800615d8  mov     [rsp+1B8h+var_150], rax
0x1800615dd  mov     [rsp+1B8h+var_178], rdi
0x1800615e2  test    rax, rax
0x1800615e5  jnz     short loc_18006164B
0x1800615e7  mov     rax, [r12]
0x1800615eb  mov     [rsp+1B8h+var_160], rax
0x1800615f0  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800615f4  inc     rdx
0x1800615f7  cmp     [rax+rdx*2], di
0x1800615fb  jnz     short loc_1800615F4
0x1800615fd  mov     [rsp+1B8h+var_158], rdx
0x180061602  lea     rdx, [rsp+1B8h+var_160]
0x180061607  lea     rcx, [rsp+1B8h+var_148]
0x18006160c  call    ?CreateInstanceForLanguage@LanguageDetails@@SA?AV?$optional@$$CBVLanguageDetails@@@std@@AEBV?$basic_string_view@GUcase_insensitive_wchar_traits@details@@@3@@Z; LanguageDetails::CreateInstanceForLanguage(std::basic_string_view<ushort,details::case_insensitive_wchar_traits> const &)
0x180061611  cmp     [rsp+1B8h+var_110], dil
0x180061619  jnz     short loc_180061626
0x18006161b  mov     [rsi], di
0x18006161e  mov     rax, rsi
0x180061621  jmp     loc_180061789
0x180061626  mov     eax, [rsp+1B8h+var_148]
0x18006162a  shr     eax, 2
0x18006162d  and     al, 1
0x18006162f  mov     [rsi], al
0x180061631  mov     byte ptr [rsi+1], 1
0x180061635  lea     rcx, [rsp+1B8h+var_130]
0x18006163d  call    ??1?$vector@U?$pair@V?$basic_string_view@GUcase_insensitive_wchar_traits@details@@@std@@V12@@std@@V?$allocator@U?$pair@V?$basic_string_view@GUcase_insensitive_wchar_traits@details@@@std@@V12@@std@@@2@@std@@QEAA@XZ; std::vector<std::pair<std::basic_string_view<ushort,details::case_insensitive_wchar_traits>,std::basic_string_view<ushort,details::case_insensitive_wchar_traits>>>::~vector<std::pair<std::basic_string_view<ushort,details::case_insensitive_wchar_traits>,std::basic_string_view<ushort,details::case_insensitive_wchar_traits>>>(void)
0x180061642  nop
0x180061643  mov     rax, rsi
0x180061646  jmp     loc_180061789
0x18006164b  lea     rdx, ?s_lookupTable@?1???$Base64Encode@$0IB@@TLV@@YAXPEBEIAEAY0IB@D@Z@4QBDB+40h; lpProcName
0x180061652  mov     rcx, rbx; hModule
0x180061655  call    cs:__imp_GetProcAddress
0x18006165b  mov     rcx, [rsp+1B8h]; this
0x180061663  test    rax, rax
0x180061666  jz      loc_1800617B1
0x18006166c  lea     r9, [rsp+1B8h+String]
0x180061671  lea     r8, [rsp+1B8h+var_184]
0x180061676  lea     rdx, [rsp+1B8h+var_188]
0x18006167b  lea     rcx, aKernelMuiLangu; "Kernel-MUI-Language-SKU"
0x180061682  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061687  mov     rcx, [rsp+1B8h]; this
0x18006168f  test    eax, eax
0x180061691  js      loc_1800617C2
0x180061697  mov     r14, [rsp+1B8h+String]
0x18006169c  mov     [rsp+1B8h+var_178], r14
0x1800616a1  cmp     [rsp+1B8h+var_188], 1
0x1800616a6  setnz   al
0x1800616a9  mov     rcx, [rsp+1B8h]; this
0x1800616b1  test    al, al
0x1800616b3  jnz     loc_1800617D6
0x1800616b9  mov     rdx, [r12+8]
0x1800616be  mov     rcx, [rsp+1B8h]; this
0x1800616c6  lea     rax, [rdx+1]
0x1800616ca  cmp     rax, 64h ; 'd'
0x1800616ce  ja      loc_1800617ED
0x1800616d4  mov     r15, rdi
0x1800616d7  test    rdx, rdx
0x1800616da  jz      short loc_1800616FE
0x1800616dc  mov     rcx, [r12]
0x1800616e0  movzx   ecx, word ptr [rcx+r15*2]
0x1800616e5  call    cs:__imp__o_towlower
0x1800616eb  mov     [rsp+r15*2+1B8h+SubStr], ax
0x1800616f4  inc     r15
0x1800616f7  cmp     r15, [r12+8]
0x1800616fc  jb      short loc_1800616DC
0x1800616fe  add     r15, r15
0x180061701  cmp     r15, 0C8h
0x180061708  jnb     loc_18006181E
0x18006170e  mov     [rsp+r15+1B8h+SubStr], di
0x180061717  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18006171b  inc     rdx
0x18006171e  cmp     [r14+rdx*2], di
0x180061723  jnz     short loc_18006171B
0x180061725  mov     r15, [rsp+1B8h]
0x18006172d  inc     rdx; SizeInWords
0x180061730  mov     rcx, r14; String
0x180061733  call    cs:__imp__wcslwr_s
0x180061739  test    eax, eax
0x18006173b  jnz     loc_180061804
0x180061741  lea     rdx, [rsp+1B8h+SubStr]; SubStr
0x180061749  mov     rcx, r14; Str
0x18006174c  call    cs:__imp_wcsstr
0x180061752  test    rax, rax
0x180061755  setz    al
0x180061758  mov     [rsi], al
0x18006175a  mov     byte ptr [rsi+1], 1
0x18006175e  test    r14, r14
0x180061761  jz      short loc_18006176D
0x180061763  mov     rcx, r14; hMem
0x180061766  call    cs:__imp_LocalFree
0x18006176c  nop
0x18006176d  mov     rcx, rbx; hLibModule
0x180061770  call    cs:__imp_FreeLibrary
0x180061776  mov     rax, rsi
0x180061779  jmp     short loc_180061789
0x18006177b  xor     edi, edi
0x18006177d  mov     rax, [rsp+1B8h+var_170]
0x180061782  mov     [rax], dil
0x180061785  mov     [rax+1], dil
0x180061789  mov     rcx, [rsp+1B8h+var_38]
0x180061791  xor     rcx, rsp; StackCookie
0x180061794  call    __security_check_cookie
0x180061799  mov     rbx, [rsp+1B8h+arg_10]
0x1800617a1  add     rsp, 190h
0x1800617a8  pop     r15
0x1800617aa  pop     r14
0x1800617ac  pop     r12
0x1800617ae  pop     rdi
0x1800617af  pop     rsi
0x1800617b0  retn
0x1800617b1  lea     r8, aOnecoreBaseLan_9; "onecore\\base\\languageoverlay\\common"...
0x1800617b8  mov     edx, 0C1h; void *
0x1800617bd  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800617c2  mov     r9d, eax; char *
0x1800617c5  lea     r8, aOnecoreBaseLan_9; "onecore\\base\\languageoverlay\\common"...
0x1800617cc  mov     edx, 0C7h; void *
0x1800617d1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800617d6  mov     r9d, 8000FFFFh; char *
0x1800617dc  lea     r8, aOnecoreBaseLan_9; "onecore\\base\\languageoverlay\\common"...
0x1800617e3  mov     edx, 0CAh; void *
0x1800617e8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800617ed  mov     r9d, 0D0000023h; char *
0x1800617f3  lea     r8, aOnecoreBaseLan_9; "onecore\\base\\languageoverlay\\common"...
0x1800617fa  mov     edx, 0CCh; void *
0x1800617ff  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180061804  mov     r9d, 8000FFFFh; char *
0x18006180a  lea     r8, aOnecoreBaseLan_9; "onecore\\base\\languageoverlay\\common"...
0x180061811  mov     edx, 0D8h; void *
0x180061816  mov     rcx, r15; this
0x180061819  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006181e  call    __report_rangecheckfailure
```
