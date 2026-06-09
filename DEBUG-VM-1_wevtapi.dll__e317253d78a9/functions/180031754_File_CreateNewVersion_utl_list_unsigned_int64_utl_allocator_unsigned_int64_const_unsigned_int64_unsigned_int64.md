# File::CreateNewVersion(utl::list<unsigned __int64,utl::allocator<unsigned __int64>> const &,unsigned __int64,unsigned __int64,bool,bool,utl::unique_lock<utl::shared_mutex> &)

- ea: `0x180031754`
- end: `0x180031d95`
- name: `?CreateNewVersion@File@@AEAAXAEBV?$list@_KV?$allocator@_K@utl@@@utl@@_K1_N2AEAV?$unique_lock@Vshared_mutex@utl@@@3@@Z`
- size: `1601`
- prototype: `__int64 __usercall@<rax>(File *this@<rcx>, char, char, __int64)`
- caller_count: `2`
- callee_count: `20`
- tags: `file_ops, installer_update`

## callers

- `0x1800323a4`
- `0x180033258`

## callees

- `0x18000a724`
- `0x18000bf84`
- `0x18000c404`
- `0x18001585c`
- `0x180022340`
- `0x1800225a8`
- `0x1800227b4`
- `0x180022d7c`
- `0x180023548`
- `0x1800249f0`
- `0x1800254b4`
- `0x1800314a0`
- `0x180031754`
- `0x180033fa8`
- `0x180034fc0`
- `0x180034fe4`
- `0x180035158`
- `0x180035320`
- `0x180035884`
- `0x180038fb4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031872`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031c40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031d12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031872`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031c40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031d12`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x180031b6e`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x180031b6e`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x180031864`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x180031864`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180031919`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180031919`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x180031c32`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x180031c32`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall File::CreateNewVersion(
        File *this,
        _QWORD *a2,
        unsigned __int64 a3,
        __int64 a4,
        char a5,
        char a6,
        __int64 a7)
{
  _QWORD *v10; // rax
  DWORD LastError; // edi
  unsigned int v12; // edx
  HANDLE FileW; // r14
  __int64 v14; // rdi
  _QWORD *i; // rbx
  __int64 v16; // rcx
  __int64 v17; // rax
  __int64 v18; // rdx
  unsigned __int64 v19; // rax
  unsigned int v20; // r15d
  unsigned int v21; // edi
  __int64 v22; // rax
  unsigned int v23; // edi
  DWORD v24; // edi
  DWORD v26; // edi
  __int128 pExceptionObject; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v28; // [rsp+50h] [rbp-B0h]
  int v29; // [rsp+58h] [rbp-A8h]
  __int64 v30; // [rsp+5Ch] [rbp-A4h]
  char v31; // [rsp+64h] [rbp-9Ch]
  __int64 v32; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v33[2]; // [rsp+70h] [rbp-90h] BYREF
  LPCWSTR lpPathName[4]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v35[8]; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v36[4]; // [rsp+A8h] [rbp-58h] BYREF
  unsigned int v37; // [rsp+C8h] [rbp-38h]
  UCHAR Buffer[16]; // [rsp+290h] [rbp+190h] BYREF
  __int64 v39; // [rsp+2A0h] [rbp+1A0h]
  __int64 v40; // [rsp+2A8h] [rbp+1A8h]
  int v41; // [rsp+2B0h] [rbp+1B0h]
  int v42; // [rsp+2B4h] [rbp+1B4h]
  __int64 v43; // [rsp+2B8h] [rbp+1B8h]
  int v44; // [rsp+30Ch] [rbp+20Ch]
  WCHAR TempFileName[264]; // [rsp+310h] [rbp+210h] BYREF

  v32 = a4;
  v33[1] = a7;
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpPathName);
  v33[0] = *((_QWORD *)this + 85);
  v10 = (_QWORD *)tlx::split_path<wchar_t>::split_path<wchar_t>(&pExceptionObject, v33);
  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                           lpPathName,
                           *v10,
                           (__int64)(v10[2] - *v10) >> 1) )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 102, &WPP_b0e12c676fa238c8d52327699eb18844_Traceguids, 14);
    }
    pExceptionObject = 0;
    v28 = 0;
    v29 = 14;
    v30 = 0xAA9FFFFFFFFLL;
    throw (EvtException *)&pExceptionObject;
  }
  if ( !GetTempFileNameW(lpPathName[0], L"evt", 0, TempFileName) )
  {
    LastError = GetLastError();
    if ( !LastError )
      LastError = 1287;
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 103, &WPP_b0e12c676fa238c8d52327699eb18844_Traceguids, LastError);
    }
    pExceptionObject = 0;
    v28 = 0;
    v29 = LastError;
    v30 = 0xAAFFFFFFFFFLL;
    throw (EvtException *)&pExceptionObject;
  }
  FileW = CreateFileW(TempFileName, 0xC0000000, 1u, 0, 4u, 0, 0);
  v33[0] = FileW;
  if ( (unsigned __int64)FileW + 1 <= 1 )
  {
    v26 = GetLastError();
    if ( !v26 )
      v26 = 1287;
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 104, &WPP_b0e12c676fa238c8d52327699eb18844_Traceguids, v26);
    }
    pExceptionObject = 0;
    v28 = 0;
    v29 = v26;
    v30 = 0xABCFFFFFFFFLL;
    throw (EvtException *)&pExceptionObject;
  }
  v14 = 0;
  WriteFileView::WriteFileView((WriteFileView *)v35, v12, 1);
  for ( i = (_QWORD *)*a2; i != a2; i = (_QWORD *)*i )
  {
    FileView::ReadIn((FileView *)v36, *((void **)this + 84), (i[2] << 16) + 4096LL);
    if ( a5 )
    {
      v16 = v36[0];
      v17 = *(_QWORD *)(v36[0] + 16LL);
      v18 = *(_QWORD *)(v36[0] + 8LL);
      *(_QWORD *)(v36[0] + 8LL) = a3;
      if ( v17 != -1 )
      {
        v19 = a3 + v17 - v18;
        *(_QWORD *)(v16 + 16) = v19;
        a3 = v19 + 1;
      }
    }
    WriteFileView::UpdateBothCRCValues((WriteFileView *)v35);
    v36[1] = (v14 << 16) + 4096;
    v20 = FileView::ActualWrite((FileView *)v36, FileW, 0, v37);
    if ( v20 )
    {
      if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 105, &WPP_b0e12c676fa238c8d52327699eb18844_Traceguids, v20);
      }
      *(_QWORD *)&pExceptionObject = &word_18004024A;
      *((_QWORD *)&pExceptionObject + 1) = 0;
      v28 = 0;
      v29 = v20;
      v30 = -1;
      v31 = 0;
      throw (EvtException *)&pExceptionObject;
    }
    ++v14;
  }
  if ( a6 )
    AddBlankChunk(FileW, a3);
  else
    --v14;
  memset_0(Buffer, 0, 0x80u);
  strcpy((char *)Buffer, "ElfFile");
  v40 = v32;
  v41 = 128;
  v42 = 196610;
  v43 = (v14 << 16) + 69632;
  v44 = 0;
  v39 = v14;
  v21 = WriteFileHeader(FileW, Buffer);
  if ( v21 )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 106, &WPP_b0e12c676fa238c8d52327699eb18844_Traceguids, v21);
    }
    *(_QWORD *)&pExceptionObject = &word_18004024A;
    *((_QWORD *)&pExceptionObject + 1) = 0;
    v28 = 0;
    v29 = v21;
    v30 = -1;
    v31 = 0;
    throw (EvtException *)&pExceptionObject;
  }
  FlushFileBuffers(FileW);
  v22 = *((_QWORD *)this + 84);
  *((_QWORD *)this + 84) = 0;
  v32 = v22;
  v23 = CloseAndDelete(&v32);
  if ( v23 )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 107, &WPP_b0e12c676fa238c8d52327699eb18844_Traceguids, v23);
    }
    *(_QWORD *)&pExceptionObject = &word_18004024A;
    *((_QWORD *)&pExceptionObject + 1) = 0;
    v28 = 0;
    v29 = v23;
    v30 = -1;
    v31 = 0;
    throw (EvtException *)&pExceptionObject;
  }
  *((_BYTE *)this + 829) = 0;
  tlx::unique_any<tlx::file_handle_traits>::reset(v33, 0);
  if ( !MoveFileExW(TempFileName, *((LPCWSTR *)this + 85), 2u) )
  {
    v24 = GetLastError();
    if ( !v24 )
      v24 = 1287;
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 108, &WPP_b0e12c676fa238c8d52327699eb18844_Traceguids, v24);
    }
    pExceptionObject = 0;
    v28 = 0;
    v29 = v24;
    v30 = 0xB07FFFFFFFFLL;
    throw (EvtException *)&pExceptionObject;
  }
  File::OpenFile(this);
  FileView::~FileView((FileView *)v36);
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(v33);
  return utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::_Uninit(lpPathName);
}

