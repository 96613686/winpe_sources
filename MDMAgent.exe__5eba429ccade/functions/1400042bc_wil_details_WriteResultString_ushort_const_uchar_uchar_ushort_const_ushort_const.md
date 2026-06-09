# wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)

- ea: `0x1400042bc`
- end: `0x140004323`
- name: `??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z`
- size: `103`
- prototype: `char *__fastcall(unsigned __int16 *Destination, const unsigned __int16 *, wil::details *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140006a50`
- `0x140006b8c`

## callees

- `0x1400042bc`
- `0x140006908`
- `0x140007ea4`

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
0x1400042bc  push    rbx
0x1400042be  push    rbp
0x1400042bf  push    rsi
0x1400042c0  push    rdi
0x1400042c1  sub     rsp, 28h
0x1400042c5  xor     ebp, ebp
0x1400042c7  mov     rbx, r9
0x1400042ca  mov     r10, rdx
0x1400042cd  mov     rdi, rcx
0x1400042d0  cmp     rcx, rdx
0x1400042d3  jz      short loc_14000430F
0x1400042d5  test    r8, r8
0x1400042d8  jz      short loc_14000430F
0x1400042da  cmp     [r8], bp
0x1400042de  jz      short loc_14000430F
0x1400042e0  mov     rcx, r8; this
0x1400042e3  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x1400042e8  sub     r10, rdi
0x1400042eb  mov     rsi, rax
0x1400042ee  cmp     r10, rax
0x1400042f1  jb      short loc_14000430F
0x1400042f3  mov     r9, rax; SourceSize
0x1400042f6  mov     rdx, r10; DestinationSize
0x1400042f9  mov     rcx, rdi; Destination
0x1400042fc  call    memcpy_s
0x140004301  test    rbx, rbx
0x140004304  jz      short loc_140004309
0x140004306  mov     [rbx], rdi
0x140004309  lea     rax, [rsi+rdi]
0x14000430d  jmp     short loc_14000431A
0x14000430f  test    rbx, rbx
0x140004312  jz      short loc_140004317
0x140004314  mov     [r9], rbp
0x140004317  mov     rax, rdi
0x14000431a  add     rsp, 28h
0x14000431e  pop     rdi
0x14000431f  pop     rsi
0x140004320  pop     rbp
0x140004321  pop     rbx
0x140004322  retn
```
