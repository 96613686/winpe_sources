# FileSystem::DiskOperations::ReadFileFromDisk(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,void * const &)

- ea: `0x180032a9c`
- end: `0x180032ea8`
- name: `?ReadFileFromDisk@DiskOperations@FileSystem@@SA?AV?$tuple@V?$scoped_error@Utag@winerror_error@@@errorlib@@V?$vector@EV?$allocator@E@std@@@std@@U_Nil@tr1@4@U564@U564@U564@U564@U564@U564@U564@@tr1@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@5@AEBQEAX@Z`
- size: `1036`
- prototype: ``
- caller_count: `2`
- callee_count: `18`
- tags: `file_ops, registry_config`

## callers

- `0x18002d320`
- `0x18002e768`

## callees

- `0x1800081bc`
- `0x1800089e8`
- `0x180008d24`
- `0x180009a5c`
- `0x180009e14`
- `0x18000aa10`
- `0x18001e778`
- `0x18001ee28`
- `0x180024478`
- `0x180025cb4`
- `0x18002e1d0`
- `0x18002f564`
- `0x180032a9c`
- `0x18003ad54`
- `0x18003aeb0`
- `0x18003af6c`
- `0x1800586c6`
- `0x180058700`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180032c25`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180032c25`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x180032bac`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x180032bac`
- `KERNEL32!CreateFileTransactedW` at `0x180032b5d`
- `KERNEL32!CreateFileTransactedW` at `0x180032b5d`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
char *__fastcall FileSystem::DiskOperations::ReadFileFromDisk(char *a1, const WCHAR *a2, HANDLE *a3)
{
  const WCHAR *v6; // rcx
  char *FileTransactedW; // rbx
  __int64 winerror_if; // rax
  BOOL v9; // eax
  __int64 v10; // rax
  BOOL v11; // eax
  __int64 v12; // rax
  unsigned int v13; // eax
  __int64 v14; // r9
  __int64 v15; // r8
  int v16; // r8d
  _QWORD *v17; // rcx
  int v18; // edx
  unsigned int v19; // eax
  __int64 v20; // r9
  __int64 v21; // r8
  int v22; // r8d
  unsigned int v23; // eax
  __int64 v24; // r9
  __int64 v25; // r8
  unsigned int v26; // eax
  __int64 v27; // r9
  __int64 v28; // r8
  char v30; // [rsp+50h] [rbp-B0h] BYREF
  int v31; // [rsp+58h] [rbp-A8h] BYREF
  int v32; // [rsp+5Ch] [rbp-A4h]
  _BYTE *v33; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD *v34; // [rsp+68h] [rbp-98h]
  union _LARGE_INTEGER FileSize; // [rsp+70h] [rbp-90h] BYREF
  char *v36; // [rsp+78h] [rbp-88h] BYREF
  DWORD NumberOfBytesRead; // [rsp+80h] [rbp-80h] BYREF
  _QWORD *v38; // [rsp+88h] [rbp-78h] BYREF
  __int16 v39; // [rsp+90h] [rbp-70h]
  LPVOID lpBuffer[2]; // [rsp+98h] [rbp-68h] BYREF
  __int64 v41; // [rsp+A8h] [rbp-58h]
  _QWORD v42[4]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v43[64]; // [rsp+E0h] [rbp-20h] BYREF
  _QWORD v44[6]; // [rsp+120h] [rbp+20h] BYREF

  v36 = a1;
  errorlib::scoped_error<winerror_error::tag>::scoped_error<winerror_error::tag>(&v31);
  *(_OWORD *)lpBuffer = 0;
  v41 = 0;
  v30 = 1;
  v42[0] = &v30;
  v42[1] = a2;
  v42[2] = &v31;
  lambda_d8fc33e9fc6915260a8ac659ebcfefcc_::operator()(v42);
  v30 = 0;
  v38 = v42;
  v39 = 258;
  if ( *((_QWORD *)a2 + 3) < 8u )
    v6 = a2;
  else
    v6 = *(const WCHAR **)a2;
  FileTransactedW = (char *)CreateFileTransactedW(v6, 0x80000000, 0, 0, 3u, 0x80u, 0, *a3, 0, 0);
  v36 = FileTransactedW;
  winerror_if = make_winerror_if(&v33, FileTransactedW + 1 == 0);
  errorlib::scoped_error<ntstatus_error::tag>::operator=(&v31, winerror_if);
  v32 = 3;
  if ( v31 )
  {
    memset_0(v43, 0, sizeof(v43));
    v26 = ReportIndentTracker::Indent();
    v33 = v43;
    v34 = v44;
    LOBYTE(v27) = 95;
    ReportIndentTracker::Format(&v33, v26, v28, v27);
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      if ( *((_QWORD *)a2 + 3) >= 8u )
        a2 = *(const WCHAR **)a2;
      v18 = 36;
      goto LABEL_33;
    }
  }
  else
  {
    FileSize.QuadPart = 0;
    v9 = GetFileSizeEx(FileTransactedW, &FileSize);
    v10 = make_winerror_if(&v33, !v9);
    errorlib::scoped_error<ntstatus_error::tag>::operator=(&v31, v10);
    v32 = 3;
    if ( v31 )
    {
      memset_0(v43, 0, sizeof(v43));
      v23 = ReportIndentTracker::Indent();
      v33 = v43;
      v34 = v44;
      LOBYTE(v24) = 95;
      ReportIndentTracker::Format(&v33, v23, v25, v24);
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        if ( *((_QWORD *)a2 + 3) >= 8u )
          a2 = *(const WCHAR **)a2;
        v18 = 37;
        goto LABEL_33;
      }
    }
    else if ( FileSize.QuadPart > 0x100000uLL )
    {
      memset_0(v43, 0, sizeof(v43));
      v19 = ReportIndentTracker::Indent();
      v33 = v43;
      v34 = v44;
      LOBYTE(v20) = 95;
      ReportIndentTracker::Format(&v33, v19, v21, v20);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        if ( *((_QWORD *)a2 + 3) >= 8u )
          a2 = *(const WCHAR **)a2;
        WPP_SF_sS(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, v22, (unsigned int)v43, (__int64)a2);
      }
      LODWORD(v33) = 223;
      errorlib::scoped_error<winerror_error::tag>::initiate<long>(&v31, &v33);
    }
    else
    {
      NumberOfBytesRead = 0;
      std::vector<unsigned char>::resize(lpBuffer, FileSize.LowPart);
      v11 = ReadFile(FileTransactedW, lpBuffer[0], LODWORD(lpBuffer[1]) - LODWORD(lpBuffer[0]), &NumberOfBytesRead, 0);
      v12 = make_winerror_if(&v33, !v11);
      errorlib::scoped_error<ntstatus_error::tag>::operator=(&v31, v12);
      v32 = 3;
      if ( v31 )
      {
        memset_0(v43, 0, sizeof(v43));
        v13 = ReportIndentTracker::Indent();
        v33 = v43;
        v34 = v44;
        LOBYTE(v14) = 95;
        ReportIndentTracker::Format(&v33, v13, v15, v14);
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          if ( *((_QWORD *)a2 + 3) >= 8u )
            a2 = *(const WCHAR **)a2;
          v18 = 39;
LABEL_33:
          WPP_SF_sDS(v17[2], v18, v16, (unsigned int)v43, v31, (__int64)a2);
        }
      }
    }
  }
  std::tr1::tuple<errorlib::scoped_error<winerror_error::tag>,std::vector<unsigned char>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>::tuple<errorlib::scoped_error<winerror_error::tag>,std::vector<unsigned char>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>(
    a1,
    &v31,
    lpBuffer);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v36);
  wil::details::ScopeExitFnGuard_std::tr1::reference_wrapper__lambda_d8fc33e9fc6915260a8ac659ebcfefcc_____::operator()(&v38);
  std::vector<_CRYPTOAPI_BLOB>::~vector<_CRYPTOAPI_BLOB>(lpBuffer);
  errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(&v31);
  return a1;
}

