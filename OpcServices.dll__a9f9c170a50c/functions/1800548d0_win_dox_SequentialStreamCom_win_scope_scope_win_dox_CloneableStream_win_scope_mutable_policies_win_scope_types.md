# win_dox::SequentialStreamCom<win_scope::scope<win_dox::CloneableStream *,win_scope::mutable_policies<win_scope::types_6<win_scope::close_delete,win_scope::convert_auto_pointer,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::detail::default_safe_types>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>,IStream>::Read_Safe(void *,ulong,ulong *)

- ea: `0x1800548d0`
- end: `0x180054af4`
- name: `?Read_Safe@?$SequentialStreamCom@V?$scope@PEAVCloneableStream@win_dox@@U?$mutable_policies@U?$types_6@Uclose_delete@win_scope@@Uconvert_auto_pointer@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Udefault_safe_types@detail@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@win_scope@@UIStream@@@win_dox@@AEAAXPEAXKPEAK@Z`
- size: `548`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180054890`

## callees

- `0x180015a68`
- `0x1800517a0`
- `0x1800548d0`
- `0x180054afc`
- `0x18005ab90`
- `0x1800cd38c`
- `0x1800d5fe4`
- `0x180117740`
- `0x18012a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180054948`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180054948`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800549bd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800549bd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180054935`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180054935`

## string_xrefs

- `0x180054a9f`: `Call to Read failed with HResult 0x%X.`
- `0x180054a45`: `Subsequent access to stream after failure not supported`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall win_dox::SequentialStreamCom<win_scope::scope<win_dox::CloneableStream *,win_scope::mutable_policies<win_scope::types_6<win_scope::close_delete,win_scope::convert_auto_pointer,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::detail::default_safe_types>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>,IStream>::Read_Safe(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _DWORD *a4)
{
  unsigned int v5; // r15d
  __int64 *v7; // rsi
  __int64 v8; // rdi
  __int64 v9; // r12
  int v10; // ecx
  signed int v11; // r14d
  __int64 v12; // r14
  unsigned int v14; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v15; // [rsp+48h] [rbp-B8h]
  char v16; // [rsp+50h] [rbp-B0h]
  __int64 v17; // [rsp+58h] [rbp-A8h]
  __int64 v18; // [rsp+60h] [rbp-A0h]
  _BYTE pExceptionObject[160]; // [rsp+70h] [rbp-90h] BYREF
  wchar_t v20[512]; // [rsp+110h] [rbp+10h] BYREF

  v18 = -2;
  v5 = a3;
  if ( !a2 )
    win_musl::detail::ThrowParameter(a1, "(no filename)", a3, 78, L"IStream", L"Read", L"pv", 0);
  HIDWORD(v15) = 0;
  v7 = *(__int64 **)(a1 + 8);
  v8 = v7[2];
  v9 = *v7;
  v15 = v8 + 8;
  EnterCriticalSection((LPCRITICAL_SECTION)(v8 + 8));
  v10 = *(_DWORD *)(v8 + 52);
  *(_DWORD *)(v8 + 52) = v10 + 1;
  if ( !v10 )
    *(_DWORD *)(v8 + 48) = GetCurrentThreadId();
  v16 = 1;
  v17 = v8;
  if ( !*(_BYTE *)(v8 + 72) )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x7Fu,
      0x8000FFFF,
      (struct win_musl::TStringEllipseBase *)L"Subsequent access to stream after failure not supported");
    throw (SplException::THResultException *)pExceptionObject;
  }
  if ( *(_QWORD *)v8 != v9 )
    win_dox::Stream::Seek(v8 + 64, v9, 0);
  v14 = 0;
  v11 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, unsigned int *))(**(_QWORD **)(v8 + 64) + 24LL))(
          *(_QWORD *)(v8 + 64),
          a2,
          v5,
          &v14);
  if ( v11 < 0 )
  {
    memset_0(v20, 0, sizeof(v20));
    StringCchPrintfW(v20, 0x200u, L"Call to Read failed with HResult 0x%X.", (unsigned int)v11);
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x60u,
      v11,
      (struct win_musl::TStringEllipseBase *)v20);
    throw (SplException::THResultException *)pExceptionObject;
  }
  v12 = v14;
  *(_QWORD *)v8 = v14 + v9;
  if ( v8 != -8 )
  {
    if ( (*(_DWORD *)(v8 + 52))-- == 1 )
      *(_DWORD *)(v8 + 48) = 0;
    LeaveCriticalSection((LPCRITICAL_SECTION)(v8 + 8));
  }
  *v7 += v12;
  if ( a4 )
    *a4 = v12;
}

