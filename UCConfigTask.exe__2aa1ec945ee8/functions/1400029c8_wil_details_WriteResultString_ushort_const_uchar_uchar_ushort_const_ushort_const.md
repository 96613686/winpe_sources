# wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)

- ea: `0x1400029c8`
- end: `0x140002a2f`
- name: `??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z`
- size: `103`
- prototype: `char *__fastcall(unsigned __int16 *Destination, const unsigned __int16 *, wil::details *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140006070`
- `0x14000629c`

## callees

- `0x1400029c8`
- `0x140005efc`
- `0x140007a00`

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
0x1400029c8  push    rbx
0x1400029ca  push    rbp
0x1400029cb  push    rsi
0x1400029cc  push    rdi
0x1400029cd  sub     rsp, 28h
0x1400029d1  xor     ebp, ebp
0x1400029d3  mov     rbx, r9
0x1400029d6  mov     r10, rdx
0x1400029d9  mov     rdi, rcx
0x1400029dc  cmp     rcx, rdx
0x1400029df  jz      short loc_140002A1B
0x1400029e1  test    r8, r8
0x1400029e4  jz      short loc_140002A1B
0x1400029e6  cmp     [r8], bp
0x1400029ea  jz      short loc_140002A1B
0x1400029ec  mov     rcx, r8; this
0x1400029ef  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x1400029f4  sub     r10, rdi
0x1400029f7  mov     rsi, rax
0x1400029fa  cmp     r10, rax
0x1400029fd  jb      short loc_140002A1B
0x1400029ff  mov     r9, rax; SourceSize
0x140002a02  mov     rdx, r10; DestinationSize
0x140002a05  mov     rcx, rdi; Destination
0x140002a08  call    memcpy_s
0x140002a0d  test    rbx, rbx
0x140002a10  jz      short loc_140002A15
0x140002a12  mov     [rbx], rdi
0x140002a15  lea     rax, [rsi+rdi]
0x140002a19  jmp     short loc_140002A26
0x140002a1b  test    rbx, rbx
0x140002a1e  jz      short loc_140002A23
0x140002a20  mov     [r9], rbp
0x140002a23  mov     rax, rdi
0x140002a26  add     rsp, 28h
0x140002a2a  pop     rdi
0x140002a2b  pop     rsi
0x140002a2c  pop     rbp
0x140002a2d  pop     rbx
0x140002a2e  retn
```
