# _lambda_d71b8ca9efe53fbf21f54ad84e4f1069_::operator()

- ea: `0x180038dd4`
- end: `0x180039088`
- name: `_lambda_d71b8ca9efe53fbf21f54ad84e4f1069_::operator()`
- size: `692`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003435c`

## callees

- `0x180003390`
- `0x1800068f0`
- `0x180007114`
- `0x180008bbc`
- `0x18000aa7c`
- `0x18000c168`
- `0x18000db70`
- `0x18001bf68`
- `0x180035334`
- `0x180035aa0`
- `0x180036a40`
- `0x180038dd4`
- `0x180050010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180038ecd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180038f93`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180038ecd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180038f93`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180038fc7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180038ff0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180038fc7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180038ff0`

## string_xrefs

- `0x180038e3d`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\retaildemouseragent.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall lambda_d71b8ca9efe53fbf21f54ad84e4f1069_::operator()(__int64 *a1, __int64 a2, __int64 a3)
{
  __int64 (__fastcall *v5)(__int64, __int64 *); // rbx
  int v6; // eax
  __int64 v7; // rdx
  __int64 v8; // r8
  unsigned int v9; // ebx
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // rdi
  int (__fastcall *v13)(__int64, __int64, __int64 *); // rbx
  char v14; // si
  __int64 v15; // rdx
  __int64 v16; // r8
  int (__fastcall *v17)(__int64, HSTRING *); // r14
  bool v18; // sf
  char v19; // al
  __int64 v20; // rdi
  int (__fastcall *v21)(__int64, __int64, __int64 *); // rbx
  __int64 v22; // rdi
  int (__fastcall *v23)(__int64, HSTRING *); // r14
  HSTRING v24; // rbx
  PCWSTR StringRawBuffer; // rax
  __int64 v26; // r8
  __int64 v27; // rbx
  __int64 v28; // rcx
  __int64 v29; // rdx
  __int64 v30; // rdx
  __int64 v31; // r8
  __int64 v32; // rdx
  __int64 v33; // r8
  HSTRING string; // [rsp+20h] [rbp-49h] BYREF
  PCWSTR v36; // [rsp+28h] [rbp-41h] BYREF
  HSTRING v37; // [rsp+30h] [rbp-39h] BYREF
  __int64 v38; // [rsp+38h] [rbp-31h] BYREF
  __int64 v39; // [rsp+40h] [rbp-29h] BYREF
  __int64 v40; // [rsp+48h] [rbp-21h] BYREF
  _BYTE v41[8]; // [rsp+50h] [rbp-19h] BYREF
  _OWORD v42[2]; // [rsp+58h] [rbp-11h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+78h] [rbp+Fh] BYREF
  __int64 v44; // [rsp+90h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  LODWORD(v36) = 0;
  v39 = 0;
  v5 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a2 + 96LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39, a2, a3);
  v6 = v5(a2, &v39);
  v9 = v6;
  if ( v6 >= 0 )
  {
    v38 = 0;
    string = 0;
    v12 = v39;
    v13 = *(int (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v39 + 48LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38, v7, v8);
    v44 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"ProcessName", 0xCu, 0xBu);
    v14 = 1;
    LODWORD(v36) = 1;
    if ( v13(v12, v44, &v38) < 0
      || (v17 = *(int (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v38 + 64LL),
          string = 0,
          v18 = v17(v38, &string) < 0,
          v19 = 0,
          v18) )
    {
      v19 = 1;
    }
    if ( !v19 )
    {
      v40 = 0;
      v37 = 0;
      v42[0] = 0;
      v42[1] = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(v42[0]) = 0;
      v20 = v39;
      v21 = *(int (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v39 + 48LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v40, v15, v16);
      v44 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"FilterKeyword", 0xEu, 0xDu);
      LODWORD(v36) = 2;
      if ( v21(v20, v44, &v40) < 0 )
        goto LABEL_11;
      v22 = v40;
      v23 = *(int (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v40 + 64LL);
      v24 = v37;
      if ( v37 )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)v41);
        WindowsDeleteString(v24);
        wil::last_error_context::~last_error_context((wil::last_error_context *)v41);
      }
      v37 = 0;
      if ( v23(v22, &v37) < 0 )
LABEL_11:
        v14 = 0;
      if ( v14 )
      {
        StringRawBuffer = WindowsGetStringRawBuffer(v37, 0);
        v26 = -1;
        do
          ++v26;
        while ( StringRawBuffer[v26] );
        std::wstring::_Assign<unsigned short>(v42, StringRawBuffer, v26);
      }
      v27 = *a1;
      v36 = WindowsGetStringRawBuffer(string, 0);
      v29 = *(_QWORD *)(v27 + 8);
      if ( v29 == *(_QWORD *)(v27 + 16) )
      {
        std::vector<ProcessInfo>::_Emplace_reallocate<unsigned short const *,std::wstring &>(v27, v29, &v36, v42);
      }
      else
      {
        std::_Default_allocator_traits<std::allocator<ProcessInfo>>::construct<ProcessInfo,unsigned short const *,std::wstring &>(
          v28,
          v29,
          &v36,
          v42);
        *(_QWORD *)(v27 + 8) += 64LL;
      }
      std::wstring::_Tidy_deallocate(v42);
      Windows::Internal::String::~String((Windows::Internal::String *)&v37);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v40, v30, v31);
    }
    Windows::Internal::String::~String((Windows::Internal::String *)&string);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38, v32, v33);
    v9 = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x632,
      (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\retaildemouseragent.cpp",
      (const char *)(unsigned int)v6,
      (int)string);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39, v10, v11);
  return v9;
}

```

