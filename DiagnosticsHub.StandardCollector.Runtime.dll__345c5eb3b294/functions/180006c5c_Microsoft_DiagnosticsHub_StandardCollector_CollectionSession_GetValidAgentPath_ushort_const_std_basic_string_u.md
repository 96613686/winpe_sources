# Microsoft::DiagnosticsHub::StandardCollector::CollectionSession::GetValidAgentPath(ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180006c5c`
- end: `0x18000704d`
- name: `?GetValidAgentPath@CollectionSession@StandardCollector@DiagnosticsHub@Microsoft@@AEAA_NPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `1009`
- prototype: `char __fastcall(__int64, _WORD *, void **)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, reparse_path, service_task, broker_com_uri`

## callers

- `0x180006544`

## callees

- `0x180006b54`
- `0x180006c5c`
- `0x180008914`
- `0x1800089a8`
- `0x180008f38`
- `0x180009d1c`
- `0x180009fa4`
- `0x18000a078`
- `0x18000a17c`
- `0x18003d864`
- `0x180040d8c`
- `0x180049b50`

## import_xrefs

- `VCRUNTIME140!memmove` at `0x180006fe9`
- `VCRUNTIME140!memmove` at `0x180006fe9`
- `VCRUNTIME140!wcsrchr` at `0x180006d69`
- `VCRUNTIME140!wcsrchr` at `0x180006d69`
- `KERNEL32!GetSystemDirectoryW` at `0x180006eed`
- `KERNEL32!GetSystemDirectoryW` at `0x180006eed`
- `KERNEL32!GetFileAttributesW` at `0x180006e6a`
- `KERNEL32!GetFileAttributesW` at `0x180006ec3`
- `KERNEL32!GetFileAttributesW` at `0x180006f72`
- `KERNEL32!GetFileAttributesW` at `0x180006e6a`
- `KERNEL32!GetFileAttributesW` at `0x180006ec3`
- `KERNEL32!GetFileAttributesW` at `0x180006f72`
- `KERNEL32!GetLastError` at `0x180006ef7`
- `KERNEL32!GetLastError` at `0x180006ef7`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x180006e03`
- `api-ms-win-crt-string-l1-1-0!wcslen` at `0x180006e03`

## string_xrefs

