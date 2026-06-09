# FileSystem::DiskOperations::CreateDirectoryOnDisk(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,void * const &)

- ea: `0x18002fae4`
- end: `0x18002fd0b`
- name: `?CreateDirectoryOnDisk@DiskOperations@FileSystem@@SA?AV?$scoped_error@Utag@winerror_error@@@errorlib@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBQEAX@Z`
- size: `551`
- prototype: ``
- caller_count: `4`
- callee_count: `12`
- tags: `file_ops`

## callers

- `0x18002ff8c`
- `0x18003365c`
- `0x180033e14`
- `0x1800344c4`

## callees

- `0x1800081bc`
- `0x180008d24`
- `0x180009a5c`
- `0x180009e14`
- `0x18001e778`
- `0x180024478`
- `0x18002c5fc`
- `0x18002f2d0`
- `0x18002fae4`
- `0x18003aeb0`
- `0x1800586c6`
- `0x180058700`

## import_xrefs

- `KERNEL32!CreateDirectoryTransactedW` at `0x18002fb5a`
- `KERNEL32!CreateDirectoryTransactedW` at `0x18002fb5a`
- `KERNEL32!SetFileAttributesTransactedW` at `0x18002fc39`
- `KERNEL32!SetFileAttributesTransactedW` at `0x18002fc39`

## pseudocode

```c
_DWORD *__fastcall FileSystem::DiskOperations::CreateDirectoryOnDisk(_DWORD *a1, const WCHAR *a2, HANDLE *a3)
{
  bool v6; // cf
  const WCHAR *v7; // rdx
  BOOL DirectoryTransactedW; // eax
  __int64 winerror_if; // rax
  bool v10; // zf
  const WCHAR *v11; // rcx
  unsigned int v12; // eax
  __int64 v13; // r9
  __int64 v14; // r8
  int v15; // r8d
  BOOL v16; // eax
  __int64 v17; // rax
  unsigned int v18; // eax
  __int64 v19; // r9
  __int64 v20; // r8
  char v22; // [rsp+30h] [rbp-59h] BYREF
  _BYTE *v23; // [rsp+40h] [rbp-49h] BYREF
  _QWORD *v24; // [rsp+48h] [rbp-41h]
  _QWORD *v25; // [rsp+50h] [rbp-39h] BYREF
  __int16 v26; // [rsp+58h] [rbp-31h]
  _QWORD v27[4]; // [rsp+60h] [rbp-29h] BYREF
  _BYTE v28[64]; // [rsp+80h] [rbp-9h] BYREF
  _QWORD v29[4]; // [rsp+C0h] [rbp+37h] BYREF

  errorlib::scoped_error<winerror_error::tag>::scoped_error<winerror_error::tag>(a1);
  v22 = 1;
  v27[0] = &v22;
  v27[1] = a2;
  v27[2] = a1;
  lambda_7fbc19f2da433063a17a52909642c4da_::operator()(v27);
  v6 = *((_QWORD *)a2 + 3) < 8u;
  v25 = v27;
  v22 = 0;
  v26 = 258;
  if ( v6 )
    v7 = a2;
  else
    v7 = *(const WCHAR **)a2;
  DirectoryTransactedW = CreateDirectoryTransactedW(0, v7, 0, *a3);
  winerror_if = make_winerror_if(&v23, !DirectoryTransactedW);
  errorlib::scoped_error<ntstatus_error::tag>::operator=(a1, winerror_if);
  v10 = *a1 == 0;
  a1[1] = 3;
  if ( v10 )
    goto LABEL_7;
  if ( *a1 == 183 )
  {
    LODWORD(v23) = 0;
    errorlib::scoped_error<winerror_error::tag>::initiate<long>(a1, &v23);
LABEL_7:
    if ( *((_QWORD *)a2 + 3) < 8u )
      v11 = a2;
    else
      v11 = *(const WCHAR **)a2;
    v16 = SetFileAttributesTransactedW(v11, 6u, *a3);
    v17 = make_winerror_if(&v23, !v16);
    errorlib::scoped_error<ntstatus_error::tag>::operator=(a1, v17);
    v10 = *a1 == 0;
    a1[1] = 3;
    if ( !v10 )
    {
      memset_0(v28, 0, sizeof(v28));
      v18 = ReportIndentTracker::Indent();
      LOBYTE(v19) = 95;
      v23 = v28;
      v24 = v29;
      ReportIndentTracker::Format(&v23, v18, v20, v19);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        if ( *((_QWORD *)a2 + 3) >= 8u )
          a2 = *(const WCHAR **)a2;
        WPP_SF_sDS(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, *a1, (unsigned int)v28, *a1, (__int64)a2);
      }
    }
    goto LABEL_23;
  }
  memset_0(v28, 0, sizeof(v28));
  v12 = ReportIndentTracker::Indent();
  LOBYTE(v13) = 95;
  v23 = v28;
  v24 = v29;
  ReportIndentTracker::Format(&v23, v12, v14, v13);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    if ( *((_QWORD *)a2 + 3) >= 8u )
      a2 = *(const WCHAR **)a2;
    WPP_SF_sDS(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, v15, (unsigned int)v28, *a1, (__int64)a2);
  }
LABEL_23:
  wil::details::ScopeExitFnGuard_std::tr1::reference_wrapper__lambda_7fbc19f2da433063a17a52909642c4da_____::operator()(&v25);
  return a1;
}

```

