# appv::shared::LoadSystemLibrary(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x140040b48`
- end: `0x140040d3d`
- name: `?LoadSystemLibrary@shared@appv@@YAPEAUHINSTANCE__@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `501`
- prototype: `__int64 __fastcall(LPCWCH lpWideCharStr)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14003efb4`

## callees

- `0x140004280`
- `0x1400060e8`
- `0x140006304`
- `0x14003eebc`
- `0x14004054c`
- `0x140040b48`
- `0x140040d44`
- `0x140040ee8`

## import_xrefs

- `KERNEL32!GetSystemDirectoryW` at `0x140040c7b`
- `KERNEL32!GetSystemDirectoryW` at `0x140040c7b`
- `KERNEL32!LoadLibraryW` at `0x140040ce1`
- `KERNEL32!LoadLibraryW` at `0x140040ce1`
- `KERNEL32!LoadLibraryA` at `0x140040d04`
- `KERNEL32!LoadLibraryA` at `0x140040d04`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x140040c50`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x140040c50`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x140040be2`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x140040be2`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
HMODULE __fastcall appv::shared::LoadSystemLibrary(_QWORD *lpWideCharStr)
{
  char v2; // r14
  __int128 *v3; // rdx
  LPCWCH v4; // rbx
  _QWORD *v5; // rcx
  char v6; // si
  const WCHAR *v7; // rcx
  const CHAR *v8; // rsi
  HMODULE LibraryA; // rbx
  unsigned __int64 v10; // r8
  __int64 v11; // rax
  __int128 v13; // [rsp+28h] [rbp-D8h] BYREF
  __int128 v14; // [rsp+38h] [rbp-C8h]
  char *v15[5]; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR Buffer[264]; // [rsp+70h] [rbp-90h] BYREF

  v2 = 0;
  if ( (int)(AppV::shared::OS::SWGetOS(lpWideCharStr) & 0xFFFF0000) < 0x800000 )
  {
    v4 = (LPCWCH)(lpWideCharStr + 3);
  }
  else
  {
    v13 = 0;
    v14 = 0;
    std::wstring::_Construct<1,wchar_t const *>((char **)&v13, L"API-MS-WIN", 0xAu);
    v2 = 1;
    v3 = &v13;
    if ( *((_QWORD *)&v14 + 1) > 7u )
      v3 = (__int128 *)v13;
    v4 = (LPCWCH)(lpWideCharStr + 3);
    if ( lpWideCharStr[3] <= 7u )
      v5 = lpWideCharStr;
    else
      v5 = (_QWORD *)*lpWideCharStr;
    if ( !(unsigned int)_o__wcsnicmp(v5, v3, v14) )
    {
      v6 = 1;
      goto LABEL_11;
    }
  }
  v6 = 0;
LABEL_11:
  if ( (v2 & 1) != 0 )
    std::wstring::~wstring((char **)&v13);
  if ( v6 )
  {
    v13 = 0;
    *(_QWORD *)&v14 = 0;
    if ( *(_QWORD *)v4 <= 7u )
      v7 = (const WCHAR *)lpWideCharStr;
    else
      v7 = (const WCHAR *)*lpWideCharStr;
    v8 = (const CHAR *)softricity::shared::narrow(v7);
    LibraryA = 0;
    if ( v8 )
    {
      while ( (unsigned int)_o__stricmp(v8, (&API_SET_KNOWN_DLLS)[(_QWORD)LibraryA]) )
      {
        LibraryA = (HMODULE)((char *)LibraryA + 1);
        if ( (unsigned __int64)LibraryA >= 6 )
        {
          std::vector<char>::~vector<char>(&v13);
          goto LABEL_21;
        }
      }
      LibraryA = LoadLibraryA(v8);
    }
    std::vector<char>::~vector<char>(&v13);
    return LibraryA;
  }
LABEL_21:
  if ( GetSystemDirectoryW(Buffer, 0x104u) - 1 <= 0x103 )
  {
    v13 = 0;
    v14 = 0;
    v10 = -1;
    do
      ++v10;
    while ( Buffer[v10] );
    std::wstring::_Construct<1,wchar_t const *>((char **)&v13, Buffer, v10);
    v11 = AppV::Shared::FileUtils::path_combine(v15, &v13, lpWideCharStr);
    if ( *(_QWORD *)(v11 + 24) > 7u )
      v11 = *(_QWORD *)v11;
    LibraryA = LoadLibraryW((LPCWSTR)v11);
    std::wstring::~wstring(v15);
    std::wstring::~wstring((char **)&v13);
    return LibraryA;
  }
  return 0;
}

```

