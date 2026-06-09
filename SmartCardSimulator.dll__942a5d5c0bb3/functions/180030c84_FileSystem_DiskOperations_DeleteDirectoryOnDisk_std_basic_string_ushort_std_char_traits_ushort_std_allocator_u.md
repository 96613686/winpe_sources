# FileSystem::DiskOperations::DeleteDirectoryOnDisk(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,void * const &)

- ea: `0x180030c84`
- end: `0x180030e83`
- name: `?DeleteDirectoryOnDisk@DiskOperations@FileSystem@@SA?AV?$scoped_error@Utag@winerror_error@@@errorlib@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBQEAX@Z`
- size: `511`
- prototype: ``
- caller_count: `4`
- callee_count: `12`
- tags: `file_ops`

## callers

- `0x18002cb60`
- `0x1800308c8`
- `0x180030e8c`
- `0x180031370`

## callees

- `0x1800081bc`
- `0x180008d24`
- `0x180009a5c`
- `0x180009e14`
- `0x180024478`
- `0x18002b824`
- `0x18002f118`
- `0x180030c84`
- `0x1800312c4`
- `0x18003aeb0`
- `0x1800586c6`
- `0x180058700`

## import_xrefs

- `KERNEL32!RemoveDirectoryTransactedW` at `0x180030d32`
- `KERNEL32!RemoveDirectoryTransactedW` at `0x180030d32`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_DWORD *__fastcall FileSystem::DiskOperations::DeleteDirectoryOnDisk(_DWORD *a1, const WCHAR *a2, HANDLE *a3)
{
  __int64 v6; // rax
  const WCHAR *v7; // rcx
  BOOL v8; // eax
  __int64 winerror_if; // rax
  unsigned int v10; // eax
  __int64 v11; // r9
  __int64 v12; // r8
  int v13; // r8d
  unsigned int v14; // eax
  __int64 v15; // r9
  __int64 v16; // r8
  char v18; // [rsp+30h] [rbp-69h] BYREF
  _BYTE v19[8]; // [rsp+38h] [rbp-61h] BYREF
  int v20; // [rsp+40h] [rbp-59h]
  _BYTE *v21; // [rsp+50h] [rbp-49h] BYREF
  _QWORD *v22; // [rsp+58h] [rbp-41h]
  _QWORD *v23; // [rsp+60h] [rbp-39h] BYREF
  __int16 v24; // [rsp+68h] [rbp-31h]
  _QWORD v25[4]; // [rsp+70h] [rbp-29h] BYREF
  _BYTE v26[64]; // [rsp+90h] [rbp-9h] BYREF
  _QWORD v27[4]; // [rsp+D0h] [rbp+37h] BYREF

  v21 = a1;
  errorlib::scoped_error<winerror_error::tag>::scoped_error<winerror_error::tag>(a1);
  v20 = 1;
  v18 = 1;
  v25[0] = &v18;
  v25[1] = a2;
  v25[2] = a1;
  lambda_5724caf13d8e406b35a42aa1f75b2bb1_::operator()(v25);
  v18 = 0;
  v23 = v25;
  v24 = 258;
  v6 = FileSystem::DiskOperations::DeleteFilesInDirectory(v19, a2, a3);
  errorlib::scoped_error<ntstatus_error::tag>::operator=(a1, v6);
  a1[1] = 3;
  if ( *a1 )
  {
    memset_0(v26, 0, sizeof(v26));
    v14 = ReportIndentTracker::Indent();
    v21 = v26;
    v22 = v27;
    LOBYTE(v15) = 95;
    ReportIndentTracker::Format(&v21, v14, v16, v15);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      if ( *((_QWORD *)a2 + 3) >= 8u )
        a2 = *(const WCHAR **)a2;
      WPP_SF_sDS(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, *a1, (unsigned int)v26, *a1, (__int64)a2);
    }
  }
  else
  {
    if ( *((_QWORD *)a2 + 3) < 8u )
      v7 = a2;
    else
      v7 = *(const WCHAR **)a2;
    v8 = RemoveDirectoryTransactedW(v7, *a3);
    winerror_if = make_winerror_if(v19, !v8);
    errorlib::scoped_error<ntstatus_error::tag>::operator=(a1, winerror_if);
    a1[1] = 3;
    if ( *a1 )
    {
      memset_0(v26, 0, sizeof(v26));
      v10 = ReportIndentTracker::Indent();
      v21 = v26;
      v22 = v27;
      LOBYTE(v11) = 95;
      ReportIndentTracker::Format(&v21, v10, v12, v11);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        if ( *((_QWORD *)a2 + 3) >= 8u )
          a2 = *(const WCHAR **)a2;
        WPP_SF_sDS(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, v13, (unsigned int)v26, *a1, (__int64)a2);
      }
    }
  }
  wil::details::ScopeExitFnGuard_std::tr1::reference_wrapper__lambda_5724caf13d8e406b35a42aa1f75b2bb1_____::operator()(&v23);
  return a1;
}

