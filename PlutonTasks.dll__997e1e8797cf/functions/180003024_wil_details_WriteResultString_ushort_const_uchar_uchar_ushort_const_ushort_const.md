# wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)

- ea: `0x180003024`
- end: `0x18000308b`
- name: `??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z`
- size: `103`
- prototype: `char *__fastcall(unsigned __int16 *Destination, const unsigned __int16 *, wil::details *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180007570`
- `0x180007798`

## callees

- `0x180003024`
- `0x180007400`
- `0x18000934c`

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
0x180003024  push    rbx
0x180003026  push    rbp
0x180003027  push    rsi
0x180003028  push    rdi
0x180003029  sub     rsp, 28h
0x18000302d  xor     ebp, ebp
0x18000302f  mov     rbx, r9
0x180003032  mov     r10, rdx
0x180003035  mov     rdi, rcx
0x180003038  cmp     rcx, rdx
0x18000303b  jz      short loc_180003077
0x18000303d  test    r8, r8
0x180003040  jz      short loc_180003077
0x180003042  cmp     [r8], bp
0x180003046  jz      short loc_180003077
0x180003048  mov     rcx, r8; this
0x18000304b  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x180003050  sub     r10, rdi
0x180003053  mov     rsi, rax
0x180003056  cmp     r10, rax
0x180003059  jb      short loc_180003077
0x18000305b  mov     r9, rax; SourceSize
0x18000305e  mov     rdx, r10; DestinationSize
0x180003061  mov     rcx, rdi; Destination
0x180003064  call    memcpy_s
0x180003069  test    rbx, rbx
0x18000306c  jz      short loc_180003071
0x18000306e  mov     [rbx], rdi
0x180003071  lea     rax, [rsi+rdi]
0x180003075  jmp     short loc_180003082
0x180003077  test    rbx, rbx
0x18000307a  jz      short loc_18000307F
0x18000307c  mov     [r9], rbp
0x18000307f  mov     rax, rdi
0x180003082  add     rsp, 28h
0x180003086  pop     rdi
0x180003087  pop     rsi
0x180003088  pop     rbp
0x180003089  pop     rbx
0x18000308a  retn
```
