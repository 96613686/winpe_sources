# GetLanguagesClosenessScore(ushort const * const,ushort const * const)

- ea: `0x180053fb4`
- end: `0x1800540bc`
- name: `?GetLanguagesClosenessScore@@YAHQEBG0@Z`
- size: `264`
- prototype: `__int64 __fastcall(PCWSTR sourceString, PCWSTR)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180053e18`

## callees

- `0x180053fb4`
- `0x180061320`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180054018`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180054059`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180054018`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180054059`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005402d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005406e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005402d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005406e`
- `Bcp47Langs!Bcp47GetDistance` at `0x180054081`
- `Bcp47Langs!Bcp47GetDistance` at `0x180054081`

## pseudocode

```c
__int64 __fastcall GetLanguagesClosenessScore(PCWSTR sourceString, PCWSTR a2)
{
  unsigned __int64 v3; // rsi
  unsigned __int64 v4; // rdi
  unsigned int v6; // ebx
  HSTRING v7; // rdi
  int v9; // [rsp+20h] [rbp-78h] BYREF
  HSTRING string; // [rsp+28h] [rbp-70h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-68h] BYREF
  HSTRING v12; // [rsp+48h] [rbp-50h] BYREF
  HSTRING_HEADER v13; // [rsp+50h] [rbp-48h] BYREF

  v3 = -1;
  v9 = 0;
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
  WindowsCreateStringReference(sourceString, v3, &v13, &v12);
  if ( (int)Bcp47GetDistance(v12, v7, &v9) >= 0 )
    return (unsigned int)(100 - v9);
  return v6;
}

```

## disassembly

```asm
0x180053fb4  mov     [rsp+arg_10], rbx
0x180053fb9  mov     [rsp+arg_18], rbp
0x180053fbe  push    rsi
0x180053fbf  push    rdi
0x180053fc0  push    r12
0x180053fc2  push    r14
0x180053fc4  push    r15
0x180053fc6  sub     rsp, 70h
0x180053fca  mov     rax, cs:__security_cookie
0x180053fd1  xor     rax, rsp
0x180053fd4  mov     [rsp+98h+var_30], rax
0x180053fd9  xor     r15d, r15d
0x180053fdc  mov     rbp, rdx
0x180053fdf  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180053fe3  mov     [rsp+98h+var_78], r15d
0x180053fe8  mov     rdi, rsi
0x180053feb  mov     r14, rcx
0x180053fee  mov     ebx, r15d
0x180053ff1  inc     rdi
0x180053ff4  cmp     [rdx+rdi*2], r15w
0x180053ff9  jnz     short loc_180053FF1
0x180053ffb  mov     r12d, 0FFFFFFFFh
0x180054001  cmp     rdi, r12
0x180054004  jbe     short loc_18005401E
0x180054006  xor     r9d, r9d; lpArguments
0x180054009  xor     r8d, r8d; nNumberOfArguments
0x18005400c  mov     ecx, 0C000000Dh; dwExceptionCode
0x180054011  mov     edi, r12d
0x180054014  lea     edx, [r9+1]; dwExceptionFlags
0x180054018  call    cs:__imp_RaiseException
0x18005401e  lea     r9, [rsp+98h+string]; string
0x180054023  mov     edx, edi; length
0x180054025  lea     r8, [rsp+98h+hstringHeader]; hstringHeader
0x18005402a  mov     rcx, rbp; sourceString
0x18005402d  call    cs:__imp_WindowsCreateStringReference
0x180054033  mov     rdi, [rsp+98h+string]
0x180054038  inc     rsi
0x18005403b  cmp     [r14+rsi*2], r15w
0x180054040  jnz     short loc_180054038
0x180054042  cmp     rsi, r12
0x180054045  jbe     short loc_18005405F
0x180054047  xor     r9d, r9d; lpArguments
0x18005404a  xor     r8d, r8d; nNumberOfArguments
0x18005404d  mov     ecx, 0C000000Dh; dwExceptionCode
0x180054052  mov     esi, r12d
0x180054055  lea     edx, [r9+1]; dwExceptionFlags
0x180054059  call    cs:__imp_RaiseException
0x18005405f  lea     r9, [rsp+98h+var_50]; string
0x180054064  mov     edx, esi; length
0x180054066  lea     r8, [rsp+98h+var_48]; hstringHeader
0x18005406b  mov     rcx, r14; sourceString
0x18005406e  call    cs:__imp_WindowsCreateStringReference
0x180054074  mov     rcx, [rsp+98h+var_50]
0x180054079  lea     r8, [rsp+98h+var_78]
0x18005407e  mov     rdx, rdi
0x180054081  call    cs:__imp_Bcp47GetDistance
0x180054087  test    eax, eax
0x180054089  js      short loc_180054094
0x18005408b  mov     ebx, 64h ; 'd'
0x180054090  sub     ebx, [rsp+98h+var_78]
0x180054094  mov     eax, ebx
0x180054096  mov     rcx, [rsp+98h+var_30]
0x18005409b  xor     rcx, rsp; StackCookie
0x18005409e  call    __security_check_cookie
0x1800540a3  lea     r11, [rsp+98h+var_28]
0x1800540a8  mov     rbx, [r11+40h]
0x1800540ac  mov     rbp, [r11+48h]
0x1800540b0  mov     rsp, r11
0x1800540b3  pop     r15
0x1800540b5  pop     r14
0x1800540b7  pop     r12
0x1800540b9  pop     rdi
0x1800540ba  pop     rsi
0x1800540bb  retn
```
