# CRTFRead::HandleFieldSymbolFont(uchar *)

- ea: `0x18007bf38`
- end: `0x18007c0b7`
- name: `?HandleFieldSymbolFont@CRTFRead@@AEAAHPEAE@Z`
- size: `383`
- prototype: `__int64 __fastcall(CRTFRead *__hidden this, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18007c0c0`

## callees

- `0x18001a520`
- `0x180027f70`
- `0x180031e80`
- `0x1800455c4`
- `0x180078d58`
- `0x18007bf38`
- `0x18009110a`
- `0x180091116`
- `0x180091140`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x18007c05d`
- `msvcrt!wcscpy_s` at `0x18007c05d`

## pseudocode

```c
__int64 __fastcall CRTFRead::HandleFieldSymbolFont(CRTFRead *this, unsigned __int8 *a2)
{
  __int16 v2; // bp
  __int64 v5; // r14
  int v6; // ecx
  int v7; // eax
  unsigned __int8 v8; // dl
  unsigned __int16 v9; // di
  const wchar_t *v10; // rsi
  wchar_t *v11; // rsi
  signed __int16 v12; // di
  __int64 result; // rax
  _BYTE v14[6]; // [rsp+20h] [rbp-88h] BYREF
  wchar_t String1[37]; // [rsp+26h] [rbp-82h] BYREF

  v2 = *((_WORD *)this + 4);
  memset_0(v14, 0, 0x4Cu);
  while ( *a2 && ((*a2 - 32) & 0xFD) == 0 )
    ++a2;
  v5 = *((_QWORD *)this + 17);
  v6 = 1;
  *((_QWORD *)this + 17) = a2;
  while ( 1 )
  {
    v8 = *a2;
    if ( !*a2 )
      break;
    if ( v8 == 34 )
    {
      *a2 = 59;
      break;
    }
    v7 = 0;
    if ( v8 <= 0x7Fu )
      v7 = v6;
    ++a2;
    v6 = v7;
  }
  CRTFRead::ReadFontName(this, (struct _textfont *)v14, v6 != 0, *((struct STATE **)this + 27));
  v9 = 0;
  if ( v2 > 0 )
  {
    while ( 1 )
    {
      v10 = (const wchar_t *)CArrayBase::Elem(this, v9);
      if ( !wcsncmp_0(String1, v10 + 3, 0x20u) )
        break;
      if ( (__int16)++v9 >= v2 )
        goto LABEL_16;
    }
    v12 = *v10;
    goto LABEL_20;
  }
LABEL_16:
  v11 = (wchar_t *)CArrayBase::ArAdd(this, 1, 0);
  if ( v11 )
  {
    v12 = v9 + 2048;
    *v11 = v12;
    wcscpy_s(v11 + 3, 0x21u, String1);
    v11[35] = 0;
    *((_BYTE *)v11 + 3) = 0;
    *((_BYTE *)v11 + 74) = 0;
    v11[36] = *((_WORD *)this + 294);
    *((_BYTE *)v11 + 2) = 1;
LABEL_20:
    CRTFRead::SelectCurrentFont(this, v12);
    goto LABEL_21;
  }
  CCallMgr::SetOutOfMemory(*(CCallMgr **)(*((_QWORD *)this + 7) + 144LL));
  *((_DWORD *)this + 12) = 9;
LABEL_21:
  result = *((unsigned int *)this + 12);
  *((_QWORD *)this + 17) = v5;
  return result;
}

