# GetLanguagesClosenessScore(ushort const * const,ushort const * const)

- ea: `0x18002de4c`
- end: `0x18002df56`
- name: `?GetLanguagesClosenessScore@@YAHQEBG0@Z`
- size: `266`
- prototype: `__int64 __fastcall(PCWSTR sourceString, PCWSTR)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18002d3f0`

## callees

- `0x18002de4c`
- `0x180043090`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002deb0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002def2`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002deb0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002def2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002dec5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002df07`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002dec5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002df07`
- `Bcp47Langs!Bcp47GetDistance` at `0x18002df1b`
- `Bcp47Langs!Bcp47GetDistance` at `0x18002df1b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetLanguagesClosenessScore(PCWSTR sourceString, PCWSTR a2)
{
  unsigned int v4; // ebx
  unsigned __int64 v5; // rsi
  unsigned __int64 v6; // rdi
  HSTRING v7; // rdi
  int v9; // [rsp+20h] [rbp-78h] BYREF
  HSTRING string; // [rsp+28h] [rbp-70h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-68h] BYREF
  HSTRING v12; // [rsp+48h] [rbp-50h] BYREF
  HSTRING_HEADER v13; // [rsp+50h] [rbp-48h] BYREF

  v4 = 0;
  v9 = 0;
  v5 = -1;
  v6 = -1;
  do
    ++v6;
  while ( a2[v6] );
  if ( v6 > 0xFFFFFFFF )
  {
    LODWORD(v6) = -1;
    RaiseException(0xC000000D, 1u, 0, 0);
  }
  WindowsCreateStringReference(a2, v6, &hstringHeader, &string);
  v7 = string;
  do
    ++v5;
  while ( sourceString[v5] );
  if ( v5 > 0xFFFFFFFF )
  {
    LODWORD(v5) = -1;
    RaiseException(0xC000000D, 1u, 0, 0);
  }
  WindowsCreateStringReference(sourceString, v5, &v13, &v12);
  if ( (int)Bcp47GetDistance(v12, v7, &v9) >= 0 )
    return (unsigned int)(100 - v9);
  return v4;
}

```

## disassembly

```asm
0x18002de4c  mov     [rsp+arg_10], rbx
0x18002de51  mov     [rsp+arg_18], rbp
0x18002de56  push    rsi
0x18002de57  push    rdi
0x18002de58  push    r12
0x18002de5a  push    r14
0x18002de5c  push    r15
0x18002de5e  sub     rsp, 70h
0x18002de62  mov     rax, cs:__security_cookie
0x18002de69  xor     rax, rsp
0x18002de6c  mov     [rsp+98h+var_30], rax
0x18002de71  mov     rbp, rdx
0x18002de74  mov     r14, rcx
0x18002de77  xor     r15d, r15d
0x18002de7a  mov     ebx, r15d
0x18002de7d  mov     [rsp+98h+var_78], r15d
0x18002de82  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18002de86  mov     rdi, rsi
0x18002de89  inc     rdi
0x18002de8c  cmp     [rdx+rdi*2], r15w
0x18002de91  jnz     short loc_18002DE89
0x18002de93  mov     r12d, 0FFFFFFFFh
0x18002de99  cmp     rdi, r12
0x18002de9c  jbe     short loc_18002DEB6
0x18002de9e  mov     edi, r12d
0x18002dea1  xor     r9d, r9d; lpArguments
0x18002dea4  xor     r8d, r8d; nNumberOfArguments
0x18002dea7  lea     edx, [r9+1]; dwExceptionFlags
0x18002deab  mov     ecx, 0C000000Dh; dwExceptionCode
0x18002deb0  call    cs:__imp_RaiseException
0x18002deb6  lea     r9, [rsp+98h+string]; string
0x18002debb  lea     r8, [rsp+98h+hstringHeader]; hstringHeader
0x18002dec0  mov     edx, edi; length
0x18002dec2  mov     rcx, rbp; sourceString
0x18002dec5  call    cs:__imp_WindowsCreateStringReference
0x18002decb  nop
0x18002decc  mov     rdi, [rsp+98h+string]
0x18002ded1  inc     rsi
0x18002ded4  cmp     [r14+rsi*2], r15w
0x18002ded9  jnz     short loc_18002DED1
0x18002dedb  cmp     rsi, r12
0x18002dede  jbe     short loc_18002DEF8
0x18002dee0  mov     esi, r12d
0x18002dee3  xor     r9d, r9d; lpArguments
0x18002dee6  xor     r8d, r8d; nNumberOfArguments
0x18002dee9  lea     edx, [r9+1]; dwExceptionFlags
0x18002deed  mov     ecx, 0C000000Dh; dwExceptionCode
0x18002def2  call    cs:__imp_RaiseException
0x18002def8  lea     r9, [rsp+98h+var_50]; string
0x18002defd  lea     r8, [rsp+98h+var_48]; hstringHeader
0x18002df02  mov     edx, esi; length
0x18002df04  mov     rcx, r14; sourceString
0x18002df07  call    cs:__imp_WindowsCreateStringReference
0x18002df0d  nop
0x18002df0e  lea     r8, [rsp+98h+var_78]
0x18002df13  mov     rdx, rdi
0x18002df16  mov     rcx, [rsp+98h+var_50]
0x18002df1b  call    cs:__imp_Bcp47GetDistance
0x18002df21  test    eax, eax
0x18002df23  js      short loc_18002DF2E
0x18002df25  mov     ebx, 64h ; 'd'
0x18002df2a  sub     ebx, [rsp+98h+var_78]
0x18002df2e  mov     eax, ebx
0x18002df30  mov     rcx, [rsp+98h+var_30]
0x18002df35  xor     rcx, rsp; StackCookie
0x18002df38  call    __security_check_cookie
0x18002df3d  lea     r11, [rsp+98h+var_28]
0x18002df42  mov     rbx, [r11+40h]
0x18002df46  mov     rbp, [r11+48h]
0x18002df4a  mov     rsp, r11
0x18002df4d  pop     r15
0x18002df4f  pop     r14
0x18002df51  pop     r12
0x18002df53  pop     rdi
0x18002df54  pop     rsi
0x18002df55  retn
```
