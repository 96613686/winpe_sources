# PerfLibrary::Init(void)

- ea: `0x180065834`
- end: `0x180065bbd`
- name: `?Init@PerfLibrary@@QEAAHXZ`
- size: `905`
- prototype: `__int64 __fastcall(PerfLibrary *__hidden this)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800657a0`

## callees

- `0x18003b678`
- `0x180064924`
- `0x180065834`
- `0x180065bc4`
- `0x18008efd8`
- `0x1800f3e64`
- `0x18010bb54`
- `0x180147b7c`
- `0x180147eb8`
- `0x1801480fc`
- `0x180160468`
- `0x180161f18`
- `0x18016a4ec`
- `0x180188d90`
- `0x180189280`
- `0x18018e8cb`
- `0x1802c0010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065933`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065964`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800659d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065a70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065aa1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065933`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065964`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800659d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065a70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065aa1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180065a0a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180065ad7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180065a0a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180065ad7`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180065a57`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180065a57`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18006591d`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18006591d`

## string_xrefs

- `0x18006586c`: `[PerfCounter] MSFTESQL: failed to load perfmon info from registry`
- `0x18006597b`: `[PerfCounter] MSFTESQL: CreateFileMapping() failed: share "%ls" 0x%08x`
- `0x1800659eb`: `[PerfCounter] MSFTESQL: cannot create share "%ls" it already exists.`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall PerfLibrary::Init(HANDLE *this)
{
  const wchar_t *v2; // r9
  __int64 MemShareName; // rax
  HANDLE v5; // rax
  int LastError; // eax
  int v7; // r8d
  unsigned __int16 v8; // r9
  signed int v9; // eax
  const wchar_t *Buffer; // rax
  unsigned __int16 v11; // r9
  _DWORD *v12; // rax
  int v13; // eax
  int v14; // r8d
  unsigned __int16 v15; // r9
  signed int v16; // eax
  unsigned int i; // edi
  HANDLE *v18; // r14
  _WORD *v19; // rcx
  _WORD *v20; // rdx
  __int64 v21; // rax
  unsigned int v22; // eax
  DWORD dwMaximumSizeLow[2]; // [rsp+20h] [rbp-E0h]
  DWORD dwMaximumSizeLowa[2]; // [rsp+20h] [rbp-E0h]
  _BYTE v25[72]; // [rsp+30h] [rbp-D0h] BYREF
  _SECURITY_ATTRIBUTES FileMappingAttributes; // [rsp+78h] [rbp-88h] BYREF
  void *Block; // [rsp+98h] [rbp-68h]
  void **v28; // [rsp+A0h] [rbp-60h] BYREF
  LPCWSTR lpName; // [rsp+A8h] [rbp-58h]
  __int64 v30; // [rsp+B0h] [rbp-50h]
  wchar_t v31[68]; // [rsp+B8h] [rbp-48h] BYREF
  void **v32; // [rsp+140h] [rbp+40h] BYREF
  wchar_t *v33; // [rsp+148h] [rbp+48h]
  wchar_t v34[1028]; // [rsp+158h] [rbp+58h] BYREF

  if ( !(unsigned int)PerfLibrary::InitRegInfo((PerfLibrary *)this) )
  {
    SearchIndexerTrace::Error(
      (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\tquery\\\\fteutil\\\\perflib.cxx\"",
      (const wchar_t *)0x54,
      (unsigned int)L"[PerfCounter] MSFTESQL: failed to load perfmon info from registry",
      v2);
    return 0;
  }
  CPerfMonSecurityAttributes::CPerfMonSecurityAttributes((CPerfMonSecurityAttributes *)v25);
  lpName = v31;
  v30 = 65;
  v31[0] = 0;
  v28 = &CCICommonPathString::`vftable';
  MemShareName = CreateMemShareName((CLMString *)&v32, (wchar_t *)this);
  ((void (__fastcall *)(void ***, _QWORD, _QWORD, __int64))v28[4])(&v28, *(_QWORD *)(MemShareName + 8), 0, 0xFFFFFFFFLL);
  v32 = &CCICommonPathString::`vftable';
  CLMString::DeleteBuf((CLMString *)&v32, v34);
  FileMappingAttributes.lpSecurityDescriptor = v25;
  v5 = CreateFileMappingW((HANDLE)0xFFFFFFFFFFFFFFFFLL, &FileMappingAttributes, 4u, 0, 0x204u, lpName);
  this[29] = v5;
  if ( !v5 )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    CErrorString::CErrorString((CErrorString *)&v32, LastError, v7);
    PerfLibrary::Report((PerfLibrary *)this, 0x80002724, v33, v8);
    v9 = GetLastError();
    if ( v9 > 0 )
      v9 = (unsigned __int16)v9 | 0x80070000;
    dwMaximumSizeLow[0] = v9;
    SearchIndexerTrace::Error(
      (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\tquery\\\\fteutil\\\\perflib.cxx\"",
      (const wchar_t *)0x6A,
      (unsigned int)L"[PerfCounter] MSFTESQL: CreateFileMapping() failed: share \"%ls\" 0x%08x",
      lpName,
      *(_QWORD *)dwMaximumSizeLow);
    v32 = &CLMString::`vftable';
    v28 = &CCICommonPathString::`vftable';
    CLMString::DeleteBuf((CLMString *)&v28, v31);
    v28 = &CLMString::`vftable';
LABEL_10:
    operator delete(Block);
    Block = 0;
    SecUtil::CSecurityDescriptor::~CSecurityDescriptor((SecUtil::CSecurityDescriptor *)v25);
    return 0;
  }
  if ( GetLastError() == 183 )
  {
    Buffer = CLMString::GetBuffer((CLMString *)&v28, 0);
    SearchIndexerTrace::Error(
      (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\tquery\\\\fteutil\\\\perflib.cxx\"",
      (const wchar_t *)0x71,
      (unsigned int)L"[PerfCounter] MSFTESQL: cannot create share \"%ls\" it already exists.",
      Buffer);
    CloseHandle(this[29]);
    this[29] = 0;
    PerfLibrary::Report((PerfLibrary *)this, 0x80002726, 0, v11);
    TLMString<64,64,32767>::~TLMString<64,64,32767>(&v28);
    CPerfMonSecurityAttributes::~CPerfMonSecurityAttributes((CPerfMonSecurityAttributes *)v25);
    return 0;
  }
  v12 = MapViewOfFile(this[29], 2u, 0, 0, 0);
  this[30] = v12;
  if ( !v12 )
  {
    v13 = GetLastError();
    if ( v13 > 0 )
      v13 = (unsigned __int16)v13 | 0x80070000;
    CErrorString::CErrorString((CErrorString *)&v32, v13, v14);
    PerfLibrary::Report((PerfLibrary *)this, 0x80002724, v33, v15);
    v16 = GetLastError();
    if ( v16 > 0 )
      v16 = (unsigned __int16)v16 | 0x80070000;
    dwMaximumSizeLowa[0] = v16;
    SearchIndexerTrace::Error(
      (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\tquery\\\\fteutil\\\\perflib.cxx\"",
      (const wchar_t *)0x84,
      (unsigned int)L"[PerfCounter] MSFTESQL: MapViewOfFile( ) failed: share \"%ls\" 0x%08x",
      lpName,
      *(_QWORD *)dwMaximumSizeLowa);
    CloseHandle(this[29]);
    this[29] = 0;
    v32 = &CLMString::`vftable';
    v28 = &CCICommonPathString::`vftable';
    CLMString::DeleteBuf((CLMString *)&v28, v31);
    v28 = &CLMString::`vftable';
    goto LABEL_10;
  }
  this[31] = v12;
  this[32] = v12 + 1;
  *v12 = *((_DWORD *)this + 56);
  for ( i = 0; i < *((_DWORD *)this + 56); ++i )
  {
    v18 = &this[i];
    if ( (unsigned int)PerfObjectDefinition::Init((PerfObjectDefinition *)v18[12], (struct PerfLibrary *)this) )
    {
      v19 = (char *)this[32] + 32 * i;
      *v19 = 0;
      v20 = v18[12];
      v21 = -1;
      do
        ++v21;
      while ( v20[v21] );
      v22 = v21 + 1;
      if ( v22 <= 0x10 )
        memcpy_0(v19, v20, 2LL * v22);
    }
  }
  TLMString<64,64,32767>::~TLMString<64,64,32767>(&v28);
  CPerfMonSecurityAttributes::~CPerfMonSecurityAttributes((CPerfMonSecurityAttributes *)v25);
  return 1;
}

```

## disassembly

```asm
0x180065834  push    rbp
0x180065836  push    rbx
0x180065837  push    rsi
0x180065838  push    rdi
0x180065839  push    r14
0x18006583b  push    r15
0x18006583d  lea     rbp, [rsp-878h]
0x180065845  sub     rsp, 978h
0x18006584c  mov     rax, cs:__security_cookie
0x180065853  xor     rax, rsp
0x180065856  mov     [rbp+8A0h+var_40], rax
0x18006585d  mov     rbx, rcx
0x180065860  call    ?InitRegInfo@PerfLibrary@@AEAAHXZ; PerfLibrary::InitRegInfo(void)
0x180065865  xor     r15d, r15d
0x180065868  test    eax, eax
0x18006586a  jnz     short loc_180065889
0x18006586c  lea     r8, aPerfcounterMsf_19; "[PerfCounter] MSFTESQL: failed to load "...
0x180065873  lea     edx, [rax+54h]; wchar_t *
0x180065876  lea     rcx, aOnecoreuapBase_153; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x18006587d  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x180065882  xor     eax, eax
0x180065884  jmp     loc_180065B9E
0x180065889  lea     rcx, [rsp+9A0h+var_970]; this
0x18006588e  call    ??0CPerfMonSecurityAttributes@@QEAA@XZ; CPerfMonSecurityAttributes::CPerfMonSecurityAttributes(void)
0x180065893  nop
0x180065894  lea     rax, [rbp+8A0h+var_8E8]
0x180065898  mov     [rbp+8A0h+var_8F8], rax
0x18006589c  mov     [rbp+8A0h+var_8F0], 41h ; 'A'
0x1800658a4  mov     [rbp+8A0h+var_8E8], r15w
0x1800658a9  lea     rsi, ??_7CCICommonPathString@@6B@; const CCICommonPathString::`vftable'
0x1800658b0  mov     [rbp+8A0h+var_900], rsi
0x1800658b4  lea     r9, [rbx+40h]
0x1800658b8  mov     rdx, rbx; wchar_t *
0x1800658bb  lea     rcx, [rbp+8A0h+var_860]; this
0x1800658bf  call    ?CreateMemShareName@@YA?AV?$TLMString@$0EA@$0EA@$0HPPP@@@PEB_W00@Z; CreateMemShareName(wchar_t const *,wchar_t const *,wchar_t const *)
0x1800658c4  mov     rdx, [rax+8]
0x1800658c8  mov     rcx, [rbp+8A0h+var_900]
0x1800658cc  mov     rax, [rcx+20h]
0x1800658d0  or      r9d, 0FFFFFFFFh
0x1800658d4  xor     r8d, r8d
0x1800658d7  lea     rcx, [rbp+8A0h+var_900]
0x1800658db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800658e0  nop
0x1800658e1  mov     [rbp+8A0h+var_860], rsi
0x1800658e5  lea     rdx, [rbp+8A0h+var_848]; wchar_t *
0x1800658e9  lea     rcx, [rbp+8A0h+var_860]; this
0x1800658ed  call    ?DeleteBuf@CLMString@@IEAAXPEB_W@Z; CLMString::DeleteBuf(wchar_t const *)
0x1800658f2  nop
0x1800658f3  lea     rax, [rsp+9A0h+var_970]
0x1800658f8  mov     [rbp+8A0h+FileMappingAttributes.lpSecurityDescriptor], rax
0x1800658fc  mov     rax, [rbp+8A0h+var_8F8]
0x180065900  mov     [rsp+9A0h+lpName], rax; lpName
0x180065905  mov     [rsp+9A0h+dwMaximumSizeLow], 204h; dwMaximumSizeLow
0x18006590d  xor     r9d, r9d; dwMaximumSizeHigh
0x180065910  lea     r8d, [r9+4]; flProtect
0x180065914  lea     rdx, [rsp+9A0h+FileMappingAttributes]; lpFileMappingAttributes
0x180065919  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x18006591d  call    cs:__imp_CreateFileMappingW
0x180065923  mov     [rbx+0E8h], rax
0x18006592a  test    rax, rax
0x18006592d  jnz     loc_1800659D0
0x180065933  call    cs:__imp_GetLastError
0x180065939  mov     edi, 80070000h
0x18006593e  test    eax, eax
0x180065940  jle     short loc_180065947
0x180065942  movzx   eax, ax
0x180065945  or      eax, edi
0x180065947  mov     edx, eax; dwMessageId
0x180065949  lea     rcx, [rbp+8A0h+var_860]; this
0x18006594d  call    ??0CErrorString@@QEAA@JH@Z; CErrorString::CErrorString(long,int)
0x180065952  nop
0x180065953  mov     r8, [rbp+8A0h+var_858]; wchar_t *
0x180065957  mov     edx, 80002724h; unsigned int
0x18006595c  mov     rcx, rbx; this
0x18006595f  call    ?Report@PerfLibrary@@AEAAXKPEB_WG@Z; PerfLibrary::Report(ulong,wchar_t const *,ushort)
0x180065964  call    cs:__imp_GetLastError
0x18006596a  test    eax, eax
0x18006596c  jle     short loc_180065973
0x18006596e  movzx   eax, ax
0x180065971  or      eax, edi
0x180065973  mov     [rsp+9A0h+dwMaximumSizeLow], eax
0x180065977  mov     r9, [rbp+8A0h+var_8F8]; wchar_t *
0x18006597b  lea     r8, aPerfcounterMsf; "[PerfCounter] MSFTESQL: CreateFileMappi"...
0x180065982  mov     edx, 6Ah ; 'j'; wchar_t *
0x180065987  lea     rcx, aOnecoreuapBase_153; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x18006598e  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x180065993  nop
0x180065994  lea     rbx, ??_7CLMString@@6B@; const CLMString::`vftable'
0x18006599b  mov     [rbp+8A0h+var_860], rbx
0x18006599f  mov     [rbp+8A0h+var_900], rsi
0x1800659a3  lea     rdx, [rbp+8A0h+var_8E8]; wchar_t *
0x1800659a7  lea     rcx, [rbp+8A0h+var_900]; this
0x1800659ab  call    ?DeleteBuf@CLMString@@IEAAXPEB_W@Z; CLMString::DeleteBuf(wchar_t const *)
0x1800659b0  mov     [rbp+8A0h+var_900], rbx
0x1800659b4  mov     rcx, [rbp+8A0h+Block]; Block
0x1800659b8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800659bd  mov     [rbp+8A0h+Block], r15
0x1800659c1  lea     rcx, [rsp+9A0h+var_970]; this
0x1800659c6  call    ??1CSecurityDescriptor@SecUtil@@QEAA@XZ; SecUtil::CSecurityDescriptor::~CSecurityDescriptor(void)
0x1800659cb  jmp     loc_180065882
0x1800659d0  call    cs:__imp_GetLastError
0x1800659d6  cmp     eax, 0B7h
0x1800659db  jnz     short loc_180065A41
0x1800659dd  xor     edx, edx; int
0x1800659df  lea     rcx, [rbp+8A0h+var_900]; this
0x1800659e3  call    ?GetBuffer@CLMString@@QEAAPEA_WH@Z; CLMString::GetBuffer(int)
0x1800659e8  mov     r9, rax; wchar_t *
0x1800659eb  lea     r8, aPerfcounterMsf_1; "[PerfCounter] MSFTESQL: cannot create s"...
0x1800659f2  mov     edx, 71h ; 'q'; wchar_t *
0x1800659f7  lea     rcx, aOnecoreuapBase_153; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x1800659fe  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x180065a03  mov     rcx, [rbx+0E8h]; hObject
0x180065a0a  call    cs:__imp_CloseHandle
0x180065a10  mov     [rbx+0E8h], r15
0x180065a17  xor     r8d, r8d; wchar_t *
0x180065a1a  mov     edx, 80002726h; unsigned int
0x180065a1f  mov     rcx, rbx; this
0x180065a22  call    ?Report@PerfLibrary@@AEAAXKPEB_WG@Z; PerfLibrary::Report(ulong,wchar_t const *,ushort)
0x180065a27  nop
0x180065a28  lea     rcx, [rbp+8A0h+var_900]
0x180065a2c  call    ??1?$TLMString@$0EA@$0EA@$0HPPP@@@UEAA@XZ; TLMString<64,64,32767>::~TLMString<64,64,32767>(void)
0x180065a31  nop
0x180065a32  lea     rcx, [rsp+9A0h+var_970]; this
0x180065a37  call    ??1CPerfMonSecurityAttributes@@QEAA@XZ; CPerfMonSecurityAttributes::~CPerfMonSecurityAttributes(void)
0x180065a3c  jmp     loc_180065882
0x180065a41  mov     qword ptr [rsp+9A0h+dwMaximumSizeLow], r15; dwNumberOfBytesToMap
0x180065a46  xor     r9d, r9d; dwFileOffsetLow
0x180065a49  xor     r8d, r8d; dwFileOffsetHigh
0x180065a4c  lea     edx, [r9+2]; dwDesiredAccess
0x180065a50  mov     rcx, [rbx+0E8h]; hFileMappingObject
0x180065a57  call    cs:__imp_MapViewOfFile
0x180065a5d  mov     rcx, rax
0x180065a60  mov     [rbx+0F0h], rax
0x180065a67  test    rax, rax
0x180065a6a  jnz     loc_180065B09
0x180065a70  call    cs:__imp_GetLastError
0x180065a76  mov     edi, 80070000h
0x180065a7b  test    eax, eax
0x180065a7d  jle     short loc_180065A84
0x180065a7f  movzx   eax, ax
0x180065a82  or      eax, edi
0x180065a84  mov     edx, eax; dwMessageId
0x180065a86  lea     rcx, [rbp+8A0h+var_860]; this
0x180065a8a  call    ??0CErrorString@@QEAA@JH@Z; CErrorString::CErrorString(long,int)
0x180065a8f  nop
0x180065a90  mov     r8, [rbp+8A0h+var_858]; wchar_t *
0x180065a94  mov     edx, 80002724h; unsigned int
0x180065a99  mov     rcx, rbx; this
0x180065a9c  call    ?Report@PerfLibrary@@AEAAXKPEB_WG@Z; PerfLibrary::Report(ulong,wchar_t const *,ushort)
0x180065aa1  call    cs:__imp_GetLastError
0x180065aa7  test    eax, eax
0x180065aa9  jle     short loc_180065AB0
0x180065aab  movzx   eax, ax
0x180065aae  or      eax, edi
0x180065ab0  mov     [rsp+9A0h+dwMaximumSizeLow], eax
0x180065ab4  mov     r9, [rbp+8A0h+var_8F8]; wchar_t *
0x180065ab8  lea     r8, aPerfcounterMsf_26; "[PerfCounter] MSFTESQL: MapViewOfFile( "...
0x180065abf  mov     edx, 84h; wchar_t *
0x180065ac4  lea     rcx, aOnecoreuapBase_153; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x180065acb  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x180065ad0  mov     rcx, [rbx+0E8h]; hObject
0x180065ad7  call    cs:__imp_CloseHandle
0x180065add  mov     [rbx+0E8h], r15
0x180065ae4  lea     rbx, ??_7CLMString@@6B@; const CLMString::`vftable'
0x180065aeb  mov     [rbp+8A0h+var_860], rbx
0x180065aef  mov     [rbp+8A0h+var_900], rsi
0x180065af3  lea     rdx, [rbp+8A0h+var_8E8]; wchar_t *
0x180065af7  lea     rcx, [rbp+8A0h+var_900]; this
0x180065afb  call    ?DeleteBuf@CLMString@@IEAAXPEB_W@Z; CLMString::DeleteBuf(wchar_t const *)
0x180065b00  mov     [rbp+8A0h+var_900], rbx
0x180065b04  jmp     loc_1800659B4
0x180065b09  mov     [rbx+0F8h], rcx
0x180065b10  add     rax, 4
0x180065b14  mov     [rbx+100h], rax
0x180065b1b  mov     eax, [rbx+0E0h]
0x180065b21  mov     [rcx], eax
0x180065b23  mov     edi, r15d
0x180065b26  cmp     [rbx+0E0h], r15d
0x180065b2d  jbe     short loc_180065B85
0x180065b2f  mov     esi, edi
0x180065b31  lea     r14, [rbx+rsi*8]
0x180065b35  mov     rdx, rbx; struct PerfLibrary *
0x180065b38  mov     rcx, [r14+60h]; this
0x180065b3c  call    ?Init@PerfObjectDefinition@@AEAAHPEAVPerfLibrary@@@Z; PerfObjectDefinition::Init(PerfLibrary *)
0x180065b41  test    eax, eax
0x180065b43  jz      short loc_180065B7B
0x180065b45  shl     rsi, 5
0x180065b49  mov     rcx, [rbx+100h]
0x180065b50  add     rcx, rsi; void *
0x180065b53  mov     [rcx], r15w
0x180065b57  mov     rdx, [r14+60h]; Src
0x180065b5b  or      rax, 0FFFFFFFFFFFFFFFFh
0x180065b5f  inc     rax
0x180065b62  cmp     [rdx+rax*2], r15w
0x180065b67  jnz     short loc_180065B5F
0x180065b69  inc     eax
0x180065b6b  cmp     eax, 10h
0x180065b6e  ja      short loc_180065B7B
0x180065b70  mov     r8d, eax
0x180065b73  add     r8, r8; Size
0x180065b76  call    memcpy_0
0x180065b7b  inc     edi
0x180065b7d  cmp     edi, [rbx+0E0h]
0x180065b83  jb      short loc_180065B2F
0x180065b85  lea     rcx, [rbp+8A0h+var_900]
0x180065b89  call    ??1?$TLMString@$0EA@$0EA@$0HPPP@@@UEAA@XZ; TLMString<64,64,32767>::~TLMString<64,64,32767>(void)
0x180065b8e  nop
0x180065b8f  lea     rcx, [rsp+9A0h+var_970]; this
0x180065b94  call    ??1CPerfMonSecurityAttributes@@QEAA@XZ; CPerfMonSecurityAttributes::~CPerfMonSecurityAttributes(void)
0x180065b99  mov     eax, 1
0x180065b9e  mov     rcx, [rbp+8A0h+var_40]
0x180065ba5  xor     rcx, rsp; StackCookie
0x180065ba8  call    __security_check_cookie
0x180065bad  add     rsp, 978h
0x180065bb4  pop     r15
0x180065bb6  pop     r14
0x180065bb8  pop     rdi
0x180065bb9  pop     rsi
0x180065bba  pop     rbx
0x180065bbb  pop     rbp
0x180065bbc  retn
```
