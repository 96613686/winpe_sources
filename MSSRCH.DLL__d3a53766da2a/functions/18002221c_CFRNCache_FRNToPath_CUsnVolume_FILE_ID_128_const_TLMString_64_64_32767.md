# CFRNCache::_FRNToPath(CUsnVolume *,_FILE_ID_128 const &,TLMString<64,64,32767> &)

- ea: `0x18002221c`
- end: `0x1800225dc`
- name: `?_FRNToPath@CFRNCache@@AEAAJPEAVCUsnVolume@@AEBU_FILE_ID_128@@AEAV?$TLMString@$0EA@$0EA@$0HPPP@@@@Z`
- size: `960`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `file_ops`

## callers

- `0x180018234`
- `0x180019c3c`

## callees

- `0x180012120`
- `0x1800121a8`
- `0x1800178f0`
- `0x18002221c`
- `0x1800225e4`
- `0x180022688`
- `0x180022710`
- `0x180022b10`
- `0x18006028c`
- `0x1800bd084`
- `0x1801244c0`
- `0x1801249b0`
- `0x180241010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022530`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022530`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800225d1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800225d1`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x18002230b`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x18002230b`
- `api-ms-win-core-file-l2-1-1!OpenFileById` at `0x1800222bc`
- `api-ms-win-core-file-l2-1-1!OpenFileById` at `0x1800222bc`

## string_xrefs