```

## disassembly

```asm
0x180030c84  mov     [rsp-8+arg_18], rbx
0x180030c89  push    rbp
0x180030c8a  push    rsi
0x180030c8b  push    rdi
0x180030c8c  lea     rbp, [rsp-47h]
0x180030c91  sub     rsp, 0E0h
0x180030c98  mov     rax, cs:__security_cookie
0x180030c9f  xor     rax, rsp
0x180030ca2  mov     [rbp+57h+var_20], rax
0x180030ca6  mov     rsi, r8
0x180030ca9  mov     rbx, rdx
0x180030cac  mov     rdi, rcx
0x180030caf  mov     [rbp+57h+var_A0], rcx
0x180030cb3  mov     [rbp+57h+var_B0], 1
0x180030cba  call    ??0?$scoped_error@Utag@winerror_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<winerror_error::tag>::scoped_error<winerror_error::tag>(void)
0x180030cbf  nop
0x180030cc0  mov     [rbp+57h+var_B0], 1
0x180030cc7  mov     [rbp+57h+var_C0], 1
0x180030ccb  lea     rax, [rbp+57h+var_C0]
0x180030ccf  mov     [rbp+57h+var_80], rax
0x180030cd3  mov     [rbp+57h+var_78], rbx
0x180030cd7  mov     [rbp+57h+var_70], rdi
0x180030cdb  lea     rcx, [rbp+57h+var_80]
0x180030cdf  call    _lambda_5724caf13d8e406b35a42aa1f75b2bb1___operator__
0x180030ce4  mov     [rbp+57h+var_C0], 0
0x180030ce8  lea     rax, [rbp+57h+var_80]
0x180030cec  mov     [rbp+57h+var_90], rax
0x180030cf0  mov     [rbp+57h+var_88], 102h
0x180030cf6  mov     r8, rsi
0x180030cf9  mov     rdx, rbx
0x180030cfc  lea     rcx, [rbp+57h+var_B8]
0x180030d00  call    ?DeleteFilesInDirectory@DiskOperations@FileSystem@@SA?AV?$scoped_error@Utag@winerror_error@@@errorlib@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBQEAX@Z; FileSystem::DiskOperations::DeleteFilesInDirectory(std::wstring const &,void * const &)
0x180030d05  mov     rdx, rax
0x180030d08  mov     rcx, rdi
0x180030d0b  call    ??4?$scoped_error@Utag@ntstatus_error@@@errorlib@@QEAAAEAV01@V01@@Z; errorlib::scoped_error<ntstatus_error::tag>::operator=(errorlib::scoped_error<ntstatus_error::tag>)
0x180030d10  mov     dword ptr [rdi+4], 3
0x180030d17  cmp     dword ptr [rdi], 0
0x180030d1a  jnz     loc_180030DDC
0x180030d20  cmp     qword ptr [rbx+18h], 8
0x180030d25  jb      short loc_180030D2C
0x180030d27  mov     rcx, [rbx]
0x180030d2a  jmp     short loc_180030D2F
0x180030d2c  mov     rcx, rbx; lpPathName
0x180030d2f  mov     rdx, [rsi]; hTransaction
0x180030d32  call    cs:__imp_RemoveDirectoryTransactedW
0x180030d38  xor     edx, edx
0x180030d3a  test    eax, eax
0x180030d3c  setz    dl
0x180030d3f  lea     rcx, [rbp+57h+var_B8]
0x180030d43  call    ?make_winerror_if@@YA?AV?$scoped_error@Utag@winerror_error@@@errorlib@@H@Z; make_winerror_if(int)
0x180030d48  mov     rdx, rax
0x180030d4b  mov     rcx, rdi
0x180030d4e  call    ??4?$scoped_error@Utag@ntstatus_error@@@errorlib@@QEAAAEAV01@V01@@Z; errorlib::scoped_error<ntstatus_error::tag>::operator=(errorlib::scoped_error<ntstatus_error::tag>)
0x180030d53  mov     dword ptr [rdi+4], 3
0x180030d5a  cmp     dword ptr [rdi], 0
0x180030d5d  jz      loc_180030E57
0x180030d63  xor     edx, edx; Val
0x180030d65  lea     r8d, [rdx+40h]; Size
0x180030d69  lea     rcx, [rbp+57h+var_60]; void *
0x180030d6d  call    memset_0
0x180030d72  call    ?Indent@ReportIndentTracker@@SAJXZ; ReportIndentTracker::Indent(void)
0x180030d77  lea     rcx, [rbp+57h+var_60]
0x180030d7b  mov     [rbp+57h+var_A0], rcx
0x180030d7f  lea     rcx, [rbp+57h+var_20]
0x180030d83  mov     [rbp+57h+var_98], rcx
0x180030d87  mov     r9b, 5Fh ; '_'
0x180030d8a  mov     edx, eax
0x180030d8c  lea     rcx, [rbp+57h+var_A0]
0x180030d90  call    ?Format@ReportIndentTracker@@SAXV?$range@PEAD@rangelib@@JDD@Z; ReportIndentTracker::Format(rangelib::range<char *>,long,char,char)
0x180030d95  lea     rax, WPP_GLOBAL_Control
0x180030d9c  mov     rcx, cs:WPP_GLOBAL_Control
0x180030da3  cmp     rcx, rax
0x180030da6  jz      loc_180030E57
0x180030dac  test    byte ptr [rcx+1Ch], 1
0x180030db0  jz      loc_180030E57
0x180030db6  cmp     byte ptr [rcx+19h], 2
0x180030dba  jb      loc_180030E57
0x180030dc0  cmp     qword ptr [rbx+18h], 8
0x180030dc5  jb      short loc_180030DCA
0x180030dc7  mov     rbx, [rbx]
0x180030dca  mov     edx, 2Dh ; '-'
0x180030dcf  mov     [rsp+0F0h+var_C8], rbx
0x180030dd4  mov     eax, [rdi]
0x180030dd6  mov     [rsp+0F0h+var_D0], eax
0x180030dda  jmp     short loc_180030E49
0x180030ddc  xor     edx, edx; Val
0x180030dde  lea     r8d, [rdx+40h]; Size
0x180030de2  lea     rcx, [rbp+57h+var_60]; void *
0x180030de6  call    memset_0
0x180030deb  call    ?Indent@ReportIndentTracker@@SAJXZ; ReportIndentTracker::Indent(void)
0x180030df0  lea     rcx, [rbp+57h+var_60]
0x180030df4  mov     [rbp+57h+var_A0], rcx
0x180030df8  lea     rcx, [rbp+57h+var_20]
0x180030dfc  mov     [rbp+57h+var_98], rcx
0x180030e00  mov     r9b, 5Fh ; '_'
0x180030e03  mov     edx, eax
0x180030e05  lea     rcx, [rbp+57h+var_A0]
0x180030e09  call    ?Format@ReportIndentTracker@@SAXV?$range@PEAD@rangelib@@JDD@Z; ReportIndentTracker::Format(rangelib::range<char *>,long,char,char)
0x180030e0e  lea     rax, WPP_GLOBAL_Control
0x180030e15  mov     rcx, cs:WPP_GLOBAL_Control
0x180030e1c  cmp     rcx, rax
0x180030e1f  jz      short loc_180030E57
0x180030e21  test    byte ptr [rcx+1Ch], 1
0x180030e25  jz      short loc_180030E57
0x180030e27  cmp     byte ptr [rcx+19h], 2
0x180030e2b  jb      short loc_180030E57
0x180030e2d  cmp     qword ptr [rbx+18h], 8
0x180030e32  jb      short loc_180030E37
0x180030e34  mov     rbx, [rbx]
0x180030e37  mov     edx, 2Ch ; ','
0x180030e3c  mov     [rsp+0F0h+var_C8], rbx
0x180030e41  mov     r8d, [rdi]
0x180030e44  mov     [rsp+0F0h+var_D0], r8d
0x180030e49  lea     r9, [rbp+57h+var_60]
0x180030e4d  mov     rcx, [rcx+10h]
0x180030e51  call    WPP_SF_sDS
0x180030e56  nop
0x180030e57  lea     rcx, [rbp+57h+var_90]
0x180030e5b  call    wil__details__ScopeExitFnGuard_std__tr1__reference_wrapper__lambda_5724caf13d8e406b35a42aa1f75b2bb1_______operator__
0x180030e60  nop
0x180030e61  mov     rax, rdi
0x180030e64  mov     rcx, [rbp+57h+var_20]
0x180030e68  xor     rcx, rsp; StackCookie
0x180030e6b  call    __security_check_cookie
0x180030e70  mov     rbx, [rsp+0F0h+arg_18]
0x180030e78  add     rsp, 0E0h
0x180030e7f  pop     rdi
0x180030e80  pop     rsi
0x180030e81  pop     rbp
0x180030e82  retn
```
