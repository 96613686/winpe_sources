# Uev::LogImpl::WriteStringToLogFile(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x1400208d0`
- end: `0x140020ae8`
- name: `?WriteStringToLogFile@LogImpl@Uev@@AEBAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `536`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1400205f4`

## callees

- `0x140003e50`
- `0x140003f88`
- `0x140003fcc`
- `0x14000423c`
- `0x14000aa1c`
- `0x14000aa84`
- `0x14000f1ac`
- `0x1400208d0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140020981`
- `KERNEL32!GetLastError` at `0x140020981`
- `KERNEL32!WideCharToMultiByte` at `0x140020973`
- `KERNEL32!WideCharToMultiByte` at `0x1400209cd`
- `KERNEL32!WideCharToMultiByte` at `0x140020a1a`
- `KERNEL32!WideCharToMultiByte` at `0x140020973`
- `KERNEL32!WideCharToMultiByte` at `0x1400209cd`
- `KERNEL32!WideCharToMultiByte` at `0x140020a1a`
- `msvcp_win!?write@?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEBD_J@Z` at `0x140020a4c`
- `msvcp_win!?write@?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEBD_J@Z` at `0x140020a4c`
- `msvcp_win!?flush@?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@XZ` at `0x140020a56`
- `msvcp_win!?flush@?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@XZ` at `0x140020a56`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall Uev::LogImpl::WriteStringToLogFile(__int64 a1, __int64 *a2)
{
  CHAR *v4; // rbx
  const WCHAR *v5; // r8
  const WCHAR *v6; // r8
  int cbMultiByte; // r14d
  CHAR *lpMultiByteStr; // rax
  int v9; // r9d
  __int64 v10; // rbx
  CHAR *v11; // [rsp+40h] [rbp-258h]
  __int128 v13; // [rsp+50h] [rbp-248h] BYREF
  __int64 v14; // [rsp+60h] [rbp-238h]
  __int64 v15; // [rsp+68h] [rbp-230h]
  CHAR MultiByteStr[512]; // [rsp+70h] [rbp-228h] BYREF

  if ( *(_QWORD *)(a1 + 72) )
  {
    if ( dword_1400D1E30 > *(_DWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 4LL) )
    {
      Init_thread_header(&dword_1400D1E30);
      if ( dword_1400D1E30 == -1 )
      {
        std::string::_Construct<1,char const *>(
          &qword_1400D1E40,
          "!!Error occurred while converting string from Unicode to MultiByte. Log message has been lost!!");
        atexit(Uev::LogImpl::WriteStringToLogFile_::_5_::_dynamic_atexit_destructor_for__errorMsg__);
        Init_thread_footer(&dword_1400D1E30);
      }
    }
    v4 = 0;
    v11 = 0;
    if ( (unsigned __int64)a2[3] <= 7 )
      v5 = (const WCHAR *)a2;
    else
      v5 = (const WCHAR *)*a2;
    if ( !WideCharToMultiByte(0xFDE9u, 0, v5, *((_DWORD *)a2 + 4), MultiByteStr, 512, 0, 0) && GetLastError() == 122 )
    {
      if ( (unsigned __int64)a2[3] <= 7 )
        v6 = (const WCHAR *)a2;
      else
        v6 = (const WCHAR *)*a2;
      cbMultiByte = WideCharToMultiByte(0xFDE9u, 0, v6, *((_DWORD *)a2 + 4), 0, 0, 0, 0);
      lpMultiByteStr = (CHAR *)operator new[](cbMultiByte);
      v4 = lpMultiByteStr;
      v11 = lpMultiByteStr;
      v9 = *((_DWORD *)a2 + 4);
      if ( (unsigned __int64)a2[3] > 7 )
        a2 = (__int64 *)*a2;
      WideCharToMultiByte(0xFDE9u, 0, (LPCWCH)a2, v9, lpMultiByteStr, cbMultiByte, 0, 0);
    }
    try
    {
      std::ostream::write();
      std::ostream::flush(*(_QWORD *)(a1 + 72));
    }
    catch ( boost::filesystem::filesystem_error )
    {
      v10 = *(_QWORD *)(a1 + 72);
      *(_QWORD *)(a1 + 72) = 0;
      if ( v10 )
      {
        if ( !std::filebuf::close(v10 + 8) )
          std::ios::setstate(v10 + *(int *)(*(_QWORD *)v10 + 4LL), 2);
        (**(void (__fastcall ***)(__int64, __int64))(*(int *)(*(_QWORD *)v10 + 4LL) + v10))(
          v10 + *(int *)(*(_QWORD *)v10 + 4LL),
          1);
      }
      v13 = 0;
      v14 = 0;
      v15 = 0;
      std::wstring::_Construct<1,wchar_t *>(&v13, L"Common", 6u);
      Uev::LogImpl::Write(
        a1,
        8,
        &v13,
        L"LogImpl::WriteStringToLogFile() - Failed to write message to local debug log file. Debug logging to the local fi"
         "le will be disabled.");
      std::wstring::_Tidy_deallocate(&v13);
      v4 = v11;
    }
    if ( v4 )
      operator delete(v4);
  }
}

