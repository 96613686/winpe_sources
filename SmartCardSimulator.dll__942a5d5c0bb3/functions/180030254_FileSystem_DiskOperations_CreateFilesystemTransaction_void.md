# FileSystem::DiskOperations::CreateFilesystemTransaction(void)

- ea: `0x180030254`
- end: `0x1800303c4`
- name: `?CreateFilesystemTransaction@DiskOperations@FileSystem@@SA?AV?$tuple@V?$scoped_error@Utag@winerror_error@@@errorlib@@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@U_Nil@tr1@std@@U567@U567@U567@U567@U567@U567@U567@@tr1@std@@XZ`
- size: `368`
- prototype: ``
- caller_count: `9`
- callee_count: `14`
- tags: `file_ops, registry_config`

## callers

- `0x18002ff8c`
- `0x1800303cc`
- `0x1800308c8`
- `0x180030e8c`
- `0x180031370`
- `0x180033048`
- `0x18003365c`
- `0x180033e14`
- `0x1800344c4`

## callees

- `0x1800081bc`
- `0x1800089e8`
- `0x180008d24`
- `0x180009a5c`
- `0x180009e14`
- `0x18001ee28`
- `0x180024478`
- `0x180024be8`
- `0x180025c64`
- `0x18002ba10`
- `0x18002f170`
- `0x180030254`
- `0x1800586c6`
- `0x180058700`

## import_xrefs

- `ktmw32!CreateTransaction` at `0x1800302d3`
- `ktmw32!CreateTransaction` at `0x1800302d3`

## pseudocode

```c
__int64 __fastcall FileSystem::DiskOperations::CreateFilesystemTransaction(__int64 a1)
{
  __int64 winerror_if; // rax
  unsigned int v3; // eax
  __int64 v4; // r9
  __int64 v5; // r8
  char v7; // [rsp+40h] [rbp-49h] BYREF
  _DWORD v8[2]; // [rsp+48h] [rbp-41h] BYREF
  _QWORD v9[2]; // [rsp+50h] [rbp-39h] BYREF
  _QWORD v10[2]; // [rsp+60h] [rbp-29h] BYREF
  _QWORD v11[2]; // [rsp+70h] [rbp-19h] BYREF
  _QWORD *v12; // [rsp+80h] [rbp-9h] BYREF
  __int16 v13; // [rsp+88h] [rbp-1h]
  _BYTE v14[64]; // [rsp+90h] [rbp+7h] BYREF
  __int64 v15; // [rsp+D0h] [rbp+47h] BYREF

  errorlib::scoped_error<winerror_error::tag>::scoped_error<winerror_error::tag>(v8);
  v7 = 1;
  v11[0] = &v7;
  v11[1] = v8;
  lambda_58cd378352a2168c2244383b56085d3e_::operator()(v11);
  v7 = 0;
  v12 = v11;
  v13 = 258;
  v9[0] = CreateTransaction(0, 0, 1u, 0, 0, 0, 0);
  winerror_if = make_winerror_if(v10, v9[0] == -1);
  errorlib::scoped_error<ntstatus_error::tag>::operator=(v8, winerror_if);
  v8[1] = 3;
  if ( v8[0] )
  {
    memset_0(v14, 0, sizeof(v14));
    v3 = ReportIndentTracker::Indent();
    LOBYTE(v4) = 95;
    v10[0] = v14;
    v10[1] = &v15;
    ReportIndentTracker::Format(v10, v3, v5, v4);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        28,
        (unsigned int)&WPP_36695029d1a03c55a0b5dfe9d9eeb62d_Traceguids,
        (unsigned int)v14,
        v8[0]);
    }
  }
  std::tr1::tuple<errorlib::scoped_error<winerror_error::tag>,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>::tuple<errorlib::scoped_error<winerror_error::tag>,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>(
    a1,
    v8,
    v9);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v9);
  wil::details::ScopeExitFnGuard_std::tr1::reference_wrapper__lambda_58cd378352a2168c2244383b56085d3e_____::operator()(&v12);
  errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(v8);
  return a1;
}

```

## disassembly

