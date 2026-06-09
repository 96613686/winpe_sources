# CreateIStreamFromFileName(wchar_t const *)

- ea: `0x180159ed0`
- end: `0x18015a24f`
- name: `?CreateIStreamFromFileName@@YAPEAUIStream@@PEB_W@Z`
- size: `895`
- prototype: `struct IStream *__fastcall(const wchar_t *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1801f4c20`

## callees

- `0x180038f08`
- `0x180063848`
- `0x1800740f4`
- `0x18009e510`
- `0x18009e614`
- `0x180147154`
- `0x180159ed0`
- `0x18015aa68`
- `0x180188d90`
- `0x180189280`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180159f23`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180159f23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015a074`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015a18b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015a074`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015a18b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18015a208`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18015a208`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18015a1d4`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18015a1d4`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18015a0f2`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18015a0f2`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180159f4e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180159f90`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180159f4e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180159f90`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18015a15b`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18015a15b`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18015a0d2`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x18015a0d2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18015a060`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18015a060`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18015a11f`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18015a11f`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18015a181`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18015a181`

## string_xrefs

- `0x18015a0a5`: `onecoreuap\base\appmodel\search\tquery\cicommon\istrmfil.cxx`
- `0x180159f61`: `onecoreuap\base\appmodel\search\tquery\cicommon\istrmfil.cxx`
- `0x180159fa3`: `onecoreuap\base\appmodel\search\tquery\cicommon\istrmfil.cxx`
- `0x18015a002`: `onecoreuap\base\appmodel\search\tquery\cicommon\istrmfil.cxx`
- `0x18015a0bb`: `onecoreuap\base\appmodel\search\tquery\cicommon\istrmfil.cxx`
- `0x18015a107`: `onecoreuap\base\appmodel\search\tquery\cicommon\istrmfil.cxx`
- `0x18015a131`: `onecoreuap\base\appmodel\search\tquery\cicommon\istrmfil.cxx`
- `0x18015a16c`: `onecoreuap\base\appmodel\search\tquery\cicommon\istrmfil.cxx`
- `0x18015a19c`: `onecoreuap\base\appmodel\search\tquery\cicommon\istrmfil.cxx`
- `0x18015a1b5`: `onecoreuap\base\appmodel\search\tquery\cicommon\istrmfil.cxx`
- `0x18015a1e8`: `onecoreuap\base\appmodel\search\tquery\cicommon\istrmfil.cxx`
- `0x18015a099`: `[Index] CreateFile(%ws) failed: hr = 0x%x\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
LPSTREAM __fastcall CreateIStreamFromFileName(const wchar_t *a1)
{
  __int64 v2; // rbx
  unsigned __int64 v3; // rdi
  UINT SystemDirectoryW; // eax
  const char *v5; // r9
  UINT v6; // edx
  unsigned __int64 v7; // rbx
  const char *v8; // r9
  LPWSTR v9; // r8
  int v10; // eax
  void *v11; // rsi
  HANDLE FileW; // rax
  void *v13; // rbx
  signed int LastError; // eax
  unsigned int v15; // edi
  DWORD FileSize; // eax
  const char *v17; // r9
  DWORD v18; // edi
  HGLOBAL v19; // rax
  const char *v20; // r9
  void *v21; // rax
  const char *v22; // r9
  const char *v23; // r9
  const char *v24; // r9
  HRESULT v25; // eax
  LPSTREAM v26; // rdi
  int dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  DWORD dwCreationDispositiona[2]; // [rsp+20h] [rbp-E0h]
  int dwCreationDispositionb; // [rsp+20h] [rbp-E0h]
  DWORD NumberOfBytesRead; // [rsp+40h] [rbp-C0h] BYREF
  LPSTREAM ppstm; // [rsp+48h] [rbp-B8h] BYREF
  HGLOBAL v33; // [rsp+50h] [rbp-B0h]
  int v34; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v35; // [rsp+60h] [rbp-A0h]
  HANDLE v36; // [rsp+68h] [rbp-98h]
  UINT uSize; // [rsp+70h] [rbp-90h] BYREF
  LPWSTR lpBuffer; // [rsp+78h] [rbp-88h]
  _BYTE v39[528]; // [rsp+80h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+1D8h]

  uSize = 260;
  lpBuffer = (LPWSTR)v39;
  XGrowable<wchar_t,260>::SetSize(&uSize, 260);
  if ( !wcschr(a1, 0x5Cu) )
  {
    v2 = -1;
    do
      ++v2;
    while ( a1[v2] );
    v3 = uSize;
    SystemDirectoryW = GetSystemDirectoryW(lpBuffer, uSize);
    v6 = SystemDirectoryW;
    if ( !SystemDirectoryW )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x2C,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\cicommon\\istrmfil.cxx",
        v5);
    v7 = SystemDirectoryW + 2LL + v2;
    if ( v7 > v3 )
    {
      XGrowable<wchar_t,260>::SetSize(&uSize, (unsigned int)v7);
      v6 = GetSystemDirectoryW(lpBuffer, v7);
      if ( !v6 )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x37,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\cicommon\\istrmfil.cxx",
          v8);
      v3 = v7;
    }
    v9 = lpBuffer;
    if ( lpBuffer[v6 - 1] != 92 )
    {
      lpBuffer[v6++] = 92;
      lpBuffer[v6] = 0;
      v9 = lpBuffer;
    }
    v9[v6] = 0;
    v10 = StringCchCatW(lpBuffer, v3, a1);
    if ( v10 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x46,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\cicommon\\istrmfil.cxx",
        (const char *)(unsigned int)v10,
        dwCreationDisposition);
    a1 = lpBuffer;
  }
  v34 = 0;
  v35 = -1;
  CImpersonateSystem::MakePrivileged((CImpersonateSystem *)&v34);
  v11 = 0;
  ppstm = 0;
  v33 = 0;
  FileW = CreateFileW(a1, 0x80000000, 1u, 0, 3u, 0, 0);
  v13 = FileW;
  v36 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v15 = LastError;
    if ( LastError != 2 )
    {
      if ( LastError > 0 )
        v15 = (unsigned __int16)LastError | 0x80070000;
      dwCreationDispositiona[0] = v15;
      SearchIndexerDebug::Error(
        (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\tquery\\cicommon\\istrmfil.cxx",
        (const wchar_t *)0x61,
        (unsigned int)L"[Index] CreateFile(%ws) failed: hr = 0x%x\n",
        a1,
        *(_QWORD *)dwCreationDispositiona);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x63,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\cicommon\\istrmfil.cxx",
        (const char *)v15,
        dwCreationDispositionb);
    }
  }
  else
  {
    FileSize = GetFileSize(FileW, 0);
    v18 = FileSize;
    if ( FileSize )
    {
      if ( FileSize == -1 )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x6F,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\cicommon\\istrmfil.cxx",
          v17);
      v19 = GlobalAlloc(0x22u, FileSize);
      v11 = v19;
      if ( !v19 )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x77,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\cicommon\\istrmfil.cxx",
          v20);
      v33 = v19;
      v21 = GlobalLock(v19);
      if ( !v21 )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x81,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\cicommon\\istrmfil.cxx",
          v22);
      NumberOfBytesRead = 0;
      if ( !ReadFile(v13, v21, v18, &NumberOfBytesRead, 0) )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x88,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\cicommon\\istrmfil.cxx",
          v23);
      if ( !GlobalUnlock(v11) && GetLastError() )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x8F,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\cicommon\\istrmfil.cxx",
          v24);
    }
  }
  v25 = CreateStreamOnHGlobal(v11, 1, &ppstm);
  if ( v25 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x9B,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\cicommon\\istrmfil.cxx",
      (const char *)(unsigned int)v25,
      dwCreationDispositiona[0]);
  v26 = ppstm;
  if ( v13 != (void *)-1LL )
    CloseHandle(v13);
  CImpersonateSystem::~CImpersonateSystem((CImpersonateSystem *)&v34);
  if ( lpBuffer != (LPWSTR)v39 )
    operator delete(lpBuffer);
  return v26;
}

```