- `0x180006d91`: `Potentially invalid agent name supplied [%s]`
- `0x180006dd7`: `Failed to get module path (HRESULT %#08x)`
- `0x180006e3b`: `Agents\`
- `0x180006f0e`: `GetSystemDirectory() failed [%#08x]`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall Microsoft::DiagnosticsHub::StandardCollector::CollectionSession::GetValidAgentPath(
        __int64 a1,
        _WORD *a2,
        void **a3)
{
  _WORD *v5; // r8
  char v6; // bl
  __int64 v7; // rdx
  unsigned __int64 i; // rcx
  __int64 v9; // rdx
  __int64 v10; // rcx
  void *v11; // rax
  int ModulePath; // eax
  wchar_t *v13; // rax
  const wchar_t *v14; // r14
  size_t v16; // rax
  const WCHAR *v17; // rcx
  DWORD FileAttributesW; // eax
  WCHAR *p_Src; // rdx
  LPCWSTR *v20; // rcx
  const WCHAR *v21; // rcx
  UINT SystemDirectoryW; // eax
  DWORD LastError; // eax
  __int64 v24; // rax
  const WCHAR *v25; // rcx
  __int64 v26; // r8
  LPCWSTR *v27; // r9
  unsigned __int64 v28; // rax
  unsigned __int64 v29; // r14
  void *v30; // rsi
  void *v31; // r8
  LPCWSTR lpFileName[2]; // [rsp+20h] [rbp-E0h] BYREF
  void *v33; // [rsp+30h] [rbp-D0h]
  unsigned __int64 v34; // [rsp+38h] [rbp-C8h]
  __int128 Src; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v36; // [rsp+50h] [rbp-B0h]
  wchar_t *Str[2]; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t *String[2]; // [rsp+70h] [rbp-90h]
  wchar_t *v39; // [rsp+80h] [rbp-80h]
  WCHAR Buffer[264]; // [rsp+90h] [rbp-70h] BYREF

  std::wstring::operator=(a3, (void *)&word_180055D48);
  v5 = a2;
  v6 = 0;
  if ( !*a2 )
  {
LABEL_15:
    *(_OWORD *)Str = 0;
    *(_OWORD *)String = 0;
    v39 = 0;
    ModulePath = DiagHubCommon::ModulePath::GetModulePath((HMODULE)0x180000000LL);
    if ( ModulePath < 0
      || ((v13 = wcsrchr(Str[0], 0x5Cu)) != 0
        ? (const wchar_t *)(*v13 = 0, v14 = Str[0], String[1] = Str[0], v39 = v13 + 1, ModulePath = 0)
        : (ModulePath = -2147024735, v14 = String[1]),
          ModulePath) )
    {
      DiagHubCommon::LogStream::Write(
        (DiagHubCommon::LogStream *)((char *)_logger + 168),
        L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\CollectionSessions.cpp",
        L"Failed to get module path (HRESULT %#08x)",
        (unsigned int)ModulePath);
LABEL_58:
      std::vector<unsigned short>::~vector<unsigned short>(Str);
      return v6;
    }
    Src = 0;
    v36 = 0;
    v16 = wcslen(v14);
    std::wstring::_Construct<1,unsigned short const *>(&Src, v14, v16);
    std::wstring::append(&Src, L"\\");
    std::wstring::wstring(lpFileName, &Src);
    std::wstring::append(lpFileName, L"Agents\\");
    std::wstring::append(lpFileName, a2);
    v17 = (const WCHAR *)lpFileName;
    if ( v34 > 7 )
      v17 = lpFileName[0];
    FileAttributesW = GetFileAttributesW(v17);
    p_Src = (WCHAR *)&Src;
    v20 = lpFileName;
    if ( FileAttributesW == -1 )
    {
      if ( *((_QWORD *)&v36 + 1) > 7u )
        p_Src = (WCHAR *)Src;
      std::wstring::operator=(lpFileName, p_Src);
      std::wstring::append(lpFileName, a2);
      v21 = (const WCHAR *)lpFileName;
      if ( v34 > 7 )
        v21 = lpFileName[0];
      if ( GetFileAttributesW(v21) == -1 )
      {
        SystemDirectoryW = GetSystemDirectoryW(Buffer, 0x105u);
        if ( !SystemDirectoryW )
        {
          LastError = GetLastError();
          DiagHubCommon::LogStream::Write(
            (DiagHubCommon::LogStream *)((char *)_logger + 168),
            L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\CollectionSessions.cpp",
            L"GetSystemDirectory() failed [%#08x]",
            LastError);
LABEL_57:
          std::wstring::~wstring(lpFileName);
          std::wstring::~wstring(&Src);
          goto LABEL_58;
        }
        v24 = SystemDirectoryW - 1;
        if ( Buffer[v24] == 92 )
          Buffer[v24] = 0;
        std::wstring::operator=(lpFileName, Buffer);
        std::wstring::append(lpFileName, L"\\");
        std::wstring::append(lpFileName, a2);
        v25 = (const WCHAR *)lpFileName;
        if ( v34 > 7 )
          v25 = lpFileName[0];
        if ( GetFileAttributesW(v25) == -1 )
          goto LABEL_57;
        p_Src = Buffer;
      }
      else
      {
        p_Src = (WCHAR *)&Src;
        if ( *((_QWORD *)&v36 + 1) > 7u )
          p_Src = (WCHAR *)Src;
      }
      v20 = lpFileName;
    }
    else if ( *((_QWORD *)&v36 + 1) > 7u )
    {
      p_Src = (WCHAR *)Src;
    }
    if ( v34 > 7 )
      v20 = (LPCWSTR *)lpFileName[0];
    if ( (unsigned __int8)anonymous_namespace_::ValidateRootedAgentPath((unsigned __int64)v20, p_Src) )
    {
      if ( a3 != (void **)lpFileName )
      {
        v27 = lpFileName;
        if ( v34 > 7 )
          v27 = (LPCWSTR *)lpFileName[0];
        v28 = (unsigned __int64)a3[3];
        v29 = (unsigned __int64)v33;
        _mm_lfence();
        if ( v29 > v28 )
        {
          std::wstring::_Reallocate_for<_lambda_05cef1f6fdf474c9f3ed207deba0f73b_,unsigned short const *>(
            a3,
            v33,
            v26,
            v27);
        }
        else
        {
          v30 = a3;
          if ( v28 > 7 )
            v30 = *a3;
          v31 = v33;
          a3[2] = v33;
          memmove(v30, v27, 2LL * (_QWORD)v31);
          *((_WORD *)v30 + v29) = 0;
        }
      }
      v6 = 1;
    }
    goto LABEL_57;
  }
  while ( 1 )
  {
    v7 = 0xCBF29CE484222325uLL;
    for ( i = 0; i < 2; ++i )
      v7 = 0x100000001B3LL * (*((unsigned __int8 *)v5 + i) ^ (unsigned __int64)v7);
    v9 = 2 * (qword_180077120 & v7);
    v10 = *(_QWORD *)(qword_180077108 + 8 * v9 + 8);
    if ( (void *)v10 == qword_1800770F8 )
    {
LABEL_10:
      v10 = 0;
    }
    else
    {
      while ( *v5 != *(_WORD *)(v10 + 16) )
      {
        if ( v10 == *(_QWORD *)(qword_180077108 + 8 * v9) )
          goto LABEL_10;
        v10 = *(_QWORD *)(v10 + 8);
      }
    }
    v11 = qword_1800770F8;
    if ( v10 )
      v11 = (void *)v10;
    if ( v11 != qword_1800770F8 )
      break;
    if ( !*++v5 )
      goto LABEL_15;
  }
  DiagHubCommon::LogStream::Write(
    (DiagHubCommon::LogStream *)((char *)_logger + 168),
    L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\CollectionSessions.cpp",
    L"Potentially invalid agent name supplied [%s]",
    a2);
  return 0;
}

