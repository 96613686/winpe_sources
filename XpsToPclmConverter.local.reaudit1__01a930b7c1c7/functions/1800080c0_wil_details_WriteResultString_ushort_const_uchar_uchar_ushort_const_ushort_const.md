# wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)

- ea: `0x1800080c0`
- end: `0x180008127`
- name: `??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z`
- size: `103`
- prototype: `__int64 __fastcall(void *Destination)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000b960`
- `0x18000bb8c`

## callees

- `0x1800080c0`
- `0x18000b7f8`
- `0x18000d374`

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
0x1800080c0  push    rbx
0x1800080c2  push    rbp
0x1800080c3  push    rsi
0x1800080c4  push    rdi
0x1800080c5  sub     rsp, 28h
0x1800080c9  xor     ebp, ebp
0x1800080cb  mov     rbx, r9
0x1800080ce  mov     r10, rdx
0x1800080d1  mov     rdi, rcx
0x1800080d4  cmp     rcx, rdx
0x1800080d7  jz      short loc_180008113
0x1800080d9  test    r8, r8
0x1800080dc  jz      short loc_180008113
0x1800080de  cmp     [r8], bp
0x1800080e2  jz      short loc_180008113
0x1800080e4  mov     rcx, r8; this
0x1800080e7  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x1800080ec  sub     r10, rdi
0x1800080ef  mov     rsi, rax
0x1800080f2  cmp     r10, rax
0x1800080f5  jb      short loc_180008113
0x1800080f7  mov     r9, rax; SourceSize
0x1800080fa  mov     rdx, r10; DestinationSize
0x1800080fd  mov     rcx, rdi; Destination
0x180008100  call    memcpy_s
0x180008105  test    rbx, rbx
0x180008108  jz      short loc_18000810D
0x18000810a  mov     [rbx], rdi
0x18000810d  lea     rax, [rsi+rdi]
0x180008111  jmp     short loc_18000811E
0x180008113  test    rbx, rbx
0x180008116  jz      short loc_18000811B
0x180008118  mov     [r9], rbp
0x18000811b  mov     rax, rdi
0x18000811e  add     rsp, 28h
0x180008122  pop     rdi
0x180008123  pop     rsi
0x180008124  pop     rbp
0x180008125  pop     rbx
0x180008126  retn
```
