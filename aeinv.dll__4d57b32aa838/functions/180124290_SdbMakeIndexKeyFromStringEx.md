# SdbMakeIndexKeyFromStringEx

- ea: `0x180124290`
- end: `0x1801243f1`
- name: `SdbMakeIndexKeyFromStringEx`
- size: `353`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1801240d4`
- `0x180124b28`

## callees

- `0x1800197d4`
- `0x180059920`
- `0x180124290`

## import_xrefs

- `ntdll!RtlUpcaseUnicodeString` at `0x18012432b`
- `ntdll!RtlUpcaseUnicodeString` at `0x18012432b`
- `ntdll!RtlCopyUnicodeString` at `0x18012430e`
- `ntdll!RtlCopyUnicodeString` at `0x18012430e`
- `ntdll!RtlInitUnicodeString` at `0x1801242ef`
- `ntdll!RtlInitUnicodeString` at `0x1801242ef`

## pseudocode

```c
__int64 __fastcall SdbMakeIndexKeyFromStringEx(PCWSTR SourceString, char a2)
{
  unsigned __int64 v2; // rax
  const WCHAR *v3; // rdx
  __int64 result; // rax
  unsigned __int64 v5; // r8
  unsigned __int64 v6; // rdx
  bool v7; // cc
  unsigned __int64 v8; // rax
  char *v9; // r8
  unsigned __int16 *v10; // r9
  unsigned __int64 v11; // rcx
  unsigned __int16 v12; // ax
  __int16 v13; // ax
  UNICODE_STRING SourceStringa; // [rsp+30h] [rbp-29h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-19h] BYREF
  struct _UNICODE_STRING v16; // [rsp+50h] [rbp-9h] BYREF
  _BYTE v17[16]; // [rsp+60h] [rbp+7h] BYREF
  char v18; // [rsp+70h] [rbp+17h] BYREF

  v2 = -1;
  do
    ++v2;
  while ( SourceString[v2] );
  DestinationString = 0;
  SourceStringa = 0;
  v16 = 0;
  if ( v2 > 8 && (a2 & 2) != 0 )
    v3 = &SourceString[v2 - 8];
  else
    v3 = SourceString;
  RtlInitUnicodeString(&DestinationString, v3);
  SourceStringa.Buffer = (PWSTR)&v18;
  SourceStringa.MaximumLength = 16;
  RtlCopyUnicodeString(&SourceStringa, &DestinationString);
  v16.MaximumLength = 16;
  v16.Buffer = (PWSTR)v17;
  if ( RtlUpcaseUnicodeString(&v16, &SourceStringa, 0) < 0 )
  {
    AslLogCallPrintf(
      1,
      (unsigned int)"SdbMakeIndexKeyFromStringEx",
      1633,
      (unsigned int)"Failed to upcase unicode string \"%ws\"");
    return 0;
  }
  v5 = 0;
  v6 = (unsigned __int64)v16.Length >> 1;
  if ( v6 )
  {
    while ( 1 )
    {
      v7 = v6 <= 8;
      if ( v6 >= 8 )
        break;
      v8 = v6 + 1;
      if ( !HIBYTE(v16.Buffer[v5]) )
        v8 = v6;
      ++v5;
      v6 = v8;
      if ( v5 >= (unsigned __int64)v16.Length >> 1 )
        goto LABEL_15;
    }
  }
  else
  {
LABEL_15:
    v7 = v6 <= 8;
  }
  if ( !v7 )
    return 0;
  v9 = (char *)&v16.MaximumLength + 5;
  result = 0;
  *(_QWORD *)&v16.Length = 0;
  v10 = (unsigned __int16 *)v17;
  v11 = 0;
  if ( v6 )
  {
    do
    {
      v12 = *v10++;
      *v9-- = v12;
      v13 = HIBYTE(v12);
      if ( (_BYTE)v13 )
      {
        if ( v11 < 7 )
        {
          *v9-- = v13;
          ++v11;
        }
      }
      ++v11;
    }
    while ( v11 < v6 );
    return *(_QWORD *)&v16.Length;
  }
  return result;
}

