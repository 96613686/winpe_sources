# wil::details::WriteResultString<ushort const *>(uchar *,uchar *,ushort const *,ushort const * *)

- ea: `0x180004dd8`
- end: `0x180004e3f`
- name: `??$WriteResultString@PEBG@details@wil@@YAPEAEPEAE0PEBGPEAPEBG@Z`
- size: `103`
- prototype: `__int64 __fastcall(void *Destination)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180006d40`
- `0x180006e7c`

## callees

- `0x180004dd8`
- `0x180006c28`
- `0x180007b30`

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
0x180004dd8  push    rbx
0x180004dda  push    rbp
0x180004ddb  push    rsi
0x180004ddc  push    rdi
0x180004ddd  sub     rsp, 28h
0x180004de1  xor     ebp, ebp
0x180004de3  mov     rbx, r9
0x180004de6  mov     r10, rdx
0x180004de9  mov     rdi, rcx
0x180004dec  cmp     rcx, rdx
0x180004def  jz      short loc_180004E2B
0x180004df1  test    r8, r8
0x180004df4  jz      short loc_180004E2B
0x180004df6  cmp     [r8], bp
0x180004dfa  jz      short loc_180004E2B
0x180004dfc  mov     rcx, r8; this
0x180004dff  call    ?ResultStringSize@details@wil@@YA_KPEBG@Z; wil::details::ResultStringSize(ushort const *)
0x180004e04  sub     r10, rdi
0x180004e07  mov     rsi, rax
0x180004e0a  cmp     r10, rax
0x180004e0d  jb      short loc_180004E2B
0x180004e0f  mov     r9, rax; SourceSize
0x180004e12  mov     rdx, r10; DestinationSize
0x180004e15  mov     rcx, rdi; Destination
0x180004e18  call    memcpy_s
0x180004e1d  test    rbx, rbx
0x180004e20  jz      short loc_180004E25
0x180004e22  mov     [rbx], rdi
0x180004e25  lea     rax, [rsi+rdi]
0x180004e29  jmp     short loc_180004E36
0x180004e2b  test    rbx, rbx
0x180004e2e  jz      short loc_180004E33
0x180004e30  mov     [r9], rbp
0x180004e33  mov     rax, rdi
0x180004e36  add     rsp, 28h
0x180004e3a  pop     rdi
0x180004e3b  pop     rsi
0x180004e3c  pop     rbp
0x180004e3d  pop     rbx
0x180004e3e  retn
```
