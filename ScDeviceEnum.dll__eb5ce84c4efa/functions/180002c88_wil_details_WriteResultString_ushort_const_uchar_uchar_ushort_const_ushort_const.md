# wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)

- ea: `0x180002c88`
- end: `0x180002cf0`
- name: `??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z`
- size: `104`
- prototype: `char *__fastcall(unsigned __int16 *Destination, const unsigned __int16 *, wil::details *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180004aac`
- `0x180004be8`

## callees

- `0x180002c88`
- `0x1800049e8`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180002cc8`
- `msvcrt!memcpy_s` at `0x180002cc8`

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
0x180002c88  push    rbx
0x180002c8a  push    rbp
0x180002c8b  push    rsi
0x180002c8c  push    rdi
0x180002c8d  sub     rsp, 28h
0x180002c91  xor     ebp, ebp
0x180002c93  mov     rbx, r9
0x180002c96  mov     r10, rdx
0x180002c99  mov     rdi, rcx
0x180002c9c  cmp     rcx, rdx
0x180002c9f  jz      short loc_180002CDC
0x180002ca1  test    r8, r8
0x180002ca4  jz      short loc_180002CDC
0x180002ca6  cmp     [r8], bp
0x180002caa  jz      short loc_180002CDC
0x180002cac  mov     rcx, r8; this
0x180002caf  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x180002cb4  sub     r10, rdi
0x180002cb7  mov     rsi, rax
0x180002cba  cmp     r10, rax
0x180002cbd  jb      short loc_180002CDC
0x180002cbf  mov     r9, rax; SourceSize
0x180002cc2  mov     rdx, r10; DestinationSize
0x180002cc5  mov     rcx, rdi; Destination
0x180002cc8  call    cs:__imp_memcpy_s
0x180002cce  test    rbx, rbx
0x180002cd1  jz      short loc_180002CD6
0x180002cd3  mov     [rbx], rdi
0x180002cd6  lea     rax, [rsi+rdi]
0x180002cda  jmp     short loc_180002CE7
0x180002cdc  test    rbx, rbx
0x180002cdf  jz      short loc_180002CE4
0x180002ce1  mov     [r9], rbp
0x180002ce4  mov     rax, rdi
0x180002ce7  add     rsp, 28h
0x180002ceb  pop     rdi
0x180002cec  pop     rsi
0x180002ced  pop     rbp
0x180002cee  pop     rbx
0x180002cef  retn
```
