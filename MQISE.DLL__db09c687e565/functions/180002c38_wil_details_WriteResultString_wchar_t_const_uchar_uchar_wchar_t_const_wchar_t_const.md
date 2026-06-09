# wil::details::WriteResultString<wchar_t const *>(uchar *,uchar *,wchar_t const *,wchar_t const * *)

- ea: `0x180002c38`
- end: `0x180002cca`
- name: `??$WriteResultString@PEB_W@details@wil@@YAPEAEPEAE0PEB_WPEAPEB_W@Z`
- size: `146`
- prototype: `__int64 __fastcall(void *Destination)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180009748`
- `0x180009a3c`

## callees

- `0x180001c0c`
- `0x180002c38`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180002c85`
- `msvcrt!memcpy_s` at `0x180002c85`
- `msvcrt!??0exception@@QEAA@XZ` at `0x180002cb2`
- `msvcrt!??0exception@@QEAA@XZ` at `0x180002cb2`

## pseudocode

```c
char *__fastcall wil::details::WriteResultString<wchar_t const *>(_BYTE *Destination, _BYTE *a2, _WORD *a3, _QWORD *a4)
{
  unsigned __int64 v6; // rax
  __int64 v7; // rax
  rsize_t v8; // rdx
  __int64 v9; // rsi
  _BYTE pExceptionObject[72]; // [rsp+20h] [rbp-48h] BYREF

  if ( Destination == a2 || !a3 || !*a3 )
    goto LABEL_11;
  v6 = -1;
  do
    ++v6;
  while ( a3[v6] );
  if ( v6 > 0xFFFFFFFF )
  {
    exception::exception((exception *)pExceptionObject);
    throw (exception *)pExceptionObject;
  }
  v7 = (unsigned int)(v6 + 1);
  v8 = a2 - Destination;
  v9 = 2 * v7;
  if ( v8 >= 2 * v7 )
  {
    memcpy_s(Destination, v8, a3, 2 * v7);
    if ( a4 )
      *a4 = Destination;
    return &Destination[v9];
  }
  else
  {
LABEL_11:
    if ( a4 )
      *a4 = 0;
    return Destination;
  }
}

```

## disassembly

```asm
0x180002c38  push    rbx
0x180002c3a  push    rbp
0x180002c3b  push    rsi
0x180002c3c  push    rdi
0x180002c3d  sub     rsp, 48h
0x180002c41  xor     ebp, ebp
0x180002c43  mov     rbx, r9
0x180002c46  mov     rdi, rcx
0x180002c49  cmp     rcx, rdx
0x180002c4c  jz      short loc_180002C99
0x180002c4e  test    r8, r8
0x180002c51  jz      short loc_180002C99
0x180002c53  cmp     [r8], bp
0x180002c57  jz      short loc_180002C99
0x180002c59  or      rax, 0FFFFFFFFFFFFFFFFh
0x180002c5d  inc     rax
0x180002c60  cmp     [r8+rax*2], bp
0x180002c65  jnz     short loc_180002C5D
0x180002c67  mov     ecx, 0FFFFFFFFh
0x180002c6c  cmp     rax, rcx
0x180002c6f  ja      short loc_180002CAD
0x180002c71  inc     eax
0x180002c73  sub     rdx, rdi; DestinationSize
0x180002c76  lea     rsi, [rax+rax]
0x180002c7a  cmp     rdx, rsi
0x180002c7d  jb      short loc_180002C99
0x180002c7f  mov     r9, rsi; SourceSize
0x180002c82  mov     rcx, rdi; Destination
0x180002c85  call    cs:__imp_memcpy_s
0x180002c8b  test    rbx, rbx
0x180002c8e  jz      short loc_180002C93
0x180002c90  mov     [rbx], rdi
0x180002c93  lea     rax, [rsi+rdi]
0x180002c97  jmp     short loc_180002CA4
0x180002c99  test    rbx, rbx
0x180002c9c  jz      short loc_180002CA1
0x180002c9e  mov     [r9], rbp
0x180002ca1  mov     rax, rdi
0x180002ca4  add     rsp, 48h
0x180002ca8  pop     rdi
0x180002ca9  pop     rsi
0x180002caa  pop     rbp
0x180002cab  pop     rbx
0x180002cac  retn
0x180002cad  lea     rcx, [rsp+68h+pExceptionObject]
0x180002cb2  call    cs:__imp_??0exception@@QEAA@XZ; exception::exception(void)
0x180002cb8  lea     rdx, _TI1?AVexception@@; pThrowInfo
0x180002cbf  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x180002cc4  call    _CxxThrowException_0
```
