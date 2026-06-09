# wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)

- ea: `0x180010660`
- end: `0x1800106c8`
- name: `??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z`
- size: `104`
- prototype: `char *__fastcall(unsigned __int16 *Destination, const unsigned __int16 *, wil::details *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180011bf4`

## callees

- `0x180010660`
- `0x180011bb0`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800106a0`
- `msvcrt!memcpy_s` at `0x1800106a0`

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
0x180010660  push    rbx
0x180010662  push    rbp
0x180010663  push    rsi
0x180010664  push    rdi
0x180010665  sub     rsp, 28h
0x180010669  xor     ebp, ebp
0x18001066b  mov     rbx, r9
0x18001066e  mov     r10, rdx
0x180010671  mov     rdi, rcx
0x180010674  cmp     rcx, rdx
0x180010677  jz      short loc_1800106B4
0x180010679  test    r8, r8
0x18001067c  jz      short loc_1800106B4
0x18001067e  cmp     [r8], bp
0x180010682  jz      short loc_1800106B4
0x180010684  mov     rcx, r8; this
0x180010687  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x18001068c  sub     r10, rdi
0x18001068f  mov     rsi, rax
0x180010692  cmp     r10, rax
0x180010695  jb      short loc_1800106B4
0x180010697  mov     r9, rax; SourceSize
0x18001069a  mov     rdx, r10; DestinationSize
0x18001069d  mov     rcx, rdi; Destination
0x1800106a0  call    cs:__imp_memcpy_s
0x1800106a6  test    rbx, rbx
0x1800106a9  jz      short loc_1800106AE
0x1800106ab  mov     [rbx], rdi
0x1800106ae  lea     rax, [rsi+rdi]
0x1800106b2  jmp     short loc_1800106BF
0x1800106b4  test    rbx, rbx
0x1800106b7  jz      short loc_1800106BC
0x1800106b9  mov     [r9], rbp
0x1800106bc  mov     rax, rdi
0x1800106bf  add     rsp, 28h
0x1800106c3  pop     rdi
0x1800106c4  pop     rsi
0x1800106c5  pop     rbp
0x1800106c6  pop     rbx
0x1800106c7  retn
```
