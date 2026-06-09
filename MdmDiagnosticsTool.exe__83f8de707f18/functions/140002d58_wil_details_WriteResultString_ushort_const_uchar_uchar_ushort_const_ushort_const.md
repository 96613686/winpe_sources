# wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)

- ea: `0x140002d58`
- end: `0x140002dc7`
- name: `??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z`
- size: `111`
- prototype: `__int64 __fastcall(void *Destination)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14000667c`
- `0x1400067c8`

## callees

- `0x140002d58`
- `0x14000657c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x140002d98`
- `msvcrt!memcpy_s` at `0x140002d98`

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
0x140002d58  push    rbx
0x140002d5a  push    rbp
0x140002d5b  push    rsi
0x140002d5c  push    rdi
0x140002d5d  sub     rsp, 28h
0x140002d61  xor     ebp, ebp
0x140002d63  mov     rbx, r9
0x140002d66  mov     r10, rdx
0x140002d69  mov     rdi, rcx
0x140002d6c  cmp     rcx, rdx
0x140002d6f  jz      short loc_140002DB2
0x140002d71  test    r8, r8
0x140002d74  jz      short loc_140002DB2
0x140002d76  cmp     [r8], bp
0x140002d7a  jz      short loc_140002DB2
0x140002d7c  mov     rcx, r8; this
0x140002d7f  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x140002d84  sub     r10, rdi
0x140002d87  mov     rsi, rax
0x140002d8a  cmp     r10, rax
0x140002d8d  jb      short loc_140002DB2
0x140002d8f  mov     r9, rax; SourceSize
0x140002d92  mov     rdx, r10; DestinationSize
0x140002d95  mov     rcx, rdi; Destination
0x140002d98  call    cs:__imp_memcpy_s
0x140002d9f  nop     dword ptr [rax+rax+00h]
0x140002da4  test    rbx, rbx
0x140002da7  jz      short loc_140002DAC
0x140002da9  mov     [rbx], rdi
0x140002dac  lea     rax, [rsi+rdi]
0x140002db0  jmp     short loc_140002DBD
0x140002db2  test    rbx, rbx
0x140002db5  jz      short loc_140002DBA
0x140002db7  mov     [r9], rbp
0x140002dba  mov     rax, rdi
0x140002dbd  add     rsp, 28h
0x140002dc1  pop     rdi
0x140002dc2  pop     rsi
0x140002dc3  pop     rbp
0x140002dc4  pop     rbx
0x140002dc5  retn
```