```

## disassembly

```asm
0x180006c5c  mov     [rsp-8+arg_0], rbx
0x180006c61  push    rbp
0x180006c62  push    rsi
0x180006c63  push    rdi
0x180006c64  push    r12
0x180006c66  push    r14
0x180006c68  lea     rbp, [rsp-1B0h]
0x180006c70  sub     rsp, 2B0h
0x180006c77  mov     rax, cs:__security_cookie
0x180006c7e  xor     rax, rsp
0x180006c81  mov     [rbp+1D0h+var_30], rax
0x180006c88  mov     rdi, r8
0x180006c8b  mov     rsi, rdx
0x180006c8e  lea     rdx, word_180055D48; Src
0x180006c95  mov     rcx, r8; void *
0x180006c98  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator=(ushort const * const)
0x180006c9d  mov     r8, rsi
0x180006ca0  xor     ebx, ebx
0x180006ca2  cmp     [rsi], bx
0x180006ca5  jz      loc_180006D30
0x180006cab  mov     r10, cs:qword_180077108
0x180006cb2  mov     r9, cs:qword_1800770F8
0x180006cb9  mov     rdx, 0CBF29CE484222325h
0x180006cc3  mov     rcx, rbx
0x180006cc6  movzx   eax, byte ptr [r8+rcx]
0x180006ccb  xor     rdx, rax
0x180006cce  mov     r11, 100000001B3h
0x180006cd8  imul    rdx, r11
0x180006cdc  inc     rcx
0x180006cdf  cmp     rcx, 2
0x180006ce3  jb      short loc_180006CC6
0x180006ce5  and     rdx, cs:qword_180077120
0x180006cec  add     rdx, rdx
0x180006cef  mov     rcx, [r10+rdx*8+8]
0x180006cf4  cmp     rcx, r9
0x180006cf7  jz      short loc_180006D14
0x180006cf9  mov     r11, [r10+rdx*8]
0x180006cfd  movzx   eax, word ptr [r8]
0x180006d01  jmp     short loc_180006D0C
0x180006d03  cmp     rcx, r11
0x180006d06  jz      short loc_180006D14
0x180006d08  mov     rcx, [rcx+8]
0x180006d0c  cmp     ax, [rcx+10h]
0x180006d10  jnz     short loc_180006D03
0x180006d12  jmp     short loc_180006D17
0x180006d14  mov     rcx, rbx
0x180006d17  mov     rax, r9
0x180006d1a  test    rcx, rcx
0x180006d1d  cmovnz  rax, rcx
0x180006d21  cmp     rax, r9
0x180006d24  jnz     short loc_180006D80
0x180006d26  add     r8, 2
0x180006d2a  cmp     [r8], bx
0x180006d2e  jnz     short loc_180006CB9
0x180006d30  xorps   xmm0, xmm0
0x180006d33  movdqu  xmmword ptr [rsp+2D0h+Str], xmm0
0x180006d39  xorps   xmm1, xmm1
0x180006d3c  movdqu  xmmword ptr [rsp+2D0h+String], xmm1
0x180006d42  mov     [rbp+1D0h+var_250], rbx
0x180006d46  lea     rdx, [rsp+2D0h+Str]
0x180006d4b  lea     rcx, cs:180000000h; hModule
0x180006d52  call    ?GetModulePath@ModulePath@DiagHubCommon@@SAJPEAUHINSTANCE__@@AEAV?$vector@GV?$allocator@G@std@@@std@@@Z; DiagHubCommon::ModulePath::GetModulePath(HINSTANCE__ *,std::vector<ushort> &)
0x180006d57  test    eax, eax
0x180006d59  js      short loc_180006DC6
0x180006d5b  mov     r12d, 5Ch ; '\'
0x180006d61  mov     edx, r12d; Ch
0x180006d64  mov     rcx, [rsp+2D0h+Str]; Str
0x180006d69  call    cs:__imp_wcsrchr
0x180006d6f  test    rax, rax
0x180006d72  jnz     short loc_180006DAB
0x180006d74  mov     eax, 800700A1h
0x180006d79  mov     r14, [rsp+2D0h+String+8]
0x180006d7e  jmp     short loc_180006DC2
0x180006d80  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x180006d87  add     rcx, 0A8h; this
0x180006d8e  mov     r9, rsi
0x180006d91  lea     r8, aPotentiallyInv; "Potentially invalid agent name supplied"...
0x180006d98  lea     rdx, aDAWork1SSource_9; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x180006d9f  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x180006da4  xor     al, al
0x180006da6  jmp     loc_180007027
0x180006dab  mov     [rax], bx
0x180006dae  mov     r14, [rsp+2D0h+Str]
0x180006db3  mov     [rsp+2D0h+String+8], r14
0x180006db8  add     rax, 2
0x180006dbc  mov     [rbp+1D0h+var_250], rax
0x180006dc0  mov     eax, ebx
0x180006dc2  test    eax, eax
0x180006dc4  jz      short loc_180006DEF
0x180006dc6  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x180006dcd  add     rcx, 0A8h; this
0x180006dd4  mov     r9d, eax
0x180006dd7  lea     r8, aFailedToGetMod; "Failed to get module path (HRESULT %#08"...
0x180006dde  lea     rdx, aDAWork1SSource_9; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x180006de5  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x180006dea  jmp     loc_18000701B
0x180006def  xorps   xmm0, xmm0
0x180006df2  movups  [rsp+2D0h+Src], xmm0
0x180006df7  xorps   xmm1, xmm1
0x180006dfa  movdqu  [rsp+2D0h+var_280], xmm1
0x180006e00  mov     rcx, r14; String
0x180006e03  call    cs:__imp_wcslen
0x180006e09  mov     r8, rax
0x180006e0c  mov     rdx, r14
0x180006e0f  lea     rcx, [rsp+2D0h+Src]
0x180006e14  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180006e19  nop
0x180006e1a  lea     rdx, asc_180055D1C; "\\"
0x180006e21  lea     rcx, [rsp+2D0h+Src]; Src
0x180006e26  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180006e2b  lea     rdx, [rsp+2D0h+Src]
0x180006e30  lea     rcx, [rsp+2D0h+lpFileName]
0x180006e35  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180006e3a  nop
0x180006e3b  lea     rdx, aAgents; "Agents\\"
0x180006e42  lea     rcx, [rsp+2D0h+lpFileName]; Src
0x180006e47  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180006e4c  mov     rdx, rsi; void *
0x180006e4f  lea     rcx, [rsp+2D0h+lpFileName]; Src
0x180006e54  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180006e59  lea     rcx, [rsp+2D0h+lpFileName]
0x180006e5e  cmp     [rsp+2D0h+var_298], 7
0x180006e64  cmova   rcx, [rsp+2D0h+lpFileName]; lpFileName
0x180006e6a  call    cs:__imp_GetFileAttributesW
0x180006e70  or      r14d, 0FFFFFFFFh
0x180006e74  lea     rdx, [rsp+2D0h+Src]
0x180006e79  lea     rcx, [rsp+2D0h+lpFileName]; void *
0x180006e7e  cmp     eax, r14d
0x180006e81  jz      short loc_180006E94
0x180006e83  cmp     qword ptr [rsp+2D0h+var_280+8], 7
0x180006e89  cmova   rdx, qword ptr [rsp+2D0h+Src]
0x180006e8f  jmp     loc_180006F8A
0x180006e94  cmp     qword ptr [rsp+2D0h+var_280+8], 7
0x180006e9a  cmova   rdx, qword ptr [rsp+2D0h+Src]; Src
0x180006ea0  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator=(ushort const * const)
0x180006ea5  mov     rdx, rsi; void *
0x180006ea8  lea     rcx, [rsp+2D0h+lpFileName]; Src
0x180006ead  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180006eb2  lea     rcx, [rsp+2D0h+lpFileName]
0x180006eb7  cmp     [rsp+2D0h+var_298], 7
0x180006ebd  cmova   rcx, [rsp+2D0h+lpFileName]; lpFileName
0x180006ec3  call    cs:__imp_GetFileAttributesW
0x180006ec9  cmp     eax, r14d
0x180006ecc  jz      short loc_180006EE4
0x180006ece  lea     rdx, [rsp+2D0h+Src]
0x180006ed3  cmp     qword ptr [rsp+2D0h+var_280+8], 7
0x180006ed9  cmova   rdx, qword ptr [rsp+2D0h+Src]
0x180006edf  jmp     loc_180006F85
0x180006ee4  mov     edx, 105h; uSize
0x180006ee9  lea     rcx, [rbp+1D0h+Buffer]; lpBuffer
0x180006eed  call    cs:__imp_GetSystemDirectoryW
0x180006ef3  test    eax, eax
0x180006ef5  jnz     short loc_180006F26
0x180006ef7  call    cs:__imp_GetLastError
0x180006efd  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x180006f04  add     rcx, 0A8h; this
0x180006f0b  mov     r9d, eax
0x180006f0e  lea     r8, aGetsystemdirec; "GetSystemDirectory() failed [%#08x]"
0x180006f15  lea     rdx, aDAWork1SSource_9; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x180006f1c  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x180006f21  jmp     loc_180007005
0x180006f26  dec     eax
0x180006f28  cmp     [rbp+rax*2+1D0h+Buffer], r12w
0x180006f2e  jnz     short loc_180006F35
0x180006f30  mov     [rbp+rax*2+1D0h+Buffer], bx
0x180006f35  lea     rdx, [rbp+1D0h+Buffer]; Src
0x180006f39  lea     rcx, [rsp+2D0h+lpFileName]; void *
0x180006f3e  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator=(ushort const * const)
0x180006f43  lea     rdx, asc_180055D1C; "\\"
0x180006f4a  lea     rcx, [rsp+2D0h+lpFileName]; Src
0x180006f4f  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180006f54  mov     rdx, rsi; void *
0x180006f57  lea     rcx, [rsp+2D0h+lpFileName]; Src
0x180006f5c  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180006f61  lea     rcx, [rsp+2D0h+lpFileName]
0x180006f66  cmp     [rsp+2D0h+var_298], 7
0x180006f6c  cmova   rcx, [rsp+2D0h+lpFileName]; lpFileName
0x180006f72  call    cs:__imp_GetFileAttributesW
0x180006f78  cmp     eax, r14d
0x180006f7b  jz      loc_180007005
0x180006f81  lea     rdx, [rbp+1D0h+Buffer]; lpStringValue
0x180006f85  lea     rcx, [rsp+2D0h+lpFileName]
0x180006f8a  cmp     [rsp+2D0h+var_298], 7
0x180006f90  cmova   rcx, [rsp+2D0h+lpFileName]; unsigned __int64
0x180006f96  call    _anonymous_namespace___ValidateRootedAgentPath
0x180006f9b  test    al, al
0x180006f9d  jz      short loc_180007005
0x180006f9f  lea     rax, [rsp+2D0h+lpFileName]
0x180006fa4  cmp     rdi, rax
0x180006fa7  jz      short loc_180007003
0x180006fa9  lea     r9, [rsp+2D0h+lpFileName]
0x180006fae  cmp     [rsp+2D0h+var_298], 7
0x180006fb4  cmova   r9, [rsp+2D0h+lpFileName]
0x180006fba  mov     rax, [rdi+18h]
0x180006fbe  mov     r14, [rsp+2D0h+var_2A0]
0x180006fc3  lfence
0x180006fc6  cmp     r14, rax
0x180006fc9  ja      short loc_180006FF6
0x180006fcb  mov     rsi, rdi
0x180006fce  cmp     rax, 7
0x180006fd2  jbe     short loc_180006FD7
0x180006fd4  mov     rsi, [rdi]
0x180006fd7  mov     r8, [rsp+2D0h+var_2A0]
0x180006fdc  mov     [rdi+10h], r8
0x180006fe0  add     r8, r8; Size
0x180006fe3  mov     rdx, r9; Src
0x180006fe6  mov     rcx, rsi; void *
0x180006fe9  call    cs:__imp_memmove
0x180006fef  mov     [rsi+r14*2], bx
0x180006ff4  jmp     short loc_180007003
0x180006ff6  mov     rdx, [rsp+2D0h+var_2A0]
0x180006ffb  mov     rcx, rdi
0x180006ffe  call    ??$_Reallocate_for@V_lambda_05cef1f6fdf474c9f3ed207deba0f73b_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_05cef1f6fdf474c9f3ed207deba0f73b_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_05cef1f6fdf474c9f3ed207deba0f73b_,ushort const *>(unsigned __int64,_lambda_05cef1f6fdf474c9f3ed207deba0f73b_,ushort const *)
0x180007003  mov     bl, 1
0x180007005  lea     rcx, [rsp+2D0h+lpFileName]
0x18000700a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000700f  nop
0x180007010  lea     rcx, [rsp+2D0h+Src]
0x180007015  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000701a  nop
0x18000701b  lea     rcx, [rsp+2D0h+Str]
0x180007020  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x180007025  mov     al, bl
0x180007027  mov     rcx, [rbp+1D0h+var_30]
0x18000702e  xor     rcx, rsp; StackCookie
0x180007031  call    __security_check_cookie
0x180007036  mov     rbx, [rsp+2D0h+arg_0]
0x18000703e  add     rsp, 2B0h
0x180007045  pop     r14
0x180007047  pop     r12
0x180007049  pop     rdi
0x18000704a  pop     rsi
0x18000704b  pop     rbp
0x18000704c  retn
```
