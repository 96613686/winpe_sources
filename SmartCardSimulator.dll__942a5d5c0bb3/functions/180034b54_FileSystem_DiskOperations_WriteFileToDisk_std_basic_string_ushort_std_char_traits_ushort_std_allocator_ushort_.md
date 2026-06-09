# FileSystem::DiskOperations::WriteFileToDisk(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,rangelib::range<uchar const *>,void * const &)

- ea: `0x180034b54`
- end: `0x180034db4`
- name: `?WriteFileToDisk@DiskOperations@FileSystem@@SA?AV?$scoped_error@Utag@winerror_error@@@errorlib@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$range@PEBE@rangelib@@AEBQEAX@Z`
- size: `608`
- prototype: ``
- caller_count: `3`
- callee_count: `12`
- tags: `file_ops, registry_config`

## callers

- `0x18003365c`
- `0x180033e14`
- `0x1800344c4`

## callees

- `0x1800081bc`
- `0x180008d24`
- `0x180009a5c`
- `0x180009e14`
- `0x18001ee28`
- `0x180024478`
- `0x18002a9b4`
- `0x18002ef08`
- `0x180034b54`
- `0x18003aeb0`
- `0x1800586c6`
- `0x180058700`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180034c61`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180034c61`
- `KERNEL32!CreateFileTransactedW` at `0x180034c06`
- `KERNEL32!CreateFileTransactedW` at `0x180034c06`

## pseudocode

```c
_DWORD *__fastcall FileSystem::DiskOperations::WriteFileToDisk(_DWORD *a1, const WCHAR *a2, _DWORD *a3, void **a4)
{
  bool v8; // cf
  void *hTransaction; // rax
  const WCHAR *v10; // rcx
  void *v11; // rbx
  __int64 winerror_if; // rax
  bool v13; // zf
  DWORD v14; // r8d
  const void *v15; // rdx
  BOOL v16; // eax
  __int64 v17; // rax
  unsigned int v18; // eax
  __int64 v19; // r9
  __int64 v20; // r8
  int v21; // r8d
  unsigned int v22; // eax
  __int64 v23; // r9
  __int64 v24; // r8
  char v26; // [rsp+50h] [rbp-79h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+54h] [rbp-75h] BYREF
  _BYTE *v28; // [rsp+60h] [rbp-69h] BYREF
  _QWORD *v29; // [rsp+68h] [rbp-61h]
  char *FileTransactedW; // [rsp+70h] [rbp-59h] BYREF
  _QWORD *v31; // [rsp+78h] [rbp-51h] BYREF
  __int16 v32; // [rsp+80h] [rbp-49h]
  _QWORD v33[5]; // [rsp+88h] [rbp-41h] BYREF
  _BYTE v34[64]; // [rsp+B0h] [rbp-19h] BYREF
  _QWORD v35[6]; // [rsp+F0h] [rbp+27h] BYREF

  errorlib::scoped_error<winerror_error::tag>::scoped_error<winerror_error::tag>(a1);
  v26 = 1;
  v33[0] = &v26;
  v33[1] = a2;
  v33[2] = a3;
  v33[3] = a1;
  lambda_12d5cdbfedd147e98a3e351a317ceb16_::operator()(v33);
  v8 = *((_QWORD *)a2 + 3) < 8u;
  v31 = v33;
  hTransaction = *a4;
  v26 = 0;
  v32 = 258;
  if ( v8 )
    v10 = a2;
  else
    v10 = *(const WCHAR **)a2;
  FileTransactedW = (char *)CreateFileTransactedW(v10, 0x40000000u, 0, 0, 2u, 6u, 0, hTransaction, 0, 0);
  v11 = FileTransactedW;
  winerror_if = make_winerror_if(&v28, FileTransactedW + 1 == 0);
  errorlib::scoped_error<ntstatus_error::tag>::operator=(a1, winerror_if);
  v13 = *a1 == 0;
  a1[1] = 3;
  if ( v13 )
  {
    v14 = a3[2] - *a3;
    v15 = *(const void **)a3;
    NumberOfBytesWritten = 0;
    v16 = WriteFile(v11, v15, v14, &NumberOfBytesWritten, 0);
    v17 = make_winerror_if(&v28, !v16);
    errorlib::scoped_error<ntstatus_error::tag>::operator=(a1, v17);
    v13 = *a1 == 0;
    a1[1] = 3;
    if ( !v13 )
    {
      memset_0(v34, 0, sizeof(v34));
      v18 = ReportIndentTracker::Indent();
      LOBYTE(v19) = 95;
      v28 = v34;
      v29 = v35;
      ReportIndentTracker::Format(&v28, v18, v20, v19);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        if ( *((_QWORD *)a2 + 3) >= 8u )
          a2 = *(const WCHAR **)a2;
        WPP_SF_sDS(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, v21, (unsigned int)v34, *a1, (__int64)a2);
      }
    }
  }
  else
  {
    memset_0(v34, 0, sizeof(v34));
    v22 = ReportIndentTracker::Indent();
    LOBYTE(v23) = 95;
    v28 = v34;
    v29 = v35;
    ReportIndentTracker::Format(&v28, v22, v24, v23);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      if ( *((_QWORD *)a2 + 3) >= 8u )
        a2 = *(const WCHAR **)a2;
      WPP_SF_sDS(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, *a1, (unsigned int)v34, *a1, (__int64)a2);
    }
  }
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&FileTransactedW);
  wil::details::ScopeExitFnGuard_std::tr1::reference_wrapper__lambda_12d5cdbfedd147e98a3e351a317ceb16_____::operator()(&v31);
  return a1;
}

```

