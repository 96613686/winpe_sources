# wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)

- ea: `0x18000abc8`
- end: `0x18000ac2a`
- name: `??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z`
- size: `98`
- prototype: `__int64 __fastcall(void *Destination)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000c39c`
- `0x18000c4d8`

## callees

- `0x1800059f0`
- `0x18000abc8`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000ac02`
- `msvcrt!memcpy_s` at `0x18000ac02`

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
  __int64 v8; // rdx
  rsize_t v9; // rdx
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
0x18000abc8  push    rbx
0x18000abca  push    rbp
0x18000abcb  push    rsi
0x18000abcc  push    rdi
0x18000abcd  sub     rsp, 28h
0x18000abd1  xor     ebp, ebp
0x18000abd3  mov     rbx, r9
0x18000abd6  mov     rdi, rcx
0x18000abd9  cmp     rcx, rdx
0x18000abdc  jz      short loc_18000AC16
0x18000abde  test    r8, r8
0x18000abe1  jz      short loc_18000AC16
0x18000abe3  cmp     [r8], bp
0x18000abe7  jz      short loc_18000AC16
0x18000abe9  mov     rcx, r8; this
0x18000abec  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x18000abf1  sub     rdx, rdi; DestinationSize
0x18000abf4  mov     rsi, rax
0x18000abf7  cmp     rdx, rax
0x18000abfa  jb      short loc_18000AC16
0x18000abfc  mov     r9, rax; SourceSize
0x18000abff  mov     rcx, rdi; Destination
0x18000ac02  call    cs:__imp_memcpy_s
0x18000ac08  test    rbx, rbx
0x18000ac0b  jz      short loc_18000AC10
0x18000ac0d  mov     [rbx], rdi
0x18000ac10  lea     rax, [rsi+rdi]
0x18000ac14  jmp     short loc_18000AC21
0x18000ac16  test    rbx, rbx
0x18000ac19  jz      short loc_18000AC1E
0x18000ac1b  mov     [r9], rbp
0x18000ac1e  mov     rax, rdi
0x18000ac21  add     rsp, 28h
0x18000ac25  pop     rdi
0x18000ac26  pop     rsi
0x18000ac27  pop     rbp
0x18000ac28  pop     rbx
0x18000ac29  retn
```
