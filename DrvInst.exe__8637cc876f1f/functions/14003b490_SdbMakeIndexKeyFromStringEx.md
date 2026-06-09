# SdbMakeIndexKeyFromStringEx

- ea: `0x14003b490`
- end: `0x14003b5f1`
- name: `SdbMakeIndexKeyFromStringEx`
- size: `353`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x14003b2d4`

## callees

- `0x14003b490`
- `0x14003bf18`
- `0x140045f30`

## import_xrefs

- `ntdll!RtlUpcaseUnicodeString` at `0x14003b52b`
- `ntdll!RtlUpcaseUnicodeString` at `0x14003b52b`
- `ntdll!RtlInitUnicodeString` at `0x14003b4ef`
- `ntdll!RtlInitUnicodeString` at `0x14003b4ef`
- `ntdll!RtlCopyUnicodeString` at `0x14003b50e`
- `ntdll!RtlCopyUnicodeString` at `0x14003b50e`

## pseudocode

```c
__int64 __fastcall SdbMakeIndexKeyFromStringEx(PCWSTR SourceString, char a2)
{
  unsigned __int64 v2; // rax
  const WCHAR *v4; // rdx
  __int64 result; // rax
  unsigned __int64 v6; // r8
  unsigned __int64 v7; // rdx
  bool v8; // cc
  unsigned __int64 v9; // rax
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
  RtlInitUnicodeString(&DestinationString, v4);
  SourceStringa.Buffer = (PWSTR)&v19;
  SourceStringa.MaximumLength = 16;
  RtlCopyUnicodeString(&SourceStringa, &DestinationString);
  v17.MaximumLength = 16;
  v17.Buffer = (PWSTR)v18;
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
0x14003b490  push    rbp
0x14003b492  push    rbx
0x14003b493  push    rsi
0x14003b494  push    rdi
0x14003b495  lea     rbp, [rsp-3Fh]
0x14003b49a  sub     rsp, 98h
0x14003b4a1  mov     rax, cs:__security_cookie
0x14003b4a8  xor     rax, rsp
0x14003b4ab  mov     [rbp+57h+var_30], rax
0x14003b4af  or      rax, 0FFFFFFFFFFFFFFFFh
0x14003b4b3  mov     rbx, rcx
0x14003b4b6  xor     esi, esi
0x14003b4b8  inc     rax
0x14003b4bb  cmp     [rcx+rax*2], si
0x14003b4bf  jnz     short loc_14003B4B8
0x14003b4c1  xorps   xmm0, xmm0
0x14003b4c4  xorps   xmm1, xmm1
0x14003b4c7  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14003b4cb  movups  xmmword ptr [rbp+57h+SourceString.Length], xmm1
0x14003b4cf  movups  xmmword ptr [rbp+57h+var_60.Length], xmm0
0x14003b4d3  cmp     rax, 8
0x14003b4d7  jbe     short loc_14003B4E8
0x14003b4d9  test    dl, 2
0x14003b4dc  jz      short loc_14003B4E8
0x14003b4de  add     rcx, 0FFFFFFFFFFFFFFF0h
0x14003b4e2  lea     rdx, [rcx+rax*2]
0x14003b4e6  jmp     short loc_14003B4EB
0x14003b4e8  mov     rdx, rbx; SourceString
0x14003b4eb  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14003b4ef  call    cs:__imp_RtlInitUnicodeString
0x14003b4f5  lea     rax, [rbp+57h+var_40]
0x14003b4f9  mov     edi, 10h
0x14003b4fe  lea     rdx, [rbp+57h+DestinationString]; SourceString
0x14003b502  mov     [rbp+57h+SourceString.Buffer], rax
0x14003b506  lea     rcx, [rbp+57h+SourceString]; DestinationString
0x14003b50a  mov     [rbp+57h+SourceString.MaximumLength], di
0x14003b50e  call    cs:__imp_RtlCopyUnicodeString
0x14003b514  lea     rax, [rbp+57h+var_50]
0x14003b518  mov     [rbp+57h+var_60.MaximumLength], di
0x14003b51c  xor     r8d, r8d; AllocateDestinationString
0x14003b51f  mov     [rbp+57h+var_60.Buffer], rax
0x14003b523  lea     rdx, [rbp+57h+SourceString]; SourceString
0x14003b527  lea     rcx, [rbp+57h+var_60]; DestinationString
0x14003b52b  call    cs:__imp_RtlUpcaseUnicodeString
0x14003b531  test    eax, eax
0x14003b533  jns     short loc_14003B55A
0x14003b535  lea     r9, aFailedToUpcase; "Failed to upcase unicode string \"%ws\""
0x14003b53c  mov     [rsp+0B0h+var_90], rbx
0x14003b541  mov     r8d, 661h
0x14003b547  lea     rdx, aSdbmakeindexke; "SdbMakeIndexKeyFromStringEx"
0x14003b54e  lea     ecx, [rdi-0Fh]
0x14003b551  call    AslLogCallPrintf
0x14003b556  xor     eax, eax
0x14003b558  jmp     short loc_14003B5D9
0x14003b55a  movzx   ecx, [rbp+57h+var_60.Length]
0x14003b55e  mov     r8, rsi
0x14003b561  shr     rcx, 1
0x14003b564  mov     rdx, rcx
0x14003b567  jz      short loc_14003B58B
0x14003b569  mov     r9, [rbp+57h+var_60.Buffer]
0x14003b56d  cmp     rdx, 8
0x14003b571  jnb     short loc_14003B58F
0x14003b573  cmp     [r9+r8*2+1], sil
0x14003b578  lea     rax, [rdx+1]
0x14003b57c  cmovz   rax, rdx
0x14003b580  inc     r8
0x14003b583  mov     rdx, rax
0x14003b586  cmp     r8, rcx
0x14003b589  jb      short loc_14003B56D
0x14003b58b  cmp     rdx, 8
0x14003b58f  ja      short loc_14003B556
0x14003b591  lea     r8, [rbp+57h+var_60+7]
0x14003b595  mov     rax, rsi
0x14003b598  mov     qword ptr [rbp+57h+var_60.Length], rax
0x14003b59c  lea     r9, [rbp+57h+var_50]
0x14003b5a0  mov     rcx, rsi
0x14003b5a3  test    rdx, rdx
0x14003b5a6  jz      short loc_14003B5D9
0x14003b5a8  movzx   eax, word ptr [r9]
0x14003b5ac  lea     r9, [r9+2]
0x14003b5b0  mov     [r8], al
0x14003b5b3  dec     r8
0x14003b5b6  shr     ax, 8
0x14003b5ba  test    al, al
0x14003b5bc  jz      short loc_14003B5CD
0x14003b5be  cmp     rcx, 7
0x14003b5c2  jnb     short loc_14003B5CD
0x14003b5c4  mov     [r8], al
0x14003b5c7  dec     r8
0x14003b5ca  inc     rcx
0x14003b5cd  inc     rcx
0x14003b5d0  cmp     rcx, rdx
0x14003b5d3  jb      short loc_14003B5A8
0x14003b5d5  mov     rax, qword ptr [rbp+57h+var_60.Length]
0x14003b5d9  mov     rcx, [rbp+57h+var_30]
0x14003b5dd  xor     rcx, rsp; StackCookie
0x14003b5e0  call    __security_check_cookie
0x14003b5e5  add     rsp, 98h
0x14003b5ec  pop     rdi
0x14003b5ed  pop     rsi
0x14003b5ee  pop     rbx
0x14003b5ef  pop     rbp
0x14003b5f0  retn
```