## disassembly

```asm
0x180034b54  push    rbp
0x180034b56  push    rbx
0x180034b57  push    rsi
0x180034b58  push    rdi
0x180034b59  push    r14
0x180034b5b  lea     rbp, [rsp-37h]
0x180034b60  sub     rsp, 100h
0x180034b67  mov     rax, cs:__security_cookie
0x180034b6e  xor     rax, rsp
0x180034b71  mov     [rbp+57h+var_30], rax
0x180034b75  mov     rbx, r9
0x180034b78  mov     r14, r8
0x180034b7b  mov     rdi, rdx
0x180034b7e  mov     rsi, rcx
0x180034b81  call    ??0?$scoped_error@Utag@winerror_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<winerror_error::tag>::scoped_error<winerror_error::tag>(void)
0x180034b86  lea     rax, [rbp+57h+var_D0]
0x180034b8a  mov     [rbp+57h+var_D0], 1
0x180034b8e  lea     rcx, [rbp+57h+var_98]
0x180034b92  mov     [rbp+57h+var_98], rax
0x180034b96  mov     [rbp+57h+var_90], rdi
0x180034b9a  mov     [rbp+57h+var_88], r14
0x180034b9e  mov     [rbp+57h+var_80], rsi
0x180034ba2  call    _lambda_12d5cdbfedd147e98a3e351a317ceb16___operator__
0x180034ba7  cmp     qword ptr [rdi+18h], 8
0x180034bac  lea     rax, [rbp+57h+var_98]
0x180034bb0  mov     [rbp+57h+var_A8], rax
0x180034bb4  mov     rax, [rbx]
0x180034bb7  mov     [rbp+57h+var_D0], 0
0x180034bbb  mov     [rbp+57h+var_A0], 102h
0x180034bc1  jb      short loc_180034BC8
0x180034bc3  mov     rcx, [rdi]
0x180034bc6  jmp     short loc_180034BCB
0x180034bc8  mov     rcx, rdi; lpFileName
0x180034bcb  mov     [rsp+120h+lpExtendedParameter], 0; lpExtendedParameter
0x180034bd4  xor     r9d, r9d; lpSecurityAttributes
0x180034bd7  mov     [rsp+120h+pusMiniVersion], 0; pusMiniVersion
0x180034be0  xor     r8d, r8d; dwShareMode
0x180034be3  mov     [rsp+120h+hTransaction], rax; hTransaction
0x180034be8  mov     edx, 40000000h; dwDesiredAccess
0x180034bed  mov     [rsp+120h+hTemplateFile], 0; hTemplateFile
0x180034bf6  mov     [rsp+120h+dwFlagsAndAttributes], 6; dwFlagsAndAttributes
0x180034bfe  mov     [rsp+120h+dwCreationDisposition], 2; dwCreationDisposition
0x180034c06  call    cs:__imp_CreateFileTransactedW
0x180034c0c  xor     edx, edx
0x180034c0e  lea     rcx, [rbp+57h+var_C0]
0x180034c12  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180034c16  mov     [rbp+57h+var_B0], rax
0x180034c1a  mov     rbx, rax
0x180034c1d  setz    dl
0x180034c20  call    ?make_winerror_if@@YA?AV?$scoped_error@Utag@winerror_error@@@errorlib@@H@Z; make_winerror_if(int)
0x180034c25  mov     rdx, rax
0x180034c28  mov     rcx, rsi
0x180034c2b  call    ??4?$scoped_error@Utag@ntstatus_error@@@errorlib@@QEAAAEAV01@V01@@Z; errorlib::scoped_error<ntstatus_error::tag>::operator=(errorlib::scoped_error<ntstatus_error::tag>)
0x180034c30  cmp     dword ptr [rsi], 0
0x180034c33  mov     dword ptr [rsi+4], 3
0x180034c3a  jnz     loc_180034D0B
0x180034c40  mov     r8d, [r14+8]
0x180034c44  lea     r9, [rbp+57h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180034c48  sub     r8d, [r14]; nNumberOfBytesToWrite
0x180034c4b  mov     rcx, rbx; hFile
0x180034c4e  mov     rdx, [r14]; lpBuffer
0x180034c51  mov     [rbp+57h+NumberOfBytesWritten], 0
0x180034c58  mov     qword ptr [rsp+120h+dwCreationDisposition], 0; lpOverlapped
0x180034c61  call    cs:__imp_WriteFile
0x180034c67  xor     edx, edx
0x180034c69  lea     rcx, [rbp+57h+var_C0]
0x180034c6d  test    eax, eax
0x180034c6f  setz    dl
0x180034c72  call    ?make_winerror_if@@YA?AV?$scoped_error@Utag@winerror_error@@@errorlib@@H@Z; make_winerror_if(int)
0x180034c77  mov     rdx, rax
0x180034c7a  mov     rcx, rsi
0x180034c7d  call    ??4?$scoped_error@Utag@ntstatus_error@@@errorlib@@QEAAAEAV01@V01@@Z; errorlib::scoped_error<ntstatus_error::tag>::operator=(errorlib::scoped_error<ntstatus_error::tag>)
0x180034c82  cmp     dword ptr [rsi], 0
0x180034c85  mov     dword ptr [rsi+4], 3
0x180034c8c  jz      loc_180034D85
0x180034c92  xor     edx, edx; Val
0x180034c94  lea     rcx, [rbp+57h+var_70]; void *
0x180034c98  lea     r8d, [rdx+40h]; Size
0x180034c9c  call    memset_0
0x180034ca1  call    ?Indent@ReportIndentTracker@@SAJXZ; ReportIndentTracker::Indent(void)
0x180034ca6  lea     rcx, [rbp+57h+var_70]
0x180034caa  mov     r9b, 5Fh ; '_'
0x180034cad  mov     [rbp+57h+var_C0], rcx
0x180034cb1  mov     edx, eax
0x180034cb3  lea     rcx, [rbp+57h+var_30]
0x180034cb7  mov     [rbp+57h+var_B8], rcx
0x180034cbb  lea     rcx, [rbp+57h+var_C0]
0x180034cbf  call    ?Format@ReportIndentTracker@@SAXV?$range@PEAD@rangelib@@JDD@Z; ReportIndentTracker::Format(rangelib::range<char *>,long,char,char)
0x180034cc4  mov     rcx, cs:WPP_GLOBAL_Control
0x180034ccb  lea     rax, WPP_GLOBAL_Control
0x180034cd2  cmp     rcx, rax
0x180034cd5  jz      loc_180034D85
0x180034cdb  test    byte ptr [rcx+1Ch], 1
0x180034cdf  jz      loc_180034D85
0x180034ce5  cmp     byte ptr [rcx+19h], 2
0x180034ce9  jb      loc_180034D85
0x180034cef  cmp     qword ptr [rdi+18h], 8
0x180034cf4  jb      short loc_180034CF9
0x180034cf6  mov     rdi, [rdi]
0x180034cf9  mov     eax, [rsi]
0x180034cfb  mov     edx, 22h ; '"'
0x180034d00  mov     qword ptr [rsp+120h+dwFlagsAndAttributes], rdi
0x180034d05  mov     [rsp+120h+dwCreationDisposition], eax
0x180034d09  jmp     short loc_180034D78
0x180034d0b  xor     edx, edx; Val
0x180034d0d  lea     rcx, [rbp+57h+var_70]; void *
0x180034d11  lea     r8d, [rdx+40h]; Size
0x180034d15  call    memset_0
0x180034d1a  call    ?Indent@ReportIndentTracker@@SAJXZ; ReportIndentTracker::Indent(void)
0x180034d1f  lea     rcx, [rbp+57h+var_70]
0x180034d23  mov     r9b, 5Fh ; '_'
0x180034d26  mov     [rbp+57h+var_C0], rcx
0x180034d2a  mov     edx, eax
0x180034d2c  lea     rcx, [rbp+57h+var_30]
0x180034d30  mov     [rbp+57h+var_B8], rcx
0x180034d34  lea     rcx, [rbp+57h+var_C0]
0x180034d38  call    ?Format@ReportIndentTracker@@SAXV?$range@PEAD@rangelib@@JDD@Z; ReportIndentTracker::Format(rangelib::range<char *>,long,char,char)
0x180034d3d  mov     rcx, cs:WPP_GLOBAL_Control
0x180034d44  lea     rax, WPP_GLOBAL_Control
0x180034d4b  cmp     rcx, rax
0x180034d4e  jz      short loc_180034D85
0x180034d50  test    byte ptr [rcx+1Ch], 1
0x180034d54  jz      short loc_180034D85
0x180034d56  cmp     byte ptr [rcx+19h], 2
0x180034d5a  jb      short loc_180034D85
0x180034d5c  cmp     qword ptr [rdi+18h], 8
0x180034d61  jb      short loc_180034D66
0x180034d63  mov     rdi, [rdi]
0x180034d66  mov     r8d, [rsi]
0x180034d69  mov     edx, 21h ; '!'
0x180034d6e  mov     qword ptr [rsp+120h+dwFlagsAndAttributes], rdi
0x180034d73  mov     [rsp+120h+dwCreationDisposition], r8d
0x180034d78  mov     rcx, [rcx+10h]
0x180034d7c  lea     r9, [rbp+57h+var_70]
0x180034d80  call    WPP_SF_sDS
0x180034d85  lea     rcx, [rbp+57h+var_B0]
0x180034d89  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180034d8e  lea     rcx, [rbp+57h+var_A8]
0x180034d92  call    wil__details__ScopeExitFnGuard_std__tr1__reference_wrapper__lambda_12d5cdbfedd147e98a3e351a317ceb16_______operator__
0x180034d97  mov     rax, rsi
0x180034d9a  mov     rcx, [rbp+57h+var_30]
0x180034d9e  xor     rcx, rsp; StackCookie
0x180034da1  call    __security_check_cookie
0x180034da6  add     rsp, 100h
0x180034dad  pop     r14
0x180034daf  pop     rdi
0x180034db0  pop     rsi
0x180034db1  pop     rbx
0x180034db2  pop     rbp
0x180034db3  retn
```