```asm
0x180030254  mov     [rsp-8+arg_8], rbx
0x180030259  push    rbp
0x18003025a  lea     rbp, [rsp-57h]
0x18003025f  sub     rsp, 0E0h
0x180030266  mov     rax, cs:__security_cookie
0x18003026d  xor     rax, rsp
0x180030270  mov     [rbp+57h+var_10], rax
0x180030274  mov     rbx, rcx
0x180030277  lea     rcx, [rbp+57h+var_98]
0x18003027b  call    ??0?$scoped_error@Utag@winerror_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<winerror_error::tag>::scoped_error<winerror_error::tag>(void)
0x180030280  lea     rax, [rbp+57h+var_A0]
0x180030284  mov     [rbp+57h+var_A0], 1
0x180030288  mov     [rbp+57h+var_70], rax
0x18003028c  lea     rcx, [rbp+57h+var_70]
0x180030290  lea     rax, [rbp+57h+var_98]
0x180030294  mov     [rbp+57h+var_68], rax
0x180030298  call    _lambda_58cd378352a2168c2244383b56085d3e___operator__
0x18003029d  xor     r9d, r9d; IsolationLevel
0x1800302a0  mov     [rsp+0E0h+Description], 0; Description
0x1800302a9  lea     rax, [rbp+57h+var_70]
0x1800302ad  mov     [rsp+0E0h+Timeout], 0; Timeout
0x1800302b5  xor     edx, edx; UOW
0x1800302b7  mov     [rbp+57h+var_A0], 0
0x1800302bb  xor     ecx, ecx; lpTransactionAttributes
0x1800302bd  mov     [rbp+57h+var_60], rax
0x1800302c1  lea     r8d, [r9+1]; CreateOptions
0x1800302c5  mov     [rbp+57h+var_58], 102h
0x1800302cb  mov     [rsp+0E0h+IsolationFlags], 0; IsolationFlags
0x1800302d3  call    cs:__imp_CreateTransaction
0x1800302d9  xor     edx, edx
0x1800302db  lea     rcx, [rbp+57h+var_80]
0x1800302df  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800302e3  mov     [rbp+57h+var_90], rax
0x1800302e7  setz    dl
0x1800302ea  call    ?make_winerror_if@@YA?AV?$scoped_error@Utag@winerror_error@@@errorlib@@H@Z; make_winerror_if(int)
0x1800302ef  mov     rdx, rax
0x1800302f2  lea     rcx, [rbp+57h+var_98]
0x1800302f6  call    ??4?$scoped_error@Utag@ntstatus_error@@@errorlib@@QEAAAEAV01@V01@@Z; errorlib::scoped_error<ntstatus_error::tag>::operator=(errorlib::scoped_error<ntstatus_error::tag>)
0x1800302fb  cmp     [rbp+57h+var_98], 0
0x1800302ff  mov     [rbp+57h+var_94], 3
0x180030306  jz      short loc_180030379
0x180030308  xor     edx, edx; Val
0x18003030a  lea     rcx, [rbp+57h+var_50]; void *
0x18003030e  lea     r8d, [rdx+40h]; Size
0x180030312  call    memset_0
0x180030317  call    ?Indent@ReportIndentTracker@@SAJXZ; ReportIndentTracker::Indent(void)
0x18003031c  lea     rcx, [rbp+57h+var_50]
0x180030320  mov     r9b, 5Fh ; '_'
0x180030323  mov     [rbp+57h+var_80], rcx
0x180030327  mov     edx, eax
0x180030329  lea     rcx, [rbp+57h+var_10]
0x18003032d  mov     [rbp+57h+var_78], rcx
0x180030331  lea     rcx, [rbp+57h+var_80]
0x180030335  call    ?Format@ReportIndentTracker@@SAXV?$range@PEAD@rangelib@@JDD@Z; ReportIndentTracker::Format(rangelib::range<char *>,long,char,char)
0x18003033a  mov     rcx, cs:WPP_GLOBAL_Control
0x180030341  lea     rax, WPP_GLOBAL_Control
0x180030348  cmp     rcx, rax
0x18003034b  jz      short loc_180030379
0x18003034d  test    byte ptr [rcx+1Ch], 1
0x180030351  jz      short loc_180030379
0x180030353  cmp     byte ptr [rcx+19h], 2
0x180030357  jb      short loc_180030379
0x180030359  mov     eax, [rbp+57h+var_98]
0x18003035c  lea     r9, [rbp+57h+var_50]
0x180030360  mov     rcx, [rcx+10h]
0x180030364  lea     r8, WPP_36695029d1a03c55a0b5dfe9d9eeb62d_Traceguids
0x18003036b  mov     edx, 1Ch
0x180030370  mov     [rsp+0E0h+IsolationFlags], eax
0x180030374  call    WPP_SF_sd
0x180030379  lea     r8, [rbp+57h+var_90]
0x18003037d  mov     rcx, rbx
0x180030380  lea     rdx, [rbp+57h+var_98]
0x180030384  call    ??$?0AEAV?$scoped_error@Utag@winerror_error@@@errorlib@@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@?$tuple@V?$scoped_error@Utag@winerror_error@@@errorlib@@V?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@U_Nil@tr1@std@@U567@U567@U567@U567@U567@U567@U567@@tr1@std@@QEAA@AEAV?$scoped_error@Utag@winerror_error@@@errorlib@@$$QEAV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Z; std::tr1::tuple<errorlib::scoped_error<winerror_error::tag>,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>::tuple<errorlib::scoped_error<winerror_error::tag>,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil,std::tr1::_Nil>(errorlib::scoped_error<winerror_error::tag> &,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x180030389  lea     rcx, [rbp+57h+var_90]
0x18003038d  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180030392  lea     rcx, [rbp+57h+var_60]
0x180030396  call    wil__details__ScopeExitFnGuard_std__tr1__reference_wrapper__lambda_58cd378352a2168c2244383b56085d3e_______operator__
0x18003039b  lea     rcx, [rbp+57h+var_98]
0x18003039f  call    ??1?$scoped_error@Utag@winerror_error@@@errorlib@@QEAA@XZ; errorlib::scoped_error<winerror_error::tag>::~scoped_error<winerror_error::tag>(void)
0x1800303a4  mov     rax, rbx
0x1800303a7  mov     rcx, [rbp+57h+var_10]
0x1800303ab  xor     rcx, rsp; StackCookie
0x1800303ae  call    __security_check_cookie
0x1800303b3  mov     rbx, [rsp+0E0h+arg_8]
0x1800303bb  add     rsp, 0E0h
0x1800303c2  pop     rbp
0x1800303c3  retn
```
