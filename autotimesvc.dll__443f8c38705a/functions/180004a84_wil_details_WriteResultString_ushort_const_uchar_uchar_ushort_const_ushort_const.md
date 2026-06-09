# wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)

- ea: `0x180004a84`
- end: `0x180004aeb`
- name: `??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z`
- size: `103`
- prototype: `char *__fastcall(unsigned __int16 *Destination, const unsigned __int16 *, wil::details *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180009240`
- `0x18000937c`

## callees

- `0x180004a84`
- `0x180009118`
- `0x18000ad7c`

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
0x180004a84  push    rbx
0x180004a86  push    rbp
0x180004a87  push    rsi
0x180004a88  push    rdi
0x180004a89  sub     rsp, 28h
0x180004a8d  xor     ebp, ebp
0x180004a8f  mov     rbx, r9
0x180004a92  mov     r10, rdx
0x180004a95  mov     rdi, rcx
0x180004a98  cmp     rcx, rdx
0x180004a9b  jz      short loc_180004AD7
0x180004a9d  test    r8, r8
0x180004aa0  jz      short loc_180004AD7
0x180004aa2  cmp     [r8], bp
0x180004aa6  jz      short loc_180004AD7
0x180004aa8  mov     rcx, r8; this
0x180004aab  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x180004ab0  sub     r10, rdi
0x180004ab3  mov     rsi, rax
0x180004ab6  cmp     r10, rax
0x180004ab9  jb      short loc_180004AD7
0x180004abb  mov     r9, rax; SourceSize
0x180004abe  mov     rdx, r10; DestinationSize
0x180004ac1  mov     rcx, rdi; Destination
0x180004ac4  call    memcpy_s
0x180004ac9  test    rbx, rbx
0x180004acc  jz      short loc_180004AD1
0x180004ace  mov     [rbx], rdi
0x180004ad1  lea     rax, [rsi+rdi]
0x180004ad5  jmp     short loc_180004AE2
0x180004ad7  test    rbx, rbx
0x180004ada  jz      short loc_180004ADF
0x180004adc  mov     [r9], rbp
0x180004adf  mov     rax, rdi
0x180004ae2  add     rsp, 28h
0x180004ae6  pop     rdi
0x180004ae7  pop     rsi
0x180004ae8  pop     rbp
0x180004ae9  pop     rbx
0x180004aea  retn
```
