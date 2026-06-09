# wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)

- ea: `0x180003650`
- end: `0x1800036b7`
- name: `??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z`
- size: `103`
- prototype: `char *__fastcall(unsigned __int16 *Destination, const unsigned __int16 *, wil::details *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180004e70`
- `0x18000e7a8`

## callees

- `0x180003650`
- `0x180004da8`
- `0x180005920`

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
0x180003650  push    rbx
0x180003652  push    rbp
0x180003653  push    rsi
0x180003654  push    rdi
0x180003655  sub     rsp, 28h
0x180003659  xor     ebp, ebp
0x18000365b  mov     rbx, r9
0x18000365e  mov     r10, rdx
0x180003661  mov     rdi, rcx
0x180003664  cmp     rcx, rdx
0x180003667  jz      short loc_1800036A3
0x180003669  test    r8, r8
0x18000366c  jz      short loc_1800036A3
0x18000366e  cmp     [r8], bp
0x180003672  jz      short loc_1800036A3
0x180003674  mov     rcx, r8; this
0x180003677  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x18000367c  sub     r10, rdi
0x18000367f  mov     rsi, rax
0x180003682  cmp     r10, rax
0x180003685  jb      short loc_1800036A3
0x180003687  mov     r9, rax; SourceSize
0x18000368a  mov     rdx, r10; DestinationSize
0x18000368d  mov     rcx, rdi; Destination
0x180003690  call    memcpy_s
0x180003695  test    rbx, rbx
0x180003698  jz      short loc_18000369D
0x18000369a  mov     [rbx], rdi
0x18000369d  lea     rax, [rsi+rdi]
0x1800036a1  jmp     short loc_1800036AE
0x1800036a3  test    rbx, rbx
0x1800036a6  jz      short loc_1800036AB
0x1800036a8  mov     [r9], rbp
0x1800036ab  mov     rax, rdi
0x1800036ae  add     rsp, 28h
0x1800036b2  pop     rdi
0x1800036b3  pop     rsi
0x1800036b4  pop     rbp
0x1800036b5  pop     rbx
0x1800036b6  retn
```