```

## disassembly

```asm
0x1800548d0  push    rbp
0x1800548d2  push    rbx
0x1800548d3  push    rsi
0x1800548d4  push    rdi
0x1800548d5  push    r12
0x1800548d7  push    r13
0x1800548d9  push    r14
0x1800548db  push    r15
0x1800548dd  lea     rbp, [rsp-428h]
0x1800548e5  sub     rsp, 528h
0x1800548ec  mov     [rsp+560h+var_500], 0FFFFFFFFFFFFFFFEh
0x1800548f5  mov     rax, cs:__security_cookie
0x1800548fc  xor     rax, rsp
0x1800548ff  mov     [rbp+460h+var_50], rax
0x180054906  mov     r13, r9
0x180054909  mov     r15d, r8d
0x18005490c  mov     r14, rdx
0x18005490f  test    rdx, rdx
0x180054912  jz      loc_180054A06
0x180054918  xor     eax, eax
0x18005491a  mov     [rsp+560h+var_514], eax
0x18005491e  mov     rsi, [rcx+8]
0x180054922  mov     rdi, [rsi+10h]
0x180054926  mov     r12, [rsi]
0x180054929  lea     rbx, [rdi+8]
0x18005492d  mov     [rsp+48h], rbx
0x180054932  mov     rcx, rbx; lpCriticalSection
0x180054935  call    cs:__imp_EnterCriticalSection
0x18005493b  mov     ecx, [rbx+2Ch]
0x18005493e  lea     eax, [rcx+1]
0x180054941  mov     [rbx+2Ch], eax
0x180054944  test    ecx, ecx
0x180054946  jnz     short loc_180054951
0x180054948  call    cs:__imp_GetCurrentThreadId
0x18005494e  mov     [rbx+28h], eax
0x180054951  mov     [rsp+560h+var_510], 1
0x180054956  mov     [rsp+560h+var_508], rdi
0x18005495b  cmp     byte ptr [rdi+48h], 0
0x18005495f  jz      loc_180054A45
0x180054965  cmp     [rdi], r12
0x180054968  jnz     loc_1800549F2
0x18005496e  mov     [rsp+560h+var_520], 0
0x180054976  mov     rcx, [rdi+40h]
0x18005497a  mov     rax, [rcx]
0x18005497d  lea     r9, [rsp+560h+var_520]
0x180054982  mov     r8d, r15d
0x180054985  mov     rdx, r14
0x180054988  mov     rax, [rax+18h]
0x18005498c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054991  mov     r14d, eax
0x180054994  test    eax, eax
0x180054996  js      loc_180054A8B
0x18005499c  mov     r14d, [rsp+560h+var_520]
0x1800549a1  lea     rax, [r14+r12]
0x1800549a5  mov     [rdi], rax
0x1800549a8  test    rbx, rbx
0x1800549ab  jz      short loc_1800549C3
0x1800549ad  add     dword ptr [rbx+2Ch], 0FFFFFFFFh
0x1800549b1  jnz     short loc_1800549BA
0x1800549b3  mov     dword ptr [rbx+28h], 0
0x1800549ba  mov     rcx, rbx; lpCriticalSection
0x1800549bd  call    cs:__imp_LeaveCriticalSection
0x1800549c3  add     [rsi], r14
0x1800549c6  test    r13, r13
0x1800549c9  jz      short loc_1800549CF
0x1800549cb  mov     [r13+0], r14d
0x1800549cf  mov     rcx, [rbp+460h+var_50]
0x1800549d6  xor     rcx, rsp; StackCookie
0x1800549d9  call    __security_check_cookie
0x1800549de  add     rsp, 528h
0x1800549e5  pop     r15
0x1800549e7  pop     r14
0x1800549e9  pop     r13
0x1800549eb  pop     r12
0x1800549ed  pop     rdi
0x1800549ee  pop     rsi
0x1800549ef  pop     rbx
0x1800549f0  pop     rbp
0x1800549f1  retn
0x1800549f2  lea     rcx, [rdi+40h]
0x1800549f6  xor     r8d, r8d
0x1800549f9  mov     rdx, r12
0x1800549fc  call    ?Seek@Stream@win_dox@@QEAA_K_JW4Enum@SeekOrigin@2@@Z; win_dox::Stream::Seek(__int64,win_dox::SeekOrigin::Enum)
0x180054a01  jmp     loc_18005496E
0x180054a06  mov     [rsp+560h+var_528], 0
0x180054a0e  lea     rax, aPv; "pv"
0x180054a15  mov     [rsp+560h+var_530], rax
0x180054a1a  lea     rax, aRead; "Read"
0x180054a21  mov     qword ptr [rsp+560h+var_538], rax
0x180054a26  lea     rax, aIstream; "IStream"
0x180054a2d  mov     qword ptr [rsp+560h+var_540], rax
0x180054a32  mov     r9d, 4Eh ; 'N'
0x180054a38  lea     rdx, aNoFilename; "(no filename)"
0x180054a3f  call    ?ThrowParameter@detail@win_musl@@YAXP6AXPEBD0IW4LOG_CATEGORY@2@JPEB_W@Z00I222W4Enum@ParameterCheckReason@2@@Z; win_musl::detail::ThrowParameter(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,wchar_t const *,wchar_t const *,wchar_t const *,win_musl::ParameterCheckReason::Enum)
0x180054a45  lea     rax, aSubsequentAcce; "Subsequent access to stream after failu"...
0x180054a4c  mov     [rsp+560h+var_530], rax; struct win_musl::TStringEllipseBase *
0x180054a51  mov     [rsp+560h+var_538], 8000FFFFh; unsigned int
0x180054a59  mov     [rsp+560h+var_540], 7Fh; unsigned int
0x180054a61  lea     r9, word_18013A0B6
0x180054a68  lea     r8, aNoFilename; "(no filename)"
0x180054a6f  lea     rcx, [rsp+560h+pExceptionObject]; this
0x180054a74  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180054a79  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180054a80  lea     rcx, [rsp+560h+pExceptionObject]; pExceptionObject
0x180054a85  call    _CxxThrowException_0
0x180054a8b  xor     edx, edx; Val
0x180054a8d  mov     r8d, 400h; Size
0x180054a93  lea     rcx, [rbp+460h+var_450]; void *
0x180054a97  call    memset_0
0x180054a9c  mov     r9d, r14d
0x180054a9f  lea     r8, aCallToReadFail; "Call to Read failed with HResult 0x%X."
0x180054aa6  mov     edx, 200h; unsigned __int64
0x180054aab  lea     rcx, [rbp+460h+var_450]; wchar_t *
0x180054aaf  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180054ab4  lea     rax, [rbp+460h+var_450]
0x180054ab8  mov     [rsp+560h+var_530], rax; struct win_musl::TStringEllipseBase *
0x180054abd  mov     [rsp+560h+var_538], r14d; unsigned int
0x180054ac2  mov     [rsp+560h+var_540], 60h ; '`'; unsigned int
0x180054aca  lea     r9, word_18013A0B6
0x180054ad1  lea     r8, aNoFilename; "(no filename)"
0x180054ad8  lea     rcx, [rsp+560h+pExceptionObject]; this
0x180054add  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180054ae2  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180054ae9  lea     rcx, [rsp+560h+pExceptionObject]; pExceptionObject
0x180054aee  call    _CxxThrowException_0
```
