# SdbMakeIndexKeyFromStringEx

- ea: `0x180011800`
- end: `0x180011961`
- name: `SdbMakeIndexKeyFromStringEx`
- size: `353`
- prototype: `__int64 __fastcall(PCWSTR SourceString)`
- caller_count: `4`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000b7f8`
- `0x1800116c0`
- `0x180049c20`
- `0x180049c30`

## callees

- `0x18000f114`
- `0x180011800`
- `0x1800591b0`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18001185f`
- `ntdll!RtlInitUnicodeString` at `0x18001185f`
- `ntdll!RtlUpcaseUnicodeString` at `0x18001189b`
- `ntdll!RtlUpcaseUnicodeString` at `0x18001189b`
- `ntdll!RtlCopyUnicodeString` at `0x18001187e`
- `ntdll!RtlCopyUnicodeString` at `0x18001187e`

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
0x180011800  push    rbp
0x180011802  push    rbx
0x180011803  push    rsi
0x180011804  push    rdi
0x180011805  lea     rbp, [rsp-3Fh]
0x18001180a  sub     rsp, 98h
0x180011811  mov     rax, cs:__security_cookie
0x180011818  xor     rax, rsp
0x18001181b  mov     [rbp+57h+var_30], rax
0x18001181f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180011823  mov     rbx, rcx
0x180011826  xor     esi, esi
0x180011828  inc     rax
0x18001182b  cmp     [rcx+rax*2], si
0x18001182f  jnz     short loc_180011828
0x180011831  xorps   xmm0, xmm0
0x180011834  xorps   xmm1, xmm1
0x180011837  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18001183b  movups  xmmword ptr [rbp+57h+SourceString.Length], xmm1
0x18001183f  movups  xmmword ptr [rbp+57h+var_60.Length], xmm0
0x180011843  cmp     rax, 8
0x180011847  jbe     short loc_180011858
0x180011849  test    dl, 2
0x18001184c  jz      short loc_180011858
0x18001184e  add     rcx, 0FFFFFFFFFFFFFFF0h
0x180011852  lea     rdx, [rcx+rax*2]
0x180011856  jmp     short loc_18001185B
0x180011858  mov     rdx, rbx; SourceString
0x18001185b  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18001185f  call    cs:__imp_RtlInitUnicodeString
0x180011865  lea     rax, [rbp+57h+var_40]
0x180011869  mov     edi, 10h
0x18001186e  lea     rdx, [rbp+57h+DestinationString]; SourceString
0x180011872  mov     [rbp+57h+SourceString.Buffer], rax
0x180011876  lea     rcx, [rbp+57h+SourceString]; DestinationString
0x18001187a  mov     [rbp+57h+SourceString.MaximumLength], di
0x18001187e  call    cs:__imp_RtlCopyUnicodeString
0x180011884  lea     rax, [rbp+57h+var_50]
0x180011888  mov     [rbp+57h+var_60.MaximumLength], di
0x18001188c  xor     r8d, r8d; AllocateDestinationString
0x18001188f  mov     [rbp+57h+var_60.Buffer], rax
0x180011893  lea     rdx, [rbp+57h+SourceString]; SourceString
0x180011897  lea     rcx, [rbp+57h+var_60]; DestinationString
0x18001189b  call    cs:__imp_RtlUpcaseUnicodeString
0x1800118a1  test    eax, eax
0x1800118a3  jns     short loc_1800118CA
0x1800118a5  lea     r9, aFailedToUpcase; "Failed to upcase unicode string \"%ws\""
0x1800118ac  mov     [rsp+0B0h+var_90], rbx
0x1800118b1  mov     r8d, 661h
0x1800118b7  lea     rdx, aSdbmakeindexke_0; "SdbMakeIndexKeyFromStringEx"
0x1800118be  lea     ecx, [rdi-0Fh]
0x1800118c1  call    AslLogCallPrintf
0x1800118c6  xor     eax, eax
0x1800118c8  jmp     short loc_180011949
0x1800118ca  movzx   ecx, [rbp+57h+var_60.Length]
0x1800118ce  mov     r8, rsi
0x1800118d1  shr     rcx, 1
0x1800118d4  mov     rdx, rcx
0x1800118d7  jz      short loc_1800118FB
0x1800118d9  mov     r9, [rbp+57h+var_60.Buffer]
0x1800118dd  cmp     rdx, 8
0x1800118e1  jnb     short loc_1800118FF
0x1800118e3  cmp     [r9+r8*2+1], sil
0x1800118e8  lea     rax, [rdx+1]
0x1800118ec  cmovz   rax, rdx
0x1800118f0  inc     r8
0x1800118f3  mov     rdx, rax
0x1800118f6  cmp     r8, rcx
0x1800118f9  jb      short loc_1800118DD
0x1800118fb  cmp     rdx, 8
0x1800118ff  ja      short loc_1800118C6
0x180011901  lea     r8, [rbp+57h+var_60+7]
0x180011905  mov     rax, rsi
0x180011908  mov     qword ptr [rbp+57h+var_60.Length], rax
0x18001190c  lea     r9, [rbp+57h+var_50]
0x180011910  mov     rcx, rsi
0x180011913  test    rdx, rdx
0x180011916  jz      short loc_180011949
0x180011918  movzx   eax, word ptr [r9]
0x18001191c  lea     r9, [r9+2]
0x180011920  mov     [r8], al
0x180011923  dec     r8
0x180011926  shr     ax, 8
0x18001192a  test    al, al
0x18001192c  jz      short loc_18001193D
0x18001192e  cmp     rcx, 7
0x180011932  jnb     short loc_18001193D
0x180011934  mov     [r8], al
0x180011937  dec     r8
0x18001193a  inc     rcx
0x18001193d  inc     rcx
0x180011940  cmp     rcx, rdx
0x180011943  jb      short loc_180011918
0x180011945  mov     rax, qword ptr [rbp+57h+var_60.Length]
0x180011949  mov     rcx, [rbp+57h+var_30]
0x18001194d  xor     rcx, rsp; StackCookie
0x180011950  call    __security_check_cookie
0x180011955  add     rsp, 98h
0x18001195c  pop     rdi
0x18001195d  pop     rsi
0x18001195e  pop     rbx
0x18001195f  pop     rbp
0x180011960  retn
```
