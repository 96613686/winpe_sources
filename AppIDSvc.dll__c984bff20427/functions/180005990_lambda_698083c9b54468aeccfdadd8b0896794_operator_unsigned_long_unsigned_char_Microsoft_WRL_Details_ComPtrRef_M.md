# _lambda_698083c9b54468aeccfdadd8b0896794_::operator()_unsigned_long_unsigned_char___Microsoft::WRL::Details::ComPtrRef_Microsoft::WRL::ComPtr_Windows::Data::Json::IJsonValue_____

- ea: `0x180005990`
- end: `0x180005b2f`
- name: `_lambda_698083c9b54468aeccfdadd8b0896794_::operator()_unsigned_long_unsigned_char___Microsoft::WRL::Details::ComPtrRef_Microsoft::WRL::ComPtr_Windows::Data::Json::IJsonValue_____`
- size: `415`
- prototype: `signed int __fastcall(__int64 ***, DWORD, const BYTE *, __int64 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180006860`

## callees

- `0x180005990`
- `0x180007874`
- `0x180008470`
- `0x18000c0e0`
- `0x18000d010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180005a82`
- `msvcrt!??3@YAXPEAX@Z` at `0x180005a82`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800059ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005a65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800059ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005a65`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180005ae9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180005ae9`
- `CRYPT32!CryptBinaryToStringW` at `0x1800059e2`
- `CRYPT32!CryptBinaryToStringW` at `0x180005a5b`
- `CRYPT32!CryptBinaryToStringW` at `0x1800059e2`
- `CRYPT32!CryptBinaryToStringW` at `0x180005a5b`

## pseudocode