```

## disassembly

```asm
0x180032a9c  push    rbp
0x180032a9e  push    rbx
0x180032a9f  push    rsi
0x180032aa0  push    rdi
0x180032aa1  push    r14
0x180032aa3  lea     rbp, [rsp-30h]
0x180032aa8  sub     rsp, 130h
0x180032aaf  mov     rax, cs:__security_cookie
0x180032ab6  xor     rax, rsp
0x180032ab9  mov     [rbp+50h+var_30], rax
0x180032abd  mov     rbx, r8
0x180032ac0  mov     rdi, rdx
0x180032ac3  mov     rsi, rcx
0x180032ac6  mov     [rsp+150h+var_D8], rcx
0x180032acb  xor     r14d, r14d
0x180032ace  lea     rcx, [rsp+150h+var_F8]
0x180032ad3  call    ??0?$scoped_error@Utag@winerror_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<winerror_error::tag>::scoped_error<winerror_error::tag>(void)
0x180032ad8  nop
0x180032ad9  xorps   xmm0, xmm0
0x180032adc  movdqu  xmmword ptr [rbp+50h+lpBuffer], xmm0
0x180032ae1  mov     [rbp+50h+var_A8], r14
0x180032ae5  mov     [rsp+150h+var_100], 1
0x180032aea  lea     rax, [rsp+150h+var_100]
0x180032aef  mov     [rbp+50h+var_90], rax
0x180032af3  mov     [rbp+50h+var_88], rdi
0x180032af7  lea     rax, [rsp+150h+var_F8]
0x180032afc  mov     [rbp+50h+var_80], rax
0x180032b00  lea     rcx, [rbp+50h+var_90]
0x180032b04  call    _lambda_d8fc33e9fc6915260a8ac659ebcfefcc___operator__
0x180032b09  mov     [rsp+150h+var_100], r14b
0x180032b0e  lea     rax, [rbp+50h+var_90]
0x180032b12  mov     [rbp+50h+var_C8], rax
0x180032b16  mov     [rbp+50h+var_C0], 102h
0x180032b1c  mov     rax, [rbx]
0x180032b1f  cmp     qword ptr [rdi+18h], 8
0x180032b24  jb      short loc_180032B2B
0x180032b26  mov     rcx, [rdi]
0x180032b29  jmp     short loc_180032B2E
0x180032b2b  mov     rcx, rdi; lpFileName
0x180032b2e  mov     [rsp+150h+lpExtendedParameter], r14; lpExtendedParameter
0x180032b33  mov     [rsp+150h+pusMiniVersion], r14; pusMiniVersion
0x180032b38  mov     [rsp+150h+hTransaction], rax; hTransaction
0x180032b3d  mov     [rsp+150h+hTemplateFile], r14; hTemplateFile
0x180032b42  mov     [rsp+150h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180032b4a  mov     [rsp+150h+dwCreationDisposition], 3; dwCreationDisposition
0x180032b52  xor     r9d, r9d; lpSecurityAttributes
0x180032b55  xor     r8d, r8d; dwShareMode
0x180032b58  mov     edx, 80000000h; dwDesiredAccess
0x180032b5d  call    cs:__imp_CreateFileTransactedW
0x180032b63  mov     rbx, rax
0x180032b66  mov     [rsp+150h+var_D8], rax
0x180032b6b  mov     edx, r14d
0x180032b6e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180032b72  setz    dl
0x180032b75  lea     rcx, [rsp+150h+var_F0]
0x180032b7a  call    ?make_winerror_if@@YA?AV?$scoped_error@Utag@winerror_error@@@errorlib@@H@Z; make_winerror_if(int)
0x180032b7f  mov     rdx, rax
0x180032b82  lea     rcx, [rsp+150h+var_F8]
0x180032b87  call    ??4?$scoped_error@Utag@ntstatus_error@@@errorlib@@QEAAAEAV01@V01@@Z; errorlib::scoped_error<ntstatus_error::tag>::operator=(errorlib::scoped_error<ntstatus_error::tag>)
0x180032b8c  mov     [rsp+150h+var_F4], 3
0x180032b94  cmp     [rsp+150h+var_F8], r14d
0x180032b99  jnz     loc_180032DD3
0x180032b9f  mov     qword ptr [rsp+150h+FileSize], r14
0x180032ba4  lea     rdx, [rsp+150h+FileSize]; lpFileSize
0x180032ba9  mov     rcx, rbx; hFile
0x180032bac  call    cs:__imp_GetFileSizeEx
0x180032bb2  mov     edx, r14d
0x180032bb5  test    eax, eax
0x180032bb7  setz    dl
0x180032bba  lea     rcx, [rsp+150h+var_F0]
0x180032bbf  call    ?make_winerror_if@@YA?AV?$scoped_error@Utag@winerror_error@@@errorlib@@H@Z; make_winerror_if(int)
0x180032bc4  mov     rdx, rax
0x180032bc7  lea     rcx, [rsp+150h+var_F8]
0x180032bcc  call    ??4?$scoped_error@Utag@ntstatus_error@@@errorlib@@QEAAAEAV01@V01@@Z; errorlib::scoped_error<ntstatus_error::tag>::operator=(errorlib::scoped_error<ntstatus_error::tag>)
0x180032bd1  mov     [rsp+150h+var_F4], 3
0x180032bd9  cmp     [rsp+150h+var_F8], r14d
0x180032bde  jnz     loc_180032D62
0x180032be4  cmp     dword ptr [rsp+150h+FileSize+4], r14d
0x180032be9  jnz     loc_180032CD1
0x180032bef  cmp     dword ptr [rsp+150h+FileSize], 100000h
0x180032bf7  ja      loc_180032CD1
0x180032bfd  mov     [rbp+50h+NumberOfBytesRead], r14d
0x180032c01  mov     edx, dword ptr [rsp+150h+FileSize]
0x180032c05  lea     rcx, [rbp+50h+lpBuffer]
0x180032c09  call    ?resize@?$vector@EV?$allocator@E@std@@@std@@QEAAX_K@Z; std::vector<uchar>::resize(unsigned __int64)
0x180032c0e  mov     r8d, dword ptr [rbp+50h+lpBuffer+8]
0x180032c12  mov     rdx, [rbp+50h+lpBuffer]; lpBuffer
0x180032c16  sub     r8d, edx; nNumberOfBytesToRead
0x180032c19  mov     qword ptr [rsp+150h+dwCreationDisposition], r14; lpOverlapped
0x180032c1e  lea     r9, [rbp+50h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180032c22  mov     rcx, rbx; hFile
0x180032c25  call    cs:__imp_ReadFile
0x180032c2b  mov     edx, r14d
0x180032c2e  test    eax, eax
0x180032c30  setz    dl
0x180032c33  lea     rcx, [rsp+150h+var_F0]
0x180032c38  call    ?make_winerror_if@@YA?AV?$scoped_error@Utag@winerror_error@@@errorlib@@H@Z; make_winerror_if(int)
0x180032c3d  mov     rdx, rax
0x180032c40  lea     rcx, [rsp+150h+var_F8]
0x180032c45  call    ??4?$scoped_error@Utag@ntstatus_error@@@errorlib@@QEAAAEAV01@V01@@Z; errorlib::scoped_error<ntstatus_error::tag>::operator=(errorlib::scoped_error<ntstatus_error::tag>)
0x180032c4a  mov     [rsp+150h+var_F4], 3
0x180032c52  cmp     [rsp+150h+var_F8], r14d
0x180032c57  jz      loc_180032E50
0x180032c5d  xor     edx, edx; Val
0x180032c5f  lea     r8d, [rdx+40h]; Size
0x180032c63  lea     rcx, [rbp+50h+var_70]; void *
0x180032c67  call    memset_0
0x180032c6c  call    ?Indent@ReportIndentTracker@@SAJXZ; ReportIndentTracker::Indent(void)
0x180032c71  lea     rcx, [rbp+50h+var_70]
0x180032c75  mov     [rsp+150h+var_F0], rcx
0x180032c7a  lea     rcx, [rbp+50h+var_30]
0x180032c7e  mov     [rsp+150h+var_E8], rcx
0x180032c83  mov     r9b, 5Fh ; '_'
0x180032c86  mov     edx, eax
0x180032c88  lea     rcx, [rsp+150h+var_F0]
0x180032c8d  call    ?Format@ReportIndentTracker@@SAXV?$range@PEAD@rangelib@@JDD@Z; ReportIndentTracker::Format(rangelib::range<char *>,long,char,char)
0x180032c92  lea     rax, WPP_GLOBAL_Control
0x180032c99  mov     rcx, cs:WPP_GLOBAL_Control
0x180032ca0  cmp     rcx, rax
0x180032ca3  jz      loc_180032E50
0x180032ca9  test    byte ptr [rcx+1Ch], 1
0x180032cad  jz      loc_180032E50
0x180032cb3  cmp     byte ptr [rcx+19h], 2
0x180032cb7  jb      loc_180032E50
0x180032cbd  cmp     qword ptr [rdi+18h], 8
0x180032cc2  jb      short loc_180032CC7
0x180032cc4  mov     rdi, [rdi]
0x180032cc7  mov     edx, 27h ; '''
0x180032ccc  jmp     loc_180032E36
0x180032cd1  xor     edx, edx; Val
0x180032cd3  lea     r8d, [rdx+40h]; Size
0x180032cd7  lea     rcx, [rbp+50h+var_70]; void *
0x180032cdb  call    memset_0
0x180032ce0  call    ?Indent@ReportIndentTracker@@SAJXZ; ReportIndentTracker::Indent(void)
0x180032ce5  lea     rcx, [rbp+50h+var_70]
0x180032ce9  mov     [rsp+150h+var_F0], rcx
0x180032cee  lea     rcx, [rbp+50h+var_30]
0x180032cf2  mov     [rsp+150h+var_E8], rcx
0x180032cf7  mov     r9b, 5Fh ; '_'
0x180032cfa  mov     edx, eax
0x180032cfc  lea     rcx, [rsp+150h+var_F0]
0x180032d01  call    ?Format@ReportIndentTracker@@SAXV?$range@PEAD@rangelib@@JDD@Z; ReportIndentTracker::Format(rangelib::range<char *>,long,char,char)
0x180032d06  lea     rax, WPP_GLOBAL_Control
0x180032d0d  mov     rcx, cs:WPP_GLOBAL_Control
0x180032d14  cmp     rcx, rax
0x180032d17  jz      short loc_180032D46
0x180032d19  test    byte ptr [rcx+1Ch], 1
0x180032d1d  jz      short loc_180032D46
0x180032d1f  cmp     byte ptr [rcx+19h], 2
0x180032d23  jb      short loc_180032D46
0x180032d25  cmp     qword ptr [rdi+18h], 8
0x180032d2a  jb      short loc_180032D2F
0x180032d2c  mov     rdi, [rdi]
0x180032d2f  mov     edx, 26h ; '&'
0x180032d34  mov     qword ptr [rsp+150h+dwCreationDisposition], rdi
0x180032d39  lea     r9, [rbp+50h+var_70]
0x180032d3d  mov     rcx, [rcx+10h]
0x180032d41  call    WPP_SF_sS
0x180032d46  mov     dword ptr [rsp+150h+var_F0], 0DFh
0x180032d4e  lea     rdx, [rsp+150h+var_F0]
0x180032d53  lea     rcx, [rsp+150h+var_F8]
0x180032d58  call    ??$initiate@J@?$scoped_error@Utag@winerror_error@@@errorlib@@QEAAAEAV01@$$QEAJ@Z; errorlib::scoped_error<winerror_error::tag>::initiate<long>(long &&)
0x180032d5d  jmp     loc_180032E50
0x180032d62  xor     edx, edx; Val
0x180032d64  lea     r8d, [rdx+40h]; Size
0x180032d68  lea     rcx, [rbp+50h+var_70]; void *
0x180032d6c  call    memset_0
0x180032d71  call    ?Indent@ReportIndentTracker@@SAJXZ; ReportIndentTracker::Indent(void)
0x180032d76  lea     rcx, [rbp+50h+var_70]
0x180032d7a  mov     [rsp+150h+var_F0], rcx
0x180032d7f  lea     rcx, [rbp+50h+var_30]
0x180032d83  mov     [rsp+150h+var_E8], rcx
0x180032d88  mov     r9b, 5Fh ; '_'
0x180032d8b  mov     edx, eax
0x180032d8d  lea     rcx, [rsp+150h+var_F0]
0x180032d92  call    ?Format@ReportIndentTracker@@SAXV?$range@PEAD@rangelib@@JDD@Z; ReportIndentTracker::Format(rangelib::range<char *>,long,char,char)
0x180032d97  lea     rax, WPP_GLOBAL_Control
0x180032d9e  mov     rcx, cs:WPP_GLOBAL_Control
0x180032da5  cmp     rcx, rax
0x180032da8  jz      loc_180032E50
0x180032dae  test    byte ptr [rcx+1Ch], 1
0x180032db2  jz      loc_180032E50
0x180032db8  cmp     byte ptr [rcx+19h], 2
0x180032dbc  jb      loc_180032E50
0x180032dc2  cmp     qword ptr [rdi+18h], 8
0x180032dc7  jb      short loc_180032DCC
0x180032dc9  mov     rdi, [rdi]
0x180032dcc  mov     edx, 25h ; '%'
0x180032dd1  jmp     short loc_180032E36
0x180032dd3  xor     edx, edx; Val
0x180032dd5  lea     r8d, [rdx+40h]; Size
0x180032dd9  lea     rcx, [rbp+50h+var_70]; void *
0x180032ddd  call    memset_0
0x180032de2  call    ?Indent@ReportIndentTracker@@SAJXZ; ReportIndentTracker::Indent(void)
0x180032de7  lea     rcx, [rbp+50h+var_70]
0x180032deb  mov     [rsp+150h+var_F0], rcx
0x180032df0  lea     rcx, [rbp+50h+var_30]
0x180032df4  mov     [rsp+150h+var_E8], rcx
0x180032df9  mov     r9b, 5Fh ; '_'
0x180032dfc  mov     edx, eax
0x180032dfe  lea     rcx, [rsp+150h+var_F0]
0x180032e03  call    ?Format@ReportIndentTracker@@SAXV?$range@PEAD@rangelib@@JDD@Z; ReportIndentTracker::Format(rangelib::range<char *>,long,char,char)
0x180032e08  lea     rax, WPP_GLOBAL_Control
0x180032e0f  mov     rcx, cs:WPP_GLOBAL_Control
0x180032e16  cmp     rcx, rax
0x180032e19  jz      short loc_180032E50
0x180032e1b  test    byte ptr [rcx+1Ch], 1
0x180032e1f  jz      short loc_180032E50
0x180032e21  cmp     byte ptr [rcx+19h], 2
0x180032e25  jb      short loc_180032E50
0x180032e27  cmp     qword ptr [rdi+18h], 8
0x180032e2c  jb      short loc_180032E31
0x180032e2e  mov     rdi, [rdi]
0x180032e31  mov     edx, 24h ; '$'
0x180032e36  mov     qword ptr [rsp+150h+dwFlagsAndAttributes], rdi
0x180032e3b  mov     eax, [rsp+150h+var_F8]
0x180032e3f  mov     [rsp+150h+dwCreationDisposition], eax
0x180032e43  lea     r9, [rbp+50h+var_70]
0x180032e47  mov     rcx, [rcx+10h]
0x180032e4b  call    WPP_SF_sDS
0x180032e50  lea     r8, [rbp+50h+lpBuffer]
0x180032e54  lea     rdx, [rsp+150h+var_F8]
0x180032e59  mov     rcx, rsi
0x180032e5c  call    ??$?0AEAV?$scoped_error@Utag@winerror_error@@@errorlib@@V?$vector@EV?$allocator@E@std@@@std@@@?$tuple@V?$scoped_error@Utag@winerror_error@@@errorlib@@V?$vector@EV?$allocator@E@std@@@std@@U_Nil@tr1@4@U564@U564@U564@U564@U564@U564@U564@@tr1@std@@QEAA@AEAV?$scoped_error@Utag@winerror_error@@@errorlib@@$$QEAV?$vector@EV?$allocator@E@std@@@2@@Z; std::tr1::tuple<errorlib::scoped_error<winerror_error::tag>,std::vector<uchar>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>::tuple<errorlib::scoped_error<winerror_error::tag>,std::vector<uchar>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>(errorlib::scoped_error<winerror_error::tag> &,std::vector<uchar> &&)
0x180032e61  nop
0x180032e62  lea     rcx, [rsp+150h+var_D8]
0x180032e67  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180032e6c  nop
0x180032e6d  lea     rcx, [rbp+50h+var_C8]
0x180032e71  call    wil__details__ScopeExitFnGuard_std__tr1__reference_wrapper__lambda_d8fc33e9fc6915260a8ac659ebcfefcc_______operator__
0x180032e76  nop
0x180032e77  lea     rcx, [rbp+50h+lpBuffer]
0x180032e7b  call    ??1?$vector@U_CRYPTOAPI_BLOB@@V?$allocator@U_CRYPTOAPI_BLOB@@@std@@@std@@QEAA@XZ; std::vector<_CRYPTOAPI_BLOB>::~vector<_CRYPTOAPI_BLOB>(void)
0x180032e80  nop
0x180032e81  lea     rcx, [rsp+150h+var_F8]
0x180032e86  call    ??1?$scoped_error@Utag@winerror_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(void)
0x180032e8b  mov     rax, rsi
0x180032e8e  mov     rcx, [rbp+50h+var_30]
0x180032e92  xor     rcx, rsp; StackCookie
0x180032e95  call    __security_check_cookie
0x180032e9a  add     rsp, 130h
0x180032ea1  pop     r14
0x180032ea3  pop     rdi
0x180032ea4  pop     rsi
0x180032ea5  pop     rbx
0x180032ea6  pop     rbp
0x180032ea7  retn
```