```

## disassembly

```asm
0x180124290  push    rbp
0x180124292  push    rbx
0x180124293  push    rsi
0x180124294  push    rdi
0x180124295  lea     rbp, [rsp-3Fh]
0x18012429a  sub     rsp, 98h
0x1801242a1  mov     rax, cs:__security_cookie
0x1801242a8  xor     rax, rsp
0x1801242ab  mov     [rbp+57h+var_30], rax
0x1801242af  or      rax, 0FFFFFFFFFFFFFFFFh
0x1801242b3  mov     rbx, rcx
0x1801242b6  xor     esi, esi
0x1801242b8  inc     rax
0x1801242bb  cmp     [rcx+rax*2], si
0x1801242bf  jnz     short loc_1801242B8
0x1801242c1  xorps   xmm0, xmm0
0x1801242c4  xorps   xmm1, xmm1
0x1801242c7  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1801242cb  movups  xmmword ptr [rbp+57h+SourceString.Length], xmm1
0x1801242cf  movups  xmmword ptr [rbp+57h+var_60.Length], xmm0
0x1801242d3  cmp     rax, 8
0x1801242d7  jbe     short loc_1801242E8
0x1801242d9  test    dl, 2
0x1801242dc  jz      short loc_1801242E8
0x1801242de  add     rcx, 0FFFFFFFFFFFFFFF0h
0x1801242e2  lea     rdx, [rcx+rax*2]
0x1801242e6  jmp     short loc_1801242EB
0x1801242e8  mov     rdx, rbx; SourceString
0x1801242eb  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1801242ef  call    cs:__imp_RtlInitUnicodeString
0x1801242f5  lea     rax, [rbp+57h+var_40]
0x1801242f9  mov     edi, 10h
0x1801242fe  lea     rdx, [rbp+57h+DestinationString]; SourceString
0x180124302  mov     [rbp+57h+SourceString.Buffer], rax
0x180124306  lea     rcx, [rbp+57h+SourceString]; DestinationString
0x18012430a  mov     [rbp+57h+SourceString.MaximumLength], di
0x18012430e  call    cs:__imp_RtlCopyUnicodeString
0x180124314  lea     rax, [rbp+57h+var_50]
0x180124318  mov     [rbp+57h+var_60.MaximumLength], di
0x18012431c  xor     r8d, r8d; AllocateDestinationString
0x18012431f  mov     [rbp+57h+var_60.Buffer], rax
0x180124323  lea     rdx, [rbp+57h+SourceString]; SourceString
0x180124327  lea     rcx, [rbp+57h+var_60]; DestinationString
0x18012432b  call    cs:__imp_RtlUpcaseUnicodeString
0x180124331  test    eax, eax
0x180124333  jns     short loc_18012435A
0x180124335  lea     r9, aFailedToUpcase; "Failed to upcase unicode string \"%ws\""
0x18012433c  mov     [rsp+0B0h+var_90], rbx
0x180124341  mov     r8d, 661h
0x180124347  lea     rdx, aSdbmakeindexke; "SdbMakeIndexKeyFromStringEx"
0x18012434e  lea     ecx, [rdi-0Fh]
0x180124351  call    AslLogCallPrintf
0x180124356  xor     eax, eax
0x180124358  jmp     short loc_1801243D9
0x18012435a  movzx   ecx, [rbp+57h+var_60.Length]
0x18012435e  mov     r8, rsi
0x180124361  shr     rcx, 1
0x180124364  mov     rdx, rcx
0x180124367  jz      short loc_18012438B
0x180124369  mov     r9, [rbp+57h+var_60.Buffer]
0x18012436d  cmp     rdx, 8
0x180124371  jnb     short loc_18012438F
0x180124373  cmp     [r9+r8*2+1], sil
0x180124378  lea     rax, [rdx+1]
0x18012437c  cmovz   rax, rdx
0x180124380  inc     r8
0x180124383  mov     rdx, rax
0x180124386  cmp     r8, rcx
0x180124389  jb      short loc_18012436D
0x18012438b  cmp     rdx, 8
0x18012438f  ja      short loc_180124356
0x180124391  lea     r8, [rbp+57h+var_60+7]
0x180124395  mov     rax, rsi
0x180124398  mov     qword ptr [rbp+57h+var_60.Length], rax
0x18012439c  lea     r9, [rbp+57h+var_50]
0x1801243a0  mov     rcx, rsi
0x1801243a3  test    rdx, rdx
0x1801243a6  jz      short loc_1801243D9
0x1801243a8  movzx   eax, word ptr [r9]
0x1801243ac  lea     r9, [r9+2]
0x1801243b0  mov     [r8], al
0x1801243b3  dec     r8
0x1801243b6  shr     ax, 8
0x1801243ba  test    al, al
0x1801243bc  jz      short loc_1801243CD
0x1801243be  cmp     rcx, 7
0x1801243c2  jnb     short loc_1801243CD
0x1801243c4  mov     [r8], al
0x1801243c7  dec     r8
0x1801243ca  inc     rcx
0x1801243cd  inc     rcx
0x1801243d0  cmp     rcx, rdx
0x1801243d3  jb      short loc_1801243A8
0x1801243d5  mov     rax, qword ptr [rbp+57h+var_60.Length]
0x1801243d9  mov     rcx, [rbp+57h+var_30]
0x1801243dd  xor     rcx, rsp; StackCookie
0x1801243e0  call    __security_check_cookie
0x1801243e5  add     rsp, 98h
0x1801243ec  pop     rdi
0x1801243ed  pop     rsi
0x1801243ee  pop     rbx
0x1801243ef  pop     rbp
0x1801243f0  retn
```
