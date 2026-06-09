# SdbMakeIndexKeyFromStringEx

- ea: `0x14003ac28`
- end: `0x14003ad99`
- name: `SdbMakeIndexKeyFromStringEx`
- size: `369`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x14003aae0`
- `0x14003af10`

## callees

- `0x14000440f`
- `0x1400079f0`
- `0x14003ac28`
- `0x14003e364`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x14003aca5`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14003aca5`
- `ntoskrnl!RtlUpcaseUnicodeString` at `0x14003acc8`
- `ntoskrnl!RtlUpcaseUnicodeString` at `0x14003acc8`

## pseudocode

```c
__int64 __fastcall SdbMakeIndexKeyFromStringEx(PCWSTR SourceString, char a2)
{
  unsigned __int64 v2; // rax
  const WCHAR *v4; // rdx
  __int64 result; // rax
  unsigned __int64 v6; // r9
  unsigned __int64 v7; // rdx
  bool v8; // cc
  unsigned __int64 v9; // rcx
  char *v10; // r8
  unsigned __int16 *v11; // r9
  unsigned __int64 v12; // rcx
  unsigned __int16 v13; // ax
  __int16 v14; // ax
  UNICODE_STRING SourceStringa; // [rsp+30h] [rbp-29h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-19h] BYREF
  struct _UNICODE_STRING v17; // [rsp+50h] [rbp-9h] BYREF
  _BYTE v18[16]; // [rsp+60h] [rbp+7h] BYREF
  char v19; // [rsp+70h] [rbp+17h] BYREF

  v2 = -1;
  do
    ++v2;
  while ( SourceString[v2] );
  DestinationString = 0;
  SourceStringa = 0;
  v17 = 0;
  if ( v2 > 8 && (a2 & 2) != 0 )
    v4 = &SourceString[v2 - 8];
  else
    v4 = SourceString;
  RtlInitUnicodeString_0(&DestinationString, v4);
  SourceStringa.Buffer = (wchar_t *)&v19;
  SourceStringa.MaximumLength = 16;
  RtlCopyUnicodeString(&SourceStringa, &DestinationString);
  v17.MaximumLength = 16;
  v17.Buffer = (wchar_t *)v18;
  if ( RtlUpcaseUnicodeString(&v17, &SourceStringa, 0) < 0 )
  {
    AslLogCallPrintf(1, "SdbMakeIndexKeyFromStringEx", 1633, "Failed to upcase unicode string \"%ws\"", SourceString);
    return 0;
  }
  v6 = 0;
  v7 = (unsigned __int64)v17.Length >> 1;
  if ( v7 )
  {
    while ( 1 )
    {
      v8 = v7 <= 8;
      if ( v7 >= 8 )
        break;
      v9 = v7 + 1;
      if ( !HIBYTE(v17.Buffer[v6]) )
        v9 = v7;
      ++v6;
      v7 = v9;
      if ( v6 >= (unsigned __int64)v17.Length >> 1 )
        goto LABEL_15;
    }
  }
  else
  {
LABEL_15:
    v8 = v7 <= 8;
  }
  if ( !v8 )
    return 0;
  v10 = (char *)&v17.MaximumLength + 5;
  result = 0;
  *(_QWORD *)&v17.Length = 0;
  v11 = (unsigned __int16 *)v18;
  v12 = 0;
  if ( v7 )
  {
    do
    {
      v13 = *v11++;
      *v10-- = v13;
      v14 = HIBYTE(v13);
      if ( (_BYTE)v14 )
      {
        if ( v12 < 7 )
        {
          *v10-- = v14;
          ++v12;
        }
      }
      ++v12;
    }
    while ( v12 < v7 );
    return *(_QWORD *)&v17.Length;
  }
  return result;
}

