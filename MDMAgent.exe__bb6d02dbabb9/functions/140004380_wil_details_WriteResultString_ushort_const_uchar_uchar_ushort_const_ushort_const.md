# wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)

- ea: `0x140004380`
- end: `0x1400043e8`
- name: `??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z`
- size: `104`
- prototype: `__int64 __fastcall(void *Destination)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140006cd4`
- `0x140006e20`

## callees

- `0x140004380`
- `0x140006b6c`
- `0x140008200`

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
0x140004380  push    rbx
0x140004382  push    rbp
0x140004383  push    rsi
0x140004384  push    rdi
0x140004385  sub     rsp, 28h
0x140004389  xor     ebp, ebp
0x14000438b  mov     rbx, r9
0x14000438e  mov     r10, rdx
0x140004391  mov     rdi, rcx
0x140004394  cmp     rcx, rdx
0x140004397  jz      short loc_1400043D3
0x140004399  test    r8, r8
0x14000439c  jz      short loc_1400043D3
0x14000439e  cmp     [r8], bp
0x1400043a2  jz      short loc_1400043D3
0x1400043a4  mov     rcx, r8; this
0x1400043a7  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x1400043ac  sub     r10, rdi
0x1400043af  mov     rsi, rax
0x1400043b2  cmp     r10, rax
0x1400043b5  jb      short loc_1400043D3
0x1400043b7  mov     r9, rax; SourceSize
0x1400043ba  mov     rdx, r10; DestinationSize
0x1400043bd  mov     rcx, rdi; Destination
0x1400043c0  call    memcpy_s
0x1400043c5  test    rbx, rbx
0x1400043c8  jz      short loc_1400043CD
0x1400043ca  mov     [rbx], rdi
0x1400043cd  lea     rax, [rsi+rdi]
0x1400043d1  jmp     short loc_1400043DE
0x1400043d3  test    rbx, rbx
0x1400043d6  jz      short loc_1400043DB
0x1400043d8  mov     [r9], rbp
0x1400043db  mov     rax, rdi
0x1400043de  add     rsp, 28h
0x1400043e2  pop     rdi
0x1400043e3  pop     rsi
0x1400043e4  pop     rbp
0x1400043e5  pop     rbx
0x1400043e6  retn
```
