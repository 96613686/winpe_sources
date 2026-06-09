# wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)

- ea: `0x140002ef8`
- end: `0x140002f60`
- name: `??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z`
- size: `104`
- prototype: `char *__fastcall(unsigned __int16 *Destination, const unsigned __int16 *, wil::details *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14000a288`
- `0x14000a4b0`

## callees

- `0x140002ef8`
- `0x14000a0c4`

## import_xrefs

- `msvcrt!memcpy_s` at `0x140002f38`
- `msvcrt!memcpy_s` at `0x140002f38`

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
0x140002ef8  push    rbx
0x140002efa  push    rbp
0x140002efb  push    rsi
0x140002efc  push    rdi
0x140002efd  sub     rsp, 28h
0x140002f01  xor     ebp, ebp
0x140002f03  mov     rbx, r9
0x140002f06  mov     r10, rdx
0x140002f09  mov     rdi, rcx
0x140002f0c  cmp     rcx, rdx
0x140002f0f  jz      short loc_140002F4C
0x140002f11  test    r8, r8
0x140002f14  jz      short loc_140002F4C
0x140002f16  cmp     [r8], bp
0x140002f1a  jz      short loc_140002F4C
0x140002f1c  mov     rcx, r8; this
0x140002f1f  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x140002f24  sub     r10, rdi
0x140002f27  mov     rsi, rax
0x140002f2a  cmp     r10, rax
0x140002f2d  jb      short loc_140002F4C
0x140002f2f  mov     r9, rax; SourceSize
0x140002f32  mov     rdx, r10; DestinationSize
0x140002f35  mov     rcx, rdi; Destination
0x140002f38  call    cs:__imp_memcpy_s
0x140002f3e  test    rbx, rbx
0x140002f41  jz      short loc_140002F46
0x140002f43  mov     [rbx], rdi
0x140002f46  lea     rax, [rsi+rdi]
0x140002f4a  jmp     short loc_140002F57
0x140002f4c  test    rbx, rbx
0x140002f4f  jz      short loc_140002F54
0x140002f51  mov     [r9], rbp
0x140002f54  mov     rax, rdi
0x140002f57  add     rsp, 28h
0x140002f5b  pop     rdi
0x140002f5c  pop     rsi
0x140002f5d  pop     rbp
0x140002f5e  pop     rbx
0x140002f5f  retn
```