- `0x180022425`: `"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\usnmonnotifier\\frncache.cxx"`
- `0x1800224f1`: `"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\usnmonnotifier\\frncache.cxx"`
- `0x18002258b`: `"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\usnmonnotifier\\frncache.cxx"`
- `0x180022419`: `[SrchGatherDirMon] FRN resolved by NTFS, FRN=%s, path=%ws`
- `0x1800224e5`: `[SrchGatherDirMon] CUsnMonitorNotifier::ResolveFrnByNtfs - Unable to open file by FRN %s`
- `0x18002257f`: `[SrchGatherDirMon] CUsnMonitorNotifier::ResolveFrnByNtfs - Unable to resolve file handle to path, frn=%s`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CFRNCache::_FRNToPath(
        __int64 a1,
        __int64 a2,
        union FILE_ID_DESCRIPTOR::$937871D590D7CF78B637FB7A33219D36 *a3,
        unsigned int *a4)
{
  void *v7; // rbx
  __int64 v8; // rsi
  char *v9; // r13
  signed int Error; // ebx
  DWORD v11; // eax
  _DWORD *v12; // rdi
  __int64 v13; // r9
  unsigned int v14; // r8d
  unsigned __int64 v15; // rax
  __int64 v16; // rdi
  const wchar_t *v17; // r9
  __int64 v19; // r8
  const wchar_t *v20; // r9
  signed int LastError; // edi
  __int64 v22; // rax
  FILE_ID_DESCRIPTOR FileId; // [rsp+38h] [rbp-C8h] BYREF
  wchar_t *v24[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v25; // [rsp+60h] [rbp-A0h]
  unsigned __int64 v26; // [rsp+68h] [rbp-98h]
  _BYTE v27[32]; // [rsp+70h] [rbp-90h] BYREF
  DWORD dwBufferSize; // [rsp+90h] [rbp-70h] BYREF
  void *Block; // [rsp+98h] [rbp-68h]
  _BYTE FileInformation[272]; // [rsp+A0h] [rbp-60h] BYREF
  wchar_t v31[40]; // [rsp+1B0h] [rbp+B0h] BYREF

  v7 = *(void **)(a2 + 280);
  v8 = -1;
  if ( v7 == (void *)-1LL )
    return 2147942406LL;
  (*(void (__fastcall **)(unsigned int *, const size_t *, _QWORD, __int64))(*(_QWORD *)a4 + 32LL))(
    a4,
    &cchOriginalDestLength,
    0,
    0xFFFFFFFFLL);
  FileId.Type = ExtendedFileIdType;
  FileId.8 = *a3;
  FileId.dwSize = 24;
  v9 = (char *)OpenFileById(v7, &FileId, 0x80u, 7u, 0, 0);
  if ( (unsigned __int64)(v9 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    Error = 0;
LABEL_4:
    v11 = 260;
    dwBufferSize = 260;
    v12 = FileInformation;
    Block = FileInformation;
    while ( 1 )
    {
      *v12 = v11 - 8;
      if ( GetFileInformationByHandleEx(v9, FileNameInfo, v12, dwBufferSize) )
      {
        v13 = *(unsigned int *)(a2 + 232);
        if ( (_DWORD)v13 && (unsigned int)IsSlash(*(_WORD *)(*(_QWORD *)(a2 + 224) + 2LL * (unsigned int)(v13 - 1))) )
          v13 = v14;
        (*(void (__fastcall **)(unsigned int *, _QWORD, _QWORD, __int64))(*(_QWORD *)a4 + 32LL))(
          a4,
          *(_QWORD *)(a2 + 224),
          a4[5],
          v13);
        LODWORD(v24[0]) = 5;
        *(wchar_t **)((char *)v24 + 4) = (wchar_t *)327680;
        HIDWORD(v24[1]) = 0;
        v15 = a3->FileId.QuadPart - (unsigned __int64)v24[0];
        if ( (wchar_t *)a3->FileId.QuadPart == v24[0] )
          v15 = *(_QWORD *)a3->ObjectId.Data4 - (unsigned __int64)v24[1];
        if ( v15 )
          (*(void (__fastcall **)(unsigned int *, _DWORD *, _QWORD, _QWORD))(*(_QWORD *)a4 + 32LL))(
            a4,
            v12 + 1,
            a4[5],
            *v12 >> 1);
        goto LABEL_13;
      }
      LastError = GetLastError();
      if ( LastError != 234 )
        break;
      XGrowable<unsigned char,260>::SetSize(&dwBufferSize, 2 * dwBufferSize);
      v12 = Block;
      v11 = dwBufferSize;
    }
    *(union FILE_ID_DESCRIPTOR::$937871D590D7CF78B637FB7A33219D36 *)v24 = *a3;
    v22 = to_wstring(v27, v24);
    if ( *(_QWORD *)(v22 + 24) > 7u )
      v22 = *(_QWORD *)v22;
    SearchIndexerTrace::Information(
      (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\mssrch\\\\gather\\\\usnmonnotifier\\\\frncache.cxx\"",
      (const wchar_t *)0x8A,
      (unsigned int)L"[SrchGatherDirMon] CUsnMonitorNotifier::ResolveFrnByNtfs - Unable to resolve file handle to path, frn=%s",
      (const wchar_t *)v22);
    ReIndexPatternInfo::~ReIndexPatternInfo((ReIndexPatternInfo *)v27);
    if ( LastError > 0 )
      Error = (unsigned __int16)LastError | 0x80070000;
    else
      Error = LastError;
LABEL_13:
    if ( Block != FileInformation )
      operator delete(Block);
    goto LABEL_15;
  }
  Error = ResultFromLastError();
  if ( Error >= 0 )
    goto LABEL_4;
  StringCbPrintfW(v31, 0x28u, L"0x%016I64X%016I64X", *(_QWORD *)a3->ObjectId.Data4, a3->FileId.QuadPart);
  *(_OWORD *)v24 = 0;
  v25 = 0;
  v26 = 0;
  v19 = -1;
  do
    ++v19;
  while ( v31[v19] );
  std::wstring::_Construct<1,wchar_t *>(v24);
  v20 = (const wchar_t *)v24;
  if ( v26 > 7 )
    v20 = v24[0];
  SearchIndexerTrace::Information(
    (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\mssrch\\\\gather\\\\usnmonnotifier\\\\frncache.cxx\"",
    (const wchar_t *)0x96,
    (unsigned int)L"[SrchGatherDirMon] CUsnMonitorNotifier::ResolveFrnByNtfs - Unable to open file by FRN %s",
    v20);
  ReIndexPatternInfo::~ReIndexPatternInfo((ReIndexPatternInfo *)v24);
LABEL_15:
  v16 = *((_QWORD *)a4 + 1);
  StringCbPrintfW(v31, 0x28u, L"0x%016I64X%016I64X", *(_QWORD *)a3->ObjectId.Data4, a3->FileId.QuadPart);
  *(_OWORD *)v24 = 0;
  v25 = 0;
  v26 = 0;
  do
    ++v8;
  while ( v31[v8] );
  std::wstring::_Construct<1,wchar_t *>(v24);
  v17 = (const wchar_t *)v24;
  if ( v26 > 7 )
    v17 = v24[0];
  SearchIndexerTrace::Verbose(
    (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\mssrch\\\\gather\\\\usnmonnotifier\\\\frncache.cxx\"",
    (const wchar_t *)0x9A,
    (unsigned int)L"[SrchGatherDirMon] FRN resolved by NTFS, FRN=%s, path=%ws",
    v17,
    v16);
  ReIndexPatternInfo::~ReIndexPatternInfo((ReIndexPatternInfo *)v24);
  if ( (unsigned __int64)(v9 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v9);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18002221c  mov     [rsp-8+arg_0], rbx
0x180022221  push    rbp
0x180022222  push    rsi
0x180022223  push    rdi
0x180022224  push    r12
0x180022226  push    r13
0x180022228  push    r14
0x18002222a  push    r15
0x18002222c  lea     rbp, [rsp-110h]
0x180022234  sub     rsp, 210h
0x18002223b  mov     rax, cs:__security_cookie
0x180022242  xor     rax, rsp
0x180022245  mov     [rbp+140h+var_40], rax
0x18002224c  mov     r12, r9
0x18002224f  mov     r14, r8
0x180022252  mov     r15, rdx
0x180022255  xor     edi, edi
0x180022257  mov     rbx, [rdx+118h]
0x18002225e  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180022262  cmp     rbx, rsi
0x180022265  jz      loc_1800225BD
0x18002226b  mov     rax, [r9]
0x18002226e  or      r9d, 0FFFFFFFFh
0x180022272  xor     r8d, r8d
0x180022275  lea     rdx, cchOriginalDestLength
0x18002227c  mov     rcx, r12
0x18002227f  mov     rax, [rax+20h]
0x180022283  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022288  nop
0x180022289  mov     [rsp+240h+FileId.Type], 2
0x180022291  movups  xmm0, xmmword ptr [r14]
0x180022295  movdqu  xmmword ptr [rsp+240h+FileId.8], xmm0
0x18002229b  mov     [rsp+240h+FileId.dwSize], 18h
0x1800222a3  mov     [rsp+240h+dwFlagsAndAttributes], edi; dwFlagsAndAttributes
0x1800222a7  mov     [rsp+240h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x1800222ac  lea     r9d, [rdi+7]; dwShareMode
0x1800222b0  lea     r8d, [r9+79h]; dwDesiredAccess
0x1800222b4  lea     rdx, [rsp+240h+FileId]; lpFileId
0x1800222b9  mov     rcx, rbx; hVolumeHint
0x1800222bc  call    cs:__imp_OpenFileById
0x1800222c2  mov     r13, rax
0x1800222c5  mov     [rsp+240h+var_210], rax
0x1800222ca  lea     rcx, [rax-1]
0x1800222ce  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x1800222d2  jbe     loc_1800225C7
0x1800222d8  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x1800222dd  mov     ebx, eax
0x1800222df  test    eax, eax
0x1800222e1  js      loc_180022476
0x1800222e7  mov     eax, 104h
0x1800222ec  mov     [rbp+140h+dwBufferSize], eax
0x1800222ef  lea     rdi, [rbp+140h+FileInformation]
0x1800222f3  mov     [rbp+140h+Block], rdi
0x1800222f7  add     eax, 0FFFFFFF8h
0x1800222fa  mov     [rdi], eax
0x1800222fc  mov     r9d, [rbp+140h+dwBufferSize]; dwBufferSize
0x180022300  mov     r8, rdi; lpFileInformation
0x180022303  mov     edx, 2; FileInformationClass
0x180022308  mov     rcx, r13; hFile
0x18002230b  call    cs:__imp_GetFileInformationByHandleEx
0x180022311  test    eax, eax
0x180022313  jz      loc_180022530
0x180022319  mov     r9d, [r15+0E8h]
0x180022320  test    r9d, r9d
0x180022323  jz      short loc_180022340
0x180022325  lea     r8d, [r9-1]
0x180022329  mov     rcx, [r15+0E0h]
0x180022330  movzx   ecx, word ptr [rcx+r8*2]; wchar_t
0x180022335  call    ?IsSlash@@YAH_W@Z; IsSlash(wchar_t)
0x18002233a  test    eax, eax
0x18002233c  cmovnz  r9d, r8d
0x180022340  mov     rax, [r12]
0x180022344  mov     r8d, [r12+14h]
0x180022349  mov     rdx, [r15+0E0h]
0x180022350  mov     rcx, r12
0x180022353  mov     rax, [rax+20h]
0x180022357  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002235c  mov     dword ptr [rsp+240h+var_1F0], 5
0x180022364  xor     r15d, r15d
0x180022367  mov     [rsp+240h+var_1F0+4], 50000h
0x180022370  mov     dword ptr [rsp+240h+var_1F0+0Ch], r15d
0x180022375  mov     rax, [r14]
0x180022378  sub     rax, [rsp+240h+var_1F0]
0x18002237d  jnz     short loc_180022388
0x18002237f  mov     rax, [r14+8]
0x180022383  sub     rax, [rsp+58h]
0x180022388  test    rax, rax
0x18002238b  jnz     loc_18002250C
0x180022391  lea     rax, [rbp+140h+FileInformation]
0x180022395  mov     rcx, [rbp+140h+Block]; Block
0x180022399  cmp     rcx, rax
0x18002239c  jz      short loc_1800223A3
0x18002239e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800223a3  mov     rdi, [r12+8]
0x1800223a8  mov     rax, [r14]
0x1800223ab  mov     [rsp+240h+lpSecurityAttributes], rax
0x1800223b0  mov     r9, [r14+8]
0x1800223b4  lea     r8, a0x016i64x016i6; "0x%016I64X%016I64X"
0x1800223bb  mov     edx, 28h ; '('; unsigned __int64
0x1800223c0  lea     rcx, [rbp+140h+var_90]; wchar_t *
0x1800223c7  call    ?StringCbPrintfW@@YAJPEA_W_KPEB_WZZ; StringCbPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800223cc  xorps   xmm0, xmm0
0x1800223cf  movups  xmmword ptr [rsp+240h+var_1F0], xmm0
0x1800223d4  mov     [rsp+240h+var_1E0], r15
0x1800223d9  mov     [rsp+240h+var_1D8], r15
0x1800223de  lea     rax, [rbp+140h+var_90]
0x1800223e5  inc     rsi
0x1800223e8  cmp     [rax+rsi*2], r15w
0x1800223ed  jnz     short loc_1800223E5
0x1800223ef  mov     r8, rsi
0x1800223f2  lea     rdx, [rbp+140h+var_90]
0x1800223f9  lea     rcx, [rsp+240h+var_1F0]
0x1800223fe  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x180022403  lea     r9, [rsp+240h+var_1F0]
0x180022408  cmp     [rsp+240h+var_1D8], 7
0x18002240e  cmova   r9, [rsp+240h+var_1F0]; wchar_t *
0x180022414  mov     [rsp+240h+lpSecurityAttributes], rdi
0x180022419  lea     r8, aSrchgatherdirm_35; "[SrchGatherDirMon] FRN resolved by NTFS"...
0x180022420  mov     edx, 9Ah; wchar_t *
0x180022425  lea     rcx, aOnecoreuapBase_81; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x18002242c  call    ?Verbose@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Verbose(wchar_t const *,uint,wchar_t const *,...)
0x180022431  lea     rcx, [rsp+240h+var_1F0]; this
0x180022436  call    ??1ReIndexPatternInfo@@QEAA@XZ; ReIndexPatternInfo::~ReIndexPatternInfo(void)
0x18002243b  nop
0x18002243c  lea     rax, [r13-1]
0x180022440  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180022444  jbe     loc_1800225CE
0x18002244a  mov     eax, ebx
0x18002244c  mov     rcx, [rbp+140h+var_40]
0x180022453  xor     rcx, rsp; StackCookie
0x180022456  call    __security_check_cookie
0x18002245b  mov     rbx, [rsp+240h+arg_0]
0x180022463  add     rsp, 210h
0x18002246a  pop     r15
0x18002246c  pop     r14
0x18002246e  pop     r13
0x180022470  pop     r12
0x180022472  pop     rdi
0x180022473  pop     rsi
0x180022474  pop     rbp
0x180022475  retn
0x180022476  mov     rax, [r14]
0x180022479  mov     [rsp+240h+lpSecurityAttributes], rax
0x18002247e  mov     r9, [r14+8]
0x180022482  lea     r8, a0x016i64x016i6; "0x%016I64X%016I64X"
0x180022489  mov     edx, 28h ; '('; unsigned __int64
0x18002248e  lea     rcx, [rbp+140h+var_90]; wchar_t *
0x180022495  call    ?StringCbPrintfW@@YAJPEA_W_KPEB_WZZ; StringCbPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18002249a  xorps   xmm0, xmm0
0x18002249d  movups  xmmword ptr [rsp+240h+var_1F0], xmm0
0x1800224a2  xor     r15d, r15d
0x1800224a5  mov     [rsp+240h+var_1E0], r15
0x1800224aa  mov     [rsp+240h+var_1D8], r15
0x1800224af  lea     rax, [rbp+140h+var_90]
0x1800224b6  mov     r8, rsi
0x1800224b9  inc     r8
0x1800224bc  cmp     [rax+r8*2], r15w
0x1800224c1  jnz     short loc_1800224B9
0x1800224c3  lea     rdx, [rbp+140h+var_90]
0x1800224ca  lea     rcx, [rsp+240h+var_1F0]
0x1800224cf  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x1800224d4  lea     r9, [rsp+240h+var_1F0]
0x1800224d9  cmp     [rsp+240h+var_1D8], 7
0x1800224df  cmova   r9, [rsp+240h+var_1F0]; wchar_t *
0x1800224e5  lea     r8, aSrchgatherdirm_26; "[SrchGatherDirMon] CUsnMonitorNotifier:"...
0x1800224ec  mov     edx, 96h; wchar_t *
0x1800224f1  lea     rcx, aOnecoreuapBase_81; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x1800224f8  call    ?Information@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Information(wchar_t const *,uint,wchar_t const *,...)
0x1800224fd  lea     rcx, [rsp+240h+var_1F0]; this
0x180022502  call    ??1ReIndexPatternInfo@@QEAA@XZ; ReIndexPatternInfo::~ReIndexPatternInfo(void)
0x180022507  jmp     loc_1800223A3
0x18002250c  mov     rax, [r12]
0x180022510  mov     r9d, [rdi]
0x180022513  shr     r9d, 1
0x180022516  lea     rdx, [rdi+4]
0x18002251a  mov     r8d, [r12+14h]
0x18002251f  mov     rcx, r12
0x180022522  mov     rax, [rax+20h]
0x180022526  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002252b  jmp     loc_180022391
0x180022530  call    cs:__imp_GetLastError
0x180022536  mov     edi, eax
0x180022538  cmp     eax, 0EAh
0x18002253d  jnz     short loc_180022559
0x18002253f  mov     edx, [rbp+140h+dwBufferSize]
0x180022542  add     edx, edx
0x180022544  lea     rcx, [rbp+140h+dwBufferSize]
0x180022548  call    ?SetSize@?$XGrowable@E$0BAE@@@QEAAPEAEI@Z; XGrowable<uchar,260>::SetSize(uint)
0x18002254d  mov     rdi, [rbp+140h+Block]
0x180022551  mov     eax, [rbp+140h+dwBufferSize]
0x180022554  jmp     loc_1800222F7
0x180022559  movups  xmm0, xmmword ptr [r14]
0x18002255d  movdqu  xmmword ptr [rsp+240h+var_1F0], xmm0
0x180022563  lea     rdx, [rsp+240h+var_1F0]
0x180022568  lea     rcx, [rsp+240h+var_1D0]
0x18002256d  call    ?to_wstring@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U_FILE_ID_128@@@Z; to_wstring(_FILE_ID_128)
0x180022572  cmp     qword ptr [rax+18h], 7
0x180022577  jbe     short loc_18002257C
0x180022579  mov     rax, [rax]
0x18002257c  mov     r9, rax; wchar_t *
0x18002257f  lea     r8, aSrchgatherdirm_33; "[SrchGatherDirMon] CUsnMonitorNotifier:"...
0x180022586  mov     edx, 8Ah; wchar_t *
0x18002258b  lea     rcx, aOnecoreuapBase_81; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x180022592  call    ?Information@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Information(wchar_t const *,uint,wchar_t const *,...)
0x180022597  lea     rcx, [rsp+240h+var_1D0]; this
0x18002259c  call    ??1ReIndexPatternInfo@@QEAA@XZ; ReIndexPatternInfo::~ReIndexPatternInfo(void)
0x1800225a1  xor     r15d, r15d
0x1800225a4  test    edi, edi
0x1800225a6  jg      short loc_1800225AF
0x1800225a8  mov     ebx, edi
0x1800225aa  jmp     loc_180022391
0x1800225af  movzx   ebx, di
0x1800225b2  or      ebx, 80070000h
0x1800225b8  jmp     loc_180022391
0x1800225bd  mov     eax, 80070006h
0x1800225c2  jmp     loc_18002244C
0x1800225c7  mov     ebx, edi
0x1800225c9  jmp     loc_1800222E7
0x1800225ce  mov     rcx, r13; hObject
0x1800225d1  call    cs:__imp_CloseHandle
0x1800225d7  jmp     loc_18002244A
```