## disassembly

```asm
0x180159ed0  push    rbp
0x180159ed2  push    rbx
0x180159ed3  push    rsi
0x180159ed4  push    rdi
0x180159ed5  push    r14
0x180159ed7  push    r15
0x180159ed9  lea     rbp, [rsp-1A8h]
0x180159ee1  sub     rsp, 2A8h
0x180159ee8  mov     rax, cs:__security_cookie
0x180159eef  xor     rax, rsp
0x180159ef2  mov     [rbp+1D0h+var_40], rax
0x180159ef9  mov     r14, rcx
0x180159efc  mov     edx, 104h
0x180159f01  mov     [rsp+2D0h+uSize], edx
0x180159f05  lea     rax, [rbp+1D0h+var_250]
0x180159f09  mov     [rsp+2D0h+lpBuffer], rax
0x180159f0e  lea     rcx, [rsp+2D0h+uSize]
0x180159f13  call    ?SetSize@?$XGrowable@_W$0BAE@@@QEAAPEA_WI@Z; XGrowable<wchar_t,260>::SetSize(uint)
0x180159f18  nop
0x180159f19  mov     esi, 5Ch ; '\'
0x180159f1e  mov     edx, esi; Ch
0x180159f20  mov     rcx, r14; Str
0x180159f23  call    cs:__imp_wcschr
0x180159f29  xor     r15d, r15d
0x180159f2c  test    rax, rax
0x180159f2f  jnz     loc_18015A019
0x180159f35  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180159f39  inc     rbx
0x180159f3c  cmp     [r14+rbx*2], r15w
0x180159f41  jnz     short loc_180159F39
0x180159f43  mov     edi, [rsp+2D0h+uSize]
0x180159f47  mov     edx, edi; uSize
0x180159f49  mov     rcx, [rsp+2D0h+lpBuffer]; lpBuffer
0x180159f4e  call    cs:__imp_GetSystemDirectoryW
0x180159f54  mov     edx, eax
0x180159f56  test    eax, eax
0x180159f58  jnz     short loc_180159F71
0x180159f5a  mov     rcx, [rbp+1D8h]; this
0x180159f61  lea     r8, aOnecoreuapBase_85; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x180159f68  lea     edx, [rax+2Ch]; void *
0x180159f6b  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180159f71  lea     rax, [rdx+2]
0x180159f75  add     rbx, rax
0x180159f78  cmp     rbx, rdi
0x180159f7b  jbe     short loc_180159FB6
0x180159f7d  mov     edx, ebx
0x180159f7f  lea     rcx, [rsp+2D0h+uSize]
0x180159f84  call    ?SetSize@?$XGrowable@_W$0BAE@@@QEAAPEA_WI@Z; XGrowable<wchar_t,260>::SetSize(uint)
0x180159f89  mov     edx, ebx; uSize
0x180159f8b  mov     rcx, [rsp+2D0h+lpBuffer]; lpBuffer
0x180159f90  call    cs:__imp_GetSystemDirectoryW
0x180159f96  mov     edx, eax
0x180159f98  test    eax, eax
0x180159f9a  jnz     short loc_180159FB3
0x180159f9c  mov     rcx, [rbp+1D8h]; this
0x180159fa3  lea     r8, aOnecoreuapBase_85; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x180159faa  lea     edx, [rax+37h]; void *
0x180159fad  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180159fb3  mov     rdi, rbx
0x180159fb6  lea     eax, [rdx-1]
0x180159fb9  mov     r8, [rsp+2D0h+lpBuffer]
0x180159fbe  cmp     [r8+rax*2], si
0x180159fc3  jz      short loc_180159FDD
0x180159fc5  mov     eax, edx
0x180159fc7  mov     [r8+rax*2], si
0x180159fcc  inc     edx
0x180159fce  mov     rax, [rsp+2D0h+lpBuffer]
0x180159fd3  mov     [rax+rdx*2], r15w
0x180159fd8  mov     r8, [rsp+2D0h+lpBuffer]
0x180159fdd  mov     ecx, edx
0x180159fdf  mov     [r8+rcx*2], r15w
0x180159fe4  mov     r8, r14; wchar_t *
0x180159fe7  mov     rdx, rdi; unsigned __int64
0x180159fea  mov     rcx, [rsp+2D0h+lpBuffer]; wchar_t *
0x180159fef  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180159ff4  test    eax, eax
0x180159ff6  jns     short loc_18015A014
0x180159ff8  mov     rcx, [rbp+1D8h]; this
0x180159fff  mov     r9d, eax; char *
0x18015a002  lea     r8, aOnecoreuapBase_85; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x18015a009  mov     edx, 46h ; 'F'; void *
0x18015a00e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18015a014  mov     r14, [rsp+2D0h+lpBuffer]
0x18015a019  mov     [rsp+2D0h+var_278], r15d
0x18015a01e  mov     [rsp+2D0h+var_270], 0FFFFFFFFFFFFFFFFh
0x18015a027  lea     rcx, [rsp+2D0h+var_278]; this
0x18015a02c  call    ?MakePrivileged@CImpersonateSystem@@AEAAXXZ; CImpersonateSystem::MakePrivileged(void)
0x18015a031  nop
0x18015a032  mov     rsi, r15
0x18015a035  mov     [rsp+2D0h+ppstm], r15
0x18015a03a  mov     [rsp+2D0h+var_280], r15
0x18015a03f  mov     [rsp+2D0h+hTemplateFile], r15; hTemplateFile
0x18015a044  mov     [rsp+2D0h+dwFlagsAndAttributes], r15d; dwFlagsAndAttributes
0x18015a049  mov     [rsp+2D0h+dwCreationDisposition], 3; int
0x18015a051  xor     r9d, r9d; lpSecurityAttributes
0x18015a054  mov     edx, 80000000h; dwDesiredAccess
0x18015a059  lea     r8d, [r9+1]; dwShareMode
0x18015a05d  mov     rcx, r14; lpFileName
0x18015a060  call    cs:__imp_CreateFileW
0x18015a066  mov     rbx, rax
0x18015a069  mov     [rsp+2D0h+var_268], rax
0x18015a06e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18015a072  jnz     short loc_18015A0CD
0x18015a074  call    cs:__imp_GetLastError
0x18015a07a  mov     edi, eax
0x18015a07c  cmp     eax, 2
0x18015a07f  jz      loc_18015A1C7
0x18015a085  test    eax, eax
0x18015a087  jle     short loc_18015A092
0x18015a089  movzx   edi, ax
0x18015a08c  or      edi, 80070000h
0x18015a092  mov     [rsp+2D0h+dwCreationDisposition], edi; int
0x18015a096  mov     r9, r14; wchar_t *
0x18015a099  lea     r8, aIndexCreatefil_0; "[Index] CreateFile(%ws) failed: hr = 0x"...
0x18015a0a0  mov     edx, 61h ; 'a'; wchar_t *
0x18015a0a5  lea     rcx, aOnecoreuapBase_195; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x18015a0ac  call    ?Error@SearchIndexerDebug@@YAXPEB_WI0ZZ; SearchIndexerDebug::Error(wchar_t const *,uint,wchar_t const *,...)
0x18015a0b1  mov     rcx, [rbp+1D8h]; this
0x18015a0b8  mov     r9d, edi; char *
0x18015a0bb  lea     r8, aOnecoreuapBase_85; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x18015a0c2  mov     edx, 63h ; 'c'; void *
0x18015a0c7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18015a0cd  xor     edx, edx; lpFileSizeHigh
0x18015a0cf  mov     rcx, rbx; hFile
0x18015a0d2  call    cs:__imp_GetFileSize
0x18015a0d8  mov     edi, eax
0x18015a0da  test    eax, eax
0x18015a0dc  jz      loc_18015A1C7
0x18015a0e2  cmp     edi, 0FFFFFFFFh
0x18015a0e5  jz      loc_18015A1AE
0x18015a0eb  mov     edx, edi; dwBytes
0x18015a0ed  mov     ecx, 22h ; '"'; uFlags
0x18015a0f2  call    cs:__imp_GlobalAlloc
0x18015a0f8  mov     rsi, rax
0x18015a0fb  test    rax, rax
0x18015a0fe  jnz     short loc_18015A117
0x18015a100  mov     rcx, [rbp+1D8h]; this
0x18015a107  lea     r8, aOnecoreuapBase_85; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x18015a10e  lea     edx, [rax+77h]; void *
0x18015a111  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18015a117  mov     [rsp+2D0h+var_280], rsi
0x18015a11c  mov     rcx, rsi; hMem
0x18015a11f  call    cs:__imp_GlobalLock
0x18015a125  test    rax, rax
0x18015a128  jnz     short loc_18015A143
0x18015a12a  mov     rcx, [rbp+1D8h]; this
0x18015a131  lea     r8, aOnecoreuapBase_85; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x18015a138  mov     edx, 81h; void *
0x18015a13d  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18015a143  mov     [rsp+2D0h+NumberOfBytesRead], r15d
0x18015a148  mov     qword ptr [rsp+2D0h+dwCreationDisposition], r15; lpOverlapped
0x18015a14d  lea     r9, [rsp+2D0h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18015a152  mov     r8d, edi; nNumberOfBytesToRead
0x18015a155  mov     rdx, rax; lpBuffer
0x18015a158  mov     rcx, rbx; hFile
0x18015a15b  call    cs:__imp_ReadFile
0x18015a161  test    eax, eax
0x18015a163  jnz     short loc_18015A17E
0x18015a165  mov     rcx, [rbp+1D8h]; this
0x18015a16c  lea     r8, aOnecoreuapBase_85; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x18015a173  mov     edx, 88h; void *
0x18015a178  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18015a17e  mov     rcx, rsi; hMem
0x18015a181  call    cs:__imp_GlobalUnlock
0x18015a187  test    eax, eax
0x18015a189  jnz     short loc_18015A1C7
0x18015a18b  call    cs:__imp_GetLastError
0x18015a191  test    eax, eax
0x18015a193  jz      short loc_18015A1C7
0x18015a195  mov     rcx, [rbp+1D8h]; this
0x18015a19c  lea     r8, aOnecoreuapBase_85; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x18015a1a3  mov     edx, 8Fh; void *
0x18015a1a8  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18015a1ae  mov     rcx, [rbp+1D8h]; this
0x18015a1b5  lea     r8, aOnecoreuapBase_85; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x18015a1bc  mov     edx, 6Fh ; 'o'; void *
0x18015a1c1  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18015a1c7  lea     r8, [rsp+2D0h+ppstm]; ppstm
0x18015a1cc  mov     edx, 1; fDeleteOnRelease
0x18015a1d1  mov     rcx, rsi; hGlobal
0x18015a1d4  call    cs:__imp_CreateStreamOnHGlobal
0x18015a1da  test    eax, eax
0x18015a1dc  jns     short loc_18015A1FA
0x18015a1de  mov     rcx, [rbp+1D8h]; this
0x18015a1e5  mov     r9d, eax; char *
0x18015a1e8  lea     r8, aOnecoreuapBase_85; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x18015a1ef  mov     edx, 9Bh; void *
0x18015a1f4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18015a1fa  mov     rdi, [rsp+2D0h+ppstm]
0x18015a1ff  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18015a203  jz      short loc_18015A20F
0x18015a205  mov     rcx, rbx; hObject
0x18015a208  call    cs:__imp_CloseHandle
0x18015a20e  nop
0x18015a20f  lea     rcx, [rsp+2D0h+var_278]; this
0x18015a214  call    ??1CImpersonateSystem@@QEAA@XZ; CImpersonateSystem::~CImpersonateSystem(void)
0x18015a219  nop
0x18015a21a  lea     rax, [rbp+1D0h+var_250]
0x18015a21e  mov     rcx, [rsp+2D0h+lpBuffer]; Block
0x18015a223  cmp     rcx, rax
0x18015a226  jz      short loc_18015A22D
0x18015a228  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18015a22d  mov     rax, rdi
0x18015a230  mov     rcx, [rbp+1D0h+var_40]
0x18015a237  xor     rcx, rsp; StackCookie
0x18015a23a  call    __security_check_cookie
0x18015a23f  add     rsp, 2A8h
0x18015a246  pop     r15
0x18015a248  pop     r14
0x18015a24a  pop     rdi
0x18015a24b  pop     rsi
0x18015a24c  pop     rbx
0x18015a24d  pop     rbp
0x18015a24e  retn
```
