# wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)

- ea: `0x140002f68`
- end: `0x140002fd0`
- name: `??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z`
- size: `104`
- prototype: `char *__fastcall(unsigned __int16 *Destination, const unsigned __int16 *, wil::details *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140004ddc`
- `0x140004f18`

## callees

- `0x140002f68`
- `0x140004d18`

## import_xrefs

- `msvcrt!memcpy_s` at `0x140002fa8`
- `msvcrt!memcpy_s` at `0x140002fa8`

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
0x140002f68  push    rbx
0x140002f6a  push    rbp
0x140002f6b  push    rsi
0x140002f6c  push    rdi
0x140002f6d  sub     rsp, 28h
0x140002f71  xor     ebp, ebp
0x140002f73  mov     rbx, r9
0x140002f76  mov     r10, rdx
0x140002f79  mov     rdi, rcx
0x140002f7c  cmp     rcx, rdx
0x140002f7f  jz      short loc_140002FBC
0x140002f81  test    r8, r8
0x140002f84  jz      short loc_140002FBC
0x140002f86  cmp     [r8], bp
0x140002f8a  jz      short loc_140002FBC
0x140002f8c  mov     rcx, r8; this
0x140002f8f  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x140002f94  sub     r10, rdi
0x140002f97  mov     rsi, rax
0x140002f9a  cmp     r10, rax
0x140002f9d  jb      short loc_140002FBC
0x140002f9f  mov     r9, rax; SourceSize
0x140002fa2  mov     rdx, r10; DestinationSize
0x140002fa5  mov     rcx, rdi; Destination
0x140002fa8  call    cs:__imp_memcpy_s
0x140002fae  test    rbx, rbx
0x140002fb1  jz      short loc_140002FB6
0x140002fb3  mov     [rbx], rdi
0x140002fb6  lea     rax, [rsi+rdi]
0x140002fba  jmp     short loc_140002FC7
0x140002fbc  test    rbx, rbx
0x140002fbf  jz      short loc_140002FC4
0x140002fc1  mov     [r9], rbp
0x140002fc4  mov     rax, rdi
0x140002fc7  add     rsp, 28h
0x140002fcb  pop     rdi
0x140002fcc  pop     rsi
0x140002fcd  pop     rbp
0x140002fce  pop     rbx
0x140002fcf  retn
```