## disassembly

```asm
0x180038dd4  mov     [rsp-8+arg_10], rbx
0x180038dd9  mov     [rsp-8+arg_18], rsi
0x180038dde  push    rbp
0x180038ddf  push    rdi
0x180038de0  push    r12
0x180038de2  push    r14
0x180038de4  push    r15
0x180038de6  lea     rbp, [rsp-37h]
0x180038deb  sub     rsp, 0A0h
0x180038df2  mov     rax, cs:__security_cookie
0x180038df9  xor     rax, rsp
0x180038dfc  mov     [rbp+57h+var_28], rax
0x180038e00  mov     rdi, rdx
0x180038e03  mov     r15, rcx
0x180038e06  xor     r12d, r12d
0x180038e09  mov     dword ptr [rbp+57h+var_98], r12d
0x180038e0d  mov     [rbp+57h+var_80], r12
0x180038e11  mov     rax, [rdx]
0x180038e14  mov     rbx, [rax+60h]
0x180038e18  lea     rcx, [rbp+57h+var_80]
0x180038e1c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180038e21  lea     rdx, [rbp+57h+var_80]
0x180038e25  mov     rcx, rdi
0x180038e28  mov     rax, rbx
0x180038e2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038e30  mov     ebx, eax
0x180038e32  test    eax, eax
0x180038e34  jns     short loc_180038E53
0x180038e36  mov     rcx, [rbp+5Fh]; this
0x180038e3a  mov     r9d, eax; char *
0x180038e3d  lea     r8, aPcshellShellRe_31; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180038e44  mov     edx, 632h; void *
0x180038e49  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180038e4e  jmp     loc_180039055
0x180038e53  mov     [rbp+57h+var_88], r12
0x180038e57  mov     [rbp+57h+string], r12
0x180038e5b  mov     rdi, [rbp+57h+var_80]
0x180038e5f  mov     rax, [rdi]
0x180038e62  mov     rbx, [rax+30h]
0x180038e66  lea     rcx, [rbp+57h+var_88]
0x180038e6a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180038e6f  mov     [rbp+57h+var_30], r12
0x180038e73  mov     r9d, 0Bh; unsigned int
0x180038e79  lea     r8d, [r9+1]; unsigned int
0x180038e7d  lea     rdx, aProcessname; "ProcessName"
0x180038e84  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180038e88  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180038e8d  nop
0x180038e8e  mov     esi, 1
0x180038e93  mov     dword ptr [rbp+57h+var_98], esi
0x180038e96  lea     r8, [rbp+57h+var_88]
0x180038e9a  mov     rdx, [rbp+57h+var_30]
0x180038e9e  mov     rcx, rdi
0x180038ea1  mov     rax, rbx
0x180038ea4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038ea9  test    eax, eax
0x180038eab  js      short loc_180038EF6
0x180038ead  mov     rdi, [rbp+57h+var_88]
0x180038eb1  mov     rax, [rdi]
0x180038eb4  mov     r14, [rax+40h]
0x180038eb8  mov     rbx, [rbp+57h+string]
0x180038ebc  test    rbx, rbx
0x180038ebf  jz      short loc_180038EDC
0x180038ec1  lea     rcx, [rbp+57h+var_70]; this
0x180038ec5  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180038eca  mov     rcx, rbx; string
0x180038ecd  call    cs:__imp_WindowsDeleteString
0x180038ed3  lea     rcx, [rbp+57h+var_70]; this
0x180038ed7  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180038edc  mov     [rbp+57h+string], r12
0x180038ee0  lea     rdx, [rbp+57h+string]
0x180038ee4  mov     rcx, rdi
0x180038ee7  mov     rax, r14
0x180038eea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038eef  test    eax, eax
0x180038ef1  mov     al, r12b
0x180038ef4  jns     short loc_180038EF9
0x180038ef6  mov     al, sil
0x180038ef9  test    al, al
0x180038efb  jnz     loc_18003903F
0x180038f01  mov     [rbp+57h+var_78], r12
0x180038f05  mov     [rbp+57h+var_90], r12
0x180038f09  xorps   xmm0, xmm0
0x180038f0c  movups  [rbp+57h+var_68], xmm0
0x180038f10  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180038f18  movdqu  [rbp+57h+var_58], xmm1
0x180038f1d  mov     word ptr [rbp+57h+var_68], r12w
0x180038f22  mov     rdi, [rbp+57h+var_80]
0x180038f26  mov     rax, [rdi]
0x180038f29  mov     rbx, [rax+30h]
0x180038f2d  lea     rcx, [rbp+57h+var_78]
0x180038f31  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180038f36  mov     [rbp+57h+var_30], r12
0x180038f3a  mov     r9d, 0Dh; unsigned int
0x180038f40  lea     r8d, [r9+1]; unsigned int
0x180038f44  lea     rdx, aFilterkeyword; "FilterKeyword"
0x180038f4b  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180038f4f  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180038f54  nop
0x180038f55  mov     dword ptr [rbp+57h+var_98], 2
0x180038f5c  lea     r8, [rbp+57h+var_78]
0x180038f60  mov     rdx, [rbp+57h+var_30]
0x180038f64  mov     rcx, rdi
0x180038f67  mov     rax, rbx
0x180038f6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038f6f  test    eax, eax
0x180038f71  js      short loc_180038FB9
0x180038f73  mov     rdi, [rbp+57h+var_78]
0x180038f77  mov     rax, [rdi]
0x180038f7a  mov     r14, [rax+40h]
0x180038f7e  mov     rbx, [rbp+57h+var_90]
0x180038f82  test    rbx, rbx
0x180038f85  jz      short loc_180038FA2
0x180038f87  lea     rcx, [rbp+57h+var_70]; this
0x180038f8b  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180038f90  mov     rcx, rbx; string
0x180038f93  call    cs:__imp_WindowsDeleteString
0x180038f99  lea     rcx, [rbp+57h+var_70]; this
0x180038f9d  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180038fa2  mov     [rbp+57h+var_90], r12
0x180038fa6  lea     rdx, [rbp+57h+var_90]
0x180038faa  mov     rcx, rdi
0x180038fad  mov     rax, r14
0x180038fb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038fb5  test    eax, eax
0x180038fb7  jns     short loc_180038FBC
0x180038fb9  mov     sil, r12b
0x180038fbc  test    sil, sil
0x180038fbf  jz      short loc_180038FE7
0x180038fc1  xor     edx, edx; length
0x180038fc3  mov     rcx, [rbp+57h+var_90]; string
0x180038fc7  call    cs:__imp_WindowsGetStringRawBuffer
0x180038fcd  or      r8, 0FFFFFFFFFFFFFFFFh
0x180038fd1  inc     r8
0x180038fd4  cmp     [rax+r8*2], r12w
0x180038fd9  jnz     short loc_180038FD1
0x180038fdb  mov     rdx, rax
0x180038fde  lea     rcx, [rbp+57h+var_68]
0x180038fe2  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180038fe7  mov     rbx, [r15]
0x180038fea  xor     edx, edx; length
0x180038fec  mov     rcx, [rbp+57h+string]; string
0x180038ff0  call    cs:__imp_WindowsGetStringRawBuffer
0x180038ff6  mov     [rbp+57h+var_98], rax
0x180038ffa  mov     rdx, [rbx+8]
0x180038ffe  lea     r9, [rbp+57h+var_68]
0x180039002  lea     r8, [rbp+57h+var_98]
0x180039006  cmp     rdx, [rbx+10h]
0x18003900a  jz      short loc_180039018
0x18003900c  call    ??$construct@UProcessInfo@@PEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Default_allocator_traits@V?$allocator@UProcessInfo@@@std@@@std@@SAXAEAV?$allocator@UProcessInfo@@@1@QEAUProcessInfo@@$$QEAPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Default_allocator_traits<std::allocator<ProcessInfo>>::construct<ProcessInfo,ushort const *,std::wstring &>(std::allocator<ProcessInfo> &,ProcessInfo * const,ushort const * &&,std::wstring &)
0x180039011  add     qword ptr [rbx+8], 40h ; '@'
0x180039016  jmp     short loc_180039021
0x180039018  mov     rcx, rbx
0x18003901b  call    ??$_Emplace_reallocate@PEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@UProcessInfo@@V?$allocator@UProcessInfo@@@std@@@std@@AEAAPEAUProcessInfo@@QEAU2@$$QEAPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::vector<ProcessInfo>::_Emplace_reallocate<ushort const *,std::wstring &>(ProcessInfo * const,ushort const * &&,std::wstring &)
0x180039020  nop
0x180039021  lea     rcx, [rbp+57h+var_68]
0x180039025  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003902a  nop
0x18003902b  lea     rcx, [rbp+57h+var_90]; this
0x18003902f  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180039034  nop
0x180039035  lea     rcx, [rbp+57h+var_78]
0x180039039  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003903e  nop
0x18003903f  lea     rcx, [rbp+57h+string]; this
0x180039043  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180039048  nop
0x180039049  lea     rcx, [rbp+57h+var_88]
0x18003904d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180039052  mov     ebx, r12d
0x180039055  lea     rcx, [rbp+57h+var_80]
0x180039059  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003905e  mov     eax, ebx
0x180039060  mov     rcx, [rbp+57h+var_28]
0x180039064  xor     rcx, rsp; StackCookie
0x180039067  call    __security_check_cookie
0x18003906c  lea     r11, [rsp+0C0h+var_20]
0x180039074  mov     rbx, [r11+40h]
0x180039078  mov     rsi, [r11+48h]
0x18003907c  mov     rsp, r11
0x18003907f  pop     r15
0x180039081  pop     r14
0x180039083  pop     r12
0x180039085  pop     rdi
0x180039086  pop     rbp
0x180039087  retn
```