```

## disassembly

```asm
0x180031754  push    rbp
0x180031756  push    rbx
0x180031757  push    rsi
0x180031758  push    rdi
0x180031759  push    r12
0x18003175b  push    r13
0x18003175d  push    r14
0x18003175f  push    r15
0x180031761  lea     rbp, [rsp-438h]
0x180031769  sub     rsp, 538h
0x180031770  mov     rax, cs:__security_cookie
0x180031777  xor     rax, rsp
0x18003177a  mov     [rbp+470h+var_50], rax
0x180031781  mov     [rsp+570h+var_508], r9
0x180031786  mov     r12, r8
0x180031789  mov     r13, rdx
0x18003178c  mov     rsi, rcx
0x18003178f  mov     r15, [rbp+470h+arg_30]
0x180031796  mov     [rsp+570h+var_4F8], r15
0x18003179b  lea     rcx, [rbp+470h+lpPathName]
0x18003179f  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800317a4  nop
0x1800317a5  mov     rax, [rsi+2A8h]
0x1800317ac  mov     [rsp+570h+var_500], rax
0x1800317b1  lea     rdx, [rsp+570h+var_500]
0x1800317b6  lea     rcx, [rsp+570h+pExceptionObject]
0x1800317bb  call    ??$?0PEB_W_W@?$split_path@_W@tlx@@QEAA@AEBQEB_W@Z; tlx::split_path<wchar_t>::split_path<wchar_t>(wchar_t const * const &)
0x1800317c0  mov     r8, [rax+10h]
0x1800317c4  sub     r8, [rax]
0x1800317c7  sar     r8, 1
0x1800317ca  mov     rdx, [rax]
0x1800317cd  lea     rcx, [rbp+470h+lpPathName]
0x1800317d1  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x1800317d6  xor     r15d, r15d
0x1800317d9  test    al, al
0x1800317db  jnz     short loc_18003184F
0x1800317dd  lea     rax, WPP_GLOBAL_Control
0x1800317e4  lea     edi, [r15+0Eh]
0x1800317e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800317ef  cmp     rcx, rax
0x1800317f2  jz      short loc_18003181B
0x1800317f4  test    dword ptr [rcx+1Ch], 8000h
0x1800317fb  jz      short loc_18003181B
0x1800317fd  lea     ebx, [rdi-0Ch]
0x180031800  cmp     [rcx+19h], bl
0x180031803  jb      short loc_18003181B
0x180031805  lea     edx, [rdi+58h]
0x180031808  mov     r9d, edi
0x18003180b  lea     r8, WPP_b0e12c676fa238c8d52327699eb18844_Traceguids
0x180031812  mov     rcx, [rcx+10h]
0x180031816  call    WPP_SF_D
0x18003181b  xorps   xmm0, xmm0
0x18003181e  movdqu  [rsp+570h+pExceptionObject], xmm0
0x180031824  mov     [rsp+570h+var_520], r15
0x180031829  mov     [rsp+570h+var_518], edi
0x18003182d  mov     dword ptr [rsp+570h+var_514], 0FFFFFFFFh
0x180031835  mov     dword ptr [rsp+570h+var_514+4], 0AA9h
0x18003183d  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180031844  lea     rcx, [rsp+570h+pExceptionObject]; pExceptionObject
0x180031849  call    _CxxThrowException_0
0x18003184f  lea     r9, [rbp+470h+TempFileName]; lpTempFileName
0x180031856  xor     r8d, r8d; uUnique
0x180031859  lea     rdx, PrefixString; "evt"
0x180031860  mov     rcx, [rbp+470h+lpPathName]; lpPathName
0x180031864  call    cs:__imp_GetTempFileNameW
0x18003186a  test    eax, eax
0x18003186c  jnz     loc_1800318F4
0x180031872  call    cs:__imp_GetLastError
0x180031878  mov     edi, eax
0x18003187a  mov     eax, 507h
0x18003187f  test    edi, edi
0x180031881  cmovz   edi, eax
0x180031884  lea     rax, WPP_GLOBAL_Control
0x18003188b  mov     rcx, cs:WPP_GLOBAL_Control
0x180031892  cmp     rcx, rax
0x180031895  jz      short loc_1800318C0
0x180031897  test    dword ptr [rcx+1Ch], 8000h
0x18003189e  jz      short loc_1800318C0
0x1800318a0  mov     ebx, 2
0x1800318a5  cmp     [rcx+19h], bl
0x1800318a8  jb      short loc_1800318C0
0x1800318aa  lea     edx, [rbx+65h]
0x1800318ad  mov     r9d, edi
0x1800318b0  lea     r8, WPP_b0e12c676fa238c8d52327699eb18844_Traceguids
0x1800318b7  mov     rcx, [rcx+10h]
0x1800318bb  call    WPP_SF_D
0x1800318c0  xorps   xmm0, xmm0
0x1800318c3  movdqu  [rsp+570h+pExceptionObject], xmm0
0x1800318c9  mov     [rsp+570h+var_520], r15
0x1800318ce  mov     [rsp+570h+var_518], edi
0x1800318d2  mov     dword ptr [rsp+570h+var_514], 0FFFFFFFFh
0x1800318da  mov     dword ptr [rsp+570h+var_514+4], 0AAFh
0x1800318e2  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800318e9  lea     rcx, [rsp+570h+pExceptionObject]; pExceptionObject
0x1800318ee  call    _CxxThrowException_0
0x1800318f4  mov     [rsp+570h+hTemplateFile], r15; hTemplateFile
0x1800318f9  mov     [rsp+570h+dwFlagsAndAttributes], r15d; dwFlagsAndAttributes
0x1800318fe  mov     [rsp+570h+dwCreationDisposition], 4; dwCreationDisposition
0x180031906  xor     r9d, r9d; lpSecurityAttributes
0x180031909  mov     edx, 0C0000000h; dwDesiredAccess
0x18003190e  lea     r8d, [r9+1]; dwShareMode
0x180031912  lea     rcx, [rbp+470h+TempFileName]; lpFileName
0x180031919  call    cs:__imp_CreateFileW
0x18003191f  mov     r14, rax
0x180031922  mov     [rsp+570h+var_500], rax
0x180031927  lea     rcx, [rax+1]
0x18003192b  cmp     rcx, 1
0x18003192f  jbe     loc_180031D12
0x180031935  mov     rdi, r15
0x180031938  mov     r8b, 1; bool
0x18003193b  lea     rcx, [rbp+470h+var_4D0]; this
0x18003193f  call    ??0WriteFileView@@QEAA@K_N@Z; WriteFileView::WriteFileView(ulong,bool)
0x180031944  nop
0x180031945  mov     rbx, [r13+0]
0x180031949  cmp     rbx, r13
0x18003194c  jz      loc_180031A58
0x180031952  mov     r8, [rbx+10h]
0x180031956  shl     r8, 10h
0x18003195a  add     r8, 1000h; unsigned __int64
0x180031961  mov     rdx, [rsi+2A0h]; void *
0x180031968  lea     rcx, [rbp+470h+var_4C8]; this
0x18003196c  call    ?ReadIn@FileView@@QEAAXPEAX_K@Z; FileView::ReadIn(void *,unsigned __int64)
0x180031971  cmp     [rbp+470h+arg_20], r15b
0x180031978  jz      short loc_18003199E
0x18003197a  mov     rcx, [rbp+470h+var_4C8]
0x18003197e  mov     rax, [rcx+10h]
0x180031982  mov     rdx, [rcx+8]
0x180031986  mov     [rcx+8], r12
0x18003198a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003198e  jz      short loc_18003199E
0x180031990  sub     rax, rdx
0x180031993  add     rax, r12
0x180031996  mov     [rcx+10h], rax
0x18003199a  lea     r12, [rax+1]
0x18003199e  lea     rcx, [rbp+470h+var_4D0]; this
0x1800319a2  call    ?UpdateBothCRCValues@WriteFileView@@QEAAXXZ; WriteFileView::UpdateBothCRCValues(void)
0x1800319a7  mov     rax, rdi
0x1800319aa  shl     rax, 10h
0x1800319ae  add     rax, 1000h
0x1800319b4  mov     [rbp+470h+var_4C0], rax
0x1800319b8  mov     r9d, [rbp+470h+var_4A8]; unsigned int
0x1800319bc  xor     r8d, r8d; unsigned int
0x1800319bf  mov     rdx, r14; void *
0x1800319c2  lea     rcx, [rbp+470h+var_4C8]; this
0x1800319c6  call    ?ActualWrite@FileView@@AEAAKPEAXKK@Z; FileView::ActualWrite(void *,ulong,ulong)
0x1800319cb  mov     r15d, eax
0x1800319ce  test    eax, eax
0x1800319d0  jnz     short loc_1800319E0
0x1800319d2  inc     rdi
0x1800319d5  mov     rbx, [rbx]
0x1800319d8  xor     r15d, r15d
0x1800319db  jmp     loc_180031949
0x1800319e0  lea     rax, WPP_GLOBAL_Control
0x1800319e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800319ee  cmp     rcx, rax
0x1800319f1  jz      short loc_180031A1C
0x1800319f3  test    dword ptr [rcx+1Ch], 8000h
0x1800319fa  jz      short loc_180031A1C
0x1800319fc  mov     ebx, 2
0x180031a01  cmp     [rcx+19h], bl
0x180031a04  jb      short loc_180031A1C
0x180031a06  lea     edx, [rbx+67h]
0x180031a09  mov     r9d, r15d
0x180031a0c  lea     r8, WPP_b0e12c676fa238c8d52327699eb18844_Traceguids
0x180031a13  mov     rcx, [rcx+10h]
0x180031a17  call    WPP_SF_D
0x180031a1c  lea     rax, word_18004024A
0x180031a23  mov     qword ptr [rsp+570h+pExceptionObject], rax
0x180031a28  xor     eax, eax
0x180031a2a  mov     qword ptr [rsp+570h+pExceptionObject+8], rax
0x180031a2f  mov     [rsp+570h+var_520], rax
0x180031a34  mov     [rsp+570h+var_518], r15d
0x180031a39  mov     [rsp+570h+var_514], 0FFFFFFFFFFFFFFFFh
0x180031a42  mov     [rsp+570h+var_50C], al
0x180031a46  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180031a4d  lea     rcx, [rsp+570h+pExceptionObject]; pExceptionObject
0x180031a52  call    _CxxThrowException_0
0x180031a58  cmp     [rbp+470h+arg_28], r15b
0x180031a5f  jz      short loc_180031A71
0x180031a61  mov     r8, rdi
0x180031a64  mov     rdx, r12; unsigned __int64
0x180031a67  mov     rcx, r14; void *
0x180031a6a  call    AddBlankChunk
0x180031a6f  jmp     short loc_180031A74
0x180031a71  dec     rdi
0x180031a74  mov     ebx, 80h
0x180031a79  mov     r8d, ebx; Size
0x180031a7c  xor     edx, edx; Val
0x180031a7e  lea     rcx, [rbp+470h+Buffer]; void *
0x180031a85  call    memset_0
0x180031a8a  mov     rax, qword ptr cs:aElffile; "ElfFile"
0x180031a91  mov     qword ptr [rbp+470h+Buffer], rax
0x180031a98  mov     rax, [rsp+570h+var_508]
0x180031a9d  mov     [rbp+470h+var_2C8], rax
0x180031aa4  mov     [rbp+470h+var_2C0], ebx
0x180031aaa  mov     [rbp+470h+var_2BC], 30002h
0x180031ab4  mov     ebx, 2
0x180031ab9  mov     rax, rdi
0x180031abc  shl     rax, 10h
0x180031ac0  add     rax, 11000h
0x180031ac6  mov     [rbp+470h+var_2B8], rax
0x180031acd  mov     [rbp+470h+var_264], r15d
0x180031ad4  mov     [rbp+470h+var_2D0], rdi
0x180031adb  xor     r9d, r9d
0x180031ade  xor     r8d, r8d
0x180031ae1  lea     rdx, [rbp+470h+Buffer]; Buffer
0x180031ae8  mov     rcx, r14; void *
0x180031aeb  call    WriteFileHeader
0x180031af0  mov     edi, eax
0x180031af2  test    eax, eax
0x180031af4  jz      short loc_180031B6B
0x180031af6  lea     rax, WPP_GLOBAL_Control
0x180031afd  mov     rcx, cs:WPP_GLOBAL_Control
0x180031b04  cmp     rcx, rax
0x180031b07  jz      short loc_180031B2D
0x180031b09  test    dword ptr [rcx+1Ch], 8000h
0x180031b10  jz      short loc_180031B2D
0x180031b12  cmp     [rcx+19h], bl
0x180031b15  jb      short loc_180031B2D
0x180031b17  lea     edx, [rbx+68h]
0x180031b1a  mov     r9d, edi
0x180031b1d  lea     r8, WPP_b0e12c676fa238c8d52327699eb18844_Traceguids
0x180031b24  mov     rcx, [rcx+10h]
0x180031b28  call    WPP_SF_D
0x180031b2d  lea     rax, word_18004024A
0x180031b34  mov     qword ptr [rsp+570h+pExceptionObject], rax
0x180031b39  mov     qword ptr [rsp+570h+pExceptionObject+8], r15
0x180031b3e  mov     [rsp+570h+var_520], 0
0x180031b47  mov     [rsp+570h+var_518], edi
0x180031b4b  mov     [rsp+570h+var_514], 0FFFFFFFFFFFFFFFFh
0x180031b54  mov     [rsp+570h+var_50C], r15b
0x180031b59  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180031b60  lea     rcx, [rsp+570h+pExceptionObject]; pExceptionObject
0x180031b65  call    _CxxThrowException_0
0x180031b6b  mov     rcx, r14; hFile
0x180031b6e  call    cs:__imp_FlushFileBuffers
0x180031b74  mov     rax, [rsi+2A0h]
0x180031b7b  mov     [rsi+2A0h], r15
0x180031b82  mov     [rsp+570h+var_508], rax
0x180031b87  lea     rcx, [rsp+570h+var_508]
0x180031b8c  call    CloseAndDelete
0x180031b91  mov     edi, eax
0x180031b93  test    eax, eax
0x180031b95  jz      short loc_180031C0E
0x180031b97  lea     rax, WPP_GLOBAL_Control
0x180031b9e  mov     rcx, cs:WPP_GLOBAL_Control
0x180031ba5  cmp     rcx, rax
0x180031ba8  jz      short loc_180031BD0
0x180031baa  test    dword ptr [rcx+1Ch], 8000h
0x180031bb1  jz      short loc_180031BD0
0x180031bb3  cmp     [rcx+19h], bl
0x180031bb6  jb      short loc_180031BD0
0x180031bb8  mov     edx, 6Bh ; 'k'
0x180031bbd  mov     r9d, edi
0x180031bc0  lea     r8, WPP_b0e12c676fa238c8d52327699eb18844_Traceguids
0x180031bc7  mov     rcx, [rcx+10h]
0x180031bcb  call    WPP_SF_D
0x180031bd0  lea     rax, word_18004024A
0x180031bd7  mov     qword ptr [rsp+570h+pExceptionObject], rax
0x180031bdc  mov     qword ptr [rsp+570h+pExceptionObject+8], r15
0x180031be1  mov     [rsp+570h+var_520], 0
0x180031bea  mov     [rsp+570h+var_518], edi
0x180031bee  mov     [rsp+570h+var_514], 0FFFFFFFFFFFFFFFFh
0x180031bf7  mov     [rsp+570h+var_50C], r15b
0x180031bfc  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180031c03  lea     rcx, [rsp+570h+pExceptionObject]; pExceptionObject
0x180031c08  call    _CxxThrowException_0
0x180031c0e  mov     [rsi+33Dh], r15b
0x180031c15  xor     edx, edx
0x180031c17  lea     rcx, [rsp+570h+var_500]
0x180031c1c  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x180031c21  mov     r8d, ebx; dwFlags
0x180031c24  mov     rdx, [rsi+2A8h]; lpNewFileName
0x180031c2b  lea     rcx, [rbp+470h+TempFileName]; lpExistingFileName
0x180031c32  call    cs:__imp_MoveFileExW
0x180031c38  test    eax, eax
0x180031c3a  jnz     loc_180031CC3
0x180031c40  call    cs:__imp_GetLastError
0x180031c46  mov     edi, eax
0x180031c48  mov     eax, 507h
0x180031c4d  test    edi, edi
0x180031c4f  cmovz   edi, eax
0x180031c52  lea     rax, WPP_GLOBAL_Control
0x180031c59  mov     rcx, cs:WPP_GLOBAL_Control
0x180031c60  cmp     rcx, rax
0x180031c63  jz      short loc_180031C8B
0x180031c65  test    dword ptr [rcx+1Ch], 8000h
0x180031c6c  jz      short loc_180031C8B
0x180031c6e  cmp     [rcx+19h], bl
0x180031c71  jb      short loc_180031C8B
0x180031c73  mov     edx, 6Ch ; 'l'
0x180031c78  mov     r9d, edi
0x180031c7b  lea     r8, WPP_b0e12c676fa238c8d52327699eb18844_Traceguids
0x180031c82  mov     rcx, [rcx+10h]
0x180031c86  call    WPP_SF_D
0x180031c8b  xorps   xmm0, xmm0
0x180031c8e  movdqu  [rsp+570h+pExceptionObject], xmm0
0x180031c94  mov     [rsp+570h+var_520], 0
0x180031c9d  mov     [rsp+570h+var_518], edi
0x180031ca1  mov     dword ptr [rsp+570h+var_514], 0FFFFFFFFh
  ... truncated ...
```
