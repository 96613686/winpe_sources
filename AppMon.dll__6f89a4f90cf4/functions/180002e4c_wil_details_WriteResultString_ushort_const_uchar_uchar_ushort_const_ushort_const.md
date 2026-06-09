# wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)

- ea: `0x180002e4c`
- end: `0x180002eb3`
- name: `??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z`
- size: `103`
- prototype: `__int64 __fastcall(void *Destination)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180004c3c`
- `0x180004d78`

## callees

- `0x180002e4c`
- `0x180004b78`
- `0x180005990`

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
0x180002e4c  push    rbx
0x180002e4e  push    rbp
0x180002e4f  push    rsi
0x180002e50  push    rdi
0x180002e51  sub     rsp, 28h
0x180002e55  xor     ebp, ebp
0x180002e57  mov     rbx, r9
0x180002e5a  mov     r10, rdx
0x180002e5d  mov     rdi, rcx
0x180002e60  cmp     rcx, rdx
0x180002e63  jz      short loc_180002E9F
0x180002e65  test    r8, r8
0x180002e68  jz      short loc_180002E9F
0x180002e6a  cmp     [r8], bp
0x180002e6e  jz      short loc_180002E9F
0x180002e70  mov     rcx, r8; this
0x180002e73  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x180002e78  sub     r10, rdi
0x180002e7b  mov     rsi, rax
0x180002e7e  cmp     r10, rax
0x180002e81  jb      short loc_180002E9F
0x180002e83  mov     r9, rax; SourceSize
0x180002e86  mov     rdx, r10; DestinationSize
0x180002e89  mov     rcx, rdi; Destination
0x180002e8c  call    memcpy_s
0x180002e91  test    rbx, rbx
0x180002e94  jz      short loc_180002E99
0x180002e96  mov     [rbx], rdi
0x180002e99  lea     rax, [rsi+rdi]
0x180002e9d  jmp     short loc_180002EAA
0x180002e9f  test    rbx, rbx
0x180002ea2  jz      short loc_180002EA7
0x180002ea4  mov     [r9], rbp
0x180002ea7  mov     rax, rdi
0x180002eaa  add     rsp, 28h
0x180002eae  pop     rdi
0x180002eaf  pop     rsi
0x180002eb0  pop     rbp
0x180002eb1  pop     rbx
0x180002eb2  retn
```
