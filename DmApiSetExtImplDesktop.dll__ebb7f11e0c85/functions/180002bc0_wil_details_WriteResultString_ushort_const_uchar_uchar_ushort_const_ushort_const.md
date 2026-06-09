# wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)

- ea: `0x180002bc0`
- end: `0x180002c2f`
- name: `??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z`
- size: `111`
- prototype: `__int64 __fastcall(void *Destination)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180004e6c`
- `0x180004fb8`

## callees

- `0x180002bc0`
- `0x180004d7c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180002c00`
- `msvcrt!memcpy_s` at `0x180002c00`

## pseudocode

```c
char *__fastcall wil::details::WriteResultString<unsigned short const *>(
        unsigned __int16 *Destination,
        const unsigned __int16 *a2,
        wil::details *a3,
        unsigned __int16 **a4)
{
  rsize_t v6; // rax
  const void *v7; // r8
  __int64 v8; // r10
  rsize_t v9; // r10
  rsize_t v10; // rsi

  if ( Destination != a2
    && a3
    && *(_WORD *)a3
    && (v6 = wil::details::ResultStringSize(a3, a2), v9 = v8 - (_QWORD)Destination, v10 = v6, v9 >= v6) )
  {
    memcpy_s(Destination, v9, v7, v6);
    if ( a4 )
      *a4 = Destination;
    return (char *)Destination + v10;
  }
  else
  {
    if ( a4 )
      *a4 = 0;
    return (char *)Destination;
  }
}

```

## disassembly

```asm
0x180002bc0  push    rbx
0x180002bc2  push    rbp
0x180002bc3  push    rsi
0x180002bc4  push    rdi
0x180002bc5  sub     rsp, 28h
0x180002bc9  xor     ebp, ebp
0x180002bcb  mov     rbx, r9
0x180002bce  mov     r10, rdx
0x180002bd1  mov     rdi, rcx
0x180002bd4  cmp     rcx, rdx
0x180002bd7  jz      short loc_180002C1A
0x180002bd9  test    r8, r8
0x180002bdc  jz      short loc_180002C1A
0x180002bde  cmp     [r8], bp
0x180002be2  jz      short loc_180002C1A
0x180002be4  mov     rcx, r8; this
0x180002be7  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x180002bec  sub     r10, rdi
0x180002bef  mov     rsi, rax
0x180002bf2  cmp     r10, rax
0x180002bf5  jb      short loc_180002C1A
0x180002bf7  mov     r9, rax; SourceSize
0x180002bfa  mov     rdx, r10; DestinationSize
0x180002bfd  mov     rcx, rdi; Destination
0x180002c00  call    cs:__imp_memcpy_s
0x180002c07  nop     dword ptr [rax+rax+00h]
0x180002c0c  test    rbx, rbx
0x180002c0f  jz      short loc_180002C14
0x180002c11  mov     [rbx], rdi
0x180002c14  lea     rax, [rsi+rdi]
0x180002c18  jmp     short loc_180002C25
0x180002c1a  test    rbx, rbx
0x180002c1d  jz      short loc_180002C22
0x180002c1f  mov     [r9], rbp
0x180002c22  mov     rax, rdi
0x180002c25  add     rsp, 28h
0x180002c29  pop     rdi
0x180002c2a  pop     rsi
0x180002c2b  pop     rbp
0x180002c2c  pop     rbx
0x180002c2d  retn
```