## disassembly

```asm
0x140040b48  push    rbp
0x140040b4a  push    rbx
0x140040b4b  push    rsi
0x140040b4c  push    rdi
0x140040b4d  push    r14
0x140040b4f  push    r15
0x140040b51  lea     rbp, [rsp-198h]
0x140040b59  sub     rsp, 298h
0x140040b60  mov     rax, cs:__security_cookie
0x140040b67  xor     rax, rsp
0x140040b6a  mov     [rbp+1C0h+var_40], rax
0x140040b71  mov     rdi, rcx
0x140040b74  xor     r15d, r15d
0x140040b77  mov     r14d, r15d
0x140040b7a  mov     [rsp+2C0h+var_2A0], r15d
0x140040b7f  call    ?SWGetOS@OS@shared@AppV@@YA?BW4AppVOS@123@XZ; AppV::shared::OS::SWGetOS(void)
0x140040b84  and     eax, 0FFFF0000h
0x140040b89  cmp     eax, 800000h
0x140040b8e  jl      short loc_140040BF1
0x140040b90  xorps   xmm0, xmm0
0x140040b93  movups  [rsp+2C0h+var_298], xmm0
0x140040b98  xorps   xmm1, xmm1
0x140040b9b  movdqu  [rsp+2C0h+var_288], xmm1
0x140040ba1  lea     r8d, [r15+0Ah]
0x140040ba5  lea     rdx, aApiMsWin; "API-MS-WIN"
0x140040bac  lea     rcx, [rsp+2C0h+var_298]
0x140040bb1  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140040bb6  lea     r14d, [r15+1]
0x140040bba  lea     rdx, [rsp+2C0h+var_298]
0x140040bbf  cmp     qword ptr [rsp+2C0h+var_288+8], 7
0x140040bc5  cmova   rdx, qword ptr [rsp+2C0h+var_298]
0x140040bcb  lea     rbx, [rdi+18h]
0x140040bcf  cmp     qword ptr [rbx], 7
0x140040bd3  jbe     short loc_140040BDA
0x140040bd5  mov     rcx, [rdi]
0x140040bd8  jmp     short loc_140040BDD
0x140040bda  mov     rcx, rdi
0x140040bdd  mov     r8, qword ptr [rsp+2C0h+var_288]
0x140040be2  call    cs:__imp__o__wcsnicmp
0x140040be8  test    eax, eax
0x140040bea  jnz     short loc_140040BF5
0x140040bec  mov     sil, r14b
0x140040bef  jmp     short loc_140040BF8
0x140040bf1  lea     rbx, [rdi+18h]
0x140040bf5  mov     sil, r15b
0x140040bf8  test    r14b, 1
0x140040bfc  jz      short loc_140040C08
0x140040bfe  lea     rcx, [rsp+2C0h+var_298]
0x140040c03  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140040c08  test    sil, sil
0x140040c0b  jz      short loc_140040C71
0x140040c0d  xorps   xmm0, xmm0
0x140040c10  movdqu  [rsp+2C0h+var_298], xmm0
0x140040c16  mov     qword ptr [rsp+2C0h+var_288], r15
0x140040c1b  cmp     qword ptr [rbx], 7
0x140040c1f  jbe     short loc_140040C26
0x140040c21  mov     rcx, [rdi]
0x140040c24  jmp     short loc_140040C29
0x140040c26  mov     rcx, rdi; lpWideCharStr
0x140040c29  lea     rdx, [rsp+2C0h+var_298]
0x140040c2e  call    ?narrow@shared@softricity@@YAPEBDPEB_WAEAV?$vector@DV?$allocator@D@std@@@std@@I@Z; softricity::shared::narrow(wchar_t const *,std::vector<char> &,uint)
0x140040c33  mov     rsi, rax
0x140040c36  mov     rbx, r15
0x140040c39  test    rax, rax
0x140040c3c  jz      loc_140040D0D
0x140040c42  lea     rdx, ?API_SET_KNOWN_DLLS@@3PAPEBDA; char const * near * API_SET_KNOWN_DLLS
0x140040c49  mov     rdx, [rdx+rbx*8]
0x140040c4d  mov     rcx, rsi
0x140040c50  call    cs:__imp__o__stricmp
0x140040c56  test    eax, eax
0x140040c58  jz      loc_140040D01
0x140040c5e  inc     rbx
0x140040c61  cmp     rbx, 6
0x140040c65  jb      short loc_140040C42
0x140040c67  lea     rcx, [rsp+2C0h+var_298]
0x140040c6c  call    ??1?$vector@DV?$allocator@D@std@@@std@@QEAA@XZ; std::vector<char>::~vector<char>(void)
0x140040c71  mov     edx, 104h; uSize
0x140040c76  lea     rcx, [rsp+2C0h+Buffer]; lpBuffer
0x140040c7b  call    cs:__imp_GetSystemDirectoryW
0x140040c81  dec     eax
0x140040c83  cmp     eax, 103h
0x140040c88  ja      loc_140040D1C
0x140040c8e  xorps   xmm0, xmm0
0x140040c91  movups  [rsp+2C0h+var_298], xmm0
0x140040c96  xorps   xmm1, xmm1
0x140040c99  movdqu  [rsp+2C0h+var_288], xmm1
0x140040c9f  lea     rax, [rsp+2C0h+Buffer]
0x140040ca4  or      r8, 0FFFFFFFFFFFFFFFFh
0x140040ca8  inc     r8
0x140040cab  cmp     [rax+r8*2], r15w
0x140040cb0  jnz     short loc_140040CA8
0x140040cb2  lea     rdx, [rsp+2C0h+Buffer]
0x140040cb7  lea     rcx, [rsp+2C0h+var_298]
0x140040cbc  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140040cc1  nop
0x140040cc2  mov     r8, rdi
0x140040cc5  lea     rdx, [rsp+2C0h+var_298]
0x140040cca  lea     rcx, [rsp+2C0h+var_278]
0x140040ccf  call    ?path_combine@FileUtils@Shared@AppV@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV45@0@Z; AppV::Shared::FileUtils::path_combine(std::wstring const &,std::wstring const &)
0x140040cd4  cmp     qword ptr [rax+18h], 7
0x140040cd9  jbe     short loc_140040CDE
0x140040cdb  mov     rax, [rax]
0x140040cde  mov     rcx, rax; lpLibFileName
0x140040ce1  call    cs:__imp_LoadLibraryW
0x140040ce7  mov     rbx, rax
0x140040cea  lea     rcx, [rsp+2C0h+var_278]
0x140040cef  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140040cf4  nop
0x140040cf5  lea     rcx, [rsp+2C0h+var_298]
0x140040cfa  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140040cff  jmp     short loc_140040D17
0x140040d01  mov     rcx, rsi; lpLibFileName
0x140040d04  call    cs:__imp_LoadLibraryA
0x140040d0a  mov     rbx, rax
0x140040d0d  lea     rcx, [rsp+2C0h+var_298]
0x140040d12  call    ??1?$vector@DV?$allocator@D@std@@@std@@QEAA@XZ; std::vector<char>::~vector<char>(void)
0x140040d17  mov     rax, rbx
0x140040d1a  jmp     short loc_140040D1E
0x140040d1c  xor     eax, eax
0x140040d1e  mov     rcx, [rbp+1C0h+var_40]
0x140040d25  xor     rcx, rsp; StackCookie
0x140040d28  call    __security_check_cookie
0x140040d2d  add     rsp, 298h
0x140040d34  pop     r15
0x140040d36  pop     r14
0x140040d38  pop     rdi
0x140040d39  pop     rsi
0x140040d3a  pop     rbx
0x140040d3b  pop     rbp
0x140040d3c  retn
```
