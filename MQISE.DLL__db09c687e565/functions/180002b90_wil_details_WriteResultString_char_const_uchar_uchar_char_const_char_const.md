# wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)

- ea: `0x180002b90`
- end: `0x180002c30`
- name: `??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z`
- size: `160`
- prototype: `__int64 __fastcall(void *Destination)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180009748`
- `0x180009a3c`

## callees

- `0x180001c0c`
- `0x180002b90`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180002be0`
- `msvcrt!memcpy_s` at `0x180002be0`
- `msvcrt!??0exception@@QEAA@XZ` at `0x180002c18`
- `msvcrt!??0exception@@QEAA@XZ` at `0x180002c18`

## pseudocode

```c
char *__fastcall wil::details::WriteResultString<char const *>(_BYTE *Destination, _BYTE *a2, _BYTE *a3, _QWORD *a4)
{
  unsigned __int64 v6; // rax
  rsize_t v7; // rdx
  unsigned __int64 v8; // rsi
  _BYTE pExceptionObject[40]; // [rsp+20h] [rbp-28h] BYREF

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
  v7 = a2 - Destination;
  v8 = (unsigned int)v6 + 1LL;
  if ( v7 >= v8 )
  {
    memcpy_s(Destination, v7, a3, (unsigned int)v6 + 1LL);
    if ( a4 )
      *a4 = Destination;
    return &Destination[v8];
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
0x180002b90  mov     [rsp+arg_0], rbx
0x180002b95  mov     [rsp+arg_8], rsi
0x180002b9a  push    rdi
0x180002b9b  sub     rsp, 40h
0x180002b9f  mov     rbx, r9
0x180002ba2  mov     rdi, rcx
0x180002ba5  cmp     rcx, rdx
0x180002ba8  jz      short loc_180002BF4
0x180002baa  test    r8, r8
0x180002bad  jz      short loc_180002BF4
0x180002baf  cmp     byte ptr [r8], 0
0x180002bb3  jz      short loc_180002BF4
0x180002bb5  or      rax, 0FFFFFFFFFFFFFFFFh
0x180002bb9  inc     rax
0x180002bbc  cmp     byte ptr [r8+rax], 0
0x180002bc1  jnz     short loc_180002BB9
0x180002bc3  mov     ecx, 0FFFFFFFFh
0x180002bc8  cmp     rax, rcx
0x180002bcb  ja      short loc_180002C13
0x180002bcd  mov     esi, eax
0x180002bcf  sub     rdx, rdi; DestinationSize
0x180002bd2  inc     rsi
0x180002bd5  cmp     rdx, rsi
0x180002bd8  jb      short loc_180002BF4
0x180002bda  mov     r9, rsi; SourceSize
0x180002bdd  mov     rcx, rdi; Destination
0x180002be0  call    cs:__imp_memcpy_s
0x180002be6  test    rbx, rbx
0x180002be9  jz      short loc_180002BEE
0x180002beb  mov     [rbx], rdi
0x180002bee  lea     rax, [rsi+rdi]
0x180002bf2  jmp     short loc_180002C03
0x180002bf4  test    rbx, rbx
0x180002bf7  jz      short loc_180002C00
0x180002bf9  mov     qword ptr [r9], 0
0x180002c00  mov     rax, rdi
0x180002c03  mov     rbx, [rsp+48h+arg_0]
0x180002c08  mov     rsi, [rsp+48h+arg_8]
0x180002c0d  add     rsp, 40h
0x180002c11  pop     rdi
0x180002c12  retn
0x180002c13  lea     rcx, [rsp+48h+pExceptionObject]
0x180002c18  call    cs:__imp_??0exception@@QEAA@XZ; exception::exception(void)
0x180002c1e  lea     rdx, _TI1?AVexception@@; pThrowInfo
0x180002c25  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180002c2a  call    _CxxThrowException_0
```