```

## disassembly

```asm
0x1400208d0  mov     [rsp+arg_10], rbx
0x1400208d5  push    rdi
0x1400208d6  push    r14
0x1400208d8  push    r15
0x1400208da  sub     rsp, 280h
0x1400208e1  mov     rax, cs:__security_cookie
0x1400208e8  xor     rax, rsp
0x1400208eb  mov     [rsp+298h+var_28], rax
0x1400208f3  mov     rdi, rdx
0x1400208f6  mov     r15, rcx
0x1400208f9  mov     [rsp+298h+var_250], rcx
0x1400208fe  cmp     qword ptr [rcx+48h], 0
0x140020903  jz      loc_140020A71
0x140020909  mov     ecx, 4
0x14002090e  mov     rax, gs:58h
0x140020917  mov     rdx, [rax]
0x14002091a  mov     eax, [rcx+rdx]
0x14002091d  cmp     cs:dword_1400D1E30, eax
0x140020923  jg      loc_140020A96
0x140020929  xor     ebx, ebx
0x14002092b  mov     [rsp+298h+var_258], rbx
0x140020930  lea     r14, [rsp+298h+MultiByteStr]
0x140020935  cmp     qword ptr [rdi+18h], 7
0x14002093a  jbe     short loc_140020941
0x14002093c  mov     r8, [rdi]
0x14002093f  jmp     short loc_140020944
0x140020941  mov     r8, rdi; lpWideCharStr
0x140020944  mov     [rsp+298h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x14002094d  mov     [rsp+298h+lpDefaultChar], 0; lpDefaultChar
0x140020956  mov     [rsp+298h+cbMultiByte], 200h; cbMultiByte
0x14002095e  lea     rax, [rsp+298h+MultiByteStr]
0x140020963  mov     [rsp+298h+lpMultiByteStr], rax; lpMultiByteStr
0x140020968  mov     r9d, [rdi+10h]; cchWideChar
0x14002096c  xor     edx, edx; dwFlags
0x14002096e  mov     ecx, 0FDE9h; CodePage
0x140020973  call    cs:__imp_WideCharToMultiByte
0x140020979  test    eax, eax
0x14002097b  jnz     loc_140020A42
0x140020981  call    cs:__imp_GetLastError
0x140020987  cmp     eax, 7Ah ; 'z'
0x14002098a  jnz     loc_140020A25
0x140020990  cmp     qword ptr [rdi+18h], 7
0x140020995  jbe     short loc_14002099C
0x140020997  mov     r8, [rdi]
0x14002099a  jmp     short loc_14002099F
0x14002099c  mov     r8, rdi; lpWideCharStr
0x14002099f  mov     [rsp+298h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x1400209a8  mov     [rsp+298h+lpDefaultChar], 0; lpDefaultChar
0x1400209b1  mov     [rsp+298h+cbMultiByte], 0; cbMultiByte
0x1400209b9  mov     [rsp+298h+lpMultiByteStr], 0; lpMultiByteStr
0x1400209c2  mov     r9d, [rdi+10h]; cchWideChar
0x1400209c6  xor     edx, edx; dwFlags
0x1400209c8  mov     ecx, 0FDE9h; CodePage
0x1400209cd  call    cs:__imp_WideCharToMultiByte
0x1400209d3  movsxd  r14, eax
0x1400209d6  mov     rcx, r14; unsigned __int64
0x1400209d9  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1400209de  mov     rbx, rax
0x1400209e1  mov     [rsp+298h+var_258], rax
0x1400209e6  mov     r9d, [rdi+10h]; cchWideChar
0x1400209ea  cmp     qword ptr [rdi+18h], 7
0x1400209ef  jbe     short loc_1400209F4
0x1400209f1  mov     rdi, [rdi]
0x1400209f4  mov     [rsp+298h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x1400209fd  mov     [rsp+298h+lpDefaultChar], 0; lpDefaultChar
0x140020a06  mov     [rsp+298h+cbMultiByte], r14d; cbMultiByte
0x140020a0b  mov     [rsp+298h+lpMultiByteStr], rbx; lpMultiByteStr
0x140020a10  mov     r8, rdi; lpWideCharStr
0x140020a13  xor     edx, edx; dwFlags
0x140020a15  mov     ecx, 0FDE9h; CodePage
0x140020a1a  call    cs:__imp_WideCharToMultiByte
0x140020a20  mov     r14, rbx
0x140020a23  jmp     short loc_140020A42
0x140020a25  mov     eax, cs:dword_1400D1E50
0x140020a2b  lea     r14, qword_1400D1E40
0x140020a32  cmp     cs:qword_1400D1E58, 0Fh
0x140020a3a  cmova   r14, cs:qword_1400D1E40
0x140020a42  movsxd  r8, eax
0x140020a45  mov     rdx, r14
0x140020a48  mov     rcx, [r15+48h]
0x140020a4c  call    cs:__imp_?write@?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@PEBD_J@Z; std::ostream::write(char const *,__int64)
0x140020a52  mov     rcx, [r15+48h]
0x140020a56  call    cs:__imp_?flush@?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV12@XZ; std::ostream::flush(void)
0x140020a5c  nop
0x140020a5d  jmp     short loc_140020A64
0x140020a5f  mov     rbx, [rsp+298h+var_258]
0x140020a64  test    rbx, rbx
0x140020a67  jz      short loc_140020A71
0x140020a69  mov     rcx, rbx; Block
0x140020a6c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140020a71  mov     rcx, [rsp+298h+var_28]
0x140020a79  xor     rcx, rsp; StackCookie
0x140020a7c  call    __security_check_cookie
0x140020a81  mov     rbx, [rsp+298h+arg_10]
0x140020a89  add     rsp, 280h
0x140020a90  pop     r15
0x140020a92  pop     r14
0x140020a94  pop     rdi
0x140020a95  retn
0x140020a96  lea     rcx, dword_1400D1E30
0x140020a9d  call    _Init_thread_header
0x140020aa2  cmp     cs:dword_1400D1E30, 0FFFFFFFFh
0x140020aa9  jnz     loc_140020929
0x140020aaf  mov     r8d, 5Fh ; '_'
0x140020ab5  lea     rdx, aErrorOccurredW; "!!Error occurred while converting strin"...
0x140020abc  lea     rcx, qword_1400D1E40
0x140020ac3  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x140020ac8  lea     rcx, _Uev__LogImpl__WriteStringToLogFile____5____dynamic_atexit_destructor_for__errorMsg__; void (__cdecl *)()
0x140020acf  call    atexit
0x140020ad4  nop
0x140020ad5  lea     rcx, dword_1400D1E30
0x140020adc  call    _Init_thread_footer
0x140020ae1  nop
0x140020ae2  jmp     loc_140020929
```
