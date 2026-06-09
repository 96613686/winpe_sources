# GetLanguagesClosenessScore(ushort const * const,ushort const * const)

- ea: `0x1800180b4`
- end: `0x1800181bc`
- name: `?GetLanguagesClosenessScore@@YAHQEBG0@Z`
- size: `264`
- prototype: `__int64 __fastcall(PCWSTR sourceString, PCWSTR)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180013c74`
- `0x18001568c`
- `0x18001f0e0`

## callees

- `0x180003520`
- `0x1800180b4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180018118`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180018159`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180018118`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180018159`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001812d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001816e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001812d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001816e`
- `Bcp47Langs!Bcp47GetDistance` at `0x180018181`
- `Bcp47Langs!Bcp47GetDistance` at `0x180018181`

## pseudocode

```c
__int64 __fastcall GetLanguagesClosenessScore(PCWSTR sourceString, PCWSTR a2)
{
  unsigned __int64 v3; // rsi
  unsigned __int64 v4; // rdi
  unsigned int v6; // ebx
  HSTRING v7; // rdi
  HSTRING string; // [rsp+20h] [rbp-78h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+28h] [rbp-70h] BYREF
  HSTRING v11; // [rsp+40h] [rbp-58h] BYREF
  HSTRING_HEADER v12; // [rsp+48h] [rbp-50h] BYREF
  int v13; // [rsp+60h] [rbp-38h] BYREF

  v3 = -1;
  v13 = 0;
  v4 = -1;
  v6 = 0;
  do
    ++v4;
  while ( a2[v4] );
  if ( v4 > 0xFFFFFFFF )
  {
    LODWORD(v4) = -1;
    RaiseException(0xC000000D, 1u, 0, 0);
  }
  WindowsCreateStringReference(a2, v4, &hstringHeader, &string);
  v7 = string;
  do
    ++v3;
  while ( sourceString[v3] );
  if ( v3 > 0xFFFFFFFF )
  {
    LODWORD(v3) = -1;
    RaiseException(0xC000000D, 1u, 0, 0);
  }
  WindowsCreateStringReference(sourceString, v3, &v12, &v11);
  if ( (int)Bcp47GetDistance(v11, v7, &v13) >= 0 )
    return (unsigned int)(100 - v13);
  return v6;
}

```

## disassembly

```asm
0x1800180b4  mov     [rsp+arg_10], rbx
0x1800180b9  mov     [rsp+arg_18], rbp
0x1800180be  push    rsi
0x1800180bf  push    rdi
0x1800180c0  push    r12
0x1800180c2  push    r14
0x1800180c4  push    r15
0x1800180c6  sub     rsp, 70h
0x1800180ca  mov     rax, cs:__security_cookie
0x1800180d1  xor     rax, rsp
0x1800180d4  mov     [rsp+98h+var_30], rax
0x1800180d9  xor     r15d, r15d
0x1800180dc  mov     rbp, rdx
0x1800180df  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800180e3  mov     [rsp+98h+var_38], r15d
0x1800180e8  mov     rdi, rsi
0x1800180eb  mov     r14, rcx
0x1800180ee  mov     ebx, r15d
0x1800180f1  inc     rdi
0x1800180f4  cmp     [rdx+rdi*2], r15w
0x1800180f9  jnz     short loc_1800180F1
0x1800180fb  mov     r12d, 0FFFFFFFFh
0x180018101  cmp     rdi, r12
0x180018104  jbe     short loc_18001811E
0x180018106  xor     r9d, r9d; lpArguments
0x180018109  xor     r8d, r8d; nNumberOfArguments
0x18001810c  mov     ecx, 0C000000Dh; dwExceptionCode
0x180018111  mov     edi, r12d
0x180018114  lea     edx, [r9+1]; dwExceptionFlags
0x180018118  call    cs:__imp_RaiseException
0x18001811e  lea     r9, [rsp+98h+string]; string
0x180018123  mov     edx, edi; length
0x180018125  lea     r8, [rsp+98h+hstringHeader]; hstringHeader
0x18001812a  mov     rcx, rbp; sourceString
0x18001812d  call    cs:__imp_WindowsCreateStringReference
0x180018133  mov     rdi, [rsp+98h+string]
0x180018138  inc     rsi
0x18001813b  cmp     [r14+rsi*2], r15w
0x180018140  jnz     short loc_180018138
0x180018142  cmp     rsi, r12
0x180018145  jbe     short loc_18001815F
0x180018147  xor     r9d, r9d; lpArguments
0x18001814a  xor     r8d, r8d; nNumberOfArguments
0x18001814d  mov     ecx, 0C000000Dh; dwExceptionCode
0x180018152  mov     esi, r12d
0x180018155  lea     edx, [r9+1]; dwExceptionFlags
0x180018159  call    cs:__imp_RaiseException
0x18001815f  lea     r9, [rsp+98h+var_58]; string
0x180018164  mov     edx, esi; length
0x180018166  lea     r8, [rsp+98h+var_50]; hstringHeader
0x18001816b  mov     rcx, r14; sourceString
0x18001816e  call    cs:__imp_WindowsCreateStringReference
0x180018174  mov     rcx, [rsp+98h+var_58]
0x180018179  lea     r8, [rsp+98h+var_38]
0x18001817e  mov     rdx, rdi
0x180018181  call    cs:__imp_Bcp47GetDistance
0x180018187  test    eax, eax
0x180018189  js      short loc_180018194
0x18001818b  mov     ebx, 64h ; 'd'
0x180018190  sub     ebx, [rsp+98h+var_38]
0x180018194  mov     eax, ebx
0x180018196  mov     rcx, [rsp+98h+var_30]
0x18001819b  xor     rcx, rsp; StackCookie
0x18001819e  call    __security_check_cookie
0x1800181a3  lea     r11, [rsp+98h+var_28]
0x1800181a8  mov     rbx, [r11+40h]
0x1800181ac  mov     rbp, [r11+48h]
0x1800181b0  mov     rsp, r11
0x1800181b3  pop     r15
0x1800181b5  pop     r14
0x1800181b7  pop     r12
0x1800181b9  pop     rdi
0x1800181ba  pop     rsi
0x1800181bb  retn
```