```

## disassembly

```asm
0x14003ac28  push    rbp
0x14003ac2a  push    rbx
0x14003ac2b  push    rsi
0x14003ac2c  push    rdi
0x14003ac2d  lea     rbp, [rsp-3Fh]
0x14003ac32  sub     rsp, 98h
0x14003ac39  mov     rax, cs:__security_cookie
0x14003ac40  xor     rax, rsp
0x14003ac43  mov     [rbp+57h+var_30], rax
0x14003ac47  or      rax, 0FFFFFFFFFFFFFFFFh
0x14003ac4b  mov     rbx, rcx
0x14003ac4e  xor     esi, esi
0x14003ac50  inc     rax
0x14003ac53  cmp     [rcx+rax*2], si
0x14003ac57  jnz     short loc_14003AC50
0x14003ac59  xorps   xmm0, xmm0
0x14003ac5c  xorps   xmm1, xmm1
0x14003ac5f  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14003ac63  movups  xmmword ptr [rbp+57h+SourceString.Length], xmm1
0x14003ac67  movups  xmmword ptr [rbp+57h+var_60.Length], xmm0
0x14003ac6b  cmp     rax, 8
0x14003ac6f  jbe     short loc_14003AC80
0x14003ac71  test    dl, 2
0x14003ac74  jz      short loc_14003AC80
0x14003ac76  lea     rdx, [rcx-10h]
0x14003ac7a  lea     rdx, [rdx+rax*2]
0x14003ac7e  jmp     short loc_14003AC83
0x14003ac80  mov     rdx, rbx; SourceString
0x14003ac83  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14003ac87  call    RtlInitUnicodeString_0
0x14003ac8c  lea     rax, [rbp+57h+var_40]
0x14003ac90  mov     edi, 10h
0x14003ac95  lea     rdx, [rbp+57h+DestinationString]; SourceString
0x14003ac99  mov     [rbp+57h+SourceString.Buffer], rax
0x14003ac9d  lea     rcx, [rbp+57h+SourceString]; DestinationString
0x14003aca1  mov     [rbp+57h+SourceString.MaximumLength], di
0x14003aca5  call    cs:__imp_RtlCopyUnicodeString
0x14003acac  nop     dword ptr [rax+rax+00h]
0x14003acb1  lea     rax, [rbp+57h+var_50]
0x14003acb5  mov     [rbp+57h+var_60.MaximumLength], di
0x14003acb9  xor     r8d, r8d; AllocateDestinationString
0x14003acbc  mov     [rbp+57h+var_60.Buffer], rax
0x14003acc0  lea     rdx, [rbp+57h+SourceString]; SourceString
0x14003acc4  lea     rcx, [rbp+57h+var_60]; DestinationString
0x14003acc8  call    cs:__imp_RtlUpcaseUnicodeString
0x14003accf  nop     dword ptr [rax+rax+00h]
0x14003acd4  test    eax, eax
0x14003acd6  jns     short loc_14003AD00
0x14003acd8  lea     r9, aFailedToUpcase; "Failed to upcase unicode string \"%ws\""
0x14003acdf  mov     [rsp+0B0h+var_90], rbx
0x14003ace4  mov     r8d, 661h
0x14003acea  lea     rdx, aSdbmakeindexke; "SdbMakeIndexKeyFromStringEx"
0x14003acf1  lea     ecx, [rdi-0Fh]
0x14003acf4  call    AslLogCallPrintf
0x14003acf9  xor     eax, eax
0x14003acfb  jmp     loc_14003AD80
0x14003ad00  movzx   r8d, [rbp+57h+var_60.Length]
0x14003ad05  mov     r9, rsi
0x14003ad08  shr     r8, 1
0x14003ad0b  mov     rdx, r8
0x14003ad0e  jz      short loc_14003AD32
0x14003ad10  mov     r10, [rbp+57h+var_60.Buffer]
0x14003ad14  cmp     rdx, 8
0x14003ad18  jnb     short loc_14003AD36
0x14003ad1a  cmp     [r10+r9*2+1], sil
0x14003ad1f  lea     rcx, [rdx+1]
0x14003ad23  cmovz   rcx, rdx
0x14003ad27  inc     r9
0x14003ad2a  mov     rdx, rcx
0x14003ad2d  cmp     r9, r8
0x14003ad30  jb      short loc_14003AD14
0x14003ad32  cmp     rdx, 8
0x14003ad36  ja      short loc_14003ACF9
0x14003ad38  lea     r8, [rbp+57h+var_60+7]
0x14003ad3c  mov     rax, rsi
0x14003ad3f  mov     qword ptr [rbp+57h+var_60.Length], rax
0x14003ad43  lea     r9, [rbp+57h+var_50]
0x14003ad47  mov     rcx, rsi
0x14003ad4a  test    rdx, rdx
0x14003ad4d  jz      short loc_14003AD80
0x14003ad4f  movzx   eax, word ptr [r9]
0x14003ad53  lea     r9, [r9+2]
0x14003ad57  mov     [r8], al
0x14003ad5a  dec     r8
0x14003ad5d  shr     ax, 8
0x14003ad61  test    al, al
0x14003ad63  jz      short loc_14003AD74
0x14003ad65  cmp     rcx, 7
0x14003ad69  jnb     short loc_14003AD74
0x14003ad6b  mov     [r8], al
0x14003ad6e  dec     r8
0x14003ad71  inc     rcx
0x14003ad74  inc     rcx
0x14003ad77  cmp     rcx, rdx
0x14003ad7a  jb      short loc_14003AD4F
0x14003ad7c  mov     rax, qword ptr [rbp+57h+var_60.Length]
0x14003ad80  mov     rcx, [rbp+57h+var_30]
0x14003ad84  xor     rcx, rsp; StackCookie
0x14003ad87  call    __security_check_cookie
0x14003ad8c  add     rsp, 98h
0x14003ad93  pop     rdi
0x14003ad94  pop     rsi
0x14003ad95  pop     rbx
0x14003ad96  pop     rbp
0x14003ad97  retn
```
