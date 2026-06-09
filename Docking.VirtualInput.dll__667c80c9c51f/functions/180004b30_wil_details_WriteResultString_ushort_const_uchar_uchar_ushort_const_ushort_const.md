# wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)

- ea: `0x180004b30`
- end: `0x180004b97`
- name: `??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z`
- size: `103`
- prototype: `__int64 __fastcall(void *Destination)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180006850`
- `0x18000698c`

## callees

- `0x180004b30`
- `0x180006748`
- `0x1800076d8`

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
0x180004b30  push    rbx
0x180004b32  push    rbp
0x180004b33  push    rsi
0x180004b34  push    rdi
0x180004b35  sub     rsp, 28h
0x180004b39  xor     ebp, ebp
0x180004b3b  mov     rbx, r9
0x180004b3e  mov     r10, rdx
0x180004b41  mov     rdi, rcx
0x180004b44  cmp     rcx, rdx
0x180004b47  jz      short loc_180004B83
0x180004b49  test    r8, r8
0x180004b4c  jz      short loc_180004B83
0x180004b4e  cmp     [r8], bp
0x180004b52  jz      short loc_180004B83
0x180004b54  mov     rcx, r8; this
0x180004b57  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x180004b5c  sub     r10, rdi
0x180004b5f  mov     rsi, rax
0x180004b62  cmp     r10, rax
0x180004b65  jb      short loc_180004B83
0x180004b67  mov     r9, rax; SourceSize
0x180004b6a  mov     rdx, r10; DestinationSize
0x180004b6d  mov     rcx, rdi; Destination
0x180004b70  call    memcpy_s
0x180004b75  test    rbx, rbx
0x180004b78  jz      short loc_180004B7D
0x180004b7a  mov     [rbx], rdi
0x180004b7d  lea     rax, [rsi+rdi]
0x180004b81  jmp     short loc_180004B8E
0x180004b83  test    rbx, rbx
0x180004b86  jz      short loc_180004B8B
0x180004b88  mov     [r9], rbp
0x180004b8b  mov     rax, rdi
0x180004b8e  add     rsp, 28h
0x180004b92  pop     rdi
0x180004b93  pop     rsi
0x180004b94  pop     rbp
0x180004b95  pop     rbx
0x180004b96  retn
```
