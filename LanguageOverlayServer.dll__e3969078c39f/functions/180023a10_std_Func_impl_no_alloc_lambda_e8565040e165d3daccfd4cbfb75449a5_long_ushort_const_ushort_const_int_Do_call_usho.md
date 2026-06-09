# std::_Func_impl_no_alloc<_lambda_e8565040e165d3daccfd4cbfb75449a5_,long,ushort const *,ushort const *,int *>::_Do_call(ushort const * &&,ushort const * &&,int * &&)

- ea: `0x180023a10`
- end: `0x180023b45`
- name: `?_Do_call@?$_Func_impl_no_alloc@V_lambda_e8565040e165d3daccfd4cbfb75449a5_@@JPEBGPEBGPEAH@std@@EEAAJ$$QEAPEBG0$$QEAPEAH@Z`
- size: `309`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180003a00`
- `0x180012a98`
- `0x180023a10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180023a7f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180023ac0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180023a7f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180023ac0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180023a94`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180023ad5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180023a94`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180023ad5`
- `Bcp47Langs!Bcp47GetDistance` at `0x180023ae8`
- `Bcp47Langs!Bcp47GetDistance` at `0x180023ae8`

## pseudocode

```c
__int64 __fastcall std::_Func_impl_no_alloc<_lambda_e8565040e165d3daccfd4cbfb75449a5_,long,unsigned short const *,unsigned short const *,int *>::_Do_call(
        __int64 a1,
        const WCHAR **a2,
        const WCHAR **a3,
        _DWORD **a4)
{
  _DWORD *v4; // r14
  const WCHAR *v5; // rbp
  unsigned __int64 v6; // rsi
  const WCHAR *v7; // r15
  unsigned __int64 v8; // rdi
  int v9; // ebx
  HSTRING v10; // rdi
  HSTRING string; // [rsp+20h] [rbp-88h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+28h] [rbp-80h] BYREF
  HSTRING v14; // [rsp+40h] [rbp-68h] BYREF
  HSTRING_HEADER v15; // [rsp+48h] [rbp-60h] BYREF
  int v16; // [rsp+60h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  v4 = *a4;
  if ( !*a4 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xC,
      (unsigned int)"onecore\\internal\\shell\\inc\\findclosestpackage.h",
      (const char *)0x80004003LL,
      (int)string);
  v5 = *a3;
  v6 = -1;
  v7 = *a2;
  v8 = -1;
  v9 = 0;
  v16 = 0;
  do
    ++v8;
  while ( v5[v8] );
  if ( v8 > 0xFFFFFFFF )
  {
    LODWORD(v8) = -1;
    RaiseException(0xC000000D, 1u, 0, 0);
  }
  WindowsCreateStringReference(v5, v8, &hstringHeader, &string);
  v10 = string;
  do
    ++v6;
  while ( v7[v6] );
  if ( v6 > 0xFFFFFFFF )
  {
    LODWORD(v6) = -1;
    RaiseException(0xC000000D, 1u, 0, 0);
  }
  WindowsCreateStringReference(v7, v6, &v15, &v14);
  if ( (int)Bcp47GetDistance(v14, v10, &v16) >= 0 )
    v9 = 100 - v16;
  *v4 = v9;
  return 0;
}

