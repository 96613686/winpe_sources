# GetModulePath(ushort *,ulong)

- ea: `0x140007bf8`
- end: `0x140007d80`
- name: `?GetModulePath@@YAJPEAGK@Z`
- size: `392`
- prototype: `__int64 __fastcall(wchar_t *Str, __int64, __int64, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140008710`

## callees

- `0x1400036d8`
- `0x140003918`
- `0x140003ab4`
- `0x140003c2c`
- `0x140007bf8`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x140007c37`
- `KERNEL32!IsDebuggerPresent` at `0x140007cf1`
- `KERNEL32!IsDebuggerPresent` at `0x140007c37`
- `KERNEL32!IsDebuggerPresent` at `0x140007cf1`
- `KERNEL32!GetLastError` at `0x140007ca6`
- `KERNEL32!GetLastError` at `0x140007ca6`
- `KERNEL32!GetModuleFileNameW` at `0x140007c98`
- `KERNEL32!GetModuleFileNameW` at `0x140007c98`
- `msvcrt!wcsrchr` at `0x140007d5b`
- `msvcrt!wcsrchr` at `0x140007d5b`

## string_xrefs

- `0x140007c05`: `GetModulePath`
- `0x140007c0f`: `termsrv\wms\src\common\srcutils\srcutils.cpp`

## pseudocode

```c
__int64 __fastcall GetModulePath(wchar_t *Str, __int64 a2, __int64 a3, const unsigned __int16 *a4)
{
  signed int LastError; // eax
  signed int v6; // ebx
  wchar_t *v7; // rax
  __int64 v9; // [rsp+30h] [rbp-48h]

  if ( !Str )
  {
    LOGASSERT(L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp", 0x38u, L"GetModulePath", a4, L"lpFilename != NULL");
    if ( IsDebuggerPresent() )
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)\n",
        L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
        56,
        L"GetModulePath",
        L"ASSERT",
        L"lpFilename != NULL");
    else
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)\n",
        L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
        56,
        L"GetModulePath",
        L"ASSERT",
        L"lpFilename != NULL");
  }
  if ( GetModuleFileNameW(0, Str, 0x103u) )
  {
    v6 = 0;
    Str[259] = 0;
    v7 = wcsrchr(Str, 0x5Cu);
    if ( v7 )
      v7[1] = 0;
    else
      *Str = 0;
  }
  else
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    if ( v6 >= 0 )
      v6 = -2147467259;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
      0x3Eu,
      L"GetModulePath",
      L"CBRAEx",
      L"cchFileName != 0",
      v6);
    if ( IsDebuggerPresent() )
    {
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
        62,
        L"GetModulePath",
        L"CBRAEx",
        L"cchFileName != 0",
        v6);
    }
    else
    {
      LODWORD(v9) = v6;
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\common\\srcutils\\srcutils.cpp",
        62,
        L"GetModulePath",
        L"CBRAEx",
        L"cchFileName != 0",
        v9);
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x140007bf8  push    rbx
0x140007bfa  push    rbp
0x140007bfb  push    rsi
0x140007bfc  push    rdi
0x140007bfd  push    r14
0x140007bff  push    r15
0x140007c01  sub     rsp, 48h
0x140007c05  lea     rbp, aGetmodulepath; "GetModulePath"
0x140007c0c  mov     rdi, rcx
0x140007c0f  lea     rsi, aTermsrvWmsSrcC_4; "termsrv\\wms\\src\\common\\srcutils\\sr"...
0x140007c16  test    rcx, rcx
0x140007c19  jnz     short loc_140007C8D
0x140007c1b  lea     ebx, [rcx+38h]
0x140007c1e  mov     r8, rbp; unsigned __int16 *
0x140007c21  lea     r14, aLpfilenameNull; "lpFilename != NULL"
0x140007c28  mov     edx, ebx; unsigned int
0x140007c2a  mov     rcx, rsi; unsigned __int16 *
0x140007c2d  mov     [rsp+78h+var_58], r14; unsigned __int16 *
0x140007c32  call    ?LOGASSERT@@YAXPEBGK000@Z; LOGASSERT(ushort const *,ulong,ushort const *,ushort const *,ushort const *)
0x140007c37  call    cs:__imp_IsDebuggerPresent
0x140007c3d  test    eax, eax
0x140007c3f  lea     rax, aAssert; "ASSERT"
0x140007c46  jz      short loc_140007C6E
0x140007c48  mov     [rsp+78h+var_48], r14
0x140007c4d  lea     rdx, aSDSAssertionFa; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140007c54  mov     qword ptr [rsp+78h+var_50], rax
0x140007c59  lea     ecx, [rdi+2]; unsigned __int8
0x140007c5c  mov     r9d, ebx
0x140007c5f  mov     [rsp+78h+var_58], rbp
0x140007c64  mov     r8, rsi
0x140007c67  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140007c6c  jmp     short loc_140007C8D
0x140007c6e  mov     qword ptr [rsp+78h+var_50], r14
0x140007c73  lea     rcx, aAssertionFaile_0; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140007c7a  mov     r9, rbp
0x140007c7d  mov     [rsp+78h+var_58], rax
0x140007c82  mov     r8d, ebx
0x140007c85  mov     rdx, rsi
0x140007c88  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140007c8d  mov     r8d, 103h; nSize
0x140007c93  mov     rdx, rdi; lpFilename
0x140007c96  xor     ecx, ecx; hModule
0x140007c98  call    cs:__imp_GetModuleFileNameW
0x140007c9e  test    eax, eax
0x140007ca0  jnz     loc_140007D4A
0x140007ca6  call    cs:__imp_GetLastError
0x140007cac  mov     ebx, eax
0x140007cae  test    eax, eax
0x140007cb0  jle     short loc_140007CBB
0x140007cb2  movzx   ebx, ax
0x140007cb5  or      ebx, 80070000h
0x140007cbb  mov     eax, 80004005h
0x140007cc0  lea     r15, aCbraex; "CBRAEx"
0x140007cc7  test    ebx, ebx
0x140007cc9  lea     r14, aCchfilename0; "cchFileName != 0"
0x140007cd0  mov     edi, 3Eh ; '>'
0x140007cd5  mov     r9, r15; unsigned __int16 *
0x140007cd8  cmovns  ebx, eax
0x140007cdb  mov     r8, rbp; unsigned __int16 *
0x140007cde  mov     [rsp+78h+var_50], ebx; int
0x140007ce2  mov     edx, edi; unsigned int
0x140007ce4  mov     rcx, rsi; unsigned __int16 *
0x140007ce7  mov     [rsp+78h+var_58], r14; unsigned __int16 *
0x140007cec  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140007cf1  call    cs:__imp_IsDebuggerPresent
0x140007cf7  test    eax, eax
0x140007cf9  jz      short loc_140007D25
0x140007cfb  mov     [rsp+78h+var_40], ebx
0x140007cff  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140007d06  mov     [rsp+78h+var_48], r14
0x140007d0b  lea     ecx, [rdi-3Ch]; unsigned __int8
0x140007d0e  mov     qword ptr [rsp+78h+var_50], r15
0x140007d13  mov     r9d, edi
0x140007d16  mov     r8, rsi
0x140007d19  mov     [rsp+78h+var_58], rbp
0x140007d1e  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140007d23  jmp     short loc_140007D71
0x140007d25  mov     dword ptr [rsp+78h+var_48], ebx
0x140007d29  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140007d30  mov     qword ptr [rsp+78h+var_50], r14
0x140007d35  mov     r9, rbp
0x140007d38  mov     r8d, edi
0x140007d3b  mov     [rsp+78h+var_58], r15
0x140007d40  mov     rdx, rsi
0x140007d43  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140007d48  jmp     short loc_140007D71
0x140007d4a  xor     eax, eax
0x140007d4c  xor     ebx, ebx
0x140007d4e  mov     rcx, rdi; Str
0x140007d51  mov     [rdi+206h], ax
0x140007d58  lea     edx, [rbx+5Ch]; Ch
0x140007d5b  call    cs:__imp_wcsrchr
0x140007d61  test    rax, rax
0x140007d64  jnz     short loc_140007D6B
0x140007d66  mov     [rdi], ax
0x140007d69  jmp     short loc_140007D71
0x140007d6b  xor     ecx, ecx
0x140007d6d  mov     [rax+2], cx
0x140007d71  mov     eax, ebx
0x140007d73  add     rsp, 48h
0x140007d77  pop     r15
0x140007d79  pop     r14
0x140007d7b  pop     rdi
0x140007d7c  pop     rsi
0x140007d7d  pop     rbp
0x140007d7e  pop     rbx
0x140007d7f  retn
```
