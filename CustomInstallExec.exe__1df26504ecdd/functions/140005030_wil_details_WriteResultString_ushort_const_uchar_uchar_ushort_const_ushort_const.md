# wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)

- ea: `0x140005030`
- end: `0x140005097`
- name: `??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z`
- size: `103`
- prototype: `char *__fastcall(unsigned __int16 *Destination, const unsigned __int16 *, wil::details *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140006c8c`
- `0x140006dc8`

## callees

- `0x140005030`
- `0x140006bc4`
- `0x140007b40`

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
0x140005030  push    rbx
0x140005032  push    rbp
0x140005033  push    rsi
0x140005034  push    rdi
0x140005035  sub     rsp, 28h
0x140005039  xor     ebp, ebp
0x14000503b  mov     rbx, r9
0x14000503e  mov     r10, rdx
0x140005041  mov     rdi, rcx
0x140005044  cmp     rcx, rdx
0x140005047  jz      short loc_140005083
0x140005049  test    r8, r8
0x14000504c  jz      short loc_140005083
0x14000504e  cmp     [r8], bp
0x140005052  jz      short loc_140005083
0x140005054  mov     rcx, r8; this
0x140005057  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x14000505c  sub     r10, rdi
0x14000505f  mov     rsi, rax
0x140005062  cmp     r10, rax
0x140005065  jb      short loc_140005083
0x140005067  mov     r9, rax; SourceSize
0x14000506a  mov     rdx, r10; DestinationSize
0x14000506d  mov     rcx, rdi; Destination
0x140005070  call    memcpy_s
0x140005075  test    rbx, rbx
0x140005078  jz      short loc_14000507D
0x14000507a  mov     [rbx], rdi
0x14000507d  lea     rax, [rsi+rdi]
0x140005081  jmp     short loc_14000508E
0x140005083  test    rbx, rbx
0x140005086  jz      short loc_14000508B
0x140005088  mov     [r9], rbp
0x14000508b  mov     rax, rdi
0x14000508e  add     rsp, 28h
0x140005092  pop     rdi
0x140005093  pop     rsi
0x140005094  pop     rbp
0x140005095  pop     rbx
0x140005096  retn
```