```

## disassembly

```asm
0x18007bf38  mov     [rsp+arg_10], rbx
0x18007bf3d  push    rbp
0x18007bf3e  push    rsi
0x18007bf3f  push    rdi
0x18007bf40  push    r14
0x18007bf42  push    r15
0x18007bf44  sub     rsp, 80h
0x18007bf4b  mov     rax, cs:__security_cookie
0x18007bf52  xor     rax, rsp
0x18007bf55  mov     [rsp+0A8h+var_38], rax
0x18007bf5a  movzx   ebp, word ptr [rcx+8]
0x18007bf5e  mov     rdi, rdx
0x18007bf61  xor     edx, edx; Val
0x18007bf63  mov     rbx, rcx
0x18007bf66  lea     rcx, [rsp+0A8h+var_88]; void *
0x18007bf6b  lea     r8d, [rdx+4Ch]; Size
0x18007bf6f  call    memset_0
0x18007bf74  mov     r15d, 1
0x18007bf7a  jmp     short loc_18007BF85
0x18007bf7c  sub     al, 20h ; ' '
0x18007bf7e  test    al, 0FDh
0x18007bf80  jnz     short loc_18007BF8B
0x18007bf82  add     rdi, r15
0x18007bf85  mov     al, [rdi]
0x18007bf87  test    al, al
0x18007bf89  jnz     short loc_18007BF7C
0x18007bf8b  mov     r14, [rbx+88h]
0x18007bf92  mov     ecx, r15d
0x18007bf95  mov     [rbx+88h], rdi
0x18007bf9c  jmp     short loc_18007BFB0
0x18007bf9e  cmp     dl, 22h ; '"'
0x18007bfa1  jz      short loc_18007BFB8
0x18007bfa3  xor     eax, eax
0x18007bfa5  cmp     dl, 7Fh
0x18007bfa8  cmovbe  eax, ecx
0x18007bfab  add     rdi, r15
0x18007bfae  mov     ecx, eax
0x18007bfb0  mov     dl, [rdi]
0x18007bfb2  test    dl, dl
0x18007bfb4  jnz     short loc_18007BF9E
0x18007bfb6  jmp     short loc_18007BFBB
0x18007bfb8  mov     byte ptr [rdi], 3Bh ; ';'
0x18007bfbb  mov     r9, [rbx+0D8h]; struct STATE *
0x18007bfc2  lea     rdx, [rsp+0A8h+var_88]; struct _textfont *
0x18007bfc7  xor     r8d, r8d
0x18007bfca  test    ecx, ecx
0x18007bfcc  mov     rcx, rbx; this
0x18007bfcf  setnz   r8b; int
0x18007bfd3  call    ?ReadFontName@CRTFRead@@AEAAXPEAU_textfont@@HPEAUSTATE@@@Z; CRTFRead::ReadFontName(_textfont *,int,STATE *)
0x18007bfd8  xor     eax, eax
0x18007bfda  xor     edi, edi
0x18007bfdc  cmp     ax, bp
0x18007bfdf  jge     short loc_18007C010
0x18007bfe1  movzx   edx, di; int
0x18007bfe4  mov     rcx, rbx; this
0x18007bfe7  call    ?Elem@CArrayBase@@QEBAPEAXJ@Z; CArrayBase::Elem(long)
0x18007bfec  mov     r8d, 20h ; ' '; MaxCount
0x18007bff2  lea     rcx, [rsp+0A8h+String1]; String1
0x18007bff7  mov     rsi, rax
0x18007bffa  lea     rdx, [rax+6]; String2
0x18007bffe  call    wcsncmp_0
0x18007c003  test    eax, eax
0x18007c005  jz      short loc_18007C03F
0x18007c007  add     di, r15w
0x18007c00b  cmp     di, bp
0x18007c00e  jl      short loc_18007BFE1
0x18007c010  xor     r8d, r8d; int *
0x18007c013  mov     edx, r15d; int
0x18007c016  mov     rcx, rbx; this
0x18007c019  call    ?ArAdd@CArrayBase@@IEAAPEAXJPEAJ@Z; CArrayBase::ArAdd(long,long *)
0x18007c01e  mov     rsi, rax
0x18007c021  test    rax, rax
0x18007c024  jnz     short loc_18007C044
0x18007c026  mov     rcx, [rbx+38h]
0x18007c02a  mov     rcx, [rcx+90h]; this
0x18007c031  call    ?SetOutOfMemory@CCallMgr@@QEAAXXZ; CCallMgr::SetOutOfMemory(void)
0x18007c036  mov     dword ptr [rbx+30h], 9
0x18007c03d  jmp     short loc_18007C089
0x18007c03f  movzx   edi, word ptr [rsi]
0x18007c042  jmp     short loc_18007C07E
0x18007c044  mov     eax, 800h
0x18007c049  lea     rcx, [rsi+6]; Destination
0x18007c04d  add     di, ax
0x18007c050  lea     r8, [rsp+0A8h+String1]; Source
0x18007c055  mov     edx, 21h ; '!'; SizeInWords
0x18007c05a  mov     [rsi], di
0x18007c05d  call    cs:__imp_wcscpy_s
0x18007c063  xor     eax, eax
0x18007c065  mov     [rsi+46h], ax
0x18007c069  mov     [rsi+3], al
0x18007c06c  mov     [rsi+4Ah], al
0x18007c06f  movzx   eax, word ptr [rbx+24Ch]
0x18007c076  mov     [rsi+48h], ax
0x18007c07a  mov     [rsi+2], r15b
0x18007c07e  movsx   edx, di; int
0x18007c081  mov     rcx, rbx; this
0x18007c084  call    ?SelectCurrentFont@CRTFRead@@AEAAPEAU_textfont@@H@Z; CRTFRead::SelectCurrentFont(int)
0x18007c089  mov     eax, [rbx+30h]
0x18007c08c  mov     [rbx+88h], r14
0x18007c093  mov     rcx, [rsp+0A8h+var_38]
0x18007c098  xor     rcx, rsp; StackCookie
0x18007c09b  call    __security_check_cookie
0x18007c0a0  mov     rbx, [rsp+0A8h+arg_10]
0x18007c0a8  add     rsp, 80h
0x18007c0af  pop     r15
0x18007c0b1  pop     r14
0x18007c0b3  pop     rdi
0x18007c0b4  pop     rsi
0x18007c0b5  pop     rbp
0x18007c0b6  retn
```