## disassembly

```asm
0x18002fae4  mov     [rsp-8+arg_18], rbx
0x18002fae9  push    rbp
0x18002faea  push    rsi
0x18002faeb  push    rdi
0x18002faec  lea     rbp, [rsp-47h]
0x18002faf1  sub     rsp, 0D0h
0x18002faf8  mov     rax, cs:__security_cookie
0x18002faff  xor     rax, rsp
0x18002fb02  mov     [rbp+57h+var_20], rax
0x18002fb06  mov     rsi, r8
0x18002fb09  mov     rbx, rdx
0x18002fb0c  mov     rdi, rcx
0x18002fb0f  call    ??0?$scoped_error@Utag@winerror_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<winerror_error::tag>::scoped_error<winerror_error::tag>(void)
0x18002fb14  lea     rax, [rbp+57h+var_B0]
0x18002fb18  mov     [rbp+57h+var_B0], 1
0x18002fb1c  lea     rcx, [rbp+57h+var_80]
0x18002fb20  mov     [rbp+57h+var_80], rax
0x18002fb24  mov     [rbp+57h+var_78], rbx
0x18002fb28  mov     [rbp+57h+var_70], rdi
0x18002fb2c  call    _lambda_7fbc19f2da433063a17a52909642c4da___operator__
0x18002fb31  cmp     qword ptr [rbx+18h], 8
0x18002fb36  lea     rax, [rbp+57h+var_80]
0x18002fb3a  mov     [rbp+57h+var_90], rax
0x18002fb3e  mov     [rbp+57h+var_B0], 0
0x18002fb42  mov     [rbp+57h+var_88], 102h
0x18002fb48  jb      short loc_18002FB4F
0x18002fb4a  mov     rdx, [rbx]
0x18002fb4d  jmp     short loc_18002FB52
0x18002fb4f  mov     rdx, rbx; lpNewDirectory
0x18002fb52  mov     r9, [rsi]; hTransaction
0x18002fb55  xor     r8d, r8d; lpSecurityAttributes
0x18002fb58  xor     ecx, ecx; lpTemplateDirectory
0x18002fb5a  call    cs:__imp_CreateDirectoryTransactedW
0x18002fb60  xor     edx, edx
0x18002fb62  lea     rcx, [rbp+57h+var_A0]
0x18002fb66  test    eax, eax
0x18002fb68  setz    dl
0x18002fb6b  call    ?make_winerror_if@@YA?AV?$scoped_error@Utag@winerror_error@@@errorlib@@H@Z; make_winerror_if(int)
0x18002fb70  mov     rdx, rax
0x18002fb73  mov     rcx, rdi
0x18002fb76  call    ??4?$scoped_error@Utag@ntstatus_error@@@errorlib@@QEAAAEAV01@V01@@Z; errorlib::scoped_error<ntstatus_error::tag>::operator=(errorlib::scoped_error<ntstatus_error::tag>)
0x18002fb7b  cmp     dword ptr [rdi], 0
0x18002fb7e  mov     dword ptr [rdi+4], 3
0x18002fb85  jz      short loc_18002FBA2
0x18002fb87  cmp     dword ptr [rdi], 0B7h
0x18002fb8d  jnz     short loc_18002FBB2
0x18002fb8f  lea     rdx, [rbp+57h+var_A0]
0x18002fb93  mov     dword ptr [rbp+57h+var_A0], 0
0x18002fb9a  mov     rcx, rdi
0x18002fb9d  call    ??$initiate@J@?$scoped_error@Utag@winerror_error@@@errorlib@@QEAAAEAV01@$$QEAJ@Z; errorlib::scoped_error<winerror_error::tag>::initiate<long>(long &&)
0x18002fba2  cmp     qword ptr [rbx+18h], 8
0x18002fba7  jb      loc_18002FC2E
0x18002fbad  mov     rcx, [rbx]
0x18002fbb0  jmp     short loc_18002FC31
0x18002fbb2  xor     edx, edx; Val
0x18002fbb4  lea     rcx, [rbp+57h+var_60]; void *
0x18002fbb8  lea     r8d, [rdx+40h]; Size
0x18002fbbc  call    memset_0
0x18002fbc1  call    ?Indent@ReportIndentTracker@@SAJXZ; ReportIndentTracker::Indent(void)
0x18002fbc6  lea     rcx, [rbp+57h+var_60]
0x18002fbca  mov     r9b, 5Fh ; '_'
0x18002fbcd  mov     [rbp+57h+var_A0], rcx
0x18002fbd1  mov     edx, eax
0x18002fbd3  lea     rcx, [rbp+57h+var_20]
0x18002fbd7  mov     [rbp+57h+var_98], rcx
0x18002fbdb  lea     rcx, [rbp+57h+var_A0]
0x18002fbdf  call    ?Format@ReportIndentTracker@@SAXV?$range@PEAD@rangelib@@JDD@Z; ReportIndentTracker::Format(rangelib::range<char *>,long,char,char)
0x18002fbe4  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fbeb  lea     rax, WPP_GLOBAL_Control
0x18002fbf2  cmp     rcx, rax
0x18002fbf5  jz      loc_18002FCE0
0x18002fbfb  test    byte ptr [rcx+1Ch], 1
0x18002fbff  jz      loc_18002FCE0
0x18002fc05  cmp     byte ptr [rcx+19h], 2
0x18002fc09  jb      loc_18002FCE0
0x18002fc0f  cmp     qword ptr [rbx+18h], 8
0x18002fc14  jb      short loc_18002FC19
0x18002fc16  mov     rbx, [rbx]
0x18002fc19  mov     eax, [rdi]
0x18002fc1b  mov     edx, 1Eh
0x18002fc20  mov     [rsp+0E0h+var_B8], rbx
0x18002fc25  mov     [rsp+0E0h+var_C0], eax
0x18002fc29  jmp     loc_18002FCD3
0x18002fc2e  mov     rcx, rbx; lpFileName
0x18002fc31  mov     r8, [rsi]; hTransaction
0x18002fc34  mov     edx, 6; dwFileAttributes
0x18002fc39  call    cs:__imp_SetFileAttributesTransactedW
0x18002fc3f  xor     edx, edx
0x18002fc41  lea     rcx, [rbp+57h+var_A0]
0x18002fc45  test    eax, eax
0x18002fc47  setz    dl
0x18002fc4a  call    ?make_winerror_if@@YA?AV?$scoped_error@Utag@winerror_error@@@errorlib@@H@Z; make_winerror_if(int)
0x18002fc4f  mov     rdx, rax
0x18002fc52  mov     rcx, rdi
0x18002fc55  call    ??4?$scoped_error@Utag@ntstatus_error@@@errorlib@@QEAAAEAV01@V01@@Z; errorlib::scoped_error<ntstatus_error::tag>::operator=(errorlib::scoped_error<ntstatus_error::tag>)
0x18002fc5a  cmp     dword ptr [rdi], 0
0x18002fc5d  mov     dword ptr [rdi+4], 3
0x18002fc64  jz      short loc_18002FCE0
0x18002fc66  xor     edx, edx; Val
0x18002fc68  lea     rcx, [rbp+57h+var_60]; void *
0x18002fc6c  lea     r8d, [rdx+40h]; Size
0x18002fc70  call    memset_0
0x18002fc75  call    ?Indent@ReportIndentTracker@@SAJXZ; ReportIndentTracker::Indent(void)
0x18002fc7a  lea     rcx, [rbp+57h+var_60]
0x18002fc7e  mov     r9b, 5Fh ; '_'
0x18002fc81  mov     [rbp+57h+var_A0], rcx
0x18002fc85  mov     edx, eax
0x18002fc87  lea     rcx, [rbp+57h+var_20]
0x18002fc8b  mov     [rbp+57h+var_98], rcx
0x18002fc8f  lea     rcx, [rbp+57h+var_A0]
0x18002fc93  call    ?Format@ReportIndentTracker@@SAXV?$range@PEAD@rangelib@@JDD@Z; ReportIndentTracker::Format(rangelib::range<char *>,long,char,char)
0x18002fc98  mov     rcx, cs:WPP_GLOBAL_Control
0x18002fc9f  lea     rax, WPP_GLOBAL_Control
0x18002fca6  cmp     rcx, rax
0x18002fca9  jz      short loc_18002FCE0
0x18002fcab  test    byte ptr [rcx+1Ch], 1
0x18002fcaf  jz      short loc_18002FCE0
0x18002fcb1  cmp     byte ptr [rcx+19h], 2
0x18002fcb5  jb      short loc_18002FCE0
0x18002fcb7  cmp     qword ptr [rbx+18h], 8
0x18002fcbc  jb      short loc_18002FCC1
0x18002fcbe  mov     rbx, [rbx]
0x18002fcc1  mov     r8d, [rdi]
0x18002fcc4  mov     edx, 1Fh
0x18002fcc9  mov     [rsp+0E0h+var_B8], rbx
0x18002fcce  mov     [rsp+0E0h+var_C0], r8d
0x18002fcd3  mov     rcx, [rcx+10h]
0x18002fcd7  lea     r9, [rbp+57h+var_60]
0x18002fcdb  call    WPP_SF_sDS
0x18002fce0  lea     rcx, [rbp+57h+var_90]
0x18002fce4  call    wil__details__ScopeExitFnGuard_std__tr1__reference_wrapper__lambda_7fbc19f2da433063a17a52909642c4da_______operator__
0x18002fce9  mov     rax, rdi
0x18002fcec  mov     rcx, [rbp+57h+var_20]
0x18002fcf0  xor     rcx, rsp; StackCookie
0x18002fcf3  call    __security_check_cookie
0x18002fcf8  mov     rbx, [rsp+0E0h+arg_18]
0x18002fd00  add     rsp, 0D0h
0x18002fd07  pop     rdi
0x18002fd08  pop     rsi
0x18002fd09  pop     rbp
0x18002fd0a  retn
```