```

## disassembly

```asm
0x180023a10  mov     [rsp+arg_0], rbx
0x180023a15  push    rbp
0x180023a16  push    rsi
0x180023a17  push    rdi
0x180023a18  push    r12
0x180023a1a  push    r13
0x180023a1c  push    r14
0x180023a1e  push    r15
0x180023a20  sub     rsp, 70h
0x180023a24  mov     rax, cs:__security_cookie
0x180023a2b  xor     rax, rsp
0x180023a2e  mov     [rsp+0A8h+var_40], rax
0x180023a33  mov     r14, [r9]
0x180023a36  xor     r12d, r12d
0x180023a39  test    r14, r14
0x180023a3c  jz      loc_180023B25
0x180023a42  mov     rbp, [r8]
0x180023a45  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180023a49  mov     r15, [rdx]
0x180023a4c  mov     rdi, rsi
0x180023a4f  mov     ebx, r12d
0x180023a52  mov     [rsp+0A8h+var_48], r12d
0x180023a57  inc     rdi
0x180023a5a  cmp     [rbp+rdi*2+0], r12w
0x180023a60  jnz     short loc_180023A57
0x180023a62  mov     r13d, 0FFFFFFFFh
0x180023a68  cmp     rdi, r13
0x180023a6b  jbe     short loc_180023A85
0x180023a6d  xor     r9d, r9d; lpArguments
0x180023a70  xor     r8d, r8d; nNumberOfArguments
0x180023a73  mov     ecx, 0C000000Dh; dwExceptionCode
0x180023a78  mov     edi, r13d
0x180023a7b  lea     edx, [r9+1]; dwExceptionFlags
0x180023a7f  call    cs:__imp_RaiseException
0x180023a85  lea     r9, [rsp+0A8h+string]; string
0x180023a8a  mov     edx, edi; length
0x180023a8c  lea     r8, [rsp+0A8h+hstringHeader]; hstringHeader
0x180023a91  mov     rcx, rbp; sourceString
0x180023a94  call    cs:__imp_WindowsCreateStringReference
0x180023a9a  mov     rdi, [rsp+0A8h+string]
0x180023a9f  inc     rsi
0x180023aa2  cmp     [r15+rsi*2], r12w
0x180023aa7  jnz     short loc_180023A9F
0x180023aa9  cmp     rsi, r13
0x180023aac  jbe     short loc_180023AC6
0x180023aae  xor     r9d, r9d; lpArguments
0x180023ab1  xor     r8d, r8d; nNumberOfArguments
0x180023ab4  mov     ecx, 0C000000Dh; dwExceptionCode
0x180023ab9  mov     esi, r13d
0x180023abc  lea     edx, [r9+1]; dwExceptionFlags
0x180023ac0  call    cs:__imp_RaiseException
0x180023ac6  lea     r9, [rsp+0A8h+var_68]; string
0x180023acb  mov     edx, esi; length
0x180023acd  lea     r8, [rsp+0A8h+var_60]; hstringHeader
0x180023ad2  mov     rcx, r15; sourceString
0x180023ad5  call    cs:__imp_WindowsCreateStringReference
0x180023adb  mov     rcx, [rsp+0A8h+var_68]
0x180023ae0  lea     r8, [rsp+0A8h+var_48]
0x180023ae5  mov     rdx, rdi
0x180023ae8  call    cs:__imp_Bcp47GetDistance
0x180023aee  test    eax, eax
0x180023af0  js      short loc_180023AFB
0x180023af2  mov     ebx, 64h ; 'd'
0x180023af7  sub     ebx, [rsp+0A8h+var_48]
0x180023afb  mov     [r14], ebx
0x180023afe  xor     eax, eax
0x180023b00  mov     rcx, [rsp+0A8h+var_40]
0x180023b05  xor     rcx, rsp; StackCookie
0x180023b08  call    __security_check_cookie
0x180023b0d  mov     rbx, [rsp+0A8h+arg_0]
0x180023b15  add     rsp, 70h
0x180023b19  pop     r15
0x180023b1b  pop     r14
0x180023b1d  pop     r13
0x180023b1f  pop     r12
0x180023b21  pop     rdi
0x180023b22  pop     rsi
0x180023b23  pop     rbp
0x180023b24  retn
0x180023b25  mov     rcx, [rsp+0A8h]; this
0x180023b2d  lea     r8, aOnecoreInterna_7; "onecore\\internal\\shell\\inc\\findclos"...
0x180023b34  mov     r9d, 80004003h; char *
0x180023b3a  mov     edx, 0Ch; void *
0x180023b3f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