```c
signed int __fastcall lambda_698083c9b54468aeccfdadd8b0896794_::operator()_unsigned_long_unsigned_char___Microsoft::WRL::Details::ComPtrRef_Microsoft::WRL::ComPtr_Windows::Data::Json::IJsonValue_____(
        __int64 ***a1,
        DWORD a2,
        const BYTE *a3,
        __int64 *a4)
{
  signed int result; // eax
  WCHAR *v9; // rdi
  signed int LastError; // eax
  unsigned int v11; // ebx
  __int64 *v12; // rsi
  __int64 v13; // r14
  __int64 v14; // rcx
  unsigned __int64 v15; // rdx
  HRESULT v16; // eax
  DWORD pcchString; // [rsp+30h] [rbp-50h] BYREF
  LPWSTR pszString[2]; // [rsp+38h] [rbp-48h] BYREF
  __int64 v19; // [rsp+48h] [rbp-38h]
  HSTRING_HEADER hstringHeader; // [rsp+50h] [rbp-30h] BYREF
  HSTRING string; // [rsp+68h] [rbp-18h] BYREF

  pcchString = 0;
  if ( CryptBinaryToStringW(a3, a2, 0x40000001u, 0, &pcchString) )
  {
    *(_OWORD *)pszString = 0;
    v19 = 0;
    std::vector<unsigned short>::resize(pszString, pcchString);
    v9 = pszString[0];
    if ( CryptBinaryToStringW(a3, a2, 0x40000001u, pszString[0], &pcchString) )
    {
      v12 = **a1;
      v13 = *v12;
      v14 = *a4;
      if ( *a4 )
      {
        *a4 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
      }
      string = 0;
      v15 = -1;
      do
        ++v15;
      while ( v9[v15] );
      if ( v15 > 0xFFFFFFFF )
      {
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL);
        __debugbreak();
      }
      if ( (int)v15 + 1 < (unsigned int)v15 )
      {
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL);
        JUMPOUT(0x180005B2ELL);
      }
      v16 = WindowsCreateStringReference(v9, v15, &hstringHeader, &string);
      if ( v16 < 0 )
      {
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v16);
        __debugbreak();
      }
      v11 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, __int64 *))(v13 + 80))(v12, string, a4);
      string = 0;
    }
    else
    {
      LastError = GetLastError();
      v11 = LastError;
      if ( LastError > 0 )
        v11 = (unsigned __int16)LastError | 0x80070000;
    }
    if ( v9 )
    {
      operator delete(v9);
      *(_OWORD *)pszString = 0;
      v19 = 0;
    }
    return v11;
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x180005990  mov     [rsp-28h+arg_8], rbx
0x180005995  mov     [rsp-28h+arg_10], rsi
0x18000599a  push    rbp
0x18000599b  push    rdi
0x18000599c  push    r12
0x18000599e  push    r14
0x1800059a0  push    r15
0x1800059a2  mov     rbp, rsp
0x1800059a5  sub     rsp, 80h
0x1800059ac  mov     rax, cs:__security_cookie
0x1800059b3  xor     rax, rsp
0x1800059b6  mov     [rbp+var_10], rax
0x1800059ba  mov     rbx, r9
0x1800059bd  mov     r14, r8
0x1800059c0  mov     r15d, edx
0x1800059c3  mov     rsi, rcx
0x1800059c6  xor     r12d, r12d
0x1800059c9  mov     [rbp+var_50], r12d
0x1800059cd  lea     rax, [rbp+var_50]
0x1800059d1  mov     [rsp+80h+pcchString], rax; pcchString
0x1800059d6  xor     r9d, r9d; pszString
0x1800059d9  mov     r8d, 40000001h; dwFlags
0x1800059df  mov     rcx, r14; pbBinary
0x1800059e2  call    cs:__imp_CryptBinaryToStringW
0x1800059e8  test    eax, eax
0x1800059ea  jnz     short loc_180005A26
0x1800059ec  call    cs:__imp_GetLastError
0x1800059f2  test    eax, eax
0x1800059f4  jle     short loc_1800059FE
0x1800059f6  movzx   eax, ax
0x1800059f9  or      eax, 80070000h
0x1800059fe  mov     rcx, [rbp+var_10]
0x180005a02  xor     rcx, rsp; StackCookie
0x180005a05  call    __security_check_cookie
0x180005a0a  lea     r11, [rsp+80h+var_s0]
0x180005a12  mov     rbx, [r11+38h]
0x180005a16  mov     rsi, [r11+40h]
0x180005a1a  mov     rsp, r11
0x180005a1d  pop     r15
0x180005a1f  pop     r14
0x180005a21  pop     r12
0x180005a23  pop     rdi
0x180005a24  pop     rbp
0x180005a25  retn
0x180005a26  xorps   xmm0, xmm0
0x180005a29  movdqu  xmmword ptr [rbp+pszString], xmm0
0x180005a2e  mov     [rbp+var_38], r12
0x180005a32  mov     edx, [rbp+var_50]
0x180005a35  lea     rcx, [rbp+pszString]
0x180005a39  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180005a3e  nop
0x180005a3f  lea     rax, [rbp+var_50]
0x180005a43  mov     [rsp+80h+pcchString], rax; pcchString
0x180005a48  mov     rdi, [rbp+pszString]
0x180005a4c  mov     r9, rdi; pszString
0x180005a4f  mov     r8d, 40000001h; dwFlags
0x180005a55  mov     edx, r15d; cbBinary
0x180005a58  mov     rcx, r14; pbBinary
0x180005a5b  call    cs:__imp_CryptBinaryToStringW
0x180005a61  test    eax, eax
0x180005a63  jnz     short loc_180005A9B
0x180005a65  call    cs:__imp_GetLastError
0x180005a6b  mov     ebx, eax
0x180005a6d  test    eax, eax
0x180005a6f  jle     short loc_180005A7A
0x180005a71  movzx   ebx, ax
0x180005a74  or      ebx, 80070000h
0x180005a7a  test    rdi, rdi
0x180005a7d  jz      short loc_180005A94
0x180005a7f  mov     rcx, rdi
0x180005a82  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180005a88  xorps   xmm0, xmm0
0x180005a8b  movdqu  xmmword ptr [rbp+pszString], xmm0
0x180005a90  mov     [rbp+var_38], r12
0x180005a94  mov     eax, ebx
0x180005a96  jmp     loc_1800059FE
0x180005a9b  mov     rax, [rsi]
0x180005a9e  mov     rsi, [rax]
0x180005aa1  mov     r14, [rsi]
0x180005aa4  mov     rcx, [rbx]
0x180005aa7  test    rcx, rcx
0x180005aaa  jz      short loc_180005ABB
0x180005aac  mov     [rbx], r12
0x180005aaf  mov     rax, [rcx]
0x180005ab2  mov     rax, [rax+10h]
0x180005ab6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005abb  mov     [rbp+string], r12
0x180005abf  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180005ac3  inc     rdx; int
0x180005ac6  cmp     [rdi+rdx*2], r12w
0x180005acb  jnz     short loc_180005AC3
0x180005acd  mov     eax, 0FFFFFFFFh
0x180005ad2  cmp     rdx, rax
0x180005ad5  ja      short loc_180005B19
0x180005ad7  lea     eax, [rdx+1]
0x180005ada  cmp     eax, edx
0x180005adc  jb      short loc_180005B24
0x180005ade  lea     r9, [rbp+string]; string
0x180005ae2  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180005ae6  mov     rcx, rdi; sourceString
0x180005ae9  call    cs:__imp_WindowsCreateStringReference
0x180005aef  test    eax, eax
0x180005af1  js      short loc_180005B11
0x180005af3  mov     r8, rbx
0x180005af6  mov     rdx, [rbp+string]
0x180005afa  mov     rcx, rsi
0x180005afd  mov     rax, [r14+50h]
0x180005b01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b06  mov     ebx, eax
0x180005b08  mov     [rbp+string], r12
0x180005b0c  jmp     loc_180005A7A
0x180005b11  mov     ecx, eax; this
0x180005b13  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x180005b18  int     3; Trap to Debugger
0x180005b19  mov     ecx, 80070216h; this
0x180005b1e  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x180005b23  int     3; Trap to Debugger
0x180005b24  mov     ecx, 80070216h; this
0x180005b29  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
